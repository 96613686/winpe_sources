# SdbpGetMergeRedirectPathInternal

- ea: `0x14082024c`
- end: `0x1408207be`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1394`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *, int, const wchar_t *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14081f820`

## callees

- `0x140412430`
- `0x14053cf40`
- `0x14053d080`
- `0x1406d9d70`
- `0x1406daa70`
- `0x140738828`
- `0x14081fcd0`
- `0x14081fee0`
- `0x14082024c`
- `0x140826060`
- `0x140827228`
- `0x14097b68c`
- `0x14097d158`
- `0x140ac65d4`
- `0x140ac67cc`

## string_xrefs

- `0x1408206ff`: `Failed to get manifested stub [%x]`
- `0x140820472`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x140820448`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x140820404`: `StagedDelete_`
- `0x14082036e`: `SdbpGetMergeRedirectPathInternal`
- `0x140820483`: `SdbpGetMergeRedirectPathInternal`
- `0x140820588`: `SdbpGetMergeRedirectPathInternal`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, const wchar_t *a4)
{
  __int64 v7; // r12
  const WCHAR *v8; // rdi
  int String; // ebx
  __int64 FileNamePart; // rax
  HANDLE v12; // rcx
  const wchar_t *v13; // r13
  const wchar_t *i; // rdi
  const char *v15; // r9
  int v16; // r8d
  __int64 v17; // r14
  const WCHAR *v18; // rdi
  int Key; // eax
  const char *v20; // r9
  int v21; // r8d
  HANDLE v22; // rdi
  int UInt32; // eax
  unsigned int v24; // r14d
  STRSAFE_PCNZWCH v25; // r14
  int FileTimestamp; // eax
  int ManifestedMergeStubAlloc; // eax
  __int64 v28; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-71h] BYREF
  const WCHAR *v30; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v31; // [rsp+48h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-59h] BYREF
  wchar_t *Str1; // [rsp+58h] [rbp-51h] BYREF
  int v34; // [rsp+60h] [rbp-49h]
  size_t pcchLength; // [rsp+68h] [rbp-41h] BYREF
  __int64 v36; // [rsp+70h] [rbp-39h] BYREF
  __int64 v37; // [rsp+78h] [rbp-31h] BYREF
  size_t v38; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v39; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v40; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v41; // [rsp+98h] [rbp-11h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+A0h] [rbp-9h]
  _QWORD *v43; // [rsp+A8h] [rbp-1h]
  wchar_t Str2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v43 = a1;
  psz = a4;
  v34 = a3;
  v29 = 0;
  Handle = 0;
  v7 = 0;
  Str1 = 0;
  v8 = 0;
  v38 = 0;
  pcchLength = 0;
  v31 = 0;
  v36 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v28 = 0;
  v37 = 0;
  v30 = 0;
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
    String = RtlStringCchLengthW(v13, 0x7FFFFFFFu, &pcchLength);
    if ( String < 0 )
    {
      v15 = "RtlStringCchLengthW failed [%x]";
      v16 = 1866;
LABEL_15:
      AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v16, (_DWORD)v15);
