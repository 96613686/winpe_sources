# CMapiPreviewer::FinalConstruct(void)

- ea: `0x1800245d8`
- end: `0x18002466f`
- name: `?FinalConstruct@CMapiPreviewer@@QEAAJXZ`
- size: `151`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000caa0`
- `0x18000d0a4`

## callees

- `0x18000557c`
- `0x180006dcc`
- `0x1800245d8`
- `0x1800314c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180024640`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180024640`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x180024633`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x180024633`

## string_xrefs

- `0x180024639`: `msftedit.dll`

## pseudocode

```c
int __fastcall CMapiPreviewer::FinalConstruct(CMapiPreviewer *this)
{
  HMODULE LibraryW; // rax
  int result; // eax
  WNDCLASSW WndClass; // [rsp+20h] [rbp-58h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 3;
  WndClass.lpfnWndProc = (WNDPROC)CMapiPreviewer::FullWndProc;
  WndClass.hInstance = off_180053498;
  WndClass.lpszClassName = L"MAPI Preview Full class";
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.cbWndExtra = 8;
  RegisterClassW(&WndClass);
  LibraryW = LoadLibraryW(L"msftedit.dll");
  *((_QWORD *)this + 33) = LibraryW;
  if ( LibraryW )
    return CMapiManager::GetMapiManager((struct CMapiManager **)this + 36, 0);
  result = ResultFromLastError();
  if ( result >= 0 )
    return CMapiManager::GetMapiManager((struct CMapiManager **)this + 36, 0);
  return result;
}

```

## disassembly

```asm
0x1800245d8  push    rbx
0x1800245da  sub     rsp, 70h
0x1800245de  xor     edx, edx; Val
0x1800245e0  mov     rbx, rcx
0x1800245e3  lea     rcx, [rsp+78h+WndClass]; void *
0x1800245e8  lea     r8d, [rdx+48h]; Size
0x1800245ec  call    memset_0
0x1800245f1  lea     rax, ?FullWndProc@CMapiPreviewer@@CA_JPEAUHWND__@@I_K_J@Z; CMapiPreviewer::FullWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800245f8  mov     [rsp+78h+WndClass.style], 3
0x180024600  mov     [rsp+78h+WndClass.lpfnWndProc], rax
0x180024605  lea     rcx, [rsp+78h+WndClass]; lpWndClass
0x18002460a  mov     rax, cs:off_180053498
0x180024611  mov     [rsp+78h+WndClass.hInstance], rax
0x180024616  lea     rax, aMapiPreviewFul; "MAPI Preview Full class"
0x18002461d  mov     [rsp+78h+WndClass.lpszClassName], rax
0x180024622  mov     [rsp+78h+WndClass.hbrBackground], 6
0x18002462b  mov     [rsp+78h+WndClass.cbWndExtra], 8
0x180024633  call    cs:__imp_RegisterClassW
0x180024639  lea     rcx, aMsfteditDll; "msftedit.dll"
0x180024640  call    cs:__imp_LoadLibraryW
0x180024646  mov     [rbx+108h], rax
0x18002464d  test    rax, rax
0x180024650  jnz     short loc_18002465B
0x180024652  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180024657  test    eax, eax
0x180024659  js      short loc_180024669
0x18002465b  lea     rcx, [rbx+120h]; struct CMapiManager **
0x180024662  xor     edx, edx; unsigned int
0x180024664  call    ?GetMapiManager@CMapiManager@@SAJPEAPEAV1@K@Z; CMapiManager::GetMapiManager(CMapiManager * *,ulong)
0x180024669  add     rsp, 70h
0x18002466d  pop     rbx
0x18002466e  retn
```
