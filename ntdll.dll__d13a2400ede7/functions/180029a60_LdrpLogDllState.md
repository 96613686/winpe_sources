# LdrpLogDllState

- ea: `0x180029a60`
- end: `0x180029b26`
- name: `LdrpLogDllState`
- size: `198`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001dc60`
- `0x180023e10`
- `0x180028270`
- `0x180028510`
- `0x180028ac0`
- `0x1800295d0`
- `0x180029b2c`
- `0x18004ff78`
- `0x180050718`
- `0x180085e5c`
- `0x1800b6f08`
- `0x1800c2338`
- `0x1800dbc80`
- `0x1800e6424`
- `0x180104d30`
- `0x1801379c4`

## callees

- `0x180029a60`
- `0x180069af8`
- `0x18006f0d0`

## pseudocode

```c
__int64 __fastcall LdrpLogDllState(int a1, __int64 a2, unsigned __int16 a3)
{
  _DWORD *SharedData; // r9
  __int64 result; // rax
  __int64 v8; // rcx

  SharedData = NtCurrentPeb()->SharedData;
  if ( SharedData && *SharedData )
    result = (__int64)NtCurrentPeb()->SharedData + 554;
  else
    result = 2147353476;
  if ( *(_BYTE *)result )
  {
    result = (__int64)NtCurrentPeb();
    if ( (*(_BYTE *)(result + 888) & 4) != 0 )
    {
      result = (__int64)RtlGetCurrentServiceSessionId();
      if ( (_DWORD)result )
      {
        result = (__int64)NtCurrentPeb();
        v8 = *(_QWORD *)(result + 144) + 555LL;
      }
      else
      {
        v8 = 2147353477;
      }
      if ( (*(_BYTE *)v8 & 0x20) != 0 )
        return LdrpLogEtwEvent(a3, a1, 0, 0, a2, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180029a60  mov     [rsp+arg_0], rbx
0x180029a65  mov     [rsp+arg_8], rsi
0x180029a6a  push    rdi
0x180029a6b  sub     rsp, 30h
0x180029a6f  mov     rax, gs:60h
0x180029a78  movzx   ebx, r8w
0x180029a7c  mov     rdi, rdx
0x180029a7f  mov     rsi, rcx
0x180029a82  mov     r9, [rax+90h]
0x180029a89  test    r9, r9
0x180029a8c  jnz     short loc_180029ABB
0x180029a8e  mov     eax, 7FFE0384h
0x180029a93  cmp     byte ptr [rax], 0
0x180029a96  jz      short loc_180029AAA
0x180029a98  mov     rax, gs:60h
0x180029aa1  test    byte ptr [rax+378h], 4
0x180029aa8  jnz     short loc_180029AD9
0x180029aaa  mov     rbx, [rsp+38h+arg_0]
0x180029aaf  mov     rsi, [rsp+38h+arg_8]
0x180029ab4  add     rsp, 30h
0x180029ab8  pop     rdi
0x180029ab9  retn
0x180029abb  cmp     dword ptr [r9], 0
0x180029abf  jz      short loc_180029A8E
0x180029ac1  mov     rax, gs:60h
0x180029aca  mov     rax, [rax+90h]
0x180029ad1  add     rax, 22Ah
0x180029ad7  jmp     short loc_180029A93
0x180029ad9  call    RtlGetCurrentServiceSessionId
0x180029ade  test    eax, eax
0x180029ae0  jz      short loc_180029B1F
0x180029ae2  mov     rax, gs:60h
0x180029aeb  mov     rcx, [rax+90h]
0x180029af2  add     rcx, 22Bh
0x180029af9  test    byte ptr [rcx], 20h
0x180029afc  jz      short loc_180029AAA
0x180029afe  mov     [rsp+38h+var_10], 0
0x180029b07  xor     r9d, r9d
0x180029b0a  xor     r8d, r8d
0x180029b0d  mov     [rsp+38h+var_18], rdi
0x180029b12  mov     rdx, rsi
0x180029b15  movzx   ecx, bx
0x180029b18  call    LdrpLogEtwEvent
0x180029b1d  jmp     short loc_180029AAA
0x180029b1f  mov     ecx, 7FFE0385h
0x180029b24  jmp     short loc_180029AF9
```
