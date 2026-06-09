# DhcpOpenDebugFile

- ea: `0x18001c9dc`
- end: `0x18001cead`
- name: `DhcpOpenDebugFile`
- size: `1233`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180025bf4`

## callees

- `0x180002854`
- `0x18000323c`
- `0x1800055ec`
- `0x1800056c0`
- `0x1800058cc`
- `0x180005934`
- `0x18001c9dc`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001cb69`
- `KERNEL32!HeapAlloc` at `0x18001cb69`
- `KERNEL32!CreateDirectoryW` at `0x18001cc71`
- `KERNEL32!CreateDirectoryW` at `0x18001cc71`
- `KERNEL32!GetFileAttributesW` at `0x18001cc44`
- `KERNEL32!GetFileAttributesW` at `0x18001cc44`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001caa9`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001caa9`
- `KERNEL32!GetLastError` at `0x18001cada`
- `KERNEL32!GetLastError` at `0x18001cc59`
- `KERNEL32!GetLastError` at `0x18001cca6`
- `KERNEL32!GetLastError` at `0x18001cada`
- `KERNEL32!GetLastError` at `0x18001cc59`
- `KERNEL32!GetLastError` at `0x18001cca6`
- `KERNEL32!CloseHandle` at `0x18001ca64`
- `KERNEL32!CloseHandle` at `0x18001ca64`
- `KERNEL32!EnterCriticalSection` at `0x18001ca4c`
- `KERNEL32!EnterCriticalSection` at `0x18001cda6`
- `KERNEL32!EnterCriticalSection` at `0x18001ca4c`
- `KERNEL32!EnterCriticalSection` at `0x18001cda6`
- `KERNEL32!LeaveCriticalSection` at `0x18001ca7a`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce11`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce51`
- `KERNEL32!LeaveCriticalSection` at `0x18001ca7a`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce11`
- `KERNEL32!LeaveCriticalSection` at `0x18001ce51`
- `KERNEL32!CreateFileW` at `0x18001cdd8`
- `KERNEL32!CreateFileW` at `0x18001cdd8`
- `KERNEL32!SetFilePointer` at `0x18001ce02`
- `KERNEL32!SetFilePointer` at `0x18001ce02`

## pseudocode

```c
void DhcpOpenDebugFile()
{
  WCHAR *p_Buffer; // rcx
  DWORD LastError; // eax
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // r8
  void *v5; // rax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  signed __int64 v9; // rdx
  WCHAR v10; // ax
  WCHAR *v11; // rax
  DWORD FileAttributesW; // eax
  DWORD v13; // eax
  int v14; // edx
  __int64 v15; // rdx
  wchar_t *p_pszDest; // rcx
  wchar_t v17; // ax
  wchar_t *v18; // rax
  char *v19; // rcx
  WCHAR Buffer; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v21[1006]; // [rsp+4Ah] [rbp-BEh] BYREF
  wchar_t pszDest; // [rsp+438h] [rbp+330h] BYREF
  _BYTE v23[1006]; // [rsp+43Ah] [rbp+332h] BYREF

  Buffer = 0;
  memset_0(v21, 0, 0x3E6u);
  pszDest = 0;
  memset_0(v23, 0, 0x3E6u);
  EnterCriticalSection(&DhcpGlobalDebugFileCritSect);
  if ( DhcpGlobalDebugFileHandle )
  {
    CloseHandle(DhcpGlobalDebugFileHandle);
    DhcpGlobalDebugFileHandle = 0;
  }
  LeaveCriticalSection(&DhcpGlobalDebugFileCritSect);
  p_Buffer = &Buffer;
  if ( DhcpGlobalDebugSharePath )
  {
    v8 = 500;
    v9 = (_BYTE *)DhcpGlobalDebugSharePath - (_BYTE *)&Buffer;
    do
    {
      if ( v8 == -2147483146 )
        break;
      v10 = *(WCHAR *)((char *)p_Buffer + v9);
      if ( !v10 )
        break;
      *p_Buffer++ = v10;
      --v8;
    }
    while ( v8 );
    v11 = p_Buffer - 1;
    if ( v8 )
      v11 = p_Buffer;
    *v11 = 0;
  }
  else
  {
    if ( !GetWindowsDirectoryW(&Buffer, 0x1F4u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, LastError);
      }
      return;
    }
    v2 = -1;
    v3 = -1;
    do
      ++v3;
    while ( *(_WORD *)&v21[2 * v3 - 2] );
    if ( (unsigned __int64)(2 * v3 + 60) > 0x3E8 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v7 = 14;
      goto LABEL_17;
    }
    StringCchCatW(&Buffer, 0x1F4u, L"\\debug\\dhcplog");
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&v21[2 * v4 - 2] );
    v5 = HeapAlloc(gDhcpHeap, 8u, 2 * v4 + 2);
    DhcpGlobalDebugSharePath = v5;
    if ( !v5 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v7 = 15;
      goto LABEL_17;
    }
    do
      ++v2;
    while ( *(_WORD *)&v21[2 * v2 - 2] );
    StringCchCopyW((STRSAFE_LPWSTR)v5, v2 + 1, &Buffer);
  }
  FileAttributesW = GetFileAttributesW(&Buffer);
  if ( FileAttributesW == -1 )
  {
    v13 = GetLastError();
    if ( v13 != 2 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v14 = 17;
LABEL_36:
      WPP_SF_SD(v6[2], v14, (unsigned int)&WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, (unsigned int)&Buffer, v13);
      goto LABEL_56;
    }
    if ( !CreateDirectoryW(&Buffer, 0) )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      LOBYTE(v13) = GetLastError();
      v6 = WPP_GLOBAL_Control;
      v14 = 16;
      goto LABEL_36;
    }
