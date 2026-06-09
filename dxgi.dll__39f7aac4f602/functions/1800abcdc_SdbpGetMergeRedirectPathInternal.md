# SdbpGetMergeRedirectPathInternal

- ea: `0x1800abcdc`
- end: `0x1800ac423`
- name: `SdbpGetMergeRedirectPathInternal`
- size: `1863`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800ab848`

## callees

- `0x18004130c`
- `0x180041774`
- `0x180041794`
- `0x1800419a0`
- `0x180041b98`
- `0x18004281c`
- `0x180042bc8`
- `0x18005c9c4`
- `0x18005d1f4`
- `0x18006f0a0`
- `0x1800710a8`
- `0x180075fa0`
- `0x180076e90`
- `0x180076e9c`
- `0x1800abcdc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800abe71`
- `ntdll!RtlAllocateHeap` at `0x1800abe71`
- `ntdll!ZwClose` at `0x1800ac112`
- `ntdll!ZwClose` at `0x1800ac112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abeac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abeb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abeac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800abeb6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800abdfb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800abe98`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800abdfb`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800abe98`

## string_xrefs

- `0x1800ac0c0`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1800ac0da`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`
- `0x1800ac381`: `Failed to get manifested stub [%x]`
- `0x1800abe2c`: `Failed to get full path size [%x]`
- `0x1800abec7`: `Failed to get full path [%x]`
- `0x1800abe38`: `SdbpGetMergeRedirectPathInternal`
- `0x1800abed3`: `SdbpGetMergeRedirectPathInternal`
- `0x1800abf6a`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac093`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac0eb`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac224`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac273`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac2e8`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac336`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac3ba`: `SdbpGetMergeRedirectPathInternal`
- `0x1800ac06c`: `StagedDelete_`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeRedirectPathInternal(_QWORD *a1, _DWORD *a2, int a3, unsigned __int64 a4)
{
  __int64 v6; // rsi
  signed int LastError; // ebx
  unsigned __int64 v9; // rax
  BOOL v10; // ecx
  bool v11; // zf
  WCHAR *v12; // r12
  DWORD FullPathNameW; // eax
  DWORD v14; // ebx
  WCHAR *Heap; // rax
  __int64 v16; // r14
  __int64 FileNamePart; // rax
  const wchar_t *v18; // r15
  const wchar_t *i; // rsi
  __int64 v20; // rdx
  int v21; // eax
  unsigned __int64 v22; // r12
  int v23; // eax
  const wchar_t *v24; // rsi
  int Key; // eax
  const char *v26; // r9
  __int64 v27; // r8
  wchar_t *v28; // rbx
  unsigned int v29; // esi
  __int64 v30; // rdx
  int v31; // eax
  int FileTimestamp; // eax
  __int64 v33; // r8
  const char *v34; // r9
  int v35; // eax
  __int64 v36; // [rsp+20h] [rbp-89h]
  __int64 v37; // [rsp+20h] [rbp-89h]
  __int64 v38; // [rsp+30h] [rbp-79h] BYREF
  __int64 v39; // [rsp+38h] [rbp-71h]
  unsigned int v40; // [rsp+40h] [rbp-69h] BYREF
  int v41; // [rsp+44h] [rbp-65h]
  HANDLE Handle; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v43; // [rsp+50h] [rbp-59h] BYREF
  WCHAR *v44; // [rsp+58h] [rbp-51h]
  wchar_t *String1; // [rsp+60h] [rbp-49h] BYREF
  __int64 v46; // [rsp+68h] [rbp-41h] BYREF
  __int64 v47; // [rsp+70h] [rbp-39h] BYREF
  const wchar_t *v48; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int64 v49; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v50; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int64 v51; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int64 v52; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v53; // [rsp+A0h] [rbp-9h] BYREF
  _QWORD *v54; // [rsp+A8h] [rbp-1h]
  wchar_t String2[12]; // [rsp+B0h] [rbp+7h] BYREF

  v41 = a3;
  v54 = a1;
  v6 = 0;
  v40 = 0;
  Handle = 0;
  String1 = 0;
  v50 = 0;
  v49 = 0;
  v43 = 0;
  v39 = 0;
  v46 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v38 = 0;
  v47 = 0;
  v48 = 0;
  wcscpy(String2, L"\\AppPach\\");
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( a2 && a3 )
    *a2 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
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
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1816, "Failed to get full path size [%x]", LastError);
          return (unsigned int)LastError;
        }
        Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * FullPathNameW);
        v44 = Heap;
        v12 = Heap;
        if ( !Heap )
          return (unsigned int)-1073741801;
        if ( !GetFullPathNameW((LPCWSTR)a4, v14, Heap, 0) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            LastError = GetLastError();
          if ( LastError >= 0 )
            LastError = -1073741595;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1830, "Failed to get full path [%x]", LastError);
          v16 = v38;
          goto LABEL_45;
        }
        a4 = (unsigned __int64)v12;
