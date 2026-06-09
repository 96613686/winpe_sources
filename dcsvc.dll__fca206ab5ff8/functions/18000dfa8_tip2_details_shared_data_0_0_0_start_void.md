# tip2::details::shared_data<0,0,0>::start(void)

- ea: `0x18000dfa8`
- end: `0x18000e1c2`
- name: `?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c200`

## callees

- `0x180001cf0`
- `0x18000dce4`
- `0x18000dfa8`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e0b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e139`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e0b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e139`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e09a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e122`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e09a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e156`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e156`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e0fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dfe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dfe8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e18f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e18f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e181`

## string_xrefs

- `0x18000e093`: `kernelbase.dll`
- `0x18000e11b`: `kernelbase.dll`
- `0x18000e0a7`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,0>::start(__int64 a1, _OWORD *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v5; // r8
  bool v6; // al
  _OWORD *v7; // r14
  __int64 v8; // r15
  unsigned int v9; // edi
  char v10; // r12
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  __int64 v13; // r12
  __int64 v14; // rdi
  DWORD LastError; // r15d
  FARPROC v16; // rax
  HMODULE v17; // rax
  unsigned int v19; // [rsp+40h] [rbp-C0h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  char v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+59h] [rbp-A7h] BYREF
  char v23; // [rsp+5Dh] [rbp-A3h]
  char v24; // [rsp+5Eh] [rbp-A2h] BYREF
  char v25; // [rsp+859h] [rbp+759h] BYREF
  int *v26; // [rsp+860h] [rbp+760h]
  char *v27; // [rsp+868h] [rbp+768h]
  char *v28; // [rsp+870h] [rbp+770h]

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  pv = 0;
  v21 = 0;
  v26 = &v22;
  v28 = &v25;
  v22 = -2143256512;
  v23 = 0;
  v27 = &v24;
  v6 = (*(_DWORD *)(a1 + 64) & 0x800) != 0 && (*(_DWORD *)(a1 + 20) & 0x8000) == 0;
  v7 = (_OWORD *)(a1 + 144);
  if ( v6 )
    v8 = tip2::details::shared_data<0,0,0>::serialize_data((__int64 *)a1, (struct tson::write_buffer *)&pv, 1u);
  else
    v8 = 0;
  v9 = *(_DWORD *)(a1 + 20);
  v10 = *(_BYTE *)(a1 + 32);
  v19 = *(_DWORD *)(a1 + 16);
  ProcAddress = (FARPROC)`TestCreate'::`2'::s_pfnTestCreate;
  if ( `TestCreate'::`2'::s_pfnTestCreate )
    goto LABEL_13;
  ModuleHandleW = g_tip_details_kernelbaseModuleHandle;
  if ( !g_tip_details_kernelbaseModuleHandle )
  {
    ModuleHandleW = GetModuleHandleW(L"kernelbase.dll");
    g_tip_details_kernelbaseModuleHandle = ModuleHandleW;
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "TestCreate");
  `TestCreate'::`2'::s_pfnTestCreate = (__int64)ProcAddress;
  if ( ProcAddress )
  {
LABEL_13:
    LOBYTE(v5) = v10;
    v13 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64))ProcAddress)(
            v19,
            0,
            v5,
            v9,
            v8,
            a1 + 144);
  }
  else
  {
    *v7 = 0;
    v13 = 0;
  }
  v14 = *(_QWORD *)(a1 + 240);
  if ( v14 )
  {
    LastError = GetLastError();
    v16 = (FARPROC)`TestClose'::`2'::s_pfnTestClose;
    if ( `TestClose'::`2'::s_pfnTestClose )
      goto LABEL_19;
    v17 = g_tip_details_kernelbaseModuleHandle;
    if ( !g_tip_details_kernelbaseModuleHandle )
    {
      v17 = GetModuleHandleW(L"kernelbase.dll");
      g_tip_details_kernelbaseModuleHandle = v17;
    }
    v16 = GetProcAddress(v17, "TestClose");
    `TestClose'::`2'::s_pfnTestClose = (__int64)v16;
    if ( v16 )
LABEL_19:
      ((void (__fastcall *)(__int64))v16)(v14);
    SetLastError(LastError);
  }
  *(_QWORD *)(a1 + 240) = v13;
  *(_DWORD *)(a1 + 184) = 1;
  *a2 = *v7;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v4 )
    LeaveCriticalSection(v4);
  return a2;
}

