# RevokeDragDropImpl

- ea: `0x18000b9bc`
- end: `0x18000bb4a`
- name: `RevokeDragDropImpl`
- size: `398`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, IUnknown **ppRevoked)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b900`
- `0x18008ecd0`
- `0x180095b20`

## callees

- `0x180008544`
- `0x18000a0e8`
- `0x18000b7a0`
- `0x18000b9bc`
- `0x18000fce0`
- `0x18000fecc`
- `0x180059088`
- `0x1800c3d9c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bb2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bb2b`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000bb19`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000bb19`
- `USER32!IsWindow` at `0x18000b9d1`
- `USER32!IsWindow` at `0x18000b9d1`
- `USER32!GetPropW` at `0x18000ba42`
- `USER32!GetPropW` at `0x18000ba42`
- `USER32!RemovePropW` at `0x18000b9ef`
- `USER32!RemovePropW` at `0x18000ba64`
- `USER32!RemovePropW` at `0x18000b9ef`
- `USER32!RemovePropW` at `0x18000ba64`
- `api-ms-win-core-com-private-l1-2-0!InternalRevokeWindowPropInterface` at `0x18000bad2`
- `api-ms-win-core-com-private-l1-2-0!InternalRevokeWindowPropInterface` at `0x18000bad2`

## pseudocode

```c
__int64 __fastcall RevokeDragDropImpl(HWND hwnd, IUnknown **ppRevoked)
{
  unsigned int v4; // ebx
  CEndPointAtom *v5; // rcx
  const wchar_t *PropPtr; // rax
  unsigned int function; // esi
  HANDLE v8; // rdi
  DWORD line; // eax
  const char *v10; // rcx
  TraceLevel v11; // r9d
  int *pfLocal; // [rsp+20h] [rbp-30h]
  Microsoft::WRL::ComPtr<IDragDropExtensionForOLE> spExtension; // [rsp+40h] [rbp-10h] BYREF
  unsigned int dwAssignAptID; // [rsp+80h] [rbp+30h] BYREF
  unsigned int dwAssignPID; // [rsp+88h] [rbp+38h] BYREF

  if ( !IsWindow(hwnd) )
    return (unsigned int)-2147221246;
  if ( !RemovePropW(hwnd, (LPCWSTR)g_aDropTarget) )
    return (unsigned int)-2147221248;
  if ( ppRevoked )
  {
    LODWORD(spExtension.ptr_) = 0;
    UnmarshalFromEndpointProperty(hwnd, 0, 1, ppRevoked, (int *)&spExtension);
  }
  dwAssignAptID = 0;
  dwAssignPID = 0;
  if ( GetPropW(hwnd, (LPCWSTR)g_aEndPointAtom) )
  {
    PropPtr = CEndPointAtom::GetPropPtr(v5);
    function = (unsigned int)PropPtr;
    if ( PropPtr )
    {
      v8 = RemovePropW(hwnd, PropPtr);
      if ( v8 )
      {
LABEL_16:
        InternalRevokeWindowPropInterface(
          hwnd,
          v8,
          &GUID_00000160_0000_0000_c000_000000000046,
          &dwAssignAptID,
          &dwAssignPID);
        spExtension.ptr_ = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
        if ( GetDragDropExtensionPoint(&spExtension.ptr_) >= 0 )
          ((void (__fastcall *)(IDragDropExtensionForOLE *, HWND))spExtension.ptr_->lpVtbl[1].AddRef)(
            spExtension.ptr_,
            hwnd);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<ITypeLibRegistrationReader> *)&spExtension);
        goto LABEL_19;
      }
    }
    else
    {
      v8 = 0;
    }
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      line = GetLastError();
      ComTraceMessageT<HWND__ *,unsigned int,unsigned long>(
        v10,
        "UnAssignEndpointProperty",
        397,
        v11,
        (const wchar_t *)pfLocal,
        hwnd,
        function,
        line);
    }
    goto LABEL_16;
  }
LABEL_19:
  GlobalDeleteAtom(g_aEndPointAtom);
  if ( dwAssignAptID != GetCurrentApartmentId() )
    return (unsigned int)-2147417842;
  v4 = 0;
  if ( dwAssignPID != GetCurrentProcessId() )
    return (unsigned int)-2147417842;
  return v4;
}

