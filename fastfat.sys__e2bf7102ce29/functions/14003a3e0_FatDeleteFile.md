# FatDeleteFile

- ea: `0x14003a3e0`
- end: `0x14003a54a`
- name: `FatDeleteFile`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14003172c`
- `0x14003bea4`

## callees

- `0x140023ad4`
- `0x140031468`
- `0x14003a3e0`
- `0x140047960`
- `0x140048184`
- `0x1400492a4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003a44f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003a44f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a47b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a47b`
- `ntoskrnl!KeBugCheckEx` at `0x14003a4a2`
- `ntoskrnl!KeBugCheckEx` at `0x14003a4a2`

## pseudocode

```c
void __fastcall FatDeleteFile(__int64 a1, __int64 a2, int a3, int a4, __int64 a5, __int64 a6)
{
  _QWORD *v9; // r14
  _QWORD *i; // rsi
  _QWORD *v11; // rdi
  struct _ERESOURCE *v12; // rbx
  _DWORD *Fcb; // rbx
  __int64 v14; // rcx
  _DWORD *v15; // [rsp+88h] [rbp+10h] BYREF
  int v16; // [rsp+90h] [rbp+18h]

  v16 = a3;
  v9 = (_QWORD *)(a2 + 320);
  for ( i = *(_QWORD **)(a2 + 320); i != v9; i = (_QWORD *)*i )
  {
    v11 = i - 20;
    if ( (i[4] & 0x100) != 0 && *((_DWORD *)v11 + 61) == a4 )
    {
      if ( *((_DWORD *)v11 + 57) )
        KeBugCheckEx(0x23u, 0x1015BBu, 0, 0, 0);
      FatRemoveNames(0, (__int64)(i - 20));
      v12 = (struct _ERESOURCE *)v11[2];
      ExAcquireResourceExclusiveLite(v12, 1u);
      *((_DWORD *)v11 + 48) |= 1u;
      *((_DWORD *)v11 + 70) = 0;
      v11[5] = 0;
      v11[4] = 0;
      *((_DWORD *)v11 + 32) = 0;
      ExReleaseResourceLite(v12);
    }
  }
  Fcb = FatCreateFcb(0, *(_QWORD *)(a2 + 184), a2, v16, a4, a5, a6, 0, 0, 0);
  v15 = Fcb;
  Fcb[8] = 0;
  FatTruncateFileAllocation(a1, Fcb, 0);
  FatDeleteDirent(a1, (__int64)Fcb, 0, 1);
  FatDeleteFcb(v14, (__int64 *)&v15);
}

```

## disassembly

```asm
0x14003a3e0  mov     [rsp+arg_0], rbx
0x14003a3e5  mov     [rsp+arg_18], rsi
0x14003a3ea  mov     [rsp+arg_10], r8d
0x14003a3ef  push    rdi
0x14003a3f0  push    r12
0x14003a3f2  push    r13
0x14003a3f4  push    r14
0x14003a3f6  push    r15
0x14003a3f8  sub     rsp, 50h
0x14003a3fc  mov     r13d, r9d
0x14003a3ff  mov     r15, rdx
0x14003a402  mov     r12, rcx
0x14003a405  lea     r14, [rdx+140h]
0x14003a40c  mov     rsi, [r14]
0x14003a40f  xor     ecx, ecx
0x14003a411  cmp     rsi, r14
0x14003a414  jz      loc_14003A4AF
0x14003a41a  lea     rdi, [rsi-0A0h]
0x14003a421  test    dword ptr [rdi+0C0h], 100h
0x14003a42b  jz      short loc_14003A489
0x14003a42d  cmp     [rdi+0F4h], r13d
0x14003a434  jnz     short loc_14003A489
0x14003a436  cmp     [rdi+0E4h], ecx
0x14003a43c  jnz     short loc_14003A48E
0x14003a43e  mov     rdx, rdi
0x14003a441  call    FatRemoveNames
0x14003a446  mov     rbx, [rdi+10h]
0x14003a44a  mov     dl, 1; Wait
0x14003a44c  mov     rcx, rbx; Resource
0x14003a44f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003a456  nop     dword ptr [rax+rax+00h]
0x14003a45b  or      dword ptr [rdi+0C0h], 1
0x14003a462  xor     eax, eax
0x14003a464  mov     [rdi+118h], eax
0x14003a46a  mov     [rdi+28h], rax
0x14003a46e  mov     [rdi+20h], rax
0x14003a472  mov     [rdi+80h], eax
0x14003a478  mov     rcx, rbx; Resource
0x14003a47b  call    cs:__imp_ExReleaseResourceLite
0x14003a482  nop     dword ptr [rax+rax+00h]
0x14003a487  xor     ecx, ecx
0x14003a489  mov     rsi, [rsi]
0x14003a48c  jmp     short loc_14003A411
0x14003a48e  mov     [rsp+78h+BugCheckParameter4], rcx; BugCheckParameter4
0x14003a493  xor     r9d, r9d; BugCheckParameter3
0x14003a496  xor     r8d, r8d; BugCheckParameter2
0x14003a499  mov     edx, 1015BBh; BugCheckParameter1
0x14003a49e  lea     ecx, [r9+23h]; BugCheckCode
0x14003a4a2  call    cs:__imp_KeBugCheckEx
0x14003a4af  mov     [rsp+78h+var_30], cl
0x14003a4b3  mov     [rsp+78h+var_38], cl
0x14003a4b7  mov     [rsp+78h+var_40], rcx
0x14003a4bc  mov     rax, [rsp+78h+arg_28]
0x14003a4c4  mov     [rsp+78h+var_48], rax
0x14003a4c9  mov     rax, [rsp+78h+arg_20]
0x14003a4d1  mov     [rsp+78h+var_50], rax
0x14003a4d6  mov     dword ptr [rsp+78h+BugCheckParameter4], r13d
0x14003a4db  mov     r9d, [rsp+78h+arg_10]
0x14003a4e3  mov     r8, r15
0x14003a4e6  mov     rdx, [r15+0B8h]
0x14003a4ed  call    FatCreateFcb
0x14003a4f2  mov     rbx, rax
0x14003a4f5  mov     [rsp+78h+arg_8], rax
0x14003a4fd  xor     eax, eax
0x14003a4ff  mov     [rbx+20h], eax
0x14003a502  xor     r8d, r8d
0x14003a505  mov     rdx, rbx
0x14003a508  mov     rcx, r12
0x14003a50b  call    FatTruncateFileAllocation
0x14003a510  mov     r9b, 1
0x14003a513  xor     r8d, r8d
0x14003a516  mov     rdx, rbx
0x14003a519  mov     rcx, r12
0x14003a51c  call    FatDeleteDirent
0x14003a521  nop
0x14003a522  lea     rdx, [rsp+78h+arg_8]
0x14003a52a  call    FatDeleteFcb
0x14003a52f  lea     r11, [rsp+78h+var_28]
0x14003a534  mov     rbx, [r11+30h]
0x14003a538  mov     rsi, [r11+48h]
0x14003a53c  mov     rsp, r11
0x14003a53f  pop     r15
0x14003a541  pop     r14
0x14003a543  pop     r13
0x14003a545  pop     r12
0x14003a547  pop     rdi
0x14003a548  retn
0x14005e3d6  push    rbp
0x14005e3d8  sub     rsp, 50h
0x14005e3dc  mov     rbp, rdx
0x14005e3df  lea     rdx, [rbp+88h]
0x14005e3e6  call    FatDeleteFcb
0x14005e3eb  nop
0x14005e3ec  add     rsp, 50h
0x14005e3f0  pop     rbp
0x14005e3f1  retn
```
