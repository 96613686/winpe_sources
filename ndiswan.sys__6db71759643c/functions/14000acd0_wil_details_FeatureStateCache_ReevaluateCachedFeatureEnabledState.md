# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14000acd0`
- end: `0x14000ade2`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008530`
- `0x14000a798`

## callees

- `0x14000acd0`
- `0x14000ae3c`
- `0x140016230`

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
0x14000acd0  mov     [rsp+arg_10], rbx
0x14000acd5  mov     [rsp+arg_18], rbp
0x14000acda  push    rsi
0x14000acdb  push    rdi
0x14000acdc  push    r12
0x14000acde  push    r14
0x14000ace0  push    r15
0x14000ace2  sub     rsp, 20h
0x14000ace6  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14000aced  xor     r14d, r14d
0x14000acf0  mov     [rsp+48h+arg_0], r14d
0x14000acf5  mov     r15, r8
0x14000acf8  mov     [rsp+48h+arg_8], rdx
0x14000acfd  mov     rbx, rdx
0x14000ad00  mov     r12, rcx
0x14000ad03  test    rax, rax
0x14000ad06  jz      short loc_14000AD10
0x14000ad08  call    _guard_dispatch_icall
0x14000ad0d  mov     r14d, eax
0x14000ad10  lea     rdx, [rsp+48h+arg_0]
0x14000ad15  mov     rcx, r15
0x14000ad18  call    wil_details_GetCurrentFeatureEnabledState
0x14000ad1d  cmp     byte ptr [r15+1Ch], 0
0x14000ad22  mov     rdi, rax
0x14000ad25  jnz     short loc_14000AD34
0x14000ad27  mov     ecx, r14d
0x14000ad2a  neg     ecx
0x14000ad2c  sbb     ebp, ebp
0x14000ad2e  and     ebp, [rsp+48h+arg_0]
0x14000ad32  jmp     short loc_14000AD38
0x14000ad34  mov     ebp, [rsp+48h+arg_0]
0x14000ad38  mov     dword ptr [rsp+48h+arg_8], ebx
0x14000ad3c  mov     esi, ebx
0x14000ad3e  test    ebp, ebp
0x14000ad40  jz      short loc_14000AD61
0x14000ad42  mov     dword ptr [rsp+48h+arg_8], ebx
0x14000ad46  test    bl, 2
0x14000ad49  jnz     short loc_14000AD61
0x14000ad4b  and     esi, 0FFFFF63Eh
0x14000ad51  mov     eax, edi
0x14000ad53  and     eax, 9C1h
0x14000ad58  or      esi, eax
0x14000ad5a  or      esi, 2
0x14000ad5d  mov     dword ptr [rsp+48h+arg_8], esi
0x14000ad61  mov     edx, ebx
0x14000ad63  and     edx, 4
0x14000ad66  jnz     short loc_14000AD81
0x14000ad68  mov     eax, esi
0x14000ad6a  mov     ecx, edi
0x14000ad6c  and     ecx, 400h
0x14000ad72  btr     eax, 0Ah
0x14000ad76  mov     esi, ecx
0x14000ad78  or      esi, eax
0x14000ad7a  or      esi, 4
0x14000ad7d  mov     dword ptr [rsp+48h+arg_8], esi
0x14000ad81  mov     eax, ebx
0x14000ad83  lock cmpxchg [r12], esi
0x14000ad89  jz      short loc_14000AD8F
0x14000ad8b  mov     ebx, eax
0x14000ad8d  jmp     short loc_14000AD38
0x14000ad8f  test    edx, edx
0x14000ad91  jnz     short loc_14000ADAF
0x14000ad93  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14000ad9a  test    rax, rax
0x14000ad9d  jz      short loc_14000ADAF
0x14000ad9f  movzx   edx, byte ptr [r15+1Ch]
0x14000ada4  mov     r8d, r14d
0x14000ada7  mov     rcx, r12
0x14000adaa  call    _guard_dispatch_icall
0x14000adaf  test    ebp, ebp
0x14000adb1  jnz     short loc_14000ADC5
0x14000adb3  and     esi, 0FFFFF63Eh
0x14000adb9  and     edi, 9C1h
0x14000adbf  or      esi, edi
0x14000adc1  mov     dword ptr [rsp+48h+arg_8], esi
0x14000adc5  mov     rax, [rsp+48h+arg_8]
0x14000adca  mov     rbx, [rsp+48h+arg_10]
0x14000adcf  mov     rbp, [rsp+48h+arg_18]
0x14000add4  add     rsp, 20h
0x14000add8  pop     r15
0x14000adda  pop     r14
0x14000addc  pop     r12
0x14000adde  pop     rdi
0x14000addf  pop     rsi
0x14000ade0  retn
```
