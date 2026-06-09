# SdbpGetManifestedMergeStubAlloc

- ea: `0x18001f4e4`
- end: `0x18001f9b4`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1232`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800231b4`
- `0x1800245a0`

## callees

- `0x18001ee64`
- `0x18001ef20`
- `0x18001f028`
- `0x18001f4e4`
- `0x180021144`
- `0x1800212e4`
- `0x1800214b4`
- `0x180021764`
- `0x18005c3a8`
- `0x18005c414`
- `0x18007c010`

## import_xrefs

- `ntdll!ZwClose` at `0x18001f7d4`
- `ntdll!ZwClose` at `0x18001f7d4`
- `ntdll!ZwEnumerateValueKey` at `0x18001f60a`
- `ntdll!ZwEnumerateValueKey` at `0x18001f676`
- `ntdll!ZwEnumerateValueKey` at `0x18001f60a`
- `ntdll!ZwEnumerateValueKey` at `0x18001f676`
- `ntdll!RtlAllocateHeap` at `0x18001f5ce`
- `ntdll!RtlAllocateHeap` at `0x18001f64a`
- `ntdll!RtlAllocateHeap` at `0x18001f5ce`
- `ntdll!RtlAllocateHeap` at `0x18001f64a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f85f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f85f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f875`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f875`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f847`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001f847`

## string_xrefs

- `0x18001f555`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x18001f702`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001f7ec`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001f8ad`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001f8de`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001f987`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001f6f5`: `Failed to allocate or convert stub path.`
- `0x18001f835`: `ntdll.dll`
- `0x18001f89c`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x18001f96b`: `Failed to allocate stub path.`
- `0x18001f954`: `Failed to duplicate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  __int64 v3; // rsi
  NTSTATUS MergeSdbsDisabled; // ebx
  const wchar_t *Heap; // r12
  wchar_t *v6; // r13
  int Key; // eax
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rax
  ULONG Length; // ebx
  ULONG v12; // r12d
  wchar_t *v13; // rax
  NTSTATUS v14; // eax
  ULONG v15; // ebx
  unsigned __int64 v16; // r15
  __int64 v17; // rbx
  size_t v18; // r8
  const char *v19; // r9
  int v20; // r8d
  __int64 v22; // rax
  HMODULE Library; // rax
  HMODULE v24; // rsi
  __int64 (*ProcAddress)(void); // rax
  const char *v26; // r9
  int v27; // r8d
  const wchar_t *KeyValueInformation; // [rsp+30h] [rbp-20h]
  __int64 v29; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  ULONG v33; // [rsp+A8h] [rbp+58h] BYREF

  v33 = 0;
  v3 = 0;
  ResultLength = 0;
  v29 = 0;
  KeyHandle[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( !(unsigned int)SdbpGetMergeSdbsSupported() )
    return (unsigned int)-1073741772;
  MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v33);
  if ( MergeSdbsDisabled < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpGetManifestedMergeStubAlloc",
      1186,
      (unsigned int)"SdbpGetMergeSdbsDisabled failed [%x]");
    return (unsigned int)MergeSdbsDisabled;
  }
  if ( v33 )
    return (unsigned int)-1073741772;
  Heap = 0;
  v6 = 0;
  Key = AslRegistryGetKey(
          KeyHandle,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
          2147483904LL);
  MergeSdbsDisabled = Key;
  if ( Key < 0 )
  {
    if ( Key != -1073741772 )
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpGetManifestedMergeStubAlloc",
        1202,
        (unsigned int)"AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]");
    goto LABEL_27;
  }
  v8 = 1;
  while ( wcsicmp_0(a2, (const wchar_t *)qword_18007D038[4 * v8]) )
  {
    if ( (int)++v8 >= 10 )
    {
LABEL_14:
      MergeSdbsDisabled = -1073741772;
      goto LABEL_27;
    }
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  Length = 2 * v10 + 18;
  v33 = Length;
  Heap = (const wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
  KeyValueInformation = Heap;
  if ( !Heap )
  {
    MergeSdbsDisabled = -1073741801;
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpGetManifestedMergeStubAlloc",
      1222,
      (unsigned int)"Failed to allocate partial info.");
    goto LABEL_27;
  }
  v12 = 0;
  v13 = (wchar_t *)KeyValueInformation;
  while ( 1 )
  {
    v14 = ZwEnumerateValueKey(KeyHandle[0], v12, KeyValuePartialInformation, v13, Length, &ResultLength);
    MergeSdbsDisabled = v14;
    if ( v14 == -2147483622 )
    {
      Heap = KeyValueInformation;
      goto LABEL_14;
    }
    if ( v14 == -2147483643 || v14 == -1073741789 )
      goto LABEL_59;
    if ( v14 < 0 )
    {
      v26 = "Failed to query partial info.";
      v27 = 1241;
      goto LABEL_68;
    }
    v13 = (wchar_t *)KeyValueInformation;
    if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
      break;
LABEL_60:
    Length = v33;
    ++v12;
  }
  if ( wcsicmp_0(a2, KeyValueInformation + 6) )
  {
LABEL_59:
    v13 = (wchar_t *)KeyValueInformation;
    goto LABEL_60;
  }
  v22 = -1;
  do
    ++v22;
  while ( a2[v22] );
  v15 = 2 * v22 + 538;
  v16 = v15;
  v6 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v15);
  if ( v6 )
  {
    MergeSdbsDisabled = ZwEnumerateValueKey(KeyHandle[0], v12, KeyValueBasicInformation, v6, v15, &ResultLength);
    if ( MergeSdbsDisabled < 0 )
    {
      v26 = "Failed to query basic info.";
      v27 = 1269;
    }
    else if ( (unsigned __int64)ResultLength + 2 > v16 )
    {
      MergeSdbsDisabled = -1073741789;
      v26 = "Buffer too small to query basic info.";
      v27 = 1274;
    }
    else
    {
      v17 = (__int64)Src;
      if ( !Src )
      {
        v17 = 2147352624;
        Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
        v24 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
          if ( ProcAddress )
            v17 = ProcAddress();
          FreeLibrary(v24);
        }
        Src = (wchar_t *)v17;
      }
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v17 + 2 * v18) );
      if ( wcsnicmp_0((const wchar_t *)v17, v6 + 6, v18) )
      {
        MergeSdbsDisabled = AslStringDuplicate(&v29, v6 + 6);
        if ( MergeSdbsDisabled < 0 )
        {
          v19 = "Failed to duplicate stub path.";
          v20 = 1301;
          goto LABEL_25;
        }
      }
      else
      {
        do
          ++v9;
        while ( *(_WORD *)(v17 + 2 * v9) );
        MergeSdbsDisabled = AslPathToSystemPath(&v29, &v6[v9 + 6]);
        if ( MergeSdbsDisabled < 0 )
        {
          v19 = "Failed to allocate or convert stub path.";
          v20 = 1294;
LABEL_25:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v20, (_DWORD)v19);
          v3 = v29;
          goto LABEL_26;
        }
      }
      v3 = v29;
      if ( v29 )
      {
        MergeSdbsDisabled = 0;
        *a1 = v29;
        v3 = 0;
        goto LABEL_26;
      }
      MergeSdbsDisabled = -1073741801;
      v26 = "Failed to allocate stub path.";
      v27 = 1308;
    }
  }
  else
  {
    MergeSdbsDisabled = -1073741801;
    v26 = "Failed to allocate basic info.";
    v27 = 1258;
  }
LABEL_68:
  AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v27, (_DWORD)v26);
LABEL_26:
  Heap = KeyValueInformation;
LABEL_27:
  if ( (unsigned __int64)KeyHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    ZwClose(KeyHandle[0]);
  if ( v3 )
    AslFree(NtCurrentPeb()->ProcessHeap, v3);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  if ( v6 )
    AslFree(NtCurrentPeb()->ProcessHeap, v6);
  return (unsigned int)MergeSdbsDisabled;
}

```

