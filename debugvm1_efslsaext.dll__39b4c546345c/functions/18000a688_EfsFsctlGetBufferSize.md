# EfsFsctlGetBufferSize

- ea: `0x18000a688`
- end: `0x18000a726`
- name: `EfsFsctlGetBufferSize`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008bd0`
- `0x180008f88`
- `0x180009200`

## callees

- `0x180007e6c`
- `0x18000a688`

## pseudocode

```c
__int64 __fastcall EfsFsctlGetBufferSize(int *a1, unsigned int *a2)
{
  int v4; // ecx
  bool v5; // zf
  __int64 result; // rax
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  unsigned int v10; // ecx

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v4 = *a1;
  if ( *a1 == 2 )
  {
    if ( !*((_QWORD *)a1 + 1) )
      return 87;
    v5 = *((_QWORD *)a1 + 2) == 0;
  }
  else
  {
    if ( v4 != 3 )
      goto LABEL_12;
    v5 = *((_QWORD *)a1 + 1) == 0;
  }
  if ( v5 )
    return 87;
LABEL_12:
  *a2 = 0;
  v7 = v4 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      if ( v8 != 1 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        return 87;
      }
      v9 = **((_DWORD **)a1 + 1) + 15;
    }
    else
    {
      v9 = **((_DWORD **)a1 + 2) + **((_DWORD **)a1 + 1) + 71;
    }
    v10 = (v9 & 0xFFFFFFF0) + 16;
  }
  else
  {
    v10 = 16;
  }
  result = 0;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x18000a688  mov     [rsp+arg_0], rbx
0x18000a68d  push    rdi
0x18000a68e  sub     rsp, 20h
0x18000a692  mov     rdi, rdx
0x18000a695  mov     rbx, rcx
0x18000a698  test    rcx, rcx
0x18000a69b  jnz     short loc_18000A6A2
0x18000a69d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a6a2  test    rdi, rdi
0x18000a6a5  jnz     short loc_18000A6AC
0x18000a6a7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a6ac  mov     ecx, [rbx]
0x18000a6ae  cmp     ecx, 2
0x18000a6b1  jnz     short loc_18000A6C8
0x18000a6b3  cmp     qword ptr [rbx+8], 0
0x18000a6b8  jz      short loc_18000A6C1
0x18000a6ba  cmp     qword ptr [rbx+10h], 0
0x18000a6bf  jnz     short loc_18000A6D4
0x18000a6c1  mov     eax, 57h ; 'W'
0x18000a6c6  jmp     short loc_18000A71B
0x18000a6c8  cmp     ecx, 3
0x18000a6cb  jnz     short loc_18000A6D4
0x18000a6cd  cmp     qword ptr [rbx+8], 0
0x18000a6d2  jmp     short loc_18000A6BF
0x18000a6d4  mov     dword ptr [rdi], 0
0x18000a6da  sub     ecx, 1
0x18000a6dd  jz      short loc_18000A712
0x18000a6df  sub     ecx, 1
0x18000a6e2  jz      short loc_18000A6FB
0x18000a6e4  cmp     ecx, 1
0x18000a6e7  jz      short loc_18000A6F0
0x18000a6e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a6ee  jmp     short loc_18000A6C1
0x18000a6f0  mov     rax, [rbx+8]
0x18000a6f4  mov     ecx, [rax]
0x18000a6f6  add     ecx, 0Fh
0x18000a6f9  jmp     short loc_18000A70A
0x18000a6fb  mov     rcx, [rbx+8]
0x18000a6ff  mov     rax, [rbx+10h]
0x18000a703  mov     ecx, [rcx]
0x18000a705  add     ecx, 47h ; 'G'
0x18000a708  add     ecx, [rax]
0x18000a70a  and     ecx, 0FFFFFFF0h
0x18000a70d  add     ecx, 10h
0x18000a710  jmp     short loc_18000A717
0x18000a712  mov     ecx, 10h
0x18000a717  xor     eax, eax
0x18000a719  mov     [rdi], ecx
0x18000a71b  mov     rbx, [rsp+28h+arg_0]
0x18000a720  add     rsp, 20h
0x18000a724  pop     rdi
0x18000a725  retn
```
