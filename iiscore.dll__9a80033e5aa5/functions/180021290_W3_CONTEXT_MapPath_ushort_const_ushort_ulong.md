# W3_CONTEXT::MapPath(ushort const *,ushort *,ulong *)

- ea: `0x180021290`
- end: `0x180021373`
- name: `?MapPath@W3_CONTEXT@@UEAAJPEBGPEAGPEAK@Z`
- size: `227`
- prototype: `__int64 __fastcall(W3_CONTEXT *this, unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002bf0`
- `0x180021290`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18002134d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002134d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800212de`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800212de`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180021339`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180021339`

## pseudocode

```c
__int64 __fastcall W3_CONTEXT::MapPath(W3_CONTEXT *this, unsigned __int16 *a2, unsigned __int16 *a3, unsigned int *a4)
{
  __int64 v8; // r8
  int v9; // ebx
  bool v11; // [rsp+30h] [rbp-288h] BYREF
  _BYTE v12[56]; // [rsp+38h] [rbp-280h] BYREF
  unsigned __int16 v13[264]; // [rsp+70h] [rbp-248h] BYREF

  memset_0(v13, 0, 0x208u);
  STRU::STRU((STRU *)v12, v13, 0x104u);
  v11 = 0;
  if ( a2 && a4 && (a3 || !*a4) )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
    v9 = W3_CONTEXT::MapPath(this, a2, v8, (struct STRU *)v12, &v11);
    if ( v9 >= 0 )
      v9 = STRU::CopyToBuffer((STRU *)v12, a3, a4);
  }
  else
  {
    v9 = -2147024809;
  }
  STRU::~STRU((STRU *)v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180021290  push    rbx
0x180021292  push    rbp
0x180021293  push    rsi
0x180021294  push    rdi
0x180021295  push    r14
0x180021297  sub     rsp, 290h
0x18002129e  mov     rax, cs:__security_cookie
0x1800212a5  xor     rax, rsp
0x1800212a8  mov     [rsp+2B8h+var_38], rax
0x1800212b0  mov     rsi, r8
0x1800212b3  mov     rbx, rdx
0x1800212b6  mov     rbp, rcx
0x1800212b9  xor     edx, edx; Val
0x1800212bb  mov     r8d, 208h; Size
0x1800212c1  lea     rcx, [rsp+2B8h+var_248]; void *
0x1800212c6  mov     rdi, r9
0x1800212c9  call    memset_0
0x1800212ce  mov     r8d, 104h
0x1800212d4  lea     rdx, [rsp+2B8h+var_248]
0x1800212d9  lea     rcx, [rsp+2B8h+var_280]
0x1800212de  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800212e4  xor     r14d, r14d
0x1800212e7  mov     [rsp+2B8h+var_288], r14b
0x1800212ec  test    rbx, rbx
0x1800212ef  jz      short loc_180021343
0x1800212f1  test    rdi, rdi
0x1800212f4  jz      short loc_180021343
0x1800212f6  test    rsi, rsi
0x1800212f9  jnz     short loc_180021300
0x1800212fb  cmp     [rdi], r14d
0x1800212fe  jnz     short loc_180021343
0x180021300  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021304  inc     r8; unsigned int
0x180021307  cmp     [rbx+r8*2], r14w
0x18002130c  jnz     short loc_180021304
0x18002130e  lea     rax, [rsp+2B8h+var_288]
0x180021313  mov     rdx, rbx; unsigned __int16 *
0x180021316  lea     r9, [rsp+2B8h+var_280]; struct STRU *
0x18002131b  mov     [rsp+2B8h+var_298], rax; bool *
0x180021320  mov     rcx, rbp; this
0x180021323  call    ?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z; W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)
0x180021328  mov     ebx, eax
0x18002132a  test    eax, eax
0x18002132c  js      short loc_180021348
0x18002132e  mov     r8, rdi
0x180021331  lea     rcx, [rsp+2B8h+var_280]
0x180021336  mov     rdx, rsi
0x180021339  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x18002133f  mov     ebx, eax
0x180021341  jmp     short loc_180021348
0x180021343  mov     ebx, 80070057h
0x180021348  lea     rcx, [rsp+2B8h+var_280]
0x18002134d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021353  mov     eax, ebx
0x180021355  mov     rcx, [rsp+2B8h+var_38]
0x18002135d  xor     rcx, rsp; StackCookie
0x180021360  call    __security_check_cookie
0x180021365  add     rsp, 290h
0x18002136c  pop     r14
0x18002136e  pop     rdi
0x18002136f  pop     rsi
0x180021370  pop     rbp
0x180021371  pop     rbx
0x180021372  retn
```
