# InitializeData

- ea: `0x180027024`
- end: `0x18002714c`
- name: `InitializeData`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025bf4`

## callees

- `0x180001834`
- `0x180002854`
- `0x180027024`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x180027091`
- `KERNEL32!GetComputerNameW` at `0x180027091`
- `KERNEL32!CreateEventW` at `0x18002711c`
- `KERNEL32!CreateEventW` at `0x18002711c`
- `KERNEL32!GetLastError` at `0x1800270a3`
- `KERNEL32!GetLastError` at `0x180027134`
- `KERNEL32!GetLastError` at `0x1800270a3`
- `KERNEL32!GetLastError` at `0x180027134`

## pseudocode

```c
DWORD InitializeData()
{
  __int64 v0; // rcx
  _QWORD *v1; // rax
  DWORD LastError; // ebx
  DWORD v4; // ecx
  unsigned __int64 v5; // rax
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  DhcpLeaseExtension = 14400;
  qword_1801548E8 = (__int64)&PendingList;
  v0 = 512;
  PendingList = (__int64)&PendingList;
  v1 = &Buckets;
  DhcpGlobalScavengerTimeout = 60000;
  do
  {
    v1[1] = v1;
    *v1 = v1;
    v1 += 2;
    --v0;
  }
  while ( v0 );
  ++dword_1800FB130;
  nSize = 16;
  if ( GetComputerNameW(&DhcpGlobalServerName, &nSize) )
  {
    v4 = nSize;
    v5 = 2LL * nSize;
    if ( v5 >= 0x20 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)&DhcpGlobalServerName + v5) = 0;
    DhcpGlobalServerNameLen = 2 * v4 + 2;
    DhcpGlobalGenericEndpointReadyEvent = CreateEventW(0, 1, 0, 0);
    if ( DhcpGlobalGenericEndpointReadyEvent )
      return 0;
    else
      return GetLastError();
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, LastError);
    return LastError;
  }
}

```

## disassembly

```asm
0x180027024  mov     [rsp+arg_8], rbx
0x180027029  push    rdi
0x18002702a  sub     rsp, 20h
0x18002702e  lea     rax, PendingList
0x180027035  mov     cs:DhcpLeaseExtension, 3840h
0x18002703f  mov     cs:qword_1801548E8, rax
0x180027046  mov     ecx, 200h
0x18002704b  mov     cs:PendingList, rax
0x180027052  lea     rax, Buckets
0x180027059  mov     cs:DhcpGlobalScavengerTimeout, 0EA60h
0x180027063  mov     [rax+8], rax
0x180027067  mov     [rax], rax
0x18002706a  add     rax, 10h
0x18002706e  sub     rcx, 1
0x180027072  jnz     short loc_180027063
0x180027074  inc     cs:dword_1800FB130
0x18002707a  lea     rdi, DhcpGlobalServerName
0x180027081  mov     rcx, rdi; lpBuffer
0x180027084  mov     [rsp+28h+nSize], 10h
0x18002708c  lea     rdx, [rsp+28h+nSize]; nSize
0x180027091  call    cs:__imp_GetComputerNameW
0x180027098  nop     dword ptr [rax+rax+00h]
0x18002709d  xor     ebx, ebx
0x18002709f  test    eax, eax
0x1800270a1  jnz     short loc_1800270F0
0x1800270a3  call    cs:__imp_GetLastError
0x1800270aa  nop     dword ptr [rax+rax+00h]
0x1800270af  mov     ebx, eax
0x1800270b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800270b8  lea     rax, WPP_GLOBAL_Control
0x1800270bf  cmp     rcx, rax
0x1800270c2  jz      short loc_1800270E2
0x1800270c4  test    byte ptr [rcx+1Ch], 10h
0x1800270c8  jz      short loc_1800270E2
0x1800270ca  mov     rcx, [rcx+10h]
0x1800270ce  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x1800270d5  mov     edx, 12h
0x1800270da  mov     r9d, ebx
0x1800270dd  call    WPP_SF_D
0x1800270e2  mov     eax, ebx
0x1800270e4  mov     rbx, [rsp+28h+arg_8]
0x1800270e9  add     rsp, 20h
0x1800270ed  pop     rdi
0x1800270ee  retn
0x1800270f0  mov     ecx, [rsp+28h+nSize]
0x1800270f4  mov     eax, ecx
0x1800270f6  add     rax, rax
0x1800270f9  cmp     rax, 20h ; ' '
0x1800270fd  jnb     short loc_180027146
0x1800270ff  xor     r9d, r9d; lpName
0x180027102  mov     [rax+rdi], bx
0x180027106  lea     eax, ds:2[rcx*2]
0x18002710d  xor     r8d, r8d; bInitialState
0x180027110  xor     ecx, ecx; lpEventAttributes
0x180027112  mov     cs:DhcpGlobalServerNameLen, eax
0x180027118  lea     edx, [r9+1]; bManualReset
0x18002711c  call    cs:__imp_CreateEventW
0x180027123  nop     dword ptr [rax+rax+00h]
0x180027128  mov     cs:DhcpGlobalGenericEndpointReadyEvent, rax
0x18002712f  test    rax, rax
0x180027132  jnz     short loc_180027142
0x180027134  call    cs:__imp_GetLastError
0x18002713b  nop     dword ptr [rax+rax+00h]
0x180027140  jmp     short loc_1800270E4
0x180027142  xor     eax, eax
0x180027144  jmp     short loc_1800270E4
0x180027146  call    __report_rangecheckfailure
```
