# RxSecurityDescriptorDelete

- ea: `0x14004ad3c`
- end: `0x14004adba`
- name: `RxSecurityDescriptorDelete`
- size: `126`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400491d4`

## callees

- `0x14004ad3c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ad8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ada7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ad8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ada7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc9f`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14004ad69`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14004ad69`

## pseudocode

```c
void __fastcall RxSecurityDescriptorDelete(PVOID P, int a2)
{
  PVOID Pa; // [rsp+20h] [rbp-18h] BYREF
  BOOLEAN v4; // [rsp+50h] [rbp+18h] BYREF
  BOOLEAN v5; // [rsp+58h] [rbp+20h] BYREF

  Pa = 0;
  if ( !a2 )
  {
    v4 = 0;
    v5 = 0;
    if ( RtlGetDaclSecurityDescriptor(P, &v4, (PACL *)&Pa, &v5) >= 0 )
    {
      if ( v4 )
      {
        ExFreePoolWithTag(Pa, 0x734D7852u);
        Pa = 0;
      }
    }
  }
  ExFreePoolWithTag(P, 0x734D7852u);
}

```

## disassembly

```asm
0x14004ad3c  mov     rax, rsp
0x14004ad3f  mov     [rax+8], rcx
0x14004ad43  push    rbx
0x14004ad44  sub     rsp, 30h
0x14004ad48  mov     rbx, rcx
0x14004ad4b  mov     qword ptr [rax-18h], 0
0x14004ad53  test    edx, edx
0x14004ad55  jnz     short loc_14004AD9F
0x14004ad57  mov     [rax+18h], dl
0x14004ad5a  mov     [rax+20h], dl
0x14004ad5d  lea     r9, [rax+20h]; DaclDefaulted
0x14004ad61  lea     r8, [rax-18h]; Dacl
0x14004ad65  lea     rdx, [rax+18h]; DaclPresent
0x14004ad69  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14004ad70  nop     dword ptr [rax+rax+00h]
0x14004ad75  test    eax, eax
0x14004ad77  js      short loc_14004AD9F
0x14004ad79  cmp     [rsp+38h+arg_10], 0
0x14004ad7e  jz      short loc_14004AD9F
0x14004ad80  mov     edx, 734D7852h; Tag
0x14004ad85  mov     rcx, [rsp+38h+P]; P
0x14004ad8a  call    cs:__imp_ExFreePoolWithTag
0x14004ad91  nop     dword ptr [rax+rax+00h]
0x14004ad96  mov     [rsp+38h+P], 0
0x14004ad9f  mov     edx, 734D7852h; Tag
0x14004ada4  mov     rcx, rbx; P
0x14004ada7  call    cs:__imp_ExFreePoolWithTag
0x14004adae  nop     dword ptr [rax+rax+00h]
0x14004adb3  add     rsp, 30h
0x14004adb7  pop     rbx
0x14004adb8  retn
0x14007bc8d  push    rbp
0x14007bc8f  sub     rsp, 20h
0x14007bc93  mov     rbp, rdx
0x14007bc96  mov     edx, 734D7852h; Tag
0x14007bc9b  mov     rcx, [rbp+40h]; P
0x14007bc9f  call    cs:__imp_ExFreePoolWithTag
0x14007bca6  nop     dword ptr [rax+rax+00h]
0x14007bcab  nop
0x14007bcac  add     rsp, 20h
0x14007bcb0  pop     rbp
0x14007bcb1  retn
```
