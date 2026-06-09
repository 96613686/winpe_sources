# SetClipboardDataObject(HWND__ *,IDataObject *,IDataObject *,void * *)

- ea: `0x1800110e0`
- end: `0x18001132a`
- name: `?SetClipboardDataObject@@YAJPEAUHWND__@@PEAUIDataObject@@1PEAPEAX@Z`
- size: `586`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, IDataObject *pDataObject, IDataObject *pSourceDataObject, void **ppDataObjectMTAAddress)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000f900`

## callees

- `0x18000fecc`
- `0x1800110e0`
- `0x18002570c`
- `0x1800323f0`
- `0x180042188`
- `0x180059088`
- `0x1800c3d9c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011281`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800111d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011281`
- `USER32!RemovePropW` at `0x1800111a8`
- `USER32!RemovePropW` at `0x180011205`
- `USER32!RemovePropW` at `0x180011252`
- `USER32!RemovePropW` at `0x1800112d1`
- `USER32!RemovePropW` at `0x1800112e1`
- `USER32!RemovePropW` at `0x1800111a8`
- `USER32!RemovePropW` at `0x180011205`
- `USER32!RemovePropW` at `0x180011252`
- `USER32!RemovePropW` at `0x1800112d1`
- `USER32!RemovePropW` at `0x1800112e1`
- `USER32!SetPropW` at `0x18001112a`
- `USER32!SetPropW` at `0x18001116d`
- `USER32!SetPropW` at `0x1800111ca`
- `USER32!SetPropW` at `0x18001112a`
- `USER32!SetPropW` at `0x18001116d`
- `USER32!SetPropW` at `0x1800111ca`
- `api-ms-win-core-com-private-l1-2-0!InternalRevokeWindowPropInterface` at `0x1800112c1`
- `api-ms-win-core-com-private-l1-2-0!InternalRevokeWindowPropInterface` at `0x1800112c1`

## pseudocode

```c
__int64 __fastcall SetClipboardDataObject(
        HWND__ *hClipWnd,
        IDataObject *pDataObject,
        IDataObject *pSourceDataObject,
        void **ppDataObjectMTAAddress)
{
  unsigned int v8; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  const wchar_t *v11; // rdx
  HWND v12; // rcx
  signed int v13; // eax
  CEndPointAtom *v14; // rcx
  HWND__ *file; // rsi
  const wchar_t *PropPtr; // rax
  unsigned int function; // r14d
  HANDLE v18; // rdi
  DWORD line; // eax
  const char *v20; // rcx
  TraceLevel v21; // r9d
  const wchar_t *v23; // [rsp+20h] [rbp-38h]
  unsigned int dwAssignPID; // [rsp+40h] [rbp-18h] BYREF
  unsigned int dwAssignAptID[5]; // [rsp+44h] [rbp-14h] BYREF
  HWND__ *pData; // [rsp+90h] [rbp+38h] BYREF

  pData = hClipWnd;
  dwAssignAptID[0] = 0;
  dwAssignPID = 0;
  v8 = AssignClipboardEndpointProperty(hClipWnd);
  if ( v8 )
    return v8;
  if ( !SetPropW(hClipWnd, L"ClipboardDataObjectInterface", pDataObject) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    UnAssignEndpointProperty(hClipWnd, 0, dwAssignAptID, &dwAssignPID);
    return v8;
  }
  if ( !SetPropW(hClipWnd, L"ClipboardRootDataObjectInterface", pSourceDataObject) )
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    UnAssignEndpointProperty(hClipWnd, 0, dwAssignAptID, &dwAssignPID);
    v11 = L"ClipboardDataObjectInterface";
LABEL_10:
    v12 = hClipWnd;
LABEL_11:
    RemovePropW(v12, v11);
    return v8;
  }
  if ( ppDataObjectMTAAddress && *ppDataObjectMTAAddress )
  {
    if ( !SetPropW(hClipWnd, L"ClipboardDataObjectInterfaceMTA", *ppDataObjectMTAAddress) )
    {
      v13 = GetLastError();
      v8 = v13;
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
      UnAssignEndpointProperty(hClipWnd, 0, dwAssignAptID, &dwAssignPID);
      RemovePropW(hClipWnd, L"ClipboardDataObjectInterface");
      v11 = L"ClipboardRootDataObjectInterface";
      goto LABEL_10;
    }
    *ppDataObjectMTAAddress = 0;
  }
  v8 = SetFormatAsHGlobal(g_cfDataObject, &pData, 8u);
  if ( (v8 & 0x80000000) != 0 )
  {
    file = pData;
    PropPtr = CEndPointAtom::GetPropPtr(v14);
    function = (unsigned int)PropPtr;
    if ( PropPtr )
    {
      v18 = RemovePropW(file, PropPtr);
      if ( v18 )
      {
LABEL_28:
        InternalRevokeWindowPropInterface(
          file,
          v18,
          &GUID_00000135_0000_0000_c000_000000000046,
          dwAssignAptID,
          &dwAssignPID);
        RemovePropW(file, L"ClipboardDataObjectInterface");
        RemovePropW(file, L"ClipboardRootDataObjectInterface");
        v11 = L"ClipboardDataObjectInterfaceMTA";
        v12 = file;
        goto LABEL_11;
      }
    }
    else
    {
      v18 = 0;
    }
    if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
    {
      line = GetLastError();
      ComTraceMessageT<HWND__ *,unsigned int,unsigned long>(
        v20,
        "UnAssignEndpointProperty",
        397,
        v21,
        v23,
        file,
        function,
        line);
    }
    goto LABEL_28;
  }
  ((void (__fastcall *)(IDataObject *))pDataObject->lpVtbl->AddRef)(pDataObject);
  if ( pSourceDataObject )
    ((void (__fastcall *)(IDataObject *))pSourceDataObject->lpVtbl->AddRef)(pSourceDataObject);
  return 0;
}

```

