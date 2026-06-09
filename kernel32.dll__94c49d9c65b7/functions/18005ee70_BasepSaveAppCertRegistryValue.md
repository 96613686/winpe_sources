# BasepSaveAppCertRegistryValue

- ea: `0x18005ee70`
- end: `0x18005f007`
- name: `BasepSaveAppCertRegistryValue`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e740`

## callees

- `0x18005ee70`
- `0x18007a7d1`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18005ee91`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005ee91`
- `ntdll!RtlCompareUnicodeString` at `0x18005eeaf`
- `ntdll!RtlCompareUnicodeString` at `0x18005eeaf`
- `ntdll!RtlFreeHeap` at `0x18005ef99`
- `ntdll!RtlFreeHeap` at `0x18005efec`
- `ntdll!RtlFreeHeap` at `0x18005ef99`
- `ntdll!RtlFreeHeap` at `0x18005efec`
- `ntdll!RtlAllocateHeap` at `0x18005eeef`
- `ntdll!RtlAllocateHeap` at `0x18005eeef`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005eed0`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x18005eed0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005efae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005efae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005eff5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005eff5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005ef58`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18005ef58`

## string_xrefs

- `0x18005efa4`: `CreateProcessNotify`

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
0x18005ee70  mov     rax, rsp
0x18005ee73  mov     [rax+8], rbx
0x18005ee77  mov     [rax+10h], rsi
0x18005ee7b  push    rdi
0x18005ee7c  sub     rsp, 30h
0x18005ee80  mov     rdi, rcx
0x18005ee83  xorps   xmm0, xmm0
0x18005ee86  lea     rcx, [rax-18h]; DestinationString
0x18005ee8a  mov     rsi, r8
0x18005ee8d  movups  xmmword ptr [rax-18h], xmm0
0x18005ee91  call    cs:__imp_RtlInitUnicodeStringEx
0x18005ee97  test    eax, eax
0x18005ee99  js      short loc_18005EEC0
0x18005ee9b  mov     rbx, [rdi]
0x18005ee9e  cmp     rbx, rdi
0x18005eea1  jz      short loc_18005EED0
0x18005eea3  lea     rcx, [rbx+10h]; String1
0x18005eea7  mov     r8b, 1; CaseInsensitive
0x18005eeaa  lea     rdx, [rsp+38h+String2]; String2
0x18005eeaf  call    cs:__imp_RtlCompareUnicodeString
0x18005eeb5  test    eax, eax
0x18005eeb7  jz      short loc_18005EEBE
0x18005eeb9  mov     rbx, [rbx]
0x18005eebc  jmp     short loc_18005EE9E
0x18005eebe  xor     eax, eax
0x18005eec0  mov     rbx, [rsp+38h+arg_0]
0x18005eec5  mov     rsi, [rsp+38h+arg_8]
0x18005eeca  add     rsp, 30h
0x18005eece  pop     rdi
0x18005eecf  retn
0x18005eed0  call    cs:__imp_KernelBaseGetGlobalData
0x18005eed6  mov     rcx, gs:60h
0x18005eedf  movzx   r8d, [rsp+38h+String2.MaximumLength]
0x18005eee5  add     r8, 28h ; '('; Size
0x18005eee9  mov     edx, [rax]; Flags
0x18005eeeb  mov     rcx, [rcx+30h]; HeapHandle
0x18005eeef  call    cs:__imp_RtlAllocateHeap
0x18005eef5  mov     rbx, rax
0x18005eef8  test    rax, rax
0x18005eefb  jnz     short loc_18005EF04
0x18005eefd  mov     eax, 0C0000017h
0x18005ef02  jmp     short loc_18005EEC0
0x18005ef04  mov     [rax+8], rbx
0x18005ef08  lea     rcx, [rax+28h]; void *
0x18005ef0c  mov     [rax], rbx
0x18005ef0f  mov     [rax+18h], rcx
0x18005ef13  movzx   eax, [rsp+38h+String2.Length]
0x18005ef18  mov     [rbx+10h], ax
0x18005ef1c  movzx   eax, [rsp+38h+String2.MaximumLength]
0x18005ef21  mov     [rbx+12h], ax
0x18005ef25  movzx   r8d, [rsp+38h+String2.MaximumLength]; Size
0x18005ef2b  mov     rdx, [rsp+38h+String2.Buffer]; Src
0x18005ef30  call    memcpy_0
0x18005ef35  mov     rax, [rdi+8]
0x18005ef39  cmp     [rax], rdi
0x18005ef3c  jnz     loc_18005F000
0x18005ef42  mov     [rbx], rdi
0x18005ef45  mov     [rbx+8], rax
0x18005ef49  mov     [rax], rbx
0x18005ef4c  mov     [rdi+8], rbx
0x18005ef50  test    rsi, rsi
0x18005ef53  jz      short loc_18005EF66
0x18005ef55  mov     rcx, rsi; lpLibFileName
0x18005ef58  call    cs:__imp_LoadLibraryW
0x18005ef5e  mov     rdi, rax
0x18005ef61  test    rax, rax
0x18005ef64  jnz     short loc_18005EFA4
0x18005ef66  mov     rax, [rbx]
0x18005ef69  cmp     [rax+8], rbx
0x18005ef6d  jnz     loc_18005F000
0x18005ef73  mov     rcx, [rbx+8]
0x18005ef77  cmp     [rcx], rbx
0x18005ef7a  jnz     loc_18005F000
0x18005ef80  mov     [rcx], rax
0x18005ef83  mov     r8, rbx; P
0x18005ef86  mov     [rax+8], rcx
0x18005ef8a  xor     edx, edx; Flags
0x18005ef8c  mov     rcx, gs:60h
0x18005ef95  mov     rcx, [rcx+30h]; HeapHandle
0x18005ef99  call    cs:__imp_RtlFreeHeap
0x18005ef9f  jmp     loc_18005EEBE
0x18005efa4  lea     rdx, aCreateprocessn; "CreateProcessNotify"
0x18005efab  mov     rcx, rdi; hModule
0x18005efae  call    cs:__imp_GetProcAddress
0x18005efb4  mov     [rbx+20h], rax
0x18005efb8  test    rax, rax
0x18005efbb  jnz     loc_18005EEBE
0x18005efc1  mov     rax, [rbx]
0x18005efc4  cmp     [rax+8], rbx
0x18005efc8  jnz     short loc_18005F000
0x18005efca  mov     rcx, [rbx+8]
0x18005efce  cmp     [rcx], rbx
0x18005efd1  jnz     short loc_18005F000
0x18005efd3  mov     [rcx], rax
0x18005efd6  mov     r8, rbx; P
0x18005efd9  mov     [rax+8], rcx
0x18005efdd  xor     edx, edx; Flags
0x18005efdf  mov     rcx, gs:60h
0x18005efe8  mov     rcx, [rcx+30h]; HeapHandle
0x18005efec  call    cs:__imp_RtlFreeHeap
0x18005eff2  mov     rcx, rdi; hLibModule
0x18005eff5  call    cs:__imp_FreeLibrary
0x18005effb  jmp     loc_18005EEBE
0x18005f000  mov     ecx, 3
0x18005f005  int     29h; Win8: RtlFailFast(ecx)
```
