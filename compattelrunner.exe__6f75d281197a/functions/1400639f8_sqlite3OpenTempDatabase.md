# sqlite3OpenTempDatabase

- ea: `0x1400639f8`
- end: `0x140063aa6`
- name: `sqlite3OpenTempDatabase`
- size: `174`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14002bf38`
- `0x14004c754`
- `0x1400516cc`
- `0x140066370`

## callees

- `0x14004efa0`
- `0x14004fb9c`
- `0x1400560c4`
- `0x1400636dc`
- `0x1400639f8`

## string_xrefs

- `0x140063a51`: `unable to open a temporary database file for storing temporary tables`

## pseudocode

```c
__int64 __fastcall sqlite3OpenTempDatabase(__int64 **a1)
{
  __int64 *v1; // rdi
  __int64 v3; // rcx
  int v4; // esi
  __int64 v6; // rcx
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1;
  if ( !*(_QWORD *)((*a1)[4] + 40) && !*((_BYTE *)a1 + 299) )
  {
    v3 = *v1;
    v7 = 0;
    v4 = sqlite3BtreeOpen(v3, 0, v1, &v7, 0, 542);
    if ( v4 )
    {
      sqlite3ErrorMsg(a1, "unable to open a temporary database file for storing temporary tables");
      *((_DWORD *)a1 + 6) = v4;
      return 1;
    }
    v6 = v7;
    *(_QWORD *)(v1[4] + 40) = v7;
    if ( (unsigned int)sqlite3BtreeSetPageSize(v6, *((unsigned int *)v1 + 29), 0, 0) == 7 )
    {
      sqlite3OomFault(v1);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400639f8  mov     r11, rsp
0x1400639fb  mov     [r11+10h], rbx
0x1400639ff  mov     [r11+18h], rsi
0x140063a03  push    rdi
0x140063a04  sub     rsp, 30h
0x140063a08  mov     rdi, [rcx]
0x140063a0b  mov     rbx, rcx
0x140063a0e  mov     rax, [rdi+20h]
0x140063a12  cmp     qword ptr [rax+28h], 0
0x140063a17  jnz     short loc_140063A94
0x140063a19  cmp     byte ptr [rcx+12Bh], 0
0x140063a20  jnz     short loc_140063A94
0x140063a22  mov     rcx, [rdi]
0x140063a25  lea     r9, [r11+8]
0x140063a29  mov     [rsp+38h+var_10], 21Eh
0x140063a31  mov     r8, rdi
0x140063a34  xor     edx, edx
0x140063a36  mov     [rsp+38h+var_18], 0
0x140063a3e  mov     qword ptr [r11+8], 0
0x140063a46  call    sqlite3BtreeOpen
0x140063a4b  mov     esi, eax
0x140063a4d  test    eax, eax
0x140063a4f  jz      short loc_140063A6A
0x140063a51  lea     rdx, aUnableToOpenAT; "unable to open a temporary database fil"...
0x140063a58  mov     rcx, rbx
0x140063a5b  call    sqlite3ErrorMsg
0x140063a60  mov     [rbx+18h], esi
0x140063a63  mov     eax, 1
0x140063a68  jmp     short loc_140063A96
0x140063a6a  mov     rax, [rdi+20h]
0x140063a6e  xor     r9d, r9d
0x140063a71  mov     rcx, [rsp+38h+arg_0]
0x140063a76  xor     r8d, r8d
0x140063a79  mov     [rax+28h], rcx
0x140063a7d  mov     edx, [rdi+74h]
0x140063a80  call    sqlite3BtreeSetPageSize
0x140063a85  cmp     eax, 7
0x140063a88  jnz     short loc_140063A94
0x140063a8a  mov     rcx, rdi
0x140063a8d  call    sqlite3OomFault
0x140063a92  jmp     short loc_140063A63
0x140063a94  xor     eax, eax
0x140063a96  mov     rbx, [rsp+38h+arg_8]
0x140063a9b  mov     rsi, [rsp+38h+arg_10]
0x140063aa0  add     rsp, 30h
0x140063aa4  pop     rdi
0x140063aa5  retn
```
