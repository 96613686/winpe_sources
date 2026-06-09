# MRxSmb2QuerySecurityInformation

- ea: `0x140019260`
- end: `0x14001949b`
- name: `MRxSmb2QuerySecurityInformation`
- size: `571`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400040a0`
- `0x140019260`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400193cc`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140019420`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400193cc`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140019420`
- `mrxsmb!SmbCeInitiateExchange` at `0x1400193aa`
- `mrxsmb!SmbCeInitiateExchange` at `0x1400193aa`
- `mrxsmb!SmbCeInitializeExchange` at `0x140019336`
- `mrxsmb!SmbCeInitializeExchange` at `0x140019336`

## pseudocode

```c
__int64 __fastcall MRxSmb2QuerySecurityInformation(__int64 a1)
{
  __int64 v1; // rdx
  int v3; // edi
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v6; // rcx
  bool v7; // cl
  __int64 v8; // rax
  unsigned int v9; // edi
  __int64 result; // rax
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_DWORD *)(a1 + 472);
  v4 = *(_QWORD *)(a1 + 72);
  LODWORD(v11) = v3;
  v5 = *(_QWORD *)(v1 + 120);
  v6 = *(_QWORD *)(v5 + 32);
  v7 = (*(_DWORD *)(v6 + 96) & 0x80u) == 0
    && (*(_BYTE *)(*(_QWORD *)(v6 + 32) + 764LL) & 2) != 0
    && (*(_DWORD *)(v1 + 156) & 0x4000000) == 0
    && (*(_DWORD *)(*(_QWORD *)(v1 + 136) + 8LL) & 1) == 0
    && !*(_BYTE *)(v5 + 77)
    && (*(_DWORD *)(a1 + 120) & 0x10000000) == 0;
  if ( *(_WORD *)v1 == 0xEC22
    && (*(_DWORD *)(v4 + 120) & 0x27) != 0
    && ((*(_BYTE *)(v1 + 256) & 1) != 0 || (*(_DWORD *)(v1 + 164) & 1) == 0)
    || !v7
    || (result = Smb2FetchFileInfoFromCache(
                   a1,
                   *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 40LL) + 424LL) + 376LL,
                   3,
                   *(unsigned int *)(a1 + 448),
                   *(_DWORD *)(a1 + 512),
                   *(_QWORD *)(a1 + 456),
                   &v11),
        (_DWORD)result == -1073741802) )
  {
    v8 = *(_QWORD *)(a1 + 72);
    v11 = 0;
    v9 = SmbCeInitializeExchange(&v11, a1, 0, 0, 0, *(_QWORD *)(*(_QWORD *)(v8 + 40) + 40LL), 2600, &QueryInfoDispatch);
    if ( !v9 )
    {
      *(_DWORD *)(v11 + 2424) = 0;
      *(_DWORD *)(v11 + 2420) = 3;
      *(_QWORD *)(v11 + 2408) = *(_QWORD *)(a1 + 456);
      *(_DWORD *)(v11 + 2416) = *(_DWORD *)(a1 + 472);
      *(_DWORD *)(v11 + 2432) = *(_DWORD *)(a1 + 512);
      _InterlockedOr((volatile signed __int32 *)(v11 + 68), 1u);
      v9 = SmbCeInitiateExchange(v11);
      if ( v9 == 259 )
        return (unsigned int)SmbCeWaitForCompletionAndFinalizeExchangeEx(v11, 0, 0, 0);
      else
        SmbCeWaitForCompletionAndFinalizeExchangeEx(v11, 0, 0, 0);
    }
    return v9;
  }
  else if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -1073741789 )
    {
      *(_QWORD *)(a1 + 184) = (unsigned int)v11;
      return 2147483653LL;
    }
  }
  else
  {
    *(_DWORD *)(a1 + 472) = v3 - v11;
  }
  return result;
}

