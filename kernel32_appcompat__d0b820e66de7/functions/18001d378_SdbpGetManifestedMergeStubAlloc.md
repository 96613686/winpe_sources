# SdbpGetManifestedMergeStubAlloc

- ea: `0x18001d378`
- end: `0x18001d7eb`
- name: `SdbpGetManifestedMergeStubAlloc`
- size: `1139`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800210a8`
- `0x1800224f4`

## callees

- `0x18001ccac`
- `0x18001cd68`
- `0x18001ce78`
- `0x18001d378`
- `0x18001e7f0`
- `0x18001ef8c`
- `0x18001f138`
- `0x18001f31c`
- `0x18001f5ec`
- `0x180061d88`
- `0x180061df4`

## import_xrefs

- `ntdll!ZwClose` at `0x18001d667`
- `ntdll!ZwClose` at `0x18001d667`
- `ntdll!ZwEnumerateValueKey` at `0x18001d49b`
- `ntdll!ZwEnumerateValueKey` at `0x18001d50f`
- `ntdll!ZwEnumerateValueKey` at `0x18001d49b`
- `ntdll!ZwEnumerateValueKey` at `0x18001d50f`
- `ntdll!RtlAllocateHeap` at `0x18001d462`
- `ntdll!RtlAllocateHeap` at `0x18001d4dd`
- `ntdll!RtlAllocateHeap` at `0x18001d462`
- `ntdll!RtlAllocateHeap` at `0x18001d4dd`

## string_xrefs

- `0x18001d3e9`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates\ManifestedMergeStubSdbs`
- `0x18001d599`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001d68a`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001d6f2`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001d723`: `SdbpGetManifestedMergeStubAlloc`
- `0x18001d58c`: `Failed to allocate or convert stub path.`
- `0x18001d6e1`: `AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]`
- `0x18001d79b`: `Failed to duplicate stub path.`
- `0x18001d7ad`: `Failed to allocate stub path.`

## pseudocode

```c
__int64 __fastcall SdbpGetManifestedMergeStubAlloc(_QWORD *a1, const wchar_t *a2)
{
  __int64 v3; // rsi
  NTSTATUS MergeSdbsDisabled; // ebx
  wchar_t *Heap; // r12
  wchar_t *v6; // r13
  int Key; // eax
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rax
  ULONG Length; // ebx
  ULONG v12; // eax
  NTSTATUS v13; // eax
  ULONG v14; // ebx
  unsigned __int64 v15; // r15
  const wchar_t *NtSystemRoot; // rax
  const wchar_t *v17; // rbx
  size_t v18; // r8
  const char *v19; // r9
  int v20; // r8d
  __int64 v22; // rax
  const char *v23; // r9
  int v24; // r8d
  ULONG v25; // [rsp+30h] [rbp-20h]
  __int64 v26; // [rsp+38h] [rbp-18h] BYREF
  HANDLE KeyHandle[2]; // [rsp+40h] [rbp-10h] BYREF
  ULONG Index; // [rsp+A0h] [rbp+50h] BYREF
  ULONG ResultLength; // [rsp+A8h] [rbp+58h] BYREF

  Index = 0;
  v3 = 0;
  ResultLength = 0;
  v26 = 0;
  KeyHandle[0] = 0;
  if ( a1 )
  {
    *a1 = 0;
    if ( (unsigned int)SdbpGetMergeSdbsSupported() )
    {
      MergeSdbsDisabled = SdbpGetMergeSdbsDisabled(&Index);
      if ( MergeSdbsDisabled < 0 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbpGetManifestedMergeStubAlloc",
          1184,
          (unsigned int)"SdbpGetMergeSdbsDisabled failed [%x]");
        return (unsigned int)MergeSdbsDisabled;
      }
      if ( !Index )
      {
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
              1200,
              (unsigned int)"AslRegistryGetKey failed to open ManifestedMergeStubSdbs key [%x]");
        }
        else
        {
          v8 = 1;
          while ( wcsicmp_0(a2, (const wchar_t *)qword_180085038[4 * v8]) )
          {
            if ( (int)++v8 >= 10 )
            {
LABEL_12:
              MergeSdbsDisabled = -1073741772;
              goto LABEL_23;
            }
          }
          v9 = -1;
          v10 = -1;
          do
            ++v10;
          while ( a2[v10] );
          Length = 2 * v10 + 18;
          v25 = Length;
          Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, Length);
          v12 = 0;
          if ( Heap )
          {
            while ( 1 )
            {
              Index = v12;
              v13 = ZwEnumerateValueKey(KeyHandle[0], v12, KeyValuePartialInformation, Heap, Length, &ResultLength);
              MergeSdbsDisabled = v13;
              if ( v13 == -2147483622 )
                goto LABEL_12;
              if ( v13 != -2147483643 && v13 != -1073741789 )
              {
                if ( v13 < 0 )
                {
                  v23 = "Failed to query partial info.";
                  v24 = 1239;
                  goto LABEL_42;
                }
                if ( *((_DWORD *)Heap + 1) == 1 && !wcsicmp_0(a2, Heap + 6) )
                  break;
              }
              Length = v25;
              v12 = Index + 1;
            }
            v22 = -1;
            do
              ++v22;
            while ( a2[v22] );
            v14 = 2 * v22 + 538;
            v15 = v14;
            v6 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v14);
            if ( !v6 )
            {
              v23 = "Failed to allocate basic info.";
              v24 = 1256;
              goto LABEL_41;
            }
            MergeSdbsDisabled = ZwEnumerateValueKey(
                                  KeyHandle[0],
                                  Index,
                                  KeyValueBasicInformation,
                                  v6,
                                  v14,
                                  &ResultLength);
            if ( MergeSdbsDisabled < 0 )
            {
              v23 = "Failed to query basic info.";
              v24 = 1267;
              goto LABEL_42;
            }
            if ( (unsigned __int64)ResultLength + 2 > v15 )
            {
              MergeSdbsDisabled = -1073741789;
              v23 = "Buffer too small to query basic info.";
              v24 = 1272;
              goto LABEL_42;
            }
            NtSystemRoot = (const wchar_t *)RtlDownlevelGetNtSystemRoot();
            v17 = NtSystemRoot;
            v18 = -1;
            do
              ++v18;
            while ( NtSystemRoot[v18] );
            if ( wcsnicmp_0(NtSystemRoot, v6 + 6, v18) )
            {
              MergeSdbsDisabled = AslStringDuplicate(&v26, v6 + 6);
              if ( MergeSdbsDisabled < 0 )
              {
                v19 = "Failed to duplicate stub path.";
                v20 = 1299;
                goto LABEL_22;
              }
            }
            else
            {
              do
                ++v9;
              while ( v17[v9] );
              MergeSdbsDisabled = AslPathToSystemPath(&v26, &v6[v9 + 6]);
              if ( MergeSdbsDisabled < 0 )
              {
                v19 = "Failed to allocate or convert stub path.";
                v20 = 1292;
LABEL_22:
                AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v20, (_DWORD)v19);
                v3 = v26;
                goto LABEL_23;
              }
            }
            v3 = v26;
            if ( v26 )
            {
              MergeSdbsDisabled = 0;
              *a1 = v26;
              v3 = 0;
              goto LABEL_23;
            }
            v23 = "Failed to allocate stub path.";
            v24 = 1306;
          }
          else
          {
            v23 = "Failed to allocate partial info.";
            v24 = 1220;
          }
