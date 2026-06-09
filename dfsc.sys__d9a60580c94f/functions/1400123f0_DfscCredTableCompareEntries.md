# DfscCredTableCompareEntries

- ea: `0x1400123f0`
- end: `0x1400124c1`
- name: `DfscCredTableCompareEntries`
- size: `209`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400035dc`
- `0x1400123f0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001243d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001243d`

## pseudocode

```c
__int64 __fastcall DfscCredTableCompareEntries(
        struct _RTL_AVL_TABLE *Table,
        const UNICODE_STRING *FirstStruct,
        const UNICODE_STRING *SecondStruct)
{
  unsigned int v3; // eax
  unsigned int v6; // edx
  unsigned int v7; // r8d
  LONG v9; // eax
  int Buffer; // eax

  v3 = *(_DWORD *)&SecondStruct[1].Length;
  if ( *(_DWORD *)&FirstStruct[1].Length > v3 )
    return 1;
  if ( *(_DWORD *)&FirstStruct[1].Length < v3 )
    return 0;
  v6 = *(_DWORD *)(&SecondStruct[1].MaximumLength + 1);
  v7 = *(_DWORD *)(&FirstStruct[1].MaximumLength + 1);
  if ( v7 != v6 || LODWORD(FirstStruct[1].Buffer) != LODWORD(SecondStruct[1].Buffer) )
  {
    Buffer = (int)SecondStruct[1].Buffer;
    if ( LODWORD(FirstStruct[1].Buffer) == Buffer )
      return v7 > v6;
    return SLODWORD(FirstStruct[1].Buffer) > Buffer;
  }
  if ( FirstStruct->Length != SecondStruct->Length )
    return FirstStruct->Length > SecondStruct->Length;
  v9 = RtlCompareUnicodeString(FirstStruct, SecondStruct, 1u);
  if ( v9 > 0 )
    return 1;
  if ( v9 < 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    WPP_SF_dDDZ(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      (unsigned int)WPP_521f112f0c4c3c3f435a4c29cad4d330_Traceguids,
      *(_DWORD *)&FirstStruct[1].Length,
      (char)FirstStruct[1].Buffer,
      *(_DWORD *)(&FirstStruct[1].MaximumLength + 1),
      (__int64)FirstStruct);
  return 2;
}

```

## disassembly

```asm
0x1400123f0  push    rbx
0x1400123f2  sub     rsp, 40h
0x1400123f6  mov     eax, [r8+10h]
0x1400123fa  mov     r9, r8
0x1400123fd  mov     rbx, rdx
0x140012400  cmp     [rdx+10h], eax
0x140012403  ja      loc_1400124AB
0x140012409  jb      short loc_140012430
0x14001240b  mov     edx, [r8+14h]
0x14001240f  mov     r8d, [rbx+14h]
0x140012413  cmp     r8d, edx
0x140012416  jnz     loc_1400124A0
0x14001241c  mov     eax, [r9+18h]
0x140012420  cmp     [rbx+18h], eax
0x140012423  jnz     short loc_1400124A0
0x140012425  movzx   eax, word ptr [r9]
0x140012429  cmp     [rbx], ax
0x14001242c  jz      short loc_140012434
0x14001242e  ja      short loc_1400124AB
0x140012430  xor     eax, eax
0x140012432  jmp     short loc_1400124B0
0x140012434  mov     r8b, 1; CaseInSensitive
0x140012437  mov     rdx, r9; String2
0x14001243a  mov     rcx, rbx; String1
0x14001243d  call    cs:__imp_RtlCompareUnicodeString
0x140012444  nop     dword ptr [rax+rax+00h]
0x140012449  mov     ecx, eax
0x14001244b  test    eax, eax
0x14001244d  jg      short loc_1400124AB
0x14001244f  js      short loc_140012430
0x140012451  mov     rcx, cs:WPP_GLOBAL_Control
0x140012458  lea     rax, WPP_GLOBAL_Control
0x14001245f  cmp     rcx, rax
0x140012462  jz      short loc_140012499
0x140012464  test    dword ptr [rcx+2Ch], 400000h
0x14001246b  jz      short loc_140012499
0x14001246d  mov     eax, [rbx+14h]
0x140012470  lea     r8, WPP_521f112f0c4c3c3f435a4c29cad4d330_Traceguids
0x140012477  mov     r9d, [rbx+10h]
0x14001247b  mov     edx, 11h
0x140012480  mov     rcx, [rcx+18h]
0x140012484  mov     [rsp+48h+var_18], rbx
0x140012489  mov     [rsp+48h+var_20], eax
0x14001248d  mov     eax, [rbx+18h]
0x140012490  mov     [rsp+48h+var_28], eax
0x140012494  call    WPP_SF_dDDZ
0x140012499  mov     eax, 2
0x14001249e  jmp     short loc_1400124B0
0x1400124a0  mov     eax, [r9+18h]
0x1400124a4  cmp     [rbx+18h], eax
0x1400124a7  jz      short loc_1400124B7
0x1400124a9  jle     short loc_140012430
0x1400124ab  mov     eax, 1
0x1400124b0  add     rsp, 40h
0x1400124b4  pop     rbx
0x1400124b5  retn
0x1400124b7  xor     eax, eax
0x1400124b9  cmp     r8d, edx
0x1400124bc  setnbe  al
0x1400124bf  jmp     short loc_1400124B0
```
