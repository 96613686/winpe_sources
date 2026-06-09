# RevokeDragDropImpl

- ea: `0x18000a254`
- end: `0x18000a398`
- name: `RevokeDragDropImpl`
- size: `324`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, IUnknown **ppRevoked)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000a190`
- `0x18008a62c`
- `0x180094810`

## callees

- `0x1800085a8`
- `0x18000a01c`
- `0x18000a254`
- `0x18000a70c`
- `0x18000a8f0`
- `0x18000d788`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a340`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a340`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000a32a`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000a32a`
- `USER32!IsWindow` at `0x18000a26b`
- `USER32!IsWindow` at `0x18000a26b`
- `USER32!GetPropW` at `0x18000a2b7`
- `USER32!GetPropW` at `0x18000a2b7`
- `USER32!RemovePropW` at `0x18000a289`
- `USER32!RemovePropW` at `0x18000a289`

## pseudocode

```c
__int64 __fastcall RevokeDragDropImpl(HWND__ *hwnd, IUnknown **ppRevoked)
{
  unsigned int v4; // ebx
  IDragDropExtensionForOLE *ptr; // rcx
  Microsoft::WRL::ComPtr<IDragDropExtensionForOLE> spExtension; // [rsp+30h] [rbp-10h] BYREF
  unsigned int dwAssignAptID; // [rsp+70h] [rbp+30h] BYREF
  unsigned int dwAssignPID; // [rsp+78h] [rbp+38h] BYREF

  v4 = 0;
  if ( IsWindow(hwnd) )
  {
    if ( RemovePropW(hwnd, (LPCWSTR)g_aDropTarget) )
    {
      if ( ppRevoked )
      {
        LODWORD(spExtension.ptr_) = 0;
        UnmarshalFromEndpointProperty(hwnd, 0, 1, ppRevoked, (int *)&spExtension);
      }
      dwAssignAptID = 0;
      dwAssignPID = 0;
      if ( GetPropW(hwnd, (LPCWSTR)g_aEndPointAtom) )
      {
        UnAssignEndpointProperty(hwnd, 1, &dwAssignAptID, &dwAssignPID);
        spExtension.ptr_ = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
        if ( (int)GetDragDropExtensionPoint((LPVOID *)&spExtension.ptr_) >= 0 )
          ((void (__fastcall *)(IDragDropExtensionForOLE *, HWND__ *))spExtension.ptr_->lpVtbl[1].AddRef)(
            spExtension.ptr_,
            hwnd);
        ptr = spExtension.ptr_;
        if ( spExtension.ptr_ )
        {
          spExtension.ptr_ = 0;
          ((void (__fastcall *)(IDragDropExtensionForOLE *))ptr->lpVtbl->Release)(ptr);
        }
      }
      GlobalDeleteAtom(g_aEndPointAtom);
      if ( dwAssignAptID != GetCurrentApartmentId() || dwAssignPID != GetCurrentProcessId() )
        return (unsigned int)-2147417842;
    }
    else
    {
      return (unsigned int)-2147221248;
    }
  }
  else
  {
    return (unsigned int)-2147221246;
  }
  return v4;
}

