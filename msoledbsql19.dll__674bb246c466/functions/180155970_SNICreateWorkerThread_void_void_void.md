# SNICreateWorkerThread(void * (*)(void *),void *)

- ea: `0x180155970`
- end: `0x180155b47`
- name: `?SNICreateWorkerThread@@YAKP6APEAXPEAX@Z0@Z`
- size: `471`
- prototype: `unsigned int __fastcall(void *(*)(void *), void *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1801744b0`
- `0x180176400`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180155970`
- `0x18015a6f0`
- `0x18015a880`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180155a29`
- `KERNEL32!GetLastError` at `0x180155ae1`
- `KERNEL32!GetLastError` at `0x180155a29`
- `KERNEL32!GetLastError` at `0x180155ae1`
- `KERNEL32!CreateThread` at `0x180155a1b`
- `KERNEL32!CreateThread` at `0x180155a1b`
- `KERNEL32!CloseHandle` at `0x180155ad7`
- `KERNEL32!CloseHandle` at `0x180155ad7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SNICreateWorkerThread(void *(*a1)(void *), void *a2)
{
  _QWORD *v4; // rax
  DWORD LastError; // edi
  HANDLE Thread; // rbx
  __int64 v8; // [rsp+30h] [rbp-18h] BYREF

  v8 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802667E0[0] )
    bidScopeEnterW(&v8, off_1802667E0[0], a1, a2);
  v4 = (_QWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 16);
  if ( !v4 )
  {
    LastError = 8;
LABEL_10:
    if ( (bidGblFlags & 2) != 0 && off_180263EC0[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_180260B78[0], 2585600, off_180263EC0[0], 8);
    }
    SNISetLastError(8, LastError, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263EC8[0] )
      bidTraceW(off_180260B80[0], 2587648, off_180263EC8[0], LastError);
    goto LABEL_23;
  }
  *v4 = a1;
  v4[1] = a2;
  Thread = CreateThread(0, 0x1000u, ThreadHandle<SNIThreadHandleAllocator>::ThreadProcAdapter, v4, 0, 0);
  if ( Thread )
    LastError = 0;
  else
    LastError = GetLastError();
  if ( LastError )
    goto LABEL_10;
  if ( Thread && !CloseHandle(Thread) )
    GetLastError();
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180263ED0[0] )
    bidTraceW(off_180260B88[0], 2594816, off_180263ED0[0], 0);
  LastError = 0;
LABEL_23:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v8);
  return LastError;
}

```

## disassembly

