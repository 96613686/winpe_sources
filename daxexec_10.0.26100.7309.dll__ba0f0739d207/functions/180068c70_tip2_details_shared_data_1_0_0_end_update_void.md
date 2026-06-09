# tip2::details::shared_data<1,0,0>::end_update(void)

- ea: `0x180068c70`
- end: `0x180068e38`
- name: `?end_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180066fe0`
- `0x180067e48`

## callees

- `0x1800053a0`
- `0x180068840`
- `0x180068c70`
- `0x18006b194`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068d6a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180068d4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180068d4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068e02`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068dde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068dde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068def`

## string_xrefs

- `0x180068d46`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::end_update(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  __int64 v4; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // ecx
  __int128 v8; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+48h] [rbp-C0h]
  __int128 v10; // [rsp+58h] [rbp-B0h]
  LPVOID pv; // [rsp+68h] [rbp-A0h] BYREF
  char v12; // [rsp+70h] [rbp-98h]
  int v13; // [rsp+71h] [rbp-97h] BYREF
  char v14; // [rsp+75h] [rbp-93h]
  char v15; // [rsp+76h] [rbp-92h] BYREF
  char v16; // [rsp+871h] [rbp+769h] BYREF
  int *v17; // [rsp+878h] [rbp+770h]
  char *v18; // [rsp+880h] [rbp+778h]
  char *v19; // [rsp+888h] [rbp+780h]

  v2 = *(_DWORD *)(a1 + 64) | 0x800;
  *(_DWORD *)(a1 + 64) = v2;
  if ( *(_QWORD *)(a1 + 232) && (v2 & 0x100) == 0 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    pv = 0;
    v12 = 0;
    v17 = &v13;
    v19 = &v16;
    v13 = -2143256512;
    v14 = 0;
    v18 = &v15;
    v3 = tip2::details::shared_data<1,0,0>::serialize_data(a1, &pv, 1);
    v4 = *(_QWORD *)(a1 + 232);
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
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v4, 0, v3, &v8);
    }
    else
    {
      v8 = 0;
      v9 = 0;
      v10 = 0;
    }
    v7 = v9;
    *(_DWORD *)(a1 + 64) |= DWORD1(v9);
    if ( *((_QWORD *)&v9 + 1) )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v8);
    else
      *(_DWORD *)(a1 + 184) = v7;
    if ( pv )
      CoTaskMemFree(pv);
    CoTaskMemFree(*((LPVOID *)&v9 + 1));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
}

