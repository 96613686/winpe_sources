# SmbShellEnumerateConnections

- ea: `0x140049e60`
- end: `0x14004a5ab`
- name: `SmbShellEnumerateConnections`
- size: `1867`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x14001f0e0`

## callees

- `0x140010f94`
- `0x14003838c`
- `0x1400383d0`
- `0x140039fa8`
- `0x140049e60`
- `0x140059dc0`
- `0x140059df0`
- `0x140059ea0`
- `0x14007e128`
- `0x14007e164`
- `0x14007e1e8`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004a2c9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004a2c9`
- `ntoskrnl!IoGetRequestorProcess` at `0x140049fe1`
- `ntoskrnl!IoGetRequestorProcess` at `0x140049fe1`
- `ntoskrnl!ProbeForWrite` at `0x14004a048`
- `ntoskrnl!ProbeForWrite` at `0x14004a061`
- `ntoskrnl!ProbeForWrite` at `0x14004a048`
- `ntoskrnl!ProbeForWrite` at `0x14004a061`
- `ntoskrnl!KeStackAttachProcess` at `0x140049ff8`
- `ntoskrnl!KeStackAttachProcess` at `0x140049ff8`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14004a598`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14004a598`
- `ntoskrnl!IoIs32bitProcess` at `0x14004a14d`
- `ntoskrnl!IoIs32bitProcess` at `0x14004a14d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a584`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a960`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004a584`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005a960`
- `ntoskrnl!IoGetSiloParameters` at `0x140049f1a`
- `ntoskrnl!IoGetSiloParameters` at `0x140049f1a`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x140049f2f`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x140049f2f`
- `ntoskrnl!PsIsHostSilo` at `0x140049f46`
- `ntoskrnl!PsIsHostSilo` at `0x140049f46`
- `rdbss!RxMapUserBuffer` at `0x14004a00b`
- `rdbss!RxMapUserBuffer` at `0x14004a00b`
- `rdbss!RxPrefixTableEndLookup` at `0x14004a562`
- `rdbss!RxPrefixTableEndLookup` at `0x14005a934`
- `rdbss!RxPrefixTableEndLookup` at `0x14004a562`
- `rdbss!RxPrefixTableEndLookup` at `0x14005a934`
- `rdbss!RxPrefixTableLookupNextObject` at `0x14004a4a9`
- `rdbss!RxPrefixTableLookupNextObject` at `0x14004a4a9`
- `rdbss!RxPrefixTableLookupFirstObject` at `0x14004a302`
- `rdbss!RxPrefixTableLookupFirstObject` at `0x14004a302`

## pseudocode

```c
__int64 __fastcall SmbShellEnumerateConnections(PRX_CONTEXT RxContext)
{
  PIRP CurrentIrp; // rcx
  KPROCESSOR_MODE RequestorMode; // r12
  int v4; // ebx
  _DWORD *v5; // r13
  wchar_t *Buffer; // r15
  SIZE_T v7; // r14
  __int64 SiloParameters; // rax
  struct _KPROCESS *RequestorProcess; // rax
  PVOID v11; // rbx
  unsigned int v12; // ebx
  _DWORD *v13; // rbx
  int ULongFromUser; // eax
  unsigned int v15; // r13d
  unsigned int v16; // eax
  unsigned int *v17; // r15
  unsigned int *v18; // r14
  __int64 i; // rax
  __int64 v20; // rbx
  int v21; // eax
  unsigned int v22; // ebx
  unsigned int *v23; // rcx
  int v24; // [rsp+38h] [rbp-120h]
  char v25; // [rsp+50h] [rbp-108h]
  char v26; // [rsp+51h] [rbp-107h]
  unsigned int Length; // [rsp+58h] [rbp-100h] BYREF
  bool Length_4; // [rsp+5Ch] [rbp-FCh]
  unsigned int v29; // [rsp+60h] [rbp-F8h]
  unsigned int v30; // [rsp+64h] [rbp-F4h]
  unsigned int v31; // [rsp+68h] [rbp-F0h]
  unsigned int v32; // [rsp+6Ch] [rbp-ECh] BYREF
  __int64 ULong64FromUser; // [rsp+70h] [rbp-E8h] BYREF
  int v34; // [rsp+78h] [rbp-E0h]
  int v35; // [rsp+7Ch] [rbp-DCh]
  PVOID v36; // [rsp+80h] [rbp-D8h] BYREF
  __int64 EffectiveServerSilo; // [rsp+88h] [rbp-D0h]
  _DWORD *v38; // [rsp+90h] [rbp-C8h]
  PRX_CONTEXT v39; // [rsp+98h] [rbp-C0h]
  int v40; // [rsp+A0h] [rbp-B8h]
  PVOID v41; // [rsp+A8h] [rbp-B0h]
  _OWORD v42[3]; // [rsp+B0h] [rbp-A8h] BYREF
  _KAPC_STATE ApcState; // [rsp+E0h] [rbp-78h] BYREF

  v39 = RxContext;
  CurrentIrp = RxContext->CurrentIrp;
  RequestorMode = CurrentIrp->RequestorMode;
  v4 = (__int64)RxContext->RdbssDbgExtension & 2;
  v5 = (_DWORD *)*((_QWORD *)&RxContext->9 + 19);
  v38 = v5;
  Buffer = RxContext->Create.TransportName.Buffer;
  Length = *((_DWORD *)&RxContext->9 + 43);
  v7 = *((unsigned int *)&RxContext->9 + 42);
  v36 = 0;
  ULong64FromUser = 0;
  v32 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(v42, 0, sizeof(v42));
  SiloParameters = IoGetSiloParameters(CurrentIrp->Tail.Overlay.CurrentStackLocation->FileObject);
  if ( !SiloParameters
    || (EffectiveServerSilo = PsGetEffectiveServerSilo(*(_QWORD *)(SiloParameters + 8)),
        (unsigned __int8)PsIsHostSilo(EffectiveServerSilo)) )
  {
    EffectiveServerSilo = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_a378b67053473c077e88bb075e0102ae_Traceguids, RxContext);
  }
  if ( !v4 )
  {
    BYTE3(RxContext->RealDevice) = 1;
    return 3225485315LL;
  }
  v26 = 0;
  v30 = 0;
  v29 = 0;
  v25 = 0;
  RequestorProcess = IoGetRequestorProcess(RxContext->CurrentIrp);
  KeStackAttachProcess(RequestorProcess, &ApcState);
  v11 = RxMapUserBuffer(RxContext, RxContext->CurrentIrp);
  v34 = (_DWORD)v11 - (_DWORD)Buffer;
  v36 = v11;
  Length_4 = RxContext->CurrentIrp->MdlAddress != 0;
  if ( RequestorMode )
  {
    ProbeForWrite(v5, v7, 1u);
    ProbeForWrite(v11, Length, 1u);
  }
  if ( (unsigned int)v7 < 0x24 )
  {
    v12 = -1073741789;
    goto LABEL_104;
  }
  v13 = v38;
  if ( RequestorMode )
    ULongFromUser = RtlReadULongFromUser(v38 + 1);
  else
    ULongFromUser = v38[1];
  if ( ULongFromUser != 6 )
  {
    v12 = -1073741811;
    goto LABEL_104;
  }
  if ( RequestorMode )
    v15 = RtlReadULongFromUser(v38 + 2);
  else
    v15 = v38[2];
  if ( RequestorMode )
    v16 = RtlReadULongFromUser(v38 + 8);
  else
    v16 = v38[8];
  v31 = v16;
  if ( RequestorMode )
    ULong64FromUser = RtlReadULong64FromUser(v38 + 3);
  else
    RtlCopyVolatileMemory(&ULong64FromUser, v38 + 3, 8u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_a378b67053473c077e88bb075e0102ae_Traceguids, v15);
  }
  if ( IoIs32bitProcess(RxContext->CurrentIrp) )
  {
    if ( v15 )
    {
      switch ( v15 )
      {
        case 1u:
          if ( Length < 0x18 )
          {
            v12 = -1073741789;
            goto LABEL_104;
          }
          break;
        case 2u:
          if ( Length < 0x44 )
          {
            v12 = -1073741789;
            goto LABEL_104;
          }
          break;
        case 3u:
          if ( Length < 0xD0 )
          {
            v12 = -1073741789;
            goto LABEL_104;
          }
          break;
        default:
          v12 = -1073741821;
          goto LABEL_104;
      }
    }
    else if ( Length < 0xC )
    {
      v12 = -1073741789;
      goto LABEL_104;
    }
  }
  else if ( v15 )
  {
    switch ( v15 )
    {
      case 1u:
        if ( Length < 0x20 )
        {
          v12 = -1073741789;
          goto LABEL_104;
        }
        break;
      case 2u:
        if ( Length < 0x60 )
        {
          v12 = -1073741789;
          goto LABEL_104;
        }
        break;
      case 3u:
        if ( Length < 0xF0 )
        {
          v12 = -1073741789;
          goto LABEL_104;
        }
        break;
      case 4u:
        if ( Length < 0x40 )
        {
          v12 = -1073741789;
          goto LABEL_104;
        }
        break;
      default:
        v12 = -1073741821;
        goto LABEL_104;
    }
  }
  else if ( Length < 0x18 )
  {
    v12 = -1073741789;
    goto LABEL_104;
  }
  v17 = v13 + 5;
  if ( RequestorMode )
    RtlWriteULongToUser(v13 + 5, 0);
  else
    *v17 = 0;
  v18 = v13 + 6;
  if ( RequestorMode )
    RtlWriteULongToUser(v13 + 6, 0);
  else
    *v18 = 0;
  ExAcquireResourceExclusiveLite(
    (PERESOURCE)&RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink[1].Blink,
    1u);
  v26 = 1;
  v25 = 1;
  for ( i = RxPrefixTableLookupFirstObject(
              RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink,
              0,
              0,
              60178,
              v42); ; i = RxPrefixTableLookupNextObject(v42) )
  {
    v20 = i;
    if ( !i )
    {
      v22 = v29;
      goto LABEL_94;
    }
    if ( *(_QWORD *)(i + 288) == EffectiveServerSilo
      && *(_DWORD *)(i + 352) >= v31
      && (v15 == 4 || *(_WORD *)(*(_QWORD *)(i + 232) + 2LL) != 59)
      && *(_DWORD *)(i + 204) == 3
      && (v15 == 4
       || (ULong64FromUser == *(_QWORD *)(i + 72) || ULong64FromUser == *(_QWORD *)(i + 80)) && *(_BYTE *)(i + 192)) )
    {
      break;
    }
LABEL_88:
    ;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a378b67053473c077e88bb075e0102ae_Traceguids);
  }
  v41 = v36;
  LOBYTE(v24) = Length_4;
  v21 = (*(__int64 (__fastcall **)(PRX_CONTEXT, __int64, _QWORD, PVOID *, unsigned int *, int, unsigned int *, int))(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 32) + 32LL) + 32LL) + 56LL) + 792LL))(
          RxContext,
          v20,
          v15,
          &v36,
          &Length,
          v34,
          &v32,
          v24);
  if ( !v21 )
  {
    v40 = ++v30;
    v35 = ++v29;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_a378b67053473c077e88bb075e0102ae_Traceguids, v41);
    }
    goto LABEL_88;
  }
  if ( v21 == -1073741790 || v21 == -1073741300 )
    goto LABEL_88;
  v22 = v29;
  if ( v21 == -1073741789 )
  {
    v22 = v29 + 1;
    v35 = v29 + 1;
  }
