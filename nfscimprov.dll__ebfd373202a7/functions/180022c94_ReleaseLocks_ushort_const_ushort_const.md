# ReleaseLocks(ushort const *,ushort const *)

- ea: `0x180022c94`
- end: `0x180022ee0`
- name: `?ReleaseLocks@@YAKPEBG0@Z`
- size: `588`
- prototype: `unsigned int __fastcall(LPCWCH lpWideCharStr, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180019644`
- `0x1800196ec`

## callees

- `0x180006a28`
- `0x180006a54`
- `0x1800219fc`
- `0x180022c94`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180022d89`
- `ntdll!RtlInitUnicodeString` at `0x180022d9c`
- `ntdll!RtlInitUnicodeString` at `0x180022d89`
- `ntdll!RtlInitUnicodeString` at `0x180022d9c`
- `KERNEL32!HeapFree` at `0x180022ea4`
- `KERNEL32!HeapFree` at `0x180022ebd`
- `KERNEL32!HeapFree` at `0x180022ea4`
- `KERNEL32!HeapFree` at `0x180022ebd`
- `KERNEL32!GetLastError` at `0x180022d65`
- `KERNEL32!GetLastError` at `0x180022e80`
- `KERNEL32!GetLastError` at `0x180022ec5`
- `KERNEL32!GetLastError` at `0x180022d65`
- `KERNEL32!GetLastError` at `0x180022e80`
- `KERNEL32!GetLastError` at `0x180022ec5`
- `KERNEL32!CloseHandle` at `0x180022e8b`
- `KERNEL32!CloseHandle` at `0x180022e8b`
- `KERNEL32!HeapAlloc` at `0x180022d28`
- `KERNEL32!HeapAlloc` at `0x180022dc0`
- `KERNEL32!HeapAlloc` at `0x180022d28`
- `KERNEL32!HeapAlloc` at `0x180022dc0`
- `KERNEL32!GetProcessHeap` at `0x180022d17`
- `KERNEL32!GetProcessHeap` at `0x180022dad`
- `KERNEL32!GetProcessHeap` at `0x180022e96`
- `KERNEL32!GetProcessHeap` at `0x180022eaf`
- `KERNEL32!GetProcessHeap` at `0x180022d17`
- `KERNEL32!GetProcessHeap` at `0x180022dad`
- `KERNEL32!GetProcessHeap` at `0x180022e96`
- `KERNEL32!GetProcessHeap` at `0x180022eaf`
- `KERNEL32!WideCharToMultiByte` at `0x180022d0e`
- `KERNEL32!WideCharToMultiByte` at `0x180022d5b`
- `KERNEL32!WideCharToMultiByte` at `0x180022d0e`
- `KERNEL32!WideCharToMultiByte` at `0x180022d5b`
- `KERNEL32!CreateFileW` at `0x180022cd6`
- `KERNEL32!CreateFileW` at `0x180022cd6`
- `KERNEL32!DeviceIoControl` at `0x180022e76`
- `KERNEL32!DeviceIoControl` at `0x180022e76`

## pseudocode

```c
__int64 __fastcall ReleaseLocks(LPCWCH lpWideCharStr, const unsigned __int16 *a2)
{
  __int64 v4; // rsi
  HANDLE FileW; // r12
  unsigned __int16 *v6; // rdi
  SIZE_T cbMultiByte; // r13
  HANDLE ProcessHeap; // rax
  DWORD ErrorFromHr; // ebx
  CHAR *lpMultiByteStr; // rax
  char *v11; // r15
  DWORD v12; // ebp
  HANDLE v13; // rax
  int v14; // eax
  int v15; // eax
  HANDLE v16; // rax
  HANDLE v17; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  DWORD BytesReturned; // [rsp+B0h] [rbp+18h] BYREF

  BytesReturned = 0;
  v4 = -1;
  FileW = CreateFileW(L"\\\\.\\NfsSvr", 0xC0000000, 0, 0, 3u, 0x1000080u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    v6 = 0;
    cbMultiByte = WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, 0, 0, 0, 0);
    ProcessHeap = GetProcessHeap();
    ErrorFromHr = 8;
    lpMultiByteStr = (CHAR *)HeapAlloc(ProcessHeap, 8u, cbMultiByte);
    v11 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      if ( WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0)
        || (ErrorFromHr = GetLastError()) == 0 )
      {
        v12 = 1036;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, 0);
        if ( a2 )
        {
          RtlInitUnicodeString(&DestinationString, a2);
          v12 = DestinationString.Length + 1038;
        }
        v13 = GetProcessHeap();
        ErrorFromHr = 8;
        v6 = (unsigned __int16 *)HeapAlloc(v13, 8u, v12);
        if ( v6 )
        {
          v6[516] = 0;
          v14 = StringCchCopyA((char *)v6 + 4, 0x401u, v11);
          ErrorFromHr = NfsGetErrorFromHr(v14);
          if ( !ErrorFromHr )
          {
            if ( !a2
              || (v15 = StringCchCopyW(v6 + 517, ((unsigned __int64)DestinationString.Length >> 1) + 1, a2),
                  (ErrorFromHr = NfsGetErrorFromHr(v15)) == 0) )
            {
              do
                ++v4;
              while ( v11[v4] );
              *(_DWORD *)v6 = v4;
              v6[516] = DestinationString.Length;
              if ( !DeviceIoControl(FileW, 0xA028A000, v6, v12, 0, 0, &BytesReturned, 0) )
                ErrorFromHr = GetLastError();
            }
          }
        }
      }
    }
    CloseHandle(FileW);
    if ( v11 )
    {
      v16 = GetProcessHeap();
      HeapFree(v16, 0, v11);
    }
    if ( v6 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v6);
    }
  }
  return ErrorFromHr;
}

