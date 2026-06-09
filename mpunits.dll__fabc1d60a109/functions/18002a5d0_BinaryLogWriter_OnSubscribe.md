# BinaryLogWriter_OnSubscribe

- ea: `0x18002a5d0`
- end: `0x18002a9b2`
- name: `BinaryLogWriter_OnSubscribe`
- size: `994`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e64`
- `0x180007920`
- `0x180007c80`
- `0x18000ab88`
- `0x18000af38`
- `0x18000af88`
- `0x180028858`
- `0x180029cc4`
- `0x18002a5d0`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!_close` at `0x18002a70d`
- `msvcrt!_close` at `0x18002a70d`
- `msvcrt!wcscpy_s` at `0x18002a7f6`
- `msvcrt!wcscpy_s` at `0x18002a898`
- `msvcrt!wcscpy_s` at `0x18002a7f6`
- `msvcrt!wcscpy_s` at `0x18002a898`
- `msvcrt!calloc` at `0x18002a7d4`
- `msvcrt!calloc` at `0x18002a7d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a81a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a8ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a81a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002a8ba`

## string_xrefs

- `0x18002a807`: `mpunits.dll`
- `0x18002a8a9`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_OnSubscribe(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rdi
  unsigned int ClassesFromMOF; // esi
  wchar_t *v8; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rax
  __int16 v13; // r12
  __int64 v14; // rax
  __int64 v15; // r15
  wchar_t *v16; // rax
  __int64 v17; // rbx
  HMODULE ModuleHandleA; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  HMODULE v21; // rax
  void (__fastcall ***v22)(_QWORD, __int64 *); // rcx
  void (__fastcall **v23)(_QWORD, __int64 *); // rax
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // [rsp+30h] [rbp-39h] BYREF
  LPVOID lpTlsValue; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int128 v29; // [rsp+48h] [rbp-21h] BYREF
  __int128 v30; // [rsp+58h] [rbp-11h]
  __int64 (__fastcall *v31)(); // [rsp+68h] [rbp-1h]
  __int128 v32; // [rsp+70h] [rbp+7h] BYREF

  *(_QWORD *)&v32 = a3;
  v31 = 0;
  lpTlsValue = 0;
  v29 = 0;
  v26 = 0;
  v30 = 0;
  v4 = s_observerProtocolFT(a2, 0, (int)BinaryLogWriter_Operation_OnDestroy, (int)&v26, 168);
  if ( v4 )
  {
    trace_BinLogWriter_FailedSubscription(v4, 0);
    return 0;
  }
  v5 = 0;
  v6 = v26 + 152;
  *(_QWORD *)(v26 + 240) = v26;
  *(_QWORD *)&v29 = v26;
  *((_QWORD *)&v29 + 1) = BinaryLogWriter_OnNext;
  *(_QWORD *)&v30 = BinaryLogWriter_OnCompleted;
  *((_QWORD *)&v30 + 1) = BinaryLogWriter_OnError;
  v31 = ObserverProtocol_Release;
  *(_QWORD *)(v6 + 160) = 0;
  *(_DWORD *)(v6 + 116) = 0;
  if ( (*(_BYTE *)(a1 + 84) & 4) != 0 )
    *(_BYTE *)(v6 + 4) = 1;
  *(_QWORD *)(v6 + 96) = 0;
  ClassesFromMOF = BinaryLogWriter_Core_Init(v6);
  if ( ClassesFromMOF )
  {
LABEL_9:
    trace_BinLogWriter_FailedSubscription(ClassesFromMOF, v5);
    if ( *(_DWORD *)v6 != -1 )
    {
      _close(*(_DWORD *)v6);
      *(_DWORD *)v6 = -1;
      trace_BinLogWriter_ClosedLogFile();
    }
    ((void (__fastcall *)(__int64, _QWORD, LPVOID))ObserverProtocol_PostError)(v26, ClassesFromMOF, lpTlsValue);
    if ( lpTlsValue )
    {
      if ( *(_QWORD *)lpTlsValue )
        (*(void (**)(void))(*(_QWORD *)lpTlsValue + 16LL))();
    }
    ((void (__fastcall *)(__int64))ObserverProtocol_Release)(v26);
    return 0;
  }
  v8 = *(wchar_t **)(a1 + 64);
  if ( v8 )
  {
    ClassesFromMOF = ReadClassesFromMOF(v8, (char **)(v6 + 72), (MI_Instance *)&lpTlsValue);
    if ( ClassesFromMOF )
    {
      ReportErrorDetails(lpTlsValue);
      lpTlsValue = 0;
      goto LABEL_9;
    }
  }
  v10 = *(_QWORD *)(a1 + 48);
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(v10 + 2 * v11) );
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(*(_QWORD *)(a1 + 56) + 2 * v12) );
  v13 = *(_WORD *)(v10 + 2 * v11 - 2);
  v14 = v11 + v12;
  v15 = v14 + 1;
  if ( v13 == 92 )
    v15 = v14;
  v16 = (wchar_t *)calloc(v15 + 1, 2u);
  *(_QWORD *)(v6 + 96) = v16;
  if ( !v16 )
  {
    ClassesFromMOF = 27;
    goto LABEL_9;
  }
  v5 = wcscpy_s(v16, v15 + 1, *(const wchar_t **)(a1 + 48));
  if ( v5 )
  {
    v17 = *(_QWORD *)(a1 + 48);
    ClassesFromMOF = 1;
    v32 = 0;
    ModuleHandleA = GetModuleHandleA("mpunits.dll");
    v19 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2007, v17);
    BYTE8(v32) = 1;
