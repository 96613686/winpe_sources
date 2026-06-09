# BinaryLogWriter_Core_WriteInstance

- ea: `0x180027680`
- end: `0x1800279aa`
- name: `BinaryLogWriter_Core_WriteInstance`
- size: `810`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026130`
- `0x180027f20`

## callees

- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x1800089b0`
- `0x18000aee8`
- `0x18000afdc`
- `0x18000b084`
- `0x180026660`
- `0x1800266f0`
- `0x180027634`
- `0x180027680`
- `0x180027f84`
- `0x18002a4bc`
- `0x180044880`

## import_xrefs

- `msvcrt!_write` at `0x1800278e8`
- `msvcrt!_write` at `0x1800278e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027724`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800277ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027860`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002790c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027724`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800277ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180027860`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18002790c`

## string_xrefs

- `0x180027716`: `mpunits.dll`
- `0x1800277a2`: `mpunits.dll`
- `0x180027855`: `mpunits.dll`
- `0x1800278fc`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall BinaryLogWriter_Core_WriteInstance(unsigned int *a1, __int64 a2, __int64 a3, int a4)
{
  const wchar_t *v4; // r14
  unsigned int Buffer; // edi
  HMODULE v8; // rax
  int v9; // edx
  int v10; // r9d
  HMODULE ModuleHandleA; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  HMODULE v15; // rax
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  HMODULE v19; // rax
  __int64 v20; // rax
  unsigned int MaxCharCount[4]; // [rsp+30h] [rbp-49h] BYREF
  __int128 v23; // [rsp+40h] [rbp-39h]
  __int128 v24; // [rsp+50h] [rbp-29h] BYREF
  __int64 v25; // [rsp+60h] [rbp-19h]
  _OWORD v26[3]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v27; // [rsp+98h] [rbp+1Fh]

  v4 = L"NULL ClassDecl";
  MaxCharCount[0] = 0;
  v25 = 0;
  v24 = 0;
  if ( *((_QWORD *)a1 + 6) || (Buffer = AllocateBuffer(a1, 4000)) == 0 )
  {
    Buffer = SerializeInstanceToBinary((_DWORD)a1, a2, a2, a4, (__int64)MaxCharCount);
    if ( Buffer == 27 )
    {
      if ( !MaxCharCount[0] )
      {
LABEL_10:
        v23 = 0;
        ModuleHandleA = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&v23 = Intlstr_FormatString_FormatMessage(ModuleHandleA, 2014, Buffer);
        BYTE8(v23) = 1;
        MI_ReportErrorDetails_ForCustomError(12, (int)L"BinaryLogger", 0, 0);
        v12 = *(_QWORD *)(a2 + 8);
        if ( v12 )
          v13 = *(const wchar_t **)(v12 + 8);
        else
          v13 = L"NULL ClassDecl";
        trace_BinLogWriter_FailedToSerializInstance(v13);
        goto LABEL_21;
      }
      if ( MaxCharCount[0] > 0x7FFFFFFF )
      {
        v23 = 0;
        Buffer = 1;
        v8 = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&v23 = Intlstr_GetString_LoadString(v8, 2019);
        BYTE8(v23) = 0;
        MI_ReportErrorDetails_ForCustomError(21, (int)L"BinaryLogger", 0, 0);
        trace_BinLogWriter_BufferNeededTooLarge();
        goto LABEL_21;
      }
      Buffer = AllocateBuffer(a1, MaxCharCount[0]);
      if ( Buffer )
        goto LABEL_21;
      Buffer = SerializeInstanceToBinary((_DWORD)a1, v9, a2, v10, (__int64)MaxCharCount);
    }
    if ( Buffer )
      goto LABEL_10;
    if ( !*((_QWORD *)a1 + 8) )
      goto LABEL_19;
    v14 = *a1;
    v27 = 0;
    memset(v26, 0, sizeof(v26));
    if ( (unsigned int)Logger_LockPartOfFile(&v24, v14, 4) )
    {
      v23 = 0;
      v15 = GetModuleHandleA("mpunits.dll");
      *(_QWORD *)&v23 = Intlstr_GetString_LoadString(v15, 2017);
      BYTE8(v23) = 0;
      MI_ReportErrorDetails_ForCustomError(17, (int)L"BinaryLogger", 0, 0);
      Buffer = 1;
      goto LABEL_21;
    }
    Buffer = Item_FromInstance(a2, v26);
    if ( !Buffer )
    {
      Buffer = DelegateInvoke1_2(*((_QWORD *)a1 + 8), v26, v16, a1, 200);
      if ( !Buffer )
      {
LABEL_19:
        v17 = _write(*a1, *((const void **)a1 + 6), MaxCharCount[0]);
        v18 = MaxCharCount[0];
        if ( v17 == MaxCharCount[0] )
        {
          ++a1[4];
          *((_QWORD *)a1 + 1) += v18 + 4;
          return Logger_UnlockPartOfFile(&v24);
        }
        v23 = 0;
        Buffer = 1;
        v19 = GetModuleHandleA("mpunits.dll");
        *(_QWORD *)&v23 = Intlstr_GetString_LoadString(v19, 2017);
        BYTE8(v23) = 0;
        MI_ReportErrorDetails_ForCustomError(14, (int)L"BinaryLogger", 0, 0);
      }
    }
  }
LABEL_21:
  Logger_UnlockPartOfFile(&v24);
  v20 = *(_QWORD *)(a2 + 8);
  if ( v20 )
    v4 = *(const wchar_t **)(v20 + 8);
  trace_BinLogWriter_FailedToWriteInstance(v4);
  return Buffer;
}

