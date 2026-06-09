# OpenSubkeys::EnsureInitialized(_OBJECT_ATTRIBUTES *)

- ea: `0x18004be9c`
- end: `0x18004bfee`
- name: `?EnsureInitialized@OpenSubkeys@@AEAAJPEAU_OBJECT_ATTRIBUTES@@@Z`
- size: `338`
- prototype: `int(OpenSubkeys *__hidden this, struct _OBJECT_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004bb10`

## callees

- `0x18000b060`
- `0x180030ad0`
- `0x1800364c8`
- `0x18004be9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bed8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bf72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bed8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004bf72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bf5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bec4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bf5e`
- `ntdll!NtQueryOpenSubKeysEx` at `0x18004bf31`
- `ntdll!NtQueryOpenSubKeysEx` at `0x18004bfb0`
- `ntdll!NtQueryOpenSubKeysEx` at `0x18004bf31`
- `ntdll!NtQueryOpenSubKeysEx` at `0x18004bfb0`

## string_xrefs

- `0x18004bf07`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x18004bfca`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

## pseudocode

```c
int __fastcall OpenSubkeys::EnsureInitialized(OpenSubkeys *this, struct _OBJECT_ATTRIBUTES *a2)
{
  HANDLE ProcessHeap; // rax
  LPVOID v5; // rax
  __int64 v6; // rcx
  void *v7; // rbx
  __int64 v8; // rdx
  NTSTATUS v10; // eax
  __int64 v11; // rdx
  ULONG v12; // ebx
  HANDLE v13; // rax
  LPVOID v14; // rax
  __int64 v15; // rcx
  void *v16; // rbx
  int v17; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG RequiredSize; // [rsp+30h] [rbp+8h] BYREF

  if ( !*(_QWORD *)this )
  {
    RequiredSize = 1024;
    ProcessHeap = GetProcessHeap();
    v5 = HeapAlloc(ProcessHeap, 0, 0x400u);
    v6 = *(_QWORD *)this;
    v7 = v5;
    *(_QWORD *)this = v5;
    if ( v6 )
      Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v6);
    if ( !*(_QWORD *)this )
    {
      v8 = 80;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
        (const char *)0x8007000ELL,
        v17);
      return -2147024882;
    }
    v10 = NtQueryOpenSubKeysEx(a2, RequiredSize, v7, &RequiredSize);
    if ( v10 == -2147483643 || v10 == -1073741820 )
    {
      v12 = RequiredSize;
      v13 = GetProcessHeap();
      v14 = HeapAlloc(v13, 0, v12);
      v15 = *(_QWORD *)this;
      v16 = v14;
      *(_QWORD *)this = v14;
      if ( v15 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v15);
      if ( !*(_QWORD *)this )
      {
        v8 = 87;
        goto LABEL_6;
      }
      v10 = NtQueryOpenSubKeysEx(a2, RequiredSize, v16, &RequiredSize);
      if ( v10 < 0 )
      {
        v11 = 89;
        return wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)v11,
                 (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
                 (const char *)(unsigned int)v10,
                 v17);
      }
    }
    else if ( v10 < 0 )
    {
      v11 = 93;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v11,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profreg.cpp",
               (const char *)(unsigned int)v10,
               v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004be9c  mov     [rsp+arg_8], rbx
0x18004bea1  mov     [rsp+arg_10], rsi
0x18004bea6  push    rdi; int
0x18004bea7  sub     rsp, 20h
0x18004beab  cmp     qword ptr [rcx], 0
0x18004beaf  mov     rsi, rdx
0x18004beb2  mov     rdi, rcx
0x18004beb5  jnz     loc_18004BFDB
0x18004bebb  mov     ebx, 400h
0x18004bec0  mov     [rsp+28h+RequiredSize], ebx
0x18004bec4  call    cs:__imp_GetProcessHeap
0x18004becb  nop     dword ptr [rax+rax+00h]
0x18004bed0  mov     r8d, ebx; dwBytes
0x18004bed3  xor     edx, edx; dwFlags
0x18004bed5  mov     rcx, rax; hHeap
0x18004bed8  call    cs:__imp_HeapAlloc
0x18004bedf  nop     dword ptr [rax+rax+00h]
0x18004bee4  mov     rcx, [rdi]
0x18004bee7  mov     rbx, rax
0x18004beea  mov     [rdi], rax
0x18004beed  test    rcx, rcx
0x18004bef0  jz      short loc_18004BEF7
0x18004bef2  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004bef7  cmp     qword ptr [rdi], 0
0x18004befb  jnz     short loc_18004BF22
0x18004befd  mov     edx, 50h ; 'P'; void *
0x18004bf02  mov     rcx, [rsp+28h]; this
0x18004bf07  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bf0e  mov     ebx, 8007000Eh
0x18004bf13  mov     r9d, ebx; char *
0x18004bf16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bf1b  mov     eax, ebx
0x18004bf1d  jmp     loc_18004BFDD
0x18004bf22  mov     edx, [rsp+28h+RequiredSize]; BufferLength
0x18004bf26  lea     r9, [rsp+28h+RequiredSize]; RequiredSize
0x18004bf2b  mov     r8, rbx; Buffer
0x18004bf2e  mov     rcx, rsi; TargetKey
0x18004bf31  call    cs:__imp_NtQueryOpenSubKeysEx
0x18004bf38  nop     dword ptr [rax+rax+00h]
0x18004bf3d  cmp     eax, 80000005h
0x18004bf42  jz      short loc_18004BF5A
0x18004bf44  cmp     eax, 0C0000004h
0x18004bf49  jz      short loc_18004BF5A
0x18004bf4b  test    eax, eax
0x18004bf4d  jns     loc_18004BFDB
0x18004bf53  mov     edx, 5Dh ; ']'
0x18004bf58  jmp     short loc_18004BFC5
0x18004bf5a  mov     ebx, [rsp+28h+RequiredSize]
0x18004bf5e  call    cs:__imp_GetProcessHeap
0x18004bf65  nop     dword ptr [rax+rax+00h]
0x18004bf6a  mov     r8d, ebx; dwBytes
0x18004bf6d  xor     edx, edx; dwFlags
0x18004bf6f  mov     rcx, rax; hHeap
0x18004bf72  call    cs:__imp_HeapAlloc
0x18004bf79  nop     dword ptr [rax+rax+00h]
0x18004bf7e  mov     rcx, [rdi]
0x18004bf81  mov     rbx, rax
0x18004bf84  mov     [rdi], rax
0x18004bf87  test    rcx, rcx
0x18004bf8a  jz      short loc_18004BF91
0x18004bf8c  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18004bf91  cmp     qword ptr [rdi], 0
0x18004bf95  jnz     short loc_18004BFA1
0x18004bf97  mov     edx, 57h ; 'W'
0x18004bf9c  jmp     loc_18004BF02
0x18004bfa1  mov     edx, [rsp+28h+RequiredSize]; BufferLength
0x18004bfa5  lea     r9, [rsp+28h+RequiredSize]; RequiredSize
0x18004bfaa  mov     r8, rbx; Buffer
0x18004bfad  mov     rcx, rsi; TargetKey
0x18004bfb0  call    cs:__imp_NtQueryOpenSubKeysEx
0x18004bfb7  nop     dword ptr [rax+rax+00h]
0x18004bfbc  test    eax, eax
0x18004bfbe  jns     short loc_18004BFDB
0x18004bfc0  mov     edx, 59h ; 'Y'; void *
0x18004bfc5  mov     rcx, [rsp+28h]; this
0x18004bfca  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004bfd1  mov     r9d, eax; char *
0x18004bfd4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004bfd9  jmp     short loc_18004BFDD
0x18004bfdb  xor     eax, eax
0x18004bfdd  mov     rbx, [rsp+28h+arg_8]
0x18004bfe2  mov     rsi, [rsp+28h+arg_10]
0x18004bfe7  add     rsp, 20h
0x18004bfeb  pop     rdi
0x18004bfec  retn
```
