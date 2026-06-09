# CDDEServer::Create(ushort *,_GUID const &,_tagDdeClassInfo *,HWND__ * *,ushort,CNVTYP)

- ea: `0x18007adf0`
- end: `0x18007afb9`
- name: `?Create@CDDEServer@@SAJPEAGAEBU_GUID@@PEAU_tagDdeClassInfo@@PEAPEAUHWND__@@GW4CNVTYP@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(wchar_t *lpclass, const _GUID *rclsid, _tagDdeClassInfo *lpDdeInfo, HWND__ **phwnd, unsigned __int16 aOriginalClass, unsigned int cnvtyp)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007d9c8`

## callees

- `0x180052760`
- `0x180077a18`
- `0x180077cc8`
- `0x18007ac5c`
- `0x18007adf0`
- `0x18007c0f4`
- `0x18007c13c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ae39`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007ae39`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007af85`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007af94`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007af85`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007af94`
- `USER32!SetWindowLongPtrW` at `0x18007af23`
- `USER32!SetWindowLongPtrW` at `0x18007af47`
- `USER32!SetWindowLongPtrW` at `0x18007af23`
- `USER32!SetWindowLongPtrW` at `0x18007af47`
- `USER32!CreateWindowExW` at `0x18007af05`
- `USER32!CreateWindowExW` at `0x18007af05`
- `USER32!SetWindowWord` at `0x18007af5c`
- `USER32!SetWindowWord` at `0x18007af5c`
- `USER32!DestroyWindow` at `0x18007af76`
- `USER32!DestroyWindow` at `0x18007af76`
- `api-ms-win-core-com-private-l1-1-0!InternalCCSetDdeServerWindow` at `0x18007af34`
- `api-ms-win-core-com-private-l1-1-0!InternalCCSetDdeServerWindow` at `0x18007af34`

## pseudocode

```c
__int64 __fastcall CDDEServer::Create(
        wchar_t *lpclass,
        const _GUID *rclsid,
        _tagDdeClassInfo *lpDdeInfo,
        HWND__ **phwnd,
        unsigned __int16 aOriginalClass,
        unsigned int cnvtyp)
{
  CDDEServer *v11; // rax
  unsigned int *v12; // rax
  unsigned int *v13; // rdi
  unsigned __int16 v14; // ax
  HINSTANCE hInstance; // rbx
  HWND hWndParent; // rax
  HWND Window; // rax
  __int64 v18; // rcx
  HWND v19; // rcx
  ATOM v20; // cx
  ATOM v21; // cx
  unsigned __int16 aExe[36]; // [rsp+60h] [rbp-48h] BYREF

  aExe[0] = 0;
  if ( !ValidateSrvrClass(lpclass, aExe) )
    return 2147746132LL;
  v11 = (CDDEServer *)HeapAlloc(g_hHeap, 0, 0x80u);
  if ( v11 )
  {
    CDDEServer::CDDEServer(v11);
    v13 = v12;
    if ( v12 )
    {
      v12[28] = 4660;
      *((_WORD *)v12 + 58) = wGlobalAddAtom(lpclass);
      *(_GUID *)v13 = *rclsid;
      v14 = wDupAtom(aOriginalClass);
      hInstance = g_hinst;
      *((_WORD *)v13 + 59) = v14;
      *((_QWORD *)v13 + 3) = 0;
      v13[4] = lpDdeInfo->dwRegistrationKey;
      *((_WORD *)v13 + 60) = aExe[0];
      v13[27] = cnvtyp;
      v13[26] = lpDdeInfo->dwFlags;
      v13[18] = 0;
      *((_QWORD *)v13 + 11) = 0;
      *((_QWORD *)v13 + 12) = 0;
      v13[31] = 0;
      hWndParent = TLSGetDdeServer();
      Window = CreateWindowExW(
                 0,
                 gOleDdeWindowClass,
                 L"CDDEServer",
                 0x40000000u,
                 0,
                 0,
                 0,
                 0,
                 hWndParent,
                 0,
                 hInstance,
                 0);
      *((_QWORD *)v13 + 10) = Window;
      if ( Window )
      {
        SetWindowLongPtrW(Window, -4, (LONG_PTR)SrvrWndProc);
        v18 = v13[4];
        if ( !(_DWORD)v18 || (unsigned int)InternalCCSetDdeServerWindow(v18, *((_QWORD *)v13 + 10)) )
        {
          SetWindowLongPtrW(*((HWND *)v13 + 10), 0, (LONG_PTR)v13);
          SetWindowWord(*((HWND *)v13 + 10), 8, 0x4C45u);
          *phwnd = (HWND__ *)*((_QWORD *)v13 + 10);
          return 0;
        }
      }
      v19 = (HWND)*((_QWORD *)v13 + 10);
      if ( v19 )
        DestroyWindow(v19);
      v20 = *((_WORD *)v13 + 58);
      if ( v20 )
        GlobalDeleteAtom(v20);
      v21 = *((_WORD *)v13 + 60);
      if ( v21 )
        GlobalDeleteAtom(v21);
      operator delete(v13, 0x80u);
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18007adf0  push    rbx
0x18007adf2  push    rbp
0x18007adf3  push    rsi
0x18007adf4  push    rdi
0x18007adf5  push    r14
0x18007adf7  push    r15
0x18007adf9  sub     rsp, 78h
0x18007adfd  mov     r14, rclsid
0x18007ae00  xor     r15d, r15d
0x18007ae03  lea     rclsid, [rsp+0A8h+aExe]; lpAtom
0x18007ae08  mov     [rsp+0A8h+aExe], r15w
0x18007ae0e  mov     rsi, phwnd
0x18007ae11  mov     rbp, lpDdeInfo
0x18007ae14  mov     rbx, lpclass
0x18007ae17  call    ?ValidateSrvrClass@@YAHPEAG0@Z; ValidateSrvrClass(ushort *,ushort *)
0x18007ae1c  test    eax, eax
0x18007ae1e  jnz     short loc_18007AE2A
0x18007ae20  mov     eax, 80040154h
0x18007ae25  jmp     loc_18007AFAC
0x18007ae2a  mov     lpclass, cs:?g_hHeap@@3QEAXEA; hHeap
0x18007ae31  xor     edx, edx; dwFlags
0x18007ae33  mov     r8d, 80h; dwBytes
0x18007ae39  call    cs:__imp_HeapAlloc
0x18007ae3f  test    rax, rax
0x18007ae42  jz      loc_18007AFA7
0x18007ae48  mov     lpclass, rax; this
0x18007ae4b  call    ??0CDDEServer@@QEAA@XZ; CDDEServer::CDDEServer(void)
0x18007ae50  mov     rdi, rax
0x18007ae53  test    rax, rax
0x18007ae56  jz      loc_18007AFA7
0x18007ae5c  mov     lpclass, rbx; sz
0x18007ae5f  mov     dword ptr [rax+70h], 1234h
0x18007ae66  call    ?wGlobalAddAtom@@YAGPEBG@Z; wGlobalAddAtom(ushort const *)
0x18007ae6b  movzx   ecx, [rsp+0A8h+arg_20]; a
0x18007ae73  mov     [rdi+74h], ax
0x18007ae77  movups  xmm0, xmmword ptr [r14]
0x18007ae7b  movdqu  xmmword ptr [rdi], xmm0
0x18007ae7f  call    ?wDupAtom@@YAGG@Z; wDupAtom(ushort)
0x18007ae84  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18007ae8b  mov     [rdi+76h], ax
0x18007ae8f  mov     [rdi+18h], r15
0x18007ae93  mov     eax, [rbp+14h]
0x18007ae96  mov     [rdi+10h], eax
0x18007ae99  movzx   eax, [rsp+0A8h+aExe]
0x18007ae9e  mov     [rdi+78h], ax
0x18007aea2  mov     eax, [rsp+0A8h+arg_28]
0x18007aea9  mov     [rdi+6Ch], eax
0x18007aeac  mov     eax, [rbp+0Ch]
0x18007aeaf  mov     [rdi+68h], eax
0x18007aeb2  mov     [rdi+48h], r15d
0x18007aeb6  mov     [rdi+58h], r15
0x18007aeba  mov     [rdi+60h], r15
0x18007aebe  mov     [rdi+7Ch], r15d
0x18007aec2  call    ?TLSGetDdeServer@@YAPEAUHWND__@@XZ; TLSGetDdeServer(void)
0x18007aec7  mov     rclsid, cs:?gOleDdeWindowClass@@3PEAGEA; lpClassName
0x18007aece  lea     lpDdeInfo, aCddeserver; "CDDEServer"
0x18007aed5  mov     [rsp+0A8h+lpParam], r15; lpParam
0x18007aeda  mov     r9d, 40000000h; dwStyle
0x18007aee0  mov     [rsp+0A8h+hInstance], rbx; hInstance
0x18007aee5  xor     ecx, ecx; dwExStyle
0x18007aee7  mov     [rsp+0A8h+hMenu], r15; hMenu
0x18007aeec  mov     [rsp+0A8h+hWndParent], rax; hWndParent
0x18007aef1  mov     [rsp+0A8h+nHeight], r15d; nHeight
0x18007aef6  mov     [rsp+0A8h+nWidth], r15d; nWidth
0x18007aefb  mov     [rsp+0A8h+Y], r15d; Y
0x18007af00  mov     [rsp+0A8h+X], r15d; X
0x18007af05  call    cs:__imp_CreateWindowExW
0x18007af0b  mov     [rdi+50h], rax
0x18007af0f  test    rax, rax
0x18007af12  jz      short $errReturn
0x18007af14  lea     lpDdeInfo, SrvrWndProc; dwNewLong
0x18007af1b  mov     edx, 0FFFFFFFCh; nIndex
0x18007af20  mov     lpclass, rax; hWnd
0x18007af23  call    cs:__imp_SetWindowLongPtrW
0x18007af29  mov     ecx, [rdi+10h]
0x18007af2c  test    ecx, ecx
0x18007af2e  jz      short loc_18007AF3E
0x18007af30  mov     rclsid, [rdi+50h]
0x18007af34  call    cs:__imp_InternalCCSetDdeServerWindow
0x18007af3a  test    eax, eax
0x18007af3c  jz      short $errReturn
0x18007af3e  mov     lpclass, [rdi+50h]; hWnd
0x18007af42  mov     lpDdeInfo, rdi; dwNewLong
0x18007af45  xor     edx, edx; nIndex
0x18007af47  call    cs:__imp_SetWindowLongPtrW
0x18007af4d  mov     lpclass, [rdi+50h]; hWnd
0x18007af51  mov     edx, 8; nIndex
0x18007af56  mov     r8d, 4C45h; wNewWord
0x18007af5c  call    cs:__imp_SetWindowWord
0x18007af62  mov     rax, [rdi+50h]
0x18007af66  mov     [rsi], rax
0x18007af69  xor     eax, eax
0x18007af6b  jmp     short loc_18007AFAC
0x18007af6d  mov     lpclass, [rdi+50h]; hWnd
0x18007af71  test    lpclass, lpclass
0x18007af74  jz      short loc_18007AF7C
0x18007af76  call    cs:__imp_DestroyWindow
0x18007af7c  movzx   ecx, word ptr [rdi+74h]; nAtom
0x18007af80  test    cx, cx
0x18007af83  jz      short loc_18007AF8B
0x18007af85  call    cs:__imp_GlobalDeleteAtom
0x18007af8b  movzx   ecx, word ptr [rdi+78h]; nAtom
0x18007af8f  test    cx, cx
0x18007af92  jz      short loc_18007AF9A
0x18007af94  call    cs:__imp_GlobalDeleteAtom
0x18007af9a  mov     edx, 80h; __formal
0x18007af9f  mov     lpclass, rdi; block
0x18007afa2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007afa7  mov     eax, 8007000Eh
0x18007afac  add     rsp, 78h
0x18007afb0  pop     r15
0x18007afb2  pop     r14
0x18007afb4  pop     rdi
0x18007afb5  pop     rsi
0x18007afb6  pop     rbp
0x18007afb7  pop     rbx
0x18007afb8  retn
```