LABEL_41:
          MergeSdbsDisabled = -1073741801;
LABEL_42:
          AslLogCallPrintf(1, (unsigned int)"SdbpGetManifestedMergeStubAlloc", v24, (_DWORD)v23);
        }
LABEL_23:
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
0x18001d378  mov     [rsp-38h+arg_8], rbx
0x18001d37d  mov     [rsp-38h+arg_0], rcx
0x18001d382  push    rbp
0x18001d383  push    rsi
0x18001d384  push    rdi
0x18001d385  push    r12
0x18001d387  push    r13
0x18001d389  push    r14
0x18001d38b  push    r15
0x18001d38d  mov     rbp, rsp
0x18001d390  sub     rsp, 50h
0x18001d394  xor     r14d, r14d
0x18001d397  mov     r15, rdx
0x18001d39a  mov     [rbp+Index], r14d
0x18001d39e  mov     esi, r14d
0x18001d3a1  mov     [rbp+arg_18], r14d
0x18001d3a5  mov     [rbp+var_18], r14
0x18001d3a9  mov     [rbp+KeyHandle], r14
0x18001d3ad  test    rcx, rcx
0x18001d3b0  jz      loc_18001D6CC
0x18001d3b6  mov     [rcx], r14
0x18001d3b9  call    SdbpGetMergeSdbsSupported
0x18001d3be  test    eax, eax
0x18001d3c0  jz      loc_18001D708
0x18001d3c6  lea     rcx, [rbp+Index]
0x18001d3ca  call    SdbpGetMergeSdbsDisabled
0x18001d3cf  mov     ebx, eax
0x18001d3d1  test    eax, eax
0x18001d3d3  js      loc_18001D712
0x18001d3d9  cmp     [rbp+Index], r14d
0x18001d3dd  jnz     loc_18001D708
0x18001d3e3  mov     r8d, 80000100h
0x18001d3e9  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001d3f0  lea     rcx, [rbp+KeyHandle]
0x18001d3f4  mov     r12d, r14d
0x18001d3f7  mov     r13d, r14d
0x18001d3fa  call    AslRegistryGetKey
0x18001d3ff  mov     ebx, eax
0x18001d401  test    eax, eax
0x18001d403  js      loc_18001D6D6
0x18001d409  lea     edi, [r14+1]
0x18001d40d  mov     ebx, edi
0x18001d40f  lea     rax, qword_180085038
0x18001d416  mov     edx, ebx
0x18001d418  shl     rdx, 5
0x18001d41c  mov     rcx, r15; String1
0x18001d41f  mov     rdx, [rdx+rax]; String2
0x18001d423  call    _wcsicmp_0
0x18001d428  test    eax, eax
0x18001d42a  jnz     loc_18001D6BC
0x18001d430  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001d434  mov     rax, r14
0x18001d437  xor     ecx, ecx
0x18001d439  inc     rax
0x18001d43c  cmp     [r15+rax*2], cx
0x18001d441  jnz     short loc_18001D439
0x18001d443  mov     rcx, gs:60h
0x18001d44c  lea     ebx, ds:12h[rax*2]
0x18001d453  mov     r8d, ebx; Size
0x18001d456  mov     edx, 8; Flags
0x18001d45b  mov     [rbp+var_20], ebx
0x18001d45e  mov     rcx, [rcx+30h]; HeapHandle
0x18001d462  call    cs:__imp_RtlAllocateHeap
0x18001d469  nop     dword ptr [rax+rax+00h]
0x18001d46e  mov     r12, rax
0x18001d471  xor     eax, eax
0x18001d473  test    r12, r12
0x18001d476  jz      loc_18001D678
0x18001d47c  lea     rcx, [rbp+arg_18]
0x18001d480  mov     [rbp+Index], eax
0x18001d483  mov     [rsp+50h+ResultLength], rcx; ResultLength
0x18001d488  mov     r9, r12; KeyValueInformation
0x18001d48b  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001d48f  mov     r8d, 2; KeyValueInformationClass
0x18001d495  mov     edx, eax; Index
0x18001d497  mov     [rsp+50h+Length], ebx; Length
0x18001d49b  call    cs:__imp_ZwEnumerateValueKey
0x18001d4a2  nop     dword ptr [rax+rax+00h]
0x18001d4a7  mov     ebx, eax
0x18001d4a9  cmp     eax, 8000001Ah
0x18001d4ae  jnz     loc_18001D615
0x18001d4b4  mov     ebx, 0C0000034h
0x18001d4b9  jmp     loc_18001D5AB
0x18001d4be  mov     rcx, gs:60h
0x18001d4c7  lea     ebx, ds:21Ah[rax*2]
0x18001d4ce  mov     r8d, ebx; Size
0x18001d4d1  mov     edx, 8; Flags
0x18001d4d6  mov     r15d, ebx
0x18001d4d9  mov     rcx, [rcx+30h]; HeapHandle
0x18001d4dd  call    cs:__imp_RtlAllocateHeap
0x18001d4e4  nop     dword ptr [rax+rax+00h]
0x18001d4e9  mov     r13, rax
0x18001d4ec  test    rax, rax
0x18001d4ef  jz      loc_18001D746
0x18001d4f5  mov     edx, [rbp+Index]; Index
0x18001d4f8  lea     rax, [rbp+arg_18]
0x18001d4fc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001d500  mov     r9, r13; KeyValueInformation
0x18001d503  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18001d508  xor     r8d, r8d; KeyValueInformationClass
0x18001d50b  mov     [rsp+50h+Length], ebx; Length
0x18001d50f  call    cs:__imp_ZwEnumerateValueKey
0x18001d516  nop     dword ptr [rax+rax+00h]
0x18001d51b  mov     ebx, eax
0x18001d51d  test    eax, eax
0x18001d51f  js      loc_18001D758
0x18001d525  mov     eax, [rbp+arg_18]
0x18001d528  add     rax, 2
0x18001d52c  cmp     rax, r15
0x18001d52f  ja      loc_18001D76A
0x18001d535  call    RtlDownlevelGetNtSystemRoot
0x18001d53a  mov     rbx, rax
0x18001d53d  mov     r8, r14
0x18001d540  xor     r15d, r15d
0x18001d543  inc     r8; MaxCount
0x18001d546  cmp     [rax+r8*2], r15w
0x18001d54b  jnz     short loc_18001D543
0x18001d54d  lea     rdx, [r13+0Ch]; String2
0x18001d551  mov     rcx, rbx; String1
0x18001d554  call    _wcsnicmp_0
0x18001d559  test    eax, eax
0x18001d55b  jnz     loc_18001D781
0x18001d561  inc     r14
0x18001d564  cmp     [rbx+r14*2], r15w
0x18001d569  jnz     short loc_18001D561
0x18001d56b  lea     rdx, ds:0Ch[r14*2]
0x18001d573  add     rdx, r13
0x18001d576  lea     rcx, [rbp+var_18]
0x18001d57a  call    AslPathToSystemPath
0x18001d57f  xor     r14d, r14d
0x18001d582  mov     ebx, eax
0x18001d584  test    eax, eax
0x18001d586  jns     loc_18001D69D
0x18001d58c  lea     r9, aFailedToAlloca_3; "Failed to allocate or convert stub path"...
0x18001d593  mov     r8d, 50Ch
0x18001d599  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001d5a0  mov     ecx, edi
0x18001d5a2  call    AslLogCallPrintf
0x18001d5a7  mov     rsi, [rbp+var_18]
0x18001d5ab  mov     rcx, [rbp+KeyHandle]; Handle
0x18001d5af  lea     rax, [rcx-1]
0x18001d5b3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d5b7  jbe     loc_18001D667
0x18001d5bd  test    rsi, rsi
0x18001d5c0  jnz     loc_18001D7D1
0x18001d5c6  test    r12, r12
0x18001d5c9  jz      short loc_18001D5E0
0x18001d5cb  mov     rcx, gs:60h
0x18001d5d4  mov     rdx, r12
0x18001d5d7  mov     rcx, [rcx+30h]
0x18001d5db  call    AslFree
0x18001d5e0  test    r13, r13
0x18001d5e3  jz      short loc_18001D5FA
0x18001d5e5  mov     rcx, gs:60h
0x18001d5ee  mov     rdx, r13
0x18001d5f1  mov     rcx, [rcx+30h]
0x18001d5f5  call    AslFree
0x18001d5fa  mov     eax, ebx
0x18001d5fc  mov     rbx, [rsp+50h+arg_8]
0x18001d604  add     rsp, 50h
0x18001d608  pop     r15
0x18001d60a  pop     r14
0x18001d60c  pop     r13
0x18001d60e  pop     r12
0x18001d610  pop     rdi
0x18001d611  pop     rsi
0x18001d612  pop     rbp
0x18001d613  retn
0x18001d615  cmp     eax, 80000005h
0x18001d61a  jz      loc_18001D739
0x18001d620  cmp     eax, 0C0000023h
0x18001d625  jz      loc_18001D739
0x18001d62b  test    eax, eax
0x18001d62d  js      loc_18001D7BF
0x18001d633  cmp     [r12+4], edi
0x18001d638  jnz     loc_18001D739
0x18001d63e  lea     rdx, [r12+0Ch]; String2
0x18001d643  mov     rcx, r15; String1
0x18001d646  call    _wcsicmp_0
0x18001d64b  xor     ecx, ecx
0x18001d64d  test    eax, eax
0x18001d64f  jnz     loc_18001D739
0x18001d655  mov     rax, r14
0x18001d658  inc     rax
0x18001d65b  cmp     [r15+rax*2], cx
0x18001d660  jnz     short loc_18001D658
0x18001d662  jmp     loc_18001D4BE
0x18001d667  call    cs:__imp_ZwClose
0x18001d66e  nop     dword ptr [rax+rax+00h]
0x18001d673  jmp     loc_18001D5BD
0x18001d678  lea     r9, aFailedToAlloca_1; "Failed to allocate partial info."
0x18001d67f  mov     r8d, 4C4h
0x18001d685  mov     ebx, 0C0000017h
0x18001d68a  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001d691  mov     ecx, edi
0x18001d693  call    AslLogCallPrintf
0x18001d698  jmp     loc_18001D5AB
0x18001d69d  mov     rsi, [rbp+var_18]
0x18001d6a1  test    rsi, rsi
0x18001d6a4  jz      loc_18001D7AD
0x18001d6aa  mov     rax, [rbp+arg_0]
0x18001d6ae  mov     ebx, r14d
0x18001d6b1  mov     [rax], rsi
0x18001d6b4  mov     rsi, r14
0x18001d6b7  jmp     loc_18001D5AB
0x18001d6bc  add     ebx, edi
0x18001d6be  cmp     ebx, 0Ah
0x18001d6c1  jl      loc_18001D40F
0x18001d6c7  jmp     loc_18001D4B4
0x18001d6cc  mov     eax, 0C00000EFh
0x18001d6d1  jmp     loc_18001D5FC
0x18001d6d6  cmp     eax, 0C0000034h
0x18001d6db  jz      loc_18001D5AB
0x18001d6e1  lea     r9, aAslregistryget_2; "AslRegistryGetKey failed to open Manife"...
0x18001d6e8  mov     [rsp+50h+Length], eax
0x18001d6ec  mov     r8d, 4B0h
0x18001d6f2  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001d6f9  mov     ecx, 1
0x18001d6fe  call    AslLogCallPrintf
0x18001d703  jmp     loc_18001D5AB
0x18001d708  mov     ebx, 0C0000034h
0x18001d70d  jmp     loc_18001D5FA
0x18001d712  lea     r9, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled failed [%x]"
0x18001d719  mov     [rsp+50h+Length], eax
0x18001d71d  mov     r8d, 4A0h
0x18001d723  lea     rdx, aSdbpgetmanifes; "SdbpGetManifestedMergeStubAlloc"
0x18001d72a  mov     ecx, 1
0x18001d72f  call    AslLogCallPrintf
0x18001d734  jmp     loc_18001D5FA
0x18001d739  mov     eax, [rbp+Index]
0x18001d73c  mov     ebx, [rbp+var_20]
0x18001d73f  add     eax, edi
0x18001d741  jmp     loc_18001D47C
0x18001d746  lea     r9, aFailedToAlloca_7; "Failed to allocate basic info."
0x18001d74d  mov     r8d, 4E8h
0x18001d753  jmp     loc_18001D685
0x18001d758  lea     r9, aFailedToQueryB; "Failed to query basic info."
0x18001d75f  mov     r8d, 4F3h
0x18001d765  jmp     loc_18001D68A
0x18001d76a  mov     ebx, 0C0000023h
0x18001d76f  lea     r9, aBufferTooSmall_0; "Buffer too small to query basic info."
0x18001d776  mov     r8d, 4F8h
0x18001d77c  jmp     loc_18001D68A
0x18001d781  lea     rdx, [r13+0Ch]
0x18001d785  lea     rcx, [rbp+var_18]
0x18001d789  call    AslStringDuplicate
0x18001d78e  xor     r14d, r14d
0x18001d791  mov     ebx, eax
0x18001d793  test    eax, eax
0x18001d795  jns     loc_18001D69D
0x18001d79b  lea     r9, aFailedToDuplic; "Failed to duplicate stub path."
0x18001d7a2  mov     r8d, 513h
0x18001d7a8  jmp     loc_18001D599
0x18001d7ad  lea     r9, aFailedToAlloca_11; "Failed to allocate stub path."
0x18001d7b4  mov     r8d, 51Ah
0x18001d7ba  jmp     loc_18001D685
0x18001d7bf  lea     r9, aFailedToQueryP; "Failed to query partial info."
0x18001d7c6  mov     r8d, 4D7h
0x18001d7cc  jmp     loc_18001D68A
0x18001d7d1  mov     rcx, gs:60h
0x18001d7da  mov     rdx, rsi
0x18001d7dd  mov     rcx, [rcx+30h]
0x18001d7e1  call    AslFree
0x18001d7e6  jmp     loc_18001D5C6
```
