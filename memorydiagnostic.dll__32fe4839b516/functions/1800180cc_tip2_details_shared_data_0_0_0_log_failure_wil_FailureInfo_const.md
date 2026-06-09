# tip2::details::shared_data<0,0,0>::log_failure(wil::FailureInfo const &)

- ea: `0x1800180cc`
- end: `0x1800183ac`
- name: `?log_failure@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXAEBUFailureInfo@wil@@@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ed00`

## callees

- `0x1800026b0`
- `0x180008540`
- `0x18001199c`
- `0x1800180cc`
- `0x1800184cc`
- `0x180019820`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800182ca`
- `KERNEL32!GetModuleHandleW` at `0x1800182ca`
- `KERNEL32!GetProcAddress` at `0x1800182e7`
- `KERNEL32!GetProcAddress` at `0x1800182e7`
- `KERNEL32!LeaveCriticalSection` at `0x180018377`
- `KERNEL32!LeaveCriticalSection` at `0x180018377`
- `KERNEL32!EnterCriticalSection` at `0x18001810a`
- `KERNEL32!EnterCriticalSection` at `0x18001810a`
- `ole32!CoTaskMemFree` at `0x180018351`
- `ole32!CoTaskMemFree` at `0x180018362`
- `ole32!CoTaskMemFree` at `0x180018351`
- `ole32!CoTaskMemFree` at `0x180018362`

## string_xrefs

- `0x1800182c3`: `kernelbase.dll`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,0>::log_failure(__int64 a1, const struct wil::FailureInfo *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // r14
  unsigned __int64 v5; // rax
  __int64 v6; // rdx
  char v7; // di
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdi
  __int64 v11; // rsi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v14; // edx
  void *v15; // rcx
  __int128 v16; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v17[2]; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 pv; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h]
  __int128 v22; // [rsp+90h] [rbp-70h]
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int128 v24; // [rsp+B0h] [rbp-50h]
  __int128 v25; // [rsp+C0h] [rbp-40h]
  __int128 v26; // [rsp+D0h] [rbp-30h]
  __int128 v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+F0h] [rbp-10h]
  __int128 v29; // [rsp+F8h] [rbp-8h]
  char v30; // [rsp+869h] [rbp+769h] BYREF
  char *v31; // [rsp+870h] [rbp+770h]
  char *v32; // [rsp+878h] [rbp+778h]
  char *v33; // [rsp+880h] [rbp+780h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    v29 = 0;
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)&pv, a2);
    v5 = *(_QWORD *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 88) < v5 )
      goto LABEL_7;
    v6 = 2 * v5;
    if ( !v5 )
      v6 = 10;
    if ( (unsigned __int8)tip2::vector_nothrow<wil::StoredFailureInfo>::reserve(a1 + 72, v6) )
    {
LABEL_7:
      v8 = *(_QWORD *)(a1 + 72) + 168LL * *(_QWORD *)(a1 + 88);
      *(_OWORD *)v8 = pv;
      *(_OWORD *)(v8 + 16) = v20;
      *(_OWORD *)(v8 + 32) = v21;
      *(_OWORD *)(v8 + 48) = v22;
      *(_OWORD *)(v8 + 64) = v23;
      *(_OWORD *)(v8 + 80) = v24;
      *(_OWORD *)(v8 + 96) = v25;
      *(_OWORD *)(v8 + 112) = v26;
      *(_OWORD *)(v8 + 128) = v27;
      *(_QWORD *)(v8 + 144) = v28;
      *(_OWORD *)(v8 + 152) = v29;
      v29 = 0;
      ++*(_QWORD *)(a1 + 88);
      v7 = 0;
    }
    else
    {
      v7 = 1;
    }
    wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)&pv);
    if ( v7 )
      *(_DWORD *)(a1 + 64) |= 0x100000u;
  }
  v9 = *(_DWORD *)(a1 + 64) | 0x800;
  *(_DWORD *)(a1 + 64) = v9;
  if ( *(_QWORD *)(a1 + 240) && (v9 & 0x100) == 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0 )
  {
    v16 = 0;
    *(_OWORD *)v17 = 0;
    v18 = 0;
    *(_QWORD *)&pv = 0;
    BYTE8(pv) = 0;
    v31 = (char *)&pv + 9;
    v33 = &v30;
    *(_DWORD *)((char *)&pv + 9) = -2143256512;
    BYTE13(pv) = 0;
    v32 = (char *)&pv + 14;
    v10 = tip2::details::shared_data<0,0,0>::serialize_data(a1, &pv, 1);
    v11 = *(_QWORD *)(a1 + 240);
    ProcAddress = (FARPROC)`TestUnlockData'::`2'::s_pfnTestUnlockData;
    if ( `TestUnlockData'::`2'::s_pfnTestUnlockData )
      goto LABEL_18;
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
LABEL_18:
      ((void (__fastcall *)(__int64, _QWORD, __int64, __int128 *))ProcAddress)(v11, 0, v10, &v16);
    }
    else
    {
      v16 = 0;
      *(_OWORD *)v17 = 0;
      v18 = 0;
    }
    v14 = (int)v17[0];
    *(_DWORD *)(a1 + 64) |= HIDWORD(v17[0]);
    v15 = v17[1];
    if ( !v17[1] )
      *(_DWORD *)(a1 + 184) = v14;
    if ( (_QWORD)pv )
    {
      CoTaskMemFree((LPVOID)pv);
      v15 = v17[1];
    }
    CoTaskMemFree(v15);
  }
  --*(_DWORD *)(a1 + 232);
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x1800180cc  mov     [rsp-8+arg_10], rbx
0x1800180d1  mov     [rsp-8+arg_18], rsi
0x1800180d6  push    rbp
0x1800180d7  push    rdi
0x1800180d8  push    r14
0x1800180da  lea     rbp, [rsp-7A0h]
0x1800180e2  sub     rsp, 8A0h
0x1800180e9  mov     rax, cs:__security_cookie
0x1800180f0  xor     rax, rsp
0x1800180f3  mov     [rbp+7B0h+var_20], rax
0x1800180fa  mov     rsi, rdx
0x1800180fd  mov     rbx, rcx
0x180018100  lea     r14, [rcx+0C0h]
0x180018107  mov     rcx, r14; lpCriticalSection
0x18001810a  call    cs:__imp_EnterCriticalSection
0x180018111  nop     dword ptr [rax+rax+00h]
0x180018116  inc     dword ptr [rbx+0E8h]
0x18001811c  test    dword ptr [rbx+40h], 100h
0x180018123  jnz     loc_18001820F
0x180018129  xorps   xmm0, xmm0
0x18001812c  movdqu  [rbp+7B0h+var_7B8], xmm0
0x180018131  mov     rdx, rsi; struct wil::FailureInfo *
0x180018134  lea     rcx, [rsp+8B0h+pv]; this
0x180018139  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18001813e  mov     rax, [rbx+50h]
0x180018142  cmp     [rbx+58h], rax
0x180018146  jb      short loc_18001816B
0x180018148  test    rax, rax
0x18001814b  lea     rdx, [rax+rax]
0x18001814f  jnz     short loc_180018156
0x180018151  mov     edx, 0Ah
0x180018156  lea     rcx, [rbx+48h]
0x18001815a  call    ?reserve@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N_K@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::reserve(unsigned __int64)
0x18001815f  test    al, al
0x180018161  jnz     short loc_18001816B
0x180018163  mov     dil, 1
0x180018166  jmp     loc_1800181FB
0x18001816b  imul    rdx, [rbx+58h], 0A8h
0x180018173  add     rdx, [rbx+48h]
0x180018177  lea     rax, [rsp+8B0h+pv]
0x18001817c  movups  xmm0, xmmword ptr [rax]
0x18001817f  movups  xmmword ptr [rdx], xmm0
0x180018182  movups  xmm1, xmmword ptr [rax+10h]
0x180018186  movups  xmmword ptr [rdx+10h], xmm1
0x18001818a  movups  xmm0, xmmword ptr [rax+20h]
0x18001818e  movups  xmmword ptr [rdx+20h], xmm0
0x180018192  movups  xmm1, xmmword ptr [rax+30h]
0x180018196  movups  xmmword ptr [rdx+30h], xmm1
0x18001819a  movups  xmm0, xmmword ptr [rax+40h]
0x18001819e  movups  xmmword ptr [rdx+40h], xmm0
0x1800181a2  movups  xmm1, xmmword ptr [rax+50h]
0x1800181a6  movups  xmmword ptr [rdx+50h], xmm1
0x1800181aa  movups  xmm0, xmmword ptr [rax+60h]
0x1800181ae  movups  xmmword ptr [rdx+60h], xmm0
0x1800181b2  mov     r8d, 80h
0x1800181b8  movups  xmm0, xmmword ptr [rax+70h]
0x1800181bc  movups  xmmword ptr [rdx+r8-10h], xmm0
0x1800181c2  movups  xmm1, xmmword ptr [rax+r8]
0x1800181c7  movups  xmmword ptr [rdx+r8], xmm1
0x1800181cc  mov     rax, [rax+r8+10h]
0x1800181d1  mov     [rdx+r8+10h], rax
0x1800181d6  mov     rax, qword ptr [rbp+7B0h+var_7B8]
0x1800181da  mov     [rdx+98h], rax
0x1800181e1  mov     rax, qword ptr [rbp+7B0h+var_7B8+8]
0x1800181e5  mov     [rdx+0A0h], rax
0x1800181ec  xorps   xmm0, xmm0
0x1800181ef  movdqu  [rbp+7B0h+var_7B8], xmm0
0x1800181f4  inc     qword ptr [rbx+58h]
0x1800181f8  xor     dil, dil
0x1800181fb  lea     rcx, [rsp+8B0h+pv]; this
0x180018200  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180018205  test    dil, dil
0x180018208  jz      short loc_18001820F
0x18001820a  bts     dword ptr [rbx+40h], 14h
0x18001820f  mov     eax, [rbx+40h]
0x180018212  bts     eax, 0Bh
0x180018216  mov     [rbx+40h], eax
0x180018219  cmp     qword ptr [rbx+0F0h], 0
0x180018221  jz      loc_18001836E
0x180018227  bt      eax, 8
0x18001822b  jb      loc_18001836E
0x180018231  test    dword ptr [rbx+14h], 8000h
0x180018238  jnz     loc_18001836E
0x18001823e  xorps   xmm0, xmm0
0x180018241  movups  [rsp+8B0h+var_880], xmm0
0x180018246  movups  xmmword ptr [rsp+8B0h+var_870], xmm0
0x18001824b  movups  [rsp+8B0h+var_860], xmm0
0x180018250  and     [rsp+8B0h+pv], 0
0x180018256  mov     [rsp+8B0h+var_848], 0
0x18001825b  lea     rax, [rsp+8B0h+var_847]
0x180018260  mov     [rbp+7B0h+var_40], rax
0x180018267  lea     rax, [rbp+7B0h+var_47]
0x18001826e  mov     [rbp+7B0h+var_30], rax
0x180018275  mov     [rsp+8B0h+var_847], 80408040h
0x18001827d  mov     [rsp+8B0h+var_843], 0
0x180018282  lea     rax, [rsp+8B0h+var_842]
0x180018287  mov     [rbp+7B0h+var_38], rax
0x18001828e  mov     r8d, 1
0x180018294  lea     rdx, [rsp+8B0h+pv]
0x180018299  mov     rcx, rbx
0x18001829c  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800182a1  mov     rdi, rax
0x1800182a4  mov     rsi, [rbx+0F0h]
0x1800182ab  mov     rax, cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800182b2  test    rax, rax
0x1800182b5  jnz     short loc_180018313
0x1800182b7  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800182be  test    rax, rax
0x1800182c1  jnz     short loc_1800182DD
0x1800182c3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800182ca  call    cs:__imp_GetModuleHandleW
0x1800182d1  nop     dword ptr [rax+rax+00h]
0x1800182d6  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800182dd  lea     rdx, aTestunlockdata; "TestUnlockData"
0x1800182e4  mov     rcx, rax; hModule
0x1800182e7  call    cs:__imp_GetProcAddress
0x1800182ee  nop     dword ptr [rax+rax+00h]
0x1800182f3  mov     cs:?s_pfnTestUnlockData@?1??TestUnlockData@@9@4P6AXPEAUHTIPTEST__@@W4TestUnlockOptions@@PEBDPEAUTestInfo@TestInfo_ODR_guard@@@ZEA, rax; void (*`TestUnlockData'::`2'::s_pfnTestUnlockData)(HTIPTEST__ *,TestUnlockOptions,char const *,TestInfo_ODR_guard::TestInfo *)
0x1800182fa  test    rax, rax
0x1800182fd  jnz     short loc_180018313
0x1800182ff  xorps   xmm0, xmm0
0x180018302  movups  [rsp+8B0h+var_880], xmm0
0x180018307  movups  xmmword ptr [rsp+8B0h+var_870], xmm0
0x18001830c  movups  [rsp+8B0h+var_860], xmm0
0x180018311  jmp     short loc_180018325
0x180018313  lea     r9, [rsp+8B0h+var_880]
0x180018318  mov     r8, rdi
0x18001831b  xor     edx, edx
0x18001831d  mov     rcx, rsi
0x180018320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018325  mov     rdx, [rsp+8B0h+var_870]
0x18001832a  mov     rax, rdx
0x18001832d  shr     rax, 20h
0x180018331  or      [rbx+40h], eax
0x180018334  mov     rcx, [rsp+8B0h+var_870+8]
0x180018339  test    rcx, rcx
0x18001833c  jnz     short loc_180018344
0x18001833e  mov     [rbx+0B8h], edx
0x180018344  mov     rax, [rsp+8B0h+pv]
0x180018349  test    rax, rax
0x18001834c  jz      short loc_180018362
0x18001834e  mov     rcx, rax; pv
0x180018351  call    cs:__imp_CoTaskMemFree
0x180018358  nop     dword ptr [rax+rax+00h]
0x18001835d  mov     rcx, [rsp+8B0h+var_870+8]; pv
0x180018362  call    cs:__imp_CoTaskMemFree
0x180018369  nop     dword ptr [rax+rax+00h]
0x18001836e  dec     dword ptr [rbx+0E8h]
0x180018374  mov     rcx, r14; lpCriticalSection
0x180018377  call    cs:__imp_LeaveCriticalSection
0x18001837e  nop     dword ptr [rax+rax+00h]
0x180018383  nop
0x180018384  mov     rcx, [rbp+7B0h+var_20]
0x18001838b  xor     rcx, rsp; StackCookie
0x18001838e  call    __security_check_cookie
0x180018393  lea     r11, [rsp+8B0h+var_10]
0x18001839b  mov     rbx, [r11+30h]
0x18001839f  mov     rsi, [r11+38h]
0x1800183a3  mov     rsp, r11
0x1800183a6  pop     r14
0x1800183a8  pop     rdi
0x1800183a9  pop     rbp
0x1800183aa  retn
```
