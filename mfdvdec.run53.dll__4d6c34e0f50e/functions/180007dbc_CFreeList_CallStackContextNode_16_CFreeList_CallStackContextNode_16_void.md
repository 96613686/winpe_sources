# CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)

- ea: `0x180007dbc`
- end: `0x180007e35`
- name: `??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007e3c`
- `0x180007eb0`

## callees

- `0x180001178`
- `0x180005fb0`
- `0x180007dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007e2e`

## pseudocode

```c
void __fastcall CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(__int64 a1)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r14
  __int64 v5; // rbp

  v1 = *(_QWORD **)(a1 + 56);
  *(_QWORD *)a1 = &CFreeList<CallStackContextNode,16>::`vftable';
  if ( v1 )
  {
    do
    {
      v3 = (_QWORD *)v1[254];
      v4 = v1 + 248;
      --*(_DWORD *)(a1 + 68);
      v5 = 124;
      do
      {
        v4 -= 2;
        rgbtransYUY2FulloutRight(v4);
        --v5;
      }
      while ( v5 );
      operator delete(v1);
      *(_QWORD *)(a1 + 56) = v3;
      v1 = v3;
    }
    while ( v3 );
  }
  *(_DWORD *)(a1 + 64) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
}

```

## disassembly

```asm
0x180007dbc  push    rbx
0x180007dbe  push    rbp
0x180007dbf  push    rsi
0x180007dc0  push    rdi
0x180007dc1  push    r14
0x180007dc3  sub     rsp, 20h
0x180007dc7  mov     rdi, [rcx+38h]
0x180007dcb  lea     rax, ??_7?$CFreeList@VCallStackContextNode@@$0BA@@@6B@; const CFreeList<CallStackContextNode,16>::`vftable'
0x180007dd2  mov     [rcx], rax
0x180007dd5  mov     rbx, rcx
0x180007dd8  test    rdi, rdi
0x180007ddb  jz      short loc_180007E19
0x180007ddd  mov     rsi, [rdi+7F0h]
0x180007de4  lea     r14, [rdi+7C0h]
0x180007deb  dec     dword ptr [rbx+44h]
0x180007dee  mov     ebp, 7Ch ; '|'
0x180007df3  sub     r14, 10h
0x180007df7  mov     rcx, r14
0x180007dfa  call    rgbtransYUY2FulloutRight
0x180007dff  sub     rbp, 1
0x180007e03  jnz     short loc_180007DF3
0x180007e05  mov     rcx, rdi; Block
0x180007e08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007e0d  mov     [rbx+38h], rsi
0x180007e11  mov     rdi, rsi
0x180007e14  test    rsi, rsi
0x180007e17  jnz     short loc_180007DDD
0x180007e19  lea     rcx, [rbx+10h]
0x180007e1d  mov     dword ptr [rbx+40h], 0
0x180007e24  add     rsp, 20h
0x180007e28  pop     r14
0x180007e2a  pop     rdi
0x180007e2b  pop     rsi
0x180007e2c  pop     rbp
0x180007e2d  pop     rbx
0x180007e2e  jmp     cs:__imp_DeleteCriticalSection
```
