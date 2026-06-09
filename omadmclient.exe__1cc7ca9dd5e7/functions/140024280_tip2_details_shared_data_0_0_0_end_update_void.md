# tip2::details::shared_data<0,0,0>::end_update(void)

- ea: `0x140024280`
- end: `0x14002443b`
- name: `?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ`
- size: `443`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140020870`
- `0x1400223f0`
- `0x14003b9f0`
- `0x140046f98`
- `0x140048db0`

## callees

- `0x140003450`
- `0x140024280`
- `0x140025a50`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002437e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14002437e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024361`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140024361`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140024412`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140024412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400243e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400243f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400243e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400243f9`

## string_xrefs

- `0x14002435a`: `kernelbase.dll`

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
0x140024280  push    rbp
0x140024282  push    rbx
0x140024283  push    rsi
0x140024284  push    rdi
0x140024285  lea     rbp, [rsp-7A8h]
0x14002428d  sub     rsp, 8A8h
0x140024294  mov     rax, cs:__security_cookie
0x14002429b  xor     rax, rsp
0x14002429e  mov     [rbp+7C0h+var_30], rax
0x1400242a5  mov     rbx, rcx
0x1400242a8  bts     dword ptr [rcx+40h], 0Bh
0x1400242ad  cmp     qword ptr [rcx+0F0h], 0
0x1400242b5  jz      loc_140024405
0x1400242bb  test    dword ptr [rcx+40h], 100h
0x1400242c2  jnz     loc_140024405
0x1400242c8  test    dword ptr [rcx+14h], 8000h
0x1400242cf  jnz     loc_140024405
0x1400242d5  xorps   xmm0, xmm0
0x1400242d8  movups  [rsp+8C0h+var_890], xmm0
0x1400242dd  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x1400242e2  movups  [rsp+8C0h+var_870], xmm0
0x1400242e7  mov     [rsp+8C0h+pv], 0
0x1400242f0  mov     [rsp+8C0h+var_858], 0
0x1400242f5  lea     rax, [rsp+8C0h+var_857]
0x1400242fa  mov     [rbp+7C0h+var_50], rax
0x140024301  lea     rax, [rbp+7C0h+var_57]
0x140024308  mov     [rbp+7C0h+var_40], rax
0x14002430f  mov     [rsp+8C0h+var_857], 80408040h
0x140024317  mov     [rsp+8C0h+var_853], 0
0x14002431c  lea     rax, [rsp+8C0h+var_852]
0x140024321  mov     [rbp+7C0h+var_48], rax
0x140024328  mov     r8d, 1
0x14002432e  lea     rdx, [rsp+8C0h+pv]
0x140024333  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x140024338  mov     rdi, rax
0x14002433b  mov     rsi, [rbx+0F0h]
0x140024342  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x140024349  test    rax, rax
0x14002434c  jnz     short loc_1400243AA
0x14002434e  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x140024355  test    rax, rax
0x140024358  jnz     short loc_140024374
0x14002435a  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x140024361  call    cs:__imp_GetModuleHandleW
0x140024368  nop     dword ptr [rax+rax+00h]
0x14002436d  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x140024374  lea     rdx, aTestunlockdata; "TestUnlockData"
0x14002437b  mov     rcx, rax; hModule
0x14002437e  call    cs:__imp_GetProcAddress
0x140024385  nop     dword ptr [rax+rax+00h]
0x14002438a  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x140024391  test    rax, rax
0x140024394  jnz     short loc_1400243AA
0x140024396  xorps   xmm0, xmm0
0x140024399  movups  [rsp+8C0h+var_890], xmm0
0x14002439e  movups  xmmword ptr [rsp+8C0h+var_880], xmm0
0x1400243a3  movups  [rsp+8C0h+var_870], xmm0
0x1400243a8  jmp     short loc_1400243BC
0x1400243aa  lea     r9, [rsp+8C0h+var_890]
0x1400243af  mov     r8, rdi
0x1400243b2  xor     edx, edx
0x1400243b4  mov     rcx, rsi
0x1400243b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400243bc  mov     rdx, [rsp+8C0h+var_880]
0x1400243c1  mov     rax, rdx
0x1400243c4  shr     rax, 20h
0x1400243c8  or      [rbx+40h], eax
0x1400243cb  mov     rcx, [rsp+8C0h+var_880+8]
0x1400243d0  test    rcx, rcx
0x1400243d3  jnz     short loc_1400243DB
0x1400243d5  mov     [rbx+0B8h], edx
0x1400243db  mov     rax, [rsp+8C0h+pv]
0x1400243e0  test    rax, rax
0x1400243e3  jz      short loc_1400243F9
0x1400243e5  mov     rcx, rax; pv
0x1400243e8  call    cs:__imp_CoTaskMemFree
0x1400243ef  nop     dword ptr [rax+rax+00h]
0x1400243f4  mov     rcx, [rsp+8C0h+var_880+8]; pv
0x1400243f9  call    cs:__imp_CoTaskMemFree
0x140024400  nop     dword ptr [rax+rax+00h]
0x140024405  dec     dword ptr [rbx+0E8h]
0x14002440b  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x140024412  call    cs:__imp_LeaveCriticalSection
0x140024419  nop     dword ptr [rax+rax+00h]
0x14002441e  nop
0x14002441f  mov     rcx, [rbp+7C0h+var_30]
0x140024426  xor     rcx, rsp; StackCookie
0x140024429  call    __security_check_cookie
0x14002442e  add     rsp, 8A8h
0x140024435  pop     rdi
0x140024436  pop     rsi
0x140024437  pop     rbx
0x140024438  pop     rbp
0x140024439  retn
```
