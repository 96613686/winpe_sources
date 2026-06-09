# AtlAxCreateDialogW

- ea: `0x14001916c`
- end: `0x1400192b0`
- name: `AtlAxCreateDialogW`
- size: `324`
- prototype: `__int64 __fastcall(HINSTANCE hInstance, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140016bd4`

## callees

- `0x140017988`
- `0x14001916c`
- `0x1400192b8`

## import_xrefs

- `KERNEL32!GlobalHandle` at `0x140019266`
- `KERNEL32!GlobalHandle` at `0x140019266`
- `KERNEL32!GlobalFree` at `0x140019275`
- `KERNEL32!GlobalFree` at `0x140019275`
- `KERNEL32!LockResource` at `0x1400191da`
- `KERNEL32!LockResource` at `0x140019204`
- `KERNEL32!LockResource` at `0x1400191da`
- `KERNEL32!LockResource` at `0x140019204`
- `KERNEL32!LoadResource` at `0x1400191cb`
- `KERNEL32!LoadResource` at `0x1400191ec`
- `KERNEL32!LoadResource` at `0x1400191cb`
- `KERNEL32!LoadResource` at `0x1400191ec`
- `KERNEL32!FindResourceExW` at `0x14001918e`
- `KERNEL32!FindResourceExW` at `0x1400191b4`
- `KERNEL32!FindResourceExW` at `0x14001918e`
- `KERNEL32!FindResourceExW` at `0x1400191b4`
- `KERNEL32!SetLastError` at `0x140019297`
- `KERNEL32!SetLastError` at `0x140019297`
- `KERNEL32!GetLastError` at `0x140019250`
- `KERNEL32!GetLastError` at `0x140019283`
- `KERNEL32!GetLastError` at `0x140019250`
- `KERNEL32!GetLastError` at `0x140019283`
- `USER32!CreateDialogIndirectParamW` at `0x140019238`
- `USER32!CreateDialogIndirectParamW` at `0x140019238`

## pseudocode

```c
HWND __fastcall AtlAxCreateDialogW(HINSTANCE hInstance, LPCWSTR lpName)
{
  HWND DialogIndirectParamW; // rbp
  HRSRC Resource; // rdi
  HRSRC v6; // rax
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax
  struct DLGTEMPLATE *v9; // rax
  unsigned __int8 *v10; // rdx
  struct DLGTEMPLATE *v11; // rdi
  const DLGTEMPLATE *v12; // rsi
  DWORD LastError; // ebx
  HGLOBAL v14; // rax

  AtlAxWinInit();
  DialogIndirectParamW = 0;
  Resource = FindResourceExW(hInstance, (LPCWSTR)5, lpName, 0);
  if ( Resource )
  {
    v6 = FindResourceExW(hInstance, (LPCWSTR)0xF0, lpName, 0);
    if ( v6 )
    {
      v7 = LoadResource(hInstance, v6);
      LockResource(v7);
    }
    v8 = LoadResource(hInstance, Resource);
    if ( v8 && (v9 = (struct DLGTEMPLATE *)LockResource(v8), (v11 = v9) != 0) )
    {
      v12 = ATL::_DialogSplitHelper::SplitDialogTemplate(v9, v10);
      DialogIndirectParamW = CreateDialogIndirectParamW(
                               hInstance,
                               v12,
                               0,
                               ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc,
                               0);
      if ( DialogIndirectParamW )
        LastError = 0;
      else
        LastError = GetLastError();
      if ( v12 != v11 )
      {
        v14 = GlobalHandle(v12);
        GlobalFree(v14);
      }
    }
    else
    {
      LastError = GetLastError();
    }
    if ( LastError )
      SetLastError(LastError);
  }
  return DialogIndirectParamW;
}

```

## disassembly

