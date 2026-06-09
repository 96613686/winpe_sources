# CDDEServer::Create(ushort *,_GUID const &,_tagDdeClassInfo *,HWND__ * *,ushort,CNVTYP)

- ea: `0x180073cd0`
- end: `0x180073ee6`
- name: `?Create@CDDEServer@@SAJPEAGAEBU_GUID@@PEAU_tagDdeClassInfo@@PEAPEAUHWND__@@GW4CNVTYP@@@Z`
- size: `534`
- prototype: `HRESULT __fastcall(wchar_t *lpclass, const _GUID *rclsid, _tagDdeClassInfo *lpDdeInfo, HWND__ **phwnd, unsigned __int16 aOriginalClass, CNVTYP cnvtyp)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180076cd4`

## callees

- `0x180046854`
- `0x18007021c`
- `0x180070514`
- `0x180073afc`
- `0x180073cd0`
- `0x1800751cc`
- `0x18007521c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180073d22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180073d22`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073e98`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073ead`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073e98`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180073ead`
- `USER32!SetWindowLongPtrW` at `0x180073e18`
- `USER32!SetWindowLongPtrW` at `0x180073e48`
- `USER32!SetWindowLongPtrW` at `0x180073e18`
- `USER32!SetWindowLongPtrW` at `0x180073e48`
- `USER32!CreateWindowExW` at `0x180073df4`
- `USER32!CreateWindowExW` at `0x180073df4`
- `USER32!SetWindowWord` at `0x180073e63`
- `USER32!SetWindowWord` at `0x180073e63`
- `USER32!DestroyWindow` at `0x180073e83`
- `USER32!DestroyWindow` at `0x180073e83`
- `api-ms-win-core-com-private-l1-1-0!InternalCCSetDdeServerWindow` at `0x180073e2f`
- `api-ms-win-core-com-private-l1-1-0!InternalCCSetDdeServerWindow` at `0x180073e2f`

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
  unsigned __int16 aExe[8]; // [rsp+60h] [rbp-28h] BYREF

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
0x180073cd0  mov     rax, rsp
0x180073cd3  mov     [rax+8], rbx
0x180073cd7  mov     [rax+10h], rbp
0x180073cdb  mov     [rax+18h], rsi
0x180073cdf  push    rdi
0x180073ce0  push    r14
0x180073ce2  push    r15
0x180073ce4  sub     rsp, 70h
0x180073ce8  mov     r14, rclsid
0x180073ceb  xor     r15d, r15d
0x180073cee  lea     rclsid, [rax-28h]; lpAtom
0x180073cf2  mov     [rax-28h], r15w
0x180073cf7  mov     rsi, phwnd
0x180073cfa  mov     rbp, lpDdeInfo
0x180073cfd  mov     rbx, lpclass
0x180073d00  call    ?ValidateSrvrClass@@YAHPEAG0@Z; ValidateSrvrClass(ushort *,ushort *)
0x180073d05  test    eax, eax
0x180073d07  jnz     short loc_180073D13
0x180073d09  mov     eax, 80040154h
0x180073d0e  jmp     loc_180073ECB
0x180073d13  mov     lpclass, cs:?g_hHeap@@3QEAXEA; hHeap
0x180073d1a  xor     edx, edx; dwFlags
0x180073d1c  mov     r8d, 80h; dwBytes
0x180073d22  call    cs:__imp_HeapAlloc
0x180073d29  nop     dword ptr [rax+rax+00h]
0x180073d2e  test    rax, rax
0x180073d31  jz      loc_180073EC6
0x180073d37  mov     lpclass, rax; this
0x180073d3a  call    ??0CDDEServer@@QEAA@XZ; CDDEServer::CDDEServer(void)
0x180073d3f  mov     rdi, rax
0x180073d42  test    rax, rax
0x180073d45  jz      loc_180073EC6
0x180073d4b  mov     lpclass, rbx; sz
0x180073d4e  mov     dword ptr [rax+70h], 1234h
0x180073d55  call    ?wGlobalAddAtom@@YAGPEBG@Z; wGlobalAddAtom(ushort const *)
0x180073d5a  movzx   ecx, [rsp+88h+arg_20]; a
0x180073d62  mov     [rdi+74h], ax
0x180073d66  movups  xmm0, xmmword ptr [r14]
0x180073d6a  movdqu  xmmword ptr [rdi], xmm0
0x180073d6e  call    ?wDupAtom@@YAGG@Z; wDupAtom(ushort)
0x180073d73  mov     rbx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180073d7a  mov     [rdi+76h], ax
0x180073d7e  mov     [rdi+18h], r15
0x180073d82  mov     eax, [rbp+14h]
0x180073d85  mov     [rdi+10h], eax
0x180073d88  movzx   eax, [rsp+88h+aExe]
0x180073d8d  mov     [rdi+78h], ax
0x180073d91  mov     eax, [rsp+88h+arg_28]
0x180073d98  mov     [rdi+6Ch], eax
0x180073d9b  mov     eax, [rbp+0Ch]
0x180073d9e  mov     [rdi+68h], eax
0x180073da1  mov     [rdi+48h], r15d
0x180073da5  mov     [rdi+58h], r15
0x180073da9  mov     [rdi+60h], r15
0x180073dad  mov     [rdi+7Ch], r15d
0x180073db1  call    ?TLSGetDdeServer@@YAPEAUHWND__@@XZ; TLSGetDdeServer(void)
0x180073db6  mov     rclsid, cs:?gOleDdeWindowClass@@3PEAGEA; lpClassName
0x180073dbd  lea     lpDdeInfo, aCddeserver; "CDDEServer"
0x180073dc4  mov     [rsp+88h+lpParam], r15; lpParam
0x180073dc9  mov     r9d, 40000000h; dwStyle
0x180073dcf  mov     [rsp+88h+hInstance], rbx; hInstance
0x180073dd4  xor     ecx, ecx; dwExStyle
0x180073dd6  mov     [rsp+88h+hMenu], r15; hMenu
0x180073ddb  mov     [rsp+88h+hWndParent], rax; hWndParent
0x180073de0  mov     [rsp+88h+nHeight], r15d; nHeight
0x180073de5  mov     [rsp+88h+nWidth], r15d; nWidth
0x180073dea  mov     [rsp+88h+Y], r15d; Y
0x180073def  mov     [rsp+88h+X], r15d; X
0x180073df4  call    cs:__imp_CreateWindowExW
0x180073dfb  nop     dword ptr [rax+rax+00h]
0x180073e00  mov     [rdi+50h], rax
0x180073e04  test    rax, rax
0x180073e07  jz      short $errReturn
0x180073e09  lea     lpDdeInfo, SrvrWndProc; dwNewLong
0x180073e10  mov     edx, 0FFFFFFFCh; nIndex
0x180073e15  mov     lpclass, rax; hWnd
0x180073e18  call    cs:__imp_SetWindowLongPtrW
0x180073e1f  nop     dword ptr [rax+rax+00h]
0x180073e24  mov     ecx, [rdi+10h]
0x180073e27  test    ecx, ecx
0x180073e29  jz      short loc_180073E3F
0x180073e2b  mov     rclsid, [rdi+50h]
0x180073e2f  call    cs:__imp_InternalCCSetDdeServerWindow
0x180073e36  nop     dword ptr [rax+rax+00h]
0x180073e3b  test    eax, eax
0x180073e3d  jz      short $errReturn
0x180073e3f  mov     lpclass, [rdi+50h]; hWnd
0x180073e43  mov     lpDdeInfo, rdi; dwNewLong
0x180073e46  xor     edx, edx; nIndex
0x180073e48  call    cs:__imp_SetWindowLongPtrW
0x180073e4f  nop     dword ptr [rax+rax+00h]
0x180073e54  mov     lpclass, [rdi+50h]; hWnd
0x180073e58  mov     edx, 8; nIndex
0x180073e5d  mov     r8d, 4C45h; wNewWord
0x180073e63  call    cs:__imp_SetWindowWord
0x180073e6a  nop     dword ptr [rax+rax+00h]
0x180073e6f  mov     rax, [rdi+50h]
0x180073e73  mov     [rsi], rax
0x180073e76  xor     eax, eax
0x180073e78  jmp     short loc_180073ECB
0x180073e7a  mov     lpclass, [rdi+50h]; hWnd
0x180073e7e  test    lpclass, lpclass
0x180073e81  jz      short loc_180073E8F
0x180073e83  call    cs:__imp_DestroyWindow
0x180073e8a  nop     dword ptr [rax+rax+00h]
0x180073e8f  movzx   ecx, word ptr [rdi+74h]; nAtom
0x180073e93  test    cx, cx
0x180073e96  jz      short loc_180073EA4
0x180073e98  call    cs:__imp_GlobalDeleteAtom
0x180073e9f  nop     dword ptr [rax+rax+00h]
0x180073ea4  movzx   ecx, word ptr [rdi+78h]; nAtom
0x180073ea8  test    cx, cx
0x180073eab  jz      short loc_180073EB9
0x180073ead  call    cs:__imp_GlobalDeleteAtom
0x180073eb4  nop     dword ptr [rax+rax+00h]
0x180073eb9  mov     edx, 80h; __formal
0x180073ebe  mov     lpclass, rdi; block
0x180073ec1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180073ec6  mov     eax, 8007000Eh
0x180073ecb  lea     r11, [rsp+88h+var_18]
0x180073ed0  mov     rbx, [r11+20h]
0x180073ed4  mov     rbp, [r11+28h]
0x180073ed8  mov     rsi, [r11+30h]
0x180073edc  mov     rsp, r11
0x180073edf  pop     r15
0x180073ee1  pop     r14
0x180073ee3  pop     rdi
0x180073ee4  retn
```
