# AccWrap_Annotate::get_accRole(tagVARIANT,tagVARIANT *)

- ea: `0x18000df00`
- end: `0x18000e46d`
- name: `?get_accRole@AccWrap_Annotate@@UEAAJUtagVARIANT@@PEAU2@@Z`
- size: `1389`
- prototype: `__int64 __fastcall(AccWrap_Annotate *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000df00`
- `0x18000f940`
- `0x18000fb10`
- `0x18001e4c0`
- `0x18001f024`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e428`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e428`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e177`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e177`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000e1b5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000e20b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000e1b5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000e20b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e22b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e378`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e22b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e13d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e36f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e13d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e36f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e098`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e1d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e098`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000e1d8`
- `OLEAUT32!__imp_VariantClear` at `0x18000e453`
- `OLEAUT32!__imp_VariantClear` at `0x18000e453`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e287`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e287`
- `USER32!FindWindowW` at `0x18000e359`
- `USER32!FindWindowW` at `0x18000e359`
- `USER32!GetPropW` at `0x18000e131`
- `USER32!GetPropW` at `0x18000e131`
- `USER32!GetWindowThreadProcessId` at `0x18000e15c`
- `USER32!GetWindowThreadProcessId` at `0x18000e15c`

## pseudocode

```c
__int64 __fastcall AccWrap_Annotate::get_accRole(
        unsigned int (__fastcall ***this)(AccWrap_Annotate *, GUID *, SIZE_T *),
        struct tagVARIANT *a2,
        struct tagVARIANT *a3)
{
  struct _GUID v5; // xmm6
  unsigned int (__fastcall **v6)(AccWrap_Annotate *, GUID *, SIZE_T *); // rax
  SIZE_T v7; // rcx
  unsigned int (__fastcall **v8)(AccWrap_Annotate *, GUID *, SIZE_T *); // rcx
  __int64 Lo; // rdx
  GUID *v10; // rcx
  char *v11; // r12
  int v12; // r11d
  unsigned int v13; // edx
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned int *v16; // rdi
  HWND v17; // rsi
  WCHAR *v18; // rax
  WCHAR *v19; // rbx
  _WORD *v20; // rcx
  unsigned __int8 *v21; // rdx
  int v22; // r8d
  unsigned __int64 v23; // rax
  HANDLE PropW; // r14
  HANDLE v25; // rbx
  HLOCAL v26; // rsi
  void *v27; // rcx
  struct tagVARIANT *v28; // r14
  __int64 v29; // rcx
  int PropertyFromEntry; // ebx
  unsigned int (__fastcall **v31)(AccWrap_Annotate *, GUID *, SIZE_T *); // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int (__fastcall *v33)(AccWrap_Annotate *, GUID *, SIZE_T *); // rax
  unsigned int v34; // ecx
  __int64 result; // rax
  HWND WindowW; // rax
  unsigned int Buffer; // [rsp+48h] [rbp-B8h] BYREF
  SIZE_T NumberOfBytesRead[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+60h] [rbp-A0h]
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD dwProcessId; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v44; // [rsp+80h] [rbp-80h] BYREF
  IRecordInfo *v45; // [rsp+90h] [rbp-70h]
  __int64 v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t WindowName[64]; // [rsp+B0h] [rbp-50h] BYREF

  if ( a2->vt != 3 )
  {
    v28 = a3;
    goto LABEL_33;
  }
  v5 = PROPID_ACC_ROLE;
  if ( !*((_DWORD *)this + 34) )
  {
    v6 = *this;
    NumberOfBytesRead[0] = 0;
    if ( !(*v6)((AccWrap_Annotate *)this, &IID_IAccIdentity, NumberOfBytesRead) )
    {
      v7 = NumberOfBytesRead[0];
      if ( NumberOfBytesRead[0] )
      {
        this[18] = (unsigned int (__fastcall **)(AccWrap_Annotate *, GUID *, SIZE_T *))NumberOfBytesRead[0];
        (*(void (__fastcall **)(SIZE_T))(*(_QWORD *)v7 + 16LL))(v7);
      }
    }
  }
  v8 = this[18];
  *((_DWORD *)this + 34) = 1;
  if ( !v8
    || (Lo = a2->cyVal.Lo,
        pv[0] = 0,
        v41 = 0,
        (*((unsigned int (__fastcall **)(unsigned int (__fastcall **)(AccWrap_Annotate *, GUID *, SIZE_T *), __int64, LPVOID *, int *))*v8
         + 3))(
          v8,
          Lo,
          pv,
          &v41))
    || (v11 = (char *)pv[0]) == 0 )
  {
    v28 = a3;
    goto LABEL_33;
  }
  v12 = v41;
  v13 = 0;
  *(GUID *)NumberOfBytesRead = PROPID_ACC_ROLE;
  v40 = v41;
  while ( v13 < 0xC )
  {
    v14 = 3LL * (int)v13;
    v10 = off_18004CAA0[v14];
    v15 = *(_QWORD *)&v10->Data1 - *(_QWORD *)&PROPID_ACC_ROLE.Data1;
    if ( *(_QWORD *)&v10->Data1 == *(_QWORD *)&PROPID_ACC_ROLE.Data1 )
      v15 = *(_QWORD *)v10->Data4 - *(_QWORD *)PROPID_ACC_ROLE.Data4;
    if ( !v15 )
    {
      _mm_lfence();
      v5 = **(GUID **)((char *)&off_18004CAA8 + v14 * 8);
      break;
    }
    ++v13;
  }
  v16 = (unsigned int *)((char *)pv[0] + 4);
  if ( v41 != 16 )
    goto LABEL_55;
  if ( *(_DWORD *)pv[0] == -2147483647 )
  {
    v17 = (HWND)(int)*v16;
  }
  else
  {
    if ( *(_DWORD *)pv[0] != -2147483646 )
      goto LABEL_55;
    if ( swprintf_s(WindowName, 0x40u, L"MSAA_DA_%lx", *v16) == -1 )
    {
      SetLastError(0x57u);
      v12 = v40;
      goto LABEL_55;
    }
    WindowW = FindWindowW(L"MSAA_DA_Class", WindowName);
    v12 = v40;
    v17 = WindowW;
  }
  if ( !v17 )
  {
LABEL_55:
    v28 = a3;
    PropertyFromEntry = 0;
    goto LABEL_46;
  }
  v18 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
  v19 = v18;
  if ( !v18 )
    goto LABEL_45;
  v20 = v18 + 5;
  *(_QWORD *)v18 = *(_QWORD *)L"MSAA_";
  v18[4] = aMsaa[4];
  if ( *(_DWORD *)v11 == -2147483647 )
  {
    *v20 = 42;
    v21 = (unsigned __int8 *)(v11 + 8);
    v20 = v18 + 6;
    v22 = 8;
  }
  else
  {
    v22 = 16;
    v21 = (unsigned __int8 *)v11;
  }
  do
  {
    v20 += 2;
    v23 = (unsigned __int64)*v21++ >> 4;
    *(v20 - 2) = a0123456789abcd[v23];
    *(v20 - 1) = a0123456789abcd[*(v21 - 1) & 0xF];
    --v22;
  }
  while ( v22 );
  *v20 = 0;
  PropW = GetPropW(v17, v19);
  LocalFree(v19);
  if ( !PropW )
    goto LABEL_45;
  dwProcessId = 0;
  GetWindowThreadProcessId(v17, &dwProcessId);
  if ( !dwProcessId )
    goto LABEL_45;
  v25 = OpenProcess(0x10u, 0, dwProcessId);
  if ( !v25 )
    goto LABEL_45;
  Buffer = 0;
  NumberOfBytesRead[0] = 0;
  if ( !ReadProcessMemory(v25, PropW, &Buffer, 4u, NumberOfBytesRead) || NumberOfBytesRead[0] != 4 )
    goto LABEL_43;
  v26 = LocalAlloc(0x40u, Buffer);
  v27 = v25;
  if ( !v26 )
  {
LABEL_44:
    CloseHandle(v27);
LABEL_45:
    v28 = a3;
    PropertyFromEntry = 0;
    goto LABEL_47;
  }
  NumberOfBytesRead[0] = 0;
  if ( !ReadProcessMemory(v25, PropW, v26, Buffer, NumberOfBytesRead) || NumberOfBytesRead[0] != Buffer )
  {
    LocalFree(v26);
LABEL_43:
    v27 = v25;
    goto LABEL_44;
  }
  CloseHandle(v25);
  v28 = a3;
  v46[1] = Buffer;
  v46[0] = (__int64)v26;
  v44 = v5;
  PropertyFromEntry = MapReaderMgr::_ReadPropertyFromEntry(v29, v46, (__int64)v11, 0x10u, (__int128 *)&v44, 0, a3);
  LocalFree(v26);
  if ( PropertyFromEntry )
    goto LABEL_32;
  v12 = v40;
LABEL_46:
  if ( v12 != 16 )
    goto LABEL_32;
LABEL_47:
  if ( *(_DWORD *)v11 == -2147483647 && *((_DWORD *)v11 + 3) )
  {
    LODWORD(NumberOfBytesRead[0]) = -2147483647;
    goto LABEL_53;
  }
  if ( *(_DWORD *)v11 == -2147483646 && *((_DWORD *)v11 + 3) )
  {
    LODWORD(NumberOfBytesRead[0]) = -2147483646;
LABEL_53:
    HIDWORD(NumberOfBytesRead[0]) = *v16;
    NumberOfBytesRead[1] = *((unsigned int *)v11 + 2);
    v44 = v5;
    PropertyFromEntry = MapReaderMgr::_LookupProp(
                          (MapReaderMgr *)v10,
                          (const unsigned __int8 *)NumberOfBytesRead,
                          16,
                          (const unsigned __int8 *)v11,
                          0x10u,
                          &v44,
                          1,
                          v28);
  }
LABEL_32:
  CoTaskMemFree(pv[0]);
  if ( PropertyFromEntry )
  {
    if ( v28->vt == 3 )
      return 0;
    VariantClear(v28);
  }
LABEL_33:
  v31 = this[8];
  pRecInfo = a2->pRecInfo;
  v33 = *v31;
  v44 = *(struct _GUID *)&a2->vt;
  v45 = pRecInfo;
  v34 = (*((__int64 (__fastcall **)(_QWORD *, struct _GUID *, struct tagVARIANT *))v33 + 13))(v31, &v44, v28);
  result = 0;
  if ( v34 )
    return v34;
  return result;
}

```

