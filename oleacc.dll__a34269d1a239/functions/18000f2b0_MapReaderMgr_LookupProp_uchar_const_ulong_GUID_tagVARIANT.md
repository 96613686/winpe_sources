# MapReaderMgr::LookupProp(uchar const *,ulong,_GUID,tagVARIANT *)

- ea: `0x18000f2b0`
- end: `0x18000f939`
- name: `?LookupProp@MapReaderMgr@@QEAAHPEBEKU_GUID@@PEAUtagVARIANT@@@Z`
- size: `1673`
- prototype: `__int64 __fastcall(GUID *this, const unsigned __int8 *, int, struct _GUID *, struct tagVARIANT *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000d2b0`
- `0x18000d540`
- `0x18000d6e0`
- `0x180046918`
- `0x1800469e0`
- `0x18004731c`

## callees

- `0x18000f2b0`
- `0x18000f940`
- `0x18000fb10`
- `0x18001e4c0`
- `0x18001f024`
- `0x180047fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f91d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f91d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f487`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f802`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f487`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f802`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f4c5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f51b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f83c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f892`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f4c5`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f51b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f83c`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f53b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f635`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f90d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f53b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f635`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f8aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f90d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f44d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f58c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f62c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f7bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f44d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f58c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f62c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f7bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f904`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f3a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f4e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f70e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f85f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f3a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f4e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f70e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f85f`
- `USER32!FindWindowW` at `0x18000f616`
- `USER32!FindWindowW` at `0x18000f616`
- `USER32!GetPropW` at `0x18000f441`
- `USER32!GetPropW` at `0x18000f7b0`
- `USER32!GetPropW` at `0x18000f441`
- `USER32!GetPropW` at `0x18000f7b0`
- `USER32!GetWindowThreadProcessId` at `0x18000f46c`
- `USER32!GetWindowThreadProcessId` at `0x18000f7eb`
- `USER32!GetWindowThreadProcessId` at `0x18000f46c`
- `USER32!GetWindowThreadProcessId` at `0x18000f7eb`

## pseudocode

