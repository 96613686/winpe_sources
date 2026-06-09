# SecCreateProcessFileInformation

- ea: `0x14002cddc`
- end: `0x14002d013`
- name: `SecCreateProcessFileInformation`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x14002c6b0`

## callees

- `0x1400088dc`
- `0x140009990`
- `0x1400104af`
- `0x140011650`
- `0x140028640`
- `0x14002ad8c`
- `0x14002b220`
- `0x14002cddc`
- `0x14002d2f4`
- `0x14002d808`
- `0x14003b370`
- `0x14003b378`
- `0x14003b5bc`
- `0x14003b5c4`
- `0x14003b670`
- `0x14003b75c`
- `0x14003b964`
- `0x14003d3bc`
- `0x14003d558`
- `0x14003d61c`
- `0x14003d9bc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002cfe6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002cfe6`
- `ntoskrnl!ObfDereferenceObject` at `0x14002cfc2`
- `ntoskrnl!ObfDereferenceObject` at `0x14002cfc2`

## pseudocode

```c
__int64 __fastcall SecCreateProcessFileInformation(
        struct _KPROCESS *a1,
        struct _FILE_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        __int64 a4)
{
  struct _UNICODE_STRING *v4; // rsi
  const WCHAR *UnicodeSubstring; // r14
  int ProcessShortName; // eax
  struct _UNICODE_STRING *p_UnicodeString; // rcx
  int v12; // eax
  struct _FILE_OBJECT *v13; // r15
  int ImageNormalizedName; // r14d
  char CodeIntegrityRequiredSigningLevel; // si
  int CodeIntegrityMaximumFileSizeAllowed; // edi
  char IsCodeIntegrityForRemoteFilesEnabled; // bl
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rcx
  PVOID Object; // [rsp+30h] [rbp-38h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-30h] BYREF
  char v24[4]; // [rsp+40h] [rbp-28h] BYREF
  int v25; // [rsp+44h] [rbp-24h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-20h] BYREF

