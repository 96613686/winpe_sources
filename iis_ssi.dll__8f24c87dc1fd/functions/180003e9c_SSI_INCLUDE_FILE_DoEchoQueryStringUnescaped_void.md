# SSI_INCLUDE_FILE::DoEchoQueryStringUnescaped(void)

- ea: `0x180003e9c`
- end: `0x180003fa3`
- name: `?DoEchoQueryStringUnescaped@SSI_INCLUDE_FILE@@AEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(SSI_INCLUDE_FILE *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004afc`

## callees

- `0x180003e9c`
- `0x180005620`
- `0x180005780`
- `0x180006010`

## import_xrefs

- `iisutil!?Unescape@STRA@@QEAAJXZ` at `0x180003f49`
- `iisutil!?Unescape@STRA@@QEAAJXZ` at `0x180003f49`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180003f24`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180003f24`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f76`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180003f76`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003f38`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180003f38`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003ed3`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003ed3`

## pseudocode

```c
__int64 __fastcall SSI_INCLUDE_FILE::DoEchoQueryStringUnescaped(SSI_INCLUDE_FILE *this)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rdx
  int v5; // eax
  int v6; // ebx
  _BYTE v8[32]; // [rsp+20h] [rbp-E8h] BYREF
  char *Src; // [rsp+40h] [rbp-C8h]
  unsigned int v10; // [rsp+50h] [rbp-B8h]
  char v11[144]; // [rsp+60h] [rbp-A8h] BYREF

  STRA::STRA((STRA *)v8, v11, 0x81u);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 2) + 8LL) + 24LL))(*(_QWORD *)(*((_QWORD *)this + 2) + 8LL));
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v4 = *(_QWORD *)(v3 + 96);
  if ( v4 && *(_WORD *)(v3 + 70) )
    v5 = STRA::CopyWTruncate((STRA *)v8, (const unsigned __int16 *)(v4 + 2), (*(unsigned __int16 *)(v3 + 70) >> 1) - 1);
  else
    v5 = STRA::Copy((STRA *)v8, (const char *)qword_180007F90);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = STRA::Unescape((STRA *)v8);
    if ( v6 >= 0 )
      v6 = SSI_VECTOR_BUFFER::CopyToVector((SSI_VECTOR_BUFFER *)(*((_QWORD *)this + 2) + 800LL), Src, v10);
  }
  STRA::~STRA((STRA *)v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003e9c  mov     [rsp+arg_8], rbx
0x180003ea1  mov     [rsp+arg_10], rsi
0x180003ea6  push    rdi
0x180003ea7  sub     rsp, 100h
0x180003eae  mov     rax, cs:__security_cookie
0x180003eb5  xor     rax, rsp
0x180003eb8  mov     [rsp+108h+var_18], rax
0x180003ec0  mov     rdi, rcx
0x180003ec3  lea     rdx, [rsp+108h+var_A8]
0x180003ec8  lea     rcx, [rsp+108h+var_E8]
0x180003ecd  mov     r8d, 81h
0x180003ed3  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180003ed9  mov     rax, [rdi+10h]
0x180003edd  mov     rcx, [rax+8]
0x180003ee1  mov     rax, [rcx]
0x180003ee4  mov     rax, [rax+18h]
0x180003ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eed  mov     rdx, rax
0x180003ef0  mov     rcx, [rax]
0x180003ef3  mov     rax, [rcx+8]
0x180003ef7  mov     rcx, rdx
0x180003efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eff  xor     esi, esi
0x180003f01  mov     rdx, [rax+60h]
0x180003f05  test    rdx, rdx
0x180003f08  jz      short loc_180003F2C
0x180003f0a  cmp     [rax+46h], si
0x180003f0e  jz      short loc_180003F2C
0x180003f10  movzx   r8d, word ptr [rax+46h]
0x180003f15  lea     rcx, [rsp+108h+var_E8]
0x180003f1a  shr     r8d, 1
0x180003f1d  add     rdx, 2
0x180003f21  dec     r8d
0x180003f24  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x180003f2a  jmp     short loc_180003F3E
0x180003f2c  lea     rdx, qword_180007F90
0x180003f33  lea     rcx, [rsp+108h+var_E8]
0x180003f38  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180003f3e  lea     rcx, [rsp+108h+var_E8]
0x180003f43  mov     ebx, eax
0x180003f45  test    eax, eax
0x180003f47  js      short loc_180003F76
0x180003f49  call    cs:__imp_?Unescape@STRA@@QEAAJXZ; STRA::Unescape(void)
0x180003f4f  mov     ebx, eax
0x180003f51  test    eax, eax
0x180003f53  js      short loc_180003F71
0x180003f55  mov     rcx, [rdi+10h]
0x180003f59  mov     r8d, [rsp+108h+var_B8]; unsigned int
0x180003f5e  add     rcx, 320h; this
0x180003f65  mov     rdx, [rsp+108h+Src]; Src
0x180003f6a  call    ?CopyToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::CopyToVector(char *,ulong)
0x180003f6f  mov     ebx, eax
0x180003f71  lea     rcx, [rsp+108h+var_E8]
0x180003f76  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180003f7c  mov     eax, ebx
0x180003f7e  mov     rcx, [rsp+108h+var_18]
0x180003f86  xor     rcx, rsp; StackCookie
0x180003f89  call    __security_check_cookie
0x180003f8e  lea     r11, [rsp+108h+var_8]
0x180003f96  mov     rbx, [r11+18h]
0x180003f9a  mov     rsi, [r11+20h]
0x180003f9e  mov     rsp, r11
0x180003fa1  pop     rdi
0x180003fa2  retn
```
