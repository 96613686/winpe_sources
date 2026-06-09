# DsRolepDebugDumpRoutine

- ea: `0x180020880`
- end: `0x180020b01`
- name: `DsRolepDebugDumpRoutine`
- size: `641`
- prototype: `void __fastcall(__int64, const wchar_t *, va_list)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x1800035f0`
- `0x180020dbc`

## callees

- `0x180020880`
- `0x180020ec4`
- `0x180021048`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `msvcrt!malloc` at `0x1800209e4`
- `msvcrt!malloc` at `0x1800209e4`
- `msvcrt!free` at `0x180020ad1`
- `msvcrt!free` at `0x180020ad1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180020ab6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180020ab6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002093c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002093c`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ac3`
- `ntdll!RtlLeaveCriticalSection` at `0x180020ac3`
- `ntdll!RtlEnterCriticalSection` at `0x180020a96`
- `ntdll!RtlEnterCriticalSection` at `0x180020a96`

## pseudocode

```c
void __fastcall DsRolepDebugDumpRoutine(__int64 a1, const wchar_t *a2, va_list a3)
{
  const wchar_t *pszFormat; // r12
  wchar_t *v4; // rdi
  void *v5; // rsi
  __int64 i; // r13
  HRESULT v7; // r12d
  void *v8; // rax
  unsigned __int64 v9; // rbx
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  size_t pcchRemaining; // [rsp+78h] [rbp-88h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+80h] [rbp-80h] BYREF
  va_list argList; // [rsp+88h] [rbp-78h]
  const wchar_t *v15; // [rsp+90h] [rbp-70h]
  struct _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  wchar_t pszDest[256]; // [rsp+B0h] [rbp-50h] BYREF

  argList = a3;
  pszFormat = a2;
  v15 = a2;
  memset_0(pszDest, 0, sizeof(pszDest));
  NumberOfBytesWritten = 0;
  pcchRemaining = 0;
  SystemTime = 0;
  ppszDestEnd = 0;
  if ( DsRolepLogFile )
  {
    v4 = pszDest;
    v5 = 0;
    for ( i = 256; ; i = 0x2000 )
    {
      GetLocalTime(&SystemTime);
      StringCchPrintfExW(v4, i - 2, &ppszDestEnd, &pcchRemaining, 0, L"%02u/%02u/%04u %02u:%02u:%02u %S");
      v7 = StringCchVPrintfExW(ppszDestEnd, pcchRemaining, &ppszDestEnd, &pcchRemaining, dwFlags, pszFormat, argList);
      if ( v7 != -2147024774 )
        break;
      if ( v4 != pszDest )
        goto LABEL_8;
      v8 = malloc(0x4000u);
      v5 = v8;
      if ( !v8 )
        goto LABEL_8;
      pszFormat = v15;
      v4 = (wchar_t *)v8;
    }
    if ( v7 < 0 )
      goto LABEL_19;
LABEL_8:
    v9 = -1;
    do
      ++v9;
    while ( v4[v9] );
    if ( v9 >= 2 && v4[v9 - 1] == 10 && v4[v9 - 2] != 13 )
    {
      *(_DWORD *)&v4[v9 - 1] = 655373;
      v4[++v9] = 0;
      dword_18004D378 = 1;
    }
    if ( v9 >= 4 && v7 == -2147024774 && v4[v9 - 1] != 10 )
    {
      *(_DWORD *)&v4[v9 - 4] = 3014702;
      *(_DWORD *)&v4[v9 - 2] = 852014;
      *(_DWORD *)&v4[v9] = 10;
      LODWORD(v9) = v9 + 1;
      dword_18004D378 = 1;
    }
    RtlEnterCriticalSection(&LogFileCriticalSection);
    WriteFile(DsRolepLogFile, v4, 2 * v9, &NumberOfBytesWritten, 0);
    RtlLeaveCriticalSection(&LogFileCriticalSection);
LABEL_19:
    if ( v5 )
      free(v5);
  }
}

