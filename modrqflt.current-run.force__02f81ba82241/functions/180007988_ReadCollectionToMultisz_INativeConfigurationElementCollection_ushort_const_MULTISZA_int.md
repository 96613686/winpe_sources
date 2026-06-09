# ReadCollectionToMultisz(INativeConfigurationElementCollection *,ushort const *,MULTISZA *,int)

- ea: `0x180007988`
- end: `0x180007b0f`
- name: `?ReadCollectionToMultisz@@YAJPEAVINativeConfigurationElementCollection@@PEBGPEAVMULTISZA@@H@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct INativeConfigurationElementCollection *, const unsigned __int16 *, struct MULTISZA *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005050`

## callees

- `0x180007988`
- `0x180007bc0`
- `0x180008010`

## import_xrefs

- `msvcrt!_strlwr` at `0x180007a6c`
- `msvcrt!_strlwr` at `0x180007a6c`
- `iisutil!?Reset@MULTISZA@@QEAAXXZ` at `0x180007ad9`
- `iisutil!?Reset@MULTISZA@@QEAAXXZ` at `0x180007ad9`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007aaf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007ae3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007aaf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180007ae3`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180007a53`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180007a53`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800079d1`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800079d1`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180007a82`
- `iisutil!?Append@MULTISZA@@QEAAHPEBD@Z` at `0x180007a82`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007a63`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007a76`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007a63`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180007a76`

## pseudocode

```c
__int64 __fastcall ReadCollectionToMultisz(
        struct INativeConfigurationElementCollection *a1,
        const unsigned __int16 *a2,
        struct MULTISZA *a3)
{
  int v5; // ebx
  unsigned int i; // edi
  char *Str; // rax
  const char *v8; // rax
  __int64 v10; // [rsp+30h] [rbp-19h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-11h] BYREF
  const unsigned __int16 *v12; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v13[56]; // [rsp+48h] [rbp-1h] BYREF

  v10 = 0;
  v11 = 0;
  v12 = 0;
  STRA::STRA((STRA *)v13);
  v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, unsigned int *))(*(_QWORD *)a1 + 24LL))(
         a1,
         &v11);
  if ( v5 < 0 )
  {
LABEL_10:
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    MULTISZA::Reset(a3);
    STRA::~STRA((STRA *)v13);
    return (unsigned int)v5;
  }
  else
  {
    for ( i = 0; i < v11; ++i )
    {
      v5 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, __int64 *))(*(_QWORD *)a1 + 32LL))(
             a1,
             i,
             &v10);
      if ( v5 < 0 )
        goto LABEL_10;
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(
             v10,
             L"requestHeader",
             &v12,
             0,
             0);
      if ( v5 < 0 )
        goto LABEL_10;
      v5 = STRA::CopyW((STRA *)v13, v12);
      if ( v5 < 0 )
        goto LABEL_10;
      Str = STRA::QueryStr((STRA *)v13);
      _strlwr(Str);
      v8 = STRA::QueryStr((STRA *)v13);
      if ( !MULTISZA::Append(a3, v8) )
        goto LABEL_10;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    STRA::~STRA((STRA *)v13);
    return 0;
  }
}

```

## disassembly

