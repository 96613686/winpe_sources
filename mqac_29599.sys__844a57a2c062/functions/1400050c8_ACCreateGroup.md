# ACCreateGroup

- ea: `0x1400050c8`
- end: `0x1400051d1`
- name: `ACCreateGroup`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001128`
- `0x140001c34`
- `0x140003d84`
- `0x1400050c8`

## pseudocode

```c
__int64 __fastcall ACCreateGroup(__int64 a1, __int64 a2, unsigned int a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  __int64 v9; // rax

  v6 = operator new(0x58u, 0x40u, 0x4741514Du, LowPoolPriority);
  v7 = v6;
  if ( v6 )
  {
    v6[2] = 1;
    *((_QWORD *)v6 + 3) = v6 + 4;
    *((_QWORD *)v6 + 2) = v6 + 4;
    *((_QWORD *)v6 + 4) = 0;
    *((_QWORD *)v6 + 6) = v6 + 10;
    *((_QWORD *)v6 + 5) = v6 + 10;
    v6[14] = 0;
    *((_QWORD *)v6 + 8) = a1;
    *(_QWORD *)v6 = &CGroup::`vftable';
    *((_QWORD *)v6 + 10) = v6 + 18;
    *((_QWORD *)v6 + 9) = v6 + 18;
    v6[14] ^= ((unsigned __int8)v6[14] ^ (unsigned __int8)(2 * a3)) & 2;
  }
  else
  {
    v7 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 198, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v7);
  }
  if ( v7 )
  {
    v9 = *(_QWORD *)(a2 + 32);
    *(_QWORD *)(a2 + 24) = v7;
    *(_DWORD *)(v9 + 20) |= 1u;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 199, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a3);
    }
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400050c8  push    rbx
0x1400050ca  push    rbp
0x1400050cb  push    rsi
0x1400050cc  push    rdi
0x1400050cd  sub     rsp, 28h
0x1400050d1  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x1400050d4  mov     rdi, rdx
0x1400050d7  mov     esi, r8d
0x1400050da  mov     rbp, rcx
0x1400050dd  mov     r8d, 4741514Dh; unsigned int
0x1400050e3  lea     edx, [r9+40h]; unsigned __int64
0x1400050e7  lea     ecx, [rdx+18h]; unsigned __int64
0x1400050ea  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x1400050ef  mov     rbx, rax
0x1400050f2  test    rax, rax
0x1400050f5  jz      short loc_14000514E
0x1400050f7  mov     dword ptr [rax+8], 1
0x1400050fe  lea     rcx, [rax+28h]
0x140005102  lea     rdx, [rax+10h]
0x140005106  mov     [rdx+8], rdx
0x14000510a  mov     [rdx], rdx
0x14000510d  mov     qword ptr [rax+20h], 0
0x140005115  mov     [rcx+8], rcx
0x140005119  mov     [rcx], rcx
0x14000511c  lea     ecx, [rsi+rsi]
0x14000511f  mov     dword ptr [rax+38h], 0
0x140005126  mov     [rax+40h], rbp
0x14000512a  lea     rax, ??_7CGroup@@6B@; const CGroup::`vftable'
0x140005131  mov     [rbx], rax
0x140005134  lea     rax, [rbx+48h]
0x140005138  mov     [rax+8], rax
0x14000513c  mov     [rax], rax
0x14000513f  mov     eax, [rbx+38h]
0x140005142  xor     ecx, eax
0x140005144  and     ecx, 2
0x140005147  xor     ecx, eax
0x140005149  mov     [rbx+38h], ecx
0x14000514c  jmp     short loc_140005150
0x14000514e  xor     ebx, ebx
0x140005150  mov     rcx, cs:WPP_GLOBAL_Control
0x140005157  lea     rbp, WPP_GLOBAL_Control
0x14000515e  cmp     rcx, rbp
0x140005161  jz      short loc_140005182
0x140005163  mov     eax, [rcx+6Ch]
0x140005166  test    al, 4
0x140005168  jz      short loc_140005182
0x14000516a  mov     rcx, [rcx+58h]
0x14000516e  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005175  mov     edx, 0C6h
0x14000517a  mov     r9, rbx
0x14000517d  call    WPP_SF_q
0x140005182  test    rbx, rbx
0x140005185  jnz     short loc_1400051B9
0x140005187  mov     rcx, cs:WPP_GLOBAL_Control
0x14000518e  cmp     rcx, rbp
0x140005191  jz      short loc_1400051B2
0x140005193  mov     eax, [rcx+6Ch]
0x140005196  test    al, 1
0x140005198  jz      short loc_1400051B2
0x14000519a  mov     rcx, [rcx+58h]
0x14000519e  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400051a5  mov     edx, 0C7h
0x1400051aa  mov     r9d, esi
0x1400051ad  call    WPP_SF_d
0x1400051b2  mov     eax, 0C000009Ah
0x1400051b7  jmp     short loc_1400051C7
0x1400051b9  mov     rax, [rdi+20h]
0x1400051bd  mov     [rdi+18h], rbx
0x1400051c1  or      dword ptr [rax+14h], 1
0x1400051c5  xor     eax, eax
0x1400051c7  add     rsp, 28h
0x1400051cb  pop     rdi
0x1400051cc  pop     rsi
0x1400051cd  pop     rbp
0x1400051ce  pop     rbx
0x1400051cf  retn
```
