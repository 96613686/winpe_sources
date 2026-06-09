# Smb2IsKnownPassthroughEcp

- ea: `0x14000a400`
- end: `0x14000a55e`
- name: `Smb2IsKnownPassthroughEcp`
- size: `350`
- prototype: `bool __fastcall(void *Source1, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007470`
- `0x1400095d0`

## callees

- `0x14000a400`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000a41e`
- `ntoskrnl!RtlCompareMemory` at `0x14000a444`
- `ntoskrnl!RtlCompareMemory` at `0x14000a46a`
- `ntoskrnl!RtlCompareMemory` at `0x14000a490`
- `ntoskrnl!RtlCompareMemory` at `0x14000a4b6`
- `ntoskrnl!RtlCompareMemory` at `0x14000a4dc`
- `ntoskrnl!RtlCompareMemory` at `0x14000a4f7`
- `ntoskrnl!RtlCompareMemory` at `0x14000a519`
- `ntoskrnl!RtlCompareMemory` at `0x14000a53b`
- `ntoskrnl!RtlCompareMemory` at `0x14000a41e`
- `ntoskrnl!RtlCompareMemory` at `0x14000a444`
- `ntoskrnl!RtlCompareMemory` at `0x14000a46a`
- `ntoskrnl!RtlCompareMemory` at `0x14000a490`
- `ntoskrnl!RtlCompareMemory` at `0x14000a4b6`
- `ntoskrnl!RtlCompareMemory` at `0x14000a4dc`
- `ntoskrnl!RtlCompareMemory` at `0x14000a4f7`
- `ntoskrnl!RtlCompareMemory` at `0x14000a519`
- `ntoskrnl!RtlCompareMemory` at `0x14000a53b`

## pseudocode

```c
bool __fastcall Smb2IsKnownPassthroughEcp(void *Source1, char a2)
{
  if ( a2 )
  {
    if ( RtlCompareMemory(Source1, RkfGuidEcpIn, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_NETWORK_APP_INSTANCE, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_NETWORK_APP_INSTANCE_VERSION, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_CSV_INITIAL_INFO, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, 0x10u) != 16
      && RtlCompareMemory(Source1, &GUID_ECP_ENABLE_REDIRECTIONGUARD, 0x10u) != 16 )
    {
      return 0;
    }
  }
  else if ( RtlCompareMemory(Source1, RkfGuidEcpIn, 0x10u) != 16
         && RtlCompareMemory(Source1, &GUID_ECP_CSV_INITIAL_INFO, 0x10u) != 16 )
  {
    return RtlCompareMemory(Source1, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, 0x10u) == 16;
  }
  return 1;
}

```

## disassembly

```asm
0x14000a400  push    rbx
0x14000a402  sub     rsp, 20h
0x14000a406  test    dl, dl
0x14000a408  mov     rbx, rcx
0x14000a40b  lea     rdx, RkfGuidEcpIn; Source2
0x14000a412  mov     r8d, 10h; Length
0x14000a418  jz      loc_14000A4F7
0x14000a41e  call    cs:__imp_RtlCompareMemory
0x14000a425  nop     dword ptr [rax+rax+00h]
0x14000a42a  cmp     rax, 10h
0x14000a42e  jz      loc_14000A555
0x14000a434  mov     r8d, 10h; Length
0x14000a43a  lea     rdx, GUID_ECP_NETWORK_APP_INSTANCE; Source2
0x14000a441  mov     rcx, rbx; Source1
0x14000a444  call    cs:__imp_RtlCompareMemory
0x14000a44b  nop     dword ptr [rax+rax+00h]
0x14000a450  cmp     rax, 10h
0x14000a454  jz      loc_14000A555
0x14000a45a  mov     r8d, 10h; Length
0x14000a460  lea     rdx, GUID_ECP_NETWORK_APP_INSTANCE_VERSION; Source2
0x14000a467  mov     rcx, rbx; Source1
0x14000a46a  call    cs:__imp_RtlCompareMemory
0x14000a471  nop     dword ptr [rax+rax+00h]
0x14000a476  cmp     rax, 10h
0x14000a47a  jz      loc_14000A555
0x14000a480  mov     r8d, 10h; Length
0x14000a486  lea     rdx, GUID_ECP_CSV_INITIAL_INFO; Source2
0x14000a48d  mov     rcx, rbx; Source1
0x14000a490  call    cs:__imp_RtlCompareMemory
0x14000a497  nop     dword ptr [rax+rax+00h]
0x14000a49c  cmp     rax, 10h
0x14000a4a0  jz      loc_14000A555
0x14000a4a6  mov     r8d, 10h; Length
0x14000a4ac  lea     rdx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; Source2
0x14000a4b3  mov     rcx, rbx; Source1
0x14000a4b6  call    cs:__imp_RtlCompareMemory
0x14000a4bd  nop     dword ptr [rax+rax+00h]
0x14000a4c2  cmp     rax, 10h
0x14000a4c6  jz      loc_14000A555
0x14000a4cc  mov     r8d, 10h; Length
0x14000a4d2  lea     rdx, GUID_ECP_ENABLE_REDIRECTIONGUARD; Source2
0x14000a4d9  mov     rcx, rbx; Source1
0x14000a4dc  call    cs:__imp_RtlCompareMemory
0x14000a4e3  nop     dword ptr [rax+rax+00h]
0x14000a4e8  cmp     rax, 10h
0x14000a4ec  jz      short loc_14000A555
0x14000a4ee  xor     al, al
0x14000a4f0  add     rsp, 20h
0x14000a4f4  pop     rbx
0x14000a4f5  retn
0x14000a4f7  call    cs:__imp_RtlCompareMemory
0x14000a4fe  nop     dword ptr [rax+rax+00h]
0x14000a503  cmp     rax, 10h
0x14000a507  jz      short loc_14000A555
0x14000a509  mov     r8d, 10h; Length
0x14000a50f  lea     rdx, GUID_ECP_CSV_INITIAL_INFO; Source2
0x14000a516  mov     rcx, rbx; Source1
0x14000a519  call    cs:__imp_RtlCompareMemory
0x14000a520  nop     dword ptr [rax+rax+00h]
0x14000a525  cmp     rax, 10h
0x14000a529  jz      short loc_14000A555
0x14000a52b  mov     r8d, 10h; Length
0x14000a531  lea     rdx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; Source2
0x14000a538  mov     rcx, rbx; Source1
0x14000a53b  call    cs:__imp_RtlCompareMemory
0x14000a542  nop     dword ptr [rax+rax+00h]
0x14000a547  cmp     rax, 10h
0x14000a54b  setz    al
0x14000a54e  add     rsp, 20h
0x14000a552  pop     rbx
0x14000a553  retn
0x14000a555  mov     al, 1
0x14000a557  add     rsp, 20h
0x14000a55b  pop     rbx
0x14000a55c  retn
```
