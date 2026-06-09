# AELogAutoEnrollmentEvent

- ea: `0x1800027e0`
- end: `0x180002bac`
- name: `AELogAutoEnrollmentEvent`
- size: `972`
- prototype: `int __fastcall(DWORD, int, DWORD, DWORD, int, HANDLE TokenHandle, unsigned int, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800015d0`
- `0x180001a60`
- `0x180001d90`
- `0x180006b10`

## callees

- `0x1800027e0`
- `0x18000740c`
- `0x180007cf2`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002afb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800028cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800028cb`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002a87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180002a87`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002b96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ba1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002af1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002b3b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002af1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002b3b`
- `SspiCli!GetUserNameExW` at `0x1800029f0`
- `SspiCli!GetUserNameExW` at `0x1800029f0`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000296b`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x18000296b`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180002974`
- `api-ms-win-eventlog-legacy-l1-1-0!DeregisterEventSource` at `0x180002974`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18000287c`
- `api-ms-win-eventlog-legacy-l1-1-0!RegisterEventSourceW` at `0x18000287c`

## pseudocode

```c
int __fastcall AELogAutoEnrollmentEvent(
        DWORD a1,
        int a2,
        DWORD a3,
        DWORD a4,
        int a5,
        HANDLE TokenHandle,
        unsigned int a7,
        char a8)
{
  HANDLE v12; // rax
  DWORD v13; // ebx
  void *v14; // r15
  void *lpUserSid; // rdi
  UINT v16; // edx
  const WCHAR **v17; // r9
  WORD wNumStrings; // dx
  unsigned int v19; // r10d
  int v20; // r14d
  void **v21; // r12
  WORD v22; // ax
  DWORD v23; // ebx
  const WCHAR *v24; // rax
  __int64 v25; // rcx
  DWORD v26; // edi
  LPCWSTR *v27; // r12
  DWORD v28; // eax
  const WCHAR *v29; // rcx
  BOOL v30; // eax
  unsigned __int16 v32; // [rsp+50h] [rbp-B0h]
  DWORD ReturnLength; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int hMem; // [rsp+58h] [rbp-A8h]
  ULONG hMem_4; // [rsp+5Ch] [rbp-A4h] BYREF
  WCHAR v36[4]; // [rsp+60h] [rbp-A0h] BYREF
  void *v37; // [rsp+70h] [rbp-90h]
  LPCWSTR Strings[24]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD TokenInformation[32]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Buffer[256]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v41[256]; // [rsp+440h] [rbp+340h] BYREF

  ReturnLength = 0;
  LODWORD(v12) = (unsigned int)memset_0(Strings, 0, 0xB8u);
  hMem_4 = 0;
  *(_QWORD *)v36 = 0;
  v13 = a4 >> 30;
  if ( a4 >> 30 >= a1 && v13 )
    return (int)v12;
  v12 = RegisterEventSourceW(0, L"AutoEnrollment");
  v14 = v12;
  if ( !v12 )
    return (int)v12;
  lpUserSid = 0;
  hMem = 0;
  v37 = 0;
  Buffer[0] = 0;
  if ( a5 )
  {
    v16 = 2001;
LABEL_6:
    LoadStringW(g_hmodThisDll, v16, Buffer, 256);
    goto LABEL_7;
  }
  hMem_4 = 256;
  if ( !GetUserNameExW(NameSamCompatible, Buffer, &hMem_4) )
  {
    v16 = 2000;
    goto LABEL_6;
  }
LABEL_7:
  Strings[0] = Buffer;
  v17 = (const WCHAR **)&a8;
  v32 = 1;
  wNumStrings = 1;
  v19 = 0;
  if ( a7 )
  {
    do
    {
      v24 = *v17++;
      v25 = wNumStrings++;
      Strings[v25] = v24;
      if ( wNumStrings >= 0x14u )
        break;
      ++v19;
    }
    while ( v19 < a7 );
    v32 = wNumStrings;
  }
  if ( a2 )
  {
    v26 = -2147467259;
    if ( a3 )
      v26 = a3;
    StringCchPrintfW(v41, 0x100u, L"0x%lx", v26);
    Strings[v32] = v41;
    v27 = &Strings[(unsigned __int16)(v32 + 1)];
    v28 = FormatMessageW(0x1100u, 0, v26, 0x400u, v36, 0, 0);
    lpUserSid = v37;
    v29 = L" ";
    wNumStrings = v32 + 2;
    v32 += 2;
    if ( v28 && *(_QWORD *)v36 )
      v29 = *(const WCHAR **)v36;
    *v27 = v29;
  }
  if ( a5 || !TokenHandle )
  {
    v20 = hMem;
    v21 = (void **)hMem;
  }
  else
  {
    ReturnLength = 256;
    v21 = (void **)TokenInformation;
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &ReturnLength) )
    {
      lpUserSid = (void *)TokenInformation[0];
    }
    else if ( GetLastError() == 122 )
    {
      v21 = (void **)LocalAlloc(0x40u, ReturnLength);
      if ( v21 )
      {
        v20 = 1;
        v30 = GetTokenInformation(TokenHandle, TokenUser, v21, ReturnLength, &ReturnLength);
        wNumStrings = v32;
        if ( v30 )
          lpUserSid = *v21;
        goto LABEL_11;
      }
    }
    wNumStrings = v32;
    v20 = hMem;
  }
