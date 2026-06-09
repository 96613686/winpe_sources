# VidSchiSwitchContextWithCheck

- ea: `0x14000e4c0`
- end: `0x14000e8fa`
- name: `VidSchiSwitchContextWithCheck`
- size: `1082`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f5a0`

## callees

- `0x14000d548`
- `0x14000daac`
- `0x14000e4c0`
- `0x14000eda0`
- `0x1400121c0`
- `0x140058760`

## import_xrefs

- `ntoskrnl!RtlClearBitEx` at `0x14000e5b3`
- `ntoskrnl!RtlClearBitEx` at `0x14000e5b3`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000e5d3`
- `ntoskrnl!RtlCopyBitMapEx` at `0x14000e5d3`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000e5e5`
- `ntoskrnl!RtlIntersectBitMapsEx` at `0x14000e5e5`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000e5f9`
- `ntoskrnl!RtlAreBitsClearEx` at `0x14000e5f9`
- `watchdog!WdLogSingleEntry2` at `0x14000e779`
- `watchdog!WdLogSingleEntry2` at `0x14000e862`
- `watchdog!WdLogSingleEntry2` at `0x14000e779`
- `watchdog!WdLogSingleEntry2` at `0x14000e862`
- `HAL!KeQueryPerformanceCounter` at `0x14000e72d`
- `HAL!KeQueryPerformanceCounter` at `0x14000e81c`
- `HAL!KeQueryPerformanceCounter` at `0x14000e72d`
- `HAL!KeQueryPerformanceCounter` at `0x14000e81c`

## pseudocode

