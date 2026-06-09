# MouHid_GetRegistryParameters

- ea: `0x14000d228`
- end: `0x14000d46c`
- name: `MouHid_GetRegistryParameters`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d078`

## callees

- `0x14000171c`
- `0x14000d228`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000d437`
- `ntoskrnl!ZwClose` at `0x14000d437`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d455`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d455`
- `ntoskrnl!ExAllocatePool2` at `0x14000d261`
- `ntoskrnl!ExAllocatePool2` at `0x14000d261`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14000d2d4`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14000d2d4`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000d40a`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14000d40a`

## pseudocode

```c
__int64 __fastcall MouHid_GetRegistryParameters(__int64 a1)
{
  int v2; // edx
  __int64 Pool2; // rbx
  int RegistryValues; // edi
  int v5; // eax
  int v6; // edx
  HANDLE Handle[2]; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+68h] [rbp+28h] BYREF
  int NumberOfChannels_low; // [rsp+70h] [rbp+30h] BYREF
  int v11; // [rsp+78h] [rbp+38h] BYREF

  Handle[0] = 0;
  v9 = 0;
  NumberOfChannels_low = 0;
  v11 = 0;
  Pool2 = ExAllocatePool2(256, 224, 1215655757);
  if ( Pool2 )
  {
    v5 = IoOpenDriverRegistryKey(a1, 0, 131097, 0, Handle);
    if ( v5 >= 0 )
    {
      v9 = BYTE2(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
      *(_DWORD *)(Pool2 + 8) = 288;
      *(_QWORD *)(Pool2 + 16) = L"UseOnlyMice";
      *(_DWORD *)(Pool2 + 48) = 4;
      *(_QWORD *)(Pool2 + 24) = &v9;
      *(_DWORD *)(Pool2 + 32) = 67108868;
      *(_QWORD *)(Pool2 + 40) = &v9;
      BYTE2(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = v9;
      NumberOfChannels_low = LOBYTE(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
      *(_QWORD *)(Pool2 + 72) = L"TreatAbsoluteAsRelative";
      *(_QWORD *)(Pool2 + 80) = &NumberOfChannels_low;
      *(_QWORD *)(Pool2 + 96) = &NumberOfChannels_low;
      *(_DWORD *)(Pool2 + 64) = 288;
      *(_DWORD *)(Pool2 + 104) = 4;
      *(_DWORD *)(Pool2 + 88) = 67108868;
      LOBYTE(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = NumberOfChannels_low;
      v11 = BYTE1(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels);
      *(_QWORD *)(Pool2 + 128) = L"TreatAbsolutePointerAsAbsolute";
      *(_QWORD *)(Pool2 + 136) = &v11;
      *(_DWORD *)(Pool2 + 120) = 288;
      *(_DWORD *)(Pool2 + 160) = 4;
      *(_QWORD *)(Pool2 + 152) = &v11;
      *(_DWORD *)(Pool2 + 144) = 67108868;
      BYTE1(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = v11;
      RegistryValues = RtlQueryRegistryValuesEx(0x40000000, Handle[0], Pool2, 0, 0);
      if ( RegistryValues >= 0 )
        goto LABEL_9;
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = 3;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        6,
        17,
        (__int64)WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids,
        v5);
    }
    LOWORD(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = 0;
    RegistryValues = 0;
    BYTE2(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = 0;
  }
  else
  {
    RegistryValues = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        6,
        16,
        (__int64)WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids,
        1);
    }
  }
LABEL_9:
  if ( Handle[0] )
  {
    ZwClose(Handle[0]);
    Handle[0] = 0;
  }
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0);
  return (unsigned int)RegistryValues;
}

```

## disassembly

