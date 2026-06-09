# DwmHLSurfGetDirtyRgn

- ea: `0x18003bbe0`
- end: `0x18003bd20`
- name: `DwmHLSurfGetDirtyRgn`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18003bbe0`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003bcc6`
- `GDI32!DeleteObject` at `0x18003bce6`
- `GDI32!DeleteObject` at `0x18003bd05`
- `GDI32!DeleteObject` at `0x18003bcc6`
- `GDI32!DeleteObject` at `0x18003bce6`
- `GDI32!DeleteObject` at `0x18003bd05`
- `win32u!NtGdiHLSurfGetInformation` at `0x18003bc35`
- `win32u!NtGdiHLSurfGetInformation` at `0x18003bc35`

## pseudocode

```c
__int64 __fastcall DwmHLSurfGetDirtyRgn(
        __int64 a1,
        void *a2,
        HGDIOBJ *a3,
        HGDIOBJ *a4,
        HGDIOBJ *a5,
        _QWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        _DWORD *a9)
{
  _QWORD *v9; // rbx
  unsigned int v12; // r14d
  _DWORD *v13; // rcx
  HGDIOBJ ho[2]; // [rsp+20h] [rbp-40h] BYREF
  HGDIOBJ v16[2]; // [rsp+30h] [rbp-30h]
  __int128 v17; // [rsp+40h] [rbp-20h]
  __int64 v18; // [rsp+50h] [rbp-10h]
  int v19; // [rsp+88h] [rbp+28h] BYREF

  v9 = a6;
  v18 = 0;
  ho[1] = 0;
  ho[0] = a2;
  v19 = 56;
  *(_OWORD *)v16 = 0;
  v17 = 0;
  v12 = ((__int64 (__fastcall *)(__int64, _QWORD, HGDIOBJ *, int *))NtGdiHLSurfGetInformation)(
          a1,
          a6 != 0 ? 9 : 4,
          ho,
          &v19);
  if ( a3 )
  {
    *a3 = ho[1];
  }
  else if ( ho[1] )
  {
    DeleteObject(ho[1]);
    ho[1] = 0;
  }
  if ( a4 )
  {
    *a4 = v16[0];
  }
  else if ( v16[0] )
  {
    DeleteObject(v16[0]);
    v16[0] = 0;
  }
  if ( a5 )
  {
    *a5 = v16[1];
  }
  else if ( v16[1] )
  {
    DeleteObject(v16[1]);
  }
  if ( v9 )
    *v9 = v17;
  v13 = a7;
  if ( a7 )
  {
    *a7 = DWORD2(v17);
    v13[1] = HIDWORD(v17);
  }
  if ( a8 )
    *a8 = v18;
  if ( a9 )
    *a9 = HIDWORD(v18);
  return v12;
}

```

## disassembly

