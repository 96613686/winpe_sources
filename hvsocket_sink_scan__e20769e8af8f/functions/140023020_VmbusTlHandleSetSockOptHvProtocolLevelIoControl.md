# VmbusTlHandleSetSockOptHvProtocolLevelIoControl

- ea: `0x140023020`
- end: `0x140023107`
- name: `VmbusTlHandleSetSockOptHvProtocolLevelIoControl`
- size: `231`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140023110`

## callees

- `0x14000975c`
- `0x140022e88`
- `0x140022f54`
- `0x140023020`

## string_xrefs

- `0x140023056`: `VmbusTlHandleSetSockOptHvProtocolLevelIoControl`

## pseudocode

```c
__int64 __fastcall VmbusTlHandleSetSockOptHvProtocolLevelIoControl(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  unsigned int v4; // ebx
  __int64 v5; // r8
  const char *v6; // rcx
  __int64 v7; // rdx
  __int64 v9; // rcx

  if ( *(_DWORD *)(a2 + 24) == 1 )
  {
    if ( *(_DWORD *)(a1 + 104) == 1 )
    {
      if ( *(_QWORD *)(a2 + 40) >= 4u )
      {
        v9 = **(unsigned int **)(a2 + 32);
        if ( (unsigned int)v9 <= 0x493E0 )
        {
          v4 = 0;
          *(_QWORD *)(a1 + 176) = -10000 * v9;
          return v4;
        }
        v5 = 3221225485LL;
        v4 = -1073741811;
        if ( (unsigned int)dword_140013058 <= 2 )
          return v4;
        v7 = 202;
      }
      else
      {
        v5 = 3221225485LL;
        v4 = -1073741811;
        if ( (unsigned int)dword_140013058 <= 2 )
          return v4;
        v7 = 193;
      }
    }
    else
    {
      v4 = -1073741808;
      if ( (unsigned int)dword_140013058 <= 2 )
        return v4;
      v5 = 3221225488LL;
      v7 = 186;
    }
    v6 = "VmbusTlHandleSetSockOptConnectTimeout";
    goto LABEL_13;
  }
  v3 = (unsigned int)(*(_DWORD *)(a2 + 24) - 4);
  if ( *(_DWORD *)(a2 + 24) == 4 )
    return (unsigned int)VmbusTlHandleSetSockOptConnectedSuspend(a1, a2, v3, a1);
  if ( *(_DWORD *)(a2 + 24) == 8 )
    return (unsigned int)VmbusTlHandleSetSockOptHighVtl(a1, a2, v3, a1);
  v4 = -1073741808;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v5 = 3221225488LL;
    v6 = "VmbusTlHandleSetSockOptHvProtocolLevelIoControl";
    v7 = 313;
LABEL_13:
    HvsocketTraceEndpointError(v6, v7, v5, a1);
  }
  return v4;
}

```

## disassembly

```asm
0x140023020  push    rbx
0x140023022  sub     rsp, 20h
0x140023026  mov     r8d, [rdx+18h]
0x14002302a  mov     r9, rcx
0x14002302d  sub     r8d, 1
0x140023031  jz      short loc_140023077
0x140023033  sub     r8d, 3
0x140023037  jz      short loc_14002306B
0x140023039  cmp     r8d, 4
0x14002303d  jz      short loc_140023064
0x14002303f  mov     eax, cs:dword_140013058
0x140023045  mov     ebx, 0C0000010h
0x14002304a  cmp     eax, 2
0x14002304d  jbe     loc_1400230FE
0x140023053  mov     r8d, ebx
0x140023056  lea     rcx, aVmbustlhandles; "VmbusTlHandleSetSockOptHvProtocolLevelI"...
0x14002305d  mov     edx, 139h
0x140023062  jmp     short loc_14002309C
0x140023064  call    VmbusTlHandleSetSockOptHighVtl
0x140023069  jmp     short loc_140023070
0x14002306b  call    VmbusTlHandleSetSockOptConnectedSuspend
0x140023070  mov     ebx, eax
0x140023072  jmp     loc_1400230FE
0x140023077  cmp     dword ptr [rcx+68h], 1
0x14002307b  jz      short loc_1400230A3
0x14002307d  mov     eax, cs:dword_140013058
0x140023083  mov     ebx, 0C0000010h
0x140023088  cmp     eax, 2
0x14002308b  jbe     short loc_1400230FE
0x14002308d  mov     r8d, ebx
0x140023090  mov     edx, 0BAh
0x140023095  lea     rcx, aVmbustlhandles_4; "VmbusTlHandleSetSockOptConnectTimeout"
0x14002309c  call    HvsocketTraceEndpointError
0x1400230a1  jmp     short loc_1400230FE
0x1400230a3  cmp     qword ptr [rdx+28h], 4
0x1400230a8  jnb     short loc_1400230C5
0x1400230aa  mov     eax, cs:dword_140013058
0x1400230b0  mov     r8d, 0C000000Dh
0x1400230b6  mov     ebx, r8d
0x1400230b9  cmp     eax, 2
0x1400230bc  jbe     short loc_1400230FE
0x1400230be  mov     edx, 0C1h
0x1400230c3  jmp     short loc_140023095
0x1400230c5  mov     rax, [rdx+20h]
0x1400230c9  mov     ecx, [rax]
0x1400230cb  cmp     ecx, 493E0h
0x1400230d1  jbe     short loc_1400230EE
0x1400230d3  mov     eax, cs:dword_140013058
0x1400230d9  mov     r8d, 0C000000Dh
0x1400230df  mov     ebx, r8d
0x1400230e2  cmp     eax, 2
0x1400230e5  jbe     short loc_1400230FE
0x1400230e7  mov     edx, 0CAh
0x1400230ec  jmp     short loc_140023095
0x1400230ee  imul    rcx, 0FFFFFFFFFFFFD8F0h
0x1400230f5  xor     ebx, ebx
0x1400230f7  mov     [r9+0B0h], rcx
0x1400230fe  mov     eax, ebx
0x140023100  add     rsp, 20h
0x140023104  pop     rbx
0x140023105  retn
```
