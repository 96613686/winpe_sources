# MapReaderMgr::_LookupProp(uchar const *,ulong,uchar const *,ulong,_GUID,int,tagVARIANT *)

- ea: `0x18000fb10`
- end: `0x18000fdef`
- name: `?_LookupProp@MapReaderMgr@@AEAAHPEBEK0KU_GUID@@HPEAUtagVARIANT@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(MapReaderMgr *this, const unsigned __int8 *, int, const unsigned __int8 *, unsigned int, struct _GUID *, int, struct tagVARIANT *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000d850`
- `0x18000df00`
- `0x18000e480`
- `0x18000ec30`
- `0x18000f2b0`

## callees

- `0x18000f940`
- `0x18000fb10`
- `0x18001e4c0`
- `0x18001f024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fde4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fde4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000fcbd`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000fcbd`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000fcfb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000fd51`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000fcfb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000fd51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fdd4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fdd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fc14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fdcb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fb7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fd1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fb7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000fd1e`
- `USER32!FindWindowW` at `0x18000fc84`
- `USER32!FindWindowW` at `0x18000fc84`
- `USER32!GetPropW` at `0x18000fc08`
- `USER32!GetPropW` at `0x18000fc08`
- `USER32!GetWindowThreadProcessId` at `0x18000fca2`
- `USER32!GetWindowThreadProcessId` at `0x18000fca2`

## pseudocode

```c
__int64 __fastcall MapReaderMgr::_LookupProp(
        MapReaderMgr *this,
        const unsigned __int8 *a2,
        int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        struct _GUID *a6,
        int a7,
        struct tagVARIANT *a8)
{
  const unsigned __int8 *v9; // rbx
  HWND WindowW; // rsi
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  _WORD *v13; // rcx
  int v14; // edx
  unsigned __int64 v15; // rax
  HANDLE PropW; // rbx
  HANDLE v18; // rdi
  HLOCAL v19; // rsi
  __int128 v20; // xmm0
  __int64 v21; // rcx
  unsigned int v22; // ebx
  unsigned int uBytes; // [rsp+40h] [rbp-E8h] BYREF
  DWORD uBytes_4; // [rsp+44h] [rbp-E4h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v26[2]; // [rsp+50h] [rbp-D8h] BYREF
  __int128 v27; // [rsp+60h] [rbp-C8h] BYREF
  wchar_t Buffer[64]; // [rsp+70h] [rbp-B8h] BYREF

  v9 = a2;
  if ( a3 != 16 )
    return 0;
  if ( *(_DWORD *)a2 == -2147483647 )
  {
    WindowW = (HWND)*((int *)a2 + 1);
  }
  else
  {
    if ( *(_DWORD *)a2 != -2147483646 )
      return 0;
    if ( swprintf_s(Buffer, 0x40u, L"MSAA_DA_%lx", *((int *)a2 + 1)) == -1 )
    {
      SetLastError(0x57u);
      return 0;
    }
    WindowW = FindWindowW(L"MSAA_DA_Class", Buffer);
  }
  if ( !WindowW )
    return 0;
  v11 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
  v12 = v11;
  if ( !v11 )
    return 0;
  *(_QWORD *)v11 = *(_QWORD *)L"MSAA_";
  v11[4] = aMsaa[4];
  v13 = v11 + 5;
  if ( *(_DWORD *)v9 == -2147483647 )
  {
    *v13 = 42;
    v14 = 8;
    v13 = v11 + 6;
    v9 += 8;
  }
  else
  {
    v14 = 16;
  }
  do
  {
    v13 += 2;
    v15 = (unsigned __int64)*v9++ >> 4;
    *(v13 - 2) = a0123456789abcd[v15];
    *(v13 - 1) = a0123456789abcd[*(v9 - 1) & 0xF];
    --v14;
  }
  while ( v14 );
  *v13 = 0;
  PropW = GetPropW(WindowW, v12);
  LocalFree(v12);
  if ( !PropW )
    return 0;
  uBytes_4 = 0;
  GetWindowThreadProcessId(WindowW, &uBytes_4);
  if ( !uBytes_4 )
    return 0;
  v18 = OpenProcess(0x10u, 0, uBytes_4);
  if ( !v18 )
    return 0;
  uBytes = 0;
  NumberOfBytesRead = 0;
  if ( !ReadProcessMemory(v18, PropW, &uBytes, 4u, &NumberOfBytesRead)
    || NumberOfBytesRead != 4
    || (v19 = LocalAlloc(0x40u, uBytes)) == 0 )
  {
LABEL_24:
    CloseHandle(v18);
    return 0;
  }
  NumberOfBytesRead = 0;
  if ( !ReadProcessMemory(v18, PropW, v19, uBytes, &NumberOfBytesRead) || NumberOfBytesRead != uBytes )
  {
    LocalFree(v19);
    goto LABEL_24;
  }
  CloseHandle(v18);
  v20 = (__int128)*a6;
  v26[1] = uBytes;
  v26[0] = (__int64)v19;
  v27 = v20;
  v22 = MapReaderMgr::_ReadPropertyFromEntry(v21, v26, (__int64)a4, a5, &v27, a7, a8);
  LocalFree(v19);
  return v22;
}

