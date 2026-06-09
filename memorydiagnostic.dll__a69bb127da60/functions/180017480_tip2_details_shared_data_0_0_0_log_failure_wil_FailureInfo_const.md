# tip2::details::shared_data<0,0,0>::log_failure(wil::FailureInfo const &)

- ea: `0x180017480`
- end: `0x18001768a`
- name: `?log_failure@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXAEBUFailureInfo@wil@@@Z`
- size: `522`
- prototype: `void __fastcall(__int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000e4f0`

## callees

- `0x180002e50`
- `0x1800086c4`
- `0x180010f70`
- `0x180017480`
- `0x180017690`
- `0x180018844`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800175c7`
- `KERNEL32!GetModuleHandleW` at `0x1800175c7`
- `KERNEL32!GetProcAddress` at `0x1800175de`
- `KERNEL32!GetProcAddress` at `0x1800175de`
- `KERNEL32!LeaveCriticalSection` at `0x18001765c`
- `KERNEL32!LeaveCriticalSection` at `0x18001765c`
- `KERNEL32!EnterCriticalSection` at `0x1800174be`
- `KERNEL32!EnterCriticalSection` at `0x1800174be`
- `ole32!CoTaskMemFree` at `0x180017642`
- `ole32!CoTaskMemFree` at `0x18001764d`
- `ole32!CoTaskMemFree` at `0x180017642`
- `ole32!CoTaskMemFree` at `0x18001764d`

## string_xrefs

- `0x1800175c0`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::log_failure(__int64 a1, const struct wil::FailureInfo *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // r9
  char v6; // bl
  __int64 v7; // rbx
  __int64 v8; // r14
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v11; // edx
  void *v12; // rcx
  __int128 v13; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v14[2]; // [rsp+40h] [rbp-C0h]
  __int128 v15; // [rsp+50h] [rbp-B0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  char v17; // [rsp+68h] [rbp-98h]
  int v18; // [rsp+69h] [rbp-97h] BYREF
  char v19; // [rsp+6Dh] [rbp-93h]
  char v20; // [rsp+6Eh] [rbp-92h] BYREF
  __int128 v21; // [rsp+F8h] [rbp-8h]
  char v22; // [rsp+869h] [rbp+769h] BYREF
  int *v23; // [rsp+870h] [rbp+770h]
  char *v24; // [rsp+878h] [rbp+778h]
  char *v25; // [rsp+880h] [rbp+780h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v21 = 0;
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)&pv, a2);
    v6 = tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(a1 + 72, &pv);
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)&pv);
    if ( !v6 )
      *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  *(_DWORD *)(a1 + 64) |= 0x800u;
  if ( *(_QWORD *)(a1 + 240) && (*(_DWORD *)(a1 + 64) & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v13 = 0;
    *(_OWORD *)v14 = 0;
    v15 = 0;
    pv = 0;
    v17 = 0;
    v23 = &v18;
    v25 = &v22;
    v18 = -2143256512;
    v19 = 0;
    v24 = &v20;
    v7 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1, v5);
    v8 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_12;
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
LABEL_12:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v8, 0, v7, &v13);
    }
    else
    {
      v13 = 0;
      *(_OWORD *)v14 = 0;
      v15 = 0;
    }
    v11 = (int)v14[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v14[0]);
    v12 = v14[1];
    if ( !v14[1] )
      *(_DWORD *)(a1 + 184) = v11;
    if ( pv )
    {
      CoTaskMemFree(pv);
      v12 = v14[1];
    }
    CoTaskMemFree(v12);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180017480  mov     [rsp-8+arg_10], rbx
0x180017485  mov     [rsp-8+arg_18], rsi
0x18001748a  push    rbp
0x18001748b  push    rdi
0x18001748c  push    r14
0x18001748e  lea     rbp, [rsp-7A0h]
0x180017496  sub     rsp, 8A0h
0x18001749d  mov     rax, cs:__security_cookie
0x1800174a4  xor     rax, rsp
0x1800174a7  mov     [rbp+7B0h+var_20], rax
0x1800174ae  mov     rbx, rdx
0x1800174b1  mov     rdi, rcx
0x1800174b4  lea     rsi, [rcx+0C0h]
0x1800174bb  mov     rcx, rsi; lpCriticalSection
0x1800174be  call    cs:__imp_EnterCriticalSection
0x1800174c4  inc     dword ptr [rdi+0E8h]
0x1800174ca  mov     r14d, 100h
0x1800174d0  test    [rdi+40h], r14d
0x1800174d4  jnz     short loc_18001750E
0x1800174d6  xorps   xmm0, xmm0
0x1800174d9  movdqu  [rbp+7B0h+var_7B8], xmm0
0x1800174de  mov     rdx, rbx; struct wil::FailureInfo *
0x1800174e1  lea     rcx, [rsp+8B0h+pv]; this
0x1800174e6  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x1800174eb  lea     rcx, [rdi+48h]
0x1800174ef  lea     rdx, [rsp+8B0h+pv]
0x1800174f4  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x1800174f9  mov     bl, al
0x1800174fb  lea     rcx, [rsp+8B0h+pv]; this
0x180017500  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180017505  test    bl, bl
0x180017507  jnz     short loc_18001750E
0x180017509  bts     dword ptr [rdi+40h], 14h
0x18001750e  bts     dword ptr [rdi+40h], 0Bh
0x180017513  cmp     qword ptr [rdi+0F0h], 0
0x18001751b  jz      loc_180017653
0x180017521  test    [rdi+40h], r14d
0x180017525  jnz     loc_180017653
0x18001752b  test    dword ptr [rdi+14h], 8000h
0x180017532  jnz     loc_180017653
0x180017538  xorps   xmm0, xmm0
0x18001753b  movups  [rsp+8B0h+var_880], xmm0
0x180017540  movups  xmmword ptr [rsp+8B0h+var_870], xmm0
0x180017545  movups  [rsp+8B0h+var_860], xmm0
0x18001754a  mov     [rsp+8B0h+pv], 0
0x180017553  mov     [rsp+8B0h+var_848], 0
0x180017558  lea     rax, [rsp+8B0h+var_847]
0x18001755d  mov     [rbp+7B0h+var_40], rax
0x180017564  lea     rax, [rbp+7B0h+var_47]
0x18001756b  mov     [rbp+7B0h+var_30], rax
0x180017572  mov     [rsp+8B0h+var_847], 80408040h
0x18001757a  mov     [rsp+8B0h+var_843], 0
0x18001757f  lea     rax, [rsp+8B0h+var_842]
0x180017584  mov     [rbp+7B0h+var_38], rax
0x18001758b  mov     r8d, 1
0x180017591  lea     rdx, [rsp+8B0h+pv]
0x180017596  mov     rcx, rdi
0x180017599  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18001759e  mov     rbx, rax
0x1800175a1  mov     r14, [rdi+0F0h]
0x1800175a8  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800175af  test    rax, rax
0x1800175b2  jnz     short loc_180017604
0x1800175b4  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800175bb  test    rax, rax
0x1800175be  jnz     short loc_1800175D4
0x1800175c0  lea     rcx, ModuleName; "kernelbase.dll"
0x1800175c7  call    cs:__imp_GetModuleHandleW
0x1800175cd  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800175d4  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800175db  mov     rcx, rax; hModule
0x1800175de  call    cs:__imp_GetProcAddress
0x1800175e4  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800175eb  test    rax, rax
0x1800175ee  jnz     short loc_180017604
0x1800175f0  xorps   xmm0, xmm0
0x1800175f3  movups  [rsp+8B0h+var_880], xmm0
0x1800175f8  movups  xmmword ptr [rsp+8B0h+var_870], xmm0
0x1800175fd  movups  [rsp+8B0h+var_860], xmm0
0x180017602  jmp     short loc_180017616
0x180017604  lea     r9, [rsp+8B0h+var_880]
0x180017609  mov     r8, rbx
0x18001760c  xor     edx, edx
0x18001760e  mov     rcx, r14
0x180017611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017616  mov     rdx, [rsp+8B0h+var_870]
0x18001761b  mov     rax, rdx
0x18001761e  shr     rax, 20h
0x180017622  or      [rdi+40h], eax
0x180017625  mov     rcx, [rsp+8B0h+var_870+8]
0x18001762a  test    rcx, rcx
0x18001762d  jnz     short loc_180017635
0x18001762f  mov     [rdi+0B8h], edx
0x180017635  mov     rax, [rsp+8B0h+pv]
0x18001763a  test    rax, rax
0x18001763d  jz      short loc_18001764D
0x18001763f  mov     rcx, rax; pv
0x180017642  call    cs:__imp_CoTaskMemFree
0x180017648  mov     rcx, [rsp+8B0h+var_870+8]; pv
0x18001764d  call    cs:__imp_CoTaskMemFree
0x180017653  dec     dword ptr [rdi+0E8h]
0x180017659  mov     rcx, rsi; lpCriticalSection
0x18001765c  call    cs:__imp_LeaveCriticalSection
0x180017662  nop
0x180017663  mov     rcx, [rbp+7B0h+var_20]
0x18001766a  xor     rcx, rsp; StackCookie
0x18001766d  call    __security_check_cookie
0x180017672  lea     r11, [rsp+8B0h+var_10]
0x18001767a  mov     rbx, [r11+30h]
0x18001767e  mov     rsi, [r11+38h]
0x180017682  mov     rsp, r11
0x180017685  pop     r14
0x180017687  pop     rdi
0x180017688  pop     rbp
0x180017689  retn
```
