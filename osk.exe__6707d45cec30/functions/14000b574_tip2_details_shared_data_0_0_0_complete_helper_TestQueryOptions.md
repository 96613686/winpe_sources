# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14000b574`
- end: `0x14000b674`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004f5c`
- `0x140007f54`

## callees

- `0x14000b574`
- `0x14000bd74`
- `0x14000e13c`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000b5e5`
- `KERNEL32!GetProcAddress` at `0x14000b5e5`
- `ole32!CoTaskMemFree` at `0x14000b650`
- `ole32!CoTaskMemFree` at `0x14000b650`

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
0x14000b574  mov     [rsp+arg_10], rbx
0x14000b579  push    rbp
0x14000b57a  push    rsi
0x14000b57b  push    rdi
0x14000b57c  sub     rsp, 70h
0x14000b580  mov     rax, cs:__security_cookie
0x14000b587  xor     rax, rsp
0x14000b58a  mov     [rsp+88h+var_28], rax
0x14000b58f  mov     edi, edx
0x14000b591  mov     rbx, rcx
0x14000b594  xorps   xmm0, xmm0
0x14000b597  movups  [rsp+88h+var_58], xmm0
0x14000b59c  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14000b5a1  movups  [rsp+88h+var_38], xmm0
0x14000b5a6  cmp     dword ptr [rcx+0E8h], 0
0x14000b5ad  jbe     short loc_14000B5B2
0x14000b5af  or      edi, 8
0x14000b5b2  mov     esi, [rcx+0B8h]
0x14000b5b8  mov     rbp, [rcx+0F0h]
0x14000b5bf  mov     qword ptr [rcx+0F0h], 0
0x14000b5ca  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14000b5d1  test    rax, rax
0x14000b5d4  jnz     short loc_14000B60B
0x14000b5d6  call    tip_details_GetKernelBaseModuleHandle
0x14000b5db  mov     rcx, rax; hModule
0x14000b5de  lea     rdx, ProcName; "TestQueryData"
0x14000b5e5  call    cs:__imp_GetProcAddress
0x14000b5eb  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x14000b5f2  test    rax, rax
0x14000b5f5  jnz     short loc_14000B60B
0x14000b5f7  xorps   xmm0, xmm0
0x14000b5fa  movups  [rsp+88h+var_58], xmm0
0x14000b5ff  movups  xmmword ptr [rsp+88h+pv], xmm0
0x14000b604  movups  [rsp+88h+var_38], xmm0
0x14000b609  jmp     short loc_14000B64B
0x14000b60b  lea     r9, [rsp+88h+var_58]
0x14000b610  mov     r8d, esi
0x14000b613  mov     edx, edi
0x14000b615  mov     rcx, rbp
0x14000b618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b61d  test    eax, eax
0x14000b61f  jz      short loc_14000B64B
0x14000b621  mov     rdx, [rsp+88h+pv]
0x14000b626  mov     rax, rdx
0x14000b629  shr     rax, 20h
0x14000b62d  or      [rbx+40h], eax
0x14000b630  cmp     [rsp+88h+pv+8], 0
0x14000b636  jnz     short loc_14000B63E
0x14000b638  mov     [rbx+0B8h], edx
0x14000b63e  mov     rdx, qword ptr [rsp+88h+var_38]
0x14000b643  mov     rcx, rbx
0x14000b646  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14000b64b  mov     rcx, [rsp+88h+pv+8]; pv
0x14000b650  call    cs:__imp_CoTaskMemFree
0x14000b656  nop
0x14000b657  mov     rcx, [rsp+88h+var_28]
0x14000b65c  xor     rcx, rsp; StackCookie
0x14000b65f  call    __security_check_cookie
0x14000b664  mov     rbx, [rsp+88h+arg_10]
0x14000b66c  add     rsp, 70h
0x14000b670  pop     rdi
0x14000b671  pop     rsi
0x14000b672  pop     rbp
0x14000b673  retn
```
