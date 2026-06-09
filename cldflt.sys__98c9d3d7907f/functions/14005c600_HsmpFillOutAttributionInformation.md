# HsmpFillOutAttributionInformation

- ea: `0x14005c600`
- end: `0x14005c8b4`
- name: `HsmpFillOutAttributionInformation`
- size: `692`
- prototype: ``
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140007bb0`
- `0x14000a674`
- `0x14005aaf0`
- `0x14005be10`
- `0x14005c580`
- `0x14005c8c0`
- `0x140076734`

## callees

- `0x140003c50`
- `0x140006c64`
- `0x1400074b0`
- `0x140007d60`
- `0x14001e280`
- `0x140048ce8`
- `0x14005c600`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14005c733`
- `ntoskrnl!ObfReferenceObject` at `0x14005c733`
- `ntoskrnl!ExAllocatePool2` at `0x14005c816`
- `ntoskrnl!ExAllocatePool2` at `0x14005c816`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c8a3`
- `ntoskrnl!IoGetCurrentProcess` at `0x14005c8a3`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005c77b`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005c77b`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005c7bd`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14005c7bd`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c6ac`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c721`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c6ac`
- `FLTMGR!FltGetRequestorProcess` at `0x14005c721`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c701`
- `FLTMGR!FltReleasePushLockEx` at `0x14005c701`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c6df`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14005c6df`

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
  unsigned int ExtraCreateParameter; // eax
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
    || (v16 = HsmpValidateAttributionEcp(), HsmDbgBreakOnStatus((unsigned int)v16), v16 < 0) )
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
0x14005c600  mov     rax, rsp
0x14005c603  mov     [rax+10h], rbx
0x14005c607  mov     [rax+18h], rbp
0x14005c60b  push    rsi
0x14005c60c  push    rdi
0x14005c60d  push    r12
0x14005c60f  push    r14
0x14005c611  push    r15
0x14005c613  sub     rsp, 40h
0x14005c617  xor     r12d, r12d
0x14005c61a  mov     rbp, r9
0x14005c61d  mov     edi, r12d
0x14005c620  mov     [rax-30h], r12
0x14005c624  cmp     cs:byte_140029557, dil
0x14005c62b  mov     r14, r8
0x14005c62e  mov     r15, rdx
0x14005c631  mov     [rax+8], dil
0x14005c635  mov     rsi, rcx
0x14005c638  mov     [rax-38h], r12
0x14005c63c  mov     [rax+20h], r12d
0x14005c640  jnz     loc_14005C748
0x14005c646  test    rsi, rsi
0x14005c649  jz      short loc_14005C659
0x14005c64b  mov     eax, [rsi+28h]
0x14005c64e  test    al, 20h
0x14005c650  jz      short loc_14005C659
0x14005c652  mov     edi, [rsi+40h]
0x14005c655  test    edi, edi
0x14005c657  jnz     short loc_14005C66C
0x14005c659  test    r14, r14
0x14005c65c  jz      short loc_14005C69B
0x14005c65e  mov     rcx, r14
0x14005c661  call    HsmOsGetProxiedProcessId
0x14005c666  mov     edi, eax
0x14005c668  test    eax, eax
0x14005c66a  jz      short loc_14005C69B
0x14005c66c  mov     ecx, edi; ProcessId
0x14005c66e  call    HsmOsReferenceProcessByProcessId
0x14005c673  test    rax, rax
0x14005c676  jz      loc_14005C715
0x14005c67c  mov     [rbp+10h], rax
0x14005c680  mov     rbx, [rsp+68h+arg_8]
0x14005c685  mov     rbp, [rsp+68h+arg_10]
0x14005c68d  add     rsp, 40h
0x14005c691  pop     r15
0x14005c693  pop     r14
0x14005c695  pop     r12
0x14005c697  pop     rdi
0x14005c698  pop     rsi
0x14005c699  retn
0x14005c69b  test    r15, r15
0x14005c69e  jz      short loc_14005C715
0x14005c6a0  test    r14, r14
0x14005c6a3  jz      loc_14005C89B
0x14005c6a9  mov     rcx, r14; CallbackData
0x14005c6ac  call    cs:__imp_FltGetRequestorProcess
0x14005c6b3  nop     dword ptr [rax+rax+00h]
0x14005c6b8  lea     r8, [rsp+68h+arg_0]
0x14005c6bd  mov     [rbp+10h], rax
0x14005c6c1  mov     edx, 3
0x14005c6c6  mov     rcx, rbp
0x14005c6c9  call    HsmOsCheckAppCompatPolicy
0x14005c6ce  test    eax, eax
0x14005c6d0  js      short loc_14005C715
0x14005c6d2  cmp     [rsp+68h+arg_0], r12b
0x14005c6d7  jnz     short loc_14005C715
0x14005c6d9  xor     edx, edx
0x14005c6db  lea     rcx, [r15+40h]
0x14005c6df  call    cs:__imp_FltAcquirePushLockSharedEx
0x14005c6e6  nop     dword ptr [rax+rax+00h]
0x14005c6eb  mov     rcx, [r15+58h]
0x14005c6ef  lea     rax, [r15+58h]
0x14005c6f3  cmp     rcx, rax
0x14005c6f6  jz      short loc_14005C6FB
0x14005c6f8  mov     edi, [rcx+28h]
0x14005c6fb  xor     edx, edx
0x14005c6fd  lea     rcx, [r15+40h]
0x14005c701  call    cs:__imp_FltReleasePushLockEx
0x14005c708  nop     dword ptr [rax+rax+00h]
0x14005c70d  test    edi, edi
0x14005c70f  jnz     loc_14005C66C
0x14005c715  test    r14, r14
0x14005c718  jz      loc_14005C8A3
0x14005c71e  mov     rcx, r14; CallbackData
0x14005c721  call    cs:__imp_FltGetRequestorProcess
0x14005c728  nop     dword ptr [rax+rax+00h]
0x14005c72d  mov     rcx, rax; Object
0x14005c730  mov     rbx, rax
0x14005c733  call    cs:__imp_ObfReferenceObject
0x14005c73a  nop     dword ptr [rax+rax+00h]
0x14005c73f  mov     [rbp+10h], rbx
0x14005c743  jmp     loc_14005C680
0x14005c748  test    rsi, rsi
0x14005c74b  jz      short loc_14005C76C
0x14005c74d  mov     rax, [rcx+50h]
0x14005c751  test    rax, rax
0x14005c754  jz      short loc_14005C76C
0x14005c756  cmp     dword ptr [rcx+58h], 50h ; 'P'
0x14005c75a  jbe     short loc_14005C76C
0x14005c75c  mov     [r9+8], rax
0x14005c760  mov     eax, [rcx+58h]
0x14005c763  mov     [r9+4], eax
0x14005c767  jmp     loc_14005C64B
0x14005c76c  mov     rcx, cs:Filter; Filter
0x14005c773  lea     r8, [rsp+68h+EcpList]; EcpList
0x14005c778  mov     rdx, r14; CallbackData
0x14005c77b  call    cs:__imp_FltGetEcpListFromCallbackData
0x14005c782  nop     dword ptr [rax+rax+00h]
0x14005c787  test    eax, eax
0x14005c789  js      loc_14005C646
0x14005c78f  mov     rdx, [rsp+68h+EcpList]; EcpList
0x14005c794  test    rdx, rdx
0x14005c797  jz      loc_14005C646
0x14005c79d  mov     rcx, cs:Filter; Filter
0x14005c7a4  lea     rax, [rsp+68h+arg_18]
0x14005c7ac  lea     r9, [rsp+68h+EcpContext]; EcpContext
0x14005c7b1  mov     [rsp+68h+EcpContextSize], rax; EcpContextSize
0x14005c7b6  lea     r8, GUID_ECP_CLOUDFILES_ATTRIBUTION; EcpType
0x14005c7bd  call    cs:__imp_FltFindExtraCreateParameter
0x14005c7c4  nop     dword ptr [rax+rax+00h]
0x14005c7c9  mov     ecx, eax
0x14005c7cb  call    HsmDbgBreakOnStatus
0x14005c7d0  mov     rcx, [rsp+68h+EcpContext]
0x14005c7d5  test    rcx, rcx
0x14005c7d8  jz      loc_14005C646
0x14005c7de  mov     edx, [rsp+68h+arg_18]
0x14005c7e5  cmp     edx, 50h ; 'P'
0x14005c7e8  jbe     loc_14005C646
0x14005c7ee  call    HsmpValidateAttributionEcp
0x14005c7f3  mov     ecx, eax
0x14005c7f5  mov     ebx, eax
0x14005c7f7  call    HsmDbgBreakOnStatus
0x14005c7fc  test    ebx, ebx
0x14005c7fe  js      loc_14005C646
0x14005c804  mov     edx, [rsp+68h+arg_18]
0x14005c80b  mov     ecx, 102h
0x14005c810  mov     r8d, 69417348h
0x14005c816  call    cs:__imp_ExAllocatePool2
0x14005c81d  nop     dword ptr [rax+rax+00h]
0x14005c822  test    rsi, rsi
0x14005c825  jz      short loc_14005C866
0x14005c827  mov     [rsi+50h], rax
0x14005c82b  test    rax, rax
0x14005c82e  jz      loc_14005C64B
0x14005c834  mov     r8d, [rsp+68h+arg_18]; Size
0x14005c83c  mov     rcx, rax; void *
0x14005c83f  mov     rdx, [rsp+68h+EcpContext]; Src
0x14005c844  call    memmove
0x14005c849  mov     eax, [rsp+68h+arg_18]
0x14005c850  mov     [rsi+58h], eax
0x14005c853  mov     rax, [rsi+50h]
0x14005c857  mov     [rbp+8], rax
0x14005c85b  mov     eax, [rsi+58h]
0x14005c85e  mov     [rbp+4], eax
0x14005c861  jmp     loc_14005C64B
0x14005c866  mov     [rbp+8], rax
0x14005c86a  test    rax, rax
0x14005c86d  jz      loc_14005C659
0x14005c873  mov     r8d, [rsp+68h+arg_18]; Size
0x14005c87b  mov     rcx, rax; void *
0x14005c87e  mov     rdx, [rsp+68h+EcpContext]; Src
0x14005c883  call    memmove
0x14005c888  mov     eax, [rsp+68h+arg_18]
0x14005c88f  or      dword ptr [rbp+0], 1
0x14005c893  mov     [rbp+4], eax
0x14005c896  jmp     loc_14005C659
0x14005c89b  mov     rax, r12
0x14005c89e  jmp     loc_14005C6B8
0x14005c8a3  call    cs:__imp_IoGetCurrentProcess
0x14005c8aa  nop     dword ptr [rax+rax+00h]
0x14005c8af  jmp     loc_14005C72D
```