LABEL_16:
      v8 = v30;
      goto LABEL_17;
    }
    if ( a3 )
    {
      String = SdbpSafeAllocAndConcatW(&v30, L"StagedDelete_", 13, v13, pcchLength);
      if ( String < 0 )
      {
        v15 = "Failed to alloc and cat file to prefix [%x]";
        v16 = 1878;
        goto LABEL_15;
      }
      v18 = v30;
    }
    else
    {
      v18 = v13;
    }
    Key = AslRegistryGetKey(
            &Handle,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
            0x80000100,
            1);
    String = Key;
    if ( Key >= 0 )
    {
      String = AslRegistryGetString(&Str1, Handle, v18);
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
            String = SdbpSafeAllocAndConcatW(&v37, L"MergeVer_", 9, v18, 0);
            if ( String < 0 )
            {
              v20 = "Failed to alloc and cat file to prefix [%x]";
              v21 = 1929;
              goto LABEL_83;
            }
            v22 = Handle;
            UInt32 = AslRegistryGetUInt32(&v31, Handle, v37);
            String = UInt32;
            if ( UInt32 == -1073741772 )
            {
              v24 = 0;
            }
            else
            {
              if ( UInt32 < 0 )
              {
                v20 = "Failed to query reg value. [%x]";
                v21 = 1938;
                goto LABEL_83;
              }
              v24 = v31;
            }
            String = AslRegistryGetUInt32(&v29, v22, L"MergeVer");
            if ( String < 0 )
            {
              v20 = "Failed to query reg value. [%x]";
              v21 = 1944;
              goto LABEL_83;
            }
            if ( v29 < v24 )
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                1953,
                (unsigned int)"Merge target is too high of a version, this code might not handle it correctly.");
            String = AslRegistryGetUInt32(&v29, Handle, L"MinMergeVer");
            if ( String < 0 )
            {
              v20 = "Failed to query reg value. [%x]";
              v21 = 1959;
              goto LABEL_83;
            }
            if ( v24 < v29 )
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                1968,
                (unsigned int)"Merge target is too low of a version, it might not be possible to handle correctly.");
            v25 = psz;
            String = RtlStringCchLengthW(psz, 0x7FFFFFFFu, &v38);
            if ( String < 0 )
            {
              v20 = "RtlStringCchLengthW failed [%x]";
              v21 = 1975;
              goto LABEL_83;
            }
            if ( v38 < pcchLength )
            {
              String = -1073741675;
              v20 = "RtlSizeTSub failed [%x]";
              v21 = 1982;
              goto LABEL_83;
            }
            String = SdbpSafeAllocAndConcatW(&v36, v25, v38 - pcchLength, Str1, 0);
            if ( String >= 0 )
            {
              v7 = v36;
              FileTimestamp = SdbpGetFileTimestamp(&v39, v36, 1);
              String = FileTimestamp;
              if ( FileTimestamp >= 0 )
              {
                String = SdbpGetFileTimestamp(&v40, v25, 0);
                if ( String >= 0 )
                {
                  ManifestedMergeStubAlloc = SdbpGetManifestedMergeStubAlloc(&v28, v13);
                  String = ManifestedMergeStubAlloc;
                  if ( ManifestedMergeStubAlloc == -1073741772 )
                  {
                    v17 = v28;
                  }
                  else
                  {
                    if ( ManifestedMergeStubAlloc < 0 )
                    {
                      v20 = "Failed to get manifested stub [%x]";
                      v21 = 2028;
                      goto LABEL_83;
                    }
                    v17 = v28;
                    String = SdbpGetFileTimestamp(&v41, v28, 0);
                    if ( String < 0 )
                    {
                      AslLogCallPrintf(
                        1,
                        (unsigned int)"SdbpGetMergeRedirectPathInternal",
                        2038,
                        (unsigned int)"Failed to check timestamp [%x]");
LABEL_85:
                      v12 = Handle;
                      if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                        ZwClose(Handle);
                      v8 = v30;
                      goto LABEL_18;
                    }
                  }
                  if ( v39 < v40 || v39 < v41 )
                  {
                    String = -1073741772;
                  }
                  else
                  {
                    *v43 = v7;
                    if ( a2 && v34 )
                      *a2 = 1;
                    v7 = 0;
                    String = 0;
                  }
                  goto LABEL_85;
                }
                v20 = "Failed to check timestamp [%x]";
                v21 = 2014;
LABEL_83:
                AslLogCallPrintf(1, (unsigned int)"SdbpGetMergeRedirectPathInternal", v21, (_DWORD)v20);
                goto LABEL_84;
              }
              if ( FileTimestamp != -1073741772 )
              {
                v20 = "Failed to check timestamp [%x]";
                v21 = 2003;
                goto LABEL_83;
              }
            }
            else
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                1992,
                (unsigned int)"Failed to alloc and cat file to prefix [%x]");
              v7 = v36;
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
      v20 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
      v21 = 1895;
      goto LABEL_83;
    }
