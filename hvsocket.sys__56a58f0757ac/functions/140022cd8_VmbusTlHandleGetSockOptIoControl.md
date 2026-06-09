# VmbusTlHandleGetSockOptIoControl

- ea: `0x140022cd8`
- end: `0x140022db0`
- name: `VmbusTlHandleGetSockOptIoControl`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140019fc0`
- `0x14001b800`

## callees

- `0x14000975c`
- `0x140022b58`
- `0x140022cd8`
- `0x140022db8`

## import_xrefs

- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140022d84`
- `NDIS!NdisGetProcessObjectCompartmentId` at `0x140022d84`

## string_xrefs

- `0x140022d6b`: `VmbusTlHandleGetSockOptCompartmentId`

## pseudocode

```c
__int64 __fastcall VmbusTlHandleGetSockOptIoControl(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  unsigned int v4; // ebx
  __int64 v5; // rdx
  const char *v6; // rcx
  _DWORD *v7; // rbx

  if ( *(_DWORD *)(a2 + 20) == 1 )
    return (unsigned int)VmbusTlHandleGetSockOptHvProtocolLevelIoControl(
                           a1,
                           a2,
                           (unsigned int)(*(_DWORD *)(a2 + 20) - 1),
                           a1);
  if ( *(_DWORD *)(a2 + 20) != 0xFFFF )
  {
    v3 = 3221225488LL;
    v4 = -1073741808;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v5 = 626;
LABEL_5:
      v6 = "VmbusTlHandleGetSockOptIoControl";
LABEL_6:
      HvsocketTraceEndpointError(v6, v5, v3, a1);
      return v4;
    }
    return v4;
  }
  if ( *(_DWORD *)(a2 + 24) == 12291 )
    return (unsigned int)VmbusTlHandleGetSockOptPauseResumeAccept(a1);
  if ( *(_DWORD *)(a2 + 24) != 12292 )
  {
    v3 = 3221225488LL;
    v4 = -1073741808;
    if ( (unsigned int)dword_140013058 <= 2 )
      return v4;
    v5 = 614;
    goto LABEL_5;
  }
  if ( *(_QWORD *)(a2 + 56) == 4 )
  {
    v7 = *(_DWORD **)(a2 + 48);
    *v7 = NdisGetProcessObjectCompartmentId(*(_QWORD *)(a1 + 272));
    return 0;
  }
  v4 = -1073741811;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v3 = 3221225485LL;
    v6 = "VmbusTlHandleGetSockOptCompartmentId";
    v5 = 557;
    goto LABEL_6;
  }
  return v4;
}

```

## disassembly

```asm
0x140022cd8  push    rbx
0x140022cda  sub     rsp, 20h
0x140022cde  mov     r8d, [rdx+14h]
0x140022ce2  mov     r9, rcx
0x140022ce5  sub     r8d, 1
0x140022ce9  jz      loc_140022DA0
0x140022cef  cmp     r8d, 0FFFEh
0x140022cf6  jz      short loc_140022D26
0x140022cf8  mov     eax, cs:dword_140013058
0x140022cfe  mov     r8d, 0C0000010h
0x140022d04  mov     ebx, r8d
0x140022d07  cmp     eax, 2
0x140022d0a  jbe     loc_140022DA7
0x140022d10  mov     edx, 272h
0x140022d15  lea     rcx, aVmbustlhandleg_1; "VmbusTlHandleGetSockOptIoControl"
0x140022d1c  call    HvsocketTraceEndpointError
0x140022d21  jmp     loc_140022DA7
0x140022d26  mov     ecx, [rdx+18h]
0x140022d29  sub     ecx, 3003h
0x140022d2f  jz      short loc_140022D96
0x140022d31  cmp     ecx, 1
0x140022d34  jz      short loc_140022D51
0x140022d36  mov     eax, cs:dword_140013058
0x140022d3c  mov     r8d, 0C0000010h
0x140022d42  mov     ebx, r8d
0x140022d45  cmp     eax, 2
0x140022d48  jbe     short loc_140022DA7
0x140022d4a  mov     edx, 266h
0x140022d4f  jmp     short loc_140022D15
0x140022d51  cmp     qword ptr [rdx+38h], 4
0x140022d56  jz      short loc_140022D79
0x140022d58  mov     eax, cs:dword_140013058
0x140022d5e  mov     ebx, 0C000000Dh
0x140022d63  cmp     eax, 2
0x140022d66  jbe     short loc_140022DA7
0x140022d68  mov     r8d, ebx
0x140022d6b  lea     rcx, aVmbustlhandleg_5; "VmbusTlHandleGetSockOptCompartmentId"
0x140022d72  mov     edx, 22Dh
0x140022d77  jmp     short loc_140022D1C
0x140022d79  mov     rcx, [r9+110h]
0x140022d80  mov     rbx, [rdx+30h]
0x140022d84  call    cs:__imp_NdisGetProcessObjectCompartmentId
0x140022d8b  nop     dword ptr [rax+rax+00h]
0x140022d90  mov     [rbx], eax
0x140022d92  xor     ebx, ebx
0x140022d94  jmp     short loc_140022DA7
0x140022d96  mov     rcx, r9
0x140022d99  call    VmbusTlHandleGetSockOptPauseResumeAccept
0x140022d9e  jmp     short loc_140022DA5
0x140022da0  call    VmbusTlHandleGetSockOptHvProtocolLevelIoControl
0x140022da5  mov     ebx, eax
0x140022da7  mov     eax, ebx
0x140022da9  add     rsp, 20h
0x140022dad  pop     rbx
0x140022dae  retn
```
