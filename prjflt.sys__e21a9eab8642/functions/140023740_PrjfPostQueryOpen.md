# PrjfPostQueryOpen

- ea: `0x140023740`
- end: `0x1400237bd`
- name: `PrjfPostQueryOpen`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b1d0`
- `0x140023740`

## pseudocode

```c
__int64 __fastcall PrjfPostQueryOpen(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // eax

  if ( (a4 & 1) != 0 )
    return 0;
  v6 = 0;
  if ( *(int *)(a1 + 24) < 0 )
    return 2;
  v7 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 16) + 48LL) - 68);
  if ( (unsigned int)v7 > 9 || (v8 = 517, !_bittest(&v8, v7)) )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, a2, a3);
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
  v10 = *(_DWORD *)(v9 + 60);
  if ( v10 == -1879048164 )
  {
    v11 = *(_DWORD *)(v9 + 56) & 0xFFFFE9FF;
    if ( !v11 )
      v11 = 128;
    *(_DWORD *)(v9 + 56) = v11;
    return v6;
  }
  if ( v10 == -1610612702 )
    return 2;
  return v6;
}

```

## disassembly

```asm
0x140023740  mov     [rsp+arg_0], rbx
0x140023745  push    rdi
0x140023746  sub     rsp, 20h
0x14002374a  mov     rdi, rcx
0x14002374d  test    r9b, 1
0x140023751  jz      short loc_140023757
0x140023753  xor     eax, eax
0x140023755  jmp     short loc_1400237B1
0x140023757  xor     ebx, ebx
0x140023759  cmp     [rcx+18h], ebx
0x14002375c  jl      short loc_1400237AA
0x14002375e  mov     rax, [rcx+10h]
0x140023762  mov     ecx, [rax+30h]
0x140023765  add     ecx, 0FFFFFFBCh
0x140023768  cmp     ecx, 9
0x14002376b  ja      short loc_140023777
0x14002376d  mov     eax, 205h
0x140023772  bt      eax, ecx
0x140023775  jb      short loc_14002377C
0x140023777  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002377c  mov     rax, [rdi+10h]
0x140023780  mov     rcx, [rax+20h]
0x140023784  mov     eax, [rcx+3Ch]
0x140023787  cmp     eax, 9000001Ch
0x14002378c  jnz     short loc_1400237A3
0x14002378e  mov     eax, [rcx+38h]
0x140023791  mov     edx, 80h
0x140023796  and     eax, 0FFFFE9FFh
0x14002379b  cmovz   eax, edx
0x14002379e  mov     [rcx+38h], eax
0x1400237a1  jmp     short loc_1400237AF
0x1400237a3  cmp     eax, 0A0000022h
0x1400237a8  jnz     short loc_1400237AF
0x1400237aa  mov     ebx, 2
0x1400237af  mov     eax, ebx
0x1400237b1  mov     rbx, [rsp+28h+arg_0]
0x1400237b6  add     rsp, 20h
0x1400237ba  pop     rdi
0x1400237bb  retn
```
