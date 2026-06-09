# UtilGetProcessCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18003a6b4`
- end: `0x18003a9df`
- name: `?UtilGetProcessCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001f0c0`
- `0x18001ffe8`

## callees

- `0x1800028b4`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a074`
- `0x18000c1a8`
- `0x18003a6b4`
- `0x18003cb54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a8ea`
- `ntdll!NtQueryInformationProcess` at `0x18003a72d`
- `ntdll!NtQueryInformationProcess` at `0x18003a72d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003a779`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003a7b8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003a827`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003a779`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003a7b8`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18003a827`

## pseudocode

```c
__int64 __fastcall UtilGetProcessCommandLine(HANDLE hProcess, __int64 a2)
{
  NTSTATUS v4; // eax
  SIZE_T v5; // rbx
  unsigned int v6; // ebx
  signed int LastError; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  LPCVOID lpBaseAddress[2]; // [rsp+30h] [rbp-19h] BYREF
  LPVOID lpBuffer; // [rsp+40h] [rbp-9h] BYREF
  char *v15; // [rsp+48h] [rbp-1h]
  _WORD v16[8]; // [rsp+50h] [rbp+7h] BYREF
  _OWORD ProcessInformation[4]; // [rsp+60h] [rbp+17h] BYREF
  ULONG ReturnLength; // [rsp+B0h] [rbp+67h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+C0h] [rbp+77h] BYREF
  __int64 Buffer; // [rsp+C8h] [rbp+7Fh] BYREF

  Buffer = 0;
  lpBuffer = v16;
  v15 = (char *)v16;
  v16[0] = 0;
  NumberOfBytesRead = 0;
  ReturnLength = 0;
  memset(ProcessInformation, 0, 48);
  *(_OWORD *)lpBaseAddress = 0;
  if ( hProcess && a2 )
  {
    v4 = NtQueryInformationProcess(hProcess, ProcessBasicInformation, ProcessInformation, 0x30u, &ReturnLength);
    if ( v4 < 0 || ReturnLength != 48 || !*((_QWORD *)&ProcessInformation[0] + 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_DDq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_QWORD *)&ProcessInformation[0] + 1),
          ReturnLength,
          (unsigned int)v4,
          ReturnLength,
          *((_QWORD *)&ProcessInformation[0] + 1));
      v6 = -2147467259;
      goto LABEL_39;
    }
    NumberOfBytesRead = 0;
    if ( ReadProcessMemory(
           hProcess,
           (LPCVOID)(*((_QWORD *)&ProcessInformation[0] + 1) + 32LL),
           &Buffer,
           8u,
           &NumberOfBytesRead)
      && NumberOfBytesRead == 8 )
    {
      NumberOfBytesRead = 0;
      if ( ReadProcessMemory(hProcess, (LPCVOID)(Buffer + 112), lpBaseAddress, 0x10u, &NumberOfBytesRead)
        && NumberOfBytesRead == 16
        && lpBaseAddress[1] )
      {
        v5 = 0x2000;
        if ( LOWORD(lpBaseAddress[0]) <= 0x2000u )
          v5 = LOWORD(lpBaseAddress[0]);
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(
                                 &lpBuffer,
                                 v5 >> 1) )
        {
          v6 = -2147024882;
          goto LABEL_39;
        }
        NumberOfBytesRead = 0;
        if ( ReadProcessMemory(hProcess, lpBaseAddress[1], lpBuffer, v5, &NumberOfBytesRead) )
        {
          if ( NumberOfBytesRead >> 1 > (v15 - (_BYTE *)lpBuffer) >> 1 )
            __int2c();
          v15 = (char *)lpBuffer + 2 * (NumberOfBytesRead >> 1);
          *(_WORD *)v15 = 0;
          utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpBuffer);
          v6 = 0;
          goto LABEL_39;
        }
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_39:
          if ( lpBuffer != v16 )
            operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
          return v6;
        }
        v9 = 61;
      }
      else
      {
        v10 = GetLastError();
        v6 = v10;
        if ( v10 > 0 )
          v6 = (unsigned __int16)v10 | 0x80070000;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_39;
        v9 = 60;
      }
    }
    else
    {
      v11 = GetLastError();
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_39;
      v9 = 59;
    }
    WPP_SF_d(v8[2], v9, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v6);
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    if ( lpBuffer != v16 )
      operator delete(lpBuffer, (const struct std::nothrow_t *)&std::nothrow);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003a6b4  mov     [rsp-8+arg_8], rbx
