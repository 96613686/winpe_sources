# HandleRdmaReadCompletion

- ea: `0x18004f6c4`
- end: `0x18004f7c3`
- name: `HandleRdmaReadCompletion`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a520`

## callees

- `0x180008250`
- `0x180038a20`
- `0x18003cdc8`
- `0x18003dae8`
- `0x18004f6c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f72a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f72a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f708`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f708`

## pseudocode

```c
char __fastcall HandleRdmaReadCompletion(__int64 a1, int a2, int a3)
{
  __int64 v3; // rbx
  _DWORD *v5; // rsi
  __int64 v7; // rdx
  __int64 v8; // r8
  signed __int32 v9; // eax

  v3 = *(_QWORD *)(a1 + 56);
  v5 = *(_DWORD **)(a1 + 64);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
  if ( !a3 )
    v5[10] += a2;
  v5[27] = 1;
  v5[8] = a3;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 48));
  if ( !a3 )
    SendControlMessage((PVOID)v3, 0, 0);
  if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
    WPP_SF_qD(1036, 24, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids, v5, v5[10]);
  CheckPendingAppRecvs((char *)v3);
  v9 = _InterlockedExchangeAdd(*(volatile signed __int32 **)(v3 + 8), 0xFFFFFFFF);
  if ( v9 == 1 )
    LOBYTE(v9) = SockDestroySocket(*(_QWORD *)(v3 + 8), v7, v8);
  return v9;
}

```

## disassembly

```asm
0x18004f6c4  push    rbx
0x18004f6c6  push    rbp
0x18004f6c7  push    rsi
0x18004f6c8  push    rdi
0x18004f6c9  push    r12
0x18004f6cb  push    r13
0x18004f6cd  push    r14
0x18004f6cf  push    r15
0x18004f6d1  sub     rsp, 38h
0x18004f6d5  mov     rbx, [rcx+38h]
0x18004f6d9  mov     ebp, r8d
0x18004f6dc  mov     rsi, [rcx+40h]
0x18004f6e0  mov     r14d, edx
0x18004f6e3  mov     rax, [rbx+0D8h]
0x18004f6ea  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004f6ee  movzx   r13d, byte ptr [rbx+8Eh]
0x18004f6f6  movzx   r12d, byte ptr [rax+28h]
0x18004f6fb  mov     eax, [rbx+0D4h]
0x18004f701  mov     [rsp+78h+arg_10], eax
0x18004f708  call    cs:__imp_EnterCriticalSection
0x18004f70f  nop     dword ptr [rax+rax+00h]
0x18004f714  test    ebp, ebp
0x18004f716  jnz     short loc_18004F71C
0x18004f718  add     [rsi+28h], r14d
0x18004f71c  lea     rcx, [rbx+30h]; lpCriticalSection
0x18004f720  mov     dword ptr [rsi+6Ch], 1
0x18004f727  mov     [rsi+20h], ebp
0x18004f72a  call    cs:__imp_LeaveCriticalSection
0x18004f731  nop     dword ptr [rax+rax+00h]
0x18004f736  test    ebp, ebp
0x18004f738  jnz     short loc_18004F767
0x18004f73a  mov     r9d, [rsp+78h+arg_10]
0x18004f742  mov     r8, r14
0x18004f745  or      r9, r13
0x18004f748  mov     [rsp+78h+var_50], 0
0x18004f751  or      r9, r12
0x18004f754  mov     [rsp+78h+var_58], 0
0x18004f75d  mov     dl, 2
0x18004f75f  mov     rcx, rbx
0x18004f762  call    SendControlMessage
0x18004f767  test    byte ptr cs:xmmword_180063D60+1, 10h
0x18004f76e  jz      short loc_18004F790
0x18004f770  mov     eax, [rsi+28h]
0x18004f773  lea     r8, WPP_c3b0ca9683b83d20c098afa417d2e04a_Traceguids
0x18004f77a  mov     edx, 18h
0x18004f77f  mov     dword ptr [rsp+78h+var_58], eax
0x18004f783  mov     ecx, 40Ch
0x18004f788  mov     r9, rsi
0x18004f78b  call    WPP_SF_qD
0x18004f790  mov     rcx, rbx; CompletionContext
0x18004f793  call    CheckPendingAppRecvs
0x18004f798  mov     rcx, [rbx+8]
0x18004f79c  or      eax, 0FFFFFFFFh
0x18004f79f  lock xadd [rcx], eax
0x18004f7a3  cmp     eax, 1
0x18004f7a6  jnz     short loc_18004F7B1
0x18004f7a8  mov     rcx, [rbx+8]
0x18004f7ac  call    SockDestroySocket
0x18004f7b1  add     rsp, 38h
0x18004f7b5  pop     r15
0x18004f7b7  pop     r14
0x18004f7b9  pop     r13
0x18004f7bb  pop     r12
0x18004f7bd  pop     rdi
0x18004f7be  pop     rsi
0x18004f7bf  pop     rbp
0x18004f7c0  pop     rbx
0x18004f7c1  retn
```