```

## disassembly

```asm
0x18000fb10  mov     [rsp+arg_0], rbx
0x18000fb15  push    rbp
0x18000fb16  push    rsi
0x18000fb17  push    rdi
0x18000fb18  push    r14
0x18000fb1a  push    r15
0x18000fb1c  sub     rsp, 100h
0x18000fb23  mov     rax, cs:__security_cookie
0x18000fb2a  xor     rax, rsp
0x18000fb2d  mov     [rsp+128h+var_38], rax
0x18000fb35  mov     r14, [rsp+128h+arg_28]
0x18000fb3d  mov     rbp, r9
0x18000fb40  mov     r15, [rsp+128h+arg_38]
0x18000fb48  mov     rbx, rdx
0x18000fb4b  cmp     r8d, 10h
0x18000fb4f  jnz     loc_18000FC1F
0x18000fb55  mov     eax, [rdx]
0x18000fb57  movsxd  r9, dword ptr [rdx+4]
0x18000fb5b  cmp     eax, 80000001h
0x18000fb60  jnz     loc_18000FC52
0x18000fb66  mov     rsi, r9
0x18000fb69  test    rsi, rsi
0x18000fb6c  jz      loc_18000FC1F
0x18000fb72  mov     edx, 4Ch ; 'L'; uBytes
0x18000fb77  mov     ecx, 40h ; '@'; uFlags
0x18000fb7c  call    cs:__imp_LocalAlloc
0x18000fb82  mov     rdi, rax
0x18000fb85  test    rax, rax
0x18000fb88  jz      loc_18000FC1F
0x18000fb8e  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000fb96  movsd   qword ptr [rax], xmm0
0x18000fb9a  movzx   ecx, word ptr cs:aMsaa+8; "_"
0x18000fba1  mov     [rax+8], cx
0x18000fba5  lea     rcx, [rax+0Ah]
0x18000fba9  cmp     dword ptr [rbx], 80000001h
0x18000fbaf  jnz     loc_18000FC48
0x18000fbb5  mov     word ptr [rcx], 2Ah ; '*'
0x18000fbba  mov     edx, 8
0x18000fbbf  add     rcx, 2
0x18000fbc3  add     rbx, 8
0x18000fbc7  lea     r8, a0123456789abcd; "0123456789ABCDEF"
0x18000fbce  xchg    ax, ax
0x18000fbd0  movzx   eax, byte ptr [rbx]
0x18000fbd3  lea     rcx, [rcx+4]
0x18000fbd7  shr     rax, 4
0x18000fbdb  lea     rbx, [rbx+1]
0x18000fbdf  movzx   eax, word ptr [r8+rax*2]
0x18000fbe4  mov     [rcx-4], ax
0x18000fbe8  movzx   eax, byte ptr [rbx-1]
0x18000fbec  and     eax, 0Fh
0x18000fbef  movzx   eax, word ptr [r8+rax*2]
0x18000fbf4  mov     [rcx-2], ax
0x18000fbf8  add     edx, 0FFFFFFFFh
0x18000fbfb  jnz     short loc_18000FBD0
0x18000fbfd  xor     eax, eax
0x18000fbff  mov     rdx, rdi; lpString
0x18000fc02  mov     [rcx], ax
0x18000fc05  mov     rcx, rsi; hWnd
0x18000fc08  call    cs:__imp_GetPropW
0x18000fc0e  mov     rcx, rdi; hMem
0x18000fc11  mov     rbx, rax
0x18000fc14  call    cs:__imp_LocalFree
0x18000fc1a  test    rbx, rbx
0x18000fc1d  jnz     short loc_18000FC92
0x18000fc1f  xor     eax, eax
0x18000fc21  mov     rcx, [rsp+128h+var_38]
0x18000fc29  xor     rcx, rsp; StackCookie
0x18000fc2c  call    __security_check_cookie
0x18000fc31  mov     rbx, [rsp+128h+arg_0]
0x18000fc39  add     rsp, 100h
0x18000fc40  pop     r15
0x18000fc42  pop     r14
0x18000fc44  pop     rdi
0x18000fc45  pop     rsi
0x18000fc46  pop     rbp
0x18000fc47  retn
0x18000fc48  mov     edx, 10h
0x18000fc4d  jmp     loc_18000FBC7
0x18000fc52  cmp     eax, 80000002h
0x18000fc57  jnz     short loc_18000FC1F
0x18000fc59  lea     r8, aMsaaDaLx; "MSAA_DA_%lx"
0x18000fc60  mov     edx, 40h ; '@'; BufferCount
0x18000fc65  lea     rcx, [rsp+128h+Buffer]; Buffer
0x18000fc6a  call    swprintf_s
0x18000fc6f  cmp     eax, 0FFFFFFFFh
0x18000fc72  jz      loc_18000FDDF
0x18000fc78  lea     rdx, [rsp+128h+Buffer]; lpWindowName
0x18000fc7d  lea     rcx, ClassName; "MSAA_DA_Class"
0x18000fc84  call    cs:__imp_FindWindowW
0x18000fc8a  mov     rsi, rax
0x18000fc8d  jmp     loc_18000FB69
0x18000fc92  lea     rdx, [rsp+128h+uBytes+4]; lpdwProcessId
0x18000fc97  mov     dword ptr [rsp+128h+uBytes+4], 0
0x18000fc9f  mov     rcx, rsi; hWnd
0x18000fca2  call    cs:__imp_GetWindowThreadProcessId
0x18000fca8  mov     r8d, dword ptr [rsp+128h+uBytes+4]; dwProcessId
0x18000fcad  test    r8d, r8d
0x18000fcb0  jz      loc_18000FC1F
0x18000fcb6  xor     edx, edx; bInheritHandle
0x18000fcb8  mov     ecx, 10h; dwDesiredAccess
0x18000fcbd  call    cs:__imp_OpenProcess
0x18000fcc3  mov     rdi, rax
0x18000fcc6  test    rax, rax
0x18000fcc9  jz      loc_18000FC1F
0x18000fccf  lea     rax, [rsp+128h+NumberOfBytesRead]
0x18000fcd4  mov     dword ptr [rsp+128h+uBytes], 0
0x18000fcdc  mov     r9d, 4; nSize
0x18000fce2  mov     [rsp+128h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000fce7  lea     r8, [rsp+128h+uBytes]; lpBuffer
0x18000fcec  mov     [rsp+128h+NumberOfBytesRead], 0
0x18000fcf5  mov     rdx, rbx; lpBaseAddress
0x18000fcf8  mov     rcx, rdi; hProcess
0x18000fcfb  call    cs:__imp_ReadProcessMemory
0x18000fd01  test    eax, eax
0x18000fd03  jz      loc_18000FDD1
0x18000fd09  cmp     [rsp+128h+NumberOfBytesRead], 4
0x18000fd0f  jnz     loc_18000FDD1
0x18000fd15  mov     edx, dword ptr [rsp+128h+uBytes]; uBytes
0x18000fd19  mov     ecx, 40h ; '@'; uFlags
0x18000fd1e  call    cs:__imp_LocalAlloc
0x18000fd24  mov     rsi, rax
0x18000fd27  test    rax, rax
0x18000fd2a  jz      loc_18000FDD1
0x18000fd30  mov     r9d, dword ptr [rsp+128h+uBytes]; nSize
0x18000fd35  lea     rax, [rsp+128h+NumberOfBytesRead]
0x18000fd3a  mov     r8, rsi; lpBuffer
0x18000fd3d  mov     [rsp+128h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000fd42  mov     rdx, rbx; lpBaseAddress
0x18000fd45  mov     [rsp+128h+NumberOfBytesRead], 0
0x18000fd4e  mov     rcx, rdi; hProcess
0x18000fd51  call    cs:__imp_ReadProcessMemory
0x18000fd57  test    eax, eax
0x18000fd59  jz      short loc_18000FDC8
0x18000fd5b  mov     eax, dword ptr [rsp+128h+uBytes]
0x18000fd5f  cmp     [rsp+128h+NumberOfBytesRead], rax
0x18000fd64  jnz     short loc_18000FDC8
0x18000fd66  mov     rcx, rdi; hObject
0x18000fd69  call    cs:__imp_CloseHandle
0x18000fd6f  mov     eax, dword ptr [rsp+128h+uBytes]
0x18000fd73  lea     rdx, [rsp+128h+var_D8]
0x18000fd78  movaps  xmm0, xmmword ptr [r14]
0x18000fd7c  mov     r8, rbp
0x18000fd7f  mov     r9d, [rsp+128h+arg_20]
0x18000fd87  mov     [rsp+128h+var_D0], rax
0x18000fd8c  mov     eax, [rsp+128h+arg_30]
0x18000fd93  mov     [rsp+128h+var_F8], r15
0x18000fd98  mov     [rsp+128h+var_100], eax
0x18000fd9c  lea     rax, [rsp+128h+var_C8]
0x18000fda1  mov     [rsp+128h+lpNumberOfBytesRead], rax
0x18000fda6  mov     [rsp+128h+var_D8], rsi
0x18000fdab  movdqa  [rsp+128h+var_C8], xmm0
0x18000fdb1  call    ?_ReadPropertyFromEntry@MapReaderMgr@@AEAAHVMemStream@@PEBEKU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_ReadPropertyFromEntry(MemStream,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000fdb6  mov     rcx, rsi; hMem
0x18000fdb9  mov     ebx, eax
0x18000fdbb  call    cs:__imp_LocalFree
0x18000fdc1  mov     eax, ebx
0x18000fdc3  jmp     loc_18000FC21
0x18000fdc8  mov     rcx, rsi; hMem
0x18000fdcb  call    cs:__imp_LocalFree
0x18000fdd1  mov     rcx, rdi; hObject
0x18000fdd4  call    cs:__imp_CloseHandle
0x18000fdda  jmp     loc_18000FC1F
0x18000fddf  mov     ecx, 57h ; 'W'; dwErrCode
0x18000fde4  call    cs:__imp_SetLastError
0x18000fdea  jmp     loc_18000FC1F
```
