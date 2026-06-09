# REDIRECTION_BLOB::AddWildcardEntry(ushort const *,ushort const *)

- ea: `0x180002678`
- end: `0x180002750`
- name: `?AddWildcardEntry@REDIRECTION_BLOB@@QEAAJPEBG0@Z`
- size: `216`
- prototype: `__int64 __fastcall(REDIRECTION_BLOB *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000304c`

## callees

- `0x180001008`
- `0x180001048`
- `0x180002678`

## import_xrefs

- `msvcrt!wcschr` at `0x1800026e2`
- `msvcrt!wcschr` at `0x1800026e2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800026bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800026ce`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800026bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800026ce`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800026a5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800026af`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800026a5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800026af`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002725`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000272e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002725`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000272e`

## pseudocode

```c
__int64 __fastcall REDIRECTION_BLOB::AddWildcardEntry(
        REDIRECTION_BLOB *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  STRU *v6; // rax
  STRU *v7; // rbx
  int v8; // edi
  REDIRECTION_BLOB **v9; // rdx

  v6 = (STRU *)operator new(0x80u);
  v7 = v6;
  if ( !v6 )
    return 2147942408LL;
  STRU::STRU(v6);
  STRU::STRU((STRU *)((char *)v7 + 56));
  v8 = STRU::Copy(v7, a2);
  if ( v8 < 0 || (v8 = STRU::Copy((STRU *)((char *)v7 + 56), a3), v8 < 0) )
  {
    STRU::~STRU((STRU *)((char *)v7 + 56));
    STRU::~STRU(v7);
    operator delete(v7);
    return (unsigned int)v8;
  }
  else
  {
    *((_DWORD *)this + 4) |= wcschr(a3, 0x24u) != 0;
    v9 = (REDIRECTION_BLOB **)*((_QWORD *)this + 19);
    if ( *v9 != (REDIRECTION_BLOB *)((char *)this + 144) )
      __fastfail(3u);
    *((_QWORD *)v7 + 14) = (char *)this + 144;
    *((_QWORD *)v7 + 15) = v9;
    *v9 = (STRU *)((char *)v7 + 112);
    *((_QWORD *)this + 19) = (char *)v7 + 112;
    return 0;
  }
}

```

## disassembly

```asm
0x180002678  push    rbx
0x18000267a  push    rbp
0x18000267b  push    rsi
0x18000267c  push    rdi
0x18000267d  push    r14
0x18000267f  sub     rsp, 20h
0x180002683  mov     r14, rcx
0x180002686  mov     rbp, r8
0x180002689  mov     ecx, 80h; Size
0x18000268e  mov     rdi, rdx
0x180002691  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002696  mov     rbx, rax
0x180002699  test    rax, rax
0x18000269c  jz      loc_180002740
0x1800026a2  mov     rcx, rax
0x1800026a5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800026ab  lea     rcx, [rbx+38h]
0x1800026af  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800026b5  mov     rdx, rdi
0x1800026b8  mov     rcx, rbx
0x1800026bb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800026c1  mov     edi, eax
0x1800026c3  test    eax, eax
0x1800026c5  js      short loc_180002721
0x1800026c7  mov     rdx, rbp
0x1800026ca  lea     rcx, [rbx+38h]
0x1800026ce  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800026d4  mov     edi, eax
0x1800026d6  test    eax, eax
0x1800026d8  js      short loc_180002721
0x1800026da  mov     edx, 24h ; '$'; Ch
0x1800026df  mov     rcx, rbp; Str
0x1800026e2  call    cs:__imp_wcschr
0x1800026e8  xor     ecx, ecx
0x1800026ea  test    rax, rax
0x1800026ed  setnz   cl
0x1800026f0  or      [r14+10h], ecx
0x1800026f4  lea     rcx, [r14+90h]
0x1800026fb  mov     rdx, [rcx+8]
0x1800026ff  cmp     [rdx], rcx
0x180002702  jz      short loc_18000270B
0x180002704  mov     ecx, 3
0x180002709  int     29h; Win8: RtlFailFast(ecx)
0x18000270b  lea     rax, [rbx+70h]
0x18000270f  mov     [rax], rcx
0x180002712  mov     [rax+8], rdx
0x180002716  mov     [rdx], rax
0x180002719  mov     [rcx+8], rax
0x18000271d  xor     eax, eax
0x18000271f  jmp     short loc_180002745
0x180002721  lea     rcx, [rbx+38h]
0x180002725  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000272b  mov     rcx, rbx
0x18000272e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002734  mov     rcx, rbx; Block
0x180002737  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000273c  mov     eax, edi
0x18000273e  jmp     short loc_180002745
0x180002740  mov     eax, 80070008h
0x180002745  add     rsp, 20h
0x180002749  pop     r14
0x18000274b  pop     rdi
0x18000274c  pop     rsi
0x18000274d  pop     rbp
0x18000274e  pop     rbx
0x18000274f  retn
```
