# BinaryLogWriter_OnSerializeClassDecl

- ea: `0x1800279b0`
- end: `0x180027ea1`
- name: `BinaryLogWriter_OnSerializeClassDecl`
- size: `1265`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a160`
- `0x18002a410`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x18000abb8`
- `0x18000aee8`
- `0x18000b030`
- `0x180026660`
- `0x1800266f0`
- `0x180027634`
- `0x1800279b0`
- `0x18002a410`
- `0x180043d40`
- `0x180043e08`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!_write` at `0x180027dda`
- `msvcrt!_write` at `0x180027df4`
- `msvcrt!_write` at `0x180027dda`
- `msvcrt!_write` at `0x180027df4`
- `msvcrt!free` at `0x180027b4d`
- `msvcrt!free` at `0x180027b4d`
- `msvcrt!calloc` at `0x180027b06`
- `msvcrt!calloc` at `0x180027e50`
- `msvcrt!calloc` at `0x180027b06`
- `msvcrt!calloc` at `0x180027e50`
- `msvcrt!_wcsicmp` at `0x180027aa6`
- `msvcrt!_wcsicmp` at `0x180027aa6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027d7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027bb3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027d7c`
- `miutils!Class_New` at `0x180027ae3`
- `miutils!Class_New` at `0x180027ae3`

## string_xrefs

- `0x180027ba3`: `mpunits.dll`
- `0x180027c5c`: `mpunits.dll`
- `0x180027d05`: `mpunits.dll`
- `0x180027d71`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_OnSerializeClassDecl(
        __int64 a1,
        ULONGLONG a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5)
{
  bool v6; // zf
  __int64 v7; // r13
  __int64 v8; // r15
  _DWORD *v10; // rdi
  unsigned int Buffer; // esi
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // edx
  int v15; // r9d
  __int64 v17; // rsi
  __int64 v18; // r15
  __int64 v19; // r13
  __int64 v20; // rcx
  _DWORD *v21; // rax
  HMODULE ModuleHandleA; // rax
  HMODULE v23; // rax
  __int64 String_LoadString; // rax
  int v25; // ecx
  int v26; // edx
  int v27; // r9d
  __int64 v28; // rbx
  HMODULE v29; // rax
  __int64 v30; // rdx
  HMODULE v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  _DWORD *v34; // rax
  unsigned int MaxCharCount; // [rsp+30h] [rbp-61h] BYREF
  __int64 v36; // [rsp+38h] [rbp-59h] BYREF
  __int64 Buf; // [rsp+40h] [rbp-51h] BYREF
  __int128 v38; // [rsp+48h] [rbp-49h] BYREF
  __int64 v39; // [rsp+58h] [rbp-39h]
  EVENT_DESCRIPTOR v40[2]; // [rsp+60h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-11h] BYREF

  *(_QWORD *)&EventDescriptor.Id = a4;
  Buf = a3;
  v36 = 0;
  v6 = *(_DWORD *)(a1 + 96) == -1;
  v7 = a4;
  MaxCharCount = 0;
  v8 = a3;
  v39 = 0;
  memset(v40, 0, sizeof(v40));
  v38 = 0;
  if ( v6 )
    return 0;
  if ( !*((_QWORD *)a5 + 6) )
  {
    v10 = 0;
    Buffer = AllocateBuffer(a5, 4000);
    if ( Buffer )
      goto LABEL_21;
  }
  v12 = *((_QWORD *)a5 + 3);
  v40[0].Keyword = a2;
  v13 = HashMap_Find(v12, v40);
  v10 = (_DWORD *)v13;
  if ( v13 )
  {
    if ( *(_DWORD *)(v13 + 24) == 1 )
      return 0;
    if ( *(_DWORD *)(v13 + 24) == 2 )
    {
      *((_BYTE *)a5 + 80) = 1;
      return 0;
    }
  }
  else
  {
    v17 = *((_QWORD *)a5 + 9);
    if ( v17 )
    {
      v18 = 0;
      if ( *(_DWORD *)(v17 + 8) )
      {
        while ( 1 )
        {
          v19 = *(_QWORD *)(*(_QWORD *)v17 + 8 * v18);
          if ( !_wcsicmp(*(const wchar_t **)(*(_QWORD *)(v19 + 8) + 8LL), *(const wchar_t **)(a1 + 8)) )
            break;
          v18 = (unsigned int)(v18 + 1);
          if ( (unsigned int)v18 >= *(_DWORD *)(v17 + 8) )
            goto LABEL_13;
        }
        if ( !v19 )
        {
LABEL_13:
          v7 = *(_QWORD *)&EventDescriptor.Id;
          goto LABEL_14;
        }
        *((_BYTE *)a5 + 80) = 1;
        v21 = calloc(1u, 0x20u);
        v10 = v21;
        if ( v21 )
        {
          *((_QWORD *)v21 + 1) = a2;
          *((_QWORD *)v21 + 2) = 0;
          v21[6] = 2;
          if ( !(unsigned int)HashMap_Insert(*((_QWORD *)a5 + 3), v21) )
            return 0;
LABEL_28:
          EventDescriptor = 0;
          Buffer = 1;
          ModuleHandleA = GetModuleHandleA("mpunits.dll");
          *(_QWORD *)&EventDescriptor.Id = Intlstr_GetString_LoadString(ModuleHandleA, 2018);
          LOBYTE(EventDescriptor.Keyword) = 0;
          MI_ReportErrorDetails_ForCustomError(19, (int)L"BinaryLogger", 0, 0);
          goto LABEL_20;
        }
LABEL_19:
        Buffer = 27;
LABEL_20:
        trace_BinLogWriter_FailedToUpdateClassCache(*(_QWORD *)(a1 + 8));
        goto LABEL_21;
      }
LABEL_14:
      v8 = Buf;
    }
  }
  v20 = *(_QWORD *)(a1 + 96);
  if ( v20 )
  {
    if ( *(_QWORD *)v20 )
      Buffer = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 104LL))(v20, &v36);
    else
      Buffer = 4;
  }
  else
  {
    Buffer = Class_New(a1, v8, v7, 0, &v36);
  }
  if ( Buffer )
    goto LABEL_21;
  Buffer = SerializeClassToBinary((_DWORD)a5, v14, v36, v15, (__int64)&MaxCharCount);
  if ( Buffer != 27 )
  {
LABEL_39:
    if ( Buffer )
    {
      *(_DWORD *)&EventDescriptor.Id = 10104;
      *(_DWORD *)&EventDescriptor.Level = 4;
      EventDescriptor.Keyword = 1;
      Etw_Trace1_LPCWSTR(&EventDescriptor);
      v28 = *(_QWORD *)(a1 + 8);
      EventDescriptor = 0;
      v29 = GetModuleHandleA("mpunits.dll");
      String_LoadString = Intlstr_FormatString_FormatMessage(v29, 2015, v28);
      LOBYTE(EventDescriptor.Keyword) = 1;
      v25 = 15;
      goto LABEL_36;
    }
    if ( *((_QWORD *)a5 + 8) )
    {
      v30 = *a5;
      LODWORD(Buf) = 0;
      if ( (unsigned int)Logger_LockPartOfFile(&v38, v30, 4) || _write(*a5, &Buf, 4u) != 4 )
      {
LABEL_43:
        EventDescriptor = 0;
        v31 = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&EventDescriptor.Id = Intlstr_GetString_LoadString(v31, 2017);
        LOBYTE(EventDescriptor.Keyword) = 0;
        MI_ReportErrorDetails_ForCustomError(17, (int)L"BinaryLogger", 0, 0);
        Buffer = 1;
        goto LABEL_21;
      }
      *((_QWORD *)a5 + 1) += 4LL;
    }
    v32 = _write(*a5, *((const void **)a5 + 6), MaxCharCount);
    v33 = MaxCharCount;
    if ( v32 == MaxCharCount )
    {
      ++a5[5];
      *((_QWORD *)a5 + 1) += v33 + 4;
      if ( v10 )
      {
        if ( v36 && *(_QWORD *)v36 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 96LL))(v36);
        v10[6] = 1;
        return Logger_UnlockPartOfFile(&v38);
      }
      v34 = calloc(1u, 0x20u);
      v10 = v34;
      if ( v34 )
      {
        *((_QWORD *)v34 + 1) = a2;
        *((_QWORD *)v34 + 2) = 0;
        v34[6] = 1;
        if ( !(unsigned int)HashMap_Insert(*((_QWORD *)a5 + 3), v34) )
        {
          if ( v36 && *(_QWORD *)v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 96LL))(v36);
          return Logger_UnlockPartOfFile(&v38);
        }
        goto LABEL_28;
      }
      goto LABEL_19;
    }
    goto LABEL_43;
  }
  if ( MaxCharCount > 0x7FFFFFFF )
  {
    Buffer = 1;
    trace_BinLogWriter_BufferNeededTooLarge();
    EventDescriptor = 0;
    v23 = GetModuleHandleA("mpunits.dll");
    String_LoadString = Intlstr_GetString_LoadString(v23, 2016);
    LOBYTE(EventDescriptor.Keyword) = 0;
    v25 = 21;
LABEL_36:
    *(_QWORD *)&EventDescriptor.Id = String_LoadString;
    MI_ReportErrorDetails_ForCustomError(v25, (int)L"BinaryLogger", 0, 0);
    goto LABEL_21;
  }
  Buffer = AllocateBuffer(a5, MaxCharCount);
  if ( !Buffer )
  {
    Buffer = SerializeClassToBinary((_DWORD)a5, v26, v36, v27, (__int64)&MaxCharCount);
    goto LABEL_39;
  }
LABEL_21:
  Logger_UnlockPartOfFile(&v38);
  if ( v36 && *(_QWORD *)v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 96LL))(v36);
  if ( v10 )
    free(v10);
  *(_DWORD *)&EventDescriptor.Id = 10105;
  *(_DWORD *)&EventDescriptor.Level = 4;
  EventDescriptor.Keyword = 1;
  Etw_Trace1_LPCWSTR(&EventDescriptor);
  return Buffer;
}

```