LABEL_26:
    *(_QWORD *)&v32 = v19;
    MI_ReportErrorDetails_ForCustomError(v5, (int)L"ERRNO", 0, 0);
    goto LABEL_9;
  }
  if ( v13 != 92 )
    *(_WORD *)(*(_QWORD *)(v6 + 96) + 2 * v11++) = 92;
  v5 = wcscpy_s((wchar_t *)(*(_QWORD *)(v6 + 96) + 2 * v11), v15 - v11 + 1, *(const wchar_t **)(a1 + 56));
  if ( v5 )
  {
    v20 = *(_QWORD *)(a1 + 56);
    ClassesFromMOF = 1;
    v32 = 0;
    v21 = GetModuleHandleA("mpunits.dll");
    v19 = Intlstr_FormatString_FormatMessage(v21, 2007, v20);
    BYTE8(v32) = 1;
    goto LABEL_26;
  }
  *(_QWORD *)(v6 + 104) = *(_QWORD *)(a1 + 72);
  *(_DWORD *)(v6 + 112) = *(_DWORD *)(a1 + 80);
  *(_BYTE *)(v6 + 120) = 0;
  v22 = *(void (__fastcall ****)(_QWORD, __int64 *))(a1 + 96);
  if ( v22 )
  {
    *(_QWORD *)(v6 + 64) = v22;
    v23 = *v22;
    v28 = 0;
    if ( v23 )
      (*v23)(v22, &v28);
  }
  ((void (__fastcall *)(__int64))ObserverProtocol_AddRef)(v26);
  v24 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD))(*(_QWORD *)(a1 + 40) + 32LL))(
          *(_QWORD *)(a1 + 40),
          &v29,
          v32);
  ((void (__fastcall *)(__int64, __int64))ObserverProtocol_TrackDisposable)(v26, v24);
  if ( v24 )
    (*(void (__fastcall **)(_QWORD))(v24 + 24))(*(_QWORD *)v24);
  *(_QWORD *)&v32 = 0x40000006BLL;
  *((_QWORD *)&v32 + 1) = 1;
  Etw_Trace0(&v32);
  v25 = ((__int64 (__fastcall *)(__int64))ObserverProtocol_GetDisposable)(v26);
  ((void (__fastcall *)(__int64))ObserverProtocol_Release)(v26);
  return v25;
}