```

## disassembly

```asm
0x18000a254  mov     [rsp-18h+arg_0], rbx
0x18000a259  push    rbp
0x18000a25a  push    rsi
0x18000a25b  push    rdi
0x18000a25c  mov     rbp, rsp
0x18000a25f  sub     rsp, 40h
0x18000a263  mov     rsi, ppRevoked
0x18000a266  mov     rdi, hwnd
0x18000a269  xor     ebx, ebx
0x18000a26b  call    cs:__imp_IsWindow
0x18000a272  nop     dword ptr [rax+rax+00h]
0x18000a277  test    eax, eax
0x18000a279  jz      loc_18000A368
0x18000a27f  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000a286  mov     hwnd, rdi; hWnd
0x18000a289  call    cs:__imp_RemovePropW
0x18000a290  nop     dword ptr [rax+rax+00h]
0x18000a295  test    rax, rax
0x18000a298  jz      loc_18000A361
0x18000a29e  test    rsi, rsi
0x18000a2a1  jnz     loc_18000A36F
0x18000a2a7  movzx   edx, cs:?g_aEndPointAtom@@3GA; lpString
0x18000a2ae  mov     hwnd, rdi; hWnd
0x18000a2b1  mov     [rbp+dwAssignAptID], ebx
0x18000a2b4  mov     [rbp+dwAssignPID], ebx
0x18000a2b7  call    cs:__imp_GetPropW
0x18000a2be  nop     dword ptr [rax+rax+00h]
0x18000a2c3  test    rax, rax
0x18000a2c6  jz      short loc_18000A323
0x18000a2c8  lea     r9, [rbp+dwAssignPID]; dwAssignPID
0x18000a2cc  mov     edx, 1; fDragDrop
0x18000a2d1  lea     r8, [rbp+dwAssignAptID]; dwAssignAptID
0x18000a2d5  mov     hwnd, rdi; hWnd
0x18000a2d8  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18000a2dd  lea     hwnd, [rbp+spExtension]; this
0x18000a2e1  mov     [rbp+spExtension.ptr_], rbx
0x18000a2e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000a2ea  lea     hwnd, [rbp+spExtension]; ppExtension
0x18000a2ee  call    ?GetDragDropExtensionPoint@@YAJPEAPEAUIDragDropExtensionForOLE@@@Z; GetDragDropExtensionPoint(IDragDropExtensionForOLE * *)
0x18000a2f3  test    eax, eax
0x18000a2f5  js      short loc_18000A30A
0x18000a2f7  mov     hwnd, [rbp+spExtension.ptr_]
0x18000a2fb  mov     ppRevoked, rdi
0x18000a2fe  mov     rax, [hwnd]
0x18000a301  mov     rax, [rax+20h]
0x18000a305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a30a  mov     hwnd, [rbp+spExtension.ptr_]
0x18000a30e  test    hwnd, hwnd
0x18000a311  jz      short loc_18000A323
0x18000a313  mov     [rbp+spExtension.ptr_], rbx
0x18000a317  mov     rax, [hwnd]
0x18000a31a  mov     rax, [rax+10h]
0x18000a31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a323  movzx   ecx, cs:?g_aEndPointAtom@@3GA; nAtom
0x18000a32a  call    cs:__imp_GlobalDeleteAtom
0x18000a331  nop     dword ptr [rax+rax+00h]
0x18000a336  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x18000a33b  cmp     [rbp+dwAssignAptID], eax
0x18000a33e  jnz     short loc_18000A391
0x18000a340  call    cs:__imp_GetCurrentProcessId
0x18000a347  nop     dword ptr [rax+rax+00h]
0x18000a34c  cmp     [rbp+dwAssignPID], eax
0x18000a34f  jnz     short loc_18000A391
0x18000a351  mov     eax, ebx
0x18000a353  mov     rbx, [rsp+40h+arg_0]
0x18000a358  add     rsp, 40h
0x18000a35c  pop     rdi
0x18000a35d  pop     rsi
0x18000a35e  pop     rbp
0x18000a35f  retn
0x18000a361  mov     ebx, 80040100h
0x18000a366  jmp     short loc_18000A351
0x18000a368  mov     ebx, 80040102h
0x18000a36d  jmp     short loc_18000A351
0x18000a36f  xor     edx, edx; fDragDrop
0x18000a371  mov     dword ptr [rbp+spExtension.ptr_], ebx
0x18000a374  lea     rax, [rbp+spExtension]
0x18000a378  mov     r9, rsi; ppUnk
0x18000a37b  mov     hwnd, rdi; hWnd
0x18000a37e  mov     [rsp+40h+pfLocal], rax; pfLocal
0x18000a383  lea     r8d, [ppRevoked+1]; fCallStrongNamedProcesses
0x18000a387  call    ?UnmarshalFromEndpointProperty@@YAJPEAUHWND__@@HHPEAPEAUIUnknown@@PEAH@Z; UnmarshalFromEndpointProperty(HWND__ *,int,int,IUnknown * *,int *)
0x18000a38c  jmp     loc_18000A2A7
0x18000a391  mov     ebx, 8001010Eh
0x18000a396  jmp     short loc_18000A351
```
