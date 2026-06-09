# CTray::SaveWindowPositions(uint)

- ea: `0x1400b239c`
- end: `0x1400b24e8`
- name: `?SaveWindowPositions@CTray@@QEAAXI@Z`
- size: `332`
- prototype: `void __fastcall(CTray *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140092180`
- `0x1400abc30`

## callees

- `0x140021200`
- `0x1400b239c`
- `0x14010e160`
- `0x14013bc6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400b23d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400b23d1`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400b2447`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400b2447`
- `GDI32!CreateRectRgn` at `0x1400b2465`
- `GDI32!CreateRectRgn` at `0x1400b2465`
- `GDI32!DeleteObject` at `0x1400b24bc`
- `GDI32!DeleteObject` at `0x1400b24bc`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x1400b24a8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x1400b24a8`

## pseudocode

```c
void __fastcall CTray::SaveWindowPositions(CTray *this, int a2)
{
  _DWORD *v2; // rax
  struct _DSA *v5; // rcx
  HRGN RectRgn; // rdi
  LPARAM lParam[4]; // [rsp+20h] [rbp-48h] BYREF
  __int128 pvParam; // [rsp+40h] [rbp-28h] BYREF

  v2 = (_DWORD *)*((_QWORD *)this + 50);
  if ( v2 || (v2 = LocalAlloc(0x40u, 0x10u), (*((_QWORD *)this + 50) = v2) != 0) )
  {
    *v2 = a2;
    v5 = *(struct _DSA **)(*((_QWORD *)this + 50) + 8LL);
    if ( v5 )
      DSA_DeleteAllItems(v5);
    else
      *(_QWORD *)(*((_QWORD *)this + 50) + 8LL) = DSA_Create(56, 4);
    if ( *(_QWORD *)(*((_QWORD *)this + 50) + 8LL) )
    {
      RectRgn = 0;
      pvParam = 0;
      SystemParametersInfoW(0x30u, 0, &pvParam, 0);
      if ( a2 == 539 )
        RectRgn = CreateRectRgn(0, 0, 0, 0);
      lParam[0] = *((_QWORD *)this + 1);
      lParam[1] = *(_QWORD *)(*((_QWORD *)this + 50) + 8LL);
      lParam[2] = (LPARAM)RectRgn;
      lParam[3] = (LPARAM)&pvParam;
      EnumWindows((WNDENUMPROC)CTray::SavePosEnumProc, (LPARAM)lParam);
      if ( RectRgn )
        DeleteObject(RectRgn);
    }
  }
}

```

## disassembly

```asm
0x1400b239c  mov     [rsp+arg_8], rbx
0x1400b23a1  mov     [rsp+arg_10], rsi
0x1400b23a6  push    rdi
0x1400b23a7  sub     rsp, 60h
0x1400b23ab  mov     rax, cs:__security_cookie
0x1400b23b2  xor     rax, rsp
0x1400b23b5  mov     [rsp+68h+var_18], rax
0x1400b23ba  mov     rax, [rcx+190h]
0x1400b23c1  mov     esi, edx
0x1400b23c3  mov     rbx, rcx
0x1400b23c6  test    rax, rax
0x1400b23c9  jnz     short loc_1400B23ED
0x1400b23cb  lea     edx, [rax+10h]; uBytes
0x1400b23ce  lea     ecx, [rax+40h]; uFlags
0x1400b23d1  call    cs:__imp_LocalAlloc
0x1400b23d8  nop     dword ptr [rax+rax+00h]
0x1400b23dd  mov     [rbx+190h], rax
0x1400b23e4  test    rax, rax
0x1400b23e7  jz      loc_1400B24C8
0x1400b23ed  mov     [rax], esi
0x1400b23ef  mov     rax, [rbx+190h]
0x1400b23f6  mov     rcx, [rax+8]; hdsa
0x1400b23fa  test    rcx, rcx
0x1400b23fd  jz      short loc_1400B2406
0x1400b23ff  call    DSA_DeleteAllItems
0x1400b2404  jmp     short loc_1400B241E
0x1400b2406  mov     edx, 4; cItemGrow
0x1400b240b  lea     ecx, [rdx+34h]; cbItem
0x1400b240e  call    DSA_Create
0x1400b2413  mov     rcx, [rbx+190h]
0x1400b241a  mov     [rcx+8], rax
0x1400b241e  mov     rax, [rbx+190h]
0x1400b2425  cmp     qword ptr [rax+8], 0
0x1400b242a  jz      loc_1400B24C8
0x1400b2430  xorps   xmm0, xmm0
0x1400b2433  lea     r8, [rsp+68h+pvParam]; pvParam
0x1400b2438  xor     edi, edi
0x1400b243a  xor     r9d, r9d; fWinIni
0x1400b243d  xor     edx, edx; uiParam
0x1400b243f  movups  [rsp+68h+pvParam], xmm0
0x1400b2444  lea     ecx, [rdi+30h]; uiAction
0x1400b2447  call    cs:__imp_SystemParametersInfoW
0x1400b244e  nop     dword ptr [rax+rax+00h]
0x1400b2453  cmp     esi, 21Bh
0x1400b2459  jnz     short loc_1400B2474
0x1400b245b  xor     r9d, r9d; y2
0x1400b245e  xor     r8d, r8d; x2
0x1400b2461  xor     edx, edx; y1
0x1400b2463  xor     ecx, ecx; x1
0x1400b2465  call    cs:__imp_CreateRectRgn
0x1400b246c  nop     dword ptr [rax+rax+00h]
0x1400b2471  mov     rdi, rax
0x1400b2474  mov     rcx, [rbx+8]
0x1400b2478  lea     rax, [rsp+68h+pvParam]
0x1400b247d  mov     [rsp+68h+lParam], rcx
0x1400b2482  mov     rcx, [rbx+190h]
0x1400b2489  mov     rdx, [rcx+8]
0x1400b248d  lea     rcx, ?SavePosEnumProc@CTray@@KAHPEAUHWND__@@_J@Z; lpEnumFunc
0x1400b2494  mov     [rsp+68h+var_40], rdx
0x1400b2499  lea     rdx, [rsp+68h+lParam]; lParam
0x1400b249e  mov     [rsp+68h+var_38], rdi
0x1400b24a3  mov     [rsp+68h+var_30], rax
0x1400b24a8  call    cs:__imp_EnumWindows
0x1400b24af  nop     dword ptr [rax+rax+00h]
0x1400b24b4  test    rdi, rdi
0x1400b24b7  jz      short loc_1400B24C8
0x1400b24b9  mov     rcx, rdi; ho
0x1400b24bc  call    cs:__imp_DeleteObject
0x1400b24c3  nop     dword ptr [rax+rax+00h]
0x1400b24c8  mov     rcx, [rsp+68h+var_18]
0x1400b24cd  xor     rcx, rsp; StackCookie
0x1400b24d0  call    __security_check_cookie
0x1400b24d5  lea     r11, [rsp+68h+var_8]
0x1400b24da  mov     rbx, [r11+18h]
0x1400b24de  mov     rsi, [r11+20h]
0x1400b24e2  mov     rsp, r11
0x1400b24e5  pop     rdi
0x1400b24e6  retn
```