LABEL_11:
  if ( v13 == 2 )
  {
    v22 = 2;
  }
  else
  {
    v22 = 0;
    if ( v13 )
    {
      v23 = v13 - 1;
      if ( v23 )
      {
        if ( v23 == 2 )
          v22 = 4;
      }
      else
      {
        v22 = 1;
      }
    }
  }
  ReportEventW(v14, v22, 0, a4, lpUserSid, wNumStrings, 0, Strings, 0);
  LODWORD(v12) = DeregisterEventSource(v14);
  if ( v20 && v21 )
    LODWORD(v12) = (unsigned int)LocalFree(v21);
  if ( *(_QWORD *)v36 )
    LODWORD(v12) = (unsigned int)LocalFree(*(HLOCAL *)v36);
  return (int)v12;
}

```

## disassembly

```asm
0x1800027e0  push    rbp
0x1800027e2  push    rbx
0x1800027e3  push    rsi
0x1800027e4  push    rdi
0x1800027e5  push    r12
0x1800027e7  push    r13
0x1800027e9  push    r14
0x1800027eb  lea     rbp, [rsp-560h]
0x1800027f3  sub     rsp, 660h
0x1800027fa  mov     rax, cs:__security_cookie
0x180002801  xor     rax, rsp
0x180002804  mov     [rbp+590h+var_50], rax
0x18000280b  mov     r13, [rbp+590h+TokenHandle]
0x180002812  mov     r12d, r8d
0x180002815  mov     r14d, edx
0x180002818  mov     edi, ecx
0x18000281a  xor     ebx, ebx
0x18000281c  lea     rcx, [rbp+590h+Strings]; void *
0x180002820  xor     edx, edx; Val
0x180002822  mov     [rsp+690h+ReturnLength], ebx
0x180002826  mov     r8d, 0B8h; Size
0x18000282c  mov     esi, r9d
0x18000282f  call    memset_0
0x180002834  mov     dword ptr [rsp+690h+hMem+4], ebx
0x180002838  mov     qword ptr [rsp+690h+var_630], rbx
0x18000283d  mov     ebx, esi
0x18000283f  shr     ebx, 1Eh
0x180002842  cmp     ebx, edi
0x180002844  jb      short loc_18000286B
0x180002846  test    ebx, ebx
0x180002848  jz      short loc_18000286B
0x18000284a  mov     rcx, [rbp+590h+var_50]
0x180002851  xor     rcx, rsp; StackCookie
0x180002854  call    __security_check_cookie
0x180002859  add     rsp, 660h
0x180002860  pop     r14
0x180002862  pop     r13
0x180002864  pop     r12
0x180002866  pop     rdi
0x180002867  pop     rsi
0x180002868  pop     rbx
0x180002869  pop     rbp
0x18000286a  retn
0x18000286b  lea     rdx, SourceName; "AutoEnrollment"
0x180002872  mov     [rsp+690h+var_38], r15
0x18000287a  xor     ecx, ecx; lpUNCServerName
0x18000287c  call    cs:__imp_RegisterEventSourceW
0x180002882  mov     r15, rax
0x180002885  test    rax, rax
0x180002888  jz      loc_180002991
0x18000288e  xor     edi, edi
0x180002890  mov     dword ptr [rsp+690h+hMem], 0
0x180002898  xor     ecx, ecx
0x18000289a  mov     [rsp+690h+var_620], rdi
0x18000289f  mov     [rbp+590h+Buffer], cx
0x1800028a6  cmp     [rbp+590h+arg_20], ecx
0x1800028ac  jz      loc_1800029D7
0x1800028b2  mov     edx, 7D1h; uID
0x1800028b7  mov     rcx, cs:g_hmodThisDll; hInstance
0x1800028be  lea     r8, [rbp+590h+Buffer]; lpBuffer
0x1800028c5  mov     r9d, 100h; cchBufferMax
0x1800028cb  call    cs:__imp_LoadStringW
0x1800028d1  mov     r8d, [rbp+590h+arg_30]
0x1800028d8  lea     rax, [rbp+590h+Buffer]
0x1800028df  xor     r11d, r11d
0x1800028e2  mov     [rbp+590h+Strings], rax
0x1800028e6  lea     r9, [rbp+590h+arg_38]
0x1800028ed  mov     ecx, 1
0x1800028f2  mov     [rsp+690h+var_640], cx
0x1800028f7  movzx   edx, cx
0x1800028fa  mov     r10d, r11d
0x1800028fd  test    r8d, r8d
0x180002900  jnz     loc_1800029B0
0x180002906  test    r14d, r14d
0x180002909  jnz     loc_180002A12
0x18000290f  cmp     [rbp+590h+arg_20], 0
0x180002916  jz      loc_180002AC3
0x18000291c  mov     r14d, dword ptr [rsp+690h+hMem]
0x180002921  mov     r12d, r14d
0x180002924  cmp     ebx, 2
0x180002927  jz      short loc_18000299E
0x180002929  mov     eax, r11d
0x18000292c  test    ebx, ebx
0x18000292e  jz      short loc_180002942
0x180002930  sub     ebx, 1
0x180002933  jz      loc_180002B82
0x180002939  cmp     ebx, 2
0x18000293c  jz      loc_180002B78
0x180002942  mov     [rsp+690h+lpRawData], r11; lpRawData
0x180002947  lea     rcx, [rbp+590h+Strings]
0x18000294b  mov     [rsp+690h+lpStrings], rcx; lpStrings
0x180002950  xor     r8d, r8d; wCategory
0x180002953  mov     [rsp+690h+dwDataSize], r11d; dwDataSize
0x180002958  mov     r9d, esi; dwEventID
0x18000295b  mov     [rsp+690h+wNumStrings], dx; wNumStrings
0x180002960  mov     rcx, r15; hEventLog
0x180002963  movzx   edx, ax; wType
0x180002966  mov     [rsp+690h+lpUserSid], rdi; lpUserSid
0x18000296b  call    cs:__imp_ReportEventW
0x180002971  mov     rcx, r15; hEventLog
0x180002974  call    cs:__imp_DeregisterEventSource
0x18000297a  test    r14d, r14d
0x18000297d  jnz     loc_180002B8A
0x180002983  mov     rcx, qword ptr [rsp+690h+var_630]; hMem
0x180002988  test    rcx, rcx
0x18000298b  jnz     loc_180002BA1
0x180002991  mov     r15, [rsp+690h+var_38]
0x180002999  jmp     loc_18000284A
0x18000299e  mov     eax, 2
0x1800029a3  jmp     short loc_180002942
0x1800029b0  mov     rax, [r9]
0x1800029b3  lea     r9, [r9+8]
0x1800029b7  movzx   ecx, dx
0x1800029ba  inc     dx
0x1800029bd  mov     [rbp+rcx*8+590h+Strings], rax
0x1800029c2  cmp     dx, 14h
0x1800029c6  jb      short loc_180002A08
0x1800029c8  mov     [rsp+690h+var_640], dx
0x1800029cd  mov     ecx, 1
0x1800029d2  jmp     loc_180002906
0x1800029d7  lea     r8, [rsp+690h+hMem+4]; nSize
0x1800029dc  mov     dword ptr [rsp+690h+hMem+4], 100h
0x1800029e4  lea     rdx, [rbp+590h+Buffer]; lpNameBuffer
0x1800029eb  mov     ecx, 2; NameFormat
0x1800029f0  call    cs:__imp_GetUserNameExW
0x1800029f6  test    al, al
0x1800029f8  jnz     loc_1800028D1
0x1800029fe  mov     edx, 7D0h
0x180002a03  jmp     loc_1800028B7
0x180002a08  inc     r10d
0x180002a0b  cmp     r10d, r8d
0x180002a0e  jb      short loc_1800029B0
0x180002a10  jmp     short loc_1800029C8
0x180002a12  test    r12d, r12d
0x180002a15  lea     r8, a0xLx; "0x%lx"
0x180002a1c  mov     edi, 80004005h
0x180002a21  lea     rcx, [rbp+590h+var_250]; unsigned __int16 *
0x180002a28  cmovnz  edi, r12d
0x180002a2c  mov     edx, 100h; unsigned __int64
0x180002a31  mov     r9d, edi
0x180002a34  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002a39  movzx   ecx, [rsp+690h+var_640]
0x180002a3e  lea     rdx, [rbp+590h+var_250]
0x180002a45  mov     qword ptr [rsp+690h+dwDataSize], 0; Arguments
0x180002a4e  lea     r12, [rbp+590h+Strings]
0x180002a52  mov     dword ptr [rsp+690h+wNumStrings], 0; nSize
0x180002a5a  mov     r9d, 400h; dwLanguageId
0x180002a60  mov     r8d, edi; dwMessageId
0x180002a63  mov     [rbp+rcx*8+590h+Strings], rdx
0x180002a68  inc     cx
0x180002a6b  movzx   eax, cx
0x180002a6e  xor     edx, edx; lpSource
0x180002a70  lea     r14d, [rcx+1]
0x180002a74  mov     ecx, 1100h; dwFlags
0x180002a79  lea     r12, [r12+rax*8]
0x180002a7d  lea     rax, [rsp+690h+var_630]
0x180002a82  mov     [rsp+690h+lpUserSid], rax; lpBuffer
0x180002a87  call    cs:__imp_FormatMessageW
0x180002a8d  mov     rdi, [rsp+690h+var_620]
0x180002a92  lea     rcx, pszTrimChars; " "
0x180002a99  movzx   edx, r14w
0x180002a9d  mov     [rsp+690h+var_640], dx
0x180002aa2  test    eax, eax
0x180002aa4  jz      short loc_180002AB2
0x180002aa6  mov     rax, qword ptr [rsp+690h+var_630]
0x180002aab  test    rax, rax
0x180002aae  cmovnz  rcx, rax
0x180002ab2  mov     [r12], rcx
0x180002ab6  xor     r11d, r11d
0x180002ab9  mov     ecx, 1
0x180002abe  jmp     loc_18000290F
0x180002ac3  test    r13, r13
0x180002ac6  jz      loc_18000291C
0x180002acc  lea     rax, [rsp+690h+ReturnLength]
0x180002ad1  mov     [rsp+690h+ReturnLength], 100h
0x180002ad9  mov     edx, ecx; TokenInformationClass
0x180002adb  mov     [rsp+690h+lpUserSid], rax; ReturnLength
0x180002ae0  mov     rcx, r13; TokenHandle
0x180002ae3  lea     r8, [rbp+590h+TokenInformation]; TokenInformation
0x180002ae7  mov     r9d, 100h; TokenInformationLength
0x180002aed  lea     r12, [rbp+590h+TokenInformation]
0x180002af1  call    cs:__imp_GetTokenInformation
0x180002af7  test    eax, eax
0x180002af9  jnz     short loc_180002B5D
0x180002afb  call    cs:__imp_GetLastError
0x180002b01  cmp     eax, 7Ah ; 'z'
0x180002b04  jnz     short loc_180002B61
0x180002b06  mov     edx, [rsp+690h+ReturnLength]; uBytes
0x180002b0a  mov     ecx, 40h ; '@'; uFlags
0x180002b0f  call    cs:__imp_LocalAlloc
0x180002b15  mov     r12, rax
0x180002b18  test    rax, rax
0x180002b1b  jz      short loc_180002B61
0x180002b1d  mov     r9d, [rsp+690h+ReturnLength]; TokenInformationLength
0x180002b22  lea     rax, [rsp+690h+ReturnLength]
0x180002b27  mov     r14d, 1
0x180002b2d  mov     [rsp+690h+lpUserSid], rax; ReturnLength
0x180002b32  mov     edx, r14d; TokenInformationClass
0x180002b35  mov     r8, r12; TokenInformation
0x180002b38  mov     rcx, r13; TokenHandle
0x180002b3b  call    cs:__imp_GetTokenInformation
0x180002b41  movzx   edx, [rsp+690h+var_640]
0x180002b46  xor     r11d, r11d
0x180002b49  mov     ecx, r14d
0x180002b4c  test    eax, eax
0x180002b4e  jz      loc_180002924
0x180002b54  mov     rdi, [r12]
0x180002b58  jmp     loc_180002924
0x180002b5d  mov     rdi, [rbp+590h+TokenInformation]
0x180002b61  movzx   edx, [rsp+690h+var_640]
0x180002b66  xor     r11d, r11d
0x180002b69  mov     r14d, dword ptr [rsp+690h+hMem]
0x180002b6e  mov     ecx, 1
0x180002b73  jmp     loc_180002924
0x180002b78  mov     eax, 4
0x180002b7d  jmp     loc_180002942
0x180002b82  movzx   eax, cx
0x180002b85  jmp     loc_180002942
0x180002b8a  test    r12, r12
0x180002b8d  jz      loc_180002983
0x180002b93  mov     rcx, r12; hMem
0x180002b96  call    cs:__imp_LocalFree
0x180002b9c  jmp     loc_180002983
0x180002ba1  call    cs:__imp_LocalFree
0x180002ba7  jmp     loc_180002991
```
