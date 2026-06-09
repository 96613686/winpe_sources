# DwmpSaveColorizationParameter

- ea: `0x180008458`
- end: `0x1800084a8`
- name: `DwmpSaveColorizationParameter`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008294`

## callees

- `0x180003370`
- `0x180008458`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008479`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008479`

## pseudocode

```c
__int64 __fastcall DwmpSaveColorizationParameter(HKEY a1, const WCHAR *a2, int a3)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v3 = RegSetValueExW(a1, a2, 0, 4u, (const BYTE *)&v6, 4u);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
    DoStackCaptureDirect(v4, 0x61u);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008458  mov     r11, rsp
0x18000845b  mov     [r11+18h], r8d
0x18000845f  push    rbx
0x180008460  sub     rsp, 30h
0x180008464  mov     r9d, 4; dwType
0x18000846a  lea     rax, [r11+18h]
0x18000846e  mov     [r11-10h], r9d
0x180008472  xor     r8d, r8d; Reserved
0x180008475  mov     [r11-18h], rax
0x180008479  call    cs:__imp_RegSetValueExW
0x18000847f  mov     ebx, eax
0x180008481  test    eax, eax
0x180008483  jle     short loc_18000848E
0x180008485  movzx   ebx, ax
0x180008488  or      ebx, 80070000h
0x18000848e  test    ebx, ebx
0x180008490  js      short loc_18000849A
0x180008492  mov     eax, ebx
0x180008494  add     rsp, 30h
0x180008498  pop     rbx
0x180008499  retn
0x18000849a  mov     edx, 61h ; 'a'; unsigned int
0x18000849f  mov     ecx, ebx; int
0x1800084a1  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800084a6  jmp     short loc_180008492
```