```

## disassembly

```asm
0x18000dfa8  mov     [rsp-8+arg_10], rbx
0x18000dfad  push    rbp
0x18000dfae  push    rsi
0x18000dfaf  push    rdi
0x18000dfb0  push    r12
0x18000dfb2  push    r13
0x18000dfb4  push    r14
0x18000dfb6  push    r15
0x18000dfb8  lea     rbp, [rsp-790h]
0x18000dfc0  sub     rsp, 890h
0x18000dfc7  mov     rax, cs:__security_cookie
0x18000dfce  xor     rax, rsp
0x18000dfd1  mov     [rbp+7C0h+var_40], rax
0x18000dfd8  mov     r13, rdx
0x18000dfdb  mov     rbx, rcx
0x18000dfde  lea     rsi, [rcx+0C0h]
0x18000dfe5  mov     rcx, rsi; lpCriticalSection
0x18000dfe8  call    cs:__imp_EnterCriticalSection
0x18000dfee  mov     [rsp+8C0h+pv], 0
0x18000dff7  mov     [rsp+8C0h+var_868], 0
0x18000dffc  lea     rax, [rsp+8C0h+var_867]
0x18000e001  mov     [rbp+7C0h+var_60], rax
0x18000e008  lea     rax, [rbp+7C0h+var_67]
0x18000e00f  mov     [rbp+7C0h+var_50], rax
0x18000e016  mov     [rsp+8C0h+var_867], 80408040h
0x18000e01e  mov     [rsp+8C0h+var_863], 0
0x18000e023  lea     rax, [rsp+8C0h+var_862]
0x18000e028  mov     [rbp+7C0h+var_58], rax
0x18000e02f  test    dword ptr [rbx+40h], 800h
0x18000e036  jz      short loc_18000E045
0x18000e038  test    dword ptr [rbx+14h], 8000h
0x18000e03f  jnz     short loc_18000E045
0x18000e041  mov     al, 1
0x18000e043  jmp     short loc_18000E047
0x18000e045  xor     al, al
0x18000e047  lea     r14, [rbx+90h]
0x18000e04e  test    al, al
0x18000e050  jz      short loc_18000E06A
0x18000e052  mov     r8d, 1
0x18000e058  lea     rdx, [rsp+8C0h+pv]
0x18000e05d  mov     rcx, rbx
0x18000e060  call    ?serialize_data@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,0>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x18000e065  mov     r15, rax
0x18000e068  jmp     short loc_18000E06D
0x18000e06a  xor     r15d, r15d
0x18000e06d  mov     edi, [rbx+14h]
0x18000e070  mov     r12b, [rbx+20h]
0x18000e074  mov     eax, [rbx+10h]
0x18000e077  mov     [rsp+8C0h+var_880], eax
0x18000e07b  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000e082  test    rax, rax
0x18000e085  jnz     short loc_18000E0D0
0x18000e087  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000e08e  test    rax, rax
0x18000e091  jnz     short loc_18000E0A7
0x18000e093  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e09a  call    cs:__imp_GetModuleHandleW
0x18000e0a0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000e0a7  lea     rdx, aTestcreate; "TestCreate"
0x18000e0ae  mov     rcx, rax; hModule
0x18000e0b1  call    cs:__imp_GetProcAddress
0x18000e0b7  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18000e0be  test    rax, rax
0x18000e0c1  jnz     short loc_18000E0D0
0x18000e0c3  xorps   xmm0, xmm0
0x18000e0c6  movdqu  xmmword ptr [r14], xmm0
0x18000e0cb  xor     r12d, r12d
0x18000e0ce  jmp     short loc_18000E0EE
0x18000e0d0  mov     [rsp+8C0h+var_898], r14
0x18000e0d5  mov     [rsp+8C0h+var_8A0], r15
0x18000e0da  mov     r9d, edi
0x18000e0dd  mov     r8b, r12b
0x18000e0e0  xor     edx, edx
0x18000e0e2  mov     ecx, [rsp+8C0h+var_880]
0x18000e0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0eb  mov     r12, rax
0x18000e0ee  mov     rdi, [rbx+0F0h]
0x18000e0f5  test    rdi, rdi
0x18000e0f8  jz      short loc_18000E15C
0x18000e0fa  call    cs:__imp_GetLastError
0x18000e100  mov     r15d, eax
0x18000e103  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000e10a  test    rax, rax
0x18000e10d  jnz     short loc_18000E14B
0x18000e10f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x18000e116  test    rax, rax
0x18000e119  jnz     short loc_18000E12F
0x18000e11b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18000e122  call    cs:__imp_GetModuleHandleW
0x18000e128  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x18000e12f  lea     rdx, aTestclose; "TestClose"
0x18000e136  mov     rcx, rax; hModule
0x18000e139  call    cs:__imp_GetProcAddress
0x18000e13f  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x18000e146  test    rax, rax
0x18000e149  jz      short loc_18000E153
0x18000e14b  mov     rcx, rdi
0x18000e14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e153  mov     ecx, r15d; dwErrCode
0x18000e156  call    cs:__imp_SetLastError
0x18000e15c  mov     [rbx+0F0h], r12
0x18000e163  mov     dword ptr [rbx+0B8h], 1
0x18000e16d  movups  xmm0, xmmword ptr [r14]
0x18000e171  movdqu  xmmword ptr [r13+0], xmm0
0x18000e177  mov     rcx, [rsp+8C0h+pv]; pv
0x18000e17c  test    rcx, rcx
0x18000e17f  jz      short loc_18000E187
0x18000e181  call    cs:__imp_CoTaskMemFree
0x18000e187  test    rsi, rsi
0x18000e18a  jz      short loc_18000E195
0x18000e18c  mov     rcx, rsi; lpCriticalSection
0x18000e18f  call    cs:__imp_LeaveCriticalSection
0x18000e195  mov     rax, r13
0x18000e198  mov     rcx, [rbp+7C0h+var_40]
0x18000e19f  xor     rcx, rsp; StackCookie
0x18000e1a2  call    __security_check_cookie
0x18000e1a7  mov     rbx, [rsp+8C0h+arg_10]
0x18000e1af  add     rsp, 890h
0x18000e1b6  pop     r15
0x18000e1b8  pop     r14
0x18000e1ba  pop     r13
0x18000e1bc  pop     r12
0x18000e1be  pop     rdi
0x18000e1bf  pop     rsi
0x18000e1c0  pop     rbp
0x18000e1c1  retn
```
