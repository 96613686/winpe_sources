# HsmpFillOutAttributionInformation

- ea: `0x14005c720`
- end: `0x14005c9d4`
- name: `HsmpFillOutAttributionInformation`
- size: `692`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007bb0`
- `0x14000a674`
- `0x14005ac10`
- `0x14005bf30`
- `0x14005c6a0`
- `0x14005c9e0`
- `0x14007686c`

## callees

- `0x140003c50`
- `0x140006c64`
- `0x1400074b0`
- `0x140007d60`
- `0x14001e300`
- `0x140048dd8`
- `0x14005c720`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14005c853`
- `ntoskrnl!ObfReferenceObject` at `0x14005c853`
- `ntoskrnl!ExAllocatePool2` at `0x14005c936`
- `ntoskrnl!ExAllocatePool2` at `0x14005c936`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c9c3`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c9c3`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005c89b`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005c89b`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005c8dd`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005c8dd`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c7cc`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c841`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c7cc`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c841`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c821`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c821`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c7ff`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c7ff`

## pseudocode

```c
LONG_PTR __fastcall HsmpFillOutAttributionInformation(
        __int64 a1,
        __int64 a2,
        struct _FLT_CALLBACK_DATA *a3,
        __int64 a4)
{
  unsigned int ProxiedProcessId; // edi
  LONG_PTR result; // rax
  PEPROCESS v10; // rax
  __int64 v11; // rcx
  PEPROCESS RequestorProcess; // rax
  PEPROCESS v13; // rbx
  __int64 v14; // rax
  NTSTATUS ExtraCreateParameter; // eax
  int v16; // ebx
  void *Pool2; // rax
  ULONG v18; // eax
  PVOID EcpContext; // [rsp+30h] [rbp-38h] BYREF
  PECP_LIST EcpList; // [rsp+38h] [rbp-30h] BYREF
  char v21; // [rsp+70h] [rbp+8h] BYREF
  ULONG EcpContextSize; // [rsp+88h] [rbp+20h] BYREF

  ProxiedProcessId = 0;
  EcpList = 0;
  v21 = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  if ( !byte_140029557 )
    goto LABEL_2;
  if ( a1 )
  {
    v14 = *(_QWORD *)(a1 + 80);
    if ( v14 )
    {
      if ( *(_DWORD *)(a1 + 88) > 0x50u )
      {
        *(_QWORD *)(a4 + 8) = v14;
        *(_DWORD *)(a4 + 4) = *(_DWORD *)(a1 + 88);
        goto LABEL_3;
      }
    }
  }
  if ( FltGetEcpListFromCallbackData(Filter, a3, &EcpList) < 0
    || !EcpList
    || (ExtraCreateParameter = FltFindExtraCreateParameter(
                                 Filter,
                                 EcpList,
                                 &GUID_ECP_CLOUDFILES_ATTRIBUTION,
                                 &EcpContext,
                                 &EcpContextSize),
        HsmDbgBreakOnStatus(ExtraCreateParameter),
        !EcpContext)
    || EcpContextSize <= 0x50
    || (v16 = HsmpValidateAttributionEcp(EcpContext, EcpContextSize), HsmDbgBreakOnStatus(v16), v16 < 0) )
  {
LABEL_2:
    if ( a1 )
      goto LABEL_3;
LABEL_5:
    if ( !a3 || (ProxiedProcessId = HsmOsGetProxiedProcessId((__int64)a3)) == 0 )
    {
      if ( !a2 )
        goto LABEL_17;
      v10 = a3 ? FltGetRequestorProcess(a3) : 0LL;
      *(_QWORD *)(a4 + 16) = v10;
      if ( (int)HsmOsCheckAppCompatPolicy(a4, 3, &v21) < 0 || v21 )
        goto LABEL_17;
      FltAcquirePushLockSharedEx(a2 + 64, 0);
      v11 = *(_QWORD *)(a2 + 88);
      if ( v11 != a2 + 88 )
        ProxiedProcessId = *(_DWORD *)(v11 + 40);
      FltReleasePushLockEx(a2 + 64, 0);
      if ( !ProxiedProcessId )
        goto LABEL_17;
    }
    goto LABEL_7;
  }
  Pool2 = (void *)ExAllocatePool2(258, EcpContextSize, 1765897032);
  if ( !a1 )
  {
    *(_QWORD *)(a4 + 8) = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, EcpContext, EcpContextSize);
      v18 = EcpContextSize;
      *(_DWORD *)a4 |= 1u;
      *(_DWORD *)(a4 + 4) = v18;
    }
    goto LABEL_5;
  }
  *(_QWORD *)(a1 + 80) = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, EcpContext, EcpContextSize);
    *(_DWORD *)(a1 + 88) = EcpContextSize;
    *(_QWORD *)(a4 + 8) = *(_QWORD *)(a1 + 80);
    *(_DWORD *)(a4 + 4) = *(_DWORD *)(a1 + 88);
  }
LABEL_3:
  if ( (*(_DWORD *)(a1 + 40) & 0x20) == 0 )
    goto LABEL_5;
  ProxiedProcessId = *(_DWORD *)(a1 + 64);
  if ( !ProxiedProcessId )
    goto LABEL_5;
LABEL_7:
  result = (LONG_PTR)HsmOsReferenceProcessByProcessId((HANDLE)ProxiedProcessId);
  if ( result )
  {
    *(_QWORD *)(a4 + 16) = result;
    return result;
  }
LABEL_17:
  if ( a3 )
    RequestorProcess = FltGetRequestorProcess(a3);
  else
    RequestorProcess = IoGetCurrentProcess();
  v13 = RequestorProcess;
  result = ObfReferenceObject(RequestorProcess);
  *(_QWORD *)(a4 + 16) = v13;
  return result;
}

```

