# SdbpGetMergeRedirectPathInternal

- ea: `0x1800245a0`
- end: `0x180024ebf`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `2335`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800243c4`

## callees

- `0x18001eab4`
- `0x18001f028`
- `0x18001f4e4`
- `0x180021144`
- `0x1800212e4`
- `0x180021764`
- `0x180024068`
- `0x1800245a0`
- `0x180025dc0`
- `0x1800260fc`
- `0x180035394`
- `0x1800517b0`
- `0x180055e28`
- `0x18005c3a8`
- `0x18005c414`
- `0x18007a840`

## import_xrefs

- `ntdll!ZwClose` at `0x1800249fd`
- `ntdll!ZwClose` at `0x1800249fd`
- `ntdll!RtlAllocateHeap` at `0x180024733`
- `ntdll!RtlAllocateHeap` at `0x180024b03`
- `ntdll!RtlAllocateHeap` at `0x180024733`
- `ntdll!RtlAllocateHeap` at `0x180024b03`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800246c3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002475a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800246c3`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002475a`

## string_xrefs

- `0x1800249a4`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1800249c3`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x180024da2`: `Failed to get manifested stub [%x]`
- `0x1800246fa`: `SdbpGetMergeRedirectPathInternal`
- `0x18002478f`: `SdbpGetMergeRedirectPathInternal`
- `0x1800248a9`: `SdbpGetMergeRedirectPathInternal`
- `0x1800249d0`: `SdbpGetMergeRedirectPathInternal`
- `0x180024bda`: `SdbpGetMergeRedirectPathInternal`
- `0x180024c21`: `SdbpGetMergeRedirectPathInternal`
- `0x180024c6e`: `SdbpGetMergeRedirectPathInternal`
- `0x180024d03`: `SdbpGetMergeRedirectPathInternal`
- `0x180024d4a`: `SdbpGetMergeRedirectPathInternal`
- `0x180024ddc`: `SdbpGetMergeRedirectPathInternal`
- `0x180024783`: `Failed to get full path [%x]`
- `0x180024b3f`: `RtlStringCchCopyW failed to copy first string [%x]`
- `0x18002487e`: `StagedDelete_`
- `0x1800246ee`: `Failed to get full path size [%x]`

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
            1816,
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
            1830,
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
                  1878,
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
                  1895,
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
                1929,
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
              v30 = 1647;
LABEL_146:
              AslLogCallPrintf(1, (unsigned int)"SdbpSafeAllocAndConcatW", v30, (_DWORD)v29, LastErrorValue);
              goto LABEL_147;
            }
            if ( v28 >= 0xFFFFFFFFFFFFFFF7uLL )
            {
              v30 = 1657;
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
                  v35 = 1679;
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
                  v35 = 1688;
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
                    v41 = 1938;
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
                  v41 = 1944;
                  goto LABEL_100;
                }
                if ( v56 < v40 )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"SdbpGetMergeRedirectPathInternal",
                    1953,
                    (unsigned int)"Merge target is too high of a version, this code might not handle it correctly.",
                    v53);
                UInt32 = AslRegistryGetUInt32(&v56, v38, L"MinMergeVer");
                LastErrorValue = UInt32;
                if ( UInt32 < 0 )
                {
                  v41 = 1959;
                  goto LABEL_100;
                }
                if ( v40 < v56 )
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"SdbpGetMergeRedirectPathInternal",
                    1968,
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
                          1992,
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
                              v47 = 2028;
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
                                2038,
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
                        v47 = 2014;
                      }
                      else
                      {
                        if ( FileTimestamp == -1073741772 )
                          goto LABEL_69;
                        v47 = 2003;
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
                    v52 = 1982;
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
                v52 = 1975;
                goto LABEL_140;
              }
              v30 = 1664;
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
          1866,
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
0x1800245a0  mov     [rsp-8+arg_10], rbx
0x1800245a5  push    rbp
0x1800245a6  push    rsi
0x1800245a7  push    rdi
0x1800245a8  push    r12
0x1800245aa  push    r13
0x1800245ac  push    r14
0x1800245ae  push    r15
0x1800245b0  lea     rbp, [rsp-27h]
0x1800245b5  sub     rsp, 0E0h
0x1800245bc  mov     rax, cs:__security_cookie
0x1800245c3  xor     rax, rsp
0x1800245c6  mov     [rbp+57h+var_40], rax
0x1800245ca  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x1800245d1  xor     r14d, r14d
0x1800245d4  mov     rsi, r9
0x1800245d7  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x1800245df  mov     rax, rdx
0x1800245e2  mov     [rbp+57h+var_CC], r8d
0x1800245e6  mov     edi, r14d
0x1800245e9  mov     [rbp+57h+var_78], rdx
0x1800245ed  mov     [rbp+57h+var_60], rcx
0x1800245f1  mov     [rbp+57h+var_D0], r14d
0x1800245f5  mov     [rbp+57h+Handle], r14
0x1800245f9  mov     [rbp+57h+String1], r14
0x1800245fd  mov     [rbp+57h+var_C0], r14d
0x180024601  mov     [rsp+110h+var_D8], r14
0x180024606  mov     [rbp+57h+var_A0], r14
0x18002460a  mov     [rbp+57h+var_88], r14
0x18002460e  mov     [rbp+57h+var_80], r14
0x180024612  mov     [rbp+57h+var_90], r14
0x180024616  mov     [rsp+110h+var_E0], r14
0x18002461b  mov     [rbp+57h+var_98], r14
0x18002461f  movups  xmmword ptr [rbp+57h+String2], xmm0
0x180024623  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x180024628  test    rcx, rcx
0x18002462b  jnz     short loc_180024637
0x18002462d  mov     eax, 0C00000EFh
0x180024632  jmp     loc_18002496E
0x180024637  mov     [rcx], r14
0x18002463a  test    rax, rax
0x18002463d  jz      short loc_180024647
0x18002463f  test    r8d, r8d
0x180024642  jz      short loc_180024647
0x180024644  mov     [rdx], r14d
0x180024647  call    SdbpGetMergeSdbsSupported
0x18002464c  test    eax, eax
0x18002464e  jnz     short loc_18002465A
0x180024650  mov     ebx, 0C0000034h
0x180024655  jmp     loc_18002496C
0x18002465a  mov     r12, r14
0x18002465d  mov     [rbp+57h+var_C8], r14
0x180024661  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024665  inc     rax
0x180024668  cmp     [rsi+rax*2], r14w
0x18002466d  jnz     short loc_180024665
0x18002466f  mov     r15d, 1
0x180024675  mov     ecx, r14d
0x180024678  cmp     rax, 3
0x18002467c  jbe     short loc_180024691
0x18002467e  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180024683  jnz     short loc_180024696
0x180024685  cmp     word ptr [rsi+4], 5Ch ; '\'
0x18002468a  jnz     short loc_180024696
0x18002468c  mov     ecx, r15d
0x18002468f  jmp     short loc_180024696
0x180024691  cmp     rax, r15
0x180024694  jbe     short loc_1800246B8
0x180024696  cmp     word ptr [rsi], 5Ch ; '\'
0x18002469a  mov     eax, r14d
0x18002469d  mov     r13, r14
0x1800246a0  mov     [rbp+57h+var_B8], r14
0x1800246a4  cmovz   eax, r15d
0x1800246a8  test    ecx, ecx
0x1800246aa  jnz     loc_1800247B8
0x1800246b0  test    eax, eax
0x1800246b2  jnz     loc_1800247B8
0x1800246b8  xor     r9d, r9d; lpFilePart
0x1800246bb  xor     r8d, r8d; lpBuffer
0x1800246be  xor     edx, edx; nBufferLength
0x1800246c0  mov     rcx, rsi; lpFileName
0x1800246c3  call    cs:__imp_GetFullPathNameW
0x1800246c9  mov     ebx, eax
0x1800246cb  test    eax, eax
0x1800246cd  jnz     short loc_18002471B
0x1800246cf  mov     ebx, gs:68h
0x1800246d7  mov     eax, gs:68h
0x1800246df  test    eax, eax
0x1800246e1  jle     short loc_1800246EC
0x1800246e3  movzx   ebx, bx
0x1800246e6  or      ebx, 0C0070000h
0x1800246ec  test    ebx, ebx
0x1800246ee  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x1800246f5  mov     eax, 0C00000E5h
0x1800246fa  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x180024701  cmovns  ebx, eax
0x180024704  mov     r8d, 718h
0x18002470a  mov     ecx, r15d
0x18002470d  mov     dword ptr [rsp+110h+var_F0], ebx
0x180024711  call    AslLogCallPrintf
0x180024716  jmp     loc_18002496C
0x18002471b  mov     rcx, gs:60h
0x180024724  mov     r8, rbx
0x180024727  add     r8, r8; Size
0x18002472a  mov     edx, 8; Flags
0x18002472f  mov     rcx, [rcx+30h]; HeapHandle
0x180024733  call    cs:__imp_RtlAllocateHeap
0x180024739  mov     [rbp+57h+var_B8], rax
0x18002473d  mov     r13, rax
0x180024740  test    rax, rax
0x180024743  jnz     short loc_18002474F
0x180024745  mov     ebx, 0C0000017h
0x18002474a  jmp     loc_18002496C
0x18002474f  xor     r9d, r9d; lpFilePart
0x180024752  mov     r8, r13; lpBuffer
0x180024755  mov     edx, ebx; nBufferLength
0x180024757  mov     rcx, rsi; lpFileName
0x18002475a  call    cs:__imp_GetFullPathNameW
0x180024760  test    eax, eax
0x180024762  jnz     short loc_1800247B5
0x180024764  mov     ebx, gs:68h
0x18002476c  mov     eax, gs:68h
0x180024774  test    eax, eax
0x180024776  jle     short loc_180024781
0x180024778  movzx   ebx, bx
0x18002477b  or      ebx, 0C0070000h
0x180024781  test    ebx, ebx
0x180024783  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x18002478a  mov     eax, 0C00000E5h
0x18002478f  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x180024796  cmovns  ebx, eax
0x180024799  mov     r8d, 726h
0x18002479f  mov     ecx, r15d
0x1800247a2  mov     dword ptr [rsp+110h+var_F0], ebx
0x1800247a6  call    AslLogCallPrintf
0x1800247ab  mov     rsi, [rsp+110h+var_E0]
0x1800247b0  jmp     loc_1800248CD
0x1800247b5  mov     rsi, r13
0x1800247b8  mov     r14d, 0C0000034h
0x1800247be  mov     rcx, rsi
0x1800247c1  mov     ebx, r14d
0x1800247c4  call    AslPathGetFileNamePart
0x1800247c9  mov     [rbp+57h+var_68], rax
0x1800247cd  mov     r15, rax
0x1800247d0  cmp     rax, rsi
0x1800247d3  jz      loc_1800248C3
0x1800247d9  lea     rdi, [rax-4]
0x1800247dd  cmp     rdi, rsi
0x1800247e0  jb      loc_1800248BE
0x1800247e6  cmp     word ptr [rdi], 5Ch ; '\'
0x1800247ea  jz      short loc_1800247F2
0x1800247ec  cmp     word ptr [rdi], 2Fh ; '/'
0x1800247f0  jnz     short loc_18002480B
0x1800247f2  mov     r8d, 0Ah; MaxCount
0x1800247f8  lea     rdx, [rbp+57h+String2]; String2
0x1800247fc  mov     rcx, rdi; String1
0x1800247ff  call    _wcsnicmp_0
0x180024804  xor     r8d, r8d
0x180024807  test    eax, eax
0x180024809  jz      short loc_180024811
0x18002480b  sub     rdi, 2
0x18002480f  jmp     short loc_1800247DD
0x180024811  test    r15, r15
0x180024814  jz      loc_180024EA4
0x18002481a  mov     r13d, 7FFFFFFFh
0x180024820  mov     rax, r15
0x180024823  mov     edx, r13d
0x180024826  cmp     [rax], r8w
0x18002482a  jz      short loc_180024836
0x18002482c  add     rax, 2
0x180024830  sub     rdx, 1
0x180024834  jnz     short loc_180024826
0x180024836  mov     rax, rdx
0x180024839  mov     edi, 0C000000Dh
0x18002483e  neg     rax
0x180024841  mov     rcx, r13
0x180024844  mov     rax, rdx
0x180024847  sbb     ebx, ebx
0x180024849  sub     rcx, rdx
0x18002484c  not     ebx
0x18002484e  and     ebx, edi
0x180024850  neg     rax
0x180024853  sbb     rax, rax
0x180024856  and     rax, rcx
0x180024859  mov     [rbp+57h+var_70], rax
0x18002485d  test    rdx, rdx
0x180024860  jz      loc_180024EA9
0x180024866  cmp     [rbp+57h+var_CC], r8d
0x18002486a  jz      loc_18002499B
0x180024870  mov     r9, r15
0x180024873  mov     qword ptr [rsp+110h+var_F0], rax
0x180024878  mov     r8d, 0Dh
0x18002487e  lea     rdx, aStageddelete; "StagedDelete_"
0x180024885  lea     rcx, [rbp+57h+var_98]
0x180024889  call    SdbpSafeAllocAndConcatW
0x18002488e  mov     ebx, eax
0x180024890  test    eax, eax
0x180024892  jns     loc_180024995
0x180024898  mov     dword ptr [rsp+110h+var_F0], eax
0x18002489c  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x1800248a3  mov     r8d, 756h
0x1800248a9  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800248b0  mov     ecx, 1
0x1800248b5  call    AslLogCallPrintf
0x1800248ba  mov     r13, [rbp+57h+var_B8]
0x1800248be  mov     rdi, [rsp+110h+var_D8]
0x1800248c3  mov     rsi, [rsp+110h+var_E0]
0x1800248c8  test    r13, r13
0x1800248cb  jz      short loc_1800248E2
0x1800248cd  mov     rcx, gs:60h
0x1800248d6  mov     rdx, r13
0x1800248d9  mov     rcx, [rcx+30h]
0x1800248dd  call    AslFree
0x1800248e2  mov     rax, [rbp+57h+String1]
0x1800248e6  test    rax, rax
0x1800248e9  jz      short loc_180024900
0x1800248eb  mov     rcx, gs:60h
0x1800248f4  mov     rdx, rax
0x1800248f7  mov     rcx, [rcx+30h]
0x1800248fb  call    AslFree
0x180024900  test    rdi, rdi
0x180024903  jz      short loc_18002491A
0x180024905  mov     rcx, gs:60h
0x18002490e  mov     rdx, rdi
0x180024911  mov     rcx, [rcx+30h]
0x180024915  call    AslFree
0x18002491a  test    rsi, rsi
0x18002491d  jz      short loc_180024934
0x18002491f  mov     rcx, gs:60h
0x180024928  mov     rdx, rsi
0x18002492b  mov     rcx, [rcx+30h]
0x18002492f  call    AslFree
0x180024934  test    r12, r12
0x180024937  jz      short loc_18002494E
0x180024939  mov     rcx, gs:60h
0x180024942  mov     rdx, r12
0x180024945  mov     rcx, [rcx+30h]
0x180024949  call    AslFree
0x18002494e  mov     rax, [rbp+57h+var_98]
0x180024952  test    rax, rax
0x180024955  jz      short loc_18002496C
0x180024957  mov     rcx, gs:60h
0x180024960  mov     rdx, rax
0x180024963  mov     rcx, [rcx+30h]
0x180024967  call    AslFree
0x18002496c  mov     eax, ebx
0x18002496e  mov     rcx, [rbp+57h+var_40]
0x180024972  xor     rcx, rsp; StackCookie
0x180024975  call    __security_check_cookie
0x18002497a  mov     rbx, [rsp+110h+arg_10]
0x180024982  add     rsp, 0E0h
0x180024989  pop     r15
0x18002498b  pop     r14
0x18002498d  pop     r13
0x18002498f  pop     r12
0x180024991  pop     rdi
0x180024992  pop     rsi
0x180024993  pop     rbp
0x180024994  retn
0x180024995  mov     r12, [rbp+57h+var_98]
0x180024999  jmp     short loc_18002499E
0x18002499b  mov     r12, r15
0x18002499e  mov     r8d, 80000100h
0x1800249a4  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800249ab  lea     rcx, [rbp+57h+Handle]
0x1800249af  call    AslRegistryGetKey
0x1800249b4  mov     ebx, eax
0x1800249b6  test    eax, eax
0x1800249b8  jns     short loc_180024A0C
0x1800249ba  cmp     eax, r14d
0x1800249bd  jz      short loc_1800249E1
0x1800249bf  mov     dword ptr [rsp+110h+var_F0], eax
0x1800249c3  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1800249ca  mov     r8d, 767h
0x1800249d0  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800249d7  mov     ecx, 1
0x1800249dc  call    AslLogCallPrintf
0x1800249e1  mov     r12, [rbp+57h+var_C8]
0x1800249e5  mov     rdi, [rsp+110h+var_D8]
0x1800249ea  mov     rsi, [rsp+110h+var_E0]
0x1800249ef  mov     rcx, [rbp+57h+Handle]; Handle
0x1800249f3  lea     rax, [rcx-1]
0x1800249f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800249fb  ja      short loc_180024A03
0x1800249fd  call    cs:__imp_ZwClose
0x180024a03  mov     r13, [rbp+57h+var_B8]
0x180024a07  jmp     loc_1800248C8
0x180024a0c  mov     rdx, [rbp+57h+Handle]
0x180024a10  lea     rcx, [rbp+57h+String1]
0x180024a14  mov     r8, r12
0x180024a17  call    AslRegistryGetString
0x180024a1c  mov     ebx, eax
0x180024a1e  test    eax, eax
0x180024a20  js      short loc_1800249E1
0x180024a22  mov     rbx, [rbp+57h+String1]
0x180024a26  mov     rdx, r15; String2
0x180024a29  mov     rcx, rbx; String1
0x180024a2c  call    _wcsicmp_0
0x180024a31  xor     r15d, r15d
0x180024a34  test    eax, eax
  ... truncated ...
```
