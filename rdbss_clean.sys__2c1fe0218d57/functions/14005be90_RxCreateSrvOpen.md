# RxCreateSrvOpen

- ea: `0x14005be90`
- end: `0x14005c44a`
- name: `RxCreateSrvOpen`
- size: `1466`
- prototype: `PSRV_OPEN __stdcall(PV_NET_ROOT VNetRoot, PFCB Fcb)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14005a850`

## callees

- `0x140015230`
- `0x140016d40`
- `0x140016e70`
- `0x140017370`
- `0x14001810c`
- `0x1400581a0`
- `0x14005be90`
- `0x14005c6c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14005c1b7`
- `ntoskrnl!KeBugCheckEx` at `0x14005c2b4`
- `ntoskrnl!KeBugCheckEx` at `0x14005c37c`
- `ntoskrnl!KeBugCheckEx` at `0x14005c1b7`
- `ntoskrnl!KeBugCheckEx` at `0x14005c2b4`
- `ntoskrnl!KeBugCheckEx` at `0x14005c37c`
- `ntoskrnl!KeReleaseMutex` at `0x14005c0be`
- `ntoskrnl!KeReleaseMutex` at `0x14005c0be`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c267`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005c267`

## string_xrefs

- `0x14007af26`: `RxCreateSrvOpen`

## pseudocode

