# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18000c568`
- end: `0x18000c683`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b6b0`
- `0x18000c200`

## callees

- `0x180001cf0`
- `0x18000c568`
- `0x18000c990`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c5f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c5f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c5dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c5dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c65f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c65f`

## string_xrefs

- `0x18000c5d6`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::complete_helper(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  unsigned int v4; // esi
  __int64 v5; // rbp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
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
  if ( `TestQueryData'::`2'::s_pfnTestQueryData )
    goto LABEL_15;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
  `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_15:
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
0x18000c568  mov     [rsp+arg_10], rbx
0x18000c56d  push    rbp
0x18000c56e  push    rsi
0x18000c56f  push    rdi
0x18000c570  sub     rsp, 70h
0x18000c574  mov     rax, cs:__security_cookie
0x18000c57b  xor     rax, rsp
0x18000c57e  mov     [rsp+88h+var_28], rax
0x18000c583  mov     edi, edx
0x18000c585  mov     rbx, rcx
0x18000c588  xorps   xmm0, xmm0
0x18000c58b  movups  [rsp+88h+var_58], xmm0
0x18000c590  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000c595  movups  [rsp+88h+var_38], xmm0
0x18000c59a  cmp     dword ptr [rcx+0E8h], 0
0x18000c5a1  jbe     short loc_18000C5A6
0x18000c5a3  or      edi, 8
0x18000c5a6  mov     esi, [rcx+0B8h]
0x18000c5ac  mov     rbp, [rcx+0F0h]
0x18000c5b3  mov     qword ptr [rcx+0F0h], 0
0x18000c5be  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000c5c5  test    rax, rax
0x18000c5c8  jnz     short loc_18000C61A
0x18000c5ca  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000c5d1  test    rax, rax
0x18000c5d4  jnz     short loc_18000C5EA
0x18000c5d6  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c5dd  call    cs:__imp_GetModuleHandleW
0x18000c5e3  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000c5ea  lea     rdx, aTestquerydata; "TestQueryData"
0x18000c5f1  mov     rcx, rax; hModule
0x18000c5f4  call    cs:__imp_GetProcAddress
0x18000c5fa  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18000c601  test    rax, rax
0x18000c604  jnz     short loc_18000C61A
0x18000c606  xorps   xmm0, xmm0
0x18000c609  movups  [rsp+88h+var_58], xmm0
0x18000c60e  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18000c613  movups  [rsp+88h+var_38], xmm0
0x18000c618  jmp     short loc_18000C65A
0x18000c61a  lea     r9, [rsp+88h+var_58]
0x18000c61f  mov     r8d, esi
0x18000c622  mov     edx, edi
0x18000c624  mov     rcx, rbp
0x18000c627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c62c  test    eax, eax
0x18000c62e  jz      short loc_18000C65A
0x18000c630  mov     rdx, [rsp+88h+pv]
0x18000c635  mov     rax, rdx
0x18000c638  shr     rax, 20h
0x18000c63c  or      [rbx+40h], eax
0x18000c63f  cmp     [rsp+88h+pv+8], 0
0x18000c645  jnz     short loc_18000C64D
0x18000c647  mov     [rbx+0B8h], edx
0x18000c64d  mov     rdx, qword ptr [rsp+88h+var_38]
0x18000c652  mov     rcx, rbx
0x18000c655  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18000c65a  mov     rcx, [rsp+88h+pv+8]; pv
0x18000c65f  call    cs:__imp_CoTaskMemFree
0x18000c665  nop
0x18000c666  mov     rcx, [rsp+88h+var_28]
0x18000c66b  xor     rcx, rsp; StackCookie
0x18000c66e  call    __security_check_cookie
0x18000c673  mov     rbx, [rsp+88h+arg_10]
0x18000c67b  add     rsp, 70h
0x18000c67f  pop     rdi
0x18000c680  pop     rsi
0x18000c681  pop     rbp
0x18000c682  retn
```
