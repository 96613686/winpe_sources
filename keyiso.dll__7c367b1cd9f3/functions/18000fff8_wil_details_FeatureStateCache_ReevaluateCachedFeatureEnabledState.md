# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000fff8`
- end: `0x180010109`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a708`
- `0x18000fb3c`

## callees

- `0x18000fff8`
- `0x180010150`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // ebx
  __int16 CurrentFeatureEnabledState; // di
  int v8; // ebp
  unsigned int v9; // esi
  signed __int32 v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h]

  v3 = 0;
  v12 = 0;
  v13 = a2;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  CurrentFeatureEnabledState = wil_details_GetCurrentFeatureEnabledState(a3, &v12);
  if ( *(_BYTE *)(a3 + 28) )
    v8 = v12;
  else
    v8 = v3 != 0 ? v12 : 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 )
    {
      LODWORD(v13) = v5;
      if ( (v5 & 2) == 0 )
      {
        v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
        LODWORD(v13) = v9;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v9 = v9 & 0xFFFFFBFF | CurrentFeatureEnabledState & 0x400 | 4;
      LODWORD(v13) = v9;
    }
    v10 = _InterlockedCompareExchange(a1, v9, v5);
    if ( v5 == v10 )
      break;
    v5 = v10;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v13) = CurrentFeatureEnabledState & 0x9C1 | v9 & 0xFFFFF63E;
  return v13;
}

```

## disassembly

```asm
0x18000fff8  mov     [rsp+arg_10], rbx
0x18000fffd  mov     [rsp+arg_18], rbp
0x180010002  push    rsi
0x180010003  push    rdi
0x180010004  push    r12
0x180010006  push    r14
0x180010008  push    r15
0x18001000a  sub     rsp, 20h
0x18001000e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180010015  xor     r14d, r14d
0x180010018  mov     [rsp+48h+arg_0], r14d
0x18001001d  mov     r15, r8
0x180010020  mov     [rsp+48h+arg_8], rdx
0x180010025  mov     rbx, rdx
0x180010028  mov     r12, rcx
0x18001002b  test    rax, rax
0x18001002e  jz      short loc_180010038
0x180010030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010035  mov     r14d, eax
0x180010038  lea     rdx, [rsp+48h+arg_0]
0x18001003d  mov     rcx, r15
0x180010040  call    wil_details_GetCurrentFeatureEnabledState
0x180010045  cmp     byte ptr [r15+1Ch], 0
0x18001004a  mov     rdi, rax
0x18001004d  jnz     short loc_18001005C
0x18001004f  mov     ecx, r14d
0x180010052  neg     ecx
0x180010054  sbb     ebp, ebp
0x180010056  and     ebp, [rsp+48h+arg_0]
0x18001005a  jmp     short loc_180010060
0x18001005c  mov     ebp, [rsp+48h+arg_0]
0x180010060  mov     dword ptr [rsp+48h+arg_8], ebx
0x180010064  mov     esi, ebx
0x180010066  test    ebp, ebp
0x180010068  jz      short loc_180010089
0x18001006a  mov     dword ptr [rsp+48h+arg_8], ebx
0x18001006e  test    bl, 2
0x180010071  jnz     short loc_180010089
0x180010073  and     esi, 0FFFFF63Eh
0x180010079  mov     eax, edi
0x18001007b  and     eax, 9C1h
0x180010080  or      esi, eax
0x180010082  or      esi, 2
0x180010085  mov     dword ptr [rsp+48h+arg_8], esi
0x180010089  mov     edx, ebx
0x18001008b  and     edx, 4
0x18001008e  jnz     short loc_1800100A9
0x180010090  mov     eax, esi
0x180010092  mov     ecx, edi
0x180010094  and     ecx, 400h
0x18001009a  btr     eax, 0Ah
0x18001009e  mov     esi, ecx
0x1800100a0  or      esi, eax
0x1800100a2  or      esi, 4
0x1800100a5  mov     dword ptr [rsp+48h+arg_8], esi
0x1800100a9  mov     eax, ebx
0x1800100ab  lock cmpxchg [r12], esi
0x1800100b1  jz      short loc_1800100B7
0x1800100b3  mov     ebx, eax
0x1800100b5  jmp     short loc_180010060
0x1800100b7  test    edx, edx
0x1800100b9  jnz     short loc_1800100D7
0x1800100bb  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800100c2  test    rax, rax
0x1800100c5  jz      short loc_1800100D7
0x1800100c7  movzx   edx, byte ptr [r15+1Ch]
0x1800100cc  mov     r8d, r14d
0x1800100cf  mov     rcx, r12
0x1800100d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d7  test    ebp, ebp
0x1800100d9  jnz     short loc_1800100ED
0x1800100db  and     esi, 0FFFFF63Eh
0x1800100e1  and     edi, 9C1h
0x1800100e7  or      esi, edi
0x1800100e9  mov     dword ptr [rsp+48h+arg_8], esi
0x1800100ed  mov     rax, [rsp+48h+arg_8]
0x1800100f2  mov     rbx, [rsp+48h+arg_10]
0x1800100f7  mov     rbp, [rsp+48h+arg_18]
0x1800100fc  add     rsp, 20h
0x180010100  pop     r15
0x180010102  pop     r14
0x180010104  pop     r12
0x180010106  pop     rdi
0x180010107  pop     rsi
0x180010108  retn
```
