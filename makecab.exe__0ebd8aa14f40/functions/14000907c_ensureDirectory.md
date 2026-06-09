# ensureDirectory

- ea: `0x14000907c`
- end: `0x14000944e`
- name: `ensureDirectory`
- size: `978`
- prototype: `__int64 __fastcall(LPCSTR lpCurrentChar)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000488c`
- `0x1400072bc`
- `0x140007504`
- `0x140009884`

## callees

- `0x140001508`
- `0x140008620`
- `0x140008e64`
- `0x140008f3c`
- `0x14000907c`
- `0x14000e450`

## import_xrefs

- `msvcrt!_mkdir` at `0x1400091b2`
- `msvcrt!_mkdir` at `0x1400091b2`
- `msvcrt!_unlink` at `0x140009438`
- `msvcrt!_unlink` at `0x140009438`
- `msvcrt!__doserrno` at `0x140009307`
- `msvcrt!__doserrno` at `0x140009319`
- `msvcrt!__doserrno` at `0x14000935d`
- `msvcrt!__doserrno` at `0x140009307`
- `msvcrt!__doserrno` at `0x140009319`
- `msvcrt!__doserrno` at `0x14000935d`
- `msvcrt!_errno` at `0x1400092df`
- `msvcrt!_errno` at `0x140009321`
- `msvcrt!_errno` at `0x140009365`
- `msvcrt!_errno` at `0x1400092df`
- `msvcrt!_errno` at `0x140009321`
- `msvcrt!_errno` at `0x140009365`
- `msvcrt!_open` at `0x1400092d0`
- `msvcrt!_open` at `0x1400092d0`
- `msvcrt!_close` at `0x14000942d`
- `msvcrt!_close` at `0x14000942d`
- `msvcrt!printf` at `0x140009345`
- `msvcrt!printf` at `0x140009345`
- `USER32!CharNextExA` at `0x1400090de`
- `USER32!CharNextExA` at `0x140009138`
- `USER32!CharNextExA` at `0x1400090de`
- `USER32!CharNextExA` at `0x140009138`
- `KERNEL32!GetCurrentProcessId` at `0x14000929c`
- `KERNEL32!GetCurrentProcessId` at `0x14000929c`
- `KERNEL32!GetLastError` at `0x140009329`
- `KERNEL32!GetLastError` at `0x140009329`

## string_xrefs

- `0x14000941f`: `Could not create file in directory: %1`
- `0x140009337`: `EnsureDirectory: Cant create file: %s, errno=%d, _doserrno=%d, GLE=%d\n`
- `0x14000937e`: `Path is invalid: %1`
- `0x1400093d3`: `Ran out of temp file names after %1 attempts: %2`

## pseudocode

