# CsrThreadLazyRegister

- ea: `0x180002880`
- end: `0x1800029f9`
- name: `CsrThreadLazyRegister`
- size: `377`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800097f0`

## callees

- `0x180002880`
- `0x180002a00`

## import_xrefs

- `ntdll!NtClose` at `0x1800029de`
- `ntdll!NtClose` at `0x1800029de`
- `ntdll!NtAlpcOpenSenderThread` at `0x180002943`
- `ntdll!NtAlpcOpenSenderThread` at `0x180002943`

## pseudocode

```c
__int64 __fastcall CsrThreadLazyRegister(__int64 **a1, __int64 a2)
{
  __int64 v2; // r10
  __int64 v3; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rbx
  __int64 result; // rax
  int v8; // eax
  __int64 *v9; // r8
  __int64 *i; // rcx
  __int64 *v11; // rdx
  int Thread; // edi
  _QWORD v13[4]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v14; // [rsp+50h] [rbp-28h]
  HANDLE Handle; // [rsp+80h] [rbp+8h] BYREF

  v2 = CsrRootProcess;
  v3 = a2 + 8;
  *a1 = 0;
  v5 = (_QWORD *)(v2 + 16);
  while ( 1 )
  {
    v6 = (__int64)(v5 - 2);
    if ( *(v5 - 2) == *(_QWORD *)(a2 + 8) )
      break;
    v5 = (_QWORD *)*v5;
    if ( v5 == (_QWORD *)(v2 + 16) )
      return 0;
  }
  if ( v6 == v2 )
    return 0;
  v8 = 0x1FFFFF;
  if ( (*(_DWORD *)(v6 + 92) & 0x2000) != 0 )
    v8 = 1055744;
  v13[0] = 48;
  Handle = 0;
  memset(&v13[1], 0, 24);
  v14 = 0;
  result = NtAlpcOpenSenderThread(&Handle, CsrApiPort, a2, 0, v8, v13);
  if ( (int)result >= 0 )
  {
    Thread = CsrCreateThread(v6, Handle, (__int128 *)v3, 0);
    if ( Thread >= 0 )
    {
      v9 = &CsrThreadHashTable[2 * ((*(_DWORD *)(v3 + 8) >> 2) & 0x3FF)];
      for ( i = (__int64 *)*v9; i != v9; i = (__int64 *)*i )
      {
        v11 = i - 3;
        if ( i[3] == *(_QWORD *)(v3 + 8) && v11[5] == *(_QWORD *)v3 )
          goto LABEL_17;
      }
      v11 = 0;
LABEL_17:
      result = 0;
      *a1 = v11;
    }
    else
    {
      NtClose(Handle);
      return (unsigned int)Thread;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002880  mov     [rsp+arg_10], rbx
0x180002885  push    rbp
0x180002886  push    rsi
0x180002887  push    r14
0x180002889  sub     rsp, 60h
0x18000288d  mov     r10, cs:CsrRootProcess
0x180002894  lea     rsi, [rdx+8]
0x180002898  xor     ebp, ebp
0x18000289a  mov     r14, rcx
0x18000289d  mov     [rcx], rbp
0x1800028a0  mov     r9, [rsi]
0x1800028a3  lea     r8, [r10+10h]
0x1800028a7  mov     rax, r8
0x1800028aa  nop     word ptr [rax+rax+00h]
0x1800028b0  cmp     [rax-10h], r9
0x1800028b4  lea     rbx, [rax-10h]
0x1800028b8  jz      short loc_1800028D6
0x1800028ba  mov     rax, [rax]
0x1800028bd  cmp     rax, r8
0x1800028c0  jnz     short loc_1800028B0
0x1800028c2  xor     eax, eax
0x1800028c4  mov     rbx, [rsp+78h+arg_10]
0x1800028cc  add     rsp, 60h
0x1800028d0  pop     r14
0x1800028d2  pop     rsi
0x1800028d3  pop     rbp
0x1800028d4  retn
0x1800028d6  cmp     rbx, r10
0x1800028d9  jz      short loc_1800028C2
0x1800028db  test    dword ptr [rbx+5Ch], 2000h
0x1800028e2  mov     eax, 1FFFFFh
0x1800028e7  mov     ecx, 101C00h
0x1800028ec  mov     [rsp+78h+arg_8], rdi
0x1800028f4  cmovnz  eax, ecx
0x1800028f7  mov     [rsp+78h+var_48], 30h ; '0'
0x180002900  lea     rcx, [rsp+78h+var_48]
0x180002905  mov     [rsp+78h+var_30], rbp
0x18000290a  mov     [rsp+78h+var_50], rcx
0x18000290f  xorps   xmm0, xmm0
0x180002912  mov     r8, rdx
0x180002915  mov     [rsp+78h+Handle], rbp
0x18000291d  mov     rdx, cs:CsrApiPort
0x180002924  lea     rcx, [rsp+78h+Handle]
0x18000292c  xor     r9d, r9d
0x18000292f  mov     [rsp+78h+var_40], rbp
0x180002934  mov     [rsp+78h+var_38], rbp
0x180002939  movdqu  [rsp+78h+var_28], xmm0
0x18000293f  mov     [rsp+78h+var_58], eax
0x180002943  call    cs:__imp_NtAlpcOpenSenderThread
0x18000294a  nop     dword ptr [rax+rax+00h]
0x18000294f  mov     edi, eax
0x180002951  test    eax, eax
0x180002953  jns     short loc_1800029BA
0x180002955  mov     rdi, [rsp+78h+arg_8]
0x18000295d  jmp     loc_1800028C4
0x180002962  mov     r8d, [rsi+8]
0x180002966  lea     rcx, CsrThreadHashTable
0x18000296d  shr     r8, 2
0x180002971  and     r8d, 3FFh
0x180002978  shl     r8, 4
0x18000297c  add     r8, rcx
0x18000297f  mov     rcx, [r8]
0x180002982  cmp     rcx, r8
0x180002985  jz      short loc_1800029A5
0x180002987  mov     rax, [rsi+8]
0x18000298b  lea     rdx, [rcx-18h]
0x18000298f  cmp     [rdx+30h], rax
0x180002993  jz      short loc_18000299A
0x180002995  mov     rcx, [rcx]
0x180002998  jmp     short loc_180002982
0x18000299a  mov     rax, [rsi]
0x18000299d  cmp     [rdx+28h], rax
0x1800029a1  jnz     short loc_180002995
0x1800029a3  jmp     short loc_1800029A8
0x1800029a5  mov     rdx, rbp
0x1800029a8  mov     rdi, [rsp+78h+arg_8]
0x1800029b0  xor     eax, eax
0x1800029b2  mov     [r14], rdx
0x1800029b5  jmp     loc_1800028C4
0x1800029ba  mov     rdx, [rsp+78h+Handle]
0x1800029c2  xor     r9d, r9d
0x1800029c5  mov     r8, rsi
0x1800029c8  mov     rcx, rbx
0x1800029cb  call    CsrCreateThread
0x1800029d0  mov     edi, eax
0x1800029d2  test    eax, eax
0x1800029d4  jns     short loc_180002962
0x1800029d6  mov     rcx, [rsp+78h+Handle]; Handle
0x1800029de  call    cs:__imp_NtClose
0x1800029e5  nop     dword ptr [rax+rax+00h]
0x1800029ea  mov     eax, edi
0x1800029ec  mov     rdi, [rsp+78h+arg_8]
0x1800029f4  jmp     loc_1800028C4
```
