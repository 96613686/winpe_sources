# SockFindAndReferenceSocket

- ea: `0x180008190`
- end: `0x18000824a`
- name: `SockFindAndReferenceSocket`
- size: `186`
- prototype: ``
- caller_count: `36`
- callee_count: `4`
- tags: ``

## callers

- `0x180002240`
- `0x180004700`
- `0x180005810`
- `0x180006d00`
- `0x180007080`
- `0x180008320`
- `0x1800087c0`
- `0x180008870`
- `0x180008cb0`
- `0x180009d20`
- `0x18000a2a0`
- `0x18000c2b0`
- `0x18000de00`
- `0x18000f540`
- `0x18000faa0`
- `0x180010030`
- `0x180011e60`
- `0x180012600`
- `0x180013670`
- `0x180014030`
- `0x180014420`
- `0x180014c00`
- `0x1800182d0`
- `0x180018ba0`
- `0x1800198a0`
- `0x18001d990`
- `0x180021800`
- `0x180021b90`
- `0x180025530`
- `0x180026800`
- `0x180026d70`
- `0x180027140`
- `0x180029144`
- `0x18003dbe4`
- `0x18004abd0`
- `0x180051ff0`

## callees

- `0x180008190`
- `0x180008250`
- `0x18000d000`
- `0x180038118`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800081d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800081d1`
- `WS2_32!WahReferenceContextByHandle` at `0x1800081af`
- `WS2_32!WahReferenceContextByHandle` at `0x1800081af`

## pseudocode

```c
char *__fastcall SockFindAndReferenceSocket(HANDLE FileHandle, char a2)
{
  __int64 v4; // rax
  volatile signed __int32 *v5; // rbx
  _DWORD *Value; // rax
  __int64 v7; // rdx
  __int64 v8; // r8

  v4 = WahReferenceContextByHandle(SockContextTable, FileHandle);
  v5 = (volatile signed __int32 *)v4;
  if ( v4 )
  {
    if ( *(_DWORD *)(v4 + 24) == -1 )
    {
      Value = TlsGetValue(MSAFD_SockTlsSlot);
      if ( !Value || !Value[8] )
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_q(1025, 10, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, FileHandle);
        if ( _InterlockedExchangeAdd(v5, 0xFFFFFFFF) == 1 )
          SockDestroySocket((__int64)v5, v7, v8);
        return 0;
      }
    }
    return (char *)v5;
  }
  else
  {
    if ( !a2 )
      return 0;
    return SockImportHandle(FileHandle, 0, 1);
  }
}

```

## disassembly

```asm
0x180008190  mov     [rsp+arg_0], rbx
0x180008195  mov     [rsp+arg_8], rsi
0x18000819a  push    rdi
0x18000819b  sub     rsp, 20h
0x18000819f  mov     sil, dl
0x1800081a2  mov     rdi, rcx
0x1800081a5  mov     rdx, rcx
0x1800081a8  mov     rcx, cs:SockContextTable
0x1800081af  call    cs:__imp_WahReferenceContextByHandle
0x1800081b6  nop     dword ptr [rax+rax+00h]
0x1800081bb  mov     rbx, rax
0x1800081be  test    rax, rax
0x1800081c1  jz      short loc_180008236
0x1800081c3  mov     edx, [rax+18h]
0x1800081c6  cmp     edx, 0FFFFFFFFh
0x1800081c9  jnz     short loc_180008231
0x1800081cb  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x1800081d1  call    cs:__imp_TlsGetValue
0x1800081d8  nop     dword ptr [rax+rax+00h]
0x1800081dd  test    rax, rax
0x1800081e0  jz      short loc_1800081E8
0x1800081e2  cmp     dword ptr [rax+20h], 0
0x1800081e6  jnz     short loc_180008231
0x1800081e8  test    byte ptr cs:xmmword_180063D60, 2
0x1800081ef  jz      short loc_18000820A
0x1800081f1  mov     edx, 0Ah
0x1800081f6  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x1800081fd  mov     ecx, 401h
0x180008202  mov     r9, rdi
0x180008205  call    WPP_SF_q
0x18000820a  or      eax, 0FFFFFFFFh
0x18000820d  lock xadd [rbx], eax
0x180008211  cmp     eax, 1
0x180008214  jnz     short loc_18000821E
0x180008216  mov     rcx, rbx
0x180008219  call    SockDestroySocket
0x18000821e  xor     eax, eax
0x180008220  mov     rbx, [rsp+28h+arg_0]
0x180008225  mov     rsi, [rsp+28h+arg_8]
0x18000822a  add     rsp, 20h
0x18000822e  pop     rdi
0x18000822f  retn
0x180008231  mov     rax, rbx
0x180008234  jmp     short loc_180008220
0x180008236  test    sil, sil
0x180008239  jz      short loc_18000821E
0x18000823b  mov     r8b, 1
0x18000823e  xor     edx, edx
0x180008240  mov     rcx, rdi; FileHandle
0x180008243  call    SockImportHandle
0x180008248  jmp     short loc_180008220
```
