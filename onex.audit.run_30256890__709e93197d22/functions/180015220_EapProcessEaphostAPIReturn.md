# EapProcessEaphostAPIReturn

- ea: `0x180015220`
- end: `0x1800152ec`
- name: `EapProcessEaphostAPIReturn`
- size: `204`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e100`
- `0x180025e5c`
- `0x180025ff4`
- `0x1800266f8`
- `0x180026fbc`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180015220`
- `0x18001d208`
- `0x1800214f0`

## pseudocode

```c
__int64 __fastcall EapProcessEaphostAPIReturn(__int64 *a1, unsigned int a2, __int64 a3)
{
  __int64 result; // rax
  int v7; // ebp
  _UNKNOWN **v8; // rcx

  result = *a1;
  v7 = *(_DWORD *)(*a1 + 20);
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    result = WPP_SF_(
               *((_QWORD *)WPP_GLOBAL_Control + 7),
               0xACu,
               (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_10;
  result = EapProcessEaphostFailure(a1, a2, a3, a3);
  if ( !(_DWORD)result )
    goto LABEL_9;
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    result = WPP_SF_dd(
               *((_QWORD *)WPP_GLOBAL_Control + 7),
               0xADu,
               (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids,
               v7);
LABEL_9:
    v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  }
LABEL_10:
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
    return WPP_SF_D((__int64)v8[7], 0xAEu, (__int64)WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x180015220  push    rbx
0x180015222  push    rbp
0x180015223  push    rsi
0x180015224  push    rdi
0x180015225  push    r14
0x180015227  sub     rsp, 30h
0x18001522b  mov     rax, [rcx]
0x18001522e  mov     rsi, r8
0x180015231  mov     ebx, edx
0x180015233  mov     rdi, rcx
0x180015236  mov     ebp, [rax+14h]
0x180015239  mov     rcx, cs:WPP_GLOBAL_Control
0x180015240  lea     r14, WPP_GLOBAL_Control
0x180015247  cmp     rcx, r14
0x18001524a  jz      short loc_180015271
0x18001524c  test    dword ptr [rcx+44h], 800h
0x180015253  jz      short loc_180015271
0x180015255  mov     rcx, [rcx+38h]
0x180015259  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180015260  mov     edx, 0ACh
0x180015265  call    WPP_SF_
0x18001526a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015271  test    ebx, ebx
0x180015273  jz      short loc_1800152BB
0x180015275  mov     r9, rsi
0x180015278  mov     edx, ebx
0x18001527a  mov     rcx, rdi
0x18001527d  call    EapProcessEaphostFailure
0x180015282  test    eax, eax
0x180015284  jz      short loc_1800152B4
0x180015286  mov     rcx, cs:WPP_GLOBAL_Control
0x18001528d  cmp     rcx, r14
0x180015290  jz      short loc_1800152E1
0x180015292  test    byte ptr [rcx+44h], 1
0x180015296  jz      short loc_1800152BB
0x180015298  mov     rcx, [rcx+38h]
0x18001529c  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800152a3  mov     edx, 0ADh
0x1800152a8  mov     [rsp+58h+var_38], eax
0x1800152ac  mov     r9d, ebp
0x1800152af  call    WPP_SF_dd
0x1800152b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152bb  cmp     rcx, r14
0x1800152be  jz      short loc_1800152E1
0x1800152c0  test    dword ptr [rcx+44h], 800h
0x1800152c7  jz      short loc_1800152E1
0x1800152c9  mov     rcx, [rcx+38h]
0x1800152cd  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800152d4  mov     edx, 0AEh
0x1800152d9  xor     r9d, r9d
0x1800152dc  call    WPP_SF_D
0x1800152e1  add     rsp, 30h
0x1800152e5  pop     r14
0x1800152e7  pop     rdi
0x1800152e8  pop     rsi
0x1800152e9  pop     rbp
0x1800152ea  pop     rbx
0x1800152eb  retn
```
