# PortMgrDeInitPort

- ea: `0x180023640`
- end: `0x180023768`
- name: `PortMgrDeInitPort`
- size: `296`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180003c80`
- `0x180004780`
- `0x180005640`
- `0x18000b330`
- `0x18000e230`
- `0x18000f1d0`
- `0x18000f8c0`
- `0x180013a30`
- `0x180015120`
- `0x1800170c0`
- `0x18001fb58`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x180018c60`
- `0x18001be88`
- `0x1800214f0`
- `0x180022384`
- `0x180023640`
- `0x180028cb8`

## pseudocode

```c
__int64 __fastcall PortMgrDeInitPort(__int64 a1)
{
  __int64 v1; // rdi
  _UNKNOWN **v3; // rcx
  __int64 result; // rax
  _UNKNOWN **v5; // rcx

  v1 = *(unsigned int *)(a1 + 20);
  v3 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x17u, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
      v3 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
      WPP_SF_d((__int64)v3[7], 0x19u, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v1);
  }
  if ( (unsigned int)MSMPortDestroyCompletion(a1)
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 0x1Au, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v1);
  }
  if ( *(_DWORD *)(a1 + 2376) == 1 )
    DeInitSupplicantContext(a1 + 2384);
  PortMgrDeInitPortHelper(a1, 1, 1, 1);
  result = NetTraceMarkContextActivityStop(v1, (unsigned int)v1);
  v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      result = WPP_SF_d(
                 *((_QWORD *)WPP_GLOBAL_Control + 7),
                 0x1Bu,
                 (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids,
                 v1);
      v5 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_DWORD *)v5 + 17) & 0x800) != 0 )
      return WPP_SF_D((__int64)v5[7], 0x1Cu, (__int64)WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180023640  push    rbx
0x180023642  push    rbp
0x180023643  push    rsi
0x180023644  push    rdi
0x180023645  push    r14
0x180023647  sub     rsp, 30h
0x18002364b  mov     edi, [rcx+14h]
0x18002364e  mov     rbx, rcx
0x180023651  mov     rcx, cs:WPP_GLOBAL_Control
0x180023658  lea     rsi, WPP_GLOBAL_Control
0x18002365f  lea     r14, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180023666  mov     ebp, 800h
0x18002366b  cmp     rcx, rsi
0x18002366e  jz      short loc_1800236AB
0x180023670  test    [rcx+44h], ebp
0x180023673  jz      short loc_18002368D
0x180023675  mov     rcx, [rcx+38h]
0x180023679  mov     edx, 17h
0x18002367e  mov     r8, r14
0x180023681  call    WPP_SF_
0x180023686  mov     rcx, cs:WPP_GLOBAL_Control
0x18002368d  cmp     rcx, rsi
0x180023690  jz      short loc_1800236AB
0x180023692  test    [rcx+44h], ebp
0x180023695  jz      short loc_1800236AB
0x180023697  mov     rcx, [rcx+38h]
0x18002369b  mov     edx, 19h
0x1800236a0  mov     r9d, edi
0x1800236a3  mov     r8, r14
0x1800236a6  call    WPP_SF_d
0x1800236ab  mov     rcx, rbx
0x1800236ae  call    MSMPortDestroyCompletion
0x1800236b3  test    eax, eax
0x1800236b5  jz      short loc_1800236E1
0x1800236b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236be  cmp     rcx, rsi
0x1800236c1  jz      short loc_1800236E1
0x1800236c3  test    byte ptr [rcx+44h], 1
0x1800236c7  jz      short loc_1800236E1
0x1800236c9  mov     rcx, [rcx+38h]
0x1800236cd  mov     edx, 1Ah
0x1800236d2  mov     r9d, edi
0x1800236d5  mov     [rsp+58h+var_38], eax
0x1800236d9  mov     r8, r14
0x1800236dc  call    WPP_SF_dd
0x1800236e1  cmp     dword ptr [rbx+948h], 1
0x1800236e8  jnz     short loc_1800236F6
0x1800236ea  lea     rcx, [rbx+950h]
0x1800236f1  call    DeInitSupplicantContext
0x1800236f6  mov     edx, 1
0x1800236fb  mov     rcx, rbx
0x1800236fe  mov     r9d, edx
0x180023701  mov     r8d, edx
0x180023704  call    PortMgrDeInitPortHelper
0x180023709  mov     rcx, rdi
0x18002370c  mov     edx, edi
0x18002370e  call    NetTraceMarkContextActivityStop
0x180023713  mov     rcx, cs:WPP_GLOBAL_Control
0x18002371a  cmp     rcx, rsi
0x18002371d  jz      short loc_18002375D
0x18002371f  test    [rcx+44h], ebp
0x180023722  jz      short loc_18002373F
0x180023724  mov     rcx, [rcx+38h]
0x180023728  mov     edx, 1Bh
0x18002372d  mov     r9d, edi
0x180023730  mov     r8, r14
0x180023733  call    WPP_SF_d
0x180023738  mov     rcx, cs:WPP_GLOBAL_Control
0x18002373f  cmp     rcx, rsi
0x180023742  jz      short loc_18002375D
0x180023744  test    [rcx+44h], ebp
0x180023747  jz      short loc_18002375D
0x180023749  mov     rcx, [rcx+38h]
0x18002374d  mov     edx, 1Ch
0x180023752  xor     r9d, r9d
0x180023755  mov     r8, r14
0x180023758  call    WPP_SF_D
0x18002375d  add     rsp, 30h
0x180023761  pop     r14
0x180023763  pop     rdi
0x180023764  pop     rsi
0x180023765  pop     rbp
0x180023766  pop     rbx
0x180023767  retn
```
