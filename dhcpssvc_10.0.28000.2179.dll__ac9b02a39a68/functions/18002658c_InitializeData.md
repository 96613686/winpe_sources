# InitializeData

- ea: `0x18002658c`
- end: `0x1800266bb`
- name: `InitializeData`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025144`

## callees

- `0x180001838`
- `0x18000282c`
- `0x18002658c`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x180026600`
- `KERNEL32!GetComputerNameW` at `0x180026600`
- `KERNEL32!CreateEventW` at `0x18002668b`
- `KERNEL32!CreateEventW` at `0x18002668b`
- `KERNEL32!GetLastError` at `0x180026612`
- `KERNEL32!GetLastError` at `0x1800266a3`
- `KERNEL32!GetLastError` at `0x180026612`
- `KERNEL32!GetLastError` at `0x1800266a3`

## pseudocode

```c
DWORD InitializeData()
{
  __int64 v0; // rdx
  _QWORD *v1; // rax
  char *v2; // rcx
  DWORD LastError; // ebx
  DWORD v5; // ecx
  unsigned __int64 v6; // rax
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  DhcpLeaseExtension = 14400;
  qword_180154868 = (__int64)&PendingList;
  v0 = 512;
  PendingList = (__int64)&PendingList;
  v1 = &Buckets;
  v2 = (char *)&Buckets;
  DhcpGlobalScavengerTimeout = 60000;
  do
  {
    v1[1] = v2;
    *v1 = v2;
    v2 += 16;
    v1 += 2;
    --v0;
  }
  while ( v0 );
  ++dword_1800FD110;
  nSize = 16;
  if ( GetComputerNameW(&DhcpGlobalServerName, &nSize) )
  {
    v5 = nSize;
    v6 = 2LL * nSize;
    if ( v6 >= 0x20 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)&DhcpGlobalServerName + v6) = 0;
    DhcpGlobalServerNameLen = 2 * v5 + 2;
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
0x18002658c  mov     [rsp+arg_8], rbx
0x180026591  push    rdi
0x180026592  sub     rsp, 20h
0x180026596  lea     rax, PendingList
0x18002659d  mov     cs:DhcpLeaseExtension, 3840h
0x1800265a7  mov     cs:qword_180154868, rax
0x1800265ae  mov     edx, 200h
0x1800265b3  mov     cs:PendingList, rax
0x1800265ba  lea     rax, Buckets
0x1800265c1  mov     rcx, rax
0x1800265c4  mov     cs:DhcpGlobalScavengerTimeout, 0EA60h
0x1800265ce  mov     [rax+8], rcx
0x1800265d2  mov     [rax], rcx
0x1800265d5  add     rcx, 10h
0x1800265d9  lea     rax, [rax+10h]
0x1800265dd  sub     rdx, 1
0x1800265e1  jnz     short loc_1800265CE
0x1800265e3  inc     cs:dword_1800FD110
0x1800265e9  lea     rdi, DhcpGlobalServerName
0x1800265f0  mov     rcx, rdi; lpBuffer
0x1800265f3  mov     [rsp+28h+nSize], 10h
0x1800265fb  lea     rdx, [rsp+28h+nSize]; nSize
0x180026600  call    cs:__imp_GetComputerNameW
0x180026607  nop     dword ptr [rax+rax+00h]
0x18002660c  xor     ebx, ebx
0x18002660e  test    eax, eax
0x180026610  jnz     short loc_18002665F
0x180026612  call    cs:__imp_GetLastError
0x180026619  nop     dword ptr [rax+rax+00h]
0x18002661e  mov     ebx, eax
0x180026620  mov     rcx, cs:WPP_GLOBAL_Control
0x180026627  lea     rax, WPP_GLOBAL_Control
0x18002662e  cmp     rcx, rax
0x180026631  jz      short loc_180026651
0x180026633  test    byte ptr [rcx+1Ch], 10h
0x180026637  jz      short loc_180026651
0x180026639  mov     rcx, [rcx+10h]
0x18002663d  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180026644  mov     edx, 12h
0x180026649  mov     r9d, ebx
0x18002664c  call    WPP_SF_D
0x180026651  mov     eax, ebx
0x180026653  mov     rbx, [rsp+28h+arg_8]
0x180026658  add     rsp, 20h
0x18002665c  pop     rdi
0x18002665d  retn
0x18002665f  mov     ecx, [rsp+28h+nSize]
0x180026663  mov     eax, ecx
0x180026665  add     rax, rax
0x180026668  cmp     rax, 20h ; ' '
0x18002666c  jnb     short loc_1800266B5
0x18002666e  xor     r9d, r9d; lpName
0x180026671  mov     [rax+rdi], bx
0x180026675  lea     eax, ds:2[rcx*2]
0x18002667c  xor     r8d, r8d; bInitialState
0x18002667f  xor     ecx, ecx; lpEventAttributes
0x180026681  mov     cs:DhcpGlobalServerNameLen, eax
0x180026687  lea     edx, [r9+1]; bManualReset
0x18002668b  call    cs:__imp_CreateEventW
0x180026692  nop     dword ptr [rax+rax+00h]
0x180026697  mov     cs:DhcpGlobalGenericEndpointReadyEvent, rax
0x18002669e  test    rax, rax
0x1800266a1  jnz     short loc_1800266B1
0x1800266a3  call    cs:__imp_GetLastError
0x1800266aa  nop     dword ptr [rax+rax+00h]
0x1800266af  jmp     short loc_180026653
0x1800266b1  xor     eax, eax
0x1800266b3  jmp     short loc_180026653
0x1800266b5  call    __report_rangecheckfailure
```