```c
__int64 __fastcall ensureDirectory(char *lpCurrentChar, int a2, __int64 a3)
{
  char v3; // al
  LPSTR i; // rdx
  CHAR v8; // al
  LPSTR v9; // rbx
  CHAR v10; // al
  CHAR v11; // al
  unsigned __int64 v12; // rcx
  LPCSTR v13; // rax
  char *v14; // r8
  __int64 v15; // rdx
  char *v16; // rax
  char *v17; // r9
  const char *v18; // rdx
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rcx
  int v24; // edi
  int v25; // ebx
  size_t v26; // r14
  char *v27; // r12
  DWORD CurrentProcessId; // eax
  int v29; // eax
  int v30; // ecx
  unsigned int v31; // edi
  int v32; // ebx
  DWORD LastError; // eax
  unsigned int v34; // ebx
  int *v35; // rax
  char Path[256]; // [rsp+30h] [rbp-D0h] BYREF

  v3 = *lpCurrentChar;
  for ( i = lpCurrentChar; v3; v3 = *i )
  {
    if ( v3 == 92 )
      break;
    if ( v3 == 47 )
      break;
    if ( v3 == 58 )
    {
      v8 = i[1];
      if ( v8 != 92 && v8 != 47 )
        break;
    }
    i = CharNextExA(0, i, 0);
  }
  Path[0] = 0;
  if ( *i || !a2 )
  {
    v9 = lpCurrentChar;
    if ( *lpCurrentChar )
    {
      while ( 1 )
      {
        v10 = *v9;
        if ( !*v9 )
          break;
        do
        {
          if ( v10 == 92 )
            break;
          if ( v10 == 47 )
            break;
          if ( v10 == 58 )
          {
            v11 = v9[1];
            if ( v11 != 92 && v11 != 47 )
              break;
          }
          v9 = CharNextExA(0, v9, 0);
          v10 = *v9;
        }
        while ( *v9 );
        if ( *v9 || !a2 )
        {
          v12 = (int)v9 - (int)lpCurrentChar;
          if ( (_DWORD)v9 != (_DWORD)lpCurrentChar && (*v9 == 58 || *(v9 - 1) == 58) )
            v12 = (int)v9 - (int)lpCurrentChar + 1LL;
          if ( v12 > 0x7FFFFFFE )
          {
            Path[0] = 0;
            goto LABEL_37;
          }
          v13 = lpCurrentChar;
          v14 = Path;
          v15 = 256;
          do
          {
            if ( !v12 )
              break;
            if ( !*v13 )
              break;
            *v14++ = *v13++;
            --v12;
            --v15;
          }
          while ( v15 );
          v16 = v14 - 1;
          if ( v15 )
            v16 = v14;
          *v16 = 0;
          if ( !v15 )
            goto LABEL_37;
          _mkdir(Path);
        }
        if ( !*v9 )
          break;
        ++v9;
      }
    }
  }
  v20 = -1;
  do
    ++v20;
  while ( Path[v20] );
  if ( !v20 )
  {
    v21 = -1;
    do
      ++v21;
    while ( lpCurrentChar[v21] );
    if ( v21 && (*lpCurrentChar == 92 || *lpCurrentChar == 47) )
    {
      Path[0] = *lpCurrentChar;
      Path[1] = 0;
    }
  }
  v22 = -1;
  do
    ++v22;
  while ( Path[v22] );
  if ( v22 )
  {
    if ( v22 > 0xFE )
      goto LABEL_37;
    v23 = v22 + (int)appendPathSeparator(&Path[v22 - 1]);
  }
  else
  {
    v23 = 0;
  }
  v24 = 0;
  v25 = 0;
  v26 = 256 - v23;
  v27 = &Path[v23];
  while ( 1 )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( StringCbPrintfA(v27, v26, "CAB%5.5d.TMP", v25 + CurrentProcessId) < 0 )
      break;
    v29 = _open(Path, 1282, 384);
    if ( v29 != -1 )
    {
      _close(v29);
      _unlink(Path);
      return 1;
    }
    v30 = *_errno();
    if ( v30 == 2 )
      goto LABEL_63;
    if ( v30 == 13 )
    {
      if ( ++v24 >= 5 )
      {
        Path[v22] = 0;
        v17 = Path;
        v18 = "Could not create file in directory: %1";
        goto LABEL_38;
      }
    }
    else if ( v30 != 17 )
    {
      if ( v30 != 22 )
      {
        if ( v30 != 24 )
        {
LABEL_63:
          v31 = *__doserrno();
          v32 = *_errno();
          LastError = GetLastError();
          printf("EnsureDirectory: Cant create file: %s, errno=%d, _doserrno=%d, GLE=%d\n", Path, v32, v31, LastError);
          Path[v22] = 0;
          v34 = *__doserrno();
          v35 = _errno();
          ErrSet(a3, "Path is invalid: %1", "%s%d%d", Path, *v35, v34);
          return 0;
        }
        Path[v22] = 0;
        v17 = Path;
        v18 = "No more file handles: %1";
        goto LABEL_38;
      }
      if ( *__doserrno() != 303 )
        goto LABEL_63;
    }
    if ( ++v25 >= 999 )
    {
      Path[v22] = 0;
      ErrSet(a3, "Ran out of temp file names after %1 attempts: %2", "%d%s", v25, Path);
      return 0;
    }
  }
LABEL_37:
  v17 = lpCurrentChar;
  v18 = "File name too long: %1";
LABEL_38:
  ErrSet(a3, v18, "%s", v17);
  return 0;
}

```

## disassembly

