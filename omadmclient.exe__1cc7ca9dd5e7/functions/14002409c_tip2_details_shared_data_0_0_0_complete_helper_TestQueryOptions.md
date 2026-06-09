# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14002409c`
- end: `0x1400241ca`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `302`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140023bac`
- `0x14003b9f0`
- `0x140048ad0`
- `0x140048db0`

## callees

- `0x140003450`
- `0x14002409c`
- `0x140024850`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002412e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002412e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024111`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024111`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002419f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002419f`

## string_xrefs

- `0x14002410a`: `kernelbase.dll`

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
0x14002409c  mov     [rsp+arg_10], rbx
0x1400240a1  push    rbp
0x1400240a2  push    rsi
0x1400240a3  push    rdi
0x1400240a4  sub     rsp, 70h
0x1400240a8  mov     rax, cs:__security_cookie
0x1400240af  xor     rax, rsp
0x1400240b2  mov     [rsp+88h+var_28], rax
0x1400240b7  mov     edi, edx
0x1400240b9  mov     rbx, rcx
0x1400240bc  xorps   xmm0, xmm0
0x1400240bf  movups  [rsp+88h+var_58], xmm0
0x1400240c4  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1400240c9  movups  [rsp+88h+var_38], xmm0
0x1400240ce  cmp     dword ptr [rcx+0E8h], 0
0x1400240d5  jbe     short loc_1400240DA
0x1400240d7  or      edi, 8
0x1400240da  mov     esi, [rcx+0B8h]
0x1400240e0  mov     rbp, [rcx+0F0h]
0x1400240e7  mov     qword ptr [rcx+0F0h], 0
0x1400240f2  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1400240f9  test    rax, rax
0x1400240fc  jnz     short loc_14002415A
0x1400240fe  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140024105  test    rax, rax
0x140024108  jnz     short loc_140024124
0x14002410a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140024111  call    cs:__imp_GetModuleHandleW
0x140024118  nop     dword ptr [rax+rax+00h]
0x14002411d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140024124  lea     rdx, aTestquerydata; "TestQueryData"
0x14002412b  mov     rcx, rax; hModule
0x14002412e  call    cs:__imp_GetProcAddress
0x140024135  nop     dword ptr [rax+rax+00h]
0x14002413a  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x140024141  test    rax, rax
0x140024144  jnz     short loc_14002415A
0x140024146  xorps   xmm0, xmm0
0x140024149  movups  [rsp+88h+var_58], xmm0
0x14002414e  movups  xmmword ptr [rsp+88h+pv], xmm0
0x140024153  movups  [rsp+88h+var_38], xmm0
0x140024158  jmp     short loc_14002419A
0x14002415a  lea     r9, [rsp+88h+var_58]
0x14002415f  mov     r8d, esi
0x140024162  mov     edx, edi
0x140024164  mov     rcx, rbp
0x140024167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002416c  test    eax, eax
0x14002416e  jz      short loc_14002419A
0x140024170  mov     rdx, [rsp+88h+pv]
0x140024175  mov     rax, rdx
0x140024178  shr     rax, 20h
0x14002417c  or      [rbx+40h], eax
0x14002417f  cmp     [rsp+88h+pv+8], 0
0x140024185  jnz     short loc_14002418D
0x140024187  mov     [rbx+0B8h], edx
0x14002418d  mov     rdx, qword ptr [rsp+88h+var_38]
0x140024192  mov     rcx, rbx
0x140024195  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x14002419a  mov     rcx, [rsp+88h+pv+8]; pv
0x14002419f  call    cs:__imp_CoTaskMemFree
0x1400241a6  nop     dword ptr [rax+rax+00h]
0x1400241ab  nop
0x1400241ac  mov     rcx, [rsp+88h+var_28]
0x1400241b1  xor     rcx, rsp; StackCookie
0x1400241b4  call    __security_check_cookie
0x1400241b9  mov     rbx, [rsp+88h+arg_10]
0x1400241c1  add     rsp, 70h
0x1400241c5  pop     rdi
0x1400241c6  pop     rsi
0x1400241c7  pop     rbp
0x1400241c8  retn
```
