# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x18000c6b0`
- end: `0x18000c84c`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `412`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b73c`

## callees

- `0x180001cf0`
- `0x18000c6b0`
- `0x18000dce4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c7a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c791`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c791`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c82a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c82a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c80c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c80c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c817`

## string_xrefs

- `0x18000c78a`: `kernelbase.dll`

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
0x18000c6b0  push    rbp
0x18000c6b2  push    rbx
0x18000c6b3  push    rsi
0x18000c6b4  push    rdi
0x18000c6b5  lea     rbp, [rsp-7A8h]
0x18000c6bd  sub     rsp, 8A8h
0x18000c6c4  mov     rax, cs:__security_cookie
0x18000c6cb  xor     rax, rsp
0x18000c6ce  mov     [rbp+7C0h+var_30], rax
0x18000c6d5  mov     rbx, rcx
0x18000c6d8  bts     dword ptr [rcx+40h], 0Bh
0x18000c6dd  cmp     qword ptr [rcx+0F0h], 0
0x18000c6e5  jz      loc_18000C81D
0x18000c6eb  test    dword ptr [rcx+40h], 100h
0x18000c6f2  jnz     loc_18000C81D
0x18000c6f8  test    dword ptr [rcx+14h], 8000h
0x18000c6ff  jnz     loc_18000C81D
0x18000c705  xorps   xmm0, xmm0
0x18000c708  movups  [rsp+8C0h+var_890], xmm0
0x18000c70d  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18000c712  movups  [rsp+8C0h+var_870], xmm0
0x18000c717  mov     [rsp+8C0h+pv], 0
0x18000c720  mov     [rsp+8C0h+var_858], 0
0x18000c725  lea     rax, [rsp+8C0h+var_857]
0x18000c72a  mov     [rbp+7C0h+var_50], rax
0x18000c731  lea     rax, [rbp+7C0h+var_57]
0x18000c738  mov     [rbp+7C0h+var_40], rax
0x18000c73f  mov     [rsp+8C0h+var_857], 80408040h
0x18000c747  mov     [rsp+8C0h+var_853], 0
0x18000c74c  lea     rax, [rsp+8C0h+var_852]
0x18000c751  mov     [rbp+7C0h+var_48], rax
0x18000c758  mov     r8d, 1
0x18000c75e  lea     rdx, [rsp+8C0h+pv]
0x18000c763  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000c768  mov     rdi, rax
0x18000c76b  mov     rsi, [rbx+0F0h]
0x18000c772  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18000c779  test    rax, rax
0x18000c77c  jnz     short loc_18000C7CE
0x18000c77e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000c785  test    rax, rax
0x18000c788  jnz     short loc_18000C79E
0x18000c78a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000c791  call    cs:__imp_GetModuleHandleW
0x18000c797  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000c79e  lea     rdx, aTestunlockdata; "TestUnlockData"
0x18000c7a5  mov     rcx, rax; hModule
0x18000c7a8  call    cs:__imp_GetProcAddress
0x18000c7ae  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x18000c7b5  test    rax, rax
0x18000c7b8  jnz     short loc_18000C7CE
0x18000c7ba  xorps   xmm0, xmm0
0x18000c7bd  movups  [rsp+8C0h+var_890], xmm0
0x18000c7c2  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x18000c7c7  movups  [rsp+8C0h+var_870], xmm0
0x18000c7cc  jmp     short loc_18000C7E0
0x18000c7ce  lea     r9, [rsp+8C0h+var_890]
0x18000c7d3  mov     r8, rdi
0x18000c7d6  xor     edx, edx
0x18000c7d8  mov     rcx, rsi
0x18000c7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7e0  mov     rdx, [rsp+8C0h+var_880]
0x18000c7e5  mov     rax, rdx
0x18000c7e8  shr     rax, 20h
0x18000c7ec  or      [rbx+40h], eax
0x18000c7ef  mov     rcx, [rsp+8C0h+var_880+8]
0x18000c7f4  test    rcx, rcx
0x18000c7f7  jnz     short loc_18000C7FF
0x18000c7f9  mov     [rbx+0B8h], edx
0x18000c7ff  mov     rax, [rsp+8C0h+pv]
0x18000c804  test    rax, rax
0x18000c807  jz      short loc_18000C817
0x18000c809  mov     rcx, rax; pv
0x18000c80c  call    cs:__imp_CoTaskMemFree
0x18000c812  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x18000c817  call    cs:__imp_CoTaskMemFree
0x18000c81d  dec     dword ptr [rbx+0E8h]
0x18000c823  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000c82a  call    cs:__imp_LeaveCriticalSection
0x18000c830  nop
0x18000c831  mov     rcx, [rbp+7C0h+var_30]
0x18000c838  xor     rcx, rsp; StackCookie
0x18000c83b  call    __security_check_cookie
0x18000c840  add     rsp, 8A8h
0x18000c847  pop     rdi
0x18000c848  pop     rsi
0x18000c849  pop     rbx
0x18000c84a  pop     rbp
0x18000c84b  retn
```
