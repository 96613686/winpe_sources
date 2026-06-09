# SetClipboardDataObject(HWND__ *,IDataObject *,IDataObject *,void * *)

- ea: `0x18000be3c`
- end: `0x18000c06f`
- name: `?SetClipboardDataObject@@YAJPEAUHWND__@@PEAUIDataObject@@1PEAPEAX@Z`
- size: `563`
- prototype: `HRESULT __fastcall(HWND__ *hClipWnd, IDataObject *pDataObject, IDataObject *pSourceDataObject, void **ppDataObjectMTAAddress)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e5b4`

## callees

- `0x18000a8f0`
- `0x18000be3c`
- `0x18000c078`
- `0x1800446b8`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c003`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bfa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c003`
- `USER32!RemovePropW` at `0x18000bf05`
- `USER32!RemovePropW` at `0x18000bf1b`
- `USER32!RemovePropW` at `0x18000bf31`
- `USER32!RemovePropW` at `0x18000c03a`
- `USER32!RemovePropW` at `0x18000bf05`
- `USER32!RemovePropW` at `0x18000bf1b`
- `USER32!RemovePropW` at `0x18000bf31`
- `USER32!RemovePropW` at `0x18000c03a`
- `USER32!SetPropW` at `0x18000be8b`
- `USER32!SetPropW` at `0x18000beac`
- `USER32!SetPropW` at `0x18000bff3`
- `USER32!SetPropW` at `0x18000be8b`
- `USER32!SetPropW` at `0x18000beac`
- `USER32!SetPropW` at `0x18000bff3`

## pseudocode

