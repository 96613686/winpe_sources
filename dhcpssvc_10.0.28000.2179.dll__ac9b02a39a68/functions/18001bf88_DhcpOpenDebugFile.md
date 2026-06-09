# DhcpOpenDebugFile

- ea: `0x18001bf88`
- end: `0x18001c455`
- name: `DhcpOpenDebugFile`
- size: `1229`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180025144`

## callees

- `0x18000282c`
- `0x180003228`
- `0x1800055e8`
- `0x1800056ac`
- `0x1800058bc`
- `0x180005924`
- `0x18001bf88`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18001c111`
- `KERNEL32!HeapAlloc` at `0x18001c111`
- `KERNEL32!CreateDirectoryW` at `0x18001c219`
- `KERNEL32!CreateDirectoryW` at `0x18001c219`
- `KERNEL32!GetFileAttributesW` at `0x18001c1ec`
- `KERNEL32!GetFileAttributesW` at `0x18001c1ec`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001c055`
- `KERNEL32!GetWindowsDirectoryW` at `0x18001c055`
- `KERNEL32!GetLastError` at `0x18001c08a`
- `KERNEL32!GetLastError` at `0x18001c201`
- `KERNEL32!GetLastError` at `0x18001c252`
- `KERNEL32!GetLastError` at `0x18001c08a`
- `KERNEL32!GetLastError` at `0x18001c201`
- `KERNEL32!GetLastError` at `0x18001c252`
- `KERNEL32!CloseHandle` at `0x18001c010`
- `KERNEL32!CloseHandle` at `0x18001c010`
- `KERNEL32!EnterCriticalSection` at `0x18001bff8`
- `KERNEL32!EnterCriticalSection` at `0x18001c34e`
- `KERNEL32!EnterCriticalSection` at `0x18001bff8`
- `KERNEL32!EnterCriticalSection` at `0x18001c34e`
- `KERNEL32!LeaveCriticalSection` at `0x18001c026`
- `KERNEL32!LeaveCriticalSection` at `0x18001c3b9`
- `KERNEL32!LeaveCriticalSection` at `0x18001c3f9`
- `KERNEL32!LeaveCriticalSection` at `0x18001c026`
- `KERNEL32!LeaveCriticalSection` at `0x18001c3b9`
- `KERNEL32!LeaveCriticalSection` at `0x18001c3f9`
- `KERNEL32!CreateFileW` at `0x18001c380`
- `KERNEL32!CreateFileW` at `0x18001c380`
- `KERNEL32!SetFilePointer` at `0x18001c3aa`
- `KERNEL32!SetFilePointer` at `0x18001c3aa`

## pseudocode

```c
void DhcpOpenDebugFile()
{
  WCHAR *p_Buffer; // rcx
  __int64 v1; // rbx
  DWORD LastError; // eax
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // r8
  void *v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r8
  signed __int64 v10; // rdx
  WCHAR v11; // ax
  WCHAR *v12; // rax
  DWORD FileAttributesW; // eax
  DWORD v14; // eax
  __int64 v15; // rbx
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rdx
  wchar_t *p_pszDest; // rcx
  wchar_t v20; // ax
  wchar_t *v21; // rax
  char *v22; // rcx
  WCHAR Buffer; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v24[1006]; // [rsp+4Ah] [rbp-BEh] BYREF
  wchar_t pszDest; // [rsp+438h] [rbp+330h] BYREF
  _BYTE v26[1006]; // [rsp+43Ah] [rbp+332h] BYREF

  Buffer = 0;
  memset_0(v24, 0, 0x3E6u);
  pszDest = 0;
  memset_0(v26, 0, 0x3E6u);
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
    v9 = 500;
    v10 = (_BYTE *)DhcpGlobalDebugSharePath - (_BYTE *)&Buffer;
    do
    {
      if ( v9 == -2147483146 )
        break;
      v11 = *(WCHAR *)((char *)p_Buffer + v10);
      if ( !v11 )
        break;
      *p_Buffer++ = v11;
      --v9;
    }
    while ( v9 );
    v12 = p_Buffer - 1;
    if ( v9 )
      v12 = p_Buffer;
    *v12 = 0;
  }
  else
  {
    if ( !GetWindowsDirectoryW(&Buffer, 0x1F4u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v1 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_D(v1, 13, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, LastError);
      }
      return;
    }
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&v24[2 * v4 - 2] );
    if ( (unsigned __int64)(2 * v4 + 60) > 0x3E8 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v8 = 14;
      goto LABEL_17;
    }
    StringCchCatW(&Buffer, 0x1F4u, L"\\debug\\dhcplog");
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&v24[2 * v5 - 2] );
    v6 = HeapAlloc(gDhcpHeap, 8u, 2 * v5 + 2);
    DhcpGlobalDebugSharePath = v6;
    if ( !v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v8 = 15;
      goto LABEL_17;
    }
    do
      ++v3;
    while ( *(_WORD *)&v24[2 * v3 - 2] );
    StringCchCopyW((STRSAFE_LPWSTR)v6, v3 + 1, &Buffer);
  }
  FileAttributesW = GetFileAttributesW(&Buffer);
  if ( FileAttributesW == -1 )
  {
    v14 = GetLastError();
    if ( v14 != 2 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v16 = 17;
LABEL_36:
      WPP_SF_SD(v17, v16, (unsigned int)&WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, (unsigned int)&Buffer, v14);
      goto LABEL_56;
    }
    if ( !CreateDirectoryW(&Buffer, 0) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_57;
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LOBYTE(v14) = GetLastError();
      v16 = 16;
      LODWORD(v17) = v15;
      goto LABEL_36;
    }
LABEL_44:
    v18 = 500;
    p_pszDest = &pszDest;
    do
    {
      if ( v18 == -2147483146 )
        break;
      v20 = *(wchar_t *)((char *)p_pszDest + (char *)&Buffer - (char *)&pszDest);
      if ( !v20 )
        break;
      *p_pszDest++ = v20;
      --v18;
    }
    while ( v18 );
    v21 = p_pszDest - 1;
    if ( v18 )
      v21 = p_pszDest;
    *v21 = 0;
    StringCchCatW(&Buffer, 0x1F4u, L"\\dhcpssvc.log");
    StringCchCatW(&pszDest, 0x1F4u, L"\\dhcpssvc.bak");
    EnterCriticalSection(&DhcpGlobalDebugFileCritSect);
    v22 = (char *)CreateFileW(&Buffer, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
    DhcpGlobalDebugFileHandle = v22;
    if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      SetFilePointer(v22, 0, 0, 2u);
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
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_57;
  v8 = 18;
LABEL_17:
  WPP_SF_S(v7[2], v8, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids, &Buffer);
LABEL_56:
  v7 = WPP_GLOBAL_Control;
LABEL_57:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_(v7[2], 24, &WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids);
}

```

## disassembly

```asm
0x18001bf88  mov     rax, rsp
0x18001bf8b  mov     [rax+8], rbx
0x18001bf8f  mov     [rax+10h], rsi
0x18001bf93  mov     [rax+18h], rdi
0x18001bf97  push    rbp
0x18001bf98  push    r14
0x18001bf9a  push    r15
0x18001bf9c  lea     rbp, [rax-748h]
0x18001bfa3  sub     rsp, 830h
0x18001bfaa  mov     rax, cs:__security_cookie
0x18001bfb1  xor     rax, rsp
0x18001bfb4  mov     [rbp+740h+var_20], rax
0x18001bfbb  mov     ebx, 3E6h
0x18001bfc0  lea     rcx, [rsp+840h+var_7FE]; void *
0x18001bfc5  xor     esi, esi
0x18001bfc7  mov     r8d, ebx; Size
0x18001bfca  xor     edx, edx; Val
0x18001bfcc  mov     [rsp+840h+Buffer], si
0x18001bfd1  call    memset_0
0x18001bfd6  mov     r8d, ebx; Size
0x18001bfd9  mov     [rbp+740h+pszDest], si
0x18001bfe0  xor     edx, edx; Val
0x18001bfe2  lea     rcx, [rbp+740h+var_40E]; void *
0x18001bfe9  call    memset_0
0x18001bfee  lea     r15, DhcpGlobalDebugFileCritSect
0x18001bff5  mov     rcx, r15; lpCriticalSection
0x18001bff8  call    cs:__imp_EnterCriticalSection
0x18001bfff  nop     dword ptr [rax+rax+00h]
0x18001c004  mov     rcx, cs:DhcpGlobalDebugFileHandle; hObject
0x18001c00b  test    rcx, rcx
0x18001c00e  jz      short loc_18001C023
0x18001c010  call    cs:__imp_CloseHandle
0x18001c017  nop     dword ptr [rax+rax+00h]
0x18001c01c  mov     cs:DhcpGlobalDebugFileHandle, rsi
0x18001c023  mov     rcx, r15; lpCriticalSection
0x18001c026  call    cs:__imp_LeaveCriticalSection
0x18001c02d  nop     dword ptr [rax+rax+00h]
0x18001c032  mov     rdx, cs:DhcpGlobalDebugSharePath
0x18001c039  lea     r14, WPP_2b99184455ee3964bef8c99b4e7a97b8_Traceguids
0x18001c040  lea     rcx, [rsp+840h+Buffer]; lpBuffer
0x18001c045  mov     edi, 1F4h
0x18001c04a  test    rdx, rdx
0x18001c04d  jnz     loc_18001C1AC
0x18001c053  mov     edx, edi; uSize
0x18001c055  call    cs:__imp_GetWindowsDirectoryW
0x18001c05c  nop     dword ptr [rax+rax+00h]
0x18001c061  test    eax, eax
0x18001c063  jnz     short loc_18001C0AE
0x18001c065  mov     rbx, cs:WPP_GLOBAL_Control
0x18001c06c  lea     rdi, WPP_GLOBAL_Control
0x18001c073  cmp     rbx, rdi
0x18001c076  jz      loc_18001C428
0x18001c07c  test    byte ptr [rbx+1Ch], 10h
0x18001c080  jz      loc_18001C428
0x18001c086  mov     rbx, [rbx+10h]
0x18001c08a  call    cs:__imp_GetLastError
0x18001c091  nop     dword ptr [rax+rax+00h]
0x18001c096  mov     edx, 0Dh
0x18001c09b  mov     r8, r14
0x18001c09e  mov     r9d, eax
0x18001c0a1  mov     rcx, rbx
0x18001c0a4  call    WPP_SF_D
0x18001c0a9  jmp     loc_18001C428
0x18001c0ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c0b2  lea     rcx, [rsp+840h+Buffer]
0x18001c0b7  mov     rax, rbx
0x18001c0ba  inc     rax
0x18001c0bd  cmp     [rcx+rax*2], si
0x18001c0c1  jnz     short loc_18001C0BA
0x18001c0c3  lea     rax, ds:3Ch[rax*2]
0x18001c0cb  cmp     rax, 3E8h
0x18001c0d1  ja      loc_18001C184
0x18001c0d7  lea     r8, aDebugDhcplog; "\\debug\\dhcplog"
0x18001c0de  mov     rdx, rdi; cchDest
0x18001c0e1  lea     rcx, [rsp+840h+Buffer]; pszDest
0x18001c0e6  call    StringCchCatW
0x18001c0eb  lea     rax, [rsp+840h+Buffer]
0x18001c0f0  mov     r8, rbx
0x18001c0f3  inc     r8
0x18001c0f6  cmp     [rax+r8*2], si
0x18001c0fb  jnz     short loc_18001C0F3
0x18001c0fd  mov     rcx, cs:gDhcpHeap; hHeap
0x18001c104  lea     r8, ds:2[r8*2]; dwBytes
0x18001c10c  mov     edx, 8; dwFlags
0x18001c111  call    cs:__imp_HeapAlloc
0x18001c118  nop     dword ptr [rax+rax+00h]
0x18001c11d  mov     cs:DhcpGlobalDebugSharePath, rax
0x18001c124  test    rax, rax
0x18001c127  jnz     short loc_18001C163
0x18001c129  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c130  lea     rdi, WPP_GLOBAL_Control
0x18001c137  cmp     rcx, rdi
0x18001c13a  jz      loc_18001C428
0x18001c140  test    byte ptr [rcx+1Ch], 10h
0x18001c144  jz      loc_18001C40C
0x18001c14a  lea     edx, [rax+0Fh]
0x18001c14d  mov     rcx, [rcx+10h]
0x18001c151  lea     r9, [rsp+840h+Buffer]
0x18001c156  mov     r8, r14
0x18001c159  call    WPP_SF_S
0x18001c15e  jmp     loc_18001C405
0x18001c163  lea     rcx, [rsp+840h+Buffer]
0x18001c168  inc     rbx
0x18001c16b  cmp     [rcx+rbx*2], si
0x18001c16f  jnz     short loc_18001C168
0x18001c171  lea     rdx, [rbx+1]; cchDest
0x18001c175  mov     rcx, rax; pszDest
0x18001c178  lea     r8, [rsp+840h+Buffer]; pszSrc
0x18001c17d  call    StringCchCopyW
0x18001c182  jmp     short loc_18001C1E7
0x18001c184  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c18b  lea     rdi, WPP_GLOBAL_Control
0x18001c192  cmp     rcx, rdi
0x18001c195  jz      loc_18001C428
0x18001c19b  test    byte ptr [rcx+1Ch], 10h
0x18001c19f  jz      loc_18001C40C
0x18001c1a5  mov     edx, 0Eh
0x18001c1aa  jmp     short loc_18001C14D
0x18001c1ac  lea     rax, [rsp+840h+Buffer]
0x18001c1b1  mov     r8, rdi
0x18001c1b4  sub     rdx, rax
0x18001c1b7  lea     rax, [r8+7FFFFE0Ah]
0x18001c1be  test    rax, rax
0x18001c1c1  jz      short loc_18001C1D9
0x18001c1c3  movzx   eax, word ptr [rdx+rcx]
0x18001c1c7  test    ax, ax
0x18001c1ca  jz      short loc_18001C1D9
0x18001c1cc  mov     [rcx], ax
0x18001c1cf  add     rcx, 2
0x18001c1d3  sub     r8, 1
0x18001c1d7  jnz     short loc_18001C1B7
0x18001c1d9  test    r8, r8
0x18001c1dc  lea     rax, [rcx-2]
0x18001c1e0  cmovnz  rax, rcx
0x18001c1e4  mov     [rax], si
0x18001c1e7  lea     rcx, [rsp+840h+Buffer]; lpFileName
0x18001c1ec  call    cs:__imp_GetFileAttributesW
0x18001c1f3  nop     dword ptr [rax+rax+00h]
0x18001c1f8  cmp     eax, 0FFFFFFFFh
0x18001c1fb  jnz     loc_18001C2A8
0x18001c201  call    cs:__imp_GetLastError
0x18001c208  nop     dword ptr [rax+rax+00h]
0x18001c20d  cmp     eax, 2
0x18001c210  jnz     short loc_18001C27C
0x18001c212  xor     edx, edx; lpSecurityAttributes
0x18001c214  lea     rcx, [rsp+840h+Buffer]; lpPathName
0x18001c219  call    cs:__imp_CreateDirectoryW
0x18001c220  nop     dword ptr [rax+rax+00h]
0x18001c225  test    eax, eax
0x18001c227  jnz     loc_18001C2D7
0x18001c22d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c234  lea     rdi, WPP_GLOBAL_Control
0x18001c23b  cmp     rcx, rdi
0x18001c23e  jz      loc_18001C428
0x18001c244  test    byte ptr [rcx+1Ch], 10h
0x18001c248  jz      loc_18001C40C
0x18001c24e  mov     rbx, [rcx+10h]
0x18001c252  call    cs:__imp_GetLastError
0x18001c259  nop     dword ptr [rax+rax+00h]
0x18001c25e  mov     edx, 10h
0x18001c263  mov     rcx, rbx
0x18001c266  mov     r8, r14
0x18001c269  mov     [rsp+840h+dwCreationDisposition], eax
0x18001c26d  lea     r9, [rsp+840h+Buffer]
0x18001c272  call    WPP_SF_SD
0x18001c277  jmp     loc_18001C405
0x18001c27c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c283  lea     rdi, WPP_GLOBAL_Control
0x18001c28a  cmp     rcx, rdi
0x18001c28d  jz      loc_18001C428
0x18001c293  test    byte ptr [rcx+1Ch], 10h
0x18001c297  jz      loc_18001C40C
0x18001c29d  mov     rcx, [rcx+10h]
0x18001c2a1  mov     edx, 11h
0x18001c2a6  jmp     short loc_18001C266
0x18001c2a8  test    al, 10h
0x18001c2aa  jnz     short loc_18001C2D7
0x18001c2ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2b3  lea     rdi, WPP_GLOBAL_Control
0x18001c2ba  cmp     rcx, rdi
0x18001c2bd  jz      loc_18001C428
0x18001c2c3  test    byte ptr [rcx+1Ch], 10h
0x18001c2c7  jz      loc_18001C40C
0x18001c2cd  mov     edx, 12h
0x18001c2d2  jmp     loc_18001C14D
0x18001c2d7  lea     r8, [rsp+840h+Buffer]
0x18001c2dc  mov     rdx, rdi
0x18001c2df  lea     rax, [rbp+740h+pszDest]
0x18001c2e6  sub     r8, rax
0x18001c2e9  lea     rcx, [rbp+740h+pszDest]
0x18001c2f0  lea     rax, [rdx+7FFFFE0Ah]
0x18001c2f7  test    rax, rax
0x18001c2fa  jz      short loc_18001C313
0x18001c2fc  movzx   eax, word ptr [rcx+r8]
0x18001c301  test    ax, ax
0x18001c304  jz      short loc_18001C313
0x18001c306  mov     [rcx], ax
0x18001c309  add     rcx, 2
0x18001c30d  sub     rdx, 1
0x18001c311  jnz     short loc_18001C2F0
0x18001c313  test    rdx, rdx
0x18001c316  lea     rax, [rcx-2]
0x18001c31a  lea     r8, aDhcpssvcLog; "\\dhcpssvc.log"
0x18001c321  mov     rdx, rdi; cchDest
0x18001c324  cmovnz  rax, rcx
0x18001c328  lea     rcx, [rsp+840h+Buffer]; pszDest
0x18001c32d  mov     [rax], si
0x18001c330  call    StringCchCatW
0x18001c335  lea     r8, aDhcpssvcBak; "\\dhcpssvc.bak"
0x18001c33c  mov     rdx, rdi; cchDest
0x18001c33f  lea     rcx, [rbp+740h+pszDest]; pszDest
0x18001c346  call    StringCchCatW
0x18001c34b  mov     rcx, r15; lpCriticalSection
0x18001c34e  call    cs:__imp_EnterCriticalSection
0x18001c355  nop     dword ptr [rax+rax+00h]
0x18001c35a  xor     r9d, r9d; lpSecurityAttributes
0x18001c35d  mov     [rsp+840h+hTemplateFile], rsi; hTemplateFile
0x18001c362  mov     [rsp+840h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001c36a  lea     rcx, [rsp+840h+Buffer]; lpFileName
0x18001c36f  mov     edx, 40000000h; dwDesiredAccess
0x18001c374  mov     [rsp+840h+dwCreationDisposition], 4; dwCreationDisposition
0x18001c37c  lea     r8d, [r9+3]; dwShareMode
0x18001c380  call    cs:__imp_CreateFileW
0x18001c387  nop     dword ptr [rax+rax+00h]
0x18001c38c  mov     rcx, rax; hFile
0x18001c38f  mov     cs:DhcpGlobalDebugFileHandle, rax
0x18001c396  dec     rax
0x18001c399  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c39d  ja      short loc_18001C3C7
0x18001c39f  mov     r9d, 2; dwMoveMethod
0x18001c3a5  xor     r8d, r8d; lpDistanceToMoveHigh
0x18001c3a8  xor     edx, edx; lDistanceToMove
0x18001c3aa  call    cs:__imp_SetFilePointer
0x18001c3b1  nop     dword ptr [rax+rax+00h]
0x18001c3b6  mov     rcx, r15; lpCriticalSection
0x18001c3b9  call    cs:__imp_LeaveCriticalSection
0x18001c3c0  nop     dword ptr [rax+rax+00h]
0x18001c3c5  jmp     short loc_18001C428
0x18001c3c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3ce  lea     rdi, WPP_GLOBAL_Control
0x18001c3d5  cmp     rcx, rdi
0x18001c3d8  jz      short loc_18001C3F6
0x18001c3da  test    byte ptr [rcx+1Ch], 10h
0x18001c3de  jz      short loc_18001C3F6
0x18001c3e0  mov     rcx, [rcx+10h]
0x18001c3e4  lea     r9, [rsp+840h+Buffer]
0x18001c3e9  mov     edx, 17h
0x18001c3ee  mov     r8, r14
0x18001c3f1  call    WPP_SF_S
0x18001c3f6  mov     rcx, r15; lpCriticalSection
0x18001c3f9  call    cs:__imp_LeaveCriticalSection
0x18001c400  nop     dword ptr [rax+rax+00h]
0x18001c405  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c40c  cmp     rcx, rdi
0x18001c40f  jz      short loc_18001C428
0x18001c411  test    byte ptr [rcx+1Ch], 10h
0x18001c415  jz      short loc_18001C428
0x18001c417  mov     rcx, [rcx+10h]
0x18001c41b  mov     edx, 18h
0x18001c420  mov     r8, r14
0x18001c423  call    WPP_SF_
0x18001c428  mov     rcx, [rbp+740h+var_20]
0x18001c42f  xor     rcx, rsp; StackCookie
0x18001c432  call    __security_check_cookie
0x18001c437  lea     r11, [rsp+840h+var_10]
0x18001c43f  mov     rbx, [r11+20h]
0x18001c443  mov     rsi, [r11+28h]
0x18001c447  mov     rdi, [r11+30h]
0x18001c44b  mov     rsp, r11
0x18001c44e  pop     r15
0x18001c450  pop     r14
0x18001c452  pop     rbp
0x18001c453  retn
```
