# SdbpGetMergeRedirectPathInternal

- ea: `0x1408221bc`
- end: `0x14082272e`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1394`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140821790`

## callees

- `0x140428ff0`
- `0x140544600`
- `0x140544740`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x14073cfe8`
- `0x140821c40`
- `0x140821e50`
- `0x1408221bc`
- `0x140827fd0`
- `0x140829198`
- `0x1408c14bc`
- `0x1408c2f88`
- `0x140acb824`
- `0x140acba1c`

## string_xrefs

- `0x1408223e2`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x1408223b8`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x140822374`: `StagedDelete_`
- `0x1408222de`: `SdbpGetMergeRedirectPathInternal`
- `0x1408223f3`: `SdbpGetMergeRedirectPathInternal`
- `0x1408224f8`: `SdbpGetMergeRedirectPathInternal`
- `0x14082266f`: `Failed to get manifested stub [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, const wchar_t *a4)
{
  __int64 v7; // r12
  const wchar_t *v8; // rdi
  int String; // ebx
  __int64 FileNamePart; // rax
  HANDLE v12; // rcx
  const wchar_t *v13; // r13
  const wchar_t *i; // rdi
  NTSTATUS v15; // eax
  const char *v16; // r9
  int v17; // r8d
  __int64 v18; // r14
  const wchar_t *v19; // rdi
  int Key; // eax
  const char *v21; // r9
  int v22; // r8d
  HANDLE v23; // rdi
  unsigned int v24; // r14d
  int UInt32; // eax
  STRSAFE_PCNZWCH v26; // r14
  NTSTATUS v27; // eax
  int v28; // eax
  int FileTimestamp; // eax
  int v30; // eax
  int ManifestedMergeStubAlloc; // eax
  int v32; // eax
  __int64 v33; // [rsp+20h] [rbp-89h]
  __int64 v34; // [rsp+20h] [rbp-89h]
  __int64 v35; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-71h] BYREF
  const wchar_t *v37; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-59h] BYREF
  wchar_t *Str1; // [rsp+58h] [rbp-51h] BYREF
  int v41; // [rsp+60h] [rbp-49h]
  size_t pcchLength; // [rsp+68h] [rbp-41h] BYREF
  __int64 v43; // [rsp+70h] [rbp-39h] BYREF
  __int64 v44; // [rsp+78h] [rbp-31h] BYREF
  size_t v45; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v46; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v47; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v48; // [rsp+98h] [rbp-11h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+A0h] [rbp-9h]
  _QWORD *v50; // [rsp+A8h] [rbp-1h]
  wchar_t Str2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v50 = a1;
  psz = a4;
  v41 = a3;
  v36 = 0;
  Handle = 0;
  v7 = 0;
  Str1 = 0;
  v8 = 0;
  v45 = 0;
  pcchLength = 0;
  v38 = 0;
  v43 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v35 = 0;
  v44 = 0;
  v37 = 0;
  wcscpy(Str2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  String = -1073741772;
  FileNamePart = AslPathGetFileNamePart(a4);
  v13 = (const wchar_t *)FileNamePart;
  if ( (const wchar_t *)FileNamePart != a4 )
  {
    for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
    {
      if ( i < a4 )
        goto LABEL_16;
      if ( (*i == 92 || *i == 47) && !wcsnicmp(i, Str2, 0xAu) )
        break;
    }
    v15 = RtlStringCchLengthW(v13, 0x7FFFFFFFu, &pcchLength);
    String = v15;
    if ( v15 < 0 )
    {
      v16 = "RtlStringCchLengthW failed [%x]";
      v17 = 1864;
LABEL_15:
      LODWORD(v33) = v15;
      AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v17, (_DWORD)v16, v33);
LABEL_16:
      v8 = v37;
      goto LABEL_17;
    }
    if ( a3 )
    {
      v15 = SdbpSafeAllocAndConcatW(&v37, L"StagedDelete_", 13, v13, pcchLength);
      String = v15;
      if ( v15 < 0 )
      {
        v16 = "Failed to alloc and cat file to prefix [%x]";
        v17 = 1876;
        goto LABEL_15;
      }
      v19 = v37;
    }
    else
    {
      v19 = v13;
    }
    Key = AslRegistryGetKey(
            &Handle,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
            2147483904LL,
            1);
    String = Key;
    if ( Key >= 0 )
    {
      String = AslRegistryGetString(&Str1, Handle, v19);
      if ( String >= 0 )
      {
        if ( wcsicmp(Str1, v13) )
        {
          if ( a3 && !wcsicmp(Str1, L"__NotRedirected__") && a2 )
          {
            *a2 = 1;
            String = 0;
          }
          else
          {
            Key = SdbpSafeAllocAndConcatW(&v44, L"MergeVer_", 9, v19, 0);
            String = Key;
            if ( Key < 0 )
            {
              v21 = "Failed to alloc and cat file to prefix [%x]";
              v22 = 1927;
              goto LABEL_37;
            }
            v23 = Handle;
            Key = AslRegistryGetUInt32(&v38, Handle, v44);
            String = Key;
            if ( Key == -1073741772 )
            {
              v24 = 0;
            }
            else
            {
              if ( Key < 0 )
              {
                v21 = "Failed to query reg value. [%x]";
                v22 = 1936;
                goto LABEL_37;
              }
              v24 = v38;
            }
            Key = AslRegistryGetUInt32(&v36, v23, L"MergeVer");
            String = Key;
            if ( Key < 0 )
            {
              v21 = "Failed to query reg value. [%x]";
              v22 = 1942;
              goto LABEL_37;
            }
            if ( v36 < v24 )
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                1951,
                (unsigned int)"Merge target is too high of a version, this code might not handle it correctly.");
            UInt32 = AslRegistryGetUInt32(&v36, Handle, L"MinMergeVer");
            String = UInt32;
            if ( UInt32 >= 0 )
            {
              if ( v24 < v36 )
                AslLogCallPrintf(
                  1,
                  (unsigned int)"SdbpGetMergeRedirectPathInternal",
                  1966,
                  (unsigned int)"Merge target is too low of a version, it might not be possible to handle correctly.");
              v26 = psz;
              v27 = RtlStringCchLengthW(psz, 0x7FFFFFFFu, &v45);
              String = v27;
              if ( v27 >= 0 )
              {
                if ( v45 < pcchLength )
                {
                  String = -1073741675;
                  v21 = "RtlSizeTSub failed [%x]";
                  LODWORD(v33) = -1073741675;
                  v22 = 1980;
                  goto LABEL_84;
                }
                v28 = SdbpSafeAllocAndConcatW(&v43, v26, v45 - pcchLength, Str1, 0);
                String = v28;
                if ( v28 >= 0 )
                {
                  v7 = v43;
                  FileTimestamp = SdbpGetFileTimestamp(&v46, v43, 1);
                  String = FileTimestamp;
                  if ( FileTimestamp < 0 )
                  {
                    if ( FileTimestamp != -1073741772 )
                    {
                      LODWORD(v34) = FileTimestamp;
                      AslLogCallPrintf(
                        1,
                        (unsigned int)"SdbpGetMergeRedirectPathInternal",
                        2001,
                        (unsigned int)"Failed to check timestamp [%x]",
                        v34);
                    }
                    goto LABEL_85;
                  }
                  v30 = SdbpGetFileTimestamp(&v47, v26, 0);
                  String = v30;
                  if ( v30 >= 0 )
                  {
                    ManifestedMergeStubAlloc = SdbpGetManifestedMergeStubAlloc(&v35, v13);
                    String = ManifestedMergeStubAlloc;
                    if ( ManifestedMergeStubAlloc == -1073741772 )
                    {
                      v18 = v35;
                    }
                    else
                    {
                      if ( ManifestedMergeStubAlloc < 0 )
                      {
                        LODWORD(v34) = ManifestedMergeStubAlloc;
                        AslLogCallPrintf(
                          1,
                          (unsigned int)"SdbpGetMergeRedirectPathInternal",
                          2026,
                          (unsigned int)"Failed to get manifested stub [%x]",
                          v34);
                        goto LABEL_85;
                      }
                      v18 = v35;
                      v32 = SdbpGetFileTimestamp(&v48, v35, 0);
                      String = v32;
                      if ( v32 < 0 )
                      {
                        LODWORD(v34) = v32;
                        AslLogCallPrintf(
                          1,
                          (unsigned int)"SdbpGetMergeRedirectPathInternal",
                          2036,
                          (unsigned int)"Failed to check timestamp [%x]",
                          v34);
LABEL_86:
                        v12 = Handle;
                        if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                          ZwClose(Handle);
                        v8 = v37;
                        goto LABEL_18;
                      }
                    }
                    if ( v46 < v47 || v46 < v48 )
                    {
                      String = -1073741772;
                    }
                    else
                    {
                      *v50 = v7;
                      if ( a2 && v41 )
                        *a2 = 1;
                      v7 = 0;
                      String = 0;
                    }
                    goto LABEL_86;
                  }
                  LODWORD(v34) = v30;
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"SdbpGetMergeRedirectPathInternal",
                    2012,
                    (unsigned int)"Failed to check timestamp [%x]",
                    v34);
                }
                else
                {
                  LODWORD(v34) = v28;
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"SdbpGetMergeRedirectPathInternal",
                    1990,
                    (unsigned int)"Failed to alloc and cat file to prefix [%x]",
                    v34);
                  v7 = v43;
                }
              }
              else
              {
                LODWORD(v33) = v27;
                AslLogCallPrintf(
                  1,
                  (unsigned int)"SdbpGetMergeRedirectPathInternal",
                  1973,
                  (unsigned int)"RtlStringCchLengthW failed [%x]",
                  v33);
              }
            }
            else
            {
              LODWORD(v33) = UInt32;
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                1957,
                (unsigned int)"Failed to query reg value. [%x]",
                v33);
            }
          }
        }
        else
        {
          String = -1073741772;
        }
      }
    }
    else if ( Key != -1073741772 )
    {
      v21 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
      v22 = 1893;
LABEL_37:
      LODWORD(v33) = Key;
LABEL_84:
      AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v22, (_DWORD)v21, v33);
    }
