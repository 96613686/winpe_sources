# AccWrap_Annotate::get_accParent(IDispatch * *)

- ea: `0x18000d850`
- end: `0x18000def7`
- name: `?get_accParent@AccWrap_Annotate@@UEAAJPEAPEAUIDispatch@@@Z`
- size: `1703`
- prototype: `__int64 __fastcall(AccWrap_Annotate *__hidden this, struct IDispatch **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d850`
- `0x18000f940`
- `0x18000fb10`
- `0x18001e4c0`
- `0x18001f024`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000de8c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000dac7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000dac7`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000db01`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000db57`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000db01`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000db57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dde0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000deb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000db77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dde0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000deb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000da8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ddc6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d9e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db24`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d9e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000db24`
- `OLEAUT32!__imp_VariantClear` at `0x18000dedd`
- `OLEAUT32!__imp_VariantClear` at `0x18000dedd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dbd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dbd4`
- `USER32!FindWindowW` at `0x18000dd82`
- `USER32!FindWindowW` at `0x18000dd82`
- `USER32!GetPropW` at `0x18000da81`
- `USER32!GetPropW` at `0x18000da81`
- `USER32!GetWindowThreadProcessId` at `0x18000daac`
- `USER32!GetWindowThreadProcessId` at `0x18000daac`

## pseudocode

