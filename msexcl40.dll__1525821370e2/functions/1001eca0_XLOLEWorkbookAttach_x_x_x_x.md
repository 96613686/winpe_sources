# XLOLEWorkbookAttach(x,x,x,x)

- ea: `0x1001eca0`
- end: `0x1001f358`
- name: `_XLOLEWorkbookAttach@16`
- size: `1720`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1001abf0`

## callees

- `0x1001eca0`
- `0x1001f360`
- `0x10021260`
- `0x100212e0`
- `0x10021330`
- `0x10021dc0`
- `0x10021e70`
- `0x10021f10`
- `0x10021fe0`
- `0x10022090`
- `0x1002580a`
- `0x1002ee43`
- `0x10035510`
- `0x100358c5`
- `0x10035b40`
- `0x10035e9f`
- `0x10036684`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1001ee1a`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1001ee1a`
- `api-ms-win-crt-private-l1-1-0!__std_terminate` at `0x10035eb0`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1001f266`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1001f266`
- `OLEAUT32!__imp__GetActiveObject@12` at `0x1001ed26`
- `OLEAUT32!__imp__GetActiveObject@12` at `0x1001ed3e`
- `OLEAUT32!__imp__GetActiveObject@12` at `0x1001ed26`
- `OLEAUT32!__imp__GetActiveObject@12` at `0x1001ed3e`
- `USER32!EnumWindows` at `0x1001ecfa`
- `USER32!EnumWindows` at `0x1001ecfa`

## pseudocode

```c
int __thiscall XLOLEWorkbookAttach(wchar_t *this, int a2, int a3)
{
  int v3; // edi
  struct IDispatch *v4; // esi
  DispatchDriver *v5; // eax
  int v6; // ecx
  DispatchDriver *v7; // edi
  wchar_t *v8; // eax
  int v9; // edx
  int v10; // edi
  int v11; // eax
  wchar_t *v12; // esi
  wchar_t *v13; // edx
  int v14; // ecx
  wchar_t *v15; // eax
  ExcelRange *v16; // ecx
  DispatchDriver *v17; // ecx
  unsigned __int16 v19; // dx
  int v20; // eax
  bool v21; // zf
  wchar_t *v22; // eax
  wchar_t *v23; // edi
  IUnknown *v24; // ebx
  struct IDispatch *v25; // ebx
  int v26; // esi
  int v27; // eax
  wchar_t *v28; // eax
  wchar_t *v29; // esi
  int v30; // ebx
  wchar_t *v31; // eax
  _WORD *v32; // ecx
  int v33; // edx
  int v34; // esi
  int v35; // ebx
  _WORD *v36; // eax
  int v37; // eax
  int v38; // [esp-10h] [ebp-660h]
  int v39; // [esp+0h] [ebp-650h] BYREF
  int v40; // [esp+10h] [ebp-640h] BYREF
  int pExceptionObject; // [esp+14h] [ebp-63Ch] BYREF
  DispatchDriver *v42; // [esp+18h] [ebp-638h]
  int v43; // [esp+1Ch] [ebp-634h]
  int v44; // [esp+20h] [ebp-630h] BYREF
  int v45; // [esp+24h] [ebp-62Ch]
  CHAR v46[4]; // [esp+28h] [ebp-628h]
  CHAR v47[4]; // [esp+2Ch] [ebp-624h] BYREF
  IUnknown *ppunk; // [esp+30h] [ebp-620h] BYREF
  wchar_t *FullPath; // [esp+34h] [ebp-61Ch] BYREF
  wchar_t Filename[512]; // [esp+38h] [ebp-618h] BYREF
  wchar_t Ext[258]; // [esp+438h] [ebp-218h] BYREF
  int *v52; // [esp+640h] [ebp-10h]
  int v53; // [esp+64Ch] [ebp-4h]

  v52 = &v39;
  FullPath = this;
  *(_DWORD *)v46 = this;
  v43 = a3;
  if ( !dword_1003A760 )
    EnumWindows(EnumWindowsProc, 0);
  if ( !dword_1003A6DC )
  {
    wInvokeMethod = 2;
    if ( GetActiveObject(&CLSID_ExcelApplication, 0, &ppunk) < 0 )
    {
      if ( GetActiveObject(&CLSID_ExcelApplication95, 0, &ppunk) < 0 )
        return -6;
      wInvokeMethod = 1;
    }
    v3 = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const IID *const, void **), IUnknown *, GUID *, CHAR *))ppunk->lpVtbl->QueryInterface)(
           ppunk->lpVtbl->QueryInterface,
           ppunk,
           &IID_IDispatch,
           v47);
    ((void (__thiscall *)(ULONG (__stdcall *)(IUnknown *), IUnknown *))ppunk->lpVtbl->Release)(
      ppunk->lpVtbl->Release,
      ppunk);
    if ( v3 >= 0 )
    {
      v4 = *(struct IDispatch **)v47;
      v5 = (DispatchDriver *)MemAllocate(8);
      v7 = v5;
      v42 = v5;
      if ( v5 )
      {
        *(_DWORD *)v5 = 0;
        *((_DWORD *)v5 + 1) = 1;
        DispatchDriver::AttachDispatch(v5, v4, v6);
        ((void (__thiscall *)(ULONG (__stdcall *)(IDispatch *), struct IDispatch *))v4->lpVtbl->Release)(
          v4->lpVtbl->Release,
          v4);
        dword_1003A6DC = v7;
        dword_1003A6E0 = 0;
        goto LABEL_10;
      }
      ((void (__thiscall *)(ULONG (__stdcall *)(IDispatch *), struct IDispatch *, int))v4->lpVtbl->Release)(
        v4->lpVtbl->Release,
        v4,
        v38);
    }
    return -6;
  }
