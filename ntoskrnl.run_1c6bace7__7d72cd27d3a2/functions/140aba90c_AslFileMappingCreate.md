# AslFileMappingCreate

- ea: `0x140aba90c`
- end: `0x140abaa77`
- name: `AslFileMappingCreate`
- size: `363`
- prototype: ``
- caller_count: `6`
- callee_count: `12`
- tags: `reparse_path`

## callers

- `0x14073a320`
- `0x14073f7c4`
- `0x140821914`
- `0x140823560`
- `0x1408bf424`
- `0x140aba6f8`

## callees

- `0x140403380`
- `0x1404e4800`
- `0x1406dc8c0`
- `0x1406dd600`
- `0x140737628`
- `0x1408be914`
- `0x1408bf658`
- `0x1408c0070`
- `0x1408c2f88`
- `0x14094b120`
- `0x140aba90c`
- `0x140adbc58`

## string_xrefs

- `0x140b77d2f`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x140b77ce9`: `AslFileMappingCreate`
- `0x140b77d28`: `AslFileMappingCreate`
- `0x140b77db5`: `AslFileMappingCreate`
- `0x140b77dee`: `AslFileMappingCreate`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(__int64 *a1, const WCHAR *a2, void *a3, __int64 a4, __int64 a5)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rdi
  unsigned int v13; // ebx
  NTSTATUS v14; // eax
  void *v15; // rax
  HANDLE *v16; // rsi
  int v17; // eax
  const char *v18; // r9
  int v19; // r8d
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // r8d
  int v23; // ecx
  int FileKind; // eax
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v29; // [rsp+60h] [rbp-10h]

  v29 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v11 = AslAlloc(v10, 88);
  v12 = v11;
  if ( v11 )
  {
    v14 = AslStringDuplicate(v11, a2);
    v13 = v14;
    if ( v14 < 0 )
    {
      v18 = "AslStringDuplicate failed [%x]";
      v19 = 123;
    }
    else
    {
      v15 = 0;
      if ( a3 != (void *)-1LL )
        v15 = a3;
      v16 = (HANDLE *)(v12 + 8);
      if ( v15 )
      {
        *(_OWORD *)v16 = 0;
        *(_OWORD *)(v12 + 24) = 0;
        *(_OWORD *)(v12 + 40) = 0;
        *(_QWORD *)(v12 + 56) = 0;
        *v16 = v15;
      }
      else
      {
        v17 = RtlFileMapInitializeByNtPath(v12 + 8, &DestinationString);
        v13 = v17;
        if ( v17 < 0 )
        {
          if ( !(unsigned int)AslFileNotFound((unsigned int)v17) )
          {
            v20 = v13 + 1073741805;
            if ( (unsigned int)v20 <= 0x30 && (v21 = 0x1000000008001LL, _bittest64(&v21, v20)) || v13 == -1073741638 )
            {
              v22 = 163;
              v23 = 3;
            }
            else
            {
              v22 = 161;
              v23 = 1;
            }
            AslLogCallPrintf(
              v23,
              (unsigned int)"AslFileMappingCreate",
              v22,
              (unsigned int)"RtlFileMapInitializeByFilePath failed %S [%x]",
              a2,
              v13,
              *(_QWORD *)&DestinationString.Length);
          }
          goto LABEL_16;
        }
      }
      v29 = 0;
      IoStatusBlock = 0;
      FileInformation = 0;
      v14 = ZwQueryInformationFile(*v16, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      v13 = v14;
      if ( v14 >= 0 )
      {
        if ( a4 )
        {
          *(_QWORD *)(v12 + 40) = a5;
          *(_BYTE *)(v12 + 59) = 1;
          *(_QWORD *)(v12 + 32) = a4;
        }
        *(_QWORD *)(v12 + 24) = *((_QWORD *)&FileInformation + 1);
        if ( a4 )
        {
          if ( !*((_QWORD *)&FileInformation + 1) )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"AslFileMappingCreate",
              208,
              (unsigned int)"File size is 0 bytes yet ImageViewBase was present");
            v13 = -1073741811;
            goto LABEL_16;
          }
          FileKind = AslpFileMappingGetFileKind(v12 + 8, v12 + 64);
          if ( FileKind < 0 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"AslFileMappingCreate",
              215,
              (unsigned int)"AslpFileMappingGetFileKind failed %S [%x]",
              *(_QWORD *)v12,
              FileKind,
              *(_QWORD *)&DestinationString.Length);
            *(_DWORD *)(v12 + 64) = 3;
          }
        }
        else
        {
          *(_DWORD *)(v12 + 64) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
        }
        *a1 = v12;
        v13 = 0;
        goto LABEL_7;
      }
      v18 = "NtQueryInformationFile failed [%x]";
      v19 = 183;
    }
    FileInformationClass[0] = v14;
    AslLogCallPrintf(1, (unsigned int)"AslFileMappingCreate", v19, (_DWORD)v18, *(_QWORD *)FileInformationClass);
LABEL_16:
    AslFileMappingDelete(v12);
    goto LABEL_7;
  }
  v13 = -1073741801;
LABEL_7:
  if ( DestinationString.Buffer != a2 )
    RtlFreeAnsiString(&DestinationString);
  return v13;
}

```

