# CMBPropertyWriter::IsPropertyFlag(int)

- ea: `0x180030280`
- end: `0x180030354`
- name: `?IsPropertyFlag@CMBPropertyWriter@@AEAAHH@Z`
- size: `212`
- prototype: `__int64 __fastcall(CMBPropertyWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002fb58`
- `0x18003059c`

## callees

- `0x180030280`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x1800302e0`
- `IisRTL!PuDbgPrintW` at `0x180030327`
- `IisRTL!PuDbgPrintW` at `0x1800302e0`
- `IisRTL!PuDbgPrintW` at `0x180030327`

## string_xrefs

- `0x1800302bc`: `inetsrv\iis\mb\xmlwriter\mbpropertywriter.cpp`
- `0x180030300`: `inetsrv\iis\mb\xmlwriter\mbpropertywriter.cpp`
- `0x1800302ae`: `CMBPropertyWriter::IsPropertyFlag`
- `0x1800302f3`: `CMBPropertyWriter::IsPropertyFlag`

## pseudocode

```c
_BOOL8 __fastcall CMBPropertyWriter::IsPropertyFlag(CMBPropertyWriter *this)
{
  _QWORD *v1; // rbx
  int *v2; // rdi
  int v4; // [rsp+28h] [rbp-20h]
  __int64 v5; // [rsp+28h] [rbp-20h]
  __int64 v6; // [rsp+30h] [rbp-18h]

  if ( !*((_QWORD *)this + 5) )
    return 0;
  v1 = (_QWORD *)((char *)this + 16);
  v2 = (int *)((char *)this + 36);
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v4 = *v2;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\mbpropertywriter.cpp",
      485,
      "CMBPropertyWriter::IsPropertyFlag",
      L"[IsPropertyFlag] PropertyID %d. Type: %d.\n",
      v4,
      *v1);
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v6) = *(_DWORD *)(*v1 + 8LL);
      LODWORD(v5) = *v2;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\xmlwriter\\mbpropertywriter.cpp",
        490,
        "CMBPropertyWriter::IsPropertyFlag",
        L"[IsPropertyFlag] PropertyID %d. SynID: %d.\n",
        v5,
        v6);
    }
  }
  return dword_180042908[*(unsigned int *)(*v1 + 8LL)] == 19;
}

```

## disassembly

```asm
0x180030280  mov     [rsp+arg_0], rbx
0x180030285  push    rdi
0x180030286  sub     rsp, 40h
0x18003028a  cmp     qword ptr [rcx+28h], 0
0x18003028f  jz      loc_180030347
0x180030295  mov     eax, cs:g_dwDebugFlags
0x18003029b  lea     rbx, [rcx+10h]
0x18003029f  lea     rdi, [rcx+24h]
0x1800302a3  test    al, 3
0x1800302a5  jz      loc_18003032D
0x1800302ab  mov     rax, [rbx]
0x1800302ae  lea     r9, aCmbpropertywri_1; "CMBPropertyWriter::IsPropertyFlag"
0x1800302b5  mov     rcx, cs:g_pDebug
0x1800302bc  lea     rdx, aInetsrvIisMbXm_0; "inetsrv\\iis\\mb\\xmlwriter\\mbproperty"...
0x1800302c3  mov     [rsp+48h+var_18], rax
0x1800302c8  mov     r8d, 1E5h
0x1800302ce  mov     eax, [rdi]
0x1800302d0  mov     dword ptr [rsp+48h+var_20], eax
0x1800302d4  lea     rax, aIspropertyflag; "[IsPropertyFlag] PropertyID %d. Type: %"...
0x1800302db  mov     [rsp+48h+var_28], rax
0x1800302e0  call    cs:__imp_PuDbgPrintW
0x1800302e6  mov     eax, cs:g_dwDebugFlags
0x1800302ec  test    al, 3
0x1800302ee  jz      short loc_18003032D
0x1800302f0  mov     rax, [rbx]
0x1800302f3  lea     r9, aCmbpropertywri_1; "CMBPropertyWriter::IsPropertyFlag"
0x1800302fa  mov     r8d, 1EAh
0x180030300  lea     rdx, aInetsrvIisMbXm_0; "inetsrv\\iis\\mb\\xmlwriter\\mbproperty"...
0x180030307  mov     ecx, [rax+8]
0x18003030a  mov     eax, [rdi]
0x18003030c  mov     dword ptr [rsp+48h+var_18], ecx
0x180030310  mov     rcx, cs:g_pDebug
0x180030317  mov     dword ptr [rsp+48h+var_20], eax
0x18003031b  lea     rax, aIspropertyflag_0; "[IsPropertyFlag] PropertyID %d. SynID: "...
0x180030322  mov     [rsp+48h+var_28], rax
0x180030327  call    cs:__imp_PuDbgPrintW
0x18003032d  mov     rax, [rbx]
0x180030330  mov     ecx, [rax+8]
0x180030333  lea     rax, dword_180042908
0x18003033a  cmp     dword ptr [rax+rcx*4], 13h
0x18003033e  jnz     short loc_180030347
0x180030340  mov     eax, 1
0x180030345  jmp     short loc_180030349
0x180030347  xor     eax, eax
0x180030349  mov     rbx, [rsp+48h+arg_0]
0x18003034e  add     rsp, 40h
0x180030352  pop     rdi
0x180030353  retn
```
