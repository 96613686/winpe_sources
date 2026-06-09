# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180057f54`
- end: `0x180058054`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054ed8`
- `0x180057f28`

## callees

- `0x18002e1a0`
- `0x180057f54`
- `0x180058394`
- `0x180059a34`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057fc5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180057fc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058030`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058030`

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
0x180057f54  mov     [rsp+arg_10], rbx
0x180057f59  push    rbp
0x180057f5a  push    rsi
0x180057f5b  push    rdi
0x180057f5c  sub     rsp, 70h
0x180057f60  mov     rax, cs:__security_cookie
0x180057f67  xor     rax, rsp
0x180057f6a  mov     [rsp+88h+var_28], rax
0x180057f6f  mov     edi, edx
0x180057f71  mov     rbx, rcx
0x180057f74  xorps   xmm0, xmm0
0x180057f77  movups  [rsp+88h+var_58], xmm0
0x180057f7c  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180057f81  movups  [rsp+88h+var_38], xmm0
0x180057f86  cmp     dword ptr [rcx+0E8h], 0
0x180057f8d  jbe     short loc_180057F92
0x180057f8f  or      edi, 8
0x180057f92  mov     esi, [rcx+0B8h]
0x180057f98  mov     rbp, [rcx+0F0h]
0x180057f9f  mov     qword ptr [rcx+0F0h], 0
0x180057faa  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180057fb1  test    rax, rax
0x180057fb4  jnz     short loc_180057FEB
0x180057fb6  call    tip_details_GetKernelBaseModuleHandle
0x180057fbb  mov     rcx, rax; hModule
0x180057fbe  lea     rdx, aTestquerydata; "TestQueryData"
0x180057fc5  call    cs:__imp_GetProcAddress
0x180057fcb  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180057fd2  test    rax, rax
0x180057fd5  jnz     short loc_180057FEB
0x180057fd7  xorps   xmm0, xmm0
0x180057fda  movups  [rsp+88h+var_58], xmm0
0x180057fdf  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180057fe4  movups  [rsp+88h+var_38], xmm0
0x180057fe9  jmp     short loc_18005802B
0x180057feb  lea     r9, [rsp+88h+var_58]
0x180057ff0  mov     r8d, esi
0x180057ff3  mov     edx, edi
0x180057ff5  mov     rcx, rbp
0x180057ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057ffd  test    eax, eax
0x180057fff  jz      short loc_18005802B
0x180058001  mov     rdx, [rsp+88h+pv]
0x180058006  mov     rax, rdx
0x180058009  shr     rax, 20h
0x18005800d  or      [rbx+40h], eax
0x180058010  cmp     [rsp+88h+pv+8], 0
0x180058016  jnz     short loc_18005801E
0x180058018  mov     [rbx+0B8h], edx
0x18005801e  mov     rdx, qword ptr [rsp+88h+var_38]
0x180058023  mov     rcx, rbx
0x180058026  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18005802b  mov     rcx, [rsp+88h+pv+8]; pv
0x180058030  call    cs:__imp_CoTaskMemFree
0x180058036  nop
0x180058037  mov     rcx, [rsp+88h+var_28]
0x18005803c  xor     rcx, rsp; StackCookie
0x18005803f  call    __security_check_cookie
0x180058044  mov     rbx, [rsp+88h+arg_10]
0x18005804c  add     rsp, 70h
0x180058050  pop     rdi
0x180058051  pop     rsi
0x180058052  pop     rbp
0x180058053  retn
```
