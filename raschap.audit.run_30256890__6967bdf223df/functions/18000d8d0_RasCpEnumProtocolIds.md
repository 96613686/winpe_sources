# RasCpEnumProtocolIds

- ea: `0x18000d8d0`
- end: `0x18000d923`
- name: `RasCpEnumProtocolIds`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006a20`
- `0x18000d8d0`

## pseudocode

```c
__int64 __fastcall RasCpEnumProtocolIds(_DWORD *a1, _DWORD *a2)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_d3ccaec7459834abcb1c6432c7781bd4_Traceguids);
  *a1 = 49699;
  result = 0;
  *a2 = 1;
  return result;
}

```

## disassembly

```asm
0x18000d8d0  mov     [rsp+arg_0], rbx
0x18000d8d5  push    rdi
0x18000d8d6  sub     rsp, 20h
0x18000d8da  mov     rdi, rdx
0x18000d8dd  mov     rbx, rcx
0x18000d8e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8e7  lea     rax, WPP_GLOBAL_Control
0x18000d8ee  cmp     rcx, rax
0x18000d8f1  jnz     short loc_18000D90C
0x18000d8f3  mov     dword ptr [rbx], 0C223h
0x18000d8f9  xor     eax, eax
0x18000d8fb  mov     rbx, [rsp+28h+arg_0]
0x18000d900  mov     dword ptr [rdi], 1
0x18000d906  add     rsp, 20h
0x18000d90a  pop     rdi
0x18000d90b  retn
0x18000d90c  mov     rcx, [rcx+10h]
0x18000d910  lea     r8, WPP_d3ccaec7459834abcb1c6432c7781bd4_Traceguids
0x18000d917  mov     edx, 0Eh
0x18000d91c  call    WPP_SF_
0x18000d921  jmp     short loc_18000D8F3
```