## disassembly

```asm
0x140aba90c  mov     [rsp-38h+arg_10], rbx
0x140aba911  push    rbp
0x140aba912  push    rsi
0x140aba913  push    rdi
0x140aba914  push    r12
0x140aba916  push    r13
0x140aba918  push    r14
0x140aba91a  push    r15
0x140aba91c  mov     rbp, rsp
0x140aba91f  sub     rsp, 70h
0x140aba923  mov     rax, cs:__security_cookie
0x140aba92a  xor     rax, rsp
0x140aba92d  mov     [rbp+var_8], rax
0x140aba931  xor     eax, eax
0x140aba933  xorps   xmm0, xmm0
0x140aba936  xor     r13d, r13d
0x140aba939  mov     [rbp+var_10], rax
0x140aba93d  xorps   xmm1, xmm1
0x140aba940  mov     r15, r9
0x140aba943  mov     rsi, r8
0x140aba946  mov     r14, rdx
0x140aba949  mov     r12, rcx
0x140aba94c  movups  [rbp+FileInformation], xmm0
0x140aba950  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140aba954  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x140aba958  test    rdx, rdx
0x140aba95b  jz      short loc_140ABA968
0x140aba95d  cmp     [rdx], r13w
0x140aba961  jz      short loc_140ABA968
0x140aba963  test    rcx, rcx
0x140aba966  jnz     short loc_140ABA992
0x140aba968  mov     eax, 0C000000Dh
0x140aba96d  mov     rcx, [rbp+var_8]
0x140aba971  xor     rcx, rsp; StackCookie
0x140aba974  call    __security_check_cookie
0x140aba979  mov     rbx, [rsp+70h+arg_10]
0x140aba981  add     rsp, 70h
0x140aba985  pop     r15
0x140aba987  pop     r14
0x140aba989  pop     r13
0x140aba98b  pop     r12
0x140aba98d  pop     rdi
0x140aba98e  pop     rsi
0x140aba98f  pop     rbp
0x140aba990  retn
0x140aba992  mov     [rcx], r13
0x140aba995  lea     rcx, [rbp+DestinationString]; DestinationString
0x140aba999  call    RtlInitUnicodeString
0x140aba99e  mov     edx, 58h ; 'X'
0x140aba9a3  call    AslAlloc
0x140aba9a8  mov     rdi, rax
0x140aba9ab  test    rax, rax
0x140aba9ae  jnz     short loc_140ABA9C3
0x140aba9b0  mov     ebx, 0C0000017h
0x140aba9b5  cmp     [rbp+DestinationString.Buffer], r14
0x140aba9b9  jnz     loc_140ABAA69
0x140aba9bf  mov     eax, ebx
0x140aba9c1  jmp     short loc_140ABA96D
0x140aba9c3  mov     rdx, r14
0x140aba9c6  mov     rcx, rdi
0x140aba9c9  call    AslStringDuplicate
0x140aba9ce  mov     ebx, eax
0x140aba9d0  test    eax, eax
0x140aba9d2  js      short loc_140ABAA13
0x140aba9d4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140aba9d8  mov     rax, r13
0x140aba9db  cmovnz  rax, rsi
0x140aba9df  lea     rsi, [rdi+8]
0x140aba9e3  test    rax, rax
0x140aba9e6  jnz     short loc_140ABAA25
0x140aba9e8  lea     rdx, [rbp+DestinationString]
0x140aba9ec  mov     rcx, rsi
0x140aba9ef  call    RtlFileMapInitializeByNtPath
0x140aba9f4  mov     ebx, eax
0x140aba9f6  test    eax, eax
0x140aba9f8  jns     loc_140B77D46
0x140aba9fe  mov     ecx, eax
0x140abaa00  call    AslFileNotFound
0x140abaa05  test    eax, eax
0x140abaa07  jz      short loc_140ABAA41
0x140abaa09  mov     rcx, rdi
0x140abaa0c  call    AslFileMappingDelete
0x140abaa11  jmp     short loc_140ABA9B5
0x140abaa13  lea     r9, aAslstringdupli_0; "AslStringDuplicate failed [%x]"
0x140abaa1a  mov     r8d, 7Bh ; '{'
0x140abaa20  jmp     loc_140B77CE9
0x140abaa25  xorps   xmm0, xmm0
0x140abaa28  xor     ecx, ecx
0x140abaa2a  movups  xmmword ptr [rsi], xmm0
0x140abaa2d  movups  xmmword ptr [rsi+10h], xmm0
0x140abaa31  movups  xmmword ptr [rsi+20h], xmm0
0x140abaa35  mov     [rsi+30h], rcx
0x140abaa39  mov     [rsi], rax
0x140abaa3c  jmp     loc_140B77D46
0x140abaa41  lea     eax, [rbx+3FFFFFEDh]
0x140abaa47  cmp     eax, 30h ; '0'
0x140abaa4a  ja      loc_140B77D04
0x140abaa50  mov     rcx, 1000000008001h
0x140abaa5a  bt      rcx, rax
0x140abaa5e  jnb     loc_140B77D04
0x140abaa64  jmp     loc_140B77D19
0x140abaa69  lea     rcx, [rbp+DestinationString]; UnicodeString
0x140abaa6d  call    RtlFreeAnsiString
0x140abaa72  jmp     loc_140ABA9BF
0x140b77cdc  lea     r9, aNtqueryinforma_4; "NtQueryInformationFile failed [%x]"
0x140b77ce3  mov     r8d, 0B7h
0x140b77ce9  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x140b77cf0  mov     [rsp+70h+FileInformationClass], eax
0x140b77cf4  mov     ecx, 1
0x140b77cf9  call    AslLogCallPrintf
0x140b77cfe  nop
0x140b77cff  jmp     loc_140ABAA09
0x140b77d04  cmp     ebx, 0C00000BAh
0x140b77d0a  jz      short loc_140B77D19
0x140b77d0c  mov     r8d, 0A1h
0x140b77d12  mov     ecx, 1
0x140b77d17  jmp     short loc_140B77D24
0x140b77d19  mov     r8d, 0A3h
0x140b77d1f  mov     ecx, 3
0x140b77d24  mov     [rsp+70h+var_48], ebx
0x140b77d28  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x140b77d2f  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x140b77d36  mov     qword ptr [rsp+70h+FileInformationClass], r14
0x140b77d3b  call    AslLogCallPrintf
0x140b77d40  nop
0x140b77d41  jmp     loc_140ABAA09
0x140b77d46  xor     eax, eax
0x140b77d48  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x140b77d50  xorps   xmm0, xmm0
0x140b77d53  mov     [rbp+var_10], rax
0x140b77d57  xorps   xmm1, xmm1
0x140b77d5a  lea     r8, [rbp+FileInformation]; FileInformation
0x140b77d5e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140b77d62  lea     r9d, [rax+18h]; Length
0x140b77d66  movups  [rbp+FileInformation], xmm1
0x140b77d6a  mov     rcx, [rsi]; FileHandle
0x140b77d6d  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x140b77d71  call    ZwQueryInformationFile
0x140b77d76  mov     ebx, eax
0x140b77d78  test    eax, eax
0x140b77d7a  js      loc_140B77CDC
0x140b77d80  test    r15, r15
0x140b77d83  jz      short loc_140B77D95
0x140b77d85  mov     rax, [rbp+arg_20]
0x140b77d89  mov     [rdi+28h], rax
0x140b77d8d  mov     byte ptr [rdi+3Bh], 1
0x140b77d91  mov     [rdi+20h], r15
0x140b77d95  mov     rax, qword ptr [rbp+FileInformation+8]
0x140b77d99  mov     [rdi+18h], rax
0x140b77d9d  test    r15, r15
0x140b77da0  jz      short loc_140B77E13
0x140b77da2  cmp     qword ptr [rbp+FileInformation+8], r13
0x140b77da6  jnz     short loc_140B77DD0
0x140b77da8  lea     r9, aFileSizeIs0Byt; "File size is 0 bytes yet ImageViewBase "...
0x140b77daf  mov     r8d, 0D0h
0x140b77db5  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x140b77dbc  mov     ecx, 1
0x140b77dc1  call    AslLogCallPrintf
0x140b77dc6  mov     ebx, 0C000000Dh
0x140b77dcb  jmp     loc_140ABAA09
0x140b77dd0  lea     rdx, [rdi+40h]
0x140b77dd4  mov     rcx, rsi
0x140b77dd7  call    AslpFileMappingGetFileKind
0x140b77ddc  test    eax, eax
0x140b77dde  jns     short loc_140B77E23
0x140b77de0  mov     [rsp+70h+var_48], eax
0x140b77de4  lea     r9, aAslpfilemappin; "AslpFileMappingGetFileKind failed %S [%"...
0x140b77deb  mov     rax, [rdi]
0x140b77dee  lea     rdx, aAslfilemapping_5; "AslFileMappingCreate"
0x140b77df5  mov     r8d, 0D7h
0x140b77dfb  mov     qword ptr [rsp+70h+FileInformationClass], rax
0x140b77e00  mov     ecx, 1
0x140b77e05  call    AslLogCallPrintf
0x140b77e0a  mov     dword ptr [rdi+40h], 3
0x140b77e11  jmp     short loc_140B77E23
0x140b77e13  mov     rax, qword ptr [rbp+FileInformation+8]
0x140b77e17  neg     rax
0x140b77e1a  sbb     ecx, ecx
0x140b77e1c  neg     ecx
0x140b77e1e  inc     ecx
0x140b77e20  mov     [rdi+40h], ecx
0x140b77e23  mov     [r12], rdi
0x140b77e27  mov     ebx, r13d
0x140b77e2a  jmp     loc_140ABA9B5
```
