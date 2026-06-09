# SdbpGetMergeRedirectPathInternal

- ea: `0x1800224f4`
- end: `0x180022e32`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `2366`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180022314`

## callees

- `0x18001c954`
- `0x18001ce78`
- `0x18001d378`
- `0x18001ef8c`
- `0x18001f138`
- `0x18001f5ec`
- `0x180021f74`
- `0x1800224f4`
- `0x180023c84`
- `0x180023ff4`
- `0x180037a34`
- `0x180056950`
- `0x18005b1b4`
- `0x180061d88`
- `0x180061df4`
- `0x1800827c0`

## import_xrefs

- `ntdll!ZwClose` at `0x180022964`
- `ntdll!ZwClose` at `0x180022964`
- `ntdll!RtlAllocateHeap` at `0x18002268d`
- `ntdll!RtlAllocateHeap` at `0x180022a70`
- `ntdll!RtlAllocateHeap` at `0x18002268d`
- `ntdll!RtlAllocateHeap` at `0x180022a70`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180022617`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800226ba`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180022617`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800226ba`

## string_xrefs

- `0x18002290b`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x18002292a`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x180022d15`: `Failed to get manifested stub [%x]`
- `0x180022654`: `SdbpGetMergeRedirectPathInternal`
- `0x1800226f5`: `SdbpGetMergeRedirectPathInternal`
- `0x18002280f`: `SdbpGetMergeRedirectPathInternal`
- `0x180022937`: `SdbpGetMergeRedirectPathInternal`
- `0x180022b4d`: `SdbpGetMergeRedirectPathInternal`
- `0x180022b94`: `SdbpGetMergeRedirectPathInternal`
- `0x180022be1`: `SdbpGetMergeRedirectPathInternal`
- `0x180022c76`: `SdbpGetMergeRedirectPathInternal`
- `0x180022cbd`: `SdbpGetMergeRedirectPathInternal`
- `0x180022d4f`: `SdbpGetMergeRedirectPathInternal`
- `0x1800226e9`: `Failed to get full path [%x]`
- `0x180022ab2`: `RtlStringCchCopyW failed to copy first string [%x]`
- `0x180022648`: `Failed to get full path size [%x]`
- `0x1800227e4`: `StagedDelete_`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, unsigned __int64 a4)
{
  __int64 v5; // rdi
  signed int LastErrorValue; // ebx
  PVOID v8; // r12
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r13
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  __int64 v16; // rsi
  __int64 FileNamePart; // rax
  const wchar_t *v18; // r15
  const wchar_t *i; // rdi
  const wchar_t *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  const wchar_t *v23; // r12
  int Key; // eax
  wchar_t *v25; // rbx
  __int64 v26; // rdx
  const wchar_t *v27; // rax
  unsigned __int64 v28; // r13
  const char *v29; // r9
  int v30; // r8d
  unsigned __int64 v31; // rdi
  PVOID v32; // rax
  PVOID v33; // r15
  int v34; // eax
  int v35; // r8d
  const char *v36; // r9
  PVOID v37; // r8
  HANDLE v38; // r15
  int UInt32; // eax
  unsigned int v40; // edi
  int v41; // r8d
  _WORD *v42; // rax
  __int64 v43; // rcx
  unsigned __int64 v44; // r8
  int v45; // eax
  int FileTimestamp; // eax
  int v47; // r8d
  const char *v48; // r9
  unsigned __int64 v49; // rax
  int v50; // eax
  const char *v51; // r9
  int v52; // r8d
  char v53; // [rsp+20h] [rbp-99h]
  __int64 v54; // [rsp+30h] [rbp-89h] BYREF
  __int64 v55; // [rsp+38h] [rbp-81h]
  unsigned int v56; // [rsp+40h] [rbp-79h] BYREF
  int v57; // [rsp+44h] [rbp-75h]
  void *v58; // [rsp+48h] [rbp-71h]
  unsigned int v59; // [rsp+50h] [rbp-69h] BYREF
  WCHAR *v60; // [rsp+58h] [rbp-61h]
  HANDLE Handle; // [rsp+60h] [rbp-59h] BYREF
  wchar_t *String1; // [rsp+68h] [rbp-51h] BYREF
  __int64 v63; // [rsp+70h] [rbp-49h] BYREF
  const wchar_t *v64; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v65; // [rsp+80h] [rbp-39h] BYREF
  unsigned __int64 v66; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v67; // [rsp+90h] [rbp-29h] BYREF
  _DWORD *v68; // [rsp+98h] [rbp-21h]
  unsigned __int64 v69; // [rsp+A0h] [rbp-19h]
  __int64 v70; // [rsp+A8h] [rbp-11h]
  _QWORD *v71; // [rsp+B0h] [rbp-9h]
  wchar_t String2[12]; // [rsp+B8h] [rbp-1h] BYREF

  v57 = a3;
  v5 = 0;
  v68 = a2;
  v71 = a1;
  v56 = 0;
  Handle = 0;
  String1 = 0;
  v59 = 0;
  v55 = 0;
  v63 = 0;
  v66 = 0;
  v67 = 0;
  v65 = 0;
  v54 = 0;
  v64 = 0;
  wcscpy(String2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    v8 = 0;
    v58 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a4 + 2 * v9) );
    v10 = 0;
    if ( v9 <= 3 )
    {
      if ( v9 <= 1 )
      {
LABEL_16:
        FullPathNameW = GetFullPathNameW((LPCWSTR)a4, 0, 0, 0);
        v14 = FullPathNameW;
        if ( !FullPathNameW )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          if ( LastErrorValue > 0 )
            LastErrorValue = (unsigned __int16)LastErrorValue | 0xC0070000;
          if ( LastErrorValue >= 0 )
            LastErrorValue = -1073741595;
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1814,
            (unsigned int)"Failed to get full path size [%x]",
            LastErrorValue);
          return (unsigned int)LastErrorValue;
        }
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * FullPathNameW);
        v60 = Heap;
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        if ( !GetFullPathNameW((LPCWSTR)a4, v14, Heap, 0) )
        {
          LastErrorValue = NtCurrentTeb()->LastErrorValue;
          if ( LastErrorValue > 0 )
            LastErrorValue = (unsigned __int16)LastErrorValue | 0xC0070000;
          if ( LastErrorValue >= 0 )
            LastErrorValue = -1073741595;
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetMergeRedirectPathInternal",
            1828,
            (unsigned int)"Failed to get full path [%x]",
            LastErrorValue);
          v16 = v54;
          goto LABEL_50;
        }
        a4 = (unsigned __int64)v12;
LABEL_31:
        LastErrorValue = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v70 = FileNamePart;
        v18 = (const wchar_t *)FileNamePart;
        if ( FileNamePart == a4 )
        {
LABEL_48:
          v16 = v54;
          goto LABEL_49;
        }
        for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
        {
          if ( (unsigned __int64)i < a4 )
            goto LABEL_47;
          if ( (*i == 92 || *i == 47) && !wcsnicmp_0(i, String2, 0xAu) )
            break;
        }
        if ( v18 )
        {
          v20 = v18;
          v21 = 0x7FFFFFFF;
          do
          {
            if ( !*v20 )
              break;
            ++v20;
            --v21;
          }
          while ( v21 );
          LastErrorValue = v21 == 0 ? 0xC000000D : 0;
          v69 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
          if ( v21 )
          {
            if ( v57 )
            {
              v22 = SdbpSafeAllocAndConcatW(
                      (unsigned int)&v64,
                      (unsigned int)L"StagedDelete_",
                      13,
                      (_DWORD)v18,
                      (0x7FFFFFFF - v21) & -(__int64)(v21 != 0));
              LastErrorValue = v22;
              if ( v22 < 0 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"SdbpGetMergeRedirectPathInternal",
                  1876,
                  (unsigned int)"Failed to alloc and cat file to prefix [%x]",
                  v22);
LABEL_46:
                v12 = v60;
LABEL_47:
                v5 = v55;
                goto LABEL_48;
              }
              v23 = v64;
            }
            else
            {
              v23 = v18;
            }
            Key = AslRegistryGetKey(
                    &Handle,
                    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                    2147483904LL);
            LastErrorValue = Key;
            if ( Key < 0 )
            {
              if ( Key != -1073741772 )
                AslLogCallPrintf(
                  1,
                  (unsigned int)"SdbpGetMergeRedirectPathInternal",
                  1893,
                  (unsigned int)"AslRegistryGetKey failed to open SdbUpdates key [%x]",
                  Key);
              goto LABEL_67;
            }
            LastErrorValue = AslRegistryGetString(&String1, Handle, v23);
            if ( LastErrorValue < 0 )
            {
LABEL_67:
              v8 = v58;
LABEL_68:
              v5 = v55;
LABEL_69:
              v16 = v54;
LABEL_70:
              if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                ZwClose(Handle);
              v12 = v60;
LABEL_49:
              if ( !v12 )
              {
LABEL_51:
                if ( String1 )
                  AslFree(NtCurrentPeb()->ProcessHeap, String1);
                if ( v5 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v5);
                if ( v16 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v16);
                if ( v8 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v8);
                if ( v64 )
                  AslFree(NtCurrentPeb()->ProcessHeap, v64);
                return (unsigned int)LastErrorValue;
              }
LABEL_50:
              AslFree(NtCurrentPeb()->ProcessHeap, v12);
              goto LABEL_51;
            }
            v25 = String1;
            if ( !wcsicmp_0(String1, v18) )
            {
              LastErrorValue = -1073741772;
              v8 = 0;
              goto LABEL_68;
            }
            if ( v57 && !wcsicmp_0(v25, L"__NotRedirected__") && v68 )
            {
              LastErrorValue = 0;
              *v68 = 1;
              v8 = 0;
              goto LABEL_68;
            }
            if ( !v23 )
            {
              LastErrorValue = -1073741582;
LABEL_147:
              AslLogCallPrintf(
                1,
                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                1927,
                (unsigned int)"Failed to alloc and cat file to prefix [%x]",
                LastErrorValue);
              goto LABEL_67;
            }
            v26 = 0x7FFFFFFF;
            v27 = v23;
            do
            {
              if ( !*v27 )
                break;
              ++v27;
              --v26;
            }
            while ( v26 );
            LastErrorValue = v26 == 0 ? 0xC000000D : 0;
            v28 = (0x7FFFFFFF - v26) & -(__int64)(v26 != 0);
            if ( !v26 )
            {
              v29 = "RtlStringCchLengthW failed [%x]";
              v30 = 1645;
LABEL_146:
              AslLogCallPrintf(1, (unsigned int)"SdbpSafeAllocAndConcatW", v30, (_DWORD)v29, LastErrorValue);
              goto LABEL_147;
            }
            if ( v28 >= 0xFFFFFFFFFFFFFFF7uLL )
            {
              v30 = 1655;
            }
            else
            {
              v31 = v28 + 10;
              if ( v28 + 10 >= v28 + 9 )
              {
                v32 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v31);
                v33 = v32;
                if ( !v32 )
                {
                  LastErrorValue = -1073741801;
                  goto LABEL_147;
                }
                v34 = RtlStringCchCopyNW(v32, v31, L"MergeVer_", 9);
                LastErrorValue = v34;
                if ( v34 < 0 )
                {
                  v35 = 1677;
                  v36 = "RtlStringCchCopyW failed to copy first string [%x]";
LABEL_95:
                  AslLogCallPrintf(1, (unsigned int)"SdbpSafeAllocAndConcatW", v35, (_DWORD)v36, v34);
                  AslFree(NtCurrentPeb()->ProcessHeap, v33);
                  goto LABEL_147;
                }
                v34 = RtlStringCchCatNW(v33, v31, v23, v28);
                LastErrorValue = v34;
                if ( v34 < 0 )
                {
                  v35 = 1686;
                  v36 = "RtlStringCchCatW failed to cat second string [%x]";
                  goto LABEL_95;
                }
                v37 = v33;
                v8 = v33;
                v38 = Handle;
                UInt32 = AslRegistryGetUInt32(&v59, Handle, v37);
                LastErrorValue = UInt32;
                if ( UInt32 == -1073741772 )
                {
                  v40 = 0;
                }
                else
                {
                  if ( UInt32 < 0 )
                  {
                    v41 = 1936;
LABEL_100:
                    AslLogCallPrintf(
                      1,
                      (unsigned int)"SdbpGetMergeRedirectPathInternal",
                      v41,
                      (unsigned int)"Failed to query reg value. [%x]",
                      UInt32);
                    goto LABEL_68;
                  }
                  v40 = v59;
                }
                UInt32 = AslRegistryGetUInt32(&v56, v38, L"MergeVer");
                LastErrorValue = UInt32;
                if ( UInt32 < 0 )
                {
                  v41 = 1942;
                  goto LABEL_100;
                }
                if ( v56 < v40 )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"SdbpGetMergeRedirectPathInternal",
                    1951,
                    (unsigned int)"Merge target is too high of a version, this code might not handle it correctly.",
                    v53);
                UInt32 = AslRegistryGetUInt32(&v56, v38, L"MinMergeVer");
                LastErrorValue = UInt32;
                if ( UInt32 < 0 )
                {
                  v41 = 1957;
                  goto LABEL_100;
                }
                if ( v40 < v56 )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"SdbpGetMergeRedirectPathInternal",
                    1966,
                    (unsigned int)"Merge target is too low of a version, it might not be possible to handle correctly.",
                    v53);
                if ( a4 )
                {
                  v42 = (_WORD *)a4;
                  v43 = 0x7FFFFFFF;
                  do
                  {
                    if ( !*v42 )
                      break;
                    ++v42;
                    --v43;
                  }
                  while ( v43 );
                  LastErrorValue = v43 == 0 ? 0xC000000D : 0;
                  v44 = (0x7FFFFFFF - v43) & -(__int64)(v43 != 0);
                  if ( v43 )
                  {
                    if ( v44 >= v69 )
                    {
                      v45 = SdbpSafeAllocAndConcatW((unsigned int)&v63, a4, (int)v44 - (int)v69, (_DWORD)String1, 0);
                      LastErrorValue = v45;
                      if ( v45 < 0 )
                      {
                        AslLogCallPrintf(
                          1,
                          (unsigned int)"SdbpGetMergeRedirectPathInternal",
                          1990,
                          (unsigned int)"Failed to alloc and cat file to prefix [%x]",
                          v45);
                        v5 = v63;
                        goto LABEL_69;
                      }
                      v5 = v63;
                      FileTimestamp = SdbpGetFileTimestamp(&v66, v63, 1);
                      LastErrorValue = FileTimestamp;
                      if ( FileTimestamp >= 0 )
                      {
                        FileTimestamp = SdbpGetFileTimestamp(&v67, a4, 0);
                        LastErrorValue = FileTimestamp;
                        if ( FileTimestamp >= 0 )
                        {
                          FileTimestamp = SdbpGetManifestedMergeStubAlloc(&v54, v70);
                          LastErrorValue = FileTimestamp;
                          if ( FileTimestamp == -1073741772 )
                          {
                            v16 = v54;
                            v49 = 0;
                          }
                          else
                          {
                            if ( FileTimestamp < 0 )
                            {
                              v48 = "Failed to get manifested stub [%x]";
                              v47 = 2026;
                              goto LABEL_122;
                            }
                            v16 = v54;
                            v50 = SdbpGetFileTimestamp(&v65, v54, 0);
                            LastErrorValue = v50;
                            if ( v50 < 0 )
                            {
                              AslLogCallPrintf(
                                1,
                                (unsigned int)"SdbpGetMergeRedirectPathInternal",
                                2036,
                                (unsigned int)"Failed to check timestamp [%x]",
                                v50);
                              goto LABEL_70;
                            }
                            v49 = v65;
                          }
                          if ( v66 < v67 || v66 < v49 )
                          {
                            LastErrorValue = -1073741772;
                          }
                          else
                          {
                            *v71 = v5;
                            if ( v68 && v57 )
                              *v68 = 1;
                            v5 = 0;
                            LastErrorValue = 0;
                          }
                          goto LABEL_70;
                        }
                        v47 = 2012;
                      }
                      else
                      {
                        if ( FileTimestamp == -1073741772 )
                          goto LABEL_69;
                        v47 = 2001;
                      }
                      v48 = "Failed to check timestamp [%x]";
LABEL_122:
                      AslLogCallPrintf(
                        1,
                        (unsigned int)"SdbpGetMergeRedirectPathInternal",
                        v47,
                        (_DWORD)v48,
                        FileTimestamp);
                      goto LABEL_69;
                    }
                    LastErrorValue = -1073741675;
                    v51 = "RtlSizeTSub failed [%x]";
                    v52 = 1980;
LABEL_140:
                    AslLogCallPrintf(
                      1,
                      (unsigned int)"SdbpGetMergeRedirectPathInternal",
                      v52,
                      (_DWORD)v51,
                      LastErrorValue);
                    goto LABEL_68;
                  }
                }
                else
                {
                  LastErrorValue = -1073741811;
                }
                v51 = "RtlStringCchLengthW failed [%x]";
                v52 = 1973;
                goto LABEL_140;
              }
              v30 = 1662;
            }
            v29 = "RtlSizeTAdd failed [%x]";
            LastErrorValue = -1073741675;
            goto LABEL_146;
          }
        }
        else
        {
          LastErrorValue = -1073741811;
        }
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetMergeRedirectPathInternal",
          1864,
          (unsigned int)"RtlStringCchLengthW failed [%x]",
          LastErrorValue);
        goto LABEL_46;
      }
    }
    else if ( *(_WORD *)(a4 + 2) == 58 )
    {
      v10 = *(_WORD *)(a4 + 4) == 92;
    }
    v11 = *(_WORD *)a4 == 92;
    v12 = 0;
    v60 = 0;
    if ( v10 || v11 )
      goto LABEL_31;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x1800224f4  mov     [rsp-8+arg_10], rbx
0x1800224f9  push    rbp
0x1800224fa  push    rsi
0x1800224fb  push    rdi
0x1800224fc  push    r12
0x1800224fe  push    r13
0x180022500  push    r14
0x180022502  push    r15
0x180022504  lea     rbp, [rsp-27h]
0x180022509  sub     rsp, 0E0h
0x180022510  mov     rax, cs:__security_cookie
0x180022517  xor     rax, rsp
0x18002251a  mov     [rbp+57h+var_40], rax
0x18002251e  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x180022525  xor     r14d, r14d
0x180022528  mov     rsi, r9
0x18002252b  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x180022533  mov     rax, rdx
0x180022536  mov     [rbp+57h+var_CC], r8d
0x18002253a  mov     edi, r14d
0x18002253d  mov     [rbp+57h+var_78], rdx
0x180022541  mov     [rbp+57h+var_60], rcx
0x180022545  mov     [rbp+57h+var_D0], r14d
0x180022549  mov     [rbp+57h+Handle], r14
0x18002254d  mov     [rbp+57h+String1], r14
0x180022551  mov     [rbp+57h+var_C0], r14d
0x180022555  mov     [rsp+110h+var_D8], r14
0x18002255a  mov     [rbp+57h+var_A0], r14
0x18002255e  mov     [rbp+57h+var_88], r14
0x180022562  mov     [rbp+57h+var_80], r14
0x180022566  mov     [rbp+57h+var_90], r14
0x18002256a  mov     [rsp+110h+var_E0], r14
0x18002256f  mov     [rbp+57h+var_98], r14
0x180022573  movups  xmmword ptr [rbp+57h+String2], xmm0
0x180022577  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x18002257c  test    rcx, rcx
0x18002257f  jnz     short loc_18002258B
0x180022581  mov     eax, 0C00000EFh
0x180022586  jmp     loc_1800228D4
0x18002258b  mov     [rcx], r14
0x18002258e  test    rax, rax
0x180022591  jz      short loc_18002259B
0x180022593  test    r8d, r8d
0x180022596  jz      short loc_18002259B
0x180022598  mov     [rdx], r14d
0x18002259b  call    SdbpGetMergeSdbsSupported
0x1800225a0  test    eax, eax
0x1800225a2  jnz     short loc_1800225AE
0x1800225a4  mov     ebx, 0C0000034h
0x1800225a9  jmp     loc_1800228D2
0x1800225ae  mov     r12, r14
0x1800225b1  mov     [rbp+57h+var_C8], r14
0x1800225b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800225b9  inc     rax
0x1800225bc  cmp     [rsi+rax*2], r14w
0x1800225c1  jnz     short loc_1800225B9
0x1800225c3  mov     r15d, 1
0x1800225c9  mov     ecx, r14d
0x1800225cc  cmp     rax, 3
0x1800225d0  jbe     short loc_1800225E5
0x1800225d2  cmp     word ptr [rsi+2], 3Ah ; ':'
0x1800225d7  jnz     short loc_1800225EA
0x1800225d9  cmp     word ptr [rsi+4], 5Ch ; '\'
0x1800225de  jnz     short loc_1800225EA
0x1800225e0  mov     ecx, r15d
0x1800225e3  jmp     short loc_1800225EA
0x1800225e5  cmp     rax, r15
0x1800225e8  jbe     short loc_18002260C
0x1800225ea  cmp     word ptr [rsi], 5Ch ; '\'
0x1800225ee  mov     eax, r14d
0x1800225f1  mov     r13, r14
0x1800225f4  mov     [rbp+57h+var_B8], r14
0x1800225f8  cmovz   eax, r15d
0x1800225fc  test    ecx, ecx
0x1800225fe  jnz     loc_18002271E
0x180022604  test    eax, eax
0x180022606  jnz     loc_18002271E
0x18002260c  xor     r9d, r9d; lpFilePart
0x18002260f  xor     r8d, r8d; lpBuffer
0x180022612  xor     edx, edx; nBufferLength
0x180022614  mov     rcx, rsi; lpFileName
0x180022617  call    cs:__imp_GetFullPathNameW
0x18002261e  nop     dword ptr [rax+rax+00h]
0x180022623  mov     ebx, eax
0x180022625  test    eax, eax
0x180022627  jnz     short loc_180022675
0x180022629  mov     ebx, gs:68h
0x180022631  mov     eax, gs:68h
0x180022639  test    eax, eax
0x18002263b  jle     short loc_180022646
0x18002263d  movzx   ebx, bx
0x180022640  or      ebx, 0C0070000h
0x180022646  test    ebx, ebx
0x180022648  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x18002264f  mov     eax, 0C00000E5h
0x180022654  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18002265b  cmovns  ebx, eax
0x18002265e  mov     r8d, 716h
0x180022664  mov     ecx, r15d
0x180022667  mov     dword ptr [rsp+110h+var_F0], ebx
0x18002266b  call    AslLogCallPrintf
0x180022670  jmp     loc_1800228D2
0x180022675  mov     rcx, gs:60h
0x18002267e  mov     r8, rbx
0x180022681  add     r8, r8; Size
0x180022684  mov     edx, 8; Flags
0x180022689  mov     rcx, [rcx+30h]; HeapHandle
0x18002268d  call    cs:__imp_RtlAllocateHeap
0x180022694  nop     dword ptr [rax+rax+00h]
0x180022699  mov     [rbp+57h+var_B8], rax
0x18002269d  mov     r13, rax
0x1800226a0  test    rax, rax
0x1800226a3  jnz     short loc_1800226AF
0x1800226a5  mov     ebx, 0C0000017h
0x1800226aa  jmp     loc_1800228D2
0x1800226af  xor     r9d, r9d; lpFilePart
0x1800226b2  mov     r8, r13; lpBuffer
0x1800226b5  mov     edx, ebx; nBufferLength
0x1800226b7  mov     rcx, rsi; lpFileName
0x1800226ba  call    cs:__imp_GetFullPathNameW
0x1800226c1  nop     dword ptr [rax+rax+00h]
0x1800226c6  test    eax, eax
0x1800226c8  jnz     short loc_18002271B
0x1800226ca  mov     ebx, gs:68h
0x1800226d2  mov     eax, gs:68h
0x1800226da  test    eax, eax
0x1800226dc  jle     short loc_1800226E7
0x1800226de  movzx   ebx, bx
0x1800226e1  or      ebx, 0C0070000h
0x1800226e7  test    ebx, ebx
0x1800226e9  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x1800226f0  mov     eax, 0C00000E5h
0x1800226f5  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800226fc  cmovns  ebx, eax
0x1800226ff  mov     r8d, 724h
0x180022705  mov     ecx, r15d
0x180022708  mov     dword ptr [rsp+110h+var_F0], ebx
0x18002270c  call    AslLogCallPrintf
0x180022711  mov     rsi, [rsp+110h+var_E0]
0x180022716  jmp     loc_180022833
0x18002271b  mov     rsi, r13
0x18002271e  mov     r14d, 0C0000034h
0x180022724  mov     rcx, rsi
0x180022727  mov     ebx, r14d
0x18002272a  call    AslPathGetFileNamePart
0x18002272f  mov     [rbp+57h+var_68], rax
0x180022733  mov     r15, rax
0x180022736  cmp     rax, rsi
0x180022739  jz      loc_180022829
0x18002273f  lea     rdi, [rax-4]
0x180022743  cmp     rdi, rsi
0x180022746  jb      loc_180022824
0x18002274c  cmp     word ptr [rdi], 5Ch ; '\'
0x180022750  jz      short loc_180022758
0x180022752  cmp     word ptr [rdi], 2Fh ; '/'
0x180022756  jnz     short loc_180022771
0x180022758  mov     r8d, 0Ah; MaxCount
0x18002275e  lea     rdx, [rbp+57h+String2]; String2
0x180022762  mov     rcx, rdi; String1
0x180022765  call    _wcsnicmp_0
0x18002276a  xor     r8d, r8d
0x18002276d  test    eax, eax
0x18002276f  jz      short loc_180022777
0x180022771  sub     rdi, 2
0x180022775  jmp     short loc_180022743
0x180022777  test    r15, r15
0x18002277a  jz      loc_180022E17
0x180022780  mov     r13d, 7FFFFFFFh
0x180022786  mov     rax, r15
0x180022789  mov     edx, r13d
0x18002278c  cmp     [rax], r8w
0x180022790  jz      short loc_18002279C
0x180022792  add     rax, 2
0x180022796  sub     rdx, 1
0x18002279a  jnz     short loc_18002278C
0x18002279c  mov     rax, rdx
0x18002279f  mov     edi, 0C000000Dh
0x1800227a4  neg     rax
0x1800227a7  mov     rcx, r13
0x1800227aa  mov     rax, rdx
0x1800227ad  sbb     ebx, ebx
0x1800227af  sub     rcx, rdx
0x1800227b2  not     ebx
0x1800227b4  and     ebx, edi
0x1800227b6  neg     rax
0x1800227b9  sbb     rax, rax
0x1800227bc  and     rax, rcx
0x1800227bf  mov     [rbp+57h+var_70], rax
0x1800227c3  test    rdx, rdx
0x1800227c6  jz      loc_180022E1C
0x1800227cc  cmp     [rbp+57h+var_CC], r8d
0x1800227d0  jz      loc_180022902
0x1800227d6  mov     r9, r15
0x1800227d9  mov     qword ptr [rsp+110h+var_F0], rax
0x1800227de  mov     r8d, 0Dh
0x1800227e4  lea     rdx, aStageddelete; "StagedDelete_"
0x1800227eb  lea     rcx, [rbp+57h+var_98]
0x1800227ef  call    SdbpSafeAllocAndConcatW
0x1800227f4  mov     ebx, eax
0x1800227f6  test    eax, eax
0x1800227f8  jns     loc_1800228FC
0x1800227fe  mov     dword ptr [rsp+110h+var_F0], eax
0x180022802  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x180022809  mov     r8d, 754h
0x18002280f  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x180022816  mov     ecx, 1
0x18002281b  call    AslLogCallPrintf
0x180022820  mov     r13, [rbp+57h+var_B8]
0x180022824  mov     rdi, [rsp+110h+var_D8]
0x180022829  mov     rsi, [rsp+110h+var_E0]
0x18002282e  test    r13, r13
0x180022831  jz      short loc_180022848
0x180022833  mov     rcx, gs:60h
0x18002283c  mov     rdx, r13
0x18002283f  mov     rcx, [rcx+30h]
0x180022843  call    AslFree
0x180022848  mov     rax, [rbp+57h+String1]
0x18002284c  test    rax, rax
0x18002284f  jz      short loc_180022866
0x180022851  mov     rcx, gs:60h
0x18002285a  mov     rdx, rax
0x18002285d  mov     rcx, [rcx+30h]
0x180022861  call    AslFree
0x180022866  test    rdi, rdi
0x180022869  jz      short loc_180022880
0x18002286b  mov     rcx, gs:60h
0x180022874  mov     rdx, rdi
0x180022877  mov     rcx, [rcx+30h]
0x18002287b  call    AslFree
0x180022880  test    rsi, rsi
0x180022883  jz      short loc_18002289A
0x180022885  mov     rcx, gs:60h
0x18002288e  mov     rdx, rsi
0x180022891  mov     rcx, [rcx+30h]
0x180022895  call    AslFree
0x18002289a  test    r12, r12
0x18002289d  jz      short loc_1800228B4
0x18002289f  mov     rcx, gs:60h
0x1800228a8  mov     rdx, r12
0x1800228ab  mov     rcx, [rcx+30h]
0x1800228af  call    AslFree
0x1800228b4  mov     rax, [rbp+57h+var_98]
0x1800228b8  test    rax, rax
0x1800228bb  jz      short loc_1800228D2
0x1800228bd  mov     rcx, gs:60h
0x1800228c6  mov     rdx, rax
0x1800228c9  mov     rcx, [rcx+30h]
0x1800228cd  call    AslFree
0x1800228d2  mov     eax, ebx
0x1800228d4  mov     rcx, [rbp+57h+var_40]
0x1800228d8  xor     rcx, rsp; StackCookie
0x1800228db  call    __security_check_cookie
0x1800228e0  mov     rbx, [rsp+110h+arg_10]
0x1800228e8  add     rsp, 0E0h
0x1800228ef  pop     r15
0x1800228f1  pop     r14
0x1800228f3  pop     r13
0x1800228f5  pop     r12
0x1800228f7  pop     rdi
0x1800228f8  pop     rsi
0x1800228f9  pop     rbp
0x1800228fa  retn
0x1800228fc  mov     r12, [rbp+57h+var_98]
0x180022900  jmp     short loc_180022905
0x180022902  mov     r12, r15
0x180022905  mov     r8d, 80000100h
0x18002290b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180022912  lea     rcx, [rbp+57h+Handle]
0x180022916  call    AslRegistryGetKey
0x18002291b  mov     ebx, eax
0x18002291d  test    eax, eax
0x18002291f  jns     short loc_180022979
0x180022921  cmp     eax, r14d
0x180022924  jz      short loc_180022948
0x180022926  mov     dword ptr [rsp+110h+var_F0], eax
0x18002292a  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x180022931  mov     r8d, 765h
0x180022937  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x18002293e  mov     ecx, 1
0x180022943  call    AslLogCallPrintf
0x180022948  mov     r12, [rbp+57h+var_C8]
0x18002294c  mov     rdi, [rsp+110h+var_D8]
0x180022951  mov     rsi, [rsp+110h+var_E0]
0x180022956  mov     rcx, [rbp+57h+Handle]; Handle
0x18002295a  lea     rax, [rcx-1]
0x18002295e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022962  ja      short loc_180022970
0x180022964  call    cs:__imp_ZwClose
0x18002296b  nop     dword ptr [rax+rax+00h]
0x180022970  mov     r13, [rbp+57h+var_B8]
0x180022974  jmp     loc_18002282E
0x180022979  mov     rdx, [rbp+57h+Handle]
0x18002297d  lea     rcx, [rbp+57h+String1]
0x180022981  mov     r8, r12
0x180022984  call    AslRegistryGetString
0x180022989  mov     ebx, eax
0x18002298b  test    eax, eax
0x18002298d  js      short loc_180022948
0x18002298f  mov     rbx, [rbp+57h+String1]
0x180022993  mov     rdx, r15; String2
  ... truncated ...
```
