# LOG_ERROR_EVENT_WIN32

- ea: `0x180002320`
- end: `0x180002502`
- name: `LOG_ERROR_EVENT_WIN32`
- size: `482`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004a40`

## callees

- `0x180002320`
- `0x180002508`
- `0x180012e32`
- `0x180012e70`
- `0x180012f00`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180002417`
- `msvcrt!_snwprintf_s` at `0x18000244e`
- `msvcrt!_snwprintf_s` at `0x180002417`
- `msvcrt!_snwprintf_s` at `0x18000244e`
- `KERNEL32!LocalFree` at `0x18000245f`
- `KERNEL32!LocalFree` at `0x18000245f`
- `KERNEL32!FormatMessageW` at `0x1800023da`
- `KERNEL32!FormatMessageW` at `0x1800023da`
- `KERNEL32!GetLastError` at `0x18000236b`
- `KERNEL32!GetLastError` at `0x18000236b`
- `ADVAPI32!EventWrite` at `0x1800024af`
- `ADVAPI32!EventWrite` at `0x1800024af`

## pseudocode

```c
void LOG_ERROR_EVENT_WIN32()
{
  DWORD LastError; // ebx
  DWORD v1; // eax
  __int64 v2; // rax
  __int64 nSize; // [rsp+28h] [rbp-D8h]
  va_list *Arguments; // [rsp+30h] [rbp-D0h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v7[2048]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *(int *)&g_dwLoggingLevel >= 0 && g_hEventProviderHandle )
  {
    *(_QWORD *)Buffer = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_dde048edca7237c8ff2ee4c429efd9e5_Traceguids);
    memset_0(v7, 0, sizeof(v7));
    v1 = FormatMessageW(0x1100u, 0, LastError, 0x400u, Buffer, 0, 0);
    LODWORD(Arguments) = LastError;
    LODWORD(nSize) = 2333;
    if ( v1 )
    {
      _snwprintf_s(
        v7,
        0x800u,
        0x7FFu,
        L"[%s:%u] : %u: %s",
        L"base\\fs\\remotefs\\nfs4\\client\\netprov\\nfsnp.c",
        nSize,
        Arguments,
        *(_QWORD *)Buffer);
      LocalFree(*(HLOCAL *)Buffer);
    }
    else
    {
      _snwprintf_s(
        v7,
        0x800u,
        0x7FFu,
        L"[%s:%u] %u",
        L"base\\fs\\remotefs\\nfs4\\client\\netprov\\nfsnp.c",
        nSize,
        Arguments);
    }
    UserData.Ptr = (ULONGLONG)v7;
    v2 = -1;
    do
      ++v2;
    while ( v7[v2] );
    UserData.Size = 2 * v2 + 2;
    UserData.Reserved = 0;
    if ( EventWrite(g_hEventProviderHandle, &EVENT_ERROR_GETMODULEHANDLE, 1u, &UserData)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dde048edca7237c8ff2ee4c429efd9e5_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x180002320  push    rbp
0x180002322  push    rbx
0x180002323  push    rsi
0x180002324  push    rdi
0x180002325  lea     rbp, [rsp-0F78h]
0x18000232d  mov     eax, 1078h
0x180002332  call    _alloca_probe
0x180002337  sub     rsp, rax
0x18000233a  mov     rax, cs:__security_cookie
0x180002341  xor     rax, rsp
0x180002344  mov     [rbp+0F90h+var_30], rax
0x18000234b  xor     edi, edi
0x18000234d  cmp     cs:g_dwLoggingLevel, edi
0x180002353  jl      loc_1800024E6
0x180002359  cmp     cs:g_hEventProviderHandle, rdi
0x180002360  jz      loc_1800024E6
0x180002366  mov     qword ptr [rsp+1090h+Buffer], rdi
0x18000236b  call    cs:__imp_GetLastError
0x180002372  nop     dword ptr [rax+rax+00h]
0x180002377  mov     ebx, eax
0x180002379  mov     rcx, cs:WPP_GLOBAL_Control
0x180002380  lea     rsi, WPP_GLOBAL_Control
0x180002387  cmp     rcx, rsi
0x18000238a  jz      short loc_1800023A5
0x18000238c  test    byte ptr [rcx+1Ch], 8
0x180002390  jz      short loc_1800023A5
0x180002392  mov     rcx, [rcx+10h]
0x180002396  lea     edx, [rdi+17h]
0x180002399  lea     r8, WPP_dde048edca7237c8ff2ee4c429efd9e5_Traceguids
0x1800023a0  call    WPP_SF_
0x1800023a5  xor     edx, edx; Val
0x1800023a7  lea     rcx, [rsp+1090h+var_1030]; void *
0x1800023ac  mov     r8d, 1000h; Size
0x1800023b2  call    memset_0
0x1800023b7  lea     rax, [rsp+1090h+Buffer]
0x1800023bc  mov     [rsp+1090h+Arguments], rdi; Arguments
0x1800023c1  mov     dword ptr [rsp+1090h+nSize], edi; nSize
0x1800023c5  mov     r9d, 400h; dwLanguageId
0x1800023cb  mov     r8d, ebx; dwMessageId
0x1800023ce  mov     [rsp+1090h+lpBuffer], rax; lpBuffer
0x1800023d3  xor     edx, edx; lpSource
0x1800023d5  mov     ecx, 1100h; dwFlags
0x1800023da  call    cs:__imp_FormatMessageW
0x1800023e1  nop     dword ptr [rax+rax+00h]
0x1800023e6  mov     edx, 800h; BufferCount
0x1800023eb  lea     rcx, [rsp+1090h+var_1030]; Buffer
0x1800023f0  lea     r8d, [rdx-1]; MaxCount
0x1800023f4  test    eax, eax
0x1800023f6  jnz     short loc_180002425
0x1800023f8  mov     dword ptr [rsp+1090h+Arguments], ebx
0x1800023fc  lea     rax, aBaseFsRemotefs; "base\\fs\\remotefs\\nfs4\\client\\netpr"...
0x180002403  mov     dword ptr [rsp+1090h+nSize], 91Dh
0x18000240b  lea     r9, aSUU; "[%s:%u] %u"
0x180002412  mov     [rsp+1090h+lpBuffer], rax
0x180002417  call    cs:__imp__snwprintf_s
0x18000241e  nop     dword ptr [rax+rax+00h]
0x180002423  jmp     short loc_18000246B
0x180002425  mov     rax, qword ptr [rsp+1090h+Buffer]
0x18000242a  lea     r9, aSUUS; "[%s:%u] : %u: %s"
0x180002431  mov     [rsp+1090h+var_1058], rax
0x180002436  lea     rax, aBaseFsRemotefs; "base\\fs\\remotefs\\nfs4\\client\\netpr"...
0x18000243d  mov     dword ptr [rsp+1090h+Arguments], ebx
0x180002441  mov     dword ptr [rsp+1090h+nSize], 91Dh
0x180002449  mov     [rsp+1090h+lpBuffer], rax
0x18000244e  call    cs:__imp__snwprintf_s
0x180002455  nop     dword ptr [rax+rax+00h]
0x18000245a  mov     rcx, qword ptr [rsp+1090h+Buffer]; hMem
0x18000245f  call    cs:__imp_LocalFree
0x180002466  nop     dword ptr [rax+rax+00h]
0x18000246b  lea     rax, [rsp+1090h+var_1030]
0x180002470  mov     [rsp+1090h+UserData.Ptr], rax
0x180002475  lea     rcx, [rsp+1090h+var_1030]
0x18000247a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000247e  inc     rax
0x180002481  cmp     [rcx+rax*2], di
0x180002485  jnz     short loc_18000247E
0x180002487  mov     rcx, cs:g_hEventProviderHandle; RegHandle
0x18000248e  lea     eax, ds:2[rax*2]
0x180002495  lea     r9, [rsp+1090h+UserData]; UserData
0x18000249a  mov     [rsp+1090h+UserData.Size], eax
0x18000249e  mov     r8d, 1; UserDataCount
0x1800024a4  mov     dword ptr [rsp+1090h+UserData.0Ch], edi
0x1800024a8  lea     rdx, EVENT_ERROR_GETMODULEHANDLE; EventDescriptor
0x1800024af  call    cs:__imp_EventWrite
0x1800024b6  nop     dword ptr [rax+rax+00h]
0x1800024bb  test    eax, eax
0x1800024bd  jz      short loc_1800024E6
0x1800024bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024c6  cmp     rcx, rsi
0x1800024c9  jz      short loc_1800024E6
0x1800024cb  test    byte ptr [rcx+1Ch], 8
0x1800024cf  jz      short loc_1800024E6
0x1800024d1  mov     rcx, [rcx+10h]
0x1800024d5  lea     r8, WPP_dde048edca7237c8ff2ee4c429efd9e5_Traceguids
0x1800024dc  mov     edx, 18h
0x1800024e1  call    WPP_SF_
0x1800024e6  mov     rcx, [rbp+0F90h+var_30]
0x1800024ed  xor     rcx, rsp; StackCookie
0x1800024f0  call    __security_check_cookie
0x1800024f5  add     rsp, 1078h
0x1800024fc  pop     rdi
0x1800024fd  pop     rsi
0x1800024fe  pop     rbx
0x1800024ff  pop     rbp
0x180002500  retn
```
