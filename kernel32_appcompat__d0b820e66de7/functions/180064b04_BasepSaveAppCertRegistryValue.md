# BasepSaveAppCertRegistryValue

- ea: `0x180064b04`
- end: `0x180064cd2`
- name: `BasepSaveAppCertRegistryValue`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180064360`

## callees

- `0x180064b04`
- `0x180082751`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180064b25`
- `ntdll!RtlInitUnicodeStringEx` at `0x180064b25`
- `ntdll!RtlCompareUnicodeString` at `0x180064b49`
- `ntdll!RtlCompareUnicodeString` at `0x180064b49`
- `ntdll!RtlFreeHeap` at `0x180064c4c`
- `ntdll!RtlFreeHeap` at `0x180064cab`
- `ntdll!RtlFreeHeap` at `0x180064c4c`
- `ntdll!RtlFreeHeap` at `0x180064cab`
- `ntdll!RtlAllocateHeap` at `0x180064b96`
- `ntdll!RtlAllocateHeap` at `0x180064b96`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180064b71`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180064b71`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064c67`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064c67`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180064cba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180064cba`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180064c05`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180064c05`

## string_xrefs

- `0x180064c5d`: `CreateProcessNotify`

## pseudocode

```c
NTSTATUS __fastcall BasepSaveAppCertRegistryValue(const UNICODE_STRING **a1, const WCHAR *a2, const WCHAR *a3)
{
  NTSTATUS result; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const UNICODE_STRING *i; // rbx
  ULONG *GlobalData; // rax
  const UNICODE_STRING ***Heap; // rax
  const UNICODE_STRING ***v13; // rbx
  const UNICODE_STRING ***v14; // rax
  HMODULE LibraryW; // rax
  HMODULE v16; // rdi
  const UNICODE_STRING **v17; // rax
  const UNICODE_STRING ****v18; // rcx
  FARPROC ProcAddress; // rax
  const UNICODE_STRING **v20; // rax
  const UNICODE_STRING ****v21; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-18h] BYREF

  String2 = 0;
  result = RtlInitUnicodeStringEx(&String2, a2);
  if ( result >= 0 )
  {
    for ( i = *a1; i != (const UNICODE_STRING *)a1; i = *(const UNICODE_STRING **)&i->Length )
    {
      if ( !RtlCompareUnicodeString(i + 1, &String2, 1u) )
        return 0;
    }
    GlobalData = (ULONG *)KernelBaseGetGlobalData(v7, v6, v8, v9);
    Heap = (const UNICODE_STRING ***)RtlAllocateHeap(
                                       NtCurrentPeb()->ProcessHeap,
                                       *GlobalData,
                                       String2.MaximumLength + 40LL);
    v13 = Heap;
    if ( !Heap )
      return -1073741801;
    Heap[1] = (const UNICODE_STRING **)Heap;
    *Heap = (const UNICODE_STRING **)Heap;
    Heap[3] = (const UNICODE_STRING **)(Heap + 5);
    *((_WORD *)Heap + 8) = String2.Length;
    *((_WORD *)Heap + 9) = String2.MaximumLength;
    memcpy_0(Heap + 5, String2.Buffer, String2.MaximumLength);
    v14 = (const UNICODE_STRING ***)a1[1];
    if ( *v14 == a1 )
    {
      *v13 = a1;
      v13[1] = (const UNICODE_STRING **)v14;
      *v14 = (const UNICODE_STRING **)v13;
      a1[1] = (const UNICODE_STRING *)v13;
      if ( a3 && (LibraryW = LoadLibraryW(a3), (v16 = LibraryW) != 0) )
      {
        ProcAddress = GetProcAddress(LibraryW, "CreateProcessNotify");
        v13[4] = (const UNICODE_STRING **)ProcAddress;
        if ( ProcAddress )
          return 0;
        v20 = *v13;
        if ( (*v13)[1] == (const UNICODE_STRING *)v13 )
        {
          v21 = (const UNICODE_STRING ****)v13[1];
          if ( *v21 == v13 )
          {
            *v21 = (const UNICODE_STRING ***)v20;
            v20[1] = (const UNICODE_STRING *)v21;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
            FreeLibrary(v16);
            return 0;
          }
        }
      }
      else
      {
        v17 = *v13;
        if ( (*v13)[1] == (const UNICODE_STRING *)v13 )
        {
          v18 = (const UNICODE_STRING ****)v13[1];
          if ( *v18 == v13 )
          {
            *v18 = (const UNICODE_STRING ***)v17;
            v17[1] = (const UNICODE_STRING *)v18;
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
            return 0;
          }
        }
      }
    }
    __fastfail(3u);
  }
  return result;
}

