# SafeArrayAccessDataUnique_wchar_t___

- ea: `0x1800293a0`
- end: `0x1800293f2`
- name: `SafeArrayAccessDataUnique_wchar_t___`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001443c`
- `0x18001f990`
- `0x18002acc0`

## callees

- `0x1800293a0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800293bb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800293bb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800293da`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800293da`

## pseudocode

```c
__int64 __fastcall SafeArrayAccessDataUnique_wchar_t___(SAFEARRAY **a1, SAFEARRAY **a2, void **a3)
{
  HRESULT v5; // edi
  SAFEARRAY *v6; // r8
  SAFEARRAY *v7; // rcx

  v5 = SafeArrayAccessData(*a1, a3);
  if ( v5 < 0 )
    v6 = 0;
  else
    v6 = *a1;
  v7 = *a2;
  *a2 = v6;
  if ( v7 )
    SafeArrayUnaccessData(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800293a0  mov     [rsp+arg_0], rbx
0x1800293a5  mov     [rsp+arg_8], rsi
0x1800293aa  push    rdi
0x1800293ab  sub     rsp, 20h
0x1800293af  mov     rbx, rdx
0x1800293b2  mov     rsi, rcx
0x1800293b5  mov     rcx, [rcx]; psa
0x1800293b8  mov     rdx, r8; ppvData
0x1800293bb  call    cs:__imp_SafeArrayAccessData
0x1800293c1  mov     edi, eax
0x1800293c3  test    eax, eax
0x1800293c5  js      short loc_1800293CC
0x1800293c7  mov     r8, [rsi]
0x1800293ca  jmp     short loc_1800293CF
0x1800293cc  xor     r8d, r8d
0x1800293cf  mov     rcx, [rbx]; psa
0x1800293d2  mov     [rbx], r8
0x1800293d5  test    rcx, rcx
0x1800293d8  jz      short loc_1800293E0
0x1800293da  call    cs:__imp_SafeArrayUnaccessData
0x1800293e0  mov     rbx, [rsp+28h+arg_0]
0x1800293e5  mov     eax, edi
0x1800293e7  mov     rsi, [rsp+28h+arg_8]
0x1800293ec  add     rsp, 20h
0x1800293f0  pop     rdi
0x1800293f1  retn
```
