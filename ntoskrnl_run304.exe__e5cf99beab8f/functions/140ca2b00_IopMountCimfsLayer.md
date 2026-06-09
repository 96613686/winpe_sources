# IopMountCimfsLayer

- ea: `0x140ca2b00`
- end: `0x140ca2c62`
- name: `IopMountCimfsLayer`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x140c5f510`

## callees

- `0x1403f2d50`
- `0x1403f4ae8`
- `0x1406d9d70`
- `0x1408eeff0`
- `0x14092af90`
- `0x140964600`
- `0x140a52b80`
- `0x140ca2b00`

## import_xrefs

- `ext-ms-win-ntos-globmerger-l1-1-0!CimfsMountBootVolume` at `0x140ca2b4f`
- `ext-ms-win-ntos-globmerger-l1-1-0!CimfsMountBootVolume` at `0x140ca2b4f`

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
0x140ca2b00  mov     [rsp-8+arg_18], rbx
0x140ca2b05  push    rbp
0x140ca2b06  push    rsi
0x140ca2b07  push    rdi
0x140ca2b08  lea     rbp, [rsp-70h]
0x140ca2b0d  sub     rsp, 170h
0x140ca2b14  mov     rax, cs:__security_cookie
0x140ca2b1b  xor     rax, rsp
0x140ca2b1e  mov     [rbp+80h+var_20], rax
0x140ca2b22  xorps   xmm0, xmm0
0x140ca2b25  mov     qword ptr [rsp+180h+GuidString.Length], 0
0x140ca2b2e  xorps   xmm1, xmm1
0x140ca2b31  mov     [rsp+180h+GuidString.Buffer], 0
0x140ca2b3a  movups  xmmword ptr [rsp+180h+DestinationString.Length], xmm0
0x140ca2b3f  mov     rdi, r8
0x140ca2b42  mov     rsi, rcx
0x140ca2b45  movups  xmmword ptr [rsp+180h+DeviceName.Length], xmm1
0x140ca2b4a  movups  [rsp+180h+var_160], xmm0
0x140ca2b4f  call    cs:__imp_CimfsMountBootVolume
0x140ca2b56  nop     dword ptr [rax+rax+00h]
0x140ca2b5b  mov     ebx, eax
0x140ca2b5d  test    eax, eax
0x140ca2b5f  js      loc_140CA2C36
0x140ca2b65  lea     rcx, [rsi+8]; Guid
0x140ca2b69  lea     rdx, [rsp+180h+GuidString]; GuidString
0x140ca2b6e  call    RtlStringFromGUID
0x140ca2b73  mov     ebx, eax
0x140ca2b75  test    eax, eax
0x140ca2b77  js      loc_140CA2C36
0x140ca2b7d  mov     esi, 78h ; 'x'
0x140ca2b82  lea     r9, [rsp+180h+GuidString]
0x140ca2b87  mov     edx, esi; cbDest
0x140ca2b89  lea     r8, aArcnameCimfsWz; "\\ArcName\\cimfs%wZ"
0x140ca2b90  lea     rcx, [rsp+180h+pszDest]; pszDest
0x140ca2b95  call    RtlStringCbPrintfW
0x140ca2b9a  mov     ebx, eax
0x140ca2b9c  test    eax, eax
0x140ca2b9e  js      loc_140CA2C36
0x140ca2ba4  movaps  xmm0, xmmword ptr [rsp+180h+GuidString.Length]
0x140ca2ba9  lea     r9, [rsp+180h+var_160]
0x140ca2bae  movdqa  [rsp+180h+var_160], xmm0
0x140ca2bb4  lea     r8, aDeviceCimfsWz; "\\Device\\cimfs\\%wZ"
0x140ca2bbb  psrldq  xmm0, 8
0x140ca2bc0  lea     rcx, [rbp+80h+SourceString]; pszDest
0x140ca2bc4  movq    rax, xmm0
0x140ca2bc9  mov     edx, esi; cbDest
0x140ca2bcb  add     rax, 2
0x140ca2bcf  mov     qword ptr [rsp+180h+var_160+8], rax
0x140ca2bd4  mov     eax, 0FFFCh
0x140ca2bd9  add     word ptr [rsp+180h+var_160], ax
0x140ca2bde  add     word ptr [rsp+180h+var_160+2], ax
0x140ca2be3  call    RtlStringCbPrintfW
0x140ca2be8  mov     ebx, eax
0x140ca2bea  test    eax, eax
0x140ca2bec  js      short loc_140CA2C36
0x140ca2bee  lea     rdx, [rsp+180h+pszDest]; SourceString
0x140ca2bf3  lea     rcx, [rsp+180h+DestinationString]; DestinationString
0x140ca2bf8  call    RtlInitUnicodeString
0x140ca2bfd  lea     rdx, [rbp+80h+SourceString]; SourceString
0x140ca2c01  lea     rcx, [rsp+180h+DeviceName]; DestinationString
0x140ca2c06  call    RtlInitUnicodeString
0x140ca2c0b  lea     rdx, [rsp+180h+DeviceName]; DeviceName
0x140ca2c10  lea     rcx, [rsp+180h+DestinationString]; SymbolicLinkName
0x140ca2c15  call    IoCreateSymbolicLink
0x140ca2c1a  mov     ebx, eax
0x140ca2c1c  test    eax, eax
0x140ca2c1e  js      short loc_140CA2C36
0x140ca2c20  test    rdi, rdi
0x140ca2c23  jz      short loc_140CA2C36
0x140ca2c25  mov     r8, rdi; StringOut
0x140ca2c28  lea     rdx, [rsp+180h+DeviceName]; StringIn
0x140ca2c2d  xor     ecx, ecx; Flags
0x140ca2c2f  call    RtlDuplicateUnicodeString
0x140ca2c34  mov     ebx, eax
0x140ca2c36  lea     rcx, [rsp+180h+GuidString]; UnicodeString
0x140ca2c3b  call    RtlFreeAnsiString
0x140ca2c40  mov     eax, ebx
0x140ca2c42  mov     rcx, [rbp+80h+var_20]
0x140ca2c46  xor     rcx, rsp; StackCookie
0x140ca2c49  call    __security_check_cookie
0x140ca2c4e  mov     rbx, [rsp+180h+arg_18]
0x140ca2c56  add     rsp, 170h
0x140ca2c5d  pop     rdi
0x140ca2c5e  pop     rsi
0x140ca2c5f  pop     rbp
0x140ca2c60  retn
```
