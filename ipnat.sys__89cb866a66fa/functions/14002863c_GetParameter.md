# GetParameter

- ea: `0x14002863c`
- end: `0x1400287d0`
- name: `GetParameter`
- size: `404`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002816c`
- `0x140028280`
- `0x140028460`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14002863c`
- `0x14002c710`
- `0x14002cbc0`

## import_xrefs

- `NETIO!NmrClientDetachProviderComplete` at `0x140028729`
- `NETIO!NmrClientDetachProviderComplete` at `0x140028729`

## pseudocode

```c
__int64 __fastcall GetParameter(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        unsigned int a8)
{
  int v12; // eax
  unsigned int v13; // ebx
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  _QWORD v17[16]; // [rsp+30h] [rbp-49h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids);
  }
  memset(v17, 0, 0x50u);
  while ( 1 )
  {
    v12 = gNatNsiReferenceObject;
    if ( (gNatNsiReferenceObject & 1) != 0 )
      break;
    if ( v12 == _InterlockedCompareExchange(&gNatNsiReferenceObject, gNatNsiReferenceObject + 2, gNatNsiReferenceObject) )
    {
      LODWORD(v17[7]) = a5;
      v17[8] = a6;
      v17[9] = __PAIR64__(a8, a7);
      LODWORD(v17[1]) = 0;
      v17[2] = a1;
      LODWORD(v17[3]) = a2;
      v17[5] = a3;
      LODWORD(v17[6]) = a4;
      v17[4] = 1;
      v13 = (*(__int64 (__fastcall **)(_QWORD *))(*(_QWORD *)(gNatNsiProviderContext + 8) + 16LL))(v17);
      if ( _InterlockedExchangeAdd(&gNatNsiReferenceObject, 0xFFFFFFFE) == 3 )
        NmrClientDetachProviderComplete(*(HANDLE *)(gNatNsiProviderContext + 16));
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v15 = 33;
LABEL_22:
        WPP_SF_d(v14->AttachedDevice, v15, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids, v13);
        return v13;
      }
      return v13;
    }
  }
  v13 = -1073741823;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids, 3221225473LL);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v15 = 32;
      goto LABEL_22;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x14002863c  push    rbp
0x14002863e  push    rbx
0x14002863f  push    rsi
0x140028640  push    rdi
0x140028641  push    r12
0x140028643  push    r14
0x140028645  lea     rbp, [rsp-0Fh]
0x14002864a  sub     rsp, 88h
0x140028651  mov     ebx, r9d
0x140028654  mov     rdi, r8
0x140028657  mov     esi, edx
0x140028659  mov     r14, rcx
0x14002865c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028663  lea     r12, WPP_GLOBAL_Control
0x14002866a  cmp     rcx, r12
0x14002866d  jz      short loc_140028691
0x14002866f  mov     eax, [rcx+2Ch]
0x140028672  test    al, 2
0x140028674  jz      short loc_140028691
0x140028676  cmp     byte ptr [rcx+29h], 6
0x14002867a  jb      short loc_140028691
0x14002867c  mov     rcx, [rcx+18h]
0x140028680  lea     r8, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x140028687  mov     edx, 1Eh
0x14002868c  call    WPP_SF_
0x140028691  xor     edx, edx; Val
0x140028693  lea     rcx, [rbp+37h+var_80]; void *
0x140028697  lea     r8d, [rdx+50h]; Size
0x14002869b  call    memset
0x1400286a0  mov     eax, cs:gNatNsiReferenceObject
0x1400286a6  test    al, 1
0x1400286a8  jnz     loc_140028755
0x1400286ae  lea     ecx, [rax+2]
0x1400286b1  lock cmpxchg cs:gNatNsiReferenceObject, ecx
0x1400286b9  jnz     short loc_1400286A0
0x1400286bb  mov     eax, [rbp+37h+arg_20]
0x1400286be  mov     [rbp+37h+var_48], eax
0x1400286c1  mov     rax, [rbp+37h+arg_28]
0x1400286c5  mov     [rbp+37h+var_40], rax
0x1400286c9  mov     eax, [rbp+37h+arg_30]
0x1400286cc  mov     [rbp+37h+var_38], eax
0x1400286cf  mov     eax, [rbp+37h+arg_38]
0x1400286d2  mov     [rbp+37h+var_34], eax
0x1400286d5  mov     rax, cs:gNatNsiProviderContext
0x1400286dc  mov     [rbp+37h+var_78], 0
0x1400286e3  mov     [rbp+37h+var_70], r14
0x1400286e7  mov     [rbp+37h+var_68], esi
0x1400286ea  mov     [rbp+37h+var_58], rdi
0x1400286ee  mov     [rbp+37h+var_50], ebx
0x1400286f1  mov     [rbp+37h+var_60], 1
0x1400286f9  mov     rcx, [rax+8]
0x1400286fd  mov     rax, [rcx+10h]
0x140028701  lea     rcx, [rbp+37h+var_80]
0x140028705  call    _guard_dispatch_icall
0x14002870a  mov     ebx, eax
0x14002870c  mov     ecx, 0FFFFFFFEh
0x140028711  lock xadd cs:gNatNsiReferenceObject, ecx
0x140028719  cmp     ecx, 3
0x14002871c  jnz     short loc_140028735
0x14002871e  mov     rcx, cs:gNatNsiProviderContext
0x140028725  mov     rcx, [rcx+10h]; NmrBindingHandle
0x140028729  call    cs:__imp_NmrClientDetachProviderComplete
0x140028730  nop     dword ptr [rax+rax+00h]
0x140028735  mov     rcx, cs:WPP_GLOBAL_Control
0x14002873c  cmp     rcx, r12
0x14002873f  jz      short loc_1400287BD
0x140028741  mov     eax, [rcx+2Ch]
0x140028744  test    al, 2
0x140028746  jz      short loc_1400287BD
0x140028748  cmp     byte ptr [rcx+29h], 6
0x14002874c  jb      short loc_1400287BD
0x14002874e  mov     edx, 21h ; '!'
0x140028753  jmp     short loc_1400287AA
0x140028755  mov     rcx, cs:WPP_GLOBAL_Control
0x14002875c  mov     ebx, 0C0000001h
0x140028761  cmp     rcx, r12
0x140028764  jz      short loc_1400287BD
0x140028766  mov     eax, [rcx+2Ch]
0x140028769  test    al, 2
0x14002876b  jz      short loc_14002878B
0x14002876d  cmp     byte ptr [rcx+29h], 2
0x140028771  jb      short loc_14002878B
0x140028773  mov     rcx, [rcx+18h]
0x140028777  lea     r8, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x14002877e  mov     edx, 1Fh
0x140028783  mov     r9d, ebx
0x140028786  call    WPP_SF_d
0x14002878b  mov     rcx, cs:WPP_GLOBAL_Control
0x140028792  cmp     rcx, r12
0x140028795  jz      short loc_1400287BD
0x140028797  mov     edx, [rcx+2Ch]
0x14002879a  test    dl, 2
0x14002879d  jz      short loc_1400287BD
0x14002879f  cmp     byte ptr [rcx+29h], 6
0x1400287a3  jb      short loc_1400287BD
0x1400287a5  mov     edx, 20h ; ' '
0x1400287aa  mov     rcx, [rcx+18h]
0x1400287ae  lea     r8, WPP_a039967293013d6e0a781349d74ce0cf_Traceguids
0x1400287b5  mov     r9d, ebx
0x1400287b8  call    WPP_SF_d
0x1400287bd  mov     eax, ebx
0x1400287bf  add     rsp, 88h
0x1400287c6  pop     r14
0x1400287c8  pop     r12
0x1400287ca  pop     rdi
0x1400287cb  pop     rsi
0x1400287cc  pop     rbx
0x1400287cd  pop     rbp
0x1400287ce  retn
```
