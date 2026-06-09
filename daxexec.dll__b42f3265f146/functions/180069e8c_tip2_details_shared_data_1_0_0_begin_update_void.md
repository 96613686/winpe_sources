# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x180069e8c`
- end: `0x180069fe0`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `340`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180068a10`
- `0x18006980c`

## callees

- `0x180004f70`
- `0x180069e8c`
- `0x18006a300`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069f20`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180069f20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069f3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180069f3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069eb0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180069eb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069fd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069f82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069fd0`

## string_xrefs

- `0x180069f19`: `kernelbase.dll`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::begin_update(__int64 a1)
{
  __int64 v2; // rdi
  unsigned int v3; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  void *v7; // rcx
  __int128 v8; // [rsp+30h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-38h]
  __int128 v10; // [rsp+50h] [rbp-28h]

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
    return 0;
  v2 = *(_QWORD *)(a1 + 240);
  if ( v2 && *(_DWORD *)(a1 + 232) == 1 )
  {
    v8 = 0;
    *(_OWORD *)pv = 0;
    v10 = 0;
    v3 = *(_DWORD *)(a1 + 184);
    ProcAddress = (FARPROC)`TestQueryData'::`2'::s_pfnTestQueryData;
    if ( !`TestQueryData'::`2'::s_pfnTestQueryData )
    {
      ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
      if ( !g_tip_details_kernelbaseModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
        g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "TestQueryData");
      `TestQueryData'::`2'::s_pfnTestQueryData = (__int64)ProcAddress;
      if ( !ProcAddress )
      {
        v8 = 0;
        *(_OWORD *)pv = 0;
        v10 = 0;
LABEL_10:
        CoTaskMemFree(pv[1]);
        return 0;
      }
    }
    if ( !((unsigned int (__fastcall *)(__int64, __int64, _QWORD, __int128 *))ProcAddress)(v2, 1, v3, &v8) )
      goto LABEL_10;
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    v7 = pv[1];
    if ( pv[1] )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v8);
      v7 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x180069e8c  push    rbp
0x180069e8e  push    rbx
0x180069e8f  push    rsi
0x180069e90  push    rdi
0x180069e91  mov     rbp, rsp
0x180069e94  sub     rsp, 78h
0x180069e98  mov     rax, cs:__security_cookie
0x180069e9f  xor     rax, rsp
0x180069ea2  mov     [rbp+var_18], rax
0x180069ea6  mov     rbx, rcx
0x180069ea9  add     rcx, 0C0h; lpCriticalSection
0x180069eb0  call    cs:__imp_EnterCriticalSection
0x180069eb7  nop     dword ptr [rax+rax+00h]
0x180069ebc  inc     dword ptr [rbx+0E8h]
0x180069ec2  test    dword ptr [rbx+40h], 100h
0x180069ec9  jnz     loc_180069F8E
0x180069ecf  mov     rdi, [rbx+0F0h]
0x180069ed6  test    rdi, rdi
0x180069ed9  jz      loc_180069FDC
0x180069edf  cmp     dword ptr [rbx+0E8h], 1
0x180069ee6  jnz     loc_180069FDC
0x180069eec  xorps   xmm0, xmm0
0x180069eef  movups  [rbp+var_48], xmm0
0x180069ef3  movups  xmmword ptr [rbp+pv], xmm0
0x180069ef7  movups  [rbp+var_28], xmm0
0x180069efb  mov     esi, [rbx+0B8h]
0x180069f01  mov     rax, cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180069f08  test    rax, rax
0x180069f0b  jnz     short loc_180069F66
0x180069f0d  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180069f14  test    rax, rax
0x180069f17  jnz     short loc_180069F33
0x180069f19  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180069f20  call    cs:__imp_GetModuleHandleW
0x180069f27  nop     dword ptr [rax+rax+00h]
0x180069f2c  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180069f33  lea     rdx, aTestquerydata; "TestQueryData"
0x180069f3a  mov     rcx, rax; hModule
0x180069f3d  call    cs:__imp_GetProcAddress
0x180069f44  nop     dword ptr [rax+rax+00h]
0x180069f49  mov     cs:?s_pfnTestQueryData@?1??TestQueryData@@9@4P6AHPEAUHTIPTEST__@@W4TestQueryOptions@@IPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; int (*`TestQueryData'::`2'::s_pfnTestQueryData)(HTIPTEST__ *,TestQueryOptions,uint,TestInfo_ODR_guard::TestInfo *)
0x180069f50  test    rax, rax
0x180069f53  jnz     short loc_180069F66
0x180069f55  xorps   xmm0, xmm0
0x180069f58  movups  [rbp+var_48], xmm0
0x180069f5c  movups  xmmword ptr [rbp+pv], xmm0
0x180069f60  movups  [rbp+var_28], xmm0
0x180069f64  jmp     short loc_180069F7E
0x180069f66  lea     r9, [rbp+var_48]
0x180069f6a  mov     r8d, esi
0x180069f6d  mov     edx, 1
0x180069f72  mov     rcx, rdi
0x180069f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069f7a  test    eax, eax
0x180069f7c  jnz     short loc_180069FA6
0x180069f7e  mov     rcx, [rbp+pv+8]; pv
0x180069f82  call    cs:__imp_CoTaskMemFree
0x180069f89  nop     dword ptr [rax+rax+00h]
0x180069f8e  xor     al, al
0x180069f90  mov     rcx, [rbp+var_18]
0x180069f94  xor     rcx, rsp; StackCookie
0x180069f97  call    __security_check_cookie
0x180069f9c  add     rsp, 78h
0x180069fa0  pop     rdi
0x180069fa1  pop     rsi
0x180069fa2  pop     rbx
0x180069fa3  pop     rbp
0x180069fa4  retn
0x180069fa6  mov     eax, dword ptr [rbp+pv+4]
0x180069fa9  or      [rbx+40h], eax
0x180069fac  mov     rcx, [rbp+pv+8]; pv
0x180069fb0  test    rcx, rcx
0x180069fb3  jz      short loc_180069FC7
0x180069fb5  lea     rdx, [rbp+var_48]
0x180069fb9  mov     rcx, rbx
0x180069fbc  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180069fc1  mov     rcx, [rbp+pv+8]
0x180069fc5  jmp     short loc_180069FD0
0x180069fc7  mov     edx, dword ptr [rbp+pv]
0x180069fca  mov     [rbx+0B8h], edx
0x180069fd0  call    cs:__imp_CoTaskMemFree
0x180069fd7  nop     dword ptr [rax+rax+00h]
0x180069fdc  mov     al, 1
0x180069fde  jmp     short loc_180069F90
```
