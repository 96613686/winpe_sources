# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x180039610`
- end: `0x1800397cb`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800312e0`
- `0x180034b80`

## callees

- `0x1800026d0`
- `0x180039610`
- `0x18003ab98`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800396f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800396f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003970e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003970e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039789`

## string_xrefs

- `0x1800396ea`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v6; // edx
  void *v7; // rcx
  __int128 v8; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v9[2]; // [rsp+40h] [rbp-C0h]
  __int128 v10; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  char v12; // [rsp+68h] [rbp-98h]
  int v13; // [rsp+69h] [rbp-97h] BYREF
  char v14; // [rsp+6Dh] [rbp-93h]
  char v15; // [rsp+6Eh] [rbp-92h] BYREF
  char v16; // [rsp+869h] [rbp+769h] BYREF
  int *v17; // [rsp+870h] [rbp+770h]
  char *v18; // [rsp+878h] [rbp+778h]
  char *v19; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v8 = 0;
    *(_OWORD *)v9 = 0;
    v10 = 0;
    pv = 0;
    v12 = 0;
    v17 = &v13;
    v19 = &v16;
    v13 = -2143256512;
    v14 = 0;
    v18 = &v15;
    v2 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_9;
    ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "TestUnlockData");
    `TestUnlockData'::`2'::s_pfnTestUnlockData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_9:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v8);
    }
    else
    {
      v8 = 0;
      *(_OWORD *)v9 = 0;
      v10 = 0;
    }
    v6 = (int)v9[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v9[0]);
    v7 = v9[1];
    if ( !v9[1] )
      *(_DWORD *)(a1 + 184) = v6;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v7 = v9[1];
    }
    CoTaskMemFree(v7);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180039610  push    rbp
0x180039612  push    rbx
0x180039613  push    rsi
0x180039614  push    rdi
0x180039615  lea     rbp, [rsp-7A8h]
0x18003961d  sub     rsp, 8A8h
0x180039624  mov     rax, cs:__security_cookie
0x18003962b  xor     rax, rsp
0x18003962e  mov     [rbp+7C0h+var_30], rax
0x180039635  mov     rbx, rcx
0x180039638  bts     dword ptr [rcx+40h], 0Bh
0x18003963d  cmp     qword ptr [rcx+0F0h], 0
0x180039645  jz      loc_180039795
0x18003964b  test    dword ptr [rcx+40h], 100h
0x180039652  jnz     loc_180039795
0x180039658  test    dword ptr [rcx+14h], 8000h
0x18003965f  jnz     loc_180039795
0x180039665  xorps   xmm0, xmm0
0x180039668  movups  [rsp+8C0h+var_890], xmm0
0x18003966d  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180039672  movups  [rsp+8C0h+var_870], xmm0
0x180039677  mov     [rsp+8C0h+pv], 0
0x180039680  mov     [rsp+8C0h+var_858], 0
0x180039685  lea     rax, [rsp+8C0h+var_857]
0x18003968a  mov     [rbp+7C0h+var_50], rax
0x180039691  lea     rax, [rbp+7C0h+var_57]
0x180039698  mov     [rbp+7C0h+var_40], rax
0x18003969f  mov     [rsp+8C0h+var_857], 80408040h
0x1800396a7  mov     [rsp+8C0h+var_853], 0
0x1800396ac  lea     rax, [rsp+8C0h+var_852]
0x1800396b1  mov     [rbp+7C0h+var_48], rax
0x1800396b8  mov     r8d, 1
0x1800396be  lea     rdx, [rsp+8C0h+pv]
0x1800396c3  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800396c8  mov     rdi, rax
0x1800396cb  mov     rsi, [rbx+0F0h]
0x1800396d2  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800396d9  test    rax, rax
0x1800396dc  jnz     short loc_18003973A
0x1800396de  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800396e5  test    rax, rax
0x1800396e8  jnz     short loc_180039704
0x1800396ea  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800396f1  call    cs:__imp_GetModuleHandleW
0x1800396f8  nop     dword ptr [rax+rax+00h]
0x1800396fd  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180039704  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18003970b  mov     rcx, rax; hModule
0x18003970e  call    cs:__imp_GetProcAddress
0x180039715  nop     dword ptr [rax+rax+00h]
0x18003971a  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180039721  test    rax, rax
0x180039724  jnz     short loc_18003973A
0x180039726  xorps   xmm0, xmm0
0x180039729  movups  [rsp+8C0h+var_890], xmm0
0x18003972e  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x180039733  movups  [rsp+8C0h+var_870], xmm0
0x180039738  jmp     short loc_18003974C
0x18003973a  lea     r9, [rsp+8C0h+var_890]
0x18003973f  mov     r8, rdi
0x180039742  xor     edx, edx
0x180039744  mov     rcx, rsi
0x180039747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003974c  mov     rdx, [rsp+8C0h+var_880]
0x180039751  mov     rax, rdx
0x180039754  shr     rax, 20h
0x180039758  or      [rbx+40h], eax
0x18003975b  mov     rcx, [rsp+8C0h+var_880+8]
0x180039760  test    rcx, rcx
0x180039763  jnz     short loc_18003976B
0x180039765  mov     [rbx+0B8h], edx
0x18003976b  mov     rax, [rsp+8C0h+pv]
0x180039770  test    rax, rax
0x180039773  jz      short loc_180039789
0x180039775  mov     rcx, rax; pv
0x180039778  call    cs:__imp_CoTaskMemFree
0x18003977f  nop     dword ptr [rax+rax+00h]
0x180039784  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x180039789  call    cs:__imp_CoTaskMemFree
0x180039790  nop     dword ptr [rax+rax+00h]
0x180039795  dec     dword ptr [rbx+0E8h]
0x18003979b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x1800397a2  call    cs:__imp_LeaveCriticalSection
0x1800397a9  nop     dword ptr [rax+rax+00h]
0x1800397ae  nop
0x1800397af  mov     rcx, [rbp+7C0h+var_30]
0x1800397b6  xor     rcx, rsp; StackCookie
0x1800397b9  call    __security_check_cookie
0x1800397be  add     rsp, 8A8h
0x1800397c5  pop     rdi
0x1800397c6  pop     rsi
0x1800397c7  pop     rbx
0x1800397c8  pop     rbp
0x1800397c9  retn
```