## disassembly

```asm
0x1800110e0  mov     [rsp-30h+pData], hClipWnd
0x1800110e5  push    rbp
0x1800110e6  push    rbx
0x1800110e7  push    rsi
0x1800110e8  push    rdi
0x1800110e9  push    r14
0x1800110eb  push    r15
0x1800110ed  mov     rbp, rsp
0x1800110f0  sub     rsp, 58h
0x1800110f4  mov     r14, ppDataObjectMTAAddress
0x1800110f7  mov     [rbp+dwAssignAptID], 0
0x1800110fe  mov     rsi, pSourceDataObject
0x180011101  mov     [rbp+dwAssignPID], 0
0x180011108  mov     r15, pDataObject
0x18001110b  mov     rdi, hClipWnd
0x18001110e  call    ?AssignClipboardEndpointProperty@@YAJPEAUHWND__@@@Z; AssignClipboardEndpointProperty(HWND__ *)
0x180011113  mov     ebx, eax
0x180011115  test    eax, eax
0x180011117  jnz     $rtrn
0x18001111d  mov     pSourceDataObject, r15; hData
0x180011120  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x180011127  mov     hClipWnd, rdi; hWnd
0x18001112a  call    cs:__imp_SetPropW
0x180011130  test    eax, eax
0x180011132  jnz     short loc_180011160
0x180011134  call    cs:__imp_GetLastError
0x18001113a  mov     ebx, eax
0x18001113c  test    eax, eax
0x18001113e  jle     short loc_180011149
0x180011140  movzx   ebx, ax
0x180011143  or      ebx, 80070000h
0x180011149  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x18001114d  xor     edx, edx; fDragDrop
0x18001114f  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x180011153  mov     hClipWnd, rdi; hWnd
0x180011156  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18001115b  jmp     $rtrn
0x180011160  mov     pSourceDataObject, rsi; hData
0x180011163  lea     pDataObject, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x18001116a  mov     hClipWnd, rdi; hWnd
0x18001116d  call    cs:__imp_SetPropW
0x180011173  test    eax, eax
0x180011175  jnz     short loc_1800111B3
0x180011177  call    cs:__imp_GetLastError
0x18001117d  mov     ebx, eax
0x18001117f  test    eax, eax
0x180011181  jle     short loc_18001118C
0x180011183  movzx   ebx, ax
0x180011186  or      ebx, 80070000h
0x18001118c  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x180011190  xor     edx, edx; fDragDrop
0x180011192  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x180011196  mov     hClipWnd, rdi; hWnd
0x180011199  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18001119e  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x1800111a5  mov     hClipWnd, rdi; hWnd
0x1800111a8  call    cs:__imp_RemovePropW
0x1800111ae  jmp     $rtrn
0x1800111b3  test    r14, r14
0x1800111b6  jz      short loc_18001121B
0x1800111b8  mov     pSourceDataObject, [r14]; hData
0x1800111bb  test    pSourceDataObject, pSourceDataObject
0x1800111be  jz      short loc_18001121B
0x1800111c0  lea     pDataObject, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x1800111c7  mov     hClipWnd, rdi; hWnd
0x1800111ca  call    cs:__imp_SetPropW
0x1800111d0  test    eax, eax
0x1800111d2  jnz     short loc_180011214
0x1800111d4  call    cs:__imp_GetLastError
0x1800111da  mov     ebx, eax
0x1800111dc  test    eax, eax
0x1800111de  jle     short loc_1800111E9
0x1800111e0  movzx   ebx, ax
0x1800111e3  or      ebx, 80070000h
0x1800111e9  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x1800111ed  xor     edx, edx; fDragDrop
0x1800111ef  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x1800111f3  mov     hClipWnd, rdi; hWnd
0x1800111f6  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x1800111fb  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x180011202  mov     hClipWnd, rdi; hWnd
0x180011205  call    cs:__imp_RemovePropW
0x18001120b  lea     pDataObject, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x180011212  jmp     short loc_1800111A5
0x180011214  mov     qword ptr [r14], 0
0x18001121b  movzx   ecx, cs:?g_cfDataObject@@3GA; cfFormat
0x180011222  lea     pDataObject, [rbp+pData]; pData
0x180011226  mov     r8d, 8; cb
0x18001122c  call    ?SetFormatAsHGlobal@@YAJGPEAX_K@Z; SetFormatAsHGlobal(ushort,void *,unsigned __int64)
0x180011231  mov     ebx, eax
0x180011233  test    eax, eax
0x180011235  jns     loc_1800112F6
0x18001123b  mov     rsi, [rbp+pData]
0x18001123f  call    ?GetPropPtr@CEndPointAtom@@QEAAPEBGXZ; CEndPointAtom::GetPropPtr(void)
0x180011244  mov     r14, rax
0x180011247  test    rax, rax
0x18001124a  jz      short loc_180011262
0x18001124c  mov     pDataObject, rax; lpString
0x18001124f  mov     hClipWnd, rsi; hWnd
0x180011252  call    cs:__imp_RemovePropW
0x180011258  mov     rdi, rax
0x18001125b  test    rax, rax
0x18001125e  jnz     short loc_1800112A7
0x180011260  jmp     short loc_180011264
0x180011262  xor     edi, edi
0x180011264  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18001126a  test    eax, eax
0x18001126c  jnz     short loc_180011281
0x18001126e  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180011274  jz      short loc_1800112A7
0x180011276  xor     ecx, ecx; level
0x180011278  call    IsWppLevelEnabled
0x18001127d  test    al, al
0x18001127f  jz      short loc_1800112A7
0x180011281  call    cs:__imp_GetLastError
0x180011287  mov     [rsp+58h+line], eax; line
0x18001128b  mov     r8d, 18Dh; <args_0>
0x180011291  mov     [rsp+58h+function], r14d; function
0x180011296  lea     pDataObject, aUnassignendpoi; "UnAssignEndpointProperty"
0x18001129d  mov     [rsp+58h+file], rsi; file
0x1800112a2  call    ??$ComTraceMessageT@PEAUHWND__@@IK@@YAXPEBD0HW4TraceLevel@@PEBGPEAUHWND__@@IK@Z; ComTraceMessageT<HWND__ *,uint,ulong>(char const *,char const *,int,TraceLevel,ushort const *,HWND__ *,uint,ulong)
0x1800112a7  lea     rax, [rbp+dwAssignPID]
0x1800112ab  mov     pDataObject, rdi
0x1800112ae  lea     ppDataObjectMTAAddress, [rbp+dwAssignAptID]
0x1800112b2  mov     [rsp+58h+var_38], rax
0x1800112b7  lea     pSourceDataObject, _GUID_00000135_0000_0000_c000_000000000046
0x1800112be  mov     hClipWnd, rsi
0x1800112c1  call    cs:__imp_InternalRevokeWindowPropInterface
0x1800112c7  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x1800112ce  mov     hClipWnd, rsi; hWnd
0x1800112d1  call    cs:__imp_RemovePropW
0x1800112d7  lea     pDataObject, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x1800112de  mov     hClipWnd, rsi; hWnd
0x1800112e1  call    cs:__imp_RemovePropW
0x1800112e7  lea     pDataObject, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x1800112ee  mov     hClipWnd, rsi
0x1800112f1  jmp     loc_1800111A8
0x1800112f6  mov     rax, [r15]
0x1800112f9  mov     hClipWnd, r15
0x1800112fc  mov     rax, [rax+8]
0x180011300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011305  test    rsi, rsi
0x180011308  jz      short loc_180011319
0x18001130a  mov     rax, [rsi]
0x18001130d  mov     hClipWnd, rsi
0x180011310  mov     rax, [rax+8]
0x180011314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011319  xor     ebx, ebx
0x18001131b  mov     eax, ebx
0x18001131d  add     rsp, 58h
0x180011321  pop     r15
0x180011323  pop     r14
0x180011325  pop     rdi
0x180011326  pop     rsi
0x180011327  pop     rbx
0x180011328  pop     rbp
0x180011329  retn
```
