# FIPostOperationCommonCallback

- ea: `0x1400018d0`
- end: `0x14000199e`
- name: `FIPostOperationCommonCallback`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400018d0`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `FLTMGR!FltGetActivityIdCallbackData` at `0x14000193b`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x14000193b`

## pseudocode

```c
__int64 __fastcall FIPostOperationCommonCallback(__int64 a1)
{
  void (__fastcall *v2)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rdi
  int v3; // eax
  int ActivityIdCallbackData; // eax
  __int128 *v5; // rdx
  __int16 v7; // [rsp+20h] [rbp-68h]
  __int128 v8; // [rsp+40h] [rbp-48h] BYREF
  int v9; // [rsp+50h] [rbp-38h]
  __int128 v10; // [rsp+58h] [rbp-30h] BYREF
  _QWORD v11[2]; // [rsp+68h] [rbp-20h] BYREF

  v9 = 0;
  v8 = 0;
  v10 = 0;
  v2 = *(void (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 24);
  if ( v2 )
  {
    v3 = *(_DWORD *)(a1 + 24);
    *(_QWORD *)&v8 = a1;
    v9 = v3;
    *((_QWORD *)&v8 + 1) = *(_QWORD *)(a1 + 32);
    v11[0] = &v8;
    v11[1] = 20;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v10);
    v5 = &v10;
    if ( ActivityIdCallbackData < 0 )
      v5 = 0;
    v7 = 1100;
    v2(*(_QWORD *)(a1 + 8), v11, 1, 0x2000000, v7, v5);
  }
  return 0;
}

```

## disassembly

```asm
0x1400018d0  mov     r11, rsp
0x1400018d3  mov     [r11+10h], rbx
0x1400018d7  push    rdi
0x1400018d8  sub     rsp, 80h
0x1400018df  mov     rax, cs:__security_cookie
0x1400018e6  xor     rax, rsp
0x1400018e9  mov     [rsp+88h+var_10], rax
0x1400018ee  xor     eax, eax
0x1400018f0  xorps   xmm0, xmm0
0x1400018f3  mov     [rsp+88h+var_38], eax
0x1400018f7  mov     rbx, rcx
0x1400018fa  mov     rax, cs:qword_140009A00
0x140001901  movups  [rsp+88h+var_48], xmm0
0x140001906  movups  [rsp+88h+var_30], xmm0
0x14000190b  mov     rdi, [rax+18h]
0x14000190f  test    rdi, rdi
0x140001912  jz      short loc_14000197D
0x140001914  mov     eax, [rcx+18h]
0x140001917  lea     rdx, [r11-30h]
0x14000191b  mov     [r11-48h], rcx
0x14000191f  mov     [rsp+88h+var_38], eax
0x140001923  mov     rax, [rcx+20h]
0x140001927  mov     [r11-40h], rax
0x14000192b  lea     rax, [r11-48h]
0x14000192f  mov     [r11-20h], rax
0x140001933  mov     qword ptr [r11-18h], 14h
0x14000193b  call    cs:__imp_FltGetActivityIdCallbackData
0x140001942  nop     dword ptr [rax+rax+00h]
0x140001947  xor     ecx, ecx
0x140001949  lea     rdx, [rsp+88h+var_30]
0x14000194e  test    eax, eax
0x140001950  mov     r9d, 2000000h
0x140001956  mov     r8d, 1
0x14000195c  mov     rax, rdi
0x14000195f  cmovs   rdx, rcx
0x140001963  mov     rcx, [rbx+8]
0x140001967  mov     [rsp+88h+var_60], rdx
0x14000196c  lea     rdx, [rsp+88h+var_20]
0x140001971  mov     [rsp+88h+var_68], 44Ch
0x140001978  call    _guard_dispatch_icall
0x14000197d  xor     eax, eax
0x14000197f  mov     rcx, [rsp+88h+var_10]
0x140001984  xor     rcx, rsp; StackCookie
0x140001987  call    __security_check_cookie
0x14000198c  mov     rbx, [rsp+88h+arg_8]
0x140001994  add     rsp, 80h
0x14000199b  pop     rdi
0x14000199c  retn
```
