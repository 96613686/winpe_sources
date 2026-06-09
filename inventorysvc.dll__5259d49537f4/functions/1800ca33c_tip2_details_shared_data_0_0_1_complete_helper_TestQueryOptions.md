# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x1800ca33c`
- end: `0x1800ca457`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c7fe0`
- `0x1800c8288`

## callees

- `0x180002bf0`
- `0x1800ca33c`
- `0x1800ca58c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca3c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ca3c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ca3b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ca3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca433`

## string_xrefs

- `0x1800ca3aa`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::complete_helper(__int64 a1, unsigned int a2)
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
      tip2::details::shared_data<0,0,1>::evaluate_and_report(a1, v11);
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
0x1800ca33c  mov     [rsp+arg_10], rbx
0x1800ca341  push    rbp
0x1800ca342  push    rsi
0x1800ca343  push    rdi
0x1800ca344  sub     rsp, 70h
0x1800ca348  mov     rax, cs:__security_cookie
0x1800ca34f  xor     rax, rsp
0x1800ca352  mov     [rsp+88h+var_28], rax
0x1800ca357  mov     edi, edx
0x1800ca359  mov     rbx, rcx
0x1800ca35c  xorps   xmm0, xmm0
0x1800ca35f  movups  [rsp+88h+var_58], xmm0
0x1800ca364  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800ca369  movups  [rsp+88h+var_38], xmm0
0x1800ca36e  cmp     dword ptr [rcx+0E8h], 0
0x1800ca375  jbe     short loc_1800CA37A
0x1800ca377  or      edi, 8
0x1800ca37a  mov     esi, [rcx+0B8h]
0x1800ca380  mov     rbp, [rcx+0F0h]
0x1800ca387  mov     qword ptr [rcx+0F0h], 0
0x1800ca392  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800ca399  test    rax, rax
0x1800ca39c  jnz     short loc_1800CA3EE
0x1800ca39e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800ca3a5  test    rax, rax
0x1800ca3a8  jnz     short loc_1800CA3BE
0x1800ca3aa  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800ca3b1  call    cs:__imp_GetModuleHandleW
0x1800ca3b7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800ca3be  lea     rdx, aTestquerydata; "TestQueryData"
0x1800ca3c5  mov     rcx, rax; hModule
0x1800ca3c8  call    cs:__imp_GetProcAddress
0x1800ca3ce  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800ca3d5  test    rax, rax
0x1800ca3d8  jnz     short loc_1800CA3EE
0x1800ca3da  xorps   xmm0, xmm0
0x1800ca3dd  movups  [rsp+88h+var_58], xmm0
0x1800ca3e2  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800ca3e7  movups  [rsp+88h+var_38], xmm0
0x1800ca3ec  jmp     short loc_1800CA42E
0x1800ca3ee  lea     r9, [rsp+88h+var_58]
0x1800ca3f3  mov     r8d, esi
0x1800ca3f6  mov     edx, edi
0x1800ca3f8  mov     rcx, rbp
0x1800ca3fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca400  test    eax, eax
0x1800ca402  jz      short loc_1800CA42E
0x1800ca404  mov     rdx, [rsp+88h+pv]
0x1800ca409  mov     rax, rdx
0x1800ca40c  shr     rax, 20h
0x1800ca410  or      [rbx+40h], eax
0x1800ca413  cmp     [rsp+88h+pv+8], 0
0x1800ca419  jnz     short loc_1800CA421
0x1800ca41b  mov     [rbx+0B8h], edx
0x1800ca421  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800ca426  mov     rcx, rbx
0x1800ca429  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x1800ca42e  mov     rcx, [rsp+88h+pv+8]; pv
0x1800ca433  call    cs:__imp_CoTaskMemFree
0x1800ca439  nop
0x1800ca43a  mov     rcx, [rsp+88h+var_28]
0x1800ca43f  xor     rcx, rsp; StackCookie
0x1800ca442  call    __security_check_cookie
0x1800ca447  mov     rbx, [rsp+88h+arg_10]
0x1800ca44f  add     rsp, 70h
0x1800ca453  pop     rdi
0x1800ca454  pop     rsi
0x1800ca455  pop     rbp
0x1800ca456  retn
```
