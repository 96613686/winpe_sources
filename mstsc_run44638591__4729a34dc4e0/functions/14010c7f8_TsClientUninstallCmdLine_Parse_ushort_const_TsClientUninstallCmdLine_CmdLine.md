# TsClientUninstallCmdLine::Parse(ushort const *,TsClientUninstallCmdLine::CmdLine &)

- ea: `0x14010c7f8`
- end: `0x14010c8ba`
- name: `?Parse@TsClientUninstallCmdLine@@YAJPEBGAEAUCmdLine@1@@Z`
- size: `194`
- prototype: `__int64 __fastcall(TsClientUninstallCmdLine *__hidden this, const unsigned __int16 *, struct TsClientUninstallCmdLine::CmdLine *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006590c`

## callees

- `0x140062730`
- `0x14010c7f8`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x14010c85c`
- `KERNEL32!CompareStringOrdinal` at `0x14010c890`
- `KERNEL32!CompareStringOrdinal` at `0x14010c85c`
- `KERNEL32!CompareStringOrdinal` at `0x14010c890`
- `SHELL32!CommandLineToArgvW` at `0x14010c82c`
- `SHELL32!CommandLineToArgvW` at `0x14010c82c`

## string_xrefs

- `0x14010c84a`: `/uninstall`

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
0x14010c7f8  mov     [rsp+arg_10], rbx
0x14010c7fd  push    rbp
0x14010c7fe  push    rsi
0x14010c7ff  push    rdi
0x14010c800  sub     rsp, 30h
0x14010c804  xor     ebp, ebp
0x14010c806  mov     word ptr [rdx], 100h
0x14010c80b  mov     rdi, rdx
0x14010c80e  lea     ebx, [rbp+1]
0x14010c811  test    rcx, rcx
0x14010c814  jz      loc_14010C8AB
0x14010c81a  cmp     [rcx], bp
0x14010c81d  jz      loc_14010C8AB
0x14010c823  lea     rdx, [rsp+48h+pNumArgs]; pNumArgs
0x14010c828  mov     [rsp+48h+pNumArgs], ebp
0x14010c82c  call    cs:__imp_CommandLineToArgvW
0x14010c832  mov     [rsp+48h+arg_8], rax
0x14010c837  mov     rsi, rax
0x14010c83a  test    rax, rax
0x14010c83d  jz      short loc_14010C86B
0x14010c83f  cmp     [rsp+48h+pNumArgs], 2
0x14010c844  jl      short loc_14010C86B
0x14010c846  mov     rcx, [rax+8]; lpString1
0x14010c84a  lea     r8, aUninstall; "/uninstall"
0x14010c851  or      r9d, 0FFFFFFFFh; cchCount2
0x14010c855  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x14010c859  or      edx, r9d; cchCount1
0x14010c85c  call    cs:__imp_CompareStringOrdinal
0x14010c862  cmp     eax, 2
0x14010c865  jnz     short loc_14010C86B
0x14010c867  mov     [rdi], bl
0x14010c869  jmp     short loc_14010C873
0x14010c86b  mov     [rdi], bpl
0x14010c86e  test    rsi, rsi
0x14010c871  jz      short loc_14010C89E
0x14010c873  cmp     [rsp+48h+pNumArgs], 3
0x14010c878  jl      short loc_14010C89E
0x14010c87a  mov     rcx, [rsi+10h]; lpString1
0x14010c87e  lea     r8, aNopromptbefore; "/noPromptBeforeRestart"
0x14010c885  or      r9d, 0FFFFFFFFh; cchCount2
0x14010c889  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x14010c88d  or      edx, r9d; cchCount1
0x14010c890  call    cs:__imp_CompareStringOrdinal
0x14010c896  cmp     eax, 2
0x14010c899  jnz     short loc_14010C89E
0x14010c89b  mov     bl, bpl
0x14010c89e  lea     rcx, [rsp+48h+arg_8]
0x14010c8a3  mov     [rdi+1], bl
0x14010c8a6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14010c8ab  mov     rbx, [rsp+48h+arg_10]
0x14010c8b0  xor     eax, eax
0x14010c8b2  add     rsp, 30h
0x14010c8b6  pop     rdi
0x14010c8b7  pop     rsi
0x14010c8b8  pop     rbp
0x14010c8b9  retn
```