## disassembly

```asm
0x1800279b0  push    rbp
0x1800279b2  push    rbx
0x1800279b3  push    rsi
0x1800279b4  push    rdi
0x1800279b5  push    r12
0x1800279b7  push    r13
0x1800279b9  push    r14
0x1800279bb  push    r15
0x1800279bd  lea     rbp, [rsp-17h]
0x1800279c2  sub     rsp, 0A8h
0x1800279c9  mov     rax, cs:__security_cookie
0x1800279d0  xor     rax, rsp
0x1800279d3  mov     [rbp+4Fh+var_50], rax
0x1800279d7  mov     rbx, [rbp+4Fh+arg_20]
0x1800279db  mov     r14, rcx
0x1800279de  xor     ecx, ecx
0x1800279e0  mov     qword ptr [rbp+4Fh+EventDescriptor.Id], r9
0x1800279e4  xor     eax, eax
0x1800279e6  mov     [rbp+4Fh+Buf], r8
0x1800279ea  xorps   xmm0, xmm0
0x1800279ed  mov     [rbp+4Fh+var_A8], rcx
0x1800279f1  cmp     dword ptr [r14+60h], 0FFFFFFFFh
0x1800279f6  xorps   xmm1, xmm1
0x1800279f9  mov     r13, r9
0x1800279fc  mov     [rbp+4Fh+MaxCharCount], ecx
0x1800279ff  mov     r15, r8
0x180027a02  mov     [rbp+4Fh+var_88], rax
0x180027a06  mov     r12, rdx
0x180027a09  movups  [rbp+4Fh+var_80], xmm0
0x180027a0d  movups  [rbp+4Fh+var_70], xmm0
0x180027a11  movups  [rbp+4Fh+var_98], xmm1
0x180027a15  jz      short loc_180027A5F
0x180027a17  cmp     [rbx+30h], rcx
0x180027a1b  jnz     short loc_180027A36
0x180027a1d  mov     edi, ecx
0x180027a1f  mov     edx, 0FA0h
0x180027a24  mov     rcx, rbx
0x180027a27  call    AllocateBuffer
0x180027a2c  mov     esi, eax
0x180027a2e  test    eax, eax
0x180027a30  jnz     loc_180027B22
0x180027a36  mov     rcx, [rbx+18h]
0x180027a3a  lea     rdx, [rbp+4Fh+var_80]
0x180027a3e  mov     qword ptr [rbp+4Fh+var_80+8], r12
0x180027a42  call    HashMap_Find
0x180027a47  mov     rdi, rax
0x180027a4a  test    rax, rax
0x180027a4d  jz      short loc_180027A81
0x180027a4f  cmp     dword ptr [rax+18h], 1
0x180027a53  jz      short loc_180027A5F
0x180027a55  cmp     dword ptr [rax+18h], 2
0x180027a59  jnz     short loc_180027AC1
0x180027a5b  mov     byte ptr [rbx+50h], 1
0x180027a5f  xor     eax, eax
0x180027a61  mov     rcx, [rbp+4Fh+var_50]
0x180027a65  xor     rcx, rsp; StackCookie
0x180027a68  call    __security_check_cookie
0x180027a6d  add     rsp, 0A8h
0x180027a74  pop     r15
0x180027a76  pop     r14
0x180027a78  pop     r13
0x180027a7a  pop     r12
0x180027a7c  pop     rdi
0x180027a7d  pop     rsi
0x180027a7e  pop     rbx
0x180027a7f  pop     rbp
0x180027a80  retn
0x180027a81  mov     rsi, [rbx+48h]
0x180027a85  test    rsi, rsi
0x180027a88  jz      short loc_180027AC1
0x180027a8a  xor     r15d, r15d
0x180027a8d  cmp     [rsi+8], r15d
0x180027a91  jbe     short loc_180027ABD
0x180027a93  mov     rax, [rsi]
0x180027a96  mov     rdx, [r14+8]; String2
0x180027a9a  mov     r13, [rax+r15*8]
0x180027a9e  mov     rcx, [r13+8]
0x180027aa2  mov     rcx, [rcx+8]; String1
0x180027aa6  call    cs:__imp__wcsicmp
0x180027aac  test    eax, eax
0x180027aae  jz      short loc_180027AF3
0x180027ab0  inc     r15d
0x180027ab3  cmp     r15d, [rsi+8]
0x180027ab7  jb      short loc_180027A93
0x180027ab9  mov     r13, qword ptr [rbp+4Fh+EventDescriptor.Id]
0x180027abd  mov     r15, [rbp+4Fh+Buf]
0x180027ac1  mov     rcx, [r14+60h]
0x180027ac5  test    rcx, rcx
0x180027ac8  jnz     loc_180027BFD
0x180027ace  lea     rax, [rbp+4Fh+var_A8]
0x180027ad2  xor     r9d, r9d
0x180027ad5  mov     r8, r13
0x180027ad8  mov     [rsp+0E0h+var_C0], rax
0x180027add  mov     rdx, r15
0x180027ae0  mov     rcx, r14
0x180027ae3  call    cs:__imp_Class_New
0x180027ae9  mov     esi, eax
0x180027aeb  xor     r15d, r15d
0x180027aee  jmp     loc_180027C1E
0x180027af3  xor     r15d, r15d
0x180027af6  test    r13, r13
0x180027af9  jz      short loc_180027AB9
0x180027afb  lea     edx, [r15+20h]; Size
0x180027aff  mov     byte ptr [rbx+50h], 1
0x180027b03  lea     ecx, [rdx-1Fh]; Count
0x180027b06  call    cs:__imp_calloc
0x180027b0c  mov     rdi, rax
0x180027b0f  test    rax, rax
0x180027b12  jnz     short loc_180027B7D
0x180027b14  mov     esi, 1Bh
0x180027b19  mov     rcx, [r14+8]
0x180027b1d  call    trace_BinLogWriter_FailedToUpdateClassCache
0x180027b22  lea     rcx, [rbp+4Fh+var_98]
0x180027b26  call    Logger_UnlockPartOfFile
0x180027b2b  mov     rcx, [rbp+4Fh+var_A8]
0x180027b2f  test    rcx, rcx
0x180027b32  jz      short loc_180027B45
0x180027b34  mov     rax, [rcx]
0x180027b37  test    rax, rax
0x180027b3a  jz      short loc_180027B45
0x180027b3c  mov     rax, [rax+60h]
0x180027b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b45  test    rdi, rdi
0x180027b48  jz      short loc_180027B53
0x180027b4a  mov     rcx, rdi; Block
0x180027b4d  call    cs:__imp_free
0x180027b53  mov     rdx, [r14+8]
0x180027b57  lea     rcx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180027b5b  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 2779h
0x180027b62  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], 4
0x180027b69  mov     [rbp+4Fh+EventDescriptor.Keyword], 1
0x180027b71  call    Etw_Trace1_LPCWSTR
0x180027b76  mov     eax, esi
0x180027b78  jmp     loc_180027A61
0x180027b7d  mov     [rax+8], r12
0x180027b81  mov     rdx, rax
0x180027b84  mov     [rax+10h], r15
0x180027b88  mov     dword ptr [rax+18h], 2
0x180027b8f  mov     rcx, [rbx+18h]
0x180027b93  call    HashMap_Insert
0x180027b98  test    eax, eax
0x180027b9a  jz      loc_180027A5F
0x180027ba0  xorps   xmm0, xmm0
0x180027ba3  lea     rcx, ModuleName; "mpunits.dll"
0x180027baa  movups  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027bae  mov     esi, 1
0x180027bb3  call    cs:__imp_GetModuleHandleA
0x180027bb9  mov     rcx, rax
0x180027bbc  mov     edx, 7E2h
0x180027bc1  call    _Intlstr_GetString_LoadString
0x180027bc6  mov     qword ptr [rbp+4Fh+EventDescriptor.Id], rax
0x180027bca  lea     r9, [rbp+4Fh+EventDescriptor]
0x180027bce  mov     byte ptr [rbp+4Fh+EventDescriptor.Keyword], r15b
0x180027bd2  lea     r8d, [rsi+1Ch]
0x180027bd6  movaps  xmm0, xmmword ptr [rbp+4Fh+EventDescriptor.Id]
0x180027bda  lea     rdx, aBinarylogger; "BinaryLogger"
0x180027be1  mov     [rsp+0E0h+var_B8], r15; __int64
0x180027be6  lea     ecx, [rsi+12h]; int
0x180027be9  movdqa  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027bee  mov     [rsp+0E0h+var_C0], r15; __int64
0x180027bf3  call    MI_ReportErrorDetails_ForCustomError
0x180027bf8  jmp     loc_180027B19
0x180027bfd  mov     rax, [rcx]
0x180027c00  xor     r15d, r15d
0x180027c03  test    rax, rax
0x180027c06  jz      short loc_180027C19
0x180027c08  mov     rax, [rax+68h]
0x180027c0c  lea     rdx, [rbp+4Fh+var_A8]
0x180027c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c15  mov     esi, eax
0x180027c17  jmp     short loc_180027C1E
0x180027c19  mov     esi, 4
0x180027c1e  test    esi, esi
0x180027c20  jnz     loc_180027B22
0x180027c26  mov     r8, [rbp+4Fh+var_A8]
0x180027c2a  lea     rax, [rbp+4Fh+MaxCharCount]
0x180027c2e  mov     rcx, rbx
0x180027c31  mov     [rsp+0E0h+var_C0], rax
0x180027c36  call    SerializeClassToBinary
0x180027c3b  mov     esi, eax
0x180027c3d  cmp     eax, 1Bh
0x180027c40  jnz     loc_180027CDA
0x180027c46  mov     edx, [rbp+4Fh+MaxCharCount]
0x180027c49  cmp     edx, 7FFFFFFFh
0x180027c4f  jbe     short loc_180027CB1
0x180027c51  lea     esi, [rax-1Ah]
0x180027c54  call    trace_BinLogWriter_BufferNeededTooLarge
0x180027c59  xorps   xmm0, xmm0
0x180027c5c  lea     rcx, ModuleName; "mpunits.dll"
0x180027c63  movups  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027c67  call    cs:__imp_GetModuleHandleA
0x180027c6d  mov     rcx, rax
0x180027c70  mov     edx, 7E0h
0x180027c75  call    _Intlstr_GetString_LoadString
0x180027c7a  lea     r8d, [rsi+1Ch]
0x180027c7e  mov     byte ptr [rbp+4Fh+EventDescriptor.Keyword], r15b
0x180027c82  lea     ecx, [rsi+14h]; int
0x180027c85  mov     qword ptr [rbp+4Fh+EventDescriptor.Id], rax
0x180027c89  lea     rdx, aBinarylogger; "BinaryLogger"
0x180027c90  movaps  xmm0, xmmword ptr [rbp+4Fh+EventDescriptor.Id]
0x180027c94  lea     r9, [rbp+4Fh+EventDescriptor]
0x180027c98  mov     [rsp+0E0h+var_B8], r15; __int64
0x180027c9d  movdqa  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027ca2  mov     [rsp+0E0h+var_C0], r15; __int64
0x180027ca7  call    MI_ReportErrorDetails_ForCustomError
0x180027cac  jmp     loc_180027B22
0x180027cb1  mov     rcx, rbx
0x180027cb4  call    AllocateBuffer
0x180027cb9  mov     esi, eax
0x180027cbb  test    eax, eax
0x180027cbd  jnz     loc_180027B22
0x180027cc3  mov     r8, [rbp+4Fh+var_A8]
0x180027cc7  lea     rax, [rbp+4Fh+MaxCharCount]
0x180027ccb  mov     rcx, rbx
0x180027cce  mov     [rsp+0E0h+var_C0], rax
0x180027cd3  call    SerializeClassToBinary
0x180027cd8  mov     esi, eax
0x180027cda  test    esi, esi
0x180027cdc  jz      short loc_180027D3F
0x180027cde  mov     rdx, [r14+8]
0x180027ce2  lea     rcx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180027ce6  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 2778h
0x180027ced  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], 4
0x180027cf4  mov     [rbp+4Fh+EventDescriptor.Keyword], 1
0x180027cfc  call    Etw_Trace1_LPCWSTR
0x180027d01  mov     rbx, [r14+8]
0x180027d05  lea     rcx, ModuleName; "mpunits.dll"
0x180027d0c  xorps   xmm0, xmm0
0x180027d0f  movups  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027d13  call    cs:__imp_GetModuleHandleA
0x180027d19  mov     r9d, esi
0x180027d1c  mov     r8, rbx
0x180027d1f  mov     rcx, rax
0x180027d22  mov     edx, 7DFh
0x180027d27  call    _Intlstr_FormatString_FormatMessage
0x180027d2c  mov     r8d, 17h
0x180027d32  mov     byte ptr [rbp+4Fh+EventDescriptor.Keyword], 1
0x180027d36  lea     ecx, [r8-8]
0x180027d3a  jmp     loc_180027C85
0x180027d3f  cmp     [rbx+40h], r15
0x180027d43  jz      loc_180027DEA
0x180027d49  mov     edx, [rbx]
0x180027d4b  lea     rcx, [rbp+4Fh+var_98]
0x180027d4f  mov     r9d, 14h
0x180027d55  mov     dword ptr [rbp+4Fh+Buf], r15d
0x180027d59  mov     dword ptr [rsp+0E0h+var_C0], 0C8h
0x180027d61  lea     r8d, [r9-10h]
0x180027d65  call    Logger_LockPartOfFile
0x180027d6a  test    eax, eax
0x180027d6c  jz      short loc_180027DCE
0x180027d6e  xorps   xmm0, xmm0
0x180027d71  lea     rcx, ModuleName; "mpunits.dll"
0x180027d78  movups  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027d7c  call    cs:__imp_GetModuleHandleA
0x180027d82  mov     rcx, rax
0x180027d85  mov     edx, 7E1h
0x180027d8a  call    _Intlstr_GetString_LoadString
0x180027d8f  mov     qword ptr [rbp+4Fh+EventDescriptor.Id], rax
0x180027d93  lea     r9, [rbp+4Fh+EventDescriptor]
0x180027d97  mov     byte ptr [rbp+4Fh+EventDescriptor.Keyword], r15b
0x180027d9b  lea     rdx, aBinarylogger; "BinaryLogger"
0x180027da2  movaps  xmm0, xmmword ptr [rbp+4Fh+EventDescriptor.Id]
0x180027da6  mov     r8d, 17h
0x180027dac  mov     [rsp+0E0h+var_B8], r15; __int64
0x180027db1  movdqa  xmmword ptr [rbp+4Fh+EventDescriptor.Id], xmm0
0x180027db6  mov     [rsp+0E0h+var_C0], r15; __int64
0x180027dbb  lea     ecx, [r8-6]; int
0x180027dbf  call    MI_ReportErrorDetails_ForCustomError
0x180027dc4  mov     esi, 1
0x180027dc9  jmp     loc_180027B22
0x180027dce  mov     ecx, [rbx]; FileHandle
0x180027dd0  lea     rdx, [rbp+4Fh+Buf]; Buf
0x180027dd4  mov     r8d, 4; MaxCharCount
0x180027dda  call    cs:__imp__write
0x180027de0  cmp     eax, 4
0x180027de3  jnz     short loc_180027D6E
0x180027de5  add     qword ptr [rbx+8], 4
0x180027dea  mov     r8d, [rbp+4Fh+MaxCharCount]; MaxCharCount
0x180027dee  mov     rdx, [rbx+30h]; Buf
0x180027df2  mov     ecx, [rbx]; FileHandle
0x180027df4  call    cs:__imp__write
0x180027dfa  movsxd  rcx, eax
0x180027dfd  mov     eax, [rbp+4Fh+MaxCharCount]
0x180027e00  cmp     rcx, rax
0x180027e03  jnz     loc_180027D6E
0x180027e09  inc     dword ptr [rbx+14h]
0x180027e0c  add     rax, 4
0x180027e10  add     [rbx+8], rax
0x180027e14  test    rdi, rdi
0x180027e17  jz      short loc_180027E48
0x180027e19  mov     rcx, [rbp+4Fh+var_A8]
0x180027e1d  test    rcx, rcx
0x180027e20  jz      short loc_180027E33
0x180027e22  mov     rax, [rcx]
0x180027e25  test    rax, rax
0x180027e28  jz      short loc_180027E33
0x180027e2a  mov     rax, [rax+60h]
0x180027e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e33  mov     dword ptr [rdi+18h], 1
0x180027e3a  lea     rcx, [rbp+4Fh+var_98]
  ... truncated ...
```
