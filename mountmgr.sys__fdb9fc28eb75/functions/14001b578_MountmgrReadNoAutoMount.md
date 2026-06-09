# MountmgrReadNoAutoMount

- ea: `0x14001b578`
- end: `0x14001b64d`
- name: `MountmgrReadNoAutoMount`
- size: `213`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001b078`

## callees

- `0x140001ae0`
- `0x140003280`
- `0x14001b578`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001b5f0`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001b5f0`

## string_xrefs

- `0x14001b5ae`: `NoAutoMount`

## pseudocode

```c
__int64 __fastcall MountmgrReadNoAutoMount(__int64 a1)
{
  __int64 v2; // rdx
  int RegistryValues; // eax
  __int64 v4; // r8
  _QWORD v6[14]; // [rsp+30h] [rbp-19h] BYREF
  unsigned int v7; // [rsp+B0h] [rbp+67h] BYREF
  unsigned int v8; // [rsp+B8h] [rbp+6Fh] BYREF

  v7 = 0;
  v8 = 0;
  memset(v6, 0, sizeof(v6));
  v2 = *(_QWORD *)(a1 + 8);
  v6[2] = L"NoAutoMount";
  LODWORD(v6[1]) = 288;
  v6[3] = &v7;
  LODWORD(v6[4]) = 67108868;
  v6[5] = &v8;
  LODWORD(v6[6]) = 4;
  RegistryValues = RtlQueryRegistryValuesEx(0, v2, v6, 0, 0);
  if ( RegistryValues < 0 )
  {
    v7 = v8;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 359, v4, (unsigned int)RegistryValues);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14001b578  mov     [rsp-8+arg_10], rbx
0x14001b57d  push    rbp
0x14001b57e  lea     rbp, [rsp-57h]
0x14001b583  sub     rsp, 0A0h
0x14001b58a  xor     edx, edx; Val
0x14001b58c  mov     [rbp+57h+arg_0], 0
0x14001b593  mov     rbx, rcx
0x14001b596  mov     [rbp+57h+arg_8], 0
0x14001b59d  lea     rcx, [rbp+57h+var_70]; void *
0x14001b5a1  lea     r8d, [rdx+70h]; Size
0x14001b5a5  call    memset
0x14001b5aa  mov     rdx, [rbx+8]
0x14001b5ae  lea     rax, ValueName; "NoAutoMount"
0x14001b5b5  mov     [rbp+57h+var_60], rax
0x14001b5b9  lea     r8, [rbp+57h+var_70]
0x14001b5bd  lea     rax, [rbp+57h+arg_0]
0x14001b5c1  mov     [rbp+57h+var_68], 120h
0x14001b5c8  mov     [rbp+57h+var_58], rax
0x14001b5cc  xor     r9d, r9d
0x14001b5cf  lea     rax, [rbp+57h+arg_8]
0x14001b5d3  mov     [rbp+57h+var_50], 4000004h
0x14001b5da  xor     ecx, ecx
0x14001b5dc  mov     [rbp+57h+var_48], rax
0x14001b5e0  mov     [rbp+57h+var_40], 4
0x14001b5e7  mov     [rsp+0A0h+var_80], 0
0x14001b5f0  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001b5f7  nop     dword ptr [rax+rax+00h]
0x14001b5fc  test    eax, eax
0x14001b5fe  jns     short loc_14001B638
0x14001b600  mov     ecx, [rbp+57h+arg_8]
0x14001b603  mov     [rbp+57h+arg_0], ecx
0x14001b606  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b60d  lea     rdx, WPP_GLOBAL_Control
0x14001b614  cmp     rcx, rdx
0x14001b617  jz      short loc_14001B638
0x14001b619  mov     edx, [rcx+2Ch]
0x14001b61c  test    dl, 1
0x14001b61f  jz      short loc_14001B638
0x14001b621  cmp     byte ptr [rcx+29h], 1
0x14001b625  jb      short loc_14001B638
0x14001b627  mov     rcx, [rcx+18h]
0x14001b62b  mov     edx, 167h
0x14001b630  mov     r9d, eax
0x14001b633  call    WPP_SF_L
0x14001b638  mov     eax, [rbp+57h+arg_0]
0x14001b63b  mov     rbx, [rsp+0A0h+arg_10]
0x14001b643  add     rsp, 0A0h
0x14001b64a  pop     rbp
0x14001b64b  retn
```
