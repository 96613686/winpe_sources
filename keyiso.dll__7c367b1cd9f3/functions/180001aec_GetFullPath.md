# GetFullPath

- ea: `0x180001aec`
- end: `0x180001c0e`
- name: `GetFullPath`
- size: `290`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001d14`

## callees

- `0x180001aec`
- `0x180002d20`
- `0x180003cf0`
- `0x180004470`
- `0x180006280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001bba`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001b01`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001b88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001b01`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180001b88`

## string_xrefs

- `0x180001b30`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180001ba5`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180001be1`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetFullPath(LPCWSTR lpSrc, WCHAR **a2)
{
  DWORD v4; // eax
  DWORD v5; // ebx
  char v6; // al
  signed int v7; // eax
  unsigned int v8; // ebx
  WCHAR *v10; // rax
  WCHAR *v11; // rdi
  DWORD LastError; // eax
  signed int v13; // eax

  v4 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  v5 = v4;
  if ( v4 )
  {
    v10 = (WCHAR *)MSCryptAlloc(2LL * v4);
    v11 = v10;
    if ( v10 )
    {
      if ( ExpandEnvironmentStringsW(lpSrc, v10, v5) )
      {
        v8 = 0;
        *a2 = v11;
      }
      else
      {
        LastError = GetLastError();
        DebugTraceError(
          LastError,
          "GetLastError()",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
          59);
        v13 = GetLastError();
        v8 = v13;
        if ( v13 > 0 )
          v8 = (unsigned __int16)v13 | 0x80070000;
        MSCryptFree(v11);
      }
    }
    else
    {
      v8 = -2146893810;
      DebugTraceError(2148073486LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", 52);
    }
  }
  else
  {
    v6 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        (unsigned int)"GetLastError()",
        v6,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
        43);
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
  }
  return v8;
}

```

## disassembly

```asm
0x180001aec  push    rbx
0x180001aee  push    rsi
0x180001aef  push    rdi
0x180001af0  push    r14
0x180001af2  sub     rsp, 48h
0x180001af6  mov     r14, rdx
0x180001af9  xor     r8d, r8d; nSize
0x180001afc  xor     edx, edx; lpDst
0x180001afe  mov     rsi, rcx
0x180001b01  call    cs:__imp_ExpandEnvironmentStringsW
0x180001b07  mov     ebx, eax
0x180001b09  test    eax, eax
0x180001b0b  jnz     short loc_180001B6C
0x180001b0d  call    cs:__imp_GetLastError
0x180001b13  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b1a  lea     rdx, WPP_GLOBAL_Control
0x180001b21  cmp     rcx, rdx
0x180001b24  jz      short loc_180001B54
0x180001b26  test    byte ptr [rcx+1Ch], 1
0x180001b2a  jz      short loc_180001B54
0x180001b2c  mov     rcx, [rcx+10h]
0x180001b30  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001b37  mov     [rsp+68h+var_38], 2Bh ; '+'
0x180001b3f  lea     r9, aGetlasterror; "GetLastError()"
0x180001b46  mov     [rsp+68h+var_40], r8
0x180001b4b  mov     [rsp+68h+var_48], eax
0x180001b4f  call    WPP_SF_sDsd
0x180001b54  call    cs:__imp_GetLastError
0x180001b5a  mov     ebx, eax
0x180001b5c  test    eax, eax
0x180001b5e  jg      short loc_180001BD0
0x180001b60  mov     eax, ebx
0x180001b62  add     rsp, 48h
0x180001b66  pop     r14
0x180001b68  pop     rdi
0x180001b69  pop     rsi
0x180001b6a  pop     rbx
0x180001b6b  retn
0x180001b6c  mov     rcx, rbx
0x180001b6f  add     rcx, rcx
0x180001b72  call    MSCryptAlloc
0x180001b77  mov     rdi, rax
0x180001b7a  test    rax, rax
0x180001b7d  jz      short loc_180001BDB
0x180001b7f  mov     r8d, ebx; nSize
0x180001b82  mov     rdx, rax; lpDst
0x180001b85  mov     rcx, rsi; lpSrc
0x180001b88  call    cs:__imp_ExpandEnvironmentStringsW
0x180001b8e  test    eax, eax
0x180001b90  jz      short loc_180001B99
0x180001b92  xor     ebx, ebx
0x180001b94  mov     [r14], rdi
0x180001b97  jmp     short loc_180001B60
0x180001b99  call    cs:__imp_GetLastError
0x180001b9f  mov     r9d, 3Bh ; ';'
0x180001ba5  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001bac  mov     ecx, eax
0x180001bae  lea     rdx, aGetlasterror; "GetLastError()"
0x180001bb5  call    DebugTraceError
0x180001bba  call    cs:__imp_GetLastError
0x180001bc0  mov     ebx, eax
0x180001bc2  test    eax, eax
0x180001bc4  jg      short loc_180001C03
0x180001bc6  mov     rcx, rdi
0x180001bc9  call    MSCryptFree
0x180001bce  jmp     short loc_180001B60
0x180001bd0  movzx   ebx, ax
0x180001bd3  or      ebx, 80070000h
0x180001bd9  jmp     short loc_180001B60
0x180001bdb  mov     r9d, 34h ; '4'
0x180001be1  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001be8  lea     rdx, aStatus_0; "status"
0x180001bef  mov     ecx, 8009000Eh
0x180001bf4  mov     ebx, 8009000Eh
0x180001bf9  call    DebugTraceError
0x180001bfe  jmp     loc_180001B60
0x180001c03  movzx   ebx, ax
0x180001c06  or      ebx, 80070000h
0x180001c0c  jmp     short loc_180001BC6
```
