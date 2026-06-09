# LdrpLogDllState

- ea: `0x180029b70`
- end: `0x180029c36`
- name: `LdrpLogDllState`
- size: `198`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001dc60`
- `0x180023e20`
- `0x180028380`
- `0x180028620`
- `0x180028bd0`
- `0x1800296e0`
- `0x180029c3c`
- `0x1800693a8`
- `0x1800ac3d0`
- `0x1800be058`
- `0x1800d5d68`
- `0x1800d6508`
- `0x1800db200`
- `0x1800e60a4`
- `0x180103fb0`
- `0x180136ed4`

## callees

- `0x180029b70`
- `0x18004cef8`
- `0x1800526f0`

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
0x180029b70  mov     [rsp+arg_0], rbx
0x180029b75  mov     [rsp+arg_8], rsi
0x180029b7a  push    rdi
0x180029b7b  sub     rsp, 30h
0x180029b7f  mov     rax, gs:60h
0x180029b88  movzx   ebx, r8w
0x180029b8c  mov     rdi, rdx
0x180029b8f  mov     rsi, rcx
0x180029b92  mov     r9, [rax+90h]
0x180029b99  test    r9, r9
0x180029b9c  jnz     short loc_180029BCB
0x180029b9e  mov     eax, 7FFE0384h
0x180029ba3  cmp     byte ptr [rax], 0
0x180029ba6  jz      short loc_180029BBA
0x180029ba8  mov     rax, gs:60h
0x180029bb1  test    byte ptr [rax+378h], 4
0x180029bb8  jnz     short loc_180029BE9
0x180029bba  mov     rbx, [rsp+38h+arg_0]
0x180029bbf  mov     rsi, [rsp+38h+arg_8]
0x180029bc4  add     rsp, 30h
0x180029bc8  pop     rdi
0x180029bc9  retn
0x180029bcb  cmp     dword ptr [r9], 0
0x180029bcf  jz      short loc_180029B9E
0x180029bd1  mov     rax, gs:60h
0x180029bda  mov     rax, [rax+90h]
0x180029be1  add     rax, 22Ah
0x180029be7  jmp     short loc_180029BA3
0x180029be9  call    RtlGetCurrentServiceSessionId
0x180029bee  test    eax, eax
0x180029bf0  jz      short loc_180029C2F
0x180029bf2  mov     rax, gs:60h
0x180029bfb  mov     rcx, [rax+90h]
0x180029c02  add     rcx, 22Bh
0x180029c09  test    byte ptr [rcx], 20h
0x180029c0c  jz      short loc_180029BBA
0x180029c0e  mov     [rsp+38h+var_10], 0
0x180029c17  xor     r9d, r9d
0x180029c1a  xor     r8d, r8d
0x180029c1d  mov     [rsp+38h+var_18], rdi
0x180029c22  mov     rdx, rsi
0x180029c25  movzx   ecx, bx
0x180029c28  call    LdrpLogEtwEvent
0x180029c2d  jmp     short loc_180029BBA
0x180029c2f  mov     ecx, 7FFE0385h
0x180029c34  jmp     short loc_180029C09
```
