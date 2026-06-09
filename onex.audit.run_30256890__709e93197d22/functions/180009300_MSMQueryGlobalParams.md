# MSMQueryGlobalParams

- ea: `0x180009300`
- end: `0x180009532`
- name: `MSMQueryGlobalParams`
- size: `562`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007fb0`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180009300`
- `0x180010ae0`
- `0x1800214f0`
- `0x1800281dc`
- `0x18002eeec`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800093c8`
- `MobileNetworking!ReleaseWriteLock` at `0x1800093c8`
- `MobileNetworking!AcquireWriteLock` at `0x180009462`
- `MobileNetworking!AcquireWriteLock` at `0x1800094a8`
- `MobileNetworking!AcquireWriteLock` at `0x180009462`
- `MobileNetworking!AcquireWriteLock` at `0x1800094a8`

## pseudocode

```c
__int64 __fastcall MSMQueryGlobalParams(__int64 a1, unsigned int *a2, _QWORD *a3)
{
  unsigned int v3; // r15d
  __int64 v4; // rbp
  __int64 v6; // r14
  char *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // ebp
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned int v15; // [rsp+70h] [rbp+8h] BYREF
  __int64 v16; // [rsp+78h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a1 + 20);
  v4 = *(_QWORD *)(a1 + 192);
  v6 = *(_QWORD *)(a1 + 2368);
  v16 = 0;
  v15 = 0;
  v9 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 95, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v9 = (char *)WPP_GLOBAL_Control;
    }
    if ( v9 != (char *)&WPP_GLOBAL_Control && v9[68] < 0 )
    {
      WPP_SF_d(*((_QWORD *)v9 + 7), 96, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
      v9 = (char *)WPP_GLOBAL_Control;
    }
  }
  *a3 = 0;
  *a2 = 0;
  if ( *(_QWORD *)(a1 + 2360) )
  {
    ReleaseWriteLock(a1, a1 + 2896, "MSMQueryGlobalParams", 854);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, __int64 *))(a1 + 2360))(v4, v6, &v15, &v16);
    v11 = v10;
    if ( v10 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v13 = 97;
LABEL_16:
        WPP_SF_dd(v12[7], v13, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3, v10);
      }
    }
    else
    {
      v10 = ValidateOneXParams(v15, v16);
      v11 = v10;
      if ( !v10 )
      {
        *a3 = v16;
        *a2 = v15;
        AcquireWriteLock(a1, a1 + 2896, "MSMQueryGlobalParams", 886);
        goto LABEL_20;
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v13 = 98;
        goto LABEL_16;
      }
    }
    AcquireWriteLock(a1, a1 + 2896, "MSMQueryGlobalParams", 886);
    if ( v16 )
    {
      MSMFreeMemory(a1);
      v9 = (char *)WPP_GLOBAL_Control;
      goto LABEL_25;
    }