```c
PSRV_OPEN __stdcall RxCreateSrvOpen(PV_NET_ROOT VNetRoot, PFCB Fcb)
{
  unsigned __int16 *v3; // rsi
  PUNICODE_STRING pUserDomainName; // r15
  __int64 v5; // rcx
  int Buffer_high; // eax
  POOL_TYPE v7; // r8d
  struct _SRV_OPEN *AlreadyAllocatedObject; // rdi
  int v9; // eax
  PUNICODE_STRING *v10; // rdx
  char v11; // r13
  signed __int64 v12; // rbx
  signed __int64 v13; // r14
  __int16 v14; // dx
  ULONG_PTR v15; // r9
  unsigned int v16; // edx
  __int64 v17; // r8
  __int64 v18; // rcx
  unsigned __int16 *v19; // rbx
  _DWORD *v20; // r12
  __int64 v21; // rcx
  unsigned __int16 **v22; // rax
  unsigned int v23; // edx
  unsigned int v24; // edx
  unsigned int v25; // edx
  unsigned int v26; // edx
  signed __int64 v28; // [rsp+98h] [rbp+8h]

  v3 = (unsigned __int16 *)*((_QWORD *)&VNetRoot[2].1 + 10);
  pUserDomainName = VNetRoot->pUserDomainName;
  v5 = *((_QWORD *)v3 + 4);
  Buffer_high = HIDWORD(pUserDomainName[9].Buffer);
  v7 = 64;
  if ( (Buffer_high & 4) == 0 )
    v7 = 256;
  AlreadyAllocatedObject = (struct _SRV_OPEN *)pUserDomainName[25].Buffer;
  if ( AlreadyAllocatedObject
    && Buffer_high >= 0
    && (*(_DWORD *)(&AlreadyAllocatedObject->1 + 3) & 0x10000) == 0
    && AlreadyAllocatedObject->ScavengerFinalizationList.Flink == &AlreadyAllocatedObject->ScavengerFinalizationList )
  {
    RxAllocateFcbObject(*(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(v5 + 32) + 48LL), 0xEB1Du, v7, 0, AlreadyAllocatedObject);
    HIDWORD(pUserDomainName[9].Buffer) |= 0x80000000;
    v9 = 196608;
  }
  else
  {
    AlreadyAllocatedObject = (struct _SRV_OPEN *)RxAllocateFcbObject(
                                                   *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(v5 + 32) + 48LL),
                                                   0xEB1Cu,
                                                   v7,
                                                   0,
                                                   0);
    v9 = 0;
  }
  if ( (BYTE2(VNetRoot[2].PrefixEntry.Prefix.Buffer) & 0x40) != 0 )
    v9 |= 0x1080u;
  if ( AlreadyAllocatedObject )
  {
    *((_DWORD *)&AlreadyAllocatedObject->1 + 18) = v9;
    AlreadyAllocatedObject->Context2 = pUserDomainName;
    *((_QWORD *)&AlreadyAllocatedObject->1 + 10) = (char *)pUserDomainName + 360;
    AlreadyAllocatedObject->NodeReferenceCount = 1;
    if ( _InterlockedIncrement((volatile signed __int32 *)&pUserDomainName[9].Buffer) == 1 )
      KeBugCheckEx(0x27u, 0xFCB003A5, (ULONG_PTR)pUserDomainName, 1u, 0);
    v10 = *(PUNICODE_STRING **)&pUserDomainName[17].Length;
    if ( *v10 != (PUNICODE_STRING)&pUserDomainName[16].Buffer )
LABEL_10:
      __fastfail(3u);
    AlreadyAllocatedObject->ScavengerFinalizationList.Flink = (struct _LIST_ENTRY *)&pUserDomainName[16].Buffer;
    AlreadyAllocatedObject->ScavengerFinalizationList.Blink = (struct _LIST_ENTRY *)v10;
    *v10 = (PUNICODE_STRING)&AlreadyAllocatedObject->ScavengerFinalizationList;
    *(_QWORD *)&pUserDomainName[17].Length = &AlreadyAllocatedObject->ScavengerFinalizationList;
    AlreadyAllocatedObject->ShadowContext = (PMRXSHADOW_SRV_OPEN)v3;
    v11 = 0;
    v12 = *(_QWORD *)v3;
    v28 = *(_QWORD *)v3;
    do
    {
      v13 = v12;
      if ( (v12 & 0x1000) != 0 )
      {
        LOWORD(v28) = v12 & 0xEFFF;
        if ( !v11 )
        {
          KeWaitForSingleObject(&RxScavengerMutex, Executive, 0, 0, 0);
          v11 = 1;
        }
      }
      else
      {
        HIDWORD(v28) = HIDWORD(v12) + 1;
      }
      v14 = v12;
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)v3, v28, v12);
      v28 = v12;
    }
    while ( v12 != v13 );
    if ( (v14 & 0x1000) == 0 )
      goto LABEL_26;
    v15 = *v3;
    v16 = *v3 & 0xEFFF;
    if ( v16 == 60178 )
    {
      v17 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 4) + 32LL) + 48LL);
LABEL_18:
      if ( v16 == 60178 )
      {
        v18 = 20;
      }
      else
      {
        v23 = v16 - 60176;
        if ( v23 )
        {
          v24 = v23 - 1;
          if ( v24 )
          {
            v25 = v24 - 2;
            if ( v25 )
            {
              v26 = v25 - 9;
              if ( v26 )
              {
                if ( v26 != 276 )
                  KeBugCheckEx(0x27u, 0x1021Cu, (ULONG_PTR)v3, v15, 0);
                v18 = 28;
              }
              else
              {
                v18 = 24;
              }
            }
            else
            {
              v18 = 32;
            }
          }
          else
          {
            v18 = 16;
          }
        }
        else
        {
          v18 = 12;
        }
      }
      v19 = v3 + 8;
      if ( *(unsigned __int16 **)v19 == v19 )
        KeBugCheckEx(0x27u, 0x10225u, (ULONG_PTR)v3, v15, 0);
      v20 = (_DWORD *)(v18 + *(_QWORD *)(v17 + 832));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_7cd1a4145ac63a5107541aa80a8a6609_Traceguids, v3);
      }
      _InterlockedAnd((volatile signed __int32 *)v3, 0xFFFFEFFF);
      --*v20;
      v21 = *(_QWORD *)v19;
      if ( *(unsigned __int16 **)(*(_QWORD *)v19 + 8LL) != v19 )
        goto LABEL_10;
      v22 = (unsigned __int16 **)*((_QWORD *)v3 + 3);
      if ( *v22 != v19 )
        goto LABEL_10;
      *v22 = (unsigned __int16 *)v21;
      *(_QWORD *)(v21 + 8) = v22;
      *((_QWORD *)v3 + 3) = v3 + 8;
      *(_QWORD *)v19 = v19;
LABEL_26:
      if ( v11 )
        KeReleaseMutex(&RxScavengerMutex, 0);
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v3 + 4) + 64LL));
      _InterlockedIncrement((volatile signed __int32 *)v3 + 15);
      AlreadyAllocatedObject->SrvOpenKeyList.Flink = (struct _LIST_ENTRY *)&AlreadyAllocatedObject->InternalFobx;
      AlreadyAllocatedObject->InternalFobx = (PFOBX)&AlreadyAllocatedObject->InternalFobx;
      AlreadyAllocatedObject->FobxList.Blink = &AlreadyAllocatedObject->FobxList;
      AlreadyAllocatedObject->FobxList.Flink = &AlreadyAllocatedObject->FobxList;
      AlreadyAllocatedObject->Context = &AlreadyAllocatedObject->VNetRoot;
      AlreadyAllocatedObject->pVNetRoot = (PMRX_V_NET_ROOT)&AlreadyAllocatedObject->VNetRoot;
      AlreadyAllocatedObject->SrvOpenQLinks.Flink = (struct _LIST_ENTRY *)-1LL;
      AlreadyAllocatedObject->SrvOpenQLinks.Blink = (struct _LIST_ENTRY *)-1LL;
      AlreadyAllocatedObject[1].0 = (MRX_NORMAL_NODE_HEADER)&AlreadyAllocatedObject->OpenStatus;
      *(_QWORD *)&AlreadyAllocatedObject->OpenStatus = &AlreadyAllocatedObject->OpenStatus;
      AlreadyAllocatedObject[1].pFcb = (PMRX_FCB)AlreadyAllocatedObject;
      goto LABEL_29;
    }
    if ( v16 <= 0xEB1C )
    {
      switch ( v16 )
      {
        case 0xEB1Cu:
          v17 = *(_QWORD *)(*((_QWORD *)v3 + 4) + 400LL);
          goto LABEL_18;
        case 0xEB10u:
          v17 = *((_QWORD *)v3 + 6);
          goto LABEL_18;
        case 0xEB11u:
          v17 = *(_QWORD *)(*((_QWORD *)v3 + 4) + 48LL);
          goto LABEL_18;
        case 0xEB13u:
          v17 = *((_QWORD *)v3 + 10);
          goto LABEL_18;
      }
    }
    else
    {
      if ( v16 == 60449 || v16 == 60450 )
      {
        v17 = *((_QWORD *)v3 + 50);
        goto LABEL_18;
      }
      if ( v16 == 60464 )
      {
        v17 = *((_QWORD *)v3 + 31);
        goto LABEL_18;
      }
    }
    v17 = 0;
    goto LABEL_18;
  }
LABEL_29:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 64, &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids);
  }
  if ( AlreadyAllocatedObject
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      65,
      &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
      AlreadyAllocatedObject,
      AlreadyAllocatedObject->Context2);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      66,
      &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
      AlreadyAllocatedObject);
  }
  return AlreadyAllocatedObject;
}

```

