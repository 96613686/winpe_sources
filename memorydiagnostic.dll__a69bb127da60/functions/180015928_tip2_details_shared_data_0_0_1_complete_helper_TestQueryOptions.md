# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x180015928`
- end: `0x180015a43`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `void __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180007ca4`
- `0x1800158a0`

## callees

- `0x180002e50`
- `0x180015928`
- `0x180015f9c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18001599d`
- `KERNEL32!GetModuleHandleW` at `0x18001599d`
- `KERNEL32!GetProcAddress` at `0x1800159b4`
- `KERNEL32!GetProcAddress` at `0x1800159b4`
- `ole32!CoTaskMemFree` at `0x180015a1f`
- `ole32!CoTaskMemFree` at `0x180015a1f`

## string_xrefs

- `0x180015996`: `kernelbase.dll`

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
0x180015928  mov     [rsp+arg_10], rbx
0x18001592d  push    rbp
0x18001592e  push    rsi
0x18001592f  push    rdi
0x180015930  sub     rsp, 70h
0x180015934  mov     rax, cs:__security_cookie
0x18001593b  xor     rax, rsp
0x18001593e  mov     [rsp+88h+var_28], rax
0x180015943  mov     edi, edx
0x180015945  mov     rbx, rcx
0x180015948  xorps   xmm0, xmm0
0x18001594b  movups  [rsp+88h+var_58], xmm0
0x180015950  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180015955  movups  [rsp+88h+var_38], xmm0
0x18001595a  cmp     dword ptr [rcx+0E8h], 0
0x180015961  jbe     short loc_180015966
0x180015963  or      edi, 8
0x180015966  mov     esi, [rcx+0B8h]
0x18001596c  mov     rbp, [rcx+0F0h]
0x180015973  mov     qword ptr [rcx+0F0h], 0
0x18001597e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180015985  test    rax, rax
0x180015988  jnz     short loc_1800159DA
0x18001598a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180015991  test    rax, rax
0x180015994  jnz     short loc_1800159AA
0x180015996  lea     rcx, ModuleName; "kernelbase.dll"
0x18001599d  call    cs:__imp_GetModuleHandleW
0x1800159a3  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800159aa  lea     rdx, aTestquerydata; "TestQueryData"
0x1800159b1  mov     rcx, rax; hModule
0x1800159b4  call    cs:__imp_GetProcAddress
0x1800159ba  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800159c1  test    rax, rax
0x1800159c4  jnz     short loc_1800159DA
0x1800159c6  xorps   xmm0, xmm0
0x1800159c9  movups  [rsp+88h+var_58], xmm0
0x1800159ce  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800159d3  movups  [rsp+88h+var_38], xmm0
0x1800159d8  jmp     short loc_180015A1A
0x1800159da  lea     r9, [rsp+88h+var_58]
0x1800159df  mov     r8d, esi
0x1800159e2  mov     edx, edi
0x1800159e4  mov     rcx, rbp
0x1800159e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159ec  test    eax, eax
0x1800159ee  jz      short loc_180015A1A
0x1800159f0  mov     rdx, [rsp+88h+pv]
0x1800159f5  mov     rax, rdx
0x1800159f8  shr     rax, 20h
0x1800159fc  or      [rbx+40h], eax
0x1800159ff  cmp     [rsp+88h+pv+8], 0
0x180015a05  jnz     short loc_180015A0D
0x180015a07  mov     [rbx+0B8h], edx
0x180015a0d  mov     rdx, qword ptr [rsp+88h+var_38]
0x180015a12  mov     rcx, rbx
0x180015a15  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x180015a1a  mov     rcx, [rsp+88h+pv+8]; pv
0x180015a1f  call    cs:__imp_CoTaskMemFree
0x180015a25  nop
0x180015a26  mov     rcx, [rsp+88h+var_28]
0x180015a2b  xor     rcx, rsp; StackCookie
0x180015a2e  call    __security_check_cookie
0x180015a33  mov     rbx, [rsp+88h+arg_10]
0x180015a3b  add     rsp, 70h
0x180015a3f  pop     rdi
0x180015a40  pop     rsi
0x180015a41  pop     rbp
0x180015a42  retn
```
