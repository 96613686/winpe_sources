# MRxDAVDereferenceNetRootContext

- ea: `0x1400192b8`
- end: `0x1400193ca`
- name: `MRxDAVDereferenceNetRootContext`
- size: `274`
- prototype: `__int64 __fastcall(char *P)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400194f0`
- `0x1400195b0`

## callees

- `0x1400017e4`
- `0x140001838`
- `0x1400192b8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400192f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019397`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400192f7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140019397`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019372`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019372`
- `rdbss!RxNameCacheFinalize` at `0x14001932f`
- `rdbss!RxNameCacheFinalize` at `0x140019342`
- `rdbss!RxNameCacheFinalize` at `0x140019355`
- `rdbss!RxNameCacheFinalize` at `0x14001932f`
- `rdbss!RxNameCacheFinalize` at `0x140019342`
- `rdbss!RxNameCacheFinalize` at `0x140019355`

## pseudocode

```c
__int64 __fastcall MRxDAVDereferenceNetRootContext(char *P)
{
  signed __int32 v2; // esi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  HANDLE v6; // rax

  if ( P )
  {
    v2 = _InterlockedDecrement((volatile signed __int32 *)P);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_qqD(v3, 62, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, CurrentThreadId, P, v2);
    }
    if ( !v2 )
    {
      RxNameCacheFinalize((PNAME_CACHE_CONTROL)(P + 16));
      RxNameCacheFinalize((PNAME_CACHE_CONTROL)(P + 200));
      RxNameCacheFinalize((PNAME_CACHE_CONTROL)(P + 384));
      *(_QWORD *)(*((_QWORD *)P + 1) + 40LL) = 0;
      ExFreePoolWithTag(P, 0);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v5 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v6 = PsGetCurrentThreadId();
        WPP_SF_qq(v5, 63, WPP_295ecfbeda123026d67516205ca0d119_Traceguids, v6, P);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400192b8  push    rbx
0x1400192ba  push    rsi
0x1400192bb  push    rdi
0x1400192bc  push    r14
0x1400192be  sub     rsp, 38h
0x1400192c2  mov     rdi, rcx
0x1400192c5  test    rcx, rcx
0x1400192c8  jz      loc_1400193BD
0x1400192ce  or      esi, 0FFFFFFFFh
0x1400192d1  lock xadd [rcx], esi
0x1400192d5  dec     esi
0x1400192d7  mov     rbx, cs:WPP_GLOBAL_Control
0x1400192de  lea     r14, WPP_GLOBAL_Control
0x1400192e5  cmp     rbx, r14
0x1400192e8  jz      short loc_140019323
0x1400192ea  test    dword ptr [rbx+2Ch], 2000h
0x1400192f1  jz      short loc_140019323
0x1400192f3  mov     rbx, [rbx+18h]
0x1400192f7  call    cs:__imp_PsGetCurrentThreadId
0x1400192fe  nop     dword ptr [rax+rax+00h]
0x140019303  mov     edx, 3Eh ; '>'
0x140019308  mov     [rsp+58h+var_30], esi
0x14001930c  mov     r9, rax
0x14001930f  mov     [rsp+58h+var_38], rdi
0x140019314  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x14001931b  mov     rcx, rbx
0x14001931e  call    WPP_SF_qqD
0x140019323  test    esi, esi
0x140019325  jnz     loc_1400193BD
0x14001932b  lea     rcx, [rdi+10h]; NameCacheCtl
0x14001932f  call    cs:__imp_RxNameCacheFinalize
0x140019336  nop     dword ptr [rax+rax+00h]
0x14001933b  lea     rcx, [rdi+0C8h]; NameCacheCtl
0x140019342  call    cs:__imp_RxNameCacheFinalize
0x140019349  nop     dword ptr [rax+rax+00h]
0x14001934e  lea     rcx, [rdi+180h]; NameCacheCtl
0x140019355  call    cs:__imp_RxNameCacheFinalize
0x14001935c  nop     dword ptr [rax+rax+00h]
0x140019361  mov     rax, [rdi+8]
0x140019365  xor     edx, edx; Tag
0x140019367  mov     rcx, rdi; P
0x14001936a  mov     qword ptr [rax+28h], 0
0x140019372  call    cs:__imp_ExFreePoolWithTag
0x140019379  nop     dword ptr [rax+rax+00h]
0x14001937e  mov     rbx, cs:WPP_GLOBAL_Control
0x140019385  cmp     rbx, r14
0x140019388  jz      short loc_1400193BD
0x14001938a  test    dword ptr [rbx+2Ch], 2000h
0x140019391  jz      short loc_1400193BD
0x140019393  mov     rbx, [rbx+18h]
0x140019397  call    cs:__imp_PsGetCurrentThreadId
0x14001939e  nop     dword ptr [rax+rax+00h]
0x1400193a3  lea     edx, [rsi+3Fh]
0x1400193a6  mov     [rsp+58h+var_38], rdi
0x1400193ab  mov     r9, rax
0x1400193ae  lea     r8, WPP_295ecfbeda123026d67516205ca0d119_Traceguids
0x1400193b5  mov     rcx, rbx
0x1400193b8  call    WPP_SF_qq
0x1400193bd  xor     eax, eax
0x1400193bf  add     rsp, 38h
0x1400193c3  pop     r14
0x1400193c5  pop     rdi
0x1400193c6  pop     rsi
0x1400193c7  pop     rbx
0x1400193c8  retn
```