```asm
0x14000907c  mov     [rsp-8+arg_8], rbx
0x140009081  push    rbp
0x140009082  push    rsi
0x140009083  push    rdi
0x140009084  push    r12
0x140009086  push    r13
0x140009088  push    r14
0x14000908a  push    r15
0x14000908c  lea     rbp, [rsp-40h]
0x140009091  sub     rsp, 140h
0x140009098  mov     rax, cs:__security_cookie
0x14000909f  xor     rax, rsp
0x1400090a2  mov     [rbp+70h+var_40], rax
0x1400090a6  mov     al, [rcx]
0x1400090a8  mov     edi, edx
0x1400090aa  mov     rdx, rcx
0x1400090ad  mov     r13, r8
0x1400090b0  mov     r15, rcx
0x1400090b3  mov     sil, 5Ch ; '\'
0x1400090b6  mov     r12b, 2Fh ; '/'
0x1400090b9  xor     r14d, r14d
0x1400090bc  jmp     short loc_1400090E9
0x1400090be  cmp     al, sil
0x1400090c1  jz      short loc_1400090ED
0x1400090c3  cmp     al, r12b
0x1400090c6  jz      short loc_1400090ED
0x1400090c8  cmp     al, 3Ah ; ':'
0x1400090ca  jnz     short loc_1400090D9
0x1400090cc  mov     al, [rdx+1]
0x1400090cf  cmp     al, sil
0x1400090d2  jz      short loc_1400090D9
0x1400090d4  cmp     al, r12b
0x1400090d7  jnz     short loc_1400090ED
0x1400090d9  xor     ecx, ecx; CodePage
0x1400090db  xor     r8d, r8d; dwFlags
0x1400090de  call    cs:__imp_CharNextExA
0x1400090e4  mov     rdx, rax; lpCurrentChar
0x1400090e7  mov     al, [rax]
0x1400090e9  test    al, al
0x1400090eb  jnz     short loc_1400090BE
0x1400090ed  mov     [rsp+170h+Path], r14b
0x1400090f2  cmp     [rdx], r14b
0x1400090f5  jnz     short loc_1400090FF
0x1400090f7  test    edi, edi
0x1400090f9  jnz     loc_14000920C
0x1400090ff  mov     rbx, r15
0x140009102  cmp     [r15], r14b
0x140009105  jz      loc_14000920C
0x14000910b  mov     al, [rbx]
0x14000910d  test    al, al
0x14000910f  jz      loc_14000920C
0x140009115  cmp     al, sil
0x140009118  jz      short loc_140009147
0x14000911a  cmp     al, r12b
0x14000911d  jz      short loc_140009147
0x14000911f  cmp     al, 3Ah ; ':'
0x140009121  jnz     short loc_140009130
0x140009123  mov     al, [rbx+1]
0x140009126  cmp     al, sil
0x140009129  jz      short loc_140009130
0x14000912b  cmp     al, r12b
0x14000912e  jnz     short loc_140009147
0x140009130  xor     ecx, ecx; CodePage
0x140009132  xor     r8d, r8d; dwFlags
0x140009135  mov     rdx, rbx; lpCurrentChar
0x140009138  call    cs:__imp_CharNextExA
0x14000913e  mov     rbx, rax
0x140009141  mov     al, [rax]
0x140009143  test    al, al
0x140009145  jnz     short loc_140009115
0x140009147  cmp     [rbx], r14b
0x14000914a  jnz     short loc_140009150
0x14000914c  test    edi, edi
0x14000914e  jnz     short loc_1400091B8
0x140009150  mov     eax, ebx
0x140009152  sub     eax, r15d
0x140009155  movsxd  rcx, eax
0x140009158  jz      short loc_140009168
0x14000915a  cmp     byte ptr [rbx], 3Ah ; ':'
0x14000915d  jz      short loc_140009165
0x14000915f  cmp     byte ptr [rbx-1], 3Ah ; ':'
0x140009163  jnz     short loc_140009168
0x140009165  inc     rcx
0x140009168  cmp     rcx, 7FFFFFFEh
0x14000916f  ja      short loc_1400091C5
0x140009171  mov     rax, r15
0x140009174  lea     r8, [rsp+170h+Path]
0x140009179  mov     edx, 100h
0x14000917e  test    rcx, rcx
0x140009181  jz      short loc_14000919D
0x140009183  mov     r9b, [rax]
0x140009186  test    r9b, r9b
0x140009189  jz      short loc_14000919D
0x14000918b  mov     [r8], r9b
0x14000918e  inc     rax
0x140009191  inc     r8
0x140009194  dec     rcx
0x140009197  sub     rdx, 1
0x14000919b  jnz     short loc_14000917E
0x14000919d  test    rdx, rdx
0x1400091a0  lea     rax, [r8-1]
0x1400091a4  cmovnz  rax, r8
0x1400091a8  mov     [rax], r14b
0x1400091ab  jz      short loc_1400091CA
0x1400091ad  lea     rcx, [rsp+170h+Path]; Path
0x1400091b2  call    cs:__imp__mkdir
0x1400091b8  cmp     [rbx], r14b
0x1400091bb  jz      short loc_14000920C
0x1400091bd  inc     rbx
0x1400091c0  jmp     loc_14000910B
0x1400091c5  mov     [rsp+170h+Path], r14b
0x1400091ca  mov     r9, r15
0x1400091cd  lea     rdx, aFileNameTooLon; "File name too long: %1"
0x1400091d4  lea     r8, aS_4; "%s"
0x1400091db  mov     rcx, r13
0x1400091de  call    ErrSet
0x1400091e3  xor     eax, eax
0x1400091e5  mov     rcx, [rbp+70h+var_40]
0x1400091e9  xor     rcx, rsp; StackCookie
0x1400091ec  call    __security_check_cookie
0x1400091f1  mov     rbx, [rsp+170h+arg_8]
0x1400091f9  add     rsp, 140h
0x140009200  pop     r15
0x140009202  pop     r14
0x140009204  pop     r13
0x140009206  pop     r12
0x140009208  pop     rdi
0x140009209  pop     rsi
0x14000920a  pop     rbp
0x14000920b  retn
0x14000920c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140009210  lea     rcx, [rsp+170h+Path]
0x140009215  mov     rax, rdx
0x140009218  inc     rax
0x14000921b  cmp     [rcx+rax], r14b
0x14000921f  jnz     short loc_140009218
0x140009221  test    rax, rax
0x140009224  jnz     short loc_14000924D
0x140009226  mov     rax, rdx
0x140009229  inc     rax
0x14000922c  cmp     [r15+rax], r14b
0x140009230  jnz     short loc_140009229
0x140009232  test    rax, rax
0x140009235  jz      short loc_14000924D
0x140009237  mov     al, [r15]
0x14000923a  cmp     al, sil
0x14000923d  jz      short loc_140009244
0x14000923f  cmp     al, r12b
0x140009242  jnz     short loc_14000924D
0x140009244  mov     [rsp+170h+Path], al
0x140009248  mov     [rsp+170h+var_13F], r14b
0x14000924d  lea     rax, [rsp+170h+Path]
0x140009252  mov     rsi, rdx
0x140009255  inc     rsi
0x140009258  cmp     [rax+rsi], r14b
0x14000925c  jnz     short loc_140009255
0x14000925e  test    rsi, rsi
0x140009261  jz      short loc_140009282
0x140009263  cmp     rsi, 0FEh
0x14000926a  ja      loc_1400091CA
0x140009270  lea     rcx, [rsp+rsi+170h+var_141]
0x140009275  call    appendPathSeparator
0x14000927a  movsxd  rcx, eax
0x14000927d  add     rcx, rsi
0x140009280  jmp     short loc_140009285
0x140009282  mov     rcx, rsi
0x140009285  mov     edi, r14d
0x140009288  lea     r12, [rsp+170h+Path]
0x14000928d  mov     ebx, r14d
0x140009290  mov     r14d, 100h
0x140009296  sub     r14, rcx
0x140009299  add     r12, rcx
0x14000929c  call    cs:__imp_GetCurrentProcessId
0x1400092a2  lea     r8, pszFormat; "CAB%5.5d.TMP"
0x1400092a9  mov     rdx, r14; cbDest
0x1400092ac  mov     rcx, r12; pszDest
0x1400092af  lea     r9d, [rbx+rax]
0x1400092b3  call    StringCbPrintfA
0x1400092b8  test    eax, eax
0x1400092ba  js      loc_1400091CA
0x1400092c0  mov     edx, 502h; OpenFlag
0x1400092c5  lea     rcx, [rsp+170h+Path]; FileName
0x1400092ca  mov     r8d, 180h
0x1400092d0  call    cs:__imp__open
0x1400092d6  cmp     eax, 0FFFFFFFFh
0x1400092d9  jnz     loc_14000942B
0x1400092df  call    cs:__imp__errno
0x1400092e5  mov     ecx, [rax]
0x1400092e7  cmp     ecx, 2
0x1400092ea  jz      short loc_140009319
0x1400092ec  cmp     ecx, 0Dh
0x1400092ef  jz      loc_140009395
0x1400092f5  cmp     ecx, 11h
0x1400092f8  jz      loc_14000939C
0x1400092fe  cmp     ecx, 16h
0x140009301  jnz     loc_1400093E4
0x140009307  call    cs:__imp___doserrno
0x14000930d  cmp     dword ptr [rax], 12Fh
0x140009313  jz      loc_14000939C
0x140009319  call    cs:__imp___doserrno
0x14000931f  mov     edi, [rax]
0x140009321  call    cs:__imp__errno
0x140009327  mov     ebx, [rax]
0x140009329  call    cs:__imp_GetLastError
0x14000932f  mov     r9d, edi
0x140009332  lea     rdx, [rsp+170h+Path]
0x140009337  lea     rcx, aEnsuredirector; "EnsureDirectory: Cant create file: %s, "...
0x14000933e  mov     dword ptr [rsp+170h+var_150], eax
0x140009342  mov     r8d, ebx
0x140009345  call    cs:__imp_printf
0x14000934b  cmp     rsi, 100h
0x140009352  jnb     loc_140009448
0x140009358  mov     [rsp+rsi+170h+Path], 0
0x14000935d  call    cs:__imp___doserrno
0x140009363  mov     ebx, [rax]
0x140009365  call    cs:__imp__errno
0x14000936b  mov     [rsp+170h+var_148], ebx
0x14000936f  lea     r9, [rsp+170h+Path]
0x140009374  lea     r8, aSDD; "%s%d%d"
0x14000937b  mov     rcx, r13
0x14000937e  lea     rdx, aPathIsInvalid1; "Path is invalid: %1"
0x140009385  mov     eax, [rax]
0x140009387  mov     dword ptr [rsp+170h+var_150], eax
0x14000938b  call    ErrSet
0x140009390  jmp     loc_1400091E3
0x140009395  inc     edi
0x140009397  cmp     edi, 5
0x14000939a  jge     short loc_14000940C
0x14000939c  inc     ebx
0x14000939e  cmp     ebx, 3E7h
0x1400093a4  jl      loc_14000929C
0x1400093aa  cmp     rsi, 100h
0x1400093b1  jnb     loc_140009448
0x1400093b7  lea     rax, [rsp+170h+Path]
0x1400093bc  mov     [rsp+rsi+170h+Path], 0
0x1400093c1  mov     r9d, ebx
0x1400093c4  mov     [rsp+170h+var_150], rax
0x1400093c9  lea     r8, aDS; "%d%s"
0x1400093d0  mov     rcx, r13
0x1400093d3  lea     rdx, aRanOutOfTempFi; "Ran out of temp file names after %1 att"...
0x1400093da  call    ErrSet
0x1400093df  jmp     loc_1400091E3
0x1400093e4  cmp     ecx, 18h
0x1400093e7  jnz     loc_140009319
0x1400093ed  cmp     rsi, 100h
0x1400093f4  jnb     short loc_140009448
0x1400093f6  mov     [rsp+rsi+170h+Path], 0
0x1400093fb  lea     r9, [rsp+170h+Path]
0x140009400  lea     rdx, aNoMoreFileHand; "No more file handles: %1"
0x140009407  jmp     loc_1400091D4
0x14000940c  cmp     rsi, 100h
0x140009413  jnb     short loc_140009448
0x140009415  mov     [rsp+rsi+170h+Path], 0
0x14000941a  lea     r9, [rsp+170h+Path]
0x14000941f  lea     rdx, aCouldNotCreate; "Could not create file in directory: %1"
0x140009426  jmp     loc_1400091D4
0x14000942b  mov     ecx, eax; FileHandle
0x14000942d  call    cs:__imp__close
0x140009433  lea     rcx, [rsp+170h+Path]; FileName
0x140009438  call    cs:__imp__unlink
0x14000943e  mov     eax, 1
0x140009443  jmp     loc_1400091E5
0x140009448  call    __report_rangecheckfailure
```
