# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180230a24`
- end: `0x180230b24`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801ed220`
- `0x1802304ac`

## callees

- `0x180212490`
- `0x180230a24`
- `0x180230ee4`
- `0x180232804`
- `0x180330010`

## import_xrefs

- `kernel32!GetProcAddress` at `0x180230a95`
- `kernel32!GetProcAddress` at `0x180230a95`
- `combase!CoTaskMemFree` at `0x180230b00`
- `combase!CoTaskMemFree` at `0x180230b00`

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
0x180230a24  mov     [rsp+arg_10], rbx
0x180230a29  push    rbp
0x180230a2a  push    rsi
0x180230a2b  push    rdi
0x180230a2c  sub     rsp, 70h
0x180230a30  mov     rax, cs:__security_cookie
0x180230a37  xor     rax, rsp
0x180230a3a  mov     [rsp+88h+var_28], rax
0x180230a3f  mov     edi, edx
0x180230a41  mov     rbx, rcx
0x180230a44  xorps   xmm0, xmm0
0x180230a47  movups  [rsp+88h+var_58], xmm0
0x180230a4c  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180230a51  movups  [rsp+88h+var_38], xmm0
0x180230a56  cmp     dword ptr [rcx+0E8h], 0
0x180230a5d  jbe     short loc_180230A62
0x180230a5f  or      edi, 8
0x180230a62  mov     esi, [rcx+0B8h]
0x180230a68  mov     rbp, [rcx+0F0h]
0x180230a6f  mov     qword ptr [rcx+0F0h], 0
0x180230a7a  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180230a81  test    rax, rax
0x180230a84  jnz     short loc_180230ABB
0x180230a86  call    tip_details_GetKernelBaseModuleHandle
0x180230a8b  mov     rcx, rax; hModule
0x180230a8e  lea     rdx, aTestquerydata; "TestQueryData"
0x180230a95  call    cs:__imp_GetProcAddress
0x180230a9b  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180230aa2  test    rax, rax
0x180230aa5  jnz     short loc_180230ABB
0x180230aa7  xorps   xmm0, xmm0
0x180230aaa  movups  [rsp+88h+var_58], xmm0
0x180230aaf  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180230ab4  movups  [rsp+88h+var_38], xmm0
0x180230ab9  jmp     short loc_180230AFB
0x180230abb  lea     r9, [rsp+88h+var_58]
0x180230ac0  mov     r8d, esi
0x180230ac3  mov     edx, edi
0x180230ac5  mov     rcx, rbp
0x180230ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180230acd  test    eax, eax
0x180230acf  jz      short loc_180230AFB
0x180230ad1  mov     rdx, [rsp+88h+pv]
0x180230ad6  mov     rax, rdx
0x180230ad9  shr     rax, 20h
0x180230add  or      [rbx+40h], eax
0x180230ae0  cmp     [rsp+88h+pv+8], 0
0x180230ae6  jnz     short loc_180230AEE
0x180230ae8  mov     [rbx+0B8h], edx
0x180230aee  mov     rdx, qword ptr [rsp+88h+var_38]
0x180230af3  mov     rcx, rbx
0x180230af6  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180230afb  mov     rcx, [rsp+88h+pv+8]; pv
0x180230b00  call    cs:__imp_CoTaskMemFree
0x180230b06  nop
0x180230b07  mov     rcx, [rsp+88h+var_28]
0x180230b0c  xor     rcx, rsp; StackCookie
0x180230b0f  call    __security_check_cookie
0x180230b14  mov     rbx, [rsp+88h+arg_10]
0x180230b1c  add     rsp, 70h
0x180230b20  pop     rdi
0x180230b21  pop     rsi
0x180230b22  pop     rbp
0x180230b23  retn
```
