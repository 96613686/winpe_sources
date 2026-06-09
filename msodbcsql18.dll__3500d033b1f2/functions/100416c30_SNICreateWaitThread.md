# SNICreateWaitThread

- ea: `0x100416c30`
- end: `0x100416e4c`
- name: `SNICreateWaitThread`
- size: `540`
- prototype: `__int64 __fastcall(LPTHREAD_START_ROUTINE lpStartAddress, LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1004171e8`

## callees

- `0x100416c30`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!CreateThread` at `0x100416d47`
- `KERNEL32!CreateThread` at `0x100416d47`
- `KERNEL32!GetLastError` at `0x100416d5a`
- `KERNEL32!GetLastError` at `0x100416d5a`

## pseudocode

```c
__int64 __fastcall SNICreateWaitThread(LPTHREAD_START_ROUTINE lpStartAddress, LPVOID lpParameter)
{
  DWORD LastError; // ebx
  wchar_t *v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rbx
  HANDLE Thread; // rax
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E77F8[0] )
    bidScopeEnterW(&v10, off_1005E77F8[0], lpStartAddress);
  if ( gnWorkerThreadCount < 0x40 )
  {
    v7 = gnWorkerThreadCount++;
    Thread = CreateThread(0, 0x1000u, lpStartAddress, lpParameter, 0, 0);
    rghWorkerThreads[v7] = (__int64)Thread;
    if ( Thread || (LastError = GetLastError()) == 0 )
    {
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E47A0[0] )
        bidTraceW(0, 2771968, off_1005E47A0[0], 0);
      LastError = 0;
    }
    else
    {
      --gnWorkerThreadCount;
      if ( (bidGblFlags & 2) != 0 && off_1005E4790[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 2764800, off_1005E4790[0], 9);
      }
      SNISetLastError(9, LastError, 50100);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4798[0] )
      {
        v5 = off_1005E4798[0];
        v6 = 2766848;
        goto LABEL_19;
      }
    }
  }
  else
  {
    LastError = 164;
    if ( (bidGblFlags & 2) != 0 && off_1005E4780[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 2746368, off_1005E4780[0], 9);
    }
    SNISetLastError(9, 164, 50100);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4788[0] )
    {
      v5 = off_1005E4788[0];
      v6 = 2748416;
LABEL_19:
      bidTraceW(0, v6, v5, LastError);
    }
  }
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v10);
  return LastError;
}