LABEL_84:
    v17 = v28;
    goto LABEL_85;
  }
LABEL_17:
  v17 = v28;
LABEL_18:
  if ( Str1 )
    AslFree(v12, Str1);
  if ( v7 )
    AslFree(v12, v7);
  if ( v17 )
    AslFree(v12, v17);
  if ( v37 )
    AslFree(v12, v37);
  if ( v8 )
    AslFree(v12, v8);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x14082024c  mov     [rsp-8+arg_10], rbx
0x140820251  push    rbp
0x140820252  push    rsi
0x140820253  push    rdi
0x140820254  push    r12
0x140820256  push    r13
0x140820258  push    r14
0x14082025a  push    r15
0x14082025c  lea     rbp, [rsp-27h]
0x140820261  sub     rsp, 0D0h
0x140820268  mov     rax, cs:__security_cookie
0x14082026f  xor     rax, rsp
0x140820272  mov     [rbp+57h+var_38], rax
0x140820276  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x14082027d  mov     rax, rcx
0x140820280  mov     [rbp+57h+var_58], rcx
0x140820284  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x14082028c  xor     ecx, ecx
0x14082028e  mov     [rbp+57h+psz], r9
0x140820292  mov     rsi, r9
0x140820295  mov     [rbp+57h+var_A0], r8d
0x140820299  mov     r14d, r8d
0x14082029c  mov     [rbp+57h+var_C8], ecx
0x14082029f  mov     r15, rdx
0x1408202a2  mov     [rbp+57h+Handle], rcx
0x1408202a6  mov     r12d, ecx
0x1408202a9  mov     [rbp+57h+Str1], rcx
0x1408202ad  mov     edi, ecx
0x1408202af  mov     [rbp+57h+var_80], rcx
0x1408202b3  mov     [rbp+57h+pcchLength], rcx
0x1408202b7  mov     [rbp+57h+var_B8], ecx
0x1408202ba  mov     [rbp+57h+var_90], rcx
0x1408202be  mov     [rbp+57h+var_78], rcx
0x1408202c2  mov     [rbp+57h+var_70], rcx
0x1408202c6  mov     [rbp+57h+var_68], rcx
0x1408202ca  mov     [rbp+57h+var_D0], rcx
0x1408202ce  mov     [rbp+57h+var_88], rcx
0x1408202d2  mov     [rbp+57h+var_C0], rcx
0x1408202d6  movups  xmmword ptr [rbp+57h+Str2], xmm0
0x1408202da  movsd   qword ptr [rbp+57h+Str2+0Eh], xmm1
0x1408202df  test    rax, rax
0x1408202e2  jnz     short loc_1408202EE
0x1408202e4  mov     eax, 0C00000EFh
0x1408202e9  jmp     loc_1408203D3
0x1408202ee  mov     [rax], rcx
0x1408202f1  test    r15, r15
0x1408202f4  jz      short loc_1408202FD
0x1408202f6  test    r14d, r14d
0x1408202f9  jz      short loc_1408202FD
0x1408202fb  mov     [rdx], ecx
0x1408202fd  mov     rcx, rsi
0x140820300  mov     ebx, 0C0000034h
0x140820305  call    AslPathGetFileNamePart
0x14082030a  mov     r13, rax
0x14082030d  cmp     rax, rsi
0x140820310  jz      short loc_140820387
0x140820312  lea     rdi, [rax-4]
0x140820316  cmp     rdi, rsi
0x140820319  jb      short loc_140820383
0x14082031b  movzx   eax, word ptr [rdi]
0x14082031e  cmp     ax, 5Ch ; '\'
0x140820322  jz      short loc_14082032A
0x140820324  cmp     ax, 2Fh ; '/'
0x140820328  jnz     short loc_140820340
0x14082032a  mov     r8d, 0Ah; MaxCount
0x140820330  lea     rdx, [rbp+57h+Str2]; Str2
0x140820334  mov     rcx, rdi; Str1
0x140820337  call    _wcsnicmp
0x14082033c  test    eax, eax
0x14082033e  jz      short loc_140820346
0x140820340  sub     rdi, 2
0x140820344  jmp     short loc_140820316
0x140820346  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x14082034a  mov     edx, 7FFFFFFFh; cchMax
0x14082034f  mov     rcx, r13; psz
0x140820352  call    RtlStringCchLengthW
0x140820357  mov     ebx, eax
0x140820359  test    eax, eax
0x14082035b  jns     loc_1408203FB
0x140820361  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x140820368  mov     r8d, 74Ah
0x14082036e  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x140820375  mov     dword ptr [rsp+100h+var_E0], eax
0x140820379  mov     ecx, 1
0x14082037e  call    AslLogCallPrintf
0x140820383  mov     rdi, [rbp+57h+var_C0]
0x140820387  mov     r14, [rbp+57h+var_D0]
0x14082038b  mov     rdx, [rbp+57h+Str1]
0x14082038f  test    rdx, rdx
0x140820392  jz      short loc_140820399
0x140820394  call    AslFree
0x140820399  test    r12, r12
0x14082039c  jz      short loc_1408203A6
0x14082039e  mov     rdx, r12
0x1408203a1  call    AslFree
0x1408203a6  test    r14, r14
0x1408203a9  jz      short loc_1408203B3
0x1408203ab  mov     rdx, r14
0x1408203ae  call    AslFree
0x1408203b3  mov     rax, [rbp+57h+var_88]
0x1408203b7  test    rax, rax
0x1408203ba  jz      short loc_1408203C4
0x1408203bc  mov     rdx, rax
0x1408203bf  call    AslFree
0x1408203c4  test    rdi, rdi
0x1408203c7  jz      short loc_1408203D1
0x1408203c9  mov     rdx, rdi
0x1408203cc  call    AslFree
0x1408203d1  mov     eax, ebx
0x1408203d3  mov     rcx, [rbp+57h+var_38]
0x1408203d7  xor     rcx, rsp; StackCookie
0x1408203da  call    __security_check_cookie
0x1408203df  mov     rbx, [rsp+100h+arg_10]
0x1408203e7  add     rsp, 0D0h
0x1408203ee  pop     r15
0x1408203f0  pop     r14
0x1408203f2  pop     r13
0x1408203f4  pop     r12
0x1408203f6  pop     rdi
0x1408203f7  pop     rsi
0x1408203f8  pop     rbp
0x1408203f9  retn
0x1408203fb  test    r14d, r14d
0x1408203fe  jz      short loc_140820440
0x140820400  mov     rax, [rbp+57h+pcchLength]
0x140820404  lea     rdx, aStageddelete; "StagedDelete_"
0x14082040b  mov     r9, r13
0x14082040e  mov     [rsp+100h+var_E0], rax
0x140820413  mov     r8d, 0Dh
0x140820419  lea     rcx, [rbp+57h+var_C0]
0x14082041d  call    SdbpSafeAllocAndConcatW
0x140820422  mov     ebx, eax
0x140820424  test    eax, eax
0x140820426  jns     short loc_14082043A
0x140820428  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x14082042f  mov     r8d, 756h
0x140820435  jmp     loc_14082036E
0x14082043a  mov     rdi, [rbp+57h+var_C0]
0x14082043e  jmp     short loc_140820443
0x140820440  mov     rdi, r13
0x140820443  mov     esi, 1
0x140820448  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x14082044f  mov     r9d, esi
0x140820452  lea     rcx, [rbp+57h+Handle]
0x140820456  mov     r8d, 80000100h
0x14082045c  call    AslRegistryGetKey
0x140820461  mov     ebx, eax
0x140820463  test    eax, eax
0x140820465  jns     short loc_14082048F
0x140820467  cmp     eax, 0C0000034h
0x14082046c  jz      loc_14082079E
0x140820472  lea     r9, aAslregistryget_4; "AslRegistryGetKey failed to open SdbUpd"...
0x140820479  mov     r8d, 767h
0x14082047f  mov     dword ptr [rsp+100h+var_E0], eax
0x140820483  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x14082048a  jmp     loc_140820797
0x14082048f  mov     rdx, [rbp+57h+Handle]
0x140820493  lea     rcx, [rbp+57h+Str1]
0x140820497  mov     r8, rdi
0x14082049a  call    AslRegistryGetString
0x14082049f  mov     ebx, eax
0x1408204a1  test    eax, eax
0x1408204a3  js      loc_14082079E
0x1408204a9  mov     rcx, [rbp+57h+Str1]; Str1
0x1408204ad  mov     rdx, r13; Str2
0x1408204b0  call    _wcsicmp
0x1408204b5  test    eax, eax
0x1408204b7  jnz     short loc_1408204C3
0x1408204b9  mov     ebx, 0C0000034h
0x1408204be  jmp     loc_14082079E
0x1408204c3  test    r14d, r14d
0x1408204c6  jz      short loc_1408204EB
0x1408204c8  mov     rcx, [rbp+57h+Str1]; Str1
0x1408204cc  lea     rdx, aNotredirected; "__NotRedirected__"
0x1408204d3  call    _wcsicmp
0x1408204d8  test    eax, eax
0x1408204da  jnz     short loc_1408204EB
0x1408204dc  test    r15, r15
0x1408204df  jz      short loc_1408204EB
0x1408204e1  mov     [r15], esi
0x1408204e4  xor     ebx, ebx
0x1408204e6  jmp     loc_14082079E
0x1408204eb  mov     r9, rdi
0x1408204ee  mov     [rsp+100h+var_E0], r12
0x1408204f3  mov     r8d, 9
0x1408204f9  lea     rdx, aMergever_0; "MergeVer_"
0x140820500  lea     rcx, [rbp+57h+var_88]
0x140820504  call    SdbpSafeAllocAndConcatW
0x140820509  mov     ebx, eax
0x14082050b  test    eax, eax
0x14082050d  jns     short loc_140820521
0x14082050f  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x140820516  mov     r8d, 789h
0x14082051c  jmp     loc_14082047F
0x140820521  mov     rdi, [rbp+57h+Handle]
0x140820525  lea     rcx, [rbp+57h+var_B8]
0x140820529  mov     r8, [rbp+57h+var_88]
0x14082052d  mov     rdx, rdi
0x140820530  call    AslRegistryGetUInt32
0x140820535  mov     ebx, eax
0x140820537  cmp     eax, 0C0000034h
0x14082053c  jnz     short loc_140820543
0x14082053e  xor     r14d, r14d
0x140820541  jmp     short loc_14082055D
0x140820543  test    eax, eax
0x140820545  jns     short loc_140820559
0x140820547  lea     r9, aFailedToQueryR; "Failed to query reg value. [%x]"
0x14082054e  mov     r8d, 792h
0x140820554  jmp     loc_14082047F
0x140820559  mov     r14d, [rbp+57h+var_B8]
0x14082055d  lea     r8, aMergever; "MergeVer"
0x140820564  mov     rdx, rdi
0x140820567  lea     rcx, [rbp+57h+var_C8]
0x14082056b  call    AslRegistryGetUInt32
0x140820570  mov     ebx, eax
0x140820572  test    eax, eax
0x140820574  jns     short loc_140820588
0x140820576  lea     r9, aFailedToQueryR; "Failed to query reg value. [%x]"
0x14082057d  mov     r8d, 798h
0x140820583  jmp     loc_14082047F
0x140820588  lea     rdi, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x14082058f  cmp     [rbp+57h+var_C8], r14d
0x140820593  jnb     short loc_1408205AC
0x140820595  lea     r9, aMergeTargetIsT; "Merge target is too high of a version, "...
0x14082059c  mov     r8d, 7A1h
0x1408205a2  mov     rdx, rdi
0x1408205a5  mov     ecx, esi
0x1408205a7  call    AslLogCallPrintf
0x1408205ac  mov     rdx, [rbp+57h+Handle]
0x1408205b0  lea     r8, aMinmergever; "MinMergeVer"
0x1408205b7  lea     rcx, [rbp+57h+var_C8]
0x1408205bb  call    AslRegistryGetUInt32
0x1408205c0  mov     ebx, eax
0x1408205c2  test    eax, eax
0x1408205c4  jns     short loc_1408205DC
0x1408205c6  mov     dword ptr [rsp+100h+var_E0], eax
0x1408205ca  lea     r9, aFailedToQueryR; "Failed to query reg value. [%x]"
0x1408205d1  mov     r8d, 7A7h
0x1408205d7  jmp     loc_140820794
0x1408205dc  cmp     r14d, [rbp+57h+var_C8]
0x1408205e0  jnb     short loc_1408205F9
0x1408205e2  lea     r9, aMergeTargetIsT_0; "Merge target is too low of a version, i"...
0x1408205e9  mov     r8d, 7B0h
0x1408205ef  mov     rdx, rdi
0x1408205f2  mov     ecx, esi
0x1408205f4  call    AslLogCallPrintf
0x1408205f9  mov     r14, [rbp+57h+psz]
0x1408205fd  lea     r8, [rbp+57h+var_80]; pcchLength
0x140820601  mov     rcx, r14; psz
0x140820604  mov     edx, 7FFFFFFFh; cchMax
0x140820609  call    RtlStringCchLengthW
0x14082060e  mov     ebx, eax
0x140820610  test    eax, eax
0x140820612  jns     short loc_14082062A
0x140820614  mov     dword ptr [rsp+100h+var_E0], eax
0x140820618  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x14082061f  mov     r8d, 7B7h
0x140820625  jmp     loc_140820794
0x14082062a  mov     r8, [rbp+57h+var_80]
0x14082062e  mov     rax, [rbp+57h+pcchLength]
0x140820632  cmp     r8, rax
0x140820635  jb      loc_14082077E
0x14082063b  mov     r9, [rbp+57h+Str1]
0x14082063f  lea     rcx, [rbp+57h+var_90]
0x140820643  sub     r8, rax
0x140820646  mov     [rsp+100h+var_E0], r12
0x14082064b  mov     rdx, r14
0x14082064e  call    SdbpSafeAllocAndConcatW
0x140820653  mov     ebx, eax
0x140820655  test    eax, eax
0x140820657  jns     short loc_14082067D
0x140820659  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x140820660  mov     dword ptr [rsp+100h+var_E0], eax
0x140820664  mov     r8d, 7C8h
0x14082066a  mov     rdx, rdi
0x14082066d  mov     ecx, esi
0x14082066f  call    AslLogCallPrintf
0x140820674  mov     r12, [rbp+57h+var_90]
0x140820678  jmp     loc_14082079E
0x14082067d  mov     r12, [rbp+57h+var_90]
0x140820681  lea     rcx, [rbp+57h+var_78]
0x140820685  mov     rdx, r12
0x140820688  mov     r8d, esi
0x14082068b  call    SdbpGetFileTimestamp
0x140820690  mov     ebx, eax
0x140820692  test    eax, eax
0x140820694  jns     short loc_1408206B7
0x140820696  cmp     eax, 0C0000034h
0x14082069b  jz      loc_14082079E
0x1408206a1  mov     dword ptr [rsp+100h+var_E0], eax
0x1408206a5  lea     r9, aFailedToCheckT; "Failed to check timestamp [%x]"
0x1408206ac  mov     r8d, 7D3h
0x1408206b2  jmp     loc_140820794
0x1408206b7  xor     r8d, r8d
0x1408206ba  lea     rcx, [rbp+57h+var_70]
0x1408206be  mov     rdx, r14
0x1408206c1  call    SdbpGetFileTimestamp
0x1408206c6  mov     ebx, eax
0x1408206c8  test    eax, eax
0x1408206ca  jns     short loc_1408206E2
  ... truncated ...
```
