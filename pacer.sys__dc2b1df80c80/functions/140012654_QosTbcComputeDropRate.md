# QosTbcComputeDropRate

- ea: `0x140012654`
- end: `0x1400126ae`
- name: `QosTbcComputeDropRate`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140012410`
- `0x1400126b4`

## callees

- `0x140012654`
- `0x140012e58`

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
0x140012654  mov     [rsp+arg_0], rbx
0x140012659  push    rdi
0x14001265a  sub     rsp, 20h
0x14001265e  xor     ebx, ebx
0x140012660  mov     rdi, rcx
0x140012663  cmp     [rcx+140h], ebx
0x140012669  jz      short loc_1400126A0
0x14001266b  xor     edx, edx
0x14001266d  call    QosTbcSmoothBytesRequested
0x140012672  mov     ecx, eax
0x140012674  test    eax, eax
0x140012676  jz      short loc_1400126A0
0x140012678  imul    rax, [rdi+118h], 7FFFFFFFh
0x140012683  mov     ebx, 7FFFFFFFh
0x140012688  cqo
0x14001268a  idiv    rcx
0x14001268d  cmp     rax, rbx
0x140012690  cmovg   rax, rbx
0x140012694  xor     ecx, ecx
0x140012696  test    rax, rax
0x140012699  cmovns  rcx, rax
0x14001269d  sub     rbx, rcx
0x1400126a0  mov     eax, ebx
0x1400126a2  mov     rbx, [rsp+28h+arg_0]
0x1400126a7  add     rsp, 20h
0x1400126ab  pop     rdi
0x1400126ac  retn
```
