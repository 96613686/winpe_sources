# OpenSubkeys::EnsureInitialized(_OBJECT_ATTRIBUTES *)

- ea: `0x1800499b4`
- end: `0x180049add`
- name: `?EnsureInitialized@OpenSubkeys@@AEAAJPEAU_OBJECT_ATTRIBUTES@@@Z`
- size: `297`
- prototype: `int(OpenSubkeys *__hidden this, struct _OBJECT_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049634`

## callees

- `0x1800053a0`
- `0x18002aef0`
- `0x18002d2d8`
- `0x1800499b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800499ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049a6e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800499ea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049a6e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800499dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049a60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800499dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049a60`
- `ntdll!NtQueryOpenSubKeysEx` at `0x180049a3d`
- `ntdll!NtQueryOpenSubKeysEx` at `0x180049aa6`
- `ntdll!NtQueryOpenSubKeysEx` at `0x180049a3d`
- `ntdll!NtQueryOpenSubKeysEx` at `0x180049aa6`

## string_xrefs

- `0x180049a13`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`
- `0x180049aba`: `onecore\ds\security\gina\profile\profsvc\profreg.cpp`

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
0x1800499b4  mov     [rsp+arg_8], rbx
0x1800499b9  mov     [rsp+arg_10], rsi
0x1800499be  push    rdi; int
0x1800499bf  sub     rsp, 20h
0x1800499c3  cmp     qword ptr [rcx], 0
0x1800499c7  mov     rsi, rdx
0x1800499ca  mov     rdi, rcx
0x1800499cd  jnz     loc_180049ACB
0x1800499d3  mov     ebx, 400h
0x1800499d8  mov     [rsp+28h+RequiredSize], ebx
0x1800499dc  call    cs:__imp_GetProcessHeap
0x1800499e2  mov     r8d, ebx; dwBytes
0x1800499e5  xor     edx, edx; dwFlags
0x1800499e7  mov     rcx, rax; hHeap
0x1800499ea  call    cs:__imp_HeapAlloc
0x1800499f0  mov     rcx, [rdi]
0x1800499f3  mov     rbx, rax
0x1800499f6  mov     [rdi], rax
0x1800499f9  test    rcx, rcx
0x1800499fc  jz      short loc_180049A03
0x1800499fe  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180049a03  cmp     qword ptr [rdi], 0
0x180049a07  jnz     short loc_180049A2E
0x180049a09  mov     edx, 50h ; 'P'; void *
0x180049a0e  mov     rcx, [rsp+28h]; this
0x180049a13  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180049a1a  mov     ebx, 8007000Eh
0x180049a1f  mov     r9d, ebx; char *
0x180049a22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049a27  mov     eax, ebx
0x180049a29  jmp     loc_180049ACD
0x180049a2e  mov     edx, [rsp+28h+RequiredSize]; BufferLength
0x180049a32  lea     r9, [rsp+28h+RequiredSize]; RequiredSize
0x180049a37  mov     r8, rbx; Buffer
0x180049a3a  mov     rcx, rsi; TargetKey
0x180049a3d  call    cs:__imp_NtQueryOpenSubKeysEx
0x180049a43  cmp     eax, 80000005h
0x180049a48  jz      short loc_180049A5C
0x180049a4a  cmp     eax, 0C0000004h
0x180049a4f  jz      short loc_180049A5C
0x180049a51  test    eax, eax
0x180049a53  jns     short loc_180049ACB
0x180049a55  mov     edx, 5Dh ; ']'
0x180049a5a  jmp     short loc_180049AB5
0x180049a5c  mov     ebx, [rsp+28h+RequiredSize]
0x180049a60  call    cs:__imp_GetProcessHeap
0x180049a66  mov     r8d, ebx; dwBytes
0x180049a69  xor     edx, edx; dwFlags
0x180049a6b  mov     rcx, rax; hHeap
0x180049a6e  call    cs:__imp_HeapAlloc
0x180049a74  mov     rcx, [rdi]
0x180049a77  mov     rbx, rax
0x180049a7a  mov     [rdi], rax
0x180049a7d  test    rcx, rcx
0x180049a80  jz      short loc_180049A87
0x180049a82  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x180049a87  cmp     qword ptr [rdi], 0
0x180049a8b  jnz     short loc_180049A97
0x180049a8d  mov     edx, 57h ; 'W'
0x180049a92  jmp     loc_180049A0E
0x180049a97  mov     edx, [rsp+28h+RequiredSize]; BufferLength
0x180049a9b  lea     r9, [rsp+28h+RequiredSize]; RequiredSize
0x180049aa0  mov     r8, rbx; Buffer
0x180049aa3  mov     rcx, rsi; TargetKey
0x180049aa6  call    cs:__imp_NtQueryOpenSubKeysEx
0x180049aac  test    eax, eax
0x180049aae  jns     short loc_180049ACB
0x180049ab0  mov     edx, 59h ; 'Y'; void *
0x180049ab5  mov     rcx, [rsp+28h]; this
0x180049aba  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\gina\\profile\\p"...
0x180049ac1  mov     r9d, eax; char *
0x180049ac4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180049ac9  jmp     short loc_180049ACD
0x180049acb  xor     eax, eax
0x180049acd  mov     rbx, [rsp+28h+arg_8]
0x180049ad2  mov     rsi, [rsp+28h+arg_10]
0x180049ad7  add     rsp, 20h
0x180049adb  pop     rdi
0x180049adc  retn
```