```

## disassembly

```asm
0x180022c94  mov     rax, rsp
0x180022c97  push    rbx
0x180022c98  push    rbp
0x180022c99  push    rsi
0x180022c9a  push    rdi
0x180022c9b  push    r12
0x180022c9d  push    r13
0x180022c9f  push    r14
0x180022ca1  push    r15
0x180022ca3  sub     rsp, 58h
0x180022ca7  xor     ebx, ebx
0x180022ca9  mov     r14, rdx
0x180022cac  mov     [rax-68h], rbx
0x180022cb0  mov     rbp, rcx
0x180022cb3  mov     dword ptr [rax-70h], 1000080h
0x180022cba  lea     rcx, aNfssvr; "\\\\.\\NfsSvr"
0x180022cc1  xor     r9d, r9d; lpSecurityAttributes
0x180022cc4  mov     dword ptr [rax-78h], 3
0x180022ccb  xor     r8d, r8d; dwShareMode
0x180022cce  mov     [rax+18h], ebx
0x180022cd1  mov     edx, 0C0000000h; dwDesiredAccess
0x180022cd6  call    cs:__imp_CreateFileW
0x180022cdc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022ce0  mov     r12, rax
0x180022ce3  cmp     rax, rsi
0x180022ce6  jz      loc_180022EC5
0x180022cec  mov     [rsp+98h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x180022cf1  mov     r9d, esi; cchWideChar
0x180022cf4  mov     [rsp+98h+lpDefaultChar], rbx; lpDefaultChar
0x180022cf9  mov     r8, rbp; lpWideCharStr
0x180022cfc  mov     [rsp+98h+cbMultiByte], ebx; cbMultiByte
0x180022d00  mov     edx, 400h; dwFlags
0x180022d05  xor     ecx, ecx; CodePage
0x180022d07  mov     [rsp+98h+lpMultiByteStr], rbx; lpMultiByteStr
0x180022d0c  mov     edi, ebx
0x180022d0e  call    cs:__imp_WideCharToMultiByte
0x180022d14  movsxd  r13, eax
0x180022d17  call    cs:__imp_GetProcessHeap
0x180022d1d  lea     ebx, [rdi+8]
0x180022d20  mov     r8, r13; dwBytes
0x180022d23  mov     rcx, rax; hHeap
0x180022d26  mov     edx, ebx; dwFlags
0x180022d28  call    cs:__imp_HeapAlloc
0x180022d2e  mov     r15, rax
0x180022d31  test    rax, rax
0x180022d34  jz      loc_180022E88
0x180022d3a  mov     [rsp+98h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180022d3f  mov     r9d, esi; cchWideChar
0x180022d42  mov     [rsp+98h+lpDefaultChar], rdi; lpDefaultChar
0x180022d47  mov     r8, rbp; lpWideCharStr
0x180022d4a  mov     [rsp+98h+cbMultiByte], r13d; cbMultiByte
0x180022d4f  mov     edx, 400h; dwFlags
0x180022d54  xor     ecx, ecx; CodePage
0x180022d56  mov     [rsp+98h+lpMultiByteStr], rax; lpMultiByteStr
0x180022d5b  call    cs:__imp_WideCharToMultiByte
0x180022d61  test    eax, eax
0x180022d63  jnz     short loc_180022D75
0x180022d65  call    cs:__imp_GetLastError
0x180022d6b  mov     ebx, eax
0x180022d6d  test    eax, eax
0x180022d6f  jnz     loc_180022E88
0x180022d75  xorps   xmm0, xmm0
0x180022d78  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180022d7d  xor     edx, edx; SourceString
0x180022d7f  mov     ebp, 40Ch
0x180022d84  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x180022d89  call    cs:__imp_RtlInitUnicodeString
0x180022d8f  test    r14, r14
0x180022d92  jz      short loc_180022DAD
0x180022d94  mov     rdx, r14; SourceString
0x180022d97  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x180022d9c  call    cs:__imp_RtlInitUnicodeString
0x180022da2  movzx   ebp, [rsp+98h+DestinationString.Length]
0x180022da7  add     ebp, 40Eh
0x180022dad  call    cs:__imp_GetProcessHeap
0x180022db3  mov     ebx, 8
0x180022db8  mov     r8d, ebp; dwBytes
0x180022dbb  mov     rcx, rax; hHeap
0x180022dbe  mov     edx, ebx; dwFlags
0x180022dc0  call    cs:__imp_HeapAlloc
0x180022dc6  mov     rdi, rax
0x180022dc9  test    rax, rax
0x180022dcc  jz      loc_180022E88
0x180022dd2  xor     eax, eax
0x180022dd4  lea     rcx, [rdi+4]; char *
0x180022dd8  mov     r8, r15; char *
0x180022ddb  mov     [rdi+408h], ax
0x180022de2  mov     edx, 401h; unsigned __int64
0x180022de7  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180022dec  mov     ecx, eax; int
0x180022dee  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x180022df3  mov     ebx, eax
0x180022df5  test    eax, eax
0x180022df7  jnz     loc_180022E88
0x180022dfd  test    r14, r14
0x180022e00  jz      short loc_180022E29
0x180022e02  movzx   edx, [rsp+98h+DestinationString.Length]
0x180022e07  lea     rcx, [rdi+40Ah]; unsigned __int16 *
0x180022e0e  shr     rdx, 1
0x180022e11  mov     r8, r14; unsigned __int16 *
0x180022e14  inc     rdx; unsigned __int64
0x180022e17  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022e1c  mov     ecx, eax; int
0x180022e1e  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x180022e23  mov     ebx, eax
0x180022e25  test    eax, eax
0x180022e27  jnz     short loc_180022E88
0x180022e29  inc     rsi
0x180022e2c  cmp     byte ptr [r15+rsi], 0
0x180022e31  jnz     short loc_180022E29
0x180022e33  mov     [rsp+98h+lpUsedDefaultChar], 0; lpOverlapped
0x180022e3c  mov     r9d, ebp; nInBufferSize
0x180022e3f  mov     [rdi], esi
0x180022e41  mov     r8, rdi; lpInBuffer
0x180022e44  movzx   eax, [rsp+98h+DestinationString.Length]
0x180022e49  mov     edx, 0A028A000h; dwIoControlCode
0x180022e4e  mov     [rdi+408h], ax
0x180022e55  mov     rcx, r12; hDevice
0x180022e58  lea     rax, [rsp+98h+BytesReturned]
0x180022e60  mov     [rsp+98h+lpDefaultChar], rax; lpBytesReturned
0x180022e65  mov     [rsp+98h+cbMultiByte], 0; nOutBufferSize
0x180022e6d  mov     [rsp+98h+lpMultiByteStr], 0; lpOutBuffer
0x180022e76  call    cs:__imp_DeviceIoControl
0x180022e7c  test    eax, eax
0x180022e7e  jnz     short loc_180022E88
0x180022e80  call    cs:__imp_GetLastError
0x180022e86  mov     ebx, eax
0x180022e88  mov     rcx, r12; hObject
0x180022e8b  call    cs:__imp_CloseHandle
0x180022e91  test    r15, r15
0x180022e94  jz      short loc_180022EAA
0x180022e96  call    cs:__imp_GetProcessHeap
0x180022e9c  mov     r8, r15; lpMem
0x180022e9f  xor     edx, edx; dwFlags
0x180022ea1  mov     rcx, rax; hHeap
0x180022ea4  call    cs:__imp_HeapFree
0x180022eaa  test    rdi, rdi
0x180022ead  jz      short loc_180022ECD
0x180022eaf  call    cs:__imp_GetProcessHeap
0x180022eb5  mov     r8, rdi; lpMem
0x180022eb8  xor     edx, edx; dwFlags
0x180022eba  mov     rcx, rax; hHeap
0x180022ebd  call    cs:__imp_HeapFree
0x180022ec3  jmp     short loc_180022ECD
0x180022ec5  call    cs:__imp_GetLastError
0x180022ecb  mov     ebx, eax
0x180022ecd  mov     eax, ebx
0x180022ecf  add     rsp, 58h
0x180022ed3  pop     r15
0x180022ed5  pop     r14
0x180022ed7  pop     r13
0x180022ed9  pop     r12
0x180022edb  pop     rdi
0x180022edc  pop     rsi
0x180022edd  pop     rbp
0x180022ede  pop     rbx
0x180022edf  retn
```
