# GetShortcutTarget(ushort const *,ushort *,ushort *,ushort *)

- ea: `0x18009e6c0`
- end: `0x18009ecb0`
- name: `?GetShortcutTarget@@YA?AW4Bool@@PEBGPEAG11@Z`
- size: `1520`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18009e360`
- `0x1800ebd64`
- `0x18019ece0`

## callees

- `0x180005af8`
- `0x18000c4bc`
- `0x180016154`
- `0x18004a07c`
- `0x18009cdb8`
- `0x18009d06c`
- `0x18009e6c0`
- `0x18009ecb8`
- `0x18009ed48`
- `0x18013d2f0`
- `0x18014ae8c`
- `0x1802651ea`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009ec5c`
- `KERNEL32!CloseHandle` at `0x18009ec5c`
- `KERNEL32!GetLastError` at `0x18009e999`
- `KERNEL32!GetLastError` at `0x18009e999`
- `KERNEL32!SetLastError` at `0x18009e989`
- `KERNEL32!SetLastError` at `0x18009e989`
- `KERNEL32!CreateFileW` at `0x18009e8f7`
- `KERNEL32!CreateFileW` at `0x18009e8f7`
- `KERNEL32!LocalFree` at `0x18009e87c`
- `KERNEL32!LocalFree` at `0x18009e87c`
- `KERNEL32!GetFileType` at `0x18009e917`
- `KERNEL32!GetFileType` at `0x18009e917`
- `KERNEL32!ReadFile` at `0x18009e9e9`
- `KERNEL32!ReadFile` at `0x18009ea2e`
- `KERNEL32!ReadFile` at `0x18009ea85`
- `KERNEL32!ReadFile` at `0x18009eb09`
- `KERNEL32!ReadFile` at `0x18009eb85`
- `KERNEL32!ReadFile` at `0x18009ec0e`
- `KERNEL32!ReadFile` at `0x18009e9e9`
- `KERNEL32!ReadFile` at `0x18009ea2e`
- `KERNEL32!ReadFile` at `0x18009ea85`
- `KERNEL32!ReadFile` at `0x18009eb09`
- `KERNEL32!ReadFile` at `0x18009eb85`
- `KERNEL32!ReadFile` at `0x18009ec0e`
- `KERNEL32!SetFilePointer` at `0x18009ea5b`
- `KERNEL32!SetFilePointer` at `0x18009eabd`
- `KERNEL32!SetFilePointer` at `0x18009eb46`
- `KERNEL32!SetFilePointer` at `0x18009ebbd`
- `KERNEL32!SetFilePointer` at `0x18009ea5b`
- `KERNEL32!SetFilePointer` at `0x18009eabd`
- `KERNEL32!SetFilePointer` at `0x18009eb46`
- `KERNEL32!SetFilePointer` at `0x18009ebbd`

## string_xrefs

- `0x18009e945`: `Error: This is not a valid file, hence failing to create: %s`

## pseudocode

