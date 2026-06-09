# wil::details::ShouldBeEnabledFromConfigAndDefault(uint,bool)

- ea: `0x180011fd0`
- end: `0x18001201d`
- name: `?ShouldBeEnabledFromConfigAndDefault@details@wil@@YA_NI_N@Z`
- size: `77`
- prototype: `bool __fastcall(wil::details *__hidden this, unsigned int, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d1e4`

## callees

- `0x180011fd0`
- `0x180024010`

## pseudocode

```c
bool __fastcall wil::details::ShouldBeEnabledFromConfigAndDefault(wil::details *this)
{
  __int64 (__fastcall *v1)(__int64, _QWORD, int *); // rax
  __int64 v2; // rax
  bool result; // al
  int v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v1 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  result = (g_wil_details_internalGetFeatureEnabledState
         || (v1 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0)
        && (v2 = v1(59116012, 0, &v4) & 0xFFFFFF3FLL, (_DWORD)v2)
        && (_DWORD)v2 == 2;
  return result;
}

```

## disassembly

```asm
0x180011fd0  mov     byte ptr [rsp+arg_8], dl
0x180011fd4  sub     rsp, 28h
0x180011fd8  and     [rsp+28h+arg_8], 0
0x180011fdd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180011fe4  test    rax, rax
0x180011fe7  jnz     short loc_180011FF5
0x180011fe9  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180011ff0  test    rax, rax
0x180011ff3  jz      short loc_180012015
0x180011ff5  lea     r8, [rsp+28h+arg_8]
0x180011ffa  xor     edx, edx
0x180011ffc  mov     ecx, 38609ECh
0x180012001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012006  and     eax, 0FFFFFF3Fh
0x18001200b  jz      short loc_180012015
0x18001200d  cmp     eax, 2
0x180012010  setz    al
0x180012013  jmp     short loc_180012017
0x180012015  xor     al, al
0x180012017  add     rsp, 28h
0x18001201b  retn
```
