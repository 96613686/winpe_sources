# SpGetExtendedInformation(_SECPKG_EXTENDED_INFORMATION_CLASS,_SECPKG_EXTENDED_INFORMATION * *)

- ea: `0x180023810`
- end: `0x1800238ea`
- name: `?SpGetExtendedInformation@@YAJW4_SECPKG_EXTENDED_INFORMATION_CLASS@@PEAPEAU_SECPKG_EXTENDED_INFORMATION@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(enum _SECPKG_EXTENDED_INFORMATION_CLASS, struct _SECPKG_EXTENDED_INFORMATION **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180023810`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800238bb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800238bb`

## string_xrefs

- `0x1800238b4`: `%SystemRoot%\SysWOW64\pku2u.DLL`

## pseudocode

```c
__int64 __fastcall SpGetExtendedInformation(
        enum _SECPKG_EXTENDED_INFORMATION_CLASS a1,
        struct _SECPKG_EXTENDED_INFORMATION **a2)
{
  unsigned int v2; // ebx
  __int64 v4; // rax
  __int64 v5; // rax
  struct _SECPKG_EXTENDED_INFORMATION *v6; // rdi
  unsigned __int16 v7; // ax

  v2 = 0;
  if ( a1 == SecpkgWowClientDll )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 40LL))(576);
    v6 = (struct _SECPKG_EXTENDED_INFORMATION *)v5;
    if ( v5 )
    {
      *(_DWORD *)v5 = 4;
      *(_QWORD *)(v5 + 16) = v5 + 56;
      v7 = 2 * ExpandEnvironmentStringsW(L"%SystemRoot%\\SysWOW64\\pku2u.DLL", (LPWSTR)(v5 + 56), 0x104u);
      v6->Info.WowClientDll.WowClientDllPath.Length = v7;
      v6->Info.WowClientDll.WowClientDllPath.MaximumLength = v7 + 2;
      *a2 = v6;
      return v2;
    }
    return (unsigned int)-1073741801;
  }
  if ( a1 == SecpkgNego2Info )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 40LL))(56);
    if ( v4 )
    {
      *(_DWORD *)v4 = 7;
      *(_OWORD *)(v4 + 8) = xmmword_18004A7C8;
      *a2 = (struct _SECPKG_EXTENDED_INFORMATION *)v4;
      return v2;
    }
    return (unsigned int)-1073741801;
  }
  return (unsigned int)-1073741821;
}

```

## disassembly

```asm
0x180023810  mov     [rsp+arg_0], rbx
0x180023815  mov     [rsp+arg_8], rsi
0x18002381a  push    rdi
0x18002381b  sub     rsp, 30h
0x18002381f  xor     ebx, ebx
0x180023821  movaps  [rsp+38h+var_18], xmm6
0x180023826  mov     rsi, rdx
0x180023829  cmp     ecx, 4
0x18002382c  jz      short loc_18002387C
0x18002382e  cmp     ecx, 7
0x180023831  jz      short loc_18002383D
0x180023833  mov     ebx, 0C0000003h
0x180023838  jmp     loc_1800238D3
0x18002383d  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180023844  movups  xmm6, cs:xmmword_18004A7C8
0x18002384b  mov     rcx, [rax+0F0h]
0x180023852  mov     rax, [rcx+28h]
0x180023856  mov     ecx, 38h ; '8'
0x18002385b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023860  test    rax, rax
0x180023863  jnz     short loc_18002386C
0x180023865  mov     ebx, 0C0000017h
0x18002386a  jmp     short loc_1800238D3
0x18002386c  mov     dword ptr [rax], 7
0x180023872  movdqu  xmmword ptr [rax+8], xmm6
0x180023877  mov     [rsi], rax
0x18002387a  jmp     short loc_1800238D3
0x18002387c  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180023883  mov     rcx, [rax+0F0h]
0x18002388a  mov     rax, [rcx+28h]
0x18002388e  mov     ecx, 240h
0x180023893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023898  mov     rdi, rax
0x18002389b  test    rax, rax
0x18002389e  jz      short loc_180023865
0x1800238a0  lea     rdx, [rax+38h]; lpDst
0x1800238a4  mov     dword ptr [rax], 4
0x1800238aa  mov     r8d, 104h; nSize
0x1800238b0  mov     [rax+10h], rdx
0x1800238b4  lea     rcx, aSystemrootSysw; "%SystemRoot%\\SysWOW64\\pku2u.DLL"
0x1800238bb  call    cs:__imp_ExpandEnvironmentStringsW
0x1800238c1  add     ax, ax
0x1800238c4  mov     [rdi+8], ax
0x1800238c8  add     ax, 2
0x1800238cc  mov     [rdi+0Ah], ax
0x1800238d0  mov     [rsi], rdi
0x1800238d3  mov     rsi, [rsp+38h+arg_8]
0x1800238d8  mov     eax, ebx
0x1800238da  mov     rbx, [rsp+38h+arg_0]
0x1800238df  movaps  xmm6, [rsp+38h+var_18]
0x1800238e4  add     rsp, 30h
0x1800238e8  pop     rdi
0x1800238e9  retn
```
