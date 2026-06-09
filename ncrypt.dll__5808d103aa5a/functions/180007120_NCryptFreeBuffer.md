# NCryptFreeBuffer

- ea: `0x180007120`
- end: `0x1800071a7`
- name: `NCryptFreeBuffer`
- size: `135`
- prototype: `SECURITY_STATUS __stdcall(PVOID pvInput)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007120`
- `0x1800071b0`
- `0x180007234`
- `0x18000a770`
- `0x18000cb50`
- `0x180020010`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptFreeBuffer(PVOID pvInput)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  __int64 v4; // rbx
  SECURITY_STATUS v5; // ebp

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids, pvInput);
  v2 = MSCryptRemoveMemoryBuffer(KspRouterBufferList, pvInput);
  v3 = v2;
  if ( v2 )
  {
    v4 = *(_QWORD *)v2;
    v5 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v2 + 112LL))(pvInput);
    DereferenceProvider(v4);
  }
  else
  {
    v5 = 0;
    v3 = (__int64)pvInput;
  }
  MSCryptFree(v3);
  return v5;
}

```

## disassembly

```asm
0x180007120  push    rbx
0x180007122  push    rbp
0x180007123  push    rsi
0x180007124  push    rdi
0x180007125  sub     rsp, 28h
0x180007129  mov     rsi, rcx
0x18000712c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007133  lea     rax, WPP_GLOBAL_Control
0x18000713a  cmp     rcx, rax
0x18000713d  jz      short loc_18000715D
0x18000713f  test    byte ptr [rcx+1Ch], 4
0x180007143  jz      short loc_18000715D
0x180007145  mov     rcx, [rcx+10h]
0x180007149  lea     r8, WPP_9c60bc37c5d53bae82485e77e6896efe_Traceguids
0x180007150  mov     edx, 15h
0x180007155  mov     r9, rsi
0x180007158  call    WPP_SF_q
0x18000715d  mov     rdx, rsi
0x180007160  lea     rcx, KspRouterBufferList
0x180007167  call    MSCryptRemoveMemoryBuffer
0x18000716c  mov     rdi, rax
0x18000716f  test    rax, rax
0x180007172  jz      short loc_1800071A0
0x180007174  mov     rbx, [rax]
0x180007177  mov     rcx, rsi
0x18000717a  mov     rax, [rbx+70h]
0x18000717e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007183  mov     rcx, rbx
0x180007186  mov     ebp, eax
0x180007188  call    DereferenceProvider
0x18000718d  mov     rcx, rdi
0x180007190  call    MSCryptFree
0x180007195  mov     eax, ebp
0x180007197  add     rsp, 28h
0x18000719b  pop     rdi
0x18000719c  pop     rsi
0x18000719d  pop     rbp
0x18000719e  pop     rbx
0x18000719f  retn
0x1800071a0  xor     ebp, ebp
0x1800071a2  mov     rdi, rsi
0x1800071a5  jmp     short loc_18000718D
```
