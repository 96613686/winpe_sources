# GetKeysetDirSD

- ea: `0x1800066a4`
- end: `0x18000673e`
- name: `GetKeysetDirSD`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006744`

## callees

- `0x1800066a4`
- `0x18000b250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800066c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800066c7`

## string_xrefs

- `0x180006718`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall GetKeysetDirSD(const WCHAR *a1, _QWORD *a2)
{
  DWORD LastError; // ebx
  int v5; // edx
  int v6; // r8d
  ULONG v7; // [rsp+60h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR v8; // [rsp+68h] [rbp+20h] BYREF

  LastError = 0;
  v8 = 0;
  v7 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1, 1u, &v8, &v7) )
  {
    *a2 = v8;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        v6,
        (unsigned int)"Status",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
        59);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800066a4  mov     rax, rsp
0x1800066a7  mov     [rax+8], rbx
0x1800066ab  push    rdi
0x1800066ac  sub     rsp, 40h
0x1800066b0  xor     ebx, ebx
0x1800066b2  lea     r9, [rax+18h]; SecurityDescriptorSize
0x1800066b6  mov     rdi, rdx
0x1800066b9  mov     [rax+20h], rbx
0x1800066bd  lea     r8, [rax+20h]; SecurityDescriptor
0x1800066c1  mov     [rax+18h], ebx
0x1800066c4  lea     edx, [rbx+1]; StringSDRevision
0x1800066c7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800066ce  nop     dword ptr [rax+rax+00h]
0x1800066d3  test    eax, eax
0x1800066d5  jz      short loc_1800066ED
0x1800066d7  mov     rax, [rsp+48h+arg_18]
0x1800066dc  mov     [rdi], rax
0x1800066df  mov     eax, ebx
0x1800066e1  mov     rbx, [rsp+48h+arg_0]
0x1800066e6  add     rsp, 40h
0x1800066ea  pop     rdi
0x1800066eb  retn
0x1800066ed  call    cs:__imp_GetLastError
0x1800066f4  nop     dword ptr [rax+rax+00h]
0x1800066f9  mov     ebx, eax
0x1800066fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006702  lea     rax, WPP_GLOBAL_Control
0x180006709  cmp     rcx, rax
0x18000670c  jz      short loc_1800066DF
0x18000670e  test    byte ptr [rcx+1Ch], 1
0x180006712  jz      short loc_1800066DF
0x180006714  mov     rcx, [rcx+10h]
0x180006718  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000671f  mov     [rsp+48h+var_18], 0F3Bh
0x180006727  lea     r9, aStatus; "Status"
0x18000672e  mov     [rsp+48h+var_20], rax
0x180006733  mov     [rsp+48h+var_28], ebx
0x180006737  call    WPP_SF_sDsd
0x18000673c  jmp     short loc_1800066DF
```
