# CTray::SaveWindowPositions(uint)

- ea: `0x1400ac48c`
- end: `0x1400ac5b9`
- name: `?SaveWindowPositions@CTray@@QEAAXI@Z`
- size: `301`
- prototype: `void __fastcall(CTray *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14008c760`
- `0x1400a5b40`

## callees

- `0x140023a40`
- `0x1400ac48c`
- `0x1401040e0`
- `0x14012ff3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400ac4c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400ac4c1`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400ac531`
- `api-ms-win-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x1400ac531`
- `GDI32!DeleteObject` at `0x1400ac594`
- `GDI32!DeleteObject` at `0x1400ac594`
- `GDI32!CreateRectRgn` at `0x1400ac549`
- `GDI32!CreateRectRgn` at `0x1400ac549`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x1400ac586`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!EnumWindows` at `0x1400ac586`

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
0x1400ac48c  mov     [rsp+arg_8], rbx
0x1400ac491  mov     [rsp+arg_10], rsi
0x1400ac496  push    rdi
0x1400ac497  sub     rsp, 60h
0x1400ac49b  mov     rax, cs:__security_cookie
0x1400ac4a2  xor     rax, rsp
0x1400ac4a5  mov     [rsp+68h+var_18], rax
0x1400ac4aa  mov     rax, [rcx+190h]
0x1400ac4b1  mov     esi, edx
0x1400ac4b3  mov     rbx, rcx
0x1400ac4b6  test    rax, rax
0x1400ac4b9  jnz     short loc_1400AC4D7
0x1400ac4bb  lea     edx, [rax+10h]; uBytes
0x1400ac4be  lea     ecx, [rax+40h]; uFlags
0x1400ac4c1  call    cs:__imp_LocalAlloc
0x1400ac4c7  mov     [rbx+190h], rax
0x1400ac4ce  test    rax, rax
0x1400ac4d1  jz      loc_1400AC59A
0x1400ac4d7  mov     [rax], esi
0x1400ac4d9  mov     rax, [rbx+190h]
0x1400ac4e0  mov     rcx, [rax+8]; hdsa
0x1400ac4e4  test    rcx, rcx
0x1400ac4e7  jz      short loc_1400AC4F0
0x1400ac4e9  call    DSA_DeleteAllItems
0x1400ac4ee  jmp     short loc_1400AC508
0x1400ac4f0  mov     edx, 4; cItemGrow
0x1400ac4f5  lea     ecx, [rdx+34h]; cbItem
0x1400ac4f8  call    DSA_Create
0x1400ac4fd  mov     rcx, [rbx+190h]
0x1400ac504  mov     [rcx+8], rax
0x1400ac508  mov     rax, [rbx+190h]
0x1400ac50f  cmp     qword ptr [rax+8], 0
0x1400ac514  jz      loc_1400AC59A
0x1400ac51a  xorps   xmm0, xmm0
0x1400ac51d  lea     r8, [rsp+68h+pvParam]; pvParam
0x1400ac522  xor     edi, edi
0x1400ac524  xor     r9d, r9d; fWinIni
0x1400ac527  xor     edx, edx; uiParam
0x1400ac529  movups  [rsp+68h+pvParam], xmm0
0x1400ac52e  lea     ecx, [rdi+30h]; uiAction
0x1400ac531  call    cs:__imp_SystemParametersInfoW
0x1400ac537  cmp     esi, 21Bh
0x1400ac53d  jnz     short loc_1400AC552
0x1400ac53f  xor     r9d, r9d; y2
0x1400ac542  xor     r8d, r8d; x2
0x1400ac545  xor     edx, edx; y1
0x1400ac547  xor     ecx, ecx; x1
0x1400ac549  call    cs:__imp_CreateRectRgn
0x1400ac54f  mov     rdi, rax
0x1400ac552  mov     rcx, [rbx+8]
0x1400ac556  lea     rax, [rsp+68h+pvParam]
0x1400ac55b  mov     [rsp+68h+lParam], rcx
0x1400ac560  mov     rcx, [rbx+190h]
0x1400ac567  mov     rdx, [rcx+8]
0x1400ac56b  lea     rcx, ?SavePosEnumProc@CTray@@KAHPEAUHWND__@@_J@Z; lpEnumFunc
0x1400ac572  mov     [rsp+68h+var_40], rdx
0x1400ac577  lea     rdx, [rsp+68h+lParam]; lParam
0x1400ac57c  mov     [rsp+68h+var_38], rdi
0x1400ac581  mov     [rsp+68h+var_30], rax
0x1400ac586  call    cs:__imp_EnumWindows
0x1400ac58c  test    rdi, rdi
0x1400ac58f  jz      short loc_1400AC59A
0x1400ac591  mov     rcx, rdi; ho
0x1400ac594  call    cs:__imp_DeleteObject
0x1400ac59a  mov     rcx, [rsp+68h+var_18]
0x1400ac59f  xor     rcx, rsp; StackCookie
0x1400ac5a2  call    __security_check_cookie
0x1400ac5a7  lea     r11, [rsp+68h+var_8]
0x1400ac5ac  mov     rbx, [r11+18h]
0x1400ac5b0  mov     rsi, [r11+20h]
0x1400ac5b4  mov     rsp, r11
0x1400ac5b7  pop     rdi
0x1400ac5b8  retn
```