```

## disassembly

```asm
0x180027680  mov     [rsp-8+arg_10], rbx
0x180027685  push    rbp
0x180027686  push    rsi
0x180027687  push    rdi
0x180027688  push    r14
0x18002768a  push    r15
0x18002768c  lea     rbp, [rsp-37h]
0x180027691  sub     rsp, 0B0h
0x180027698  mov     rax, cs:__security_cookie
0x18002769f  xor     rax, rsp
0x1800276a2  mov     [rbp+57h+var_30], rax
0x1800276a6  xor     r15d, r15d
0x1800276a9  lea     r14, aNullClassdecl; "NULL ClassDecl"
0x1800276b0  xor     eax, eax
0x1800276b2  mov     [rbp+57h+MaxCharCount], r15d
0x1800276b6  xorps   xmm0, xmm0
0x1800276b9  mov     rsi, rdx
0x1800276bc  mov     rbx, rcx
0x1800276bf  mov     [rbp+57h+var_70], rax
0x1800276c3  movups  [rbp+57h+var_80], xmm0
0x1800276c7  cmp     [rcx+30h], r15
0x1800276cb  jnz     short loc_1800276E1
0x1800276cd  mov     edx, 0FA0h
0x1800276d2  call    AllocateBuffer
0x1800276d7  mov     edi, eax
0x1800276d9  test    eax, eax
0x1800276db  jnz     loc_180027951
0x1800276e1  lea     rax, [rbp+57h+MaxCharCount]
0x1800276e5  mov     r8, rsi
0x1800276e8  mov     rcx, rbx
0x1800276eb  mov     [rsp+0D0h+var_B0], rax
0x1800276f0  call    SerializeInstanceToBinary
0x1800276f5  mov     edi, eax
0x1800276f7  cmp     eax, 1Bh
0x1800276fa  jnz     loc_18002779B
0x180027700  mov     edx, [rbp+57h+MaxCharCount]
0x180027703  test    edx, edx
0x180027705  jz      loc_18002779F
0x18002770b  cmp     edx, 7FFFFFFFh
0x180027711  jbe     short loc_180027773
0x180027713  xorps   xmm0, xmm0
0x180027716  lea     rcx, ModuleName; "mpunits.dll"
0x18002771d  movups  [rbp+57h+var_90], xmm0
0x180027721  lea     edi, [rax-1Ah]
0x180027724  call    cs:__imp_GetModuleHandleA
0x18002772a  mov     rcx, rax
0x18002772d  mov     edx, 7E3h
0x180027732  call    _Intlstr_GetString_LoadString
0x180027737  mov     qword ptr [rbp+57h+var_90], rax
0x18002773b  lea     r9, [rbp+57h+var_90]
0x18002773f  mov     byte ptr [rbp+57h+var_90+8], r15b
0x180027743  lea     r8d, [rdi+1Ch]
0x180027747  movaps  xmm0, [rbp+57h+var_90]
0x18002774b  lea     rdx, aBinarylogger; "BinaryLogger"
0x180027752  mov     [rsp+0D0h+var_A8], r15; __int64
0x180027757  lea     ecx, [rdi+14h]; int
0x18002775a  movdqa  [rbp+57h+var_90], xmm0
0x18002775f  mov     [rsp+0D0h+var_B0], r15; __int64
0x180027764  call    MI_ReportErrorDetails_ForCustomError
0x180027769  call    trace_BinLogWriter_BufferNeededTooLarge
0x18002776e  jmp     loc_180027951
0x180027773  mov     rcx, rbx
0x180027776  call    AllocateBuffer
0x18002777b  mov     edi, eax
0x18002777d  test    eax, eax
0x18002777f  jnz     loc_180027951
0x180027785  lea     rax, [rbp+57h+MaxCharCount]
0x180027789  mov     r8, rsi
0x18002778c  mov     rcx, rbx
0x18002778f  mov     [rsp+0D0h+var_B0], rax
0x180027794  call    SerializeInstanceToBinary
0x180027799  mov     edi, eax
0x18002779b  test    edi, edi
0x18002779d  jz      short loc_180027814
0x18002779f  xorps   xmm0, xmm0
0x1800277a2  lea     rcx, ModuleName; "mpunits.dll"
0x1800277a9  movups  [rbp+57h+var_90], xmm0
0x1800277ad  call    cs:__imp_GetModuleHandleA
0x1800277b3  mov     r8d, edi
0x1800277b6  mov     edx, 7DEh
0x1800277bb  mov     rcx, rax
0x1800277be  call    _Intlstr_FormatString_FormatMessage
0x1800277c3  mov     qword ptr [rbp+57h+var_90], rax
0x1800277c7  lea     r9, [rbp+57h+var_90]
0x1800277cb  mov     byte ptr [rbp+57h+var_90+8], 1
0x1800277cf  lea     rdx, aBinarylogger; "BinaryLogger"
0x1800277d6  movaps  xmm0, [rbp+57h+var_90]
0x1800277da  mov     r8d, 17h
0x1800277e0  mov     [rsp+0D0h+var_A8], r15; __int64
0x1800277e5  movdqa  [rbp+57h+var_90], xmm0
0x1800277ea  mov     [rsp+0D0h+var_B0], r15; __int64
0x1800277ef  lea     ecx, [r8-0Bh]; int
0x1800277f3  call    MI_ReportErrorDetails_ForCustomError
0x1800277f8  mov     rcx, [rsi+8]
0x1800277fc  test    rcx, rcx
0x1800277ff  jnz     short loc_180027806
0x180027801  mov     rcx, r14
0x180027804  jmp     short loc_18002780A
0x180027806  mov     rcx, [rcx+8]
0x18002780a  call    trace_BinLogWriter_FailedToSerializInstance
0x18002780f  jmp     loc_180027951
0x180027814  cmp     [rbx+40h], r15
0x180027818  jz      loc_1800278DE
0x18002781e  mov     edx, [rbx]
0x180027820  lea     rcx, [rbp+57h+var_80]
0x180027824  xor     eax, eax
0x180027826  mov     dword ptr [rsp+0D0h+var_B0], 0C8h
0x18002782e  xorps   xmm0, xmm0
0x180027831  mov     [rbp+57h+var_38], rax
0x180027835  movups  [rbp+57h+var_68], xmm0
0x180027839  lea     r9d, [rax+14h]
0x18002783d  lea     r8d, [rax+4]
0x180027841  movups  [rbp+57h+var_58], xmm0
0x180027845  movups  [rbp+57h+var_48], xmm0
0x180027849  call    Logger_LockPartOfFile
0x18002784e  test    eax, eax
0x180027850  jz      short loc_1800278B2
0x180027852  xorps   xmm0, xmm0
0x180027855  lea     rcx, ModuleName; "mpunits.dll"
0x18002785c  movups  [rbp+57h+var_90], xmm0
0x180027860  call    cs:__imp_GetModuleHandleA
0x180027866  mov     rcx, rax
0x180027869  mov     edx, 7E1h
0x18002786e  call    _Intlstr_GetString_LoadString
0x180027873  mov     qword ptr [rbp+57h+var_90], rax
0x180027877  lea     r9, [rbp+57h+var_90]
0x18002787b  mov     byte ptr [rbp+57h+var_90+8], r15b
0x18002787f  lea     rdx, aBinarylogger; "BinaryLogger"
0x180027886  movaps  xmm0, [rbp+57h+var_90]
0x18002788a  mov     r8d, 17h
0x180027890  mov     [rsp+0D0h+var_A8], r15; __int64
0x180027895  movdqa  [rbp+57h+var_90], xmm0
0x18002789a  mov     [rsp+0D0h+var_B0], r15; __int64
0x18002789f  lea     ecx, [r8-6]; int
0x1800278a3  call    MI_ReportErrorDetails_ForCustomError
0x1800278a8  mov     edi, 1
0x1800278ad  jmp     loc_180027951
0x1800278b2  lea     rdx, [rbp+57h+var_68]
0x1800278b6  mov     rcx, rsi
0x1800278b9  call    Item_FromInstance
0x1800278be  mov     edi, eax
0x1800278c0  test    eax, eax
0x1800278c2  jnz     loc_180027951
0x1800278c8  mov     rcx, [rbx+40h]
0x1800278cc  lea     rdx, [rbp+57h+var_68]
0x1800278d0  mov     r9, rbx
0x1800278d3  call    DelegateInvoke1_2
0x1800278d8  mov     edi, eax
0x1800278da  test    eax, eax
0x1800278dc  jnz     short loc_180027951
0x1800278de  mov     r8d, [rbp+57h+MaxCharCount]; MaxCharCount
0x1800278e2  mov     rdx, [rbx+30h]; Buf
0x1800278e6  mov     ecx, [rbx]; FileHandle
0x1800278e8  call    cs:__imp__write
0x1800278ee  movsxd  rcx, eax
0x1800278f1  mov     eax, [rbp+57h+MaxCharCount]
0x1800278f4  cmp     rcx, rax
0x1800278f7  jz      short loc_180027973
0x1800278f9  xorps   xmm0, xmm0
0x1800278fc  lea     rcx, ModuleName; "mpunits.dll"
0x180027903  movups  [rbp+57h+var_90], xmm0
0x180027907  mov     edi, 1
0x18002790c  call    cs:__imp_GetModuleHandleA
0x180027912  mov     rcx, rax
0x180027915  mov     edx, 7E1h
0x18002791a  call    _Intlstr_GetString_LoadString
0x18002791f  mov     qword ptr [rbp+57h+var_90], rax
0x180027923  lea     r9, [rbp+57h+var_90]
0x180027927  mov     byte ptr [rbp+57h+var_90+8], r15b
0x18002792b  lea     r8d, [rdi+16h]
0x18002792f  movaps  xmm0, [rbp+57h+var_90]
0x180027933  lea     rdx, aBinarylogger; "BinaryLogger"
0x18002793a  mov     [rsp+0D0h+var_A8], r15; __int64
0x18002793f  lea     ecx, [rdi+0Dh]; int
0x180027942  movdqa  [rbp+57h+var_90], xmm0
0x180027947  mov     [rsp+0D0h+var_B0], r15; __int64
0x18002794c  call    MI_ReportErrorDetails_ForCustomError
0x180027951  lea     rcx, [rbp+57h+var_80]
0x180027955  call    Logger_UnlockPartOfFile
0x18002795a  mov     rax, [rsi+8]
0x18002795e  test    rax, rax
0x180027961  jz      short loc_180027967
0x180027963  mov     r14, [rax+8]
0x180027967  mov     rcx, r14
0x18002796a  call    trace_BinLogWriter_FailedToWriteInstance
0x18002796f  mov     eax, edi
0x180027971  jmp     short loc_180027987
0x180027973  inc     dword ptr [rbx+10h]
0x180027976  lea     rcx, [rbp+57h+var_80]
0x18002797a  add     rax, 4
0x18002797e  add     [rbx+8], rax
0x180027982  call    Logger_UnlockPartOfFile
0x180027987  mov     rcx, [rbp+57h+var_30]
0x18002798b  xor     rcx, rsp; StackCookie
0x18002798e  call    __security_check_cookie
0x180027993  mov     rbx, [rsp+0D0h+arg_10]
0x18002799b  add     rsp, 0B0h
0x1800279a2  pop     r15
0x1800279a4  pop     r14
0x1800279a6  pop     rdi
0x1800279a7  pop     rsi
0x1800279a8  pop     rbp
0x1800279a9  retn
```
