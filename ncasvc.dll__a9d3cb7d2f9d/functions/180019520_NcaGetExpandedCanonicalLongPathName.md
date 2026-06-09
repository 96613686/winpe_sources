# NcaGetExpandedCanonicalLongPathName

- ea: `0x180019520`
- end: `0x180019631`
- name: `NcaGetExpandedCanonicalLongPathName`
- size: `273`
- prototype: `__int64 __fastcall(wchar_t *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009ce0`

## callees

- `0x1800033bc`
- `0x180003770`
- `0x180004f04`
- `0x180019178`
- `0x1800193f8`
- `0x180019520`
- `0x180019638`

## import_xrefs

- `msvcrt!wcschr` at `0x180019592`
- `msvcrt!wcschr` at `0x180019592`

## string_xrefs

- `0x1800195bf`: `NcaGetExpandedCanonicalLongPathName`
- `0x1800195ed`: `NcaGetExpandedCanonicalLongPathName`
- `0x180019611`: `NcaGetExpandedCanonicalLongPathName`

## pseudocode

```c
__int64 __fastcall NcaGetExpandedCanonicalLongPathName(wchar_t *a1, _QWORD *a2, _DWORD *a3)
{
  PVOID v5; // rcx
  void *v6; // rdi
  int LongPathName; // eax
  int v8; // ebx
  int CanonicalPathName; // eax
  wchar_t *Str; // [rsp+40h] [rbp+8h] BYREF
  void *Src; // [rsp+48h] [rbp+10h] BYREF

  Str = a1;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
  v6 = 0;
  Str = 0;
  Src = 0;
  *a2 = 0;
  LongPathName = NcaExpandEnvironmentStrings((SIZE_T)v5, &Str);
  v8 = LongPathName;
  if ( LongPathName < 0 )
    goto LABEL_10;
  if ( wcschr(Str, 0x25u) )
  {
    *a3 = 0;
    goto LABEL_11;
  }
  CanonicalPathName = NcaGetCanonicalPathName(Str, &Src);
  v8 = CanonicalPathName;
  if ( CanonicalPathName < 0 )
  {
    NcaReportReturnError("NcaGetExpandedCanonicalLongPathName", (unsigned int)CanonicalPathName);
    v6 = Src;
    goto LABEL_11;
  }
  v6 = Src;
  LongPathName = NcaGetLongPathName(Src);
  v8 = LongPathName;
  if ( LongPathName < 0 )
LABEL_10:
    NcaReportReturnError("NcaGetExpandedCanonicalLongPathName", (unsigned int)LongPathName);
LABEL_11:
  NcaFree(v6);
  NcaFree(Str);
  if ( v8 < 0 )
    return (unsigned int)NcaReportReturnError("NcaGetExpandedCanonicalLongPathName", (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019520  mov     [rsp+arg_10], rbx
0x180019525  mov     [rsp+Str], rcx
0x18001952a  push    rdi
0x18001952b  push    r14
0x18001952d  push    r15
0x18001952f  sub     rsp, 20h
0x180019533  mov     r14, r8
0x180019536  mov     r15, rdx
0x180019539  mov     rcx, cs:WPP_GLOBAL_Control
0x180019540  lea     rax, WPP_GLOBAL_Control
0x180019547  cmp     rcx, rax
0x18001954a  jz      short loc_180019567
0x18001954c  test    byte ptr [rcx+1Ch], 8
0x180019550  jz      short loc_180019567
0x180019552  mov     rcx, [rcx+10h]
0x180019556  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x18001955d  mov     edx, 1Eh
0x180019562  call    WPP_SF_
0x180019567  xor     edi, edi
0x180019569  mov     [rsp+38h+Str], 0
0x180019572  lea     rdx, [rsp+38h+Str]
0x180019577  mov     [rsp+38h+Src], rdi
0x18001957c  mov     [r15], rdi
0x18001957f  call    NcaExpandEnvironmentStrings
0x180019584  mov     ebx, eax
0x180019586  test    eax, eax
0x180019588  js      short loc_1800195EB
0x18001958a  mov     rcx, [rsp+38h+Str]; Str
0x18001958f  lea     edx, [rdi+25h]; Ch
0x180019592  call    cs:__imp_wcschr
0x180019599  nop     dword ptr [rax+rax+00h]
0x18001959e  test    rax, rax
0x1800195a1  jz      short loc_1800195A8
0x1800195a3  mov     [r14], edi
0x1800195a6  jmp     short loc_1800195F9
0x1800195a8  mov     rcx, [rsp+38h+Str]; pszPath
0x1800195ad  lea     rdx, [rsp+38h+Src]
0x1800195b2  call    NcaGetCanonicalPathName
0x1800195b7  mov     ebx, eax
0x1800195b9  test    eax, eax
0x1800195bb  jns     short loc_1800195D2
0x1800195bd  mov     edx, eax
0x1800195bf  lea     rcx, aNcagetexpanded; "NcaGetExpandedCanonicalLongPathName"
0x1800195c6  call    NcaReportReturnError
0x1800195cb  mov     rdi, [rsp+38h+Src]
0x1800195d0  jmp     short loc_1800195F9
0x1800195d2  mov     rdi, [rsp+38h+Src]
0x1800195d7  mov     r8, r14
0x1800195da  mov     rcx, rdi; Src
0x1800195dd  mov     rdx, r15
0x1800195e0  call    NcaGetLongPathName
0x1800195e5  mov     ebx, eax
0x1800195e7  test    eax, eax
0x1800195e9  jns     short loc_1800195F9
0x1800195eb  mov     edx, eax
0x1800195ed  lea     rcx, aNcagetexpanded; "NcaGetExpandedCanonicalLongPathName"
0x1800195f4  call    NcaReportReturnError
0x1800195f9  mov     rcx, rdi; lpMem
0x1800195fc  call    NcaFree
0x180019601  mov     rcx, [rsp+38h+Str]; lpMem
0x180019606  call    NcaFree
0x18001960b  test    ebx, ebx
0x18001960d  jns     short loc_18001961F
0x18001960f  mov     edx, ebx
0x180019611  lea     rcx, aNcagetexpanded; "NcaGetExpandedCanonicalLongPathName"
0x180019618  call    NcaReportReturnError
0x18001961d  mov     ebx, eax
0x18001961f  mov     eax, ebx
0x180019621  mov     rbx, [rsp+38h+arg_10]
0x180019626  add     rsp, 20h
0x18001962a  pop     r15
0x18001962c  pop     r14
0x18001962e  pop     rdi
0x18001962f  retn
```
