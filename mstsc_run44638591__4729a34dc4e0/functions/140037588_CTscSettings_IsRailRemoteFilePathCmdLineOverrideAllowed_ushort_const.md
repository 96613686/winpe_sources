# CTscSettings::IsRailRemoteFilePathCmdLineOverrideAllowed(ushort const *)

- ea: `0x140037588`
- end: `0x14003771b`
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
- `0x140037588`
- `0x1400b3ef0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1400376ea`
- `msvcrt!_wcsicmp` at `0x1400376ea`
- `msvcrt!wcstok_s` at `0x1400376cc`
- `msvcrt!wcstok_s` at `0x1400376cc`
- `SHLWAPI!PathFindExtensionW` at `0x1400375d3`
- `SHLWAPI!PathFindExtensionW` at `0x1400375d3`
- `KERNEL32!LocalFree` at `0x140037700`
- `KERNEL32!LocalFree` at `0x140037700`

## string_xrefs

- `0x14003761e`: `pszRdpExtensionList`
- `0x14003768c`: `Copy Extension list to local array failed!`

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
          (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
        (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
0x140037588  mov     [rsp+arg_8], rbx
0x14003758d  mov     [rsp+arg_10], rbp
0x140037592  push    rsi
0x140037593  push    rdi
0x140037594  push    r14
0x140037596  sub     rsp, 30h
0x14003759a  xor     r14d, r14d
0x14003759d  lea     rsi, [rcx+1F18h]
0x1400375a4  movzx   r8d, word ptr [rsi]
0x1400375a8  mov     [rsp+48h+Context], r14
0x1400375ad  sub     r8d, 2Ah ; '*'
0x1400375b1  jnz     short loc_1400375BF
0x1400375b3  movzx   r8d, word ptr [rsi+2]
0x1400375b8  movzx   ecx, r14w
0x1400375bc  sub     r8d, ecx
0x1400375bf  test    r8d, r8d
0x1400375c2  jnz     short loc_1400375CD
0x1400375c4  lea     ebx, [r8+1]
0x1400375c8  jmp     loc_140037706
0x1400375cd  mov     rcx, rdx; pszPath
0x1400375d0  mov     ebx, r14d
0x1400375d3  call    cs:__imp_PathFindExtensionW
0x1400375d9  mov     ecx, 1000h; size
0x1400375de  mov     rbp, rax
0x1400375e1  call    MIDL_user_allocate
0x1400375e6  mov     rdi, rax
0x1400375e9  test    rax, rax
0x1400375ec  jnz     short loc_14003764E
0x1400375ee  mov     rax, cs:WPP_GLOBAL_Control
0x1400375f5  lea     rcx, WPP_GLOBAL_Control
0x1400375fc  cmp     rax, rcx
0x1400375ff  jz      loc_140037706
0x140037605  test    byte ptr [rax+1Ch], 8
0x140037609  jz      loc_140037706
0x14003760f  cmp     byte ptr [rax+19h], 2
0x140037613  jb      loc_140037706
0x140037619  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003761e  lea     rcx, aPszrdpextensio; "pszRdpExtensionList"
0x140037625  mov     edx, 8Dh
0x14003762a  mov     [rsp+48h+var_28], rcx
0x14003762f  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x140037636  mov     rcx, cs:WPP_GLOBAL_Control
0x14003763d  mov     r9d, eax
0x140037640  mov     rcx, [rcx+10h]
0x140037644  call    WPP_SF_Ds
0x140037649  jmp     loc_140037706
0x14003764e  mov     r8, rsi; unsigned __int16 *
0x140037651  mov     edx, 800h; unsigned __int64
0x140037656  mov     rcx, rdi; unsigned __int16 *
0x140037659  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003765e  mov     esi, eax
0x140037660  test    eax, eax
0x140037662  jns     short loc_1400376BD
0x140037664  mov     rax, cs:WPP_GLOBAL_Control
0x14003766b  lea     rcx, WPP_GLOBAL_Control
0x140037672  cmp     rax, rcx
0x140037675  jz      loc_1400376FD
0x14003767b  test    byte ptr [rax+1Ch], 8
0x14003767f  jz      short loc_1400376FD
0x140037681  cmp     byte ptr [rax+19h], 2
0x140037685  jb      short loc_1400376FD
0x140037687  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003768c  lea     rcx, aCopyExtensionL; "Copy Extension list to local array fail"...
0x140037693  mov     [rsp+48h+var_20], esi
0x140037697  mov     [rsp+48h+var_28], rcx
0x14003769c  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x1400376a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400376aa  mov     edx, 8Eh
0x1400376af  mov     r9d, eax
0x1400376b2  mov     rcx, [rcx+10h]
0x1400376b6  call    WPP_SF_DsD
0x1400376bb  jmp     short loc_1400376FD
0x1400376bd  mov     rcx, rdi; String
0x1400376c0  lea     r8, [rsp+48h+Context]; Context
0x1400376c5  lea     rdx, Delimiter; ","
0x1400376cc  call    cs:__imp_wcstok_s
0x1400376d2  test    rax, rax
0x1400376d5  jz      short loc_1400376FD
0x1400376d7  cmp     word ptr [rax], 2Eh ; '.'
0x1400376db  jnz     short loc_1400376F4
0x1400376dd  cmp     [rax+2], r14w
0x1400376e2  jz      short loc_1400376F4
0x1400376e4  mov     rdx, rbp; String2
0x1400376e7  mov     rcx, rax; String1
0x1400376ea  call    cs:__imp__wcsicmp
0x1400376f0  test    eax, eax
0x1400376f2  jz      short loc_1400376F8
0x1400376f4  xor     ecx, ecx
0x1400376f6  jmp     short loc_1400376C0
0x1400376f8  mov     ebx, 1
0x1400376fd  mov     rcx, rdi; hMem
0x140037700  call    cs:__imp_LocalFree
0x140037706  mov     rbp, [rsp+48h+arg_10]
0x14003770b  mov     eax, ebx
0x14003770d  mov     rbx, [rsp+48h+arg_8]
0x140037712  add     rsp, 30h
0x140037716  pop     r14
0x140037718  pop     rdi
0x140037719  pop     rsi
0x14003771a  retn
```
