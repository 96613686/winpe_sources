# XdrDecodeSkipBytes

- ea: `0x14000d9f0`
- end: `0x14000da7c`
- name: `XdrDecodeSkipBytes`
- size: `140`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x14000d4cc`
- `0x14000df64`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x1400124ec`
- `0x14001ea54`
- `0x14001f178`
- `0x14002a9e0`

## callees

- `0x14000d9f0`
- `0x140014c30`
- `0x1400150a4`
- `0x14001f834`
- `0x14001f860`
- `0x140038a68`

## pseudocode

```c
void __fastcall XdrDecodeSkipBytes(__int64 a1)
{
  unsigned int v1; // edi
  _DWORD *NextBufferDescriptor; // rsi
  __int64 v3; // r9
  __int64 v4; // r9
  unsigned int v5; // r10d
  unsigned int CurrentValidLengthRemaining; // eax
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 v9; // r11

  if ( *(int *)(a1 + 264) >= 0 )
  {
    v1 = 0;
    NextBufferDescriptor = *(_DWORD **)(a1 + 72);
    do
    {
      v1 += OncRpcBufMgrGetDescriptorValidLengthRemaining(NextBufferDescriptor);
      NextBufferDescriptor = (_DWORD *)OncRpcBufMgrGetNextBufferDescriptor(v3 + 32, (__int64)NextBufferDescriptor);
    }
    while ( NextBufferDescriptor );
    if ( v1 < v5 )
    {
      *(_DWORD *)(v4 + 264) = -1073741789;
    }
    else
    {
      CurrentValidLengthRemaining = OncRpcBufMgrGetCurrentValidLengthRemaining(v4 + 32);
      if ( CurrentValidLengthRemaining < (unsigned int)v8 )
      {
        XdrDecodeSkipBytesSlow(v7, (unsigned int)v8);
      }
      else
      {
        *(_QWORD *)(v9 + 64) += v8;
        XdrNextMod4Boundary(v7);
      }
    }
  }
}

```

## disassembly

```asm
0x14000d9f0  mov     [rsp+arg_0], rbx
0x14000d9f5  mov     [rsp+arg_8], rsi
0x14000d9fa  push    rdi
0x14000d9fb  sub     rsp, 20h
0x14000d9ff  cmp     dword ptr [rcx+108h], 0
0x14000da06  mov     r9, rcx
0x14000da09  mov     r10d, edx
0x14000da0c  jl      short loc_14000DA6B
0x14000da0e  mov     r11, [rcx+48h]
0x14000da12  xor     edi, edi
0x14000da14  mov     rsi, r11
0x14000da17  mov     rcx, rsi
0x14000da1a  call    OncRpcBufMgrGetDescriptorValidLengthRemaining
0x14000da1f  mov     rdx, rsi
0x14000da22  lea     rcx, [r9+20h]
0x14000da26  add     edi, eax
0x14000da28  call    OncRpcBufMgrGetNextBufferDescriptor
0x14000da2d  mov     rsi, rax
0x14000da30  test    rax, rax
0x14000da33  jnz     short loc_14000DA17
0x14000da35  cmp     edi, r10d
0x14000da38  jb      short loc_14000DA60
0x14000da3a  lea     rcx, [r9+20h]
0x14000da3e  call    OncRpcBufMgrGetCurrentValidLengthRemaining
0x14000da43  mov     rcx, r9
0x14000da46  cmp     eax, r10d
0x14000da49  jb      short loc_14000DA56
0x14000da4b  add     [r11+40h], r10
0x14000da4f  call    XdrNextMod4Boundary
0x14000da54  jmp     short loc_14000DA6B
0x14000da56  mov     edx, r10d
0x14000da59  call    XdrDecodeSkipBytesSlow
0x14000da5e  jmp     short loc_14000DA6B
0x14000da60  mov     dword ptr [r9+108h], 0C0000023h
0x14000da6b  mov     rbx, [rsp+28h+arg_0]
0x14000da70  mov     rsi, [rsp+28h+arg_8]
0x14000da75  add     rsp, 20h
0x14000da79  pop     rdi
0x14000da7a  retn
```
