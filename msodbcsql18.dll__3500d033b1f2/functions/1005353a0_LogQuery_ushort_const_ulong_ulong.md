# LogQuery(ushort const *,ulong,ulong)

- ea: `0x1005353a0`
- end: `0x100535512`
- name: `?LogQuery@@YAXPEBGKK@Z`
- size: `370`
- prototype: `void __fastcall(LPCVOID lpBuffer, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1004c8dd8`

## callees

- `0x1004070bc`
- `0x1005353a0`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x100535473`
- `KERNEL32!WriteFile` at `0x100535498`
- `KERNEL32!WriteFile` at `0x1005354b6`
- `KERNEL32!WriteFile` at `0x1005354d7`
- `KERNEL32!WriteFile` at `0x100535473`
- `KERNEL32!WriteFile` at `0x100535498`
- `KERNEL32!WriteFile` at `0x1005354b6`
- `KERNEL32!WriteFile` at `0x1005354d7`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1005353fc`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1005353fc`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1005353dc`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1005353dc`
- `api-ms-win-crt-time-l1-1-0!_wctime64` at `0x1005353e7`
- `api-ms-win-crt-time-l1-1-0!_wctime64` at `0x1005353e7`

## pseudocode

```c
void __fastcall LogQuery(LPCVOID lpBuffer, int a2, int a3)
{
  wchar_t *v6; // rax
  unsigned int FormattedMessage; // ebx
  int v8; // [rsp+28h] [rbp-D8h]
  __int64 NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  __time64_t Time; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE Destination[38]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v12; // [rsp+66h] [rbp-9Ah]
  unsigned __int16 Buffer[552]; // [rsp+70h] [rbp-90h] BYREF

  LODWORD(NumberOfBytesWritten) = 0;
  _time64(&Time);
  v6 = _wctime64(&Time);
  memcpy_s(Destination, 0x28u, v6, 0x28u);
  v8 = a3;
  v12 = 0;
  FormattedMessage = LoadFormattedMessage(
                       g_hinstance_language,
                       0x9C5Au,
                       Buffer,
                       0x223u,
                       Destination,
                       v8,
                       NumberOfBytesWritten);
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 8LL))((char *)g_csSQLPerf + 32);
  if ( g_fLogSlowQuery )
  {
    WriteFile(g_hPerfQueryFile, Buffer, 2 * FormattedMessage, (LPDWORD)&NumberOfBytesWritten, 0);
    WriteFile(g_hPerfQueryFile, L"\r\n", 4u, (LPDWORD)&NumberOfBytesWritten, 0);
    WriteFile(g_hPerfQueryFile, lpBuffer, 2 * a2, (LPDWORD)&NumberOfBytesWritten, 0);
    WriteFile(g_hPerfQueryFile, L"\r\n", 4u, (LPDWORD)&NumberOfBytesWritten, 0);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 24LL))((char *)g_csSQLPerf + 32);
}

