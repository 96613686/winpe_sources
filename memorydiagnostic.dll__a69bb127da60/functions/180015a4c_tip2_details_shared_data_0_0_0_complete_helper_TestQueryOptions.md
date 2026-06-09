# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180015a4c`
- end: `0x180015b67`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800079bc`
- `0x180007c18`
- `0x180008bf0`

## callees

- `0x180002e50`
- `0x180015a4c`
- `0x18001625c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180015ac1`
- `KERNEL32!GetModuleHandleW` at `0x180015ac1`
- `KERNEL32!GetProcAddress` at `0x180015ad8`
- `KERNEL32!GetProcAddress` at `0x180015ad8`
- `ole32!CoTaskMemFree` at `0x180015b43`
- `ole32!CoTaskMemFree` at `0x180015b43`

## string_xrefs

- `0x180015aba`: `kernelbase.dll`

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
0x180015a4c  mov     [rsp+arg_10], rbx
0x180015a51  push    rbp
0x180015a52  push    rsi
0x180015a53  push    rdi
0x180015a54  sub     rsp, 70h
0x180015a58  mov     rax, cs:__security_cookie
0x180015a5f  xor     rax, rsp
0x180015a62  mov     [rsp+88h+var_28], rax
0x180015a67  mov     edi, edx
0x180015a69  mov     rbx, rcx
0x180015a6c  xorps   xmm0, xmm0
0x180015a6f  movups  [rsp+88h+var_58], xmm0
0x180015a74  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180015a79  movups  [rsp+88h+var_38], xmm0
0x180015a7e  cmp     dword ptr [rcx+0E8h], 0
0x180015a85  jbe     short loc_180015A8A
0x180015a87  or      edi, 8
0x180015a8a  mov     esi, [rcx+0B8h]
0x180015a90  mov     rbp, [rcx+0F0h]
0x180015a97  mov     qword ptr [rcx+0F0h], 0
0x180015aa2  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180015aa9  test    rax, rax
0x180015aac  jnz     short loc_180015AFE
0x180015aae  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180015ab5  test    rax, rax
0x180015ab8  jnz     short loc_180015ACE
0x180015aba  lea     rcx, ModuleName; "kernelbase.dll"
0x180015ac1  call    cs:__imp_GetModuleHandleW
0x180015ac7  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180015ace  lea     rdx, aTestquerydata; "TestQueryData"
0x180015ad5  mov     rcx, rax; hModule
0x180015ad8  call    cs:__imp_GetProcAddress
0x180015ade  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180015ae5  test    rax, rax
0x180015ae8  jnz     short loc_180015AFE
0x180015aea  xorps   xmm0, xmm0
0x180015aed  movups  [rsp+88h+var_58], xmm0
0x180015af2  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180015af7  movups  [rsp+88h+var_38], xmm0
0x180015afc  jmp     short loc_180015B3E
0x180015afe  lea     r9, [rsp+88h+var_58]
0x180015b03  mov     r8d, esi
0x180015b06  mov     edx, edi
0x180015b08  mov     rcx, rbp
0x180015b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b10  test    eax, eax
0x180015b12  jz      short loc_180015B3E
0x180015b14  mov     rdx, [rsp+88h+pv]
0x180015b19  mov     rax, rdx
0x180015b1c  shr     rax, 20h
0x180015b20  or      [rbx+40h], eax
0x180015b23  cmp     [rsp+88h+pv+8], 0
0x180015b29  jnz     short loc_180015B31
0x180015b2b  mov     [rbx+0B8h], edx
0x180015b31  mov     rdx, qword ptr [rsp+88h+var_38]
0x180015b36  mov     rcx, rbx
0x180015b39  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180015b3e  mov     rcx, [rsp+88h+pv+8]; pv
0x180015b43  call    cs:__imp_CoTaskMemFree
0x180015b49  nop
0x180015b4a  mov     rcx, [rsp+88h+var_28]
0x180015b4f  xor     rcx, rsp; StackCookie
0x180015b52  call    __security_check_cookie
0x180015b57  mov     rbx, [rsp+88h+arg_10]
0x180015b5f  add     rsp, 70h
0x180015b63  pop     rdi
0x180015b64  pop     rsi
0x180015b65  pop     rbp
0x180015b66  retn
```