```c
__int64 __fastcall VidSchiSwitchContextWithCheck(__int64 a1)
{
  __int64 v1; // rbp
  unsigned int v3; // r15d
  __int64 v4; // r14
  int v5; // eax
  __int64 v6; // rdx
  int v7; // r12d
  union _LARGE_INTEGER v8; // rbx
  __int64 v9; // rdi
  void (__fastcall *v11)(_QWORD); // rax
  LARGE_INTEGER v12; // r9
  unsigned __int64 v13; // rcx
  __int64 v14; // r8
  void (__fastcall *v15)(_QWORD); // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  LARGE_INTEGER v18; // r9
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  _QWORD *v24; // rdx
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 96);
  v3 = 1;
  v4 = *(_QWORD *)(v1 + 24);
  if ( *(_DWORD *)(v4 + 3340) || (*(_BYTE *)(v4 + 3364) & 1) != 0 )
    goto LABEL_23;
  if ( (unsigned __int8)VidSchiBlockContextOnPendingFlips(*(_QWORD *)(a1 + 656)) )
  {
    if ( !*(_QWORD *)(a1 + 48) )
    {
      v22 = *(_QWORD *)(a1 + 96);
      v23 = *(_QWORD *)(v22 + 24) + 3848LL;
      v24 = *(_QWORD **)(*(_QWORD *)(v22 + 24) + 3856LL);
      if ( *v24 != v23 )
        __fastfail(3u);
      *(_QWORD *)(a1 + 40) = v23;
      *(_QWORD *)(a1 + 48) = v24;
      *v24 = a1 + 40;
      *(_QWORD *)(v23 + 8) = a1 + 40;
    }
    v16 = 3;
    v17 = 16747;
    goto LABEL_41;
  }
  v5 = *(_DWORD *)(a1 + 652);
  PerformanceFrequency.QuadPart = 0;
  if ( (v5 & 0xF) != 0
    || (*(_DWORD *)(a1 + 112) & 0x10) == 0
    || (v6 = *(_QWORD *)(a1 + 104), *(_BYTE *)(v6 + 212))
    || (v7 = *(_DWORD *)(v1 + 16520), _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 208), 0, 0)) )
  {
LABEL_23:
    VidSchiSwitchContext(a1);
    return v3;
  }
  if ( (unsigned int)VidSchiCheckPreemptionPolicy(a1, &PerformanceFrequency) )
  {
    v3 = 4;
LABEL_18:
    if ( v7 == -1 )
      goto LABEL_23;
    if ( (*(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) & 0x10) == 0 )
    {
      if ( *(_DWORD *)(v1 + 16520) != -1 )
      {
        v11 = *(void (__fastcall **)(_QWORD))(v4 + 3408);
        if ( v11 )
          v11(*(_QWORD *)(v4 + 3448));
      }
      *(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) |= 0x10u;
    }
    if ( *(_BYTE *)(v1 + 16524) )
      goto LABEL_23;
    v16 = 8;
    v17 = 16915;
LABEL_41:
    VidSchiUpdateContextStatus(a1, v16, v17);
    return 3;
  }
  v8 = PerformanceFrequency;
  if ( PerformanceFrequency.QuadPart != -1 )
  {
    PerformanceFrequency.QuadPart = 0;
    v18 = KeQueryPerformanceCounter(&PerformanceFrequency);
    if ( is_mul_ok(v18.QuadPart, 0x989680u) )
      v19 = (unsigned __int64)v18.QuadPart
          * (unsigned __int128)0x989680uLL
          / (unsigned __int64)PerformanceFrequency.QuadPart;
    else
      v19 = 10000000 * (v18.QuadPart / (unsigned __int64)PerformanceFrequency.QuadPart)
          + 10000000 * (v18.QuadPart % (unsigned __int64)PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart;
    v20 = v19 + v8.QuadPart;
    v21 = *(_QWORD *)(v1 + 96);
    *(_QWORD *)(v1 + 136) = v21;
    *(_QWORD *)(v1 + 128) = v20;
    WdLogSingleEntry2(4, *(unsigned __int16 *)(v1 + 4), v21);
    WdLogGlobalForLineNumber = 16797;
  }
  v9 = *(_QWORD *)(v1 + 8LL * *(unsigned int *)(v1 + 1584) + 1592);
  if ( v8.QuadPart == -1 && !*(_DWORD *)(v1 + 3032) && (*(_DWORD *)(v1 + 3012) > 1u || v9 && a1 != v9) )
  {
    PerformanceFrequency.QuadPart = 0;
    v12 = KeQueryPerformanceCounter(&PerformanceFrequency);
    if ( is_mul_ok(v12.QuadPart, 0x989680u) )
      v13 = (unsigned __int64)v12.QuadPart
          * (unsigned __int128)0x989680uLL
          / (unsigned __int64)PerformanceFrequency.QuadPart;
    else
      v13 = 10000000 * (v12.QuadPart / (unsigned __int64)PerformanceFrequency.QuadPart)
          + 10000000 * (v12.QuadPart % (unsigned __int64)PerformanceFrequency.QuadPart) / PerformanceFrequency.QuadPart;
    v14 = *(_QWORD *)(v1 + 96);
    *(_QWORD *)(v1 + 128) = v13 + *(_QWORD *)(a1 + 488);
    *(_QWORD *)(v1 + 144) = v14;
    WdLogSingleEntry2(4, *(unsigned __int16 *)(v1 + 4), v14);
    WdLogGlobalForLineNumber = 16824;
  }
  if ( *(int *)(v1 + 3008) > 0
    && *(_DWORD *)(v1 + 3024) < *(_DWORD *)(v4 + 252)
    && !*(_DWORD *)(v1 + 3032)
    && (!v9
     || !*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v9 + 96) + 24LL) + 7942LL)
     || *(_DWORD *)(v9 + 412) <= *(_DWORD *)(a1 + 412)) )
  {
    goto LABEL_18;
  }
  RtlClearBitEx(v4 + 632, *(unsigned __int16 *)(v1 + 4));
  RtlCopyBitMapEx(v4 + 584, v4 + 680, 0);
  RtlIntersectBitMapsEx(v4 + 680, v4 + 632);
  if ( !(unsigned __int8)RtlAreBitsClearEx(v4 + 680, 0, *(_QWORD *)(v4 + 680)) )
    return 3;
  if ( v7 != -1 && (*(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) & 0x10) == 0 )
  {
    if ( *(_DWORD *)(v1 + 16520) != -1 )
    {
      v15 = *(void (__fastcall **)(_QWORD))(v4 + 3408);
      if ( v15 )
        v15(*(_QWORD *)(v4 + 3448));
    }
    *(_DWORD *)(*(_QWORD *)(a1 + 656) + 80LL) |= 0x10u;
  }
  return 2;
}

```

## disassembly

