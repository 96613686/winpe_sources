# ReadCollectionToMultisz(INativeConfigurationElementCollection *,ushort const *,MULTISZ *,int)

- ea: `0x1800077f8`
- end: `0x18000797f`
- name: `?ReadCollectionToMultisz@@YAJPEAVINativeConfigurationElementCollection@@PEBGPEAVMULTISZ@@H@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct INativeConfigurationElementCollection *, const unsigned __int16 *, struct MULTISZ *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180005050`

## callees

- `0x1800077f8`
- `0x180007bc0`
- `0x180008010`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800078d9`
- `msvcrt!_wcslwr` at `0x1800078d9`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000794a`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x18000794a`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800078f3`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800078f3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007842`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007842`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007920`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007954`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007920`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007954`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800078d0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800078e3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800078d0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800078e3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800078c0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800078c0`

## pseudocode

```c
__int64 __fastcall ReadCollectionToMultisz(
        struct INativeConfigurationElementCollection *a1,
        const unsigned __int16 *a2,
        struct MULTISZ *a3)
{
  int v6; // ebx
  unsigned int i; // edi
  wchar_t *Str; // rax
  __int64 v10; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v11; // [rsp+38h] [rbp-21h] BYREF
  const unsigned __int16 *v12; // [rsp+40h] [rbp-19h] BYREF
  _BYTE v13[56]; // [rsp+48h] [rbp-11h] BYREF

  v10 = 0;
  v11 = 0;
  v12 = 0;
  STRU::STRU((STRU *)v13);
  v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, unsigned int *))(*(_QWORD *)a1 + 24LL))(
         a1,
         &v11);
  if ( v6 < 0 )
  {
LABEL_10:
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    MULTISZ::Reset(a3);
    STRU::~STRU((STRU *)v13);
    return (unsigned int)v6;
  }
  else
  {
    for ( i = 0; i < v11; ++i )
    {
      v6 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, __int64 *))(*(_QWORD *)a1 + 32LL))(
             a1,
             i,
             &v10);
      if ( v6 < 0 )
        goto LABEL_10;
      v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(
             v10,
             a2,
             &v12,
             0,
             0);
      if ( v6 < 0 )
        goto LABEL_10;
      v6 = STRU::Copy((STRU *)v13, v12);
      if ( v6 < 0 )
        goto LABEL_10;
      Str = STRU::QueryStr((STRU *)v13);
      _wcslwr(Str);
      v12 = STRU::QueryStr((STRU *)v13);
      if ( !MULTISZ::Append(a3, v12) )
        goto LABEL_10;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    STRU::~STRU((STRU *)v13);
    return 0;
  }
}

```

## disassembly

```asm
0x1800077f8  mov     [rsp-8+arg_18], rbx
0x1800077fd  push    rbp
0x1800077fe  push    rsi
0x1800077ff  push    rdi
0x180007800  push    r14
0x180007802  push    r15
0x180007804  lea     rbp, [rsp-37h]
0x180007809  sub     rsp, 90h
0x180007810  mov     rax, cs:__security_cookie
0x180007817  xor     rax, rsp
0x18000781a  mov     [rbp+57h+var_30], rax
0x18000781e  mov     rsi, rcx
0x180007821  mov     [rbp+57h+var_80], 0
0x180007829  lea     rcx, [rbp+57h+var_68]
0x18000782d  mov     [rbp+57h+var_78], 0
0x180007834  mov     r14, r8
0x180007837  mov     [rbp+57h+var_70], 0
0x18000783f  mov     r15, rdx
0x180007842  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007848  mov     rax, [rsi]
0x18000784b  lea     rdx, [rbp+57h+var_78]
0x18000784f  mov     rcx, rsi
0x180007852  mov     rax, [rax+18h]
0x180007856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785b  mov     ebx, eax
0x18000785d  test    eax, eax
0x18000785f  js      loc_18000792A
0x180007865  xor     edi, edi
0x180007867  cmp     edi, [rbp+57h+var_78]
0x18000786a  jnb     loc_18000791C
0x180007870  mov     rax, [rsi]
0x180007873  lea     r8, [rbp+57h+var_80]
0x180007877  mov     edx, edi
0x180007879  mov     rcx, rsi
0x18000787c  mov     rax, [rax+20h]
0x180007880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007885  mov     ebx, eax
0x180007887  test    eax, eax
0x180007889  js      loc_18000792A
0x18000788f  mov     rcx, [rbp+57h+var_80]
0x180007893  lea     r8, [rbp+57h+var_70]
0x180007897  xor     r9d, r9d
0x18000789a  mov     [rsp+0B0h+var_90], 0
0x1800078a3  mov     rdx, r15
0x1800078a6  mov     rax, [rcx]
0x1800078a9  mov     rax, [rax+40h]
0x1800078ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078b2  mov     ebx, eax
0x1800078b4  test    eax, eax
0x1800078b6  js      short loc_18000792A
0x1800078b8  mov     rdx, [rbp+57h+var_70]
0x1800078bc  lea     rcx, [rbp+57h+var_68]
0x1800078c0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800078c6  mov     ebx, eax
0x1800078c8  test    eax, eax
0x1800078ca  js      short loc_18000792A
0x1800078cc  lea     rcx, [rbp+57h+var_68]
0x1800078d0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800078d6  mov     rcx, rax; String
0x1800078d9  call    cs:__imp__wcslwr
0x1800078df  lea     rcx, [rbp+57h+var_68]
0x1800078e3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800078e9  mov     rdx, rax
0x1800078ec  mov     [rbp+57h+var_70], rax
0x1800078f0  mov     rcx, r14
0x1800078f3  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800078f9  test    eax, eax
0x1800078fb  jz      short loc_18000792A
0x1800078fd  mov     rcx, [rbp+57h+var_80]
0x180007901  mov     rax, [rcx]
0x180007904  mov     rax, [rax+10h]
0x180007908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000790d  inc     edi
0x18000790f  mov     [rbp+57h+var_80], 0
0x180007917  jmp     loc_180007867
0x18000791c  lea     rcx, [rbp+57h+var_68]
0x180007920  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007926  xor     eax, eax
0x180007928  jmp     short loc_18000795C
0x18000792a  mov     rcx, [rbp+57h+var_80]
0x18000792e  test    rcx, rcx
0x180007931  jz      short loc_180007947
0x180007933  mov     rax, [rcx]
0x180007936  mov     rax, [rax+10h]
0x18000793a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000793f  mov     [rbp+57h+var_80], 0
0x180007947  mov     rcx, r14
0x18000794a  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180007950  lea     rcx, [rbp+57h+var_68]
0x180007954  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000795a  mov     eax, ebx
0x18000795c  mov     rcx, [rbp+57h+var_30]
0x180007960  xor     rcx, rsp; StackCookie
0x180007963  call    __security_check_cookie
0x180007968  mov     rbx, [rsp+0B0h+arg_18]
0x180007970  add     rsp, 90h
0x180007977  pop     r15
0x180007979  pop     r14
0x18000797b  pop     rdi
0x18000797c  pop     rsi
0x18000797d  pop     rbp
0x18000797e  retn
```
