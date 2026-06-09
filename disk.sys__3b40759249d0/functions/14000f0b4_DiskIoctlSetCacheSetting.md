# DiskIoctlSetCacheSetting

- ea: `0x14000f0b4`
- end: `0x14000f190`
- name: `DiskIoctlSetCacheSetting`
- size: `220`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400014a0`

## callees

- `0x14000f0b4`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000f0d1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000f0d1`
- `CLASSPNP!ClassSetDeviceParameter` at `0x14000f16a`
- `CLASSPNP!ClassSetDeviceParameter` at `0x14000f16a`

## string_xrefs

- `0x14000f159`: `CacheIsPowerProtected`

## pseudocode

```c
__int64 __fastcall DiskIoctlSetCacheSetting(__int64 a1, __int64 a2)
{
  struct _FUNCTIONAL_DEVICE_EXTENSION *v2; // rbx
  __int64 v4; // rsi
  unsigned int v6; // edi
  __int64 v7; // rax
  bool v8; // zf
  USHORT DeviceFlags; // ax
  char v10; // cl
  USHORT v11; // ax
  ULONG v12; // r9d

  v2 = *(struct _FUNCTIONAL_DEVICE_EXTENSION **)(a1 + 64);
  v4 = *(_QWORD *)(a2 + 184);
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( *(_DWORD *)(v4 + 16) >= 0xCu )
  {
    v7 = *(_QWORD *)(a2 + 24);
    if ( *(_DWORD *)v7 == 12 )
    {
      v6 = 0;
      v8 = *(_BYTE *)(v7 + 8) == 0;
      DeviceFlags = v2->DeviceFlags;
      v10 = 1;
      if ( v8 )
      {
        v11 = DeviceFlags & 0xFFEF;
        v12 = 0;
      }
      else
      {
        v11 = DeviceFlags | 0x10;
        v12 = 1;
      }
      v2->DeviceFlags = v11;
      if ( (v2->DeviceFlags & 1) == 0 || (v2->DeviceFlags & 0x10) != 0 || (v2->ScanForSpecialFlags & 0x80u) != 0 )
        v10 = 0;
      v2->CdbForceUnitAccess = v10;
      ClassSetDeviceParameter(v2, (PWSTR)L"Disk", (PWSTR)L"CacheIsPowerProtected", v12);
    }
    else
    {
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    return (unsigned int)-1073741820;
  }
  return v6;
}

```

## disassembly

```asm
0x14000f0b4  mov     [rsp+arg_0], rbx
0x14000f0b9  mov     [rsp+arg_8], rsi
0x14000f0be  push    rdi
0x14000f0bf  sub     rsp, 20h
0x14000f0c3  mov     rbx, [rcx+40h]
0x14000f0c7  mov     rdi, rdx
0x14000f0ca  mov     rsi, [rdx+0B8h]
0x14000f0d1  call    cs:__imp_KeGetCurrentIrql
0x14000f0d8  nop     dword ptr [rax+rax+00h]
0x14000f0dd  cmp     al, 2
0x14000f0df  jb      short loc_14000F0EB
0x14000f0e1  mov     eax, 0C0000148h
0x14000f0e6  jmp     loc_14000F17F
0x14000f0eb  cmp     dword ptr [rsi+10h], 0Ch
0x14000f0ef  jnb     short loc_14000F0FB
0x14000f0f1  mov     edi, 0C0000004h
0x14000f0f6  jmp     loc_14000F17D
0x14000f0fb  mov     rax, [rdi+18h]
0x14000f0ff  cmp     dword ptr [rax], 0Ch
0x14000f102  jnz     short loc_14000F178
0x14000f104  xor     edi, edi
0x14000f106  cmp     [rax+8], dil
0x14000f10a  movzx   eax, word ptr [rbx+280h]
0x14000f111  lea     ecx, [rdi+1]
0x14000f114  jz      short loc_14000F11F
0x14000f116  or      ax, 10h
0x14000f11a  mov     r9d, ecx
0x14000f11d  jmp     short loc_14000F12A
0x14000f11f  mov     edx, 0FFEFh
0x14000f124  and     ax, dx
0x14000f127  xor     r9d, r9d; ParameterValue
0x14000f12a  mov     [rbx+280h], ax
0x14000f131  movzx   eax, word ptr [rbx+280h]
0x14000f138  test    cl, al
0x14000f13a  jz      short loc_14000F151
0x14000f13c  movzx   eax, word ptr [rbx+280h]
0x14000f143  test    al, 10h
0x14000f145  jnz     short loc_14000F151
0x14000f147  mov     eax, [rbx+36Ch]
0x14000f14d  test    al, al
0x14000f14f  jns     short loc_14000F153
0x14000f151  xor     cl, cl
0x14000f153  mov     [rbx+283h], cl
0x14000f159  lea     r8, aCacheispowerpr; "CacheIsPowerProtected"
0x14000f160  mov     rcx, rbx; FdoExtension
0x14000f163  lea     rdx, SubkeyName; "Disk"
0x14000f16a  call    cs:__imp_ClassSetDeviceParameter
0x14000f171  nop     dword ptr [rax+rax+00h]
0x14000f176  jmp     short loc_14000F17D
0x14000f178  mov     edi, 0C000000Dh
0x14000f17d  mov     eax, edi
0x14000f17f  mov     rbx, [rsp+28h+arg_0]
0x14000f184  mov     rsi, [rsp+28h+arg_8]
0x14000f189  add     rsp, 20h
0x14000f18d  pop     rdi
0x14000f18e  retn
```