```

## disassembly

```asm
0x18002a5d0  mov     [rsp-8+arg_18], rbx
0x18002a5d5  push    rbp
0x18002a5d6  push    rsi
0x18002a5d7  push    rdi
0x18002a5d8  push    r12
0x18002a5da  push    r13
0x18002a5dc  push    r14
0x18002a5de  push    r15
0x18002a5e0  lea     rbp, [rsp-27h]
0x18002a5e5  sub     rsp, 90h
0x18002a5ec  mov     rax, cs:__security_cookie
0x18002a5f3  xor     rax, rsp
0x18002a5f6  mov     [rbp+57h+var_40], rax
0x18002a5fa  xor     eax, eax
0x18002a5fc  mov     qword ptr [rbp+57h+var_50], r8
0x18002a600  mov     [rbp+57h+var_58], rax
0x18002a604  lea     r9, [rbp+57h+var_90]
0x18002a608  mov     rax, cs:off_180047BB0
0x18002a60f  lea     r8, BinaryLogWriter_Operation_OnDestroy
0x18002a616  xorps   xmm0, xmm0
0x18002a619  mov     [rsp+0C0h+var_A0], 0A8h
0x18002a622  mov     r10, rdx
0x18002a625  xor     r13d, r13d
0x18002a628  mov     rbx, rcx
0x18002a62b  mov     [rbp+57h+lpTlsValue], r13
0x18002a62f  movups  [rbp+57h+var_78], xmm0
0x18002a633  mov     [rbp+57h+var_90], r13
0x18002a637  xor     edx, edx
0x18002a639  movups  [rbp+57h+var_68], xmm0
0x18002a63d  mov     rax, [rax]
0x18002a640  mov     rcx, r10
0x18002a643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a648  test    eax, eax
0x18002a64a  jz      short loc_18002A65A
0x18002a64c  xor     edx, edx
0x18002a64e  mov     ecx, eax
0x18002a650  call    trace_BinLogWriter_FailedSubscription
0x18002a655  jmp     loc_18002A766
0x18002a65a  mov     rax, [rbp+57h+var_90]
0x18002a65e  mov     r14d, r13d
0x18002a661  lea     rdi, [rax+98h]
0x18002a668  mov     [rdi+58h], rax
0x18002a66c  mov     rax, [rbp+57h+var_90]
0x18002a670  mov     qword ptr [rbp+57h+var_78], rax
0x18002a674  lea     rax, BinaryLogWriter_OnNext
0x18002a67b  mov     qword ptr [rbp+57h+var_78+8], rax
0x18002a67f  lea     rax, BinaryLogWriter_OnCompleted
0x18002a686  mov     qword ptr [rbp+57h+var_68], rax
0x18002a68a  lea     rax, BinaryLogWriter_OnError
0x18002a691  mov     qword ptr [rbp+57h+var_68+8], rax
0x18002a695  mov     rax, cs:off_180047BB0
0x18002a69c  mov     rcx, [rax+10h]
0x18002a6a0  mov     [rbp+57h+var_58], rcx
0x18002a6a4  mov     [rdi+0A0h], r13
0x18002a6ab  mov     [rdi+74h], r13d
0x18002a6af  test    byte ptr [rbx+54h], 4
0x18002a6b3  jz      short loc_18002A6B9
0x18002a6b5  mov     byte ptr [rdi+4], 1
0x18002a6b9  mov     rcx, rdi
0x18002a6bc  mov     [rdi+60h], r13
0x18002a6c0  call    BinaryLogWriter_Core_Init
0x18002a6c5  mov     esi, eax
0x18002a6c7  test    eax, eax
0x18002a6c9  jnz     short loc_18002A6FC
0x18002a6cb  mov     rcx, [rbx+40h]; FileName
0x18002a6cf  test    rcx, rcx
0x18002a6d2  jz      loc_18002A78F
0x18002a6d8  lea     rdx, [rdi+48h]
0x18002a6dc  lea     r8, [rbp+57h+lpTlsValue]
0x18002a6e0  call    ReadClassesFromMOF
0x18002a6e5  mov     esi, eax
0x18002a6e7  test    eax, eax
0x18002a6e9  jz      loc_18002A78F
0x18002a6ef  mov     rcx, [rbp+57h+lpTlsValue]; lpTlsValue
0x18002a6f3  call    ReportErrorDetails
0x18002a6f8  mov     [rbp+57h+lpTlsValue], r13
0x18002a6fc  mov     edx, r14d
0x18002a6ff  mov     ecx, esi
0x18002a701  call    trace_BinLogWriter_FailedSubscription
0x18002a706  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18002a709  jz      short loc_18002A71E
0x18002a70b  mov     ecx, [rdi]; FileHandle
0x18002a70d  call    cs:__imp__close
0x18002a713  mov     dword ptr [rdi], 0FFFFFFFFh
0x18002a719  call    trace_BinLogWriter_ClosedLogFile
0x18002a71e  mov     rax, cs:off_180047BB0
0x18002a725  mov     edx, esi
0x18002a727  mov     r8, [rbp+57h+lpTlsValue]
0x18002a72b  mov     rcx, [rbp+57h+var_90]
0x18002a72f  mov     rax, [rax+50h]
0x18002a733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a738  mov     rcx, [rbp+57h+lpTlsValue]
0x18002a73c  test    rcx, rcx
0x18002a73f  jz      short loc_18002A752
0x18002a741  mov     rax, [rcx]
0x18002a744  test    rax, rax
0x18002a747  jz      short loc_18002A752
0x18002a749  mov     rax, [rax+10h]
0x18002a74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a752  mov     rax, cs:off_180047BB0
0x18002a759  mov     rcx, [rbp+57h+var_90]
0x18002a75d  mov     rax, [rax+10h]
0x18002a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a766  xor     eax, eax
0x18002a768  mov     rcx, [rbp+57h+var_40]
0x18002a76c  xor     rcx, rsp; StackCookie
0x18002a76f  call    __security_check_cookie
0x18002a774  mov     rbx, [rsp+0C0h+arg_18]
0x18002a77c  add     rsp, 90h
0x18002a783  pop     r15
0x18002a785  pop     r14
0x18002a787  pop     r13
0x18002a789  pop     r12
0x18002a78b  pop     rdi
0x18002a78c  pop     rsi
0x18002a78d  pop     rbp
0x18002a78e  retn
0x18002a78f  mov     rcx, [rbx+30h]
0x18002a793  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a797  inc     rsi
0x18002a79a  cmp     [rcx+rsi*2], r13w
0x18002a79f  jnz     short loc_18002A797
0x18002a7a1  mov     rdx, [rbx+38h]
0x18002a7a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a7a9  inc     rax
0x18002a7ac  cmp     [rdx+rax*2], r13w
0x18002a7b1  jnz     short loc_18002A7A9
0x18002a7b3  movzx   r12d, word ptr [rcx+rsi*2-2]
0x18002a7b9  add     rax, rsi
0x18002a7bc  mov     ecx, 5Ch ; '\'
0x18002a7c1  cmp     r12w, cx
0x18002a7c5  lea     r15, [rax+1]
0x18002a7c9  cmovz   r15, rax
0x18002a7cd  lea     edx, [rcx-5Ah]; Size
0x18002a7d0  lea     rcx, [r15+1]; Count
0x18002a7d4  call    cs:__imp_calloc
0x18002a7da  mov     [rdi+60h], rax
0x18002a7de  test    rax, rax
0x18002a7e1  jnz     short loc_18002A7EB
0x18002a7e3  lea     esi, [rax+1Bh]
0x18002a7e6  jmp     loc_18002A6FC
0x18002a7eb  mov     r8, [rbx+30h]; Source
0x18002a7ef  lea     rdx, [r15+1]; SizeInWords
0x18002a7f3  mov     rcx, rax; Destination
0x18002a7f6  call    cs:__imp_wcscpy_s
0x18002a7fc  mov     r14d, eax
0x18002a7ff  test    eax, eax
0x18002a801  jz      short loc_18002A869
0x18002a803  mov     rbx, [rbx+30h]
0x18002a807  lea     rcx, ModuleName; "mpunits.dll"
0x18002a80e  xorps   xmm0, xmm0
0x18002a811  mov     esi, 1
0x18002a816  movups  [rbp+57h+var_50], xmm0
0x18002a81a  call    cs:__imp_GetModuleHandleA
0x18002a820  mov     r8, rbx
0x18002a823  mov     edx, 7D7h
0x18002a828  mov     rcx, rax
0x18002a82b  call    _Intlstr_FormatString_FormatMessage
0x18002a830  mov     byte ptr [rbp+57h+var_50+8], sil
0x18002a834  mov     qword ptr [rbp+57h+var_50], rax
0x18002a838  lea     r9, [rbp+57h+var_50]
0x18002a83c  movaps  xmm0, [rbp+57h+var_50]
0x18002a840  lea     rdx, aErrno; "ERRNO"
0x18002a847  mov     [rsp+0C0h+var_98], r13; __int64
0x18002a84c  mov     r8d, 6
0x18002a852  mov     ecx, r14d; int
0x18002a855  movdqa  [rbp+57h+var_50], xmm0
0x18002a85a  mov     [rsp+0C0h+var_A0], r13; __int64
0x18002a85f  call    MI_ReportErrorDetails_ForCustomError
0x18002a864  jmp     loc_18002A6FC
0x18002a869  mov     ecx, 5Ch ; '\'
0x18002a86e  cmp     r12w, cx
0x18002a872  jz      short loc_18002A87F
0x18002a874  mov     rax, [rdi+60h]
0x18002a878  mov     [rax+rsi*2], cx
0x18002a87c  inc     rsi
0x18002a87f  mov     rax, [rdi+60h]
0x18002a883  sub     r15, rsi
0x18002a886  mov     r8, [rbx+38h]; Source
0x18002a88a  mov     r12d, 1
0x18002a890  lea     rcx, [rax+rsi*2]; Destination
0x18002a894  lea     rdx, [r12+r15]; SizeInWords
0x18002a898  call    cs:__imp_wcscpy_s
0x18002a89e  mov     r14d, eax
0x18002a8a1  test    eax, eax
0x18002a8a3  jz      short loc_18002A8D9
0x18002a8a5  mov     rbx, [rbx+38h]
0x18002a8a9  lea     rcx, ModuleName; "mpunits.dll"
0x18002a8b0  xorps   xmm0, xmm0
0x18002a8b3  mov     esi, r12d
0x18002a8b6  movups  [rbp+57h+var_50], xmm0
0x18002a8ba  call    cs:__imp_GetModuleHandleA
0x18002a8c0  mov     r8, rbx
0x18002a8c3  mov     edx, 7D7h
0x18002a8c8  mov     rcx, rax
0x18002a8cb  call    _Intlstr_FormatString_FormatMessage
0x18002a8d0  mov     byte ptr [rbp+57h+var_50+8], r12b
0x18002a8d4  jmp     loc_18002A834
0x18002a8d9  mov     rax, [rbx+48h]
0x18002a8dd  mov     [rdi+68h], rax
0x18002a8e1  mov     eax, [rbx+50h]
0x18002a8e4  mov     [rdi+70h], eax
0x18002a8e7  mov     [rdi+78h], r13b
0x18002a8eb  mov     rcx, [rbx+60h]
0x18002a8ef  test    rcx, rcx
0x18002a8f2  jz      short loc_18002A910
0x18002a8f4  mov     [rdi+40h], rcx
0x18002a8f8  mov     rax, [rcx]
0x18002a8fb  mov     [rbp+57h+var_80], r13
0x18002a8ff  test    rax, rax
0x18002a902  jz      short loc_18002A910
0x18002a904  mov     rax, [rax]
0x18002a907  lea     rdx, [rbp+57h+var_80]
0x18002a90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a910  mov     rax, cs:off_180047BB0
0x18002a917  mov     rcx, [rbp+57h+var_90]
0x18002a91b  mov     rax, [rax+8]
0x18002a91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a924  mov     rcx, [rbx+28h]
0x18002a928  lea     rdx, [rbp+57h+var_78]
0x18002a92c  mov     r8, qword ptr [rbp+57h+var_50]
0x18002a930  mov     rax, [rcx+20h]
0x18002a934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a939  mov     rcx, cs:off_180047BB0
0x18002a940  mov     rbx, rax
0x18002a943  mov     rdx, rbx
0x18002a946  mov     rax, [rcx+70h]
0x18002a94a  mov     rcx, [rbp+57h+var_90]
0x18002a94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a953  test    rbx, rbx
0x18002a956  jz      short loc_18002A964
0x18002a958  mov     rcx, [rbx]
0x18002a95b  mov     rax, [rbx+18h]
0x18002a95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a964  lea     rcx, [rbp+57h+var_50]
0x18002a968  mov     dword ptr [rbp+57h+var_50], 6Bh ; 'k'
0x18002a96f  mov     dword ptr [rbp+57h+var_50+4], 4
0x18002a976  mov     qword ptr [rbp+57h+var_50+8], r12
0x18002a97a  call    Etw_Trace0
0x18002a97f  mov     rax, cs:off_180047BB0
0x18002a986  mov     rcx, [rbp+57h+var_90]
0x18002a98a  mov     rax, [rax+18h]
0x18002a98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a993  mov     rcx, cs:off_180047BB0
0x18002a99a  mov     rbx, rax
0x18002a99d  mov     rax, [rcx+10h]
0x18002a9a1  mov     rcx, [rbp+57h+var_90]
0x18002a9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9aa  mov     rax, rbx
0x18002a9ad  jmp     loc_18002A768
```
