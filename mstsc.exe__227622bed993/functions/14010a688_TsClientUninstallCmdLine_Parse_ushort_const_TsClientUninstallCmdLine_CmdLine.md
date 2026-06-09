# TsClientUninstallCmdLine::Parse(ushort const *,TsClientUninstallCmdLine::CmdLine &)

- ea: `0x14010a688`
- end: `0x14010a74a`
- name: `?Parse@TsClientUninstallCmdLine@@YAJPEBGAEAUCmdLine@1@@Z`
- size: `194`
- prototype: `__int64 __fastcall(TsClientUninstallCmdLine *__hidden this, const unsigned __int16 *, struct TsClientUninstallCmdLine::CmdLine *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006379c`

## callees

- `0x1400605c0`
- `0x14010a688`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14010a6ec`
- `KERNEL32!CompareStringOrdinal` at `0x14010a720`
- `KERNEL32!CompareStringOrdinal` at `0x14010a6ec`
- `KERNEL32!CompareStringOrdinal` at `0x14010a720`
- `SHELL32!CommandLineToArgvW` at `0x14010a6bc`
- `SHELL32!CommandLineToArgvW` at `0x14010a6bc`

## string_xrefs

- `0x14010a6da`: `/uninstall`

## pseudocode

```c
__int64 __fastcall TsClientUninstallCmdLine::Parse(
        const WCHAR *this,
        unsigned __int16 *a2,
        struct TsClientUninstallCmdLine::CmdLine *a3)
{
  char v4; // bl
  LPWSTR *v5; // rax
  LPWSTR *v6; // rsi
  int pNumArgs; // [rsp+50h] [rbp+8h] BYREF
  LPWSTR *v9; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 256;
  v4 = 1;
  if ( this && *this )
  {
    pNumArgs = 0;
    v5 = CommandLineToArgvW(this, &pNumArgs);
    v9 = v5;
    v6 = v5;
    if ( v5 && pNumArgs >= 2 && CompareStringOrdinal(v5[1], -1, L"/uninstall", -1, 1) == 2 )
    {
      *(_BYTE *)a2 = 1;
    }
    else
    {
      *(_BYTE *)a2 = 0;
      if ( !v6 )
      {
LABEL_11:
        *((_BYTE *)a2 + 1) = v4;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v9);
        return 0;
      }
    }
    if ( pNumArgs >= 3 && CompareStringOrdinal(v6[2], -1, L"/noPromptBeforeRestart", -1, 1) == 2 )
      v4 = 0;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x14010a688  mov     [rsp+arg_10], rbx
0x14010a68d  push    rbp
0x14010a68e  push    rsi
0x14010a68f  push    rdi
0x14010a690  sub     rsp, 30h
0x14010a694  xor     ebp, ebp
0x14010a696  mov     word ptr [rdx], 100h
0x14010a69b  mov     rdi, rdx
0x14010a69e  lea     ebx, [rbp+1]
0x14010a6a1  test    rcx, rcx
0x14010a6a4  jz      loc_14010A73B
0x14010a6aa  cmp     [rcx], bp
0x14010a6ad  jz      loc_14010A73B
0x14010a6b3  lea     rdx, [rsp+48h+pNumArgs]; pNumArgs
0x14010a6b8  mov     [rsp+48h+pNumArgs], ebp
0x14010a6bc  call    cs:__imp_CommandLineToArgvW
0x14010a6c2  mov     [rsp+48h+arg_8], rax
0x14010a6c7  mov     rsi, rax
0x14010a6ca  test    rax, rax
0x14010a6cd  jz      short loc_14010A6FB
0x14010a6cf  cmp     [rsp+48h+pNumArgs], 2
0x14010a6d4  jl      short loc_14010A6FB
0x14010a6d6  mov     rcx, [rax+8]; lpString1
0x14010a6da  lea     r8, aUninstall; "/uninstall"
0x14010a6e1  or      r9d, 0FFFFFFFFh; cchCount2
0x14010a6e5  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x14010a6e9  or      edx, r9d; cchCount1
0x14010a6ec  call    cs:__imp_CompareStringOrdinal
0x14010a6f2  cmp     eax, 2
0x14010a6f5  jnz     short loc_14010A6FB
0x14010a6f7  mov     [rdi], bl
0x14010a6f9  jmp     short loc_14010A703
0x14010a6fb  mov     [rdi], bpl
0x14010a6fe  test    rsi, rsi
0x14010a701  jz      short loc_14010A72E
0x14010a703  cmp     [rsp+48h+pNumArgs], 3
0x14010a708  jl      short loc_14010A72E
0x14010a70a  mov     rcx, [rsi+10h]; lpString1
0x14010a70e  lea     r8, aNopromptbefore; "/noPromptBeforeRestart"
0x14010a715  or      r9d, 0FFFFFFFFh; cchCount2
0x14010a719  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x14010a71d  or      edx, r9d; cchCount1
0x14010a720  call    cs:__imp_CompareStringOrdinal
0x14010a726  cmp     eax, 2
0x14010a729  jnz     short loc_14010A72E
0x14010a72b  mov     bl, bpl
0x14010a72e  lea     rcx, [rsp+48h+arg_8]
0x14010a733  mov     [rdi+1], bl
0x14010a736  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010a73b  mov     rbx, [rsp+48h+arg_10]
0x14010a740  xor     eax, eax
0x14010a742  add     rsp, 30h
0x14010a746  pop     rdi
0x14010a747  pop     rsi
0x14010a748  pop     rbp
0x14010a749  retn
```