```

## disassembly

```asm
0x100416c30  mov     r11, rsp
0x100416c33  mov     [r11+8], rbx
0x100416c37  mov     [r11+10h], rsi
0x100416c3b  mov     [r11+20h], rdi
0x100416c3f  push    r14
0x100416c41  sub     rsp, 30h
0x100416c45  mov     eax, cs:_bidGblFlags
0x100416c4b  mov     rsi, rcx
0x100416c4e  or      qword ptr [r11+18h], 0FFFFFFFFFFFFFFFFh
0x100416c53  mov     ecx, 20004h
0x100416c58  and     eax, ecx
0x100416c5a  mov     rdi, rdx
0x100416c5d  cmp     eax, ecx
0x100416c5f  jnz     short loc_100416C83
0x100416c61  mov     rax, cs:off_1005E77F8; "<SNICreateWaitThread|API|SNI> pfnAsyncW"...
0x100416c68  test    rax, rax
0x100416c6b  jz      short loc_100416C83
0x100416c6d  mov     r9, rdx
0x100416c70  lea     rcx, [r11+18h]
0x100416c74  mov     rdx, cs:off_1005E77F8; "<SNICreateWaitThread|API|SNI> pfnAsyncW"...
0x100416c7b  mov     r8, rsi
0x100416c7e  call    _bidScopeEnterW
0x100416c83  mov     eax, cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x100416c89  cmp     eax, 40h ; '@'
0x100416c8c  jb      loc_100416D1D
0x100416c92  test    byte ptr cs:_bidGblFlags, 2
0x100416c99  mov     edi, 0C3B4h
0x100416c9e  mov     ebx, 0A4h
0x100416ca3  mov     esi, 9
0x100416ca8  jz      short loc_100416CDB
0x100416caa  mov     rax, cs:off_1005E4780; "<SNICreateWaitThread|ERR|SNI> ProviderN"...
0x100416cb1  test    rax, rax
0x100416cb4  jz      short loc_100416CDB
0x100416cb6  mov     ecx, edi; unsigned int
0x100416cb8  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100416cbd  mov     r8, cs:off_1005E4780; "<SNICreateWaitThread|ERR|SNI> ProviderN"...
0x100416cc4  mov     r9d, esi
0x100416cc7  mov     edx, 29E800h
0x100416ccc  mov     dword ptr [rsp+38h+var_10], ebx
0x100416cd0  xor     ecx, ecx
0x100416cd2  mov     [rsp+38h+var_18], eax
0x100416cd6  call    _bidTraceW
0x100416cdb  mov     r8d, edi
0x100416cde  mov     edx, ebx
0x100416ce0  mov     ecx, esi
0x100416ce2  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100416ce7  mov     eax, cs:_bidGblFlags
0x100416ced  mov     ecx, 20002h
0x100416cf2  and     eax, ecx
0x100416cf4  cmp     eax, ecx
0x100416cf6  jnz     loc_100416E2A
0x100416cfc  mov     rax, cs:off_1005E4788; "<SNICreateWaitThread|RET|SNI> %d{WINERR"...
0x100416d03  test    rax, rax
0x100416d06  jz      loc_100416E2A
0x100416d0c  mov     r8, cs:off_1005E4788; "<SNICreateWaitThread|RET|SNI> %d{WINERR"...
0x100416d13  mov     edx, 29F000h
0x100416d18  jmp     loc_100416DE9
0x100416d1d  and     [rsp+38h+var_10], 0
0x100416d23  lea     r14, ?rghWorkerThreads@@3PAV?$ThreadHandle@USNIThreadHandleAllocator@@@@A; ThreadHandle<SNIThreadHandleAllocator> near * rghWorkerThreads
0x100416d2a  and     [rsp+38h+var_18], 0
0x100416d2f  mov     rbx, rax
0x100416d32  inc     eax
0x100416d34  mov     r9, rdi; lpParameter
0x100416d37  mov     r8, rsi; lpStartAddress
0x100416d3a  mov     cs:?gnWorkerThreadCount@@3KA, eax; ulong gnWorkerThreadCount
0x100416d40  mov     edx, 1000h; dwStackSize
0x100416d45  xor     ecx, ecx; lpThreadAttributes
0x100416d47  call    cs:__imp_CreateThread
0x100416d4d  mov     [r14+rbx*8], rax
0x100416d51  test    rax, rax
0x100416d54  jnz     loc_100416DF5
0x100416d5a  call    cs:__imp_GetLastError
0x100416d60  mov     ebx, eax
0x100416d62  test    eax, eax
0x100416d64  jz      loc_100416DF5
0x100416d6a  dec     cs:?gnWorkerThreadCount@@3KA; ulong gnWorkerThreadCount
0x100416d70  mov     edi, 0C3B4h
0x100416d75  test    byte ptr cs:_bidGblFlags, 2
0x100416d7c  mov     esi, 9
0x100416d81  jz      short loc_100416DB4
0x100416d83  mov     rax, cs:off_1005E4790; "<SNICreateWaitThread|ERR|SNI> ProviderN"...
0x100416d8a  test    rax, rax
0x100416d8d  jz      short loc_100416DB4
0x100416d8f  mov     ecx, edi; unsigned int
0x100416d91  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100416d96  mov     r8, cs:off_1005E4790; "<SNICreateWaitThread|ERR|SNI> ProviderN"...
0x100416d9d  mov     r9d, esi
0x100416da0  mov     edx, 2A3000h
0x100416da5  mov     dword ptr [rsp+38h+var_10], ebx
0x100416da9  xor     ecx, ecx
0x100416dab  mov     [rsp+38h+var_18], eax
0x100416daf  call    _bidTraceW
0x100416db4  mov     r8d, edi
0x100416db7  mov     edx, ebx
0x100416db9  mov     ecx, esi
0x100416dbb  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100416dc0  mov     eax, cs:_bidGblFlags
0x100416dc6  mov     ecx, 20002h
0x100416dcb  and     eax, ecx
0x100416dcd  cmp     eax, ecx
0x100416dcf  jnz     short loc_100416E2A
0x100416dd1  mov     rax, cs:off_1005E4798; "<SNICreateWaitThread|RET|SNI> %d{WINERR"...
0x100416dd8  test    rax, rax
0x100416ddb  jz      short loc_100416E2A
0x100416ddd  mov     r8, cs:off_1005E4798; "<SNICreateWaitThread|RET|SNI> %d{WINERR"...
0x100416de4  mov     edx, 2A3800h
0x100416de9  mov     r9d, ebx
0x100416dec  xor     ecx, ecx
0x100416dee  call    _bidTraceW
0x100416df3  jmp     short loc_100416E2A
0x100416df5  mov     eax, cs:_bidGblFlags
0x100416dfb  mov     ecx, 20002h
0x100416e00  and     eax, ecx
0x100416e02  cmp     eax, ecx
0x100416e04  jnz     short loc_100416E28
0x100416e06  mov     rax, cs:off_1005E47A0; "<SNICreateWaitThread|RET|SNI> %d{WINERR"...
0x100416e0d  test    rax, rax
0x100416e10  jz      short loc_100416E28
0x100416e12  mov     r8, cs:off_1005E47A0; "<SNICreateWaitThread|RET|SNI> %d{WINERR"...
0x100416e19  xor     r9d, r9d
0x100416e1c  mov     edx, 2A4C00h
0x100416e21  xor     ecx, ecx
0x100416e23  call    _bidTraceW
0x100416e28  xor     ebx, ebx
0x100416e2a  lea     rcx, [rsp+38h+arg_10]; this
0x100416e2f  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100416e34  mov     rsi, [rsp+38h+arg_8]
0x100416e39  mov     eax, ebx
0x100416e3b  mov     rbx, [rsp+38h+arg_0]
0x100416e40  mov     rdi, [rsp+38h+arg_18]
0x100416e45  add     rsp, 30h
0x100416e49  pop     r14
0x100416e4b  retn
```
