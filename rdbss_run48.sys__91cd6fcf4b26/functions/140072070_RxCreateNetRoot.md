# RxCreateNetRoot

- ea: `0x140072070`
- end: `0x140072443`
- name: `RxCreateNetRoot`
- size: `979`
- prototype: `PNET_ROOT __stdcall(PSRV_CALL SrvCall, PUNICODE_STRING Name, ULONG NetRootFlags, PRX_CONNECTION_ID RxConnectionId)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14005f400`

## callees

- `0x14000ffa0`
- `0x140014e40`
- `0x14001b178`
- `0x14002306c`
- `0x140025d80`
- `0x1400597e0`
- `0x14005f110`
- `0x140072070`
- `0x140072450`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007215a`
- `ntoskrnl!ExAllocatePool2` at `0x14007215a`
- `ntoskrnl!ExInitializeResourceLite` at `0x14007217d`
- `ntoskrnl!ExInitializeResourceLite` at `0x14007217d`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140072264`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x140072264`

## pseudocode

```c
PNET_ROOT __stdcall RxCreateNetRoot(
        PSRV_CALL SrvCall,
        PUNICODE_STRING Name,
        ULONG NetRootFlags,
        PRX_CONNECTION_ID RxConnectionId)
{
  __int64 ContainerRefCount_low; // rsi
  ULONG v8; // r14d
  PUNICODE_STRING pDomainName; // rdx
  wchar_t *Buffer; // r13
  _QWORD *Object; // rax
  _QWORD *v12; // rbx
  int Flink; // esi
  bool v14; // si
  __int64 Pool2; // rax
  __int64 v16; // r8
  unsigned __int64 v17; // r15
  volatile signed __int32 *v18; // rax
  bool v19; // zf
  __int128 v20; // xmm0
  __int64 v21; // rsi
  unsigned __int64 v22; // rax
  int v23; // esi
  unsigned __int64 v24; // rax
  int v25; // eax
  int v26; // r8d

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 41, &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, Name);
  }
  ContainerRefCount_low = LOWORD(SrvCall->PrefixEntry.ContainerRefCount);
  v8 = ContainerRefCount_low + Name->Length;
  if ( v8 > 0xFFFE )
    return 0;
  pDomainName = SrvCall->pDomainName;
  Buffer = pDomainName[31].Buffer;
  Object = RxAllocateObject(0xEB11u, *(PMINIRDR_DISPATCH *)&pDomainName[22].Length, v8);
  v12 = Object;
  if ( Object )
  {
    memmove((void *)(ContainerRefCount_low + Object[28]), Name->Buffer, Name->Length);
    if ( (_WORD)ContainerRefCount_low )
      memmove((void *)v12[28], SrvCall->PrefixEntry.ContainingRecord, (unsigned int)ContainerRefCount_low);
    Flink = (int)SrvCall->PrefixEntry.HashLinks.Flink;
    if ( (Flink & 4) == 0 )
      LOWORD(v8) = WORD2(SrvCall->PrefixEntry.Prefix.Buffer);
    *((_DWORD *)v12 + 74) = 12118793;
    v14 = (Flink & 8) != 0;
    Pool2 = ExAllocatePool2(256, 512, 1917745234);
    v12[58] = Pool2;
    if ( Pool2 )
    {
      ExInitializeResourceLite((PERESOURCE)(v12 + 43));
      v17 = 0;
      v12[40] = 0;
      v12[42] = v12 + 41;
      v12[41] = v12 + 41;
      v18 = (volatile signed __int32 *)v12 + 1;
      *(_QWORD *)((char *)v12 + 300) = 0;
      *((_BYTE *)v12 + 472) = v14;
      v12[56] = 0;
      v12[57] = 0;
      *(_QWORD *)((char *)v12 + 308) = 0;
      v19 = *((_BYTE *)Buffer + 128) == 0;
      v12[33] = v12;
      if ( !v19 )
        LOWORD(v8) = -2;
      v12[32] = v18;
      *((_WORD *)v12 + 106) = v8;
      _InterlockedIncrement(v18);
      if ( RxConnectionId )
        v20 = *(_OWORD *)&RxConnectionId->SessionID;
      else
        v20 = 0;
      *(_OWORD *)(v12 + 35) = v20;
      v21 = *((_QWORD *)Buffer + 2);
      v22 = *((_QWORD *)Buffer + 1);
      if ( (v21 & 1) != 0 )
      {
        if ( !v22 )
        {
LABEL_31:
          LOBYTE(v16) = 0;
          goto LABEL_21;
        }
        v22 ^= (unsigned __int64)(Buffer + 4);
      }
      v23 = v21 & 1;
      LOBYTE(v16) = 0;
      v17 = v22;
      if ( v22 )
      {
        while ( 1 )
        {
          if ( (int)RxpCompareFn_PrefixName2PrefixName(v12 + 27, v17, v16) < 0 )
          {
            v24 = *(_QWORD *)v17;
            if ( v23 )
            {
              if ( !v24 )
                goto LABEL_31;
              v24 ^= v17;
            }
            if ( !v24 )
              goto LABEL_31;
          }
          else
          {
            v24 = *(_QWORD *)(v17 + 8);
            if ( v23 )
            {
              if ( !v24 )
              {
LABEL_20:
                LOBYTE(v16) = 1;
                break;
              }
              v24 ^= v17;
            }
            if ( !v24 )
              goto LABEL_20;
          }
          v17 = v24;
        }
      }
LABEL_21:
      RtlRbInsertNodeEx(Buffer + 4, v17, v16, v12 + 29);
      ++*((_DWORD *)Buffer + 1);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qqZ(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          (unsigned int)&WPP_04af8fc7118b317781e27056f3398603_Traceguids,
          (_DWORD)v12 + 208,
          (char)v12,
          (__int64)(v12 + 27));
      }
      v12[23] = v12 + 22;
      v12[22] = v12 + 22;
      v12[21] = v12 + 20;
      v12[20] = v12 + 20;
      v12[3] = v12 + 2;
      v12[2] = v12 + 2;
      v25 = SerialNumber;
      *((_DWORD *)v12 + 48) = SerialNumber;
      SerialNumber = v25 + 1;
      *((_DWORD *)v12 + 14) |= NetRootFlags;
      *((_BYTE *)v12 + 145) = 0;
      *((_DWORD *)v12 + 26) = 1;
      *((_DWORD *)v12 + 27) = 0x40000;
      v12[4] = SrvCall;
      *((_DWORD *)v12 + 24) = -1;
      RxReference(SrvCall);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qiiZ(
          WPP_GLOBAL_Control->AttachedDevice,
          42,
          v26,
          (_DWORD)v12,
          (char)*RxConnectionId,
          *(_QWORD *)&RxConnectionId[1],
          (__int64)(v12 + 27));
      }
    }
    else
    {
      RxFreeObject(v12);
      return 0;
    }
  }
  return (PNET_ROOT)v12;
}