```c
_BOOL8 __fastcall GetShortcutTarget(const WCHAR *a1, unsigned __int16 *a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  BOOL v8; // edi
  struct IUnknown *COMInterface; // rax
  struct IUnknown *v10; // r14
  int v11; // ebx
  int (__fastcall *v12)(_QWORD, GUID *, __int64 *); // r14
  bool v13; // bl
  bool v14; // cl
  int v15; // esi
  BOOL v16; // ebx
  HANDLE FileW; // rax
  void *v18; // rbx
  bool v19; // cl
  unsigned int v20; // edx
  int v21; // edi
  int v22; // esi
  int v23; // ecx
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v26[2]; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  int (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  unsigned int v29; // [rsp+78h] [rbp-88h] BYREF
  HANDLE v30; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h] BYREF
  _BYTE Buffer[20]; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+B4h] [rbp-4Ch]
  _BYTE v35[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v36[260]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v37[266]; // [rsp+1FCh] [rbp+FCh] BYREF

  if ( !a1 )
    return 0;
  v8 = g_scServerContext == 2 && GetImpersonationFromPath(a1);
  COMInterface = CreateCOMInterface((const struct _GUID *)a1);
  v10 = COMInterface;
  if ( !COMInterface )
    return 0;
  v28 = 0;
  v27 = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD))COMInterface->lpVtbl->QueryInterface)(
          COMInterface,
          &IID_IShellLinkDataList,
          &v28);
  ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
  if ( v11 >= 0 && v28 )
  {
    v12 = **v28;
    v27 = 0;
    if ( v12(v28, &IID_IPersistFile, &v27) < 0 || !v27 )
    {
      v16 = 0;
      goto LABEL_62;
    }
    v13 = g_bHKCUIsSystem;
    if ( v8 )
      StartImpersonating();
    else
      LoadCurrentUserKey(1);
    v15 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, _QWORD))(*(_QWORD *)v27 + 40LL))(v27, a1, 0);
    if ( v8 )
      StopImpersonating(v14);
    else
      LoadCurrentUserKey(v13);
    if ( v15 >= 0 )
    {
      hMem = 0;
      if ( (*v28)[4](v28, (GUID *)2684354566LL, (__int64 *)&hMem) >= 0 )
      {
        if ( hMem )
        {
          v16 = DecomposeDescriptor((const unsigned __int16 *)hMem + 134, 1, a2, a3, a4, 0, 0, 0) != 0;
          LocalFree(hMem);
LABEL_62:
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v27);
          CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v28);
          return v16;
        }
      }
    }
    goto LABEL_21;
  }
  if ( v8 )
    StartImpersonating();
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
  v30 = FileW;
  v18 = FileW;
  if ( FileW != (HANDLE)-1LL && GetFileType(FileW) - 2 <= 1 )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        9,
        0,
        0,
        L"Error: This is not a valid file, hence failing to create: %s",
        a1,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    CHandle::operator=(&v30, -1);
    SetLastError(0x6Eu);
    v18 = v30;
  }
  GetLastError();
  if ( v8 )
    StopImpersonating(v19);
  if ( v18 != (void *)-1LL )
  {
    memset_0(Buffer, 0, 0x4Cu);
    v29 = 0;
    NumberOfBytesRead = 0;
    if ( !ReadFile(v18, Buffer, 0x4Cu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 76 )
    {
      CloseHandle(v18);
LABEL_21:
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v28 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[2])(v28);
      return 0;
    }
    if ( (v34 & 1) != 0 )
    {
      v26[0] = 0;
      if ( !ReadFile(v18, v26, 2u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 2 )
        goto LABEL_67;
      SetFilePointer(v18, v26[0], 0, 1u);
    }
    if ( (v34 & 2) == 0 )
      goto LABEL_47;
    if ( ReadFile(v18, &v29, 4u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 4 )
    {
      v20 = v29;
      if ( v29 >= 4 )
      {
        v29 -= 4;
        SetFilePointer(v18, v20 - 4, 0, 1u);
      }
LABEL_47:
      v21 = 0;
      v22 = v34 & 0x80;
      while ( 1 )
      {
        v23 = *((_DWORD *)qword_1802B1780 + v21);
        if ( !v23 )
          break;
        if ( (v23 & v34) != 0 )
        {
          v26[0] = 0;
          if ( !ReadFile(v18, v26, 2u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 2 )
            goto LABEL_67;
          SetFilePointer(v18, v26[0] * ((v22 != 0) + 1), 0, 1u);
        }
        ++v21;
      }
      memset_0(v35, 0, 0x314u);
      while ( 1 )
      {
        v32 = 0;
        if ( !ReadFile(v18, &v32, 8u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 8 )
          goto LABEL_60;
        if ( HIDWORD(v32) == -1610612730 )
          break;
        if ( (unsigned int)v32 <= 8 || SetFilePointer(v18, v32 - 8, 0, 1u) == -1 )
          goto LABEL_60;
      }
      if ( !ReadFile(v18, v36, 0x30Cu, &NumberOfBytesRead, 0) || NumberOfBytesRead != 780 )
      {
LABEL_60:
        v16 = 0;
        goto LABEL_61;
      }
      v16 = DecomposeDescriptor(v37, 1, a2, a3, a4, 0, 0, 0) != 0;
LABEL_61:
      CHandle::~CHandle((CHandle *)&v30);
      goto LABEL_62;
    }
  }
LABEL_67:
  CHandle::~CHandle((CHandle *)&v30);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v27);
  CComPointer<IMsiSelectionManager>::~CComPointer<IMsiSelectionManager>(&v28);
  return 0;
}

```

## disassembly

