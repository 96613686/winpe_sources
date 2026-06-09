# HidpFdoCreateCollectionPdos

- ea: `0x18003f634`
- end: `0x18003f823`
- name: `HidpFdoCreateCollectionPdos`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019694`

## callees

- `0x18000e438`
- `0x180019014`
- `0x18001c8a0`
- `0x18002432c`
- `0x18003f634`
- `0x18003f8bc`
- `0x18003f980`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18003f68f`
- `ntoskrnl!MmBadPointer` at `0x18003f6f9`
- `ntoskrnl!MmBadPointer` at `0x18003f73b`
- `ntoskrnl!MmBadPointer` at `0x18003f7a0`
- `ntoskrnl!MmBadPointer` at `0x18003f7ba`
- `ntoskrnl!MmBadPointer` at `0x18003f7d7`
- `ntoskrnl!MmBadPointer` at `0x18003f7f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003f7ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003f7e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003f7ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003f7e5`
- `ntoskrnl!ExAllocatePool2` at `0x18003f6cb`
- `ntoskrnl!ExAllocatePool2` at `0x18003f712`
- `ntoskrnl!ExAllocatePool2` at `0x18003f6cb`
- `ntoskrnl!ExAllocatePool2` at `0x18003f712`

## string_xrefs

- `0x18003f776`: `Trying to create PDOs without a valid collection array`

## pseudocode

```c
__int64 __fastcall HidpFdoCreateCollectionPdos(__int64 a1)
{
  PVOID v2; // rdx
  __int64 v3; // r8
  __int64 v4; // r15
  char v5; // r14
  int OneCollectionPdo; // edi
  __int64 v7; // rsi
  PVOID v8; // rcx
  PVOID v9; // rax
  __int64 Pool2; // rax
  PVOID v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // ebp
  PVOID v14; // rcx
  PVOID v15; // rcx

  v4 = RefDriverExt(**(_QWORD **)(a1 + 8));
  if ( !v4 )
  {
    v5 = 0;
LABEL_3:
    OneCollectionPdo = -1073741438;
    goto LABEL_21;
  }
  v7 = *(unsigned int *)(a1 + 168);
  v5 = 1;
  if ( !(_DWORD)v7 )
  {
    TraceLoggingNoTopLevelCollection(a1);
    goto LABEL_3;
  }
  v8 = *(PVOID *)(a1 + 152);
  if ( !v8 || v8 == MmBadPointer )
  {
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      v8,
      (unsigned int)v7,
      *(unsigned __int16 *)(a1 + 110) | (*(unsigned __int16 *)(a1 + 108) << 16),
      "Trying to create PDOs without a valid collection array");
    OneCollectionPdo = -1073741436;
  }
  else
  {
    v9 = *(PVOID *)(a1 + 272);
    if ( (v9 && v9 != MmBadPointer
       || (Pool2 = ExAllocatePool2(64, 8 * v7 + 16, 1130654024), (*(_QWORD *)(a1 + 272) = Pool2) != 0))
      && ((v11 = *(PVOID *)(a1 + 288)) != 0 && v11 != MmBadPointer
       || (v12 = ExAllocatePool2(64, 8 * v7, 1130654024), (*(_QWORD *)(a1 + 288) = v12) != 0)) )
    {
      v13 = 0;
      **(_DWORD **)(a1 + 272) = v7;
      do
      {
        OneCollectionPdo = CreateOneCollectionPdo(v4, a1, v13, MmBadPointer);
        if ( OneCollectionPdo < 0 )
          break;
        ++v13;
      }
      while ( v13 < (unsigned int)v7 );
      HidpWppDumpFdo(a1);
      if ( OneCollectionPdo >= 0 )
      {
LABEL_28:
        DerefDriverExt(**(_QWORD **)(a1 + 8), v2, v3);
        return (unsigned int)OneCollectionPdo;
      }
    }
    else
    {
      OneCollectionPdo = -1073741801;
    }
  }
LABEL_21:
  v14 = *(PVOID *)(a1 + 288);
  if ( v14 && v14 != MmBadPointer )
  {
    ExFreePoolWithTag(v14, 0);
    *(_QWORD *)(a1 + 288) = MmBadPointer;
  }
  v15 = *(PVOID *)(a1 + 272);
  if ( v15 && v15 != MmBadPointer )
  {
    ExFreePoolWithTag(v15, 0);
    v2 = MmBadPointer;
    *(_QWORD *)(a1 + 272) = MmBadPointer;
  }
  if ( v5 )
    goto LABEL_28;
  return (unsigned int)OneCollectionPdo;
}

```

## disassembly

