# CDocWrap::_Clear(void)

- ea: `0x18000c200`
- end: `0x18000c249`
- name: `?_Clear@CDocWrap@@AEAAXXZ`
- size: `73`
- prototype: `void __fastcall(CDocWrap *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b400`
- `0x18000f5b0`
- `0x18000fc5c`
- `0x180011ba0`
- `0x180011e70`

## callees

- `0x18000c200`
- `0x180014010`

## pseudocode

```c
void __fastcall CDocWrap::_Clear(CDocWrap *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x18000c200  push    rbx
0x18000c202  sub     rsp, 20h
0x18000c206  mov     rbx, rcx
0x18000c209  mov     rcx, [rcx+28h]
0x18000c20d  test    rcx, rcx
0x18000c210  jz      short loc_18000C226
0x18000c212  mov     rax, [rcx]
0x18000c215  mov     rax, [rax+10h]
0x18000c219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c21e  mov     qword ptr [rbx+28h], 0
0x18000c226  mov     rcx, [rbx+20h]
0x18000c22a  test    rcx, rcx
0x18000c22d  jz      short loc_18000C243
0x18000c22f  mov     rax, [rcx]
0x18000c232  mov     rax, [rax+10h]
0x18000c236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23b  mov     qword ptr [rbx+20h], 0
0x18000c243  add     rsp, 20h
0x18000c247  pop     rbx
0x18000c248  retn
```