## disassembly

```asm
0x18001f4e4  mov     [rsp-38h+arg_8], rbx
0x18001f4e9  mov     [rsp-38h+arg_0], rcx
0x18001f4ee  push    rbp
0x18001f4ef  push    rsi
0x18001f4f0  push    rdi
0x18001f4f1  push    r12
0x18001f4f3  push    r13
0x18001f4f5  push    r14
0x18001f4f7  push    r15
0x18001f4f9  mov     rbp, rsp
0x18001f4fc  sub     rsp, 50h
0x18001f500  xor     r14d, r14d
0x18001f503  mov     r15, rdx
0x18001f506  mov     [rbp+arg_18], r14d
0x18001f50a  mov     esi, r14d
0x18001f50d  mov     [rbp+arg_10], r14d
0x18001f511  mov     [rbp+var_18], r14
0x18001f515  mov     [rbp+KeyHandle], r14
0x18001f519  test    rcx, rcx
0x18001f51c  jz      loc_18001F887
0x18001f522  mov     [rcx], r14
0x18001f525  call    SdbpGetMergeSdbsSupported
0x18001f52a  test    eax, eax
0x18001f52c  jz      loc_18001F8C3
0x18001f532  lea     rcx, [rbp+arg_18]
0x18001f536  call    SdbpGetMergeSdbsDisabled
0x18001f53b  mov     ebx, eax
0x18001f53d  test    eax, eax
0x18001f53f  js      loc_18001F8CD
0x18001f545  cmp     [rbp+arg_18], r14d
0x18001f549  jnz     loc_18001F8C3
0x18001f54f  mov     r8d, 80000100h
0x18001f555  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001f55c  lea     rcx, [rbp+KeyHandle]
0x18001f560  mov     r12d, r14d
0x18001f563  mov     r13d, r14d
0x18001f566  call    AslRegistryGetKey
0x18001f56b  mov     ebx, eax
0x18001f56d  test    eax, eax
0x18001f56f  js      loc_18001F891
0x18001f575  lea     edi, [r14+1]
0x18001f579  mov     ebx, edi
0x18001f57b  lea     rax, qword_18007D038
0x18001f582  mov     edx, ebx
0x18001f584  shl     rdx, 5
0x18001f588  mov     rcx, r15; String1
0x18001f58b  mov     rdx, [rdx+rax]; String2
0x18001f58f  call    _wcsicmp_0
0x18001f594  test    eax, eax
0x18001f596  jnz     loc_18001F823
0x18001f59c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001f5a0  mov     rax, r14
0x18001f5a3  xor     ecx, ecx
0x18001f5a5  inc     rax
0x18001f5a8  cmp     [r15+rax*2], cx
0x18001f5ad  jnz     short loc_18001F5A5
0x18001f5af  mov     rcx, gs:60h
0x18001f5b8  lea     ebx, ds:12h[rax*2]
0x18001f5bf  mov     r8d, ebx; Size
0x18001f5c2  mov     edx, 8; Flags
0x18001f5c7  mov     [rbp+arg_18], ebx
0x18001f5ca  mov     rcx, [rcx+30h]; HeapHandle
0x18001f5ce  call    cs:__imp_RtlAllocateHeap
0x18001f5d4  mov     r12, rax
0x18001f5d7  mov     [rbp+KeyValueInformation], rax
0x18001f5db  xor     eax, eax
0x18001f5dd  test    r12, r12
0x18001f5e0  jz      loc_18001F7DF
0x18001f5e6  mov     r12d, eax
0x18001f5e9  mov     rax, [rbp+KeyValueInformation]
0x18001f5ed  lea     rcx, [rbp+arg_10]
0x18001f5f1  mov     r9, rax; KeyValueInformation
0x18001f5f4  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x18001f5f9  mov     r8d, 2; KeyValueInformationClass
0x18001f5ff  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001f603  mov     edx, r12d; Index
0x18001f606  mov     [rsp+50h+Length], ebx; Length
0x18001f60a  call    cs:__imp_ZwEnumerateValueKey
0x18001f610  mov     ebx, eax
0x18001f612  cmp     eax, 8000001Ah
0x18001f617  jnz     loc_18001F781
0x18001f61d  mov     r12, [rbp+KeyValueInformation]
0x18001f621  mov     ebx, 0C0000034h
0x18001f626  jmp     loc_18001F718
0x18001f62b  mov     rcx, gs:60h
0x18001f634  lea     ebx, ds:21Ah[rax*2]
0x18001f63b  mov     r8d, ebx; Size
0x18001f63e  mov     edx, 8; Flags
0x18001f643  mov     r15d, ebx
0x18001f646  mov     rcx, [rcx+30h]; HeapHandle
0x18001f64a  call    cs:__imp_RtlAllocateHeap
0x18001f650  mov     r13, rax
0x18001f653  test    rax, rax
0x18001f656  jz      loc_18001F903
0x18001f65c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001f660  lea     rax, [rbp+arg_10]
0x18001f664  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18001f669  mov     r9, r13; KeyValueInformation
0x18001f66c  xor     r8d, r8d; KeyValueInformationClass
0x18001f66f  mov     [rsp+50h+Length], ebx; Length
0x18001f673  mov     edx, r12d; Index
0x18001f676  call    cs:__imp_ZwEnumerateValueKey
0x18001f67c  xor     r12d, r12d
0x18001f67f  mov     ebx, eax
0x18001f681  test    eax, eax
0x18001f683  js      loc_18001F917
0x18001f689  mov     eax, [rbp+arg_10]
0x18001f68c  add     rax, 2
0x18001f690  cmp     rax, r15
0x18001f693  ja      loc_18001F926
0x18001f699  mov     rbx, cs:Src
0x18001f6a0  test    rbx, rbx
0x18001f6a3  jz      loc_18001F833
0x18001f6a9  mov     r8, r14
0x18001f6ac  inc     r8; MaxCount
0x18001f6af  cmp     [rbx+r8*2], r12w
0x18001f6b4  jnz     short loc_18001F6AC
0x18001f6b6  lea     rdx, [r13+0Ch]; String2
0x18001f6ba  mov     rcx, rbx; String1
0x18001f6bd  call    _wcsnicmp_0
0x18001f6c2  test    eax, eax
0x18001f6c4  jnz     loc_18001F93A
0x18001f6ca  inc     r14
0x18001f6cd  cmp     [rbx+r14*2], r12w
0x18001f6d2  jnz     short loc_18001F6CA
0x18001f6d4  lea     rdx, ds:0Ch[r14*2]
0x18001f6dc  add     rdx, r13
0x18001f6df  lea     rcx, [rbp+var_18]
0x18001f6e3  call    AslPathToSystemPath
0x18001f6e8  xor     r14d, r14d
0x18001f6eb  mov     ebx, eax
0x18001f6ed  test    eax, eax
0x18001f6ef  jns     loc_18001F804
0x18001f6f5  lea     r9, aFailedToAlloca_3; "Failed to allocate or convert stub path"...
0x18001f6fc  mov     r8d, 50Eh
0x18001f702  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001f709  mov     ecx, edi
0x18001f70b  call    AslLogCallPrintf
0x18001f710  mov     rsi, [rbp+var_18]
0x18001f714  mov     r12, [rbp+KeyValueInformation]
0x18001f718  mov     rcx, [rbp+KeyHandle]; Handle
0x18001f71c  lea     rax, [rcx-1]
0x18001f720  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f724  jbe     loc_18001F7D4
0x18001f72a  test    rsi, rsi
0x18001f72d  jnz     loc_18001F99A
0x18001f733  test    r12, r12
0x18001f736  jz      short loc_18001F74D
0x18001f738  mov     rcx, gs:60h
0x18001f741  mov     rdx, r12
0x18001f744  mov     rcx, [rcx+30h]
0x18001f748  call    AslFree
0x18001f74d  test    r13, r13
0x18001f750  jz      short loc_18001F767
0x18001f752  mov     rcx, gs:60h
0x18001f75b  mov     rdx, r13
0x18001f75e  mov     rcx, [rcx+30h]
0x18001f762  call    AslFree
0x18001f767  mov     eax, ebx
0x18001f769  mov     rbx, [rsp+50h+arg_8]
0x18001f771  add     rsp, 50h
0x18001f775  pop     r15
0x18001f777  pop     r14
0x18001f779  pop     r13
0x18001f77b  pop     r12
0x18001f77d  pop     rdi
0x18001f77e  pop     rsi
0x18001f77f  pop     rbp
0x18001f780  retn
0x18001f781  cmp     eax, 80000005h
0x18001f786  jz      loc_18001F8F4
0x18001f78c  cmp     eax, 0C0000023h
0x18001f791  jz      loc_18001F8F4
0x18001f797  test    eax, eax
0x18001f799  js      loc_18001F97A
0x18001f79f  mov     rax, [rbp+KeyValueInformation]
0x18001f7a3  cmp     [rax+4], edi
0x18001f7a6  jnz     loc_18001F8F8
0x18001f7ac  lea     rdx, [rax+0Ch]; String2
0x18001f7b0  mov     rcx, r15; String1
0x18001f7b3  call    _wcsicmp_0
0x18001f7b8  xor     ecx, ecx
0x18001f7ba  test    eax, eax
0x18001f7bc  jnz     loc_18001F8F4
0x18001f7c2  mov     rax, r14
0x18001f7c5  inc     rax
0x18001f7c8  cmp     [r15+rax*2], cx
0x18001f7cd  jnz     short loc_18001F7C5
0x18001f7cf  jmp     loc_18001F62B
0x18001f7d4  call    cs:__imp_ZwClose
0x18001f7da  jmp     loc_18001F72A
0x18001f7df  lea     r9, aFailedToAlloca_1; "Failed to allocate partial info."
0x18001f7e6  mov     r8d, 4C6h
0x18001f7ec  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001f7f3  mov     ecx, edi
0x18001f7f5  mov     ebx, 0C0000017h
0x18001f7fa  call    AslLogCallPrintf
0x18001f7ff  jmp     loc_18001F718
0x18001f804  mov     rsi, [rbp+var_18]
0x18001f808  test    rsi, rsi
0x18001f80b  jz      loc_18001F966
0x18001f811  mov     rax, [rbp+arg_0]
0x18001f815  mov     ebx, r14d
0x18001f818  mov     [rax], rsi
0x18001f81b  mov     rsi, r14
0x18001f81e  jmp     loc_18001F714
0x18001f823  add     ebx, edi
0x18001f825  cmp     ebx, 0Ah
0x18001f828  jl      loc_18001F57B
0x18001f82e  jmp     loc_18001F621
0x18001f833  xor     edx, edx; hFile
0x18001f835  lea     rcx, ModuleName; "ntdll.dll"
0x18001f83c  mov     r8d, 800h; dwFlags
0x18001f842  mov     ebx, 7FFE0030h
0x18001f847  call    cs:__imp_LoadLibraryExW
0x18001f84d  mov     rsi, rax
0x18001f850  test    rax, rax
0x18001f853  jz      short loc_18001F87B
0x18001f855  lea     rdx, ProcName; "RtlGetNtSystemRoot"
0x18001f85c  mov     rcx, rax; hModule
0x18001f85f  call    cs:__imp_GetProcAddress
0x18001f865  test    rax, rax
0x18001f868  jz      short loc_18001F872
0x18001f86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f86f  mov     rbx, rax
0x18001f872  mov     rcx, rsi; hLibModule
0x18001f875  call    cs:__imp_FreeLibrary
0x18001f87b  mov     cs:Src, rbx
0x18001f882  jmp     loc_18001F6A9
0x18001f887  mov     eax, 0C00000EFh
0x18001f88c  jmp     loc_18001F769
0x18001f891  cmp     eax, 0C0000034h
0x18001f896  jz      loc_18001F718
0x18001f89c  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x18001f8a3  mov     [rsp+50h+Length], eax
0x18001f8a7  mov     r8d, 4B2h
0x18001f8ad  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001f8b4  mov     ecx, 1
0x18001f8b9  call    AslLogCallPrintf
0x18001f8be  jmp     loc_18001F718
0x18001f8c3  mov     ebx, 0C0000034h
0x18001f8c8  jmp     loc_18001F767
0x18001f8cd  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x18001f8d4  mov     [rsp+50h+Length], eax
0x18001f8d8  mov     r8d, 4A2h
0x18001f8de  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001f8e5  mov     ecx, 1
0x18001f8ea  call    AslLogCallPrintf
0x18001f8ef  jmp     loc_18001F767
0x18001f8f4  mov     rax, [rbp+KeyValueInformation]
0x18001f8f8  mov     ebx, [rbp+arg_18]
0x18001f8fb  add     r12d, edi
0x18001f8fe  jmp     loc_18001F5ED
0x18001f903  mov     ebx, 0C0000017h
0x18001f908  lea     r9, aFailedToAlloca_7; "Failed to allocate basic info."
0x18001f90f  mov     r8d, 4EAh
0x18001f915  jmp     short loc_18001F987
0x18001f917  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x18001f91e  mov     r8d, 4F5h
0x18001f924  jmp     short loc_18001F987
0x18001f926  mov     ebx, 0C0000023h
0x18001f92b  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x18001f932  mov     r8d, 4FAh
0x18001f938  jmp     short loc_18001F987
0x18001f93a  lea     rdx, [r13+0Ch]
0x18001f93e  lea     rcx, [rbp+var_18]
0x18001f942  call    AslStringDuplicate
0x18001f947  xor     r14d, r14d
0x18001f94a  mov     ebx, eax
0x18001f94c  test    eax, eax
0x18001f94e  jns     loc_18001F804
0x18001f954  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x18001f95b  mov     r8d, 515h
0x18001f961  jmp     loc_18001F702
0x18001f966  mov     ebx, 0C0000017h
0x18001f96b  lea     r9, aFailedToAlloca_11; "Failed to allocate stub path."
0x18001f972  mov     r8d, 51Ch
0x18001f978  jmp     short loc_18001F987
0x18001f97a  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x18001f981  mov     r8d, 4D9h
0x18001f987  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001f98e  mov     ecx, edi
0x18001f990  call    AslLogCallPrintf
0x18001f995  jmp     loc_18001F714
0x18001f99a  mov     rcx, gs:60h
0x18001f9a3  mov     rdx, rsi
0x18001f9a6  mov     rcx, [rcx+30h]
0x18001f9aa  call    AslFree
0x18001f9af  jmp     loc_18001F733
```
