# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x1800396c0`
- end: `0x1800397c0`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024058`
- `0x18002fc50`

## callees

- `0x180025bbc`
- `0x1800396c0`
- `0x1800397c8`
- `0x18003a730`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039731`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180039731`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003979c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003979c`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE KernelBaseModuleHandle; // rax
  int v8; // edx
  __int128 v9; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-48h]
  __int128 v11; // [rsp+50h] [rbp-38h]

  v2 = a2;
  v9 = 0;
  *(_OWORD *)pv = 0;
  v11 = 0;
  if ( *(_DWORD *)(a1 + 232) )
    v2 = a2 | 8;
  v4 = *(_DWORD *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
  if ( `TestQueryData'::`2'::s_pfnTestQueryData
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        ProcAddress = GetProcAddress(KernelBaseModuleHandle, "TestQueryData"),
        (`TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress) != 0) )
  {
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD, _QWORD, __int128 *))ProcAddress)(v5, v2, v4, &v9) )
    {
      v8 = (int)pv[0];
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( !pv[1] )
        *(_DWORD *)(a1 + 184) = v8;
      tip2::details::shared_data<0,0,0>::evaluate_and_report(a1, v11);
    }
  }
  else
  {
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x1800396c0  mov     [rsp+arg_10], rbx
0x1800396c5  push    rbp
0x1800396c6  push    rsi
0x1800396c7  push    rdi
0x1800396c8  sub     rsp, 70h
0x1800396cc  mov     rax, cs:__security_cookie
0x1800396d3  xor     rax, rsp
0x1800396d6  mov     [rsp+88h+var_28], rax
0x1800396db  mov     edi, edx
0x1800396dd  mov     rbx, rcx
0x1800396e0  xorps   xmm0, xmm0
0x1800396e3  movups  [rsp+88h+var_58], xmm0
0x1800396e8  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800396ed  movups  [rsp+88h+var_38], xmm0
0x1800396f2  cmp     dword ptr [rcx+0E8h], 0
0x1800396f9  jbe     short loc_1800396FE
0x1800396fb  or      edi, 8
0x1800396fe  mov     esi, [rcx+0B8h]
0x180039704  mov     rbp, [rcx+0F0h]
0x18003970b  mov     qword ptr [rcx+0F0h], 0
0x180039716  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18003971d  test    rax, rax
0x180039720  jnz     short loc_180039757
0x180039722  call    tip_details_GetKernelBaseModuleHandle
0x180039727  mov     rcx, rax; hModule
0x18003972a  lea     rdx, aTestquerydata; "TestQueryData"
0x180039731  call    cs:__imp_GetProcAddress
0x180039737  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18003973e  test    rax, rax
0x180039741  jnz     short loc_180039757
0x180039743  xorps   xmm0, xmm0
0x180039746  movups  [rsp+88h+var_58], xmm0
0x18003974b  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180039750  movups  [rsp+88h+var_38], xmm0
0x180039755  jmp     short loc_180039797
0x180039757  lea     r9, [rsp+88h+var_58]
0x18003975c  mov     r8d, esi
0x18003975f  mov     edx, edi
0x180039761  mov     rcx, rbp
0x180039764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039769  test    eax, eax
0x18003976b  jz      short loc_180039797
0x18003976d  mov     rdx, [rsp+88h+pv]
0x180039772  mov     rax, rdx
0x180039775  shr     rax, 20h
0x180039779  or      [rbx+40h], eax
0x18003977c  cmp     [rsp+88h+pv+8], 0
0x180039782  jnz     short loc_18003978A
0x180039784  mov     [rbx+0B8h], edx
0x18003978a  mov     rdx, qword ptr [rsp+88h+var_38]
0x18003978f  mov     rcx, rbx
0x180039792  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180039797  mov     rcx, [rsp+88h+pv+8]; pv
0x18003979c  call    cs:__imp_CoTaskMemFree
0x1800397a2  nop
0x1800397a3  mov     rcx, [rsp+88h+var_28]
0x1800397a8  xor     rcx, rsp; StackCookie
0x1800397ab  call    __security_check_cookie
0x1800397b0  mov     rbx, [rsp+88h+arg_10]
0x1800397b8  add     rsp, 70h
0x1800397bc  pop     rdi
0x1800397bd  pop     rsi
0x1800397be  pop     rbp
0x1800397bf  retn
```
