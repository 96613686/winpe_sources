# container::FilesystemProvider::Cleanup(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_WC_FILESYSTEM_PROVIDER const &)

- ea: `0x1800243c4`
- end: `0x1800244a0`
- name: `?Cleanup@FilesystemProvider@container@@YAXPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBW4_WC_FILESYSTEM_PROVIDER@@@Z`
- size: `220`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x180005278`
- `0x18000d134`
- `0x18000d8f0`
- `0x18000da40`
- `0x180024320`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x180007c2c`
- `0x1800243c4`
- `0x1800244a8`
- `0x180024664`
- `0x18002526c`

## import_xrefs

- `wc_storage!WcDetachFilterEx` at `0x180024469`
- `wc_storage!WcDetachFilterEx` at `0x180024469`
- `UNIONFSAPI!RemoveFileSystemUnion` at `0x180024420`
- `UNIONFSAPI!RemoveFileSystemUnion` at `0x180024420`

## pseudocode

```c
void __fastcall container::FilesystemProvider::Cleanup(container_runtime *a1, _QWORD *a2, _DWORD *a3)
{
  _QWORD *v3; // rbx
  _QWORD *UnionConfigPath; // rax
  int v5; // eax
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // r8d
  int v9[4]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE Src[32]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = a2;
  if ( *a3 == 1 )
  {
    *(_OWORD *)v9 = 0;
    if ( (int)container::FilesystemProvider::Details::ExtractGuidFromMountPath(a2, v9) >= 0 )
    {
      UnionConfigPath = (_QWORD *)container::FilesystemProvider::Details::GetUnionConfigPath(Src);
      if ( UnionConfigPath[3] > 7u )
        UnionConfigPath = (_QWORD *)*UnionConfigPath;
      v5 = RemoveFileSystemUnion(v9, 0, UnionConfigPath);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x12E, v6, (const char *)(unsigned int)v5, v9[0]);
      std::wstring::~wstring(Src);
    }
  }
  else if ( a2[2] )
  {
    container_runtime::IsServerContainer(a1, a2);
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    v7 = WcDetachFilterEx(v3, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x143, v8, (const char *)(unsigned int)v7, v9[0]);
  }
}

```

## disassembly

```asm
0x1800243c4  push    rbx
0x1800243c6  sub     rsp, 60h
0x1800243ca  mov     rax, cs:__security_cookie
0x1800243d1  xor     rax, rsp
0x1800243d4  mov     [rsp+68h+var_18], rax
0x1800243d9  mov     rbx, rdx
0x1800243dc  cmp     dword ptr [r8], 1
0x1800243e0  jnz     short loc_18002444E
0x1800243e2  xorps   xmm0, xmm0
0x1800243e5  movups  xmmword ptr [rsp+68h+var_48], xmm0; int
0x1800243ea  lea     rdx, [rsp+68h+var_48]
0x1800243ef  mov     rcx, rbx
0x1800243f2  call    ?ExtractGuidFromMountPath@Details@FilesystemProvider@container@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; container::FilesystemProvider::Details::ExtractGuidFromMountPath(std::wstring const &,_GUID &)
0x1800243f7  test    eax, eax
0x1800243f9  js      loc_18002448C
0x1800243ff  mov     rdx, rbx
0x180024402  lea     rcx, [rsp+68h+Src]; Src
0x180024407  call    ?GetUnionConfigPath@Details@FilesystemProvider@container@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; container::FilesystemProvider::Details::GetUnionConfigPath(std::wstring const &)
0x18002440c  cmp     qword ptr [rax+18h], 7
0x180024411  jbe     short loc_180024416
0x180024413  mov     rax, [rax]
0x180024416  mov     r8, rax
0x180024419  xor     edx, edx
0x18002441b  lea     rcx, [rsp+68h+var_48]
0x180024420  call    cs:__imp_RemoveFileSystemUnion
0x180024427  nop     dword ptr [rax+rax+00h]
0x18002442c  test    eax, eax
0x18002442e  jns     short loc_180024442
0x180024430  mov     rcx, [rsp+68h]; this
0x180024435  mov     r9d, eax; char *
0x180024438  mov     edx, 12Eh; void *
0x18002443d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024442  lea     rcx, [rsp+68h+Src]
0x180024447  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002444c  jmp     short loc_18002448C
0x18002444e  cmp     qword ptr [rdx+10h], 0
0x180024453  jz      short loc_18002448C
0x180024455  call    ?IsServerContainer@container_runtime@@YA_NPEAX@Z; container_runtime::IsServerContainer(void *)
0x18002445a  cmp     qword ptr [rbx+18h], 7
0x18002445f  jbe     short loc_180024464
0x180024461  mov     rbx, [rbx]
0x180024464  xor     edx, edx
0x180024466  mov     rcx, rbx
0x180024469  call    cs:__imp_WcDetachFilterEx
0x180024470  nop     dword ptr [rax+rax+00h]
0x180024475  test    eax, eax
0x180024477  jns     short loc_18002448C
0x180024479  mov     rcx, [rsp+68h]; this
0x18002447e  mov     r9d, eax; char *
0x180024481  mov     edx, 143h; void *
0x180024486  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002448b  nop
0x18002448c  mov     rcx, [rsp+68h+var_18]
0x180024491  xor     rcx, rsp; StackCookie
0x180024494  call    __security_check_cookie
0x180024499  add     rsp, 60h
0x18002449d  pop     rbx
0x18002449e  retn
```
