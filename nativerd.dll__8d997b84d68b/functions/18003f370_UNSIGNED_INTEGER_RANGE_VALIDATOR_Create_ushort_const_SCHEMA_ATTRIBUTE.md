# UNSIGNED_INTEGER_RANGE_VALIDATOR::Create(ushort const *,SCHEMA_ATTRIBUTE *)

- ea: `0x18003f370`
- end: `0x18003f503`
- name: `?Create@UNSIGNED_INTEGER_RANGE_VALIDATOR@@UEAAJPEBGPEAVSCHEMA_ATTRIBUTE@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(UNSIGNED_INTEGER_RANGE_VALIDATOR *__hidden this, const unsigned __int16 *, struct SCHEMA_ATTRIBUTE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18001844c`
- `0x18003f370`
- `0x180059bea`
- `0x180059bf6`
- `0x180059c30`

## import_xrefs

- `msvcrt!wcschr` at `0x18003f406`
- `msvcrt!wcschr` at `0x18003f454`
- `msvcrt!wcschr` at `0x18003f406`
- `msvcrt!wcschr` at `0x18003f454`
- `msvcrt!_wcstoui64` at `0x18003f43e`
- `msvcrt!_wcstoui64` at `0x18003f4a9`
- `msvcrt!_wcstoui64` at `0x18003f43e`
- `msvcrt!_wcstoui64` at `0x18003f4a9`
- `msvcrt!iswspace` at `0x18003f46e`
- `msvcrt!iswspace` at `0x18003f46e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003f4d3`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003f4d3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003f3f5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003f3f5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003f3c0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003f3c0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003f3e0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003f3e0`

## pseudocode

```c
__int64 __fastcall UNSIGNED_INTEGER_RANGE_VALIDATOR::Create(
        UNSIGNED_INTEGER_RANGE_VALIDATOR *this,
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
    *((_QWORD *)this + 2) = _wcstoui64(Str, 0, v9 != 0 ? 16 : 10);
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
    *((_QWORD *)this + 3) = _wcstoui64(v10, 0, v13 != 0 ? 16 : 10);
    *((_DWORD *)this + 8) = *((_DWORD *)this + 8) & 0xFFFFFFFD | (*((_DWORD *)a3 + 5) >> 4) & 2;
  }
