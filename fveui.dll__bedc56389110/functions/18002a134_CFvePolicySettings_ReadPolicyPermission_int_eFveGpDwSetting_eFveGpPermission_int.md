# CFvePolicySettings::ReadPolicyPermission(int,eFveGpDwSetting,eFveGpPermission *,int *)

- ea: `0x18002a134`
- end: `0x18002a1b7`
- name: `?ReadPolicyPermission@CFvePolicySettings@@IEBAJHW4eFveGpDwSetting@@PEAW4eFveGpPermission@@PEAH@Z`
- size: `131`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, enum eFveGpPermission *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b510`
- `0x18002b5e0`

## callees

- `0x180029ddc`
- `0x180029e7c`
- `0x18002a0cc`
- `0x18002a134`

## pseudocode

```c
__int64 __fastcall CFvePolicySettings::ReadPolicyPermission(
        __int64 a1,
        int a2,
        unsigned int a3,
        enum eFveGpPermission *a4,
        int *a5)
{
  int *v5; // rbx
  __int64 result; // rax
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF

  v5 = a5;
  v9 = 0;
  if ( a2
    || (result = CFvePolicySettings::ReadPolicyDword(a1, a3, (__int64)&v9, a5), (int)result >= 0)
    && (result = CFvePolicySettings::DwordToPermission(v9, a4), (int)result < 0) )
  {
    result = CFvePolicySettings::GetDefaultPolicyDword(a3, &v9);
    if ( (int)result >= 0 )
    {
      result = CFvePolicySettings::DwordToPermission(v9, a4);
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
0x18002a134  mov     rax, rsp
0x18002a137  mov     [rax+8], rbx
0x18002a13b  mov     [rax+18h], rsi
0x18002a13f  push    rdi
0x18002a140  sub     rsp, 20h
0x18002a144  mov     rbx, [rsp+28h+arg_20]
0x18002a149  mov     rdi, r9
0x18002a14c  mov     dword ptr [rax+10h], 0
0x18002a153  mov     esi, r8d
0x18002a156  test    edx, edx
0x18002a158  jnz     short loc_18002A17C
0x18002a15a  mov     r9, rbx
0x18002a15d  lea     r8, [rax+10h]
0x18002a161  mov     edx, esi
0x18002a163  call    ?ReadPolicyDword@CFvePolicySettings@@IEBAJW4eFveGpDwSetting@@PEAKPEAH@Z; CFvePolicySettings::ReadPolicyDword(eFveGpDwSetting,ulong *,int *)
0x18002a168  test    eax, eax
0x18002a16a  js      short loc_18002A1A7
0x18002a16c  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x18002a170  mov     rdx, rdi; enum eFveGpPermission *
0x18002a173  call    ?DwordToPermission@CFvePolicySettings@@KAJKPEAW4eFveGpPermission@@@Z; CFvePolicySettings::DwordToPermission(ulong,eFveGpPermission *)
0x18002a178  test    eax, eax
0x18002a17a  jns     short loc_18002A1A7
0x18002a17c  lea     rdx, [rsp+28h+arg_8]
0x18002a181  mov     ecx, esi
0x18002a183  call    ?GetDefaultPolicyDword@CFvePolicySettings@@KAJW4eFveGpDwSetting@@PEAK@Z; CFvePolicySettings::GetDefaultPolicyDword(eFveGpDwSetting,ulong *)
0x18002a188  test    eax, eax
0x18002a18a  js      short loc_18002A1A7
0x18002a18c  mov     ecx, [rsp+28h+arg_8]; unsigned int
0x18002a190  mov     rdx, rdi; enum eFveGpPermission *
0x18002a193  call    ?DwordToPermission@CFvePolicySettings@@KAJKPEAW4eFveGpPermission@@@Z; CFvePolicySettings::DwordToPermission(ulong,eFveGpPermission *)
0x18002a198  test    eax, eax
0x18002a19a  js      short loc_18002A1A7
0x18002a19c  test    rbx, rbx
0x18002a19f  jz      short loc_18002A1A7
0x18002a1a1  mov     dword ptr [rbx], 0
0x18002a1a7  mov     rbx, [rsp+28h+arg_0]
0x18002a1ac  mov     rsi, [rsp+28h+arg_10]
0x18002a1b1  add     rsp, 20h
0x18002a1b5  pop     rdi
0x18002a1b6  retn
```
