# FindPropertyWMISettingDescriptor(ushort const *,USERSTATE_SETTING_DESCRIPTOR const * *)

- ea: `0x18001d78c`
- end: `0x18001d84e`
- name: `?FindPropertyWMISettingDescriptor@@YAJPEBGPEAPEBUUSERSTATE_SETTING_DESCRIPTOR@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(LPCWSTR lpString2, const struct USERSTATE_SETTING_DESCRIPTOR **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18001da18`
- `0x18001e904`
- `0x18001e964`
- `0x18001e9b8`
- `0x18001f1c4`
- `0x18001f22c`

## callees

- `0x180014068`
- `0x18001d78c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001d7ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001d7ba`

## pseudocode

```c
__int64 __fastcall FindPropertyWMISettingDescriptor(LPCWSTR lpString2, const struct USERSTATE_SETTING_DESCRIPTOR **a2)
{
  int i; // ebx
  __int64 v5; // rsi
  const WCHAR *v6; // rcx

  for ( i = 0; ; ++i )
  {
    v5 = 26LL * i;
    v6 = *(const WCHAR **)((char *)&WMIPropertySettingMap + v5 * 4 + 16);
    if ( !v6 )
      break;
    if ( !lstrcmpiW(v6, lpString2) )
    {
      *a2 = (const struct USERSTATE_SETTING_DESCRIPTOR *)&dword_1800464B8[v5];
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
      {
        WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 72, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, lpString2);
      }
      return 0;
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 73, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, lpString2);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18001d78c  push    rbx
0x18001d78e  push    rbp
0x18001d78f  push    rsi
0x18001d790  push    rdi
0x18001d791  push    r14
0x18001d793  sub     rsp, 20h
0x18001d797  mov     r14, rdx
0x18001d79a  lea     rbp, ?WMIPropertySettingMap@@3PAUWMIPropertySettingsItem@@A; WMIPropertySettingsItem near * WMIPropertySettingMap
0x18001d7a1  mov     rdi, rcx
0x18001d7a4  xor     ebx, ebx
0x18001d7a6  movsxd  rax, ebx
0x18001d7a9  imul    rsi, rax, 68h ; 'h'
0x18001d7ad  mov     rcx, [rsi+rbp+10h]; lpString1
0x18001d7b2  test    rcx, rcx
0x18001d7b5  jz      short loc_18001D80A
0x18001d7b7  mov     rdx, rdi; lpString2
0x18001d7ba  call    cs:__imp_lstrcmpiW
0x18001d7c0  test    eax, eax
0x18001d7c2  jz      short loc_18001D7C8
0x18001d7c4  inc     ebx
0x18001d7c6  jmp     short loc_18001D7A6
0x18001d7c8  lea     rax, [rbp+18h]
0x18001d7cc  add     rax, rsi
0x18001d7cf  mov     [r14], rax
0x18001d7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7d9  lea     rax, WPP_GLOBAL_Control
0x18001d7e0  cmp     rcx, rax
0x18001d7e3  jz      short loc_18001D806
0x18001d7e5  test    dword ptr [rcx+1Ch], 4000000h
0x18001d7ec  jz      short loc_18001D806
0x18001d7ee  mov     rcx, [rcx+10h]
0x18001d7f2  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d7f9  mov     edx, 48h ; 'H'
0x18001d7fe  mov     r9, rdi
0x18001d801  call    WPP_SF_S
0x18001d806  xor     eax, eax
0x18001d808  jmp     short loc_18001D843
0x18001d80a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d811  lea     rax, WPP_GLOBAL_Control
0x18001d818  cmp     rcx, rax
0x18001d81b  jz      short loc_18001D83E
0x18001d81d  test    dword ptr [rcx+1Ch], 4000000h
0x18001d824  jz      short loc_18001D83E
0x18001d826  mov     rcx, [rcx+10h]
0x18001d82a  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d831  mov     edx, 49h ; 'I'
0x18001d836  mov     r9, rdi
0x18001d839  call    WPP_SF_S
0x18001d83e  mov     eax, 80004005h
0x18001d843  add     rsp, 20h
0x18001d847  pop     r14
0x18001d849  pop     rdi
0x18001d84a  pop     rsi
0x18001d84b  pop     rbp
0x18001d84c  pop     rbx
0x18001d84d  retn
```
