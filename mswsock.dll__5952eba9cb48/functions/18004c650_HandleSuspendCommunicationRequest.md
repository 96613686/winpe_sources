# HandleSuspendCommunicationRequest

- ea: `0x18004c650`
- end: `0x18004c76a`
- name: `HandleSuspendCommunicationRequest`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800485dc`

## callees

- `0x180008250`
- `0x180038104`
- `0x18003aefc`
- `0x18003dae8`
- `0x18004c650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c6b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c711`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c6b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c711`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c68f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c68f`

## pseudocode

```c
void __fastcall HandleSuspendCommunicationRequest(char *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  char v4; // al

  if ( SBYTE2(xmmword_180063D60) < 0 )
    WPP_SF_qq(1047, 50, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids, *(_QWORD *)(*(_QWORD *)a1 + 8LL), a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( *((_DWORD *)a1 + 44) == 1 )
  {
    if ( (a1[801] & 4) != 0 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
      return;
    }
    v4 = a1[800];
    a1[208] = 1;
    if ( v4 < 0 )
      *((_DWORD *)a1 + 108) = 1;
    a1[800] = v4 & 0x7F;
    _InterlockedDecrement(&SockSanSocksDoingDup);
    if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)a1 + 1), 0xFFFFFFFF) == 1 )
      SockDestroySocket(*((_QWORD *)a1 + 1), v2, v3);
  }
  *((_DWORD *)a1 + 44) = 3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  if ( SBYTE2(xmmword_180063D60) < 0 )
    WPP_SF_(1047, 51, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids);
  SendControlMessage(a1, 0, 0);
}

```

## disassembly

```asm
0x18004c650  mov     [rsp+arg_0], rbx
0x18004c655  push    rdi
0x18004c656  sub     rsp, 30h
0x18004c65a  mov     rbx, rcx
0x18004c65d  cmp     byte ptr cs:xmmword_180063D60+2, 0
0x18004c664  jge     short loc_18004C688
0x18004c666  mov     r9, [rcx]
0x18004c669  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004c670  mov     edx, 32h ; '2'
0x18004c675  mov     [rsp+38h+var_18], rbx
0x18004c67a  mov     ecx, 417h
0x18004c67f  mov     r9, [r9+8]
0x18004c683  call    WPP_SF_qq
0x18004c688  lea     rdi, [rbx+30h]
0x18004c68c  mov     rcx, rdi; lpCriticalSection
0x18004c68f  call    cs:__imp_EnterCriticalSection
0x18004c696  nop     dword ptr [rax+rax+00h]
0x18004c69b  cmp     dword ptr [rbx+0B0h], 1
0x18004c6a2  jnz     short loc_18004C704
0x18004c6a4  test    byte ptr [rbx+321h], 4
0x18004c6ab  jz      short loc_18004C6C1
0x18004c6ad  mov     rcx, rdi; lpCriticalSection
0x18004c6b0  call    cs:__imp_LeaveCriticalSection
0x18004c6b7  nop     dword ptr [rax+rax+00h]
0x18004c6bc  jmp     loc_18004C75E
0x18004c6c1  mov     al, [rbx+320h]
0x18004c6c7  mov     byte ptr [rbx+0D0h], 1
0x18004c6ce  test    al, al
0x18004c6d0  jns     short loc_18004C6DC
0x18004c6d2  mov     dword ptr [rbx+1B0h], 1
0x18004c6dc  and     al, 7Fh
0x18004c6de  mov     [rbx+320h], al
0x18004c6e4  lock dec cs:SockSanSocksDoingDup
0x18004c6eb  mov     rax, [rbx+8]
0x18004c6ef  or      ecx, 0FFFFFFFFh
0x18004c6f2  lock xadd [rax], ecx
0x18004c6f6  cmp     ecx, 1
0x18004c6f9  jnz     short loc_18004C704
0x18004c6fb  mov     rcx, [rbx+8]
0x18004c6ff  call    SockDestroySocket
0x18004c704  mov     rcx, rdi; lpCriticalSection
0x18004c707  mov     dword ptr [rbx+0B0h], 3
0x18004c711  call    cs:__imp_LeaveCriticalSection
0x18004c718  nop     dword ptr [rax+rax+00h]
0x18004c71d  cmp     byte ptr cs:xmmword_180063D60+2, 0
0x18004c724  jge     short loc_18004C73C
0x18004c726  mov     edx, 33h ; '3'
0x18004c72b  lea     r8, WPP_d7b6f03f9037311bd7eee0d0c42309bc_Traceguids
0x18004c732  mov     ecx, 417h
0x18004c737  call    WPP_SF_
0x18004c73c  mov     [rsp+38h+var_10], 0
0x18004c745  xor     r9d, r9d
0x18004c748  xor     r8d, r8d
0x18004c74b  mov     [rsp+38h+var_18], 0
0x18004c754  mov     dl, 10h
0x18004c756  mov     rcx, rbx
0x18004c759  call    SendControlMessage
0x18004c75e  mov     rbx, [rsp+38h+arg_0]
0x18004c763  add     rsp, 30h
0x18004c767  pop     rdi
0x18004c768  retn
```
