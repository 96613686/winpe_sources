# CiAudit

- ea: `0x1800cb940`
- end: `0x1800cb9fd`
- name: `CiAudit`
- size: `189`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800647dc`
- `0x180064be8`
- `0x180064cbc`
- `0x1800b4f38`
- `0x1800e5228`

## callees

- `0x1800cb940`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800cb978`
- `ntoskrnl!ExAllocatePool2` at `0x1800cb978`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800cb9d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800cb9d7`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1800cb9c4`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1800cb9c4`

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
0x1800cb940  mov     r11, rsp
0x1800cb943  mov     [r11+8], rbx
0x1800cb947  mov     [r11+10h], rsi
0x1800cb94b  push    rdi
0x1800cb94c  sub     rsp, 40h
0x1800cb950  mov     esi, edx
0x1800cb952  mov     qword ptr [r11-18h], 1E001Ch
0x1800cb95a  mov     rbx, rcx
0x1800cb95d  lea     rax, aCodeIntegrity; "Code Integrity"
0x1800cb964  mov     edx, 418h
0x1800cb969  mov     [r11-10h], rax
0x1800cb96d  mov     ecx, 100h
0x1800cb972  mov     r8d, 63734943h
0x1800cb978  call    cs:__imp_ExAllocatePool2
0x1800cb97f  nop     dword ptr [rax+rax+00h]
0x1800cb984  mov     rdi, rax
0x1800cb987  test    rax, rax
0x1800cb98a  jz      short loc_1800CB9F6
0x1800cb98c  mov     [rax+4], esi
0x1800cb98f  lea     rdx, [rsp+48h+SourceName]; SourceName
0x1800cb994  mov     eax, 1
0x1800cb999  mov     [rsp+48h+AuditSubcategoryId], 66h ; 'f'; AuditSubcategoryId
0x1800cb9a1  mov     [rdi], eax
0x1800cb9a3  mov     r9, rdi; AuditParameters
0x1800cb9a6  mov     [rdi+8], eax
0x1800cb9a9  xor     r8d, r8d; UserSid
0x1800cb9ac  mov     [rdi+18h], eax
0x1800cb9af  lea     ecx, [rax+0Fh]
0x1800cb9b2  mov     [rdi+12h], cx
0x1800cb9b6  movzx   eax, word ptr [rbx]
0x1800cb9b9  add     eax, ecx
0x1800cb9bb  mov     [rdi+30h], rbx
0x1800cb9bf  xor     ecx, ecx; Flags
0x1800cb9c1  mov     [rdi+1Ch], eax
0x1800cb9c4  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x1800cb9cb  nop     dword ptr [rax+rax+00h]
0x1800cb9d0  xor     edx, edx; Tag
0x1800cb9d2  mov     rcx, rdi; P
0x1800cb9d5  mov     ebx, eax
0x1800cb9d7  call    cs:__imp_ExFreePoolWithTag
0x1800cb9de  nop     dword ptr [rax+rax+00h]
0x1800cb9e3  mov     eax, ebx
0x1800cb9e5  mov     rbx, [rsp+48h+arg_0]
0x1800cb9ea  mov     rsi, [rsp+48h+arg_8]
0x1800cb9ef  add     rsp, 40h
0x1800cb9f3  pop     rdi
0x1800cb9f4  retn
0x1800cb9f6  mov     eax, 0C0000017h
0x1800cb9fb  jmp     short loc_1800CB9E5
```