```

## disassembly

```asm
0x140019260  mov     [rsp+arg_10], rbx
0x140019265  push    rdi
0x140019266  sub     rsp, 40h
0x14001926a  mov     rdx, [rcx+38h]
0x14001926e  mov     rbx, rcx
0x140019271  mov     edi, [rcx+1D8h]
0x140019277  mov     r9, [rcx+48h]
0x14001927b  mov     dword ptr [rsp+48h+arg_0], edi
0x14001927f  mov     r8, [rdx+78h]
0x140019283  mov     rcx, [r8+20h]
0x140019287  mov     eax, [rcx+60h]
0x14001928a  test    al, al
0x14001928c  js      loc_1400193ED
0x140019292  mov     rax, [rcx+20h]
0x140019296  test    byte ptr [rax+2FCh], 2
0x14001929d  jz      loc_1400193ED
0x1400192a3  test    dword ptr [rdx+9Ch], 4000000h
0x1400192ad  jnz     loc_1400193ED
0x1400192b3  mov     rax, [rdx+88h]
0x1400192ba  mov     ecx, [rax+8]
0x1400192bd  test    cl, 1
0x1400192c0  jnz     loc_1400193ED
0x1400192c6  cmp     byte ptr [r8+4Dh], 0
0x1400192cb  jnz     loc_1400193ED
0x1400192d1  mov     ecx, [rbx+78h]
0x1400192d4  shr     ecx, 1Ch
0x1400192d7  not     cl
0x1400192d9  and     cl, 1
0x1400192dc  mov     eax, 0EC22h
0x1400192e1  cmp     [rdx], ax
0x1400192e4  jz      loc_1400193F4
0x1400192ea  test    cl, cl
0x1400192ec  jnz     loc_14001942E
0x1400192f2  mov     rax, [rbx+48h]
0x1400192f6  lea     rcx, QueryInfoDispatch
0x1400192fd  mov     [rsp+48h+var_10], rcx
0x140019302  xor     r9d, r9d
0x140019305  mov     dword ptr [rsp+48h+var_18], 0A28h
0x14001930d  lea     rcx, [rsp+48h+arg_0]
0x140019312  mov     [rsp+48h+arg_8], rsi
0x140019317  xor     r8d, r8d
0x14001931a  xor     esi, esi
0x14001931c  mov     rdx, rbx
0x14001931f  mov     [rsp+48h+arg_0], rsi
0x140019324  mov     rax, [rax+28h]
0x140019328  mov     rax, [rax+28h]
0x14001932c  mov     [rsp+48h+var_20], rax
0x140019331  mov     [rsp+48h+var_28], rsi
0x140019336  call    cs:__imp_SmbCeInitializeExchange
0x14001933d  nop     dword ptr [rax+rax+00h]
0x140019342  mov     edi, eax
0x140019344  test    eax, eax
0x140019346  jnz     loc_1400193DA
0x14001934c  mov     rax, [rsp+48h+arg_0]
0x140019351  mov     [rax+978h], esi
0x140019357  mov     rax, [rsp+48h+arg_0]
0x14001935c  mov     dword ptr [rax+974h], 3
0x140019366  mov     rax, [rsp+48h+arg_0]
0x14001936b  mov     rcx, [rbx+1C8h]
0x140019372  mov     [rax+968h], rcx
0x140019379  mov     rax, [rsp+48h+arg_0]
0x14001937e  mov     ecx, [rbx+1D8h]
0x140019384  mov     [rax+970h], ecx
0x14001938a  mov     rax, [rsp+48h+arg_0]
0x14001938f  mov     ecx, [rbx+200h]
0x140019395  mov     [rax+980h], ecx
0x14001939b  mov     rax, [rsp+48h+arg_0]
0x1400193a0  lock or dword ptr [rax+44h], 1
0x1400193a5  mov     rcx, [rsp+48h+arg_0]
0x1400193aa  call    cs:__imp_SmbCeInitiateExchange
0x1400193b1  nop     dword ptr [rax+rax+00h]
0x1400193b6  mov     rcx, [rsp+48h+arg_0]
0x1400193bb  xor     r9d, r9d
0x1400193be  xor     r8d, r8d
0x1400193c1  xor     edx, edx
0x1400193c3  mov     edi, eax
0x1400193c5  cmp     eax, 103h
0x1400193ca  jnz     short loc_140019420
0x1400193cc  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x1400193d3  nop     dword ptr [rax+rax+00h]
0x1400193d8  mov     edi, eax
0x1400193da  mov     rsi, [rsp+48h+arg_8]
0x1400193df  mov     eax, edi
0x1400193e1  mov     rbx, [rsp+48h+arg_10]
0x1400193e6  add     rsp, 40h
0x1400193ea  pop     rdi
0x1400193eb  retn
0x1400193ed  xor     cl, cl
0x1400193ef  jmp     loc_1400192DC
0x1400193f4  mov     eax, [r9+78h]
0x1400193f8  test    al, 27h
0x1400193fa  jz      loc_1400192EA
0x140019400  test    byte ptr [rdx+100h], 1
0x140019407  jnz     loc_1400192F2
0x14001940d  mov     eax, [rdx+0A4h]
0x140019413  test    al, 1
0x140019415  jz      loc_1400192F2
0x14001941b  jmp     loc_1400192EA
0x140019420  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140019427  nop     dword ptr [rax+rax+00h]
0x14001942c  jmp     short loc_1400193DA
0x14001942e  mov     rax, [r9+28h]
0x140019432  mov     r8d, 3
0x140019438  mov     r9d, [rbx+1C0h]
0x14001943f  mov     rcx, [rax+28h]
0x140019443  lea     rax, [rsp+48h+arg_0]
0x140019448  mov     [rsp+48h+var_18], rax
0x14001944d  mov     rax, [rbx+1C8h]
0x140019454  mov     [rsp+48h+var_20], rax
0x140019459  mov     rdx, [rcx+1A8h]
0x140019460  mov     rcx, rbx
0x140019463  mov     eax, [rbx+200h]
0x140019469  add     rdx, 178h
0x140019470  mov     dword ptr [rsp+48h+var_28], eax
0x140019474  call    Smb2FetchFileInfoFromCache
0x140019479  cmp     eax, 0C0000016h
0x14001947e  jz      loc_1400192F2
0x140019484  test    eax, eax
0x140019486  js      loc_14003B884
0x14001948c  sub     edi, dword ptr [rsp+48h+arg_0]
0x140019490  mov     [rbx+1D8h], edi
0x140019496  jmp     loc_1400193E1
0x14003b884  cmp     eax, 0C0000023h
0x14003b889  jnz     loc_1400193E1
0x14003b88f  mov     eax, dword ptr [rsp+48h+arg_0]
0x14003b893  mov     [rbx+0B8h], rax
0x14003b89a  mov     eax, 80000005h
0x14003b89f  jmp     loc_1400193E1
```