```asm
0x18003f634  push    rbx
0x18003f636  push    rbp
0x18003f637  push    rsi
0x18003f638  push    rdi
0x18003f639  push    r14
0x18003f63b  push    r15
0x18003f63d  sub     rsp, 28h
0x18003f641  mov     rbx, rcx
0x18003f644  mov     rcx, [rcx+8]
0x18003f648  mov     rcx, [rcx]
0x18003f64b  call    RefDriverExt
0x18003f650  mov     r15, rax
0x18003f653  test    rax, rax
0x18003f656  jnz     short loc_18003F665
0x18003f658  xor     r14b, r14b
0x18003f65b  mov     edi, 0C0000182h
0x18003f660  jmp     loc_18003F794
0x18003f665  mov     esi, [rbx+0A8h]
0x18003f66b  mov     r14d, 1
0x18003f671  test    esi, esi
0x18003f673  jnz     short loc_18003F67F
0x18003f675  mov     rcx, rbx
0x18003f678  call    TraceLoggingNoTopLevelCollection
0x18003f67d  jmp     short loc_18003F65B
0x18003f67f  mov     rcx, [rbx+98h]
0x18003f686  test    rcx, rcx
0x18003f689  jz      loc_18003F771
0x18003f68f  mov     rax, cs:MmBadPointer
0x18003f696  mov     rdx, [rax]
0x18003f699  cmp     rcx, rdx
0x18003f69c  jz      loc_18003F771
0x18003f6a2  mov     rax, [rbx+110h]
0x18003f6a9  mov     edi, 43646948h
0x18003f6ae  mov     ebp, 40h ; '@'
0x18003f6b3  test    rax, rax
0x18003f6b6  jz      short loc_18003F6BD
0x18003f6b8  cmp     rax, rdx
0x18003f6bb  jnz     short loc_18003F6ED
0x18003f6bd  lea     rdx, ds:10h[rsi*8]
0x18003f6c5  mov     r8d, edi
0x18003f6c8  mov     rcx, rbp
0x18003f6cb  call    cs:__imp_ExAllocatePool2
0x18003f6d2  nop     dword ptr [rax+rax+00h]
0x18003f6d7  mov     [rbx+110h], rax
0x18003f6de  test    rax, rax
0x18003f6e1  jnz     short loc_18003F6ED
0x18003f6e3  mov     edi, 0C0000017h
0x18003f6e8  jmp     loc_18003F794
0x18003f6ed  mov     rdx, [rbx+120h]
0x18003f6f4  test    rdx, rdx
0x18003f6f7  jz      short loc_18003F705
0x18003f6f9  mov     rax, cs:MmBadPointer
0x18003f700  cmp     rdx, [rax]
0x18003f703  jnz     short loc_18003F72A
0x18003f705  mov     rdx, rsi
0x18003f708  mov     r8d, edi
0x18003f70b  shl     rdx, 3
0x18003f70f  mov     rcx, rbp
0x18003f712  call    cs:__imp_ExAllocatePool2
0x18003f719  nop     dword ptr [rax+rax+00h]
0x18003f71e  mov     [rbx+120h], rax
0x18003f725  test    rax, rax
0x18003f728  jz      short loc_18003F6E3
0x18003f72a  mov     rax, [rbx+110h]
0x18003f731  xor     edi, edi
0x18003f733  xor     ebp, ebp
0x18003f735  mov     [rax], esi
0x18003f737  test    esi, esi
0x18003f739  jz      short loc_18003F760
0x18003f73b  mov     r9, cs:MmBadPointer
0x18003f742  mov     r8d, ebp
0x18003f745  mov     rdx, rbx
0x18003f748  mov     rcx, r15
0x18003f74b  mov     r9, [r9]
0x18003f74e  call    CreateOneCollectionPdo
0x18003f753  mov     edi, eax
0x18003f755  test    eax, eax
0x18003f757  js      short loc_18003F760
0x18003f759  add     ebp, r14d
0x18003f75c  cmp     ebp, esi
0x18003f75e  jb      short loc_18003F73B
0x18003f760  mov     rcx, rbx
0x18003f763  call    HidpWppDumpFdo
0x18003f768  test    edi, edi
0x18003f76a  js      short loc_18003F794
0x18003f76c  jmp     loc_18003F807
0x18003f771  movzx   r8d, word ptr [rbx+6Ch]; __annotation("Debug", "TelemetryAssert", "FALSE", "Trying to create PDOs without a valid collection array")
0x18003f776  lea     r9, aTryingToCreate; "Trying to create PDOs without a valid c"...
0x18003f77d  movzx   eax, word ptr [rbx+6Eh]
0x18003f781  mov     edx, esi
0x18003f783  shl     r8d, 10h
0x18003f787  or      r8d, eax
0x18003f78a  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x18003f78f  mov     edi, 0C0000184h
0x18003f794  mov     rcx, [rbx+120h]; P
0x18003f79b  test    rcx, rcx
0x18003f79e  jz      short loc_18003F7CB
0x18003f7a0  mov     rax, cs:MmBadPointer
0x18003f7a7  cmp     rcx, [rax]
0x18003f7aa  jz      short loc_18003F7CB
0x18003f7ac  xor     edx, edx; Tag
0x18003f7ae  call    cs:__imp_ExFreePoolWithTag
0x18003f7b5  nop     dword ptr [rax+rax+00h]
0x18003f7ba  mov     rax, cs:MmBadPointer
0x18003f7c1  mov     rcx, [rax]
0x18003f7c4  mov     [rbx+120h], rcx
0x18003f7cb  mov     rcx, [rbx+110h]; P
0x18003f7d2  test    rcx, rcx
0x18003f7d5  jz      short loc_18003F802
0x18003f7d7  mov     rax, cs:MmBadPointer
0x18003f7de  cmp     rcx, [rax]
0x18003f7e1  jz      short loc_18003F802
0x18003f7e3  xor     edx, edx; Tag
0x18003f7e5  call    cs:__imp_ExFreePoolWithTag
0x18003f7ec  nop     dword ptr [rax+rax+00h]
0x18003f7f1  mov     rcx, cs:MmBadPointer
0x18003f7f8  mov     rdx, [rcx]
0x18003f7fb  mov     [rbx+110h], rdx
0x18003f802  test    r14b, r14b
0x18003f805  jz      short loc_18003F813
0x18003f807  mov     rcx, [rbx+8]
0x18003f80b  mov     rcx, [rcx]
0x18003f80e  call    DerefDriverExt
0x18003f813  mov     eax, edi
0x18003f815  add     rsp, 28h
0x18003f819  pop     r15
0x18003f81b  pop     r14
0x18003f81d  pop     rdi
0x18003f81e  pop     rsi
0x18003f81f  pop     rbp
0x18003f820  pop     rbx
0x18003f821  retn
```
