# CFvePolicySettings::ReadPolicyDword(eFveGpDwSetting,ulong *,int *)

- ea: `0x18002a0cc`
- end: `0x18002a12b`
- name: `?ReadPolicyDword@CFvePolicySettings@@IEBAJW4eFveGpDwSetting@@PEAKPEAH@Z`
- size: `95`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029fb4`
- `0x18002a040`
- `0x18002a134`

## callees

- `0x180029e7c`
- `0x18002a0cc`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall CFvePolicySettings::ReadPolicyDword(__int64 a1, unsigned int a2, __int64 a3, int *a4)
{
  __int64 result; // rax
  int v8; // ecx

  result = (***(__int64 (__fastcall ****)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 8));
  if ( (_DWORD)result == -2147024894 )
  {
    result = CFvePolicySettings::GetDefaultPolicyDword(a2, a3);
    if ( (int)result < 0 )
      return result;
    v8 = 0;
  }
  else
  {
    v8 = 1;
    if ( (int)result < 0 )
      return result;
  }
  if ( a4 )
    *a4 = v8;
  return result;
}

```

## disassembly

```asm
0x18002a0cc  mov     [rsp+arg_0], rbx
0x18002a0d1  mov     [rsp+arg_8], rsi
0x18002a0d6  push    rdi
0x18002a0d7  sub     rsp, 20h
0x18002a0db  mov     rcx, [rcx+8]
0x18002a0df  mov     rbx, r9
0x18002a0e2  mov     rdi, r8
0x18002a0e5  mov     esi, edx
0x18002a0e7  mov     rax, [rcx]
0x18002a0ea  mov     rax, [rax]
0x18002a0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0f2  cmp     eax, 80070002h
0x18002a0f7  jnz     short loc_18002A10B
0x18002a0f9  mov     rdx, rdi
0x18002a0fc  mov     ecx, esi
0x18002a0fe  call    ?GetDefaultPolicyDword@CFvePolicySettings@@KAJW4eFveGpDwSetting@@PEAK@Z; CFvePolicySettings::GetDefaultPolicyDword(eFveGpDwSetting,ulong *)
0x18002a103  test    eax, eax
0x18002a105  js      short loc_18002A11B
0x18002a107  xor     ecx, ecx
0x18002a109  jmp     short loc_18002A114
0x18002a10b  mov     ecx, 1
0x18002a110  test    eax, eax
0x18002a112  js      short loc_18002A11B
0x18002a114  test    rbx, rbx
0x18002a117  jz      short loc_18002A11B
0x18002a119  mov     [rbx], ecx
0x18002a11b  mov     rbx, [rsp+28h+arg_0]
0x18002a120  mov     rsi, [rsp+28h+arg_8]
0x18002a125  add     rsp, 20h
0x18002a129  pop     rdi
0x18002a12a  retn
```
