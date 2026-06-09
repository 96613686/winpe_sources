# DfscRmGetReferral

- ea: `0x14001b230`
- end: `0x14001b92d`
- name: `DfscRmGetReferral`
- size: `1789`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400118b4`
- `0x14001a8a4`
- `0x14001aa00`
- `0x14001abc0`
- `0x1400227d4`

## callees

- `0x1400025f4`
- `0x1400032fc`
- `0x14000500c`
- `0x140006080`
- `0x140006380`
- `0x140011494`
- `0x140011604`
- `0x140018ca4`
- `0x14001a718`
- `0x14001a93c`
- `0x14001b230`
- `0x14001b940`
- `0x14001b9ec`
- `0x14001c270`
- `0x14001cee0`
- `0x14001d090`
- `0x140027080`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b3e3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b40b`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b3e3`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b40b`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14001b4ab`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14001b4ab`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001b371`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14001b371`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001b4f3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001b4f3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001b3cd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001b3f5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001b3cd`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001b3f5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001b694`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001b8ab`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001b694`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14001b8ab`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001b679`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001b6d3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001b77d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001b679`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001b6d3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14001b77d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b6ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b7ba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b6ff`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001b7ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b6f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b7ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b6f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001b7ae`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b662`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b6bc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b768`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b662`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b6bc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001b768`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b902`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b902`
- `ntoskrnl!ExAllocatePool2` at `0x14001b2bf`
- `ntoskrnl!ExAllocatePool2` at `0x14001b304`
- `ntoskrnl!ExAllocatePool2` at `0x14001b3ad`
- `ntoskrnl!ExAllocatePool2` at `0x14001b2bf`
- `ntoskrnl!ExAllocatePool2` at `0x14001b304`
- `ntoskrnl!ExAllocatePool2` at `0x14001b3ad`

## pseudocode

```c
__int64 __fastcall DfscRmGetReferral(
        int a1,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        unsigned __int16 a8)
{
  ULONG_PTR v8; // r13
  _DWORD *Pool2; // rax
  _DWORD *v12; // rbx
  int v13; // r12d
  void *v14; // rax
  int inited; // edi
  unsigned __int16 v16; // ax
  __int64 v17; // rax
  bool v18; // dl
  char v20; // r14
  _WORD *v21; // rax
  __int64 v22; // rsi
  _WORD *v23; // rax
  _WORD *v24; // rax
  POBJECT_HANDLE_INFORMATION HandleInformation; // [rsp+28h] [rbp-91h]
  unsigned __int16 v26; // [rsp+30h] [rbp-89h] BYREF
  __int64 v27; // [rsp+38h] [rbp-81h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-79h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-69h] BYREF
  __int64 v30; // [rsp+58h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-59h] BYREF
  _QWORD Parameter[3]; // [rsp+70h] [rbp-49h] BYREF
  int v33; // [rsp+88h] [rbp-31h]
  int v34; // [rsp+8Ch] [rbp-2Dh]
  __int64 v35; // [rsp+90h] [rbp-29h]
  HANDLE *p_Handle; // [rsp+98h] [rbp-21h]
  bool v37; // [rsp+A0h] [rbp-19h]
  int v38; // [rsp+A1h] [rbp-18h]
  __int16 v39; // [rsp+A5h] [rbp-14h]
  char v40; // [rsp+A7h] [rbp-12h]
  __int64 v41; // [rsp+A8h] [rbp-11h]
  __int64 v42; // [rsp+B0h] [rbp-9h]

  v8 = 0;
  v27 = 0;
  v30 = 0;
  String2 = 0;
  a8 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_qZZ(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a2, a3, a5);
  String2.Buffer = 0;
  *(_DWORD *)&String2.Length = 0;
  Handle = 0;
  DestinationString = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(258, 64, 1665361476);
  v12 = Pool2;
  v13 = 1;
  if ( !Pool2 )
    goto LABEL_62;
  memset(Pool2, 0, 0x40u);
  if ( !a4->MaximumLength )
  {
    v14 = 0;
    goto LABEL_7;
  }
  v14 = (void *)ExAllocatePool2(258, a4->MaximumLength, 1984128580);
  *((_QWORD *)v12 + 2) = v14;
  if ( !v14 )
  {
LABEL_62:
    inited = -1073741670;
    DfscConnFree(v12);
    goto LABEL_18;
  }
LABEL_7:
  *v12 = 4227333;
  v12[1] = 1;
  if ( a4->Length && a4->MaximumLength )
  {
    memmove(v14, a4->Buffer, a4->Length);
    *((_WORD *)v12 + 4) = a4->Length;
    *((_WORD *)v12 + 5) = a4->MaximumLength;
  }
  else
  {
    a4->MaximumLength = 0;
    *((_WORD *)v12 + 4) = 0;
  }
  *((_QWORD *)v12 + 7) = *(_QWORD *)(a2 + 224);
  inited = RtlInitUnicodeStringEx(&DestinationString, L"\\Device\\Mup");
  if ( inited < 0 )
    goto LABEL_17;
  *((_WORD *)v12 + 12) = 0;
  v16 = a4->Length + DestinationString.Length + 18;
  *((_WORD *)v12 + 13) = v16;
  v17 = ExAllocatePool2(258, v16, 1883465284);
  *((_QWORD *)v12 + 4) = v17;
  if ( !v17 )
  {
    v12[6] = 0;
    inited = -1073741670;
LABEL_17:
    DfscReleaseIpcConnection(v12);
LABEL_18:
    v12 = 0;
    goto LABEL_20;
  }
  RtlAppendUnicodeStringToString((PUNICODE_STRING)(v12 + 6), &DestinationString);
  RtlAppendUnicodeToString((PUNICODE_STRING)(v12 + 6), L"\\");
  RtlAppendUnicodeStringToString((PUNICODE_STRING)(v12 + 6), a4);
  RtlAppendUnicodeToString((PUNICODE_STRING)(v12 + 6), L"\\IPC$");
  v18 = 0;
  if ( *(_QWORD *)a2 )
    v18 = (*(_DWORD *)(*(_QWORD *)(**(_QWORD **)a2 + 184LL) + 16LL) & 0x400) != 0;
  Parameter[0] = *(_QWORD *)(a2 + 248);
  Parameter[2] = a5;
  v33 = *(_DWORD *)(a2 + 232);
  v35 = *((_QWORD *)v12 + 7);
  p_Handle = &Handle;
  v41 = *(_QWORD *)(a2 + 256);
  v34 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v42 = 0;
  v37 = v18;
  Parameter[1] = v12 + 6;
  inited = KeExpandKernelStackAndCalloutEx(
             (PEXPAND_STACK_CALLOUT)DfscConnOpenIpcConnectionCallout,
             Parameter,
             0x6000u,
             0,
             Context);
  if ( !inited )
    inited = v42;
  if ( inited < 0 )
    goto LABEL_17;
  *((_QWORD *)v12 + 5) = Handle;
  inited = ObReferenceObjectByHandle(Handle, 0, 0, 0, (PVOID *)v12 + 6, 0);
  if ( inited < 0 )
    goto LABEL_17;
LABEL_20:
  if ( inited < 0 )
    goto LABEL_21;
  v20 = 0;
  if ( a3 )
  {
    if ( *(_WORD *)a3 )
    {
      v21 = *(_WORD **)(a3 + 8);
      if ( v21 )
      {
        if ( *v21 )
        {
          KeEnterCriticalRegion();
          ExAcquireResourceSharedLite(&Resource, 1u);
          if ( byte_14000C76E )
          {
            DfscGetIpcConnectionSmbProtocolVersion(v12, &a8, &v26);
            if ( a8 > 2u || a8 == 2 && v26 >= 2u )
            {
              DfscGetSiteName(&String2);
              v20 = 1;
            }
          }
          ExReleaseResourceLite(&Resource);
          KeLeaveCriticalRegion();
        }
      }
    }
  }
  if ( a6 )
    v22 = *(_QWORD *)(a6 + 16);
  else
    v22 = 0;
  if ( a1 != 1 )
  {
    if ( !a1 )
    {
      if ( !a3 || !*(_WORD *)a3 || (v23 = *(_WORD **)(a3 + 8)) == 0 || !*v23 )
      {
        inited = DfscRmGetDomainReferral(a2, (const void **)a3, (__int64)v12);
        goto LABEL_21;
      }
      inited = DfscRmGetDomainDcReferral(a2, (const void **)a3, (__int64)&String2, (__int64)v12, &v27);
      if ( inited < 0 )
        goto LABEL_37;
      v8 = v27;
      *(_OWORD *)(v27 + 128) = *(_OWORD *)(v27 + 144);
      *(_DWORD *)(v8 + 8) = 0;
      KeEnterCriticalRegion();
      ExAcquireResourceSharedLite(&Resource, 1u);
      if ( RtlEqualUnicodeString(&::DestinationString, &String2, 1u) )
        DfscDomainCacheStore(*(_QWORD *)(a2 + 240), v8);
      goto LABEL_61;
    }
    if ( a1 != 2 )
    {
LABEL_40:
      inited = DfscRmCreateRefContext(v8, 0, &v30);
      if ( inited >= 0 )
      {
        v8 = 0;
        if ( a7 )
          *a7 = v30;
      }
      goto LABEL_21;
    }
  }
  inited = DfscRmGetNormalReferral(a2, (const void **)a3, (__int64)&String2, (__int64)v12, &v27, HandleInformation);
  if ( inited < 0 )
  {
LABEL_37:
    v8 = v27;
    goto LABEL_21;
  }
  if ( a1 == 1 && !*(_WORD *)(a2 + 218) )
    *(_WORD *)(a2 + 218) = *(_WORD *)(a2 + 152);
  if ( !a5 || !*(_WORD *)a5 || (v24 = *(_WORD **)(a5 + 8)) == 0 || !*v24 )
    v13 = 0;
  v8 = v27;
  inited = DfscRmSetReferralType(v27, a1, v13);
  if ( inited >= 0 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&Resource, 1u);
    if ( !v20 || RtlEqualUnicodeString(&::DestinationString, &String2, 1u) )
    {
      v8 = DfscRefCacheStore(*(_QWORD *)(a2 + 240), v22, v8);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_55706db06074317498eaf8c01331c814_Traceguids, v8);
    }
