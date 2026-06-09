# ServerElevationPipe::Initialize(void)

- ea: `0x140044340`
- end: `0x14004458d`
- name: `?Initialize@ServerElevationPipe@@UEAAJXZ`
- size: `589`
- prototype: `__int64 __fastcall(ServerElevationPipe *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400070b0`
- `0x140020420`
- `0x140044340`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400443dd`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400443dd`
- `KERNEL32!GetLastError` at `0x1400443ed`
- `KERNEL32!GetLastError` at `0x1400444cc`
- `KERNEL32!GetLastError` at `0x1400444ec`
- `KERNEL32!GetLastError` at `0x14004450f`
- `KERNEL32!GetLastError` at `0x1400443ed`
- `KERNEL32!GetLastError` at `0x1400444cc`
- `KERNEL32!GetLastError` at `0x1400444ec`
- `KERNEL32!GetLastError` at `0x14004450f`
- `KERNEL32!HeapAlloc` at `0x140044374`
- `KERNEL32!HeapAlloc` at `0x140044374`
- `KERNEL32!HeapFree` at `0x14004455d`
- `KERNEL32!HeapFree` at `0x14004455d`
- `KERNEL32!GetProcessHeap` at `0x14004435d`
- `KERNEL32!GetProcessHeap` at `0x140044549`
- `KERNEL32!GetProcessHeap` at `0x14004435d`
- `KERNEL32!GetProcessHeap` at `0x140044549`
- `KERNEL32!CreateEventW` at `0x140044421`
- `KERNEL32!CreateEventW` at `0x140044421`
- `KERNEL32!LocalFree` at `0x140044573`
- `KERNEL32!LocalFree` at `0x140044573`
- `KERNEL32!CreateNamedPipeW` at `0x14004449b`
- `KERNEL32!CreateNamedPipeW` at `0x14004449b`
- `KERNEL32!ConnectNamedPipe` at `0x1400444bc`
- `KERNEL32!ConnectNamedPipe` at `0x1400444bc`

## pseudocode