```asm
0x14000d228  push    rbp
0x14000d22a  push    rbx
0x14000d22b  push    rdi
0x14000d22c  mov     rbp, rsp
0x14000d22f  sub     rsp, 40h
0x14000d233  mov     edx, 0E0h
0x14000d238  mov     [rbp+Handle], 0
0x14000d240  mov     rdi, rcx
0x14000d243  mov     [rbp+arg_8], 0
0x14000d24a  mov     r8d, 48756F4Dh
0x14000d250  mov     [rbp+arg_10], 0
0x14000d257  mov     [rbp+arg_18], 0
0x14000d25e  lea     ecx, [rdx+20h]
0x14000d261  call    cs:__imp_ExAllocatePool2
0x14000d268  nop     dword ptr [rax+rax+00h]
0x14000d26d  mov     rbx, rax
0x14000d270  test    rax, rax
0x14000d273  jnz     short loc_14000D2BD
0x14000d275  mov     edi, 0C0000001h
0x14000d27a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d281  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d288  jz      loc_14000D42E
0x14000d28e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d295  lea     rax, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x14000d29c  lea     r9d, [rbx+10h]
0x14000d2a0  mov     [rsp+40h+var_18], edi
0x14000d2a4  lea     r8d, [rbx+6]
0x14000d2a8  mov     [rsp+40h+var_20], rax
0x14000d2ad  mov     dl, 2
0x14000d2af  mov     rcx, [rcx+40h]
0x14000d2b3  call    WPP_RECORDER_SF_d
0x14000d2b8  jmp     loc_14000D42E
0x14000d2bd  lea     rax, [rbp+Handle]
0x14000d2c1  xor     r9d, r9d
0x14000d2c4  xor     edx, edx
0x14000d2c6  mov     [rsp+40h+var_20], rax
0x14000d2cb  mov     r8d, 20019h
0x14000d2d1  mov     rcx, rdi
0x14000d2d4  call    cs:__imp_IoOpenDriverRegistryKey
0x14000d2db  nop     dword ptr [rax+rax+00h]
0x14000d2e0  mov     ecx, eax
0x14000d2e2  test    eax, eax
0x14000d2e4  jns     short loc_14000D32B
0x14000d2e6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000d2ed  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d2f4  jz      loc_14000D41C
0x14000d2fa  mov     [rsp+40h+var_18], ecx
0x14000d2fe  lea     rax, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x14000d305  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d30c  mov     r9d, 11h
0x14000d312  mov     dl, 3
0x14000d314  mov     [rsp+40h+var_20], rax
0x14000d319  mov     rcx, [rcx+40h]
0x14000d31d  lea     r8d, [r9-0Bh]
0x14000d321  call    WPP_RECORDER_SF_d
0x14000d326  jmp     loc_14000D41C
0x14000d32b  movzx   eax, byte ptr cs:WPP_MAIN_CB.Queue+12h
0x14000d332  mov     ecx, 4
0x14000d337  mov     [rbp+arg_8], eax
0x14000d33a  mov     r8d, 120h
0x14000d340  mov     [rbx+8], r8d
0x14000d344  lea     rax, aUseonlymice; "UseOnlyMice"
0x14000d34b  mov     [rbx+10h], rax
0x14000d34f  mov     edx, 4000004h
0x14000d354  mov     [rbx+30h], ecx
0x14000d357  lea     rax, [rbp+arg_8]
0x14000d35b  mov     [rbx+18h], rax
0x14000d35f  xor     r9d, r9d
0x14000d362  mov     [rbx+20h], edx
0x14000d365  lea     rax, [rbp+arg_8]
0x14000d369  mov     [rbx+28h], rax
0x14000d36d  mov     al, byte ptr [rbp+arg_8]
0x14000d370  mov     byte ptr cs:WPP_MAIN_CB.Queue+12h, al
0x14000d376  movzx   eax, byte ptr cs:WPP_MAIN_CB.Queue+10h
0x14000d37d  mov     [rbp+arg_10], eax
0x14000d380  lea     rax, aTreatabsolutea; "TreatAbsoluteAsRelative"
0x14000d387  mov     [rbx+48h], rax
0x14000d38b  lea     rax, [rbp+arg_10]
0x14000d38f  mov     [rbx+50h], rax
0x14000d393  lea     rax, [rbp+arg_10]
0x14000d397  mov     [rbx+60h], rax
0x14000d39b  mov     [rbx+40h], r8d
0x14000d39f  mov     [rbx+68h], ecx
0x14000d3a2  mov     [rbx+58h], edx
0x14000d3a5  mov     al, byte ptr [rbp+arg_10]
0x14000d3a8  mov     byte ptr cs:WPP_MAIN_CB.Queue+10h, al
0x14000d3ae  movzx   eax, byte ptr cs:WPP_MAIN_CB.Queue+11h
0x14000d3b5  mov     [rbp+arg_18], eax
0x14000d3b8  lea     rax, aTreatabsolutep; "TreatAbsolutePointerAsAbsolute"
0x14000d3bf  mov     [rbx+80h], rax
0x14000d3c6  lea     rax, [rbp+arg_18]
0x14000d3ca  mov     [rbx+88h], rax
0x14000d3d1  lea     rax, [rbp+arg_18]
0x14000d3d5  mov     [rbx+78h], r8d
0x14000d3d9  mov     r8, rbx
0x14000d3dc  mov     [rbx+0A0h], ecx
0x14000d3e2  mov     ecx, 40000000h
0x14000d3e7  mov     [rbx+98h], rax
0x14000d3ee  mov     [rbx+90h], edx
0x14000d3f4  mov     al, byte ptr [rbp+arg_18]
0x14000d3f7  mov     rdx, [rbp+Handle]
0x14000d3fb  mov     byte ptr cs:WPP_MAIN_CB.Queue+11h, al
0x14000d401  mov     [rsp+40h+var_20], 0
0x14000d40a  call    cs:__imp_RtlQueryRegistryValuesEx
0x14000d411  nop     dword ptr [rax+rax+00h]
0x14000d416  mov     edi, eax
0x14000d418  test    eax, eax
0x14000d41a  jns     short loc_14000D42E
0x14000d41c  mov     word ptr cs:WPP_MAIN_CB.Queue+10h, 0
0x14000d425  xor     edi, edi
0x14000d427  mov     byte ptr cs:WPP_MAIN_CB.Queue+12h, 0
0x14000d42e  mov     rcx, [rbp+Handle]; Handle
0x14000d432  test    rcx, rcx
0x14000d435  jz      short loc_14000D44B
0x14000d437  call    cs:__imp_ZwClose
0x14000d43e  nop     dword ptr [rax+rax+00h]
0x14000d443  mov     [rbp+Handle], 0
0x14000d44b  test    rbx, rbx
0x14000d44e  jz      short loc_14000D461
0x14000d450  xor     edx, edx; Tag
0x14000d452  mov     rcx, rbx; P
0x14000d455  call    cs:__imp_ExFreePoolWithTag
0x14000d45c  nop     dword ptr [rax+rax+00h]
0x14000d461  mov     eax, edi
0x14000d463  add     rsp, 40h
0x14000d467  pop     rdi
0x14000d468  pop     rbx
0x14000d469  pop     rbp
0x14000d46a  retn
```
