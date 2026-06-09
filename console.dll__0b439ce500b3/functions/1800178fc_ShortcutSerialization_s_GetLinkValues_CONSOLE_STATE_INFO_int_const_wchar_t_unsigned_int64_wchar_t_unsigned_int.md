# ShortcutSerialization::s_GetLinkValues(_CONSOLE_STATE_INFO *,int * const,wchar_t *,unsigned __int64,wchar_t *,unsigned __int64,wchar_t *,unsigned __int64,int * const,int * const,ushort * const)

- ea: `0x1800178fc`
- end: `0x1800179c7`
- name: `?s_GetLinkValues@ShortcutSerialization@@SAJPEAU_CONSOLE_STATE_INFO@@QEAHPEA_W_K232311QEAG@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _CONSOLE_STATE_INFO *, int *const, wchar_t *, unsigned __int64, wchar_t *, unsigned __int64, wchar_t *, unsigned __int64, int *const, int *const, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013ce0`

## callees

- `0x180008714`
- `0x1800178fc`
- `0x1800179d0`
- `0x180017c78`
- `0x180017e50`
- `0x18001a010`

## string_xrefs

- `0x180017975`: `onecore\windows\core\console\open\src\propslib\shortcutserialization.cpp`

## pseudocode

```c
__int64 __fastcall ShortcutSerialization::s_GetLinkValues(struct _CONSOLE_STATE_INFO *a1, int *const a2, wchar_t *a3)
{
  struct _CONSOLE_STATE_INFO *v3; // rdi
  int LoadedShellLinkForShortcut; // ebx
  struct IShellLinkW *v6; // rcx
  int v7; // eax
  struct IShellLinkW *v9; // [rsp+20h] [rbp-18h] BYREF
  struct IPersistFile *v10; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = gpStateInfo;
  *a2 = 0;
  v9 = 0;
  v10 = 0;
  LoadedShellLinkForShortcut = ShortcutSerialization::s_GetLoadedShellLinkForShortcut(
                                 *((const wchar_t **)v3 + 25),
                                 0,
                                 &v9,
                                 &v10);
  if ( LoadedShellLinkForShortcut >= 0 )
  {
    if ( (int)ShortcutSerialization::s_PopulateV1Properties(v9, v3) >= 0 )
    {
      v6 = v9;
      *a2 = 1;
      v7 = ShortcutSerialization::s_PopulateV2Properties(v6, v3);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x19E,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propslib\\shortcutserialization.cpp",
          (const char *)(unsigned int)v7,
          (int)v9);
    }
    ((void (__fastcall *)(struct IPersistFile *))v10->lpVtbl->Release)(v10);
    ((void (__fastcall *)(struct IShellLinkW *))v9->lpVtbl->Release)(v9);
  }
  return (LoadedShellLinkForShortcut >> 31) & 0xC0000001;
}

```

## disassembly

```asm
0x1800178fc  mov     rax, rsp
0x1800178ff  mov     [rax+8], rbx
0x180017903  mov     [rax+18h], rsi
0x180017907  push    rdi
0x180017908  sub     rsp, 30h
0x18001790c  mov     rdi, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180017913  lea     r9, [rax-10h]; struct IPersistFile **
0x180017917  mov     dword ptr [rdx], 0
0x18001791d  lea     r8, [rax-18h]; struct IShellLinkW **
0x180017921  mov     rsi, rdx
0x180017924  mov     qword ptr [rax-18h], 0
0x18001792c  xor     edx, edx; unsigned int
0x18001792e  mov     qword ptr [rax-10h], 0
0x180017936  mov     rcx, [rdi+0C8h]; wchar_t *
0x18001793d  call    ?s_GetLoadedShellLinkForShortcut@ShortcutSerialization@@CAJPEB_WKPEAPEAUIShellLinkW@@PEAPEAUIPersistFile@@@Z; ShortcutSerialization::s_GetLoadedShellLinkForShortcut(wchar_t const *,ulong,IShellLinkW * *,IPersistFile * *)
0x180017942  mov     ebx, eax
0x180017944  test    eax, eax
0x180017946  js      short loc_1800179AB
0x180017948  mov     rcx, [rsp+38h+var_18]; struct IShellLinkW *
0x18001794d  mov     rdx, rdi; struct _CONSOLE_STATE_INFO *
0x180017950  call    ?s_PopulateV1Properties@ShortcutSerialization@@CAJQEAUIShellLinkW@@PEAU_CONSOLE_STATE_INFO@@@Z; ShortcutSerialization::s_PopulateV1Properties(IShellLinkW * const,_CONSOLE_STATE_INFO *)
0x180017955  test    eax, eax
0x180017957  js      short loc_180017989
0x180017959  mov     rcx, [rsp+38h+var_18]; struct IShellLinkW *
0x18001795e  mov     rdx, rdi; struct _CONSOLE_STATE_INFO *
0x180017961  mov     dword ptr [rsi], 1
0x180017967  call    ?s_PopulateV2Properties@ShortcutSerialization@@CAJQEAUIShellLinkW@@PEAU_CONSOLE_STATE_INFO@@@Z; ShortcutSerialization::s_PopulateV2Properties(IShellLinkW * const,_CONSOLE_STATE_INFO *)
0x18001796c  test    eax, eax
0x18001796e  jns     short loc_180017989
0x180017970  mov     rcx, [rsp+38h]; this
0x180017975  lea     r8, aOnecoreWindows_3; "onecore\\windows\\core\\console\\open\\"...
0x18001797c  mov     r9d, eax; char *
0x18001797f  mov     edx, 19Eh; void *
0x180017984  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017989  mov     rcx, [rsp+38h+var_10]
0x18001798e  mov     rax, [rcx]
0x180017991  mov     rax, [rax+10h]
0x180017995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001799a  mov     rcx, [rsp+38h+var_18]
0x18001799f  mov     rax, [rcx]
0x1800179a2  mov     rax, [rax+10h]
0x1800179a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ab  mov     rsi, [rsp+38h+arg_10]
0x1800179b0  sar     ebx, 1Fh
0x1800179b3  and     ebx, 0C0000001h
0x1800179b9  mov     eax, ebx
0x1800179bb  mov     rbx, [rsp+38h+arg_0]
0x1800179c0  add     rsp, 30h
0x1800179c4  pop     rdi
0x1800179c5  retn
```
