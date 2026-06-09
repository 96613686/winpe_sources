# RdbsspKernelInterfaceGetProcessPackageName

- ea: `0x1400753a0`
- end: `0x1400754d1`
- name: `RdbsspKernelInterfaceGetProcessPackageName`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400753a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400753e4`
- `ntoskrnl!ExAllocatePool2` at `0x1400753e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400754ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b877`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400754ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b877`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140075448`
- `ntoskrnl!RtlQueryPackageIdentity` at `0x140075448`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140075494`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14007b852`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140075494`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14007b852`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140075418`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140075418`

## pseudocode

```c
__int64 __fastcall RdbsspKernelInterfaceGetProcessPackageName(__int64 a1, struct _KPROCESS *a2, _QWORD *a3)
{
  PACCESS_TOKEN v5; // rdi
  __int64 Pool2; // rax
  _QWORD *v7; // rsi
  int v8; // ebx
  __int64 v10; // [rsp+40h] [rbp-28h]
  __int64 v11; // [rsp+88h] [rbp+20h] BYREF

  v5 = 0;
  v11 = 128;
  Pool2 = ExAllocatePool2(256, 144, 1229677650);
  v7 = (_QWORD *)Pool2;
  v10 = Pool2;
  if ( Pool2 )
  {
    *(_WORD *)(Pool2 + 2) = v11;
    *(_QWORD *)(Pool2 + 8) = Pool2 + 16;
    v5 = PsReferencePrimaryToken(a2);
    v8 = RtlQueryPackageIdentity(v5, v7[1], &v11, 0, 0, 0, 0, v5, v10);
    if ( v8 >= 0 )
    {
      *(_WORD *)v7 = v11;
      if ( (unsigned __int16)v11 >= 2u )
        *(_WORD *)v7 = v11 - 2;
      *a3 = v7;
    }
  }
  else
  {
    v8 = -1073741670;
  }
  if ( v5 )
    PsDereferencePrimaryToken(v5);
  if ( v8 < 0 && v7 )
    ExFreePoolWithTag(v7, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400753a0  mov     rax, rsp
0x1400753a3  mov     [rax+8], rbx
0x1400753a7  mov     [rax+10h], rsi
0x1400753ab  push    rdi
0x1400753ac  push    r14
0x1400753ae  push    r15
0x1400753b0  sub     rsp, 50h
0x1400753b4  mov     r14, r8
0x1400753b7  mov     rbx, rdx
0x1400753ba  xor     r15d, r15d
0x1400753bd  mov     [rax-28h], r15
0x1400753c1  mov     edi, r15d
0x1400753c4  mov     [rax-30h], r15
0x1400753c8  mov     [rax-38h], r15d
0x1400753cc  mov     qword ptr [rax+20h], 80h
0x1400753d4  mov     edx, 90h
0x1400753d9  mov     ecx, 100h
0x1400753de  mov     r8d, 494B6452h
0x1400753e4  call    cs:__imp_ExAllocatePool2
0x1400753eb  nop     dword ptr [rax+rax+00h]
0x1400753f0  mov     rsi, rax
0x1400753f3  mov     [rsp+68h+var_28], rax
0x1400753f8  test    rax, rax
0x1400753fb  jz      loc_140075483
0x140075401  movzx   eax, word ptr [rsp+68h+arg_18]
0x140075409  mov     [rsi+2], ax
0x14007540d  lea     rax, [rsi+10h]
0x140075411  mov     [rsi+8], rax
0x140075415  mov     rcx, rbx; Process
0x140075418  call    cs:__imp_PsReferencePrimaryToken
0x14007541f  nop     dword ptr [rax+rax+00h]
0x140075424  mov     rdi, rax
0x140075427  mov     [rsp+68h+var_30], rax
0x14007542c  mov     [rsp+68h+var_40], r15
0x140075431  mov     [rsp+68h+var_48], r15
0x140075436  xor     r9d, r9d
0x140075439  lea     r8, [rsp+68h+arg_18]
0x140075441  mov     rdx, [rsi+8]
0x140075445  mov     rcx, rax
0x140075448  call    cs:__imp_RtlQueryPackageIdentity
0x14007544f  nop     dword ptr [rax+rax+00h]
0x140075454  mov     ebx, eax
0x140075456  mov     [rsp+68h+var_38], eax
0x14007545a  test    eax, eax
0x14007545c  js      short loc_14007548C
0x14007545e  movzx   ecx, word ptr [rsp+68h+arg_18]
0x140075466  mov     [rsi], cx
0x140075469  mov     rax, [rsp+68h+arg_18]
0x140075471  cmp     ax, 2
0x140075475  jb      short loc_14007547E
0x140075477  sub     ax, 2
0x14007547b  mov     [rsi], ax
0x14007547e  mov     [r14], rsi
0x140075481  jmp     short loc_14007548C
0x140075483  mov     ebx, 0C000009Ah
0x140075488  mov     [rsp+68h+var_38], ebx
0x14007548c  test    rdi, rdi
0x14007548f  jz      short loc_1400754A0
0x140075491  mov     rcx, rdi; PrimaryToken
0x140075494  call    cs:__imp_PsDereferencePrimaryToken
0x14007549b  nop     dword ptr [rax+rax+00h]
0x1400754a0  test    ebx, ebx
0x1400754a2  jns     short loc_1400754BA
0x1400754a4  test    rsi, rsi
0x1400754a7  jz      short loc_1400754BA
0x1400754a9  xor     edx, edx; Tag
0x1400754ab  mov     rcx, rsi; P
0x1400754ae  call    cs:__imp_ExFreePoolWithTag
0x1400754b5  nop     dword ptr [rax+rax+00h]
0x1400754ba  mov     eax, ebx
0x1400754bc  mov     rbx, [rsp+68h+arg_0]
0x1400754c1  mov     rsi, [rsp+68h+arg_8]
0x1400754c6  add     rsp, 50h
0x1400754ca  pop     r15
0x1400754cc  pop     r14
0x1400754ce  pop     rdi
0x1400754cf  retn
0x14007b840  push    rbp
0x14007b842  sub     rsp, 30h
0x14007b846  mov     rbp, rdx
0x14007b849  mov     rcx, [rbp+38h]; PrimaryToken
0x14007b84d  test    rcx, rcx
0x14007b850  jz      short loc_14007B866
0x14007b852  call    cs:__imp_PsDereferencePrimaryToken
0x14007b859  nop     dword ptr [rax+rax+00h]
0x14007b85e  mov     qword ptr [rbp+38h], 0
0x14007b866  cmp     dword ptr [rbp+30h], 0
0x14007b86a  jge     short loc_14007B88B
0x14007b86c  mov     rcx, [rbp+40h]; P
0x14007b870  test    rcx, rcx
0x14007b873  jz      short loc_14007B88B
0x14007b875  xor     edx, edx; Tag
0x14007b877  call    cs:__imp_ExFreePoolWithTag
0x14007b87e  nop     dword ptr [rax+rax+00h]
0x14007b883  mov     qword ptr [rbp+40h], 0
0x14007b88b  add     rsp, 30h
0x14007b88f  pop     rbp
0x14007b890  retn
```
