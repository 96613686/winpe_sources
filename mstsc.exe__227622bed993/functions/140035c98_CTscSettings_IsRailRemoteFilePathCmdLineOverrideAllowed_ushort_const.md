# CTscSettings::IsRailRemoteFilePathCmdLineOverrideAllowed(ushort const *)

- ea: `0x140035c98`
- end: `0x140035e2b`
- name: `?IsRailRemoteFilePathCmdLineOverrideAllowed@CTscSettings@@QEAAHPEBG@Z`
- size: `403`
- prototype: `int(CTscSettings *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14002db88`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cffc`
- `0x14000d078`
- `0x140035c98`
- `0x1400b1d80`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140035dfa`
- `msvcrt!_wcsicmp` at `0x140035dfa`
- `msvcrt!wcstok_s` at `0x140035ddc`
- `msvcrt!wcstok_s` at `0x140035ddc`
- `SHLWAPI!PathFindExtensionW` at `0x140035ce3`
- `SHLWAPI!PathFindExtensionW` at `0x140035ce3`
- `KERNEL32!LocalFree` at `0x140035e10`
- `KERNEL32!LocalFree` at `0x140035e10`

## string_xrefs

- `0x140035d2e`: `pszRdpExtensionList`
- `0x140035d9c`: `Copy Extension list to local array failed!`

## pseudocode

