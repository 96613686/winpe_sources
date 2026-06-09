# AcceptExRecvCompletionRoutine

- ea: `0x180051390`
- end: `0x1800514ad`
- name: `AcceptExRecvCompletionRoutine`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008250`
- `0x180024f14`
- `0x180038104`
- `0x18003ae8c`
- `0x18003aefc`
- `0x180042128`
- `0x180051390`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18005147e`
- `ntdll!RtlFreeHeap` at `0x18005147e`

## pseudocode

```c
char __fastcall AcceptExRecvCompletionRoutine(__int64 a1, int a2, __int64 a3)
{
  unsigned int v5; // edi
  char v6; // al
  __int64 v7; // rbx
  void *v8; // rsi
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  signed __int32 v12; // eax

  v5 = a1;
  v6 = BYTE2(xmmword_180063D60);
  if ( (BYTE2(xmmword_180063D60) & 4) != 0 )
  {
    WPP_SF_(1042, 17, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids);
    v6 = BYTE2(xmmword_180063D60);
  }
  v7 = a3 - 640;
  v8 = *(void **)(a3 + 24);
  if ( v5 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 18, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, v5);
LABEL_11:
    AbortSanConnection(v7);
    goto LABEL_12;
  }
  if ( (v6 & 4) != 0 )
    WPP_SF_qq(1042, 19, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, v7, *(_QWORD *)(*(_QWORD *)v7 + 8LL));
  v9 = AfdCompleteAccept(a1, *(_QWORD *)(*(_QWORD *)v7 + 8LL), *(_QWORD *)(v7 + 216) + 24LL, v8, a2);
  if ( v9 )
  {
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_d(1025, 20, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids, v9);
    goto LABEL_11;
  }
LABEL_12:
  RtlFreeHeap(SockPrivateHeap, 0, v8);
  v12 = _InterlockedExchangeAdd(*(volatile signed __int32 **)(v7 + 8), 0xFFFFFFFF);
  if ( v12 == 1 )
    LOBYTE(v12) = SockDestroySocket(*(_QWORD *)(v7 + 8), v10, v11);
  return v12;
}

```

## disassembly

```asm
0x180051390  push    rbx
0x180051392  push    rbp
0x180051393  push    rsi
0x180051394  push    rdi
0x180051395  sub     rsp, 38h
0x180051399  mov     rsi, r8
0x18005139c  mov     ebp, edx
0x18005139e  mov     edi, ecx
0x1800513a0  mov     al, byte ptr cs:xmmword_180063D60+2
0x1800513a6  test    al, 4
0x1800513a8  jz      short loc_1800513C6
0x1800513aa  mov     edx, 11h
0x1800513af  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x1800513b6  mov     ecx, 412h
0x1800513bb  call    WPP_SF_
0x1800513c0  mov     al, byte ptr cs:xmmword_180063D60+2
0x1800513c6  lea     rbx, [rsi-280h]
0x1800513cd  mov     rsi, [rsi+18h]
0x1800513d1  test    edi, edi
0x1800513d3  jz      short loc_1800513FD
0x1800513d5  test    byte ptr cs:xmmword_180063D60, 2
0x1800513dc  jz      loc_18005146A
0x1800513e2  mov     edx, 12h
0x1800513e7  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x1800513ee  mov     ecx, 401h
0x1800513f3  mov     r9d, edi
0x1800513f6  call    WPP_SF_d
0x1800513fb  jmp     short loc_18005146A
0x1800513fd  test    al, 4
0x1800513ff  jz      short loc_180051426
0x180051401  mov     rax, [rbx]
0x180051404  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x18005140b  mov     edx, 13h
0x180051410  mov     ecx, 412h
0x180051415  mov     r9, rbx
0x180051418  mov     rax, [rax+8]
0x18005141c  mov     [rsp+58h+var_38], rax
0x180051421  call    WPP_SF_qq
0x180051426  mov     rdx, [rbx]
0x180051429  mov     r9, rsi
0x18005142c  mov     r8, [rbx+0D8h]
0x180051433  add     r8, 18h
0x180051437  mov     dword ptr [rsp+58h+var_38], ebp
0x18005143b  mov     rdx, [rdx+8]
0x18005143f  call    AfdCompleteAccept
0x180051444  test    eax, eax
0x180051446  jz      short loc_180051472
0x180051448  test    byte ptr cs:xmmword_180063D60, 2
0x18005144f  jz      short loc_18005146A
0x180051451  mov     edx, 14h
0x180051456  lea     r8, WPP_7dff6be8156b39f872850f702c5305fc_Traceguids
0x18005145d  mov     ecx, 401h
0x180051462  mov     r9d, eax
0x180051465  call    WPP_SF_d
0x18005146a  mov     rcx, rbx
0x18005146d  call    AbortSanConnection
0x180051472  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180051479  mov     r8, rsi; P
0x18005147c  xor     edx, edx; Flags
0x18005147e  call    cs:__imp_RtlFreeHeap
0x180051485  nop     dword ptr [rax+rax+00h]
0x18005148a  mov     rcx, [rbx+8]
0x18005148e  or      eax, 0FFFFFFFFh
0x180051491  lock xadd [rcx], eax
0x180051495  cmp     eax, 1
0x180051498  jnz     short loc_1800514A3
0x18005149a  mov     rcx, [rbx+8]
0x18005149e  call    SockDestroySocket
0x1800514a3  add     rsp, 38h
0x1800514a7  pop     rdi
0x1800514a8  pop     rsi
0x1800514a9  pop     rbp
0x1800514aa  pop     rbx
0x1800514ab  retn
```
