# CTxtSelection::DeleteCaretBitmap(int)

- ea: `0x1800c08f4`
- end: `0x1800c097e`
- name: `?DeleteCaretBitmap@CTxtSelection@@QEAAHH@Z`
- size: `138`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b468`
- `0x1800c03b0`
- `0x1800c087c`

## callees

- `0x1800c08f4`
- `0x180107a60`

## import_xrefs

- `ext-ms-win-ntuser-caret-l1-1-0!DestroyCaret` at `0x1800c0942`
- `ext-ms-win-ntuser-caret-l1-1-0!DestroyCaret` at `0x1800c0942`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800c0955`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800c0955`

## pseudocode

```c
__int64 __fastcall CTxtSelection::DeleteCaretBitmap(CTxtSelection *this, int a2)
{
  unsigned int v2; // edi
  __int64 v6; // rax
  CTxtEdit *v7; // rcx

  v2 = 0;
  if ( *((_QWORD *)this + 29) )
  {
    v6 = *((_QWORD *)this + 3);
    v2 = 1;
    if ( v6 && (v7 = *(CTxtEdit **)(v6 + 40)) != 0 )
      CTxtEdit::TxDestroyCaret(v7);
    else
      DestroyCaret();
    DeleteObject(*((HGDIOBJ *)this + 29));
    *((_QWORD *)this + 29) = 0;
  }
  if ( a2 )
    *((_DWORD *)this + 60) = 0;
  return v2;
}

```

## disassembly

```asm
0x1800c08f4  mov     [rsp+arg_0], rbx
0x1800c08f9  mov     [rsp+arg_8], rsi
0x1800c08fe  push    rdi
0x1800c08ff  sub     rsp, 20h
0x1800c0903  xor     edi, edi
0x1800c0905  mov     esi, edx
0x1800c0907  mov     rbx, rcx
0x1800c090a  cmp     [rcx+0E8h], rdi
0x1800c0911  jnz     short loc_1800C0934
0x1800c0913  test    esi, esi
0x1800c0915  jz      short loc_1800C0921
0x1800c0917  mov     dword ptr [rbx+0F0h], 0
0x1800c0921  mov     rbx, [rsp+28h+arg_0]
0x1800c0926  mov     eax, edi
0x1800c0928  mov     rsi, [rsp+28h+arg_8]
0x1800c092d  add     rsp, 20h
0x1800c0931  pop     rdi
0x1800c0932  retn
0x1800c0934  mov     rax, [rcx+18h]
0x1800c0938  mov     edi, 1
0x1800c093d  test    rax, rax
0x1800c0940  jnz     short loc_1800C096E
0x1800c0942  call    cs:__imp_DestroyCaret
0x1800c0949  nop     dword ptr [rax+rax+00h]
0x1800c094e  mov     rcx, [rbx+0E8h]; ho
0x1800c0955  call    cs:__imp_DeleteObject
0x1800c095c  nop     dword ptr [rax+rax+00h]
0x1800c0961  mov     qword ptr [rbx+0E8h], 0
0x1800c096c  jmp     short loc_1800C0913
0x1800c096e  mov     rcx, [rax+28h]; this
0x1800c0972  test    rcx, rcx
0x1800c0975  jz      short loc_1800C0942
0x1800c0977  call    ?TxDestroyCaret@CTxtEdit@@QEAAXXZ; CTxtEdit::TxDestroyCaret(void)
0x1800c097c  jmp     short loc_1800C094E
```
