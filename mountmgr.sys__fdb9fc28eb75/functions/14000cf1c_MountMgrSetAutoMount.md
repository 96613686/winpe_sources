# MountMgrSetAutoMount

- ea: `0x14000cf1c`
- end: `0x14000cff2`
- name: `MountMgrSetAutoMount`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x14000cf1c`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x14000cfce`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14000cfce`

## string_xrefs

- `0x14000cfb4`: `NoAutoMount`

## pseudocode

```c
__int64 __fastcall MountMgrSetAutoMount(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  int v5; // r8d
  const WCHAR *v6; // rdx
  BOOL ValueData; // [rsp+48h] [rbp+10h] BYREF

  if ( *(_DWORD *)(*(_QWORD *)(a2 + 184) + 16LL) >= 4u )
  {
    v4 = 0;
    v5 = **(_DWORD **)(a2 + 24);
    if ( (v5 == 1) != *(_BYTE *)(a1 + 192) )
    {
      *(_BYTE *)(a1 + 192) = v5 == 1;
      v6 = *(const WCHAR **)(a1 + 272);
      ValueData = v5 != 1;
      v4 = RtlWriteRegistryValue(0, v6, L"NoAutoMount", 4u, &ValueData, 4u);
    }
  }
  else
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 331, a3, 3221225485LL);
  }
  *(_QWORD *)(a2 + 56) = 0;
  return v4;
}

```

## disassembly

```asm
0x14000cf1c  mov     [rsp+arg_0], rbx
0x14000cf21  push    rdi
0x14000cf22  sub     rsp, 30h
0x14000cf26  mov     rbx, rdx
0x14000cf29  mov     r9d, 4; ValueType
0x14000cf2f  mov     rdx, rcx
0x14000cf32  mov     rax, [rbx+0B8h]
0x14000cf39  cmp     [rax+10h], r9d
0x14000cf3d  jnb     short loc_14000CF78
0x14000cf3f  mov     edi, 0C000000Dh
0x14000cf44  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cf4b  lea     rax, WPP_GLOBAL_Control
0x14000cf52  cmp     rcx, rax
0x14000cf55  jz      loc_14000CFDC
0x14000cf5b  mov     eax, [rcx+2Ch]
0x14000cf5e  test    al, 1
0x14000cf60  jz      short loc_14000CFDC
0x14000cf62  mov     rcx, [rcx+18h]
0x14000cf66  mov     edx, 14Bh
0x14000cf6b  mov     r9d, 0C000000Dh
0x14000cf71  call    WPP_SF_L
0x14000cf76  jmp     short loc_14000CFDC
0x14000cf78  mov     rax, [rbx+18h]
0x14000cf7c  xor     ecx, ecx
0x14000cf7e  xor     edi, edi
0x14000cf80  mov     r8d, [rax]
0x14000cf83  cmp     r8d, 1
0x14000cf87  movzx   eax, byte ptr [rdx+0C0h]
0x14000cf8e  setz    cl
0x14000cf91  cmp     ecx, eax
0x14000cf93  jz      short loc_14000CFDC
0x14000cf95  cmp     r8d, 1
0x14000cf99  mov     [rsp+38h+ValueLength], r9d; ValueLength
0x14000cf9e  setz    al
0x14000cfa1  mov     [rdx+0C0h], al
0x14000cfa7  xor     eax, eax
0x14000cfa9  mov     rdx, [rdx+110h]; Path
0x14000cfb0  cmp     r8d, 1
0x14000cfb4  lea     r8, ValueName; "NoAutoMount"
0x14000cfbb  setnz   al
0x14000cfbe  xor     ecx, ecx; RelativeTo
0x14000cfc0  mov     [rsp+38h+arg_8], eax
0x14000cfc4  lea     rax, [rsp+38h+arg_8]
0x14000cfc9  mov     [rsp+38h+ValueData], rax; ValueData
0x14000cfce  call    cs:__imp_RtlWriteRegistryValue
0x14000cfd5  nop     dword ptr [rax+rax+00h]
0x14000cfda  mov     edi, eax
0x14000cfdc  mov     qword ptr [rbx+38h], 0
0x14000cfe4  mov     eax, edi
0x14000cfe6  mov     rbx, [rsp+38h+arg_0]
0x14000cfeb  add     rsp, 30h
0x14000cfef  pop     rdi
0x14000cff0  retn
```