```

## disassembly

```asm
0x140072070  mov     [rsp+arg_10], r8d
0x140072075  push    rbp
0x140072076  push    rsi
0x140072077  push    rdi
0x140072078  push    r12
0x14007207a  push    r14
0x14007207c  sub     rsp, 40h
0x140072080  mov     r12, r9
0x140072083  mov     rbp, rdx
0x140072086  mov     rdi, rcx
0x140072089  mov     rcx, cs:WPP_GLOBAL_Control
0x140072090  lea     rax, WPP_GLOBAL_Control
0x140072097  cmp     rcx, rax
0x14007209a  jnz     loc_14007237C
0x1400720a0  movzx   esi, word ptr [rdi+90h]
0x1400720a7  movzx   r14d, word ptr [rbp+0]
0x1400720ac  add     r14d, esi
0x1400720af  cmp     r14d, 0FFFEh
0x1400720b6  ja      loc_1400723AE
0x1400720bc  mov     rdx, [rdi+30h]
0x1400720c0  mov     ecx, 0EB11h; NodeType
0x1400720c5  mov     [rsp+68h+arg_0], rbx
0x1400720ca  mov     r8d, r14d; NameLength
0x1400720cd  mov     [rsp+68h+arg_8], r13
0x1400720d2  mov     r13, [rdx+1F8h]
0x1400720d9  mov     rdx, [rdx+160h]; MRxDispatch
0x1400720e0  call    RxAllocateObject
0x1400720e5  mov     rbx, rax
0x1400720e8  test    rax, rax
0x1400720eb  jz      loc_14007231E
0x1400720f1  mov     rcx, [rax+0E0h]
0x1400720f8  movzx   r8d, word ptr [rbp+0]; Size
0x1400720fd  add     rcx, rsi; void *
0x140072100  mov     rdx, [rbp+8]; Src
0x140072104  mov     [rsp+68h+arg_18], r15
0x14007210c  call    memmove
0x140072111  test    si, si
0x140072114  jz      short loc_14007212C
0x140072116  mov     rdx, [rdi+98h]; Src
0x14007211d  mov     r8d, esi; Size
0x140072120  mov     rcx, [rbx+0E0h]; void *
0x140072127  call    memmove
0x14007212c  mov     esi, [rdi+60h]
0x14007212f  test    sil, 4
0x140072133  jz      loc_1400723B5
0x140072139  shr     esi, 3
0x14007213c  mov     edx, 200h
0x140072141  mov     ecx, 100h
0x140072146  mov     dword ptr [rbx+128h], 0B8EB09h
0x140072150  mov     r8d, 724E7852h
0x140072156  and     sil, 1
0x14007215a  call    cs:__imp_ExAllocatePool2
0x140072161  nop     dword ptr [rax+rax+00h]
0x140072166  mov     [rbx+1D0h], rax
0x14007216d  test    rax, rax
0x140072170  jz      loc_140072338
0x140072176  lea     rcx, [rbx+158h]; Resource
0x14007217d  call    cs:__imp_ExInitializeResourceLite
0x140072184  nop     dword ptr [rax+rax+00h]
0x140072189  xor     r15d, r15d
0x14007218c  lea     rax, [rbx+148h]
0x140072193  mov     [rbx+140h], r15
0x14007219a  lea     rbp, [rbx+0D0h]
0x1400721a1  mov     [rax+8], rax
0x1400721a5  mov     ecx, 0FFFEh
0x1400721aa  mov     [rax], rax
0x1400721ad  lea     rax, [rbx+4]
0x1400721b1  mov     [rbx+12Ch], r15
0x1400721b8  mov     [rbx+1D8h], sil
0x1400721bf  mov     [rbx+1C0h], r15
0x1400721c6  mov     [rbx+1C8h], r15
0x1400721cd  mov     [rbx+134h], r15
0x1400721d4  cmp     [r13+80h], r15b
0x1400721db  mov     [rbp+38h], rbx
0x1400721df  cmovnz  r14w, cx
0x1400721e4  mov     [rbp+30h], rax
0x1400721e8  mov     [rbp+4], r14w
0x1400721ed  lock inc dword ptr [rax]
0x1400721f0  test    r12, r12
0x1400721f3  jz      loc_140072367
0x1400721f9  movups  xmm0, xmmword ptr [r12]
0x1400721fe  lea     r14, [r13+8]
0x140072202  movups  xmmword ptr [rbp+48h], xmm0
0x140072206  mov     rsi, [r14+8]
0x14007220a  mov     rax, [r14]
0x14007220d  test    sil, 1
0x140072211  jnz     loc_14007236F
0x140072217  and     esi, 1
0x14007221a  xor     r8b, r8b
0x14007221d  mov     r15, rax
0x140072220  test    rax, rax
0x140072223  jz      short loc_14007225A
0x140072225  lea     rax, [rbp+8]
0x140072229  mov     rdx, r15
0x14007222c  mov     rcx, rax
0x14007222f  call    RxpCompareFn_PrefixName2PrefixName
0x140072234  test    eax, eax
0x140072236  js      loc_140072348
0x14007223c  mov     rax, [r15+8]
0x140072240  test    esi, esi
0x140072242  jnz     short loc_14007224E
0x140072244  test    rax, rax
0x140072247  jz      short loc_140072257
0x140072249  mov     r15, rax
0x14007224c  jmp     short loc_140072225
0x14007224e  test    rax, rax
0x140072251  jnz     loc_1400723C2
0x140072257  mov     r8b, 1
0x14007225a  lea     r9, [rbp+18h]
0x14007225e  mov     rdx, r15
0x140072261  mov     rcx, r14
0x140072264  call    cs:__imp_RtlRbInsertNodeEx
0x14007226b  nop     dword ptr [rax+rax+00h]
0x140072270  inc     dword ptr [r13+4]
0x140072274  mov     rcx, cs:WPP_GLOBAL_Control
0x14007227b  lea     rsi, WPP_GLOBAL_Control
0x140072282  cmp     rcx, rsi
0x140072285  jz      short loc_140072292
0x140072287  mov     eax, [rcx+2Ch]
0x14007228a  test    al, al
0x14007228c  js      loc_1400723CF
0x140072292  lea     rax, [rbx+0B0h]
0x140072299  mov     rcx, rdi; Instance
0x14007229c  mov     [rax+8], rax
0x1400722a0  mov     [rax], rax
0x1400722a3  lea     rax, [rbx+0A0h]
0x1400722aa  mov     [rax+8], rax
0x1400722ae  mov     [rax], rax
0x1400722b1  lea     rax, [rbx+10h]
0x1400722b5  mov     [rax+8], rax
0x1400722b9  mov     [rax], rax
0x1400722bc  mov     eax, cs:SerialNumber
0x1400722c2  mov     [rbx+0C0h], eax
0x1400722c8  inc     eax
0x1400722ca  mov     cs:SerialNumber, eax
0x1400722d0  mov     eax, [rsp+68h+arg_10]
0x1400722d7  or      [rbx+38h], eax
0x1400722da  mov     byte ptr [rbx+91h], 0
0x1400722e1  mov     dword ptr [rbx+68h], 1
0x1400722e8  mov     dword ptr [rbx+6Ch], 40000h
0x1400722ef  mov     [rbx+20h], rdi
0x1400722f3  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x1400722fa  call    RxReference
0x1400722ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140072306  cmp     rcx, rsi
0x140072309  jz      short loc_140072316
0x14007230b  mov     eax, [rcx+2Ch]
0x14007230e  test    al, al
0x140072310  js      loc_140072404
0x140072316  mov     r15, [rsp+68h+arg_18]
0x14007231e  mov     r13, [rsp+68h+arg_8]
0x140072323  mov     rax, rbx
0x140072326  mov     rbx, [rsp+68h+arg_0]
0x14007232b  add     rsp, 40h
0x14007232f  pop     r14
0x140072331  pop     r12
0x140072333  pop     rdi
0x140072334  pop     rsi
0x140072335  pop     rbp
0x140072336  retn
0x140072338  mov     rcx, rbx; pObject
0x14007233b  call    RxFreeObject
0x140072340  xor     r15d, r15d
0x140072343  mov     ebx, r15d
0x140072346  jmp     short loc_140072316
0x140072348  mov     rax, [r15]
0x14007234b  test    esi, esi
0x14007234d  jnz     short loc_14007235A
0x14007234f  test    rax, rax
0x140072352  jnz     loc_140072249
0x140072358  jmp     short loc_14007235F
0x14007235a  test    rax, rax
0x14007235d  jnz     short loc_1400723CA
0x14007235f  xor     r8b, r8b
0x140072362  jmp     loc_14007225A
0x140072367  xorps   xmm0, xmm0
0x14007236a  jmp     loc_1400721FE
0x14007236f  test    rax, rax
0x140072372  jz      short loc_14007235F
0x140072374  xor     rax, r14
0x140072377  jmp     loc_140072217
0x14007237c  mov     eax, [rcx+2Ch]
0x14007237f  test    al, al
0x140072381  jns     loc_1400720A0
0x140072387  cmp     byte ptr [rcx+29h], 2
0x14007238b  jb      loc_1400720A0
0x140072391  mov     rcx, [rcx+18h]
0x140072395  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14007239c  mov     edx, 29h ; ')'
0x1400723a1  mov     r9, rbp
0x1400723a4  call    WPP_SF_Z
0x1400723a9  jmp     loc_1400720A0
0x1400723ae  xor     eax, eax
0x1400723b0  jmp     loc_14007232B
0x1400723b5  movzx   r14d, word ptr [rdi+8Ch]
0x1400723bd  jmp     loc_140072139
0x1400723c2  xor     rax, r15
0x1400723c5  jmp     loc_140072244
0x1400723ca  xor     rax, r15
0x1400723cd  jmp     short loc_14007234F
0x1400723cf  cmp     byte ptr [rcx+29h], 4
0x1400723d3  jb      loc_140072292
0x1400723d9  mov     rcx, [rcx+18h]
0x1400723dd  lea     rax, [rbp+8]
0x1400723e1  mov     [rsp+68h+var_40], rax
0x1400723e6  lea     r8, WPP_04af8fc7118b317781e27056f3398603_Traceguids
0x1400723ed  mov     edx, 0Bh
0x1400723f2  mov     [rsp+68h+var_48], rbx
0x1400723f7  mov     r9, rbp
0x1400723fa  call    WPP_SF_qqZ
0x1400723ff  jmp     loc_140072292
0x140072404  cmp     byte ptr [rcx+29h], 2
0x140072408  jb      loc_140072316
0x14007240e  mov     rcx, [rcx+18h]
0x140072412  lea     rax, [rbx+0D8h]
0x140072419  mov     [rsp+68h+var_38], rax
0x14007241e  mov     edx, 2Ah ; '*'
0x140072423  mov     rax, [r12+8]
0x140072428  mov     r9, rbx
0x14007242b  mov     [rsp+68h+var_40], rax
0x140072430  mov     rax, [r12]
0x140072434  mov     [rsp+68h+var_48], rax
0x140072439  call    WPP_SF_qiiZ
0x14007243e  jmp     loc_140072316
```
