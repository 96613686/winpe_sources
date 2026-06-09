# SdbpGetManifestedMergeStubAlloc

- ea: `0x18004130c`
- end: `0x18004176b`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1119`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006fbd4`
- `0x1800abcdc`

## callees

- `0x180041250`
- `0x18004130c`
- `0x180041774`
- `0x180041794`
- `0x18004189c`
- `0x1800419a0`
- `0x18004281c`
- `0x180076e90`
- `0x180076e9c`
- `0x1800c0a94`
- `0x1800cb010`

## import_xrefs

- `ntdll!ZwEnumerateValueKey` at `0x1800414b5`
- `ntdll!ZwEnumerateValueKey` at `0x180041570`
- `ntdll!ZwEnumerateValueKey` at `0x1800414b5`
- `ntdll!ZwEnumerateValueKey` at `0x180041570`
- `ntdll!RtlAllocateHeap` at `0x180041458`
- `ntdll!RtlAllocateHeap` at `0x180041531`
- `ntdll!RtlAllocateHeap` at `0x180041458`
- `ntdll!RtlAllocateHeap` at `0x180041531`
- `ntdll!ZwClose` at `0x1800416fd`
- `ntdll!ZwClose` at `0x1800416fd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800415ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800415ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800415d4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800415d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041602`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041602`

## string_xrefs

- `0x1800415c2`: `ntdll.dll`
- `0x1800413a8`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x180041386`: `SdbpGetManifestedMergeStubAlloc`
- `0x1800413e0`: `SdbpGetManifestedMergeStubAlloc`
- `0x180041479`: `SdbpGetManifestedMergeStubAlloc`
- `0x180041660`: `SdbpGetManifestedMergeStubAlloc`
- `0x1800416d2`: `SdbpGetManifestedMergeStubAlloc`
- `0x1800413cf`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x18004168a`: `Failed to duplicate stub path.`
- `0x180041653`: `Failed to allocate or convert stub path.`
- `0x1800416a7`: `Failed to allocate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  __int64 v3; // rsi
  NTSTATUS v5; // ebx
  int MergeSdbsDisabled; // eax
  const wchar_t *Heap; // r12
  wchar_t *v8; // r13
  int Key; // eax
  unsigned int v10; // ebx
  __int64 v11; // r14
  __int64 v12; // rax
  ULONG Length; // ebx
  ULONG v14; // r12d
  wchar_t *v15; // rax
  NTSTATUS v16; // eax
  __int64 v17; // rax
  ULONG v18; // ebx
  unsigned __int64 v19; // r15
  __int64 v20; // rbx
  HMODULE Library; // rax
  HMODULE v22; // rsi
  __int64 (*ProcAddress)(void); // rax
  size_t v24; // r8
  const wchar_t *KeyValueInformation; // [rsp+30h] [rbp-20h]
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+50h] BYREF
  ULONG v30; // [rsp+A8h] [rbp+58h] BYREF

  v30 = 0;
  v3 = 0;
  ResultLength = 0;
  v26 = 0;
  KeyHandle[0] = 0;
  if ( !a1 )
    return 3221225711LL;
  *a1 = 0;
  if ( (unsigned int)SdbpGetMergeSdbsSupported() )
  {
    MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&v30);
    v5 = MergeSdbsDisabled;
    if ( MergeSdbsDisabled < 0 )
    {
      AslLogCallPrintf(
        1,
        "SdbpGetManifestedMergeStubAlloc",
        1186,
        "SdbpGetMergeSdbsDisabled failed [%x]",
        MergeSdbsDisabled);
      return (unsigned int)v5;
    }
    if ( !v30 )
    {
      Heap = 0;
      v8 = 0;
      Key = AslRegistryGetKey(
              KeyHandle,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
              2147483904LL);
      v5 = Key;
      if ( Key < 0 )
      {
        if ( Key != -1073741772 )
          AslLogCallPrintf(
            1,
            "SdbpGetManifestedMergeStubAlloc",
            1202,
            "AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]",
            Key);
LABEL_58:
        if ( (unsigned __int64)KeyHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          ZwClose(KeyHandle[0]);
        if ( v3 )
          AslFree(NtCurrentPeb()->ProcessHeap, v3);
        if ( Heap )
          AslFree(NtCurrentPeb()->ProcessHeap, Heap);
        if ( v8 )
          AslFree(NtCurrentPeb()->ProcessHeap, v8);
        return (unsigned int)v5;
      }
      v10 = 1;
      while ( wcsicmp(a2, (const wchar_t *)qword_1800CF9C8[4 * v10]) )
      {
        if ( (int)++v10 >= 10 )
        {
LABEL_57:
          v5 = -1073741772;
          goto LABEL_58;
        }
      }
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      Length = 2 * v12 + 18;
      v30 = Length;
      Heap = (const wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
      KeyValueInformation = Heap;
      if ( !Heap )
      {
        v5 = -1073741801;
        AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1222, "Failed to allocate partial info.");
        goto LABEL_58;
      }
      v14 = 0;
      v15 = (wchar_t *)KeyValueInformation;
      while ( 1 )
      {
        v16 = ZwEnumerateValueKey(KeyHandle[0], v14, KeyValuePartialInformation, v15, Length, &ResultLength);
        v5 = v16;
        if ( v16 == -2147483643 || v16 == -1073741789 )
          goto LABEL_26;
        if ( v16 == -2147483622 )
        {
          Heap = KeyValueInformation;
          goto LABEL_57;
        }
        if ( v16 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1241, "Failed to query partial info.");
          goto LABEL_55;
        }
        v15 = (wchar_t *)KeyValueInformation;
        if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
          break;
LABEL_27:
        Length = v30;
        ++v14;
      }
      if ( !wcsicmp(a2, KeyValueInformation + 6) )
      {
        v17 = -1;
        do
          ++v17;
        while ( a2[v17] );
        v18 = 2 * v17 + 538;
        v19 = v18;
        v8 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v18);
        if ( !v8 )
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1258, "Failed to allocate basic info.");
LABEL_55:
          Heap = KeyValueInformation;
          goto LABEL_58;
        }
        v5 = ZwEnumerateValueKey(KeyHandle[0], v14, KeyValueBasicInformation, v8, v18, &ResultLength);
        if ( v5 < 0 )
        {
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1269, "Failed to query basic info.");
          goto LABEL_55;
        }
        if ( (unsigned __int64)ResultLength + 2 > v19 )
        {
          v5 = -1073741789;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1274, "Buffer too small to query basic info.");
          goto LABEL_55;
        }
        v20 = (__int64)Src;
        if ( !Src )
        {
          v20 = 2147352624;
          Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
          v22 = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
            if ( ProcAddress )
              v20 = ProcAddress();
            FreeLibrary(v22);
          }
          Src = (wchar_t *)v20;
        }
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v20 + 2 * v24) );
        if ( wcsnicmp((const wchar_t *)v20, v8 + 6, v24) )
        {
          v5 = AslStringDuplicate(&v26, v8 + 6);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1301, "Failed to duplicate stub path.");
            goto LABEL_48;
          }
        }
        else
        {
          do
            ++v11;
          while ( *(_WORD *)(v20 + 2 * v11) );
          v5 = AslPathToSystemPath(&v26, &v8[v11 + 6]);
          if ( v5 < 0 )
          {
            AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1294, "Failed to allocate or convert stub path.");
LABEL_48:
            v3 = v26;
            goto LABEL_55;
          }
        }
        v3 = v26;
        if ( v26 )
        {
          v5 = 0;
          *a1 = v26;
          v3 = 0;
        }
        else
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "SdbpGetManifestedMergeStubAlloc", 1308, "Failed to allocate stub path.");
        }
        goto LABEL_55;
      }
