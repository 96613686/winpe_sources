# CAPITempBuffer<ushort,1>::SetSize(int,bool)

- ea: `0x14000810c`
- end: `0x140008176`
- name: `?SetSize@?$CAPITempBuffer@G$00@@QEAA_NH_N@Z`
- size: `106`
- prototype: `char __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011e4`
- `0x1400049a4`
- `0x140008300`
- `0x140008b10`

## callees

- `0x14000810c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140008131`
- `KERNEL32!GlobalAlloc` at `0x140008131`
- `KERNEL32!GlobalFree` at `0x140008158`
- `KERNEL32!GlobalFree` at `0x140008158`

## pseudocode

```c
char __fastcall CAPITempBuffer<unsigned short,1>::SetSize(__int64 a1, int a2)
{
  HGLOBAL v4; // rdi
  __int64 v5; // rax
  char result; // al

  if ( a2 <= 1 )
  {
    v4 = (HGLOBAL)(a1 + 16);
    v5 = a1 + 16;
  }
  else
  {
    v4 = GlobalAlloc(0x40u, 2LL * a2);
    v5 = a1 + 16;
  }
  if ( !v4 )
    return 0;
  if ( *(_QWORD *)a1 != v5 )
    GlobalFree(*(HGLOBAL *)a1);
  *(_QWORD *)a1 = v4;
  result = 1;
  *(_DWORD *)(a1 + 8) = a2;
  return result;
}

```

## disassembly

```asm
0x14000810c  mov     [rsp+arg_0], rbx
0x140008111  mov     [rsp+arg_8], rsi
0x140008116  push    rdi
0x140008117  sub     rsp, 20h
0x14000811b  movsxd  rsi, edx
0x14000811e  mov     rbx, rcx
0x140008121  cmp     esi, 1
0x140008124  jle     short loc_140008140
0x140008126  mov     rdx, rsi
0x140008129  mov     ecx, 40h ; '@'; uFlags
0x14000812e  add     rdx, rdx; dwBytes
0x140008131  call    cs:__imp_GlobalAlloc
0x140008137  mov     rdi, rax
0x14000813a  lea     rax, [rbx+10h]
0x14000813e  jmp     short loc_140008147
0x140008140  lea     rdi, [rcx+10h]
0x140008144  mov     rax, rdi
0x140008147  test    rdi, rdi
0x14000814a  jnz     short loc_140008150
0x14000814c  xor     al, al
0x14000814e  jmp     short loc_140008166
0x140008150  cmp     [rbx], rax
0x140008153  jz      short loc_14000815E
0x140008155  mov     rcx, [rbx]; hMem
0x140008158  call    cs:__imp_GlobalFree
0x14000815e  mov     [rbx], rdi
0x140008161  mov     al, 1
0x140008163  mov     [rbx+8], esi
0x140008166  mov     rbx, [rsp+28h+arg_0]
0x14000816b  mov     rsi, [rsp+28h+arg_8]
0x140008170  add     rsp, 20h
0x140008174  pop     rdi
0x140008175  retn
```
