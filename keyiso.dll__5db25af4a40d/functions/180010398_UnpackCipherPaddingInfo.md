# _UnpackCipherPaddingInfo

- ea: `0x180010398`
- end: `0x1800104a9`
- name: `_UnpackCipherPaddingInfo`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800104b0`
- `0x180010660`

## callees

- `0x180003cf0`
- `0x18000d0ac`
- `0x180010398`

## string_xrefs

- `0x1800103bb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall UnpackCipherPaddingInfo(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v6; // r9
  unsigned int v7; // ebx
  int v8; // eax

  if ( !a1 )
  {
    v6 = 930;
LABEL_3:
    v7 = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", v6);
    return v7;
  }
  if ( *(_DWORD *)(a1 + 16) && *(_DWORD *)(a1 + 16) != 88 )
  {
    v6 = 939;
    goto LABEL_3;
  }
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  memset_0(a3, 0, 0x58u);
  *(_DWORD *)a2 = 40;
  *(_DWORD *)(a2 + 4) = *(_DWORD *)a1;
  if ( *(_DWORD *)(a1 + 4) )
  {
    *(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 8);
    *(_DWORD *)(a2 + 16) = *(_DWORD *)(a1 + 4);
  }
  v8 = *(_DWORD *)(a1 + 16);
  if ( v8 )
  {
    *(_DWORD *)(a2 + 32) = v8;
    *(_QWORD *)(a2 + 24) = a3;
    *a3 = 88;
    a3[1] = 1;
    a3[4] = *(_DWORD *)(a1 + 24);
    *((_QWORD *)a3 + 1) = *(_QWORD *)(a1 + 32);
    a3[8] = *(_DWORD *)(a1 + 40);
    *((_QWORD *)a3 + 3) = *(_QWORD *)(a1 + 48);
    a3[12] = *(_DWORD *)(a1 + 56);
    *((_QWORD *)a3 + 5) = *(_QWORD *)(a1 + 64);
    a3[16] = *(_DWORD *)(a1 + 72);
    *((_QWORD *)a3 + 7) = *(_QWORD *)(a1 + 80);
    a3[17] = *(_DWORD *)(a1 + 88);
    *((_QWORD *)a3 + 9) = *(_QWORD *)(a1 + 96);
    a3[20] = *(_DWORD *)(a1 + 104);
  }
  return 0;
}

```

## disassembly

```asm
0x180010398  mov     [rsp+arg_0], rbx
0x18001039d  mov     [rsp+arg_8], rsi
0x1800103a2  push    rdi
0x1800103a3  sub     rsp, 20h
0x1800103a7  mov     rsi, r8
0x1800103aa  mov     rdi, rdx
0x1800103ad  mov     rbx, rcx
0x1800103b0  test    rcx, rcx
0x1800103b3  jnz     short loc_1800103DD
0x1800103b5  mov     r9d, 3A2h
0x1800103bb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800103c2  mov     ecx, 80090027h
0x1800103c7  lea     rdx, aStatus; "Status"
0x1800103ce  mov     ebx, 80090027h
0x1800103d3  call    DebugTraceError
0x1800103d8  jmp     loc_180010497
0x1800103dd  cmp     dword ptr [rcx+10h], 0
0x1800103e1  jbe     short loc_1800103F1
0x1800103e3  cmp     dword ptr [rcx+10h], 58h ; 'X'
0x1800103e7  jz      short loc_1800103F1
0x1800103e9  mov     r9d, 3ABh
0x1800103ef  jmp     short loc_1800103BB
0x1800103f1  xorps   xmm0, xmm0
0x1800103f4  xor     eax, eax
0x1800103f6  movups  xmmword ptr [rdx], xmm0
0x1800103f9  mov     rcx, rsi; void *
0x1800103fc  movups  xmmword ptr [rdx+10h], xmm0
0x180010400  mov     [rdx+20h], rax
0x180010404  lea     r8d, [rax+58h]; Size
0x180010408  xor     edx, edx; Val
0x18001040a  call    memset_0
0x18001040f  mov     dword ptr [rdi], 28h ; '('
0x180010415  mov     eax, [rbx]
0x180010417  mov     [rdi+4], eax
0x18001041a  cmp     dword ptr [rbx+4], 0
0x18001041e  jbe     short loc_18001042E
0x180010420  mov     rax, [rbx+8]
0x180010424  mov     [rdi+8], rax
0x180010428  mov     eax, [rbx+4]
0x18001042b  mov     [rdi+10h], eax
0x18001042e  mov     eax, [rbx+10h]
0x180010431  test    eax, eax
0x180010433  jz      short loc_180010495
0x180010435  mov     [rdi+20h], eax
0x180010438  mov     [rdi+18h], rsi
0x18001043c  mov     dword ptr [rsi], 58h ; 'X'
0x180010442  mov     dword ptr [rsi+4], 1
0x180010449  mov     eax, [rbx+18h]
0x18001044c  mov     [rsi+10h], eax
0x18001044f  mov     rax, [rbx+20h]
0x180010453  mov     [rsi+8], rax
0x180010457  mov     eax, [rbx+28h]
0x18001045a  mov     [rsi+20h], eax
0x18001045d  mov     rax, [rbx+30h]
0x180010461  mov     [rsi+18h], rax
0x180010465  mov     eax, [rbx+38h]
0x180010468  mov     [rsi+30h], eax
0x18001046b  mov     rax, [rbx+40h]
0x18001046f  mov     [rsi+28h], rax
0x180010473  mov     eax, [rbx+48h]
0x180010476  mov     [rsi+40h], eax
0x180010479  mov     rax, [rbx+50h]
0x18001047d  mov     [rsi+38h], rax
0x180010481  mov     eax, [rbx+58h]
0x180010484  mov     [rsi+44h], eax
0x180010487  mov     rax, [rbx+60h]
0x18001048b  mov     [rsi+48h], rax
0x18001048f  mov     eax, [rbx+68h]
0x180010492  mov     [rsi+50h], eax
0x180010495  xor     ebx, ebx
0x180010497  mov     rsi, [rsp+28h+arg_8]
0x18001049c  mov     eax, ebx
0x18001049e  mov     rbx, [rsp+28h+arg_0]
0x1800104a3  add     rsp, 20h
0x1800104a7  pop     rdi
0x1800104a8  retn
```
