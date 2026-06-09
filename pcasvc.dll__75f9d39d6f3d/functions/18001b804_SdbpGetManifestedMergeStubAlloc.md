# SdbpGetManifestedMergeStubAlloc

- ea: `0x18001b804`
- end: `0x18001bcdc`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1240`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001cea4`
- `0x1800e987c`

## callees

- `0x180012920`
- `0x180012de0`
- `0x180019c84`
- `0x18001b804`
- `0x18001bd38`
- `0x18001be40`
- `0x18001c870`
- `0x18001caf0`
- `0x1800f7010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001ba27`
- `msvcrt!_wcsnicmp` at `0x18001ba27`
- `msvcrt!_wcsicmp` at `0x18001b8b7`
- `msvcrt!_wcsicmp` at `0x18001b978`
- `msvcrt!_wcsicmp` at `0x18001b8b7`
- `msvcrt!_wcsicmp` at `0x18001b978`
- `ntdll!ZwEnumerateValueKey` at `0x18001b933`
- `ntdll!ZwEnumerateValueKey` at `0x18001b9e0`
- `ntdll!ZwEnumerateValueKey` at `0x18001b933`
- `ntdll!ZwEnumerateValueKey` at `0x18001b9e0`
- `ntdll!ZwClose` at `0x18001baf7`
- `ntdll!ZwClose` at `0x18001baf7`
- `ntdll!RtlAllocateHeap` at `0x18001b8f7`
- `ntdll!RtlAllocateHeap` at `0x18001b9b4`
- `ntdll!RtlAllocateHeap` at `0x18001b8f7`
- `ntdll!RtlAllocateHeap` at `0x18001b9b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001bc2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001bc2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bc5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001bc5b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bc45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001bc45`

## string_xrefs

