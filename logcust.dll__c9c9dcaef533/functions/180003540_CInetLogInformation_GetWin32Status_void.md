# CInetLogInformation::GetWin32Status(void)

- ea: `0x180003540`
- end: `0x1800035fb`
- name: `?GetWin32Status@CInetLogInformation@@UEAAKXZ`
- size: `187`
- prototype: `unsigned int __fastcall(CInetLogInformation *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003540`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall CInetLogInformation::GetWin32Status(CInetLogInformation *this)
{
  __int64 v1; // rcx
  __int64 v2; // rax
  unsigned int v3; // ecx
  _QWORD v5[3]; // [rsp+60h] [rbp-18h] BYREF
  __int16 v6; // [rsp+80h] [rbp+8h] BYREF
  __int16 v7; // [rsp+88h] [rbp+10h] BYREF
  __int16 v8; // [rsp+90h] [rbp+18h] BYREF
  int v9; // [rsp+98h] [rbp+20h] BYREF

  v1 = *((_QWORD *)this + 8);
  v8 = 0;
  v7 = 0;
  v6 = 0;
  v5[0] = 0;
  v9 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 32LL))(v1);
  (*(void (__fastcall **)(__int64, __int16 *, __int16 *, _QWORD *, __int16 *, int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v2 + 184LL))(
    v2,
    &v8,
    &v7,
    v5,
    &v6,
    &v9,
    0,
    0,
    0,
    0);
  v3 = v9;
  if ( v9 < 0 && (v9 & 0x1FFF0000) == 0x70000 )
    return (unsigned __int16)v9;
  return v3;
}

```

## disassembly

```asm
0x180003540  mov     r11, rsp
0x180003543  sub     rsp, 78h
0x180003547  mov     rcx, [rcx+40h]
0x18000354b  xor     eax, eax
0x18000354d  mov     [r11+18h], ax
0x180003552  mov     [r11+10h], ax
0x180003557  mov     [r11+8], ax
0x18000355c  mov     [r11-18h], rax
0x180003560  mov     [r11+20h], eax
0x180003564  mov     rax, [rcx]
0x180003567  mov     rax, [rax+20h]
0x18000356b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003570  mov     [rsp+78h+var_30], 0
0x180003579  lea     r9, [rsp+78h+var_18]
0x18000357e  mov     [rsp+78h+var_38], 0
0x180003587  lea     r8, [rsp+78h+arg_8]
0x18000358f  mov     r10, rax
0x180003592  mov     [rsp+78h+var_40], 0
0x18000359b  mov     rcx, [rax]
0x18000359e  lea     rdx, [rsp+78h+arg_10]
0x1800035a6  mov     [rsp+78h+var_48], 0
0x1800035af  mov     rax, [rcx+0B8h]
0x1800035b6  lea     rcx, [rsp+78h+arg_18]
0x1800035be  mov     [rsp+78h+var_50], rcx
0x1800035c3  lea     rcx, [rsp+78h+arg_0]
0x1800035cb  mov     [rsp+78h+var_58], rcx
0x1800035d0  mov     rcx, r10
0x1800035d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d8  mov     ecx, [rsp+78h+arg_18]
0x1800035df  test    ecx, ecx
0x1800035e1  jns     short loc_1800035F4
0x1800035e3  mov     eax, ecx
0x1800035e5  and     eax, 1FFF0000h
0x1800035ea  cmp     eax, 70000h
0x1800035ef  jnz     short loc_1800035F4
0x1800035f1  movzx   ecx, cx
0x1800035f4  mov     eax, ecx
0x1800035f6  add     rsp, 78h
0x1800035fa  retn
```