LABEL_85:
    v18 = v35;
    goto LABEL_86;
  }
LABEL_17:
  v18 = v35;
LABEL_18:
  if ( Str1 )
    AslFree(v12, Str1);
  if ( v7 )
    AslFree(v12, v7);
  if ( v18 )
    AslFree(v12, v18);
  if ( v44 )
    AslFree(v12, v44);
  if ( v8 )
    AslFree(v12, v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1408221bc  mov     [rsp-8+arg_10], rbx
0x1408221c1  push    rbp
0x1408221c2  push    rsi
0x1408221c3  push    rdi
0x1408221c4  push    r12
0x1408221c6  push    r13
0x1408221c8  push    r14
0x1408221ca  push    r15
0x1408221cc  lea     rbp, [rsp-27h]
0x1408221d1  sub     rsp, 0D0h
0x1408221d8  mov     rax, cs:__security_cookie
0x1408221df  xor     rax, rsp
0x1408221e2  mov     [rbp+57h+var_38], rax
0x1408221e6  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x1408221ed  mov     rax, rcx
0x1408221f0  mov     [rbp+57h+var_58], rcx
0x1408221f4  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x1408221fc  xor     ecx, ecx
0x1408221fe  mov     [rbp+57h+psz], r9
0x140822202  mov     rsi, r9
0x140822205  mov     [rbp+57h+var_A0], r8d
0x140822209  mov     r14d, r8d
0x14082220c  mov     [rbp+57h+var_C8], ecx
0x14082220f  mov     r15, rdx
0x140822212  mov     [rbp+57h+Handle], rcx
0x140822216  mov     r12d, ecx
0x140822219  mov     [rbp+57h+Str1], rcx
0x14082221d  mov     edi, ecx
0x14082221f  mov     [rbp+57h+var_80], rcx
0x140822223  mov     [rbp+57h+pcchLength], rcx
0x140822227  mov     [rbp+57h+var_B8], ecx
0x14082222a  mov     [rbp+57h+var_90], rcx
0x14082222e  mov     [rbp+57h+var_78], rcx
0x140822232  mov     [rbp+57h+var_70], rcx
0x140822236  mov     [rbp+57h+var_68], rcx
0x14082223a  mov     [rbp+57h+var_D0], rcx
0x14082223e  mov     [rbp+57h+var_88], rcx
0x140822242  mov     [rbp+57h+var_C0], rcx
0x140822246  movups  xmmword ptr [rbp+57h+Str2], xmm0
0x14082224a  movsd   qword ptr [rbp+57h+Str2+0Eh], xmm1
0x14082224f  test    rax, rax
0x140822252  jnz     short loc_14082225E
0x140822254  mov     eax, 0C00000EFh
0x140822259  jmp     loc_140822343
0x14082225e  mov     [rax], rcx
0x140822261  test    r15, r15
0x140822264  jz      short loc_14082226D
0x140822266  test    r14d, r14d
0x140822269  jz      short loc_14082226D
0x14082226b  mov     [rdx], ecx
0x14082226d  mov     rcx, rsi
0x140822270  mov     ebx, 0C0000034h
0x140822275  call    AslPathGetFileNamePart
0x14082227a  mov     r13, rax
0x14082227d  cmp     rax, rsi
0x140822280  jz      short loc_1408222F7
0x140822282  lea     rdi, [rax-4]
0x140822286  cmp     rdi, rsi
0x140822289  jb      short loc_1408222F3
0x14082228b  movzx   eax, word ptr [rdi]
0x14082228e  cmp     ax, 5Ch ; '\'
0x140822292  jz      short loc_14082229A
0x140822294  cmp     ax, 2Fh ; '/'
0x140822298  jnz     short loc_1408222B0
0x14082229a  mov     r8d, 0Ah; MaxCount
0x1408222a0  lea     rdx, [rbp+57h+Str2]; Str2
0x1408222a4  mov     rcx, rdi; Str1
0x1408222a7  call    _wcsnicmp
0x1408222ac  test    eax, eax
0x1408222ae  jz      short loc_1408222B6
0x1408222b0  sub     rdi, 2
0x1408222b4  jmp     short loc_140822286
0x1408222b6  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x1408222ba  mov     edx, 7FFFFFFFh; cchMax
0x1408222bf  mov     rcx, r13; psz
0x1408222c2  call    RtlStringCchLengthW
0x1408222c7  mov     ebx, eax
0x1408222c9  test    eax, eax
0x1408222cb  jns     loc_14082236B
0x1408222d1  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x1408222d8  mov     r8d, 748h
0x1408222de  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1408222e5  mov     dword ptr [rsp+100h+var_E0], eax
0x1408222e9  mov     ecx, 1
0x1408222ee  call    AslLogCallPrintf
0x1408222f3  mov     rdi, [rbp+57h+var_C0]
0x1408222f7  mov     r14, [rbp+57h+var_D0]
0x1408222fb  mov     rdx, [rbp+57h+Str1]
0x1408222ff  test    rdx, rdx
0x140822302  jz      short loc_140822309
0x140822304  call    AslFree
0x140822309  test    r12, r12
0x14082230c  jz      short loc_140822316
0x14082230e  mov     rdx, r12
0x140822311  call    AslFree
0x140822316  test    r14, r14
0x140822319  jz      short loc_140822323
0x14082231b  mov     rdx, r14
0x14082231e  call    AslFree
0x140822323  mov     rax, [rbp+57h+var_88]
0x140822327  test    rax, rax
0x14082232a  jz      short loc_140822334
0x14082232c  mov     rdx, rax
0x14082232f  call    AslFree
0x140822334  test    rdi, rdi
0x140822337  jz      short loc_140822341
0x140822339  mov     rdx, rdi
0x14082233c  call    AslFree
0x140822341  mov     eax, ebx
0x140822343  mov     rcx, [rbp+57h+var_38]
0x140822347  xor     rcx, rsp; StackCookie
0x14082234a  call    __security_check_cookie
0x14082234f  mov     rbx, [rsp+100h+arg_10]
0x140822357  add     rsp, 0D0h
0x14082235e  pop     r15
0x140822360  pop     r14
0x140822362  pop     r13
0x140822364  pop     r12
0x140822366  pop     rdi
0x140822367  pop     rsi
0x140822368  pop     rbp
0x140822369  retn
0x14082236b  test    r14d, r14d
0x14082236e  jz      short loc_1408223B0
0x140822370  mov     rax, [rbp+57h+pcchLength]
0x140822374  lea     rdx, aStageddelete; "StagedDelete_"
0x14082237b  mov     r9, r13
0x14082237e  mov     [rsp+100h+var_E0], rax
0x140822383  mov     r8d, 0Dh
0x140822389  lea     rcx, [rbp+57h+var_C0]
0x14082238d  call    SdbpSafeAllocAndConcatW
0x140822392  mov     ebx, eax
0x140822394  test    eax, eax
0x140822396  jns     short loc_1408223AA
0x140822398  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x14082239f  mov     r8d, 754h
0x1408223a5  jmp     loc_1408222DE
0x1408223aa  mov     rdi, [rbp+57h+var_C0]
0x1408223ae  jmp     short loc_1408223B3
0x1408223b0  mov     rdi, r13
0x1408223b3  mov     esi, 1
0x1408223b8  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1408223bf  mov     r9d, esi
0x1408223c2  lea     rcx, [rbp+57h+Handle]
0x1408223c6  mov     r8d, 80000100h
0x1408223cc  call    AslRegistryGetKey
0x1408223d1  mov     ebx, eax
0x1408223d3  test    eax, eax
0x1408223d5  jns     short loc_1408223FF
0x1408223d7  cmp     eax, 0C0000034h
0x1408223dc  jz      loc_14082270E
0x1408223e2  lea     r9, aAslregistryget_4; "AslRegistryGetKey failed to open SdbUpd"...
0x1408223e9  mov     r8d, 765h
0x1408223ef  mov     dword ptr [rsp+100h+var_E0], eax
0x1408223f3  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1408223fa  jmp     loc_140822707
0x1408223ff  mov     rdx, [rbp+57h+Handle]
0x140822403  lea     rcx, [rbp+57h+Str1]
0x140822407  mov     r8, rdi
0x14082240a  call    AslRegistryGetString
0x14082240f  mov     ebx, eax
0x140822411  test    eax, eax
0x140822413  js      loc_14082270E
0x140822419  mov     rcx, [rbp+57h+Str1]; Str1
0x14082241d  mov     rdx, r13; Str2
0x140822420  call    _wcsicmp
0x140822425  test    eax, eax
0x140822427  jnz     short loc_140822433
0x140822429  mov     ebx, 0C0000034h
0x14082242e  jmp     loc_14082270E
0x140822433  test    r14d, r14d
0x140822436  jz      short loc_14082245B
0x140822438  mov     rcx, [rbp+57h+Str1]; Str1
0x14082243c  lea     rdx, aNotredirected; "__NotRedirected__"
0x140822443  call    _wcsicmp
0x140822448  test    eax, eax
0x14082244a  jnz     short loc_14082245B
0x14082244c  test    r15, r15
0x14082244f  jz      short loc_14082245B
0x140822451  mov     [r15], esi
0x140822454  xor     ebx, ebx
0x140822456  jmp     loc_14082270E
0x14082245b  mov     r9, rdi
0x14082245e  mov     [rsp+100h+var_E0], r12
0x140822463  mov     r8d, 9
0x140822469  lea     rdx, aMergever_0; "MergeVer_"
0x140822470  lea     rcx, [rbp+57h+var_88]
0x140822474  call    SdbpSafeAllocAndConcatW
0x140822479  mov     ebx, eax
0x14082247b  test    eax, eax
0x14082247d  jns     short loc_140822491
0x14082247f  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x140822486  mov     r8d, 787h
0x14082248c  jmp     loc_1408223EF
0x140822491  mov     rdi, [rbp+57h+Handle]
0x140822495  lea     rcx, [rbp+57h+var_B8]
0x140822499  mov     r8, [rbp+57h+var_88]
0x14082249d  mov     rdx, rdi
0x1408224a0  call    AslRegistryGetUInt32
0x1408224a5  mov     ebx, eax
0x1408224a7  cmp     eax, 0C0000034h
0x1408224ac  jnz     short loc_1408224B3
0x1408224ae  xor     r14d, r14d
0x1408224b1  jmp     short loc_1408224CD
0x1408224b3  test    eax, eax
0x1408224b5  jns     short loc_1408224C9
0x1408224b7  lea     r9, aFailedToQueryR; "Failed to query reg value. [%x]"
0x1408224be  mov     r8d, 790h
0x1408224c4  jmp     loc_1408223EF
0x1408224c9  mov     r14d, [rbp+57h+var_B8]
0x1408224cd  lea     r8, aMergever; "MergeVer"
0x1408224d4  mov     rdx, rdi
0x1408224d7  lea     rcx, [rbp+57h+var_C8]
0x1408224db  call    AslRegistryGetUInt32
0x1408224e0  mov     ebx, eax
0x1408224e2  test    eax, eax
0x1408224e4  jns     short loc_1408224F8
0x1408224e6  lea     r9, aFailedToQueryR; "Failed to query reg value. [%x]"
0x1408224ed  mov     r8d, 796h
0x1408224f3  jmp     loc_1408223EF
0x1408224f8  lea     rdi, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1408224ff  cmp     [rbp+57h+var_C8], r14d
0x140822503  jnb     short loc_14082251C
0x140822505  lea     r9, aMergeTargetIsT; "Merge target is too high of a version, "...
0x14082250c  mov     r8d, 79Fh
0x140822512  mov     rdx, rdi
0x140822515  mov     ecx, esi
0x140822517  call    AslLogCallPrintf
0x14082251c  mov     rdx, [rbp+57h+Handle]
0x140822520  lea     r8, aMinmergever; "MinMergeVer"
0x140822527  lea     rcx, [rbp+57h+var_C8]
0x14082252b  call    AslRegistryGetUInt32
0x140822530  mov     ebx, eax
0x140822532  test    eax, eax
0x140822534  jns     short loc_14082254C
0x140822536  mov     dword ptr [rsp+100h+var_E0], eax
0x14082253a  lea     r9, aFailedToQueryR; "Failed to query reg value. [%x]"
0x140822541  mov     r8d, 7A5h
0x140822547  jmp     loc_140822704
0x14082254c  cmp     r14d, [rbp+57h+var_C8]
0x140822550  jnb     short loc_140822569
0x140822552  lea     r9, aMergeTargetIsT_0; "Merge target is too low of a version, i"...
0x140822559  mov     r8d, 7AEh
0x14082255f  mov     rdx, rdi
0x140822562  mov     ecx, esi
0x140822564  call    AslLogCallPrintf
0x140822569  mov     r14, [rbp+57h+psz]
0x14082256d  lea     r8, [rbp+57h+var_80]; pcchLength
0x140822571  mov     rcx, r14; psz
0x140822574  mov     edx, 7FFFFFFFh; cchMax
0x140822579  call    RtlStringCchLengthW
0x14082257e  mov     ebx, eax
0x140822580  test    eax, eax
0x140822582  jns     short loc_14082259A
0x140822584  mov     dword ptr [rsp+100h+var_E0], eax
0x140822588  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x14082258f  mov     r8d, 7B5h
0x140822595  jmp     loc_140822704
0x14082259a  mov     r8, [rbp+57h+var_80]
0x14082259e  mov     rax, [rbp+57h+pcchLength]
0x1408225a2  cmp     r8, rax
0x1408225a5  jb      loc_1408226EE
0x1408225ab  mov     r9, [rbp+57h+Str1]
0x1408225af  lea     rcx, [rbp+57h+var_90]
0x1408225b3  sub     r8, rax
0x1408225b6  mov     [rsp+100h+var_E0], r12
0x1408225bb  mov     rdx, r14
0x1408225be  call    SdbpSafeAllocAndConcatW
0x1408225c3  mov     ebx, eax
0x1408225c5  test    eax, eax
0x1408225c7  jns     short loc_1408225ED
0x1408225c9  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x1408225d0  mov     dword ptr [rsp+100h+var_E0], eax
0x1408225d4  mov     r8d, 7C6h
0x1408225da  mov     rdx, rdi
0x1408225dd  mov     ecx, esi
0x1408225df  call    AslLogCallPrintf
0x1408225e4  mov     r12, [rbp+57h+var_90]
0x1408225e8  jmp     loc_14082270E
0x1408225ed  mov     r12, [rbp+57h+var_90]
0x1408225f1  lea     rcx, [rbp+57h+var_78]
0x1408225f5  mov     rdx, r12
0x1408225f8  mov     r8d, esi
0x1408225fb  call    SdbpGetFileTimestamp
0x140822600  mov     ebx, eax
0x140822602  test    eax, eax
0x140822604  jns     short loc_140822627
0x140822606  cmp     eax, 0C0000034h
0x14082260b  jz      loc_14082270E
0x140822611  mov     dword ptr [rsp+100h+var_E0], eax
0x140822615  lea     r9, aFailedToCheckT; "Failed to check timestamp [%x]"
0x14082261c  mov     r8d, 7D1h
0x140822622  jmp     loc_140822704
0x140822627  xor     r8d, r8d
0x14082262a  lea     rcx, [rbp+57h+var_70]
0x14082262e  mov     rdx, r14
0x140822631  call    SdbpGetFileTimestamp
0x140822636  mov     ebx, eax
0x140822638  test    eax, eax
0x14082263a  jns     short loc_140822652
  ... truncated ...
```