```c
__int64 __fastcall MapReaderMgr::LookupProp(
        GUID *this,
        const unsigned __int8 *a2,
        int a3,
        struct _GUID *a4,
        struct tagVARIANT *a5)
{
  struct _GUID v5; // xmm0
  struct tagVARIANT *v6; // r15
  int v9; // r11d
  unsigned int v10; // edx
  __int64 v11; // r8
  SIZE_T v12; // rax
  int v13; // r14d
  unsigned int *v14; // rdi
  HWND v15; // rsi
  WCHAR *v16; // rax
  WCHAR *v17; // rbx
  _WORD *v18; // rcx
  const unsigned __int8 *v19; // rdx
  int v20; // r8d
  unsigned __int64 v21; // rax
  HANDLE PropW; // r15
  HANDLE v23; // rbx
  HLOCAL v24; // rsi
  void *v25; // rcx
  struct _GUID v26; // xmm0
  __int64 v27; // rcx
  unsigned int PropertyFromEntry; // ebx
  HWND WindowW; // rax
  struct _GUID v31; // xmm0
  int v32; // eax
  HWND v33; // rsi
  WCHAR *v34; // rax
  WCHAR *v35; // rdi
  _WORD *v36; // rbx
  struct tagVARIANT **p_Buf1; // rdx
  char v38; // cl
  unsigned __int64 v39; // rax
  HANDLE v40; // r14
  HANDLE v41; // rbx
  HLOCAL v42; // rdi
  void *v43; // rcx
  struct _GUID v44; // xmm0
  __int64 v45; // rcx
  unsigned int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  int Buf2; // [rsp+44h] [rbp-BCh] BYREF
  DWORD dwProcessId; // [rsp+48h] [rbp-B8h] BYREF
  SIZE_T NumberOfBytesRead[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct tagVARIANT *Buf1; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v51[2]; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h]
  struct _GUID v54; // [rsp+80h] [rbp-80h] BYREF
  wchar_t WindowName[64]; // [rsp+90h] [rbp-70h] BYREF

  v5 = *a4;
  v6 = a5;
  *(struct _GUID *)NumberOfBytesRead = *a4;
  v9 = a3;
  v10 = 0;
  Buf2 = a3;
  Buf1 = a5;
  while ( v10 < 0xC )
  {
    v11 = 3LL * (int)v10;
    this = off_18004CAA0[v11];
    v12 = *(_QWORD *)&this->Data1 - NumberOfBytesRead[0];
    if ( *(_QWORD *)&this->Data1 == NumberOfBytesRead[0] )
      v12 = *(_QWORD *)this->Data4 - NumberOfBytesRead[1];
    if ( !v12 )
    {
      _mm_lfence();
      v5 = **(GUID **)((char *)&off_18004CAA8 + v11 * 8);
      break;
    }
    ++v10;
  }
  v13 = 8;
  v14 = (unsigned int *)(a2 + 4);
  *a4 = v5;
  if ( v9 != 16 )
    goto LABEL_62;
  if ( *(_DWORD *)a2 == -2147483647 )
  {
    v15 = (HWND)(int)*v14;
  }
  else
  {
    if ( *(_DWORD *)a2 != -2147483646 )
      goto LABEL_62;
    if ( swprintf_s(WindowName, 0x40u, L"MSAA_DA_%lx", *v14) == -1 )
    {
      SetLastError(0x57u);
      v9 = Buf2;
      goto LABEL_62;
    }
    WindowW = FindWindowW(L"MSAA_DA_Class", WindowName);
    v9 = Buf2;
    v15 = WindowW;
  }
  if ( v15 )
  {
    v16 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
    v17 = v16;
    if ( !v16 )
    {
LABEL_35:
      PropertyFromEntry = 0;
      goto LABEL_37;
    }
    v18 = v16 + 5;
    *(_QWORD *)v16 = *(_QWORD *)L"MSAA_";
    v16[4] = aMsaa[4];
    if ( *(_DWORD *)a2 == -2147483647 )
    {
      *v18 = 42;
      v19 = a2 + 8;
      v18 = v16 + 6;
      v20 = 8;
    }
    else
    {
      v20 = 16;
      v19 = a2;
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
    PropW = GetPropW(v15, v17);
    LocalFree(v17);
    if ( !PropW
      || (dwProcessId = 0, GetWindowThreadProcessId(v15, &dwProcessId), !dwProcessId)
      || (v23 = OpenProcess(0x10u, 0, dwProcessId)) == 0 )
    {
LABEL_34:
      v6 = Buf1;
      goto LABEL_35;
    }
    Buffer = 0;
    NumberOfBytesRead[0] = 0;
    if ( ReadProcessMemory(v23, PropW, &Buffer, 4u, NumberOfBytesRead) && NumberOfBytesRead[0] == 4 )
    {
      v24 = LocalAlloc(0x40u, Buffer);
      v25 = v23;
      if ( !v24 )
      {
LABEL_33:
        CloseHandle(v25);
        goto LABEL_34;
      }
      NumberOfBytesRead[0] = 0;
      if ( ReadProcessMemory(v23, PropW, v24, Buffer, NumberOfBytesRead) && NumberOfBytesRead[0] == Buffer )
      {
        CloseHandle(v23);
        v26 = *a4;
        v6 = Buf1;
        v53 = Buffer;
        v52 = v24;
        v54 = v26;
        PropertyFromEntry = MapReaderMgr::_ReadPropertyFromEntry(
                              v27,
                              (__int64 *)&v52,
                              (__int64)a2,
                              0x10u,
                              (__int128 *)&v54,
                              0,
                              Buf1);
        LocalFree(v24);
        if ( PropertyFromEntry )
          return PropertyFromEntry;
        v9 = Buf2;
        goto LABEL_36;
      }
      LocalFree(v24);
    }
    v25 = v23;
    goto LABEL_33;
  }
LABEL_62:
  PropertyFromEntry = 0;
LABEL_36:
  if ( v9 != 16 )
    return PropertyFromEntry;
LABEL_37:
  if ( *(_DWORD *)a2 == -2147483647 && *((_DWORD *)a2 + 3) )
  {
    v32 = *((_DWORD *)a2 + 2);
    v33 = (HWND)(int)*v14;
    LODWORD(Buf1) = -2147483647;
    HIDWORD(Buf1) = (_DWORD)v33;
    v51[0] = v32;
    v51[1] = 0;
    if ( !(_DWORD)v33 )
      return 0;
    v34 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
    v35 = v34;
    if ( !v34 )
      return 0;
    *(_QWORD *)v34 = *(_QWORD *)L"MSAA_";
    v36 = v34 + 5;
    v34[4] = aMsaa[4];
    Buf2 = -2147483647;
    if ( !memcmp_0(&Buf1, &Buf2, 4u) )
    {
      *v36 = 42;
      p_Buf1 = (struct tagVARIANT **)v51;
      v36 = v35 + 6;
    }
    else
    {
      v13 = 16;
      p_Buf1 = &Buf1;
    }
    do
    {
      v38 = *(_BYTE *)p_Buf1;
      v36 += 2;
      v39 = *(unsigned __int8 *)p_Buf1;
      p_Buf1 = (struct tagVARIANT **)((char *)p_Buf1 + 1);
      *(v36 - 2) = a0123456789abcd[v39 >> 4];
      *(v36 - 1) = a0123456789abcd[v38 & 0xF];
      --v13;
    }
    while ( v13 );
    *v36 = 0;
    v40 = GetPropW(v33, v35);
    LocalFree(v35);
    if ( !v40 )
      return 0;
    dwProcessId = 0;
    GetWindowThreadProcessId(v33, &dwProcessId);
    if ( !dwProcessId )
      return 0;
    v41 = OpenProcess(0x10u, 0, dwProcessId);
    if ( !v41 )
      return 0;
    Buffer = 0;
    NumberOfBytesRead[0] = 0;
    if ( ReadProcessMemory(v41, v40, &Buffer, 4u, NumberOfBytesRead) && NumberOfBytesRead[0] == 4 )
    {
      v42 = LocalAlloc(0x40u, Buffer);
      v43 = v41;
      if ( !v42 )
      {
LABEL_60:
        CloseHandle(v43);
        return 0;
      }
      NumberOfBytesRead[0] = 0;
      if ( ReadProcessMemory(v41, v40, v42, Buffer, NumberOfBytesRead) && NumberOfBytesRead[0] == Buffer )
      {
        CloseHandle(v41);
        v44 = *a4;
        v53 = Buffer;
        v52 = v42;
        v54 = v44;
        PropertyFromEntry = MapReaderMgr::_ReadPropertyFromEntry(
                              v45,
                              (__int64 *)&v52,
                              (__int64)a2,
                              0x10u,
                              (__int128 *)&v54,
                              1,
                              v6);
        LocalFree(v42);
        return PropertyFromEntry;
      }
      LocalFree(v42);
    }
    v43 = v41;
    goto LABEL_60;
  }
  if ( *(_DWORD *)a2 == -2147483646 && *((_DWORD *)a2 + 3) )
  {
    v31 = *a4;
    HIDWORD(NumberOfBytesRead[0]) = *v14;
    NumberOfBytesRead[1] = *((unsigned int *)a2 + 2);
    LODWORD(NumberOfBytesRead[0]) = -2147483646;
    v54 = v31;
    return MapReaderMgr::_LookupProp(
             (MapReaderMgr *)this,
             (const unsigned __int8 *)NumberOfBytesRead,
             0x10u,
             a2,
             0x10u,
             &v54,
             1,
             v6);
  }
  return PropertyFromEntry;
}

```