```c
__int64 __fastcall ServerElevationPipe::Initialize(ServerElevationPipe *this)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rsi
  signed int v4; // ebx
  signed int LastError; // eax
  int v6; // r9d
  char *EventW; // rax
  int v8; // eax
  char *NamedPipeW; // rax
  signed int v10; // eax
  signed int v11; // eax
  HANDLE v12; // rax
  struct _SECURITY_ATTRIBUTES SecurityDescriptor[3]; // [rsp+40h] [rbp-48h] BYREF

  memset(SecurityDescriptor, 0, 24);
  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  if ( !v3 )
  {
    v4 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Initialize", 261, -2147024882);
    goto LABEL_23;
  }
  SecurityDescriptor[0].nLength = 24;
  SecurityDescriptor[0].lpSecurityDescriptor = 0;
  SecurityDescriptor[0].bInheritHandle = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;BA)(A;;GA;;;SY)",
          1u,
          &SecurityDescriptor[0].lpSecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v6 = 275;
LABEL_21:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Initialize", v6, v4);
      goto LABEL_22;
    }
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 8) = EventW;
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = GetLastError();
    v4 = v11;
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    v6 = 281;
    goto LABEL_21;
  }
  v8 = StringCchPrintfW(v3, 0x400u, L"\\\\.\\pipe\\%s", *((_QWORD *)this + 3));
  v4 = v8;
  if ( v8 >= 0 )
  {
    NamedPipeW = (char *)CreateNamedPipeW(v3, 0x40000003u, 8u, 1u, 0x200u, 0x200u, 0x3E8u, SecurityDescriptor);
    *((_QWORD *)this + 1) = NamedPipeW;
    if ( (unsigned __int64)(NamedPipeW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
      v6 = 298;
    }
    else
    {
      if ( !ConnectNamedPipe(NamedPipeW, (LPOVERLAPPED)((char *)this + 40)) && GetLastError() == 997 )
        goto LABEL_22;
      v4 = -2147467259;
      v6 = 306;
    }
    goto LABEL_21;
  }
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Initialize", 284, v8);
LABEL_22:
  v12 = GetProcessHeap();
  HeapFree(v12, 0, v3);
LABEL_23:
  if ( SecurityDescriptor[0].lpSecurityDescriptor )
    LocalFree(SecurityDescriptor[0].lpSecurityDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140044340  push    rbx
0x140044342  push    rbp
0x140044343  push    rsi
0x140044344  push    rdi
0x140044345  push    r14
0x140044347  sub     rsp, 60h
0x14004434b  xorps   xmm0, xmm0
0x14004434e  xor     eax, eax
0x140044350  movups  xmmword ptr [rsp+88h+SecurityDescriptor], xmm0
0x140044355  mov     [rsp+88h+var_38], rax
0x14004435a  mov     rbp, rcx
0x14004435d  call    cs:__imp_GetProcessHeap
0x140044364  nop     dword ptr [rax+rax+00h]
0x140044369  xor     edx, edx; dwFlags
0x14004436b  mov     r8d, 800h; dwBytes
0x140044371  mov     rcx, rax; hHeap
0x140044374  call    cs:__imp_HeapAlloc
0x14004437b  nop     dword ptr [rax+rax+00h]
0x140044380  mov     rsi, rax
0x140044383  test    rax, rax
0x140044386  jnz     short loc_1400443B2
0x140044388  mov     ebx, 8007000Eh
0x14004438d  lea     r8, aServerelevatio; "ServerElevationPipe::Initialize"
0x140044394  mov     r9d, 105h
0x14004439a  mov     [rsp+88h+nOutBufferSize], ebx
0x14004439e  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400443a5  lea     ecx, [rax+1]; Level
0x1400443a8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400443ad  jmp     loc_140044569
0x1400443b2  mov     edi, 1
0x1400443b7  mov     dword ptr [rsp+88h+SecurityDescriptor], 18h
0x1400443bf  mov     edx, edi; StringSDRevision
0x1400443c1  mov     [rsp+88h+SecurityDescriptor+8], 0
0x1400443ca  xor     r9d, r9d; SecurityDescriptorSize
0x1400443cd  mov     dword ptr [rsp+88h+var_38], edi
0x1400443d1  lea     r8, [rsp+88h+SecurityDescriptor+8]; SecurityDescriptor
0x1400443d6  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x1400443dd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400443e4  nop     dword ptr [rax+rax+00h]
0x1400443e9  test    eax, eax
0x1400443eb  jnz     short loc_140044417
0x1400443ed  call    cs:__imp_GetLastError
0x1400443f4  nop     dword ptr [rax+rax+00h]
0x1400443f9  mov     ebx, eax
0x1400443fb  test    eax, eax
0x1400443fd  jle     short loc_140044408
0x1400443ff  movzx   ebx, ax
0x140044402  or      ebx, 80070000h
0x140044408  test    ebx, ebx
0x14004440a  jns     short loc_140044417
0x14004440c  mov     r9d, 113h
0x140044412  jmp     loc_140044530
0x140044417  xor     r9d, r9d; lpName
0x14004441a  xor     r8d, r8d; bInitialState
0x14004441d  mov     edx, edi; bManualReset
0x14004441f  xor     ecx, ecx; lpEventAttributes
0x140044421  call    cs:__imp_CreateEventW
0x140044428  nop     dword ptr [rax+rax+00h]
0x14004442d  mov     [rbp+40h], rax
0x140044431  dec     rax
0x140044434  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140044438  ja      loc_14004450F
0x14004443e  mov     r9, [rbp+18h]
0x140044442  lea     r8, aPipeS; "\\\\.\\pipe\\%s"
0x140044449  mov     edx, 400h; unsigned __int64
0x14004444e  mov     rcx, rsi; unsigned __int16 *
0x140044451  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140044456  mov     ebx, eax
0x140044458  test    eax, eax
0x14004445a  jns     short loc_14004446B
0x14004445c  mov     [rsp+88h+nOutBufferSize], eax
0x140044460  mov     r9d, 11Ch
0x140044466  jmp     loc_140044534
0x14004446b  lea     rax, [rsp+88h+SecurityDescriptor]
0x140044470  mov     r9d, edi; nMaxInstances
0x140044473  mov     [rsp+88h+lpSecurityAttributes], rax; lpSecurityAttributes
0x140044478  mov     edx, 40000003h; dwOpenMode
0x14004447d  mov     eax, 200h
0x140044482  mov     [rsp+88h+nDefaultTimeOut], 3E8h; nDefaultTimeOut
0x14004448a  mov     [rsp+88h+nInBufferSize], eax; nInBufferSize
0x14004448e  mov     r8d, 8; dwPipeMode
0x140044494  mov     rcx, rsi; lpName
0x140044497  mov     [rsp+88h+nOutBufferSize], eax; nOutBufferSize
0x14004449b  call    cs:__imp_CreateNamedPipeW
0x1400444a2  nop     dword ptr [rax+rax+00h]
0x1400444a7  mov     [rbp+8], rax
0x1400444ab  lea     rcx, [rax-1]
0x1400444af  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1400444b3  ja      short loc_1400444EC
0x1400444b5  lea     rdx, [rbp+28h]; lpOverlapped
0x1400444b9  mov     rcx, rax; hNamedPipe
0x1400444bc  call    cs:__imp_ConnectNamedPipe
0x1400444c3  nop     dword ptr [rax+rax+00h]
0x1400444c8  test    eax, eax
0x1400444ca  jnz     short loc_1400444DF
0x1400444cc  call    cs:__imp_GetLastError
0x1400444d3  nop     dword ptr [rax+rax+00h]
0x1400444d8  cmp     eax, 3E5h
0x1400444dd  jz      short loc_140044549
0x1400444df  mov     ebx, 80004005h
0x1400444e4  mov     r9d, 132h
0x1400444ea  jmp     short loc_140044530
0x1400444ec  call    cs:__imp_GetLastError
0x1400444f3  nop     dword ptr [rax+rax+00h]
0x1400444f8  mov     ebx, eax
0x1400444fa  test    eax, eax
0x1400444fc  jle     short loc_140044507
0x1400444fe  movzx   ebx, ax
0x140044501  or      ebx, 80070000h
0x140044507  mov     r9d, 12Ah
0x14004450d  jmp     short loc_140044530
0x14004450f  call    cs:__imp_GetLastError
0x140044516  nop     dword ptr [rax+rax+00h]
0x14004451b  mov     ebx, eax
0x14004451d  test    eax, eax
0x14004451f  jle     short loc_14004452A
0x140044521  movzx   ebx, ax
0x140044524  or      ebx, 80070000h
0x14004452a  mov     r9d, 119h
0x140044530  mov     [rsp+88h+nOutBufferSize], ebx
0x140044534  lea     r8, aServerelevatio; "ServerElevationPipe::Initialize"
0x14004453b  mov     ecx, edi; Level
0x14004453d  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140044544  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140044549  call    cs:__imp_GetProcessHeap
0x140044550  nop     dword ptr [rax+rax+00h]
0x140044555  mov     r8, rsi; lpMem
0x140044558  xor     edx, edx; dwFlags
0x14004455a  mov     rcx, rax; hHeap
0x14004455d  call    cs:__imp_HeapFree
0x140044564  nop     dword ptr [rax+rax+00h]
0x140044569  mov     rcx, [rsp+88h+SecurityDescriptor+8]; hMem
0x14004456e  test    rcx, rcx
0x140044571  jz      short loc_14004457F
0x140044573  call    cs:__imp_LocalFree
0x14004457a  nop     dword ptr [rax+rax+00h]
0x14004457f  mov     eax, ebx
0x140044581  add     rsp, 60h
0x140044585  pop     r14
0x140044587  pop     rdi
0x140044588  pop     rsi
0x140044589  pop     rbp
0x14004458a  pop     rbx
0x14004458b  retn
```
