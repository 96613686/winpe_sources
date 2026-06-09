# Dhcpv6FindAndRefContext

- ea: `0x18000a430`
- end: `0x18000a4b3`
- name: `Dhcpv6FindAndRefContext`
- size: `131`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180009520`
- `0x180009a70`
- `0x180026858`
- `0x180026e30`
- `0x180027120`
- `0x180027440`
- `0x180027540`
- `0x1800276b0`
- `0x180027900`
- `0x180027a08`

## callees

- `0x18000a430`
- `0x18000b350`
- `0x1800269d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a455`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a455`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a478`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a478`

## pseudocode

```c
__int64 __fastcall Dhcpv6FindAndRefContext(__int64 a1, __int64 *a2)
{
  __int64 Dhcpv6ContextOnNicList; // rax
  __int64 v5; // rbx
  __int64 result; // rax

  if ( g_fVelocityAddUserClassTracing )
    return Dhcpv6FindAndRefContext_New(a1, a2);
  if ( !a1 )
    return 87;
  EnterCriticalSection(&Dhcpv6GlobalNicListCritSect);
  Dhcpv6ContextOnNicList = FindDhcpv6ContextOnNicList(a1);
  v5 = Dhcpv6ContextOnNicList;
  if ( Dhcpv6ContextOnNicList )
    _InterlockedIncrement((volatile signed __int32 *)(Dhcpv6ContextOnNicList + 16));
  LeaveCriticalSection(&Dhcpv6GlobalNicListCritSect);
  if ( !v5 )
    return 2;
  result = 0;
  *a2 = v5;
  return result;
}

```

## disassembly

```asm
0x18000a430  mov     [rsp+arg_0], rbx
0x18000a435  push    rdi
0x18000a436  sub     rsp, 20h
0x18000a43a  cmp     cs:g_fVelocityAddUserClassTracing, 0
0x18000a441  mov     rdi, rdx
0x18000a444  mov     rbx, rcx
0x18000a447  jnz     short loc_18000A49E
0x18000a449  test    rcx, rcx
0x18000a44c  jz      short loc_18000A4A5
0x18000a44e  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18000a455  call    cs:__imp_EnterCriticalSection
0x18000a45c  nop     dword ptr [rax+rax+00h]
0x18000a461  mov     rcx, rbx
0x18000a464  call    FindDhcpv6ContextOnNicList
0x18000a469  mov     rbx, rax
0x18000a46c  test    rax, rax
0x18000a46f  jnz     short loc_18000A498
0x18000a471  lea     rcx, Dhcpv6GlobalNicListCritSect; lpCriticalSection
0x18000a478  call    cs:__imp_LeaveCriticalSection
0x18000a47f  nop     dword ptr [rax+rax+00h]
0x18000a484  test    rbx, rbx
0x18000a487  jnz     short loc_18000A4AC
0x18000a489  lea     eax, [rbx+2]
0x18000a48c  mov     rbx, [rsp+28h+arg_0]
0x18000a491  add     rsp, 20h
0x18000a495  pop     rdi
0x18000a496  retn
0x18000a498  lock inc dword ptr [rax+10h]
0x18000a49c  jmp     short loc_18000A471
0x18000a49e  call    Dhcpv6FindAndRefContext_New
0x18000a4a3  jmp     short loc_18000A48C
0x18000a4a5  mov     eax, 57h ; 'W'
0x18000a4aa  jmp     short loc_18000A48C
0x18000a4ac  xor     eax, eax
0x18000a4ae  mov     [rdi], rbx
0x18000a4b1  jmp     short loc_18000A48C
```
