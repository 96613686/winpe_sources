# MSMFreeMemory

- ea: `0x1800281dc`
- end: `0x180028304`
- name: `MSMFreeMemory`
- size: `296`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180007fb0`
- `0x180009300`
- `0x18000a318`
- `0x1800284bc`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18001d838`
- `0x1800214f0`
- `0x1800281dc`
- `0x180030010`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18002826a`
- `MobileNetworking!ReleaseWriteLock` at `0x18002826a`
- `MobileNetworking!AcquireWriteLock` at `0x1800282c4`
- `MobileNetworking!AcquireWriteLock` at `0x1800282c4`

## pseudocode

```c
__int64 __fastcall MSMFreeMemory(__int64 a1, __int64 a2)
{
  unsigned int v2; // edi
  char *v5; // rcx
  int v6; // eax

  v2 = *(_DWORD *)(a1 + 20);
  v5 = (char *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 48, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids);
      v5 = (char *)WPP_GLOBAL_Control;
    }
    if ( v5 != (char *)&WPP_GLOBAL_Control && v5[68] < 0 )
      WPP_SF_dq(*((_QWORD *)v5 + 7), 49, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v2, a2);
  }
  ReleaseWriteLock(a1, a1 + 2896, "MSMFreeMemory", 504);
  v6 = (*(__int64 (__fastcall **)(__int64))(a1 + 2328))(a2);
  if ( v6 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, v2, v6);
  AcquireWriteLock(a1, a1 + 2896, "MSMFreeMemory", 516);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800281dc  push    rbx
0x1800281de  push    rbp
0x1800281df  push    rsi
0x1800281e0  push    rdi
0x1800281e1  push    r14
0x1800281e3  sub     rsp, 30h
0x1800281e7  mov     edi, [rcx+14h]
0x1800281ea  mov     rsi, rdx
0x1800281ed  mov     rbx, rcx
0x1800281f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281f7  lea     r14, WPP_GLOBAL_Control
0x1800281fe  cmp     rcx, r14
0x180028201  jz      short loc_180028250
0x180028203  test    dword ptr [rcx+44h], 800h
0x18002820a  jz      short loc_180028228
0x18002820c  mov     rcx, [rcx+38h]
0x180028210  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x180028217  mov     edx, 30h ; '0'
0x18002821c  call    WPP_SF_
0x180028221  mov     rcx, cs:WPP_GLOBAL_Control
0x180028228  cmp     rcx, r14
0x18002822b  jz      short loc_180028250
0x18002822d  test    byte ptr [rcx+44h], 80h
0x180028231  jz      short loc_180028250
0x180028233  mov     rcx, [rcx+38h]
0x180028237  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x18002823e  mov     edx, 31h ; '1'
0x180028243  mov     [rsp+58h+var_38], rsi
0x180028248  mov     r9d, edi
0x18002824b  call    WPP_SF_dq
0x180028250  lea     rbp, [rbx+0B50h]
0x180028257  mov     r9d, 1F8h
0x18002825d  mov     rdx, rbp
0x180028260  lea     r8, aMsmfreememory; "MSMFreeMemory"
0x180028267  mov     rcx, rbx
0x18002826a  call    cs:__imp_ReleaseWriteLock
0x180028270  mov     rax, [rbx+918h]
0x180028277  mov     rcx, rsi
0x18002827a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002827f  test    eax, eax
0x180028281  jz      short loc_1800282B1
0x180028283  mov     rcx, cs:WPP_GLOBAL_Control
0x18002828a  cmp     rcx, r14
0x18002828d  jz      short loc_1800282B1
0x18002828f  test    byte ptr [rcx+44h], 1
0x180028293  jz      short loc_1800282B1
0x180028295  mov     rcx, [rcx+38h]
0x180028299  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800282a0  mov     edx, 32h ; '2'
0x1800282a5  mov     dword ptr [rsp+58h+var_38], eax
0x1800282a9  mov     r9d, edi
0x1800282ac  call    WPP_SF_dd
0x1800282b1  mov     r9d, 204h
0x1800282b7  lea     r8, aMsmfreememory; "MSMFreeMemory"
0x1800282be  mov     rdx, rbp
0x1800282c1  mov     rcx, rbx
0x1800282c4  call    cs:__imp_AcquireWriteLock
0x1800282ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282d1  cmp     rcx, r14
0x1800282d4  jz      short loc_1800282F7
0x1800282d6  test    dword ptr [rcx+44h], 800h
0x1800282dd  jz      short loc_1800282F7
0x1800282df  mov     rcx, [rcx+38h]
0x1800282e3  lea     r8, WPP_980772dc0b713ed2d597554bce319f4c_Traceguids
0x1800282ea  mov     edx, 33h ; '3'
0x1800282ef  xor     r9d, r9d
0x1800282f2  call    WPP_SF_D
0x1800282f7  xor     eax, eax
0x1800282f9  add     rsp, 30h
0x1800282fd  pop     r14
0x1800282ff  pop     rdi
0x180028300  pop     rsi
0x180028301  pop     rbp
0x180028302  pop     rbx
0x180028303  retn
```
