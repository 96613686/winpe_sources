# VmbusTlSiloCreateCallback

- ea: `0x140019960`
- end: `0x1400199fb`
- name: `VmbusTlSiloCreateCallback`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x140009cf8`
- `0x140019960`
- `0x140020124`

## import_xrefs

- `ntoskrnl!PsGetSiloContainerId` at `0x140019976`
- `ntoskrnl!PsGetSiloContainerId` at `0x140019976`

## string_xrefs

- `0x140019997`: `The host silo should already exist when hvsocket is running.`
- `0x1400199a6`: `VmbusTlSiloCreateCallback`

## pseudocode

```c
__int64 __fastcall VmbusTlSiloCreateCallback(__int64 a1)
{
  _QWORD *v1; // rbx
  __int128 *SiloContainerId; // rax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int128 v6; // [rsp+40h] [rbp-18h] BYREF
  __int64 v7; // [rsp+68h] [rbp+10h] BYREF

  v1 = VmbusProviderContext;
  v7 = 0;
  SiloContainerId = (__int128 *)PsGetSiloContainerId(a1);
  if ( SiloContainerId )
  {
    v4 = v1[22];
    v6 = *SiloContainerId;
    return (unsigned int)VmbusTlSetupPartition((__int64)v1, v4, 0, &v6, 0, 0, &v7);
  }
  else
  {
    v3 = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceError(
        "VmbusTlSiloCreateCallback",
        120,
        3221225485LL,
        "The host silo should already exist when hvsocket is running.");
  }
  return v3;
}

```

## disassembly

```asm
0x140019960  push    rbx
0x140019962  sub     rsp, 50h
0x140019966  mov     rbx, cs:VmbusProviderContext
0x14001996d  mov     [rsp+58h+arg_8], 0
0x140019976  call    cs:__imp_PsGetSiloContainerId
0x14001997d  nop     dword ptr [rax+rax+00h]
0x140019982  test    rax, rax
0x140019985  jnz     short loc_1400199B4
0x140019987  mov     eax, cs:dword_140013058
0x14001998d  mov     ebx, 0C000000Dh
0x140019992  cmp     eax, 2
0x140019995  jbe     short loc_1400199F2
0x140019997  lea     r9, aTheHostSiloSho_0; "The host silo should already exist when"...
0x14001999e  mov     r8d, ebx
0x1400199a1  mov     edx, 78h ; 'x'
0x1400199a6  lea     rcx, aVmbustlsilocre; "VmbusTlSiloCreateCallback"
0x1400199ad  call    HvsocketTraceError
0x1400199b2  jmp     short loc_1400199F2
0x1400199b4  movups  xmm0, xmmword ptr [rax]
0x1400199b7  mov     rdx, [rbx+0B0h]
0x1400199be  lea     rax, [rsp+58h+arg_8]
0x1400199c3  mov     [rsp+58h+var_28], rax
0x1400199c8  lea     r9, [rsp+58h+var_18]
0x1400199cd  mov     [rsp+58h+var_30], 0
0x1400199d6  xor     r8d, r8d
0x1400199d9  mov     rcx, rbx
0x1400199dc  mov     [rsp+58h+var_38], 0
0x1400199e5  movdqu  [rsp+58h+var_18], xmm0
0x1400199eb  call    VmbusTlSetupPartition
0x1400199f0  mov     ebx, eax
0x1400199f2  mov     eax, ebx
0x1400199f4  add     rsp, 50h
0x1400199f8  pop     rbx
0x1400199f9  retn
```