```c
__int64 __fastcall SetClipboardDataObject(
        HWND__ *hClipWnd,
        IDataObject *pDataObject,
        IDataObject *pSourceDataObject,
        void **ppDataObjectMTAAddress)
{
  HWND__ *v7; // rbx
  unsigned int v8; // edi
  const wchar_t *v9; // rdx
  signed int v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  unsigned int dwAssignPID; // [rsp+20h] [rbp-10h] BYREF
  unsigned int dwAssignAptID[3]; // [rsp+24h] [rbp-Ch] BYREF
  HWND__ *pData; // [rsp+50h] [rbp+20h] BYREF

  pData = hClipWnd;
  dwAssignAptID[0] = 0;
  dwAssignPID = 0;
  v7 = hClipWnd;
  v8 = AssignClipboardEndpointProperty(hClipWnd);
  if ( !v8 )
  {
    if ( SetPropW(v7, L"ClipboardDataObjectInterface", pDataObject) )
    {
      if ( !SetPropW(v7, L"ClipboardRootDataObjectInterface", pSourceDataObject) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        UnAssignEndpointProperty(v7, 0, dwAssignAptID, &dwAssignPID);
        v9 = L"ClipboardDataObjectInterface";
        goto LABEL_7;
      }
      if ( ppDataObjectMTAAddress && *ppDataObjectMTAAddress )
      {
        if ( !SetPropW(v7, L"ClipboardDataObjectInterfaceMTA", *ppDataObjectMTAAddress) )
        {
          v13 = GetLastError();
          v8 = v13;
          if ( v13 > 0 )
            v8 = (unsigned __int16)v13 | 0x80070000;
          UnAssignEndpointProperty(v7, 0, dwAssignAptID, &dwAssignPID);
          RemovePropW(v7, L"ClipboardDataObjectInterface");
          v9 = L"ClipboardRootDataObjectInterface";
          goto LABEL_7;
        }
        *ppDataObjectMTAAddress = 0;
      }
      v8 = SetFormatAsHGlobal(g_cfDataObject, &pData, 8u);
      if ( (v8 & 0x80000000) != 0 )
      {
        v7 = pData;
        UnAssignEndpointProperty(pData, 0, dwAssignAptID, &dwAssignPID);
        RemovePropW(v7, L"ClipboardDataObjectInterface");
        RemovePropW(v7, L"ClipboardRootDataObjectInterface");
        v9 = L"ClipboardDataObjectInterfaceMTA";
LABEL_7:
        RemovePropW(v7, v9);
        return v8;
      }
      ((void (__fastcall *)(IDataObject *))pDataObject->lpVtbl->AddRef)(pDataObject);
      if ( pSourceDataObject )
        ((void (__fastcall *)(IDataObject *))pSourceDataObject->lpVtbl->AddRef)(pSourceDataObject);
      return 0;
    }
    else
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      UnAssignEndpointProperty(v7, 0, dwAssignAptID, &dwAssignPID);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18000be3c  mov     rax, rsp
0x18000be3f  mov     [rax+10h], rbx
0x18000be43  mov     [rax+18h], rsi
0x18000be47  mov     [rax+20h], rdi
0x18000be4b  mov     [rax+8], hClipWnd
0x18000be4f  push    rbp
0x18000be50  push    r14
0x18000be52  push    r15
0x18000be54  mov     rbp, rsp
0x18000be57  sub     rsp, 30h
0x18000be5b  and     [rbp+dwAssignAptID], 0
0x18000be5f  mov     r14, ppDataObjectMTAAddress
0x18000be62  and     [rbp+dwAssignPID], 0
0x18000be66  mov     rsi, pSourceDataObject
0x18000be69  mov     r15, pDataObject
0x18000be6c  mov     rbx, hClipWnd
0x18000be6f  call    ?AssignClipboardEndpointProperty@@YAJPEAUHWND__@@@Z; AssignClipboardEndpointProperty(HWND__ *)
0x18000be74  mov     edi, eax
0x18000be76  test    eax, eax
0x18000be78  jnz     $rtrn
0x18000be7e  mov     pSourceDataObject, r15; hData
0x18000be81  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x18000be88  mov     hClipWnd, rbx; hWnd
0x18000be8b  call    cs:__imp_SetPropW
0x18000be92  nop     dword ptr [rax+rax+00h]
0x18000be97  test    eax, eax
0x18000be99  jz      loc_18000BF75
0x18000be9f  mov     pSourceDataObject, rsi; hData
0x18000bea2  lea     pDataObject, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x18000bea9  mov     hClipWnd, rbx; hWnd
0x18000beac  call    cs:__imp_SetPropW
0x18000beb3  nop     dword ptr [rax+rax+00h]
0x18000beb8  test    eax, eax
0x18000beba  jz      loc_18000BFA4
0x18000bec0  test    r14, r14
0x18000bec3  jnz     loc_18000BFDD
0x18000bec9  movzx   ecx, cs:?g_cfDataObject@@3GA; cfFormat
0x18000bed0  lea     pDataObject, [rbp+pData]; pData
0x18000bed4  mov     r8d, 8; cb
0x18000beda  call    ?SetFormatAsHGlobal@@YAJGPEAX_K@Z; SetFormatAsHGlobal(ushort,void *,unsigned __int64)
0x18000bedf  mov     edi, eax
0x18000bee1  test    eax, eax
0x18000bee3  jns     short loc_18000BF59
0x18000bee5  mov     rbx, [rbp+pData]
0x18000bee9  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x18000beed  mov     hClipWnd, rbx; hWnd
0x18000bef0  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x18000bef4  xor     edx, edx; fDragDrop
0x18000bef6  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18000befb  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x18000bf02  mov     hClipWnd, rbx; hWnd
0x18000bf05  call    cs:__imp_RemovePropW
0x18000bf0c  nop     dword ptr [rax+rax+00h]
0x18000bf11  lea     pDataObject, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x18000bf18  mov     hClipWnd, rbx; hWnd
0x18000bf1b  call    cs:__imp_RemovePropW
0x18000bf22  nop     dword ptr [rax+rax+00h]
0x18000bf27  lea     pDataObject, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x18000bf2e  mov     hClipWnd, rbx; hWnd
0x18000bf31  call    cs:__imp_RemovePropW
0x18000bf38  nop     dword ptr [rax+rax+00h]
0x18000bf3d  mov     rbx, [rsp+30h+arg_8]
0x18000bf42  mov     eax, edi
0x18000bf44  mov     rdi, [rsp+30h+arg_18]
0x18000bf49  mov     rsi, [rsp+30h+arg_10]
0x18000bf4e  add     rsp, 30h
0x18000bf52  pop     r15
0x18000bf54  pop     r14
0x18000bf56  pop     rbp
0x18000bf57  retn
0x18000bf59  mov     rax, [r15]
0x18000bf5c  mov     hClipWnd, r15
0x18000bf5f  mov     rax, [rax+8]
0x18000bf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf68  test    rsi, rsi
0x18000bf6b  jnz     loc_18000C05B
0x18000bf71  xor     edi, edi
0x18000bf73  jmp     short $rtrn
0x18000bf75  call    cs:__imp_GetLastError
0x18000bf7c  nop     dword ptr [rax+rax+00h]
0x18000bf81  mov     edi, eax
0x18000bf83  test    eax, eax
0x18000bf85  jle     short loc_18000BF90
0x18000bf87  movzx   edi, ax
0x18000bf8a  or      edi, 80070000h
0x18000bf90  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x18000bf94  xor     edx, edx; fDragDrop
0x18000bf96  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x18000bf9a  mov     hClipWnd, rbx; hWnd
0x18000bf9d  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18000bfa2  jmp     short $rtrn
0x18000bfa4  call    cs:__imp_GetLastError
0x18000bfab  nop     dword ptr [rax+rax+00h]
0x18000bfb0  mov     edi, eax
0x18000bfb2  test    eax, eax
0x18000bfb4  jle     short loc_18000BFBF
0x18000bfb6  movzx   edi, ax
0x18000bfb9  or      edi, 80070000h
0x18000bfbf  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x18000bfc3  xor     edx, edx; fDragDrop
0x18000bfc5  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x18000bfc9  mov     hClipWnd, rbx; hWnd
0x18000bfcc  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18000bfd1  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x18000bfd8  jmp     loc_18000BF2E
0x18000bfdd  mov     pSourceDataObject, [r14]; hData
0x18000bfe0  test    pSourceDataObject, pSourceDataObject
0x18000bfe3  jz      loc_18000BEC9
0x18000bfe9  lea     pDataObject, aClipboarddatao; "ClipboardDataObjectInterfaceMTA"
0x18000bff0  mov     hClipWnd, rbx; hWnd
0x18000bff3  call    cs:__imp_SetPropW
0x18000bffa  nop     dword ptr [rax+rax+00h]
0x18000bfff  test    eax, eax
0x18000c001  jnz     short loc_18000C052
0x18000c003  call    cs:__imp_GetLastError
0x18000c00a  nop     dword ptr [rax+rax+00h]
0x18000c00f  mov     edi, eax
0x18000c011  test    eax, eax
0x18000c013  jle     short loc_18000C01E
0x18000c015  movzx   edi, ax
0x18000c018  or      edi, 80070000h
0x18000c01e  lea     ppDataObjectMTAAddress, [rbp+dwAssignPID]; dwAssignPID
0x18000c022  xor     edx, edx; fDragDrop
0x18000c024  lea     pSourceDataObject, [rbp+dwAssignAptID]; dwAssignAptID
0x18000c028  mov     hClipWnd, rbx; hWnd
0x18000c02b  call    ?UnAssignEndpointProperty@@YAJPEAUHWND__@@HPEAK1@Z; UnAssignEndpointProperty(HWND__ *,int,ulong *,ulong *)
0x18000c030  lea     pDataObject, aClipboarddatao_0; "ClipboardDataObjectInterface"
0x18000c037  mov     hClipWnd, rbx; hWnd
0x18000c03a  call    cs:__imp_RemovePropW
0x18000c041  nop     dword ptr [rax+rax+00h]
0x18000c046  lea     pDataObject, aClipboardrootd; "ClipboardRootDataObjectInterface"
0x18000c04d  jmp     loc_18000BF2E
0x18000c052  and     qword ptr [r14], 0
0x18000c056  jmp     loc_18000BEC9
0x18000c05b  mov     rax, [rsi]
0x18000c05e  mov     hClipWnd, rsi
0x18000c061  mov     rax, [rax+8]
0x18000c065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06a  jmp     loc_18000BF71
```