## disassembly

```asm
0x14005c720  mov     rax, rsp
0x14005c723  mov     [rax+10h], rbx
0x14005c727  mov     [rax+18h], rbp
0x14005c72b  push    rsi
0x14005c72c  push    rdi
0x14005c72d  push    r12
0x14005c72f  push    r14
0x14005c731  push    r15
0x14005c733  sub     rsp, 40h
0x14005c737  xor     r12d, r12d
0x14005c73a  mov     rbp, r9
0x14005c73d  mov     edi, r12d
0x14005c740  mov     [rax-30h], r12
0x14005c744  cmp     cs:byte_140029557, dil
0x14005c74b  mov     r14, r8
0x14005c74e  mov     r15, rdx
0x14005c751  mov     [rax+8], dil
0x14005c755  mov     rsi, rcx
0x14005c758  mov     [rax-38h], r12
0x14005c75c  mov     [rax+20h], r12d
0x14005c760  jnz     loc_14005C868
0x14005c766  test    rsi, rsi
0x14005c769  jz      short loc_14005C779
0x14005c76b  mov     eax, [rsi+28h]
0x14005c76e  test    al, 20h
0x14005c770  jz      short loc_14005C779
0x14005c772  mov     edi, [rsi+40h]
0x14005c775  test    edi, edi
0x14005c777  jnz     short loc_14005C78C
0x14005c779  test    r14, r14
0x14005c77c  jz      short loc_14005C7BB
0x14005c77e  mov     rcx, r14
0x14005c781  call    HsmOsGetProxiedProcessId
0x14005c786  mov     edi, eax
0x14005c788  test    eax, eax
0x14005c78a  jz      short loc_14005C7BB
0x14005c78c  mov     ecx, edi; ProcessId
0x14005c78e  call    HsmOsReferenceProcessByProcessId
0x14005c793  test    rax, rax
0x14005c796  jz      loc_14005C835
0x14005c79c  mov     [rbp+10h], rax
0x14005c7a0  mov     rbx, [rsp+68h+arg_8]
0x14005c7a5  mov     rbp, [rsp+68h+arg_10]
0x14005c7ad  add     rsp, 40h
0x14005c7b1  pop     r15
0x14005c7b3  pop     r14
0x14005c7b5  pop     r12
0x14005c7b7  pop     rdi
0x14005c7b8  pop     rsi
0x14005c7b9  retn
0x14005c7bb  test    r15, r15
0x14005c7be  jz      short loc_14005C835
0x14005c7c0  test    r14, r14
0x14005c7c3  jz      loc_14005C9BB
0x14005c7c9  mov     rcx, r14; CallbackData
0x14005c7cc  call    cs:__imp_FltGetRequestorProcess
0x14005c7d3  nop     dword ptr [rax+rax+00h]
0x14005c7d8  lea     r8, [rsp+68h+arg_0]
0x14005c7dd  mov     [rbp+10h], rax
0x14005c7e1  mov     edx, 3
0x14005c7e6  mov     rcx, rbp
0x14005c7e9  call    HsmOsCheckAppCompatPolicy
0x14005c7ee  test    eax, eax
0x14005c7f0  js      short loc_14005C835
0x14005c7f2  cmp     [rsp+68h+arg_0], r12b
0x14005c7f7  jnz     short loc_14005C835
0x14005c7f9  xor     edx, edx
0x14005c7fb  lea     rcx, [r15+40h]
0x14005c7ff  call    cs:__imp_FltAcquirePushLockSharedEx
0x14005c806  nop     dword ptr [rax+rax+00h]
0x14005c80b  mov     rcx, [r15+58h]
0x14005c80f  lea     rax, [r15+58h]
0x14005c813  cmp     rcx, rax
0x14005c816  jz      short loc_14005C81B
0x14005c818  mov     edi, [rcx+28h]
0x14005c81b  xor     edx, edx
0x14005c81d  lea     rcx, [r15+40h]
0x14005c821  call    cs:__imp_FltReleasePushLockEx
0x14005c828  nop     dword ptr [rax+rax+00h]
0x14005c82d  test    edi, edi
0x14005c82f  jnz     loc_14005C78C
0x14005c835  test    r14, r14
0x14005c838  jz      loc_14005C9C3
0x14005c83e  mov     rcx, r14; CallbackData
0x14005c841  call    cs:__imp_FltGetRequestorProcess
0x14005c848  nop     dword ptr [rax+rax+00h]
0x14005c84d  mov     rcx, rax; Object
0x14005c850  mov     rbx, rax
0x14005c853  call    cs:__imp_ObfReferenceObject
0x14005c85a  nop     dword ptr [rax+rax+00h]
0x14005c85f  mov     [rbp+10h], rbx
0x14005c863  jmp     loc_14005C7A0
0x14005c868  test    rsi, rsi
0x14005c86b  jz      short loc_14005C88C
0x14005c86d  mov     rax, [rcx+50h]
0x14005c871  test    rax, rax
0x14005c874  jz      short loc_14005C88C
0x14005c876  cmp     dword ptr [rcx+58h], 50h ; 'P'
0x14005c87a  jbe     short loc_14005C88C
0x14005c87c  mov     [r9+8], rax
0x14005c880  mov     eax, [rcx+58h]
0x14005c883  mov     [r9+4], eax
0x14005c887  jmp     loc_14005C76B
0x14005c88c  mov     rcx, cs:Filter; Filter
0x14005c893  lea     r8, [rsp+68h+EcpList]; EcpList
0x14005c898  mov     rdx, r14; CallbackData
0x14005c89b  call    cs:__imp_FltGetEcpListFromCallbackData
0x14005c8a2  nop     dword ptr [rax+rax+00h]
0x14005c8a7  test    eax, eax
0x14005c8a9  js      loc_14005C766
0x14005c8af  mov     rdx, [rsp+68h+EcpList]; EcpList
0x14005c8b4  test    rdx, rdx
0x14005c8b7  jz      loc_14005C766
0x14005c8bd  mov     rcx, cs:Filter; Filter
0x14005c8c4  lea     rax, [rsp+68h+arg_18]
0x14005c8cc  lea     r9, [rsp+68h+EcpContext]; EcpContext
0x14005c8d1  mov     [rsp+68h+EcpContextSize], rax; EcpContextSize
0x14005c8d6  lea     r8, GUID_ECP_CLOUDFILES_ATTRIBUTION; EcpType
0x14005c8dd  call    cs:__imp_FltFindExtraCreateParameter
0x14005c8e4  nop     dword ptr [rax+rax+00h]
0x14005c8e9  mov     ecx, eax
0x14005c8eb  call    HsmDbgBreakOnStatus
0x14005c8f0  mov     rcx, [rsp+68h+EcpContext]
0x14005c8f5  test    rcx, rcx
0x14005c8f8  jz      loc_14005C766
0x14005c8fe  mov     edx, [rsp+68h+arg_18]
0x14005c905  cmp     edx, 50h ; 'P'
0x14005c908  jbe     loc_14005C766
0x14005c90e  call    HsmpValidateAttributionEcp
0x14005c913  mov     ecx, eax
0x14005c915  mov     ebx, eax
0x14005c917  call    HsmDbgBreakOnStatus
0x14005c91c  test    ebx, ebx
0x14005c91e  js      loc_14005C766
0x14005c924  mov     edx, [rsp+68h+arg_18]
0x14005c92b  mov     ecx, 102h
0x14005c930  mov     r8d, 69417348h
0x14005c936  call    cs:__imp_ExAllocatePool2
0x14005c93d  nop     dword ptr [rax+rax+00h]
0x14005c942  test    rsi, rsi
0x14005c945  jz      short loc_14005C986
0x14005c947  mov     [rsi+50h], rax
0x14005c94b  test    rax, rax
0x14005c94e  jz      loc_14005C76B
0x14005c954  mov     r8d, [rsp+68h+arg_18]; Size
0x14005c95c  mov     rcx, rax; void *
0x14005c95f  mov     rdx, [rsp+68h+EcpContext]; Src
0x14005c964  call    memmove
0x14005c969  mov     eax, [rsp+68h+arg_18]
0x14005c970  mov     [rsi+58h], eax
0x14005c973  mov     rax, [rsi+50h]
0x14005c977  mov     [rbp+8], rax
0x14005c97b  mov     eax, [rsi+58h]
0x14005c97e  mov     [rbp+4], eax
0x14005c981  jmp     loc_14005C76B
0x14005c986  mov     [rbp+8], rax
0x14005c98a  test    rax, rax
0x14005c98d  jz      loc_14005C779
0x14005c993  mov     r8d, [rsp+68h+arg_18]; Size
0x14005c99b  mov     rcx, rax; void *
0x14005c99e  mov     rdx, [rsp+68h+EcpContext]; Src
0x14005c9a3  call    memmove
0x14005c9a8  mov     eax, [rsp+68h+arg_18]
0x14005c9af  or      dword ptr [rbp+0], 1
0x14005c9b3  mov     [rbp+4], eax
0x14005c9b6  jmp     loc_14005C779
0x14005c9bb  mov     rax, r12
0x14005c9be  jmp     loc_14005C7D8
0x14005c9c3  call    cs:__imp_IoGetCurrentProcess
0x14005c9ca  nop     dword ptr [rax+rax+00h]
0x14005c9cf  jmp     loc_14005C84D
```