0x18003a6b9  push    rbp
0x18003a6ba  push    rsi
0x18003a6bb  push    rdi
0x18003a6bc  lea     rbp, [rsp-47h]
0x18003a6c1  sub     rsp, 90h
0x18003a6c8  xorps   xmm0, xmm0
0x18003a6cb  mov     [rbp+57h+Buffer], 0
0x18003a6d3  lea     rax, [rbp+57h+var_50]
0x18003a6d7  mov     rsi, rdx
0x18003a6da  mov     [rbp+57h+lpBuffer], rax
0x18003a6de  mov     rdi, rcx
0x18003a6e1  lea     rax, [rbp+57h+var_50]
0x18003a6e5  mov     [rbp+57h+var_58], rax
0x18003a6e9  xor     eax, eax
0x18003a6eb  mov     [rbp+57h+var_50], ax
0x18003a6ef  mov     [rbp+57h+NumberOfBytesRead], rax
0x18003a6f3  mov     [rbp+57h+arg_0], eax
0x18003a6f6  movups  [rbp+57h+ProcessInformation], xmm0
0x18003a6fa  movups  [rbp+57h+var_30], xmm0
0x18003a6fe  movups  [rbp+57h+var_20], xmm0
0x18003a702  movups  xmmword ptr [rbp+57h+lpBaseAddress], xmm0
0x18003a706  test    rcx, rcx
0x18003a709  jz      loc_18003A980
0x18003a70f  test    rdx, rdx
0x18003a712  jz      loc_18003A980
0x18003a718  lea     rax, [rbp+57h+arg_0]
0x18003a71c  mov     r9d, 30h ; '0'; ProcessInformationLength
0x18003a722  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x18003a726  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x18003a72b  xor     edx, edx; ProcessInformationClass
0x18003a72d  call    cs:__imp_NtQueryInformationProcess
0x18003a733  mov     rdx, qword ptr [rbp+57h+ProcessInformation+8]
0x18003a737  mov     r9d, eax
0x18003a73a  mov     r8d, [rbp+57h+arg_0]
0x18003a73e  test    eax, eax
0x18003a740  js      loc_18003A932
0x18003a746  cmp     r8d, 30h ; '0'
0x18003a74a  jnz     loc_18003A932
0x18003a750  test    rdx, rdx
0x18003a753  jz      loc_18003A932
0x18003a759  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18003a75d  mov     [rbp+57h+NumberOfBytesRead], 0
0x18003a765  lea     r9d, [r8-28h]; nSize
0x18003a769  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x18003a76e  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18003a772  add     rdx, 20h ; ' '; lpBaseAddress
0x18003a776  mov     rcx, rdi; hProcess
0x18003a779  call    cs:__imp_ReadProcessMemory
0x18003a77f  test    eax, eax
0x18003a781  jz      loc_18003A8EA
0x18003a787  cmp     [rbp+57h+NumberOfBytesRead], 8
0x18003a78c  jnz     loc_18003A8EA
0x18003a792  mov     rdx, [rbp+57h+Buffer]
0x18003a796  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18003a79a  add     rdx, 70h ; 'p'; lpBaseAddress
0x18003a79e  mov     [rbp+57h+NumberOfBytesRead], 0
0x18003a7a6  mov     r9d, 10h; nSize
0x18003a7ac  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x18003a7b1  lea     r8, [rbp+57h+lpBaseAddress]; lpBuffer
0x18003a7b5  mov     rcx, rdi; hProcess
0x18003a7b8  call    cs:__imp_ReadProcessMemory
0x18003a7be  test    eax, eax
0x18003a7c0  jz      loc_18003A8AD
0x18003a7c6  cmp     [rbp+57h+NumberOfBytesRead], 10h
0x18003a7cb  jnz     loc_18003A8AD
0x18003a7d1  cmp     [rbp+57h+lpBaseAddress+8], 0
0x18003a7d6  jz      loc_18003A8AD
0x18003a7dc  mov     ebx, 2000h
0x18003a7e1  cmp     bx, word ptr [rbp+57h+lpBaseAddress]
0x18003a7e5  jb      short loc_18003A7EB
0x18003a7e7  movzx   ebx, word ptr [rbp+57h+lpBaseAddress]
0x18003a7eb  mov     rdx, rbx
0x18003a7ee  lea     rcx, [rbp+57h+lpBuffer]
0x18003a7f2  shr     rdx, 1
0x18003a7f5  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18003a7fa  test    al, al
0x18003a7fc  jnz     short loc_18003A808
0x18003a7fe  mov     ebx, 8007000Eh
0x18003a803  jmp     loc_18003A963
0x18003a808  mov     r8, [rbp+57h+lpBuffer]; lpBuffer
0x18003a80c  lea     rax, [rbp+57h+NumberOfBytesRead]
0x18003a810  mov     rdx, [rbp+57h+lpBaseAddress+8]; lpBaseAddress
0x18003a814  mov     r9, rbx; nSize
0x18003a817  mov     rcx, rdi; hProcess
0x18003a81a  mov     [rsp+0A0h+ReturnLength], rax; lpNumberOfBytesRead
0x18003a81f  mov     [rbp+57h+NumberOfBytesRead], 0
0x18003a827  call    cs:__imp_ReadProcessMemory
0x18003a82d  test    eax, eax
0x18003a82f  jnz     short loc_18003A871
0x18003a831  call    cs:__imp_GetLastError
0x18003a837  mov     ebx, eax
0x18003a839  test    eax, eax
0x18003a83b  jle     short loc_18003A846
0x18003a83d  movzx   ebx, ax
0x18003a840  or      ebx, 80070000h
0x18003a846  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a84d  lea     rax, WPP_GLOBAL_Control
0x18003a854  cmp     rcx, rax
0x18003a857  jz      loc_18003A963
0x18003a85d  test    byte ptr [rcx+1Ch], 1
0x18003a861  jz      loc_18003A963
0x18003a867  mov     edx, 3Dh ; '='
0x18003a86c  jmp     loc_18003A91D
0x18003a871  mov     rax, [rbp+57h+var_58]
0x18003a875  mov     rdx, [rbp+57h+lpBuffer]
0x18003a879  mov     rcx, [rbp+57h+NumberOfBytesRead]
0x18003a87d  sub     rax, rdx
0x18003a880  sar     rax, 1
0x18003a883  shr     rcx, 1
0x18003a886  cmp     rcx, rax
0x18003a889  jbe     short loc_18003A88D
0x18003a88b  int     2Ch; Windows NT - assertion failure
0x18003a88d  lea     rcx, [rdx+rcx*2]
0x18003a891  xor     eax, eax
0x18003a893  mov     [rbp+57h+var_58], rcx
0x18003a897  lea     rdx, [rbp+57h+lpBuffer]
0x18003a89b  mov     [rcx], ax
0x18003a89e  mov     rcx, rsi
0x18003a8a1  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18003a8a6  xor     ebx, ebx
0x18003a8a8  jmp     loc_18003A963
0x18003a8ad  call    cs:__imp_GetLastError
0x18003a8b3  mov     ebx, eax
0x18003a8b5  test    eax, eax
0x18003a8b7  jle     short loc_18003A8C2
0x18003a8b9  movzx   ebx, ax
0x18003a8bc  or      ebx, 80070000h
0x18003a8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8c9  lea     rax, WPP_GLOBAL_Control
0x18003a8d0  cmp     rcx, rax
0x18003a8d3  jz      loc_18003A963
0x18003a8d9  test    byte ptr [rcx+1Ch], 1
0x18003a8dd  jz      loc_18003A963
0x18003a8e3  mov     edx, 3Ch ; '<'
0x18003a8e8  jmp     short loc_18003A91D
0x18003a8ea  call    cs:__imp_GetLastError
0x18003a8f0  mov     ebx, eax
0x18003a8f2  test    eax, eax
0x18003a8f4  jle     short loc_18003A8FF
0x18003a8f6  movzx   ebx, ax
0x18003a8f9  or      ebx, 80070000h
0x18003a8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a906  lea     rax, WPP_GLOBAL_Control
0x18003a90d  cmp     rcx, rax
0x18003a910  jz      short loc_18003A963
0x18003a912  test    byte ptr [rcx+1Ch], 1
0x18003a916  jz      short loc_18003A963
0x18003a918  mov     edx, 3Bh ; ';'
0x18003a91d  mov     rcx, [rcx+10h]
0x18003a921  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003a928  mov     r9d, ebx
0x18003a92b  call    WPP_SF_d
0x18003a930  jmp     short loc_18003A963
0x18003a932  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a939  lea     rax, WPP_GLOBAL_Control
0x18003a940  cmp     rcx, rax
0x18003a943  jz      short loc_18003A95E
0x18003a945  test    byte ptr [rcx+1Ch], 1
0x18003a949  jz      short loc_18003A95E
0x18003a94b  mov     rcx, [rcx+10h]
0x18003a94f  mov     [rsp+0A0h+var_78], rdx
0x18003a954  mov     dword ptr [rsp+0A0h+ReturnLength], r8d
0x18003a959  call    WPP_SF_DDq
0x18003a95e  mov     ebx, 80004005h
0x18003a963  mov     rcx, [rbp+57h+lpBuffer]; void *
0x18003a967  lea     rax, [rbp+57h+var_50]
0x18003a96b  cmp     rcx, rax
0x18003a96e  jz      short loc_18003A97C
0x18003a970  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a977  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a97c  mov     eax, ebx
0x18003a97e  jmp     short loc_18003A9CC
0x18003a980  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a987  lea     rax, WPP_GLOBAL_Control
0x18003a98e  cmp     rcx, rax
0x18003a991  jz      short loc_18003A9C7
0x18003a993  test    byte ptr [rcx+1Ch], 1
0x18003a997  jz      short loc_18003A9C7
0x18003a999  mov     rcx, [rcx+10h]
0x18003a99d  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003a9a4  mov     edx, 39h ; '9'
0x18003a9a9  call    WPP_SF_
0x18003a9ae  mov     rcx, [rbp+57h+lpBuffer]; void *
0x18003a9b2  lea     rax, [rbp+57h+var_50]
0x18003a9b6  cmp     rcx, rax
0x18003a9b9  jz      short loc_18003A9C7
0x18003a9bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a9c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003a9c7  mov     eax, 80070057h
0x18003a9cc  mov     rbx, [rsp+0A0h+arg_8]
0x18003a9d4  add     rsp, 90h
0x18003a9db  pop     rdi
0x18003a9dc  pop     rsi
0x18003a9dd  pop     rbp
0x18003a9de  retn
```
