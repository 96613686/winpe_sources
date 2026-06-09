# iSNSConnectToServer

- ea: `0x18000d8ac`
- end: `0x18000d957`
- name: `iSNSConnectToServer`
- size: `171`
- prototype: `__int64 __fastcall(__int64, __int64, SOCKET *, struct sockaddr *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c124`
- `0x18000c474`
- `0x18000ce28`

## callees

- `0x180001cfe`
- `0x18000d8ac`

## import_xrefs

- `ISCSIUM!DiscpEnableWinsock` at `0x18000d8d7`
- `ISCSIUM!DiscpEnableWinsock` at `0x18000d8d7`
- `ISCSIUM!DiscpEstablishTCPSocket` at `0x18000d8ff`
- `ISCSIUM!DiscpEstablishTCPSocket` at `0x18000d8ff`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d8e6`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d8e6`
- `ntdll!RtlEnterCriticalSection` at `0x18000d8d1`
- `ntdll!RtlEnterCriticalSection` at `0x18000d8d1`
- `WS2_32!__imp_closesocket` at `0x18000d938`
- `WS2_32!__imp_closesocket` at `0x18000d938`
- `WS2_32!__imp_getsockname` at `0x18000d92a`
- `WS2_32!__imp_getsockname` at `0x18000d92a`

## pseudocode

```c
__int64 __fastcall iSNSConnectToServer(__int64 a1, __int64 a2, SOCKET *a3, struct sockaddr *a4)
{
  unsigned int v7; // edi
  __int64 result; // rax
  SOCKET v9; // rcx
  int namelen; // [rsp+58h] [rbp+10h] BYREF

  namelen = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  v7 = DiscpEnableWinsock();
  RtlLeaveCriticalSection(&DiscpCritSection);
  if ( v7 )
    return v7;
  result = DiscpEstablishTCPSocket(a1, 3205, a3);
  if ( !(_DWORD)result )
  {
    memset_0(a4, 0, 0x80u);
    v9 = *a3;
    namelen = 128;
    if ( getsockname(v9, a4, &namelen) == -1 )
    {
      closesocket(*a3);
      result = 4026466307LL;
      *a3 = 0;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d8ac  mov     word ptr [rsp+namelen], dx
0x18000d8b1  push    rbx
0x18000d8b2  push    rbp
0x18000d8b3  push    rsi
0x18000d8b4  push    rdi
0x18000d8b5  sub     rsp, 28h
0x18000d8b9  mov     rbp, rcx
0x18000d8bc  mov     [rsp+48h+namelen], 0
0x18000d8c4  lea     rcx, DiscpCritSection; CriticalSection
0x18000d8cb  mov     rsi, r9
0x18000d8ce  mov     rbx, r8
0x18000d8d1  call    cs:__imp_RtlEnterCriticalSection
0x18000d8d7  call    cs:__imp_DiscpEnableWinsock
0x18000d8dd  lea     rcx, DiscpCritSection; CriticalSection
0x18000d8e4  mov     edi, eax
0x18000d8e6  call    cs:__imp_RtlLeaveCriticalSection
0x18000d8ec  test    edi, edi
0x18000d8ee  jz      short loc_18000D8F4
0x18000d8f0  mov     eax, edi
0x18000d8f2  jmp     short loc_18000D94E
0x18000d8f4  mov     edx, 0C85h
0x18000d8f9  mov     r8, rbx
0x18000d8fc  mov     rcx, rbp
0x18000d8ff  call    cs:__imp_DiscpEstablishTCPSocket
0x18000d905  test    eax, eax
0x18000d907  jnz     short loc_18000D94E
0x18000d909  mov     edi, 80h
0x18000d90e  xor     edx, edx; Val
0x18000d910  mov     r8d, edi; Size
0x18000d913  mov     rcx, rsi; void *
0x18000d916  call    memset_0
0x18000d91b  mov     rcx, [rbx]; s
0x18000d91e  lea     r8, [rsp+48h+namelen]; namelen
0x18000d923  mov     rdx, rsi; name
0x18000d926  mov     [rsp+48h+namelen], edi
0x18000d92a  call    cs:__imp_getsockname
0x18000d930  cmp     eax, 0FFFFFFFFh
0x18000d933  jnz     short loc_18000D94C
0x18000d935  mov     rcx, [rbx]; s
0x18000d938  call    cs:__imp_closesocket
0x18000d93e  mov     eax, 0EFFF0003h
0x18000d943  mov     qword ptr [rbx], 0
0x18000d94a  jmp     short loc_18000D94E
0x18000d94c  xor     eax, eax
0x18000d94e  add     rsp, 28h
0x18000d952  pop     rdi
0x18000d953  pop     rsi
0x18000d954  pop     rbp
0x18000d955  pop     rbx
0x18000d956  retn
```
