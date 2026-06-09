# TRANSPORT_NAMEDPIPE::SendReceive(int,uchar *,ulong,int)

- ea: `0x1800028c0`
- end: `0x1800029dd`
- name: `?SendReceive@TRANSPORT_NAMEDPIPE@@MEAAJHPEAEKH@Z`
- size: `285`
- prototype: `int(TRANSPORT_NAMEDPIPE *__hidden this, int, unsigned __int8 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800028c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000299d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000299d`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180002993`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180002993`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000295f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18000295f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002957`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180002957`

## pseudocode

```c
__int64 __fastcall TRANSPORT_NAMEDPIPE::SendReceive(
        TRANSPORT_NAMEDPIPE *this,
        int a2,
        unsigned __int8 *a3,
        DWORD a4,
        int a5)
{
  DWORD LastError; // ebx
  char *lpOverlapped; // rbp
  void *v9; // rcx
  BOOL File; // eax
  DWORD NumberOfBytesTransferred; // [rsp+58h] [rbp+10h] BYREF

  LastError = 0;
  NumberOfBytesTransferred = 0;
  lpOverlapped = (char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFC0uLL) + 88;
  *(_OWORD *)lpOverlapped = 0;
  *((_OWORD *)lpOverlapped + 1) = 0;
  if ( a5 )
    *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFC0uLL) + 136) = 0;
  else
    *(_QWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFC0uLL) + 112) = *(_QWORD *)((char *)this
                                                                                                + (-(__int64)(a2 != 0)
                                                                                                 & 0xFFFFFFFFFFFFFFF8uLL)
                                                                                                + 240)
                                                                                    + 1LL;
  v9 = (void *)*((_QWORD *)this + 28);
  if ( a2 )
    File = WriteFile(v9, a3, a4, 0, (LPOVERLAPPED)lpOverlapped);
  else
    File = ReadFile(v9, a3, a4, 0, (LPOVERLAPPED)lpOverlapped);
  if ( !File )
  {
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      LastError = 0;
      if ( a5 || GetOverlappedResult(*((HANDLE *)this + 28), (LPOVERLAPPED)lpOverlapped, &NumberOfBytesTransferred, 1) )
        return LastError;
      LastError = GetLastError();
    }
    else
    {
      *(_DWORD *)((char *)this + (-(__int64)(a2 != 0) & 0xFFFFFFFFFFFFFFC0uLL) + 136) = 1;
    }
    if ( (int)LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800028c0  mov     [rsp+arg_0], rbx
0x1800028c5  mov     [rsp+arg_10], rbp
0x1800028ca  push    rsi
0x1800028cb  push    rdi
0x1800028cc  push    r15
0x1800028ce  sub     rsp, 30h
0x1800028d2  xor     ebx, ebx
0x1800028d4  lea     rbp, [rcx+58h]
0x1800028d8  xorps   xmm0, xmm0
0x1800028db  mov     [rsp+48h+NumberOfBytesTransferred], ebx
0x1800028df  mov     eax, edx
0x1800028e1  mov     r11d, r9d
0x1800028e4  neg     eax
0x1800028e6  mov     r15, r8
0x1800028e9  mov     edi, edx
0x1800028eb  mov     rsi, rcx
0x1800028ee  sbb     r10, r10
0x1800028f1  mov     eax, edx
0x1800028f3  and     r10, 0FFFFFFFFFFFFFFC0h
0x1800028f7  add     rbp, r10
0x1800028fa  movups  xmmword ptr [rbp+0], xmm0
0x1800028fe  movups  xmmword ptr [rbp+10h], xmm0
0x180002902  cmp     [rsp+48h+arg_20], ebx
0x180002906  jz      short loc_18000291A
0x180002908  neg     eax
0x18000290a  sbb     rcx, rcx
0x18000290d  and     rcx, 0FFFFFFFFFFFFFFC0h
0x180002911  mov     [rcx+rsi+88h], ebx
0x180002918  jmp     short loc_18000293E
0x18000291a  neg     eax
0x18000291c  mov     eax, edi
0x18000291e  sbb     rcx, rcx
0x180002921  and     rcx, 0FFFFFFFFFFFFFFF8h
0x180002925  mov     rdx, [rcx+rsi+0F0h]
0x18000292d  inc     rdx
0x180002930  neg     eax
0x180002932  sbb     rcx, rcx
0x180002935  and     rcx, 0FFFFFFFFFFFFFFC0h
0x180002939  mov     [rcx+rsi+70h], rdx
0x18000293e  mov     rcx, [rsi+0E0h]; hFile
0x180002945  xor     r9d, r9d; lpNumberOfBytesRead
0x180002948  mov     [rsp+48h+lpOverlapped], rbp; lpOverlapped
0x18000294d  mov     r8d, r11d; nNumberOfBytesToRead
0x180002950  mov     rdx, r15; lpBuffer
0x180002953  test    edi, edi
0x180002955  jz      short loc_18000295F
0x180002957  call    cs:__imp_WriteFile
0x18000295d  jmp     short loc_180002965
0x18000295f  call    cs:__imp_ReadFile
0x180002965  test    eax, eax
0x180002967  jnz     short loc_1800029C8
0x180002969  call    cs:__imp_GetLastError
0x18000296f  mov     ebx, eax
0x180002971  cmp     eax, 3E5h
0x180002976  jnz     short loc_1800029A7
0x180002978  xor     ebx, ebx
0x18000297a  cmp     [rsp+48h+arg_20], ebx
0x18000297e  jnz     short loc_1800029C8
0x180002980  mov     rcx, [rsi+0E0h]; hFile
0x180002987  lea     r9d, [rbx+1]; bWait
0x18000298b  lea     r8, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180002990  mov     rdx, rbp; lpOverlapped
0x180002993  call    cs:__imp_GetOverlappedResult
0x180002999  test    eax, eax
0x18000299b  jnz     short loc_1800029C8
0x18000299d  call    cs:__imp_GetLastError
0x1800029a3  mov     ebx, eax
0x1800029a5  jmp     short loc_1800029BB
0x1800029a7  neg     edi
0x1800029a9  sbb     rax, rax
0x1800029ac  and     rax, 0FFFFFFFFFFFFFFC0h
0x1800029b0  mov     dword ptr [rax+rsi+88h], 1
0x1800029bb  test    ebx, ebx
0x1800029bd  jle     short loc_1800029C8
0x1800029bf  movzx   ebx, bx
0x1800029c2  or      ebx, 80070000h
0x1800029c8  mov     rbp, [rsp+48h+arg_10]
0x1800029cd  mov     eax, ebx
0x1800029cf  mov     rbx, [rsp+48h+arg_0]
0x1800029d4  add     rsp, 30h
0x1800029d8  pop     r15
0x1800029da  pop     rdi
0x1800029db  pop     rsi
0x1800029dc  retn
```
