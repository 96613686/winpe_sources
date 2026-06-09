# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18003abac`
- end: `0x18003acb9`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026970`
- `0x18002ef18`

## callees

- `0x180028658`
- `0x18003abac`
- `0x18003acc0`
- `0x18003bc70`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ac1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ac1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac8e`

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
0x18003abac  mov     [rsp+arg_10], rbx
0x18003abb1  push    rbp
0x18003abb2  push    rsi
0x18003abb3  push    rdi
0x18003abb4  sub     rsp, 70h
0x18003abb8  mov     rax, cs:__security_cookie
0x18003abbf  xor     rax, rsp
0x18003abc2  mov     [rsp+88h+var_28], rax
0x18003abc7  mov     edi, edx
0x18003abc9  mov     rbx, rcx
0x18003abcc  xorps   xmm0, xmm0
0x18003abcf  movups  [rsp+88h+var_58], xmm0
0x18003abd4  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18003abd9  movups  [rsp+88h+var_38], xmm0
0x18003abde  cmp     dword ptr [rcx+0E8h], 0
0x18003abe5  jbe     short loc_18003ABEA
0x18003abe7  or      edi, 8
0x18003abea  mov     esi, [rcx+0B8h]
0x18003abf0  mov     rbp, [rcx+0F0h]
0x18003abf7  mov     qword ptr [rcx+0F0h], 0
0x18003ac02  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18003ac09  test    rax, rax
0x18003ac0c  jnz     short loc_18003AC49
0x18003ac0e  call    tip_details_GetKernelBaseModuleHandle
0x18003ac13  mov     rcx, rax; hModule
0x18003ac16  lea     rdx, aTestquerydata; "TestQueryData"
0x18003ac1d  call    cs:__imp_GetProcAddress
0x18003ac24  nop     dword ptr [rax+rax+00h]
0x18003ac29  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x18003ac30  test    rax, rax
0x18003ac33  jnz     short loc_18003AC49
0x18003ac35  xorps   xmm0, xmm0
0x18003ac38  movups  [rsp+88h+var_58], xmm0
0x18003ac3d  movups  xmmword ptr [rsp+88h+pv], xmm0
0x18003ac42  movups  [rsp+88h+var_38], xmm0
0x18003ac47  jmp     short loc_18003AC89
0x18003ac49  lea     r9, [rsp+88h+var_58]
0x18003ac4e  mov     r8d, esi
0x18003ac51  mov     edx, edi
0x18003ac53  mov     rcx, rbp
0x18003ac56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac5b  test    eax, eax
0x18003ac5d  jz      short loc_18003AC89
0x18003ac5f  mov     rdx, [rsp+88h+pv]
0x18003ac64  mov     rax, rdx
0x18003ac67  shr     rax, 20h
0x18003ac6b  or      [rbx+40h], eax
0x18003ac6e  cmp     [rsp+88h+pv+8], 0
0x18003ac74  jnz     short loc_18003AC7C
0x18003ac76  mov     [rbx+0B8h], edx
0x18003ac7c  mov     rdx, qword ptr [rsp+88h+var_38]
0x18003ac81  mov     rcx, rbx
0x18003ac84  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x18003ac89  mov     rcx, [rsp+88h+pv+8]; pv
0x18003ac8e  call    cs:__imp_CoTaskMemFree
0x18003ac95  nop     dword ptr [rax+rax+00h]
0x18003ac9a  nop
0x18003ac9b  mov     rcx, [rsp+88h+var_28]
0x18003aca0  xor     rcx, rsp; StackCookie
0x18003aca3  call    __security_check_cookie
0x18003aca8  mov     rbx, [rsp+88h+arg_10]
0x18003acb0  add     rsp, 70h
0x18003acb4  pop     rdi
0x18003acb5  pop     rsi
0x18003acb6  pop     rbp
0x18003acb7  retn
```
