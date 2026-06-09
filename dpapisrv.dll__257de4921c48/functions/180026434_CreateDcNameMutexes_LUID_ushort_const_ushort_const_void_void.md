# CreateDcNameMutexes(_LUID *,ushort const *,ushort const *,void * *,void * *)

- ea: `0x180026434`
- end: `0x180026586`
- name: `?CreateDcNameMutexes@@YAKPEAU_LUID@@PEBG1PEAPEAX2@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct _LUID *, const unsigned __int16 *, const unsigned __int16 *, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002677c`

## callees

- `0x180007f10`
- `0x18000c1b4`
- `0x18001d810`
- `0x180026434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800264ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002650b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800264ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002650b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002651c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800264c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002651c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002654d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002654d`

## string_xrefs

- `0x18002648a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x180026530`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall CreateDcNameMutexes(
        struct _LUID *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4,
        void **a5)
{
  HANDLE MutexW; // rdi
  DWORD DcMutexName; // eax
  DWORD v10; // ebx
  __int64 v11; // r9
  HANDLE v12; // rax
  DWORD LastError; // eax
  __int64 v14; // r9
  WCHAR Name[72]; // [rsp+20h] [rbp-168h] BYREF
  WCHAR v17[72]; // [rsp+B0h] [rbp-D8h] BYREF

  MutexW = 0;
  *a4 = 0;
  *a5 = 0;
  if ( a2 )
  {
    DcMutexName = GetDcMutexName(a1, a2, (unsigned int)a3, Name);
    v10 = DcMutexName;
    if ( DcMutexName )
    {
      v11 = 2493;
LABEL_4:
      DebugTraceError(DcMutexName, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v11);
      return v10;
    }
    MutexW = CreateMutexW(0, 0, Name);
    if ( !MutexW )
    {
      DcMutexName = GetLastError();
      v10 = DcMutexName;
      v11 = 2504;
      goto LABEL_4;
    }
  }
  v12 = 0;
  if ( !a3 )
    goto LABEL_14;
  LastError = GetDcMutexName(a1, a3, (unsigned int)a3, v17);
  v10 = LastError;
  if ( LastError )
  {
    v14 = 2518;
    goto LABEL_12;
  }
  v12 = CreateMutexW(0, 0, v17);
  if ( v12 )
  {
LABEL_14:
    *a4 = MutexW;
    v10 = 0;
    *a5 = v12;
    return v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  v14 = 2529;
LABEL_12:
  DebugTraceError(LastError, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", v14);
  if ( MutexW )
    CloseHandle(MutexW);
  return v10;
}

```

## disassembly

```asm
0x180026434  push    rbx
0x180026436  push    rbp
0x180026437  push    rsi
0x180026438  push    rdi
0x180026439  push    r14
0x18002643b  push    r15
0x18002643d  sub     rsp, 158h
0x180026444  mov     rax, cs:__security_cookie
0x18002644b  xor     rax, rsp
0x18002644e  mov     [rsp+188h+var_48], rax
0x180026456  mov     r15, [rsp+188h+arg_20]
0x18002645e  xor     edi, edi
0x180026460  mov     [r9], rdi
0x180026463  mov     r14, r9
0x180026466  mov     rsi, r8
0x180026469  mov     rbp, rcx
0x18002646c  mov     [r15], rdi
0x18002646f  test    rdx, rdx
0x180026472  jz      short loc_1800264D7
0x180026474  lea     r9, [rsp+188h+Name]; unsigned __int16 *
0x180026479  call    ?GetDcMutexName@@YAKPEAU_LUID@@PEBGKPEAG@Z; GetDcMutexName(_LUID *,ushort const *,ulong,ushort *)
0x18002647e  mov     ebx, eax
0x180026480  test    eax, eax
0x180026482  jz      short loc_1800264A4
0x180026484  mov     r9d, 9BDh
0x18002648a  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026491  mov     ecx, eax
0x180026493  lea     rdx, aDwretval; "dwRetVal"
0x18002649a  call    DebugTraceError
0x18002649f  jmp     loc_180026563
0x1800264a4  lea     r8, [rsp+188h+Name]; lpName
0x1800264a9  xor     edx, edx; bInitialOwner
0x1800264ab  xor     ecx, ecx; lpMutexAttributes
0x1800264ad  call    cs:__imp_CreateMutexW
0x1800264b4  nop     dword ptr [rax+rax+00h]
0x1800264b9  mov     rdi, rax
0x1800264bc  test    rax, rax
0x1800264bf  jnz     short loc_1800264D7
0x1800264c1  call    cs:__imp_GetLastError
0x1800264c8  nop     dword ptr [rax+rax+00h]
0x1800264cd  mov     ebx, eax
0x1800264cf  mov     r9d, 9C8h
0x1800264d5  jmp     short loc_18002648A
0x1800264d7  xor     eax, eax
0x1800264d9  test    rsi, rsi
0x1800264dc  jz      short loc_18002655B
0x1800264de  lea     r9, [rsp+188h+var_D8]; unsigned __int16 *
0x1800264e6  mov     rdx, rsi; unsigned __int16 *
0x1800264e9  mov     rcx, rbp; struct _LUID *
0x1800264ec  call    ?GetDcMutexName@@YAKPEAU_LUID@@PEBGKPEAG@Z; GetDcMutexName(_LUID *,ushort const *,ulong,ushort *)
0x1800264f1  mov     ebx, eax
0x1800264f3  test    eax, eax
0x1800264f5  jz      short loc_1800264FF
0x1800264f7  mov     r9d, 9D6h
0x1800264fd  jmp     short loc_180026530
0x1800264ff  lea     r8, [rsp+188h+var_D8]; lpName
0x180026507  xor     edx, edx; bInitialOwner
0x180026509  xor     ecx, ecx; lpMutexAttributes
0x18002650b  call    cs:__imp_CreateMutexW
0x180026512  nop     dword ptr [rax+rax+00h]
0x180026517  test    rax, rax
0x18002651a  jnz     short loc_18002655B
0x18002651c  call    cs:__imp_GetLastError
0x180026523  nop     dword ptr [rax+rax+00h]
0x180026528  mov     ebx, eax
0x18002652a  mov     r9d, 9E1h
0x180026530  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180026537  mov     ecx, eax
0x180026539  lea     rdx, aDwretval; "dwRetVal"
0x180026540  call    DebugTraceError
0x180026545  test    rdi, rdi
0x180026548  jz      short loc_180026563
0x18002654a  mov     rcx, rdi; hObject
0x18002654d  call    cs:__imp_CloseHandle
0x180026554  nop     dword ptr [rax+rax+00h]
0x180026559  jmp     short loc_180026563
0x18002655b  mov     [r14], rdi
0x18002655e  xor     ebx, ebx
0x180026560  mov     [r15], rax
0x180026563  mov     eax, ebx
0x180026565  mov     rcx, [rsp+188h+var_48]
0x18002656d  xor     rcx, rsp; StackCookie
0x180026570  call    __security_check_cookie
0x180026575  add     rsp, 158h
0x18002657c  pop     r15
0x18002657e  pop     r14
0x180026580  pop     rdi
0x180026581  pop     rsi
0x180026582  pop     rbp
0x180026583  pop     rbx
0x180026584  retn
```
