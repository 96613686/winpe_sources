# OpenLogFile(ushort const *)

- ea: `0x1801a32cc`
- end: `0x1801a33cd`
- name: `?OpenLogFile@@YAXPEBG@Z`
- size: `257`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000d670`

## callees

- `0x18000dfac`
- `0x180021374`
- `0x18002147c`
- `0x1801a32cc`
- `0x1801a855c`
- `0x1801a85e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a3366`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a3366`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a330d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a330d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a3334`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a3350`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a3350`

## string_xrefs

- `0x1801a333d`: `error 0x%x opening %s\n`

## pseudocode

```c
void __fastcall OpenLogFile(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  wchar_t *v4; // rbx
  const unsigned __int16 *v5; // rdx
  time_t Time; // [rsp+58h] [rbp+10h] BYREF

  Time = 0;
  if ( !hFile )
  {
    FileW = CreateFileW(a1, 2u, 0, 0, 4u, 0, 0);
    hFile = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      hFile = 0;
      if ( (unsigned int)spew() )
      {
        LastError = GetLastError();
        _pwprint(0, L"error 0x%x opening %s\n", LastError, a1);
      }
      SetLastError(0);
    }
    else
    {
      SetFilePointer(FileW, 0, 0, 2u);
      time(&Time);
      v4 = wctime(&Time);
      if ( (unsigned int)spew() )
        _pewprint(0x10000000u, 0, L"\n");
      if ( (unsigned int)spew() )
      {
        v5 = L"new session: %s";
        if ( !v4 )
          v5 = L"new session:\n";
        _pwprint(0, v5, v4);
      }
    }
  }
}

```

## disassembly

```asm
0x1801a32cc  mov     rax, rsp
0x1801a32cf  push    rbx
0x1801a32d0  sub     rsp, 40h
0x1801a32d4  cmp     cs:hFile, 0
0x1801a32dc  mov     rbx, rcx
0x1801a32df  mov     qword ptr [rax+10h], 0
0x1801a32e7  jnz     loc_1801A33C7
0x1801a32ed  mov     qword ptr [rax-18h], 0
0x1801a32f5  xor     r9d, r9d; lpSecurityAttributes
0x1801a32f8  mov     dword ptr [rax-20h], 0
0x1801a32ff  xor     r8d, r8d; dwShareMode
0x1801a3302  mov     dword ptr [rax-28h], 4
0x1801a3309  lea     edx, [r9+2]; dwDesiredAccess
0x1801a330d  call    cs:__imp_CreateFileW
0x1801a3313  mov     cs:hFile, rax
0x1801a331a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a331e  jnz     short loc_1801A3358
0x1801a3320  mov     cs:hFile, 0
0x1801a332b  call    ?spew@@YAHXZ; spew(void)
0x1801a3330  test    eax, eax
0x1801a3332  jz      short loc_1801A334E
0x1801a3334  call    cs:__imp_GetLastError
0x1801a333a  mov     r9, rbx
0x1801a333d  lea     rdx, aError0xXOpenin; "error 0x%x opening %s\n"
0x1801a3344  mov     r8d, eax
0x1801a3347  xor     ecx, ecx; struct _PROCESS_ENTRY *
0x1801a3349  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a334e  xor     ecx, ecx; dwErrCode
0x1801a3350  call    cs:__imp_SetLastError
0x1801a3356  jmp     short loc_1801A33C7
0x1801a3358  mov     r9d, 2; dwMoveMethod
0x1801a335e  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801a3361  xor     edx, edx; lDistanceToMove
0x1801a3363  mov     rcx, rax; hFile
0x1801a3366  call    cs:__imp_SetFilePointer
0x1801a336c  lea     rcx, [rsp+48h+Time]; Time
0x1801a3371  call    time
0x1801a3376  lea     rcx, [rsp+48h+Time]; Time
0x1801a337b  call    _wctime
0x1801a3380  mov     rbx, rax
0x1801a3383  call    ?spew@@YAHXZ; spew(void)
0x1801a3388  test    eax, eax
0x1801a338a  jz      short loc_1801A339F
0x1801a338c  lea     r8, asc_1802499F4; "\n"
0x1801a3393  xor     edx, edx; struct _PROCESS_ENTRY *
0x1801a3395  mov     ecx, 10000000h; unsigned int
0x1801a339a  call    ?_pewprint@@YAHKPEAU_PROCESS_ENTRY@@PEBGZZ; _pewprint(ulong,_PROCESS_ENTRY *,ushort const *,...)
0x1801a339f  call    ?spew@@YAHXZ; spew(void)
0x1801a33a4  test    eax, eax
0x1801a33a6  jz      short loc_1801A33C7
0x1801a33a8  test    rbx, rbx
0x1801a33ab  lea     rax, aNewSession; "new session:\n"
0x1801a33b2  lea     rdx, aNewSessionS; "new session: %s"
0x1801a33b9  mov     r8, rbx
0x1801a33bc  cmovz   rdx, rax; unsigned __int16 *
0x1801a33c0  xor     ecx, ecx; struct _PROCESS_ENTRY *
0x1801a33c2  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a33c7  add     rsp, 40h
0x1801a33cb  pop     rbx
0x1801a33cc  retn
```
