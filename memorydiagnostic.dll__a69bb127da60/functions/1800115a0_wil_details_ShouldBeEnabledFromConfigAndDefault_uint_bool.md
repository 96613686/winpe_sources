# wil::details::ShouldBeEnabledFromConfigAndDefault(uint,bool)

- ea: `0x1800115a0`
- end: `0x1800115ef`
- name: `?ShouldBeEnabledFromConfigAndDefault@details@wil@@YA_NI_N@Z`
- size: `79`
- prototype: `bool __fastcall(wil::details *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c9c0`

## callees

- `0x1800115a0`
- `0x180023010`

## pseudocode

```c
bool __fastcall wil::details::ShouldBeEnabledFromConfigAndDefault(wil::details *this)
{
  __int64 (__fastcall *v1)(__int64, _QWORD, int *); // rax
  __int64 v2; // rax
  bool result; // al
  int v4; // [rsp+38h] [rbp+10h] BYREF

  v1 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  v4 = 0;
  result = (g_wil_details_internalGetFeatureEnabledState
         || (v1 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0)
        && (v2 = v1(59116012, 0, &v4) & 0xFFFFFF3FLL, (_DWORD)v2)
        && (_DWORD)v2 == 2;
  return result;
}

```

## disassembly

```asm
0x1800115a0  mov     byte ptr [rsp+arg_8], dl
0x1800115a4  sub     rsp, 28h
0x1800115a8  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800115af  mov     [rsp+28h+arg_8], 0
0x1800115b7  test    rax, rax
0x1800115ba  jnz     short loc_1800115C8
0x1800115bc  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800115c3  test    rax, rax
0x1800115c6  jz      short loc_1800115E8
0x1800115c8  lea     r8, [rsp+28h+arg_8]
0x1800115cd  xor     edx, edx
0x1800115cf  mov     ecx, 38609ECh
0x1800115d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115d9  and     eax, 0FFFFFF3Fh
0x1800115de  jz      short loc_1800115E8
0x1800115e0  cmp     eax, 2
0x1800115e3  setz    al
0x1800115e6  jmp     short loc_1800115EA
0x1800115e8  xor     al, al
0x1800115ea  add     rsp, 28h
0x1800115ee  retn
```
