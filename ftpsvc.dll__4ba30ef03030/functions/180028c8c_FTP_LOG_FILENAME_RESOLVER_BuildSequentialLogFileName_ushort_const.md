# FTP_LOG_FILENAME_RESOLVER::BuildSequentialLogFileName(ushort const *)

- ea: `0x180028c8c`
- end: `0x180028e78`
- name: `?BuildSequentialLogFileName@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBG@Z`
- size: `492`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800282e8`

## callees

- `0x180028c24`
- `0x180028c8c`
- `0x1800290ac`
- `0x180029344`
- `0x180047050`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180028cfb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180028cfb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028d16`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028d2d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028d48`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028dbc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028dcf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028d16`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028d2d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028d48`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028dbc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180028dcf`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180028cbe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180028cc9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180028cd4`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180028cbe`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180028cc9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180028cd4`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180028da2`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180028da2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028e36`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028e41`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028e4c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028e36`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028e41`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180028e4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_LOG_FILENAME_RESOLVER::BuildSequentialLogFileName(
        const unsigned __int16 **this,
        const unsigned __int16 *a2)
{
  int NextFileNameBySequenceNumber; // ebx
  __int64 v5; // r8
  unsigned int v6; // r8d
  unsigned int v8; // [rsp+30h] [rbp-79h] BYREF
  int v9; // [rsp+34h] [rbp-75h] BYREF
  _BYTE v10[32]; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int16 *v11; // [rsp+58h] [rbp-51h]
  _BYTE v12[32]; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v13; // [rsp+90h] [rbp-19h]
  _BYTE v14[32]; // [rsp+A8h] [rbp-1h] BYREF
  const unsigned __int16 *v15; // [rsp+C8h] [rbp+1Fh]

  STRU::STRU(v10);
  STRU::STRU(v14);
  STRU::STRU(v12);
  v8 = 0;
  v9 = 0;
  if ( *((_DWORD *)this + 32) )
  {
    NextFileNameBySequenceNumber = FTP_LOG_FILENAME_RESOLVER::BuildFileNameFormatString(this, a2, (struct STRU *)v12);
    if ( NextFileNameBySequenceNumber < 0 )
      goto LABEL_20;
    v6 = *((_DWORD *)this + 32);
LABEL_18:
    NextFileNameBySequenceNumber = FTP_LOG_FILENAME_RESOLVER::FindNextFileNameBySequenceNumber(
                                     (FTP_LOG_FILENAME_RESOLVER *)this,
                                     v13,
                                     v6);
    if ( NextFileNameBySequenceNumber >= 0 )
      goto LABEL_19;
    goto LABEL_20;
  }
  NextFileNameBySequenceNumber = STRU::Copy((STRU *)v10, this[4]);
  if ( NextFileNameBySequenceNumber < 0 )
    goto LABEL_20;
  NextFileNameBySequenceNumber = STRU::Append((STRU *)v10, L"\\");
  if ( NextFileNameBySequenceNumber < 0 )
    goto LABEL_20;
  NextFileNameBySequenceNumber = STRU::Append((STRU *)v10, a2);
  if ( NextFileNameBySequenceNumber < 0 )
    goto LABEL_20;
  NextFileNameBySequenceNumber = STRU::Append((STRU *)v10, L"*.log");
  if ( NextFileNameBySequenceNumber < 0 )
    goto LABEL_20;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  NextFileNameBySequenceNumber = FTP_LOG_FILENAME_RESOLVER::FindFirstSequenceNumber(
                                   (FTP_LOG_FILENAME_RESOLVER *)this,
                                   v11,
                                   v5,
                                   &v8,
                                   (struct STRU *)v14,
                                   &v9);
  if ( NextFileNameBySequenceNumber < 0 )
    goto LABEL_20;
  if ( !v9 )
  {
    NextFileNameBySequenceNumber = FTP_LOG_FILENAME_RESOLVER::BuildFileNameFormatString(this, a2, (struct STRU *)v12);
    if ( NextFileNameBySequenceNumber < 0 )
      goto LABEL_20;
    v6 = v8;
    goto LABEL_18;
  }
  NextFileNameBySequenceNumber = STRU::Copy((STRU *)(this + 7), (const struct STRU *)this);
  if ( NextFileNameBySequenceNumber >= 0 )
  {
    NextFileNameBySequenceNumber = STRU::Append((STRU *)(this + 7), L"\\");
    if ( NextFileNameBySequenceNumber >= 0 )
    {
      NextFileNameBySequenceNumber = STRU::Append((STRU *)(this + 7), v15);
      if ( NextFileNameBySequenceNumber >= 0 )
      {
        *((_DWORD *)this + 32) = v8;
LABEL_19:
        NextFileNameBySequenceNumber = 0;
      }
    }
  }
LABEL_20:
  STRU::~STRU(v12);
  STRU::~STRU(v14);
  STRU::~STRU(v10);
  return (unsigned int)NextFileNameBySequenceNumber;
}

