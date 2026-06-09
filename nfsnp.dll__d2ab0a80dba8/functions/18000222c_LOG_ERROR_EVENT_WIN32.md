# LOG_ERROR_EVENT_WIN32

- ea: `0x18000222c`
- end: `0x1800023e9`
- name: `LOG_ERROR_EVENT_WIN32`
- size: `445`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004720`

## callees

- `0x18000222c`
- `0x1800023f0`
- `0x180011b62`
- `0x180011ba0`
- `0x180011c30`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180002317`
- `msvcrt!_snwprintf_s` at `0x180002348`
- `msvcrt!_snwprintf_s` at `0x180002317`
- `msvcrt!_snwprintf_s` at `0x180002348`
- `KERNEL32!LocalFree` at `0x180002353`
- `KERNEL32!LocalFree` at `0x180002353`
- `KERNEL32!FormatMessageW` at `0x1800022e0`
- `KERNEL32!FormatMessageW` at `0x1800022e0`
- `KERNEL32!GetLastError` at `0x180002277`
- `KERNEL32!GetLastError` at `0x180002277`
- `ADVAPI32!EventWrite` at `0x18000239d`
- `ADVAPI32!EventWrite` at `0x18000239d`

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
0x18000222c  push    rbp
0x18000222e  push    rbx
0x18000222f  push    rsi
0x180002230  push    rdi
0x180002231  lea     rbp, [rsp-0F78h]
0x180002239  mov     eax, 1078h
0x18000223e  call    _alloca_probe
0x180002243  sub     rsp, rax
0x180002246  mov     rax, cs:__security_cookie
0x18000224d  xor     rax, rsp
0x180002250  mov     [rbp+0F90h+var_30], rax
0x180002257  xor     edi, edi
0x180002259  cmp     cs:g_dwLoggingLevel, edi
0x18000225f  jl      loc_1800023CE
0x180002265  cmp     cs:g_hEventProviderHandle, rdi
0x18000226c  jz      loc_1800023CE
0x180002272  mov     qword ptr [rsp+1090h+Buffer], rdi
0x180002277  call    cs:__imp_GetLastError
0x18000227d  mov     ebx, eax
0x18000227f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002286  lea     rsi, WPP_GLOBAL_Control
0x18000228d  cmp     rcx, rsi
0x180002290  jz      short loc_1800022AB
0x180002292  test    byte ptr [rcx+1Ch], 8
0x180002296  jz      short loc_1800022AB
0x180002298  mov     rcx, [rcx+10h]
0x18000229c  lea     edx, [rdi+17h]
0x18000229f  lea     r8, WPP_dde048edca7237c8ff2ee4c429efd9e5_Traceguids
0x1800022a6  call    WPP_SF_
0x1800022ab  xor     edx, edx; Val
0x1800022ad  lea     rcx, [rsp+1090h+var_1030]; void *
0x1800022b2  mov     r8d, 1000h; Size
0x1800022b8  call    memset_0
0x1800022bd  lea     rax, [rsp+1090h+Buffer]
0x1800022c2  mov     [rsp+1090h+Arguments], rdi; Arguments
0x1800022c7  mov     dword ptr [rsp+1090h+nSize], edi; nSize
0x1800022cb  mov     r9d, 400h; dwLanguageId
0x1800022d1  mov     r8d, ebx; dwMessageId
0x1800022d4  mov     [rsp+1090h+lpBuffer], rax; lpBuffer
0x1800022d9  xor     edx, edx; lpSource
0x1800022db  mov     ecx, 1100h; dwFlags
0x1800022e0  call    cs:__imp_FormatMessageW
0x1800022e6  mov     edx, 800h; BufferCount
0x1800022eb  lea     rcx, [rsp+1090h+var_1030]; Buffer
0x1800022f0  lea     r8d, [rdx-1]; MaxCount
0x1800022f4  test    eax, eax
0x1800022f6  jnz     short loc_18000231F
0x1800022f8  mov     dword ptr [rsp+1090h+Arguments], ebx
0x1800022fc  lea     rax, aBaseFsRemotefs; "base\\fs\\remotefs\\nfs4\\client\\netpr"...
0x180002303  mov     dword ptr [rsp+1090h+nSize], 91Dh
0x18000230b  lea     r9, aSUU; "[%s:%u] %u"
0x180002312  mov     [rsp+1090h+lpBuffer], rax
0x180002317  call    cs:__imp__snwprintf_s
0x18000231d  jmp     short loc_180002359
0x18000231f  mov     rax, qword ptr [rsp+1090h+Buffer]
0x180002324  lea     r9, aSUUS; "[%s:%u] : %u: %s"
0x18000232b  mov     [rsp+1090h+var_1058], rax
0x180002330  lea     rax, aBaseFsRemotefs; "base\\fs\\remotefs\\nfs4\\client\\netpr"...
0x180002337  mov     dword ptr [rsp+1090h+Arguments], ebx
0x18000233b  mov     dword ptr [rsp+1090h+nSize], 91Dh
0x180002343  mov     [rsp+1090h+lpBuffer], rax
0x180002348  call    cs:__imp__snwprintf_s
0x18000234e  mov     rcx, qword ptr [rsp+1090h+Buffer]; hMem
0x180002353  call    cs:__imp_LocalFree
0x180002359  lea     rax, [rsp+1090h+var_1030]
0x18000235e  mov     [rsp+1090h+UserData.Ptr], rax
0x180002363  lea     rcx, [rsp+1090h+var_1030]
0x180002368  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000236c  inc     rax
0x18000236f  cmp     [rcx+rax*2], di
0x180002373  jnz     short loc_18000236C
0x180002375  mov     rcx, cs:g_hEventProviderHandle; RegHandle
0x18000237c  lea     eax, ds:2[rax*2]
0x180002383  lea     r9, [rsp+1090h+UserData]; UserData
0x180002388  mov     [rsp+1090h+UserData.Size], eax
0x18000238c  mov     r8d, 1; UserDataCount
0x180002392  mov     dword ptr [rsp+1090h+UserData.0Ch], edi
0x180002396  lea     rdx, EVENT_ERROR_GETMODULEHANDLE; EventDescriptor
0x18000239d  call    cs:__imp_EventWrite
0x1800023a3  test    eax, eax
0x1800023a5  jz      short loc_1800023CE
0x1800023a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023ae  cmp     rcx, rsi
0x1800023b1  jz      short loc_1800023CE
0x1800023b3  test    byte ptr [rcx+1Ch], 8
0x1800023b7  jz      short loc_1800023CE
0x1800023b9  mov     rcx, [rcx+10h]
0x1800023bd  lea     r8, WPP_dde048edca7237c8ff2ee4c429efd9e5_Traceguids
0x1800023c4  mov     edx, 18h
0x1800023c9  call    WPP_SF_
0x1800023ce  mov     rcx, [rbp+0F90h+var_30]
0x1800023d5  xor     rcx, rsp; StackCookie
0x1800023d8  call    __security_check_cookie
0x1800023dd  add     rsp, 1078h
0x1800023e4  pop     rdi
0x1800023e5  pop     rsi
0x1800023e6  pop     rbx
0x1800023e7  pop     rbp
0x1800023e8  retn
```
