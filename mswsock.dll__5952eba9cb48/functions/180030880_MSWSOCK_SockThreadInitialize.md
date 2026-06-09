# MSWSOCK_SockThreadInitialize

- ea: `0x180030880`
- end: `0x1800308d7`
- name: `MSWSOCK_SockThreadInitialize`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002c390`
- `0x1800307b4`

## callees

- `0x180005f78`
- `0x180030880`
- `0x180038118`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003088a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003088a`

## pseudocode

```c
__int64 MSWSOCK_SockThreadInitialize()
{
  __int64 result; // rax

  if ( TlsGetValue(MSAFD_SockTlsSlot) || (result = MSAFD_SockThreadInitialize(), (_DWORD)result) )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_q(1025, 10, WPP_7bf4364a7a3230d446995a7829b0da73_Traceguids, NtCurrentTeb());
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180030880  sub     rsp, 28h
0x180030884  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x18003088a  call    cs:__imp_TlsGetValue
0x180030891  nop     dword ptr [rax+rax+00h]
0x180030896  test    rax, rax
0x180030899  jnz     short loc_1800308A4
0x18003089b  call    MSAFD_SockThreadInitialize
0x1800308a0  test    eax, eax
0x1800308a2  jz      short loc_1800308D1
0x1800308a4  test    byte ptr cs:xmmword_180063D60, 2
0x1800308ab  jz      short loc_1800308CC
0x1800308ad  mov     r9, gs:30h
0x1800308b6  lea     r8, WPP_7bf4364a7a3230d446995a7829b0da73_Traceguids
0x1800308bd  mov     edx, 0Ah
0x1800308c2  mov     ecx, 401h
0x1800308c7  call    WPP_SF_q
0x1800308cc  mov     eax, 1
0x1800308d1  add     rsp, 28h
0x1800308d5  retn
```
