# SpGetExtendedInformation(_SECPKG_EXTENDED_INFORMATION_CLASS,_SECPKG_EXTENDED_INFORMATION * *)

- ea: `0x1800184d0`
- end: `0x180018559`
- name: `?SpGetExtendedInformation@@YAJW4_SECPKG_EXTENDED_INFORMATION_CLASS@@PEAPEAU_SECPKG_EXTENDED_INFORMATION@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(enum _SECPKG_EXTENDED_INFORMATION_CLASS, struct _SECPKG_EXTENDED_INFORMATION **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800184d0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001852f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001852f`

## string_xrefs

- `0x180018526`: `%SystemRoot%\SysWOW64\negoexts.DLL`

## pseudocode

```c
__int64 __fastcall SpGetExtendedInformation(
        enum _SECPKG_EXTENDED_INFORMATION_CLASS a1,
        struct _SECPKG_EXTENDED_INFORMATION **a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  struct _SECPKG_EXTENDED_INFORMATION *v5; // rdi
  unsigned __int16 v6; // ax

  if ( a1 == SecpkgWowClientDll )
  {
    v4 = ((__int64 (__fastcall *)(__int64))basessp::WSTGlobalLsaFunctions->AllocateLsaHeap)(576);
    v5 = (struct _SECPKG_EXTENDED_INFORMATION *)v4;
    if ( v4 )
    {
      *(_DWORD *)v4 = 4;
      *(_QWORD *)(v4 + 16) = v4 + 56;
      v3 = 0;
      v6 = 2 * ExpandEnvironmentStringsW(L"%SystemRoot%\\SysWOW64\\negoexts.DLL", (LPWSTR)(v4 + 56), 0x104u);
      v5->Info.WowClientDll.WowClientDllPath.Length = v6;
      v5->Info.WowClientDll.WowClientDllPath.MaximumLength = v6 + 2;
      *a2 = v5;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  else
  {
    return (unsigned int)-1073741821;
  }
  return v3;
}

```

## disassembly

```asm
0x1800184d0  mov     [rsp+arg_0], rbx
0x1800184d5  mov     [rsp+arg_8], rsi
0x1800184da  push    rdi
0x1800184db  sub     rsp, 20h
0x1800184df  mov     rsi, rdx
0x1800184e2  cmp     ecx, 4
0x1800184e5  jz      short loc_1800184EE
0x1800184e7  mov     ebx, 0C0000003h
0x1800184ec  jmp     short loc_180018547
0x1800184ee  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x1800184f5  mov     ecx, 240h
0x1800184fa  mov     rax, [rax+28h]
0x1800184fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018503  mov     rdi, rax
0x180018506  test    rax, rax
0x180018509  jnz     short loc_180018512
0x18001850b  mov     ebx, 0C0000017h
0x180018510  jmp     short loc_180018547
0x180018512  lea     rdx, [rax+38h]; lpDst
0x180018516  mov     dword ptr [rax], 4
0x18001851c  mov     r8d, 104h; nSize
0x180018522  mov     [rax+10h], rdx
0x180018526  lea     rcx, Src; "%SystemRoot%\\SysWOW64\\negoexts.DLL"
0x18001852d  xor     ebx, ebx
0x18001852f  call    cs:__imp_ExpandEnvironmentStringsW
0x180018535  add     ax, ax
0x180018538  mov     [rdi+8], ax
0x18001853c  add     ax, 2
0x180018540  mov     [rdi+0Ah], ax
0x180018544  mov     [rsi], rdi
0x180018547  mov     rsi, [rsp+28h+arg_8]
0x18001854c  mov     eax, ebx
0x18001854e  mov     rbx, [rsp+28h+arg_0]
0x180018553  add     rsp, 20h
0x180018557  pop     rdi
0x180018558  retn
```
