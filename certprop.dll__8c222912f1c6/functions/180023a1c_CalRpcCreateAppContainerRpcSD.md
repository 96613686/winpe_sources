# CalRpcCreateAppContainerRpcSD

- ea: `0x180023a1c`
- end: `0x180023aa1`
- name: `CalRpcCreateAppContainerRpcSD`
- size: `133`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023aa8`

## callees

- `0x180018bb4`
- `0x1800238a4`
- `0x180023a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a44`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023a3a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023a3a`

## pseudocode

```c
__int64 __fastcall CalRpcCreateAppContainerRpcSD(PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  DWORD LastError; // ebx
  __int64 v2; // rcx

  *SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GR;;;AN)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;S-1-15-3-9)",
         1u,
         SecurityDescriptor,
         0) )
  {
    return 0;
  }
  LastError = GetLastError();
  WppTraceIndent(v2, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids,
      (_DWORD)WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180023a1c  push    rbx
0x180023a1e  sub     rsp, 30h
0x180023a22  xor     r9d, r9d; SecurityDescriptorSize
0x180023a25  mov     qword ptr [rcx], 0
0x180023a2c  mov     r8, rcx; SecurityDescriptor
0x180023a2f  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180023a36  lea     edx, [r9+1]; StringSDRevision
0x180023a3a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023a40  test    eax, eax
0x180023a42  jnz     short loc_180023A99
0x180023a44  call    cs:__imp_GetLastError
0x180023a4a  mov     edx, 2
0x180023a4f  mov     ebx, eax
0x180023a51  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180023a56  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a5d  lea     rax, WPP_GLOBAL_Control
0x180023a64  cmp     rcx, rax
0x180023a67  jz      short loc_180023A95
0x180023a69  test    byte ptr [rcx+1Ch], 1
0x180023a6d  jz      short loc_180023A95
0x180023a6f  cmp     byte ptr [rcx+19h], 2
0x180023a73  jb      short loc_180023A95
0x180023a75  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180023a7c  lea     r8, WPP_6bc86d6463543fa2cd93c11fe697381a_Traceguids
0x180023a83  mov     rcx, [rcx+10h]
0x180023a87  mov     edx, 0Ch
0x180023a8c  mov     [rsp+38h+var_18], ebx
0x180023a90  call    WPP_SF_sD
0x180023a95  mov     eax, ebx
0x180023a97  jmp     short loc_180023A9B
0x180023a99  xor     eax, eax
0x180023a9b  add     rsp, 30h
0x180023a9f  pop     rbx
0x180023aa0  retn
```
