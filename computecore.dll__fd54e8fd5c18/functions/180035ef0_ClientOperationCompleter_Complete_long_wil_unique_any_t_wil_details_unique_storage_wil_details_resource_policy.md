# ClientOperationCompleter::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)

- ea: `0x180035ef0`
- end: `0x180035fbb`
- name: `?Complete@ClientOperationCompleter@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036ae0`

## callees

- `0x18002a0b4`
- `0x180035ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035f3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180035f3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f2c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180035f53`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180035f53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fa2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035f71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035fa2`

## pseudocode

```c
char __fastcall ClientOperationCompleter::Complete(__int64 a1, int a2, HLOCAL *a3)
{
  void **v5; // r14
  void *v6; // rbp
  HLOCAL v7; // r15
  DWORD LastError; // ebx
  RTL_SRWLOCK *v10; // rcx

  if ( *(_QWORD *)(a1 + 16) )
  {
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 16LL) = a2;
    v5 = (void **)(*(_QWORD *)(a1 + 24) + 24LL);
    if ( v5 != a3 )
    {
      v6 = *v5;
      v7 = *a3;
      if ( *v5 )
      {
        LastError = GetLastError();
        LocalFree(v6);
        SetLastError(LastError);
      }
      *v5 = v7;
      *a3 = 0;
    }
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 16));
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    if ( *a3 )
      LocalFree(*a3);
    return 0;
  }
  else
  {
    v10 = *(RTL_SRWLOCK **)a1;
    *a3 = 0;
    ClientOperation::Complete(v10);
    if ( *a3 )
      LocalFree(*a3);
    return 1;
  }
}

```

## disassembly

```asm
0x180035ef0  mov     [rsp+arg_18], rbx
0x180035ef5  push    rbp
0x180035ef6  push    rsi
0x180035ef7  push    rdi
0x180035ef8  push    r14
0x180035efa  push    r15
0x180035efc  sub     rsp, 30h
0x180035f00  cmp     qword ptr [rcx+10h], 0
0x180035f05  mov     rdi, r8
0x180035f08  mov     rsi, rcx
0x180035f0b  jz      short loc_180035F7B
0x180035f0d  mov     rax, [rcx+18h]
0x180035f11  mov     [rax+10h], edx
0x180035f14  mov     r14, [rcx+18h]
0x180035f18  add     r14, 18h
0x180035f1c  cmp     r14, r8
0x180035f1f  jz      short loc_180035F4F
0x180035f21  mov     rbp, [r14]
0x180035f24  mov     r15, [r8]
0x180035f27  test    rbp, rbp
0x180035f2a  jz      short loc_180035F45
0x180035f2c  call    cs:__imp_GetLastError
0x180035f32  mov     rcx, rbp; hMem
0x180035f35  mov     ebx, eax
0x180035f37  call    cs:__imp_LocalFree
0x180035f3d  mov     ecx, ebx; dwErrCode
0x180035f3f  call    cs:__imp_SetLastError
0x180035f45  mov     [r14], r15
0x180035f48  mov     qword ptr [rdi], 0
0x180035f4f  mov     rcx, [rsi+10h]; pwk
0x180035f53  call    cs:__imp_SubmitThreadpoolWork
0x180035f59  mov     qword ptr [rsi+18h], 0
0x180035f61  mov     qword ptr [rsi+10h], 0
0x180035f69  mov     rcx, [rdi]; hMem
0x180035f6c  test    rcx, rcx
0x180035f6f  jz      short loc_180035F77
0x180035f71  call    cs:__imp_LocalFree
0x180035f77  xor     al, al
0x180035f79  jmp     short loc_180035FAA
0x180035f7b  mov     rax, [r8]
0x180035f7e  xor     r9d, r9d
0x180035f81  mov     rcx, [rcx]; SRWLock
0x180035f84  mov     qword ptr [r8], 0
0x180035f8b  lea     r8, [rsp+58h+var_38]
0x180035f90  mov     [rsp+58h+var_38], rax
0x180035f95  call    ?Complete@ClientOperation@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z; ClientOperation::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)
0x180035f9a  mov     rcx, [rdi]; hMem
0x180035f9d  test    rcx, rcx
0x180035fa0  jz      short loc_180035FA8
0x180035fa2  call    cs:__imp_LocalFree
0x180035fa8  mov     al, 1
0x180035faa  mov     rbx, [rsp+58h+arg_18]
0x180035faf  add     rsp, 30h
0x180035fb3  pop     r15
0x180035fb5  pop     r14
0x180035fb7  pop     rdi
0x180035fb8  pop     rsi
0x180035fb9  pop     rbp
0x180035fba  retn
```
