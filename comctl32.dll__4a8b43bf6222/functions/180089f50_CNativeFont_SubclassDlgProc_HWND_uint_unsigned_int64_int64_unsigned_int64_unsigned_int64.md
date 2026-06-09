# CNativeFont::_SubclassDlgProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x180089f50`
- end: `0x18008a045`
- name: `?_SubclassDlgProc@CNativeFont@@KA_JPEAUHWND__@@I_K_J11@Z`
- size: `245`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180030230`
- `0x1800306e0`
- `0x180089c68`
- `0x180089f50`

## import_xrefs

- `GDI32!DeleteObject` at `0x180089ff8`
- `GDI32!DeleteObject` at `0x18008a00a`
- `GDI32!DeleteObject` at `0x180089ff8`
- `GDI32!DeleteObject` at `0x18008a00a`
- `USER32!EnumChildWindows` at `0x180089fc0`
- `USER32!EnumChildWindows` at `0x180089fee`
- `USER32!EnumChildWindows` at `0x180089fc0`
- `USER32!EnumChildWindows` at `0x180089fee`

## pseudocode

```c
LRESULT __fastcall CNativeFont::_SubclassDlgProc(
        HWND hWnd,
        UINT uMsg,
        WPARAM wParam,
        LPARAM lParam,
        UINT_PTR uIdSubclass,
        DWORD_PTR dwRefData)
{
  LRESULT result; // rax
  void *v11; // rcx
  LPARAM lParama; // [rsp+20h] [rbp-38h] BYREF
  int v13; // [rsp+28h] [rbp-30h]
  int v14; // [rsp+2Ch] [rbp-2Ch]

  result = 0;
  if ( dwRefData )
  {
    if ( uMsg == 2 )
    {
      if ( *(_QWORD *)(dwRefData + 80) )
      {
        v14 = 0;
        lParama = *(_QWORD *)(dwRefData + 64);
        v13 = *(_DWORD *)(dwRefData + 24);
        EnumChildWindows(hWnd, CNativeFont::_SetFontEnumProc, (LPARAM)&lParama);
        DeleteObject(*(HGDIOBJ *)(dwRefData + 80));
        v11 = *(void **)(dwRefData + 72);
        *(_QWORD *)(dwRefData + 80) = 0;
        DeleteObject(v11);
        *(_QWORD *)(dwRefData + 72) = 0;
      }
      RemoveWindowSubclass(hWnd, CNativeFont::_SubclassDlgProc, 0);
    }
    else if ( uMsg == 272 && !CNativeFont::_GetNativeDialogFont((CNativeFont *)dwRefData, hWnd) )
    {
      v14 = 0;
      lParama = *(_QWORD *)(dwRefData + 72);
      v13 = *(_DWORD *)(dwRefData + 24);
      EnumChildWindows(hWnd, CNativeFont::_SetFontEnumProc, (LPARAM)&lParama);
    }
    return DefSubclassProc(hWnd, uMsg, wParam, lParam);
  }
  return result;
}

```

## disassembly

```asm
0x180089f50  push    rbx
0x180089f52  push    rbp
0x180089f53  push    rsi
0x180089f54  push    rdi
0x180089f55  push    r14
0x180089f57  sub     rsp, 30h
0x180089f5b  mov     rbx, [rsp+58h+dwRefData]
0x180089f63  xor     eax, eax
0x180089f65  mov     rbp, r9
0x180089f68  mov     r14, r8
0x180089f6b  mov     esi, edx
0x180089f6d  mov     rdi, rcx
0x180089f70  test    rbx, rbx
0x180089f73  jz      loc_18008A03A
0x180089f79  cmp     edx, 2
0x180089f7c  jz      short loc_180089FC8
0x180089f7e  cmp     edx, 110h
0x180089f84  jnz     loc_18008A02A
0x180089f8a  mov     rdx, rcx; HWND
0x180089f8d  mov     rcx, rbx; this
0x180089f90  call    ?_GetNativeDialogFont@CNativeFont@@IEAAJPEAUHWND__@@@Z; CNativeFont::_GetNativeDialogFont(HWND__ *)
0x180089f95  test    eax, eax
0x180089f97  jnz     loc_18008A02A
0x180089f9d  mov     [rsp+58h+var_2C], eax
0x180089fa1  lea     r8, [rsp+58h+lParam]; lParam
0x180089fa6  mov     rax, [rbx+48h]
0x180089faa  lea     rdx, ?_SetFontEnumProc@CNativeFont@@KAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180089fb1  mov     [rsp+58h+lParam], rax
0x180089fb6  mov     rcx, rdi; hWndParent
0x180089fb9  mov     eax, [rbx+18h]
0x180089fbc  mov     [rsp+58h+var_30], eax
0x180089fc0  call    cs:__imp_EnumChildWindows
0x180089fc6  jmp     short loc_18008A02A
0x180089fc8  cmp     [rbx+50h], rax
0x180089fcc  jz      short loc_18008A018
0x180089fce  mov     [rsp+58h+var_2C], eax
0x180089fd2  lea     r8, [rsp+58h+lParam]; lParam
0x180089fd7  mov     rax, [rbx+40h]
0x180089fdb  lea     rdx, ?_SetFontEnumProc@CNativeFont@@KAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180089fe2  mov     [rsp+58h+lParam], rax
0x180089fe7  mov     eax, [rbx+18h]
0x180089fea  mov     [rsp+58h+var_30], eax
0x180089fee  call    cs:__imp_EnumChildWindows
0x180089ff4  mov     rcx, [rbx+50h]; ho
0x180089ff8  call    cs:__imp_DeleteObject
0x180089ffe  mov     rcx, [rbx+48h]; ho
0x18008a002  mov     qword ptr [rbx+50h], 0
0x18008a00a  call    cs:__imp_DeleteObject
0x18008a010  mov     qword ptr [rbx+48h], 0
0x18008a018  xor     r8d, r8d; uIdSubclass
0x18008a01b  lea     rdx, ?_SubclassDlgProc@CNativeFont@@KA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x18008a022  mov     rcx, rdi; hWnd
0x18008a025  call    RemoveWindowSubclass
0x18008a02a  mov     r9, rbp; lParam
0x18008a02d  mov     r8, r14; wParam
0x18008a030  mov     edx, esi; uMsg
0x18008a032  mov     rcx, rdi; hWnd
0x18008a035  call    DefSubclassProc
0x18008a03a  add     rsp, 30h
0x18008a03e  pop     r14
0x18008a040  pop     rdi
0x18008a041  pop     rsi
0x18008a042  pop     rbp
0x18008a043  pop     rbx
0x18008a044  retn
```