LABEL_61:
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    goto LABEL_40;
  }
LABEL_21:
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0);
  if ( inited < 0 && v8 )
    DfscRmDereferenceReferral((volatile signed __int32 *)v8);
  if ( v12 )
    DfscReleaseIpcConnection(v12);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14001b230  mov     [rsp-8+arg_8], rbx
0x14001b235  mov     qword ptr [rsp-8+arg_10], r8
0x14001b23a  mov     [rsp-8+arg_0], ecx
0x14001b23e  push    rbp
0x14001b23f  push    rsi
0x14001b240  push    rdi
0x14001b241  push    r12
0x14001b243  push    r13
0x14001b245  push    r14
0x14001b247  push    r15
0x14001b249  lea     rbp, [rsp-7]
0x14001b24e  sub     rsp, 0C0h
0x14001b255  xor     edi, edi
0x14001b257  xorps   xmm0, xmm0
0x14001b25a  mov     r13d, edi
0x14001b25d  mov     [rsp+0F0h+var_B8], rdi
0x14001b262  mov     [rbp+37h+var_98], rdi
0x14001b266  mov     rsi, r9
0x14001b269  movups  xmmword ptr [rbp+37h+String2.Length], xmm0
0x14001b26d  mov     [rbp+37h+arg_38], di
0x14001b271  mov     r15, rdx
0x14001b274  mov     [rsp+0F0h+var_C0], di
0x14001b279  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b280  lea     rax, WPP_GLOBAL_Control
0x14001b287  cmp     rcx, rax
0x14001b28a  jz      short loc_14001B299
0x14001b28c  test    dword ptr [rcx+2Ch], 400000h
0x14001b293  jnz     loc_14001B7CB
0x14001b299  xorps   xmm0, xmm0
0x14001b29c  mov     [rbp+37h+String2.Buffer], rdi
0x14001b2a0  mov     r14d, 40h ; '@'
0x14001b2a6  mov     dword ptr [rbp+37h+String2.Length], edi
0x14001b2a9  mov     edx, r14d
0x14001b2ac  mov     [rbp+37h+Handle], rdi
0x14001b2b0  mov     r8d, 63436644h
0x14001b2b6  mov     ecx, 102h
0x14001b2bb  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x14001b2bf  call    cs:__imp_ExAllocatePool2
0x14001b2c6  nop     dword ptr [rax+rax+00h]
0x14001b2cb  mov     rbx, rax
0x14001b2ce  mov     r12d, 1
0x14001b2d4  test    rax, rax
0x14001b2d7  jz      loc_14001B7EA
0x14001b2dd  mov     r8d, r14d; Size
0x14001b2e0  xor     edx, edx; Val
0x14001b2e2  mov     rcx, rax; void *
0x14001b2e5  call    memset
0x14001b2ea  movzx   eax, word ptr [rsi+2]
0x14001b2ee  test    ax, ax
0x14001b2f1  jz      loc_14001B7FC
0x14001b2f7  mov     edx, eax
0x14001b2f9  mov     ecx, 102h
0x14001b2fe  mov     r8d, 76436644h
0x14001b304  call    cs:__imp_ExAllocatePool2
0x14001b30b  nop     dword ptr [rax+rax+00h]
0x14001b310  mov     [rbx+10h], rax
0x14001b314  test    rax, rax
0x14001b317  jz      loc_14001B7EA
0x14001b31d  mov     dword ptr [rbx], 408105h
0x14001b323  mov     [rbx+4], r12d
0x14001b327  movzx   ecx, word ptr [rsi]
0x14001b32a  test    cx, cx
0x14001b32d  jz      loc_14001B710
0x14001b333  cmp     [rsi+2], di
0x14001b337  jz      loc_14001B710
0x14001b33d  mov     rdx, [rsi+8]; Src
0x14001b341  mov     r8d, ecx; Size
0x14001b344  mov     rcx, rax; void *
0x14001b347  call    memmove
0x14001b34c  movzx   eax, word ptr [rsi]
0x14001b34f  mov     [rbx+8], ax
0x14001b353  movzx   eax, word ptr [rsi+2]
0x14001b357  mov     [rbx+0Ah], ax
0x14001b35b  mov     rax, [r15+0E0h]
0x14001b362  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x14001b369  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x14001b36d  mov     [rbx+38h], rax
0x14001b371  call    cs:__imp_RtlInitUnicodeStringEx
0x14001b378  nop     dword ptr [rax+rax+00h]
0x14001b37d  mov     edi, eax
0x14001b37f  test    eax, eax
0x14001b381  js      loc_14001B4C5
0x14001b387  xor     eax, eax
0x14001b389  lea     rdi, [rbx+18h]
0x14001b38d  mov     [rdi], ax
0x14001b390  mov     ecx, 102h
0x14001b395  movzx   eax, [rbp+37h+DestinationString.Length]
0x14001b399  mov     r8d, 70436644h
0x14001b39f  add     ax, 12h
0x14001b3a3  add     ax, [rsi]
0x14001b3a6  movzx   edx, ax
0x14001b3a9  mov     [rdi+2], dx
0x14001b3ad  call    cs:__imp_ExAllocatePool2
0x14001b3b4  nop     dword ptr [rax+rax+00h]
0x14001b3b9  mov     [rdi+8], rax
0x14001b3bd  test    rax, rax
0x14001b3c0  jz      loc_14001B804
0x14001b3c6  lea     rdx, [rbp+37h+DestinationString]; Source
0x14001b3ca  mov     rcx, rdi; Destination
0x14001b3cd  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001b3d4  nop     dword ptr [rax+rax+00h]
0x14001b3d9  lea     rdx, Source; "\\"
0x14001b3e0  mov     rcx, rdi; Destination
0x14001b3e3  call    cs:__imp_RtlAppendUnicodeToString
0x14001b3ea  nop     dword ptr [rax+rax+00h]
0x14001b3ef  mov     rdx, rsi; Source
0x14001b3f2  mov     rcx, rdi; Destination
0x14001b3f5  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001b3fc  nop     dword ptr [rax+rax+00h]
0x14001b401  lea     rdx, aIpc; "\\IPC$"
0x14001b408  mov     rcx, rdi; Destination
0x14001b40b  call    cs:__imp_RtlAppendUnicodeToString
0x14001b412  nop     dword ptr [rax+rax+00h]
0x14001b417  mov     rax, [r15]
0x14001b41a  xor     dl, dl
0x14001b41c  test    rax, rax
0x14001b41f  jz      short loc_14001B439
0x14001b421  mov     rax, [rax]
0x14001b424  movzx   edx, dl
0x14001b427  mov     rcx, [rax+0B8h]
0x14001b42e  test    dword ptr [rcx+10h], 400h
0x14001b435  cmovnz  edx, r12d
0x14001b439  mov     rax, [r15+0F8h]
0x14001b440  xor     ecx, ecx
0x14001b442  mov     [rbp+37h+Parameter], rax
0x14001b446  xor     r9d, r9d; Wait
0x14001b449  mov     rax, [rbp+37h+arg_20]
0x14001b44d  mov     r8d, 6000h; Size
0x14001b453  mov     [rbp+37h+var_70], rax
0x14001b457  mov     eax, [r15+0E8h]
0x14001b45e  mov     [rbp+37h+var_68], eax
0x14001b461  mov     rax, [rbx+38h]
0x14001b465  mov     [rbp+37h+var_60], rax
0x14001b469  lea     rax, [rbp+37h+Handle]
0x14001b46d  mov     [rbp+37h+var_58], rax
0x14001b471  mov     rax, [r15+100h]
0x14001b478  mov     [rbp+37h+var_48], rax
0x14001b47c  mov     rax, cs:Context
0x14001b483  mov     [rbp+37h+var_64], ecx
0x14001b486  mov     [rbp+37h+var_4F], ecx
0x14001b489  mov     [rbp+37h+var_4B], cx
0x14001b48d  mov     [rbp+37h+var_49], cl
0x14001b490  mov     [rbp+37h+var_40], rcx
0x14001b494  lea     rcx, DfscConnOpenIpcConnectionCallout; Callout
0x14001b49b  mov     [rbp+37h+var_50], dl
0x14001b49e  lea     rdx, [rbp+37h+Parameter]; Parameter
0x14001b4a2  mov     [rsp+0F0h+Context], rax; Context
0x14001b4a7  mov     [rbp+37h+var_78], rdi
0x14001b4ab  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14001b4b2  nop     dword ptr [rax+rax+00h]
0x14001b4b7  mov     edi, eax
0x14001b4b9  test    eax, eax
0x14001b4bb  jz      loc_14001B810
0x14001b4c1  test    edi, edi
0x14001b4c3  jns     short loc_14001B4D1
0x14001b4c5  mov     rcx, rbx; P
0x14001b4c8  call    DfscReleaseIpcConnection
0x14001b4cd  xor     ebx, ebx
0x14001b4cf  jmp     short loc_14001B505
0x14001b4d1  mov     rax, [rbp+37h+Handle]
0x14001b4d5  xor     r9d, r9d; AccessMode
0x14001b4d8  mov     [rbx+28h], rax
0x14001b4dc  xor     r8d, r8d; ObjectType
0x14001b4df  mov     rcx, [rbp+37h+Handle]; Handle
0x14001b4e3  lea     rax, [rbx+30h]
0x14001b4e7  mov     [rsp+0F0h+HandleInformation], r13; P
0x14001b4ec  xor     edx, edx; DesiredAccess
0x14001b4ee  mov     [rsp+0F0h+Context], rax; Object
0x14001b4f3  call    cs:__imp_ObReferenceObjectByHandle
0x14001b4fa  nop     dword ptr [rax+rax+00h]
0x14001b4ff  mov     edi, eax
0x14001b501  test    eax, eax
0x14001b503  js      short loc_14001B4C5
0x14001b505  test    edi, edi
0x14001b507  jns     short loc_14001B54A
0x14001b509  mov     rcx, [rbp+37h+String2.Buffer]; P
0x14001b50d  test    rcx, rcx
0x14001b510  jnz     loc_14001B900
0x14001b516  test    edi, edi
0x14001b518  jns     short loc_14001B523
0x14001b51a  test    r13, r13
0x14001b51d  jnz     loc_14001B913
0x14001b523  test    rbx, rbx
0x14001b526  jnz     loc_14001B920
0x14001b52c  mov     rbx, [rsp+0F0h+arg_8]
0x14001b534  mov     eax, edi
0x14001b536  add     rsp, 0C0h
0x14001b53d  pop     r15
0x14001b53f  pop     r14
0x14001b541  pop     r13
0x14001b543  pop     r12
0x14001b545  pop     rdi
0x14001b546  pop     rsi
0x14001b547  pop     rbp
0x14001b548  retn
0x14001b54a  mov     rdi, qword ptr [rbp+37h+arg_10]
0x14001b54e  xor     r14b, r14b
0x14001b551  test    rdi, rdi
0x14001b554  jz      short loc_14001B56F
0x14001b556  cmp     [rdi], r13w
0x14001b55a  jz      short loc_14001B56F
0x14001b55c  mov     rax, [rdi+8]
0x14001b560  test    rax, rax
0x14001b563  jz      short loc_14001B56F
0x14001b565  cmp     [rax], r13w
0x14001b569  jnz     loc_14001B6BC
0x14001b56f  mov     rax, [rbp+37h+arg_28]
0x14001b573  test    rax, rax
0x14001b576  jnz     short loc_14001B5EF
0x14001b578  xor     esi, esi
0x14001b57a  mov     eax, [rbp+37h+arg_0]
0x14001b57d  cmp     eax, r12d
0x14001b580  jnz     short loc_14001B5B2
0x14001b582  lea     rax, [rsp+0F0h+var_B8]
0x14001b587  mov     r9, rbx; int
0x14001b58a  lea     r8, [rbp+37h+String2]; int
0x14001b58e  mov     [rsp+0F0h+Context], rax; __int64
0x14001b593  mov     rdx, rdi; int
0x14001b596  mov     rcx, r15; int
0x14001b599  call    DfscRmGetNormalReferral
0x14001b59e  mov     edi, eax
0x14001b5a0  test    eax, eax
0x14001b5a2  jns     loc_14001B732
0x14001b5a8  mov     r13, [rsp+0F0h+var_B8]
0x14001b5ad  jmp     loc_14001B509
0x14001b5b2  test    eax, eax
0x14001b5b4  jz      short loc_14001B5F5
0x14001b5b6  cmp     eax, 2
0x14001b5b9  jz      short loc_14001B582
0x14001b5bb  lea     r8, [rbp+37h+var_98]
0x14001b5bf  xor     edx, edx
0x14001b5c1  mov     rcx, r13
0x14001b5c4  call    DfscRmCreateRefContext
0x14001b5c9  mov     edi, eax
0x14001b5cb  test    eax, eax
0x14001b5cd  js      loc_14001B509
0x14001b5d3  mov     rcx, [rbp+37h+arg_30]
0x14001b5d7  xor     r13d, r13d
0x14001b5da  test    rcx, rcx
0x14001b5dd  jz      loc_14001B509
0x14001b5e3  mov     rax, [rbp+37h+var_98]
0x14001b5e7  mov     [rcx], rax
0x14001b5ea  jmp     loc_14001B509
0x14001b5ef  mov     rsi, [rax+10h]
0x14001b5f3  jmp     short loc_14001B57A
0x14001b5f5  test    rdi, rdi
0x14001b5f8  jz      loc_14001B71D
0x14001b5fe  cmp     [rdi], r13w
0x14001b602  jz      loc_14001B71D
0x14001b608  mov     rax, [rdi+8]
0x14001b60c  test    rax, rax
0x14001b60f  jz      loc_14001B71D
0x14001b615  cmp     [rax], r13w
0x14001b619  jz      loc_14001B71D
0x14001b61f  lea     rax, [rsp+0F0h+var_B8]
0x14001b624  mov     r9, rbx
0x14001b627  lea     r8, [rbp+37h+String2]
0x14001b62b  mov     [rsp+0F0h+Context], rax
0x14001b630  mov     rdx, rdi
0x14001b633  mov     rcx, r15
0x14001b636  call    DfscRmGetDomainDcReferral
0x14001b63b  mov     edi, eax
0x14001b63d  test    eax, eax
0x14001b63f  js      loc_14001B5A8
0x14001b645  mov     r13, [rsp+0F0h+var_B8]
0x14001b64a  movups  xmm0, xmmword ptr [r13+90h]
0x14001b652  movups  xmmword ptr [r13+80h], xmm0
0x14001b65a  mov     dword ptr [r13+8], 0
0x14001b662  call    cs:__imp_KeEnterCriticalRegion
0x14001b669  nop     dword ptr [rax+rax+00h]
0x14001b66e  movzx   edx, r12b; Wait
0x14001b672  lea     rcx, Resource; Resource
0x14001b679  call    cs:__imp_ExAcquireResourceSharedLite
0x14001b680  nop     dword ptr [rax+rax+00h]
0x14001b685  movzx   r8d, r12b; CaseInSensitive
0x14001b689  lea     rdx, [rbp+37h+String2]; String2
0x14001b68d  lea     rcx, DestinationString; String1
0x14001b694  call    cs:__imp_RtlEqualUnicodeString
0x14001b69b  nop     dword ptr [rax+rax+00h]
0x14001b6a0  test    al, al
0x14001b6a2  jz      loc_14001B7A7
0x14001b6a8  mov     rcx, [r15+0F0h]
0x14001b6af  mov     rdx, r13
0x14001b6b2  call    DfscDomainCacheStore
0x14001b6b7  jmp     loc_14001B7A7
0x14001b6bc  call    cs:__imp_KeEnterCriticalRegion
0x14001b6c3  nop     dword ptr [rax+rax+00h]
0x14001b6c8  movzx   edx, r12b; Wait
0x14001b6cc  lea     rcx, Resource; Resource
0x14001b6d3  call    cs:__imp_ExAcquireResourceSharedLite
0x14001b6da  nop     dword ptr [rax+rax+00h]
0x14001b6df  cmp     cs:byte_14000C76E, r13b
0x14001b6e6  jnz     loc_14001B818
0x14001b6ec  lea     rcx, Resource; Resource
0x14001b6f3  call    cs:__imp_ExReleaseResourceLite
0x14001b6fa  nop     dword ptr [rax+rax+00h]
0x14001b6ff  call    cs:__imp_KeLeaveCriticalRegion
0x14001b706  nop     dword ptr [rax+rax+00h]
0x14001b70b  jmp     loc_14001B56F
0x14001b710  mov     [rsi+2], di
  ... truncated ...
```