LABEL_10:
  ++dword_1003A760;
  __wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x1FFu, Ext, 0x100u);
  v8 = Filename;
  v9 = 511;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v9;
  }
  while ( v9 );
  v10 = v9 != 0 ? 511 - v9 : 0;
  if ( v9 )
  {
    v11 = 2147483646;
    v12 = Ext;
    v13 = &Filename[v10];
    v14 = 511 - v10;
    if ( 511 != v10 )
    {
      do
      {
        if ( !v11 )
          break;
        if ( !*v12 )
          break;
        *v13++ = *v12++;
        --v11;
        --v14;
      }
      while ( v14 );
    }
    v15 = v13 - 1;
    if ( v14 )
      v15 = v13;
    *v15 = 0;
  }
  v53 = 0;
  FullPath = (wchar_t *)dword_1003A6DC;
  DispatchDriver::InvokeHelper(dword_1003A6DC, 572, wInvokeMethod, 9u, v47, String, Filename);
  v17 = ExcelRange::AttachToRange(v16, *(struct IDispatch **)v47);
  v19 = wInvokeMethod;
  v20 = 8;
  v21 = wInvokeMethod == 1;
  *(_DWORD *)(a3 + 12) = v17;
  v44 = 0;
  if ( v21 )
    v20 = 5;
  v45 = 1;
  *(_DWORD *)(a3 + 4) = v20;
  v53 = 5;
  FullPath = 0;
  DispatchDriver::InvokeHelper(v17, 494, v19, 9u, (LPSTR)&ppunk, 0);
  v22 = (wchar_t *)MemAllocate(8);
  v23 = v22;
  if ( !v22 )
  {
    ((void (__thiscall *)(ULONG (__stdcall *)(IUnknown *), IUnknown *))ppunk->lpVtbl->Release)(
      ppunk->lpVtbl->Release,
      ppunk);
    v40 = 1;
    _CxxThrowException(&v40, (_ThrowInfo *)&_TI1H);
  }
  *(_DWORD *)v22 = 0;
  *((_DWORD *)v22 + 1) = 1;
  v24 = ppunk;
  if ( *(_DWORD *)v22 && *((_DWORD *)v22 + 1) )
    (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)v22 + 8))(*(_DWORD *)(**(_DWORD **)v22 + 8), *(_DWORD *)v22);
  *(_DWORD *)v23 = v24;
  *((_DWORD *)v23 + 1) = 1;
  ((void (__thiscall *)(ULONG (__stdcall *)(IUnknown *), IUnknown *))v24->lpVtbl->AddRef)(v24->lpVtbl->AddRef, v24);
  ((void (__thiscall *)(ULONG (__stdcall *)(IUnknown *), IUnknown *))ppunk->lpVtbl->Release)(
    ppunk->lpVtbl->Release,
    ppunk);
  FullPath = v23;
  DispatchCollectionIterator::QueryNewEnum((DispatchCollectionIterator *)&v44, (struct DispatchDriver *)v23);
  while ( 1 )
  {
    DispatchDriver::~DispatchDriver((DispatchDriver *)v23);
    operator delete(v23, 8u);
    v53 = 4;
    v25 = DispatchCollectionIterator::Next((DispatchCollectionIterator *)&v44);
    if ( !v25 )
      break;
    v28 = (wchar_t *)MemAllocate(8);
    v23 = v28;
    v42 = (DispatchDriver *)v28;
    if ( !v28 )
    {
      ((void (__thiscall *)(ULONG (__stdcall *)(IDispatch *), struct IDispatch *))v25->lpVtbl->Release)(
        v25->lpVtbl->Release,
        v25);
      pExceptionObject = 1;
      _CxxThrowException(&pExceptionObject, (_ThrowInfo *)&_TI1H);
    }
    *(_DWORD *)v28 = 0;
    *((_DWORD *)v28 + 1) = 1;
    if ( *(_DWORD *)v28 && *((_DWORD *)v28 + 1) )
      (*(void (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)v28 + 8))(*(_DWORD *)(**(_DWORD **)v28 + 8), *(_DWORD *)v28);
    *(_DWORD *)v23 = v25;
    *((_DWORD *)v23 + 1) = 1;
    ((void (__thiscall *)(ULONG (__stdcall *)(IDispatch *), struct IDispatch *))v25->lpVtbl->AddRef)(
      v25->lpVtbl->AddRef,
      v25);
    ((void (__thiscall *)(ULONG (__stdcall *)(IDispatch *), struct IDispatch *))v25->lpVtbl->Release)(
      v25->lpVtbl->Release,
      v25);
    *(_DWORD *)v47 = v23;
    LOBYTE(v53) = 7;
    DispatchDriver::InvokeHelper((DispatchDriver *)v23, 110, 2u, 8u, (LPSTR)&FullPath, 0);
    v29 = FullPath;
    v30 = MemAllocate(528);
    *(_DWORD *)v46 = v30;
    if ( v30 )
    {
      v31 = v29;
      v32 = (_WORD *)(v30 + 14);
      v33 = 2147483646;
      v34 = 256;
      do
      {
        if ( !v33 )
          break;
        if ( !*v31 )
          break;
        *v32++ = *v31++;
        --v33;
        --v34;
      }
      while ( v34 );
      v35 = *(_DWORD *)v46;
      v36 = v32 - 1;
      if ( v34 )
        v36 = v32;
      *v36 = 0;
      v37 = v43;
      *(_BYTE *)(v35 + 12) = 1;
      if ( *(_DWORD *)(v37 + 80) )
        *(_DWORD *)dword_1003AE7C = v35;
      else
        *(_DWORD *)(v37 + 80) = v35;
      v29 = FullPath;
      dword_1003AE7C = v35;
    }
    SysFreeString(v29);
  }
  v26 = MemAllocate(20);
  if ( !v26 )
  {
    v53 = 9;
LABEL_36:
    if ( v44 )
    {
      if ( v45 )
        (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v44 + 8))(*(_DWORD *)(*(_DWORD *)v44 + 8), v44);
    }
    return -2;
  }
  if ( FMTStoreFormat(L"General", (_DWORD *)(v26 + 8)) )
  {
    v53 = 10;
    goto LABEL_36;
  }
  v27 = v43;
  *(_DWORD *)(v26 + 4) = 0;
  *(_DWORD *)(v27 + 76) = v26;
  v53 = 11;
  if ( v44 && v45 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v44 + 8))(*(_DWORD *)(*(_DWORD *)v44 + 8), v44);
  return 0;
}

