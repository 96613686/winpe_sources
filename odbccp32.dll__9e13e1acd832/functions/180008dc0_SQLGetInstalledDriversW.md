# SQLGetInstalledDriversW

- ea: `0x180008dc0`
- end: `0x180008e72`
- name: `SQLGetInstalledDriversW`
- size: `178`
- prototype: `BOOL __stdcall(LPWSTR lpszBuf, WORD cchBufMax, WORD *pcchBufOut)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000eea0`

## callees

- `0x180001740`
- `0x1800017c0`
- `0x180004bac`
- `0x180008dc0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008e57`
- `KERNEL32!LeaveCriticalSection` at `0x180008e57`
- `KERNEL32!EnterCriticalSection` at `0x180008de2`
- `KERNEL32!EnterCriticalSection` at `0x180008de2`

## pseudocode

```c
BOOL __stdcall SQLGetInstalledDriversW(LPWSTR lpszBuf, WORD cchBufMax, WORD *pcchBufOut)
{
  int v4; // esi
  WORD *v6; // rdi
  BOOL v7; // ebx
  WORD v8; // ax
  int v9; // ecx
  char v11; // [rsp+50h] [rbp+8h] BYREF

  v4 = cchBufMax;
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  v6 = (WORD *)&v11;
  if ( pcchBufOut )
    v6 = pcchBufOut;
  *v6 = 0;
  if ( !lpszBuf || (v7 = 1, (unsigned __int16)v4 <= 1u) )
  {
    v9 = 2;
    goto LABEL_8;
  }
  v8 = SQLGetPrivateProfileStringCover(L"ODBC Drivers", 0, &SubKey, lpszBuf, v4, L"ODBCINST.INI");
  *v6 = v8;
  if ( !v8 )
  {
    v9 = 6;
LABEL_8:
    PostInstError(v9);
    v7 = 0;
  }
  LeaveCriticalSection(&g_csInstaller);
  return v7;
}

```

## disassembly

```asm
0x180008dc0  mov     [rsp+arg_8], rbx
0x180008dc5  mov     [rsp+arg_10], rbp
0x180008dca  push    rsi
0x180008dcb  push    rdi
0x180008dcc  push    r14
0x180008dce  sub     rsp, 30h
0x180008dd2  mov     rbp, rcx
0x180008dd5  movzx   esi, dx
0x180008dd8  lea     rcx, g_csInstaller; lpCriticalSection
0x180008ddf  mov     rbx, r8
0x180008de2  call    cs:__imp_EnterCriticalSection
0x180008de8  call    FreeErrorQueue
0x180008ded  xor     r14d, r14d
0x180008df0  lea     rdi, [rsp+48h+arg_0]
0x180008df5  test    rbx, rbx
0x180008df8  cmovnz  rdi, rbx
0x180008dfc  mov     [rdi], r14w
0x180008e00  test    rbp, rbp
0x180008e03  jz      short loc_180008E43
0x180008e05  lea     ebx, [r14+1]
0x180008e09  cmp     si, bx
0x180008e0c  jbe     short loc_180008E43
0x180008e0e  lea     rcx, aOdbcinstIni; "ODBCINST.INI"
0x180008e15  mov     r9, rbp
0x180008e18  mov     [rsp+48h+var_20], rcx
0x180008e1d  lea     r8, SubKey
0x180008e24  lea     rcx, aOdbcDrivers; "ODBC Drivers"
0x180008e2b  mov     [rsp+48h+var_28], esi
0x180008e2f  xor     edx, edx
0x180008e31  call    SQLGetPrivateProfileStringCover
0x180008e36  mov     [rdi], ax
0x180008e39  test    ax, ax
0x180008e3c  jnz     short loc_180008E50
0x180008e3e  lea     ecx, [rbx+5]
0x180008e41  jmp     short loc_180008E48
0x180008e43  mov     ecx, 2
0x180008e48  call    PostInstError
0x180008e4d  mov     ebx, r14d
0x180008e50  lea     rcx, g_csInstaller; lpCriticalSection
0x180008e57  call    cs:__imp_LeaveCriticalSection
0x180008e5d  mov     rbp, [rsp+48h+arg_10]
0x180008e62  mov     eax, ebx
0x180008e64  mov     rbx, [rsp+48h+arg_8]
0x180008e69  add     rsp, 30h
0x180008e6d  pop     r14
0x180008e6f  pop     rdi
0x180008e70  pop     rsi
0x180008e71  retn
```