```

## disassembly

```asm
0x180020880  mov     [rsp-8+arg_0], rbx
0x180020885  push    rbp
0x180020886  push    rsi
0x180020887  push    rdi
0x180020888  push    r12
0x18002088a  push    r13
0x18002088c  push    r14
0x18002088e  push    r15
0x180020890  lea     rbp, [rsp-1C0h]
0x180020898  sub     rsp, 2C0h
0x18002089f  mov     rax, cs:__security_cookie
0x1800208a6  xor     rax, rsp
0x1800208a9  mov     [rbp+1F0h+var_40], rax
0x1800208b0  mov     [rbp+1F0h+var_268], r8
0x1800208b4  mov     r12, rdx
0x1800208b7  mov     [rbp+1F0h+var_260], rdx
0x1800208bb  mov     r15d, ecx
0x1800208be  xor     edx, edx; Val
0x1800208c0  lea     rcx, [rbp+1F0h+pszDest]; void *
0x1800208c4  mov     r8d, 200h; Size
0x1800208ca  call    memset_0
0x1800208cf  xor     ecx, ecx
0x1800208d1  xorps   xmm0, xmm0
0x1800208d4  cmp     cs:DsRolepLogFile, rcx
0x1800208db  mov     [rsp+2F0h+NumberOfBytesWritten], ecx
0x1800208df  mov     [rsp+2F0h+pcchRemaining], rcx
0x1800208e4  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x1800208e8  mov     [rbp+1F0h+ppszDestEnd], rcx
0x1800208ec  jz      loc_180020AD7
0x1800208f2  mov     r14d, r15d
0x1800208f5  lea     rdi, [rbp+1F0h+pszDest]
0x1800208f9  and     r14d, 1
0x1800208fd  mov     esi, ecx
0x1800208ff  mov     r13d, 100h
0x180020905  test    r14d, r14d
0x180020908  jz      short loc_180020913
0x18002090a  lea     rbx, aError; "[ERROR] "
0x180020911  jmp     short loc_180020938
0x180020913  test    r15b, 2
0x180020917  jz      short loc_180020922
0x180020919  lea     rbx, aWarning; "[WARNING] "
0x180020920  jmp     short loc_180020938
0x180020922  test    r15b, 0Ch
0x180020926  lea     rbx, dword_180040DA4
0x18002092d  lea     rax, aInfo; "[INFO] "
0x180020934  cmovnz  rbx, rax
0x180020938  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x18002093c  call    cs:__imp_GetLocalTime
0x180020942  movzx   eax, [rbp+1F0h+SystemTime.wSecond]
0x180020946  lea     rdx, [r13-2]; cchDest
0x18002094a  movzx   ecx, [rbp+1F0h+SystemTime.wMinute]
0x18002094e  movzx   r8d, [rbp+1F0h+SystemTime.wHour]
0x180020953  movzx   r9d, [rbp+1F0h+SystemTime.wYear]
0x180020958  movzx   r10d, [rbp+1F0h+SystemTime.wDay]
0x18002095d  movzx   r11d, [rbp+1F0h+SystemTime.wMonth]
0x180020962  mov     [rsp+2F0h+var_290], rbx
0x180020967  xor     ebx, ebx
0x180020969  mov     [rsp+2F0h+var_298], eax
0x18002096d  lea     rax, a02u02u04u02u02; "%02u/%02u/%04u %02u:%02u:%02u %S"
0x180020974  mov     [rsp+2F0h+var_2A0], ecx
0x180020978  mov     rcx, rdi; pszDest
0x18002097b  mov     [rsp+2F0h+var_2A8], r8d
0x180020980  lea     r8, [rbp+1F0h+ppszDestEnd]; ppszDestEnd
0x180020984  mov     [rsp+2F0h+var_2B0], r9d
0x180020989  lea     r9, [rsp+2F0h+pcchRemaining]; pcchRemaining
0x18002098e  mov     [rsp+2F0h+var_2B8], r10d
0x180020993  mov     dword ptr [rsp+2F0h+argList], r11d
0x180020998  mov     [rsp+2F0h+pszFormat], rax; pszFormat
0x18002099d  mov     qword ptr [rsp+2F0h+dwFlags], rbx; dwFlags
0x1800209a2  call    StringCchPrintfExW
0x1800209a7  mov     rax, [rbp+1F0h+var_268]
0x1800209ab  lea     r9, [rsp+2F0h+pcchRemaining]; pcchRemaining
0x1800209b0  mov     rdx, [rsp+2F0h+pcchRemaining]; cchDest
0x1800209b5  lea     r8, [rbp+1F0h+ppszDestEnd]; ppszDestEnd
0x1800209b9  mov     rcx, [rbp+1F0h+ppszDestEnd]; pszDest
0x1800209bd  mov     [rsp+2F0h+argList], rax; argList
0x1800209c2  mov     [rsp+2F0h+pszFormat], r12; pszFormat
0x1800209c7  call    StringCchVPrintfExW
0x1800209cc  mov     r12d, eax
0x1800209cf  cmp     eax, 8007007Ah
0x1800209d4  jnz     short loc_180020A06
0x1800209d6  lea     rax, [rbp+1F0h+pszDest]
0x1800209da  cmp     rdi, rax
0x1800209dd  jnz     short loc_180020A12
0x1800209df  mov     ecx, 4000h; Size
0x1800209e4  call    cs:__imp_malloc
0x1800209ea  xor     ecx, ecx
0x1800209ec  mov     rsi, rax
0x1800209ef  test    rax, rax
0x1800209f2  jz      short loc_180020A14
0x1800209f4  mov     r12, [rbp+1F0h+var_260]
0x1800209f8  mov     rdi, rax
0x1800209fb  mov     r13d, 2000h
0x180020a01  jmp     loc_180020905
0x180020a06  xor     ecx, ecx
0x180020a08  test    r12d, r12d
0x180020a0b  jns     short loc_180020A14
0x180020a0d  jmp     loc_180020AC9
0x180020a12  xor     ecx, ecx
0x180020a14  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020a18  inc     rbx
0x180020a1b  cmp     [rdi+rbx*2], cx
0x180020a1f  jnz     short loc_180020A18
0x180020a21  mov     edx, 0Ah
0x180020a26  lea     r8d, [rdx+3]
0x180020a2a  cmp     rbx, 2
0x180020a2e  jb      short loc_180020A59
0x180020a30  cmp     [rdi+rbx*2-2], dx
0x180020a35  jnz     short loc_180020A59
0x180020a37  cmp     [rdi+rbx*2-4], r8w
0x180020a3d  jz      short loc_180020A59
0x180020a3f  mov     dword ptr [rdi+rbx*2-2], 0A000Dh
0x180020a47  mov     [rdi+rbx*2+2], cx
0x180020a4c  inc     rbx
0x180020a4f  mov     cs:dword_18004D378, 1
0x180020a59  cmp     rbx, 4
0x180020a5d  jb      short loc_180020A8F
0x180020a5f  cmp     r12d, 8007007Ah
0x180020a66  jnz     short loc_180020A8F
0x180020a68  cmp     [rdi+rbx*2-2], dx
0x180020a6d  jz      short loc_180020A8F
0x180020a6f  mov     dword ptr [rdi+rbx*2-8], 2E002Eh
0x180020a77  mov     dword ptr [rdi+rbx*2-4], 0D002Eh
0x180020a7f  mov     [rdi+rbx*2], edx
0x180020a82  inc     rbx
0x180020a85  mov     cs:dword_18004D378, 1
0x180020a8f  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020a96  call    cs:__imp_RtlEnterCriticalSection
0x180020a9c  mov     rcx, cs:DsRolepLogFile; hFile
0x180020aa3  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x180020aa7  xor     ebx, ebx
0x180020aa9  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180020aae  mov     rdx, rdi; lpBuffer
0x180020ab1  mov     qword ptr [rsp+2F0h+dwFlags], rbx; lpOverlapped
0x180020ab6  call    cs:__imp_WriteFile
0x180020abc  lea     rcx, LogFileCriticalSection; CriticalSection
0x180020ac3  call    cs:__imp_RtlLeaveCriticalSection
0x180020ac9  test    rsi, rsi
0x180020acc  jz      short loc_180020AD7
0x180020ace  mov     rcx, rsi; Block
0x180020ad1  call    cs:__imp_free
0x180020ad7  mov     rcx, [rbp+1F0h+var_40]
0x180020ade  xor     rcx, rsp; StackCookie
0x180020ae1  call    __security_check_cookie
0x180020ae6  mov     rbx, [rsp+2F0h+arg_0]
0x180020aee  add     rsp, 2C0h
0x180020af5  pop     r15
0x180020af7  pop     r14
0x180020af9  pop     r13
0x180020afb  pop     r12
0x180020afd  pop     rdi
0x180020afe  pop     rsi
0x180020aff  pop     rbp
0x180020b00  retn
```
