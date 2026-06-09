# tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180039428`
- end: `0x180039556`
- name: `?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180034b80`
- `0x18003894c`

## callees

- `0x1800026d0`
- `0x180039428`
- `0x18003991c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003949d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003949d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800394ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800394ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003952b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003952b`

## string_xrefs

- `0x180039496`: `kernelbase.dll`

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
0x180039428  mov     [rsp+arg_10], rbx
0x18003942d  push    rbp
0x18003942e  push    rsi
0x18003942f  push    rdi
0x180039430  sub     rsp, 70h
0x180039434  mov     rax, cs:__security_cookie
0x18003943b  xor     rax, rsp
0x18003943e  mov     [rsp+88h+var_28], rax
0x180039443  mov     edi, edx
0x180039445  mov     rbx, rcx
0x180039448  xorps   xmm0, xmm0
0x18003944b  movups  [rsp+88h+var_58], xmm0
0x180039450  movups  xmmword ptr [rsp+88h+pv], xmm0
0x180039455  movups  [rsp+88h+var_38], xmm0
0x18003945a  cmp     dword ptr [rcx+0E8h], 0
0x180039461  jbe     short loc_180039466
0x180039463  or      edi, 8
0x180039466  mov     esi, [rcx+0B8h]
0x18003946c  mov     rbp, [rcx+0F0h]
0x180039473  mov     qword ptr [rcx+0F0h], 0
0x18003947e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180039485  test    rax, rax
0x180039488  jnz     short loc_1800394E6
0x18003948a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180039491  test    rax, rax
0x180039494  jnz     short loc_1800394B0
0x180039496  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18003949d  call    cs:__imp_GetModuleHandleW
0x1800394a4  nop     dword ptr [rax+rax+00h]
0x1800394a9  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800394b0  lea     rdx, aTestquerydata; "TestQueryData"
0x1800394b7  mov     rcx, rax; hModule
0x1800394ba  call    cs:__imp_GetProcAddress
0x1800394c1  nop     dword ptr [rax+rax+00h]
0x1800394c6  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800394cd  test    rax, rax
0x1800394d0  jnz     short loc_1800394E6
0x1800394d2  xorps   xmm0, xmm0
0x1800394d5  movups  [rsp+88h+var_58], xmm0
0x1800394da  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800394df  movups  [rsp+88h+var_38], xmm0
0x1800394e4  jmp     short loc_180039526
0x1800394e6  lea     r9, [rsp+88h+var_58]
0x1800394eb  mov     r8d, esi
0x1800394ee  mov     edx, edi
0x1800394f0  mov     rcx, rbp
0x1800394f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800394f8  test    eax, eax
0x1800394fa  jz      short loc_180039526
0x1800394fc  mov     rdx, [rsp+88h+pv]
0x180039501  mov     rax, rdx
0x180039504  shr     rax, 20h
0x180039508  or      [rbx+40h], eax
0x18003950b  cmp     [rsp+88h+pv+8], 0
0x180039511  jnz     short loc_180039519
0x180039513  mov     [rbx+0B8h], edx
0x180039519  mov     rdx, qword ptr [rsp+88h+var_38]
0x18003951e  mov     rcx, rbx
0x180039521  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,0>::evaluate_and_report(__int64)
0x180039526  mov     rcx, [rsp+88h+pv+8]; pv
0x18003952b  call    cs:__imp_CoTaskMemFree
0x180039532  nop     dword ptr [rax+rax+00h]
0x180039537  nop
0x180039538  mov     rcx, [rsp+88h+var_28]
0x18003953d  xor     rcx, rsp; StackCookie
0x180039540  call    __security_check_cookie
0x180039545  mov     rbx, [rsp+88h+arg_10]
0x18003954d  add     rsp, 70h
0x180039551  pop     rdi
0x180039552  pop     rsi
0x180039553  pop     rbp
0x180039554  retn
```
