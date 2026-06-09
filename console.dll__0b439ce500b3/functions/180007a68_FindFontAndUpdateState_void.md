# FindFontAndUpdateState(void)

- ea: `0x180007a68`
- end: `0x180007ae1`
- name: `?FindFontAndUpdateState@@YAJXZ`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180009980`
- `0x180013ce0`

## callees

- `0x180005e60`
- `0x180009578`

## pseudocode

```c
__int64 FindFontAndUpdateState(void)
{
  unsigned int Font; // eax
  struct _CONSOLE_STATE_INFO *v1; // rdx
  _DWORD *v2; // r9

  Font = FindCreateFont(
           *((_DWORD *)gpStateInfo + 5),
           (wchar_t *)gpStateInfo + 14,
           *(struct _COORD *)((char *)gpStateInfo + 16),
           *((_DWORD *)gpStateInfo + 6),
           *((_DWORD *)gpStateInfo + 52));
  v1 = gpStateInfo;
  v2 = FontInfo;
  g_currentFontIndex = Font;
  *((_DWORD *)gpStateInfo + 5) = *((unsigned __int8 *)FontInfo + 40 * Font + 32);
  *((_DWORD *)v1 + 4) = v2[10 * Font + 2];
  *((_DWORD *)v1 + 6) = v2[10 * Font + 4];
  return StringCchCopyW((wchar_t *)v1 + 14, 0x20u, *(wchar_t **)&v2[10 * Font + 6]);
}

```

## disassembly

```asm
0x180007a68  sub     rsp, 38h
0x180007a6c  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007a73  mov     eax, [rcx+0D0h]
0x180007a79  lea     rdx, [rcx+1Ch]; wchar_t *
0x180007a7d  mov     r9d, [rcx+18h]; int
0x180007a81  mov     r8d, [rcx+10h]; struct _COORD
0x180007a85  mov     ecx, [rcx+14h]; unsigned int
0x180007a88  mov     [rsp+38h+var_18], eax; unsigned int
0x180007a8c  call    ?FindCreateFont@@YAHKPEA_WU_COORD@@JI@Z; FindCreateFont(ulong,wchar_t *,_COORD,long,uint)
0x180007a91  mov     rdx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180007a98  mov     r9, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180007a9f  mov     r8d, eax
0x180007aa2  mov     cs:?g_currentFontIndex@@3KA, r8d; ulong g_currentFontIndex
0x180007aa9  lea     rax, [r8+r8*4]
0x180007aad  movzx   ecx, byte ptr [r9+rax*8+20h]
0x180007ab3  lea     r8, [r8+r8*4]
0x180007ab7  mov     [rdx+14h], ecx
0x180007aba  lea     rcx, [rdx+1Ch]; wchar_t *
0x180007abe  mov     eax, [r9+r8*8+8]
0x180007ac3  mov     [rdx+10h], eax
0x180007ac6  mov     eax, [r9+r8*8+10h]
0x180007acb  mov     [rdx+18h], eax
0x180007ace  mov     edx, 20h ; ' '; unsigned __int64
0x180007ad3  mov     r8, [r9+r8*8+18h]; wchar_t *
0x180007ad8  add     rsp, 38h
0x180007adc  jmp     ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
```
