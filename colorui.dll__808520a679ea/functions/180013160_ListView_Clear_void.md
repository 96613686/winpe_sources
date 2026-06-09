# ListView::Clear(void)

- ea: `0x180013160`
- end: `0x1800131e6`
- name: `?Clear@ListView@@QEAAXXZ`
- size: `134`
- prototype: `void __fastcall(ListView *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000d060`
- `0x18000e558`
- `0x18000f9c0`
- `0x180013050`
- `0x1800174f0`

## callees

- `0x180001334`
- `0x180013160`
- `0x1800131ec`

## import_xrefs

- `USER32!SendMessageW` at `0x180013186`
- `USER32!SendMessageW` at `0x1800131bd`
- `USER32!SendMessageW` at `0x180013186`
- `USER32!SendMessageW` at `0x1800131bd`
- `USER32!SendMessageW` at `0x1800131df`

## pseudocode

```c
void __fastcall ListView::Clear(ListView *this)
{
  int i; // edi
  void *Block; // [rsp+30h] [rbp+8h] BYREF

  Block = 0;
  for ( i = 0; i < (int)SendMessageW(*(HWND *)this, 0x1004u, 0, 0); ++i )
  {
    if ( !(unsigned int)ListView::GetItemLParam(this, i, (struct Profile **)&Block) )
      operator delete(Block);
  }
  SendMessageW(*(HWND *)this, 0x1009u, 0, 0);
}

```

## disassembly

```asm
0x180013160  mov     [rsp+arg_8], rbx
0x180013165  push    rdi
0x180013166  sub     rsp, 20h
0x18001316a  mov     rbx, rcx
0x18001316d  mov     [rsp+28h+Block], 0
0x180013176  mov     rcx, [rcx]; hWnd
0x180013179  xor     r9d, r9d; lParam
0x18001317c  xor     r8d, r8d; wParam
0x18001317f  mov     edx, 1004h; Msg
0x180013184  xor     edi, edi
0x180013186  call    cs:__imp_SendMessageW
0x18001318c  test    eax, eax
0x18001318e  jle     short loc_1800131C7
0x180013190  lea     r8, [rsp+28h+Block]; struct Profile **
0x180013195  mov     edx, edi; int
0x180013197  mov     rcx, rbx; this
0x18001319a  call    ?GetItemLParam@ListView@@QEBAJHPEAPEAUProfile@@@Z; ListView::GetItemLParam(int,Profile * *)
0x18001319f  test    eax, eax
0x1800131a1  jnz     short loc_1800131AD
0x1800131a3  mov     rcx, [rsp+28h+Block]; Block
0x1800131a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800131ad  mov     rcx, [rbx]; hWnd
0x1800131b0  xor     r9d, r9d; lParam
0x1800131b3  xor     r8d, r8d; wParam
0x1800131b6  mov     edx, 1004h; Msg
0x1800131bb  inc     edi
0x1800131bd  call    cs:__imp_SendMessageW
0x1800131c3  cmp     edi, eax
0x1800131c5  jl      short loc_180013190
0x1800131c7  mov     rcx, [rbx]
0x1800131ca  xor     r9d, r9d
0x1800131cd  xor     r8d, r8d
0x1800131d0  mov     edx, 1009h
0x1800131d5  mov     rbx, [rsp+28h+arg_8]
0x1800131da  add     rsp, 20h
0x1800131de  pop     rdi
0x1800131df  jmp     cs:__imp_SendMessageW
```
