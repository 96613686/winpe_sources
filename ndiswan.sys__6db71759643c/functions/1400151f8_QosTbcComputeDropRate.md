# QosTbcComputeDropRate

- ea: `0x1400151f8`
- end: `0x140015252`
- name: `QosTbcComputeDropRate`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014fb4`
- `0x140015258`

## callees

- `0x1400151f8`
- `0x140015e24`

## pseudocode

```c
__int64 __fastcall QosTbcComputeDropRate(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned int v3; // eax
  __int64 v4; // rax
  int v5; // ecx

  v1 = 0;
  if ( *(_DWORD *)(a1 + 320) )
  {
    v3 = QosTbcSmoothBytesRequested(a1, 0);
    if ( v3 )
    {
      v4 = 0x7FFFFFFFLL * *(_QWORD *)(a1 + 280) / v3;
      if ( v4 > 0x7FFFFFFF )
        v4 = 0x7FFFFFFF;
      v5 = 0;
      if ( v4 >= 0 )
        v5 = v4;
      return (unsigned int)(0x7FFFFFFF - v5);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1400151f8  mov     [rsp+arg_0], rbx
0x1400151fd  push    rdi
0x1400151fe  sub     rsp, 20h
0x140015202  xor     ebx, ebx
0x140015204  mov     rdi, rcx
0x140015207  cmp     [rcx+140h], ebx
0x14001520d  jz      short loc_140015244
0x14001520f  xor     edx, edx
0x140015211  call    QosTbcSmoothBytesRequested
0x140015216  mov     ecx, eax
0x140015218  test    eax, eax
0x14001521a  jz      short loc_140015244
0x14001521c  imul    rax, [rdi+118h], 7FFFFFFFh
0x140015227  mov     ebx, 7FFFFFFFh
0x14001522c  cqo
0x14001522e  idiv    rcx
0x140015231  cmp     rax, rbx
0x140015234  cmovg   rax, rbx
0x140015238  xor     ecx, ecx
0x14001523a  test    rax, rax
0x14001523d  cmovns  rcx, rax
0x140015241  sub     rbx, rcx
0x140015244  mov     eax, ebx
0x140015246  mov     rbx, [rsp+28h+arg_0]
0x14001524b  add     rsp, 20h
0x14001524f  pop     rdi
0x140015250  retn
```