LABEL_26:
      v15 = (wchar_t *)KeyValueInformation;
      goto LABEL_27;
    }
  }
  return (unsigned int)-1073741772;
}

```

## disassembly

```asm
0x18004130c  mov     [rsp-38h+arg_8], rbx
0x180041311  mov     [rsp-38h+arg_0], rcx
0x180041316  push    rbp
0x180041317  push    rsi
0x180041318  push    rdi
0x180041319  push    r12
0x18004131b  push    r13
0x18004131d  push    r14
0x18004131f  push    r15
0x180041321  mov     rbp, rsp
0x180041324  sub     rsp, 50h
0x180041328  xor     r14d, r14d
0x18004132b  mov     r15, rdx
0x18004132e  mov     [rbp+arg_18], r14d
0x180041332  mov     esi, r14d
0x180041335  mov     [rbp+arg_10], r14d
0x180041339  mov     [rbp+var_18], r14
0x18004133d  mov     [rbp+KeyHandle], r14
0x180041341  test    rcx, rcx
0x180041344  jnz     short loc_180041350
0x180041346  mov     eax, 0C00000EFh
0x18004134b  jmp     loc_180041753
0x180041350  mov     [rcx], r14
0x180041353  call    SdbpGetMergeSdbsSupported
0x180041358  test    eax, eax
0x18004135a  jnz     short loc_180041366
0x18004135c  mov     ebx, 0C0000034h
0x180041361  jmp     loc_180041751
0x180041366  lea     rcx, [rbp+arg_18]
0x18004136a  call    SdbpGetMergeSdbsDisabled
0x18004136f  mov     ebx, eax
0x180041371  test    eax, eax
0x180041373  jns     short loc_18004139C
0x180041375  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x18004137c  mov     [rsp+50h+Length], eax
0x180041380  mov     r8d, 4A2h
0x180041386  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18004138d  mov     ecx, 1
0x180041392  call    AslLogCallPrintf
0x180041397  jmp     loc_180041751
0x18004139c  cmp     [rbp+arg_18], r14d
0x1800413a0  jnz     short loc_18004135C
0x1800413a2  mov     r8d, 80000100h
0x1800413a8  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800413af  lea     rcx, [rbp+KeyHandle]
0x1800413b3  mov     r12, r14
0x1800413b6  mov     r13, r14
0x1800413b9  call    AslRegistryGetKey
0x1800413be  mov     ebx, eax
0x1800413c0  test    eax, eax
0x1800413c2  jns     short loc_1800413F6
0x1800413c4  cmp     eax, 0C0000034h
0x1800413c9  jz      loc_1800416EF
0x1800413cf  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x1800413d6  mov     [rsp+50h+Length], eax
0x1800413da  mov     r8d, 4B2h
0x1800413e0  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1800413e7  mov     ecx, 1
0x1800413ec  call    AslLogCallPrintf
0x1800413f1  jmp     loc_1800416EF
0x1800413f6  mov     edi, 1
0x1800413fb  mov     ebx, edi
0x1800413fd  lea     rax, qword_1800CF9C8
0x180041404  mov     edx, ebx
0x180041406  shl     rdx, 5
0x18004140a  mov     rcx, r15; String1
0x18004140d  mov     rdx, [rdx+rax]; String2
0x180041411  call    _wcsicmp
0x180041416  test    eax, eax
0x180041418  jz      short loc_180041426
0x18004141a  add     ebx, edi
0x18004141c  cmp     ebx, 0Ah
0x18004141f  jl      short loc_1800413FD
0x180041421  jmp     loc_1800416EA
0x180041426  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004142a  mov     rax, r14
0x18004142d  xor     ecx, ecx
0x18004142f  inc     rax
0x180041432  cmp     [r15+rax*2], cx
0x180041437  jnz     short loc_18004142F
0x180041439  mov     rcx, gs:60h
0x180041442  lea     ebx, ds:12h[rax*2]
0x180041449  mov     r8d, ebx; Size
0x18004144c  mov     edx, 8; Flags
0x180041451  mov     [rbp+arg_18], ebx
0x180041454  mov     rcx, [rcx+30h]; HeapHandle
0x180041458  call    cs:__imp_RtlAllocateHeap
0x18004145e  mov     r12, rax
0x180041461  mov     [rbp+KeyValueInformation], rax
0x180041465  xor     eax, eax
0x180041467  test    r12, r12
0x18004146a  jnz     short loc_180041491
0x18004146c  lea     r9, aFailedToAlloca_1; "Failed to allocate partial info."
0x180041473  mov     r8d, 4C6h
0x180041479  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180041480  mov     ecx, edi
0x180041482  mov     ebx, 0C0000017h
0x180041487  call    AslLogCallPrintf
0x18004148c  jmp     loc_1800416EF
0x180041491  mov     r12d, eax
0x180041494  mov     rax, [rbp+KeyValueInformation]
0x180041498  lea     rcx, [rbp+arg_10]
0x18004149c  mov     r9, rax; KeyValueInformation
0x18004149f  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x1800414a4  mov     r8d, 2; KeyValueInformationClass
0x1800414aa  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800414ae  mov     edx, r12d; Index
0x1800414b1  mov     [rsp+50h+Length], ebx; Length
0x1800414b5  call    cs:__imp_ZwEnumerateValueKey
0x1800414bb  mov     ebx, eax
0x1800414bd  cmp     eax, 80000005h
0x1800414c2  jz      short loc_1800414F9
0x1800414c4  cmp     eax, 0C0000023h
0x1800414c9  jz      short loc_1800414F9
0x1800414cb  cmp     eax, 8000001Ah
0x1800414d0  jz      loc_1800416E6
0x1800414d6  test    eax, eax
0x1800414d8  js      loc_1800416C5
0x1800414de  mov     rax, [rbp+KeyValueInformation]
0x1800414e2  cmp     [rax+4], edi
0x1800414e5  jnz     short loc_1800414FD
0x1800414e7  lea     rdx, [rax+0Ch]; String2
0x1800414eb  mov     rcx, r15; String1
0x1800414ee  call    _wcsicmp
0x1800414f3  xor     ecx, ecx
0x1800414f5  test    eax, eax
0x1800414f7  jz      short loc_180041505
0x1800414f9  mov     rax, [rbp+KeyValueInformation]
0x1800414fd  mov     ebx, [rbp+arg_18]
0x180041500  add     r12d, edi
0x180041503  jmp     short loc_180041498
0x180041505  mov     rax, r14
0x180041508  inc     rax
0x18004150b  cmp     [r15+rax*2], cx
0x180041510  jnz     short loc_180041508
0x180041512  mov     rcx, gs:60h
0x18004151b  lea     ebx, ds:21Ah[rax*2]
0x180041522  mov     r8d, ebx; Size
0x180041525  mov     edx, 8; Flags
0x18004152a  mov     r15d, ebx
0x18004152d  mov     rcx, [rcx+30h]; HeapHandle
0x180041531  call    cs:__imp_RtlAllocateHeap
0x180041537  mov     r13, rax
0x18004153a  test    rax, rax
0x18004153d  jnz     short loc_180041556
0x18004153f  mov     ebx, 0C0000017h
0x180041544  lea     r9, aFailedToAlloca_7; "Failed to allocate basic info."
0x18004154b  mov     r8d, 4EAh
0x180041551  jmp     loc_1800416D2
0x180041556  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004155a  lea     rax, [rbp+arg_10]
0x18004155e  mov     [rsp+50h+ResultLength], rax; ResultLength
0x180041563  mov     r9, r13; KeyValueInformation
0x180041566  xor     r8d, r8d; KeyValueInformationClass
0x180041569  mov     [rsp+50h+Length], ebx; Length
0x18004156d  mov     edx, r12d; Index
0x180041570  call    cs:__imp_ZwEnumerateValueKey
0x180041576  xor     r12d, r12d
0x180041579  mov     ebx, eax
0x18004157b  test    eax, eax
0x18004157d  jns     short loc_180041591
0x18004157f  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x180041586  mov     r8d, 4F5h
0x18004158c  jmp     loc_1800416D2
0x180041591  mov     eax, [rbp+arg_10]
0x180041594  add     rax, 2
0x180041598  cmp     rax, r15
0x18004159b  jbe     short loc_1800415B4
0x18004159d  mov     ebx, 0C0000023h
0x1800415a2  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x1800415a9  mov     r8d, 4FAh
0x1800415af  jmp     loc_1800416D2
0x1800415b4  mov     rbx, cs:Src
0x1800415bb  test    rbx, rbx
0x1800415be  jnz     short loc_18004160F
0x1800415c0  xor     edx, edx; hFile
0x1800415c2  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1800415c9  mov     r8d, 800h; dwFlags
0x1800415cf  mov     ebx, 7FFE0030h
0x1800415d4  call    cs:__imp_LoadLibraryExW
0x1800415da  mov     rsi, rax
0x1800415dd  test    rax, rax
0x1800415e0  jz      short loc_180041608
0x1800415e2  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1800415e9  mov     rcx, rax; hModule
0x1800415ec  call    cs:__imp_GetProcAddress
0x1800415f2  test    rax, rax
0x1800415f5  jz      short loc_1800415FF
0x1800415f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415fc  mov     rbx, rax
0x1800415ff  mov     rcx, rsi; hLibModule
0x180041602  call    cs:__imp_FreeLibrary
0x180041608  mov     cs:Src, rbx
0x18004160f  mov     r8, r14
0x180041612  inc     r8; MaxCount
0x180041615  cmp     [rbx+r8*2], r12w
0x18004161a  jnz     short loc_180041612
0x18004161c  lea     rdx, [r13+0Ch]; String2
0x180041620  mov     rcx, rbx; String1
0x180041623  call    _wcsnicmp
0x180041628  test    eax, eax
0x18004162a  jnz     short loc_180041674
0x18004162c  inc     r14
0x18004162f  cmp     [rbx+r14*2], r12w
0x180041634  jnz     short loc_18004162C
0x180041636  lea     rdx, ds:0Ch[r14*2]
0x18004163e  add     rdx, r13
0x180041641  lea     rcx, [rbp+var_18]
0x180041645  call    AslPathToSystemPath
0x18004164a  xor     r14d, r14d
0x18004164d  mov     ebx, eax
0x18004164f  test    eax, eax
0x180041651  jns     short loc_180041699
0x180041653  lea     r9, aFailedToAlloca_3; "Failed to allocate or convert stub path"...
0x18004165a  mov     r8d, 50Eh
0x180041660  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x180041667  mov     ecx, edi
0x180041669  call    AslLogCallPrintf
0x18004166e  mov     rsi, [rbp+var_18]
0x180041672  jmp     short loc_1800416E0
0x180041674  lea     rdx, [r13+0Ch]
0x180041678  lea     rcx, [rbp+var_18]
0x18004167c  call    AslStringDuplicate
0x180041681  xor     r14d, r14d
0x180041684  mov     ebx, eax
0x180041686  test    eax, eax
0x180041688  jns     short loc_180041699
0x18004168a  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x180041691  mov     r8d, 515h
0x180041697  jmp     short loc_180041660
0x180041699  mov     rsi, [rbp+var_18]
0x18004169d  test    rsi, rsi
0x1800416a0  jnz     short loc_1800416B6
0x1800416a2  mov     ebx, 0C0000017h
0x1800416a7  lea     r9, aFailedToAlloca_11; "Failed to allocate stub path."
0x1800416ae  mov     r8d, 51Ch
0x1800416b4  jmp     short loc_1800416D2
0x1800416b6  mov     rax, [rbp+arg_0]
0x1800416ba  mov     ebx, r14d
0x1800416bd  mov     [rax], rsi
0x1800416c0  mov     rsi, r14
0x1800416c3  jmp     short loc_1800416E0
0x1800416c5  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x1800416cc  mov     r8d, 4D9h
0x1800416d2  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x1800416d9  mov     ecx, edi
0x1800416db  call    AslLogCallPrintf
0x1800416e0  mov     r12, [rbp+KeyValueInformation]
0x1800416e4  jmp     short loc_1800416EF
0x1800416e6  mov     r12, [rbp+KeyValueInformation]
0x1800416ea  mov     ebx, 0C0000034h
0x1800416ef  mov     rcx, [rbp+KeyHandle]; Handle
0x1800416f3  lea     rax, [rcx-1]
0x1800416f7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800416fb  ja      short loc_180041703
0x1800416fd  call    cs:__imp_ZwClose
0x180041703  test    rsi, rsi
0x180041706  jz      short loc_18004171D
0x180041708  mov     rcx, gs:60h
0x180041711  mov     rdx, rsi
0x180041714  mov     rcx, [rcx+30h]
0x180041718  call    AslFree
0x18004171d  test    r12, r12
0x180041720  jz      short loc_180041737
0x180041722  mov     rcx, gs:60h
0x18004172b  mov     rdx, r12
0x18004172e  mov     rcx, [rcx+30h]
0x180041732  call    AslFree
0x180041737  test    r13, r13
0x18004173a  jz      short loc_180041751
0x18004173c  mov     rcx, gs:60h
0x180041745  mov     rdx, r13
0x180041748  mov     rcx, [rcx+30h]
0x18004174c  call    AslFree
0x180041751  mov     eax, ebx
0x180041753  mov     rbx, [rsp+50h+arg_8]
0x18004175b  add     rsp, 50h
0x18004175f  pop     r15
0x180041761  pop     r14
0x180041763  pop     r13
0x180041765  pop     r12
0x180041767  pop     rdi
0x180041768  pop     rsi
0x180041769  pop     rbp
0x18004176a  retn
```
