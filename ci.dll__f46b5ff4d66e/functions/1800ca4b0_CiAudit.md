# CiAudit

- ea: `0x1800ca4b0`
- end: `0x1800ca56d`
- name: `CiAudit`
- size: `189`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180063d3c`
- `0x180064160`
- `0x180064234`
- `0x1800b3c18`
- `0x1800e4cb8`

## callees

- `0x1800ca4b0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800ca4e8`
- `ntoskrnl!ExAllocatePool2` at `0x1800ca4e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800ca547`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800ca547`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1800ca534`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1800ca534`

## pseudocode

```c
__int64 __fastcall CiAudit(unsigned __int16 *a1, int a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rdi
  struct _SE_ADT_PARAMETER_ARRAY *v6; // r9
  int v7; // eax
  unsigned int v8; // ebx
  struct _UNICODE_STRING SourceName; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&SourceName.Length = 1966108;
  SourceName.Buffer = L"Code Integrity";
  Pool2 = ExAllocatePool2(256, 1048, 1668499779);
  v5 = Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  *(_DWORD *)(Pool2 + 4) = a2;
  *(_DWORD *)Pool2 = 1;
  v6 = (struct _SE_ADT_PARAMETER_ARRAY *)Pool2;
  *(_DWORD *)(Pool2 + 8) = 1;
  *(_DWORD *)(Pool2 + 24) = 1;
  *(_WORD *)(Pool2 + 18) = 16;
  v7 = *a1 + 16;
  *(_QWORD *)(v5 + 48) = a1;
  *(_DWORD *)(v5 + 28) = v7;
  v8 = SeReportSecurityEventWithSubCategory(0, &SourceName, 0, v6, 0x66u);
  ExFreePoolWithTag((PVOID)v5, 0);
  return v8;
}

```

## disassembly

```asm
0x1800ca4b0  mov     r11, rsp
0x1800ca4b3  mov     [r11+8], rbx
0x1800ca4b7  mov     [r11+10h], rsi
0x1800ca4bb  push    rdi
0x1800ca4bc  sub     rsp, 40h
0x1800ca4c0  mov     esi, edx
0x1800ca4c2  mov     qword ptr [r11-18h], 1E001Ch
0x1800ca4ca  mov     rbx, rcx
0x1800ca4cd  lea     rax, aCodeIntegrity; "Code Integrity"
0x1800ca4d4  mov     edx, 418h
0x1800ca4d9  mov     [r11-10h], rax
0x1800ca4dd  mov     ecx, 100h
0x1800ca4e2  mov     r8d, 63734943h
0x1800ca4e8  call    cs:__imp_ExAllocatePool2
0x1800ca4ef  nop     dword ptr [rax+rax+00h]
0x1800ca4f4  mov     rdi, rax
0x1800ca4f7  test    rax, rax
0x1800ca4fa  jz      short loc_1800CA566
0x1800ca4fc  mov     [rax+4], esi
0x1800ca4ff  lea     rdx, [rsp+48h+SourceName]; SourceName
0x1800ca504  mov     eax, 1
0x1800ca509  mov     [rsp+48h+AuditSubcategoryId], 66h ; 'f'; AuditSubcategoryId
0x1800ca511  mov     [rdi], eax
0x1800ca513  mov     r9, rdi; AuditParameters
0x1800ca516  mov     [rdi+8], eax
0x1800ca519  xor     r8d, r8d; UserSid
0x1800ca51c  mov     [rdi+18h], eax
0x1800ca51f  lea     ecx, [rax+0Fh]
0x1800ca522  mov     [rdi+12h], cx
0x1800ca526  movzx   eax, word ptr [rbx]
0x1800ca529  add     eax, ecx
0x1800ca52b  mov     [rdi+30h], rbx
0x1800ca52f  xor     ecx, ecx; Flags
0x1800ca531  mov     [rdi+1Ch], eax
0x1800ca534  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x1800ca53b  nop     dword ptr [rax+rax+00h]
0x1800ca540  xor     edx, edx; Tag
0x1800ca542  mov     rcx, rdi; P
0x1800ca545  mov     ebx, eax
0x1800ca547  call    cs:__imp_ExFreePoolWithTag
0x1800ca54e  nop     dword ptr [rax+rax+00h]
0x1800ca553  mov     eax, ebx
0x1800ca555  mov     rbx, [rsp+48h+arg_0]
0x1800ca55a  mov     rsi, [rsp+48h+arg_8]
0x1800ca55f  add     rsp, 40h
0x1800ca563  pop     rdi
0x1800ca564  retn
0x1800ca566  mov     eax, 0C0000017h
0x1800ca56b  jmp     short loc_1800CA555
```