  v4 = (struct _UNICODE_STRING *)(a4 + 184);
  Object = 0;
  FileHandle = 0;
  v24[0] = 0;
  v25 = 0;
  UnicodeString = 0;
  UnicodeSubstring = 0;
  SecGetProcessOriginalFilename(a1);
  if ( _bittest64((const signed __int64 *)&xmmword_14001B740, 0x3Du) )
    UnicodeSubstring = SecRtlFindUnicodeSubstring(&a3->Length, (PCWCH *)L"$&", 0);
  if ( a3->Buffer && a3->Length )
  {
    if ( UnicodeSubstring && *(_QWORD *)(a4 + 192) && v4->Length )
      a3 = v4;
  }
  else if ( (unsigned __int8)SecIsProcessShortNamesEnabled() )
  {
    ProcessShortName = SecGetProcessShortName(a1, &UnicodeString);
    p_UnicodeString = &UnicodeString;
    if ( ProcessShortName < 0 )
      p_UnicodeString = a3;
    a3 = p_UnicodeString;
  }
  if ( (a2->Flags & 0x4000) != 0 )
  {
    v12 = SecReOpenImageFileObject((_DWORD)a2, (_DWORD)a3, 1, (unsigned int)&Object, (__int64)&FileHandle);
    v13 = (struct _FILE_OBJECT *)Object;
    if ( v12 < 0 )
      v13 = a2;
  }
  else
  {
    v13 = a2;
  }
  ImageNormalizedName = SecGetImageNormalizedName(v13, a3, a4 + 152);
  if ( ImageNormalizedName >= 0 )
  {
    _mm_lfence();
    ImageNormalizedName = SecGetFileFinalComponentName(a3, a4 + 168);
    if ( ImageNormalizedName >= 0 )
    {
      _mm_lfence();
      if ( (unsigned __int8)SecIsFileSourceMonitoringEnabled() )
        *(_BYTE *)(a4 + 724) = SecIsInMonitoredFileSourceApplicationsList(a4 + 168);
      *(_BYTE *)(a4 + 576) = SecFileHasMotwAds(v13);
      CodeIntegrityRequiredSigningLevel = SecGetCodeIntegrityRequiredSigningLevel();
      CodeIntegrityMaximumFileSizeAllowed = SecGetCodeIntegrityMaximumFileSizeAllowed();
      IsCodeIntegrityForRemoteFilesEnabled = SecIsCodeIntegrityForRemoteFilesEnabled();
      LOBYTE(v18) = SecIsCodeIntegrityEnabled();
      LOBYTE(v19) = IsCodeIntegrityForRemoteFilesEnabled;
      SecGetCiInformation(
        (_DWORD)v13,
        v18,
        v19,
        CodeIntegrityMaximumFileSizeAllowed,
        CodeIntegrityRequiredSigningLevel,
        a4 + 200);
      if ( !*(_DWORD *)(a4 + 204) && (unsigned __int8)SecIsCodeIntegrityFastLookupEnabled() )
      {
        _mm_lfence();
        if ( (int)SecGetFileObjectCachedSigningLevel(v13, v24, &v25) >= 0 )
        {
          _mm_lfence();
          LOBYTE(v20) = v24[0];
          SecConvertImageSignatureLevelToCiInformation(v20, a4 + 200);
        }
        ImageNormalizedName = 0;
      }
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose_0(FileHandle);
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)ImageNormalizedName;
}

```

## disassembly

```asm
0x14002cddc  push    rbp
0x14002cdde  push    rbx
0x14002cddf  push    rsi
0x14002cde0  push    rdi
0x14002cde1  push    r12
0x14002cde3  push    r13
0x14002cde5  push    r14
0x14002cde7  push    r15
0x14002cde9  mov     rbp, rsp
0x14002cdec  sub     rsp, 68h
0x14002cdf0  mov     rax, cs:__security_cookie
0x14002cdf7  xor     rax, rsp
0x14002cdfa  mov     [rbp+var_10], rax
0x14002cdfe  xor     r12d, r12d
0x14002ce01  lea     rsi, [r9+0B8h]
0x14002ce08  mov     rdi, rdx
0x14002ce0b  mov     [rbp+Object], r12
0x14002ce0f  xorps   xmm0, xmm0
0x14002ce12  mov     [rbp+FileHandle], r12
0x14002ce16  mov     rdx, rsi
0x14002ce19  mov     [rbp+var_28], r12b
0x14002ce1d  mov     r13, r9
0x14002ce20  mov     [rbp+var_24], r12d
0x14002ce24  mov     rbx, r8
0x14002ce27  mov     r15, rcx
0x14002ce2a  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14002ce2e  mov     r14d, r12d
0x14002ce31  call    SecGetProcessOriginalFilename
0x14002ce36  bt      qword ptr cs:xmmword_14001B740, 3Dh ; '='
0x14002ce3f  jnb     short loc_14002CE56
0x14002ce41  xor     r8d, r8d
0x14002ce44  lea     rdx, asc_140013600; "$&"
0x14002ce4b  mov     rcx, rbx
0x14002ce4e  call    SecRtlFindUnicodeSubstring
0x14002ce53  mov     r14, rax
0x14002ce56  cmp     [rbx+8], r12
0x14002ce5a  jz      short loc_14002CE7B
0x14002ce5c  cmp     [rbx], r12w
0x14002ce60  jz      short loc_14002CE7B
0x14002ce62  test    r14, r14
0x14002ce65  jz      short loc_14002CE9D
0x14002ce67  cmp     [r13+0C0h], r12
0x14002ce6e  jz      short loc_14002CE9D
0x14002ce70  cmp     [rsi], r12w
0x14002ce74  jz      short loc_14002CE9D
0x14002ce76  mov     rbx, rsi
0x14002ce79  jmp     short loc_14002CE9D
0x14002ce7b  call    SecIsProcessShortNamesEnabled
0x14002ce80  test    al, al
0x14002ce82  jz      short loc_14002CE9D
0x14002ce84  lea     rdx, [rbp+UnicodeString]
0x14002ce88  mov     rcx, r15
0x14002ce8b  call    SecGetProcessShortName
0x14002ce90  test    eax, eax
0x14002ce92  lea     rcx, [rbp+UnicodeString]
0x14002ce96  cmovs   rcx, rbx
0x14002ce9a  mov     rbx, rcx
0x14002ce9d  test    dword ptr [rdi+50h], 4000h
0x14002cea4  jz      short loc_14002CED0
0x14002cea6  lea     rax, [rbp+FileHandle]
0x14002ceaa  mov     r8d, 1
0x14002ceb0  lea     r9, [rbp+Object]
0x14002ceb4  mov     [rsp+68h+var_48], rax
0x14002ceb9  mov     rdx, rbx
0x14002cebc  mov     rcx, rdi
0x14002cebf  call    SecReOpenImageFileObject
0x14002cec4  mov     r15, [rbp+Object]
0x14002cec8  test    eax, eax
0x14002ceca  cmovs   r15, rdi
0x14002cece  jmp     short loc_14002CED3
0x14002ced0  mov     r15, rdi
0x14002ced3  lea     r8, [r13+98h]
0x14002ceda  mov     rdx, rbx
0x14002cedd  mov     rcx, r15
0x14002cee0  call    SecGetImageNormalizedName
0x14002cee5  mov     r14d, eax
0x14002cee8  test    eax, eax
0x14002ceea  js      loc_14002CFB9
0x14002cef0  lfence
0x14002cef3  lea     rdi, [r13+0A8h]
0x14002cefa  mov     rcx, rbx
0x14002cefd  mov     rdx, rdi
0x14002cf00  call    SecGetFileFinalComponentName
0x14002cf05  mov     r14d, eax
0x14002cf08  test    eax, eax
0x14002cf0a  js      loc_14002CFB9
0x14002cf10  lfence
0x14002cf13  call    SecIsFileSourceMonitoringEnabled
0x14002cf18  test    al, al
0x14002cf1a  jz      short loc_14002CF2B
0x14002cf1c  mov     rcx, rdi
0x14002cf1f  call    SecIsInMonitoredFileSourceApplicationsList
0x14002cf24  mov     [r13+2D4h], al
0x14002cf2b  mov     rcx, r15; FileObject
0x14002cf2e  call    SecFileHasMotwAds
0x14002cf33  mov     [r13+240h], al
0x14002cf3a  lea     r12, [r13+0C8h]
0x14002cf41  call    SecGetCodeIntegrityRequiredSigningLevel
0x14002cf46  mov     sil, al
0x14002cf49  call    SecGetCodeIntegrityMaximumFileSizeAllowed
0x14002cf4e  mov     edi, eax
0x14002cf50  call    SecIsCodeIntegrityForRemoteFilesEnabled
0x14002cf55  mov     bl, al
0x14002cf57  call    SecIsCodeIntegrityEnabled
0x14002cf5c  mov     dl, al
0x14002cf5e  mov     [rsp+68h+var_40], r12
0x14002cf63  mov     r9d, edi
0x14002cf66  mov     byte ptr [rsp+68h+var_48], sil
0x14002cf6b  mov     r8b, bl
0x14002cf6e  mov     rcx, r15
0x14002cf71  call    SecGetCiInformation
0x14002cf76  cmp     dword ptr [r13+0CCh], 0
0x14002cf7e  jnz     short loc_14002CFB6
0x14002cf80  call    SecIsCodeIntegrityFastLookupEnabled
0x14002cf85  test    al, al
0x14002cf87  jz      short loc_14002CFB6
0x14002cf89  lfence
0x14002cf8c  lea     r8, [rbp+var_24]
0x14002cf90  mov     rcx, r15
0x14002cf93  lea     rdx, [rbp+var_28]
0x14002cf97  call    SecGetFileObjectCachedSigningLevel
0x14002cf9c  test    eax, eax
0x14002cf9e  js      short loc_14002CFAE
0x14002cfa0  lfence
0x14002cfa3  mov     cl, [rbp+var_28]
0x14002cfa6  mov     rdx, r12
0x14002cfa9  call    SecConvertImageSignatureLevelToCiInformation
0x14002cfae  xor     r12d, r12d
0x14002cfb1  mov     r14d, r12d
0x14002cfb4  jmp     short loc_14002CFB9
0x14002cfb6  xor     r12d, r12d
0x14002cfb9  mov     rcx, [rbp+Object]; Object
0x14002cfbd  test    rcx, rcx
0x14002cfc0  jz      short loc_14002CFCE
0x14002cfc2  call    cs:__imp_ObfDereferenceObject
0x14002cfc9  nop     dword ptr [rax+rax+00h]
0x14002cfce  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002cfd2  test    rcx, rcx
0x14002cfd5  jz      short loc_14002CFDC
0x14002cfd7  call    FltClose_0
0x14002cfdc  cmp     [rbp+UnicodeString.Buffer], r12
0x14002cfe0  jz      short loc_14002CFF2
0x14002cfe2  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14002cfe6  call    cs:__imp_RtlFreeUnicodeString
0x14002cfed  nop     dword ptr [rax+rax+00h]
0x14002cff2  mov     eax, r14d
0x14002cff5  mov     rcx, [rbp+var_10]
0x14002cff9  xor     rcx, rsp; StackCookie
0x14002cffc  call    __security_check_cookie
0x14002d001  add     rsp, 68h
0x14002d005  pop     r15
0x14002d007  pop     r14
0x14002d009  pop     r13
0x14002d00b  pop     r12
0x14002d00d  pop     rdi
0x14002d00e  pop     rsi
0x14002d00f  pop     rbx
0x14002d010  pop     rbp
0x14002d011  retn
```