```c
__int64 __fastcall CTscSettings::IsRailRemoteFilePathCmdLineOverrideAllowed(
        CTscSettings *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rsi
  int v3; // r8d
  int v4; // r8d
  unsigned int v5; // ebx
  const wchar_t *ExtensionW; // rbp
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rdi
  unsigned int v9; // eax
  int v10; // eax
  char v11; // si
  unsigned int CurrentThreadActivityIdPrefix; // eax
  wchar_t *i; // rcx
  wchar_t *v14; // rax
  wchar_t *Context; // [rsp+50h] [rbp+8h] BYREF

  v2 = (const unsigned __int16 *)((char *)this + 7960);
  v3 = *((unsigned __int16 *)this + 3980);
  Context = 0;
  v4 = v3 - 42;
  if ( !v4 )
    v4 = *((unsigned __int16 *)this + 3981);
  if ( v4 )
  {
    v5 = 0;
    ExtensionW = PathFindExtensionW(a2);
    v7 = (unsigned __int16 *)MIDL_user_allocate(0x1000u);
    v8 = v7;
    if ( v7 )
    {
      v10 = StringCchCopyW(v7, 0x800u, v2);
      v11 = v10;
      if ( v10 >= 0 )
      {
        for ( i = v8; ; i = 0 )
        {
          v14 = wcstok_s(i, L",", &Context);
          if ( !v14 )
            break;
          if ( *v14 == 46 && v14[1] && !_wcsicmp(v14, ExtensionW) )
          {
            v5 = 1;
            break;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          142,
          (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"Copy Extension list to local array failed!",
          v11);
      }
      LocalFree(v8);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        141,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        v9,
        (__int64)"pszRdpExtensionList");
    }
  }
  else
  {
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x140035c98  mov     [rsp+arg_8], rbx
0x140035c9d  mov     [rsp+arg_10], rbp
0x140035ca2  push    rsi
0x140035ca3  push    rdi
0x140035ca4  push    r14
0x140035ca6  sub     rsp, 30h
0x140035caa  xor     r14d, r14d
0x140035cad  lea     rsi, [rcx+1F18h]
0x140035cb4  movzx   r8d, word ptr [rsi]
0x140035cb8  mov     [rsp+48h+Context], r14
0x140035cbd  sub     r8d, 2Ah ; '*'
0x140035cc1  jnz     short loc_140035CCF
0x140035cc3  movzx   r8d, word ptr [rsi+2]
0x140035cc8  movzx   ecx, r14w
0x140035ccc  sub     r8d, ecx
0x140035ccf  test    r8d, r8d
0x140035cd2  jnz     short loc_140035CDD
0x140035cd4  lea     ebx, [r8+1]
0x140035cd8  jmp     loc_140035E16
0x140035cdd  mov     rcx, rdx; pszPath
0x140035ce0  mov     ebx, r14d
0x140035ce3  call    cs:__imp_PathFindExtensionW
0x140035ce9  mov     ecx, 1000h; size
0x140035cee  mov     rbp, rax
0x140035cf1  call    MIDL_user_allocate
0x140035cf6  mov     rdi, rax
0x140035cf9  test    rax, rax
0x140035cfc  jnz     short loc_140035D5E
0x140035cfe  mov     rax, cs:WPP_GLOBAL_Control
0x140035d05  lea     rcx, WPP_GLOBAL_Control
0x140035d0c  cmp     rax, rcx
0x140035d0f  jz      loc_140035E16
0x140035d15  test    byte ptr [rax+1Ch], 8
0x140035d19  jz      loc_140035E16
0x140035d1f  cmp     byte ptr [rax+19h], 2
0x140035d23  jb      loc_140035E16
0x140035d29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035d2e  lea     rcx, aPszrdpextensio; "pszRdpExtensionList"
0x140035d35  mov     edx, 8Dh
0x140035d3a  mov     [rsp+48h+var_28], rcx
0x140035d3f  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140035d46  mov     rcx, cs:WPP_GLOBAL_Control
0x140035d4d  mov     r9d, eax
0x140035d50  mov     rcx, [rcx+10h]
0x140035d54  call    WPP_SF_Ds
0x140035d59  jmp     loc_140035E16
0x140035d5e  mov     r8, rsi; unsigned __int16 *
0x140035d61  mov     edx, 800h; unsigned __int64
0x140035d66  mov     rcx, rdi; unsigned __int16 *
0x140035d69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140035d6e  mov     esi, eax
0x140035d70  test    eax, eax
0x140035d72  jns     short loc_140035DCD
0x140035d74  mov     rax, cs:WPP_GLOBAL_Control
0x140035d7b  lea     rcx, WPP_GLOBAL_Control
0x140035d82  cmp     rax, rcx
0x140035d85  jz      loc_140035E0D
0x140035d8b  test    byte ptr [rax+1Ch], 8
0x140035d8f  jz      short loc_140035E0D
0x140035d91  cmp     byte ptr [rax+19h], 2
0x140035d95  jb      short loc_140035E0D
0x140035d97  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035d9c  lea     rcx, aCopyExtensionL; "Copy Extension list to local array fail"...
0x140035da3  mov     [rsp+48h+var_20], esi
0x140035da7  mov     [rsp+48h+var_28], rcx
0x140035dac  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140035db3  mov     rcx, cs:WPP_GLOBAL_Control
0x140035dba  mov     edx, 8Eh
0x140035dbf  mov     r9d, eax
0x140035dc2  mov     rcx, [rcx+10h]
0x140035dc6  call    WPP_SF_DsD
0x140035dcb  jmp     short loc_140035E0D
0x140035dcd  mov     rcx, rdi; String
0x140035dd0  lea     r8, [rsp+48h+Context]; Context
0x140035dd5  lea     rdx, Delimiter; ","
0x140035ddc  call    cs:__imp_wcstok_s
0x140035de2  test    rax, rax
0x140035de5  jz      short loc_140035E0D
0x140035de7  cmp     word ptr [rax], 2Eh ; '.'
0x140035deb  jnz     short loc_140035E04
0x140035ded  cmp     [rax+2], r14w
0x140035df2  jz      short loc_140035E04
0x140035df4  mov     rdx, rbp; String2
0x140035df7  mov     rcx, rax; String1
0x140035dfa  call    cs:__imp__wcsicmp
0x140035e00  test    eax, eax
0x140035e02  jz      short loc_140035E08
0x140035e04  xor     ecx, ecx
0x140035e06  jmp     short loc_140035DD0
0x140035e08  mov     ebx, 1
0x140035e0d  mov     rcx, rdi; hMem
0x140035e10  call    cs:__imp_LocalFree
0x140035e16  mov     rbp, [rsp+48h+arg_10]
0x140035e1b  mov     eax, ebx
0x140035e1d  mov     rbx, [rsp+48h+arg_8]
0x140035e22  add     rsp, 30h
0x140035e26  pop     r14
0x140035e28  pop     rdi
0x140035e29  pop     rsi
0x140035e2a  retn
```
