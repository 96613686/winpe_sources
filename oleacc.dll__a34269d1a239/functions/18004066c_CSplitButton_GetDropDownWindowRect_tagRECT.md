# CSplitButton::GetDropDownWindowRect(tagRECT *)

- ea: `0x18004066c`
- end: `0x18004080f`
- name: `?GetDropDownWindowRect@CSplitButton@@AEAAJPEAUtagRECT@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(CSplitButton *__hidden this, LPPOINT lpPoints)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180040c30`

## callees

- `0x1800056a4`
- `0x180006c58`
- `0x18000771c`
- `0x18001e4c0`
- `0x18004066c`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004076f`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18004076f`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800406ee`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x1800406ee`
- `USER32!SetRect` at `0x1800407b9`
- `USER32!SetRect` at `0x1800407b9`
- `USER32!MapWindowPoints` at `0x1800407ce`
- `USER32!MapWindowPoints` at `0x1800407ce`
- `USER32!GetWindowRect` at `0x180040788`
- `USER32!GetWindowRect` at `0x180040788`

## pseudocode

```c
__int64 __fastcall CSplitButton::GetDropDownWindowRect(HWND *this, struct tagRECT *lpPoints)
{
  void *v4; // rax
  void *v5; // rbx
  unsigned int v6; // esi
  HWND v7; // r8
  int v8; // r15d
  HWND v10; // rcx
  int v11; // r9d
  int v12; // eax
  HANDLE hProcess; // [rsp+40h] [rbp-40h] BYREF
  __int128 Buffer; // [rsp+48h] [rbp-38h] BYREF
  __int128 v15; // [rsp+58h] [rbp-28h]
  struct tagRECT Rect; // [rsp+68h] [rbp-18h] BYREF

  hProcess = 0;
  v4 = SharedAlloc(0x20u, this[10], &hProcess);
  v5 = v4;
  if ( v4 )
  {
    Buffer = 0;
    LODWORD(Buffer) = 8;
    v6 = -2147467259;
    v15 = 0;
    if ( WriteProcessMemory(hProcess, v4, &Buffer, 0x20u, 0) )
    {
      v7 = this[10];
      *(_QWORD *)&Rect.left = 0;
      v8 = CAccessible::AccSendMessageTimeout(
             (CAccessible *)this,
             0,
             v7,
             0x1608u,
             0,
             (__int64)v5,
             (__int64 *)&Rect.left);
      if ( v8 < 0 )
      {
        SharedFree(v5, hProcess);
        return (unsigned int)v8;
      }
      if ( *(_QWORD *)&Rect.left && ReadProcessMemory(hProcess, v5, &Buffer, 0x20u, 0) )
      {
        v10 = this[10];
        Rect = 0;
        GetWindowRect(v10, &Rect);
        v11 = 0;
        if ( Rect.right - Rect.left >= 0 )
          v11 = Rect.right - Rect.left;
        v12 = 0;
        if ( Rect.bottom - Rect.top >= 0 )
          v12 = Rect.bottom - Rect.top;
        SetRect(lpPoints, v11 - DWORD1(v15), 0, v11, v12);
        MapWindowPoints(this[10], 0, (LPPOINT)lpPoints, 2u);
        v6 = 0;
      }
    }
    SharedFree(v5, hProcess);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x18004066c  mov     [rsp-28h+arg_10], rbx
0x180040671  push    rbp
0x180040672  push    rsi
0x180040673  push    r12
0x180040675  push    r14
0x180040677  push    r15
0x180040679  mov     rbp, rsp
0x18004067c  sub     rsp, 80h
0x180040683  mov     rax, cs:__security_cookie
0x18004068a  xor     rax, rsp
0x18004068d  mov     [rbp+var_8], rax
0x180040691  mov     r12, rdx
0x180040694  mov     [rbp+hProcess], 0
0x18004069c  mov     rdx, [rcx+50h]; HWND
0x1800406a0  lea     r8, [rbp+hProcess]; void **
0x1800406a4  mov     r14, rcx
0x1800406a7  mov     ecx, 20h ; ' '; dwSize
0x1800406ac  call    ?SharedAlloc@@YAPEAXIPEAUHWND__@@PEAPEAX@Z; SharedAlloc(uint,HWND__ *,void * *)
0x1800406b1  mov     rbx, rax
0x1800406b4  test    rax, rax
0x1800406b7  jz      loc_1800407E4
0x1800406bd  mov     rcx, [rbp+hProcess]; hProcess
0x1800406c1  lea     r8, [rbp+Buffer]; lpBuffer
0x1800406c5  xorps   xmm0, xmm0
0x1800406c8  mov     [rsp+80h+lpNumberOfBytesWritten], 0; lpNumberOfBytesWritten
0x1800406d1  movups  [rbp+Buffer], xmm0
0x1800406d5  mov     r9d, 20h ; ' '; nSize
0x1800406db  mov     dword ptr [rbp+Buffer], 8
0x1800406e2  mov     rdx, rax; lpBaseAddress
0x1800406e5  mov     esi, 80004005h
0x1800406ea  movups  [rbp+var_28], xmm0
0x1800406ee  call    cs:__imp_WriteProcessMemory
0x1800406f4  test    eax, eax
0x1800406f6  jz      loc_1800407D6
0x1800406fc  mov     r8, [r14+50h]; HWND
0x180040700  lea     rax, [rbp+Rect]
0x180040704  mov     [rsp+80h+var_50], rax; __int64 *
0x180040709  mov     r9d, 1608h; unsigned int
0x18004070f  mov     [rsp+80h+var_58], rbx; __int64
0x180040714  xor     edx, edx; bool
0x180040716  mov     rcx, r14; this
0x180040719  mov     [rsp+80h+lpNumberOfBytesWritten], 0; unsigned __int64
0x180040722  mov     qword ptr [rbp+Rect.left], 0
0x18004072a  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18004072f  mov     r15d, eax
0x180040732  test    eax, eax
0x180040734  jns     short loc_18004074A
0x180040736  mov     rdx, [rbp+hProcess]; hProcess
0x18004073a  mov     rcx, rbx; lpAddress
0x18004073d  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x180040742  mov     eax, r15d
0x180040745  jmp     loc_1800407EB
0x18004074a  cmp     qword ptr [rbp+Rect.left], 0
0x18004074f  jz      loc_1800407D6
0x180040755  mov     rcx, [rbp+hProcess]; hProcess
0x180040759  lea     r8, [rbp+Buffer]; lpBuffer
0x18004075d  mov     r9d, 20h ; ' '; nSize
0x180040763  mov     [rsp+80h+lpNumberOfBytesWritten], 0; lpNumberOfBytesRead
0x18004076c  mov     rdx, rbx; lpBaseAddress
0x18004076f  call    cs:__imp_ReadProcessMemory
0x180040775  test    eax, eax
0x180040777  jz      short loc_1800407D6
0x180040779  mov     rcx, [r14+50h]; hWnd
0x18004077d  lea     rdx, [rbp+Rect]; lpRect
0x180040781  xorps   xmm0, xmm0
0x180040784  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180040788  call    cs:__imp_GetWindowRect
0x18004078e  mov     ecx, [rbp+Rect.bottom]
0x180040791  mov     r9d, 0
0x180040797  mov     eax, [rbp+Rect.right]
0x18004079a  sub     eax, [rbp+Rect.left]
0x18004079d  cmovns  r9d, eax; xRight
0x1800407a1  xor     eax, eax
0x1800407a3  sub     ecx, [rbp+Rect.top]
0x1800407a6  mov     edx, r9d
0x1800407a9  cmovns  eax, ecx
0x1800407ac  sub     edx, dword ptr [rbp+var_28+4]; xLeft
0x1800407af  xor     r8d, r8d; yTop
0x1800407b2  mov     dword ptr [rsp+80h+lpNumberOfBytesWritten], eax; yBottom
0x1800407b6  mov     rcx, r12; lprc
0x1800407b9  call    cs:__imp_SetRect
0x1800407bf  mov     rcx, [r14+50h]; hWndFrom
0x1800407c3  mov     r9d, 2; cPoints
0x1800407c9  mov     r8, r12; lpPoints
0x1800407cc  xor     edx, edx; hWndTo
0x1800407ce  call    cs:__imp_MapWindowPoints
0x1800407d4  xor     esi, esi
0x1800407d6  mov     rdx, [rbp+hProcess]; hProcess
0x1800407da  mov     rcx, rbx; lpAddress
0x1800407dd  call    ?SharedFree@@YAXPEAX0@Z; SharedFree(void *,void *)
0x1800407e2  jmp     short loc_1800407E9
0x1800407e4  mov     esi, 8007000Eh
0x1800407e9  mov     eax, esi
0x1800407eb  mov     rcx, [rbp+var_8]
0x1800407ef  xor     rcx, rsp; StackCookie
0x1800407f2  call    __security_check_cookie
0x1800407f7  mov     rbx, [rsp+80h+arg_10]
0x1800407ff  add     rsp, 80h
0x180040806  pop     r15
0x180040808  pop     r14
0x18004080a  pop     r12
0x18004080c  pop     rsi
0x18004080d  pop     rbp
0x18004080e  retn
```
