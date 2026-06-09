# UploadFile(ushort *,ushort *,ushort *,ulong *)

- ea: `0x140052688`
- end: `0x1400529e9`
- name: `?UploadFile@@YAJPEAG00PEAK@Z`
- size: `865`
- prototype: `__int64 __fastcall(LPCWSTR lpcwszUrl, LPCWSTR lpFileName, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140052458`

## callees

- `0x140010eb4`
- `0x1400506ac`
- `0x140052688`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x140052747`
- `KERNEL32!GetFileSizeEx` at `0x140052747`
- `KERNEL32!GetLastError` at `0x14005271d`
- `KERNEL32!GetLastError` at `0x140052757`
- `KERNEL32!GetLastError` at `0x140052834`
- `KERNEL32!GetLastError` at `0x14005287a`
- `KERNEL32!GetLastError` at `0x1400528bc`
- `KERNEL32!GetLastError` at `0x14005291a`
- `KERNEL32!GetLastError` at `0x14005271d`
- `KERNEL32!GetLastError` at `0x140052757`
- `KERNEL32!GetLastError` at `0x140052834`
- `KERNEL32!GetLastError` at `0x14005287a`
- `KERNEL32!GetLastError` at `0x1400528bc`
- `KERNEL32!GetLastError` at `0x14005291a`
- `KERNEL32!CloseHandle` at `0x140052990`
- `KERNEL32!CloseHandle` at `0x140052990`
- `KERNEL32!HeapAlloc` at `0x1400527ec`
- `KERNEL32!HeapAlloc` at `0x1400527ec`
- `KERNEL32!HeapFree` at `0x1400529b5`
- `KERNEL32!HeapFree` at `0x1400529b5`
- `KERNEL32!GetProcessHeap` at `0x1400527d2`
- `KERNEL32!GetProcessHeap` at `0x1400529a1`
- `KERNEL32!GetProcessHeap` at `0x1400527d2`
- `KERNEL32!GetProcessHeap` at `0x1400529a1`
- `KERNEL32!CreateFileW` at `0x140052703`
- `KERNEL32!CreateFileW` at `0x140052703`
- `KERNEL32!ReadFile` at `0x140052824`
- `KERNEL32!ReadFile` at `0x140052824`
- `WINHTTP!WinHttpReceiveResponse` at `0x1400528ac`
- `WINHTTP!WinHttpReceiveResponse` at `0x1400528ac`
- `WINHTTP!WinHttpQueryHeaders` at `0x140052906`
- `WINHTTP!WinHttpQueryHeaders` at `0x140052906`
- `WINHTTP!WinHttpCloseHandle` at `0x140052948`
- `WINHTTP!WinHttpCloseHandle` at `0x14005295d`
- `WINHTTP!WinHttpCloseHandle` at `0x140052971`
- `WINHTTP!WinHttpCloseHandle` at `0x140052948`
- `WINHTTP!WinHttpCloseHandle` at `0x14005295d`
- `WINHTTP!WinHttpCloseHandle` at `0x140052971`
- `WINHTTP!WinHttpWriteData` at `0x14005286a`
- `WINHTTP!WinHttpWriteData` at `0x14005286a`

## pseudocode

```c
__int64 __fastcall UploadFile(LPCWSTR lpcwszUrl, LPCWSTR lpFileName, unsigned __int16 *a3, unsigned int *a4)
{
  unsigned int v6; // r13d
  void *v7; // rsi
  void *v8; // rdi
  char *v9; // r14
  signed int LastError; // eax
  signed int v11; // ebx
  signed int v12; // eax
  HANDLE ProcessHeap; // rax
  LPVOID v14; // rax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  unsigned int *v18; // r15
  signed int v19; // eax
  HANDLE v20; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-39h] BYREF
  DWORD dwOptionalLength; // [rsp+44h] [rbp-35h] BYREF
  HINTERNET hRequest; // [rsp+48h] [rbp-31h] BYREF
  DWORD dwNumberOfBytesWritten; // [rsp+50h] [rbp-29h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-21h] BYREF
  HINTERNET hInternet; // [rsp+60h] [rbp-19h] BYREF
  HINTERNET v28; // [rsp+68h] [rbp-11h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-9h] BYREF

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  v28 = 0;
  FileSize.QuadPart = 0;
  v6 = 1;
  dwOptionalLength = 0;
  v7 = 0;
  NumberOfBytesRead = 0;
  v8 = 0;
  hRequest = 0;
  hInternet = 0;
  dwNumberOfBytesWritten = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v9 = (char *)CreateFileW(lpFileName, 0xC0000000, 3u, &SecurityAttributes, 3u, 0, 0);
  if ( ((unsigned __int64)(v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_50;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_50:
    if ( !GetFileSizeEx(v9, &FileSize) )
    {
      v12 = GetLastError();
      v11 = v12;
      if ( v12 > 0 )
        v11 = (unsigned __int16)v12 | 0x80070000;
      if ( v11 < 0 )
        goto LABEL_39;
    }
    v11 = ULongLongToULong(FileSize.QuadPart, &dwOptionalLength);
    if ( v11 < 0 )
    {
LABEL_39:
      v18 = a4;
      goto LABEL_40;
    }
    v11 = Connect(lpcwszUrl, L"PUT", a3, 0, dwOptionalLength, &hInternet, &v28, &hRequest);
    if ( v11 < 0 )
    {
      v8 = hRequest;
    }
    else
    {
      ProcessHeap = GetProcessHeap();
      v14 = HeapAlloc(ProcessHeap, 0, 0x1000u);
      v8 = hRequest;
      v7 = v14;
      if ( v14 )
      {
        while ( 1 )
        {
          if ( !ReadFile(v9, v7, 0x1000u, &NumberOfBytesRead, 0) )
          {
            v15 = GetLastError();
            v11 = v15;
            if ( v15 > 0 )
              v11 = (unsigned __int16)v15 | 0x80070000;
            if ( v11 < 0 )
              break;
          }
          if ( NumberOfBytesRead )
          {
            if ( !WinHttpWriteData(v8, v7, NumberOfBytesRead, &dwNumberOfBytesWritten) )
            {
              v16 = GetLastError();
              v11 = v16;
              if ( v16 > 0 )
                v11 = (unsigned __int16)v16 | 0x80070000;
              if ( v11 < 0 )
                break;
            }
            if ( NumberOfBytesRead )
              continue;
          }
          if ( WinHttpReceiveResponse(v8, 0) )
            goto LABEL_27;
          v17 = GetLastError();
          v11 = v17;
          if ( v17 > 0 )
            v11 = (unsigned __int16)v17 | 0x80070000;
          if ( v11 >= 0 )
          {
LABEL_27:
            v18 = a4;
            NumberOfBytesRead = 4;
            if ( WinHttpQueryHeaders(v8, 0x20000013u, 0, a4, &NumberOfBytesRead, 0) )
            {
              v11 = 0;
            }
            else
            {
              v19 = GetLastError();
              v11 = v19;
              if ( v19 > 0 )
                v11 = (unsigned __int16)v19 | 0x80070000;
            }
            goto LABEL_33;
          }
          break;
        }
      }
      else
      {
        v11 = -2147024882;
      }
    }
  }
  v18 = a4;
LABEL_33:
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v28 )
    WinHttpCloseHandle(v28);
  if ( v8 )
    WinHttpCloseHandle(v8);
LABEL_40:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  if ( v7 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v7);
  }
  if ( v11 < 0 || *v18 == 200 )
    return (unsigned int)v11;
  return v6;
}

