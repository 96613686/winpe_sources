# tip2::details::shared_data<0,0,1>::start(void)

- ea: `0x1800b3650`
- end: `0x1800b386a`
- name: `?start@?$shared_data@$0A@$0A@$00@details@tip2@@AEAA?AU_GUID@@XZ`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b3870`

## callees

- `0x180008dc0`
- `0x1800b33c0`
- `0x1800b3650`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b3759`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b37e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b3759`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b37e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b3742`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b37ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b3742`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b37ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3690`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b3690`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b3837`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b3837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b37fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b37fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b37a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b37a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3829`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b3829`

## string_xrefs

- `0x1800b373b`: `kernelbase.dll`
- `0x1800b37c3`: `kernelbase.dll`
- `0x1800b374f`: `TestCreate`

## pseudocode

```c
_OWORD *__fastcall tip2::details::shared_data<0,0,1>::start(__int64 a1, _OWORD *a2)
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
    v8 = tip2::details::shared_data<0,0,1>::serialize_data(a1, &pv, 1);
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
0x1800b3650  mov     [rsp-8+arg_10], rbx
0x1800b3655  push    rbp
0x1800b3656  push    rsi
0x1800b3657  push    rdi
0x1800b3658  push    r12
0x1800b365a  push    r13
0x1800b365c  push    r14
0x1800b365e  push    r15
0x1800b3660  lea     rbp, [rsp-790h]
0x1800b3668  sub     rsp, 890h
0x1800b366f  mov     rax, cs:__security_cookie
0x1800b3676  xor     rax, rsp
0x1800b3679  mov     [rbp+7C0h+var_40], rax
0x1800b3680  mov     r13, rdx
0x1800b3683  mov     rbx, rcx
0x1800b3686  lea     rsi, [rcx+0C0h]
0x1800b368d  mov     rcx, rsi; lpCriticalSection
0x1800b3690  call    cs:__imp_EnterCriticalSection
0x1800b3696  mov     [rsp+8C0h+pv], 0
0x1800b369f  mov     [rsp+8C0h+var_868], 0
0x1800b36a4  lea     rax, [rsp+8C0h+var_867]
0x1800b36a9  mov     [rbp+7C0h+var_60], rax
0x1800b36b0  lea     rax, [rbp+7C0h+var_67]
0x1800b36b7  mov     [rbp+7C0h+var_50], rax
0x1800b36be  mov     [rsp+8C0h+var_867], 80408040h
0x1800b36c6  mov     [rsp+8C0h+var_863], 0
0x1800b36cb  lea     rax, [rsp+8C0h+var_862]
0x1800b36d0  mov     [rbp+7C0h+var_58], rax
0x1800b36d7  test    dword ptr [rbx+40h], 800h
0x1800b36de  jz      short loc_1800B36ED
0x1800b36e0  test    dword ptr [rbx+14h], 8000h
0x1800b36e7  jnz     short loc_1800B36ED
0x1800b36e9  mov     al, 1
0x1800b36eb  jmp     short loc_1800B36EF
0x1800b36ed  xor     al, al
0x1800b36ef  lea     r14, [rbx+90h]
0x1800b36f6  test    al, al
0x1800b36f8  jz      short loc_1800B3712
0x1800b36fa  mov     r8d, 1
0x1800b3700  lea     rdx, [rsp+8C0h+pv]
0x1800b3705  mov     rcx, rbx
0x1800b3708  call    ?serialize_data@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAPEBDAEAVwrite_buffer@tson@@W4serialize_options@23@@Z; tip2::details::shared_data<0,0,1>::serialize_data(tson::write_buffer &,tip2::details::serialize_options)
0x1800b370d  mov     r15, rax
0x1800b3710  jmp     short loc_1800B3715
0x1800b3712  xor     r15d, r15d
0x1800b3715  mov     edi, [rbx+14h]
0x1800b3718  mov     r12b, [rbx+20h]
0x1800b371c  mov     eax, [rbx+10h]
0x1800b371f  mov     [rsp+8C0h+var_880], eax
0x1800b3723  mov     rax, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800b372a  test    rax, rax
0x1800b372d  jnz     short loc_1800B3778
0x1800b372f  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800b3736  test    rax, rax
0x1800b3739  jnz     short loc_1800B374F
0x1800b373b  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800b3742  call    cs:__imp_GetModuleHandleW
0x1800b3748  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800b374f  lea     rdx, aTestcreate; "TestCreate"
0x1800b3756  mov     rcx, rax; hModule
0x1800b3759  call    cs:__imp_GetProcAddress
0x1800b375f  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x1800b3766  test    rax, rax
0x1800b3769  jnz     short loc_1800B3778
0x1800b376b  xorps   xmm0, xmm0
0x1800b376e  movdqu  xmmword ptr [r14], xmm0
0x1800b3773  xor     r12d, r12d
0x1800b3776  jmp     short loc_1800B3796
0x1800b3778  mov     [rsp+8C0h+var_898], r14
0x1800b377d  mov     [rsp+8C0h+var_8A0], r15
0x1800b3782  mov     r9d, edi
0x1800b3785  mov     r8b, r12b
0x1800b3788  xor     edx, edx
0x1800b378a  mov     ecx, [rsp+8C0h+var_880]
0x1800b378e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3793  mov     r12, rax
0x1800b3796  mov     rdi, [rbx+0F0h]
0x1800b379d  test    rdi, rdi
0x1800b37a0  jz      short loc_1800B3804
0x1800b37a2  call    cs:__imp_GetLastError
0x1800b37a8  mov     r15d, eax
0x1800b37ab  mov     rax, cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800b37b2  test    rax, rax
0x1800b37b5  jnz     short loc_1800B37F3
0x1800b37b7  mov     rax, cs:g_tip_details_kernelbaseModuleHandle
0x1800b37be  test    rax, rax
0x1800b37c1  jnz     short loc_1800B37D7
0x1800b37c3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800b37ca  call    cs:__imp_GetModuleHandleW
0x1800b37d0  mov     cs:g_tip_details_kernelbaseModuleHandle, rax
0x1800b37d7  lea     rdx, aTestclose; "TestClose"
0x1800b37de  mov     rcx, rax; hModule
0x1800b37e1  call    cs:__imp_GetProcAddress
0x1800b37e7  mov     cs:?s_pfnTestClose@?1??TestClose@@9@4P6AXPEAUHTIPTEST__@@@ZEA, rax; void (*`TestClose'::`2'::s_pfnTestClose)(HTIPTEST__ *)
0x1800b37ee  test    rax, rax
0x1800b37f1  jz      short loc_1800B37FB
0x1800b37f3  mov     rcx, rdi
0x1800b37f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b37fb  mov     ecx, r15d; dwErrCode
0x1800b37fe  call    cs:__imp_SetLastError
0x1800b3804  mov     [rbx+0F0h], r12
0x1800b380b  mov     dword ptr [rbx+0B8h], 1
0x1800b3815  movups  xmm0, xmmword ptr [r14]
0x1800b3819  movdqu  xmmword ptr [r13+0], xmm0
0x1800b381f  mov     rcx, [rsp+8C0h+pv]; pv
0x1800b3824  test    rcx, rcx
0x1800b3827  jz      short loc_1800B382F
0x1800b3829  call    cs:__imp_CoTaskMemFree
0x1800b382f  test    rsi, rsi
0x1800b3832  jz      short loc_1800B383D
0x1800b3834  mov     rcx, rsi; lpCriticalSection
0x1800b3837  call    cs:__imp_LeaveCriticalSection
0x1800b383d  mov     rax, r13
0x1800b3840  mov     rcx, [rbp+7C0h+var_40]
0x1800b3847  xor     rcx, rsp; StackCookie
0x1800b384a  call    __security_check_cookie
0x1800b384f  mov     rbx, [rsp+8C0h+arg_10]
0x1800b3857  add     rsp, 890h
0x1800b385e  pop     r15
0x1800b3860  pop     r14
0x1800b3862  pop     r13
0x1800b3864  pop     r12
0x1800b3866  pop     rdi
0x1800b3867  pop     rsi
0x1800b3868  pop     rbp
0x1800b3869  retn
```
