# UninitializeCNG

- ea: `0x18000b584`
- end: `0x18000b623`
- name: `UninitializeCNG`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009aa4`
- `0x18000b45c`

## callees

- `0x18000b584`
- `0x18000df1c`
- `0x180016744`
- `0x180017160`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000b5e6`
- `ntdll!RtlDeleteCriticalSection` at `0x18000b611`
- `ntdll!RtlDeleteCriticalSection` at `0x18000b5e6`
- `ntdll!RtlDeleteCriticalSection` at `0x18000b611`

## pseudocode

```c
NTSTATUS UninitializeCNG()
{
  NTSTATUS result; // eax
  char v1; // cl

  result = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetImpl'::`2'::impl);
  v1 = dword_180025D78;
  if ( (_BYTE)result && (dword_180025D78 & 8) != 0 )
  {
    result = UninitializeKeyIsoPerfCounters();
    v1 = dword_180025D78 & 0xF7;
    dword_180025D78 &= ~8u;
  }
  if ( (v1 & 2) != 0 )
  {
    result = UninitializeLoader();
    v1 = dword_180025D78 & 0xFD;
    dword_180025D78 &= ~2u;
  }
  if ( (v1 & 1) != 0 )
  {
    result = dword_180025FFC;
    if ( dword_180025FFC )
    {
      result = RtlDeleteCriticalSection(&CriticalSection);
      dword_180025FFC = 0;
    }
    v1 = dword_180025D78 & 0xFE;
    dword_180025D78 &= ~1u;
  }
  if ( (v1 & 4) != 0 )
  {
    result = RtlDeleteCriticalSection(&g_ResLock);
    dword_180025D78 &= ~4u;
  }
  return result;
}

```

## disassembly

```asm
0x18000b584  sub     rsp, 28h
0x18000b588  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT> `wil::Feature<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::GetImpl(void)'::`2'::impl
0x18000b58f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT>::__private_IsEnabled(void)
0x18000b594  mov     ecx, cs:dword_180025D78
0x18000b59a  test    al, al
0x18000b59c  jz      short loc_18000B5B7
0x18000b59e  test    cl, 8
0x18000b5a1  jz      short loc_18000B5B7
0x18000b5a3  call    UninitializeKeyIsoPerfCounters
0x18000b5a8  mov     ecx, cs:dword_180025D78
0x18000b5ae  and     ecx, 0FFFFFFF7h
0x18000b5b1  mov     cs:dword_180025D78, ecx
0x18000b5b7  test    cl, 2
0x18000b5ba  jz      short loc_18000B5D0
0x18000b5bc  call    UninitializeLoader
0x18000b5c1  mov     ecx, cs:dword_180025D78
0x18000b5c7  and     ecx, 0FFFFFFFDh
0x18000b5ca  mov     cs:dword_180025D78, ecx
0x18000b5d0  test    cl, 1
0x18000b5d3  jz      short loc_18000B605
0x18000b5d5  mov     eax, cs:dword_180025FFC
0x18000b5db  test    eax, eax
0x18000b5dd  jz      short loc_18000B5F6
0x18000b5df  lea     rcx, CriticalSection; CriticalSection
0x18000b5e6  call    cs:__imp_RtlDeleteCriticalSection
0x18000b5ec  mov     cs:dword_180025FFC, 0
0x18000b5f6  mov     ecx, cs:dword_180025D78
0x18000b5fc  and     ecx, 0FFFFFFFEh
0x18000b5ff  mov     cs:dword_180025D78, ecx
0x18000b605  test    cl, 4
0x18000b608  jz      short loc_18000B61E
0x18000b60a  lea     rcx, g_ResLock; CriticalSection
0x18000b611  call    cs:__imp_RtlDeleteCriticalSection
0x18000b617  and     cs:dword_180025D78, 0FFFFFFFBh
0x18000b61e  add     rsp, 28h
0x18000b622  retn
```