LABEL_33:
        LastError = -1073741772;
        FileNamePart = AslPathGetFileNamePart(a4);
        v18 = (const wchar_t *)FileNamePart;
        if ( FileNamePart == a4 )
        {
LABEL_43:
          v16 = v38;
          goto LABEL_44;
        }
        for ( i = (const wchar_t *)(FileNamePart - 4); ; --i )
        {
          if ( (unsigned __int64)i < a4 )
            goto LABEL_42;
          if ( (*i == 92 || *i == 47) && !wcsnicmp(i, String2, 0xAu) )
            break;
        }
        v21 = RtlStringCchLengthW(v18, v20, &v49);
        LastError = v21;
        if ( v21 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1866, "RtlStringCchLengthW failed [%x]", v21);
LABEL_42:
          v6 = v39;
          goto LABEL_43;
        }
        v22 = v49;
        if ( v41 )
        {
          v23 = SdbpSafeAllocAndConcatW((unsigned int)&v48, (unsigned int)L"StagedDelete_", 13, (_DWORD)v18, v49);
          LastError = v23;
          if ( v23 < 0 )
          {
            AslLogCallPrintf(
              1,
              "SdbpGetMergeRedirectPathInternal",
              1878,
              "Failed to alloc and cat file to prefix [%x]",
              v23);
            v6 = v39;
            v12 = v44;
            goto LABEL_43;
          }
          v24 = v48;
        }
        else
        {
          v24 = v18;
        }
        Key = AslRegistryGetKey(
                &Handle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
                2147483904LL);
        LastError = Key;
        if ( Key < 0 )
        {
          if ( Key == -1073741772 )
          {
LABEL_66:
            v6 = v39;
LABEL_67:
            v16 = v38;
LABEL_68:
            if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              ZwClose(Handle);
            v12 = v44;
LABEL_44:
            if ( !v12 )
            {
LABEL_46:
              if ( String1 )
                AslFree(NtCurrentPeb()->ProcessHeap, String1);
              if ( v6 )
                AslFree(NtCurrentPeb()->ProcessHeap, v6);
              if ( v16 )
                AslFree(NtCurrentPeb()->ProcessHeap, v16);
              if ( v47 )
                AslFree(NtCurrentPeb()->ProcessHeap, v47);
              if ( v48 )
                AslFree(NtCurrentPeb()->ProcessHeap, v48);
              return (unsigned int)LastError;
            }
LABEL_45:
            AslFree(NtCurrentPeb()->ProcessHeap, v12);
            goto LABEL_46;
          }
          v26 = "AslRegistryGetKey failed to open SdbUpdates key [%x]";
          v27 = 1895;
LABEL_65:
          LODWORD(v36) = Key;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v27, v26, v36);
          goto LABEL_66;
        }
        LastError = AslRegistryGetString(&String1, Handle, v24);
        if ( LastError < 0 )
          goto LABEL_66;
        v28 = String1;
        if ( !wcsicmp(String1, v18) )
        {
          LastError = -1073741772;
          goto LABEL_66;
        }
        if ( v41 && !wcsicmp(v28, L"__NotRedirected__") && a2 )
        {
          *a2 = 1;
          LastError = 0;
          goto LABEL_66;
        }
        Key = SdbpSafeAllocAndConcatW((unsigned int)&v47, (unsigned int)L"MergeVer_", 9, (_DWORD)v24, 0);
        LastError = Key;
        if ( Key < 0 )
        {
          v26 = "Failed to alloc and cat file to prefix [%x]";
          v27 = 1929;
          goto LABEL_65;
        }
        Key = AslRegistryGetUInt32(&v43, Handle, v47);
        LastError = Key;
        if ( Key == -1073741772 )
        {
          v29 = 0;
        }
        else
        {
          if ( Key < 0 )
          {
            v26 = "Failed to query reg value. [%x]";
            v27 = 1938;
            goto LABEL_65;
          }
          v29 = v43;
        }
        Key = AslRegistryGetUInt32(&v40, Handle, L"MergeVer");
        LastError = Key;
        if ( Key < 0 )
        {
          v26 = "Failed to query reg value. [%x]";
          v27 = 1944;
          goto LABEL_65;
        }
        if ( v40 < v29 )
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1953,
            "Merge target is too high of a version, this code might not handle it correctly.");
        Key = AslRegistryGetUInt32(&v40, Handle, L"MinMergeVer");
        LastError = Key;
        if ( Key < 0 )
        {
          v26 = "Failed to query reg value. [%x]";
          v27 = 1959;
          goto LABEL_65;
        }
        if ( v29 < v40 )
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1968,
            "Merge target is too low of a version, it might not be possible to handle correctly.");
        Key = RtlStringCchLengthW(a4, v30, &v50);
        LastError = Key;
        if ( Key < 0 )
        {
          v26 = "RtlStringCchLengthW failed [%x]";
          v27 = 1975;
          goto LABEL_65;
        }
        if ( v50 < v22 )
        {
          LastError = -1073741675;
          LODWORD(v36) = -1073741675;
          AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 1982, "RtlSizeTSub failed [%x]", v36);
          goto LABEL_66;
        }
        v31 = SdbpSafeAllocAndConcatW((unsigned int)&v46, a4, (int)v50 - (int)v22, (_DWORD)String1, 0);
        LastError = v31;
        if ( v31 < 0 )
        {
          AslLogCallPrintf(
            1,
            "SdbpGetMergeRedirectPathInternal",
            1992,
            "Failed to alloc and cat file to prefix [%x]",
            v31);
          v6 = v46;
          goto LABEL_67;
        }
        v6 = v46;
        FileTimestamp = SdbpGetFileTimestamp(&v51, v46, 1);
        LastError = FileTimestamp;
        if ( FileTimestamp >= 0 )
        {
          FileTimestamp = SdbpGetFileTimestamp(&v52, a4, 0);
          LastError = FileTimestamp;
          if ( FileTimestamp >= 0 )
          {
            FileTimestamp = SdbpGetManifestedMergeStubAlloc(&v38, v18);
            LastError = FileTimestamp;
            if ( FileTimestamp == -1073741772 )
            {
              v16 = v38;
            }
            else
            {
              if ( FileTimestamp < 0 )
              {
                v34 = "Failed to get manifested stub [%x]";
                v33 = 2028;
                goto LABEL_102;
              }
              v16 = v38;
              v35 = SdbpGetFileTimestamp(&v53, v38, 0);
              LastError = v35;
              if ( v35 < 0 )
              {
                AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", 2038, "Failed to check timestamp [%x]", v35);
                goto LABEL_68;
              }
            }
            if ( v51 < v52 || v51 < v53 )
            {
              LastError = -1073741772;
            }
            else
            {
              *v54 = v6;
              if ( a2 && v41 )
                *a2 = 1;
              v6 = 0;
              LastError = 0;
            }
            goto LABEL_68;
          }
          v33 = 2014;
        }
        else
        {
          if ( FileTimestamp == -1073741772 )
            goto LABEL_67;
          v33 = 2003;
        }
        v34 = "Failed to check timestamp [%x]";
