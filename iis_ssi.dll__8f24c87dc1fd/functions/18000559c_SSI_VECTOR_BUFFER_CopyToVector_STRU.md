# SSI_VECTOR_BUFFER::CopyToVector(STRU &)

- ea: `0x18000559c`
- end: `0x180005617`
- name: `?CopyToVector@SSI_VECTOR_BUFFER@@QEAAJAEAVSTRU@@@Z`
- size: `123`
- prototype: `__int64 __fastcall(SSI_VECTOR_BUFFER *this, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004afc`

## callees

- `0x18000559c`
- `0x180005620`
- `0x180005780`

## import_xrefs

- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800055cf`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800055cf`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800055f4`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800055f4`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800055c0`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800055c0`

## pseudocode

```c
__int64 __fastcall SSI_VECTOR_BUFFER::CopyToVector(SSI_VECTOR_BUFFER *this, const unsigned __int16 **a2)
{
  int v4; // ebx
  _BYTE v6[32]; // [rsp+20h] [rbp-48h] BYREF
  char *Src; // [rsp+40h] [rbp-28h]
  unsigned int v8; // [rsp+50h] [rbp-18h]

  STRA::STRA((STRA *)v6);
  v4 = STRA::CopyW((STRA *)v6, a2[4]);
  if ( v4 >= 0 )
    v4 = SSI_VECTOR_BUFFER::CopyToVector(this, Src, v8);
  STRA::~STRA((STRA *)v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000559c  mov     [rsp+arg_10], rbx
0x1800055a1  push    rdi
0x1800055a2  sub     rsp, 60h
0x1800055a6  mov     rax, cs:__security_cookie
0x1800055ad  xor     rax, rsp
0x1800055b0  mov     [rsp+68h+var_10], rax
0x1800055b5  mov     rdi, rcx
0x1800055b8  mov     rbx, rdx
0x1800055bb  lea     rcx, [rsp+68h+var_48]
0x1800055c0  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800055c6  mov     rdx, [rbx+20h]
0x1800055ca  lea     rcx, [rsp+68h+var_48]
0x1800055cf  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800055d5  mov     ebx, eax
0x1800055d7  test    eax, eax
0x1800055d9  js      short loc_1800055EF
0x1800055db  mov     r8d, [rsp+68h+var_18]; unsigned int
0x1800055e0  mov     rcx, rdi; this
0x1800055e3  mov     rdx, [rsp+68h+Src]; Src
0x1800055e8  call    ?CopyToVector@SSI_VECTOR_BUFFER@@QEAAJPEADK@Z; SSI_VECTOR_BUFFER::CopyToVector(char *,ulong)
0x1800055ed  mov     ebx, eax
0x1800055ef  lea     rcx, [rsp+68h+var_48]
0x1800055f4  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800055fa  mov     eax, ebx
0x1800055fc  mov     rcx, [rsp+68h+var_10]
0x180005601  xor     rcx, rsp; StackCookie
0x180005604  call    __security_check_cookie
0x180005609  mov     rbx, [rsp+68h+arg_10]
0x180005611  add     rsp, 60h
0x180005615  pop     rdi
0x180005616  retn
```