LABEL_44:
    v15 = 500;
    p_pszDest = &pszDest;
    do
    {
      if ( v15 == -2147483146 )
        break;
      v17 = *(wchar_t *)((char *)p_pszDest + (char *)&Buffer - (char *)&pszDest);
      if ( !v17 )
        break;
      *p_pszDest++ = v17;
      --v15;
    }
    while ( v15 );
    v18 = p_pszDest - 1;
    if ( v15 )
      v18 = p_pszDest;
    *v18 = 0;
    StringCchCatW(&Buffer, 0x1F4u, L"\\dhcpssvc.log");
    StringCchCatW(&pszDest, 0x1F4u, L"\\dhcpssvc.bak");
    EnterCriticalSection(&DhcpGlobalDebugFileCritSect);
    v19 = (char *)CreateFileW(&Buffer, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
    DhcpGlobalDebugFileHandle = v19;
    if ( (unsigned __int64)(v19 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SetFilePointer(v19, 0, 0, 2u);
      LeaveCriticalSection(&DhcpGlobalDebugFileCritSect);
      return;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, &Buffer);
    LeaveCriticalSection(&DhcpGlobalDebugFileCritSect);
    goto LABEL_56;
  }
  if ( (FileAttributesW & 0x10) != 0 )
    goto LABEL_44;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_57;
  v7 = 18;
LABEL_17:
  WPP_SF_S(v6[2], v7, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, &Buffer);
LABEL_56:
  v6 = WPP_GLOBAL_Control;
LABEL_57:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
    WPP_SF_(v6[2], 24, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids);
}

