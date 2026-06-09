# FTP_BINDINGS_CONFIG::EncodeHostNameIfIDN(STRU *)

- ea: `0x180043de0`
- end: `0x180043f71`
- name: `?EncodeHostNameIfIDN@FTP_BINDINGS_CONFIG@@AEAAJPEAVSTRU@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(FTP_BINDINGS_CONFIG *__hidden this, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180045730`

## callees

- `0x180043de0`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180043e9a`
- `KERNEL32!GetLastError` at `0x180043ed9`
- `KERNEL32!GetLastError` at `0x180043e9a`
- `KERNEL32!GetLastError` at `0x180043ed9`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180043e69`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180043e69`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180043e30`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180043e5a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180043e30`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180043e5a`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x180043f1a`
- `iisutil!?Equals@STRU@@QEBA_NAEBV1@@Z` at `0x180043f1a`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180043f2c`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180043f2c`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180043eac`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180043eac`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180043f39`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180043f45`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180043f39`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180043f45`
- `Normaliz!IdnToAscii` at `0x180043e90`
- `Normaliz!IdnToAscii` at `0x180043ecf`
- `Normaliz!IdnToAscii` at `0x180043e90`
- `Normaliz!IdnToAscii` at `0x180043ecf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_BINDINGS_CONFIG::EncodeHostNameIfIDN(FTP_BINDINGS_CONFIG *this, struct STRU *a2)
{
  signed int v3; // ebx
  int v4; // eax
  signed int LastError; // eax
  __int64 v6; // r9
  _BYTE v8[32]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR lpASCIICharStr; // [rsp+50h] [rbp-B0h]
  unsigned int v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+60h] [rbp-A0h]
  _BYTE v12[32]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpUnicodeCharStr; // [rsp+88h] [rbp-78h]
  unsigned __int16 v14[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v15[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(v14, 0, 0x208u);
  STRU::STRU((STRU *)v12, v14, 0x104u);
  memset_0(v15, 0, 0x208u);
  STRU::STRU((STRU *)v8, v15, 0x104u);
  v3 = STRU::Copy((STRU *)v12, a2);
  if ( v3 >= 0 )
  {
    v4 = IdnToAscii(0, lpUnicodeCharStr, -1, lpASCIICharStr, 260);
    if ( v4 )
      goto LABEL_8;
    if ( GetLastError() != 122 )
      goto LABEL_6;
    v3 = STRU::Resize((STRU *)v8, 0);
    if ( v3 < 0 )
      goto LABEL_12;
    v4 = IdnToAscii(0, lpUnicodeCharStr, -1, lpASCIICharStr, 260);
    if ( v4 )
    {
LABEL_8:
      v6 = (unsigned int)(v4 - 1);
      if ( (unsigned int)v6 < v10 >> 1 )
      {
        lpASCIICharStr[v6] = 0;
        v11 = v4 - 1;
      }
      if ( !STRU::Equals((STRU *)v12, (const struct STRU *)v8) )
        v3 = STRU::Copy(a2, (const struct STRU *)v8);
    }
    else
    {
LABEL_6:
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_12:
  STRU::~STRU(v8);
  STRU::~STRU(v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180043de0  mov     [rsp-8+arg_0], rbx
0x180043de5  mov     [rsp-8+arg_10], rdi
0x180043dea  push    rbp
0x180043deb  lea     rbp, [rsp-3D0h]
0x180043df3  sub     rsp, 4D0h
0x180043dfa  mov     rax, cs:__security_cookie
0x180043e01  xor     rax, rsp
0x180043e04  mov     [rbp+3D0h+var_10], rax
0x180043e0b  mov     rdi, rdx
0x180043e0e  mov     ebx, 208h
0x180043e13  mov     r8d, ebx; Size
0x180043e16  xor     edx, edx; Val
0x180043e18  lea     rcx, [rbp+3D0h+var_430]; void *
0x180043e1c  call    memset_0
0x180043e21  mov     r8d, 104h
0x180043e27  lea     rdx, [rbp+3D0h+var_430]
0x180043e2b  lea     rcx, [rsp+4D0h+var_468]
0x180043e30  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180043e36  nop
0x180043e37  mov     r8d, ebx; Size
0x180043e3a  xor     edx, edx; Val
0x180043e3c  lea     rcx, [rbp+3D0h+var_220]; void *
0x180043e43  call    memset_0
0x180043e48  mov     r8d, 104h
0x180043e4e  lea     rdx, [rbp+3D0h+var_220]
0x180043e55  lea     rcx, [rsp+4D0h+var_4A0]
0x180043e5a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180043e60  nop
0x180043e61  mov     rdx, rdi
0x180043e64  lea     rcx, [rsp+4D0h+var_468]
0x180043e69  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x180043e6f  mov     ebx, eax
0x180043e71  test    eax, eax
0x180043e73  js      loc_180043F34
0x180043e79  mov     [rsp+4D0h+cchASCIIChar], 104h; cchASCIIChar
0x180043e81  mov     r9, [rsp+4D0h+lpASCIICharStr]; lpASCIICharStr
0x180043e86  or      r8d, 0FFFFFFFFh; cchUnicodeChar
0x180043e8a  mov     rdx, [rbp+3D0h+lpUnicodeCharStr]; lpUnicodeCharStr
0x180043e8e  xor     ecx, ecx; dwFlags
0x180043e90  call    cs:__imp_IdnToAscii
0x180043e96  test    eax, eax
0x180043e98  jnz     short loc_180043EF0
0x180043e9a  call    cs:__imp_GetLastError
0x180043ea0  cmp     eax, 7Ah ; 'z'
0x180043ea3  jnz     short loc_180043ED9
0x180043ea5  xor     edx, edx
0x180043ea7  lea     rcx, [rsp+4D0h+var_4A0]
0x180043eac  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180043eb2  mov     ebx, eax
0x180043eb4  test    eax, eax
0x180043eb6  js      short loc_180043F34
0x180043eb8  mov     [rsp+4D0h+cchASCIIChar], 104h; cchASCIIChar
0x180043ec0  mov     r9, [rsp+4D0h+lpASCIICharStr]; lpASCIICharStr
0x180043ec5  or      r8d, 0FFFFFFFFh; cchUnicodeChar
0x180043ec9  mov     rdx, [rbp+3D0h+lpUnicodeCharStr]; lpUnicodeCharStr
0x180043ecd  xor     ecx, ecx; dwFlags
0x180043ecf  call    cs:__imp_IdnToAscii
0x180043ed5  test    eax, eax
0x180043ed7  jnz     short loc_180043EF0
0x180043ed9  call    cs:__imp_GetLastError
0x180043edf  mov     ebx, eax
0x180043ee1  test    eax, eax
0x180043ee3  jle     short loc_180043F34
0x180043ee5  movzx   ebx, ax
0x180043ee8  or      ebx, 80070000h
0x180043eee  jmp     short loc_180043F34
0x180043ef0  lea     r9d, [rax-1]
0x180043ef4  mov     eax, [rsp+4D0h+var_478]
0x180043ef8  shr     eax, 1
0x180043efa  cmp     r9d, eax
0x180043efd  jnb     short loc_180043F10
0x180043eff  xor     edx, edx
0x180043f01  mov     rax, [rsp+4D0h+lpASCIICharStr]
0x180043f06  mov     [rax+r9*2], dx
0x180043f0b  mov     [rsp+4D0h+var_470], r9d
0x180043f10  lea     rdx, [rsp+4D0h+var_4A0]
0x180043f15  lea     rcx, [rsp+4D0h+var_468]
0x180043f1a  call    cs:__imp_?Equals@STRU@@QEBA_NAEBV1@@Z; STRU::Equals(STRU const &)
0x180043f20  test    al, al
0x180043f22  jnz     short loc_180043F34
0x180043f24  lea     rdx, [rsp+4D0h+var_4A0]
0x180043f29  mov     rcx, rdi
0x180043f2c  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180043f32  mov     ebx, eax
0x180043f34  lea     rcx, [rsp+4D0h+var_4A0]
0x180043f39  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180043f3f  nop
0x180043f40  lea     rcx, [rsp+4D0h+var_468]
0x180043f45  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180043f4b  mov     eax, ebx
0x180043f4d  mov     rcx, [rbp+3D0h+var_10]
0x180043f54  xor     rcx, rsp; StackCookie
0x180043f57  call    __security_check_cookie
0x180043f5c  lea     r11, [rsp+4D0h+var_s0]
0x180043f64  mov     rbx, [r11+10h]
0x180043f68  mov     rdi, [r11+20h]
0x180043f6c  mov     rsp, r11
0x180043f6f  pop     rbp
0x180043f70  retn
```
