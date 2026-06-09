# tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)

- ea: `0x1800b1418`
- end: `0x1800b1533`
- name: `?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ae9ec`
- `0x1800af2a8`

## callees

- `0x180008dc0`
- `0x1800b1418`
- `0x1800b166c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b14a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b14a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b148d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b148d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b150f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b150f`

## string_xrefs

- `0x1800b1486`: `kernelbase.dll`

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
0x1800b1418  mov     [rsp+arg_10], rbx
0x1800b141d  push    rbp
0x1800b141e  push    rsi
0x1800b141f  push    rdi
0x1800b1420  sub     rsp, 70h
0x1800b1424  mov     rax, cs:__security_cookie
0x1800b142b  xor     rax, rsp
0x1800b142e  mov     [rsp+88h+var_28], rax
0x1800b1433  mov     edi, edx
0x1800b1435  mov     rbx, rcx
0x1800b1438  xorps   xmm0, xmm0
0x1800b143b  movups  [rsp+88h+var_58], xmm0
0x1800b1440  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800b1445  movups  [rsp+88h+var_38], xmm0
0x1800b144a  cmp     dword ptr [rcx+0E8h], 0
0x1800b1451  jbe     short loc_1800B1456
0x1800b1453  or      edi, 8
0x1800b1456  mov     esi, [rcx+0B8h]
0x1800b145c  mov     rbp, [rcx+0F0h]
0x1800b1463  mov     qword ptr [rcx+0F0h], 0
0x1800b146e  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800b1475  test    rax, rax
0x1800b1478  jnz     short loc_1800B14CA
0x1800b147a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800b1481  test    rax, rax
0x1800b1484  jnz     short loc_1800B149A
0x1800b1486  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800b148d  call    cs:__imp_GetModuleHandleW
0x1800b1493  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800b149a  lea     rdx, aTestquerydata; "TestQueryData"
0x1800b14a1  mov     rcx, rax; hModule
0x1800b14a4  call    cs:__imp_GetProcAddress
0x1800b14aa  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x1800b14b1  test    rax, rax
0x1800b14b4  jnz     short loc_1800B14CA
0x1800b14b6  xorps   xmm0, xmm0
0x1800b14b9  movups  [rsp+88h+var_58], xmm0
0x1800b14be  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800b14c3  movups  [rsp+88h+var_38], xmm0
0x1800b14c8  jmp     short loc_1800B150A
0x1800b14ca  lea     r9, [rsp+88h+var_58]
0x1800b14cf  mov     r8d, esi
0x1800b14d2  mov     edx, edi
0x1800b14d4  mov     rcx, rbp
0x1800b14d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b14dc  test    eax, eax
0x1800b14de  jz      short loc_1800B150A
0x1800b14e0  mov     rdx, [rsp+88h+pv]
0x1800b14e5  mov     rax, rdx
0x1800b14e8  shr     rax, 20h
0x1800b14ec  or      [rbx+40h], eax
0x1800b14ef  cmp     [rsp+88h+pv+8], 0
0x1800b14f5  jnz     short loc_1800B14FD
0x1800b14f7  mov     [rbx+0B8h], edx
0x1800b14fd  mov     rdx, qword ptr [rsp+88h+var_38]
0x1800b1502  mov     rcx, rbx
0x1800b1505  call    ?evaluate_and_report@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<0,0,1>::evaluate_and_report(__int64)
0x1800b150a  mov     rcx, [rsp+88h+pv+8]; pv
0x1800b150f  call    cs:__imp_CoTaskMemFree
0x1800b1515  nop
0x1800b1516  mov     rcx, [rsp+88h+var_28]
0x1800b151b  xor     rcx, rsp; StackCookie
0x1800b151e  call    __security_check_cookie
0x1800b1523  mov     rbx, [rsp+88h+arg_10]
0x1800b152b  add     rsp, 70h
0x1800b152f  pop     rdi
0x1800b1530  pop     rsi
0x1800b1531  pop     rbp
0x1800b1532  retn
```
