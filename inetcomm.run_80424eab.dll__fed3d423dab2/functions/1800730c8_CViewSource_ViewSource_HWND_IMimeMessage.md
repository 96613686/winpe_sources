# CViewSource::ViewSource(HWND__ *,IMimeMessage *)

- ea: `0x1800730c8`
- end: `0x1800731d0`
- name: `?ViewSource@CViewSource@@SAJPEAUHWND__@@PEAUIMimeMessage@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(HWND hWndParent, struct IMimeMessage *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180023d04`
- `0x180064a10`
- `0x180067680`

## callees

- `0x1800299d0`
- `0x180034288`
- `0x180072eec`
- `0x1800730c8`

## import_xrefs

- `MSOERT2!GetTopMostParent` at `0x180073167`
- `MSOERT2!GetTopMostParent` at `0x180073167`
- `KERNEL32!LoadLibraryA` at `0x1800730ee`
- `KERNEL32!LoadLibraryA` at `0x1800730ee`
- `USER32!ShowWindow` at `0x1800731a0`
- `USER32!ShowWindow` at `0x1800731a0`
- `USER32!CreateDialogParamW` at `0x18007318c`
- `USER32!CreateDialogParamW` at `0x18007318c`

## string_xrefs

- `0x1800730e7`: `riched32.dll`

## pseudocode

```c
__int64 __fastcall CViewSource::ViewSource(HWND hWndParent, struct IMimeMessage *a2)
{
  char *dwInitParam; // rbx
  __int64 TopMostParent; // rax
  HINSTANCE v7; // rcx
  unsigned int v8; // edi

  if ( !qword_1800F3378 )
  {
    qword_1800F3378 = (__int64)LoadLibraryA("riched32.dll");
    if ( !qword_1800F3378 )
      return 2148275970LL;
  }
  dwInitParam = (char *)operator new(0x38u);
  if ( !dwInitParam )
    return 2147942414LL;
  *(_QWORD *)dwInitParam = &CViewSource::`vftable';
  _InterlockedIncrement(&g_cRef);
  *((_QWORD *)dwInitParam + 1) = 0;
  *((_QWORD *)dwInitParam + 2) = 0;
  *((_QWORD *)dwInitParam + 3) = 0;
  *((_QWORD *)dwInitParam + 5) = 0;
  *((_DWORD *)dwInitParam + 8) = 1;
  ReplaceInterface<IOleClientSite>(dwInitParam + 40, a2);
  TopMostParent = GetTopMostParent(hWndParent);
  v7 = g_hLocRes;
  *((_QWORD *)dwInitParam + 3) = TopMostParent;
  if ( CreateDialogParamW(v7, (LPCWSTR)0x65, hWndParent, CViewSource::_ExtDlgProc, (LPARAM)dwInitParam) )
  {
    ShowWindow(*((HWND *)dwInitParam + 1), 5);
    v8 = 0;
  }
  else
  {
    v8 = -2147024882;
  }
  CViewSource::Release((CViewSource *)dwInitParam);
  return v8;
}

```

## disassembly

```asm
0x1800730c8  mov     [rsp+arg_0], rbx
0x1800730cd  mov     [rsp+arg_8], rsi
0x1800730d2  push    rdi
0x1800730d3  sub     rsp, 30h
0x1800730d7  cmp     cs:qword_1800F3378, 0
0x1800730df  mov     rsi, rdx
0x1800730e2  mov     rdi, rcx
0x1800730e5  jnz     short loc_18007310A
0x1800730e7  lea     rcx, aRiched32Dll; "riched32.dll"
0x1800730ee  call    cs:__imp_LoadLibraryA
0x1800730f4  mov     cs:qword_1800F3378, rax
0x1800730fb  test    rax, rax
0x1800730fe  jnz     short loc_18007310A
0x180073100  mov     eax, 800C1702h
0x180073105  jmp     loc_1800731C0
0x18007310a  mov     ecx, 38h ; '8'; Size
0x18007310f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180073114  mov     rbx, rax
0x180073117  test    rax, rax
0x18007311a  jz      loc_1800731BB
0x180073120  lea     rax, ??_7CViewSource@@6B@; const CViewSource::`vftable'
0x180073127  mov     [rbx], rax
0x18007312a  lock inc cs:?g_cRef@@3JA; long g_cRef
0x180073131  lea     rcx, [rbx+28h]
0x180073135  mov     qword ptr [rbx+8], 0
0x18007313d  mov     rdx, rsi
0x180073140  mov     qword ptr [rbx+10h], 0
0x180073148  mov     qword ptr [rbx+18h], 0
0x180073150  mov     qword ptr [rbx+28h], 0
0x180073158  mov     dword ptr [rbx+20h], 1
0x18007315f  call    ??$ReplaceInterface@UIOleClientSite@@@@YAXAEAPEAUIOleClientSite@@PEAU0@@Z; ReplaceInterface<IOleClientSite>(IOleClientSite * &,IOleClientSite *)
0x180073164  mov     rcx, rdi
0x180073167  call    cs:__imp_GetTopMostParent
0x18007316d  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x180073174  lea     r9, ?_ExtDlgProc@CViewSource@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18007317b  mov     r8, rdi; hWndParent
0x18007317e  mov     [rbx+18h], rax
0x180073182  mov     edx, 65h ; 'e'; lpTemplateName
0x180073187  mov     [rsp+38h+dwInitParam], rbx; dwInitParam
0x18007318c  call    cs:__imp_CreateDialogParamW
0x180073192  test    rax, rax
0x180073195  jz      short loc_1800731AA
0x180073197  mov     rcx, [rbx+8]; hWnd
0x18007319b  mov     edx, 5; nCmdShow
0x1800731a0  call    cs:__imp_ShowWindow
0x1800731a6  xor     edi, edi
0x1800731a8  jmp     short loc_1800731AF
0x1800731aa  mov     edi, 8007000Eh
0x1800731af  mov     rcx, rbx; this
0x1800731b2  call    ?Release@CViewSource@@AEAAKXZ; CViewSource::Release(void)
0x1800731b7  mov     eax, edi
0x1800731b9  jmp     short loc_1800731C0
0x1800731bb  mov     eax, 8007000Eh
0x1800731c0  mov     rbx, [rsp+38h+arg_0]
0x1800731c5  mov     rsi, [rsp+38h+arg_8]
0x1800731ca  add     rsp, 30h
0x1800731ce  pop     rdi
0x1800731cf  retn
```
