# FTP_VDIR_PARENT_TABLE::FindEntry(ushort const *,FTP_VDIR_PARENT_ENTRY * *)

- ea: `0x180018014`
- end: `0x18001814a`
- name: `?FindEntry@FTP_VDIR_PARENT_TABLE@@QEAAJPEBGPEAPEAVFTP_VDIR_PARENT_ENTRY@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(FTP_VDIR_PARENT_TABLE **this, const unsigned __int16 *, struct FTP_VDIR_PARENT_ENTRY **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180010370`
- `0x180018150`
- `0x180018764`

## callees

- `0x180018014`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018105`
- `msvcrt!_wcsicmp` at `0x180018105`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800180c6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800180e4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800180c6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800180e4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800180b6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800180b6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001805f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18001805f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018124`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180018124`

## pseudocode

```c
__int64 __fastcall FTP_VDIR_PARENT_TABLE::FindEntry(
        FTP_VDIR_PARENT_TABLE **this,
        const unsigned __int16 *a2,
        struct FTP_VDIR_PARENT_ENTRY **a3)
{
  __int64 v6; // rax
  const unsigned __int16 *v7; // r8
  unsigned __int16 v8; // ax
  int v9; // ecx
  int v10; // eax
  int v11; // ebx
  FTP_VDIR_PARENT_TABLE *i; // rbx
  struct FTP_VDIR_PARENT_ENTRY *v13; // rdi
  _BYTE v15[32]; // [rsp+20h] [rbp-178h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-158h]
  int v17; // [rsp+50h] [rbp-148h]
  unsigned __int16 v18[128]; // [rsp+60h] [rbp-138h] BYREF

  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v15, v18, 0x80u);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = &a2[v6];
  v8 = *v7;
  if ( *v7 == 47 )
    goto LABEL_11;
  v9 = 0;
  do
  {
    if ( v8 == 42 || v8 == 63 )
      v9 = 1;
    v8 = *--v7;
  }
  while ( *v7 != 47 );
  if ( !v9 )
LABEL_11:
    v10 = STRU::Copy((STRU *)v15, a2);
  else
    v10 = STRU::Copy((STRU *)v15, a2, v7 - a2);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( v17 || (v11 = STRU::Copy((STRU *)v15, L"/"), v11 >= 0) )
    {
      for ( i = *this; ; i = *(FTP_VDIR_PARENT_TABLE **)i )
      {
        v13 = 0;
        if ( i == (FTP_VDIR_PARENT_TABLE *)this )
          break;
        v13 = (FTP_VDIR_PARENT_TABLE *)((char *)i - 328);
        if ( !_wcsicmp(String1, *((const wchar_t **)i - 37)) )
          break;
      }
      *a3 = v13;
      v11 = 0;
    }
  }
  STRU::~STRU(v15);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180018014  push    rbx
0x180018016  push    rbp
0x180018017  push    rsi
0x180018018  push    rdi
0x180018019  push    r14
0x18001801b  sub     rsp, 170h
0x180018022  mov     rax, cs:__security_cookie
0x180018029  xor     rax, rsp
0x18001802c  mov     [rsp+198h+var_38], rax
0x180018034  mov     r14, r8
0x180018037  mov     rbx, rdx
0x18001803a  mov     rsi, rcx
0x18001803d  xor     edx, edx; Val
0x18001803f  mov     r8d, 100h; Size
0x180018045  lea     rcx, [rsp+198h+var_138]; void *
0x18001804a  call    memset_0
0x18001804f  mov     r8d, 80h
0x180018055  lea     rdx, [rsp+198h+var_138]
0x18001805a  lea     rcx, [rsp+198h+var_178]
0x18001805f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180018065  nop
0x180018066  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001806a  xor     ebp, ebp
0x18001806c  inc     rax
0x18001806f  cmp     [rbx+rax*2], bp
0x180018073  jnz     short loc_18001806C
0x180018075  lea     r8, [rbx+rax*2]
0x180018079  movzx   eax, word ptr [r8]
0x18001807d  cmp     ax, 2Fh ; '/'
0x180018081  jz      short loc_1800180BE
0x180018083  mov     ecx, ebp
0x180018085  cmp     ax, 2Ah ; '*'
0x180018089  jz      short loc_180018091
0x18001808b  cmp     ax, 3Fh ; '?'
0x18001808f  jnz     short loc_180018096
0x180018091  mov     ecx, 1
0x180018096  sub     r8, 2
0x18001809a  movzx   eax, word ptr [r8]
0x18001809e  cmp     ax, 2Fh ; '/'
0x1800180a2  jnz     short loc_180018085
0x1800180a4  test    ecx, ecx
0x1800180a6  jz      short loc_1800180BE
0x1800180a8  sub     r8, rbx
0x1800180ab  sar     r8, 1
0x1800180ae  mov     rdx, rbx
0x1800180b1  lea     rcx, [rsp+198h+var_178]
0x1800180b6  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800180bc  jmp     short loc_1800180CC
0x1800180be  mov     rdx, rbx
0x1800180c1  lea     rcx, [rsp+198h+var_178]
0x1800180c6  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800180cc  mov     ebx, eax
0x1800180ce  test    eax, eax
0x1800180d0  js      short loc_18001811F
0x1800180d2  cmp     [rsp+198h+var_148], ebp
0x1800180d6  jnz     short loc_1800180F0
0x1800180d8  lea     rdx, asc_18004BD14; "/"
0x1800180df  lea     rcx, [rsp+198h+var_178]
0x1800180e4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800180ea  mov     ebx, eax
0x1800180ec  test    eax, eax
0x1800180ee  js      short loc_18001811F
0x1800180f0  mov     rbx, [rsi]
0x1800180f3  jmp     short loc_180018112
0x1800180f5  lea     rdi, [rbx-148h]
0x1800180fc  mov     rdx, [rdi+20h]; String2
0x180018100  mov     rcx, [rsp+198h+String1]; String1
0x180018105  call    cs:__imp__wcsicmp
0x18001810b  test    eax, eax
0x18001810d  jz      short loc_18001811A
0x18001810f  mov     rbx, [rbx]
0x180018112  cmp     rbx, rsi
0x180018115  mov     rdi, rbp
0x180018118  jnz     short loc_1800180F5
0x18001811a  mov     [r14], rdi
0x18001811d  mov     ebx, ebp
0x18001811f  lea     rcx, [rsp+198h+var_178]
0x180018124  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001812a  mov     eax, ebx
0x18001812c  mov     rcx, [rsp+198h+var_38]
0x180018134  xor     rcx, rsp; StackCookie
0x180018137  call    __security_check_cookie
0x18001813c  add     rsp, 170h
0x180018143  pop     r14
0x180018145  pop     rdi
0x180018146  pop     rsi
0x180018147  pop     rbp
0x180018148  pop     rbx
0x180018149  retn
```