LABEL_102:
        LODWORD(v37) = FileTimestamp;
        AslLogCallPrintf(1, "SdbpGetMergeRedirectPathInternal", v33, v34, v37);
        goto LABEL_67;
      }
    }
    else if ( *(_WORD *)(a4 + 2) == 58 )
    {
      v10 = *(_WORD *)(a4 + 4) == 92;
    }
    v11 = *(_WORD *)a4 == 92;
    v12 = 0;
    v44 = 0;
    if ( v10 || v11 )
      goto LABEL_33;
    goto LABEL_16;
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x1800abcdc  mov     [rsp-8+arg_10], rbx
0x1800abce1  push    rbp
0x1800abce2  push    rsi
0x1800abce3  push    rdi
0x1800abce4  push    r12
0x1800abce6  push    r13
0x1800abce8  push    r14
0x1800abcea  push    r15
0x1800abcec  lea     rbp, [rsp-27h]
0x1800abcf1  sub     rsp, 0D0h
0x1800abcf8  mov     rax, cs:__security_cookie
0x1800abcff  xor     rax, rsp
0x1800abd02  mov     [rbp+57h+var_38], rax
0x1800abd06  movups  xmm0, xmmword ptr cs:aApppatch; "\\AppPatch\\"
0x1800abd0d  xor     edi, edi
0x1800abd0f  mov     eax, r8d
0x1800abd12  movsd   xmm1, qword ptr cs:aApppatch+0Eh; "ch\\"
0x1800abd1a  mov     r14, r9
0x1800abd1d  mov     [rbp+57h+var_BC], eax
0x1800abd20  mov     r13, rdx
0x1800abd23  mov     [rbp+57h+var_58], rcx
0x1800abd27  mov     esi, edi
0x1800abd29  mov     [rbp+57h+var_C0], edi
0x1800abd2c  mov     [rbp+57h+Handle], rdi
0x1800abd30  mov     [rbp+57h+String1], rdi
0x1800abd34  mov     [rbp+57h+var_78], rdi
0x1800abd38  mov     [rbp+57h+var_80], rdi
0x1800abd3c  mov     [rbp+57h+var_B0], edi
0x1800abd3f  mov     [rbp+57h+var_C8], rdi
0x1800abd43  mov     [rbp+57h+var_98], rdi
0x1800abd47  mov     [rbp+57h+var_70], rdi
0x1800abd4b  mov     [rbp+57h+var_68], rdi
0x1800abd4f  mov     [rbp+57h+var_60], rdi
0x1800abd53  mov     [rbp+57h+var_D0], rdi
0x1800abd57  mov     [rbp+57h+var_90], rdi
0x1800abd5b  mov     [rbp+57h+var_88], rdi
0x1800abd5f  movups  xmmword ptr [rbp+57h+String2], xmm0
0x1800abd63  movsd   qword ptr [rbp+57h+String2+0Eh], xmm1
0x1800abd68  test    rcx, rcx
0x1800abd6b  jnz     short loc_1800ABD77
0x1800abd6d  mov     eax, 0C00000EFh
0x1800abd72  jmp     loc_1800AC02D
0x1800abd77  mov     [rcx], rdi
0x1800abd7a  test    r13, r13
0x1800abd7d  jz      short loc_1800ABD85
0x1800abd7f  test    eax, eax
0x1800abd81  jz      short loc_1800ABD85
0x1800abd83  mov     [rdx], edi
0x1800abd85  call    SdbpGetMergeSdbsSupported
0x1800abd8a  test    eax, eax
0x1800abd8c  jnz     short loc_1800ABD98
0x1800abd8e  mov     ebx, 0C0000034h
0x1800abd93  jmp     loc_1800AC02B
0x1800abd98  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800abd9c  inc     rax
0x1800abd9f  cmp     [r14+rax*2], di
0x1800abda4  jnz     short loc_1800ABD9C
0x1800abda6  mov     r15d, 1
0x1800abdac  mov     ecx, edi
0x1800abdae  cmp     rax, 3
0x1800abdb2  jbe     short loc_1800ABDC9
0x1800abdb4  cmp     word ptr [r14+2], 3Ah ; ':'
0x1800abdba  jnz     short loc_1800ABDCE
0x1800abdbc  cmp     word ptr [r14+4], 5Ch ; '\'
0x1800abdc2  jnz     short loc_1800ABDCE
0x1800abdc4  mov     ecx, r15d
0x1800abdc7  jmp     short loc_1800ABDCE
0x1800abdc9  cmp     rax, r15
0x1800abdcc  jbe     short loc_1800ABDF0
0x1800abdce  cmp     word ptr [r14], 5Ch ; '\'
0x1800abdd3  mov     eax, edi
0x1800abdd5  mov     r12, rdi
0x1800abdd8  mov     [rbp+57h+var_A8], rdi
0x1800abddc  cmovz   eax, r15d
0x1800abde0  test    ecx, ecx
0x1800abde2  jnz     loc_1800ABEFB
0x1800abde8  test    eax, eax
0x1800abdea  jnz     loc_1800ABEFB
0x1800abdf0  xor     r9d, r9d; lpFilePart
0x1800abdf3  xor     r8d, r8d; lpBuffer
0x1800abdf6  xor     edx, edx; nBufferLength
0x1800abdf8  mov     rcx, r14; lpFileName
0x1800abdfb  call    cs:__imp_GetFullPathNameW
0x1800abe01  mov     ebx, eax
0x1800abe03  test    eax, eax
0x1800abe05  jnz     short loc_1800ABE59
0x1800abe07  call    cs:__imp_GetLastError
0x1800abe0d  test    eax, eax
0x1800abe0f  jg      short loc_1800ABE1B
0x1800abe11  call    cs:__imp_GetLastError
0x1800abe17  mov     ebx, eax
0x1800abe19  jmp     short loc_1800ABE2A
0x1800abe1b  call    cs:__imp_GetLastError
0x1800abe21  movzx   ebx, ax
0x1800abe24  or      ebx, 0C0070000h
0x1800abe2a  test    ebx, ebx
0x1800abe2c  lea     r9, aFailedToGetFul; "Failed to get full path size [%x]"
0x1800abe33  mov     eax, 0C00000E5h
0x1800abe38  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800abe3f  cmovns  ebx, eax
0x1800abe42  mov     r8d, 718h
0x1800abe48  mov     ecx, r15d
0x1800abe4b  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800abe4f  call    AslLogCallPrintf
0x1800abe54  jmp     loc_1800AC02B
0x1800abe59  mov     rcx, gs:60h
0x1800abe62  mov     r8, rbx
0x1800abe65  add     r8, r8; Size
0x1800abe68  mov     edx, 8; Flags
0x1800abe6d  mov     rcx, [rcx+30h]; HeapHandle
0x1800abe71  call    cs:__imp_RtlAllocateHeap
0x1800abe77  mov     [rbp+57h+var_A8], rax
0x1800abe7b  mov     r12, rax
0x1800abe7e  test    rax, rax
0x1800abe81  jnz     short loc_1800ABE8D
0x1800abe83  mov     ebx, 0C0000017h
0x1800abe88  jmp     loc_1800AC02B
0x1800abe8d  xor     r9d, r9d; lpFilePart
0x1800abe90  mov     r8, r12; lpBuffer
0x1800abe93  mov     edx, ebx; nBufferLength
0x1800abe95  mov     rcx, r14; lpFileName
0x1800abe98  call    cs:__imp_GetFullPathNameW
0x1800abe9e  test    eax, eax
0x1800abea0  jnz     short loc_1800ABEF8
0x1800abea2  call    cs:__imp_GetLastError
0x1800abea8  test    eax, eax
0x1800abeaa  jg      short loc_1800ABEB6
0x1800abeac  call    cs:__imp_GetLastError
0x1800abeb2  mov     ebx, eax
0x1800abeb4  jmp     short loc_1800ABEC5
0x1800abeb6  call    cs:__imp_GetLastError
0x1800abebc  movzx   ebx, ax
0x1800abebf  or      ebx, 0C0070000h
0x1800abec5  test    ebx, ebx
0x1800abec7  lea     r9, aFailedToGetFul_0; "Failed to get full path [%x]"
0x1800abece  mov     eax, 0C00000E5h
0x1800abed3  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800abeda  cmovns  ebx, eax
0x1800abedd  mov     r8d, 726h
0x1800abee3  mov     ecx, r15d
0x1800abee6  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800abeea  call    AslLogCallPrintf
0x1800abeef  mov     r14, [rbp+57h+var_D0]
0x1800abef3  jmp     loc_1800ABF88
0x1800abef8  mov     r14, r12
0x1800abefb  mov     edi, 0C0000034h
0x1800abf00  mov     rcx, r14
0x1800abf03  mov     ebx, edi
0x1800abf05  call    AslPathGetFileNamePart
0x1800abf0a  mov     r15, rax
0x1800abf0d  cmp     rax, r14
0x1800abf10  jz      short loc_1800ABF7F
0x1800abf12  lea     rsi, [rax-4]
0x1800abf16  cmp     rsi, r14
0x1800abf19  jb      short loc_1800ABF7B
0x1800abf1b  cmp     word ptr [rsi], 5Ch ; '\'
0x1800abf1f  jz      short loc_1800ABF27
0x1800abf21  cmp     word ptr [rsi], 2Fh ; '/'
0x1800abf25  jnz     short loc_1800ABF3D
0x1800abf27  mov     r8d, 0Ah; MaxCount
0x1800abf2d  lea     rdx, [rbp+57h+String2]; String2
0x1800abf31  mov     rcx, rsi; String1
0x1800abf34  call    _wcsnicmp
0x1800abf39  test    eax, eax
0x1800abf3b  jz      short loc_1800ABF43
0x1800abf3d  sub     rsi, 2
0x1800abf41  jmp     short loc_1800ABF16
0x1800abf43  lea     r8, [rbp+57h+var_80]
0x1800abf47  mov     rcx, r15
0x1800abf4a  call    RtlStringCchLengthW
0x1800abf4f  mov     ebx, eax
0x1800abf51  test    eax, eax
0x1800abf53  jns     loc_1800AC054
0x1800abf59  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x1800abf60  mov     dword ptr [rsp+100h+var_E0], eax
0x1800abf64  mov     r8d, 74Ah
0x1800abf6a  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800abf71  mov     ecx, 1
0x1800abf76  call    AslLogCallPrintf
0x1800abf7b  mov     rsi, [rbp+57h+var_C8]
0x1800abf7f  mov     r14, [rbp+57h+var_D0]
0x1800abf83  test    r12, r12
0x1800abf86  jz      short loc_1800ABF9D
0x1800abf88  mov     rcx, gs:60h
0x1800abf91  mov     rdx, r12
0x1800abf94  mov     rcx, [rcx+30h]
0x1800abf98  call    AslFree
0x1800abf9d  mov     rax, [rbp+57h+String1]
0x1800abfa1  test    rax, rax
0x1800abfa4  jz      short loc_1800ABFBB
0x1800abfa6  mov     rcx, gs:60h
0x1800abfaf  mov     rdx, rax
0x1800abfb2  mov     rcx, [rcx+30h]
0x1800abfb6  call    AslFree
0x1800abfbb  test    rsi, rsi
0x1800abfbe  jz      short loc_1800ABFD5
0x1800abfc0  mov     rcx, gs:60h
0x1800abfc9  mov     rdx, rsi
0x1800abfcc  mov     rcx, [rcx+30h]
0x1800abfd0  call    AslFree
0x1800abfd5  test    r14, r14
0x1800abfd8  jz      short loc_1800ABFEF
0x1800abfda  mov     rcx, gs:60h
0x1800abfe3  mov     rdx, r14
0x1800abfe6  mov     rcx, [rcx+30h]
0x1800abfea  call    AslFree
0x1800abfef  mov     rax, [rbp+57h+var_90]
0x1800abff3  test    rax, rax
0x1800abff6  jz      short loc_1800AC00D
0x1800abff8  mov     rcx, gs:60h
0x1800ac001  mov     rdx, rax
0x1800ac004  mov     rcx, [rcx+30h]
0x1800ac008  call    AslFree
0x1800ac00d  mov     rax, [rbp+57h+var_88]
0x1800ac011  test    rax, rax
0x1800ac014  jz      short loc_1800AC02B
0x1800ac016  mov     rcx, gs:60h
0x1800ac01f  mov     rdx, rax
0x1800ac022  mov     rcx, [rcx+30h]
0x1800ac026  call    AslFree
0x1800ac02b  mov     eax, ebx
0x1800ac02d  mov     rcx, [rbp+57h+var_38]
0x1800ac031  xor     rcx, rsp; StackCookie
0x1800ac034  call    __security_check_cookie
0x1800ac039  mov     rbx, [rsp+100h+arg_10]
0x1800ac041  add     rsp, 0D0h
0x1800ac048  pop     r15
0x1800ac04a  pop     r14
0x1800ac04c  pop     r13
0x1800ac04e  pop     r12
0x1800ac050  pop     rdi
0x1800ac051  pop     rsi
0x1800ac052  pop     rbp
0x1800ac053  retn
0x1800ac054  cmp     [rbp+57h+var_BC], 0
0x1800ac058  mov     r12, [rbp+57h+var_80]
0x1800ac05c  jz      short loc_1800AC0B7
0x1800ac05e  mov     r9, r15
0x1800ac061  mov     [rsp+100h+var_E0], r12
0x1800ac066  mov     r8d, 0Dh
0x1800ac06c  lea     rdx, aStageddelete; "StagedDelete_"
0x1800ac073  lea     rcx, [rbp+57h+var_88]
0x1800ac077  call    SdbpSafeAllocAndConcatW
0x1800ac07c  mov     ebx, eax
0x1800ac07e  test    eax, eax
0x1800ac080  jns     short loc_1800AC0B1
0x1800ac082  lea     r9, aFailedToAllocA; "Failed to alloc and cat file to prefix "...
0x1800ac089  mov     dword ptr [rsp+100h+var_E0], eax
0x1800ac08d  mov     r8d, 756h
0x1800ac093  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800ac09a  mov     ecx, 1
0x1800ac09f  call    AslLogCallPrintf
0x1800ac0a4  mov     rsi, [rbp+57h+var_C8]
0x1800ac0a8  mov     r12, [rbp+57h+var_A8]
0x1800ac0ac  jmp     loc_1800ABF7F
0x1800ac0b1  mov     rsi, [rbp+57h+var_88]
0x1800ac0b5  jmp     short loc_1800AC0BA
0x1800ac0b7  mov     rsi, r15
0x1800ac0ba  mov     r8d, 80000100h
0x1800ac0c0  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800ac0c7  lea     rcx, [rbp+57h+Handle]
0x1800ac0cb  call    AslRegistryGetKey
0x1800ac0d0  mov     ebx, eax
0x1800ac0d2  test    eax, eax
0x1800ac0d4  jns     short loc_1800AC121
0x1800ac0d6  cmp     eax, edi
0x1800ac0d8  jz      short loc_1800AC0FC
0x1800ac0da  lea     r9, aAslregistryget_3; "AslRegistryGetKey failed to open SdbUpd"...
0x1800ac0e1  mov     r8d, 767h
0x1800ac0e7  mov     dword ptr [rsp+100h+var_E0], eax
0x1800ac0eb  lea     rdx, aSdbpgetmergere; "SdbpGetMergeRedirectPathInternal"
0x1800ac0f2  mov     ecx, 1
0x1800ac0f7  call    AslLogCallPrintf
0x1800ac0fc  mov     rsi, [rbp+57h+var_C8]
0x1800ac100  mov     r14, [rbp+57h+var_D0]
0x1800ac104  mov     rcx, [rbp+57h+Handle]; Handle
0x1800ac108  lea     rax, [rcx-1]
0x1800ac10c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ac110  ja      short loc_1800AC118
0x1800ac112  call    cs:__imp_ZwClose
0x1800ac118  mov     r12, [rbp+57h+var_A8]
0x1800ac11c  jmp     loc_1800ABF83
0x1800ac121  mov     rdx, [rbp+57h+Handle]
0x1800ac125  lea     rcx, [rbp+57h+String1]
0x1800ac129  mov     r8, rsi
0x1800ac12c  call    AslRegistryGetString
0x1800ac131  mov     ebx, eax
0x1800ac133  test    eax, eax
0x1800ac135  js      short loc_1800AC0FC
0x1800ac137  mov     rbx, [rbp+57h+String1]
0x1800ac13b  mov     rdx, r15; String2
0x1800ac13e  mov     rcx, rbx; String1
0x1800ac141  call    _wcsicmp
0x1800ac146  test    eax, eax
0x1800ac148  jnz     short loc_1800AC14E
0x1800ac14a  mov     ebx, edi
0x1800ac14c  jmp     short loc_1800AC0FC
0x1800ac14e  cmp     [rbp+57h+var_BC], 0
0x1800ac152  jz      short loc_1800AC178
0x1800ac154  lea     rdx, aNotredirected; "__NotRedirected__"
  ... truncated ...
```
