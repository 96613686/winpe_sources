# TIMESPAN_RANGE_VALIDATOR::Create(ushort const *,SCHEMA_ATTRIBUTE *)

- ea: `0x18003f1b0`
- end: `0x18003f364`
- name: `?Create@TIMESPAN_RANGE_VALIDATOR@@UEAAJPEBGPEAVSCHEMA_ATTRIBUTE@@@Z`
- size: `436`
- prototype: `__int64 __fastcall(TIMESPAN_RANGE_VALIDATOR *__hidden this, const unsigned __int16 *, struct SCHEMA_ATTRIBUTE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18003f1b0`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcschr` at `0x18003f246`
- `msvcrt!wcschr` at `0x18003f282`
- `msvcrt!wcschr` at `0x18003f2b4`
- `msvcrt!wcschr` at `0x18003f246`
- `msvcrt!wcschr` at `0x18003f282`
- `msvcrt!wcschr` at `0x18003f2b4`
- `msvcrt!_wcstoi64` at `0x18003f26c`
- `msvcrt!_wcstoi64` at `0x18003f29e`
- `msvcrt!_wcstoi64` at `0x18003f2fc`
- `msvcrt!_wcstoi64` at `0x18003f26c`
- `msvcrt!_wcstoi64` at `0x18003f29e`
- `msvcrt!_wcstoi64` at `0x18003f2fc`
- `msvcrt!iswspace` at `0x18003f2ce`
- `msvcrt!iswspace` at `0x18003f2ce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003f334`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003f334`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003f235`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003f235`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003f200`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003f200`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003f220`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003f220`

## pseudocode

