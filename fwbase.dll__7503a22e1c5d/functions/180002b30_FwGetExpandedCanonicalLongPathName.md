# FwGetExpandedCanonicalLongPathName

- ea: `0x180002b30`
- end: `0x180002c0a`
- name: `FwGetExpandedCanonicalLongPathName`
- size: `218`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180007180`
- `0x180011790`
- `0x1800138f0`

## callees

- `0x1800024a0`
- `0x180002b30`
- `0x1800030b0`
- `0x1800043a0`
- `0x1800047e0`
- `0x180004840`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002b6e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002b6e`

## string_xrefs

- `0x180002bd0`: `FwGetExpandedCanonicalLongPathName`
- `0x180002be5`: `FwGetExpandedCanonicalLongPathName`
- `0x180002bfa`: `FwGetExpandedCanonicalLongPathName`

## pseudocode

```c
__int64 __fastcall FwGetExpandedCanonicalLongPathName(const WCHAR *a1, _QWORD *a2, _DWORD *a3)
{
  void *v3; // rdi
  int LongPathName; // eax
  int v7; // ebx
  int CanonicalPathName; // eax
  void *Src; // [rsp+58h] [rbp+20h] BYREF

  v3 = 0;
  *a2 = 0;
  Src = 0;
  LongPathName = FwExpandEnvironmentStrings(a1);
  v7 = LongPathName;
  if ( LongPathName < 0 )
  {
LABEL_8:
    FwReportReturnError("FwGetExpandedCanonicalLongPathName", (unsigned int)LongPathName);
    goto LABEL_5;
  }
  if ( wcschr(0, 0x25u) )
  {
    *a3 = 0;
  }
  else
  {
    CanonicalPathName = FwGetCanonicalPathName(0, &Src);
    v7 = CanonicalPathName;
    if ( CanonicalPathName >= 0 )
    {
      v3 = Src;
      LongPathName = FwGetLongPathName(Src, a2, a3);
      v7 = LongPathName;
      if ( LongPathName >= 0 )
        goto LABEL_5;
      goto LABEL_8;
    }
    FwReportReturnError("FwGetExpandedCanonicalLongPathName", (unsigned int)CanonicalPathName);
    v3 = Src;
  }
LABEL_5:
  FwFree(v3);
  FwFree(0);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwGetExpandedCanonicalLongPathName", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002b30  mov     rax, rsp
0x180002b33  mov     [rax+8], rbx
0x180002b37  push    rdi
0x180002b38  push    r14
0x180002b3a  push    r15
0x180002b3c  sub     rsp, 20h
0x180002b40  xor     edi, edi
0x180002b42  mov     qword ptr [rax+10h], 0
0x180002b4a  mov     [rdx], rdi
0x180002b4d  mov     r15, rdx
0x180002b50  lea     rdx, [rax+10h]
0x180002b54  mov     [rax+20h], rdi
0x180002b58  mov     r14, r8
0x180002b5b  call    FwExpandEnvironmentStrings
0x180002b60  mov     ebx, eax
0x180002b62  test    eax, eax
0x180002b64  js      short loc_180002BCE
0x180002b66  mov     rcx, [rsp+38h+Str]; Str
0x180002b6b  lea     edx, [rdi+25h]; Ch
0x180002b6e  call    cs:__imp_wcschr
0x180002b74  test    rax, rax
0x180002b77  jnz     short loc_180002BDE
0x180002b79  mov     rcx, [rsp+38h+Str]; pszPath
0x180002b7e  lea     rdx, [rsp+38h+Src]
0x180002b83  call    FwGetCanonicalPathName
0x180002b88  mov     ebx, eax
0x180002b8a  test    eax, eax
0x180002b8c  js      short loc_180002BE3
0x180002b8e  mov     rdi, [rsp+38h+Src]
0x180002b93  mov     r8, r14
0x180002b96  mov     rcx, rdi; Src
0x180002b99  mov     rdx, r15
0x180002b9c  call    FwGetLongPathName
0x180002ba1  mov     ebx, eax
0x180002ba3  test    eax, eax
0x180002ba5  js      short loc_180002BCE
0x180002ba7  mov     rcx, rdi
0x180002baa  call    FwFree
0x180002baf  mov     rcx, [rsp+38h+Str]
0x180002bb4  call    FwFree
0x180002bb9  test    ebx, ebx
0x180002bbb  js      short loc_180002BF8
0x180002bbd  mov     eax, ebx
0x180002bbf  mov     rbx, [rsp+38h+arg_0]
0x180002bc4  add     rsp, 20h
0x180002bc8  pop     r15
0x180002bca  pop     r14
0x180002bcc  pop     rdi
0x180002bcd  retn
0x180002bce  mov     edx, eax
0x180002bd0  lea     rcx, aFwgetexpandedc_0; "FwGetExpandedCanonicalLongPathName"
0x180002bd7  call    FwReportReturnError
0x180002bdc  jmp     short loc_180002BA7
0x180002bde  mov     [r14], edi
0x180002be1  jmp     short loc_180002BA7
0x180002be3  mov     edx, eax
0x180002be5  lea     rcx, aFwgetexpandedc_0; "FwGetExpandedCanonicalLongPathName"
0x180002bec  call    FwReportReturnError
0x180002bf1  mov     rdi, [rsp+38h+Src]
0x180002bf6  jmp     short loc_180002BA7
0x180002bf8  mov     edx, ebx
0x180002bfa  lea     rcx, aFwgetexpandedc_0; "FwGetExpandedCanonicalLongPathName"
0x180002c01  call    FwReportReturnError
0x180002c06  mov     ebx, eax
0x180002c08  jmp     short loc_180002BBD
```
