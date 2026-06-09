# SipFile::InvalidateCache(void)

- ea: `0x180004700`
- end: `0x180004768`
- name: `?InvalidateCache@SipFile@@AEAAXXZ`
- size: `104`
- prototype: `void __fastcall(SipFile *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003424`
- `0x180004fd4`

## callees

- `0x180001008`
- `0x180004700`

## pseudocode

```c
void __fastcall SipFile::InvalidateCache(SipFile *this)
{
  void *v1; // rdi
  void *v3; // rsi
  void *v4; // rcx

  v1 = (void *)*((_QWORD *)this + 8);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v1 )
    operator delete(v1);
  if ( v3 != v1 )
  {
    v4 = (void *)*((_QWORD *)this + 9);
    if ( v4 )
      operator delete(v4);
  }
  *((_WORD *)this + 48) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 11) = 0;
}

```

## disassembly

```asm
0x180004700  mov     [rsp+arg_0], rbx
0x180004705  mov     [rsp+arg_8], rsi
0x18000470a  push    rdi
0x18000470b  sub     rsp, 20h
0x18000470f  mov     rdi, [rcx+40h]
0x180004713  mov     rbx, rcx
0x180004716  mov     rsi, [rcx+48h]
0x18000471a  test    rdi, rdi
0x18000471d  jz      short loc_180004727
0x18000471f  mov     rcx, rdi; Block
0x180004722  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004727  cmp     rsi, rdi
0x18000472a  jz      short loc_18000473A
0x18000472c  mov     rcx, [rbx+48h]; Block
0x180004730  test    rcx, rcx
0x180004733  jz      short loc_18000473A
0x180004735  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000473a  mov     rsi, [rsp+28h+arg_8]
0x18000473f  xor     eax, eax
0x180004741  mov     [rbx+60h], ax
0x180004745  mov     qword ptr [rbx+40h], 0
0x18000474d  mov     qword ptr [rbx+48h], 0
0x180004755  mov     qword ptr [rbx+58h], 0
0x18000475d  mov     rbx, [rsp+28h+arg_0]
0x180004762  add     rsp, 20h
0x180004766  pop     rdi
0x180004767  retn
```
