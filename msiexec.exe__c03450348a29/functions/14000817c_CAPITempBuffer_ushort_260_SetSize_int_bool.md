# CAPITempBuffer<ushort,260>::SetSize(int,bool)

- ea: `0x14000817c`
- end: `0x1400081e9`
- name: `?SetSize@?$CAPITempBuffer@G$0BAE@@@QEAA_NH_N@Z`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011e4`
- `0x140007568`

## callees

- `0x14000817c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1400081a4`
- `KERNEL32!GlobalAlloc` at `0x1400081a4`
- `KERNEL32!GlobalFree` at `0x1400081cb`
- `KERNEL32!GlobalFree` at `0x1400081cb`

## pseudocode

```c
char __fastcall CAPITempBuffer<unsigned short,260>::SetSize(__int64 a1, int a2)
{
  HGLOBAL v4; // rdi
  __int64 v5; // rax
  char result; // al

  if ( a2 <= 260 )
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
0x14000817c  mov     [rsp+arg_0], rbx
0x140008181  mov     [rsp+arg_8], rsi
0x140008186  push    rdi
0x140008187  sub     rsp, 20h
0x14000818b  movsxd  rsi, edx
0x14000818e  mov     rbx, rcx
0x140008191  cmp     esi, 104h
0x140008197  jle     short loc_1400081B3
0x140008199  mov     rdx, rsi
0x14000819c  mov     ecx, 40h ; '@'; uFlags
0x1400081a1  add     rdx, rdx; dwBytes
0x1400081a4  call    cs:__imp_GlobalAlloc
0x1400081aa  mov     rdi, rax
0x1400081ad  lea     rax, [rbx+10h]
0x1400081b1  jmp     short loc_1400081BA
0x1400081b3  lea     rdi, [rcx+10h]
0x1400081b7  mov     rax, rdi
0x1400081ba  test    rdi, rdi
0x1400081bd  jnz     short loc_1400081C3
0x1400081bf  xor     al, al
0x1400081c1  jmp     short loc_1400081D9
0x1400081c3  cmp     [rbx], rax
0x1400081c6  jz      short loc_1400081D1
0x1400081c8  mov     rcx, [rbx]; hMem
0x1400081cb  call    cs:__imp_GlobalFree
0x1400081d1  mov     [rbx], rdi
0x1400081d4  mov     al, 1
0x1400081d6  mov     [rbx+8], esi
0x1400081d9  mov     rbx, [rsp+28h+arg_0]
0x1400081de  mov     rsi, [rsp+28h+arg_8]
0x1400081e3  add     rsp, 20h
0x1400081e7  pop     rdi
0x1400081e8  retn
```
