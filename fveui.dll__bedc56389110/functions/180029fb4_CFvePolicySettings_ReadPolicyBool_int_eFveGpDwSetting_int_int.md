# CFvePolicySettings::ReadPolicyBool(int,eFveGpDwSetting,int *,int *)

- ea: `0x180029fb4`
- end: `0x18002a037`
- name: `?ReadPolicyBool@CFvePolicySettings@@IEBAJHW4eFveGpDwSetting@@PEAH1@Z`
- size: `131`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, int *, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002a460`
- `0x18002a650`

## callees

- `0x180029d88`
- `0x180029e7c`
- `0x180029fb4`
- `0x18002a0cc`

## pseudocode

```c
__int64 __fastcall CFvePolicySettings::ReadPolicyBool(__int64 a1, int a2, unsigned int a3, int *a4, _DWORD *a5)
{
  _DWORD *v5; // rbx
  __int64 result; // rax
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF

  v5 = a5;
  v9 = 0;
  if ( a2
    || (result = CFvePolicySettings::ReadPolicyDword(a1, a3, &v9, a5), (int)result >= 0)
    && (result = CFvePolicySettings::DwordToBool(v9, a4), (int)result < 0) )
  {
    result = CFvePolicySettings::GetDefaultPolicyDword(a3, &v9);
    if ( (int)result >= 0 )
    {
      result = CFvePolicySettings::DwordToBool(v9, a4);
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
0x180029fb4  mov     rax, rsp
0x180029fb7  mov     [rax+8], rbx
0x180029fbb  mov     [rax+18h], rsi
0x180029fbf  push    rdi
0x180029fc0  sub     rsp, 20h
0x180029fc4  mov     rbx, [rsp+28h+arg_20]
0x180029fc9  mov     rdi, r9
0x180029fcc  mov     dword ptr [rax+10h], 0
0x180029fd3  mov     esi, r8d
0x180029fd6  test    edx, edx
0x180029fd8  jnz     short loc_180029FFC
0x180029fda  mov     r9, rbx
0x180029fdd  lea     r8, [rax+10h]
0x180029fe1  mov     edx, esi
0x180029fe3  call    ?ReadPolicyDword@CFvePolicySettings@@IEBAJW4eFveGpDwSetting@@PEAKPEAH@Z; CFvePolicySettings::ReadPolicyDword(eFveGpDwSetting,ulong *,int *)
0x180029fe8  test    eax, eax
0x180029fea  js      short loc_18002A027
0x180029fec  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x180029ff0  mov     rdx, rdi; int *
0x180029ff3  call    ?DwordToBool@CFvePolicySettings@@KAJKPEAH@Z; CFvePolicySettings::DwordToBool(ulong,int *)
0x180029ff8  test    eax, eax
0x180029ffa  jns     short loc_18002A027
0x180029ffc  lea     rdx, [rsp+28h+arg_8]
0x18002a001  mov     ecx, esi
0x18002a003  call    ?GetDefaultPolicyDword@CFvePolicySettings@@KAJW4eFveGpDwSetting@@PEAK@Z; CFvePolicySettings::GetDefaultPolicyDword(eFveGpDwSetting,ulong *)
0x18002a008  test    eax, eax
0x18002a00a  js      short loc_18002A027
0x18002a00c  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x18002a010  mov     rdx, rdi; int *
0x18002a013  call    ?DwordToBool@CFvePolicySettings@@KAJKPEAH@Z; CFvePolicySettings::DwordToBool(ulong,int *)
0x18002a018  test    eax, eax
0x18002a01a  js      short loc_18002A027
0x18002a01c  test    rbx, rbx
0x18002a01f  jz      short loc_18002A027
0x18002a021  mov     dword ptr [rbx], 0
0x18002a027  mov     rbx, [rsp+28h+arg_0]
0x18002a02c  mov     rsi, [rsp+28h+arg_10]
0x18002a031  add     rsp, 20h
0x18002a035  pop     rdi
0x18002a036  retn
```
