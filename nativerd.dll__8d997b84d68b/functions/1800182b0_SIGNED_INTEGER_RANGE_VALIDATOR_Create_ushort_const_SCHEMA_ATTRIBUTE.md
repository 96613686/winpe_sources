# SIGNED_INTEGER_RANGE_VALIDATOR::Create(ushort const *,SCHEMA_ATTRIBUTE *)

- ea: `0x1800182b0`
- end: `0x180018443`
- name: `?Create@SIGNED_INTEGER_RANGE_VALIDATOR@@UEAAJPEBGPEAVSCHEMA_ATTRIBUTE@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(SIGNED_INTEGER_RANGE_VALIDATOR *__hidden this, const unsigned __int16 *, struct SCHEMA_ATTRIBUTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1800182b0`
- `0x18001844c`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcschr` at `0x180018346`
- `msvcrt!wcschr` at `0x180018394`
- `msvcrt!wcschr` at `0x180018346`
- `msvcrt!wcschr` at `0x180018394`
- `msvcrt!_wcstoi64` at `0x18001837e`
- `msvcrt!_wcstoi64` at `0x1800183e9`
- `msvcrt!_wcstoi64` at `0x18001837e`
- `msvcrt!_wcstoi64` at `0x1800183e9`
- `msvcrt!iswspace` at `0x1800183ae`
- `msvcrt!iswspace` at `0x1800183ae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018413`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018413`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180018335`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180018335`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180018300`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180018300`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018320`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180018320`

## pseudocode

