# CODBCLOG::PrepareStatement(void)

- ea: `0x18000bc18`
- end: `0x18000bd97`
- name: `?PrepareStatement@CODBCLOG@@QEAAHXZ`
- size: `383`
- prototype: `__int64 __fastcall(CODBCLOG *this, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000afb0`
- `0x18000b120`

## callees

- `0x18000a7ac`
- `0x18000bc18`
- `0x18000d740`
- `0x18000e560`
- `0x18000eca0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18000bc8f`
- `msvcrt!sprintf_s` at `0x18000bd3a`
- `msvcrt!sprintf_s` at `0x18000bc8f`
- `msvcrt!sprintf_s` at `0x18000bd3a`
- `KERNEL32!LocalFree` at `0x18000bd63`
- `KERNEL32!LocalFree` at `0x18000bd63`
- `KERNEL32!LocalAlloc` at `0x18000bcee`
- `KERNEL32!LocalAlloc` at `0x18000bcee`
- `KERNEL32!lstrlenA` at `0x18000bcd6`
- `KERNEL32!lstrlenA` at `0x18000bcd6`

## pseudocode

```c
__int64 __fastcall CODBCLOG::PrepareStatement(CODBCLOG *this, __int64 a2, unsigned int a3)
{
  struct ODBC_CONNECTION *v4; // rcx
  __int64 result; // rax
  __int64 v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // rsi
  unsigned int v9; // esi
  char *v10; // rdi
  struct ODBC_STATEMENT *v11; // rax
  BOOL v12; // ebx
  char Buffer[208]; // [rsp+30h] [rbp-288h] BYREF
  char v14[400]; // [rsp+100h] [rbp-1B8h] BYREF

  Buffer[0] = 0;
  v4 = (struct ODBC_CONNECTION *)*((_QWORD *)this + 113);
  v14[0] = 0;
  result = GenerateFieldNames(v4, v14, a3);
  if ( (_DWORD)result )
  {
    sprintf_s(
      Buffer,
      0xC8u,
      " ?, ?, ?, '%s', '%s', ?, ?, ?, ?, ?, ?, ?, ?, ?",
      (const char *)this + 928,
      (const char *)this + 1189);
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( v14[v7] );
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    do
      ++v6;
    while ( *((_BYTE *)this + v6 + 356) );
    v9 = v7 + 20 + v6 + lstrlenA("insert into %s ( %s) values ( %s)") + v8;
    v10 = (char *)LocalAlloc(0x40u, v9);
    v11 = ODBC_CONNECTION::AllocStatement(*((ODBC_CONNECTION **)this + 113));
    *((_QWORD *)this + 114) = v11;
    if ( v10 && v11 )
    {
      v12 = sprintf_s(v10, v9, "insert into %s ( %s) values ( %s)", (const char *)this + 356, v14, Buffer) < v9
         && ODBC_STATEMENT::PrepareStatement(*((SQLHSTMT **)this + 114), (SQLCHAR *)v10);
      LocalFree(v10);
    }
    else
    {
      return 0;
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x18000bc18  mov     [rsp+arg_8], rbx
0x18000bc1d  mov     [rsp+arg_10], rbp
0x18000bc22  push    rsi
0x18000bc23  push    rdi
0x18000bc24  push    r14
0x18000bc26  sub     rsp, 2A0h
0x18000bc2d  mov     rax, cs:__security_cookie
0x18000bc34  xor     rax, rsp
0x18000bc37  mov     [rsp+2B8h+var_28], rax
0x18000bc3f  mov     rbx, rcx
0x18000bc42  mov     [rsp+2B8h+Buffer], 0
0x18000bc47  mov     rcx, [rcx+388h]; struct ODBC_CONNECTION *
0x18000bc4e  lea     rdx, [rsp+2B8h+var_1B8]; char *
0x18000bc56  mov     [rsp+2B8h+var_1B8], 0
0x18000bc5e  call    ?GenerateFieldNames@@YAHPEAVODBC_CONNECTION@@PEADK@Z; GenerateFieldNames(ODBC_CONNECTION *,char *,ulong)
0x18000bc63  test    eax, eax
0x18000bc65  jz      loc_18000BD6F
0x18000bc6b  lea     rax, [rbx+4A5h]
0x18000bc72  mov     edx, 0C8h; BufferCount
0x18000bc77  lea     r9, [rbx+3A0h]
0x18000bc7e  mov     [rsp+2B8h+var_298], rax
0x18000bc83  lea     r8, aSS; " ?, ?, ?, '%s', '%s', ?, ?, ?, ?, ?, ?,"...
0x18000bc8a  lea     rcx, [rsp+2B8h+Buffer]; Buffer
0x18000bc8f  call    cs:__imp_sprintf_s
0x18000bc95  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000bc99  lea     r14, [rbx+164h]
0x18000bca0  mov     rbp, rdi
0x18000bca3  lea     rax, [rsp+2B8h+var_1B8]
0x18000bcab  inc     rbp
0x18000bcae  cmp     byte ptr [rax+rbp], 0
0x18000bcb2  jnz     short loc_18000BCAB
0x18000bcb4  lea     rax, [rsp+2B8h+Buffer]
0x18000bcb9  mov     rsi, rdi
0x18000bcbc  inc     rsi
0x18000bcbf  cmp     byte ptr [rax+rsi], 0
0x18000bcc3  jnz     short loc_18000BCBC
0x18000bcc5  inc     rdi
0x18000bcc8  cmp     byte ptr [r14+rdi], 0
0x18000bccd  jnz     short loc_18000BCC5
0x18000bccf  lea     rcx, String; "insert into %s ( %s) values ( %s)"
0x18000bcd6  call    cs:__imp_lstrlenA
0x18000bcdc  add     ebp, 14h
0x18000bcdf  mov     ecx, 40h ; '@'; uFlags
0x18000bce4  add     eax, edi
0x18000bce6  add     esi, eax
0x18000bce8  add     esi, ebp
0x18000bcea  mov     edx, esi; uBytes
0x18000bcec  mov     ebp, esi
0x18000bcee  call    cs:__imp_LocalAlloc
0x18000bcf4  mov     rcx, [rbx+388h]; this
0x18000bcfb  mov     rdi, rax
0x18000bcfe  call    ?AllocStatement@ODBC_CONNECTION@@QEAAPEAVODBC_STATEMENT@@XZ; ODBC_CONNECTION::AllocStatement(void)
0x18000bd03  mov     [rbx+390h], rax
0x18000bd0a  test    rdi, rdi
0x18000bd0d  jz      short loc_18000BD6B
0x18000bd0f  test    rax, rax
0x18000bd12  jz      short loc_18000BD6B
0x18000bd14  lea     rax, [rsp+2B8h+Buffer]
0x18000bd19  mov     r9, r14
0x18000bd1c  mov     [rsp+2B8h+var_290], rax
0x18000bd21  lea     r8, String; "insert into %s ( %s) values ( %s)"
0x18000bd28  lea     rax, [rsp+2B8h+var_1B8]
0x18000bd30  mov     edx, ebp; BufferCount
0x18000bd32  mov     rcx, rdi; Buffer
0x18000bd35  mov     [rsp+2B8h+var_298], rax
0x18000bd3a  call    cs:__imp_sprintf_s
0x18000bd40  cmp     eax, esi
0x18000bd42  jnb     short loc_18000BD5E
0x18000bd44  mov     rcx, [rbx+390h]; this
0x18000bd4b  mov     rdx, rdi; char *
0x18000bd4e  call    ?PrepareStatement@ODBC_STATEMENT@@QEAAHPEBD@Z; ODBC_STATEMENT::PrepareStatement(char const *)
0x18000bd53  test    eax, eax
0x18000bd55  jz      short loc_18000BD5E
0x18000bd57  mov     ebx, 1
0x18000bd5c  jmp     short loc_18000BD60
0x18000bd5e  xor     ebx, ebx
0x18000bd60  mov     rcx, rdi; hMem
0x18000bd63  call    cs:__imp_LocalFree
0x18000bd69  jmp     short loc_18000BD6D
0x18000bd6b  xor     ebx, ebx
0x18000bd6d  mov     eax, ebx
0x18000bd6f  mov     rcx, [rsp+2B8h+var_28]
0x18000bd77  xor     rcx, rsp; StackCookie
0x18000bd7a  call    __security_check_cookie
0x18000bd7f  lea     r11, [rsp+2B8h+var_18]
0x18000bd87  mov     rbx, [r11+28h]
0x18000bd8b  mov     rbp, [r11+30h]
0x18000bd8f  mov     rsp, r11
0x18000bd92  pop     r14
0x18000bd94  pop     rdi
0x18000bd95  pop     rsi
0x18000bd96  retn
```