```

## disassembly

```asm
0x140052688  mov     [rsp-8+lpBuffer], r9
0x14005268d  push    rbp
0x14005268e  push    rbx
0x14005268f  push    rsi
0x140052690  push    rdi
0x140052691  push    r12
0x140052693  push    r13
0x140052695  push    r14
0x140052697  push    r15
0x140052699  lea     rbp, [rsp-1Fh]
0x14005269e  sub     rsp, 98h
0x1400526a5  mov     r12, rcx
0x1400526a8  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x1400526b0  xor     ecx, ecx
0x1400526b2  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], 1
0x1400526ba  mov     [rsp+0D0h+hTemplateFile], rcx; hTemplateFile
0x1400526bf  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x1400526c3  mov     rax, rdx
0x1400526c6  mov     [rsp+0D0h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x1400526ca  mov     r15, r8
0x1400526cd  mov     [rbp+57h+var_68], rcx
0x1400526d1  lea     r8d, [rcx+3]; dwShareMode
0x1400526d5  mov     qword ptr [rbp+57h+FileSize], rcx
0x1400526d9  lea     r13d, [rcx+1]
0x1400526dd  mov     [rbp+57h+dwOptionalLength], ecx
0x1400526e0  mov     esi, ecx
0x1400526e2  mov     [rbp+57h+NumberOfBytesRead], ecx
0x1400526e5  mov     edi, ecx
0x1400526e7  mov     [rbp+57h+hRequest], rcx
0x1400526eb  mov     [rbp+57h+hInternet], rcx
0x1400526ef  mov     edx, 0C0000000h; dwDesiredAccess
0x1400526f4  mov     [rbp+57h+dwNumberOfBytesWritten], ecx
0x1400526f7  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rcx
0x1400526fb  mov     rcx, rax; lpFileName
0x1400526fe  mov     [rsp+0D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x140052703  call    cs:__imp_CreateFileW
0x14005270a  nop     dword ptr [rax+rax+00h]
0x14005270f  mov     r14, rax
0x140052712  inc     rax
0x140052715  test    rax, 0FFFFFFFFFFFFFFFEh
0x14005271b  jnz     short loc_140052740
0x14005271d  call    cs:__imp_GetLastError
0x140052724  nop     dword ptr [rax+rax+00h]
0x140052729  mov     ebx, eax
0x14005272b  test    eax, eax
0x14005272d  jle     short loc_140052738
0x14005272f  movzx   ebx, ax
0x140052732  or      ebx, 80070000h
0x140052738  test    ebx, ebx
0x14005273a  js      loc_14005293B
0x140052740  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x140052744  mov     rcx, r14; hFile
0x140052747  call    cs:__imp_GetFileSizeEx
0x14005274e  nop     dword ptr [rax+rax+00h]
0x140052753  test    eax, eax
0x140052755  jnz     short loc_14005277A
0x140052757  call    cs:__imp_GetLastError
0x14005275e  nop     dword ptr [rax+rax+00h]
0x140052763  mov     ebx, eax
0x140052765  test    eax, eax
0x140052767  jle     short loc_140052772
0x140052769  movzx   ebx, ax
0x14005276c  or      ebx, 80070000h
0x140052772  test    ebx, ebx
0x140052774  js      loc_14005297F
0x14005277a  mov     rcx, qword ptr [rbp+57h+FileSize]; unsigned __int64
0x14005277e  lea     rdx, [rbp+57h+dwOptionalLength]; unsigned int *
0x140052782  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140052787  mov     ebx, eax
0x140052789  test    eax, eax
0x14005278b  js      loc_14005297F
0x140052791  lea     rax, [rbp+57h+hRequest]
0x140052795  xor     r9d, r9d; char *
0x140052798  mov     [rsp+0D0h+var_98], rax; void **
0x14005279d  lea     rdx, pwszVerb; "PUT"
0x1400527a4  lea     rax, [rbp+57h+var_68]
0x1400527a8  mov     r8, r15; unsigned __int16 *
0x1400527ab  mov     [rsp+0D0h+hTemplateFile], rax; void **
0x1400527b0  mov     rcx, r12; lpcwszUrl
0x1400527b3  lea     rax, [rbp+57h+hInternet]
0x1400527b7  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], rax; void **
0x1400527bc  mov     eax, [rbp+57h+dwOptionalLength]
0x1400527bf  mov     [rsp+0D0h+dwCreationDisposition], eax; dwOptionalLength
0x1400527c3  call    ?Connect@@YAJPEBG00PEBDKPEAPEAX22@Z; Connect(ushort const *,ushort const *,ushort const *,char const *,ulong,void * *,void * *,void * *)
0x1400527c8  mov     ebx, eax
0x1400527ca  test    eax, eax
0x1400527cc  js      loc_140052937
0x1400527d2  call    cs:__imp_GetProcessHeap
0x1400527d9  nop     dword ptr [rax+rax+00h]
0x1400527de  mov     r15d, 1000h
0x1400527e4  xor     edx, edx; dwFlags
0x1400527e6  mov     rcx, rax; hHeap
0x1400527e9  mov     r8d, r15d; dwBytes
0x1400527ec  call    cs:__imp_HeapAlloc
0x1400527f3  nop     dword ptr [rax+rax+00h]
0x1400527f8  mov     rdi, [rbp+57h+hRequest]
0x1400527fc  mov     rsi, rax
0x1400527ff  test    rax, rax
0x140052802  jnz     short loc_14005280E
0x140052804  mov     ebx, 8007000Eh
0x140052809  jmp     loc_14005293B
0x14005280e  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x140052812  mov     qword ptr [rsp+0D0h+dwCreationDisposition], 0; lpOverlapped
0x14005281b  mov     r8d, r15d; nNumberOfBytesToRead
0x14005281e  mov     rdx, rsi; lpBuffer
0x140052821  mov     rcx, r14; hFile
0x140052824  call    cs:__imp_ReadFile
0x14005282b  nop     dword ptr [rax+rax+00h]
0x140052830  test    eax, eax
0x140052832  jnz     short loc_140052857
0x140052834  call    cs:__imp_GetLastError
0x14005283b  nop     dword ptr [rax+rax+00h]
0x140052840  mov     ebx, eax
0x140052842  test    eax, eax
0x140052844  jle     short loc_14005284F
0x140052846  movzx   ebx, ax
0x140052849  or      ebx, 80070000h
0x14005284f  test    ebx, ebx
0x140052851  js      loc_14005293B
0x140052857  mov     r8d, [rbp+57h+NumberOfBytesRead]; dwNumberOfBytesToWrite
0x14005285b  test    r8d, r8d
0x14005285e  jz      short loc_1400528A7
0x140052860  lea     r9, [rbp+57h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x140052864  mov     rdx, rsi; lpBuffer
0x140052867  mov     rcx, rdi; hRequest
0x14005286a  call    cs:__imp_WinHttpWriteData
0x140052871  nop     dword ptr [rax+rax+00h]
0x140052876  test    eax, eax
0x140052878  jnz     short loc_14005289D
0x14005287a  call    cs:__imp_GetLastError
0x140052881  nop     dword ptr [rax+rax+00h]
0x140052886  mov     ebx, eax
0x140052888  test    eax, eax
0x14005288a  jle     short loc_140052895
0x14005288c  movzx   ebx, ax
0x14005288f  or      ebx, 80070000h
0x140052895  test    ebx, ebx
0x140052897  js      loc_14005293B
0x14005289d  cmp     [rbp+57h+NumberOfBytesRead], 0
0x1400528a1  ja      loc_14005280E
0x1400528a7  xor     edx, edx; lpReserved
0x1400528a9  mov     rcx, rdi; hRequest
0x1400528ac  call    cs:__imp_WinHttpReceiveResponse
0x1400528b3  nop     dword ptr [rax+rax+00h]
0x1400528b8  test    eax, eax
0x1400528ba  jnz     short loc_1400528DB
0x1400528bc  call    cs:__imp_GetLastError
0x1400528c3  nop     dword ptr [rax+rax+00h]
0x1400528c8  mov     ebx, eax
0x1400528ca  test    eax, eax
0x1400528cc  jle     short loc_1400528D7
0x1400528ce  movzx   ebx, ax
0x1400528d1  or      ebx, 80070000h
0x1400528d7  test    ebx, ebx
0x1400528d9  js      short loc_14005293B
0x1400528db  mov     r15, [rbp+57h+lpBuffer]
0x1400528df  lea     rax, [rbp+57h+NumberOfBytesRead]
0x1400528e3  mov     r9, r15; lpBuffer
0x1400528e6  mov     qword ptr [rsp+0D0h+dwFlagsAndAttributes], 0; lpdwIndex
0x1400528ef  xor     r8d, r8d; pwszName
0x1400528f2  mov     [rbp+57h+NumberOfBytesRead], 4
0x1400528f9  mov     edx, 20000013h; dwInfoLevel
0x1400528fe  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax; lpdwBufferLength
0x140052903  mov     rcx, rdi; hRequest
0x140052906  call    cs:__imp_WinHttpQueryHeaders
0x14005290d  nop     dword ptr [rax+rax+00h]
0x140052912  test    eax, eax
0x140052914  jz      short loc_14005291A
0x140052916  xor     ebx, ebx
0x140052918  jmp     short loc_14005293F
0x14005291a  call    cs:__imp_GetLastError
0x140052921  nop     dword ptr [rax+rax+00h]
0x140052926  mov     ebx, eax
0x140052928  test    eax, eax
0x14005292a  jle     short loc_14005293F
0x14005292c  movzx   ebx, ax
0x14005292f  or      ebx, 80070000h
0x140052935  jmp     short loc_14005293F
0x140052937  mov     rdi, [rbp+57h+hRequest]
0x14005293b  mov     r15, [rbp+57h+lpBuffer]
0x14005293f  mov     rcx, [rbp+57h+hInternet]; hInternet
0x140052943  test    rcx, rcx
0x140052946  jz      short loc_140052954
0x140052948  call    cs:__imp_WinHttpCloseHandle
0x14005294f  nop     dword ptr [rax+rax+00h]
0x140052954  mov     rcx, [rbp+57h+var_68]; hInternet
0x140052958  test    rcx, rcx
0x14005295b  jz      short loc_140052969
0x14005295d  call    cs:__imp_WinHttpCloseHandle
0x140052964  nop     dword ptr [rax+rax+00h]
0x140052969  test    rdi, rdi
0x14005296c  jz      short loc_140052983
0x14005296e  mov     rcx, rdi; hInternet
0x140052971  call    cs:__imp_WinHttpCloseHandle
0x140052978  nop     dword ptr [rax+rax+00h]
0x14005297d  jmp     short loc_140052983
0x14005297f  mov     r15, [rbp+57h+lpBuffer]
0x140052983  lea     rax, [r14-1]
0x140052987  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005298b  ja      short loc_14005299C
0x14005298d  mov     rcx, r14; hObject
0x140052990  call    cs:__imp_CloseHandle
0x140052997  nop     dword ptr [rax+rax+00h]
0x14005299c  test    rsi, rsi
0x14005299f  jz      short loc_1400529C1
0x1400529a1  call    cs:__imp_GetProcessHeap
0x1400529a8  nop     dword ptr [rax+rax+00h]
0x1400529ad  mov     r8, rsi; lpMem
0x1400529b0  xor     edx, edx; dwFlags
0x1400529b2  mov     rcx, rax; hHeap
0x1400529b5  call    cs:__imp_HeapFree
0x1400529bc  nop     dword ptr [rax+rax+00h]
0x1400529c1  test    ebx, ebx
0x1400529c3  js      short loc_1400529CE
0x1400529c5  cmp     dword ptr [r15], 0C8h
0x1400529cc  jnz     short loc_1400529D1
0x1400529ce  mov     r13d, ebx
0x1400529d1  mov     eax, r13d
0x1400529d4  add     rsp, 98h
0x1400529db  pop     r15
0x1400529dd  pop     r14
0x1400529df  pop     r13
0x1400529e1  pop     r12
0x1400529e3  pop     rdi
0x1400529e4  pop     rsi
0x1400529e5  pop     rbx
0x1400529e6  pop     rbp
0x1400529e7  retn
```
