# GetOverlayFilePathUsingChecksum

- ea: `0x18005ae20`
- end: `0x18005b0e8`
- name: `GetOverlayFilePathUsingChecksum`
- size: `712`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x180059200`
- `0x18005c420`

## callees

- `0x18005a9f0`
- `0x18005ae20`
- `0x18005b0f0`
- `0x18005b470`
- `0x18005b808`
- `0x18005b94c`
- `0x18005ba20`
- `0x18005c6d0`
- `0x180090418`
- `0x1800e7bcc`
- `0x180127e50`
- `0x18015e4b0`
- `0x180162000`

## pseudocode

```c
__int64 __fastcall GetOverlayFilePathUsingChecksum(
        __int64 a1,
        __int64 a2,
        wchar_t *a3,
        __int64 a4,
        unsigned int *a5,
        wchar_t *Destination)
{
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  wchar_t *v12; // r14
  const wchar_t *NtSystemRoot; // rax
  __int64 v14; // rdi
  size_t v15; // rbx
  wchar_t v16; // cx
  wchar_t *Source; // rsi
  bool v18; // zf
  wchar_t *v19; // rbx
  unsigned int v20; // r14d
  int OverlayPackageKeyForLanguage; // ebp
  int OverlayPackagePathFromKey; // eax
  int started; // r8d
  __int64 v24; // rax
  int v25; // eax
  int v26; // edi
  int v28; // ecx
  unsigned int v29; // eax
  unsigned int v30; // ecx
  rsize_t v31; // rdx
  HANDLE Handle; // [rsp+50h] [rbp-338h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-330h]
  unsigned int v34; // [rsp+60h] [rbp-328h] BYREF
  int v35; // [rsp+64h] [rbp-324h] BYREF
  __int64 v36; // [rsp+68h] [rbp-320h]
  char v37; // [rsp+70h] [rbp-318h] BYREF

  v36 = a4;
  Handle = (HANDLE)46006272;
  String1 = (wchar_t *)&v37;
  if ( !a1 || !a2 || !a5 )
    return 3221225485LL;
  result = RtlAppendUnicodeToString(&Handle, a2);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -1073741789 )
      return 3221225659LL;
  }
  else
  {
    v12 = String1;
    Handle = 0;
    NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot(v10, v9, v11);
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( NtSystemRoot[v15] );
    if ( wcsnicmp(v12, NtSystemRoot, v15) )
    {
      if ( (int)IsProgramFilesPath(v12) < 0 )
        return 3221225659LL;
      v16 = aProgramFiles[0];
      Source = L"\\Program Files";
      v15 = (size_t)Handle;
    }
    else
    {
      v16 = aWindows[0];
      Source = (wchar_t *)L"\\Windows";
    }
    v18 = v12[v15] == 92;
    v19 = &v12[v15];
    if ( !v18 || (result = 0, v16 != 92) )
      result = 3221225659LL;
    if ( (int)result >= 0 )
    {
      v20 = *a5;
      v34 = *a5;
      v35 = 0;
      if ( Destination && v20 >= 2 )
        *Destination = 0;
      Handle = 0;
      OverlayPackageKeyForLanguage = GetOverlayPackageKeyForLanguage(a1, &Handle);
      if ( OverlayPackageKeyForLanguage >= 0 )
      {
        OverlayPackageKeyForLanguage = GetOverlayPackageTypeFromKey(Handle, &v35);
        if ( OverlayPackageKeyForLanguage >= 0 )
        {
          OverlayPackagePathFromKey = GetOverlayPackagePathFromKey(Handle, &v34, Destination);
          v20 = v34;
          OverlayPackageKeyForLanguage = OverlayPackagePathFromKey;
        }
        if ( Handle )
          NtClose(Handle);
      }
      started = -1073741789;
      if ( OverlayPackageKeyForLanguage < 0 )
      {
        if ( Destination && *a5 >= 2 )
          *Destination = 0;
        if ( OverlayPackageKeyForLanguage != -1073741789 )
          return (unsigned int)OverlayPackageKeyForLanguage;
      }
      v24 = -1;
      do
        ++v24;
      while ( v19[v24] );
      v25 = 2 * v24;
      do
        ++v14;
      while ( Source[v14] );
      v26 = 2 * v14;
      if ( (v35 & 1) != 0 && v36 && a3 )
      {
        return (unsigned int)BuildCumulativeOverlayFilePath(v20, Source, a3, v36, (__int64)a5, Destination);
      }
      else
      {
        v28 = v26 + v25;
        v29 = *a5;
        v30 = v20 + v28;
        v31 = v30 + 8;
        if ( v30 < 0x208 )
          v31 = v30;
        *a5 = v31;
        if ( (unsigned int)v31 > v29 )
          return (unsigned int)started;
        started = StartPathWithLongPathPrefixIfNeeded(v20, v31, Destination);
        if ( started < 0 )
          return (unsigned int)started;
        return (unsigned int)AppendStandardOverlayFilePath(v19, Source);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005ae20  push    rbx
0x18005ae22  push    rbp
0x18005ae23  push    rsi
0x18005ae24  push    rdi
0x18005ae25  push    r12
0x18005ae27  push    r13
0x18005ae29  push    r14
0x18005ae2b  push    r15
0x18005ae2d  sub     rsp, 348h
0x18005ae34  mov     rax, cs:__security_cookie
0x18005ae3b  xor     rax, rsp
0x18005ae3e  mov     [rsp+388h+var_58], rax
0x18005ae46  mov     r12, [rsp+388h+arg_20]
0x18005ae4e  lea     rax, [rsp+388h+var_318]
0x18005ae53  mov     r15, [rsp+388h+Destination]
0x18005ae5b  xor     ebx, ebx
0x18005ae5d  mov     [rsp+388h+var_320], r9
0x18005ae62  mov     r13, r8
0x18005ae65  mov     [rsp+388h+Handle], 2BE0000h
0x18005ae6e  mov     rbp, rcx
0x18005ae71  mov     [rsp+388h+String1], rax
0x18005ae76  test    rcx, rcx
0x18005ae79  jz      loc_18005B08B
0x18005ae7f  test    rdx, rdx
0x18005ae82  jz      loc_18005B08B
0x18005ae88  test    r12, r12
0x18005ae8b  jz      loc_18005B08B
0x18005ae91  lea     rcx, [rsp+388h+Handle]
0x18005ae96  call    RtlAppendUnicodeToString
0x18005ae9b  test    eax, eax
0x18005ae9d  js      loc_18005B0BA
0x18005aea3  mov     r14, [rsp+388h+String1]
0x18005aea8  mov     [rsp+388h+Handle], rbx
0x18005aead  call    RtlGetNtSystemRoot
0x18005aeb2  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18005aeb9  mov     rbx, rdi
0x18005aebc  nop     dword ptr [rax+00h]
0x18005aec0  inc     rbx
0x18005aec3  cmp     word ptr [rax+rbx*2], 0
0x18005aec8  jnz     short loc_18005AEC0
0x18005aeca  mov     r8, rbx; MaxCount
0x18005aecd  mov     rdx, rax; String2
0x18005aed0  mov     rcx, r14; String1
0x18005aed3  call    _wcsnicmp
0x18005aed8  test    eax, eax
0x18005aeda  jnz     loc_18005B095
0x18005aee0  movzx   ecx, word ptr cs:aWindows; "\\Windows"
0x18005aee7  lea     rsi, aWindows; "\\Windows"
0x18005aeee  cmp     word ptr [r14+rbx*2], 5Ch ; '\'
0x18005aef4  lea     rbx, [r14+rbx*2]
0x18005aef8  jnz     loc_18005B0B0
0x18005aefe  xor     eax, eax
0x18005af00  cmp     cx, 5Ch ; '\'
0x18005af04  jnz     loc_18005B0B0
0x18005af0a  test    eax, eax
0x18005af0c  js      loc_18005B001
0x18005af12  mov     r14d, [r12]
0x18005af16  mov     [rsp+388h+var_328], r14d
0x18005af1b  mov     [rsp+388h+var_324], 0
0x18005af23  test    r15, r15
0x18005af26  jz      short loc_18005AF34
0x18005af28  cmp     r14d, 2
0x18005af2c  jb      short loc_18005AF34
0x18005af2e  xor     eax, eax
0x18005af30  mov     [r15], ax
0x18005af34  lea     rdx, [rsp+388h+Handle]
0x18005af39  mov     [rsp+388h+Handle], 0
0x18005af42  mov     rcx, rbp
0x18005af45  call    _GetOverlayPackageKeyForLanguage
0x18005af4a  mov     ebp, eax
0x18005af4c  test    eax, eax
0x18005af4e  js      short loc_18005AF8D
0x18005af50  mov     rcx, [rsp+388h+Handle]
0x18005af55  lea     rdx, [rsp+388h+var_324]
0x18005af5a  call    _GetOverlayPackageTypeFromKey
0x18005af5f  mov     ebp, eax
0x18005af61  test    eax, eax
0x18005af63  js      short loc_18005AF7E
0x18005af65  mov     rcx, [rsp+388h+Handle]
0x18005af6a  lea     rdx, [rsp+388h+var_328]
0x18005af6f  mov     r8, r15
0x18005af72  call    _GetOverlayPackagePathFromKey
0x18005af77  mov     r14d, [rsp+388h+var_328]
0x18005af7c  mov     ebp, eax
0x18005af7e  mov     rcx, [rsp+388h+Handle]; Handle
0x18005af83  test    rcx, rcx
0x18005af86  jz      short loc_18005AF8D
0x18005af88  call    NtClose
0x18005af8d  mov     r8d, 0C0000023h
0x18005af93  test    ebp, ebp
0x18005af95  js      loc_18005B069
0x18005af9b  mov     rax, rdi
0x18005af9e  xchg    ax, ax
0x18005afa0  inc     rax
0x18005afa3  cmp     word ptr [rbx+rax*2], 0
0x18005afa8  jnz     short loc_18005AFA0
0x18005afaa  add     eax, eax
0x18005afac  nop     dword ptr [rax+00h]
0x18005afb0  inc     rdi
0x18005afb3  cmp     word ptr [rsi+rdi*2], 0
0x18005afb8  jnz     short loc_18005AFB0
0x18005afba  add     edi, edi
0x18005afbc  test    byte ptr [rsp+388h+var_324], 1
0x18005afc1  jz      short loc_18005B026
0x18005afc3  mov     rcx, [rsp+388h+var_320]
0x18005afc8  test    rcx, rcx
0x18005afcb  jz      short loc_18005B026
0x18005afcd  test    r13, r13
0x18005afd0  jz      short loc_18005B026
0x18005afd2  mov     [rsp+388h+var_348], r15; Destination
0x18005afd7  mov     r9d, edi
0x18005afda  mov     [rsp+388h+var_350], r12; __int64
0x18005afdf  mov     r8, rbx
0x18005afe2  mov     [rsp+388h+var_358], rcx; __int64
0x18005afe7  mov     edx, eax
0x18005afe9  mov     [rsp+388h+var_360], r13; wchar_t *
0x18005afee  mov     ecx, r14d; SourceSize
0x18005aff1  mov     [rsp+388h+Source], rsi; Source
0x18005aff6  call    _BuildCumulativeOverlayFilePath
0x18005affb  mov     r8d, eax
0x18005affe  mov     eax, r8d
0x18005b001  mov     rcx, [rsp+388h+var_58]
0x18005b009  xor     rcx, rsp; StackCookie
0x18005b00c  call    __security_check_cookie
0x18005b011  add     rsp, 348h
0x18005b018  pop     r15
0x18005b01a  pop     r14
0x18005b01c  pop     r13
0x18005b01e  pop     r12
0x18005b020  pop     rdi
0x18005b021  pop     rsi
0x18005b022  pop     rbp
0x18005b023  pop     rbx
0x18005b024  retn
0x18005b026  lea     ecx, [rdi+rax]
0x18005b029  mov     eax, [r12]
0x18005b02d  add     ecx, r14d
0x18005b030  cmp     ecx, 208h
0x18005b036  lea     edx, [rcx+8]
0x18005b039  cmovb   edx, ecx; DestinationSize
0x18005b03c  mov     [r12], edx
0x18005b040  cmp     edx, eax
0x18005b042  ja      short loc_18005AFFE
0x18005b044  mov     r8, r15; Destination
0x18005b047  mov     ecx, r14d; SourceSize
0x18005b04a  call    _StartPathWithLongPathPrefixIfNeeded
0x18005b04f  mov     r8d, eax
0x18005b052  test    eax, eax
0x18005b054  js      short loc_18005AFFE
0x18005b056  mov     r9, r15
0x18005b059  mov     r8, r12
0x18005b05c  mov     rdx, rsi; wchar_t *
0x18005b05f  mov     rcx, rbx; Source
0x18005b062  call    _AppendStandardOverlayFilePath
0x18005b067  jmp     short loc_18005AFFB
0x18005b069  test    r15, r15
0x18005b06c  jz      short loc_18005B07B
0x18005b06e  cmp     dword ptr [r12], 2
0x18005b073  jb      short loc_18005B07B
0x18005b075  xor     eax, eax
0x18005b077  mov     [r15], ax
0x18005b07b  cmp     ebp, r8d
0x18005b07e  jz      loc_18005AF9B
0x18005b084  mov     eax, ebp
0x18005b086  jmp     loc_18005B001
0x18005b08b  mov     eax, 0C000000Dh
0x18005b090  jmp     loc_18005B001
0x18005b095  lea     rdx, [rsp+388h+Handle]
0x18005b09a  mov     rcx, r14; String1
0x18005b09d  call    _IsProgramFilesPath
0x18005b0a2  test    eax, eax
0x18005b0a4  jns     short loc_18005B0D0
0x18005b0a6  mov     eax, 0C00000BBh
0x18005b0ab  jmp     loc_18005B001
0x18005b0b0  mov     eax, 0C00000BBh
0x18005b0b5  jmp     loc_18005AF0A
0x18005b0ba  mov     r8d, 0C0000023h
0x18005b0c0  mov     ecx, 0C00000BBh
0x18005b0c5  cmp     eax, r8d
0x18005b0c8  cmovz   eax, ecx
0x18005b0cb  jmp     loc_18005B001
0x18005b0d0  movzx   ecx, word ptr cs:aProgramFiles; "\\Program Files"
0x18005b0d7  lea     rsi, aProgramFiles; "\\Program Files"
0x18005b0de  mov     rbx, [rsp+388h+Handle]
0x18005b0e3  jmp     loc_18005AEEE
```
