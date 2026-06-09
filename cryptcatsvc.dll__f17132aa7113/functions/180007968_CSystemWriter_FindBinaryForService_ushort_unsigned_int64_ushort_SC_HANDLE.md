# CSystemWriter::FindBinaryForService(ushort *,unsigned __int64,ushort * *,SC_HANDLE__ *)

- ea: `0x180007968`
- end: `0x180007c02`
- name: `?FindBinaryForService@CSystemWriter@@CAKPEAG_KPEAPEAGPEAUSC_HANDLE__@@@Z`
- size: `666`
- prototype: `unsigned int __fastcall(unsigned __int16 *Src, unsigned __int64, unsigned __int16 **, struct SC_HANDLE__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180007898`

## callees

- `0x180007968`
- `0x18000be40`
- `0x1800215b0`
- `0x1800215d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007a25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800079ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007a46`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007b45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007bd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007a39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007bd9`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180007aca`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180007aca`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800079c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800079c3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007bcb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007bcb`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007a19`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007a66`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007a19`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180007a66`

## string_xrefs

- `0x180007aa7`: `%SystemRoot%\System32\Drivers\`

## pseudocode

```c
__int64 __fastcall CSystemWriter::FindBinaryForService(
        unsigned __int16 *Src,
        __int64 a2,
        unsigned __int16 **a3,
        SC_HANDLE a4)
{
  unsigned __int16 **v4; // rdi
  unsigned __int16 *v6; // r15
  char *v8; // r12
  size_t v9; // r14
  __int64 v10; // r13
  DWORD LastError; // ebx
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  struct _QUERY_SERVICE_CONFIGW *v13; // rbp
  struct _QUERY_SERVICE_CONFIGW *v14; // rax
  WCHAR *lpBinaryPathName; // rbx
  __int64 v16; // rdi
  size_t v17; // rdi
  const wchar_t *v18; // rsi
  unsigned __int64 v19; // rcx
  __int64 v20; // r13
  size_t Size; // [rsp+28h] [rbp-70h]
  const wchar_t *Srca; // [rsp+30h] [rbp-68h]
  SC_HANDLE hService; // [rsp+38h] [rbp-60h]
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-58h] BYREF

  pcbBytesNeeded = 0;
  v4 = a3;
  v6 = Src;
  if ( !Src )
    return 87;
  Size = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  hService = OpenServiceW(a4, Src, 1u);
  if ( hService )
  {
    v12 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, 0x200u);
    v13 = v12;
    if ( !v12 )
    {
LABEL_6:
      LastError = GetLastError();
      goto LABEL_35;
    }
    if ( !QueryServiceConfigW(hService, v12, 0x200u, &pcbBytesNeeded) )
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_35;
      LocalFree(v13);
      v14 = (struct _QUERY_SERVICE_CONFIGW *)LocalAlloc(0x40u, pcbBytesNeeded);
      v13 = v14;
      if ( !v14 || !QueryServiceConfigW(hService, v14, pcbBytesNeeded, &pcbBytesNeeded) )
        goto LABEL_6;
    }
    lpBinaryPathName = v13->lpBinaryPathName;
    if ( !lpBinaryPathName )
    {
      LastError = 87;
      goto LABEL_35;
    }
    v16 = -1;
    do
      ++v16;
    while ( lpBinaryPathName[v16] );
    v17 = 2 * v16;
    if ( !v17 )
    {
      v9 = 60;
      v17 = 2 * a2;
      Srca = L".SYS";
      v18 = L"%SystemRoot%\\System32\\Drivers\\";
      v10 = 8;
      Size = 8;
LABEL_22:
      v19 = v17 + v10 + v9 + 2;
      v20 = (unsigned __int16)v19;
      if ( (unsigned __int16)v19 < v19 )
      {
        LastError = 234;
LABEL_32:
        v4 = a3;
        goto LABEL_35;
      }
      v8 = (char *)LocalAlloc(0, (unsigned __int16)v19);
      if ( v8 )
      {
        LastError = 0;
        if ( v18 )
          memcpy_0(v8, v18, v9);
        if ( v17 )
          memcpy_0(&v8[v9], v6, v17);
        if ( Size )
          memcpy_0(&v8[v17 + v9], Srca, Size);
        *(_WORD *)&v8[2 * ((unsigned __int64)(v20 - 2) >> 1)] = 0;
        goto LABEL_32;
      }
      v4 = a3;
      LastError = 1450;
      *a3 = 0;
LABEL_35:
      CloseServiceHandle(hService);
      if ( v13 )
        LocalFree(v13);
      goto LABEL_37;
    }
    v6 = v13->lpBinaryPathName;
    Srca = 0;
    if ( *lpBinaryPathName == 92 )
    {
      CharLowerW(lpBinaryPathName);
      v18 = 0;
      if ( !wcsncmp_0(lpBinaryPathName, L"\\??\\", 4u) )
      {
        v6 = lpBinaryPathName + 4;
        v17 -= 8LL;
        goto LABEL_22;
      }
      if ( wcsncmp_0(lpBinaryPathName, L"\\systemroot\\", 0xCu) )
        goto LABEL_22;
      v6 = lpBinaryPathName + 12;
      v17 -= 24LL;
    }
    v9 = 26;
    v18 = L"%SystemRoot%\\";
    goto LABEL_22;
  }
  LastError = GetLastError();