```

## disassembly

```asm
0x1001eca0  mov     edi, edi
0x1001eca2  push    ebp
0x1001eca3  mov     ebp, esp
0x1001eca5  push    0FFFFFFFFh
0x1001eca7  push    offset _XLOLEWorkbookAttach@16_SEH
0x1001ecac  mov     eax, large fs:0
0x1001ecb2  push    eax
0x1001ecb3  sub     esp, 634h
0x1001ecb9  mov     eax, ___security_cookie
0x1001ecbe  xor     eax, ebp
0x1001ecc0  mov     [ebp+var_14], eax
0x1001ecc3  push    ebx
0x1001ecc4  push    esi
0x1001ecc5  push    edi
0x1001ecc6  push    eax
0x1001ecc7  lea     eax, [ebp+var_C]
0x1001ecca  mov     large fs:0, eax
0x1001ecd0  mov     [ebp+var_10], esp
0x1001ecd3  mov     eax, ecx
0x1001ecd5  mov     [ebp+FullPath], eax
0x1001ecdb  cmp     dword_1003A760, 0
0x1001ece2  mov     ebx, [ebp+arg_4]
0x1001ece5  mov     dword ptr [ebp+var_628], eax
0x1001eceb  mov     [ebp+var_634], ebx
0x1001ecf1  jnz     short loc_1001ED00
0x1001ecf3  push    0; lParam
0x1001ecf5  push    offset ?EnumWindowsProc@@YGHPAUHWND__@@J@Z; lpEnumFunc
0x1001ecfa  call    ds:__imp__EnumWindows@8; EnumWindows(x,x)
0x1001ed00  cmp     dword_1003A6DC, 0
0x1001ed07  jnz     loc_1001EDEE
0x1001ed0d  mov     eax, 2
0x1001ed12  mov     ?wInvokeMethod@@3GA, ax; ushort wInvokeMethod
0x1001ed18  lea     eax, [ebp+ppunk]
0x1001ed1e  push    eax; ppunk
0x1001ed1f  push    0; pvReserved
0x1001ed21  push    offset _CLSID_ExcelApplication; rclsid
0x1001ed26  call    ds:__imp__GetActiveObject@12; GetActiveObject(x,x,x)
0x1001ed2c  test    eax, eax
0x1001ed2e  jns     short loc_1001ED57
0x1001ed30  lea     eax, [ebp+ppunk]
0x1001ed36  push    eax; ppunk
0x1001ed37  push    0; pvReserved
0x1001ed39  push    offset _CLSID_ExcelApplication95; rclsid
0x1001ed3e  call    ds:__imp__GetActiveObject@12; GetActiveObject(x,x,x)
0x1001ed44  test    eax, eax
0x1001ed46  js      loc_1001EEF8
0x1001ed4c  mov     eax, 1
0x1001ed51  mov     ?wInvokeMethod@@3GA, ax; ushort wInvokeMethod
0x1001ed57  mov     ecx, [ebp+ppunk]
0x1001ed5d  mov     eax, [ecx]
0x1001ed5f  mov     esi, [eax]
0x1001ed61  lea     eax, [ebp+var_624]
0x1001ed67  push    eax
0x1001ed68  push    offset _IID_IDispatch
0x1001ed6d  push    ecx
0x1001ed6e  mov     ecx, esi
0x1001ed70  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001ed76  call    esi
0x1001ed78  mov     ecx, [ebp+ppunk]
0x1001ed7e  mov     edi, eax
0x1001ed80  push    ecx
0x1001ed81  mov     edx, [ecx]
0x1001ed83  mov     esi, [edx+8]
0x1001ed86  mov     ecx, esi
0x1001ed88  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001ed8e  call    esi
0x1001ed90  test    edi, edi
0x1001ed92  js      loc_1001EEF8
0x1001ed98  mov     esi, dword ptr [ebp+var_624]
0x1001ed9e  mov     ecx, 8
0x1001eda3  call    _MemAllocate@4; MemAllocate(x)
0x1001eda8  mov     edi, eax
0x1001edaa  mov     [ebp+var_638], edi
0x1001edb0  test    edi, edi
0x1001edb2  jz      loc_1001EEE8
0x1001edb8  push    ecx; int
0x1001edb9  push    esi; struct IDispatch *
0x1001edba  mov     ecx, edi; this
0x1001edbc  mov     dword ptr [edi], 0
0x1001edc2  mov     dword ptr [edi+4], 1
0x1001edc9  call    ?AttachDispatch@DispatchDriver@@QAEXPAUIDispatch@@H@Z; DispatchDriver::AttachDispatch(IDispatch *,int)
0x1001edce  mov     eax, [esi]
0x1001edd0  push    esi
0x1001edd1  mov     esi, [eax+8]
0x1001edd4  mov     ecx, esi
0x1001edd6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001eddc  call    esi
0x1001edde  mov     dword_1003A6DC, edi
0x1001ede4  mov     dword_1003A6E0, 0
0x1001edee  inc     dword_1003A760
0x1001edf4  lea     eax, [ebp+Ext]
0x1001edfa  push    100h; ExtCount
0x1001edff  push    eax; Ext
0x1001ee00  push    1FFh; FilenameCount
0x1001ee05  lea     eax, [ebp+Filename]
0x1001ee0b  push    eax; Filename
0x1001ee0c  push    0; DirCount
0x1001ee0e  push    0; Dir
0x1001ee10  push    0; DriveCount
0x1001ee12  push    0; Drive
0x1001ee14  push    [ebp+FullPath]; FullPath
0x1001ee1a  call    ds:__imp___wsplitpath_s
0x1001ee20  add     esp, 24h
0x1001ee23  lea     eax, [ebp+Filename]
0x1001ee29  mov     edx, 1FFh
0x1001ee2e  mov     edi, edi
0x1001ee30  cmp     word ptr [eax], 0
0x1001ee34  jz      short loc_1001EE3E
0x1001ee36  add     eax, 2
0x1001ee39  sub     edx, 1
0x1001ee3c  jnz     short loc_1001EE30
0x1001ee3e  mov     ecx, 1FFh
0x1001ee43  mov     edi, edx
0x1001ee45  mov     eax, ecx
0x1001ee47  sub     eax, edx
0x1001ee49  neg     edi
0x1001ee4b  sbb     edi, edi
0x1001ee4d  and     edi, eax
0x1001ee4f  test    edx, edx
0x1001ee51  jz      short loc_1001EE98
0x1001ee53  lea     edx, [ebp+Filename]
0x1001ee59  mov     eax, 7FFFFFFEh
0x1001ee5e  lea     esi, [ebp+Ext]
0x1001ee64  lea     edx, [edx+edi*2]
0x1001ee67  sub     ecx, edi
0x1001ee69  jz      short loc_1001EE8B
0x1001ee6b  nop     dword ptr [eax+eax+00h]
0x1001ee70  test    eax, eax
0x1001ee72  jz      short loc_1001EE8B
0x1001ee74  movzx   edi, word ptr [esi]
0x1001ee77  test    di, di
0x1001ee7a  jz      short loc_1001EE8B
0x1001ee7c  mov     [edx], di
0x1001ee7f  add     esi, 2
0x1001ee82  add     edx, 2
0x1001ee85  dec     eax
0x1001ee86  sub     ecx, 1
0x1001ee89  jnz     short loc_1001EE70
0x1001ee8b  test    ecx, ecx
0x1001ee8d  lea     eax, [edx-2]
0x1001ee90  cmovnz  eax, edx
0x1001ee93  xor     ecx, ecx
0x1001ee95  mov     [eax], cx
0x1001ee98  mov     ecx, dword_1003A6DC
0x1001ee9e  lea     eax, [ebp+Filename]
0x1001eea4  push    eax
0x1001eea5  push    offset String; lpString
0x1001eeaa  lea     eax, [ebp+var_624]
0x1001eeb0  mov     [ebp+var_4], 0
0x1001eeb7  push    eax; LPSTR
0x1001eeb8  movzx   eax, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x1001eebf  push    9; unsigned __int16
0x1001eec1  push    eax; unsigned __int16
0x1001eec2  push    23Ch; int
0x1001eec7  push    ecx; this
0x1001eec8  mov     [ebp+FullPath], ecx
0x1001eece  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1001eed3  add     esp, 1Ch
0x1001eed6  push    dword ptr [ebp+var_624]; struct IDispatch *
0x1001eedc  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x1001eee1  mov     ecx, eax
0x1001eee3  jmp     loc_1001EFA0
0x1001eee8  mov     eax, [esi]
0x1001eeea  push    esi
0x1001eeeb  mov     esi, [eax+8]
0x1001eeee  mov     ecx, esi
0x1001eef0  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001eef6  call    esi
0x1001eef8  mov     eax, 0FFFFFFFAh
0x1001eefd  mov     ecx, [ebp+var_C]
0x1001ef00  mov     large fs:0, ecx
0x1001ef07  pop     ecx
0x1001ef08  pop     edi
0x1001ef09  pop     esi
0x1001ef0a  pop     ebx
0x1001ef0b  mov     ecx, [ebp+var_14]
0x1001ef0e  xor     ecx, ebp; StackCookie
0x1001ef10  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001ef15  mov     esp, ebp
0x1001ef17  pop     ebp
0x1001ef18  retn    8
0x1001ef1b  mov     byte ptr [ebp+var_4], 2
0x1001ef1f  mov     ecx, [ebp+FullPath]; this
0x1001ef25  mov     [ebp+var_10], esp
0x1001ef28  mov     [ebp+ppunk], 0
0x1001ef32  call    ?Workbooks@ExcelApplication@@QAEPAVExcelWorkbooks@@XZ; ExcelApplication::Workbooks(void)
0x1001ef37  push    0
0x1001ef39  push    0
0x1001ef3b  push    dword ptr [ebp+var_628]
0x1001ef41  mov     esi, eax
0x1001ef43  lea     eax, [ebp+var_628]
0x1001ef49  push    offset dword_1003A638; lpString
0x1001ef4e  push    eax; LPSTR
0x1001ef4f  push    9; unsigned __int16
0x1001ef51  push    1; unsigned __int16
0x1001ef53  push    2AAh; int
0x1001ef58  push    esi; this
0x1001ef59  mov     [ebp+ppunk], esi
0x1001ef5f  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1001ef64  add     esp, 24h
0x1001ef67  push    dword ptr [ebp+var_628]; struct IDispatch *
0x1001ef6d  call    ?AttachToRange@ExcelRange@@IAEPAV1@PAUIDispatch@@@Z; ExcelRange::AttachToRange(IDispatch *)
0x1001ef72  mov     [ebp+FullPath], eax
0x1001ef78  test    esi, esi
0x1001ef7a  jz      short loc_1001EF8E
0x1001ef7c  mov     ecx, esi; this
0x1001ef7e  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x1001ef83  push    8; unsigned int
0x1001ef85  push    esi; void *
0x1001ef86  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001ef8b  add     esp, 8
0x1001ef8e  mov     eax, offset loc_1001EF94
0x1001ef93  retn
0x1001ef94  mov     ecx, [ebp+FullPath]
0x1001ef9a  mov     ebx, [ebp+var_634]
0x1001efa0  mov     dx, ?wInvokeMethod@@3GA; ushort wInvokeMethod
0x1001efa7  mov     eax, 8
0x1001efac  cmp     dx, 1
0x1001efb0  mov     [ebx+0Ch], ecx
0x1001efb3  mov     esi, 5
0x1001efb8  mov     [ebp+var_630], 0
0x1001efc2  cmovz   eax, esi
0x1001efc5  mov     [ebp+var_62C], 1
0x1001efcf  mov     [ebx+4], eax
0x1001efd2  push    0; lpString
0x1001efd4  lea     eax, [ebp+ppunk]
0x1001efda  mov     [ebp+var_4], 4
0x1001efe1  push    eax; LPSTR
0x1001efe2  push    9; unsigned __int16
0x1001efe4  movzx   eax, dx
0x1001efe7  push    eax; unsigned __int16
0x1001efe8  push    1EEh; int
0x1001efed  push    ecx; this
0x1001efee  mov     [ebp+FullPath], 0
0x1001eff8  mov     byte ptr [ebp+var_4], 5
0x1001effc  call    ?InvokeHelper@DispatchDriver@@QAAHJGGPAXPBEZZ; DispatchDriver::InvokeHelper(long,ushort,ushort,void *,uchar const *,...)
0x1001f001  add     esp, 18h
0x1001f004  lea     ecx, [esi+3]
0x1001f007  call    _MemAllocate@4; MemAllocate(x)
0x1001f00c  mov     edi, eax
0x1001f00e  test    edi, edi
0x1001f010  jz      loc_1001F327
0x1001f016  mov     dword ptr [edi], 0
0x1001f01c  mov     dword ptr [edi+4], 1
0x1001f023  mov     ecx, [edi]
0x1001f025  mov     ebx, [ebp+ppunk]
0x1001f02b  test    ecx, ecx
0x1001f02d  jz      short loc_1001F045
0x1001f02f  cmp     dword ptr [edi+4], 0
0x1001f033  jz      short loc_1001F045
0x1001f035  mov     eax, [ecx]
0x1001f037  push    ecx
0x1001f038  mov     esi, [eax+8]
0x1001f03b  mov     ecx, esi
0x1001f03d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f043  call    esi
0x1001f045  mov     [edi], ebx
0x1001f047  mov     dword ptr [edi+4], 1
0x1001f04e  mov     eax, [ebx]
0x1001f050  push    ebx
0x1001f051  mov     esi, [eax+4]
0x1001f054  mov     ecx, esi
0x1001f056  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f05c  call    esi
0x1001f05e  mov     eax, [ebp+ppunk]
0x1001f064  push    eax
0x1001f065  mov     ecx, [eax]
0x1001f067  mov     esi, [ecx+8]
0x1001f06a  mov     ecx, esi
0x1001f06c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001f072  call    esi
0x1001f074  push    edi; struct DispatchDriver *
0x1001f075  lea     ecx, [ebp+var_630]; this
0x1001f07b  mov     [ebp+FullPath], edi
0x1001f081  call    ?QueryNewEnum@DispatchCollectionIterator@@QAEHPAVDispatchDriver@@@Z; DispatchCollectionIterator::QueryNewEnum(DispatchDriver *)
0x1001f086  mov     ecx, edi; this
0x1001f088  call    ??1DispatchDriver@@QAE@XZ; DispatchDriver::~DispatchDriver(void)
0x1001f08d  push    8; unsigned int
0x1001f08f  push    edi; void *
0x1001f090  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1001f095  add     esp, 8
0x1001f098  lea     ecx, [ebp+var_630]; this
0x1001f09e  mov     [ebp+var_4], 4
0x1001f0a5  call    ?Next@DispatchCollectionIterator@@QAEPAUIDispatch@@XZ; DispatchCollectionIterator::Next(void)
0x1001f0aa  mov     ebx, eax
0x1001f0ac  test    ebx, ebx
0x1001f0ae  jnz     loc_1001F157
0x1001f0b4  lea     ecx, [eax+14h]
0x1001f0b7  call    _MemAllocate@4; MemAllocate(x)
0x1001f0bc  mov     esi, eax
0x1001f0be  test    esi, esi
0x1001f0c0  jnz     short loc_1001F0CB
0x1001f0c2  mov     [ebp+var_4], 9
0x1001f0c9  jmp     short loc_1001F0E9
0x1001f0cb  lea     eax, [esi+8]
0x1001f0ce  mov     edx, offset _ControlPanelSettings
0x1001f0d3  push    eax
0x1001f0d4  mov     ecx, offset aGeneral; "General"
0x1001f0d9  call    _FMTStoreFormat@12; FMTStoreFormat(x,x,x)
0x1001f0de  test    eax, eax
  ... truncated ...
```
