# W3_CONTEXT::MapPath(ushort const *,ushort *,ulong *)

- ea: `0x180022ef0`
- end: `0x180022fe6`
- name: `?MapPath@W3_CONTEXT@@UEAAJPEBGPEAGPEAK@Z`
- size: `246`
- prototype: `__int64 __fastcall(W3_CONTEXT *__hidden this, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002db0`
- `0x180022ef0`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180022fb9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022fb9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022f3e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022f3e`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180022f9f`
- `iisutil!?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z` at `0x180022f9f`

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
0x180022ef0  push    rbx
0x180022ef2  push    rbp
0x180022ef3  push    rsi
0x180022ef4  push    rdi
0x180022ef5  push    r14
0x180022ef7  sub     rsp, 290h
0x180022efe  mov     rax, cs:__security_cookie
0x180022f05  xor     rax, rsp
0x180022f08  mov     [rsp+2B8h+var_38], rax
0x180022f10  mov     rsi, r8
0x180022f13  mov     rbx, rdx
0x180022f16  mov     rbp, rcx
0x180022f19  xor     edx, edx; Val
0x180022f1b  mov     r8d, 208h; Size
0x180022f21  lea     rcx, [rsp+2B8h+var_248]; void *
0x180022f26  mov     rdi, r9
0x180022f29  call    memset_0
0x180022f2e  mov     r8d, 104h
0x180022f34  lea     rdx, [rsp+2B8h+var_248]
0x180022f39  lea     rcx, [rsp+2B8h+var_280]
0x180022f3e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022f45  nop     dword ptr [rax+rax+00h]
0x180022f4a  xor     r14d, r14d
0x180022f4d  mov     [rsp+2B8h+var_288], r14b
0x180022f52  test    rbx, rbx
0x180022f55  jz      short loc_180022FAF
0x180022f57  test    rdi, rdi
0x180022f5a  jz      short loc_180022FAF
0x180022f5c  test    rsi, rsi
0x180022f5f  jnz     short loc_180022F66
0x180022f61  cmp     [rdi], r14d
0x180022f64  jnz     short loc_180022FAF
0x180022f66  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022f6a  inc     r8; unsigned int
0x180022f6d  cmp     [rbx+r8*2], r14w
0x180022f72  jnz     short loc_180022F6A
0x180022f74  lea     rax, [rsp+2B8h+var_288]
0x180022f79  mov     rdx, rbx; unsigned __int16 *
0x180022f7c  lea     r9, [rsp+2B8h+var_280]; struct STRU *
0x180022f81  mov     [rsp+2B8h+var_298], rax; bool *
0x180022f86  mov     rcx, rbp; this
0x180022f89  call    ?MapPath@W3_CONTEXT@@QEAAJPEBGKPEAVSTRU@@PEA_N@Z; W3_CONTEXT::MapPath(ushort const *,ulong,STRU *,bool *)
0x180022f8e  mov     ebx, eax
0x180022f90  test    eax, eax
0x180022f92  js      short loc_180022FB4
0x180022f94  mov     r8, rdi
0x180022f97  lea     rcx, [rsp+2B8h+var_280]
0x180022f9c  mov     rdx, rsi
0x180022f9f  call    cs:__imp_?CopyToBuffer@STRU@@QEBAJPEAGPEAK@Z; STRU::CopyToBuffer(ushort *,ulong *)
0x180022fa6  nop     dword ptr [rax+rax+00h]
0x180022fab  mov     ebx, eax
0x180022fad  jmp     short loc_180022FB4
0x180022faf  mov     ebx, 80070057h
0x180022fb4  lea     rcx, [rsp+2B8h+var_280]
0x180022fb9  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022fc0  nop     dword ptr [rax+rax+00h]
0x180022fc5  mov     eax, ebx
0x180022fc7  mov     rcx, [rsp+2B8h+var_38]
0x180022fcf  xor     rcx, rsp; StackCookie
0x180022fd2  call    __security_check_cookie
0x180022fd7  add     rsp, 290h
0x180022fde  pop     r14
0x180022fe0  pop     rdi
0x180022fe1  pop     rsi
0x180022fe2  pop     rbp
0x180022fe3  pop     rbx
0x180022fe4  retn
```