## disassembly

```asm
0x18000df00  push    rbp
0x18000df02  push    r12
0x18000df04  push    r13
0x18000df06  push    r14
0x18000df08  push    r15
0x18000df0a  lea     rbp, [rsp-60h]
0x18000df0f  sub     rsp, 160h
0x18000df16  movaps  [rsp+180h+var_40], xmm6
0x18000df1e  mov     rax, cs:__security_cookie
0x18000df25  xor     rax, rsp
0x18000df28  mov     [rbp+80h+var_50], rax
0x18000df2c  xor     r14d, r14d
0x18000df2f  mov     [rsp+180h+pvarg], r8
0x18000df34  cmp     word ptr [rdx], 3
0x18000df38  mov     r13, rdx
0x18000df3b  mov     r15, rcx
0x18000df3e  jnz     loc_18000E465
0x18000df44  movups  xmm6, xmmword ptr cs:PROPID_ACC_ROLE.Data1
0x18000df4b  cmp     [rcx+88h], r14d
0x18000df52  jnz     short loc_18000DF91
0x18000df54  mov     rax, [rcx]
0x18000df57  lea     r8, [rsp+180h+NumberOfBytesRead]
0x18000df5c  lea     rdx, IID_IAccIdentity
0x18000df63  mov     [rsp+180h+NumberOfBytesRead], r14
0x18000df68  mov     rax, [rax]
0x18000df6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df70  test    eax, eax
0x18000df72  jnz     short loc_18000DF91
0x18000df74  mov     rcx, [rsp+180h+NumberOfBytesRead]
0x18000df79  test    rcx, rcx
0x18000df7c  jz      short loc_18000DF91
0x18000df7e  mov     [r15+90h], rcx
0x18000df85  mov     rax, [rcx]
0x18000df88  mov     rax, [rax+10h]
0x18000df8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df91  mov     rcx, [r15+90h]
0x18000df98  mov     dword ptr [r15+88h], 1
0x18000dfa3  test    rcx, rcx
0x18000dfa6  jz      loc_18000E30D
0x18000dfac  mov     edx, [r13+8]
0x18000dfb0  lea     r9, [rsp+180h+var_11C]
0x18000dfb5  mov     [rsp+180h+pv], r14
0x18000dfba  lea     r8, [rsp+180h+pv]
0x18000dfbf  mov     [rsp+180h+var_11C], r14d
0x18000dfc4  mov     rax, [rcx]
0x18000dfc7  mov     rax, [rax+18h]
0x18000dfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd0  test    eax, eax
0x18000dfd2  jnz     loc_18000E30D
0x18000dfd8  mov     r12, [rsp+180h+pv]
0x18000dfdd  test    r12, r12
0x18000dfe0  jz      loc_18000E30D
0x18000dfe6  mov     r11d, [rsp+180h+var_11C]
0x18000dfeb  mov     edx, r14d
0x18000dfee  movdqa  xmmword ptr [rsp+180h+NumberOfBytesRead], xmm6
0x18000dff4  lea     r14, __ImageBase
0x18000dffb  mov     r9, [rsp+180h+NumberOfBytesRead+8]
0x18000e000  mov     r10, [rsp+180h+NumberOfBytesRead]
0x18000e005  mov     [rsp+180h+var_120], r11d
0x18000e00a  mov     [rsp+180h+arg_18], rbx
0x18000e012  cmp     edx, 0Ch
0x18000e015  jnb     short loc_18000E054
0x18000e017  movsxd  rax, edx
0x18000e01a  lea     rcx, [rax+rax*2]
0x18000e01e  lea     r8, ds:0[rcx*8]
0x18000e026  mov     rcx, [r8+r14+4CAA0h]
0x18000e02e  mov     rax, [rcx]
0x18000e031  sub     rax, r10
0x18000e034  jnz     short loc_18000E03D
0x18000e036  mov     rax, [rcx+8]
0x18000e03a  sub     rax, r9
0x18000e03d  test    rax, rax
0x18000e040  jnz     loc_18000E306
0x18000e046  lfence
0x18000e049  mov     rax, [r8+r14+4CAA8h]
0x18000e051  movups  xmm6, xmmword ptr [rax]
0x18000e054  mov     [rsp+180h+var_28], rsi
0x18000e05c  mov     [rsp+180h+var_30], rdi
0x18000e064  lea     rdi, [r12+4]
0x18000e069  cmp     r11d, 10h
0x18000e06d  jnz     loc_18000E433
0x18000e073  mov     eax, [r12]
0x18000e077  cmp     eax, 80000001h
0x18000e07c  jnz     loc_18000E322
0x18000e082  movsxd  rsi, dword ptr [rdi]
0x18000e085  test    rsi, rsi
0x18000e088  jz      loc_18000E433
0x18000e08e  mov     edx, 4Ch ; 'L'; uBytes
0x18000e093  mov     ecx, 40h ; '@'; uFlags
0x18000e098  call    cs:__imp_LocalAlloc
0x18000e09e  mov     rbx, rax
0x18000e0a1  test    rax, rax
0x18000e0a4  jz      loc_18000E37E
0x18000e0aa  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000e0b2  lea     rcx, [rbx+0Ah]
0x18000e0b6  movsd   qword ptr [rax], xmm0
0x18000e0ba  movzx   eax, word ptr cs:aMsaa+8; "_"
0x18000e0c1  mov     [rbx+8], ax
0x18000e0c5  cmp     dword ptr [r12], 80000001h
0x18000e0cd  jnz     loc_18000E314
0x18000e0d3  mov     word ptr [rcx], 2Ah ; '*'
0x18000e0d8  lea     rdx, [r12+8]
0x18000e0dd  add     rcx, 2
0x18000e0e1  mov     r8d, 8
0x18000e0e7  nop     word ptr [rax+rax+00000000h]
0x18000e0f0  movzx   eax, byte ptr [rdx]
0x18000e0f3  lea     rcx, [rcx+4]
0x18000e0f7  shr     rax, 4
0x18000e0fb  lea     rdx, [rdx+1]
0x18000e0ff  movzx   eax, word ptr ds:rva a0123456789abcd[r14+rax*2]; "0123456789ABCDEF" ...
0x18000e108  mov     [rcx-4], ax
0x18000e10c  movzx   eax, byte ptr [rdx-1]
0x18000e110  and     eax, 0Fh
0x18000e113  movzx   eax, word ptr ds:rva a0123456789abcd[r14+rax*2]; "0123456789ABCDEF" ...
0x18000e11c  mov     [rcx-2], ax
0x18000e120  add     r8d, 0FFFFFFFFh
0x18000e124  jnz     short loc_18000E0F0
0x18000e126  xor     eax, eax
0x18000e128  mov     rdx, rbx; lpString
0x18000e12b  mov     [rcx], ax
0x18000e12e  mov     rcx, rsi; hWnd
0x18000e131  call    cs:__imp_GetPropW
0x18000e137  mov     rcx, rbx; hMem
0x18000e13a  mov     r14, rax
0x18000e13d  call    cs:__imp_LocalFree
0x18000e143  test    r14, r14
0x18000e146  jz      loc_18000E37E
0x18000e14c  lea     rdx, [rsp+180h+dwProcessId]; lpdwProcessId
0x18000e151  mov     [rsp+180h+dwProcessId], 0
0x18000e159  mov     rcx, rsi; hWnd
0x18000e15c  call    cs:__imp_GetWindowThreadProcessId
0x18000e162  mov     r8d, [rsp+180h+dwProcessId]; dwProcessId
0x18000e167  test    r8d, r8d
0x18000e16a  jz      loc_18000E37E
0x18000e170  xor     edx, edx; bInheritHandle
0x18000e172  mov     ecx, 10h; dwDesiredAccess
0x18000e177  call    cs:__imp_OpenProcess
0x18000e17d  mov     rbx, rax
0x18000e180  test    rax, rax
0x18000e183  jz      loc_18000E37E
0x18000e189  lea     rax, [rsp+180h+NumberOfBytesRead]
0x18000e18e  mov     [rsp+180h+Buffer], 0
0x18000e196  mov     r9d, 4; nSize
0x18000e19c  mov     [rsp+180h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000e1a1  lea     r8, [rsp+180h+Buffer]; lpBuffer
0x18000e1a6  mov     [rsp+180h+NumberOfBytesRead], 0
0x18000e1af  mov     rdx, r14; lpBaseAddress
0x18000e1b2  mov     rcx, rbx; hProcess
0x18000e1b5  call    cs:__imp_ReadProcessMemory
0x18000e1bb  test    eax, eax
0x18000e1bd  jz      loc_18000E375
0x18000e1c3  cmp     [rsp+180h+NumberOfBytesRead], 4
0x18000e1c9  jnz     loc_18000E375
0x18000e1cf  mov     edx, [rsp+180h+Buffer]; uBytes
0x18000e1d3  mov     ecx, 40h ; '@'; uFlags
0x18000e1d8  call    cs:__imp_LocalAlloc
0x18000e1de  mov     rsi, rax
0x18000e1e1  mov     rcx, rbx; hProcess
0x18000e1e4  test    rax, rax
0x18000e1e7  jz      loc_18000E378
0x18000e1ed  mov     r9d, [rsp+180h+Buffer]; nSize
0x18000e1f2  lea     rax, [rsp+180h+NumberOfBytesRead]
0x18000e1f7  mov     r8, rsi; lpBuffer
0x18000e1fa  mov     [rsp+180h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000e1ff  mov     rdx, r14; lpBaseAddress
0x18000e202  mov     [rsp+180h+NumberOfBytesRead], 0
0x18000e20b  call    cs:__imp_ReadProcessMemory
0x18000e211  test    eax, eax
0x18000e213  jz      loc_18000E36C
0x18000e219  mov     eax, [rsp+180h+Buffer]
0x18000e21d  cmp     [rsp+180h+NumberOfBytesRead], rax
0x18000e222  jnz     loc_18000E36C
0x18000e228  mov     rcx, rbx; hObject
0x18000e22b  call    cs:__imp_CloseHandle
0x18000e231  mov     eax, [rsp+180h+Buffer]
0x18000e235  lea     rdx, [rbp+80h+var_E0]
0x18000e239  mov     r14, [rsp+180h+pvarg]
0x18000e23e  mov     r9d, 10h
0x18000e244  mov     [rbp+80h+var_D8], rax
0x18000e248  mov     r8, r12
0x18000e24b  lea     rax, [rbp+80h+var_100]
0x18000e24f  mov     qword ptr [rsp+180h+var_150], r14
0x18000e254  mov     dword ptr [rsp+180h+var_158], 0
0x18000e25c  mov     [rsp+180h+lpNumberOfBytesRead], rax
0x18000e261  mov     [rbp+80h+var_E0], rsi
0x18000e265  movdqa  xmmword ptr [rbp+80h+var_100.Data1], xmm6
0x18000e26a  call    ?_ReadPropertyFromEntry@MapReaderMgr@@AEAAHVMemStream@@PEBEKU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_ReadPropertyFromEntry(MemStream,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000e26f  mov     rcx, rsi; hMem
0x18000e272  mov     ebx, eax
0x18000e274  call    cs:__imp_LocalFree
0x18000e27a  test    ebx, ebx
0x18000e27c  jz      loc_18000E43F
0x18000e282  mov     rcx, [rsp+180h+pv]; pv
0x18000e287  call    cs:__imp_CoTaskMemFree
0x18000e28d  mov     rdi, [rsp+180h+var_30]
0x18000e295  test    ebx, ebx
0x18000e297  mov     rbx, [rsp+180h+arg_18]
0x18000e29f  mov     rsi, [rsp+180h+var_28]
0x18000e2a7  jnz     loc_18000E449
0x18000e2ad  mov     rcx, [r15+40h]
0x18000e2b1  lea     rdx, [rbp+80h+var_100]
0x18000e2b5  movups  xmm0, xmmword ptr [r13+0]
0x18000e2ba  mov     r8, r14
0x18000e2bd  movsd   xmm1, qword ptr [r13+10h]
0x18000e2c3  mov     rax, [rcx]
0x18000e2c6  movaps  xmmword ptr [rbp+80h+var_100.Data1], xmm0
0x18000e2ca  movsd   [rbp+80h+var_F0], xmm1
0x18000e2cf  mov     rax, [rax+68h]
0x18000e2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2d8  mov     ecx, eax
0x18000e2da  xor     eax, eax
0x18000e2dc  test    ecx, ecx
0x18000e2de  cmovnz  eax, ecx
0x18000e2e1  mov     rcx, [rbp+80h+var_50]
0x18000e2e5  xor     rcx, rsp; StackCookie
0x18000e2e8  call    __security_check_cookie
0x18000e2ed  movaps  xmm6, [rsp+180h+var_40]
0x18000e2f5  add     rsp, 160h
0x18000e2fc  pop     r15
0x18000e2fe  pop     r14
0x18000e300  pop     r13
0x18000e302  pop     r12
0x18000e304  pop     rbp
0x18000e305  retn
0x18000e306  inc     edx
0x18000e308  jmp     loc_18000E012
0x18000e30d  mov     r14, [rsp+180h+pvarg]
0x18000e312  jmp     short loc_18000E2AD
0x18000e314  mov     r8d, 10h
0x18000e31a  mov     rdx, r12
0x18000e31d  jmp     loc_18000E0F0
0x18000e322  cmp     eax, 80000002h
0x18000e327  jnz     loc_18000E433
0x18000e32d  mov     r9d, [rdi]
0x18000e330  lea     r8, aMsaaDaLx; "MSAA_DA_%lx"
0x18000e337  mov     edx, 40h ; '@'; BufferCount
0x18000e33c  lea     rcx, [rbp+80h+WindowName]; Buffer
0x18000e340  call    swprintf_s
0x18000e345  cmp     eax, 0FFFFFFFFh
0x18000e348  jz      loc_18000E423
0x18000e34e  lea     rdx, [rbp+80h+WindowName]; lpWindowName
0x18000e352  lea     rcx, ClassName; "MSAA_DA_Class"
0x18000e359  call    cs:__imp_FindWindowW
0x18000e35f  mov     r11d, [rsp+180h+var_120]
0x18000e364  mov     rsi, rax
0x18000e367  jmp     loc_18000E085
0x18000e36c  mov     rcx, rsi; hMem
0x18000e36f  call    cs:__imp_LocalFree
0x18000e375  mov     rcx, rbx; hObject
0x18000e378  call    cs:__imp_CloseHandle
0x18000e37e  mov     r14, [rsp+180h+pvarg]
0x18000e383  xor     ebx, ebx
0x18000e385  jmp     short loc_18000E391
0x18000e387  cmp     r11d, 10h
0x18000e38b  jnz     loc_18000E282
0x18000e391  cmp     dword ptr [r12], 80000001h
0x18000e399  jnz     short loc_18000E3A3
0x18000e39b  cmp     dword ptr [r12+0Ch], 0
0x18000e3a1  jnz     short loc_18000E3C7
0x18000e3a3  cmp     dword ptr [r12], 80000002h
0x18000e3ab  jnz     loc_18000E282
0x18000e3b1  cmp     dword ptr [r12+0Ch], 0
0x18000e3b7  jz      loc_18000E282
0x18000e3bd  mov     dword ptr [rsp+180h+NumberOfBytesRead], 80000002h
0x18000e3c5  jmp     short loc_18000E3CF
0x18000e3c7  mov     dword ptr [rsp+180h+NumberOfBytesRead], 80000001h
0x18000e3cf  mov     eax, [rdi]
0x18000e3d1  lea     rdx, [rsp+180h+NumberOfBytesRead]; unsigned __int8 *
0x18000e3d6  mov     dword ptr [rsp+180h+NumberOfBytesRead+4], eax
0x18000e3da  mov     r9, r12; unsigned __int8 *
0x18000e3dd  mov     eax, [r12+8]
0x18000e3e2  mov     r8d, 10h; unsigned int
0x18000e3e8  mov     [rsp+180h+var_148], r14; struct tagVARIANT *
0x18000e3ed  mov     dword ptr [rsp+180h+NumberOfBytesRead+8], eax
0x18000e3f1  lea     rax, [rbp+80h+var_100]
0x18000e3f5  mov     [rsp+180h+var_150], 1; int
0x18000e3fd  mov     [rsp+180h+var_158], rax; struct _GUID *
0x18000e402  mov     dword ptr [rsp+180h+lpNumberOfBytesRead], 10h; unsigned int
0x18000e40a  mov     dword ptr [rsp+180h+NumberOfBytesRead+0Ch], 0
0x18000e412  movdqa  xmmword ptr [rbp+80h+var_100.Data1], xmm6
0x18000e417  call    ?_LookupProp@MapReaderMgr@@AEAAHPEBEK0KU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_LookupProp(uchar const *,ulong,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000e41c  mov     ebx, eax
0x18000e41e  jmp     loc_18000E282
0x18000e423  mov     ecx, 57h ; 'W'; dwErrCode
0x18000e428  call    cs:__imp_SetLastError
0x18000e42e  mov     r11d, [rsp+180h+var_120]
0x18000e433  mov     r14, [rsp+180h+pvarg]
0x18000e438  xor     ebx, ebx
0x18000e43a  jmp     loc_18000E387
0x18000e43f  mov     r11d, [rsp+180h+var_120]
0x18000e444  jmp     loc_18000E387
0x18000e449  cmp     word ptr [r14], 3
0x18000e44e  jz      short loc_18000E45E
0x18000e450  mov     rcx, r14; pvarg
0x18000e453  call    cs:__imp_VariantClear
0x18000e459  jmp     loc_18000E2AD
0x18000e45e  xor     eax, eax
0x18000e460  jmp     loc_18000E2E1
0x18000e465  mov     r14, r8
0x18000e468  jmp     loc_18000E2AD
  ... truncated ...
```
