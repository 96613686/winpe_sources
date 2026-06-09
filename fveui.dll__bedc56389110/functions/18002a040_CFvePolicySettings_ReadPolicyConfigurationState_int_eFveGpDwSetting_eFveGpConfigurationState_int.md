# CFvePolicySettings::ReadPolicyConfigurationState(int,eFveGpDwSetting,eFveGpConfigurationState *,int *)

- ea: `0x18002a040`
- end: `0x18002a0c3`
- name: `?ReadPolicyConfigurationState@CFvePolicySettings@@IEBAJHW4eFveGpDwSetting@@PEAW4eFveGpConfigurationState@@PEAH@Z`
- size: `131`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, enum eFveGpConfigurationState *, _DWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002a5a0`
- `0x18002b390`
- `0x18002b460`

## callees

- `0x180029dac`
- `0x180029e7c`
- `0x18002a040`
- `0x18002a0cc`

## pseudocode

```c
__int64 __fastcall CFvePolicySettings::ReadPolicyConfigurationState(
        __int64 a1,
        int a2,
        unsigned int a3,
        enum eFveGpConfigurationState *a4,
        _DWORD *a5)
{
  _DWORD *v5; // rbx
  __int64 result; // rax
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF

  v5 = a5;
  v9 = 0;
  if ( a2
    || (result = CFvePolicySettings::ReadPolicyDword(a1, a3, &v9, a5), (int)result >= 0)
    && (result = CFvePolicySettings::DwordToConfigurationState(v9, a4), (int)result < 0) )
  {
    result = CFvePolicySettings::GetDefaultPolicyDword(a3, &v9);
    if ( (int)result >= 0 )
    {
      result = CFvePolicySettings::DwordToConfigurationState(v9, a4);
      if ( (int)result >= 0 )
      {
        if ( v5 )
          *v5 = 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a040  mov     rax, rsp
0x18002a043  mov     [rax+8], rbx
0x18002a047  mov     [rax+18h], rsi
0x18002a04b  push    rdi
0x18002a04c  sub     rsp, 20h
0x18002a050  mov     rbx, [rsp+28h+arg_20]
0x18002a055  mov     rdi, r9
0x18002a058  mov     dword ptr [rax+10h], 0
0x18002a05f  mov     esi, r8d
0x18002a062  test    edx, edx
0x18002a064  jnz     short loc_18002A088
0x18002a066  mov     r9, rbx
0x18002a069  lea     r8, [rax+10h]
0x18002a06d  mov     edx, esi
0x18002a06f  call    ?ReadPolicyDword@CFvePolicySettings@@IEBAJW4eFveGpDwSetting@@PEAKPEAH@Z; CFvePolicySettings::ReadPolicyDword(eFveGpDwSetting,ulong *,int *)
0x18002a074  test    eax, eax
0x18002a076  js      short loc_18002A0B3
0x18002a078  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x18002a07c  mov     rdx, rdi; enum eFveGpConfigurationState *
0x18002a07f  call    ?DwordToConfigurationState@CFvePolicySettings@@KAJKPEAW4eFveGpConfigurationState@@@Z; CFvePolicySettings::DwordToConfigurationState(ulong,eFveGpConfigurationState *)
0x18002a084  test    eax, eax
0x18002a086  jns     short loc_18002A0B3
0x18002a088  lea     rdx, [rsp+28h+arg_8]
0x18002a08d  mov     ecx, esi
0x18002a08f  call    ?GetDefaultPolicyDword@CFvePolicySettings@@KAJW4eFveGpDwSetting@@PEAK@Z; CFvePolicySettings::GetDefaultPolicyDword(eFveGpDwSetting,ulong *)
0x18002a094  test    eax, eax
0x18002a096  js      short loc_18002A0B3
0x18002a098  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x18002a09c  mov     rdx, rdi; enum eFveGpConfigurationState *
0x18002a09f  call    ?DwordToConfigurationState@CFvePolicySettings@@KAJKPEAW4eFveGpConfigurationState@@@Z; CFvePolicySettings::DwordToConfigurationState(ulong,eFveGpConfigurationState *)
0x18002a0a4  test    eax, eax
0x18002a0a6  js      short loc_18002A0B3
0x18002a0a8  test    rbx, rbx
0x18002a0ab  jz      short loc_18002A0B3
0x18002a0ad  mov     dword ptr [rbx], 0
0x18002a0b3  mov     rbx, [rsp+28h+arg_0]
0x18002a0b8  mov     rsi, [rsp+28h+arg_10]
0x18002a0bd  add     rsp, 20h
0x18002a0c1  pop     rdi
0x18002a0c2  retn
```