```asm
0x14001916c  push    rbx
0x14001916e  push    rbp
0x14001916f  push    rsi
0x140019170  push    rdi
0x140019171  sub     rsp, 38h
0x140019175  mov     rsi, rdx
0x140019178  mov     rbx, rcx
0x14001917b  call    AtlAxWinInit
0x140019180  xor     ebp, ebp
0x140019182  xor     r9d, r9d; wLanguage
0x140019185  mov     r8, rsi; lpName
0x140019188  mov     rcx, rbx; hModule
0x14001918b  lea     edx, [rbp+5]; lpType
0x14001918e  call    cs:__imp_FindResourceExW
0x140019195  nop     dword ptr [rax+rax+00h]
0x14001919a  mov     rdi, rax
0x14001919d  test    rax, rax
0x1400191a0  jz      loc_1400192A3
0x1400191a6  xor     r9d, r9d; wLanguage
0x1400191a9  mov     r8, rsi; lpName
0x1400191ac  mov     edx, 0F0h; lpType
0x1400191b1  mov     rcx, rbx; hModule
0x1400191b4  call    cs:__imp_FindResourceExW
0x1400191bb  nop     dword ptr [rax+rax+00h]
0x1400191c0  test    rax, rax
0x1400191c3  jz      short loc_1400191E6
0x1400191c5  mov     rdx, rax; hResInfo
0x1400191c8  mov     rcx, rbx; hModule
0x1400191cb  call    cs:__imp_LoadResource
0x1400191d2  nop     dword ptr [rax+rax+00h]
0x1400191d7  mov     rcx, rax; hResData
0x1400191da  call    cs:__imp_LockResource
0x1400191e1  nop     dword ptr [rax+rax+00h]
0x1400191e6  mov     rdx, rdi; hResInfo
0x1400191e9  mov     rcx, rbx; hModule
0x1400191ec  call    cs:__imp_LoadResource
0x1400191f3  nop     dword ptr [rax+rax+00h]
0x1400191f8  test    rax, rax
0x1400191fb  jz      loc_140019283
0x140019201  mov     rcx, rax; hResData
0x140019204  call    cs:__imp_LockResource
0x14001920b  nop     dword ptr [rax+rax+00h]
0x140019210  mov     rdi, rax
0x140019213  test    rax, rax
0x140019216  jz      short loc_140019283
0x140019218  mov     rcx, rax; Source
0x14001921b  call    ?SplitDialogTemplate@_DialogSplitHelper@ATL@@SAPEAUDLGTEMPLATE@@PEAU3@PEAE@Z; ATL::_DialogSplitHelper::SplitDialogTemplate(DLGTEMPLATE *,uchar *)
0x140019220  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x140019227  mov     [rsp+58h+dwInitParam], rbp; dwInitParam
0x14001922c  xor     r8d, r8d; hWndParent
0x14001922f  mov     rdx, rax; lpTemplate
0x140019232  mov     rcx, rbx; hInstance
0x140019235  mov     rsi, rax
0x140019238  call    cs:__imp_CreateDialogIndirectParamW
0x14001923f  nop     dword ptr [rax+rax+00h]
0x140019244  mov     rbp, rax
0x140019247  test    rax, rax
0x14001924a  jz      short loc_140019250
0x14001924c  xor     ebx, ebx
0x14001924e  jmp     short loc_14001925E
0x140019250  call    cs:__imp_GetLastError
0x140019257  nop     dword ptr [rax+rax+00h]
0x14001925c  mov     ebx, eax
0x14001925e  cmp     rsi, rdi
0x140019261  jz      short loc_140019291
0x140019263  mov     rcx, rsi; pMem
0x140019266  call    cs:__imp_GlobalHandle
0x14001926d  nop     dword ptr [rax+rax+00h]
0x140019272  mov     rcx, rax; hMem
0x140019275  call    cs:__imp_GlobalFree
0x14001927c  nop     dword ptr [rax+rax+00h]
0x140019281  jmp     short loc_140019291
0x140019283  call    cs:__imp_GetLastError
0x14001928a  nop     dword ptr [rax+rax+00h]
0x14001928f  mov     ebx, eax
0x140019291  test    ebx, ebx
0x140019293  jz      short loc_1400192A3
0x140019295  mov     ecx, ebx; dwErrCode
0x140019297  call    cs:__imp_SetLastError
0x14001929e  nop     dword ptr [rax+rax+00h]
0x1400192a3  mov     rax, rbp
0x1400192a6  add     rsp, 38h
0x1400192aa  pop     rdi
0x1400192ab  pop     rsi
0x1400192ac  pop     rbp
0x1400192ad  pop     rbx
0x1400192ae  retn
```