LABEL_37:
  *v4 = (unsigned __int16 *)v8;
  return LastError;
}

```

## disassembly

```asm
0x180007968  push    rbx
0x18000796a  push    rbp
0x18000796b  push    rsi
0x18000796c  push    rdi
0x18000796d  push    r12
0x18000796f  push    r13
0x180007971  push    r14
0x180007973  push    r15
0x180007975  sub     rsp, 58h
0x180007979  mov     rax, cs:__security_cookie
0x180007980  xor     rax, rsp
0x180007983  mov     [rsp+98h+var_50], rax
0x180007988  xor     ebp, ebp
0x18000798a  mov     [rsp+98h+var_78], r8
0x18000798f  mov     [rsp+98h+pcbBytesNeeded], ebp
0x180007993  mov     rdi, r8
0x180007996  mov     rsi, rdx
0x180007999  mov     r15, rcx
0x18000799c  test    rcx, rcx
0x18000799f  jnz     short loc_1800079A9
0x1800079a1  lea     eax, [rcx+57h]
0x1800079a4  jmp     loc_180007BE4
0x1800079a9  mov     rdx, rcx; lpServiceName
0x1800079ac  mov     [rsp+98h+Size], rbp
0x1800079b1  mov     rcx, r9; hSCManager
0x1800079b4  mov     r8d, 1; dwDesiredAccess
0x1800079ba  mov     r12, rbp
0x1800079bd  mov     r14, rbp
0x1800079c0  mov     r13, rbp
0x1800079c3  call    cs:__imp_OpenServiceW
0x1800079c9  mov     [rsp+98h+hService], rax
0x1800079ce  mov     rbx, rax
0x1800079d1  test    rax, rax
0x1800079d4  jnz     short loc_1800079E3
0x1800079d6  call    cs:__imp_GetLastError
0x1800079dc  mov     ebx, eax
0x1800079de  jmp     loc_180007BDF
0x1800079e3  mov     edx, 200h; uBytes
0x1800079e8  mov     ecx, 40h ; '@'; uFlags
0x1800079ed  call    cs:__imp_LocalAlloc
0x1800079f3  mov     rbp, rax
0x1800079f6  test    rax, rax
0x1800079f9  jnz     short loc_180007A08
0x1800079fb  call    cs:__imp_GetLastError
0x180007a01  mov     ebx, eax
0x180007a03  jmp     loc_180007BC6
0x180007a08  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x180007a0d  mov     r8d, 200h; cbBufSize
0x180007a13  mov     rdx, rbp; lpServiceConfig
0x180007a16  mov     rcx, rbx; hService
0x180007a19  call    cs:__imp_QueryServiceConfigW
0x180007a1f  xor     edx, edx
0x180007a21  test    eax, eax
0x180007a23  jnz     short loc_180007A72
0x180007a25  call    cs:__imp_GetLastError
0x180007a2b  mov     ebx, eax
0x180007a2d  cmp     eax, 7Ah ; 'z'
0x180007a30  jnz     loc_180007BC6
0x180007a36  mov     rcx, rbp; hMem
0x180007a39  call    cs:__imp_LocalFree
0x180007a3f  mov     edx, [rsp+98h+pcbBytesNeeded]; uBytes
0x180007a43  lea     ecx, [rbx-3Ah]; uFlags
0x180007a46  call    cs:__imp_LocalAlloc
0x180007a4c  mov     rbp, rax
0x180007a4f  test    rax, rax
0x180007a52  jz      short loc_1800079FB
0x180007a54  mov     r8d, [rsp+98h+pcbBytesNeeded]; cbBufSize
0x180007a59  lea     r9, [rsp+98h+pcbBytesNeeded]; pcbBytesNeeded
0x180007a5e  mov     rcx, [rsp+98h+hService]; hService
0x180007a63  mov     rdx, rax; lpServiceConfig
0x180007a66  call    cs:__imp_QueryServiceConfigW
0x180007a6c  xor     edx, edx
0x180007a6e  test    eax, eax
0x180007a70  jz      short loc_1800079FB
0x180007a72  mov     rbx, [rbp+10h]
0x180007a76  test    rbx, rbx
0x180007a79  jz      loc_180007BC1
0x180007a7f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007a83  inc     rdi
0x180007a86  cmp     [rbx+rdi*2], dx
0x180007a8a  jnz     short loc_180007A83
0x180007a8c  add     rdi, rdi
0x180007a8f  jnz     short loc_180007AB9
0x180007a91  mov     r14d, 3Ch ; '<'
0x180007a97  lea     rdx, aSys; ".SYS"
0x180007a9e  lea     rdi, [rsi+rsi]
0x180007aa2  mov     [rsp+98h+Src], rdx
0x180007aa7  lea     rsi, aSystemrootSyst_1; "%SystemRoot%\\System32\\Drivers\\"
0x180007aae  lea     r13d, [r14-34h]
0x180007ab2  mov     [rsp+98h+Size], r13
0x180007ab7  jmp     short loc_180007B25
0x180007ab9  cmp     word ptr [rbx], 5Ch ; '\'
0x180007abd  mov     r15, rbx
0x180007ac0  mov     [rsp+98h+Src], rdx
0x180007ac5  jnz     short loc_180007B18
0x180007ac7  mov     rcx, rbx; lpsz
0x180007aca  call    cs:__imp_CharLowerW
0x180007ad0  mov     r8d, 4; MaxCount
0x180007ad6  lea     rdx, String2; "\\??\\"
0x180007add  mov     rcx, rbx; String1
0x180007ae0  call    wcsncmp_0
0x180007ae5  xor     edx, edx
0x180007ae7  mov     esi, edx
0x180007ae9  test    eax, eax
0x180007aeb  jnz     short loc_180007AF7
0x180007aed  lea     r15, [rbx+8]
0x180007af1  sub     rdi, 8
0x180007af5  jmp     short loc_180007B25
0x180007af7  mov     r8d, 0Ch; MaxCount
0x180007afd  lea     rdx, aSystemroot_0; "\\systemroot\\"
0x180007b04  mov     rcx, r15; String1
0x180007b07  call    wcsncmp_0
0x180007b0c  test    eax, eax
0x180007b0e  jnz     short loc_180007B25
0x180007b10  add     r15, 18h
0x180007b14  sub     rdi, 18h
0x180007b18  mov     r14d, 1Ah
0x180007b1e  lea     rsi, aSystemroot_1; "%SystemRoot%\\"
0x180007b25  lea     rax, [rdi+r13]
0x180007b29  lea     rcx, [r14+2]
0x180007b2d  add     rcx, rax
0x180007b30  movzx   r13d, cx
0x180007b34  cmp     r13, rcx
0x180007b37  jnb     short loc_180007B40
0x180007b39  mov     ebx, 0EAh
0x180007b3e  jmp     short loc_180007BAB
0x180007b40  mov     rdx, r13; uBytes
0x180007b43  xor     ecx, ecx; uFlags
0x180007b45  call    cs:__imp_LocalAlloc
0x180007b4b  mov     r12, rax
0x180007b4e  xor     eax, eax
0x180007b50  test    r12, r12
0x180007b53  jz      short loc_180007BB2
0x180007b55  mov     ebx, eax
0x180007b57  test    rsi, rsi
0x180007b5a  jz      short loc_180007B6C
0x180007b5c  mov     r8, r14; Size
0x180007b5f  mov     rdx, rsi; Src
0x180007b62  mov     rcx, r12; void *
0x180007b65  call    memcpy_0
0x180007b6a  xor     eax, eax
0x180007b6c  test    rdi, rdi
0x180007b6f  jz      short loc_180007B82
0x180007b71  lea     rcx, [r14+r12]; void *
0x180007b75  mov     r8, rdi; Size
0x180007b78  mov     rdx, r15; Src
0x180007b7b  call    memcpy_0
0x180007b80  xor     eax, eax
0x180007b82  mov     r8, [rsp+98h+Size]; Size
0x180007b87  test    r8, r8
0x180007b8a  jz      short loc_180007B9F
0x180007b8c  mov     rdx, [rsp+98h+Src]; Src
0x180007b91  lea     rcx, [rdi+r14]
0x180007b95  add     rcx, r12; void *
0x180007b98  call    memcpy_0
0x180007b9d  xor     eax, eax
0x180007b9f  lea     rcx, [r13-2]
0x180007ba3  shr     rcx, 1
0x180007ba6  mov     [r12+rcx*2], ax
0x180007bab  mov     rdi, [rsp+98h+var_78]
0x180007bb0  jmp     short loc_180007BC6
0x180007bb2  mov     rdi, [rsp+98h+var_78]
0x180007bb7  mov     ebx, 5AAh
0x180007bbc  mov     [rdi], rax
0x180007bbf  jmp     short loc_180007BC6
0x180007bc1  mov     ebx, 57h ; 'W'
0x180007bc6  mov     rcx, [rsp+98h+hService]; hSCObject
0x180007bcb  call    cs:__imp_CloseServiceHandle
0x180007bd1  test    rbp, rbp
0x180007bd4  jz      short loc_180007BDF
0x180007bd6  mov     rcx, rbp; hMem
0x180007bd9  call    cs:__imp_LocalFree
0x180007bdf  mov     [rdi], r12
0x180007be2  mov     eax, ebx
0x180007be4  mov     rcx, [rsp+98h+var_50]
0x180007be9  xor     rcx, rsp; StackCookie
0x180007bec  call    __security_check_cookie
0x180007bf1  add     rsp, 58h
0x180007bf5  pop     r15
0x180007bf7  pop     r14
0x180007bf9  pop     r13
0x180007bfb  pop     r12
0x180007bfd  pop     rdi
0x180007bfe  pop     rsi
0x180007bff  pop     rbp
0x180007c00  pop     rbx
0x180007c01  retn
```