## disassembly

```asm
0x14005be90  mov     [rsp+arg_10], rbx
0x14005be95  mov     [rsp+arg_18], rsi
0x14005be9a  push    rdi
0x14005be9b  push    r12
0x14005be9d  push    r13
0x14005be9f  push    r14
0x14005bea1  push    r15
0x14005bea3  sub     rsp, 40h
0x14005bea7  mov     rbx, rcx
0x14005beaa  mov     rsi, [rcx+290h]
0x14005beb1  mov     r15, [rcx+38h]
0x14005beb5  xor     r14d, r14d
0x14005beb8  mov     [rsp+68h+var_30], r14
0x14005bebd  mov     rcx, [rsi+20h]
0x14005bec1  mov     eax, [r15+9Ch]
0x14005bec8  test    al, 4
0x14005beca  mov     r8d, 40h ; '@'
0x14005bed0  mov     r12d, 100h
0x14005bed6  cmovz   r8d, r12d; PoolType
0x14005beda  mov     rdi, [r15+198h]
0x14005bee1  mov     [rsp+68h+var_30], rdi
0x14005bee6  test    rdi, rdi
0x14005bee9  jnz     loc_14005C2CD
0x14005beef  mov     edx, 0EB1Ch; NodeType
0x14005bef4  mov     rcx, [rcx+20h]
0x14005bef8  mov     [rsp+68h+AlreadyAllocatedObject], r14; AlreadyAllocatedObject
0x14005befd  xor     r9d, r9d; NameSize
0x14005bf00  mov     rcx, [rcx+30h]; RxDeviceObject
0x14005bf04  call    RxAllocateFcbObject
0x14005bf09  mov     rdi, rax
0x14005bf0c  mov     [rsp+68h+var_30], rax
0x14005bf11  mov     eax, r14d
0x14005bf14  mov     [rsp+68h+var_34], eax
0x14005bf18  test    byte ptr [rbx+2EAh], 40h
0x14005bf1f  jz      short loc_14005BF2A
0x14005bf21  or      eax, 1080h
0x14005bf26  mov     [rsp+68h+var_34], eax
0x14005bf2a  test    rdi, rdi
0x14005bf2d  jz      loc_14005C2C1
0x14005bf33  mov     [rdi+48h], eax
0x14005bf36  mov     [rdi+20h], r15
0x14005bf3a  lea     rax, [r15+168h]
0x14005bf41  mov     [rdi+50h], rax
0x14005bf45  mov     dword ptr [rdi+4], 1
0x14005bf4c  mov     eax, 1
0x14005bf51  lock xadd [r15+98h], eax
0x14005bf5a  inc     eax
0x14005bf5c  cmp     eax, 1
0x14005bf5f  jz      loc_14005C29C
0x14005bf65  lea     rcx, [r15+108h]
0x14005bf6c  mov     rdx, [rcx+8]
0x14005bf70  cmp     [rdx], rcx
0x14005bf73  jz      short loc_14005BF7C
0x14005bf75  mov     ecx, 3
0x14005bf7a  int     29h; Win8: RtlFailFast(ecx)
0x14005bf7c  lea     rax, [rdi+88h]
0x14005bf83  mov     [rax], rcx
0x14005bf86  mov     [rax+8], rdx
0x14005bf8a  mov     [rdx], rax
0x14005bf8d  mov     [rcx+8], rax
0x14005bf91  mov     [rdi+28h], rsi
0x14005bf95  mov     [rsp+68h+arg_8], r14
0x14005bf9a  mov     [rsp+68h+arg_0], r14
0x14005bf9f  xor     r13b, r13b
0x14005bfa2  mov     [rsp+68h+var_38], r13b
0x14005bfa7  mov     rbx, [rsi]
0x14005bfaa  mov     [rsp+68h+arg_0], rbx
0x14005bfaf  mov     ecx, 0EFFFh
0x14005bfb4  mov     r8d, 1000h
0x14005bfba  nop     word ptr [rax+rax+00h]
0x14005bfc0  mov     [rsp+68h+arg_8], rbx
0x14005bfc5  mov     r14, rbx
0x14005bfc8  movzx   eax, bx
0x14005bfcb  test    r8w, bx
0x14005bfcf  jnz     loc_14005C23E
0x14005bfd5  mov     rax, rbx
0x14005bfd8  shr     rax, 20h
0x14005bfdc  inc     eax
0x14005bfde  mov     dword ptr [rsp+68h+arg_0+4], eax
0x14005bfe2  mov     rdx, rbx
0x14005bfe5  mov     rcx, [rsp+68h+arg_0]
0x14005bfea  mov     rax, rbx
0x14005bfed  lock cmpxchg [rsi], rcx
0x14005bff2  mov     rbx, rax
0x14005bff5  mov     [rsp+68h+arg_0], rax
0x14005bffa  cmp     rax, r14
0x14005bffd  mov     ecx, 0EFFFh
0x14005c002  jnz     short loc_14005BFC0
0x14005c004  test    r8w, dx
0x14005c008  jz      loc_14005C290
0x14005c00e  movzx   r9d, word ptr [rsi]; BugCheckParameter3
0x14005c012  mov     edx, r9d
0x14005c015  btr     edx, 0Ch
0x14005c019  cmp     edx, 0EB12h
0x14005c01f  jnz     loc_14005C1C4
0x14005c025  mov     rax, [rsi+20h]
0x14005c029  mov     rcx, [rax+20h]
0x14005c02d  mov     r8, [rcx+30h]
0x14005c031  cmp     edx, 0EB12h
0x14005c037  jnz     loc_14005C172
0x14005c03d  mov     ecx, 14h
0x14005c042  lea     rbx, [rsi+10h]
0x14005c046  cmp     [rbx], rbx
0x14005c049  jz      loc_14005C366
0x14005c04f  mov     r12, [r8+340h]
0x14005c056  add     r12, rcx
0x14005c059  lea     r14, WPP_GLOBAL_Control
0x14005c060  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c067  cmp     rcx, r14
0x14005c06a  jz      short loc_14005C077
0x14005c06c  mov     eax, [rcx+2Ch]
0x14005c06f  test    al, al
0x14005c071  js      loc_14005C389
0x14005c077  lock and dword ptr [rsi], 0FFFFEFFFh
0x14005c07e  dec     dword ptr [r12]
0x14005c082  mov     rcx, [rbx]
0x14005c085  cmp     [rcx+8], rbx
0x14005c089  jnz     loc_14005BF75
0x14005c08f  mov     rax, [rbx+8]
0x14005c093  cmp     [rax], rbx
0x14005c096  jnz     loc_14005BF75
0x14005c09c  mov     [rax], rcx
0x14005c09f  mov     [rcx+8], rax
0x14005c0a3  mov     [rbx+8], rbx
0x14005c0a7  mov     [rbx], rbx
0x14005c0aa  mov     r12d, 100h
0x14005c0b0  test    r13b, r13b
0x14005c0b3  jz      short loc_14005C0CF
0x14005c0b5  xor     edx, edx; Wait
0x14005c0b7  lea     rcx, RxScavengerMutex; Mutex
0x14005c0be  call    cs:__imp_KeReleaseMutex
0x14005c0c5  nop     dword ptr [rax+rax+00h]
0x14005c0ca  mov     [rsp+68h+var_38], 0
0x14005c0cf  mov     rax, [rsi+20h]
0x14005c0d3  lock inc dword ptr [rax+40h]
0x14005c0d7  lock inc dword ptr [rsi+3Ch]
0x14005c0db  lea     rax, [rdi+0B8h]
0x14005c0e2  mov     [rax+8], rax
0x14005c0e6  mov     [rax], rax
0x14005c0e9  lea     rax, [rdi+0A8h]
0x14005c0f0  mov     [rax+8], rax
0x14005c0f4  mov     [rax], rax
0x14005c0f7  lea     rax, [rdi+10h]
0x14005c0fb  mov     [rax+8], rax
0x14005c0ff  mov     [rax], rax
0x14005c102  mov     qword ptr [rdi+68h], 0FFFFFFFFFFFFFFFFh
0x14005c10a  mov     qword ptr [rdi+70h], 0FFFFFFFFFFFFFFFFh
0x14005c112  lea     rax, [rdi+0D0h]
0x14005c119  mov     [rax+8], rax
0x14005c11d  mov     [rax], rax
0x14005c120  mov     [rdi+0E0h], rdi
0x14005c127  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c12e  cmp     rcx, r14
0x14005c131  jz      loc_14005C3BA
0x14005c137  test    [rcx+2Ch], r12d
0x14005c13b  jz      loc_14005C3BA
0x14005c141  cmp     byte ptr [rcx+29h], 4
0x14005c145  jb      loc_14005C3BA
0x14005c14b  mov     edx, 40h ; '@'
0x14005c150  mov     [rsp+68h+var_40], rsi
0x14005c155  mov     [rsp+68h+AlreadyAllocatedObject], r15
0x14005c15a  mov     r9, rdi
0x14005c15d  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14005c164  mov     rcx, [rcx+18h]
0x14005c168  call    WPP_SF_qqq
0x14005c16d  jmp     loc_14005C3BA
0x14005c172  sub     edx, 0EB10h
0x14005c178  jz      short loc_14005C1F7
0x14005c17a  sub     edx, 1
0x14005c17d  jz      loc_14005C35C
0x14005c183  sub     edx, 2
0x14005c186  jz      loc_14005C219
0x14005c18c  sub     edx, 9
0x14005c18f  jz      loc_14005C352
0x14005c195  cmp     edx, 114h
0x14005c19b  jz      loc_14005C286
0x14005c1a1  mov     [rsp+68h+AlreadyAllocatedObject], 0; BugCheckParameter4
0x14005c1aa  mov     r8, rsi; BugCheckParameter2
0x14005c1ad  mov     edx, 1021Ch; BugCheckParameter1
0x14005c1b2  mov     ecx, 27h ; '''; BugCheckCode
0x14005c1b7  call    cs:__imp_KeBugCheckEx
0x14005c1c4  cmp     edx, 0EB1Ch
0x14005c1ca  jbe     short loc_14005C201
0x14005c1cc  mov     eax, edx
0x14005c1ce  sub     eax, 0EC21h
0x14005c1d3  jz      loc_14005C346
0x14005c1d9  sub     eax, 1
0x14005c1dc  jz      loc_14005C346
0x14005c1e2  cmp     eax, 0Eh
0x14005c1e5  jnz     loc_14005C33E
0x14005c1eb  mov     r8, [rsi+0F8h]
0x14005c1f2  jmp     loc_14005C031
0x14005c1f7  mov     ecx, 0Ch
0x14005c1fc  jmp     loc_14005C042
0x14005c201  jz      loc_14005C32E
0x14005c207  mov     eax, edx
0x14005c209  sub     eax, 0EB10h
0x14005c20e  jnz     short loc_14005C223
0x14005c210  mov     r8, [rsi+30h]
0x14005c214  jmp     loc_14005C031
0x14005c219  mov     ecx, 20h ; ' '
0x14005c21e  jmp     loc_14005C042
0x14005c223  sub     eax, 1
0x14005c226  jz      loc_14005C321
0x14005c22c  cmp     eax, 2
0x14005c22f  jnz     loc_14005C33E
0x14005c235  mov     r8, [rsi+50h]
0x14005c239  jmp     loc_14005C031
0x14005c23e  and     ax, cx
0x14005c241  mov     word ptr [rsp+68h+arg_0], ax
0x14005c246  test    r13b, r13b
0x14005c249  jnz     loc_14005BFE2
0x14005c24f  mov     [rsp+68h+AlreadyAllocatedObject], 0; Timeout
0x14005c258  xor     r9d, r9d; Alertable
0x14005c25b  xor     r8d, r8d; WaitMode
0x14005c25e  xor     edx, edx; WaitReason
0x14005c260  lea     rcx, RxScavengerMutex; Object
0x14005c267  call    cs:__imp_KeWaitForSingleObject
0x14005c26e  nop     dword ptr [rax+rax+00h]
0x14005c273  mov     r13b, 1
0x14005c276  mov     [rsp+68h+var_38], r13b
0x14005c27b  mov     r8d, 1000h
0x14005c281  jmp     loc_14005BFE2
0x14005c286  mov     ecx, 1Ch
0x14005c28b  jmp     loc_14005C042
0x14005c290  lea     r14, WPP_GLOBAL_Control
0x14005c297  jmp     loc_14005C0B0
0x14005c29c  mov     [rsp+68h+AlreadyAllocatedObject], r14; BugCheckParameter4
0x14005c2a1  mov     r9d, 1; BugCheckParameter3
0x14005c2a7  mov     r8, r15; BugCheckParameter2
0x14005c2aa  mov     edx, 0FCB003A5h; BugCheckParameter1
0x14005c2af  mov     ecx, 27h ; '''; BugCheckCode
0x14005c2b4  call    cs:__imp_KeBugCheckEx
0x14005c2c1  lea     r14, WPP_GLOBAL_Control
0x14005c2c8  jmp     loc_14005C127
0x14005c2cd  test    eax, eax
0x14005c2cf  js      loc_14005BEEF
0x14005c2d5  test    dword ptr [rdi+48h], 10000h
0x14005c2dc  jnz     loc_14005BEEF
0x14005c2e2  lea     rax, [rdi+88h]
0x14005c2e9  cmp     [rax], rax
0x14005c2ec  jnz     loc_14005BEEF
0x14005c2f2  mov     edx, 0EB1Dh; NodeType
0x14005c2f7  mov     rcx, [rcx+20h]
0x14005c2fb  mov     [rsp+68h+AlreadyAllocatedObject], rdi; AlreadyAllocatedObject
0x14005c300  xor     r9d, r9d; NameSize
0x14005c303  mov     rcx, [rcx+30h]; RxDeviceObject
0x14005c307  call    RxAllocateFcbObject
0x14005c30c  or      dword ptr [r15+9Ch], 80000000h
0x14005c317  mov     eax, 30000h
0x14005c31c  jmp     loc_14005BF14
0x14005c321  mov     rax, [rsi+20h]
0x14005c325  mov     r8, [rax+30h]
0x14005c329  jmp     loc_14005C031
0x14005c32e  mov     rax, [rsi+20h]
0x14005c332  mov     r8, [rax+190h]
0x14005c339  jmp     loc_14005C031
0x14005c33e  xor     r8d, r8d
0x14005c341  jmp     loc_14005C031
0x14005c346  mov     r8, [rsi+190h]
0x14005c34d  jmp     loc_14005C031
0x14005c352  mov     ecx, 18h
0x14005c357  jmp     loc_14005C042
0x14005c35c  mov     ecx, 10h
0x14005c361  jmp     loc_14005C042
0x14005c366  mov     [rsp+68h+AlreadyAllocatedObject], 0; BugCheckParameter4
0x14005c36f  mov     r8, rsi; BugCheckParameter2
0x14005c372  mov     edx, 10225h; BugCheckParameter1
0x14005c377  mov     ecx, 27h ; '''; BugCheckCode
0x14005c37c  call    cs:__imp_KeBugCheckEx
0x14005c389  cmp     byte ptr [rcx+29h], 2
0x14005c38d  jb      loc_14005C077
0x14005c393  btr     r9d, 0Ch
0x14005c398  mov     edx, 0Eh
0x14005c39d  mov     dword ptr [rsp+68h+AlreadyAllocatedObject], r9d
0x14005c3a2  mov     r9, rsi
0x14005c3a5  lea     r8, WPP_7cd1a4145ac63a5107541aa80a8a6609_Traceguids
0x14005c3ac  mov     rcx, [rcx+18h]
0x14005c3b0  call    WPP_SF_qD
0x14005c3b5  jmp     loc_14005C077
0x14005c3ba  test    rdi, rdi
0x14005c3bd  jz      short loc_14005C3D1
0x14005c3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c3c6  cmp     rcx, r14
0x14005c3c9  jz      short loc_14005C3D1
0x14005c3cb  test    [rcx+2Ch], r12d
0x14005c3cf  jnz     short loc_14005C401
0x14005c3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c3d8  cmp     rcx, r14
0x14005c3db  jz      short loc_14005C3E3
0x14005c3dd  test    [rcx+2Ch], r12d
0x14005c3e1  jnz     short loc_14005C42A
0x14005c3e3  mov     rax, rdi
0x14005c3e6  lea     r11, [rsp+68h+var_28]
0x14005c3eb  mov     rbx, [r11+40h]
0x14005c3ef  mov     rsi, [r11+48h]
0x14005c3f3  mov     rsp, r11
0x14005c3f6  pop     r15
0x14005c3f8  pop     r14
0x14005c3fa  pop     r13
  ... truncated ...
```
