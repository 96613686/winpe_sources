# DnsInitWinsock

- ea: `0x18000ee5c`
- end: `0x18000f019`
- name: `DnsInitWinsock`
- size: `445`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000d1bc`
- `0x18000dfb8`
- `0x180039e64`
- `0x180079dd4`
- `0x18009f190`
- `0x1800a3b74`

## callees

- `0x18000ee5c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ee96`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ef32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eece`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eece`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ef61`
- `WS2_32!__imp_WSAStartup` at `0x18000ef19`
- `WS2_32!__imp_WSAStartup` at `0x18000ef19`
- `WS2_32!__imp_WSACleanup` at `0x18000ef75`
- `WS2_32!__imp_WSACleanup` at `0x18000ef75`

## pseudocode

```c
__int64 DnsInitWinsock()
{
  unsigned int v0; // ebx
  int v1; // edi
  unsigned int v3; // eax
  unsigned int v4; // edi
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  v0 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  EnterCriticalSection(&g_csWinsock);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 14, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids, (unsigned int)g_dwWinsockRefCount);
  if ( g_dwWinsockRefCount )
  {
    v1 = 0;
    ++g_dwWinsockRefCount;
  }
  else
  {
    v1 = 1;
  }
  LeaveCriticalSection(&g_csWinsock);
  if ( v1 )
  {
    v3 = WSAStartup(0x202u, &WSAData);
    v0 = v3;
    if ( v3 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        return v0;
      WPP_SF_d(1035, 15, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids, v3);
    }
    else
    {
      EnterCriticalSection(&g_csWinsock);
      v4 = g_dwWinsockRefCount++;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_d(1035, 16, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids, v4);
      LeaveCriticalSection(&g_csWinsock);
      if ( v4 )
        WSACleanup();
    }
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 17, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18000ee5c  mov     [rsp+arg_0], rbx
0x18000ee61  push    rdi
0x18000ee62  sub     rsp, 1D0h
0x18000ee69  mov     rax, cs:__security_cookie
0x18000ee70  xor     rax, rsp
0x18000ee73  mov     [rsp+1D8h+var_18], rax
0x18000ee7b  xor     edx, edx; Val
0x18000ee7d  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18000ee82  mov     r8d, 198h; Size
0x18000ee88  xor     ebx, ebx
0x18000ee8a  call    memset_0
0x18000ee8f  lea     rcx, g_csWinsock; lpCriticalSection
0x18000ee96  call    cs:__imp_EnterCriticalSection
0x18000ee9d  nop     dword ptr [rax+rax+00h]
0x18000eea2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000eea9  jnz     loc_18000EFBB
0x18000eeaf  mov     eax, cs:g_dwWinsockRefCount
0x18000eeb5  test    eax, eax
0x18000eeb7  jz      loc_18000EFB1
0x18000eebd  xor     edi, edi
0x18000eebf  inc     eax
0x18000eec1  mov     cs:g_dwWinsockRefCount, eax
0x18000eec7  lea     rcx, g_csWinsock; lpCriticalSection
0x18000eece  call    cs:__imp_LeaveCriticalSection
0x18000eed5  nop     dword ptr [rax+rax+00h]
0x18000eeda  test    edi, edi
0x18000eedc  jnz     short loc_18000EF0F
0x18000eede  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000eee5  jnz     loc_18000EFFB
0x18000eeeb  mov     eax, ebx
0x18000eeed  mov     rcx, [rsp+1D8h+var_18]
0x18000eef5  xor     rcx, rsp; StackCookie
0x18000eef8  call    __security_check_cookie
0x18000eefd  mov     rbx, [rsp+1D8h+arg_0]
0x18000ef05  add     rsp, 1D0h
0x18000ef0c  pop     rdi
0x18000ef0d  retn
0x18000ef0f  mov     ecx, 202h; wVersionRequested
0x18000ef14  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x18000ef19  call    cs:__imp_WSAStartup
0x18000ef20  nop     dword ptr [rax+rax+00h]
0x18000ef25  mov     ebx, eax
0x18000ef27  test    eax, eax
0x18000ef29  jnz     short loc_18000EF86
0x18000ef2b  lea     rcx, g_csWinsock; lpCriticalSection
0x18000ef32  call    cs:__imp_EnterCriticalSection
0x18000ef39  nop     dword ptr [rax+rax+00h]
0x18000ef3e  mov     edi, cs:g_dwWinsockRefCount
0x18000ef44  lea     edx, [rdi+1]
0x18000ef47  mov     cs:g_dwWinsockRefCount, edx
0x18000ef4d  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000ef54  jnz     loc_18000EFDD
0x18000ef5a  lea     rcx, g_csWinsock; lpCriticalSection
0x18000ef61  call    cs:__imp_LeaveCriticalSection
0x18000ef68  nop     dword ptr [rax+rax+00h]
0x18000ef6d  test    edi, edi
0x18000ef6f  jz      loc_18000EEDE
0x18000ef75  call    cs:__imp_WSACleanup
0x18000ef7c  nop     dword ptr [rax+rax+00h]
0x18000ef81  jmp     loc_18000EEDE
0x18000ef86  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18000ef8d  jz      loc_18000EEEB
0x18000ef93  mov     edx, 0Fh
0x18000ef98  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18000ef9f  mov     ecx, 40Bh
0x18000efa4  mov     r9d, eax
0x18000efa7  call    WPP_SF_d
0x18000efac  jmp     loc_18000EEDE
0x18000efb1  mov     edi, 1
0x18000efb6  jmp     loc_18000EEC7
0x18000efbb  mov     r9d, cs:g_dwWinsockRefCount
0x18000efc2  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18000efc9  mov     edx, 0Eh
0x18000efce  mov     ecx, 40Bh
0x18000efd3  call    WPP_SF_d
0x18000efd8  jmp     loc_18000EEAF
0x18000efdd  mov     edx, 10h
0x18000efe2  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18000efe9  mov     ecx, 40Bh
0x18000efee  mov     r9d, edi
0x18000eff1  call    WPP_SF_d
0x18000eff6  jmp     loc_18000EF5A
0x18000effb  mov     edx, 11h
0x18000f000  lea     r8, WPP_a95ff7eb17973a901025f7b3e2b4c359_Traceguids
0x18000f007  mov     ecx, 40Bh
0x18000f00c  mov     r9d, ebx
0x18000f00f  call    WPP_SF_d
0x18000f014  jmp     loc_18000EEEB
```
