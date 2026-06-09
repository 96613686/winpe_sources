# PppoeCmOpenAf

- ea: `0x140006420`
- end: `0x140006596`
- name: `PppoeCmOpenAf`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000110c`
- `0x1400023c0`
- `0x140006420`

## pseudocode

```c
__int64 __fastcall PppoeCmOpenAf(__int64 a1, _DWORD *a2, signed __int64 a3, _QWORD *a4)
{
  _DWORD *v6; // rdi
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx

  v6 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
  }
  if ( !a1 || *(_DWORD *)a1 != 1631940432 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      return 3221225473LL;
    }
    v9 = 11;
    goto LABEL_29;
  }
  if ( *v6 == 2049 && v6[1] == 6 && v6[2] == 30 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 128), a3, 0) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        return 3221225473LL;
      }
      v9 = 13;
LABEL_29:
      WPP_SF_(v8->AttachedDevice, v9, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
      return 3221225473LL;
    }
    LOBYTE(a2) = 1;
    ReferenceAdapter(a1, a2);
    *a4 = a1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
    }
    return 3221291012LL;
  }
}

```

## disassembly

```asm
0x140006420  mov     [rsp+arg_8], rbx
0x140006425  mov     [rsp+arg_10], rbp
0x14000642a  push    rsi
0x14000642b  push    rdi
0x14000642c  push    r12
0x14000642e  push    r14
0x140006430  push    r15
0x140006432  sub     rsp, 20h
0x140006436  mov     r14, r9
0x140006439  mov     rsi, r8
0x14000643c  mov     rdi, rdx
0x14000643f  mov     rbx, rcx
0x140006442  mov     rcx, cs:WPP_GLOBAL_Control
0x140006449  lea     r12, WPP_GLOBAL_Control
0x140006450  lea     r15, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140006457  cmp     rcx, r12
0x14000645a  jz      short loc_14000647A
0x14000645c  bt      dword ptr [rcx+2Ch], 0Fh
0x140006461  jnb     short loc_14000647A
0x140006463  cmp     byte ptr [rcx+29h], 2
0x140006467  jb      short loc_14000647A
0x140006469  mov     rcx, [rcx+18h]
0x14000646d  mov     edx, 0Ah
0x140006472  mov     r8, r15
0x140006475  call    WPP_SF_
0x14000647a  test    rbx, rbx
0x14000647d  jz      loc_14000654F
0x140006483  cmp     dword ptr [rbx], 61456F50h
0x140006489  jnz     loc_14000654F
0x14000648f  cmp     dword ptr [rdi], 801h
0x140006495  jnz     loc_14000651E
0x14000649b  cmp     dword ptr [rdi+4], 6
0x14000649f  jnz     short loc_14000651E
0x1400064a1  cmp     dword ptr [rdi+8], 1Eh
0x1400064a5  jnz     short loc_14000651E
0x1400064a7  xor     eax, eax
0x1400064a9  lock cmpxchg [rbx+80h], rsi
0x1400064b2  jz      short loc_1400064E3
0x1400064b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064bb  cmp     rcx, r12
0x1400064be  jz      loc_140006579
0x1400064c4  bt      dword ptr [rcx+2Ch], 0Fh
0x1400064c9  jnb     loc_140006579
0x1400064cf  cmp     byte ptr [rcx+29h], 1
0x1400064d3  jb      loc_140006579
0x1400064d9  mov     edx, 0Dh
0x1400064de  jmp     loc_14000656D
0x1400064e3  mov     dl, 1
0x1400064e5  mov     rcx, rbx
0x1400064e8  call    ReferenceAdapter
0x1400064ed  mov     [r14], rbx
0x1400064f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400064f7  cmp     rcx, r12
0x1400064fa  jz      short loc_14000651A
0x1400064fc  bt      dword ptr [rcx+2Ch], 0Fh
0x140006501  jnb     short loc_14000651A
0x140006503  cmp     byte ptr [rcx+29h], 2
0x140006507  jb      short loc_14000651A
0x140006509  mov     rcx, [rcx+18h]
0x14000650d  mov     edx, 0Eh
0x140006512  mov     r8, r15
0x140006515  call    WPP_SF_
0x14000651a  xor     eax, eax
0x14000651c  jmp     short loc_14000657E
0x14000651e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006525  cmp     rcx, r12
0x140006528  jz      short loc_140006548
0x14000652a  bt      dword ptr [rcx+2Ch], 0Fh
0x14000652f  jnb     short loc_140006548
0x140006531  cmp     byte ptr [rcx+29h], 1
0x140006535  jb      short loc_140006548
0x140006537  mov     rcx, [rcx+18h]
0x14000653b  mov     edx, 0Ch
0x140006540  mov     r8, r15
0x140006543  call    WPP_SF_
0x140006548  mov     eax, 0C0010004h
0x14000654d  jmp     short loc_14000657E
0x14000654f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006556  cmp     rcx, r12
0x140006559  jz      short loc_140006579
0x14000655b  bt      dword ptr [rcx+2Ch], 0Fh
0x140006560  jnb     short loc_140006579
0x140006562  cmp     byte ptr [rcx+29h], 1
0x140006566  jb      short loc_140006579
0x140006568  mov     edx, 0Bh
0x14000656d  mov     rcx, [rcx+18h]
0x140006571  mov     r8, r15
0x140006574  call    WPP_SF_
0x140006579  mov     eax, 0C0000001h
0x14000657e  mov     rbx, [rsp+48h+arg_8]
0x140006583  mov     rbp, [rsp+48h+arg_10]
0x140006588  add     rsp, 20h
0x14000658c  pop     r15
0x14000658e  pop     r14
0x140006590  pop     r12
0x140006592  pop     rdi
0x140006593  pop     rsi
0x140006594  retn
```
