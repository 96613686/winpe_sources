# ClientElevationPipe::Initialize(void)

- ea: `0x1400441a0`
- end: `0x140044330`
- name: `?Initialize@ClientElevationPipe@@UEAAJXZ`
- size: `400`
- prototype: `__int64 __fastcall(ClientElevationPipe *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x1400070b0`
- `0x140020420`
- `0x1400441a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14004429d`
- `KERNEL32!GetLastError` at `0x1400442c0`
- `KERNEL32!GetLastError` at `0x14004429d`
- `KERNEL32!GetLastError` at `0x1400442c0`
- `KERNEL32!HeapAlloc` at `0x1400441c9`
- `KERNEL32!HeapAlloc` at `0x1400441c9`
- `KERNEL32!HeapFree` at `0x140044311`
- `KERNEL32!HeapFree` at `0x140044311`
- `KERNEL32!GetProcessHeap` at `0x1400441b2`
- `KERNEL32!GetProcessHeap` at `0x1400442fd`
- `KERNEL32!GetProcessHeap` at `0x1400441b2`
- `KERNEL32!GetProcessHeap` at `0x1400442fd`
- `KERNEL32!CreateEventW` at `0x140044211`
- `KERNEL32!CreateEventW` at `0x140044211`
- `KERNEL32!CreateFileW` at `0x140044282`
- `KERNEL32!CreateFileW` at `0x140044282`

## pseudocode

```c
__int64 __fastcall ClientElevationPipe::Initialize(ClientElevationPipe *this)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v3; // rsi
  unsigned int v4; // ebx
  char *EventW; // rax
  int v6; // eax
  HANDLE FileW; // rax
  signed int v8; // eax
  int v9; // r9d
  signed int LastError; // eax
  HANDLE v11; // rax

  ProcessHeap = GetProcessHeap();
  v3 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( v3 )
  {
    EventW = (char *)CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 8) = EventW;
    if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v9 = 94;
    }
    else
    {
      v6 = StringCchPrintfW(v3, 0x104u, L"\\\\.\\pipe\\%s", *((_QWORD *)this + 3));
      v4 = v6;
      if ( v6 < 0 )
      {
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ClientElevationPipe::Initialize", 97, v6);
LABEL_14:
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v3);
        return v4;
      }
      FileW = CreateFileW(v3, 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
      *((_QWORD *)this + 1) = FileW;
      if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_14;
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      v9 = 110;
    }
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ClientElevationPipe::Initialize", v9, v4);
    goto LABEL_14;
  }
  v4 = -2147024882;
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ClientElevationPipe::Initialize", 88, -2147024882);
  return v4;
}

```

## disassembly

```asm
0x1400441a0  mov     [rsp+arg_0], rbx
0x1400441a5  mov     [rsp+arg_8], rbp
0x1400441aa  push    rsi
0x1400441ab  sub     rsp, 40h
0x1400441af  mov     rbp, rcx
0x1400441b2  call    cs:__imp_GetProcessHeap
0x1400441b9  nop     dword ptr [rax+rax+00h]
0x1400441be  xor     edx, edx; dwFlags
0x1400441c0  mov     r8d, 208h; dwBytes
0x1400441c6  mov     rcx, rax; hHeap
0x1400441c9  call    cs:__imp_HeapAlloc
0x1400441d0  nop     dword ptr [rax+rax+00h]
0x1400441d5  mov     rsi, rax
0x1400441d8  test    rax, rax
0x1400441db  jnz     short loc_140044205
0x1400441dd  mov     ebx, 8007000Eh
0x1400441e2  lea     r9d, [rax+58h]
0x1400441e6  lea     r8, aClientelevatio_0; "ClientElevationPipe::Initialize"
0x1400441ed  mov     [rsp+48h+dwCreationDisposition], ebx
0x1400441f1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400441f8  lea     ecx, [rax+1]; Level
0x1400441fb  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140044200  jmp     loc_14004431D
0x140044205  xor     r9d, r9d; lpName
0x140044208  xor     r8d, r8d; bInitialState
0x14004420b  xor     ecx, ecx; lpEventAttributes
0x14004420d  lea     edx, [r9+1]; bManualReset
0x140044211  call    cs:__imp_CreateEventW
0x140044218  nop     dword ptr [rax+rax+00h]
0x14004421d  mov     [rbp+40h], rax
0x140044221  dec     rax
0x140044224  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140044228  ja      loc_1400442C0
0x14004422e  mov     r9, [rbp+18h]
0x140044232  lea     r8, aPipeS; "\\\\.\\pipe\\%s"
0x140044239  mov     edx, 104h; unsigned __int64
0x14004423e  mov     rcx, rsi; unsigned __int16 *
0x140044241  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140044246  mov     ebx, eax
0x140044248  test    eax, eax
0x14004424a  jns     short loc_14004425B
0x14004424c  mov     [rsp+48h+dwCreationDisposition], eax
0x140044250  mov     r9d, 61h ; 'a'
0x140044256  jmp     loc_1400442E5
0x14004425b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140044264  xor     r9d, r9d; lpSecurityAttributes
0x140044267  mov     [rsp+48h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x14004426f  xor     r8d, r8d; dwShareMode
0x140044272  mov     edx, 0C0000000h; dwDesiredAccess
0x140044277  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14004427f  mov     rcx, rsi; lpFileName
0x140044282  call    cs:__imp_CreateFileW
0x140044289  nop     dword ptr [rax+rax+00h]
0x14004428e  mov     [rbp+8], rax
0x140044292  inc     rax
0x140044295  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004429b  jnz     short loc_1400442FD
0x14004429d  call    cs:__imp_GetLastError
0x1400442a4  nop     dword ptr [rax+rax+00h]
0x1400442a9  mov     ebx, eax
0x1400442ab  test    eax, eax
0x1400442ad  jle     short loc_1400442B8
0x1400442af  movzx   ebx, ax
0x1400442b2  or      ebx, 80070000h
0x1400442b8  mov     r9d, 6Eh ; 'n'
0x1400442be  jmp     short loc_1400442E1
0x1400442c0  call    cs:__imp_GetLastError
0x1400442c7  nop     dword ptr [rax+rax+00h]
0x1400442cc  mov     ebx, eax
0x1400442ce  test    eax, eax
0x1400442d0  jle     short loc_1400442DB
0x1400442d2  movzx   ebx, ax
0x1400442d5  or      ebx, 80070000h
0x1400442db  mov     r9d, 5Eh ; '^'
0x1400442e1  mov     [rsp+48h+dwCreationDisposition], ebx
0x1400442e5  lea     r8, aClientelevatio_0; "ClientElevationPipe::Initialize"
0x1400442ec  mov     ecx, 1; Level
0x1400442f1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400442f8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400442fd  call    cs:__imp_GetProcessHeap
0x140044304  nop     dword ptr [rax+rax+00h]
0x140044309  mov     r8, rsi; lpMem
0x14004430c  xor     edx, edx; dwFlags
0x14004430e  mov     rcx, rax; hHeap
0x140044311  call    cs:__imp_HeapFree
0x140044318  nop     dword ptr [rax+rax+00h]
0x14004431d  mov     rbp, [rsp+48h+arg_8]
0x140044322  mov     eax, ebx
0x140044324  mov     rbx, [rsp+48h+arg_0]
0x140044329  add     rsp, 40h
0x14004432d  pop     rsi
0x14004432e  retn
```
