# CTxtSelection::DeleteCaretBitmap(int)

- ea: `0x18007eee0`
- end: `0x18007ef42`
- name: `?DeleteCaretBitmap@CTxtSelection@@QEAAHH@Z`
- size: `98`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d670`
- `0x18005d210`
- `0x18007ea5c`

## callees

- `0x18007eee0`

## import_xrefs

- `USER32!DestroyCaret` at `0x18007ef04`
- `USER32!DestroyCaret` at `0x18007ef04`
- `GDI32!DeleteObject` at `0x18007ef11`
- `GDI32!DeleteObject` at `0x18007ef11`

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
0x18007eee0  mov     [rsp+arg_0], rbx
0x18007eee5  mov     [rsp+arg_8], rsi
0x18007eeea  push    rdi
0x18007eeeb  sub     rsp, 20h
0x18007eeef  xor     edi, edi
0x18007eef1  mov     esi, edx
0x18007eef3  mov     rbx, rcx
0x18007eef6  cmp     [rcx+0B0h], rdi
0x18007eefd  jz      short loc_18007EF22
0x18007eeff  mov     edi, 1
0x18007ef04  call    cs:__imp_DestroyCaret
0x18007ef0a  mov     rcx, [rbx+0B0h]; ho
0x18007ef11  call    cs:__imp_DeleteObject
0x18007ef17  mov     qword ptr [rbx+0B0h], 0
0x18007ef22  test    esi, esi
0x18007ef24  jz      short loc_18007EF30
0x18007ef26  mov     dword ptr [rbx+0B8h], 0
0x18007ef30  mov     rbx, [rsp+28h+arg_0]
0x18007ef35  mov     eax, edi
0x18007ef37  mov     rsi, [rsp+28h+arg_8]
0x18007ef3c  add     rsp, 20h
0x18007ef40  pop     rdi
0x18007ef41  retn
```