LABEL_13:
  STRU::~STRU((STRU *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003f370  mov     [rsp+arg_10], rbx
0x18003f375  mov     [rsp+arg_18], rbp
0x18003f37a  push    rsi
0x18003f37b  push    rdi
0x18003f37c  push    r14
0x18003f37e  sub     rsp, 0B0h
0x18003f385  mov     rax, cs:__security_cookie
0x18003f38c  xor     rax, rsp
0x18003f38f  mov     [rsp+0C8h+var_28], rax
0x18003f397  mov     rbx, rdx
0x18003f39a  mov     rbp, r8
0x18003f39d  xor     edx, edx; Val
0x18003f39f  mov     rsi, rcx
0x18003f3a2  lea     rcx, [rsp+0C8h+var_68]; void *
0x18003f3a7  lea     r8d, [rdx+40h]; Size
0x18003f3ab  call    memset_0
0x18003f3b0  mov     r8d, 20h ; ' '
0x18003f3b6  lea     rdx, [rsp+0C8h+var_68]
0x18003f3bb  lea     rcx, [rsp+0C8h+var_A8]
0x18003f3c0  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003f3c6  test    rbx, rbx
0x18003f3c9  jz      loc_18003F4C9
0x18003f3cf  test    rbp, rbp
0x18003f3d2  jz      loc_18003F4C9
0x18003f3d8  mov     rdx, rbx
0x18003f3db  lea     rcx, [rsp+0C8h+var_A8]
0x18003f3e0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003f3e6  mov     ebx, eax
0x18003f3e8  test    eax, eax
0x18003f3ea  js      loc_18003F4CE
0x18003f3f0  lea     rcx, [rsp+0C8h+var_A8]
0x18003f3f5  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003f3fb  mov     rcx, rax; Str
0x18003f3fe  mov     edx, 2Ch ; ','; Ch
0x18003f403  mov     rdi, rax
0x18003f406  call    cs:__imp_wcschr
0x18003f40c  mov     r14, rax
0x18003f40f  test    rax, rax
0x18003f412  jnz     short loc_18003F41E
0x18003f414  mov     ebx, 8007000Dh
0x18003f419  jmp     loc_18003F4CE
0x18003f41e  xor     eax, eax
0x18003f420  mov     rcx, rdi; unsigned __int16 *
0x18003f423  mov     [r14], ax
0x18003f427  call    ?IsNumberInHexFormat@@YAHPEBG@Z; IsNumberInHexFormat(ushort const *)
0x18003f42c  neg     eax
0x18003f42e  mov     rcx, rdi; String
0x18003f431  sbb     r8d, r8d
0x18003f434  xor     edx, edx; EndPtr
0x18003f436  and     r8d, 6
0x18003f43a  add     r8d, 0Ah; Radix
0x18003f43e  call    cs:__imp__wcstoui64
0x18003f444  add     r14, 2
0x18003f448  mov     edx, 2Ch ; ','; Ch
0x18003f44d  mov     rcx, r14; Str
0x18003f450  mov     [rsi+10h], rax
0x18003f454  call    cs:__imp_wcschr
0x18003f45a  mov     rdi, rax
0x18003f45d  test    rax, rax
0x18003f460  jz      short loc_18003F48F
0x18003f462  xor     ecx, ecx
0x18003f464  mov     [rax], cx
0x18003f467  add     rdi, 2
0x18003f46b  movzx   ecx, word ptr [rdi]; C
0x18003f46e  call    cs:__imp_iswspace
0x18003f474  test    eax, eax
0x18003f476  jnz     short loc_18003F467
0x18003f478  lea     rdx, aExclude; "exclude"
0x18003f47f  mov     rcx, rdi; String1
0x18003f482  call    wcscmp_0
0x18003f487  test    eax, eax
0x18003f489  jnz     short loc_18003F414
0x18003f48b  or      dword ptr [rsi+20h], 1
0x18003f48f  mov     rcx, r14; unsigned __int16 *
0x18003f492  call    ?IsNumberInHexFormat@@YAHPEBG@Z; IsNumberInHexFormat(ushort const *)
0x18003f497  neg     eax
0x18003f499  mov     rcx, r14; String
0x18003f49c  sbb     r8d, r8d
0x18003f49f  xor     edx, edx; EndPtr
0x18003f4a1  and     r8d, 6
0x18003f4a5  add     r8d, 0Ah; Radix
0x18003f4a9  call    cs:__imp__wcstoui64
0x18003f4af  mov     [rsi+18h], rax
0x18003f4b3  mov     ecx, [rbp+14h]
0x18003f4b6  mov     eax, [rsi+20h]
0x18003f4b9  shr     ecx, 4
0x18003f4bc  and     eax, 0FFFFFFFDh
0x18003f4bf  and     ecx, 2
0x18003f4c2  or      ecx, eax
0x18003f4c4  mov     [rsi+20h], ecx
0x18003f4c7  jmp     short loc_18003F4CE
0x18003f4c9  mov     ebx, 80070057h
0x18003f4ce  lea     rcx, [rsp+0C8h+var_A8]
0x18003f4d3  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003f4d9  mov     eax, ebx
0x18003f4db  mov     rcx, [rsp+0C8h+var_28]
0x18003f4e3  xor     rcx, rsp; StackCookie
0x18003f4e6  call    __security_check_cookie
0x18003f4eb  lea     r11, [rsp+0C8h+var_18]
0x18003f4f3  mov     rbx, [r11+30h]
0x18003f4f7  mov     rbp, [r11+38h]
0x18003f4fb  mov     rsp, r11
0x18003f4fe  pop     r14
0x18003f500  pop     rdi
0x18003f501  pop     rsi
0x18003f502  retn
```
