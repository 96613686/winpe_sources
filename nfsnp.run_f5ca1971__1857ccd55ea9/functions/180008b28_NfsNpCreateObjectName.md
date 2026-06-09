# NfsNpCreateObjectName

- ea: `0x180008b28`
- end: `0x180008cf9`
- name: `NfsNpCreateObjectName`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180004a40`

## callees

- `0x180002508`
- `0x18000486c`
- `0x180008b28`
- `0x180012e70`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x180008c0b`
- `msvcrt!_snwprintf_s` at `0x180008c0b`
- `ntdll!RtlAppendUnicodeToString` at `0x180008b88`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c22`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c3d`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c59`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c74`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c8b`
- `ntdll!RtlAppendUnicodeToString` at `0x180008ca6`
- `ntdll!RtlAppendUnicodeToString` at `0x180008cbd`
- `ntdll!RtlAppendUnicodeToString` at `0x180008b88`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c22`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c3d`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c59`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c74`
- `ntdll!RtlAppendUnicodeToString` at `0x180008c8b`
- `ntdll!RtlAppendUnicodeToString` at `0x180008ca6`
- `ntdll!RtlAppendUnicodeToString` at `0x180008cbd`

## pseudocode

```c
__int64 __fastcall NfsNpCreateObjectName(WCHAR *a1, __int64 a2, const WCHAR *a3, const WCHAR *a4, const WCHAR *Source)
{
  int ProcessLuid; // ebx
  NTSTATUS appended; // eax
  unsigned int v10; // edx
  LONG HighPart; // [rsp+20h] [rbp-60h]
  DWORD LowPart; // [rsp+28h] [rbp-58h]
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-50h] BYREF
  struct _LUID DestinationLuid; // [rsp+40h] [rbp-40h] BYREF
  wchar_t Buffer[8]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v16; // [rsp+58h] [rbp-28h]
  __int128 v17; // [rsp+68h] [rbp-18h]

  Destination.Buffer = a1;
  DestinationLuid = 0;
  a1[259] = 0;
  *(_QWORD *)&Destination.Length = 33947648;
  *(_OWORD *)Buffer = 0;
  v16 = 0;
  v17 = 0;
  if ( RtlAppendUnicodeToString(&Destination, L"\\Device\\MRxNfs") < 0 )
    return 3221225507LL;
  if ( a3 )
  {
    ProcessLuid = GetProcessLuid(&DestinationLuid);
    if ( ProcessLuid < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      return (unsigned int)ProcessLuid;
    }
    LowPart = DestinationLuid.LowPart;
    HighPart = DestinationLuid.HighPart;
    _snwprintf_s(Buffer, 0x18u, 0x17u, L"%08x%08x", HighPart, LowPart);
    if ( RtlAppendUnicodeToString(&Destination, L"\\;") < 0
      || RtlAppendUnicodeToString(&Destination, a3) < 0
      || RtlAppendUnicodeToString(&Destination, Buffer) < 0 )
    {
      return 3221225507LL;
    }
  }
  if ( RtlAppendUnicodeToString(&Destination, L"\\") < 0
    || RtlAppendUnicodeToString(&Destination, a4) < 0
    || RtlAppendUnicodeToString(&Destination, L"\\") < 0 )
  {
    return 3221225507LL;
  }
  appended = RtlAppendUnicodeToString(&Destination, Source);
  v10 = -1073741789;
  if ( appended >= 0 )
    return 0;
  return v10;
}

