# FatSearchRemainderOfDirectoryForCollisions

- ea: `0x14002c910`
- end: `0x14002ca40`
- name: `FatSearchRemainderOfDirectoryForCollisions`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400268c0`
- `0x14003bea4`

## callees

- `0x14000c230`
- `0x14002c910`
- `0x140031e8c`
- `0x1400486ec`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x14002c9cc`
- `ntoskrnl!CcUnpinData` at `0x14002c9ef`
- `ntoskrnl!CcUnpinData` at `0x14005cbd3`
- `ntoskrnl!CcUnpinData` at `0x14002c9cc`
- `ntoskrnl!CcUnpinData` at `0x14002c9ef`
- `ntoskrnl!CcUnpinData` at `0x14005cbd3`

## pseudocode

```c
__int64 __fastcall FatSearchRemainderOfDirectoryForCollisions(__int64 a1, __int64 a2, __int64 a3, int a4, int *a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  PVOID v11; // rcx
  __int64 v13; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+68h] [rbp-A0h] BYREF
  PVOID Bcb; // [rsp+70h] [rbp-98h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-90h] BYREF
  __int64 v17; // [rsp+88h] [rbp-80h] BYREF
  __int64 v18; // [rsp+90h] [rbp-78h] BYREF

  LODWORD(v14) = a4;
  v17 = 0;
  Bcb = 0;
  LOBYTE(v13) = 0;
  *(_QWORD *)&SourceString.Length = 0x400000;
  SourceString.Buffer = (PWSTR)&v18;
  while ( 1 )
  {
    FatLocateDirent(a1, a2, a3, a4, a5, (PVOID *)&v17, &Bcb, (unsigned int *)&v14, &v13, &SourceString, 0);
    v11 = Bcb;
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      v11 = 0;
      Bcb = 0;
    }
    if ( !v17 )
      break;
    a4 = v14 + 32;
    LODWORD(v14) = v14 + 32;
  }
  if ( v11 )
  {
    CcUnpinData(v11);
    Bcb = 0;
  }
  return FatFreeStringBuffer(&SourceString, v8, v9, v10);
}

```

## disassembly

```asm
0x14002c910  mov     r11, rsp
0x14002c913  push    rbx
0x14002c914  push    rsi
0x14002c915  push    rdi
0x14002c916  push    r14
0x14002c918  sub     rsp, 0E8h
0x14002c91f  mov     rax, cs:__security_cookie
0x14002c926  xor     rax, rsp
0x14002c929  mov     [rsp+108h+var_38], rax
0x14002c931  mov     rsi, r8
0x14002c934  mov     rdi, rdx
0x14002c937  mov     rbx, rcx
0x14002c93a  mov     dword ptr [rsp+108h+var_A0], r9d
0x14002c93f  mov     r14, [rsp+108h+arg_20]
0x14002c947  mov     qword ptr [r11-80h], 0
0x14002c94f  mov     [rsp+108h+Bcb], 0
0x14002c958  mov     byte ptr [rsp+108h+var_A8], 0
0x14002c95d  mov     qword ptr [rsp+108h+var_90.Length], 400000h
0x14002c966  lea     rax, [r11-78h]
0x14002c96a  mov     [r11-88h], rax
0x14002c971  mov     [rsp+108h+var_B8], 0; __int64
0x14002c97a  lea     rax, [rsp+108h+var_90]
0x14002c97f  mov     [rsp+108h+SourceString], rax; SourceString
0x14002c984  lea     rax, [rsp+108h+var_A8]
0x14002c989  mov     [rsp+108h+var_C8], rax; __int64
0x14002c98e  lea     rax, [rsp+108h+var_A0]
0x14002c993  mov     [rsp+108h+var_D0], rax; __int64
0x14002c998  lea     rax, [rsp+108h+Bcb]
0x14002c99d  mov     [rsp+108h+var_D8], rax; __int64
0x14002c9a2  lea     rax, [rsp+108h+var_80]
0x14002c9aa  mov     [rsp+108h+var_E0], rax; __int64
0x14002c9af  mov     [rsp+108h+var_E8], r14; __int64
0x14002c9b4  mov     r8, rsi; int
0x14002c9b7  mov     rdx, rdi; int
0x14002c9ba  mov     rcx, rbx; int
0x14002c9bd  call    FatLocateDirent
0x14002c9c2  mov     rcx, [rsp+108h+Bcb]; Bcb
0x14002c9c7  test    rcx, rcx
0x14002c9ca  jz      short loc_14002C9DF
0x14002c9cc  call    cs:__imp_CcUnpinData
0x14002c9d3  nop     dword ptr [rax+rax+00h]
0x14002c9d8  xor     ecx, ecx; Bcb
0x14002c9da  mov     [rsp+108h+Bcb], rcx
0x14002c9df  cmp     [rsp+108h+var_80], 0
0x14002c9e8  jnz     short loc_14002CA2C
0x14002c9ea  test    rcx, rcx
0x14002c9ed  jz      short loc_14002CA04
0x14002c9ef  call    cs:__imp_CcUnpinData
0x14002c9f6  nop     dword ptr [rax+rax+00h]
0x14002c9fb  mov     [rsp+108h+Bcb], 0
0x14002ca04  lea     rcx, [rsp+108h+var_90]
0x14002ca09  call    FatFreeStringBuffer
0x14002ca0e  mov     rcx, [rsp+108h+var_38]
0x14002ca16  xor     rcx, rsp; StackCookie
0x14002ca19  call    __security_check_cookie
0x14002ca1e  add     rsp, 0E8h
0x14002ca25  pop     r14
0x14002ca27  pop     rdi
0x14002ca28  pop     rsi
0x14002ca29  pop     rbx
0x14002ca2a  retn
0x14002ca2c  mov     r9d, dword ptr [rsp+108h+var_A0]
0x14002ca31  add     r9d, 20h ; ' '
0x14002ca35  mov     dword ptr [rsp+108h+var_A0], r9d
0x14002ca3a  jmp     loc_14002C971
0x14005cbc1  push    rbp
0x14005cbc3  sub     rsp, 60h
0x14005cbc7  mov     rbp, rdx
0x14005cbca  mov     rcx, [rbp+70h]; Bcb
0x14005cbce  test    rcx, rcx
0x14005cbd1  jz      short loc_14005CBE7
0x14005cbd3  call    cs:__imp_CcUnpinData
0x14005cbda  nop     dword ptr [rax+rax+00h]
0x14005cbdf  mov     qword ptr [rbp+70h], 0
0x14005cbe7  lea     rcx, [rbp+78h]
0x14005cbeb  call    FatFreeStringBuffer
0x14005cbf0  nop
0x14005cbf1  add     rsp, 60h
0x14005cbf5  pop     rbp
0x14005cbf6  retn
```