```

## disassembly

```asm
0x1005353a0  push    rbp
0x1005353a2  push    rbx
0x1005353a3  push    rsi
0x1005353a4  push    rdi
0x1005353a5  push    r14
0x1005353a7  lea     rbp, [rsp-3D0h]
0x1005353af  sub     rsp, 4D0h
0x1005353b6  mov     rax, cs:__security_cookie
0x1005353bd  xor     rax, rsp
0x1005353c0  mov     [rbp+3F0h+var_30], rax
0x1005353c7  mov     rdi, rcx
0x1005353ca  xor     r14d, r14d
0x1005353cd  lea     rcx, [rsp+4F0h+Time]; Time
0x1005353d2  mov     dword ptr [rsp+4F0h+NumberOfBytesWritten], r14d
0x1005353d7  mov     ebx, r8d
0x1005353da  mov     esi, edx
0x1005353dc  call    cs:__imp__time64
0x1005353e2  lea     rcx, [rsp+4F0h+Time]; Time
0x1005353e7  call    cs:__imp__wctime64
0x1005353ed  lea     edx, [r14+28h]; DestinationSize
0x1005353f1  mov     r8, rax; Source
0x1005353f4  mov     r9d, edx; SourceSize
0x1005353f7  lea     rcx, [rsp+4F0h+Destination]; Destination
0x1005353fc  call    cs:__imp_memcpy_s
0x100535402  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x100535409  lea     rax, [rsp+4F0h+Destination]
0x10053540e  mov     [rsp+4F0h+var_4C8], ebx
0x100535412  lea     r8, [rsp+4F0h+Buffer]; unsigned __int16 *
0x100535417  mov     r9d, 223h; unsigned int
0x10053541d  mov     [rsp+4F0h+lpOverlapped], rax
0x100535422  mov     edx, 9C5Ah; unsigned int
0x100535427  mov     [rsp+4F0h+var_48A], r14w
0x10053542d  call    ?LoadFormattedMessage@@YAKPEAUHINSTANCE__@@KPEAGKZZ; LoadFormattedMessage(HINSTANCE__ *,ulong,ushort *,ulong,...)
0x100535432  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x100535439  mov     ebx, eax
0x10053543b  add     rcx, 20h ; ' '
0x10053543f  mov     rdx, [rcx]
0x100535442  mov     rax, [rdx+8]
0x100535446  call    cs:__guard_dispatch_icall_fptr
0x10053544c  cmp     cs:?g_fLogSlowQuery@@3HA, r14d; int g_fLogSlowQuery
0x100535453  jz      loc_1005354DD
0x100535459  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x100535460  lea     r8d, [rbx+rbx]; nNumberOfBytesToWrite
0x100535464  lea     r9, [rsp+4F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100535469  mov     [rsp+4F0h+lpOverlapped], r14; lpOverlapped
0x10053546e  lea     rdx, [rsp+4F0h+Buffer]; lpBuffer
0x100535473  call    cs:__imp_WriteFile
0x100535479  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x100535480  lea     ebx, [r14+4]
0x100535484  mov     r8d, ebx; nNumberOfBytesToWrite
0x100535487  mov     [rsp+4F0h+lpOverlapped], r14; lpOverlapped
0x10053548c  lea     r9, [rsp+4F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100535491  lea     rdx, asc_1005AB1E0; "\r\n"
0x100535498  call    cs:__imp_WriteFile
0x10053549e  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x1005354a5  lea     r8d, [rsi+rsi]; nNumberOfBytesToWrite
0x1005354a9  lea     r9, [rsp+4F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1005354ae  mov     [rsp+4F0h+lpOverlapped], r14; lpOverlapped
0x1005354b3  mov     rdx, rdi; lpBuffer
0x1005354b6  call    cs:__imp_WriteFile
0x1005354bc  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x1005354c3  lea     r9, [rsp+4F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1005354c8  mov     r8d, ebx; nNumberOfBytesToWrite
0x1005354cb  mov     [rsp+4F0h+lpOverlapped], r14; lpOverlapped
0x1005354d0  lea     rdx, asc_1005AB1E0; "\r\n"
0x1005354d7  call    cs:__imp_WriteFile
0x1005354dd  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x1005354e4  add     rcx, 20h ; ' '
0x1005354e8  mov     rax, [rcx]
0x1005354eb  mov     rax, [rax+18h]
0x1005354ef  call    cs:__guard_dispatch_icall_fptr
0x1005354f5  mov     rcx, [rbp+3F0h+var_30]
0x1005354fc  xor     rcx, rsp; StackCookie
0x1005354ff  call    __security_check_cookie
0x100535504  add     rsp, 4D0h
0x10053550b  pop     r14
0x10053550d  pop     rdi
0x10053550e  pop     rsi
0x10053550f  pop     rbx
0x100535510  pop     rbp
0x100535511  retn
```
