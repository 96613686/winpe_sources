# FlatSB_SetScrollRange

- ea: `0x180034880`
- end: `0x1800349b7`
- name: `FlatSB_SetScrollRange`
- size: `311`
- prototype: `int __stdcall(HWND, int code, int min, int max, BOOL fRedraw)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800751a0`
- `0x18007a9f0`

## callees

- `0x1800115f0`
- `0x180030440`
- `0x180030800`
- `0x1800330c4`
- `0x180033a40`
- `0x180034880`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003492d`
- `GDI32!DeleteObject` at `0x18003493a`
- `GDI32!DeleteObject` at `0x18003492d`
- `GDI32!DeleteObject` at `0x18003493a`
- `KERNEL32!LocalFree` at `0x180034943`
- `KERNEL32!LocalFree` at `0x180034943`
- `USER32!SetScrollRange` at `0x1800348ef`
- `USER32!SetScrollRange` at `0x1800348ef`

## pseudocode

```c
int __stdcall FlatSB_SetScrollRange(HWND a1, int code, int min, int max, BOOL fRedraw)
{
  HGDIOBJ *v9; // rbx
  char *inited; // rax
  _BOOL8 v12; // r9
  DWORD_PTR pdwRefData; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v14[4]; // [rsp+38h] [rbp-50h] BYREF

  memset(v14, 0, 28);
  pdwRefData = 0;
  GetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, &pdwRefData);
  v9 = (HGDIOBJ *)pdwRefData;
  if ( !pdwRefData )
    return SetScrollRange(a1, code, min, max, fRedraw);
  if ( pdwRefData == -1 )
  {
    inited = FlatSB_Internal_InitPwSB((__int64)a1);
    v9 = (HGDIOBJ *)inited;
    if ( !inited )
      return 0;
    if ( !SetWindowSubclass(a1, (SUBCLASSPROC)FlatSB_SubclassWndProc, 0, (DWORD_PTR)inited) )
    {
      DeleteObject(v9[31]);
      DeleteObject(v9[30]);
      LocalFree(v9);
      return 0;
    }
    v12 = 1;
  }
  else
  {
    if ( a1 != *(HWND *)(pdwRefData + 264) )
      return 0;
    v12 = fRedraw;
  }
  if ( (unsigned int)(max - min) > 0x7FFF )
    return 0;
  v14[0] = 0x10000001CLL;
  v14[1] = __PAIR64__(max, min);
  FlatSB_Internal_SetScrollBar(v9, (unsigned int)code, v14, v12);
  return 1;
}

```

## disassembly

```asm
0x180034880  push    rbx
0x180034882  push    rbp
0x180034883  push    rsi
0x180034884  push    rdi
0x180034885  push    r14
0x180034887  sub     rsp, 60h
0x18003488b  mov     rax, cs:__security_cookie
0x180034892  xor     rax, rsp
0x180034895  mov     [rsp+88h+var_30], rax
0x18003489a  xorps   xmm0, xmm0
0x18003489d  mov     ebp, r9d
0x1800348a0  mov     esi, r8d
0x1800348a3  lea     r9, [rsp+88h+pdwRefData]; pdwRefData
0x1800348a8  mov     r14d, edx
0x1800348ab  xor     eax, eax
0x1800348ad  movups  xmmword ptr [rsp+88h+var_50], xmm0
0x1800348b2  xor     r8d, r8d; uIdSubclass
0x1800348b5  mov     [rsp+88h+pdwRefData], rax
0x1800348ba  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x1800348c1  mov     rdi, rcx
0x1800348c4  movups  xmmword ptr [rsp+88h+var_50+0Ch], xmm0
0x1800348c9  call    GetWindowSubclass
0x1800348ce  mov     rbx, [rsp+88h+pdwRefData]
0x1800348d3  test    rbx, rbx
0x1800348d6  jnz     short loc_1800348F7
0x1800348d8  mov     eax, [rsp+88h+fRedraw]
0x1800348df  mov     r9d, ebp; nMaxPos
0x1800348e2  mov     r8d, esi; nMinPos
0x1800348e5  mov     [rsp+88h+bRedraw], eax; bRedraw
0x1800348e9  mov     edx, r14d; nBar
0x1800348ec  mov     rcx, rdi; hWnd
0x1800348ef  call    cs:__imp_SetScrollRange
0x1800348f5  jmp     short loc_18003494B
0x1800348f7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800348fb  jnz     short loc_18003496B
0x1800348fd  mov     rcx, rdi
0x180034900  call    FlatSB_Internal_InitPwSB
0x180034905  mov     rbx, rax
0x180034908  test    rax, rax
0x18003490b  jz      short loc_180034949
0x18003490d  mov     r9, rax; dwRefData
0x180034910  lea     rdx, FlatSB_SubclassWndProc; pfnSubclass
0x180034917  xor     r8d, r8d; uIdSubclass
0x18003491a  mov     rcx, rdi; hWnd
0x18003491d  call    SetWindowSubclass
0x180034922  test    eax, eax
0x180034924  jnz     short loc_180034963
0x180034926  mov     rcx, [rbx+0F8h]; ho
0x18003492d  call    cs:__imp_DeleteObject
0x180034933  mov     rcx, [rbx+0F0h]; ho
0x18003493a  call    cs:__imp_DeleteObject
0x180034940  mov     rcx, rbx; hMem
0x180034943  call    cs:__imp_LocalFree
0x180034949  xor     eax, eax
0x18003494b  mov     rcx, [rsp+88h+var_30]
0x180034950  xor     rcx, rsp; StackCookie
0x180034953  call    __security_check_cookie
0x180034958  add     rsp, 60h
0x18003495c  pop     r14
0x18003495e  pop     rdi
0x18003495f  pop     rsi
0x180034960  pop     rbp
0x180034961  pop     rbx
0x180034962  retn
0x180034963  mov     r9d, 1
0x180034969  jmp     short loc_18003497C
0x18003496b  cmp     rdi, [rbx+108h]
0x180034972  jnz     short loc_180034949
0x180034974  mov     r9d, [rsp+88h+fRedraw]
0x18003497c  mov     ecx, ebp
0x18003497e  sub     ecx, esi
0x180034980  cmp     ecx, 7FFFh
0x180034986  ja      short loc_180034949
0x180034988  lea     r8, [rsp+88h+var_50]
0x18003498d  mov     dword ptr [rsp+88h+var_50], 1Ch
0x180034995  mov     edx, r14d
0x180034998  mov     dword ptr [rsp+88h+var_50+4], 1
0x1800349a0  mov     rcx, rbx
0x1800349a3  mov     dword ptr [rsp+88h+var_50+8], esi
0x1800349a7  mov     dword ptr [rsp+88h+var_50+0Ch], ebp
0x1800349ab  call    FlatSB_Internal_SetScrollBar
0x1800349b0  mov     eax, 1
0x1800349b5  jmp     short loc_18003494B
```
