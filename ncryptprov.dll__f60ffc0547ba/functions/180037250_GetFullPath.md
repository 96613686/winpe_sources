# GetFullPath

- ea: `0x180037250`
- end: `0x18003736f`
- name: `GetFullPath`
- size: `287`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800613cc`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180037250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003729e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037277`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003729e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037311`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037338`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037265`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037301`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037265`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180037301`

## string_xrefs

- `0x180037289`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x1800372de`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180037323`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetFullPath(LPCWSTR lpSrc, WCHAR **a2)
{
  DWORD v4; // eax
  DWORD v5; // ebx
  DWORD v6; // eax
  signed int v7; // eax
  unsigned int v8; // ebx
  WCHAR *v9; // rax
  WCHAR *v10; // rdi
  DWORD LastError; // eax
  signed int v12; // eax

  v4 = ExpandEnvironmentStringsW(lpSrc, 0, 0);
  v5 = v4;
  if ( v4 )
  {
    v9 = (WCHAR *)SafeAllocaAllocateFromHeap(2LL * v4);
    v10 = v9;
    if ( v9 )
    {
      if ( ExpandEnvironmentStringsW(lpSrc, v9, v5) )
      {
        v8 = 0;
        *a2 = v10;
      }
      else
      {
        LastError = GetLastError();
        DebugTraceError(
          LastError,
          "GetLastError()",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
          59);
        v12 = GetLastError();
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        MSCryptFree(v10);
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
    DebugTraceError(v6, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", 43);
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
0x180037250  push    rbx
0x180037252  push    rsi
0x180037253  push    rdi
0x180037254  push    r14
0x180037256  sub     rsp, 28h
0x18003725a  mov     r14, rdx
0x18003725d  xor     r8d, r8d; nSize
0x180037260  xor     edx, edx; lpDst
0x180037262  mov     rsi, rcx
0x180037265  call    cs:__imp_ExpandEnvironmentStringsW
0x18003726c  nop     dword ptr [rax+rax+00h]
0x180037271  mov     ebx, eax
0x180037273  test    eax, eax
0x180037275  jnz     short loc_1800372C2
0x180037277  call    cs:__imp_GetLastError
0x18003727e  nop     dword ptr [rax+rax+00h]
0x180037283  mov     r9d, 2Bh ; '+'
0x180037289  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180037290  mov     ecx, eax
0x180037292  lea     rdx, aGetlasterror; "GetLastError()"
0x180037299  call    DebugTraceError
0x18003729e  call    cs:__imp_GetLastError
0x1800372a5  nop     dword ptr [rax+rax+00h]
0x1800372aa  mov     ebx, eax
0x1800372ac  test    eax, eax
0x1800372ae  jle     loc_180037362
0x1800372b4  movzx   ebx, ax
0x1800372b7  or      ebx, 80070000h
0x1800372bd  jmp     loc_180037362
0x1800372c2  mov     rcx, rbx
0x1800372c5  add     rcx, rcx
0x1800372c8  call    SafeAllocaAllocateFromHeap
0x1800372cd  mov     rdi, rax
0x1800372d0  test    rax, rax
0x1800372d3  jnz     short loc_1800372F8
0x1800372d5  lea     r9d, [rax+34h]
0x1800372d9  mov     ecx, 8009000Eh
0x1800372de  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800372e5  mov     ebx, 8009000Eh
0x1800372ea  lea     rdx, aStatus_0; "status"
0x1800372f1  call    DebugTraceError
0x1800372f6  jmp     short loc_180037362
0x1800372f8  mov     r8d, ebx; nSize
0x1800372fb  mov     rdx, rdi; lpDst
0x1800372fe  mov     rcx, rsi; lpSrc
0x180037301  call    cs:__imp_ExpandEnvironmentStringsW
0x180037308  nop     dword ptr [rax+rax+00h]
0x18003730d  test    eax, eax
0x18003730f  jnz     short loc_18003735D
0x180037311  call    cs:__imp_GetLastError
0x180037318  nop     dword ptr [rax+rax+00h]
0x18003731d  mov     r9d, 3Bh ; ';'
0x180037323  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003732a  mov     ecx, eax
0x18003732c  lea     rdx, aGetlasterror; "GetLastError()"
0x180037333  call    DebugTraceError
0x180037338  call    cs:__imp_GetLastError
0x18003733f  nop     dword ptr [rax+rax+00h]
0x180037344  mov     ebx, eax
0x180037346  test    eax, eax
0x180037348  jle     short loc_180037353
0x18003734a  movzx   ebx, ax
0x18003734d  or      ebx, 80070000h
0x180037353  mov     rcx, rdi
0x180037356  call    MSCryptFree
0x18003735b  jmp     short loc_180037362
0x18003735d  xor     ebx, ebx
0x18003735f  mov     [r14], rdi
0x180037362  mov     eax, ebx
0x180037364  add     rsp, 28h
0x180037368  pop     r14
0x18003736a  pop     rdi
0x18003736b  pop     rsi
0x18003736c  pop     rbx
0x18003736d  retn
```