```asm
0x180155970  mov     [rsp+arg_10], rbx
0x180155975  push    rdi
0x180155976  sub     rsp, 40h
0x18015597a  mov     rax, cs:__security_cookie
0x180155981  xor     rax, rsp
0x180155984  mov     [rsp+48h+var_10], rax
0x180155989  mov     rdi, rdx
0x18015598c  mov     rbx, rcx
0x18015598f  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFFh
0x180155998  mov     eax, cs:_bidGblFlags
0x18015599e  and     eax, 20004h
0x1801559a3  cmp     eax, 20004h
0x1801559a8  jnz     short loc_1801559CD
0x1801559aa  mov     rax, cs:off_1802667E0; "<SNICreateWorkerThread|API|SNI> pfnAsyn"...
0x1801559b1  test    rax, rax
0x1801559b4  jz      short loc_1801559CD
0x1801559b6  mov     r9, rdx
0x1801559b9  mov     r8, rcx
0x1801559bc  mov     rdx, cs:off_1802667E0; "<SNICreateWorkerThread|API|SNI> pfnAsyn"...
0x1801559c3  lea     rcx, [rsp+48h+var_18]
0x1801559c8  call    _bidScopeEnterW
0x1801559cd  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1801559d4  mov     rax, [rcx]
0x1801559d7  mov     edx, 10h
0x1801559dc  mov     rax, [rax+58h]
0x1801559e0  call    cs:__guard_dispatch_icall_fptr
0x1801559e6  test    rax, rax
0x1801559e9  jnz     short loc_1801559F2
0x1801559eb  mov     edi, 8
0x1801559f0  jmp     short loc_180155A3D
0x1801559f2  mov     [rax], rbx
0x1801559f5  mov     [rax+8], rdi
0x1801559f9  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x180155a02  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180155a0a  mov     r9, rax; lpParameter
0x180155a0d  lea     r8, ?ThreadProcAdapter@?$ThreadHandle@USNIThreadHandleAllocator@@@@CAKPEAX@Z; lpStartAddress
0x180155a14  mov     edx, 1000h; dwStackSize
0x180155a19  xor     ecx, ecx; lpThreadAttributes
0x180155a1b  call    cs:__imp_CreateThread
0x180155a21  mov     rbx, rax
0x180155a24  test    rax, rax
0x180155a27  jnz     short loc_180155A33
0x180155a29  call    cs:__imp_GetLastError
0x180155a2f  mov     edi, eax
0x180155a31  jmp     short loc_180155A35
0x180155a33  xor     edi, edi
0x180155a35  test    edi, edi
0x180155a37  jz      loc_180155ACF
0x180155a3d  test    byte ptr cs:_bidGblFlags, 2
0x180155a44  jz      short loc_180155A82
0x180155a46  mov     rax, cs:off_180263EC0; "<SNICreateWorkerThread|ERR|SNI> Provide"...
0x180155a4d  test    rax, rax
0x180155a50  jz      short loc_180155A82
0x180155a52  mov     ecx, 0C3B4h; unsigned int
0x180155a57  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180155a5c  mov     dword ptr [rsp+48h+lpThreadId], edi
0x180155a60  mov     [rsp+48h+dwCreationFlags], eax
0x180155a64  mov     r9d, 8
0x180155a6a  mov     r8, cs:off_180263EC0; "<SNICreateWorkerThread|ERR|SNI> Provide"...
0x180155a71  mov     edx, 277400h
0x180155a76  mov     rcx, cs:off_180260B78; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180155a7d  call    _bidTraceW
0x180155a82  mov     r8d, 0C3B4h
0x180155a88  mov     edx, edi
0x180155a8a  mov     ecx, 8
0x180155a8f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180155a94  mov     eax, cs:_bidGblFlags
0x180155a9a  and     eax, 20002h
0x180155a9f  cmp     eax, 20002h
0x180155aa4  jnz     short loc_180155B22
0x180155aa6  mov     rax, cs:off_180263EC8; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x180155aad  test    rax, rax
0x180155ab0  jz      short loc_180155B22
0x180155ab2  mov     r9d, edi
0x180155ab5  mov     r8, cs:off_180263EC8; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x180155abc  mov     edx, 277C00h
0x180155ac1  mov     rcx, cs:off_180260B80; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180155ac8  call    _bidTraceW
0x180155acd  jmp     short loc_180155B22
0x180155acf  test    rbx, rbx
0x180155ad2  jz      short loc_180155AE7
0x180155ad4  mov     rcx, rbx; hObject
0x180155ad7  call    cs:__imp_CloseHandle
0x180155add  test    eax, eax
0x180155adf  jnz     short loc_180155AE7
0x180155ae1  call    cs:__imp_GetLastError
0x180155ae7  mov     eax, cs:_bidGblFlags
0x180155aed  and     eax, 20002h
0x180155af2  cmp     eax, 20002h
0x180155af7  jnz     short loc_180155B20
0x180155af9  mov     rax, cs:off_180263ED0; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x180155b00  test    rax, rax
0x180155b03  jz      short loc_180155B20
0x180155b05  xor     r9d, r9d
0x180155b08  mov     r8, cs:off_180263ED0; "<SNICreateWorkerThread|RET|SNI> %d{WINE"...
0x180155b0f  mov     edx, 279800h
0x180155b14  mov     rcx, cs:off_180260B88; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180155b1b  call    _bidTraceW
0x180155b20  xor     edi, edi
0x180155b22  lea     rcx, [rsp+48h+var_18]; this
0x180155b27  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180155b2c  nop
0x180155b2d  mov     eax, edi
0x180155b2f  mov     rcx, [rsp+48h+var_10]
0x180155b34  xor     rcx, rsp; StackCookie
0x180155b37  call    __security_check_cookie
0x180155b3c  mov     rbx, [rsp+48h+arg_10]
0x180155b41  add     rsp, 40h
0x180155b45  pop     rdi
0x180155b46  retn
```
