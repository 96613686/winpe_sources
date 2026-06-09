# IopMountCimfsLayer

- ea: `0x140ca5650`
- end: `0x140ca57b2`
- name: `IopMountCimfsLayer`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x140c647e0`

## callees

- `0x1403887e8`
- `0x140403380`
- `0x1406dc8c0`
- `0x1408739b0`
- `0x1409230b0`
- `0x14094b120`
- `0x140a59ff0`
- `0x140ca5650`

## import_xrefs

- `ext-ms-win-ntos-globmerger-l1-1-0!CimfsMountBootVolume` at `0x140ca569f`
- `ext-ms-win-ntos-globmerger-l1-1-0!CimfsMountBootVolume` at `0x140ca569f`

## pseudocode

```c
__int64 __fastcall IopMountCimfsLayer(__int64 a1, __int64 a2, UNICODE_STRING *a3)
{
  NTSTATUS v5; // ebx
  __int128 v7; // [rsp+20h] [rbp-E0h] BYREF
  UNICODE_STRING GuidString; // [rsp+30h] [rbp-D0h] BYREF
  UNICODE_STRING DeviceName; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[64]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t SourceString[64]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&GuidString.Length = 0;
  GuidString.Buffer = 0;
  DestinationString = 0;
  DeviceName = 0;
  v7 = 0;
  v5 = CimfsMountBootVolume(a1, a2);
  if ( v5 >= 0 )
  {
    v5 = RtlStringFromGUID((const GUID *const)(a1 + 8), &GuidString);
    if ( v5 >= 0 )
    {
      v5 = RtlStringCbPrintfW(pszDest, 0x78u, L"\\ArcName\\cimfs%wZ", &GuidString);
      if ( v5 >= 0 )
      {
        DWORD1(v7) = *(_DWORD *)(&GuidString.MaximumLength + 1);
        *((_QWORD *)&v7 + 1) = _mm_srli_si128((__m128i)GuidString, 8).m128i_u64[0] + 2;
        LOWORD(v7) = GuidString.Length - 4;
        WORD1(v7) = GuidString.MaximumLength - 4;
        v5 = RtlStringCbPrintfW(SourceString, 0x78u, L"\\Device\\cimfs\\%wZ", &v7);
        if ( v5 >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, pszDest);
          RtlInitUnicodeString(&DeviceName, SourceString);
          v5 = IoCreateSymbolicLink(&DestinationString, &DeviceName);
          if ( v5 >= 0 )
          {
            if ( a3 )
              v5 = RtlDuplicateUnicodeString(0, &DeviceName, a3);
          }
        }
      }
    }
  }
  RtlFreeAnsiString(&GuidString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140ca5650  mov     [rsp-8+arg_18], rbx
0x140ca5655  push    rbp
0x140ca5656  push    rsi
0x140ca5657  push    rdi
0x140ca5658  lea     rbp, [rsp-70h]
0x140ca565d  sub     rsp, 170h
0x140ca5664  mov     rax, cs:__security_cookie
0x140ca566b  xor     rax, rsp
0x140ca566e  mov     [rbp+80h+var_20], rax
0x140ca5672  xorps   xmm0, xmm0
0x140ca5675  mov     qword ptr [rsp+180h+GuidString.Length], 0
0x140ca567e  xorps   xmm1, xmm1
0x140ca5681  mov     [rsp+180h+GuidString.Buffer], 0
0x140ca568a  movups  xmmword ptr [rsp+180h+DestinationString.Length], xmm0
0x140ca568f  mov     rdi, r8
0x140ca5692  mov     rsi, rcx
0x140ca5695  movups  xmmword ptr [rsp+180h+DeviceName.Length], xmm1
0x140ca569a  movups  [rsp+180h+var_160], xmm0
0x140ca569f  call    cs:__imp_CimfsMountBootVolume
0x140ca56a6  nop     dword ptr [rax+rax+00h]
0x140ca56ab  mov     ebx, eax
0x140ca56ad  test    eax, eax
0x140ca56af  js      loc_140CA5786
0x140ca56b5  lea     rcx, [rsi+8]; Guid
0x140ca56b9  lea     rdx, [rsp+180h+GuidString]; GuidString
0x140ca56be  call    RtlStringFromGUID
0x140ca56c3  mov     ebx, eax
0x140ca56c5  test    eax, eax
0x140ca56c7  js      loc_140CA5786
0x140ca56cd  mov     esi, 78h ; 'x'
0x140ca56d2  lea     r9, [rsp+180h+GuidString]
0x140ca56d7  mov     edx, esi; cbDest
0x140ca56d9  lea     r8, aArcnameCimfsWz; "\\ArcName\\cimfs%wZ"
0x140ca56e0  lea     rcx, [rsp+180h+pszDest]; pszDest
0x140ca56e5  call    RtlStringCbPrintfW
0x140ca56ea  mov     ebx, eax
0x140ca56ec  test    eax, eax
0x140ca56ee  js      loc_140CA5786
0x140ca56f4  movaps  xmm0, xmmword ptr [rsp+180h+GuidString.Length]
0x140ca56f9  lea     r9, [rsp+180h+var_160]
0x140ca56fe  movdqa  [rsp+180h+var_160], xmm0
0x140ca5704  lea     r8, aDeviceCimfsWz; "\\Device\\cimfs\\%wZ"
0x140ca570b  psrldq  xmm0, 8
0x140ca5710  lea     rcx, [rbp+80h+SourceString]; pszDest
0x140ca5714  movq    rax, xmm0
0x140ca5719  mov     edx, esi; cbDest
0x140ca571b  add     rax, 2
0x140ca571f  mov     qword ptr [rsp+180h+var_160+8], rax
0x140ca5724  mov     eax, 0FFFCh
0x140ca5729  add     word ptr [rsp+180h+var_160], ax
0x140ca572e  add     word ptr [rsp+180h+var_160+2], ax
0x140ca5733  call    RtlStringCbPrintfW
0x140ca5738  mov     ebx, eax
0x140ca573a  test    eax, eax
0x140ca573c  js      short loc_140CA5786
0x140ca573e  lea     rdx, [rsp+180h+pszDest]; SourceString
0x140ca5743  lea     rcx, [rsp+180h+DestinationString]; DestinationString
0x140ca5748  call    RtlInitUnicodeString
0x140ca574d  lea     rdx, [rbp+80h+SourceString]; SourceString
0x140ca5751  lea     rcx, [rsp+180h+DeviceName]; DestinationString
0x140ca5756  call    RtlInitUnicodeString
0x140ca575b  lea     rdx, [rsp+180h+DeviceName]; DeviceName
0x140ca5760  lea     rcx, [rsp+180h+DestinationString]; SymbolicLinkName
0x140ca5765  call    IoCreateSymbolicLink
0x140ca576a  mov     ebx, eax
0x140ca576c  test    eax, eax
0x140ca576e  js      short loc_140CA5786
0x140ca5770  test    rdi, rdi
0x140ca5773  jz      short loc_140CA5786
0x140ca5775  mov     r8, rdi; StringOut
0x140ca5778  lea     rdx, [rsp+180h+DeviceName]; StringIn
0x140ca577d  xor     ecx, ecx; Flags
0x140ca577f  call    RtlDuplicateUnicodeString
0x140ca5784  mov     ebx, eax
0x140ca5786  lea     rcx, [rsp+180h+GuidString]; UnicodeString
0x140ca578b  call    RtlFreeAnsiString
0x140ca5790  mov     eax, ebx
0x140ca5792  mov     rcx, [rbp+80h+var_20]
0x140ca5796  xor     rcx, rsp; StackCookie
0x140ca5799  call    __security_check_cookie
0x140ca579e  mov     rbx, [rsp+180h+arg_18]
0x140ca57a6  add     rsp, 170h
0x140ca57ad  pop     rdi
0x140ca57ae  pop     rsi
0x140ca57af  pop     rbp
0x140ca57b0  retn
```