```asm
0x14000e4c0  mov     [rsp+arg_10], rbx
0x14000e4c5  push    rbp
0x14000e4c6  push    rsi
0x14000e4c7  push    rdi
0x14000e4c8  push    r12
0x14000e4ca  push    r13
0x14000e4cc  push    r14
0x14000e4ce  push    r15
0x14000e4d0  sub     rsp, 20h
0x14000e4d4  mov     rbp, [rcx+60h]
0x14000e4d8  xor     r13d, r13d
0x14000e4db  mov     rsi, rcx
0x14000e4de  mov     r15d, 1
0x14000e4e4  mov     r14, [rbp+18h]
0x14000e4e8  cmp     [r14+0D0Ch], r13d
0x14000e4ef  jnz     loc_14000E687
0x14000e4f5  test    [r14+0D24h], r15b
0x14000e4fc  jnz     loc_14000E687
0x14000e502  mov     rcx, [rcx+290h]
0x14000e509  call    VidSchiBlockContextOnPendingFlips
0x14000e50e  test    al, al
0x14000e510  jnz     loc_14000E8A8
0x14000e516  mov     eax, [rsi+28Ch]
0x14000e51c  mov     qword ptr [rsp+58h+PerformanceFrequency], r13
0x14000e521  test    al, 0Fh
0x14000e523  jnz     loc_14000E687
0x14000e529  mov     eax, [rsi+70h]
0x14000e52c  test    al, 10h
0x14000e52e  jz      loc_14000E687
0x14000e534  mov     rdx, [rsi+68h]
0x14000e538  cmp     [rdx+0D4h], r13b
0x14000e53f  jnz     loc_14000E687
0x14000e545  mov     r12d, [rbp+4088h]
0x14000e54c  mov     ecx, r13d
0x14000e54f  xor     eax, eax
0x14000e551  lock cmpxchg [rdx+0D0h], ecx
0x14000e559  jnz     loc_14000E687
0x14000e55f  lea     rdx, [rsp+58h+PerformanceFrequency]
0x14000e564  mov     rcx, rsi
0x14000e567  call    VidSchiCheckPreemptionPolicy
0x14000e56c  test    eax, eax
0x14000e56e  jnz     loc_14000E8EF
0x14000e574  mov     rbx, qword ptr [rsp+58h+PerformanceFrequency]
0x14000e579  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e57d  jnz     loc_14000E812
0x14000e583  mov     eax, [rbp+630h]
0x14000e589  mov     rdi, [rbp+rax*8+638h]
0x14000e591  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000e595  jz      loc_14000E6FB
0x14000e59b  mov     eax, [rbp+0BC0h]
0x14000e5a1  test    eax, eax
0x14000e5a3  jg      short loc_14000E614
0x14000e5a5  movzx   edx, word ptr [rbp+4]
0x14000e5a9  lea     rbx, [r14+278h]
0x14000e5b0  mov     rcx, rbx
0x14000e5b3  call    cs:__imp_RtlClearBitEx
0x14000e5ba  nop     dword ptr [rax+rax+00h]
0x14000e5bf  lea     rdi, [r14+2A8h]
0x14000e5c6  xor     r8d, r8d
0x14000e5c9  mov     rdx, rdi
0x14000e5cc  lea     rcx, [r14+248h]
0x14000e5d3  call    cs:__imp_RtlCopyBitMapEx
0x14000e5da  nop     dword ptr [rax+rax+00h]
0x14000e5df  mov     rdx, rbx
0x14000e5e2  mov     rcx, rdi
0x14000e5e5  call    cs:__imp_RtlIntersectBitMapsEx
0x14000e5ec  nop     dword ptr [rax+rax+00h]
0x14000e5f1  mov     r8, [rdi]
0x14000e5f4  xor     edx, edx
0x14000e5f6  mov     rcx, rdi
0x14000e5f9  call    cs:__imp_RtlAreBitsClearEx
0x14000e600  nop     dword ptr [rax+rax+00h]
0x14000e605  test    al, al
0x14000e607  jnz     loc_14000E6C2
0x14000e60d  mov     eax, 3
0x14000e612  jmp     short loc_14000E692
0x14000e614  mov     ecx, [r14+0FCh]
0x14000e61b  mov     eax, [rbp+0BD0h]
0x14000e621  cmp     eax, ecx
0x14000e623  jnb     short loc_14000E5A5
0x14000e625  cmp     [rbp+0BD8h], r13d
0x14000e62c  jnz     loc_14000E5A5
0x14000e632  test    rdi, rdi
0x14000e635  jz      short loc_14000E64C
0x14000e637  mov     rax, [rdi+60h]
0x14000e63b  mov     rcx, [rax+18h]
0x14000e63f  cmp     [rcx+1F06h], r13b
0x14000e646  jnz     loc_14000E7FB
0x14000e64c  or      r8d, 0FFFFFFFFh
0x14000e650  cmp     r12d, r8d
0x14000e653  jz      short loc_14000E687
0x14000e655  mov     rax, [rsi+290h]
0x14000e65c  mov     edx, [rax+50h]
0x14000e65f  test    dl, 10h
0x14000e662  jnz     short loc_14000E67A
0x14000e664  mov     edx, [rbp+4088h]
0x14000e66a  cmp     edx, r8d
0x14000e66d  jnz     short loc_14000E6A8
0x14000e66f  mov     rax, [rsi+290h]
0x14000e676  or      dword ptr [rax+50h], 10h
0x14000e67a  cmp     [rbp+408Ch], r13b
0x14000e681  jz      loc_14000E7B5
0x14000e687  mov     rcx, rsi
0x14000e68a  call    VidSchiSwitchContext
0x14000e68f  mov     eax, r15d
0x14000e692  mov     rbx, [rsp+58h+arg_10]
0x14000e697  add     rsp, 20h
0x14000e69b  pop     r15
0x14000e69d  pop     r14
0x14000e69f  pop     r13
0x14000e6a1  pop     r12
0x14000e6a3  pop     rdi
0x14000e6a4  pop     rsi
0x14000e6a5  pop     rbp
0x14000e6a6  retn
0x14000e6a8  mov     rax, [r14+0D50h]
0x14000e6af  test    rax, rax
0x14000e6b2  jz      short loc_14000E66F
0x14000e6b4  mov     rcx, [r14+0D78h]
0x14000e6bb  call    _guard_dispatch_icall
0x14000e6c0  jmp     short loc_14000E66F
0x14000e6c2  or      r8d, 0FFFFFFFFh
0x14000e6c6  cmp     r12d, r8d
0x14000e6c9  jz      short loc_14000E6F4
0x14000e6cb  mov     rax, [rsi+290h]
0x14000e6d2  mov     ecx, [rax+50h]
0x14000e6d5  test    cl, 10h
0x14000e6d8  jnz     short loc_14000E6F4
0x14000e6da  mov     edx, [rbp+4088h]
0x14000e6e0  cmp     edx, r8d
0x14000e6e3  jnz     loc_14000E794
0x14000e6e9  mov     rax, [rsi+290h]
0x14000e6f0  or      dword ptr [rax+50h], 10h
0x14000e6f4  mov     eax, 2
0x14000e6f9  jmp     short loc_14000E692
0x14000e6fb  cmp     [rbp+0BD8h], r13d
0x14000e702  jnz     loc_14000E59B
0x14000e708  cmp     [rbp+0BC4h], r15d
0x14000e70f  ja      short loc_14000E723
0x14000e711  test    rdi, rdi
0x14000e714  jz      loc_14000E59B
0x14000e71a  cmp     rsi, rdi
0x14000e71d  jz      loc_14000E59B
0x14000e723  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14000e728  mov     qword ptr [rsp+58h+PerformanceFrequency], r13
0x14000e72d  call    cs:__imp_KeQueryPerformanceCounter
0x14000e734  nop     dword ptr [rax+rax+00h]
0x14000e739  mov     r8, qword ptr [rsp+58h+PerformanceFrequency]
0x14000e73e  mov     r9, rax
0x14000e741  mov     eax, 989680h
0x14000e746  mul     r9
0x14000e749  test    rdx, rdx
0x14000e74c  jnz     short loc_14000E7CD
0x14000e74e  div     r8
0x14000e751  mov     rcx, rax
0x14000e754  mov     rdx, [rsi+1E8h]
0x14000e75b  mov     r8, [rbp+60h]
0x14000e75f  add     rdx, rcx
0x14000e762  mov     [rbp+80h], rdx
0x14000e769  mov     [rbp+90h], r8
0x14000e770  movzx   edx, word ptr [rbp+4]
0x14000e774  mov     ecx, 4
0x14000e779  call    cs:__imp_WdLogSingleEntry2
0x14000e780  nop     dword ptr [rax+rax+00h]
0x14000e785  mov     cs:WdLogGlobalForLineNumber, 41B8h
0x14000e78f  jmp     loc_14000E59B
0x14000e794  mov     rax, [r14+0D50h]
0x14000e79b  test    rax, rax
0x14000e79e  jz      loc_14000E6E9
0x14000e7a4  mov     rcx, [r14+0D78h]
0x14000e7ab  call    _guard_dispatch_icall
0x14000e7b0  jmp     loc_14000E6E9
0x14000e7b5  mov     edx, 8
0x14000e7ba  mov     r8d, 4213h
0x14000e7c0  mov     rcx, rsi
0x14000e7c3  call    VidSchiUpdateContextStatus
0x14000e7c8  jmp     loc_14000E60D
0x14000e7cd  xor     edx, edx
0x14000e7cf  mov     rax, r9
0x14000e7d2  div     r8
0x14000e7d5  imul    rax, rdx, 989680h
0x14000e7dc  xor     edx, edx
0x14000e7de  div     r8
0x14000e7e1  xor     edx, edx
0x14000e7e3  mov     rcx, rax
0x14000e7e6  mov     rax, r9
0x14000e7e9  div     r8
0x14000e7ec  imul    rdx, rax, 989680h
0x14000e7f3  add     rcx, rdx
0x14000e7f6  jmp     loc_14000E754
0x14000e7fb  mov     eax, [rsi+19Ch]
0x14000e801  cmp     [rdi+19Ch], eax
0x14000e807  jbe     loc_14000E64C
0x14000e80d  jmp     loc_14000E5A5
0x14000e812  lea     rcx, [rsp+58h+PerformanceFrequency]; PerformanceFrequency
0x14000e817  mov     qword ptr [rsp+58h+PerformanceFrequency], r13
0x14000e81c  call    cs:__imp_KeQueryPerformanceCounter
0x14000e823  nop     dword ptr [rax+rax+00h]
0x14000e828  mov     rcx, qword ptr [rsp+58h+PerformanceFrequency]
0x14000e82d  mov     r9, rax
0x14000e830  mov     eax, 989680h
0x14000e835  mul     r9
0x14000e838  test    rdx, rdx
0x14000e83b  jnz     short loc_14000E87D
0x14000e83d  div     rcx
0x14000e840  mov     r8, rax
0x14000e843  lea     rax, [r8+rbx]
0x14000e847  mov     r8, [rbp+60h]
0x14000e84b  mov     [rbp+88h], r8
0x14000e852  mov     [rbp+80h], rax
0x14000e859  movzx   edx, word ptr [rbp+4]
0x14000e85d  mov     ecx, 4
0x14000e862  call    cs:__imp_WdLogSingleEntry2
0x14000e869  nop     dword ptr [rax+rax+00h]
0x14000e86e  mov     cs:WdLogGlobalForLineNumber, 419Dh
0x14000e878  jmp     loc_14000E583
0x14000e87d  xor     edx, edx
0x14000e87f  mov     rax, r9
0x14000e882  div     rcx
0x14000e885  imul    rax, rdx, 989680h
0x14000e88c  xor     edx, edx
0x14000e88e  div     rcx
0x14000e891  xor     edx, edx
0x14000e893  mov     r8, rax
0x14000e896  mov     rax, r9
0x14000e899  div     rcx
0x14000e89c  imul    rcx, rax, 989680h
0x14000e8a3  add     r8, rcx
0x14000e8a6  jmp     short loc_14000E843
0x14000e8a8  cmp     [rsi+30h], r13
0x14000e8ac  jnz     short loc_14000E8D8
0x14000e8ae  mov     rax, [rsi+60h]
0x14000e8b2  mov     rcx, [rax+18h]
0x14000e8b6  add     rcx, 0F08h
0x14000e8bd  mov     rdx, [rcx+8]
0x14000e8c1  cmp     [rdx], rcx
0x14000e8c4  jnz     short loc_14000E8E8
0x14000e8c6  lea     rax, [rsi+28h]
0x14000e8ca  mov     [rax], rcx
0x14000e8cd  mov     [rax+8], rdx
0x14000e8d1  mov     [rdx], rax
0x14000e8d4  mov     [rcx+8], rax
0x14000e8d8  mov     edx, 3
0x14000e8dd  mov     r8d, 416Bh
0x14000e8e3  jmp     loc_14000E7C0
0x14000e8e8  mov     ecx, 3
0x14000e8ed  int     29h; Win8: RtlFailFast(ecx)
0x14000e8ef  mov     r15d, 4
0x14000e8f5  jmp     loc_14000E64C
```