```

## disassembly

```asm
0x18001c9dc  mov     rax, rsp
0x18001c9df  mov     [rax+8], rbx
0x18001c9e3  mov     [rax+10h], rsi
0x18001c9e7  mov     [rax+18h], rdi
0x18001c9eb  push    rbp
0x18001c9ec  push    r14
0x18001c9ee  push    r15
0x18001c9f0  lea     rbp, [rax-748h]
0x18001c9f7  sub     rsp, 830h
0x18001c9fe  mov     rax, cs:__security_cookie
0x18001ca05  xor     rax, rsp
0x18001ca08  mov     [rbp+740h+var_20], rax
0x18001ca0f  mov     ebx, 3E6h
0x18001ca14  lea     rcx, [rsp+840h+var_7FE]; void *
0x18001ca19  xor     esi, esi
0x18001ca1b  mov     r8d, ebx; Size
0x18001ca1e  xor     edx, edx; Val
0x18001ca20  mov     [rsp+840h+Buffer], si
0x18001ca25  call    memset_0
0x18001ca2a  mov     r8d, ebx; Size
0x18001ca2d  mov     [rbp+740h+pszDest], si
0x18001ca34  xor     edx, edx; Val
0x18001ca36  lea     rcx, [rbp+740h+var_40E]; void *
0x18001ca3d  call    memset_0
0x18001ca42  lea     r15, DhcpGlobalDebugFileCritSect
0x18001ca49  mov     rcx, r15; lpCriticalSection
0x18001ca4c  call    cs:__imp_EnterCriticalSection
0x18001ca53  nop     dword ptr [rax+rax+00h]
0x18001ca58  mov     rcx, cs:DhcpGlobalDebugFileHandle; hObject
0x18001ca5f  test    rcx, rcx
0x18001ca62  jz      short loc_18001CA77
0x18001ca64  call    cs:__imp_CloseHandle
0x18001ca6b  nop     dword ptr [rax+rax+00h]
0x18001ca70  mov     cs:DhcpGlobalDebugFileHandle, rsi
0x18001ca77  mov     rcx, r15; lpCriticalSection
0x18001ca7a  call    cs:__imp_LeaveCriticalSection
0x18001ca81  nop     dword ptr [rax+rax+00h]
0x18001ca86  mov     rdx, cs:DhcpGlobalDebugSharePath
0x18001ca8d  lea     r14, WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids
0x18001ca94  lea     rcx, [rsp+840h+Buffer]; lpBuffer
0x18001ca99  mov     edi, 1F4h
0x18001ca9e  test    rdx, rdx
0x18001caa1  jnz     loc_18001CC04
0x18001caa7  mov     edx, edi; uSize
0x18001caa9  call    cs:__imp_GetWindowsDirectoryW
0x18001cab0  nop     dword ptr [rax+rax+00h]
0x18001cab5  test    eax, eax
0x18001cab7  jnz     short loc_18001CB06
0x18001cab9  mov     rax, cs:WPP_GLOBAL_Control
0x18001cac0  lea     rbx, WPP_GLOBAL_Control
0x18001cac7  cmp     rax, rbx
0x18001caca  jz      loc_18001CE80
0x18001cad0  test    byte ptr [rax+1Ch], 10h
0x18001cad4  jz      loc_18001CE80
0x18001cada  call    cs:__imp_GetLastError
0x18001cae1  nop     dword ptr [rax+rax+00h]
0x18001cae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caed  mov     edx, 0Dh
0x18001caf2  mov     r9d, eax
0x18001caf5  mov     r8, r14
0x18001caf8  mov     rcx, [rcx+10h]
0x18001cafc  call    WPP_SF_D
0x18001cb01  jmp     loc_18001CE80
0x18001cb06  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001cb0a  lea     rcx, [rsp+840h+Buffer]
0x18001cb0f  mov     rax, rbx
0x18001cb12  inc     rax
0x18001cb15  cmp     [rcx+rax*2], si
0x18001cb19  jnz     short loc_18001CB12
0x18001cb1b  lea     rax, ds:3Ch[rax*2]
0x18001cb23  cmp     rax, 3E8h
0x18001cb29  ja      loc_18001CBDC
0x18001cb2f  lea     r8, aDebugDhcplog; "\\debug\\dhcplog"
0x18001cb36  mov     rdx, rdi; cchDest
0x18001cb39  lea     rcx, [rsp+840h+Buffer]; pszDest
0x18001cb3e  call    StringCchCatW
0x18001cb43  lea     rax, [rsp+840h+Buffer]
0x18001cb48  mov     r8, rbx
0x18001cb4b  inc     r8
0x18001cb4e  cmp     [rax+r8*2], si
0x18001cb53  jnz     short loc_18001CB4B
0x18001cb55  mov     rcx, cs:gDhcpHeap; hHeap
0x18001cb5c  lea     r8, ds:2[r8*2]; dwBytes
0x18001cb64  mov     edx, 8; dwFlags
0x18001cb69  call    cs:__imp_HeapAlloc
0x18001cb70  nop     dword ptr [rax+rax+00h]
0x18001cb75  mov     cs:DhcpGlobalDebugSharePath, rax
0x18001cb7c  test    rax, rax
0x18001cb7f  jnz     short loc_18001CBBB
0x18001cb81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb88  lea     rbx, WPP_GLOBAL_Control
0x18001cb8f  cmp     rcx, rbx
0x18001cb92  jz      loc_18001CE80
0x18001cb98  test    byte ptr [rcx+1Ch], 10h
0x18001cb9c  jz      loc_18001CE64
0x18001cba2  lea     edx, [rax+0Fh]
0x18001cba5  mov     rcx, [rcx+10h]
0x18001cba9  lea     r9, [rsp+840h+Buffer]
0x18001cbae  mov     r8, r14
0x18001cbb1  call    WPP_SF_S
0x18001cbb6  jmp     loc_18001CE5D
0x18001cbbb  lea     rcx, [rsp+840h+Buffer]
0x18001cbc0  inc     rbx
0x18001cbc3  cmp     [rcx+rbx*2], si
0x18001cbc7  jnz     short loc_18001CBC0
0x18001cbc9  lea     rdx, [rbx+1]; cchDest
0x18001cbcd  mov     rcx, rax; pszDest
0x18001cbd0  lea     r8, [rsp+840h+Buffer]; pszSrc
0x18001cbd5  call    StringCchCopyW
0x18001cbda  jmp     short loc_18001CC3F
0x18001cbdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbe3  lea     rbx, WPP_GLOBAL_Control
0x18001cbea  cmp     rcx, rbx
0x18001cbed  jz      loc_18001CE80
0x18001cbf3  test    byte ptr [rcx+1Ch], 10h
0x18001cbf7  jz      loc_18001CE64
0x18001cbfd  mov     edx, 0Eh
0x18001cc02  jmp     short loc_18001CBA5
0x18001cc04  lea     rax, [rsp+840h+Buffer]
0x18001cc09  mov     r8, rdi
0x18001cc0c  sub     rdx, rax
0x18001cc0f  lea     rax, [r8+7FFFFE0Ah]
0x18001cc16  test    rax, rax
0x18001cc19  jz      short loc_18001CC31
0x18001cc1b  movzx   eax, word ptr [rdx+rcx]
0x18001cc1f  test    ax, ax
0x18001cc22  jz      short loc_18001CC31
0x18001cc24  mov     [rcx], ax
0x18001cc27  add     rcx, 2
0x18001cc2b  sub     r8, 1
0x18001cc2f  jnz     short loc_18001CC0F
0x18001cc31  test    r8, r8
0x18001cc34  lea     rax, [rcx-2]
0x18001cc38  cmovnz  rax, rcx
0x18001cc3c  mov     [rax], si
0x18001cc3f  lea     rcx, [rsp+840h+Buffer]; lpFileName
0x18001cc44  call    cs:__imp_GetFileAttributesW
0x18001cc4b  nop     dword ptr [rax+rax+00h]
0x18001cc50  cmp     eax, 0FFFFFFFFh
0x18001cc53  jnz     loc_18001CD00
0x18001cc59  call    cs:__imp_GetLastError
0x18001cc60  nop     dword ptr [rax+rax+00h]
0x18001cc65  cmp     eax, 2
0x18001cc68  jnz     short loc_18001CCD8
0x18001cc6a  xor     edx, edx; lpSecurityAttributes
0x18001cc6c  lea     rcx, [rsp+840h+Buffer]; lpPathName
0x18001cc71  call    cs:__imp_CreateDirectoryW
0x18001cc78  nop     dword ptr [rax+rax+00h]
0x18001cc7d  test    eax, eax
0x18001cc7f  jnz     loc_18001CD2F
0x18001cc85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc8c  lea     rbx, WPP_GLOBAL_Control
0x18001cc93  cmp     rcx, rbx
0x18001cc96  jz      loc_18001CE80
0x18001cc9c  test    byte ptr [rcx+1Ch], 10h
0x18001cca0  jz      loc_18001CE64
0x18001cca6  call    cs:__imp_GetLastError
0x18001ccad  nop     dword ptr [rax+rax+00h]
0x18001ccb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccb9  mov     edx, 10h
0x18001ccbe  mov     rcx, [rcx+10h]
0x18001ccc2  lea     r9, [rsp+840h+Buffer]
0x18001ccc7  mov     r8, r14
0x18001ccca  mov     [rsp+840h+dwCreationDisposition], eax
0x18001ccce  call    WPP_SF_SD
0x18001ccd3  jmp     loc_18001CE5D
0x18001ccd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccdf  lea     rbx, WPP_GLOBAL_Control
0x18001cce6  cmp     rcx, rbx
0x18001cce9  jz      loc_18001CE80
0x18001ccef  test    byte ptr [rcx+1Ch], 10h
0x18001ccf3  jz      loc_18001CE64
0x18001ccf9  mov     edx, 11h
0x18001ccfe  jmp     short loc_18001CCBE
0x18001cd00  test    al, 10h
0x18001cd02  jnz     short loc_18001CD2F
0x18001cd04  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd0b  lea     rbx, WPP_GLOBAL_Control
0x18001cd12  cmp     rcx, rbx
0x18001cd15  jz      loc_18001CE80
0x18001cd1b  test    byte ptr [rcx+1Ch], 10h
0x18001cd1f  jz      loc_18001CE64
0x18001cd25  mov     edx, 12h
0x18001cd2a  jmp     loc_18001CBA5
0x18001cd2f  lea     r8, [rsp+840h+Buffer]
0x18001cd34  mov     rdx, rdi
0x18001cd37  lea     rax, [rbp+740h+pszDest]
0x18001cd3e  sub     r8, rax
0x18001cd41  lea     rcx, [rbp+740h+pszDest]
0x18001cd48  lea     rax, [rdx+7FFFFE0Ah]
0x18001cd4f  test    rax, rax
0x18001cd52  jz      short loc_18001CD6B
0x18001cd54  movzx   eax, word ptr [r8+rcx]
0x18001cd59  test    ax, ax
0x18001cd5c  jz      short loc_18001CD6B
0x18001cd5e  mov     [rcx], ax
0x18001cd61  add     rcx, 2
0x18001cd65  sub     rdx, 1
0x18001cd69  jnz     short loc_18001CD48
0x18001cd6b  test    rdx, rdx
0x18001cd6e  lea     rax, [rcx-2]
0x18001cd72  lea     r8, aDhcpssvcLog; "\\dhcpssvc.log"
0x18001cd79  mov     rdx, rdi; cchDest
0x18001cd7c  cmovnz  rax, rcx
0x18001cd80  lea     rcx, [rsp+840h+Buffer]; pszDest
0x18001cd85  mov     [rax], si
0x18001cd88  call    StringCchCatW
0x18001cd8d  lea     r8, aDhcpssvcBak; "\\dhcpssvc.bak"
0x18001cd94  mov     rdx, rdi; cchDest
0x18001cd97  lea     rcx, [rbp+740h+pszDest]; pszDest
0x18001cd9e  call    StringCchCatW
0x18001cda3  mov     rcx, r15; lpCriticalSection
0x18001cda6  call    cs:__imp_EnterCriticalSection
0x18001cdad  nop     dword ptr [rax+rax+00h]
0x18001cdb2  xor     r9d, r9d; lpSecurityAttributes
0x18001cdb5  mov     [rsp+840h+hTemplateFile], rsi; hTemplateFile
0x18001cdba  mov     [rsp+840h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001cdc2  lea     rcx, [rsp+840h+Buffer]; lpFileName
0x18001cdc7  mov     edx, 40000000h; dwDesiredAccess
0x18001cdcc  mov     [rsp+840h+dwCreationDisposition], 4; dwCreationDisposition
0x18001cdd4  lea     r8d, [r9+3]; dwShareMode
0x18001cdd8  call    cs:__imp_CreateFileW
0x18001cddf  nop     dword ptr [rax+rax+00h]
0x18001cde4  mov     rcx, rax; hFile
0x18001cde7  mov     cs:DhcpGlobalDebugFileHandle, rax
0x18001cdee  dec     rax
0x18001cdf1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001cdf5  ja      short loc_18001CE1F
0x18001cdf7  mov     r9d, 2; dwMoveMethod
0x18001cdfd  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001ce00  xor     edx, edx; lDistanceToMove
0x18001ce02  call    cs:__imp_SetFilePointer
0x18001ce09  nop     dword ptr [rax+rax+00h]
0x18001ce0e  mov     rcx, r15; lpCriticalSection
0x18001ce11  call    cs:__imp_LeaveCriticalSection
0x18001ce18  nop     dword ptr [rax+rax+00h]
0x18001ce1d  jmp     short loc_18001CE80
0x18001ce1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce26  lea     rbx, WPP_GLOBAL_Control
0x18001ce2d  cmp     rcx, rbx
0x18001ce30  jz      short loc_18001CE4E
0x18001ce32  test    byte ptr [rcx+1Ch], 10h
0x18001ce36  jz      short loc_18001CE4E
0x18001ce38  mov     rcx, [rcx+10h]
0x18001ce3c  lea     r9, [rsp+840h+Buffer]
0x18001ce41  mov     edx, 17h
0x18001ce46  mov     r8, r14
0x18001ce49  call    WPP_SF_S
0x18001ce4e  mov     rcx, r15; lpCriticalSection
0x18001ce51  call    cs:__imp_LeaveCriticalSection
0x18001ce58  nop     dword ptr [rax+rax+00h]
0x18001ce5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce64  cmp     rcx, rbx
0x18001ce67  jz      short loc_18001CE80
0x18001ce69  test    byte ptr [rcx+1Ch], 10h
0x18001ce6d  jz      short loc_18001CE80
0x18001ce6f  mov     rcx, [rcx+10h]
0x18001ce73  mov     edx, 18h
0x18001ce78  mov     r8, r14
0x18001ce7b  call    WPP_SF_
0x18001ce80  mov     rcx, [rbp+740h+var_20]
0x18001ce87  xor     rcx, rsp; StackCookie
0x18001ce8a  call    __security_check_cookie
0x18001ce8f  lea     r11, [rsp+840h+var_10]
0x18001ce97  mov     rbx, [r11+20h]
0x18001ce9b  mov     rsi, [r11+28h]
0x18001ce9f  mov     rdi, [r11+30h]
0x18001cea3  mov     rsp, r11
0x18001cea6  pop     r15
0x18001cea8  pop     r14
0x18001ceaa  pop     rbp
0x18001ceab  retn
```