```c
__int64 __fastcall AccWrap_Annotate::get_accParent(
        unsigned int (__fastcall ***this)(AccWrap_Annotate *, GUID *, SIZE_T *),
        struct IDispatch **a2)
{
  struct _GUID v2; // xmm6
  HWND v3; // r14
  unsigned int (__fastcall **v6)(AccWrap_Annotate *, GUID *, SIZE_T *); // rax
  SIZE_T v7; // rcx
  unsigned int (__fastcall **v8)(AccWrap_Annotate *, GUID *, SIZE_T *); // rcx
  GUID *v9; // rcx
  char *v10; // r12
  int v11; // r11d
  unsigned int v12; // edx
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned int *v15; // rdi
  WCHAR *v16; // rax
  WCHAR *v17; // rbx
  _WORD *v18; // rcx
  unsigned __int8 *v19; // rdx
  int v20; // r8d
  unsigned __int64 v21; // rax
  HANDLE PropW; // r15
  HANDLE v23; // rbx
  __int64 v24; // rcx
  int v25; // ebx
  __int64 result; // rax
  __int64 v27; // rdi
  unsigned int (__fastcall **v28)(__int64, GUID *, LPVOID *); // rax
  int v29; // ebx
  HWND WindowW; // rax
  SIZE_T NumberOfBytesRead[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int Buffer; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+54h] [rbp-ACh]
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwProcessId[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _GUID v37; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  __int64 v39[3]; // [rsp+98h] [rbp-68h] BYREF
  wchar_t WindowName[64]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = PROPID_ACC_PARENT;
  LODWORD(v3) = 0;
  memset(&pvarg, 0, sizeof(pvarg));
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
  if ( !v8 )
    goto LABEL_32;
  pv = 0;
  v35 = 0;
  if ( (*((unsigned int (__fastcall **)(unsigned int (__fastcall **)(AccWrap_Annotate *, GUID *, SIZE_T *), _QWORD, LPVOID *, int *))*v8
        + 3))(
         v8,
         0,
         &pv,
         &v35) )
  {
    goto LABEL_32;
  }
  v10 = (char *)pv;
  if ( !pv )
    goto LABEL_32;
  v11 = v35;
  v12 = 0;
  *(GUID *)NumberOfBytesRead = PROPID_ACC_PARENT;
  v33 = v35;
  while ( v12 < 0xC )
  {
    v13 = 3LL * (int)v12;
    v9 = off_18004CAA0[v13];
    v14 = *(_QWORD *)&v9->Data1 - *(_QWORD *)&PROPID_ACC_PARENT.Data1;
    if ( *(_QWORD *)&v9->Data1 == *(_QWORD *)&PROPID_ACC_PARENT.Data1 )
      v14 = *(_QWORD *)v9->Data4 - *(_QWORD *)PROPID_ACC_PARENT.Data4;
    if ( !v14 )
    {
      _mm_lfence();
      v2 = **(GUID **)((char *)&off_18004CAA8 + v13 * 8);
      break;
    }
    ++v12;
  }
  v15 = (unsigned int *)((char *)pv + 4);
  if ( v35 != 16 )
    goto LABEL_61;
  if ( *(_DWORD *)pv == -2147483647 )
  {
    v3 = (HWND)(int)*v15;
  }
  else
  {
    if ( *(_DWORD *)pv != -2147483646 )
      goto LABEL_61;
    if ( swprintf_s(WindowName, 0x40u, L"MSAA_DA_%lx", *v15) == -1 )
    {
      SetLastError(0x57u);
      v11 = v33;
      goto LABEL_61;
    }
    WindowW = FindWindowW(L"MSAA_DA_Class", WindowName);
    v11 = v33;
    v3 = WindowW;
  }
  if ( !v3 )
  {
LABEL_61:
    v25 = (int)v3;
    goto LABEL_52;
  }
  v16 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
  v17 = v16;
  if ( !v16 )
  {
    LODWORD(v3) = 0;
    goto LABEL_50;
  }
  v18 = v16 + 5;
  *(_QWORD *)v16 = *(_QWORD *)L"MSAA_";
  v16[4] = aMsaa[4];
  if ( *(_DWORD *)v10 == -2147483647 )
  {
    *v18 = 42;
    v19 = (unsigned __int8 *)(v10 + 8);
    v18 = v16 + 6;
    v20 = 8;
  }
  else
  {
    v20 = 16;
    v19 = (unsigned __int8 *)v10;
  }
  do
  {
    v18 += 2;
    v21 = (unsigned __int64)*v19++ >> 4;
    *(v18 - 2) = a0123456789abcd[v21];
    *(v18 - 1) = a0123456789abcd[*(v19 - 1) & 0xF];
    --v20;
  }
  while ( v20 );
  *v18 = 0;
  PropW = GetPropW(v3, v17);
  LocalFree(v17);
  if ( !PropW )
  {
    LODWORD(v3) = 0;
    goto LABEL_50;
  }
  dwProcessId[0] = 0;
  GetWindowThreadProcessId(v3, dwProcessId);
  if ( !dwProcessId[0] )
  {
    LODWORD(v3) = 0;
    goto LABEL_50;
  }
  LODWORD(v3) = 0;
  v23 = OpenProcess(0x10u, 0, dwProcessId[0]);
  if ( !v23 )
  {
LABEL_50:
    v25 = 0;
    goto LABEL_53;
  }
  Buffer = 0;
  NumberOfBytesRead[0] = 0;
  if ( !ReadProcessMemory(v23, PropW, &Buffer, 4u, NumberOfBytesRead) || NumberOfBytesRead[0] != 4 )
  {
    CloseHandle(v23);
    goto LABEL_50;
  }
  v3 = (HWND)LocalAlloc(0x40u, Buffer);
  if ( !v3 )
  {
    CloseHandle(v23);
    LODWORD(v3) = 0;
    goto LABEL_50;
  }
  NumberOfBytesRead[0] = 0;
  if ( !ReadProcessMemory(v23, PropW, v3, Buffer, NumberOfBytesRead) || NumberOfBytesRead[0] != Buffer )
  {
    LocalFree(v3);
    CloseHandle(v23);
    LODWORD(v3) = 0;
    goto LABEL_50;
  }
  CloseHandle(v23);
  v39[1] = Buffer;
  v39[0] = (__int64)v3;
  v37 = v2;
  v25 = MapReaderMgr::_ReadPropertyFromEntry(v24, v39, (__int64)v10, 0x10u, (__int128 *)&v37, 0, &pvarg);
  LocalFree(v3);
  if ( v25 )
    goto LABEL_31;
  v11 = v33;
  LODWORD(v3) = 0;
LABEL_52:
  if ( v11 != 16 )
    goto LABEL_31;
LABEL_53:
  if ( *(_DWORD *)v10 == -2147483647 && *((_DWORD *)v10 + 3) )
  {
    LODWORD(NumberOfBytesRead[0]) = -2147483647;
    goto LABEL_59;
  }
  if ( *(_DWORD *)v10 == -2147483646 && *((_DWORD *)v10 + 3) )
  {
    LODWORD(NumberOfBytesRead[0]) = -2147483646;
LABEL_59:
    HIDWORD(NumberOfBytesRead[0]) = *v15;
    LODWORD(NumberOfBytesRead[1]) = *((_DWORD *)v10 + 2);
    HIDWORD(NumberOfBytesRead[1]) = (_DWORD)v3;
    v37 = v2;
    v25 = MapReaderMgr::_LookupProp(
            (MapReaderMgr *)v9,
            (const unsigned __int8 *)NumberOfBytesRead,
            16,
            (const unsigned __int8 *)v10,
            0x10u,
            &v37,
            1,
            &pvarg);
  }
LABEL_31:
  CoTaskMemFree(pv);
  if ( v25 )
  {
    if ( pvarg.vt == 9 )
    {
      *a2 = pvarg.pdispVal;
      return 0;
    }
    VariantClear(&pvarg);
  }
LABEL_32:
  result = (*((__int64 (__fastcall **)(unsigned int (__fastcall **)(AccWrap_Annotate *, GUID *, SIZE_T *), struct IDispatch **))*this[8]
            + 7))(
             this[8],
             a2);
  if ( (_DWORD)result )
    return result;
  if ( a2 )
  {
    v27 = (__int64)*a2;
    if ( *a2 )
    {
      v28 = *(unsigned int (__fastcall ***)(__int64, GUID *, LPVOID *))v27;
      pv = 0;
      if ( !(*v28)(v27, &IID_IServiceProvider, &pv) )
      {
        if ( pv )
        {
          *(_QWORD *)dwProcessId = 0;
          v29 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, DWORD *))(*(_QWORD *)pv + 24LL))(
                  pv,
                  &IIS_AccWrapBase_GetIUnknown,
                  &IID_IUnknown,
                  dwProcessId);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
          if ( !v29 )
          {
            if ( *(_QWORD *)dwProcessId )
            {
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)dwProcessId + 16LL))(*(_QWORD *)dwProcessId);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
              goto LABEL_39;
            }
          }
        }
      }
      v27 = ((__int64 (__fastcall *)(AccWrap_Annotate *, __int64, __int64))(*this)[29])(
              (AccWrap_Annotate *)this,
              v27,
              1);
      if ( v27 )
      {
LABEL_39:
        NumberOfBytesRead[0] = 0;
        (**(__int64 (__fastcall ***)(__int64, GUID *, SIZE_T *))v27)(v27, &IID_IDispatch, NumberOfBytesRead);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        ((void (__fastcall *)(_QWORD))(*a2)->lpVtbl->Release)(*a2);
        *a2 = (struct IDispatch *)NumberOfBytesRead[0];
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d850  push    rbp
0x18000d852  push    rsi
0x18000d853  push    r13
0x18000d855  push    r14
0x18000d857  lea     rbp, [rsp-68h]
0x18000d85c  sub     rsp, 168h
0x18000d863  movaps  [rsp+180h+var_40], xmm6
0x18000d86b  mov     rax, cs:__security_cookie
0x18000d872  xor     rax, rsp
0x18000d875  mov     [rbp+80h+var_50], rax
0x18000d879  movups  xmm6, xmmword ptr cs:PROPID_ACC_PARENT.Data1
0x18000d880  xor     eax, eax
0x18000d882  xor     r14d, r14d
0x18000d885  xorps   xmm0, xmm0
0x18000d888  mov     r13, rdx
0x18000d88b  mov     rsi, rcx
0x18000d88e  mov     qword ptr [rbp+80h+pvarg+10h], rax
0x18000d892  movups  xmmword ptr [rbp+80h+pvarg], xmm0
0x18000d896  cmp     [rcx+88h], eax
0x18000d89c  jnz     short loc_18000D8DB
0x18000d89e  mov     rax, [rcx]
0x18000d8a1  lea     r8, [rsp+180h+NumberOfBytesRead]
0x18000d8a6  lea     rdx, IID_IAccIdentity
0x18000d8ad  mov     [rsp+180h+NumberOfBytesRead], r14
0x18000d8b2  mov     rax, [rax]
0x18000d8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ba  test    eax, eax
0x18000d8bc  jnz     short loc_18000D8DB
0x18000d8be  mov     rcx, [rsp+180h+NumberOfBytesRead]
0x18000d8c3  test    rcx, rcx
0x18000d8c6  jz      short loc_18000D8DB
0x18000d8c8  mov     [rsi+90h], rcx
0x18000d8cf  mov     rax, [rcx]
0x18000d8d2  mov     rax, [rax+10h]
0x18000d8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8db  mov     rcx, [rsi+90h]
0x18000d8e2  mov     [rsp+180h+arg_10], rbx
0x18000d8ea  mov     [rsp+180h+var_20], rdi
0x18000d8f2  mov     [rsp+180h+var_28], r12
0x18000d8fa  mov     dword ptr [rsi+88h], 1
0x18000d904  test    rcx, rcx
0x18000d907  jz      loc_18000DBED
0x18000d90d  mov     [rsp+180h+pv], r14
0x18000d912  lea     r9, [rsp+180h+var_120]
0x18000d917  mov     [rsp+180h+var_120], r14d
0x18000d91c  lea     r8, [rsp+180h+pv]
0x18000d921  mov     rax, [rcx]
0x18000d924  xor     edx, edx
0x18000d926  mov     rax, [rax+18h]
0x18000d92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92f  test    eax, eax
0x18000d931  jnz     loc_18000DBED
0x18000d937  mov     r12, [rsp+180h+pv]
0x18000d93c  test    r12, r12
0x18000d93f  jz      loc_18000DBED
0x18000d945  mov     r11d, [rsp+180h+var_120]
0x18000d94a  mov     edx, r14d
0x18000d94d  movdqa  xmmword ptr [rsp+180h+NumberOfBytesRead], xmm6
0x18000d953  mov     r9, [rsp+180h+NumberOfBytesRead+8]
0x18000d958  mov     r10, [rsp+180h+NumberOfBytesRead]
0x18000d95d  mov     [rsp+180h+var_30], r15
0x18000d965  lea     r15, __ImageBase
0x18000d96c  mov     [rsp+180h+var_12C], r11d
0x18000d971  cmp     edx, 0Ch
0x18000d974  jnb     short loc_18000D9B3
0x18000d976  movsxd  rax, edx
0x18000d979  lea     rcx, [rax+rax*2]
0x18000d97d  lea     r8, ds:0[rcx*8]
0x18000d985  mov     rcx, [r8+r15+4CAA0h]
0x18000d98d  mov     rax, [rcx]
0x18000d990  sub     rax, r10
0x18000d993  jnz     short loc_18000D99C
0x18000d995  mov     rax, [rcx+8]
0x18000d999  sub     rax, r9
0x18000d99c  test    rax, rax
0x18000d99f  jnz     loc_18000DD36
0x18000d9a5  lfence
0x18000d9a8  mov     rax, [r8+r15+4CAA8h]
0x18000d9b0  movups  xmm6, xmmword ptr [rax]
0x18000d9b3  lea     rdi, [r12+4]
0x18000d9b8  cmp     r11d, 10h
0x18000d9bc  jnz     loc_18000DE97
0x18000d9c2  mov     eax, [r12]
0x18000d9c6  cmp     eax, 80000001h
0x18000d9cb  jnz     loc_18000DD4B
0x18000d9d1  movsxd  r14, dword ptr [rdi]
0x18000d9d4  test    r14, r14
0x18000d9d7  jz      loc_18000DE97
0x18000d9dd  mov     edx, 4Ch ; 'L'; uBytes
0x18000d9e2  mov     ecx, 40h ; '@'; uFlags
0x18000d9e7  call    cs:__imp_LocalAlloc
0x18000d9ed  mov     rbx, rax
0x18000d9f0  test    rax, rax
0x18000d9f3  jz      loc_18000DE9F
0x18000d9f9  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000da01  lea     rcx, [rbx+0Ah]
0x18000da05  movsd   qword ptr [rax], xmm0
0x18000da09  movzx   eax, word ptr cs:aMsaa+8; "_"
0x18000da10  mov     [rbx+8], ax
0x18000da14  cmp     dword ptr [r12], 80000001h
0x18000da1c  jnz     loc_18000DD3D
0x18000da22  mov     word ptr [rcx], 2Ah ; '*'
0x18000da27  lea     rdx, [r12+8]
0x18000da2c  add     rcx, 2
0x18000da30  mov     r8d, 8
0x18000da36  nop     word ptr [rax+rax+00000000h]
0x18000da40  movzx   eax, byte ptr [rdx]
0x18000da43  lea     rcx, [rcx+4]
0x18000da47  shr     rax, 4
0x18000da4b  lea     rdx, [rdx+1]
0x18000da4f  movzx   eax, word ptr ds:rva a0123456789abcd[r15+rax*2]; "0123456789ABCDEF" ...
0x18000da58  mov     [rcx-4], ax
0x18000da5c  movzx   eax, byte ptr [rdx-1]
0x18000da60  and     eax, 0Fh
0x18000da63  movzx   eax, word ptr ds:rva a0123456789abcd[r15+rax*2]; "0123456789ABCDEF" ...
0x18000da6c  mov     [rcx-2], ax
0x18000da70  add     r8d, 0FFFFFFFFh
0x18000da74  jnz     short loc_18000DA40
0x18000da76  xor     eax, eax
0x18000da78  mov     rdx, rbx; lpString
0x18000da7b  mov     [rcx], ax
0x18000da7e  mov     rcx, r14; hWnd
0x18000da81  call    cs:__imp_GetPropW
0x18000da87  mov     rcx, rbx; hMem
0x18000da8a  mov     r15, rax
0x18000da8d  call    cs:__imp_LocalFree
0x18000da93  test    r15, r15
0x18000da96  jz      loc_18000DEA7
0x18000da9c  lea     rdx, [rsp+180h+dwProcessId]; lpdwProcessId
0x18000daa1  mov     [rsp+180h+dwProcessId], 0
0x18000daa9  mov     rcx, r14; hWnd
0x18000daac  call    cs:__imp_GetWindowThreadProcessId
0x18000dab2  mov     r8d, [rsp+180h+dwProcessId]; dwProcessId
0x18000dab7  test    r8d, r8d
0x18000daba  jz      loc_18000DEAF
0x18000dac0  xor     edx, edx; bInheritHandle
0x18000dac2  mov     ecx, 10h; dwDesiredAccess
0x18000dac7  call    cs:__imp_OpenProcess
0x18000dacd  xor     r14d, r14d
0x18000dad0  mov     rbx, rax
0x18000dad3  test    rax, rax
0x18000dad6  jz      loc_18000DDD8
0x18000dadc  lea     rax, [rsp+180h+NumberOfBytesRead]
0x18000dae1  mov     [rsp+180h+Buffer], r14d
0x18000dae6  mov     r9d, 4; nSize
0x18000daec  mov     [rsp+180h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000daf1  lea     r8, [rsp+180h+Buffer]; lpBuffer
0x18000daf6  mov     [rsp+180h+NumberOfBytesRead], r14
0x18000dafb  mov     rdx, r15; lpBaseAddress
0x18000dafe  mov     rcx, rbx; hProcess
0x18000db01  call    cs:__imp_ReadProcessMemory
0x18000db07  test    eax, eax
0x18000db09  jz      loc_18000DDDD
0x18000db0f  cmp     [rsp+180h+NumberOfBytesRead], 4
0x18000db15  jnz     loc_18000DDDD
0x18000db1b  mov     edx, [rsp+180h+Buffer]; uBytes
0x18000db1f  mov     ecx, 40h ; '@'; uFlags
0x18000db24  call    cs:__imp_LocalAlloc
0x18000db2a  mov     r14, rax
0x18000db2d  mov     rcx, rbx; hObject
0x18000db30  test    rax, rax
0x18000db33  jz      loc_18000DEB7
0x18000db39  mov     r9d, [rsp+180h+Buffer]; nSize
0x18000db3e  lea     rax, [rsp+180h+NumberOfBytesRead]
0x18000db43  mov     r8, r14; lpBuffer
0x18000db46  mov     [rsp+180h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000db4b  mov     rdx, r15; lpBaseAddress
0x18000db4e  mov     [rsp+180h+NumberOfBytesRead], 0
0x18000db57  call    cs:__imp_ReadProcessMemory
0x18000db5d  test    eax, eax
0x18000db5f  jz      loc_18000DDC3
0x18000db65  mov     eax, [rsp+180h+Buffer]
0x18000db69  cmp     [rsp+180h+NumberOfBytesRead], rax
0x18000db6e  jnz     loc_18000DDC3
0x18000db74  mov     rcx, rbx; hObject
0x18000db77  call    cs:__imp_CloseHandle
0x18000db7d  mov     eax, [rsp+180h+Buffer]
0x18000db81  lea     rdx, [rbp+80h+var_E8]
0x18000db85  mov     [rbp+80h+var_E0], rax
0x18000db89  mov     r9d, 10h
0x18000db8f  lea     rax, [rbp+80h+pvarg]
0x18000db93  mov     [rbp+80h+var_E8], r14
0x18000db97  mov     qword ptr [rsp+180h+var_150], rax
0x18000db9c  mov     r8, r12
0x18000db9f  lea     rax, [rsp+180h+var_110]
0x18000dba4  mov     dword ptr [rsp+180h+var_158], 0
0x18000dbac  mov     [rsp+180h+lpNumberOfBytesRead], rax
0x18000dbb1  movdqa  xmmword ptr [rsp+180h+var_110.Data1], xmm6
0x18000dbb7  call    ?_ReadPropertyFromEntry@MapReaderMgr@@AEAAHVMemStream@@PEBEKU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_ReadPropertyFromEntry(MemStream,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000dbbc  mov     rcx, r14; hMem
0x18000dbbf  mov     ebx, eax
0x18000dbc1  call    cs:__imp_LocalFree
0x18000dbc7  test    ebx, ebx
0x18000dbc9  jz      loc_18000DEC5
0x18000dbcf  mov     rcx, [rsp+180h+pv]; pv
0x18000dbd4  call    cs:__imp_CoTaskMemFree
0x18000dbda  mov     r15, [rsp+180h+var_30]
0x18000dbe2  test    ebx, ebx
0x18000dbe4  jnz     loc_18000DED2
0x18000dbea  xor     r14d, r14d
0x18000dbed  mov     rcx, [rsi+40h]
0x18000dbf1  mov     rdx, r13
0x18000dbf4  mov     rax, [rcx]
0x18000dbf7  mov     rax, [rax+38h]
0x18000dbfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc00  test    eax, eax
0x18000dc02  jnz     loc_18000DCFC
0x18000dc08  test    r13, r13
0x18000dc0b  jz      loc_18000DCF9
0x18000dc11  mov     rdi, [r13+0]
0x18000dc15  test    rdi, rdi
0x18000dc18  jz      loc_18000DCF9
0x18000dc1e  mov     rax, [rdi]
0x18000dc21  lea     r8, [rsp+180h+pv]
0x18000dc26  lea     rdx, IID_IServiceProvider
0x18000dc2d  mov     [rsp+180h+pv], r14
0x18000dc32  mov     rcx, rdi
0x18000dc35  mov     rax, [rax]
0x18000dc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc3d  test    eax, eax
0x18000dc3f  jnz     short loc_18000DC8D
0x18000dc41  mov     rcx, [rsp+180h+pv]
0x18000dc46  test    rcx, rcx
0x18000dc49  jz      short loc_18000DC8D
0x18000dc4b  mov     qword ptr [rsp+180h+dwProcessId], r14
0x18000dc50  lea     r9, [rsp+180h+dwProcessId]
0x18000dc55  mov     rax, [rcx]
0x18000dc58  lea     r8, IID_IUnknown
0x18000dc5f  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x18000dc66  mov     rax, [rax+18h]
0x18000dc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc6f  mov     rdx, [rsp+180h+pv]
0x18000dc74  mov     ebx, eax
0x18000dc76  mov     rcx, [rdx]
0x18000dc79  mov     rax, [rcx+10h]
0x18000dc7d  mov     rcx, rdx
0x18000dc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc85  test    ebx, ebx
0x18000dc87  jz      loc_18000DD95
0x18000dc8d  mov     rax, [rsi]
0x18000dc90  mov     r8d, 1
0x18000dc96  mov     rdx, rdi
0x18000dc99  mov     rcx, rsi
0x18000dc9c  mov     rax, [rax+0E8h]
0x18000dca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dca8  mov     rdi, rax
0x18000dcab  test    rax, rax
0x18000dcae  jz      short loc_18000DCF9
0x18000dcb0  mov     [rsp+180h+NumberOfBytesRead], r14
0x18000dcb5  lea     r8, [rsp+180h+NumberOfBytesRead]
0x18000dcba  mov     rax, [rdi]
0x18000dcbd  lea     rdx, IID_IDispatch
0x18000dcc4  mov     rcx, rdi
0x18000dcc7  mov     rax, [rax]
0x18000dcca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dccf  mov     rdx, [rdi]
0x18000dcd2  mov     ebx, eax
0x18000dcd4  mov     rcx, rdi
0x18000dcd7  mov     rax, [rdx+10h]
0x18000dcdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dce0  mov     rcx, [r13+0]
0x18000dce4  mov     rdx, [rcx]
0x18000dce7  mov     rax, [rdx+10h]
0x18000dceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf0  mov     rax, [rsp+180h+NumberOfBytesRead]
0x18000dcf5  mov     [r13+0], rax
0x18000dcf9  mov     eax, r14d
0x18000dcfc  mov     r12, [rsp+180h+var_28]
0x18000dd04  mov     rdi, [rsp+180h+var_20]
0x18000dd0c  mov     rbx, [rsp+180h+arg_10]
0x18000dd14  mov     rcx, [rbp+80h+var_50]
0x18000dd18  xor     rcx, rsp; StackCookie
0x18000dd1b  call    __security_check_cookie
0x18000dd20  movaps  xmm6, [rsp+180h+var_40]
0x18000dd28  add     rsp, 168h
0x18000dd2f  pop     r14
0x18000dd31  pop     r13
0x18000dd33  pop     rsi
0x18000dd34  pop     rbp
0x18000dd35  retn
0x18000dd36  inc     edx
0x18000dd38  jmp     loc_18000D971
0x18000dd3d  mov     r8d, 10h
0x18000dd43  mov     rdx, r12
0x18000dd46  jmp     loc_18000DA40
0x18000dd4b  cmp     eax, 80000002h
0x18000dd50  jnz     loc_18000DE97
0x18000dd56  mov     r9d, [rdi]
0x18000dd59  lea     r8, aMsaaDaLx; "MSAA_DA_%lx"
0x18000dd60  mov     edx, 40h ; '@'; BufferCount
0x18000dd65  lea     rcx, [rbp+80h+WindowName]; Buffer
0x18000dd69  call    swprintf_s
0x18000dd6e  cmp     eax, 0FFFFFFFFh
0x18000dd71  jz      loc_18000DE87
0x18000dd77  lea     rdx, [rbp+80h+WindowName]; lpWindowName
0x18000dd7b  lea     rcx, ClassName; "MSAA_DA_Class"
0x18000dd82  call    cs:__imp_FindWindowW
0x18000dd88  mov     r11d, [rsp+180h+var_12C]
0x18000dd8d  mov     r14, rax
0x18000dd90  jmp     loc_18000D9D4
  ... truncated ...
```