```

## disassembly

```asm
0x18000b9bc  mov     [rsp-18h+arg_0], rbx
0x18000b9c1  push    rbp
0x18000b9c2  push    rsi
0x18000b9c3  push    rdi
0x18000b9c4  mov     rbp, rsp
0x18000b9c7  sub     rsp, 50h
0x18000b9cb  mov     rdi, ppRevoked
0x18000b9ce  mov     rbx, hwnd
0x18000b9d1  call    cs:__imp_IsWindow
0x18000b9d7  test    eax, eax
0x18000b9d9  jnz     short loc_18000B9E5
0x18000b9db  mov     ebx, 80040102h
0x18000b9e0  jmp     loc_18000BB3B
0x18000b9e5  movzx   edx, cs:?g_aDropTarget@@3GA; lpString
0x18000b9ec  mov     hwnd, rbx; hWnd
0x18000b9ef  call    cs:__imp_RemovePropW
0x18000b9f5  test    rax, rax
0x18000b9f8  jnz     short loc_18000BA04
0x18000b9fa  mov     ebx, 80040100h
0x18000b9ff  jmp     loc_18000BB3B
0x18000ba04  test    rdi, rdi
0x18000ba07  jz      short loc_18000BA2A
0x18000ba09  xor     edx, edx; fDragDrop
0x18000ba0b  mov     dword ptr [rbp+spExtension.ptr_], 0
0x18000ba12  lea     rax, [rbp+spExtension]
0x18000ba16  mov     r9, rdi; ppUnk
0x18000ba19  mov     hwnd, rbx; hWnd
0x18000ba1c  mov     [rsp+50h+pfLocal], rax; <args_2>
0x18000ba21  lea     r8d, [ppRevoked+1]; fCallStrongNamedProcesses
0x18000ba25  call    ?UnmarshalFromEndpointProperty@@YAJPEAUHWND__@@HHPEAPEAUIUnknown@@PEAH@Z; UnmarshalFromEndpointProperty(HWND__ *,int,int,IUnknown * *,int *)
0x18000ba2a  movzx   edx, cs:?g_aEndPointAtom@@3GA; lpString
0x18000ba31  mov     hwnd, rbx; hWnd
0x18000ba34  mov     [rbp+dwAssignAptID], 0
0x18000ba3b  mov     [rbp+dwAssignPID], 0
0x18000ba42  call    cs:__imp_GetPropW
0x18000ba48  test    rax, rax
0x18000ba4b  jz      loc_18000BB12
0x18000ba51  call    ?GetPropPtr@CEndPointAtom@@QEAAPEBGXZ; CEndPointAtom::GetPropPtr(void)
0x18000ba56  mov     rsi, rax
0x18000ba59  test    rax, rax
0x18000ba5c  jz      short loc_18000BA74
0x18000ba5e  mov     ppRevoked, rax; lpString
0x18000ba61  mov     hwnd, rbx; hWnd
0x18000ba64  call    cs:__imp_RemovePropW
0x18000ba6a  mov     rdi, rax
0x18000ba6d  test    rax, rax
0x18000ba70  jnz     short loc_18000BAB8
0x18000ba72  jmp     short loc_18000BA76
0x18000ba74  xor     edi, edi
0x18000ba76  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18000ba7c  test    eax, eax
0x18000ba7e  jnz     short loc_18000BA93
0x18000ba80  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18000ba86  jz      short loc_18000BAB8
0x18000ba88  xor     ecx, ecx; level
0x18000ba8a  call    IsWppLevelEnabled
0x18000ba8f  test    al, al
0x18000ba91  jz      short loc_18000BAB8
0x18000ba93  call    cs:__imp_GetLastError
0x18000ba99  mov     [rsp+50h+line], eax; line
0x18000ba9d  mov     r8d, 18Dh; <args_0>
0x18000baa3  mov     [rsp+50h+function], esi; function
0x18000baa7  lea     ppRevoked, aUnassignendpoi; "UnAssignEndpointProperty"
0x18000baae  mov     [rsp+50h+file], rbx; file
0x18000bab3  call    ??$ComTraceMessageT@PEAUHWND__@@IK@@YAXPEBD0HW4TraceLevel@@PEBGPEAUHWND__@@IK@Z; ComTraceMessageT<HWND__ *,uint,ulong>(char const *,char const *,int,TraceLevel,ushort const *,HWND__ *,uint,ulong)
0x18000bab8  lea     rax, [rbp+dwAssignPID]
0x18000babc  mov     ppRevoked, rdi
0x18000babf  lea     r9, [rbp+dwAssignAptID]
0x18000bac3  mov     [rsp+50h+pfLocal], rax
0x18000bac8  lea     r8, _GUID_00000160_0000_0000_c000_000000000046
0x18000bacf  mov     hwnd, rbx
0x18000bad2  call    cs:__imp_InternalRevokeWindowPropInterface
0x18000bad8  lea     hwnd, [rbp+spExtension]; this
0x18000badc  mov     [rbp+spExtension.ptr_], 0
0x18000bae4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bae9  lea     hwnd, [rbp+spExtension]; ppExtension
0x18000baed  call    ?GetDragDropExtensionPoint@@YAJPEAPEAUIDragDropExtensionForOLE@@@Z; GetDragDropExtensionPoint(IDragDropExtensionForOLE * *)
0x18000baf2  test    eax, eax
0x18000baf4  js      short loc_18000BB09
0x18000baf6  mov     hwnd, [rbp+spExtension.ptr_]
0x18000bafa  mov     ppRevoked, rbx
0x18000bafd  mov     rax, [hwnd]
0x18000bb00  mov     rax, [rax+20h]
0x18000bb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb09  lea     hwnd, [rbp+spExtension]; this
0x18000bb0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000bb12  movzx   ecx, cs:?g_aEndPointAtom@@3GA; nAtom
0x18000bb19  call    cs:__imp_GlobalDeleteAtom
0x18000bb1f  call    ?GetCurrentApartmentId@@YAKXZ; GetCurrentApartmentId(void)
0x18000bb24  cmp     [rbp+dwAssignAptID], eax
0x18000bb27  jnz     short loc_18000BB36
0x18000bb29  xor     ebx, ebx
0x18000bb2b  call    cs:__imp_GetCurrentProcessId
0x18000bb31  cmp     [rbp+dwAssignPID], eax
0x18000bb34  jz      short loc_18000BB3B
0x18000bb36  mov     ebx, 8001010Eh
0x18000bb3b  mov     eax, ebx
0x18000bb3d  mov     rbx, [rsp+50h+arg_0]
0x18000bb42  add     rsp, 50h
0x18000bb46  pop     rdi
0x18000bb47  pop     rsi
0x18000bb48  pop     rbp
0x18000bb49  retn
```
