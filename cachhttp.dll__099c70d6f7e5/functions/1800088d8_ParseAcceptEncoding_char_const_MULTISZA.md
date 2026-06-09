# ParseAcceptEncoding(char const *,MULTISZA *)

- ea: `0x1800088d8`
- end: `0x1800089ea`
- name: `?ParseAcceptEncoding@@YAJPEBDPEAVMULTISZA@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(const char *, struct MULTISZA *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000838c`
- `0x1800089f0`

## callees

- `0x1800088d8`
- `0x180008bf0`

## import_xrefs

- `msvcrt!isalnum` at `0x18000893c`
- `msvcrt!isalnum` at `0x18000893c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000899b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000899b`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x180008975`
- `iisutil!?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z` at `0x180008975`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008963`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180008963`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800089bd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800089bd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180008911`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180008911`

## pseudocode

```c
__int64 __fastcall ParseAcceptEncoding(const char *a1, struct MULTISZA *a2)
{
  const char *v4; // rdi
  int v5; // eax
  signed int LastError; // eax
  unsigned int v7; // ebx
  _BYTE v9[56]; // [rsp+28h] [rbp-70h] BYREF
  char v10[32]; // [rsp+60h] [rbp-38h] BYREF

  STRA::STRA((STRA *)v9, v10, 0x20u);
  if ( a1 )
  {
    while ( *a1 )
    {
      for ( ; *a1 == 32; ++a1 )
        ;
      v4 = a1;
      while ( isalnum(*(unsigned __int8 *)a1) || *a1 == 42 )
        ++a1;
      if ( a1 > v4 )
      {
        v5 = STRA::Copy((STRA *)v9, v4, (_DWORD)a1 - (_DWORD)v4);
        if ( v5 < 0 )
        {
          v7 = v5;
          goto LABEL_21;
        }
        if ( !MULTISZA::Append(a2, (struct STRA *)v9) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_21;
        }
      }
      if ( *a1 != 44 )
      {
        do
        {
          if ( !*a1 )
            break;
          ++a1;
        }
        while ( *a1 != 44 );
        if ( *a1 != 44 )
          continue;
      }
      ++a1;
    }
  }
  v7 = 0;
LABEL_21:
  STRA::~STRA((STRA *)v9);
  return v7;
}

```

## disassembly

```asm
0x1800088d8  mov     r11, rsp
0x1800088db  mov     [r11+18h], rbx
0x1800088df  mov     [r11+20h], rsi
0x1800088e3  push    rdi
0x1800088e4  sub     rsp, 90h
0x1800088eb  mov     rax, cs:__security_cookie
0x1800088f2  xor     rax, rsp
0x1800088f5  mov     [rsp+98h+var_18], rax
0x1800088fd  mov     rsi, rdx
0x180008900  mov     rbx, rcx
0x180008903  lea     rdx, [r11-38h]
0x180008907  mov     r8d, 20h ; ' '
0x18000890d  lea     rcx, [r11-70h]
0x180008911  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180008917  test    rbx, rbx
0x18000891a  jz      loc_1800089B6
0x180008920  mov     al, [rbx]
0x180008922  test    al, al
0x180008924  jz      loc_1800089B6
0x18000892a  cmp     al, 20h ; ' '
0x18000892c  jnz     short loc_180008936
0x18000892e  inc     rbx
0x180008931  cmp     byte ptr [rbx], 20h ; ' '
0x180008934  jz      short loc_18000892E
0x180008936  mov     rdi, rbx
0x180008939  movzx   ecx, byte ptr [rbx]; C
0x18000893c  call    cs:__imp_isalnum
0x180008942  test    eax, eax
0x180008944  jnz     short loc_18000894B
0x180008946  cmp     byte ptr [rbx], 2Ah ; '*'
0x180008949  jnz     short loc_180008950
0x18000894b  inc     rbx
0x18000894e  jmp     short loc_180008939
0x180008950  cmp     rbx, rdi
0x180008953  jbe     short loc_18000897F
0x180008955  mov     r8d, ebx
0x180008958  lea     rcx, [rsp+98h+var_70]
0x18000895d  sub     r8d, edi
0x180008960  mov     rdx, rdi
0x180008963  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180008969  test    eax, eax
0x18000896b  js      short loc_1800089B2
0x18000896d  lea     rdx, [rsp+98h+var_70]
0x180008972  mov     rcx, rsi
0x180008975  call    cs:__imp_?Append@MULTISZA@@QEAAHAEAVSTRA@@@Z; MULTISZA::Append(STRA &)
0x18000897b  test    eax, eax
0x18000897d  jz      short loc_18000899B
0x18000897f  cmp     byte ptr [rbx], 2Ch ; ','
0x180008982  jz      short loc_180008996
0x180008984  cmp     byte ptr [rbx], 0
0x180008987  jz      short loc_180008991
0x180008989  inc     rbx
0x18000898c  cmp     byte ptr [rbx], 2Ch ; ','
0x18000898f  jnz     short loc_180008984
0x180008991  cmp     byte ptr [rbx], 2Ch ; ','
0x180008994  jnz     short loc_180008920
0x180008996  inc     rbx
0x180008999  jmp     short loc_180008920
0x18000899b  call    cs:__imp_GetLastError
0x1800089a1  mov     ebx, eax
0x1800089a3  test    eax, eax
0x1800089a5  jle     short loc_1800089B8
0x1800089a7  movzx   ebx, ax
0x1800089aa  or      ebx, 80070000h
0x1800089b0  jmp     short loc_1800089B8
0x1800089b2  mov     ebx, eax
0x1800089b4  jmp     short loc_1800089B8
0x1800089b6  xor     ebx, ebx
0x1800089b8  lea     rcx, [rsp+98h+var_70]
0x1800089bd  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800089c3  mov     eax, ebx
0x1800089c5  mov     rcx, [rsp+98h+var_18]
0x1800089cd  xor     rcx, rsp; StackCookie
0x1800089d0  call    __security_check_cookie
0x1800089d5  lea     r11, [rsp+98h+var_8]
0x1800089dd  mov     rbx, [r11+20h]
0x1800089e1  mov     rsi, [r11+28h]
0x1800089e5  mov     rsp, r11
0x1800089e8  pop     rdi
0x1800089e9  retn
```