```asm
0x18003bbe0  mov     [rsp-18h+arg_0], rbx
0x18003bbe5  mov     [rsp-18h+arg_10], rsi
0x18003bbea  push    rbp
0x18003bbeb  push    rdi
0x18003bbec  push    r14
0x18003bbee  mov     rbp, rsp
0x18003bbf1  sub     rsp, 60h
0x18003bbf5  mov     rbx, [rbp+arg_28]
0x18003bbf9  xor     eax, eax
0x18003bbfb  xorps   xmm0, xmm0
0x18003bbfe  mov     [rbp+var_10], rax
0x18003bc02  movups  xmmword ptr [rbp+ho], xmm0
0x18003bc06  mov     [rbp+ho], rdx
0x18003bc0a  mov     rdi, r9
0x18003bc0d  mov     rsi, r8
0x18003bc10  mov     [rbp+arg_8], 38h ; '8'
0x18003bc17  mov     rax, rbx
0x18003bc1a  lea     r9, [rbp+arg_8]
0x18003bc1e  neg     rax
0x18003bc21  lea     r8, [rbp+ho]
0x18003bc25  movups  xmmword ptr [rbp+var_30], xmm0
0x18003bc29  sbb     edx, edx
0x18003bc2b  and     edx, 5
0x18003bc2e  add     edx, 4
0x18003bc31  movups  [rbp+var_20], xmm0
0x18003bc35  call    cs:__imp_NtGdiHLSurfGetInformation
0x18003bc3b  mov     rcx, [rbp+ho+8]; ho
0x18003bc3f  mov     r14d, eax
0x18003bc42  test    rsi, rsi
0x18003bc45  jz      short loc_18003BCC1
0x18003bc47  mov     [rsi], rcx
0x18003bc4a  test    rdi, rdi
0x18003bc4d  jz      loc_18003BCD9
0x18003bc53  mov     rax, [rbp+var_30]
0x18003bc57  mov     [rdi], rax
0x18003bc5a  mov     rcx, [rbp+arg_20]
0x18003bc5e  test    rcx, rcx
0x18003bc61  jnz     loc_18003BCF9
0x18003bc67  mov     rcx, [rbp+var_30+8]; ho
0x18003bc6b  test    rcx, rcx
0x18003bc6e  jnz     loc_18003BD05
0x18003bc74  test    rbx, rbx
0x18003bc77  jz      short loc_18003BC80
0x18003bc79  mov     rax, qword ptr [rbp+var_20]
0x18003bc7d  mov     [rbx], rax
0x18003bc80  mov     rcx, [rbp+arg_30]
0x18003bc84  test    rcx, rcx
0x18003bc87  jnz     loc_18003BD10
0x18003bc8d  mov     rcx, [rbp+arg_38]
0x18003bc91  test    rcx, rcx
0x18003bc94  jz      short loc_18003BC9B
0x18003bc96  mov     eax, dword ptr [rbp+var_10]
0x18003bc99  mov     [rcx], eax
0x18003bc9b  mov     rcx, [rbp+arg_40]
0x18003bc9f  test    rcx, rcx
0x18003bca2  jz      short loc_18003BCA9
0x18003bca4  mov     eax, dword ptr [rbp+var_10+4]
0x18003bca7  mov     [rcx], eax
0x18003bca9  lea     r11, [rsp+60h+var_s0]
0x18003bcae  mov     eax, r14d
0x18003bcb1  mov     rbx, [r11+20h]
0x18003bcb5  mov     rsi, [r11+30h]
0x18003bcb9  mov     rsp, r11
0x18003bcbc  pop     r14
0x18003bcbe  pop     rdi
0x18003bcbf  pop     rbp
0x18003bcc0  retn
0x18003bcc1  test    rcx, rcx
0x18003bcc4  jz      short loc_18003BC4A
0x18003bcc6  call    cs:__imp_DeleteObject
0x18003bccc  mov     [rbp+ho+8], 0
0x18003bcd4  jmp     loc_18003BC4A
0x18003bcd9  mov     rcx, [rbp+var_30]; ho
0x18003bcdd  test    rcx, rcx
0x18003bce0  jz      loc_18003BC5A
0x18003bce6  call    cs:__imp_DeleteObject
0x18003bcec  mov     [rbp+var_30], 0
0x18003bcf4  jmp     loc_18003BC5A
0x18003bcf9  mov     rax, [rbp+var_30+8]
0x18003bcfd  mov     [rcx], rax
0x18003bd00  jmp     loc_18003BC74
0x18003bd05  call    cs:__imp_DeleteObject
0x18003bd0b  jmp     loc_18003BC74
0x18003bd10  mov     eax, dword ptr [rbp+var_20+8]
0x18003bd13  mov     [rcx], eax
0x18003bd15  mov     eax, dword ptr [rbp+var_20+0Ch]
0x18003bd18  mov     [rcx+4], eax
0x18003bd1b  jmp     loc_18003BC8D
```
