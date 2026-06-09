# Combo<Device>::Clear(void)

- ea: `0x18000c5d0`
- end: `0x18000c654`
- name: `?Clear@?$Combo@UDevice@@@@QEAAXXZ`
- size: `132`
- prototype: `LRESULT __fastcall(HWND *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c65c`
- `0x18000d060`
- `0x18000e244`
- `0x18000ffe0`
- `0x180010780`

## callees

- `0x180001334`
- `0x18000c5d0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000c5f0`
- `USER32!SendMessageW` at `0x18000c612`
- `USER32!SendMessageW` at `0x18000c5f0`
- `USER32!SendMessageW` at `0x18000c612`
- `USER32!SendMessageW` at `0x18000c64d`

## pseudocode

```c
LRESULT __fastcall Combo<Device>::Clear(HWND *a1)
{
  int v2; // eax
  int v3; // edi
  int v4; // ebx
  void *v5; // rax

  v2 = SendMessageW(*a1, 0x146u, 0, 0);
  v3 = v2;
  if ( v2 != -1 )
  {
    v4 = 0;
    if ( v2 > 0 )
    {
      do
      {
        v5 = (void *)SendMessageW(*a1, 0x150u, v4, 0);
        if ( (unsigned __int64)v5 + 1 > 1 )
          operator delete(v5);
        ++v4;
      }
      while ( v4 < v3 );
    }
  }
  return SendMessageW(*a1, 0x14Bu, 0, 0);
}

```

## disassembly

```asm
0x18000c5d0  mov     [rsp+arg_0], rbx
0x18000c5d5  mov     [rsp+arg_8], rsi
0x18000c5da  push    rdi
0x18000c5db  sub     rsp, 20h
0x18000c5df  mov     rsi, rcx
0x18000c5e2  xor     r9d, r9d; lParam
0x18000c5e5  mov     rcx, [rcx]; hWnd
0x18000c5e8  xor     r8d, r8d; wParam
0x18000c5eb  mov     edx, 146h; Msg
0x18000c5f0  call    cs:__imp_SendMessageW
0x18000c5f6  mov     rdi, rax
0x18000c5f9  cmp     eax, 0FFFFFFFFh
0x18000c5fc  jz      short loc_18000C630
0x18000c5fe  xor     ebx, ebx
0x18000c600  test    edi, edi
0x18000c602  jle     short loc_18000C630
0x18000c604  mov     rcx, [rsi]; hWnd
0x18000c607  xor     r9d, r9d; lParam
0x18000c60a  movsxd  r8, ebx; wParam
0x18000c60d  mov     edx, 150h; Msg
0x18000c612  call    cs:__imp_SendMessageW
0x18000c618  lea     rcx, [rax+1]
0x18000c61c  cmp     rcx, 1
0x18000c620  jbe     short loc_18000C62A
0x18000c622  mov     rcx, rax; Block
0x18000c625  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c62a  inc     ebx
0x18000c62c  cmp     ebx, edi
0x18000c62e  jl      short loc_18000C604
0x18000c630  mov     rcx, [rsi]
0x18000c633  xor     r9d, r9d
0x18000c636  xor     r8d, r8d
0x18000c639  mov     edx, 14Bh
0x18000c63e  mov     rbx, [rsp+28h+arg_0]
0x18000c643  mov     rsi, [rsp+28h+arg_8]
0x18000c648  add     rsp, 20h
0x18000c64c  pop     rdi
0x18000c64d  jmp     cs:__imp_SendMessageW
```