## disassembly

```asm
0x18000f2b0  push    rbp
0x18000f2b2  push    rbx
0x18000f2b3  push    r12
0x18000f2b5  push    r13
0x18000f2b7  push    r14
0x18000f2b9  push    r15
0x18000f2bb  lea     rbp, [rsp-28h]
0x18000f2c0  sub     rsp, 128h
0x18000f2c7  mov     rax, cs:__security_cookie
0x18000f2ce  xor     rax, rsp
0x18000f2d1  mov     [rbp+50h+var_40], rax
0x18000f2d5  movaps  xmm0, xmmword ptr [r9]
0x18000f2d9  lea     rbx, __ImageBase
0x18000f2e0  mov     r15, [rbp+50h+arg_20]
0x18000f2e7  mov     r13, r9
0x18000f2ea  movdqa  xmmword ptr [rsp+150h+NumberOfBytesRead], xmm0
0x18000f2f0  mov     r12, rdx
0x18000f2f3  mov     r9, [rsp+150h+NumberOfBytesRead+8]
0x18000f2f8  mov     r11d, r8d
0x18000f2fb  mov     r10, [rsp+150h+NumberOfBytesRead]
0x18000f300  xor     edx, edx
0x18000f302  mov     [rsp+150h+Buf2], r8d
0x18000f307  mov     [rsp+150h+Buf1], r15
0x18000f30c  nop     dword ptr [rax+00h]
0x18000f310  cmp     edx, 0Ch
0x18000f313  jnb     short loc_18000F352
0x18000f315  movsxd  rax, edx
0x18000f318  lea     rcx, [rax+rax*2]
0x18000f31c  lea     r8, ds:0[rcx*8]
0x18000f324  mov     rcx, [r8+rbx+4CAA0h]
0x18000f32c  mov     rax, [rcx]
0x18000f32f  sub     rax, r10
0x18000f332  jnz     short loc_18000F33B
0x18000f334  mov     rax, [rcx+8]
0x18000f338  sub     rax, r9
0x18000f33b  test    rax, rax
0x18000f33e  jnz     loc_18000F5CA
0x18000f344  lfence
0x18000f347  mov     rax, [r8+rbx+4CAA8h]
0x18000f34f  movups  xmm0, xmmword ptr [rax]
0x18000f352  mov     [rsp+150h+arg_0], rsi
0x18000f35a  mov     r14d, 8
0x18000f360  mov     [rsp+150h+var_30], rdi
0x18000f368  lea     rdi, [r12+4]
0x18000f36d  movaps  xmmword ptr [r13+0], xmm0
0x18000f372  cmp     r11d, 10h
0x18000f376  jnz     loc_18000F928
0x18000f37c  mov     eax, [r12]
0x18000f380  cmp     eax, 80000001h
0x18000f385  jnz     loc_18000F5DF
0x18000f38b  movsxd  rsi, dword ptr [rdi]
0x18000f38e  test    rsi, rsi
0x18000f391  jz      loc_18000F928
0x18000f397  mov     edx, 4Ch ; 'L'; uBytes
0x18000f39c  mov     ecx, 40h ; '@'; uFlags
0x18000f3a1  call    cs:__imp_LocalAlloc
0x18000f3a7  mov     rbx, rax
0x18000f3aa  test    rax, rax
0x18000f3ad  jz      loc_18000F640
0x18000f3b3  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000f3bb  lea     rcx, [rbx+0Ah]
0x18000f3bf  movsd   qword ptr [rax], xmm0
0x18000f3c3  movzx   eax, word ptr cs:aMsaa+8; "_"
0x18000f3ca  mov     [rbx+8], ax
0x18000f3ce  cmp     dword ptr [r12], 80000001h
0x18000f3d6  jnz     loc_18000F5D1
0x18000f3dc  mov     word ptr [rcx], 2Ah ; '*'
0x18000f3e1  lea     rdx, [r12+8]
0x18000f3e6  add     rcx, 2
0x18000f3ea  mov     r8d, r14d
0x18000f3ed  lea     r9, __ImageBase
0x18000f3f4  nop     dword ptr [rax+00h]
0x18000f3f8  nop     dword ptr [rax+rax+00000000h]
0x18000f400  movzx   eax, byte ptr [rdx]
0x18000f403  lea     rcx, [rcx+4]
0x18000f407  shr     rax, 4
0x18000f40b  lea     rdx, [rdx+1]
0x18000f40f  movzx   eax, word ptr ds:rva a0123456789abcd[r9+rax*2]; "0123456789ABCDEF" ...
0x18000f418  mov     [rcx-4], ax
0x18000f41c  movzx   eax, byte ptr [rdx-1]
0x18000f420  and     eax, 0Fh
0x18000f423  movzx   eax, word ptr ds:rva a0123456789abcd[r9+rax*2]; "0123456789ABCDEF" ...
0x18000f42c  mov     [rcx-2], ax
0x18000f430  add     r8d, 0FFFFFFFFh
0x18000f434  jnz     short loc_18000F400
0x18000f436  xor     eax, eax
0x18000f438  mov     rdx, rbx; lpString
0x18000f43b  mov     [rcx], ax
0x18000f43e  mov     rcx, rsi; hWnd
0x18000f441  call    cs:__imp_GetPropW
0x18000f447  mov     rcx, rbx; hMem
0x18000f44a  mov     r15, rax
0x18000f44d  call    cs:__imp_LocalFree
0x18000f453  test    r15, r15
0x18000f456  jz      loc_18000F63B
0x18000f45c  lea     rdx, [rsp+150h+dwProcessId]; lpdwProcessId
0x18000f461  mov     [rsp+150h+dwProcessId], 0
0x18000f469  mov     rcx, rsi; hWnd
0x18000f46c  call    cs:__imp_GetWindowThreadProcessId
0x18000f472  mov     r8d, [rsp+150h+dwProcessId]; dwProcessId
0x18000f477  test    r8d, r8d
0x18000f47a  jz      loc_18000F63B
0x18000f480  xor     edx, edx; bInheritHandle
0x18000f482  mov     ecx, 10h; dwDesiredAccess
0x18000f487  call    cs:__imp_OpenProcess
0x18000f48d  mov     rbx, rax
0x18000f490  test    rax, rax
0x18000f493  jz      loc_18000F63B
0x18000f499  lea     rax, [rsp+150h+NumberOfBytesRead]
0x18000f49e  mov     [rsp+150h+Buffer], 0
0x18000f4a6  mov     r9d, 4; nSize
0x18000f4ac  mov     [rsp+150h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000f4b1  lea     r8, [rsp+150h+Buffer]; lpBuffer
0x18000f4b6  mov     [rsp+150h+NumberOfBytesRead], 0
0x18000f4bf  mov     rdx, r15; lpBaseAddress
0x18000f4c2  mov     rcx, rbx; hProcess
0x18000f4c5  call    cs:__imp_ReadProcessMemory
0x18000f4cb  test    eax, eax
0x18000f4cd  jz      loc_18000F632
0x18000f4d3  cmp     [rsp+150h+NumberOfBytesRead], 4
0x18000f4d9  jnz     loc_18000F632
0x18000f4df  mov     edx, [rsp+150h+Buffer]; uBytes
0x18000f4e3  mov     ecx, 40h ; '@'; uFlags
0x18000f4e8  call    cs:__imp_LocalAlloc
0x18000f4ee  mov     rsi, rax
0x18000f4f1  mov     rcx, rbx; hProcess
0x18000f4f4  test    rax, rax
0x18000f4f7  jz      loc_18000F635
0x18000f4fd  mov     r9d, [rsp+150h+Buffer]; nSize
0x18000f502  lea     rax, [rsp+150h+NumberOfBytesRead]
0x18000f507  mov     r8, rsi; lpBuffer
0x18000f50a  mov     [rsp+150h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000f50f  mov     rdx, r15; lpBaseAddress
0x18000f512  mov     [rsp+150h+NumberOfBytesRead], 0
0x18000f51b  call    cs:__imp_ReadProcessMemory
0x18000f521  test    eax, eax
0x18000f523  jz      loc_18000F629
0x18000f529  mov     eax, [rsp+150h+Buffer]
0x18000f52d  cmp     [rsp+150h+NumberOfBytesRead], rax
0x18000f532  jnz     loc_18000F629
0x18000f538  mov     rcx, rbx; hObject
0x18000f53b  call    cs:__imp_CloseHandle
0x18000f541  mov     eax, [rsp+150h+Buffer]
0x18000f545  lea     rdx, [rsp+150h+var_E0]
0x18000f54a  movaps  xmm0, xmmword ptr [r13+0]
0x18000f54f  mov     r9d, 10h
0x18000f555  mov     r15, [rsp+150h+Buf1]
0x18000f55a  mov     r8, r12
0x18000f55d  mov     [rsp+150h+var_D8], rax
0x18000f562  lea     rax, [rbp+50h+var_D0]
0x18000f566  mov     qword ptr [rsp+150h+var_120], r15
0x18000f56b  mov     dword ptr [rsp+150h+var_128], 0
0x18000f573  mov     [rsp+150h+lpNumberOfBytesRead], rax
0x18000f578  mov     [rsp+150h+var_E0], rsi
0x18000f57d  movdqa  xmmword ptr [rbp+50h+var_D0.Data1], xmm0
0x18000f582  call    ?_ReadPropertyFromEntry@MapReaderMgr@@AEAAHVMemStream@@PEBEKU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_ReadPropertyFromEntry(MemStream,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000f587  mov     rcx, rsi; hMem
0x18000f58a  mov     ebx, eax
0x18000f58c  call    cs:__imp_LocalFree
0x18000f592  test    ebx, ebx
0x18000f594  jz      loc_18000F92F
0x18000f59a  mov     eax, ebx
0x18000f59c  mov     rdi, [rsp+150h+var_30]
0x18000f5a4  mov     rsi, [rsp+150h+arg_0]
0x18000f5ac  mov     rcx, [rbp+50h+var_40]
0x18000f5b0  xor     rcx, rsp; StackCookie
0x18000f5b3  call    __security_check_cookie
0x18000f5b8  add     rsp, 128h
0x18000f5bf  pop     r15
0x18000f5c1  pop     r14
0x18000f5c3  pop     r13
0x18000f5c5  pop     r12
0x18000f5c7  pop     rbx
0x18000f5c8  pop     rbp
0x18000f5c9  retn
0x18000f5ca  inc     edx
0x18000f5cc  jmp     loc_18000F310
0x18000f5d1  mov     r8d, 10h
0x18000f5d7  mov     rdx, r12
0x18000f5da  jmp     loc_18000F3ED
0x18000f5df  cmp     eax, 80000002h
0x18000f5e4  jnz     loc_18000F928
0x18000f5ea  mov     r9d, [rdi]
0x18000f5ed  lea     r8, aMsaaDaLx; "MSAA_DA_%lx"
0x18000f5f4  mov     edx, 40h ; '@'; BufferCount
0x18000f5f9  lea     rcx, [rbp+50h+WindowName]; Buffer
0x18000f5fd  call    swprintf_s
0x18000f602  cmp     eax, 0FFFFFFFFh
0x18000f605  jz      loc_18000F918
0x18000f60b  lea     rdx, [rbp+50h+WindowName]; lpWindowName
0x18000f60f  lea     rcx, ClassName; "MSAA_DA_Class"
0x18000f616  call    cs:__imp_FindWindowW
0x18000f61c  mov     r11d, [rsp+150h+Buf2]
0x18000f621  mov     rsi, rax
0x18000f624  jmp     loc_18000F38E
0x18000f629  mov     rcx, rsi; hMem
0x18000f62c  call    cs:__imp_LocalFree
0x18000f632  mov     rcx, rbx; hObject
0x18000f635  call    cs:__imp_CloseHandle
0x18000f63b  mov     r15, [rsp+150h+Buf1]
0x18000f640  xor     ebx, ebx
0x18000f642  jmp     short loc_18000F64E
0x18000f644  cmp     r11d, 10h
0x18000f648  jnz     loc_18000F59A
0x18000f64e  cmp     dword ptr [r12], 80000001h
0x18000f656  jnz     short loc_18000F660
0x18000f658  cmp     dword ptr [r12+0Ch], 0
0x18000f65e  jnz     short loc_18000F6D9
0x18000f660  cmp     dword ptr [r12], 80000002h
0x18000f668  jnz     loc_18000F59A
0x18000f66e  cmp     dword ptr [r12+0Ch], 0
0x18000f674  jz      loc_18000F59A
0x18000f67a  mov     eax, [rdi]
0x18000f67c  lea     rdx, [rsp+150h+NumberOfBytesRead]; unsigned __int8 *
0x18000f681  movaps  xmm0, xmmword ptr [r13+0]
0x18000f686  mov     r9, r12; unsigned __int8 *
0x18000f689  mov     dword ptr [rsp+150h+NumberOfBytesRead+4], eax
0x18000f68d  mov     r8d, 10h; unsigned int
0x18000f693  mov     eax, [r12+8]
0x18000f698  mov     [rsp+150h+var_118], r15; struct tagVARIANT *
0x18000f69d  mov     dword ptr [rsp+150h+NumberOfBytesRead+8], eax
0x18000f6a1  lea     rax, [rbp+50h+var_D0]
0x18000f6a5  mov     [rsp+150h+var_120], 1; int
0x18000f6ad  mov     [rsp+150h+var_128], rax; struct _GUID *
0x18000f6b2  mov     dword ptr [rsp+150h+lpNumberOfBytesRead], 10h; unsigned int
0x18000f6ba  mov     dword ptr [rsp+150h+NumberOfBytesRead], 80000002h
0x18000f6c2  mov     dword ptr [rsp+150h+NumberOfBytesRead+0Ch], 0
0x18000f6ca  movdqa  xmmword ptr [rbp+50h+var_D0.Data1], xmm0
0x18000f6cf  call    ?_LookupProp@MapReaderMgr@@AEAAHPEBEK0KU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_LookupProp(uchar const *,ulong,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000f6d4  jmp     loc_18000F59C
0x18000f6d9  movsxd  rcx, dword ptr [rdi]
0x18000f6dc  mov     eax, [r12+8]
0x18000f6e1  mov     rsi, rcx
0x18000f6e4  mov     dword ptr [rsp+150h+Buf1], 80000001h
0x18000f6ec  mov     dword ptr [rsp+150h+Buf1+4], ecx
0x18000f6f0  mov     [rsp+150h+var_E8], eax
0x18000f6f4  mov     [rsp+150h+var_E4], 0
0x18000f6fc  test    ecx, ecx
0x18000f6fe  jz      loc_18000F7C7
0x18000f704  mov     edx, 4Ch ; 'L'; uBytes
0x18000f709  mov     ecx, 40h ; '@'; uFlags
0x18000f70e  call    cs:__imp_LocalAlloc
0x18000f714  mov     rdi, rax
0x18000f717  test    rax, rax
0x18000f71a  jz      loc_18000F7C7
0x18000f720  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000f728  lea     rdx, [rsp+150h+Buf2]; Buf2
0x18000f72d  movsd   qword ptr [rax], xmm0
0x18000f731  lea     rcx, [rsp+150h+Buf1]; Buf1
0x18000f736  movzx   eax, word ptr cs:aMsaa+8; "_"
0x18000f73d  lea     rbx, [rdi+0Ah]
0x18000f741  mov     r8d, 4; Size
0x18000f747  mov     [rdi+8], ax
0x18000f74b  mov     [rsp+150h+Buf2], 80000001h
0x18000f753  call    memcmp_0
0x18000f758  test    eax, eax
0x18000f75a  jnz     short loc_18000F7CE
0x18000f75c  mov     word ptr [rbx], 2Ah ; '*'
0x18000f761  lea     rdx, [rsp+150h+var_E8]
0x18000f766  add     rbx, 2
0x18000f76a  lea     r8, __ImageBase
0x18000f771  movzx   ecx, byte ptr [rdx]
0x18000f774  lea     rbx, [rbx+4]
0x18000f778  mov     eax, ecx
0x18000f77a  lea     rdx, [rdx+1]
0x18000f77e  shr     rax, 4
0x18000f782  and     ecx, 0Fh
0x18000f785  movzx   eax, word ptr ds:rva a0123456789abcd[r8+rax*2]; "0123456789ABCDEF" ...
0x18000f78e  mov     [rbx-4], ax
0x18000f792  movzx   eax, word ptr ds:rva a0123456789abcd[r8+rcx*2]; "0123456789ABCDEF" ...
0x18000f79b  mov     [rbx-2], ax
0x18000f79f  add     r14d, 0FFFFFFFFh
0x18000f7a3  jnz     short loc_18000F771
0x18000f7a5  xor     eax, eax
0x18000f7a7  mov     rdx, rdi; lpString
0x18000f7aa  mov     rcx, rsi; hWnd
0x18000f7ad  mov     [rbx], ax
0x18000f7b0  call    cs:__imp_GetPropW
0x18000f7b6  mov     rcx, rdi; hMem
0x18000f7b9  mov     r14, rax
0x18000f7bc  call    cs:__imp_LocalFree
0x18000f7c2  test    r14, r14
0x18000f7c5  jnz     short loc_18000F7DB
0x18000f7c7  xor     ebx, ebx
0x18000f7c9  jmp     loc_18000F59A
0x18000f7ce  mov     r14d, 10h
0x18000f7d4  lea     rdx, [rsp+150h+Buf1]
0x18000f7d9  jmp     short loc_18000F76A
0x18000f7db  lea     rdx, [rsp+150h+dwProcessId]; lpdwProcessId
0x18000f7e0  mov     [rsp+150h+dwProcessId], 0
0x18000f7e8  mov     rcx, rsi; hWnd
0x18000f7eb  call    cs:__imp_GetWindowThreadProcessId
0x18000f7f1  mov     r8d, [rsp+150h+dwProcessId]; dwProcessId
0x18000f7f6  test    r8d, r8d
0x18000f7f9  jz      short loc_18000F7C7
0x18000f7fb  xor     edx, edx; bInheritHandle
0x18000f7fd  mov     ecx, 10h; dwDesiredAccess
0x18000f802  call    cs:__imp_OpenProcess
0x18000f808  mov     rbx, rax
0x18000f80b  test    rax, rax
  ... truncated ...
```