LABEL_94:
  if ( RequestorMode )
    RtlWriteULongToUser(v17, v30);
  else
    *v17 = v30;
  if ( RequestorMode )
    RtlWriteULongToUser(v18, v22);
  else
    *v18 = v22;
  v23 = v38 + 7;
  if ( RequestorMode )
    RtlWriteULongToUser(v23, v32);
  else
    *v23 = v32;
  RxContext->InformationToReturn = 36;
  v12 = 0;
LABEL_104:
  if ( v25 )
    RxPrefixTableEndLookup(v42);
  if ( v26 )
    ExReleaseResourceLite((PERESOURCE)&RxContext->NonPagedFcb[1].HeaderResource.SystemResourcesList.Flink[1].Blink);
  KeUnstackDetachProcess(&ApcState);
  return v12;
}

```

## disassembly

```asm
0x140049e60  mov     r11, rsp
0x140049e63  push    rbx
0x140049e64  push    rsi
0x140049e65  push    r12
0x140049e67  push    r13
0x140049e69  push    r14
0x140049e6b  push    r15
0x140049e6d  sub     rsp, 128h
0x140049e74  mov     rax, cs:__security_cookie
0x140049e7b  xor     rax, rsp
0x140049e7e  mov     [rsp+158h+var_48], rax
0x140049e86  mov     rsi, rcx
0x140049e89  mov     [rsp+158h+var_C0], rcx
0x140049e91  mov     rcx, [rcx+28h]
0x140049e95  mov     r12b, [rcx+40h]
0x140049e99  mov     ebx, [rsi+78h]
0x140049e9c  and     ebx, 2
0x140049e9f  mov     r13, [rsi+228h]
0x140049ea6  mov     [rsp+158h+var_C8], r13
0x140049eae  mov     r15, [rsi+230h]
0x140049eb5  mov     eax, [rsi+23Ch]
0x140049ebb  mov     dword ptr [rsp+158h+Length], eax
0x140049ebf  mov     r14d, [rsi+238h]
0x140049ec6  mov     qword ptr [r11-0D8h], 0
0x140049ed1  mov     [rsp+158h+var_E8], 0
0x140049eda  mov     [rsp+158h+var_EC], 0
0x140049ee2  xorps   xmm0, xmm0
0x140049ee5  movups  xmmword ptr [r11-78h], xmm0
0x140049eea  movups  xmmword ptr [r11-68h], xmm0
0x140049eef  movups  xmmword ptr [r11-58h], xmm0
0x140049ef4  xorps   xmm1, xmm1
0x140049ef7  movups  [rsp+158h+var_A8], xmm1
0x140049eff  movups  [rsp+158h+var_98], xmm1
0x140049f07  movups  [rsp+158h+var_88], xmm1
0x140049f0f  mov     rcx, [rcx+0B8h]
0x140049f16  mov     rcx, [rcx+30h]
0x140049f1a  call    cs:__imp_IoGetSiloParameters
0x140049f21  nop     dword ptr [rax+rax+00h]
0x140049f26  test    rax, rax
0x140049f29  jz      short loc_140049F56
0x140049f2b  mov     rcx, [rax+8]
0x140049f2f  call    cs:__imp_PsGetEffectiveServerSilo
0x140049f36  nop     dword ptr [rax+rax+00h]
0x140049f3b  mov     [rsp+158h+var_D0], rax
0x140049f43  mov     rcx, rax
0x140049f46  call    cs:__imp_PsIsHostSilo
0x140049f4d  nop     dword ptr [rax+rax+00h]
0x140049f52  test    al, al
0x140049f54  jz      short loc_140049F62
0x140049f56  mov     [rsp+158h+var_D0], 0
0x140049f62  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140049f69  mov     rcx, cs:WPP_GLOBAL_Control
0x140049f70  cmp     rcx, rax
0x140049f73  jz      short loc_140049F9A
0x140049f75  mov     eax, [rcx+2Ch]
0x140049f78  test    al, 2
0x140049f7a  jz      short loc_140049F9A
0x140049f7c  cmp     byte ptr [rcx+29h], 4
0x140049f80  jb      short loc_140049F9A
0x140049f82  mov     edx, 12h
0x140049f87  mov     r9, rsi
0x140049f8a  lea     r8, WPP_a378b67053473c077e88bb075e0102ae_Traceguids
0x140049f91  mov     rcx, [rcx+18h]
0x140049f95  call    WPP_SF_q
0x140049f9a  test    ebx, ebx
0x140049f9c  jnz     short loc_140049FCA
0x140049f9e  mov     byte ptr [rsi+23h], 1
0x140049fa2  mov     eax, 0C0410003h
0x140049fa7  mov     rcx, [rsp+158h+var_48]
0x140049faf  xor     rcx, rsp; StackCookie
0x140049fb2  call    __security_check_cookie
0x140049fb7  add     rsp, 128h
0x140049fbe  pop     r15
0x140049fc0  pop     r14
0x140049fc2  pop     r13
0x140049fc4  pop     r12
0x140049fc6  pop     rsi
0x140049fc7  pop     rbx
0x140049fc8  retn
0x140049fca  mov     [rsp+158h+var_107], 0
0x140049fcf  xor     eax, eax
0x140049fd1  mov     [rsp+158h+var_F4], eax
0x140049fd5  mov     [rsp+158h+var_F8], eax
0x140049fd9  mov     [rsp+158h+var_108], al
0x140049fdd  mov     rcx, [rsi+28h]; Irp
0x140049fe1  call    cs:__imp_IoGetRequestorProcess
0x140049fe8  nop     dword ptr [rax+rax+00h]
0x140049fed  mov     rcx, rax; PROCESS
0x140049ff0  lea     rdx, [rsp+158h+ApcState]; ApcState
0x140049ff8  call    cs:__imp_KeStackAttachProcess
0x140049fff  nop     dword ptr [rax+rax+00h]
0x14004a004  mov     rdx, [rsi+28h]; Irp
0x14004a008  mov     rcx, rsi; RxContext
0x14004a00b  call    cs:__imp_RxMapUserBuffer
0x14004a012  nop     dword ptr [rax+rax+00h]
0x14004a017  mov     rbx, rax
0x14004a01a  sub     eax, r15d
0x14004a01d  mov     [rsp+158h+var_E0], eax
0x14004a021  mov     [rsp+158h+var_D8], rbx
0x14004a029  mov     rcx, [rsi+28h]
0x14004a02d  cmp     qword ptr [rcx+8], 0
0x14004a032  setnz   byte ptr [rsp+158h+Length+4]
0x14004a037  test    r12b, r12b
0x14004a03a  jz      short loc_14004A079
0x14004a03c  mov     rdx, r14; Length
0x14004a03f  mov     r8d, 1; Alignment
0x14004a045  mov     rcx, r13; Address
0x14004a048  call    cs:__imp_ProbeForWrite
0x14004a04f  nop     dword ptr [rax+rax+00h]
0x14004a054  mov     edx, dword ptr [rsp+158h+Length]; Length
0x14004a058  mov     r8d, 1; Alignment
0x14004a05e  mov     rcx, rbx; Address
0x14004a061  call    cs:__imp_ProbeForWrite
0x14004a068  nop     dword ptr [rax+rax+00h]
0x14004a06d  jmp     short loc_14004A079
0x14004a06f  mov     ebx, 0C000000Dh
0x14004a074  jmp     loc_14004A590
0x14004a079  cmp     r14d, 24h ; '$'
0x14004a07d  jnb     short loc_14004A08D
0x14004a07f  mov     ebx, 0C0000023h
0x14004a084  mov     [rsp+158h+var_104], ebx
0x14004a088  jmp     loc_14004A553
0x14004a08d  mov     rbx, [rsp+158h+var_C8]
0x14004a095  test    r12b, r12b
0x14004a098  jz      short loc_14004A0A5
0x14004a09a  lea     rcx, [rbx+4]
0x14004a09e  call    RtlReadULongFromUser
0x14004a0a3  jmp     short loc_14004A0A8
0x14004a0a5  mov     eax, [rbx+4]
0x14004a0a8  cmp     eax, 6
0x14004a0ab  jz      short loc_14004A0BB
0x14004a0ad  mov     ebx, 0C000000Dh
0x14004a0b2  mov     [rsp+158h+var_104], ebx
0x14004a0b6  jmp     loc_14004A553
0x14004a0bb  test    r12b, r12b
0x14004a0be  jz      short loc_14004A0CE
0x14004a0c0  lea     rcx, [rbx+8]
0x14004a0c4  call    RtlReadULongFromUser
0x14004a0c9  mov     r13d, eax
0x14004a0cc  jmp     short loc_14004A0D2
0x14004a0ce  mov     r13d, [rbx+8]
0x14004a0d2  test    r12b, r12b
0x14004a0d5  jz      short loc_14004A0E2
0x14004a0d7  lea     rcx, [rbx+20h]
0x14004a0db  call    RtlReadULongFromUser
0x14004a0e0  jmp     short loc_14004A0E5
0x14004a0e2  mov     eax, [rbx+20h]
0x14004a0e5  mov     [rsp+158h+var_F0], eax
0x14004a0e9  lea     rdx, [rbx+0Ch]; Src
0x14004a0ed  test    r12b, r12b
0x14004a0f0  jz      short loc_14004A101
0x14004a0f2  mov     rcx, rdx
0x14004a0f5  call    RtlReadULong64FromUser
0x14004a0fa  mov     [rsp+158h+var_E8], rax
0x14004a0ff  jmp     short loc_14004A111
0x14004a101  mov     r8d, 8; Size
0x14004a107  lea     rcx, [rsp+158h+var_E8]; void *
0x14004a10c  call    RtlCopyVolatileMemory
0x14004a111  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004a118  lea     rax, WPP_GLOBAL_Control
0x14004a11f  cmp     rcx, rax
0x14004a122  jz      short loc_14004A149
0x14004a124  mov     eax, [rcx+2Ch]
0x14004a127  test    al, 2
0x14004a129  jz      short loc_14004A149
0x14004a12b  cmp     byte ptr [rcx+29h], 4
0x14004a12f  jb      short loc_14004A149
0x14004a131  mov     edx, 13h
0x14004a136  mov     r9d, r13d
0x14004a139  lea     r8, WPP_a378b67053473c077e88bb075e0102ae_Traceguids
0x14004a140  mov     rcx, [rcx+18h]
0x14004a144  call    WPP_SF_d
0x14004a149  mov     rcx, [rsi+28h]; Irp
0x14004a14d  call    cs:__imp_IoIs32bitProcess
0x14004a154  nop     dword ptr [rax+rax+00h]
0x14004a159  test    al, al
0x14004a15b  mov     eax, r13d
0x14004a15e  jz      loc_14004A1ED
0x14004a164  test    r13d, r13d
0x14004a167  jz      short loc_14004A1D4
0x14004a169  sub     eax, 1
0x14004a16c  jz      short loc_14004A1BB
0x14004a16e  sub     eax, 1
0x14004a171  jz      short loc_14004A1A2
0x14004a173  sub     eax, 1
0x14004a176  jz      short loc_14004A186
0x14004a178  mov     ebx, 0C0000003h
0x14004a17d  mov     [rsp+158h+var_104], ebx
0x14004a181  jmp     loc_14004A553
0x14004a186  cmp     dword ptr [rsp+158h+Length], 0D0h
0x14004a18e  jnb     loc_14004A280
0x14004a194  mov     ebx, 0C0000023h
0x14004a199  mov     [rsp+158h+var_104], ebx
0x14004a19d  jmp     loc_14004A553
0x14004a1a2  cmp     dword ptr [rsp+158h+Length], 44h ; 'D'
0x14004a1a7  jnb     loc_14004A280
0x14004a1ad  mov     ebx, 0C0000023h
0x14004a1b2  mov     [rsp+158h+var_104], ebx
0x14004a1b6  jmp     loc_14004A553
0x14004a1bb  cmp     dword ptr [rsp+158h+Length], 18h
0x14004a1c0  jnb     loc_14004A280
0x14004a1c6  mov     ebx, 0C0000023h
0x14004a1cb  mov     [rsp+158h+var_104], ebx
0x14004a1cf  jmp     loc_14004A553
0x14004a1d4  cmp     dword ptr [rsp+158h+Length], 0Ch
0x14004a1d9  jnb     loc_14004A280
0x14004a1df  mov     ebx, 0C0000023h
0x14004a1e4  mov     [rsp+158h+var_104], ebx
0x14004a1e8  jmp     loc_14004A553
0x14004a1ed  test    r13d, r13d
0x14004a1f0  jz      short loc_14004A26B
0x14004a1f2  sub     eax, 1
0x14004a1f5  jz      short loc_14004A256
0x14004a1f7  sub     eax, 1
0x14004a1fa  jz      short loc_14004A241
0x14004a1fc  sub     eax, 1
0x14004a1ff  jz      short loc_14004A229
0x14004a201  sub     eax, 1
0x14004a204  jz      short loc_14004A214
0x14004a206  mov     ebx, 0C0000003h
0x14004a20b  mov     [rsp+158h+var_104], ebx
0x14004a20f  jmp     loc_14004A553
0x14004a214  cmp     dword ptr [rsp+158h+Length], 40h ; '@'
0x14004a219  jnb     short loc_14004A280
0x14004a21b  mov     ebx, 0C0000023h
0x14004a220  mov     [rsp+158h+var_104], ebx
0x14004a224  jmp     loc_14004A553
0x14004a229  cmp     dword ptr [rsp+158h+Length], 0F0h
0x14004a231  jnb     short loc_14004A280
0x14004a233  mov     ebx, 0C0000023h
0x14004a238  mov     [rsp+158h+var_104], ebx
0x14004a23c  jmp     loc_14004A553
0x14004a241  cmp     dword ptr [rsp+158h+Length], 60h ; '`'
0x14004a246  jnb     short loc_14004A280
0x14004a248  mov     ebx, 0C0000023h
0x14004a24d  mov     [rsp+158h+var_104], ebx
0x14004a251  jmp     loc_14004A553
0x14004a256  cmp     dword ptr [rsp+158h+Length], 20h ; ' '
0x14004a25b  jnb     short loc_14004A280
0x14004a25d  mov     ebx, 0C0000023h
0x14004a262  mov     [rsp+158h+var_104], ebx
0x14004a266  jmp     loc_14004A553
0x14004a26b  cmp     dword ptr [rsp+158h+Length], 18h
0x14004a270  jnb     short loc_14004A280
0x14004a272  mov     ebx, 0C0000023h
0x14004a277  mov     [rsp+158h+var_104], ebx
0x14004a27b  jmp     loc_14004A553
0x14004a280  lea     r15, [rbx+14h]
0x14004a284  test    r12b, r12b
0x14004a287  jz      short loc_14004A295
0x14004a289  xor     edx, edx
0x14004a28b  mov     rcx, r15
0x14004a28e  call    RtlWriteULongToUser
0x14004a293  jmp     short loc_14004A29C
0x14004a295  mov     dword ptr [r15], 0
0x14004a29c  lea     r14, [rbx+18h]
0x14004a2a0  test    r12b, r12b
0x14004a2a3  jz      short loc_14004A2B1
0x14004a2a5  xor     edx, edx
0x14004a2a7  mov     rcx, r14
0x14004a2aa  call    RtlWriteULongToUser
0x14004a2af  jmp     short loc_14004A2B8
0x14004a2b1  mov     dword ptr [r14], 0
0x14004a2b8  mov     rax, [rsi+50h]
0x14004a2bc  mov     rcx, [rax+1F8h]
0x14004a2c3  add     rcx, 18h; Resource
0x14004a2c7  mov     dl, 1; Wait
0x14004a2c9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004a2d0  nop     dword ptr [rax+rax+00h]
0x14004a2d5  mov     [rsp+158h+var_107], 1
0x14004a2da  mov     [rsp+158h+var_108], 1
0x14004a2df  mov     r9d, 0EB12h
0x14004a2e5  mov     rcx, [rsi+50h]
0x14004a2e9  lea     rax, [rsp+158h+var_A8]
0x14004a2f1  mov     [rsp+158h+var_138], rax
0x14004a2f6  xor     r8d, r8d
0x14004a2f9  xor     edx, edx
0x14004a2fb  mov     rcx, [rcx+1F8h]
0x14004a302  call    cs:__imp_RxPrefixTableLookupFirstObject
0x14004a309  nop     dword ptr [rax+rax+00h]
0x14004a30e  mov     rbx, rax
0x14004a311  test    rax, rax
0x14004a314  jz      loc_14004A4DD
0x14004a31a  mov     rax, [rsp+158h+var_D0]
0x14004a322  cmp     [rbx+120h], rax
0x14004a329  jz      short loc_14004A330
0x14004a32b  jmp     loc_14004A4A1
0x14004a330  mov     eax, [rsp+158h+var_F0]
0x14004a334  cmp     [rbx+160h], eax
0x14004a33a  jb      loc_14004A4A1
0x14004a340  cmp     r13d, 4
0x14004a344  jz      short loc_14004A358
0x14004a346  mov     rax, [rbx+0E8h]
0x14004a34d  cmp     word ptr [rax+2], 3Bh ; ';'
0x14004a352  jz      loc_14004A4A1
0x14004a358  cmp     dword ptr [rbx+0CCh], 3
0x14004a35f  jnz     loc_14004A4A1
0x14004a365  cmp     r13d, 4
0x14004a369  jz      short loc_14004A3A7
0x14004a36b  mov     rax, [rsp+158h+var_E8]
  ... truncated ...
```
