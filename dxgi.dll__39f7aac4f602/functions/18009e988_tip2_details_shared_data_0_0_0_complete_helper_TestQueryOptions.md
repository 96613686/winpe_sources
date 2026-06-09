# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18009e988`
- end: `0x18009ea88`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009b970`
- `0x18009bc04`

## callees

- `0x180075fa0`
- `0x18007f2ec`
- `0x18009e988`
- `0x18009ee14`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009e9f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009e9f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ea64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ea64`

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
0x18009e988  mov     [rsp+arg_10], rbx
0x18009e98d  push    rbp
0x18009e98e  push    rsi
0x18009e98f  push    rdi
0x18009e990  sub     rsp, 70h
0x18009e994  mov     rax, cs:__security_cookie
0x18009e99b  xor     rax, rsp
0x18009e99e  mov     [rsp+88h+var_28], rax
0x18009e9a3  mov     edi, edx
0x18009e9a5  mov     rbx, rcx
0x18009e9a8  xorps   xmm0, xmm0
0x18009e9ab  movups  [rsp+88h+var_58], xmm0
0x18009e9b0  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18009e9b5  movups  [rsp+88h+var_38], xmm0
0x18009e9ba  cmp     dword ptr [rcx+0E8h], 0
0x18009e9c1  jbe     short loc_18009E9C6
0x18009e9c3  or      edi, 8
0x18009e9c6  mov     esi, [rcx+0B8h]
0x18009e9cc  mov     rbp, [rcx+0F0h]
0x18009e9d3  mov     qword ptr [rcx+0F0h], 0
0x18009e9de  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18009e9e5  test    rax, rax
0x18009e9e8  jnz     short loc_18009EA1F
0x18009e9ea  call    tip_details_GetKernelBaseModuleHandle
0x18009e9ef  mov     rcx, rax; hModule
0x18009e9f2  lea     rdx, aTestquerydata; "TestQueryData"
0x18009e9f9  call    cs:__imp_GetProcAddress
0x18009e9ff  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18009ea06  test    rax, rax
0x18009ea09  jnz     short loc_18009EA1F
0x18009ea0b  xorps   xmm0, xmm0
0x18009ea0e  movups  [rsp+88h+var_58], xmm0
0x18009ea13  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18009ea18  movups  [rsp+88h+var_38], xmm0
0x18009ea1d  jmp     short loc_18009EA5F
0x18009ea1f  lea     r9, [rsp+88h+var_58]
0x18009ea24  mov     r8d, esi
0x18009ea27  mov     edx, edi
0x18009ea29  mov     rcx, rbp
0x18009ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ea31  test    eax, eax
0x18009ea33  jz      short loc_18009EA5F
0x18009ea35  mov     rdx, [rsp+88h+pv]
0x18009ea3a  mov     rax, rdx
0x18009ea3d  shr     rax, 20h
0x18009ea41  or      [rbx+40h], eax
0x18009ea44  cmp     [rsp+88h+pv+8], 0
0x18009ea4a  jnz     short loc_18009EA52
0x18009ea4c  mov     [rbx+0B8h], edx
0x18009ea52  mov     rdx, qword ptr [rsp+88h+var_38]
0x18009ea57  mov     rcx, rbx
0x18009ea5a  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18009ea5f  mov     rcx, [rsp+88h+pv+8]; pv
0x18009ea64  call    cs:__imp_CoTaskMemFree
0x18009ea6a  nop
0x18009ea6b  mov     rcx, [rsp+88h+var_28]
0x18009ea70  xor     rcx, rsp; StackCookie
0x18009ea73  call    __security_check_cookie
0x18009ea78  mov     rbx, [rsp+88h+arg_10]
0x18009ea80  add     rsp, 70h
0x18009ea84  pop     rdi
0x18009ea85  pop     rsi
0x18009ea86  pop     rbp
0x18009ea87  retn
```