```c
__int64 __fastcall SIGNED_INTEGER_RANGE_VALIDATOR::Create(
        SIGNED_INTEGER_RANGE_VALIDATOR *this,
        const unsigned __int16 *a2,
        struct SCHEMA_ATTRIBUTE *a3)
{
  int v6; // ebx
  const wchar_t *Str; // rdi
  wchar_t *v8; // r14
  int v9; // eax
  const wchar_t *v10; // r14
  wchar_t *v11; // rax
  wint_t *v12; // rdi
  int v13; // eax
  _BYTE v15[64]; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int16 v16[32]; // [rsp+60h] [rbp-68h] BYREF

  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v15, v16, 0x20u);
  if ( !a2 || !a3 )
  {
    v6 = -2147024809;
    goto LABEL_13;
  }
  v6 = STRU::Copy((STRU *)v15, a2);
  if ( v6 >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v15);
    v8 = wcschr(Str, 0x2Cu);
    if ( !v8 )
    {
LABEL_5:
      v6 = -2147024883;
      goto LABEL_13;
    }
    *v8 = 0;
    v9 = IsNumberInHexFormat(Str);
    v10 = v8 + 1;
    *((_QWORD *)this + 2) = _wcstoi64(Str, 0, v9 != 0 ? 16 : 10);
    v11 = wcschr(v10, 0x2Cu);
    v12 = v11;
    if ( v11 )
    {
      *v11 = 0;
      do
        ++v12;
      while ( iswspace(*v12) );
      if ( wcscmp_0(v12, L"exclude") )
        goto LABEL_5;
      *((_DWORD *)this + 8) |= 1u;
    }
    v13 = IsNumberInHexFormat(v10);
    *((_QWORD *)this + 3) = _wcstoi64(v10, 0, v13 != 0 ? 16 : 10);
    *((_DWORD *)this + 8) = *((_DWORD *)this + 8) & 0xFFFFFFFD | (*((_DWORD *)a3 + 5) >> 4) & 2;
  }
LABEL_13:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800182b0  mov     [rsp+arg_10], rbx
0x1800182b5  mov     [rsp+arg_18], rbp
0x1800182ba  push    rsi
0x1800182bb  push    rdi
0x1800182bc  push    r14
0x1800182be  sub     rsp, 0B0h
0x1800182c5  mov     rax, cs:__security_cookie
0x1800182cc  xor     rax, rsp
0x1800182cf  mov     [rsp+0C8h+var_28], rax
0x1800182d7  mov     rbx, rdx
0x1800182da  mov     rbp, r8
0x1800182dd  xor     edx, edx; Val
0x1800182df  mov     rsi, rcx
0x1800182e2  lea     rcx, [rsp+0C8h+var_68]; void *
0x1800182e7  lea     r8d, [rdx+40h]; Size
0x1800182eb  call    memset_0
0x1800182f0  mov     r8d, 20h ; ' '
0x1800182f6  lea     rdx, [rsp+0C8h+var_68]
0x1800182fb  lea     rcx, [rsp+0C8h+var_A8]
0x180018300  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180018306  test    rbx, rbx
0x180018309  jz      loc_180018409
0x18001830f  test    rbp, rbp
0x180018312  jz      loc_180018409
0x180018318  mov     rdx, rbx
0x18001831b  lea     rcx, [rsp+0C8h+var_A8]
0x180018320  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180018326  mov     ebx, eax
0x180018328  test    eax, eax
0x18001832a  js      loc_18001840E
0x180018330  lea     rcx, [rsp+0C8h+var_A8]
0x180018335  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18001833b  mov     rcx, rax; Str
0x18001833e  mov     edx, 2Ch ; ','; Ch
0x180018343  mov     rdi, rax
0x180018346  call    cs:__imp_wcschr
0x18001834c  mov     r14, rax
0x18001834f  test    rax, rax
0x180018352  jnz     short loc_18001835E
0x180018354  mov     ebx, 8007000Dh
0x180018359  jmp     loc_18001840E
0x18001835e  xor     eax, eax
0x180018360  mov     rcx, rdi; unsigned __int16 *
0x180018363  mov     [r14], ax
0x180018367  call    ?IsNumberInHexFormat@@YAHPEBG@Z; IsNumberInHexFormat(ushort const *)
0x18001836c  neg     eax
0x18001836e  mov     rcx, rdi; String
0x180018371  sbb     r8d, r8d
0x180018374  xor     edx, edx; EndPtr
0x180018376  and     r8d, 6
0x18001837a  add     r8d, 0Ah; Radix
0x18001837e  call    cs:__imp__wcstoi64
0x180018384  add     r14, 2
0x180018388  mov     edx, 2Ch ; ','; Ch
0x18001838d  mov     rcx, r14; Str
0x180018390  mov     [rsi+10h], rax
0x180018394  call    cs:__imp_wcschr
0x18001839a  mov     rdi, rax
0x18001839d  test    rax, rax
0x1800183a0  jz      short loc_1800183CF
0x1800183a2  xor     ecx, ecx
0x1800183a4  mov     [rax], cx
0x1800183a7  add     rdi, 2
0x1800183ab  movzx   ecx, word ptr [rdi]; C
0x1800183ae  call    cs:__imp_iswspace
0x1800183b4  test    eax, eax
0x1800183b6  jnz     short loc_1800183A7
0x1800183b8  lea     rdx, aExclude; "exclude"
0x1800183bf  mov     rcx, rdi; String1
0x1800183c2  call    wcscmp_0
0x1800183c7  test    eax, eax
0x1800183c9  jnz     short loc_180018354
0x1800183cb  or      dword ptr [rsi+20h], 1
0x1800183cf  mov     rcx, r14; unsigned __int16 *
0x1800183d2  call    ?IsNumberInHexFormat@@YAHPEBG@Z; IsNumberInHexFormat(ushort const *)
0x1800183d7  neg     eax
0x1800183d9  mov     rcx, r14; String
0x1800183dc  sbb     r8d, r8d
0x1800183df  xor     edx, edx; EndPtr
0x1800183e1  and     r8d, 6
0x1800183e5  add     r8d, 0Ah; Radix
0x1800183e9  call    cs:__imp__wcstoi64
0x1800183ef  mov     [rsi+18h], rax
0x1800183f3  mov     ecx, [rbp+14h]
0x1800183f6  mov     eax, [rsi+20h]
0x1800183f9  shr     ecx, 4
0x1800183fc  and     eax, 0FFFFFFFDh
0x1800183ff  and     ecx, 2
0x180018402  or      ecx, eax
0x180018404  mov     [rsi+20h], ecx
0x180018407  jmp     short loc_18001840E
0x180018409  mov     ebx, 80070057h
0x18001840e  lea     rcx, [rsp+0C8h+var_A8]
0x180018413  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180018419  mov     eax, ebx
0x18001841b  mov     rcx, [rsp+0C8h+var_28]
0x180018423  xor     rcx, rsp; StackCookie
0x180018426  call    __security_check_cookie
0x18001842b  lea     r11, [rsp+0C8h+var_18]
0x180018433  mov     rbx, [r11+30h]
0x180018437  mov     rbp, [r11+38h]
0x18001843b  mov     rsp, r11
0x18001843e  pop     r14
0x180018440  pop     rdi
0x180018441  pop     rsi
0x180018442  retn
```