```

## disassembly

```asm
0x180068c70  mov     rax, rsp
0x180068c73  mov     [rax+10h], rbx
0x180068c77  mov     [rax+18h], rsi
0x180068c7b  mov     [rax+20h], rdi
0x180068c7f  push    rbp
0x180068c80  lea     rbp, [rax-7A8h]
0x180068c87  sub     rsp, 8A0h
0x180068c8e  mov     rax, cs:__security_cookie
0x180068c95  xor     rax, rsp
0x180068c98  mov     [rbp+7A0h+var_10], rax
0x180068c9f  mov     rbx, rcx
0x180068ca2  mov     eax, [rcx+40h]
0x180068ca5  bts     eax, 0Bh
0x180068ca9  mov     [rcx+40h], eax
0x180068cac  cmp     qword ptr [rcx+0E8h], 0
0x180068cb4  jz      loc_180068DFB
0x180068cba  bt      eax, 8
0x180068cbe  jb      loc_180068DFB
0x180068cc4  xorps   xmm0, xmm0
0x180068cc7  movups  [rsp+8A0h+var_878+8], xmm0
0x180068ccc  movups  [rsp+8A0h+var_868+8], xmm0
0x180068cd1  movups  xmmword ptr [rsp+8A0h+var_858+8], xmm0
0x180068cd6  and     [rsp+8A0h+pv], 0
0x180068cdc  mov     [rsp+8A0h+var_838], 0
0x180068ce1  lea     rax, [rsp+8A0h+var_837]
0x180068ce6  mov     [rbp+7A0h+var_30], rax
0x180068ced  lea     rax, [rbp+7A0h+var_37]
0x180068cf4  mov     [rbp+7A0h+var_20], rax
0x180068cfb  mov     [rsp+8A0h+var_837], 80408040h
0x180068d03  mov     [rsp+8A0h+var_833], 0
0x180068d08  lea     rax, [rsp+8A0h+var_832]
0x180068d0d  mov     [rbp+7A0h+var_28], rax
0x180068d14  mov     r8d, 1
0x180068d1a  lea     rdx, [rsp+8A0h+pv]
0x180068d1f  call    ?serialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<1,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x180068d24  mov     rdi, rax
0x180068d27  mov     rsi, [rbx+0E8h]
0x180068d2e  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180068d35  test    rax, rax
0x180068d38  jnz     short loc_180068D96
0x180068d3a  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x180068d41  test    rax, rax
0x180068d44  jnz     short loc_180068D60
0x180068d46  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x180068d4d  call    cs:__imp_GetModuleHandleW
0x180068d54  nop     dword ptr [rax+rax+00h]
0x180068d59  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x180068d60  lea     rdx, aTestunlockdata; "TestUnlockData"
0x180068d67  mov     rcx, rax; hModule
0x180068d6a  call    cs:__imp_GetProcAddress
0x180068d71  nop     dword ptr [rax+rax+00h]
0x180068d76  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x180068d7d  test    rax, rax
0x180068d80  jnz     short loc_180068D96
0x180068d82  xorps   xmm0, xmm0
0x180068d85  movups  [rsp+8A0h+var_878+8], xmm0
0x180068d8a  movups  [rsp+8A0h+var_868+8], xmm0
0x180068d8f  movups  xmmword ptr [rsp+8A0h+var_858+8], xmm0
0x180068d94  jmp     short loc_180068DA8
0x180068d96  lea     r9, [rsp+8A0h+var_878+8]
0x180068d9b  mov     r8, rdi
0x180068d9e  xor     edx, edx
0x180068da0  mov     rcx, rsi
0x180068da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068da8  mov     rcx, qword ptr [rsp+8A0h+var_868+8]
0x180068dad  mov     rax, rcx
0x180068db0  shr     rax, 20h
0x180068db4  or      [rbx+40h], eax
0x180068db7  cmp     qword ptr [rsp+8A0h+var_858], 0
0x180068dbd  jz      short loc_180068DCE
0x180068dbf  lea     rdx, [rsp+8A0h+var_878+8]
0x180068dc4  mov     rcx, rbx
0x180068dc7  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180068dcc  jmp     short loc_180068DD4
0x180068dce  mov     [rbx+0B8h], ecx
0x180068dd4  mov     rcx, [rsp+8A0h+pv]; pv
0x180068dd9  test    rcx, rcx
0x180068ddc  jz      short loc_180068DEA
0x180068dde  call    cs:__imp_CoTaskMemFree
0x180068de5  nop     dword ptr [rax+rax+00h]
0x180068dea  mov     rcx, qword ptr [rsp+8A0h+var_858]; pv
0x180068def  call    cs:__imp_CoTaskMemFree
0x180068df6  nop     dword ptr [rax+rax+00h]
0x180068dfb  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x180068e02  call    cs:__imp_LeaveCriticalSection
0x180068e09  nop     dword ptr [rax+rax+00h]
0x180068e0e  nop
0x180068e0f  mov     rcx, [rbp+7A0h+var_10]
0x180068e16  xor     rcx, rsp; StackCookie
0x180068e19  call    __security_check_cookie
0x180068e1e  lea     r11, [rsp+8A0h+var_s0]
0x180068e26  mov     rbx, [r11+18h]
0x180068e2a  mov     rsi, [r11+20h]
0x180068e2e  mov     rdi, [r11+28h]
0x180068e32  mov     rsp, r11
0x180068e35  pop     rbp
0x180068e36  retn
```
