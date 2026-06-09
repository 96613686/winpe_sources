# ObjectFromLresult

- ea: `0x180006770`
- end: `0x180006c50`
- name: `ObjectFromLresult`
- size: `1248`
- prototype: `HRESULT __stdcall(LONG_PTR lResult, const IID *const riid, WPARAM wParam, void **ppvObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006720`

## callees

- `0x180006770`
- `0x180007700`
- `0x18001e4c0`
- `0x180047fec`
- `0x180047ff8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006b6d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180006b6d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800069b1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006a31`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800069b1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180006a31`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800069cb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006a55`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800069cb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180006a55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006aed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006aed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006b5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006bab`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006ba0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180006ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800067c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006988`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800069e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800067c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006988`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800069e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ae3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006ae3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006a63`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006a63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006a07`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006c32`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006c45`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006c32`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006c45`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006a98`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006a98`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006a78`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006a78`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180006802`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180006802`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000697f`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18000697f`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180006ac8`
- `api-ms-win-core-com-l1-1-0!CoUnmarshalInterface` at `0x180006ac8`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180006aae`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180006aae`
- `USER32!EnumWindows` at `0x180006c0d`
- `USER32!EnumWindows` at `0x180006c0d`

## pseudocode

```c
HRESULT __stdcall ObjectFromLresult(LONG_PTR lResult, const IID *const riid, WPARAM wParam, void **ppvObject)
{
  int CurrentProcessId; // r15d
  int v7; // esi
  char *v8; // rdx
  DWORD v9; // edi
  int v10; // eax
  int v11; // r8d
  int v12; // edi
  int v13; // edi
  char *v14; // rdx
  HANDLE v15; // rbx
  int v16; // ecx
  int v17; // r8d
  int v18; // ebx
  int v19; // ebx
  __int16 *v20; // rdx
  int i; // ecx
  __int16 v22; // r8
  __int16 *v23; // rdx
  int j; // ecx
  __int16 v25; // r8
  int *v26; // rax
  int v27; // ebx
  int v28; // esi
  SIZE_T v29; // rdi
  size_t v30; // rbx
  HLOCAL v31; // rdi
  char *v32; // rax
  const void *v33; // rsi
  HGLOBAL v34; // rax
  void *v35; // rsi
  void *v36; // rax
  int v37; // ebx
  HANDLE ProcessHandleFromHwnd; // rsi
  HANDLE CurrentProcess; // rax
  BOOL v41; // ebx
  HANDLE hFileMappingObject; // [rsp+48h] [rbp-79h] BYREF
  LPSTREAM ppstm; // [rsp+50h] [rbp-71h] BYREF
  __int64 v44; // [rsp+58h] [rbp-69h]
  WCHAR Buffer[5]; // [rsp+68h] [rbp-59h] BYREF
  char v46; // [rsp+72h] [rbp-4Fh] BYREF
  __int16 v47; // [rsp+82h] [rbp-3Fh]
  char v48; // [rsp+84h] [rbp-3Dh] BYREF
  __int16 v49; // [rsp+94h] [rbp-2Dh]
  char v50; // [rsp+96h] [rbp-2Bh] BYREF
  __int16 v51; // [rsp+A6h] [rbp-1Bh]
  char v52; // [rsp+A8h] [rbp-19h] BYREF
  __int16 v53; // [rsp+B8h] [rbp-9h]
  __int16 v54; // [rsp+BAh] [rbp-7h]

  CurrentProcessId = wParam;
  v7 = lResult;
  if ( !ppvObject )
    return -2147467261;
  *ppvObject = 0;
  if ( (int)lResult < 0 )
    return -2147024809;
  if ( wParam == 0xFFFFFFFF )
    CurrentProcessId = GetCurrentProcessId();
  hFileMappingObject = 0;
  if ( HIWORD(v7)
    || !(_WORD)v7
    || GlobalGetAtomNameW(v7, Buffer, 42) != 41
    || memcmp_0(Buffer, L"MSAA:", 0xAu)
    || v47 != 58
    || v49 != 58
    || v51 != 58
    || v53 != 58
    || v54 )
  {
    return -2147467259;
  }
  v8 = &v46;
  v9 = 0;
  v10 = 0;
  while ( v10 < 8 )
  {
    v11 = *(unsigned __int16 *)v8;
    v12 = 16 * v9;
    if ( (unsigned __int16)(v11 - 48) <= 9u )
    {
      v13 = v12 - 48;
      goto LABEL_18;
    }
    if ( (unsigned __int16)(v11 - 65) > 5u )
    {
      if ( (unsigned __int16)(v11 - 97) > 5u )
        return -2147467259;
      v13 = v12 - 87;
LABEL_18:
      v9 = v11 + v13;
      ++v10;
      v8 += 2;
    }
    else
    {
      ++v10;
      v9 = v11 + v12 - 55;
      v8 += 2;
    }
  }
  v14 = &v48;
  LODWORD(v15) = 0;
  v16 = 0;
  while ( v16 < 8 )
  {
    v17 = *(unsigned __int16 *)v14;
    v18 = 16 * (_DWORD)v15;
    if ( (unsigned __int16)(v17 - 48) <= 9u )
    {
      v19 = v18 - 48;
      goto LABEL_25;
    }
    if ( (unsigned __int16)(v17 - 65) > 5u )
    {
      if ( (unsigned __int16)(v17 - 97) > 5u )
        return -2147467259;
      v19 = v18 - 87;
LABEL_25:
      LODWORD(v15) = v17 + v19;
      ++v16;
      v14 += 2;
    }
    else
    {
      ++v16;
      LODWORD(v15) = v17 + v18 - 55;
      v14 += 2;
    }
  }
  v20 = (__int16 *)&v50;
  for ( i = 0; i < 8; ++i )
  {
    v22 = *v20;
    if ( (unsigned __int16)(*v20 - 48) > 9u && (unsigned __int16)(v22 - 65) > 5u && (unsigned __int16)(v22 - 97) > 5u )
      return -2147467259;
    ++v20;
  }
  v23 = (__int16 *)&v52;
  for ( j = 0; j < 8; ++j )
  {
    v25 = *v23;
    if ( (unsigned __int16)(*v23 - 48) > 9u && (unsigned __int16)(v25 - 65) > 5u && (unsigned __int16)(v25 - 97) > 5u )
      return -2147467259;
    ++v23;
  }
  GlobalDeleteAtom(v7);
  v15 = (HANDLE)(int)v15;
  if ( v9 == GetCurrentProcessId() )
  {
    hFileMappingObject = (HANDLE)(int)v15;
    goto LABEL_44;
  }
  ProcessHandleFromHwnd = OpenProcess(0x40u, 0, v9);
  if ( !ProcessHandleFromHwnd )
  {
    ppstm = (LPSTREAM)v9;
    v44 = 0;
    EnumWindows(FindWindowFromProcessEnumWindowsProc, (LPARAM)&ppstm);
    if ( !v44 )
      return -2147467259;
    ProcessHandleFromHwnd = (HANDLE)GetProcessHandleFromHwnd(v44);
    if ( !ProcessHandleFromHwnd )
      return -2147467259;
  }
  CurrentProcess = GetCurrentProcess();
  v41 = DuplicateHandle(ProcessHandleFromHwnd, (HANDLE)(int)v15, CurrentProcess, &hFileMappingObject, 0, 0, 3u);
  CloseHandle(ProcessHandleFromHwnd);
  if ( !v41 )
    return -2147467259;
  v15 = hFileMappingObject;
  if ( !hFileMappingObject )
    return -2147467259;
LABEL_44:
  v26 = (int *)MapViewOfFile(v15, 0xF001Fu, 0, 0, 0x10u);
  if ( !v26 )
    return -2147467259;
  v27 = *v26;
  v28 = v26[2];
  v29 = (unsigned int)v26[3];
  UnmapViewOfFile(v26);
  if ( v27 != -1440944115 || CurrentProcessId && v28 != GetCurrentProcessId() )
    return -2147467259;
  if ( (unsigned int)v29 <= 0x100000 )
  {
    v30 = v29;
    v31 = LocalAlloc(0x40u, v29);
    if ( v31 )
    {
      v32 = (char *)MapViewOfFile(hFileMappingObject, 0xF001Fu, 0, 0, v30 + 16);
      v33 = v32;
      if ( v32 )
      {
        memcpy_0(v31, v32 + 16, v30);
        UnmapViewOfFile(v33);
        v34 = GlobalAlloc(2u, v30);
        v35 = v34;
        if ( !v34 )
        {
          v37 = -2147024882;
          goto LABEL_55;
        }
        v36 = GlobalLock(v34);
        if ( v36 )
        {
          memcpy_0(v36, v31, v30);
          GlobalUnlock(v35);
          ppstm = 0;
          v37 = CreateStreamOnHGlobal(v35, 1, &ppstm);
          if ( v37 < 0 )
          {
            GlobalFree(v35);
          }
          else
          {
            v37 = CoUnmarshalInterface(ppstm, riid, ppvObject);
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
          }
LABEL_55:
          LocalFree(v31);
LABEL_56:
          CloseHandle(hFileMappingObject);
          return v37;
        }
        GlobalFree(v35);
      }
      v37 = -2147467259;
      goto LABEL_55;
    }
    v37 = -2147024882;
    goto LABEL_56;
  }
  v37 = -2147467259;
  CloseHandle(hFileMappingObject);
  return v37;
}

```