```c
__int64 __fastcall TIMESPAN_RANGE_VALIDATOR::Create(
        TIMESPAN_RANGE_VALIDATOR *this,
        const unsigned __int16 *a2,
        struct SCHEMA_ATTRIBUTE *a3)
{
  int v6; // ebx
  const wchar_t *Str; // r14
  wchar_t *v8; // rsi
  __int64 v9; // rax
  const wchar_t *v10; // r14
  wchar_t *v11; // rsi
  __int64 v12; // rax
  const wchar_t *v13; // r14
  wchar_t *v14; // rax
  wint_t *v15; // rsi
  _DWORD *v16; // rax
  _BYTE v18[64]; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int16 v19[32]; // [rsp+60h] [rbp-68h] BYREF

  memset_0(v19, 0, sizeof(v19));
  STRU::STRU((STRU *)v18, v19, 0x20u);
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_16;
  }
  v6 = STRU::Copy((STRU *)v18, a2);
  if ( v6 >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v18);
    v8 = wcschr(Str, 0x2Cu);
    if ( v8 )
    {
      *v8 = 0;
      v9 = _wcstoi64(Str, 0, 10);
      v10 = v8 + 1;
      *((_QWORD *)this + 2) = v9;
      v11 = wcschr(v8 + 1, 0x2Cu);
      if ( v11 )
      {
        *v11 = 0;
        v12 = _wcstoi64(v10, 0, 10);
        v13 = v11 + 1;
        *((_QWORD *)this + 3) = v12;
        v14 = wcschr(v11 + 1, 0x2Cu);
        v15 = v14;
        if ( !v14 )
        {
LABEL_12:
          *((_QWORD *)this + 4) = _wcstoi64(v13, 0, 10);
          v16 = (_DWORD *)*((_QWORD *)a3 + 7);
          if ( v16 )
            LODWORD(v16) = *v16;
          *((_DWORD *)this + 10) = (_DWORD)v16;
          *((_DWORD *)this + 11) = *((_DWORD *)this + 11) & 0xFFFFFFFD | (*((_DWORD *)a3 + 5) >> 4) & 2;
          goto LABEL_16;
        }
        *v14 = 0;
        do
          ++v15;
        while ( iswspace(*v15) );
        if ( !wcscmp_0(v15, L"exclude") )
        {
          *((_DWORD *)this + 11) |= 1u;
          goto LABEL_12;
        }
      }
    }
    v6 = -2147024883;
  }
LABEL_16:
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003f1b0  mov     [rsp+arg_10], rbx
0x18003f1b5  mov     [rsp+arg_18], rbp
0x18003f1ba  push    rsi
0x18003f1bb  push    rdi
0x18003f1bc  push    r14
0x18003f1be  sub     rsp, 0B0h
0x18003f1c5  mov     rax, cs:__security_cookie
0x18003f1cc  xor     rax, rsp
0x18003f1cf  mov     [rsp+0C8h+var_28], rax
0x18003f1d7  mov     rbx, rdx
0x18003f1da  mov     rbp, r8
0x18003f1dd  xor     edx, edx; Val
0x18003f1df  mov     rdi, rcx
0x18003f1e2  lea     rcx, [rsp+0C8h+var_68]; void *
0x18003f1e7  lea     r8d, [rdx+40h]; Size
0x18003f1eb  call    memset_0
0x18003f1f0  mov     r8d, 20h ; ' '
0x18003f1f6  lea     rdx, [rsp+0C8h+var_68]
0x18003f1fb  lea     rcx, [rsp+0C8h+var_A8]
0x18003f200  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003f206  test    rbx, rbx
0x18003f209  jz      loc_18003F32A
0x18003f20f  test    rbp, rbp
0x18003f212  jz      loc_18003F32A
0x18003f218  mov     rdx, rbx
0x18003f21b  lea     rcx, [rsp+0C8h+var_A8]
0x18003f220  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003f226  mov     ebx, eax
0x18003f228  test    eax, eax
0x18003f22a  js      loc_18003F32F
0x18003f230  lea     rcx, [rsp+0C8h+var_A8]
0x18003f235  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003f23b  mov     rcx, rax; Str
0x18003f23e  mov     edx, 2Ch ; ','; Ch
0x18003f243  mov     r14, rax
0x18003f246  call    cs:__imp_wcschr
0x18003f24c  mov     rsi, rax
0x18003f24f  test    rax, rax
0x18003f252  jnz     short loc_18003F25E
0x18003f254  mov     ebx, 8007000Dh
0x18003f259  jmp     loc_18003F32F
0x18003f25e  xor     eax, eax
0x18003f260  xor     edx, edx; EndPtr
0x18003f262  mov     rcx, r14; String
0x18003f265  mov     [rsi], ax
0x18003f268  lea     r8d, [rax+0Ah]; Radix
0x18003f26c  call    cs:__imp__wcstoi64
0x18003f272  lea     r14, [rsi+2]
0x18003f276  mov     edx, 2Ch ; ','; Ch
0x18003f27b  mov     rcx, r14; Str
0x18003f27e  mov     [rdi+10h], rax
0x18003f282  call    cs:__imp_wcschr
0x18003f288  mov     rsi, rax
0x18003f28b  test    rax, rax
0x18003f28e  jz      short loc_18003F254
0x18003f290  xor     eax, eax
0x18003f292  xor     edx, edx; EndPtr
0x18003f294  mov     rcx, r14; String
0x18003f297  mov     [rsi], ax
0x18003f29a  lea     r8d, [rax+0Ah]; Radix
0x18003f29e  call    cs:__imp__wcstoi64
0x18003f2a4  lea     r14, [rsi+2]
0x18003f2a8  mov     edx, 2Ch ; ','; Ch
0x18003f2ad  mov     rcx, r14; Str
0x18003f2b0  mov     [rdi+18h], rax
0x18003f2b4  call    cs:__imp_wcschr
0x18003f2ba  mov     rsi, rax
0x18003f2bd  test    rax, rax
0x18003f2c0  jz      short loc_18003F2F3
0x18003f2c2  xor     ecx, ecx
0x18003f2c4  mov     [rax], cx
0x18003f2c7  add     rsi, 2
0x18003f2cb  movzx   ecx, word ptr [rsi]; C
0x18003f2ce  call    cs:__imp_iswspace
0x18003f2d4  test    eax, eax
0x18003f2d6  jnz     short loc_18003F2C7
0x18003f2d8  lea     rdx, aExclude; "exclude"
0x18003f2df  mov     rcx, rsi; String1
0x18003f2e2  call    wcscmp_0
0x18003f2e7  test    eax, eax
0x18003f2e9  jnz     loc_18003F254
0x18003f2ef  or      dword ptr [rdi+2Ch], 1
0x18003f2f3  xor     edx, edx; EndPtr
0x18003f2f5  mov     rcx, r14; String
0x18003f2f8  lea     r8d, [rdx+0Ah]; Radix
0x18003f2fc  call    cs:__imp__wcstoi64
0x18003f302  mov     [rdi+20h], rax
0x18003f306  mov     rax, [rbp+38h]
0x18003f30a  test    rax, rax
0x18003f30d  jz      short loc_18003F311
0x18003f30f  mov     eax, [rax]
0x18003f311  mov     [rdi+28h], eax
0x18003f314  mov     ecx, [rbp+14h]
0x18003f317  mov     eax, [rdi+2Ch]
0x18003f31a  shr     ecx, 4
0x18003f31d  and     eax, 0FFFFFFFDh
0x18003f320  and     ecx, 2
0x18003f323  or      ecx, eax
0x18003f325  mov     [rdi+2Ch], ecx
0x18003f328  jmp     short loc_18003F32F
0x18003f32a  mov     ebx, 80070057h
0x18003f32f  lea     rcx, [rsp+0C8h+var_A8]
0x18003f334  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003f33a  mov     eax, ebx
0x18003f33c  mov     rcx, [rsp+0C8h+var_28]
0x18003f344  xor     rcx, rsp; StackCookie
0x18003f347  call    __security_check_cookie
0x18003f34c  lea     r11, [rsp+0C8h+var_18]
0x18003f354  mov     rbx, [r11+30h]
0x18003f358  mov     rbp, [r11+38h]
0x18003f35c  mov     rsp, r11
0x18003f35f  pop     r14
0x18003f361  pop     rdi
0x18003f362  pop     rsi
0x18003f363  retn
```
