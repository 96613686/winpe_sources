# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x18006a728`
- end: `0x18006a8e0`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `440`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180068a10`
- `0x18006980c`

## callees

- `0x180004f70`
- `0x18006a300`
- `0x18006a728`
- `0x18006cacc`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006a7fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006a7fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a819`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a8b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006a8b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a88d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a88d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006a89e`

## string_xrefs

- `0x18006a7f5`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v6; // ecx
  __int128 v7; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v8[2]; // [rsp+40h] [rbp-C0h]
  __int128 v9; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  char v11; // [rsp+68h] [rbp-98h]
  int v12; // [rsp+69h] [rbp-97h] BYREF
  char v13; // [rsp+6Dh] [rbp-93h]
  char v14; // [rsp+6Eh] [rbp-92h] BYREF
  char v15; // [rsp+869h] [rbp+769h] BYREF
  int *v16; // [rsp+870h] [rbp+770h]
  char *v17; // [rsp+878h] [rbp+778h]
  char *v18; // [rsp+880h] [rbp+780h]

  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v7 = 0;
    *(_OWORD *)v8 = 0;
    v9 = 0;
    pv = 0;
    v11 = 0;
    v16 = &v12;
    v18 = &v15;
    v12 = -2143256512;
    v13 = 0;
    v17 = &v14;
    v2 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, 1);
    v3 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_8;
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
LABEL_8:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v3, 0, v2, &v7);
    }
    else
    {
      v7 = 0;
      *(_OWORD *)v8 = 0;
      v9 = 0;
    }
    v6 = (int)v8[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v8[0]);
    if ( v8[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
    else
      *(_DWORD *)(a1 + 184) = v6;
    if ( pv )
      CoTaskMemFree(pv);
    CoTaskMemFree(v8[1]);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x18006a728  push    rbp
0x18006a72a  push    rbx
0x18006a72b  push    rsi
0x18006a72c  push    rdi
0x18006a72d  lea     rbp, [rsp-7A8h]
0x18006a735  sub     rsp, 8A8h
0x18006a73c  mov     rax, cs:__security_cookie
0x18006a743  xor     rax, rsp
0x18006a746  mov     [rbp+7C0h+var_30], rax
0x18006a74d  mov     rbx, rcx
0x18006a750  bts     dword ptr [rcx+40h], 0Bh
0x18006a755  cmp     qword ptr [rcx+0F0h], 0
0x18006a75d  jz      loc_18006A8AA
0x18006a763  test    dword ptr [rcx+40h], 100h
0x18006a76a  jnz     loc_18006A8AA
0x18006a770  xorps   xmm0, xmm0
0x18006a773  movups  [rsp+8C0h+var_890], xmm0
0x18006a778  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18006a77d  movups  [rsp+8C0h+var_870], xmm0
0x18006a782  mov     [rsp+8C0h+pv], 0
0x18006a78b  mov     [rsp+8C0h+var_858], 0
0x18006a790  lea     rax, [rsp+8C0h+var_857]
0x18006a795  mov     [rbp+7C0h+var_50], rax
0x18006a79c  lea     rax, [rbp+7C0h+var_57]
0x18006a7a3  mov     [rbp+7C0h+var_40], rax
0x18006a7aa  mov     [rsp+8C0h+var_857], 80408040h
0x18006a7b2  mov     [rsp+8C0h+var_853], 0
0x18006a7b7  lea     rax, [rsp+8C0h+var_852]
0x18006a7bc  mov     [rbp+7C0h+var_48], rax
0x18006a7c3  mov     r8d, 1
0x18006a7c9  lea     rdx, [rsp+8C0h+pv]
0x18006a7ce  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18006a7d3  mov     rdi, rax
0x18006a7d6  mov     rsi, [rbx+0F0h]
0x18006a7dd  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18006a7e4  test    rax, rax
0x18006a7e7  jnz     short loc_18006A845
0x18006a7e9  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18006a7f0  test    rax, rax
0x18006a7f3  jnz     short loc_18006A80F
0x18006a7f5  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18006a7fc  call    cs:__imp_GetModuleHandleW
0x18006a803  nop     dword ptr [rax+rax+00h]
0x18006a808  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18006a80f  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18006a816  mov     rcx, rax; hModule
0x18006a819  call    cs:__imp_GetProcAddress
0x18006a820  nop     dword ptr [rax+rax+00h]
0x18006a825  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18006a82c  test    rax, rax
0x18006a82f  jnz     short loc_18006A845
0x18006a831  xorps   xmm0, xmm0
0x18006a834  movups  [rsp+8C0h+var_890], xmm0
0x18006a839  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18006a83e  movups  [rsp+8C0h+var_870], xmm0
0x18006a843  jmp     short loc_18006A857
0x18006a845  lea     r9, [rsp+8C0h+var_890]
0x18006a84a  mov     r8, rdi
0x18006a84d  xor     edx, edx
0x18006a84f  mov     rcx, rsi
0x18006a852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a857  mov     rcx, [rsp+8C0h+var_880]
0x18006a85c  mov     rax, rcx
0x18006a85f  shr     rax, 20h
0x18006a863  or      [rbx+40h], eax
0x18006a866  cmp     [rsp+8C0h+var_880+8], 0
0x18006a86c  jz      short loc_18006A87D
0x18006a86e  lea     rdx, [rsp+8C0h+var_890]
0x18006a873  mov     rcx, rbx
0x18006a876  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18006a87b  jmp     short loc_18006A883
0x18006a87d  mov     [rbx+0B8h], ecx
0x18006a883  mov     rcx, [rsp+8C0h+pv]; pv
0x18006a888  test    rcx, rcx
0x18006a88b  jz      short loc_18006A899
0x18006a88d  call    cs:__imp_CoTaskMemFree
0x18006a894  nop     dword ptr [rax+rax+00h]
0x18006a899  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x18006a89e  call    cs:__imp_CoTaskMemFree
0x18006a8a5  nop     dword ptr [rax+rax+00h]
0x18006a8aa  dec     dword ptr [rbx+0E8h]
0x18006a8b0  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18006a8b7  call    cs:__imp_LeaveCriticalSection
0x18006a8be  nop     dword ptr [rax+rax+00h]
0x18006a8c3  nop
0x18006a8c4  mov     rcx, [rbp+7C0h+var_30]
0x18006a8cb  xor     rcx, rsp; StackCookie
0x18006a8ce  call    __security_check_cookie
0x18006a8d3  add     rsp, 8A8h
0x18006a8da  pop     rdi
0x18006a8db  pop     rsi
0x18006a8dc  pop     rbx
0x18006a8dd  pop     rbp
0x18006a8de  retn
```