```asm
0x18009e6c0  push    rbp
0x18009e6c2  push    rbx
0x18009e6c3  push    rsi
0x18009e6c4  push    rdi
0x18009e6c5  push    r12
0x18009e6c7  push    r13
0x18009e6c9  push    r14
0x18009e6cb  push    r15
0x18009e6cd  lea     rbp, [rsp-328h]
0x18009e6d5  sub     rsp, 428h
0x18009e6dc  mov     rax, cs:__security_cookie
0x18009e6e3  xor     rax, rsp
0x18009e6e6  mov     [rbp+360h+var_50], rax
0x18009e6ed  mov     r13, r9
0x18009e6f0  mov     r12, r8
0x18009e6f3  mov     r15, rdx
0x18009e6f6  mov     rsi, rcx
0x18009e6f9  test    rcx, rcx
0x18009e6fc  jz      loc_18009EC8A
0x18009e702  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18009e709  jnz     short loc_18009E71B
0x18009e70b  call    ?GetImpersonationFromPath@@YA_NPEBG@Z; GetImpersonationFromPath(ushort const *)
0x18009e710  cmp     al, 1
0x18009e712  jnz     short loc_18009E71B
0x18009e714  mov     edi, 1
0x18009e719  jmp     short loc_18009E71D
0x18009e71b  xor     edi, edi
0x18009e71d  call    ?CreateCOMInterface@@YAPEAUIUnknown@@AEBU_GUID@@@Z; CreateCOMInterface(_GUID const &)
0x18009e722  mov     r14, rax
0x18009e725  test    rax, rax
0x18009e728  jz      loc_18009EC8A
0x18009e72e  mov     [rsp+460h+var_3F0], 0
0x18009e737  lea     r8, [rsp+460h+var_3F0]
0x18009e73c  mov     [rsp+460h+var_3F8], 0
0x18009e745  lea     rdx, IID_IShellLinkDataList
0x18009e74c  mov     rcx, [rax]
0x18009e74f  mov     rax, [rcx]
0x18009e752  mov     rcx, r14
0x18009e755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e75a  mov     rcx, [r14]
0x18009e75d  mov     ebx, eax
0x18009e75f  mov     rax, [rcx+10h]
0x18009e763  mov     rcx, r14
0x18009e766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e76b  xor     r14d, r14d
0x18009e76e  test    ebx, ebx
0x18009e770  js      loc_18009E8CA
0x18009e776  mov     rbx, [rsp+460h+var_3F0]
0x18009e77b  test    rbx, rbx
0x18009e77e  jz      loc_18009E8CA
0x18009e784  mov     rax, [rbx]
0x18009e787  mov     rcx, [rsp+460h+var_3F8]
0x18009e78c  mov     r14, [rax]
0x18009e78f  test    rcx, rcx
0x18009e792  jz      short loc_18009E7A0
0x18009e794  mov     rdx, [rcx]
0x18009e797  mov     rax, [rdx+10h]
0x18009e79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e7a0  lea     r8, [rsp+460h+var_3F8]
0x18009e7a5  mov     [rsp+460h+var_3F8], 0
0x18009e7ae  lea     rdx, IID_IPersistFile
0x18009e7b5  mov     rcx, rbx
0x18009e7b8  mov     rax, r14
0x18009e7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e7c0  xor     r14d, r14d
0x18009e7c3  test    eax, eax
0x18009e7c5  js      loc_18009E8C2
0x18009e7cb  cmp     [rsp+460h+var_3F8], r14
0x18009e7d0  jz      loc_18009E8C2
0x18009e7d6  mov     bl, cs:?g_bHKCUIsSystem@@3_NA; bool g_bHKCUIsSystem
0x18009e7dc  test    edi, edi
0x18009e7de  jz      short loc_18009E7E7
0x18009e7e0  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18009e7e5  jmp     short loc_18009E7EE
0x18009e7e7  mov     cl, 1; bool
0x18009e7e9  call    ?LoadCurrentUserKey@@YA_N_N@Z; LoadCurrentUserKey(bool)
0x18009e7ee  mov     rcx, [rsp+460h+var_3F8]
0x18009e7f3  xor     r8d, r8d
0x18009e7f6  mov     rdx, rsi
0x18009e7f9  mov     rax, [rcx]
0x18009e7fc  mov     rax, [rax+28h]
0x18009e800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e805  mov     esi, eax
0x18009e807  test    edi, edi
0x18009e809  jz      short loc_18009E812
0x18009e80b  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18009e810  jmp     short loc_18009E819
0x18009e812  mov     cl, bl; bool
0x18009e814  call    ?LoadCurrentUserKey@@YA_N_N@Z; LoadCurrentUserKey(bool)
0x18009e819  test    esi, esi
0x18009e81b  js      short loc_18009E88D
0x18009e81d  mov     rcx, [rsp+460h+var_3F0]
0x18009e822  lea     r8, [rbp+360h+hMem]
0x18009e826  mov     [rbp+360h+hMem], r14
0x18009e82a  mov     edx, 0A0000006h
0x18009e82f  mov     rax, [rcx]
0x18009e832  mov     rax, [rax+20h]
0x18009e836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e83b  test    eax, eax
0x18009e83d  js      short loc_18009E88D
0x18009e83f  mov     rcx, [rbp+360h+hMem]
0x18009e843  test    rcx, rcx
0x18009e846  jz      short loc_18009E88D
0x18009e848  mov     [rsp+460h+var_428], r14; bool *
0x18009e84d  add     rcx, 10Ch; unsigned __int16 *
0x18009e854  mov     [rsp+460h+hTemplateFile], r14; unsigned int *
0x18009e859  mov     r9, r12; unsigned __int16 *
0x18009e85c  mov     qword ptr [rsp+460h+dwFlagsAndAttributes], r14; unsigned int *
0x18009e861  mov     r8, r15; unsigned __int16 *
0x18009e864  mov     dl, 1; bool
0x18009e866  mov     qword ptr [rsp+460h+dwCreationDisposition], r13; unsigned __int16 *
0x18009e86b  call    ?DecomposeDescriptor@@YAHPEBG_NPEAG22PEAK3PEA_N@Z; DecomposeDescriptor(ushort const *,bool,ushort *,ushort *,ushort *,ulong *,ulong *,bool *)
0x18009e870  mov     rcx, [rbp+360h+hMem]; hMem
0x18009e874  test    eax, eax
0x18009e876  mov     ebx, r14d
0x18009e879  setnz   bl
0x18009e87c  call    cs:__imp_LocalFree
0x18009e883  nop     dword ptr [rax+rax+00h]
0x18009e888  jmp     loc_18009EBDA
0x18009e88d  mov     rcx, [rsp+460h+var_3F8]
0x18009e892  test    rcx, rcx
0x18009e895  jz      short loc_18009E8A3
0x18009e897  mov     rax, [rcx]
0x18009e89a  mov     rax, [rax+10h]
0x18009e89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e8a3  mov     rcx, [rsp+460h+var_3F0]
0x18009e8a8  test    rcx, rcx
0x18009e8ab  jz      loc_18009EC8A
0x18009e8b1  mov     rax, [rcx]
0x18009e8b4  mov     rax, [rax+10h]
0x18009e8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e8bd  jmp     loc_18009EC8A
0x18009e8c2  mov     ebx, r14d
0x18009e8c5  jmp     loc_18009EBDA
0x18009e8ca  test    edi, edi
0x18009e8cc  jz      short loc_18009E8D3
0x18009e8ce  call    ?StartImpersonating@@YA_NXZ; StartImpersonating(void)
0x18009e8d3  xor     r9d, r9d; lpSecurityAttributes
0x18009e8d6  mov     [rsp+460h+hTemplateFile], r14; hTemplateFile
0x18009e8db  mov     [rsp+460h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18009e8e3  mov     edx, 80000000h; dwDesiredAccess
0x18009e8e8  mov     rcx, rsi; lpFileName
0x18009e8eb  mov     [rsp+460h+dwCreationDisposition], 3; dwCreationDisposition
0x18009e8f3  lea     r8d, [r9+1]; dwShareMode
0x18009e8f7  call    cs:__imp_CreateFileW
0x18009e8fe  nop     dword ptr [rax+rax+00h]
0x18009e903  mov     [rbp+360h+var_3E0], rax
0x18009e907  mov     rbx, rax
0x18009e90a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009e90e  jz      loc_18009E999
0x18009e914  mov     rcx, rax; hFile
0x18009e917  call    cs:__imp_GetFileType
0x18009e91e  nop     dword ptr [rax+rax+00h]
0x18009e923  add     eax, 0FFFFFFFEh
0x18009e926  cmp     eax, 1
0x18009e929  ja      short loc_18009E999
0x18009e92b  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18009e932  jz      short loc_18009E977
0x18009e934  mov     [rsp+460h+var_408], r14; void *
0x18009e939  lea     rax, aNull; "(NULL)"
0x18009e940  mov     [rsp+460h+var_410], r14d; unsigned int
0x18009e945  lea     r9, aErrorThisIsNot; "Error: This is not a valid file, hence "...
0x18009e94c  mov     [rsp+460h+var_418], rax; unsigned __int16 *
0x18009e951  xor     edx, edx; unsigned __int16
0x18009e953  mov     [rsp+460h+var_420], rax; unsigned __int16 *
0x18009e958  xor     r8d, r8d; int
0x18009e95b  mov     [rsp+460h+var_428], rax; unsigned __int16 *
0x18009e960  mov     [rsp+460h+hTemplateFile], rax; unsigned __int16 *
0x18009e965  mov     qword ptr [rsp+460h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18009e96a  lea     ecx, [rdx+9]; int
0x18009e96d  mov     qword ptr [rsp+460h+dwCreationDisposition], rsi; unsigned __int16 *
0x18009e972  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009e977  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009e97b  lea     rcx, [rbp+360h+var_3E0]
0x18009e97f  call    ??4CHandle@@QEAAXPEAX@Z; CHandle::operator=(void *)
0x18009e984  mov     ecx, 6Eh ; 'n'; dwErrCode
0x18009e989  call    cs:__imp_SetLastError
0x18009e990  nop     dword ptr [rax+rax+00h]
0x18009e995  mov     rbx, [rbp+360h+var_3E0]
0x18009e999  call    cs:__imp_GetLastError
0x18009e9a0  nop     dword ptr [rax+rax+00h]
0x18009e9a5  test    edi, edi
0x18009e9a7  jz      short loc_18009E9AE
0x18009e9a9  call    ?StopImpersonating@@YAX_N@Z; StopImpersonating(bool)
0x18009e9ae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18009e9b2  jz      loc_18009EC6D
0x18009e9b8  mov     edi, 4Ch ; 'L'
0x18009e9bd  lea     rcx, [rbp+360h+Buffer]; void *
0x18009e9c1  mov     r8d, edi; Size
0x18009e9c4  xor     edx, edx; Val
0x18009e9c6  call    memset_0
0x18009e9cb  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009e9d0  mov     [rsp+460h+var_3E8], r14d
0x18009e9d5  mov     r8d, edi; nNumberOfBytesToRead
0x18009e9d8  mov     [rsp+460h+NumberOfBytesRead], r14d
0x18009e9dd  lea     rdx, [rbp+360h+Buffer]; lpBuffer
0x18009e9e1  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18009e9e6  mov     rcx, rbx; hFile
0x18009e9e9  call    cs:__imp_ReadFile
0x18009e9f0  nop     dword ptr [rax+rax+00h]
0x18009e9f5  test    eax, eax
0x18009e9f7  jz      loc_18009EC59
0x18009e9fd  cmp     [rsp+460h+NumberOfBytesRead], edi
0x18009ea01  jnz     loc_18009EC59
0x18009ea07  mov     edi, 1
0x18009ea0c  test    byte ptr [rbp+360h+var_3AC], dil
0x18009ea10  jz      short loc_18009EA67
0x18009ea12  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009ea17  mov     [rsp+460h+var_3FC], r14w
0x18009ea1d  lea     r8d, [rdi+1]; nNumberOfBytesToRead
0x18009ea21  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18009ea26  lea     rdx, [rsp+460h+var_3FC]; lpBuffer
0x18009ea2b  mov     rcx, rbx; hFile
0x18009ea2e  call    cs:__imp_ReadFile
0x18009ea35  nop     dword ptr [rax+rax+00h]
0x18009ea3a  test    eax, eax
0x18009ea3c  jz      loc_18009EC6D
0x18009ea42  cmp     [rsp+460h+NumberOfBytesRead], 2
0x18009ea47  jnz     loc_18009EC6D
0x18009ea4d  movzx   edx, [rsp+460h+var_3FC]; lDistanceToMove
0x18009ea52  mov     r9d, edi; dwMoveMethod
0x18009ea55  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009ea58  mov     rcx, rbx; hFile
0x18009ea5b  call    cs:__imp_SetFilePointer
0x18009ea62  nop     dword ptr [rax+rax+00h]
0x18009ea67  test    byte ptr [rbp+360h+var_3AC], 2
0x18009ea6b  jz      short loc_18009EAC9
0x18009ea6d  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009ea72  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18009ea77  mov     r8d, 4; nNumberOfBytesToRead
0x18009ea7d  lea     rdx, [rsp+460h+var_3E8]; lpBuffer
0x18009ea82  mov     rcx, rbx; hFile
0x18009ea85  call    cs:__imp_ReadFile
0x18009ea8c  nop     dword ptr [rax+rax+00h]
0x18009ea91  test    eax, eax
0x18009ea93  jz      loc_18009EC6D
0x18009ea99  cmp     [rsp+460h+NumberOfBytesRead], 4
0x18009ea9e  jnz     loc_18009EC6D
0x18009eaa4  mov     edx, [rsp+460h+var_3E8]
0x18009eaa8  cmp     edx, 4
0x18009eaab  jb      short loc_18009EAC9
0x18009eaad  add     edx, 0FFFFFFFCh; lDistanceToMove
0x18009eab0  mov     r9d, edi; dwMoveMethod
0x18009eab3  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009eab6  mov     [rsp+460h+var_3E8], edx
0x18009eaba  mov     rcx, rbx; hFile
0x18009eabd  call    cs:__imp_SetFilePointer
0x18009eac4  nop     dword ptr [rax+rax+00h]
0x18009eac9  mov     esi, [rbp+360h+var_3AC]
0x18009eacc  mov     edi, r14d
0x18009eacf  and     esi, 80h
0x18009ead5  movsxd  rax, edi
0x18009ead8  lea     rcx, qword_1802B1780
0x18009eadf  mov     ecx, [rcx+rax*4]
0x18009eae2  test    ecx, ecx
0x18009eae4  jz      short loc_18009EB59
0x18009eae6  test    [rbp+360h+var_3AC], ecx
0x18009eae9  jz      short loc_18009EB52
0x18009eaeb  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009eaf0  mov     [rsp+460h+var_3FC], r14w
0x18009eaf6  mov     r8d, 2; nNumberOfBytesToRead
0x18009eafc  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18009eb01  lea     rdx, [rsp+460h+var_3FC]; lpBuffer
0x18009eb06  mov     rcx, rbx; hFile
0x18009eb09  call    cs:__imp_ReadFile
0x18009eb10  nop     dword ptr [rax+rax+00h]
0x18009eb15  test    eax, eax
0x18009eb17  jz      loc_18009EC6D
0x18009eb1d  cmp     [rsp+460h+NumberOfBytesRead], 2
0x18009eb22  jnz     loc_18009EC6D
0x18009eb28  mov     eax, esi
0x18009eb2a  mov     r9d, 1; dwMoveMethod
0x18009eb30  neg     eax
0x18009eb32  mov     rcx, rbx; hFile
0x18009eb35  movzx   eax, [rsp+460h+var_3FC]
0x18009eb3a  sbb     edx, edx
0x18009eb3c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18009eb3f  neg     edx
0x18009eb41  inc     edx
0x18009eb43  imul    edx, eax; lDistanceToMove
0x18009eb46  call    cs:__imp_SetFilePointer
0x18009eb4d  nop     dword ptr [rax+rax+00h]
0x18009eb52  inc     edi
0x18009eb54  jmp     loc_18009EAD5
0x18009eb59  xor     edx, edx; Val
0x18009eb5b  lea     rcx, [rbp+360h+var_370]; void *
0x18009eb5f  mov     r8d, 314h; Size
0x18009eb65  call    memset_0
0x18009eb6a  lea     r9, [rsp+460h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18009eb6f  mov     [rbp+360h+var_3D0], r14
0x18009eb73  mov     r8d, 8; nNumberOfBytesToRead
0x18009eb79  mov     qword ptr [rsp+460h+dwCreationDisposition], r14; lpOverlapped
0x18009eb7e  lea     rdx, [rbp+360h+var_3D0]; lpBuffer
0x18009eb82  mov     rcx, rbx; hFile
0x18009eb85  call    cs:__imp_ReadFile
0x18009eb8c  nop     dword ptr [rax+rax+00h]
0x18009eb91  test    eax, eax
0x18009eb93  jz      short loc_18009EBCE
0x18009eb95  cmp     [rsp+460h+NumberOfBytesRead], 8
0x18009eb9a  jnz     short loc_18009EBCE
  ... truncated ...
```