```

## disassembly

```asm
0x180008b28  push    rbp
0x180008b2a  push    rbx
0x180008b2b  push    rsi
0x180008b2c  push    rdi
0x180008b2d  push    r14
0x180008b2f  mov     rbp, rsp
0x180008b32  sub     rsp, 80h
0x180008b39  mov     rax, cs:__security_cookie
0x180008b40  xor     rax, rsp
0x180008b43  mov     [rbp+var_8], rax
0x180008b47  mov     r14, [rbp+Source]
0x180008b4b  lea     rdx, SourceString; "\\Device\\MRxNfs"
0x180008b52  xorps   xmm0, xmm0
0x180008b55  mov     [rbp+Destination.Buffer], rcx
0x180008b59  xor     eax, eax
0x180008b5b  mov     qword ptr [rbp+DestinationLuid.LowPart], 0
0x180008b63  mov     [rcx+206h], ax
0x180008b6a  mov     rsi, r9
0x180008b6d  lea     rcx, [rbp+Destination]; Destination
0x180008b71  mov     qword ptr [rbp+Destination.Length], 2060000h
0x180008b79  mov     rdi, r8
0x180008b7c  movups  xmmword ptr [rbp+Buffer], xmm0
0x180008b80  movups  [rbp+var_28], xmm0
0x180008b84  movups  [rbp+var_18], xmm0
0x180008b88  call    cs:__imp_RtlAppendUnicodeToString
0x180008b8f  nop     dword ptr [rax+rax+00h]
0x180008b94  test    eax, eax
0x180008b96  js      loc_180008CD9
0x180008b9c  test    rdi, rdi
0x180008b9f  jz      loc_180008C69
0x180008ba5  lea     rcx, [rbp+DestinationLuid]; DestinationLuid
0x180008ba9  call    GetProcessLuid
0x180008bae  mov     ebx, eax
0x180008bb0  test    eax, eax
0x180008bb2  jns     short loc_180008BE9
0x180008bb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bbb  lea     rax, WPP_GLOBAL_Control
0x180008bc2  cmp     rcx, rax
0x180008bc5  jz      short loc_180008BE2
0x180008bc7  test    byte ptr [rcx+1Ch], 2
0x180008bcb  jz      short loc_180008BE2
0x180008bcd  mov     rcx, [rcx+10h]
0x180008bd1  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008bd8  mov     edx, 0FBh
0x180008bdd  call    WPP_SF_
0x180008be2  mov     eax, ebx
0x180008be4  jmp     loc_180008CDE
0x180008be9  mov     eax, [rbp+DestinationLuid.LowPart]
0x180008bec  lea     r9, a08x08x; "%08x%08x"
0x180008bf3  mov     [rsp+80h+var_58], eax
0x180008bf7  lea     rcx, [rbp+Buffer]; Buffer
0x180008bfb  mov     eax, [rbp+DestinationLuid.HighPart]
0x180008bfe  mov     edx, 18h; BufferCount
0x180008c03  mov     [rsp+80h+var_60], eax
0x180008c07  lea     r8d, [rdx-1]; MaxCount
0x180008c0b  call    cs:__imp__snwprintf_s
0x180008c12  nop     dword ptr [rax+rax+00h]
0x180008c17  lea     rdx, asc_18001535C; "\\;"
0x180008c1e  lea     rcx, [rbp+Destination]; Destination
0x180008c22  call    cs:__imp_RtlAppendUnicodeToString
0x180008c29  nop     dword ptr [rax+rax+00h]
0x180008c2e  test    eax, eax
0x180008c30  js      loc_180008CD9
0x180008c36  mov     rdx, rdi; Source
0x180008c39  lea     rcx, [rbp+Destination]; Destination
0x180008c3d  call    cs:__imp_RtlAppendUnicodeToString
0x180008c44  nop     dword ptr [rax+rax+00h]
0x180008c49  test    eax, eax
0x180008c4b  js      loc_180008CD9
0x180008c51  lea     rdx, [rbp+Buffer]; Source
0x180008c55  lea     rcx, [rbp+Destination]; Destination
0x180008c59  call    cs:__imp_RtlAppendUnicodeToString
0x180008c60  nop     dword ptr [rax+rax+00h]
0x180008c65  test    eax, eax
0x180008c67  js      short loc_180008CD9
0x180008c69  lea     rdx, SubStr; "\\"
0x180008c70  lea     rcx, [rbp+Destination]; Destination
0x180008c74  call    cs:__imp_RtlAppendUnicodeToString
0x180008c7b  nop     dword ptr [rax+rax+00h]
0x180008c80  test    eax, eax
0x180008c82  js      short loc_180008CD9
0x180008c84  mov     rdx, rsi; Source
0x180008c87  lea     rcx, [rbp+Destination]; Destination
0x180008c8b  call    cs:__imp_RtlAppendUnicodeToString
0x180008c92  nop     dword ptr [rax+rax+00h]
0x180008c97  test    eax, eax
0x180008c99  js      short loc_180008CD9
0x180008c9b  lea     rdx, SubStr; "\\"
0x180008ca2  lea     rcx, [rbp+Destination]; Destination
0x180008ca6  call    cs:__imp_RtlAppendUnicodeToString
0x180008cad  nop     dword ptr [rax+rax+00h]
0x180008cb2  test    eax, eax
0x180008cb4  js      short loc_180008CD9
0x180008cb6  mov     rdx, r14; Source
0x180008cb9  lea     rcx, [rbp+Destination]; Destination
0x180008cbd  call    cs:__imp_RtlAppendUnicodeToString
0x180008cc4  nop     dword ptr [rax+rax+00h]
0x180008cc9  xor     ecx, ecx
0x180008ccb  mov     edx, 0C0000023h
0x180008cd0  test    eax, eax
0x180008cd2  cmovns  edx, ecx
0x180008cd5  mov     eax, edx
0x180008cd7  jmp     short loc_180008CDE
0x180008cd9  mov     eax, 0C0000023h
0x180008cde  mov     rcx, [rbp+var_8]
0x180008ce2  xor     rcx, rsp; StackCookie
0x180008ce5  call    __security_check_cookie
0x180008cea  add     rsp, 80h
0x180008cf1  pop     r14
0x180008cf3  pop     rdi
0x180008cf4  pop     rsi
0x180008cf5  pop     rbx
0x180008cf6  pop     rbp
0x180008cf7  retn
```
