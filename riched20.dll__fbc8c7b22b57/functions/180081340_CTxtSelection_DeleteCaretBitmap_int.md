# CTxtSelection::DeleteCaretBitmap(int)

- ea: `0x180081340`
- end: `0x1800813af`
- name: `?DeleteCaretBitmap@CTxtSelection@@QEAAHH@Z`
- size: `111`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dad0`
- `0x18005e8d4`
- `0x180080ec0`

## callees

- `0x180081340`

## import_xrefs

- `USER32!DestroyCaret` at `0x180081364`
- `USER32!DestroyCaret` at `0x180081364`
- `GDI32!DeleteObject` at `0x180081377`
- `GDI32!DeleteObject` at `0x180081377`

## pseudocode

```c
__int64 __fastcall CTxtSelection::DeleteCaretBitmap(HGDIOBJ *this, int a2)
{
  unsigned int v2; // edi

  v2 = 0;
  if ( this[22] )
  {
    v2 = 1;
    DestroyCaret();
    DeleteObject(this[22]);
    this[22] = 0;
  }
  if ( a2 )
    *((_DWORD *)this + 46) = 0;
  return v2;
}

```

## disassembly

```asm
0x180081340  mov     [rsp+arg_0], rbx
0x180081345  mov     [rsp+arg_8], rsi
0x18008134a  push    rdi
0x18008134b  sub     rsp, 20h
0x18008134f  xor     edi, edi
0x180081351  mov     esi, edx
0x180081353  mov     rbx, rcx
0x180081356  cmp     [rcx+0B0h], rdi
0x18008135d  jz      short loc_18008138E
0x18008135f  mov     edi, 1
0x180081364  call    cs:__imp_DestroyCaret
0x18008136b  nop     dword ptr [rax+rax+00h]
0x180081370  mov     rcx, [rbx+0B0h]; ho
0x180081377  call    cs:__imp_DeleteObject
0x18008137e  nop     dword ptr [rax+rax+00h]
0x180081383  mov     qword ptr [rbx+0B0h], 0
0x18008138e  test    esi, esi
0x180081390  jz      short loc_18008139C
0x180081392  mov     dword ptr [rbx+0B8h], 0
0x18008139c  mov     rbx, [rsp+28h+arg_0]
0x1800813a1  mov     eax, edi
0x1800813a3  mov     rsi, [rsp+28h+arg_8]
0x1800813a8  add     rsp, 20h
0x1800813ac  pop     rdi
0x1800813ad  retn
```
