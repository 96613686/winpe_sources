# GetDirectoryName(ushort const *,ulong,ushort *,ulong)

- ea: `0x180001b78`
- end: `0x180001cbd`
- name: `?GetDirectoryName@@YAJPEBGKPEAGK@Z`
- size: `325`
- prototype: `int(const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a8b8`

## callees

- `0x180001b78`
- `0x18000edde`
- `0x18000ee10`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180001c3a`
- `msvcrt!wcsrchr` at `0x180001c3a`
- `msvcrt!memcpy_s` at `0x180001c6c`
- `msvcrt!memcpy_s` at `0x180001c6c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001bd6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001bd6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c8d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180001c8d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001bff`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180001bff`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180001c29`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180001c29`

## pseudocode

```c
__int64 __fastcall GetDirectoryName(const unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // rdi
  int v6; // ebx
  wchar_t *v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  _BYTE v12[32]; // [rsp+20h] [rbp-278h] BYREF
  wchar_t *Str; // [rsp+40h] [rbp-258h]
  unsigned __int16 v14[264]; // [rsp+60h] [rbp-238h] BYREF

  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  memset_0(v14, 0, 0x208u);
  STRU::STRU((STRU *)v12, v14, 0x104u);
  if ( !a1 || !a3 || (unsigned int)v3 <= 3 )
    goto LABEL_15;
  v6 = STRU::Copy((STRU *)v12, a1);
  if ( v6 < 0 )
    goto LABEL_16;
  v7 = Str;
  if ( Str[(unsigned int)v3 - 1] == 92 )
  {
    LODWORD(v3) = v3 - 1;
    STRU::SetLen((STRU *)v12, v3);
    v7 = Str;
  }
  v8 = wcsrchr(v7, 0x5Cu);
  if ( !v8 || (v9 = (unsigned int)(v8 - Str) + 1, (unsigned int)v9 > (unsigned int)v3) || (unsigned int)v9 > 0x104 )
  {
LABEL_15:
    v6 = -2147024809;
    goto LABEL_16;
  }
  v10 = v9;
  if ( memcpy_s(a3, 0x20Au, Str, 2 * v9) )
    v6 = -2147418113;
  else
    a3[v10] = 0;
LABEL_16:
  STRU::~STRU((STRU *)v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180001b78  mov     [rsp+arg_8], rbx
0x180001b7d  mov     [rsp+arg_18], rbp
0x180001b82  push    rsi
0x180001b83  push    rdi
0x180001b84  push    r14
0x180001b86  sub     rsp, 280h
0x180001b8d  mov     rax, cs:__security_cookie
0x180001b94  xor     rax, rsp
0x180001b97  mov     [rsp+298h+var_28], rax
0x180001b9f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180001ba3  mov     rsi, r8
0x180001ba6  xor     ebp, ebp
0x180001ba8  mov     rbx, rcx
0x180001bab  inc     rdi
0x180001bae  cmp     [rcx+rdi*2], bp
0x180001bb2  jnz     short loc_180001BAB
0x180001bb4  xor     edx, edx; Val
0x180001bb6  lea     rcx, [rsp+298h+var_238]; void *
0x180001bbb  mov     r8d, 208h; Size
0x180001bc1  call    memset_0
0x180001bc6  mov     r8d, 104h
0x180001bcc  lea     rdx, [rsp+298h+var_238]
0x180001bd1  lea     rcx, [rsp+298h+var_278]
0x180001bd6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001bdc  test    rbx, rbx
0x180001bdf  jz      loc_180001C83
0x180001be5  test    rsi, rsi
0x180001be8  jz      loc_180001C83
0x180001bee  cmp     edi, 3
0x180001bf1  jbe     loc_180001C83
0x180001bf7  mov     rdx, rbx
0x180001bfa  lea     rcx, [rsp+298h+var_278]
0x180001bff  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001c05  mov     ebx, eax
0x180001c07  test    eax, eax
0x180001c09  js      short loc_180001C88
0x180001c0b  mov     rax, [rsp+298h+Str]
0x180001c10  mov     r14d, 5Ch ; '\'
0x180001c16  mov     ecx, edi
0x180001c18  cmp     [rax+rcx*2-2], r14w
0x180001c1e  jnz     short loc_180001C34
0x180001c20  dec     edi
0x180001c22  lea     rcx, [rsp+298h+var_278]
0x180001c27  mov     edx, edi
0x180001c29  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180001c2f  mov     rax, [rsp+298h+Str]
0x180001c34  mov     edx, r14d; Ch
0x180001c37  mov     rcx, rax; Str
0x180001c3a  call    cs:__imp_wcsrchr
0x180001c40  test    rax, rax
0x180001c43  jz      short loc_180001C83
0x180001c45  mov     r8, [rsp+298h+Str]; Source
0x180001c4a  sub     rax, r8
0x180001c4d  sar     rax, 1
0x180001c50  inc     eax
0x180001c52  cmp     eax, edi
0x180001c54  ja      short loc_180001C83
0x180001c56  cmp     eax, 104h
0x180001c5b  ja      short loc_180001C83
0x180001c5d  lea     rdi, [rax+rax]
0x180001c61  mov     edx, 20Ah; DestinationSize
0x180001c66  mov     r9, rdi; SourceSize
0x180001c69  mov     rcx, rsi; Destination
0x180001c6c  call    cs:__imp_memcpy_s
0x180001c72  test    eax, eax
0x180001c74  jz      short loc_180001C7D
0x180001c76  mov     ebx, 8000FFFFh
0x180001c7b  jmp     short loc_180001C88
0x180001c7d  mov     [rdi+rsi], bp
0x180001c81  jmp     short loc_180001C88
0x180001c83  mov     ebx, 80070057h
0x180001c88  lea     rcx, [rsp+298h+var_278]
0x180001c8d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180001c93  mov     eax, ebx
0x180001c95  mov     rcx, [rsp+298h+var_28]
0x180001c9d  xor     rcx, rsp; StackCookie
0x180001ca0  call    __security_check_cookie
0x180001ca5  lea     r11, [rsp+298h+var_18]
0x180001cad  mov     rbx, [r11+28h]
0x180001cb1  mov     rbp, [r11+38h]
0x180001cb5  mov     rsp, r11
0x180001cb8  pop     r14
0x180001cba  pop     rdi
0x180001cbb  pop     rsi
0x180001cbc  retn
```
