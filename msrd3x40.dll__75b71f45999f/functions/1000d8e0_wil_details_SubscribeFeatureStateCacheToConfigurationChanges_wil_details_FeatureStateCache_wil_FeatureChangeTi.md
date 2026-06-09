# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1000d8e0`
- end: `0x1000d9f6`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YGXPATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `278`
- prototype: ``
- caller_count: `15`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1000cc40`
- `0x1003ffc0`
- `0x100400b0`
- `0x100401a0`
- `0x10040290`
- `0x10040380`
- `0x10040470`
- `0x10040560`
- `0x10040650`
- `0x100407c0`
- `0x10040930`
- `0x10040aa0`
- `0x10040c10`
- `0x10040d80`
- `0x10040ef0`

## callees

- `0x1000a900`
- `0x1000d8e0`
- `0x1005f10c`
- `0x1005f180`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000d94f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000d9a8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000d94f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1000d9a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d8fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d8fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d96c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d98f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d9c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d9e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d96c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d98f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d9c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d9e9`

## pseudocode

```c
void __stdcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD *v3; // edx
  unsigned int v4; // eax

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_10066544);
    if ( a3
      && a3 == dword_10066550
      && wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&dword_10066564, 8u) )
    {
      v3 = dword_10066568;
      if ( dword_10066568 )
      {
        if ( ((dword_1006656C - (_DWORD)dword_10066568) & (unsigned int)-((unsigned int)dword_10066568 < dword_1006656C)) < 8 )
        {
          memset(
            dword_10066568,
            0,
            (unsigned int)dword_10066568 < dword_1006656C ? dword_1006656C - (_DWORD)dword_10066568 : 0);
          *__errno() = 34;
          _invalid_parameter_noinfo();
        }
        else
        {
          *(_DWORD *)dword_10066568 = a2;
          v3[1] = a1;
        }
        dword_10066568 = (char *)dword_10066568 + 8;
        ReleaseSRWLockExclusive(&stru_10066544);
      }
      else
      {
        *__errno() = 22;
        _invalid_parameter_noinfo();
        dword_10066568 = (char *)dword_10066568 + 8;
        ReleaseSRWLockExclusive(&stru_10066544);
      }
    }
    else
    {
      v4 = -2111;
      if ( a2 )
        v4 = -5;
      _InterlockedAnd(a1, v4);
      ReleaseSRWLockExclusive(&stru_10066544);
    }
  }
}

```

## disassembly

```asm
0x1000d8e0  mov     edi, edi
0x1000d8e2  push    ebp
0x1000d8e3  mov     ebp, esp
0x1000d8e5  push    ecx
0x1000d8e6  mov     eax, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1000d8eb  push    esi
0x1000d8ec  push    edi
0x1000d8ed  test    eax, eax
0x1000d8ef  jz      loc_1000D9EF
0x1000d8f5  push    offset stru_10066544; SRWLock
0x1000d8fa  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d900  mov     eax, [ebp+arg_8]
0x1000d903  mov     ecx, dword_10066550
0x1000d909  mov     esi, [ebp+arg_4]
0x1000d90c  mov     edi, [ebp+arg_0]
0x1000d90f  test    eax, eax
0x1000d911  jz      loc_1000D9D2
0x1000d917  cmp     eax, ecx
0x1000d919  jnz     loc_1000D9D2
0x1000d91f  push    8; unsigned int
0x1000d921  mov     ecx, offset dword_10066564; this
0x1000d926  call    ?ensure@heap_buffer@details_abi@wil@@QAE_NI@Z; wil::details_abi::heap_buffer::ensure(uint)
0x1000d92b  test    al, al
0x1000d92d  jz      loc_1000D9D2
0x1000d933  mov     edx, dword_10066568
0x1000d939  mov     ecx, dword_1006656C
0x1000d93f  sub     ecx, edx
0x1000d941  cmp     edx, dword_1006656C
0x1000d947  sbb     eax, eax
0x1000d949  and     eax, ecx
0x1000d94b  test    edx, edx
0x1000d94d  jnz     short loc_1000D979
0x1000d94f  call    ds:__imp___errno
0x1000d955  mov     dword ptr [eax], 16h
0x1000d95b  call    __invalid_parameter_noinfo
0x1000d960  add     dword_10066568, 8
0x1000d967  push    offset stru_10066544; SRWLock
0x1000d96c  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d972  pop     edi
0x1000d973  pop     esi
0x1000d974  pop     ecx
0x1000d975  pop     ebp
0x1000d976  retn    0Ch
0x1000d979  cmp     eax, 8
0x1000d97c  jb      short loc_1000D99C
0x1000d97e  mov     [edx], esi
0x1000d980  mov     [edx+4], edi
0x1000d983  add     dword_10066568, 8
0x1000d98a  push    offset stru_10066544; SRWLock
0x1000d98f  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d995  pop     edi
0x1000d996  pop     esi
0x1000d997  pop     ecx
0x1000d998  pop     ebp
0x1000d999  retn    0Ch
0x1000d99c  push    eax; Size
0x1000d99d  push    0; Val
0x1000d99f  push    edx; void *
0x1000d9a0  call    _memset
0x1000d9a5  add     esp, 0Ch
0x1000d9a8  call    ds:__imp___errno
0x1000d9ae  mov     dword ptr [eax], 22h ; '"'
0x1000d9b4  call    __invalid_parameter_noinfo
0x1000d9b9  add     dword_10066568, 8
0x1000d9c0  push    offset stru_10066544; SRWLock
0x1000d9c5  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d9cb  pop     edi
0x1000d9cc  pop     esi
0x1000d9cd  pop     ecx
0x1000d9ce  pop     ebp
0x1000d9cf  retn    0Ch
0x1000d9d2  test    esi, esi
0x1000d9d4  mov     eax, 0FFFFF7C1h
0x1000d9d9  mov     ecx, 0FFFFFFFBh
0x1000d9de  cmovnz  eax, ecx
0x1000d9e1  lock and [edi], eax
0x1000d9e4  push    offset stru_10066544; SRWLock
0x1000d9e9  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d9ef  pop     edi
0x1000d9f0  pop     esi
0x1000d9f1  pop     ecx
0x1000d9f2  pop     ebp
0x1000d9f3  retn    0Ch
```