```

## disassembly

```asm
0x180064b04  mov     rax, rsp
0x180064b07  mov     [rax+8], rbx
0x180064b0b  mov     [rax+10h], rsi
0x180064b0f  push    rdi
0x180064b10  sub     rsp, 30h
0x180064b14  mov     rdi, rcx
0x180064b17  xorps   xmm0, xmm0
0x180064b1a  lea     rcx, [rax-18h]; DestinationString
0x180064b1e  mov     rsi, r8
0x180064b21  movups  xmmword ptr [rax-18h], xmm0
0x180064b25  call    cs:__imp_RtlInitUnicodeStringEx
0x180064b2c  nop     dword ptr [rax+rax+00h]
0x180064b31  test    eax, eax
0x180064b33  js      short loc_180064B60
0x180064b35  mov     rbx, [rdi]
0x180064b38  cmp     rbx, rdi
0x180064b3b  jz      short loc_180064B71
0x180064b3d  lea     rcx, [rbx+10h]; String1
0x180064b41  mov     r8b, 1; CaseInsensitive
0x180064b44  lea     rdx, [rsp+38h+String2]; String2
0x180064b49  call    cs:__imp_RtlCompareUnicodeString
0x180064b50  nop     dword ptr [rax+rax+00h]
0x180064b55  test    eax, eax
0x180064b57  jz      short loc_180064B5E
0x180064b59  mov     rbx, [rbx]
0x180064b5c  jmp     short loc_180064B38
0x180064b5e  xor     eax, eax
0x180064b60  mov     rbx, [rsp+38h+arg_0]
0x180064b65  mov     rsi, [rsp+38h+arg_8]
0x180064b6a  add     rsp, 30h
0x180064b6e  pop     rdi
0x180064b6f  retn
0x180064b71  call    cs:__imp_KernelBaseGetGlobalData
0x180064b78  nop     dword ptr [rax+rax+00h]
0x180064b7d  mov     rcx, gs:60h
0x180064b86  movzx   r8d, [rsp+38h+String2.MaximumLength]
0x180064b8c  add     r8, 28h ; '('; Size
0x180064b90  mov     edx, [rax]; Flags
0x180064b92  mov     rcx, [rcx+30h]; HeapHandle
0x180064b96  call    cs:__imp_RtlAllocateHeap
0x180064b9d  nop     dword ptr [rax+rax+00h]
0x180064ba2  mov     rbx, rax
0x180064ba5  test    rax, rax
0x180064ba8  jnz     short loc_180064BB1
0x180064baa  mov     eax, 0C0000017h
0x180064baf  jmp     short loc_180064B60
0x180064bb1  mov     [rax+8], rbx
0x180064bb5  lea     rcx, [rax+28h]; void *
0x180064bb9  mov     [rax], rbx
0x180064bbc  mov     [rax+18h], rcx
0x180064bc0  movzx   eax, [rsp+38h+String2.Length]
0x180064bc5  mov     [rbx+10h], ax
0x180064bc9  movzx   eax, [rsp+38h+String2.MaximumLength]
0x180064bce  mov     [rbx+12h], ax
0x180064bd2  movzx   r8d, [rsp+38h+String2.MaximumLength]; Size
0x180064bd8  mov     rdx, [rsp+38h+String2.Buffer]; Src
0x180064bdd  call    memcpy_0
0x180064be2  mov     rax, [rdi+8]
0x180064be6  cmp     [rax], rdi
0x180064be9  jnz     loc_180064CCB
0x180064bef  mov     [rbx], rdi
0x180064bf2  mov     [rbx+8], rax
0x180064bf6  mov     [rax], rbx
0x180064bf9  mov     [rdi+8], rbx
0x180064bfd  test    rsi, rsi
0x180064c00  jz      short loc_180064C19
0x180064c02  mov     rcx, rsi; lpLibFileName
0x180064c05  call    cs:__imp_LoadLibraryW
0x180064c0c  nop     dword ptr [rax+rax+00h]
0x180064c11  mov     rdi, rax
0x180064c14  test    rax, rax
0x180064c17  jnz     short loc_180064C5D
0x180064c19  mov     rax, [rbx]
0x180064c1c  cmp     [rax+8], rbx
0x180064c20  jnz     loc_180064CCB
0x180064c26  mov     rcx, [rbx+8]
0x180064c2a  cmp     [rcx], rbx
0x180064c2d  jnz     loc_180064CCB
0x180064c33  mov     [rcx], rax
0x180064c36  mov     r8, rbx; P
0x180064c39  mov     [rax+8], rcx
0x180064c3d  xor     edx, edx; Flags
0x180064c3f  mov     rcx, gs:60h
0x180064c48  mov     rcx, [rcx+30h]; HeapHandle
0x180064c4c  call    cs:__imp_RtlFreeHeap
0x180064c53  nop     dword ptr [rax+rax+00h]
0x180064c58  jmp     loc_180064B5E
0x180064c5d  lea     rdx, aCreateprocessn; "CreateProcessNotify"
0x180064c64  mov     rcx, rdi; hModule
0x180064c67  call    cs:__imp_GetProcAddress
0x180064c6e  nop     dword ptr [rax+rax+00h]
0x180064c73  mov     [rbx+20h], rax
0x180064c77  test    rax, rax
0x180064c7a  jnz     loc_180064B5E
0x180064c80  mov     rax, [rbx]
0x180064c83  cmp     [rax+8], rbx
0x180064c87  jnz     short loc_180064CCB
0x180064c89  mov     rcx, [rbx+8]
0x180064c8d  cmp     [rcx], rbx
0x180064c90  jnz     short loc_180064CCB
0x180064c92  mov     [rcx], rax
0x180064c95  mov     r8, rbx; P
0x180064c98  mov     [rax+8], rcx
0x180064c9c  xor     edx, edx; Flags
0x180064c9e  mov     rcx, gs:60h
0x180064ca7  mov     rcx, [rcx+30h]; HeapHandle
0x180064cab  call    cs:__imp_RtlFreeHeap
0x180064cb2  nop     dword ptr [rax+rax+00h]
0x180064cb7  mov     rcx, rdi; hLibModule
0x180064cba  call    cs:__imp_FreeLibrary
0x180064cc1  nop     dword ptr [rax+rax+00h]
0x180064cc6  jmp     loc_180064B5E
0x180064ccb  mov     ecx, 3
0x180064cd0  int     29h; Win8: RtlFailFast(ecx)
```