- `0x18001b87b`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x18001ba6d`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001bb1f`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001bb68`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001bb9b`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001bbcd`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001ba60`: `Failed to allocate or convert stub path.`
- `0x18001bc1b`: `ntdll.dll`
- `0x18001bbbc`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x18001bc9e`: `Failed to allocate stub path.`
- `0x18001bc87`: `Failed to duplicate stub path.`

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
  __int64 v15; // rax
  ULONG v16; // ebx
  unsigned __int64 v17; // r15
  __int64 v18; // rbx
  size_t v19; // r8
  const char *v20; // r9
  int v21; // r8d
  const char *v23; // r9
  int v24; // r8d
  HMODULE Library; // rax
  HMODULE v26; // rsi
  __int64 (*ProcAddress)(void); // rax
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
  if ( a1 )
  {
    *a1 = 0;
    if ( (unsigned int)SdbpGetMergeSdbsSupported() )
    {
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
      if ( !v33 )
      {
        Heap = 0;
        v6 = 0;
        Key = AslRegistryGetKey(
                KeyHandle,
                L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates\\ManifestedMergeStubSdbs",
                2147483904LL,
                1,
                0);
        MergeSdbsDisabled = Key;
        if ( Key < 0 )
        {
          if ( Key != -1073741772 )
            AslLogCallPrintf(
              1,
              (unsigned int)"SdbpGetManifestedMergeStubAlloc",
              1202,
              (unsigned int)"AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]");
        }
        else
        {
          v8 = 1;
          while ( _wcsicmp(a2, (const wchar_t *)qword_1800F84F8[4 * v8]) )
          {
            if ( (int)++v8 >= 10 )
            {
LABEL_44:
              MergeSdbsDisabled = -1073741772;
              goto LABEL_32;
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
          if ( Heap )
          {
            v12 = 0;
            v13 = (wchar_t *)KeyValueInformation;
            while ( 1 )
            {
              v14 = ZwEnumerateValueKey(KeyHandle[0], v12, KeyValuePartialInformation, v13, Length, &ResultLength);
              MergeSdbsDisabled = v14;
              if ( v14 == -2147483622 )
              {
                Heap = KeyValueInformation;
                goto LABEL_44;
              }
              if ( v14 == -2147483643 || v14 == -1073741789 )
                goto LABEL_41;
              if ( v14 < 0 )
              {
                v23 = "Failed to query partial info.";
                v24 = 1241;
                goto LABEL_46;
              }
              v13 = (wchar_t *)KeyValueInformation;
              if ( *((_DWORD *)KeyValueInformation + 1) == 1 )
                break;
LABEL_42:
              Length = v33;
              ++v12;
            }
            if ( !_wcsicmp(a2, KeyValueInformation + 6) )
            {
              v15 = -1;
              do
                ++v15;
              while ( a2[v15] );
              v16 = 2 * v15 + 538;
              v17 = v16;
              v6 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v16);
              if ( !v6 )
              {
                MergeSdbsDisabled = -1073741801;
                v23 = "Failed to allocate basic info.";
                v24 = 1258;
                goto LABEL_46;
              }
              MergeSdbsDisabled = ZwEnumerateValueKey(
                                    KeyHandle[0],
                                    v12,
                                    KeyValueBasicInformation,
                                    v6,
                                    v16,
                                    &ResultLength);
              if ( MergeSdbsDisabled < 0 )
              {
                v23 = "Failed to query basic info.";
                v24 = 1269;
                goto LABEL_46;
              }
              if ( (unsigned __int64)ResultLength + 2 > v17 )
              {
                MergeSdbsDisabled = -1073741789;
                v23 = "Buffer too small to query basic info.";
                v24 = 1274;
                goto LABEL_46;
              }
              v18 = (__int64)qword_18015BF38;
              if ( !qword_18015BF38 )
              {
                v18 = 2147352624;
                Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
                v26 = Library;
                if ( Library )
                {
                  ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
                  if ( ProcAddress )
                    v18 = ProcAddress();
                  FreeLibrary(v26);
                }
                qword_18015BF38 = (wchar_t *)v18;
              }
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)(v18 + 2 * v19) );
              if ( _wcsnicmp((const wchar_t *)v18, v6 + 6, v19) )
              {
                MergeSdbsDisabled = AslStringDuplicate(&v29, v6 + 6);
                if ( MergeSdbsDisabled >= 0 )
                  goto LABEL_47;
                v20 = "Failed to duplicate stub path.";
                v21 = 1301;
LABEL_30:
                AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v21, (_DWORD)v20);
                v3 = v29;
              }
              else
              {
                do
                  ++v9;
                while ( *(_WORD *)(v18 + 2 * v9) );
                MergeSdbsDisabled = AslPathToSystemPath(&v29, &v6[v9 + 6]);
                if ( MergeSdbsDisabled < 0 )
                {
                  v20 = "Failed to allocate or convert stub path.";
                  v21 = 1294;
                  goto LABEL_30;
                }
LABEL_47:
                v3 = v29;
                if ( v29 )
                {
                  MergeSdbsDisabled = 0;
                  *a1 = v29;
                  v3 = 0;
                  goto LABEL_31;
                }
                MergeSdbsDisabled = -1073741801;
                v23 = "Failed to allocate stub path.";
                v24 = 1308;
LABEL_46:
                AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v24, (_DWORD)v23);
              }
LABEL_31:
              Heap = KeyValueInformation;
              goto LABEL_32;
            }
LABEL_41:
            v13 = (wchar_t *)KeyValueInformation;
            goto LABEL_42;
          }
          MergeSdbsDisabled = -1073741801;
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbpGetManifestedMergeStubAlloc",
            1222,
            (unsigned int)"Failed to allocate partial info.");
        }
LABEL_32:
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
    }
    return (unsigned int)-1073741772;
  }
  return 3221225711LL;
}

```

## disassembly

