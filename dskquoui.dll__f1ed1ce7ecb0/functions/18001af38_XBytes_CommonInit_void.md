# XBytes::CommonInit(void)

- ea: `0x18001af38`
- end: `0x18001af89`
- name: `?CommonInit@XBytes@@AEAAXXZ`
- size: `81`
- prototype: `void __fastcall(XBytes *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001add0`

## callees

- `0x18001af38`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001af7e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001af7e`
- `USER32!SendMessageW` at `0x18001af56`
- `USER32!SendMessageW` at `0x18001af56`

## pseudocode

```c
void __fastcall XBytes::CommonInit(XBytes *this)
{
  if ( *((_QWORD *)this + 1) )
    SendMessageW(*((HWND *)this + 1), *((_DWORD *)this + 4), 0xC5u, 16);
  if ( !XBytes::m_szNoLimit )
    LoadStringW(g_hInstDll, 0x1388Fu, &XBytes::m_szNoLimit, 80);
}

```

## disassembly

```asm
0x18001af38  sub     rsp, 28h
0x18001af3c  cmp     qword ptr [rcx+8], 0
0x18001af41  jz      short loc_18001AF5C
0x18001af43  mov     edx, [rcx+10h]; Msg
0x18001af46  mov     r9d, 10h; lParam
0x18001af4c  mov     rcx, [rcx+8]; hWnd
0x18001af50  mov     r8d, 0C5h; wParam
0x18001af56  call    cs:__imp_SendMessageW
0x18001af5c  xor     eax, eax
0x18001af5e  cmp     ax, cs:?m_szNoLimit@XBytes@@0PAGA; ushort near * XBytes::m_szNoLimit
0x18001af65  jnz     short loc_18001AF84
0x18001af67  mov     rcx, cs:?g_hInstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18001af6e  lea     r9d, [rax+50h]; cchBufferMax
0x18001af72  lea     r8, ?m_szNoLimit@XBytes@@0PAGA; lpBuffer
0x18001af79  mov     edx, 1388Fh; uID
0x18001af7e  call    cs:__imp_LoadStringW
0x18001af84  add     rsp, 28h
0x18001af88  retn
```