## disassembly

```asm
0x180006770  mov     r11, rsp
0x180006773  push    rbp
0x180006774  push    rsi
0x180006775  push    r12
0x180006777  push    r14
0x180006779  push    r15
0x18000677b  lea     rbp, [r11-5Fh]
0x18000677f  sub     rsp, 0F0h
0x180006786  mov     rax, cs:__security_cookie
0x18000678d  xor     rax, rsp
0x180006790  mov     [rbp+57h+var_50], rax
0x180006794  mov     r14, r9
0x180006797  mov     r15, r8
0x18000679a  mov     r12, rdx
0x18000679d  mov     rsi, rcx
0x1800067a0  test    r9, r9
0x1800067a3  jz      loc_180006B3D
0x1800067a9  mov     [r11-40h], r13
0x1800067ad  xor     r13d, r13d
0x1800067b0  mov     [r9], r13
0x1800067b3  test    esi, esi
0x1800067b5  js      loc_180006B4B
0x1800067bb  mov     eax, 0FFFFFFFFh
0x1800067c0  mov     [r11-30h], rbx
0x1800067c4  cmp     r8, rax
0x1800067c7  jnz     short loc_1800067D2
0x1800067c9  call    cs:__imp_GetCurrentProcessId
0x1800067cf  mov     r15d, eax
0x1800067d2  mov     eax, esi
0x1800067d4  mov     [rsp+110h+var_30], rdi
0x1800067dc  shr     eax, 10h
0x1800067df  mov     [rbp+57h+hFileMappingObject], r13
0x1800067e3  test    ax, ax
0x1800067e6  jnz     loc_180006B02
0x1800067ec  test    si, si
0x1800067ef  jz      loc_180006B02
0x1800067f5  mov     r8d, 2Ah ; '*'; nSize
0x1800067fb  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800067ff  movzx   ecx, si; nAtom
0x180006802  call    cs:__imp_GlobalGetAtomNameW
0x180006808  cmp     eax, 29h ; ')'
0x18000680b  jnz     loc_180006B02
0x180006811  mov     r8d, 0Ah; Size
0x180006817  lea     rdx, aMsaa_0; "MSAA:"
0x18000681e  lea     rcx, [rbp+57h+Buffer]; Buf1
0x180006822  call    memcmp_0
0x180006827  test    eax, eax
0x180006829  jnz     loc_180006B02
0x18000682f  cmp     [rbp+57h+var_96], 3Ah ; ':'
0x180006834  jnz     loc_180006B02
0x18000683a  cmp     [rbp+57h+var_84], 3Ah ; ':'
0x18000683f  jnz     loc_180006B02
0x180006845  cmp     [rbp+57h+var_72], 3Ah ; ':'
0x18000684a  jnz     loc_180006B02
0x180006850  cmp     [rbp+57h+var_60], 3Ah ; ':'
0x180006855  jnz     loc_180006B02
0x18000685b  cmp     [rbp+57h+var_5E], r13w
0x180006860  jnz     loc_180006B02
0x180006866  lea     rdx, [rbp+57h+var_A6]
0x18000686a  mov     edi, r13d
0x18000686d  mov     eax, r13d
0x180006870  cmp     eax, 8
0x180006873  jge     short loc_1800068B0
0x180006875  movzx   r8d, word ptr [rdx]
0x180006879  shl     edi, 4
0x18000687c  lea     ecx, [r8-30h]
0x180006880  cmp     cx, 9
0x180006884  ja      short loc_180006894
0x180006886  add     edi, 0FFFFFFD0h
0x180006889  add     edi, r8d
0x18000688c  inc     eax
0x18000688e  add     rdx, 2
0x180006892  jmp     short loc_180006870
0x180006894  lea     ecx, [r8-41h]
0x180006898  cmp     cx, 5
0x18000689c  ja      loc_180006BCB
0x1800068a2  add     edi, 0FFFFFFC9h
0x1800068a5  inc     eax
0x1800068a7  add     edi, r8d
0x1800068aa  add     rdx, 2
0x1800068ae  jmp     short loc_180006870
0x1800068b0  lea     rdx, [rbp+57h+var_94]
0x1800068b4  mov     ebx, r13d
0x1800068b7  mov     ecx, r13d
0x1800068ba  nop     word ptr [rax+rax+00h]
0x1800068c0  cmp     ecx, 8
0x1800068c3  jge     short loc_180006900
0x1800068c5  movzx   r8d, word ptr [rdx]
0x1800068c9  shl     ebx, 4
0x1800068cc  lea     eax, [r8-30h]
0x1800068d0  cmp     ax, 9
0x1800068d4  ja      short loc_1800068E4
0x1800068d6  add     ebx, 0FFFFFFD0h
0x1800068d9  add     ebx, r8d
0x1800068dc  inc     ecx
0x1800068de  add     rdx, 2
0x1800068e2  jmp     short loc_1800068C0
0x1800068e4  lea     eax, [r8-41h]
0x1800068e8  cmp     ax, 5
0x1800068ec  ja      loc_180006BE1
0x1800068f2  add     ebx, 0FFFFFFC9h
0x1800068f5  inc     ecx
0x1800068f7  add     ebx, r8d
0x1800068fa  add     rdx, 2
0x1800068fe  jmp     short loc_1800068C0
0x180006900  lea     rdx, [rbp+57h+var_82]
0x180006904  mov     ecx, r13d
0x180006907  cmp     ecx, 8
0x18000690a  jge     short loc_18000693E
0x18000690c  movzx   r8d, word ptr [rdx]
0x180006910  lea     eax, [r8-30h]
0x180006914  cmp     ax, 9
0x180006918  ja      short loc_180006922
0x18000691a  inc     ecx
0x18000691c  add     rdx, 2
0x180006920  jmp     short loc_180006907
0x180006922  lea     eax, [r8-41h]
0x180006926  cmp     ax, 5
0x18000692a  jbe     short loc_18000691A
0x18000692c  sub     r8w, 61h ; 'a'
0x180006931  cmp     r8w, 5
0x180006936  ja      loc_180006B02
0x18000693c  jmp     short loc_18000691A
0x18000693e  lea     rdx, [rbp+57h+var_70]
0x180006942  mov     ecx, r13d
0x180006945  cmp     ecx, 8
0x180006948  jge     short loc_18000697C
0x18000694a  movzx   r8d, word ptr [rdx]
0x18000694e  lea     eax, [r8-30h]
0x180006952  cmp     ax, 9
0x180006956  ja      short loc_180006960
0x180006958  inc     ecx
0x18000695a  add     rdx, 2
0x18000695e  jmp     short loc_180006945
0x180006960  lea     eax, [r8-41h]
0x180006964  cmp     ax, 5
0x180006968  jbe     short loc_180006958
0x18000696a  sub     r8w, 61h ; 'a'
0x18000696f  cmp     r8w, 5
0x180006974  ja      loc_180006B02
0x18000697a  jmp     short loc_180006958
0x18000697c  movzx   ecx, si; nAtom
0x18000697f  call    cs:__imp_GlobalDeleteAtom
0x180006985  movsxd  rbx, ebx
0x180006988  call    cs:__imp_GetCurrentProcessId
0x18000698e  cmp     edi, eax
0x180006990  jnz     loc_180006B63
0x180006996  mov     [rbp+57h+hFileMappingObject], rbx
0x18000699a  xor     r9d, r9d; dwFileOffsetLow
0x18000699d  mov     [rsp+110h+dwNumberOfBytesToMap], 10h; dwNumberOfBytesToMap
0x1800069a6  xor     r8d, r8d; dwFileOffsetHigh
0x1800069a9  mov     edx, 0F001Fh; dwDesiredAccess
0x1800069ae  mov     rcx, rbx; hFileMappingObject
0x1800069b1  call    cs:__imp_MapViewOfFile
0x1800069b7  test    rax, rax
0x1800069ba  jz      loc_180006B02
0x1800069c0  mov     ebx, [rax]
0x1800069c2  mov     rcx, rax; lpBaseAddress
0x1800069c5  mov     esi, [rax+8]
0x1800069c8  mov     edi, [rax+0Ch]
0x1800069cb  call    cs:__imp_UnmapViewOfFile
0x1800069d1  cmp     ebx, 0AA1CF00Dh
0x1800069d7  jnz     loc_180006B02
0x1800069dd  test    r15d, r15d
0x1800069e0  jz      short loc_1800069F0
0x1800069e2  call    cs:__imp_GetCurrentProcessId
0x1800069e8  cmp     esi, eax
0x1800069ea  jnz     loc_180006B02
0x1800069f0  cmp     edi, 100000h
0x1800069f6  ja      loc_180006B52
0x1800069fc  mov     rdx, rdi; uBytes
0x1800069ff  mov     ecx, 40h ; '@'; uFlags
0x180006a04  mov     rbx, rdi
0x180006a07  call    cs:__imp_LocalAlloc
0x180006a0d  mov     rdi, rax
0x180006a10  test    rax, rax
0x180006a13  jz      loc_180006C25
0x180006a19  mov     rcx, [rbp+57h+hFileMappingObject]; hFileMappingObject
0x180006a1d  lea     rax, [rbx+10h]
0x180006a21  xor     r9d, r9d; dwFileOffsetLow
0x180006a24  mov     [rsp+110h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x180006a29  xor     r8d, r8d; dwFileOffsetHigh
0x180006a2c  mov     edx, 0F001Fh; dwDesiredAccess
0x180006a31  call    cs:__imp_MapViewOfFile
0x180006a37  mov     rsi, rax
0x180006a3a  test    rax, rax
0x180006a3d  jz      loc_180006C38
0x180006a43  lea     rdx, [rax+10h]; Src
0x180006a47  mov     r8, rbx; Size
0x180006a4a  mov     rcx, rdi; void *
0x180006a4d  call    memcpy_0
0x180006a52  mov     rcx, rsi; lpBaseAddress
0x180006a55  call    cs:__imp_UnmapViewOfFile
0x180006a5b  mov     rdx, rbx; dwBytes
0x180006a5e  mov     ecx, 2; uFlags
0x180006a63  call    cs:__imp_GlobalAlloc
0x180006a69  mov     rsi, rax
0x180006a6c  test    rax, rax
0x180006a6f  jz      loc_180006B44
0x180006a75  mov     rcx, rax; hMem
0x180006a78  call    cs:__imp_GlobalLock
0x180006a7e  test    rax, rax
0x180006a81  jz      loc_180006C2F
0x180006a87  mov     r8, rbx; Size
0x180006a8a  mov     rdx, rdi; Src
0x180006a8d  mov     rcx, rax; void *
0x180006a90  call    memcpy_0
0x180006a95  mov     rcx, rsi; hMem
0x180006a98  call    cs:__imp_GlobalUnlock
0x180006a9e  lea     r8, [rbp+57h+ppstm]; ppstm
0x180006aa2  mov     [rbp+57h+ppstm], r13
0x180006aa6  mov     edx, 1; fDeleteOnRelease
0x180006aab  mov     rcx, rsi; hGlobal
0x180006aae  call    cs:__imp_CreateStreamOnHGlobal
0x180006ab4  mov     ebx, eax
0x180006ab6  test    eax, eax
0x180006ab8  js      loc_180006C42
0x180006abe  mov     rcx, [rbp+57h+ppstm]; pStm
0x180006ac2  mov     r8, r14; ppv
0x180006ac5  mov     rdx, r12; riid
0x180006ac8  call    cs:__imp_CoUnmarshalInterface
0x180006ace  mov     rcx, [rbp+57h+ppstm]
0x180006ad2  mov     ebx, eax
0x180006ad4  mov     rax, [rcx]
0x180006ad7  mov     rax, [rax+10h]
0x180006adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae0  mov     rcx, rdi; hMem
0x180006ae3  call    cs:__imp_LocalFree
0x180006ae9  mov     rcx, [rbp+57h+hFileMappingObject]; hObject
0x180006aed  call    cs:__imp_CloseHandle
0x180006af3  jmp     short loc_180006B07
0x180006af5  call    GetProcessHandleFromHwnd
0x180006afa  mov     rsi, rax
0x180006afd  test    rax, rax
0x180006b00  jnz     short loc_180006B7B
0x180006b02  mov     ebx, 80004005h
0x180006b07  mov     rdi, [rsp+110h+var_30]
0x180006b0f  mov     eax, ebx
0x180006b11  mov     rbx, [rsp+0E8h]
0x180006b19  mov     r13, [rsp+110h+var_38]
0x180006b21  mov     rcx, [rbp+57h+var_50]
0x180006b25  xor     rcx, rsp; StackCookie
0x180006b28  call    __security_check_cookie
0x180006b2d  add     rsp, 0F0h
0x180006b34  pop     r15
0x180006b36  pop     r14
0x180006b38  pop     r12
0x180006b3a  pop     rsi
0x180006b3b  pop     rbp
0x180006b3c  retn
0x180006b3d  mov     eax, 80004003h
0x180006b42  jmp     short loc_180006B21
0x180006b44  mov     ebx, 8007000Eh
0x180006b49  jmp     short loc_180006AE0
0x180006b4b  mov     eax, 80070057h
0x180006b50  jmp     short loc_180006B19
0x180006b52  mov     rcx, [rbp+57h+hFileMappingObject]; hObject
0x180006b56  mov     ebx, 80004005h
0x180006b5b  call    cs:__imp_CloseHandle
0x180006b61  jmp     short loc_180006B07
0x180006b63  mov     r8d, edi; dwProcessId
0x180006b66  xor     edx, edx; bInheritHandle
0x180006b68  mov     ecx, 40h ; '@'; dwDesiredAccess
0x180006b6d  call    cs:__imp_OpenProcess
0x180006b73  mov     rsi, rax
0x180006b76  test    rax, rax
0x180006b79  jz      short loc_180006BF7
0x180006b7b  call    cs:__imp_GetCurrentProcess
0x180006b81  mov     dword ptr [rsp+30h], 3; dwOptions
0x180006b89  lea     r9, [rbp+57h+hFileMappingObject]; lpTargetHandle
0x180006b8d  mov     r8, rax; hTargetProcessHandle
0x180006b90  mov     [rsp+110h+bInheritHandle], r13d; bInheritHandle
0x180006b95  mov     rdx, rbx; hSourceHandle
0x180006b98  mov     dword ptr [rsp+110h+dwNumberOfBytesToMap], r13d; dwDesiredAccess
0x180006b9d  mov     rcx, rsi; hSourceProcessHandle
0x180006ba0  call    cs:__imp_DuplicateHandle
0x180006ba6  mov     rcx, rsi; hObject
0x180006ba9  mov     ebx, eax
0x180006bab  call    cs:__imp_CloseHandle
0x180006bb1  test    ebx, ebx
0x180006bb3  jz      loc_180006B02
0x180006bb9  mov     rbx, [rbp+57h+hFileMappingObject]
0x180006bbd  test    rbx, rbx
0x180006bc0  jnz     loc_18000699A
0x180006bc6  jmp     loc_180006B02
0x180006bcb  lea     ecx, [r8-61h]
0x180006bcf  cmp     cx, 5
0x180006bd3  ja      loc_180006B02
0x180006bd9  add     edi, 0FFFFFFA9h
0x180006bdc  jmp     loc_180006889
0x180006be1  lea     eax, [r8-61h]
0x180006be5  cmp     ax, 5
0x180006be9  ja      loc_180006B02
0x180006bef  add     ebx, 0FFFFFFA9h
0x180006bf2  jmp     loc_1800068D9
0x180006bf7  lea     rdx, [rbp+57h+ppstm]; lParam
0x180006bfb  mov     dword ptr [rbp+57h+ppstm+4], r13d
0x180006bff  lea     rcx, ?FindWindowFromProcessEnumWindowsProc@@YAHPEAUHWND__@@_J@Z; lpEnumFunc
0x180006c06  mov     dword ptr [rbp+57h+ppstm], edi
0x180006c09  mov     [rbp+57h+var_C0], r13
  ... truncated ...
```