```asm
0x18001b804  mov     [rsp-38h+arg_8], rbx
0x18001b809  mov     [rsp-38h+arg_0], rcx
0x18001b80e  push    rbp
0x18001b80f  push    rsi
0x18001b810  push    rdi
0x18001b811  push    r12
0x18001b813  push    r13
0x18001b815  push    r14
0x18001b817  push    r15
0x18001b819  mov     rbp, rsp
0x18001b81c  sub     rsp, 50h
0x18001b820  xor     r14d, r14d
0x18001b823  mov     r15, rdx
0x18001b826  mov     [rbp+arg_18], r14d
0x18001b82a  mov     esi, r14d
0x18001b82d  mov     [rbp+arg_10], r14d
0x18001b831  mov     [rbp+var_18], r14
0x18001b835  mov     [rbp+KeyHandle], r14
0x18001b839  test    rcx, rcx
0x18001b83c  jz      loc_18001BB80
0x18001b842  mov     [rcx], r14
0x18001b845  call    SdbpGetMergeSdbsSupported
0x18001b84a  test    eax, eax
0x18001b84c  jz      loc_18001BB51
0x18001b852  lea     rcx, [rbp+arg_18]
0x18001b856  call    SdbpGetMergeSdbsDisabled
0x18001b85b  mov     ebx, eax
0x18001b85d  test    eax, eax
0x18001b85f  js      loc_18001BB8A
0x18001b865  cmp     [rbp+arg_18], r14d
0x18001b869  jnz     loc_18001BB51
0x18001b86f  lea     edi, [r14+1]
0x18001b873  mov     [rsp+50h+Length], r14d
0x18001b878  mov     r9d, edi
0x18001b87b  lea     rdx, aSoftwareMicros_19; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001b882  mov     r8d, 80000100h
0x18001b888  lea     rcx, [rbp+KeyHandle]
0x18001b88c  mov     r12d, r14d
0x18001b88f  mov     r13d, r14d
0x18001b892  call    AslRegistryGetKey
0x18001b897  mov     ebx, eax
0x18001b899  test    eax, eax
0x18001b89b  js      loc_18001BBB1
0x18001b8a1  mov     ebx, edi
0x18001b8a3  lea     rax, qword_1800F84F8
0x18001b8aa  mov     edx, ebx
0x18001b8ac  shl     rdx, 5
0x18001b8b0  mov     rcx, r15; String1
0x18001b8b3  mov     rdx, [rdx+rax]; String2
0x18001b8b7  call    cs:__imp__wcsicmp
0x18001b8bd  test    eax, eax
0x18001b8bf  jnz     loc_18001BBE0
0x18001b8c5  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001b8c9  mov     rax, r14
0x18001b8cc  xor     ecx, ecx
0x18001b8ce  inc     rax
0x18001b8d1  cmp     [r15+rax*2], cx
0x18001b8d6  jnz     short loc_18001B8CE
0x18001b8d8  mov     rcx, gs:60h
0x18001b8e1  lea     ebx, ds:12h[rax*2]
0x18001b8e8  mov     r8d, ebx; Size
0x18001b8eb  mov     edx, 8; Flags
0x18001b8f0  mov     [rbp+arg_18], ebx
0x18001b8f3  mov     rcx, [rcx+30h]; HeapHandle
0x18001b8f7  call    cs:__imp_RtlAllocateHeap
0x18001b8fd  mov     r12, rax
0x18001b900  mov     [rbp+KeyValueInformation], rax
0x18001b904  xor     eax, eax
0x18001b906  test    r12, r12
0x18001b909  jz      loc_18001BB5B
0x18001b90f  mov     r12d, eax
0x18001b912  mov     rax, [rbp+KeyValueInformation]
0x18001b916  lea     rcx, [rbp+arg_10]
0x18001b91a  mov     r9, rax; KeyValueInformation
0x18001b91d  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x18001b922  mov     r8d, 2; KeyValueInformationClass
0x18001b928  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001b92c  mov     edx, r12d; Index
0x18001b92f  mov     [rsp+50h+Length], ebx; Length
0x18001b933  call    cs:__imp_ZwEnumerateValueKey
0x18001b939  mov     ebx, eax
0x18001b93b  cmp     eax, 8000001Ah
0x18001b940  jz      loc_18001BAFF
0x18001b946  cmp     eax, 80000005h
0x18001b94b  jz      loc_18001BAE8
0x18001b951  cmp     eax, 0C0000023h
0x18001b956  jz      loc_18001BAE8
0x18001b95c  test    eax, eax
0x18001b95e  js      loc_18001BCB0
0x18001b964  mov     rax, [rbp+KeyValueInformation]
0x18001b968  cmp     [rax+4], edi
0x18001b96b  jnz     loc_18001BAEC
0x18001b971  lea     rdx, [rax+0Ch]; String2
0x18001b975  mov     rcx, r15; String1
0x18001b978  call    cs:__imp__wcsicmp
0x18001b97e  xor     ecx, ecx
0x18001b980  test    eax, eax
0x18001b982  jnz     loc_18001BAE8
0x18001b988  mov     rax, r14
0x18001b98b  inc     rax
0x18001b98e  cmp     [r15+rax*2], cx
0x18001b993  jnz     short loc_18001B98B
0x18001b995  mov     rcx, gs:60h
0x18001b99e  lea     ebx, ds:21Ah[rax*2]
0x18001b9a5  mov     r8d, ebx; Size
0x18001b9a8  mov     edx, 8; Flags
0x18001b9ad  mov     r15d, ebx
0x18001b9b0  mov     rcx, [rcx+30h]; HeapHandle
0x18001b9b4  call    cs:__imp_RtlAllocateHeap
0x18001b9ba  mov     r13, rax
0x18001b9bd  test    rax, rax
0x18001b9c0  jz      loc_18001BB0D
0x18001b9c6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001b9ca  lea     rax, [rbp+arg_10]
0x18001b9ce  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18001b9d3  mov     r9, r13; KeyValueInformation
0x18001b9d6  xor     r8d, r8d; KeyValueInformationClass
0x18001b9d9  mov     [rsp+50h+Length], ebx; Length
0x18001b9dd  mov     edx, r12d; Index
0x18001b9e0  call    cs:__imp_ZwEnumerateValueKey
0x18001b9e6  xor     r12d, r12d
0x18001b9e9  mov     ebx, eax
0x18001b9eb  test    eax, eax
0x18001b9ed  js      loc_18001BBF0
0x18001b9f3  mov     eax, [rbp+arg_10]
0x18001b9f6  add     rax, 2
0x18001b9fa  cmp     rax, r15
0x18001b9fd  ja      loc_18001BC02
0x18001ba03  mov     rbx, cs:qword_18015BF38
0x18001ba0a  test    rbx, rbx
0x18001ba0d  jz      loc_18001BC19
0x18001ba13  mov     r8, r14
0x18001ba16  inc     r8; MaxCount
0x18001ba19  cmp     [rbx+r8*2], r12w
0x18001ba1e  jnz     short loc_18001BA16
0x18001ba20  lea     rdx, [r13+0Ch]; String2
0x18001ba24  mov     rcx, rbx; String1
0x18001ba27  call    cs:__imp__wcsnicmp
0x18001ba2d  test    eax, eax
0x18001ba2f  jnz     loc_18001BC6D
0x18001ba35  inc     r14
0x18001ba38  cmp     [rbx+r14*2], r12w
0x18001ba3d  jnz     short loc_18001BA35
0x18001ba3f  lea     rdx, ds:0Ch[r14*2]
0x18001ba47  add     rdx, r13
0x18001ba4a  lea     rcx, [rbp+var_18]
0x18001ba4e  call    AslPathToSystemPath
0x18001ba53  xor     r14d, r14d
0x18001ba56  mov     ebx, eax
0x18001ba58  test    eax, eax
0x18001ba5a  jns     loc_18001BB32
0x18001ba60  lea     r9, aFailedToAlloca_13; "Failed to allocate or convert stub path"...
0x18001ba67  mov     r8d, 50Eh
0x18001ba6d  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001ba74  mov     ecx, edi
0x18001ba76  call    AslLogCallPrintf
0x18001ba7b  mov     rsi, [rbp+var_18]
0x18001ba7f  mov     r12, [rbp+KeyValueInformation]
0x18001ba83  mov     rcx, [rbp+KeyHandle]; Handle
0x18001ba87  lea     rax, [rcx-1]
0x18001ba8b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ba8f  jbe     short loc_18001BAF7
0x18001ba91  test    rsi, rsi
0x18001ba94  jnz     loc_18001BCC2
0x18001ba9a  test    r12, r12
0x18001ba9d  jz      short loc_18001BAB4
0x18001ba9f  mov     rcx, gs:60h
0x18001baa8  mov     rdx, r12
0x18001baab  mov     rcx, [rcx+30h]
0x18001baaf  call    AslFree
0x18001bab4  test    r13, r13
0x18001bab7  jz      short loc_18001BACE
0x18001bab9  mov     rcx, gs:60h
0x18001bac2  mov     rdx, r13
0x18001bac5  mov     rcx, [rcx+30h]
0x18001bac9  call    AslFree
0x18001bace  mov     eax, ebx
0x18001bad0  mov     rbx, [rsp+50h+arg_8]
0x18001bad8  add     rsp, 50h
0x18001badc  pop     r15
0x18001bade  pop     r14
0x18001bae0  pop     r13
0x18001bae2  pop     r12
0x18001bae4  pop     rdi
0x18001bae5  pop     rsi
0x18001bae6  pop     rbp
0x18001bae7  retn
0x18001bae8  mov     rax, [rbp+KeyValueInformation]
0x18001baec  mov     ebx, [rbp+arg_18]
0x18001baef  add     r12d, edi
0x18001baf2  jmp     loc_18001B916
0x18001baf7  call    cs:__imp_ZwClose
0x18001bafd  jmp     short loc_18001BA91
0x18001baff  mov     r12, [rbp+KeyValueInformation]
0x18001bb03  mov     ebx, 0C0000034h
0x18001bb08  jmp     loc_18001BA83
0x18001bb0d  mov     ebx, 0C0000017h
0x18001bb12  lea     r9, aFailedToAlloca_20; "Failed to allocate basic info."
0x18001bb19  mov     r8d, 4EAh
0x18001bb1f  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001bb26  mov     ecx, edi
0x18001bb28  call    AslLogCallPrintf
0x18001bb2d  jmp     loc_18001BA7F
0x18001bb32  mov     rsi, [rbp+var_18]
0x18001bb36  test    rsi, rsi
0x18001bb39  jz      loc_18001BC99
0x18001bb3f  mov     rax, [rbp+arg_0]
0x18001bb43  mov     ebx, r14d
0x18001bb46  mov     [rax], rsi
0x18001bb49  mov     rsi, r14
0x18001bb4c  jmp     loc_18001BA7F
0x18001bb51  mov     ebx, 0C0000034h
0x18001bb56  jmp     loc_18001BACE
0x18001bb5b  lea     r9, aFailedToAlloca_5; "Failed to allocate partial info."
0x18001bb62  mov     r8d, 4C6h
0x18001bb68  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001bb6f  mov     ecx, edi
0x18001bb71  mov     ebx, 0C0000017h
0x18001bb76  call    AslLogCallPrintf
0x18001bb7b  jmp     loc_18001BA83
0x18001bb80  mov     eax, 0C00000EFh
0x18001bb85  jmp     loc_18001BAD0
0x18001bb8a  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x18001bb91  mov     [rsp+50h+Length], eax
0x18001bb95  mov     r8d, 4A2h
0x18001bb9b  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001bba2  mov     ecx, 1
0x18001bba7  call    AslLogCallPrintf
0x18001bbac  jmp     loc_18001BACE
0x18001bbb1  cmp     eax, 0C0000034h
0x18001bbb6  jz      loc_18001BA83
0x18001bbbc  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x18001bbc3  mov     [rsp+50h+Length], eax
0x18001bbc7  mov     r8d, 4B2h
0x18001bbcd  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001bbd4  mov     ecx, edi
0x18001bbd6  call    AslLogCallPrintf
0x18001bbdb  jmp     loc_18001BA83
0x18001bbe0  add     ebx, edi
0x18001bbe2  cmp     ebx, 0Ah
0x18001bbe5  jl      loc_18001B8A3
0x18001bbeb  jmp     loc_18001BB03
0x18001bbf0  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x18001bbf7  mov     r8d, 4F5h
0x18001bbfd  jmp     loc_18001BB1F
0x18001bc02  mov     ebx, 0C0000023h
0x18001bc07  lea     r9, aBufferTooSmall_1; "Buffer too small to query basic info."
0x18001bc0e  mov     r8d, 4FAh
0x18001bc14  jmp     loc_18001BB1F
0x18001bc19  xor     edx, edx; hFile
0x18001bc1b  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18001bc22  mov     r8d, 800h; dwFlags
0x18001bc28  mov     ebx, 7FFE0030h
0x18001bc2d  call    cs:__imp_LoadLibraryExW
0x18001bc33  mov     rsi, rax
0x18001bc36  test    rax, rax
0x18001bc39  jz      short loc_18001BC61
0x18001bc3b  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18001bc42  mov     rcx, rax; hModule
0x18001bc45  call    cs:__imp_GetProcAddress
0x18001bc4b  test    rax, rax
0x18001bc4e  jz      short loc_18001BC58
0x18001bc50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc55  mov     rbx, rax
0x18001bc58  mov     rcx, rsi; hLibModule
0x18001bc5b  call    cs:__imp_FreeLibrary
0x18001bc61  mov     cs:qword_18015BF38, rbx
0x18001bc68  jmp     loc_18001BA13
0x18001bc6d  lea     rdx, [r13+0Ch]
0x18001bc71  lea     rcx, [rbp+var_18]
0x18001bc75  call    AslStringDuplicate
0x18001bc7a  xor     r14d, r14d
0x18001bc7d  mov     ebx, eax
0x18001bc7f  test    eax, eax
0x18001bc81  jns     loc_18001BB32
0x18001bc87  lea     r9, aFailedToDuplic_4; "Failed to duplicate stub path."
0x18001bc8e  mov     r8d, 515h
0x18001bc94  jmp     loc_18001BA6D
0x18001bc99  mov     ebx, 0C0000017h
0x18001bc9e  lea     r9, aFailedToAlloca_33; "Failed to allocate stub path."
0x18001bca5  mov     r8d, 51Ch
0x18001bcab  jmp     loc_18001BB1F
0x18001bcb0  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x18001bcb7  mov     r8d, 4D9h
0x18001bcbd  jmp     loc_18001BB1F
0x18001bcc2  mov     rcx, gs:60h
0x18001bccb  mov     rdx, rsi
0x18001bcce  mov     rcx, [rcx+30h]
0x18001bcd2  call    AslFree
0x18001bcd7  jmp     loc_18001BA9A
```