LABEL_20:
    v9 = (char *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v11 = 0;
  if ( v9 != (char *)&WPP_GLOBAL_Control && v9[68] < 0 )
  {
    WPP_SF_d(*((_QWORD *)v9 + 7), 99, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v3);
    v9 = (char *)WPP_GLOBAL_Control;
  }
  *a3 = v16;
  *a2 = v15;
LABEL_25:
  if ( v9 != (char *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)v9 + 7), 100, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180009300  mov     [rsp+arg_10], rbx
0x180009305  push    rbp
0x180009306  push    rsi
0x180009307  push    rdi
0x180009308  push    r12
0x18000930a  push    r13
0x18000930c  push    r14
0x18000930e  push    r15
0x180009310  sub     rsp, 30h
0x180009314  mov     r15d, [rcx+14h]
0x180009318  xor     r12d, r12d
0x18000931b  mov     rbp, [rcx+0C0h]
0x180009322  mov     rdi, r8
0x180009325  mov     r14, [rcx+940h]
0x18000932c  mov     rsi, rdx
0x18000932f  mov     [rsp+68h+arg_8], r12
0x180009334  mov     rbx, rcx
0x180009337  mov     [rsp+68h+arg_0], r12d
0x18000933c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009343  lea     r13, WPP_GLOBAL_Control
0x18000934a  cmp     rcx, r13
0x18000934d  jz      short loc_18000939E
0x18000934f  test    dword ptr [rcx+44h], 800h
0x180009356  jz      short loc_180009374
0x180009358  mov     rcx, [rcx+38h]
0x18000935c  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180009363  mov     edx, 5Fh ; '_'
0x180009368  call    WPP_SF_
0x18000936d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009374  cmp     rcx, r13
0x180009377  jz      short loc_18000939E
0x180009379  test    byte ptr [rcx+44h], 80h
0x18000937d  jz      short loc_18000939E
0x18000937f  mov     rcx, [rcx+38h]
0x180009383  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000938a  mov     edx, 60h ; '`'
0x18000938f  mov     r9d, r15d
0x180009392  call    WPP_SF_d
0x180009397  mov     rcx, cs:WPP_GLOBAL_Control
0x18000939e  mov     [rdi], r12
0x1800093a1  mov     [rsi], r12d
0x1800093a4  cmp     [rbx+938h], r12
0x1800093ab  jz      loc_1800094B7
0x1800093b1  lea     rdx, [rbx+0B50h]
0x1800093b8  mov     r9d, 356h
0x1800093be  lea     r8, aMsmqueryglobal; "MSMQueryGlobalParams"
0x1800093c5  mov     rcx, rbx
0x1800093c8  call    cs:__imp_ReleaseWriteLock
0x1800093ce  mov     rax, [rbx+938h]
0x1800093d5  lea     r9, [rsp+68h+arg_8]
0x1800093da  lea     r8, [rsp+68h+arg_0]
0x1800093df  mov     rdx, r14
0x1800093e2  mov     rcx, rbp
0x1800093e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ea  mov     ebp, eax
0x1800093ec  test    eax, eax
0x1800093ee  jz      short loc_180009409
0x1800093f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093f7  cmp     rcx, r13
0x1800093fa  jz      short loc_18000944B
0x1800093fc  test    byte ptr [rcx+44h], 1
0x180009400  jz      short loc_18000944B
0x180009402  mov     edx, 61h ; 'a'
0x180009407  jmp     short loc_180009434
0x180009409  mov     rdx, [rsp+68h+arg_8]
0x18000940e  mov     ecx, [rsp+68h+arg_0]
0x180009412  call    ValidateOneXParams
0x180009417  mov     ebp, eax
0x180009419  test    eax, eax
0x18000941b  jz      short loc_180009483
0x18000941d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009424  cmp     rcx, r13
0x180009427  jz      short loc_18000944B
0x180009429  test    byte ptr [rcx+44h], 1
0x18000942d  jz      short loc_18000944B
0x18000942f  mov     edx, 62h ; 'b'
0x180009434  mov     rcx, [rcx+38h]
0x180009438  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000943f  mov     r9d, r15d
0x180009442  mov     [rsp+68h+var_48], eax
0x180009446  call    WPP_SF_dd
0x18000944b  mov     r9d, 376h
0x180009451  lea     r8, aMsmqueryglobal; "MSMQueryGlobalParams"
0x180009458  lea     rdx, [rbx+0B50h]
0x18000945f  mov     rcx, rbx
0x180009462  call    cs:__imp_AcquireWriteLock
0x180009468  mov     rdx, [rsp+68h+arg_8]
0x18000946d  test    rdx, rdx
0x180009470  jz      short loc_1800094AE
0x180009472  mov     rcx, rbx
0x180009475  call    MSMFreeMemory
0x18000947a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009481  jmp     short loc_1800094F2
0x180009483  mov     rax, [rsp+68h+arg_8]
0x180009488  lea     rdx, [rbx+0B50h]
0x18000948f  mov     [rdi], rax
0x180009492  lea     r8, aMsmqueryglobal; "MSMQueryGlobalParams"
0x180009499  mov     eax, [rsp+68h+arg_0]
0x18000949d  mov     r9d, 376h
0x1800094a3  mov     rcx, rbx
0x1800094a6  mov     [rsi], eax
0x1800094a8  call    cs:__imp_AcquireWriteLock
0x1800094ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094b5  jmp     short loc_1800094F2
0x1800094b7  mov     ebp, r12d
0x1800094ba  cmp     rcx, r13
0x1800094bd  jz      short loc_1800094E4
0x1800094bf  test    byte ptr [rcx+44h], 80h
0x1800094c3  jz      short loc_1800094E4
0x1800094c5  mov     rcx, [rcx+38h]
0x1800094c9  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800094d0  mov     edx, 63h ; 'c'
0x1800094d5  mov     r9d, r15d
0x1800094d8  call    WPP_SF_d
0x1800094dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094e4  mov     rax, [rsp+68h+arg_8]
0x1800094e9  mov     [rdi], rax
0x1800094ec  mov     eax, [rsp+68h+arg_0]
0x1800094f0  mov     [rsi], eax
0x1800094f2  cmp     rcx, r13
0x1800094f5  jz      short loc_180009518
0x1800094f7  test    dword ptr [rcx+44h], 800h
0x1800094fe  jz      short loc_180009518
0x180009500  mov     rcx, [rcx+38h]
0x180009504  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18000950b  mov     edx, 64h ; 'd'
0x180009510  mov     r9d, ebp
0x180009513  call    WPP_SF_D
0x180009518  mov     rbx, [rsp+68h+arg_10]
0x180009520  mov     eax, ebp
0x180009522  add     rsp, 30h
0x180009526  pop     r15
0x180009528  pop     r14
0x18000952a  pop     r13
0x18000952c  pop     r12
0x18000952e  pop     rdi
0x18000952f  pop     rsi
0x180009530  pop     rbp
0x180009531  retn
```