```asm
0x180007988  mov     [rsp-8+arg_8], rbx
0x18000798d  mov     [rsp-8+arg_18], rsi
0x180007992  push    rbp
0x180007993  push    rdi
0x180007994  push    r14
0x180007996  lea     rbp, [rsp-47h]
0x18000799b  sub     rsp, 90h
0x1800079a2  mov     rax, cs:__security_cookie
0x1800079a9  xor     rax, rsp
0x1800079ac  mov     [rbp+57h+var_20], rax
0x1800079b0  mov     rsi, rcx
0x1800079b3  mov     [rbp+57h+var_70], 0
0x1800079bb  lea     rcx, [rbp+57h+var_58]
0x1800079bf  mov     [rbp+57h+var_68], 0
0x1800079c6  mov     r14, r8
0x1800079c9  mov     [rbp+57h+var_60], 0
0x1800079d1  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800079d7  mov     rax, [rsi]
0x1800079da  lea     rdx, [rbp+57h+var_68]
0x1800079de  mov     rcx, rsi
0x1800079e1  mov     rax, [rax+18h]
0x1800079e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ea  mov     ebx, eax
0x1800079ec  test    eax, eax
0x1800079ee  js      loc_180007AB9
0x1800079f4  xor     edi, edi
0x1800079f6  cmp     edi, [rbp+57h+var_68]
0x1800079f9  jnb     loc_180007AAB
0x1800079ff  mov     rax, [rsi]
0x180007a02  lea     r8, [rbp+57h+var_70]
0x180007a06  mov     edx, edi
0x180007a08  mov     rcx, rsi
0x180007a0b  mov     rax, [rax+20h]
0x180007a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a14  mov     ebx, eax
0x180007a16  test    eax, eax
0x180007a18  js      loc_180007AB9
0x180007a1e  mov     rcx, [rbp+57h+var_70]
0x180007a22  lea     r8, [rbp+57h+var_60]
0x180007a26  xor     r9d, r9d
0x180007a29  mov     [rsp+0A0h+var_80], 0
0x180007a32  lea     rdx, aRequestheader; "requestHeader"
0x180007a39  mov     rax, [rcx]
0x180007a3c  mov     rax, [rax+40h]
0x180007a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a45  mov     ebx, eax
0x180007a47  test    eax, eax
0x180007a49  js      short loc_180007AB9
0x180007a4b  mov     rdx, [rbp+57h+var_60]
0x180007a4f  lea     rcx, [rbp+57h+var_58]
0x180007a53  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x180007a59  mov     ebx, eax
0x180007a5b  test    eax, eax
0x180007a5d  js      short loc_180007AB9
0x180007a5f  lea     rcx, [rbp+57h+var_58]
0x180007a63  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007a69  mov     rcx, rax; String
0x180007a6c  call    cs:__imp__strlwr
0x180007a72  lea     rcx, [rbp+57h+var_58]
0x180007a76  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180007a7c  mov     rdx, rax
0x180007a7f  mov     rcx, r14
0x180007a82  call    cs:__imp_?Append@MULTISZA@@QEAAHPEBD@Z; MULTISZA::Append(char const *)
0x180007a88  test    eax, eax
0x180007a8a  jz      short loc_180007AB9
0x180007a8c  mov     rcx, [rbp+57h+var_70]
0x180007a90  mov     rax, [rcx]
0x180007a93  mov     rax, [rax+10h]
0x180007a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9c  inc     edi
0x180007a9e  mov     [rbp+57h+var_70], 0
0x180007aa6  jmp     loc_1800079F6
0x180007aab  lea     rcx, [rbp+57h+var_58]
0x180007aaf  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007ab5  xor     eax, eax
0x180007ab7  jmp     short loc_180007AEB
0x180007ab9  mov     rcx, [rbp+57h+var_70]
0x180007abd  test    rcx, rcx
0x180007ac0  jz      short loc_180007AD6
0x180007ac2  mov     rax, [rcx]
0x180007ac5  mov     rax, [rax+10h]
0x180007ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ace  mov     [rbp+57h+var_70], 0
0x180007ad6  mov     rcx, r14
0x180007ad9  call    cs:__imp_?Reset@MULTISZA@@QEAAXXZ; MULTISZA::Reset(void)
0x180007adf  lea     rcx, [rbp+57h+var_58]
0x180007ae3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007ae9  mov     eax, ebx
0x180007aeb  mov     rcx, [rbp+57h+var_20]
0x180007aef  xor     rcx, rsp; StackCookie
0x180007af2  call    __security_check_cookie
0x180007af7  lea     r11, [rsp+0A0h+var_10]
0x180007aff  mov     rbx, [r11+28h]
0x180007b03  mov     rsi, [r11+38h]
0x180007b07  mov     rsp, r11
0x180007b0a  pop     r14
0x180007b0c  pop     rdi
0x180007b0d  pop     rbp
0x180007b0e  retn
```
