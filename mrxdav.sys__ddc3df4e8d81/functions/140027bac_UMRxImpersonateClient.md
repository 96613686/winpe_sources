# UMRxImpersonateClient

- ea: `0x140027bac`
- end: `0x140027ce2`
- name: `UMRxImpersonateClient`
- size: `310`
- prototype: `__int64 __fastcall(PSECURITY_CLIENT_CONTEXT ClientContext, __int64)`
- caller_count: `10`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004b00`
- `0x140010620`
- `0x1400145d0`
- `0x140014e00`
- `0x1400199a0`
- `0x14001b360`
- `0x14001dec0`
- `0x140020090`
- `0x140020660`
- `0x140020e80`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140027bac`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140027bdb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027c17`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027c6d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027caf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027bdb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027c17`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027c6d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140027caf`
- `ntoskrnl!SeImpersonateClientEx` at `0x140027c44`
- `ntoskrnl!SeImpersonateClientEx` at `0x140027c44`

## pseudocode

```c
__int64 __fastcall UMRxImpersonateClient(PSECURITY_CLIENT_CONTEXT ClientContext, __int64 a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  NTSTATUS v8; // edi
  __int64 v9; // rbx
  HANDLE v10; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x800) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 124, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x200) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qq(v6, 125, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v7, ClientContext);
    }
  }
  v8 = SeImpersonateClientEx(ClientContext, 0);
  if ( v8 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0 )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_q(v11, 127, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v12);
    }
    *(_DWORD *)(a2 + 20) |= 1u;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 126, WPP_a822c02206083b1dd333c41b90cba843_Traceguids, v10, v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140027bac  push    rbx
0x140027bae  push    rbp
0x140027baf  push    rsi
0x140027bb0  push    rdi
0x140027bb1  sub     rsp, 38h
0x140027bb5  mov     rsi, rdx
0x140027bb8  mov     rdi, rcx
0x140027bbb  mov     rbx, cs:WPP_GLOBAL_Control
0x140027bc2  lea     rbp, WPP_GLOBAL_Control
0x140027bc9  cmp     rbx, rbp
0x140027bcc  jz      short loc_140027C3F
0x140027bce  test    dword ptr [rbx+2Ch], 800h
0x140027bd5  jz      short loc_140027BFE
0x140027bd7  mov     rbx, [rbx+18h]
0x140027bdb  call    cs:__imp_PsGetCurrentThreadId
0x140027be2  nop     dword ptr [rax+rax+00h]
0x140027be7  mov     edx, 7Ch ; '|'
0x140027bec  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027bf3  mov     r9, rax
0x140027bf6  mov     rcx, rbx
0x140027bf9  call    WPP_SF_q
0x140027bfe  mov     rbx, cs:WPP_GLOBAL_Control
0x140027c05  cmp     rbx, rbp
0x140027c08  jz      short loc_140027C3F
0x140027c0a  test    dword ptr [rbx+2Ch], 200h
0x140027c11  jz      short loc_140027C3F
0x140027c13  mov     rbx, [rbx+18h]
0x140027c17  call    cs:__imp_PsGetCurrentThreadId
0x140027c1e  nop     dword ptr [rax+rax+00h]
0x140027c23  mov     edx, 7Dh ; '}'
0x140027c28  mov     [rsp+58h+var_38], rdi
0x140027c2d  mov     r9, rax
0x140027c30  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027c37  mov     rcx, rbx
0x140027c3a  call    WPP_SF_qq
0x140027c3f  xor     edx, edx; ServerThread
0x140027c41  mov     rcx, rdi; ClientContext
0x140027c44  call    cs:__imp_SeImpersonateClientEx
0x140027c4b  nop     dword ptr [rax+rax+00h]
0x140027c50  mov     edi, eax
0x140027c52  test    eax, eax
0x140027c54  jns     short loc_140027C96
0x140027c56  mov     rbx, cs:WPP_GLOBAL_Control
0x140027c5d  cmp     rbx, rbp
0x140027c60  jz      short loc_140027CD6
0x140027c62  mov     ecx, [rbx+2Ch]
0x140027c65  test    cl, cl
0x140027c67  jns     short loc_140027CD6
0x140027c69  mov     rbx, [rbx+18h]
0x140027c6d  call    cs:__imp_PsGetCurrentThreadId
0x140027c74  nop     dword ptr [rax+rax+00h]
0x140027c79  mov     edx, 7Eh ; '~'
0x140027c7e  mov     dword ptr [rsp+58h+var_38], edi
0x140027c82  mov     r9, rax
0x140027c85  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027c8c  mov     rcx, rbx
0x140027c8f  call    WPP_SF_qD
0x140027c94  jmp     short loc_140027CD6
0x140027c96  mov     rbx, cs:WPP_GLOBAL_Control
0x140027c9d  cmp     rbx, rbp
0x140027ca0  jz      short loc_140027CD2
0x140027ca2  test    dword ptr [rbx+2Ch], 400h
0x140027ca9  jz      short loc_140027CD2
0x140027cab  mov     rbx, [rbx+18h]
0x140027caf  call    cs:__imp_PsGetCurrentThreadId
0x140027cb6  nop     dword ptr [rax+rax+00h]
0x140027cbb  mov     edx, 7Fh
0x140027cc0  lea     r8, WPP_a822c02206083b1dd333c41b90cba843_Traceguids
0x140027cc7  mov     r9, rax
0x140027cca  mov     rcx, rbx
0x140027ccd  call    WPP_SF_q
0x140027cd2  or      dword ptr [rsi+14h], 1
0x140027cd6  mov     eax, edi
0x140027cd8  add     rsp, 38h
0x140027cdc  pop     rdi
0x140027cdd  pop     rsi
0x140027cde  pop     rbp
0x140027cdf  pop     rbx
0x140027ce0  retn
```
