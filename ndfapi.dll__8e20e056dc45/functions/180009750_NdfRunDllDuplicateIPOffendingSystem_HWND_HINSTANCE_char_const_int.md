# NdfRunDllDuplicateIPOffendingSystem(HWND__ *,HINSTANCE__ *,char const *,int)

- ea: `0x180009750`
- end: `0x1800097a8`
- name: `?NdfRunDllDuplicateIPOffendingSystem@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@Z`
- size: `88`
- prototype: `void __fastcall(HWND, HINSTANCE, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180008cb8`
- `0x180010054`

## import_xrefs

- `USER32!GetDesktopWindow` at `0x180009769`
- `USER32!GetDesktopWindow` at `0x180009769`
- `ole32!CoTaskMemFree` at `0x1800097a1`

## pseudocode

```c
void __fastcall NdfRunDllDuplicateIPOffendingSystem(HWND a1, HINSTANCE a2, const char *a3)
{
  HWND DesktopWindow; // rax
  struct _GUID *v4; // rbx
  const unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // r9
  struct _GUID *v7; // [rsp+40h] [rbp-18h] BYREF

  v7 = 0;
  GetGUIDForFirstDADAdapter(&v7);
  DesktopWindow = GetDesktopWindow();
  v4 = v7;
  DuplicateIPMessageBox(g_hinstDll, DesktopWindow, v5, v6, (const unsigned __int16 *)0x9CBB, 1, v7);
  CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x180009750  push    rbx
0x180009752  sub     rsp, 50h
0x180009756  lea     rcx, [rsp+58h+var_18]; struct _GUID **
0x18000975b  mov     [rsp+58h+var_18], 0
0x180009764  call    ?GetGUIDForFirstDADAdapter@@YAXPEAPEAU_GUID@@@Z; GetGUIDForFirstDADAdapter(_GUID * *)
0x180009769  call    cs:__imp_GetDesktopWindow
0x18000976f  mov     rbx, [rsp+58h+var_18]
0x180009774  mov     rdx, rax; HWND
0x180009777  mov     rcx, cs:?g_hinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x18000977e  mov     [rsp+58h+var_28], rbx; struct _GUID *
0x180009783  mov     [rsp+58h+var_30], 1; int
0x18000978b  mov     [rsp+58h+var_38], 9CBBh; unsigned __int16 *
0x180009794  call    ?DuplicateIPMessageBox@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBG22HPEAU_GUID@@@Z; DuplicateIPMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,ushort const *,int,_GUID *)
0x180009799  mov     rcx, rbx
0x18000979c  add     rsp, 50h
0x1800097a0  pop     rbx
0x1800097a1  jmp     cs:__imp_CoTaskMemFree
```