```

## disassembly

```asm
0x180028c8c  mov     [rsp-8+arg_10], rbx
0x180028c91  mov     [rsp-8+arg_18], rsi
0x180028c96  push    rbp
0x180028c97  push    rdi
0x180028c98  push    r14
0x180028c9a  lea     rbp, [rsp-47h]
0x180028c9f  sub     rsp, 0F0h
0x180028ca6  mov     rax, cs:__security_cookie
0x180028cad  xor     rax, rsp
0x180028cb0  mov     [rbp+57h+var_20], rax
0x180028cb4  mov     rsi, rdx
0x180028cb7  mov     rdi, rcx
0x180028cba  lea     rcx, [rbp+57h+var_C8]
0x180028cbe  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180028cc4  nop
0x180028cc5  lea     rcx, [rbp+57h+var_58]
0x180028cc9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180028ccf  nop
0x180028cd0  lea     rcx, [rbp+57h+var_90]
0x180028cd4  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180028cda  nop
0x180028cdb  xor     r14d, r14d
0x180028cde  mov     [rbp+57h+var_D0], r14d
0x180028ce2  mov     [rbp+57h+var_CC], r14d
0x180028ce6  cmp     [rdi+80h], r14d
0x180028ced  jnz     loc_180028E01
0x180028cf3  mov     rdx, [rdi+20h]
0x180028cf7  lea     rcx, [rbp+57h+var_C8]
0x180028cfb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180028d01  mov     ebx, eax
0x180028d03  test    eax, eax
0x180028d05  js      loc_180028E32
0x180028d0b  lea     rdx, asc_18004BD10; "\\"
0x180028d12  lea     rcx, [rbp+57h+var_C8]
0x180028d16  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180028d1c  mov     ebx, eax
0x180028d1e  test    eax, eax
0x180028d20  js      loc_180028E32
0x180028d26  mov     rdx, rsi
0x180028d29  lea     rcx, [rbp+57h+var_C8]
0x180028d2d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180028d33  mov     ebx, eax
0x180028d35  test    eax, eax
0x180028d37  js      loc_180028E32
0x180028d3d  lea     rdx, aLog; "*.log"
0x180028d44  lea     rcx, [rbp+57h+var_C8]
0x180028d48  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180028d4e  mov     ebx, eax
0x180028d50  test    eax, eax
0x180028d52  js      loc_180028E32
0x180028d58  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028d5c  inc     r8; unsigned int
0x180028d5f  cmp     [rsi+r8*2], r14w
0x180028d64  jnz     short loc_180028D5C
0x180028d66  lea     rax, [rbp+57h+var_CC]
0x180028d6a  mov     [rsp+100h+var_D8], rax; int *
0x180028d6f  lea     rax, [rbp+57h+var_58]
0x180028d73  mov     [rsp+100h+var_E0], rax; struct STRU *
0x180028d78  lea     r9, [rbp+57h+var_D0]; unsigned int *
0x180028d7c  mov     rdx, [rbp+57h+var_A8]; unsigned __int16 *
0x180028d80  mov     rcx, rdi; this
0x180028d83  call    ?FindFirstSequenceNumber@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBGKPEAKPEAVSTRU@@PEAH@Z; FTP_LOG_FILENAME_RESOLVER::FindFirstSequenceNumber(ushort const *,ulong,ulong *,STRU *,int *)
0x180028d88  mov     ebx, eax
0x180028d8a  test    eax, eax
0x180028d8c  js      loc_180028E32
0x180028d92  cmp     [rbp+57h+var_CC], r14d
0x180028d96  jz      short loc_180028DE6
0x180028d98  lea     rsi, [rdi+38h]
0x180028d9c  mov     rdx, rdi
0x180028d9f  mov     rcx, rsi
0x180028da2  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180028da8  mov     ebx, eax
0x180028daa  test    eax, eax
0x180028dac  js      loc_180028E32
0x180028db2  lea     rdx, asc_18004BD10; "\\"
0x180028db9  mov     rcx, rsi
0x180028dbc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180028dc2  mov     ebx, eax
0x180028dc4  test    eax, eax
0x180028dc6  js      short loc_180028E32
0x180028dc8  mov     rdx, [rbp+57h+var_38]
0x180028dcc  mov     rcx, rsi
0x180028dcf  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180028dd5  mov     ebx, eax
0x180028dd7  test    eax, eax
0x180028dd9  js      short loc_180028E32
0x180028ddb  mov     eax, [rbp+57h+var_D0]
0x180028dde  mov     [rdi+80h], eax
0x180028de4  jmp     short loc_180028E2F
0x180028de6  lea     r8, [rbp+57h+var_90]; struct STRU *
0x180028dea  mov     rdx, rsi; unsigned __int16 *
0x180028ded  mov     rcx, rdi; this
0x180028df0  call    ?BuildFileNameFormatString@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBGPEAVSTRU@@@Z; FTP_LOG_FILENAME_RESOLVER::BuildFileNameFormatString(ushort const *,STRU *)
0x180028df5  mov     ebx, eax
0x180028df7  test    eax, eax
0x180028df9  js      short loc_180028E32
0x180028dfb  mov     r8d, [rbp+57h+var_D0]
0x180028dff  jmp     short loc_180028E1D
0x180028e01  lea     r8, [rbp+57h+var_90]; struct STRU *
0x180028e05  mov     rdx, rsi; unsigned __int16 *
0x180028e08  mov     rcx, rdi; this
0x180028e0b  call    ?BuildFileNameFormatString@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBGPEAVSTRU@@@Z; FTP_LOG_FILENAME_RESOLVER::BuildFileNameFormatString(ushort const *,STRU *)
0x180028e10  mov     ebx, eax
0x180028e12  test    eax, eax
0x180028e14  js      short loc_180028E32
0x180028e16  mov     r8d, [rdi+80h]; unsigned int
0x180028e1d  mov     rdx, [rbp+57h+var_70]; unsigned __int16 *
0x180028e21  mov     rcx, rdi; this
0x180028e24  call    ?FindNextFileNameBySequenceNumber@FTP_LOG_FILENAME_RESOLVER@@AEAAJPEBGK@Z; FTP_LOG_FILENAME_RESOLVER::FindNextFileNameBySequenceNumber(ushort const *,ulong)
0x180028e29  test    eax, eax
0x180028e2b  mov     ebx, eax
0x180028e2d  js      short loc_180028E32
0x180028e2f  mov     ebx, r14d
0x180028e32  lea     rcx, [rbp+57h+var_90]
0x180028e36  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180028e3c  nop
0x180028e3d  lea     rcx, [rbp+57h+var_58]
0x180028e41  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180028e47  nop
0x180028e48  lea     rcx, [rbp+57h+var_C8]
0x180028e4c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180028e52  mov     eax, ebx
0x180028e54  mov     rcx, [rbp+57h+var_20]
0x180028e58  xor     rcx, rsp; StackCookie
0x180028e5b  call    __security_check_cookie
0x180028e60  lea     r11, [rsp+100h+var_10]
0x180028e68  mov     rbx, [r11+30h]
0x180028e6c  mov     rsi, [r11+38h]
0x180028e70  mov     rsp, r11
0x180028e73  pop     r14
0x180028e75  pop     rdi
0x180028e76  pop     rbp
0x180028e77  retn
```
