# RtdsInternalUpdateCallbackWorker

- ea: `0x140009230`
- end: `0x14000932c`
- name: `RtdsInternalUpdateCallbackWorker`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140009210`

## callees

- `0x140001760`
- `0x140001780`
- `0x140001b80`
- `0x140009230`
- `0x140009340`
- `0x140009410`
- `0x140009890`

## pseudocode

```c
__int64 __fastcall RtdsInternalUpdateCallbackWorker(int a1, __int64 a2)
{
  const wchar_t *v4; // r9
  size_t v5; // rdx
  const wchar_t *v6; // rcx
  _QWORD *v7; // rax
  __int128 v9; // [rsp+20h] [rbp-28h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h] BYREF
  void (__fastcall *v11)(__int128 *); // [rsp+58h] [rbp+10h]

  *((_QWORD *)&v9 + 1) = &v9;
  *(_QWORD *)&v9 = &v9;
  v10 = 0;
  if ( a1 != *(_DWORD *)a2 )
  {
    RtdspLock(*(_QWORD *)(a2 + 48));
    v11 = *(void (__fastcall **)(__int128 *))(a2 + 24);
    if ( v11 )
    {
      v5 = *(_QWORD *)(a2 + 8);
      v6 = *(const wchar_t **)(a2 + 16);
      *(_DWORD *)a2 = a1;
      if ( (int)RtdspGetTriggerEndpoints(v6, v5, (size_t *)&v9, v4) >= 0 )
      {
        RtdspGenerateEndpointChangelist(*(_QWORD *)(a2 + 40), &v9, &v10);
        if ( (__int128 *)v10 == &v10 )
        {
          RtdspFreeEndpointList(&v9);
        }
        else
        {
          v11(&v10);
          RtdspFreeEndpointList(*(_QWORD *)(a2 + 40));
          v7 = *(_QWORD **)(a2 + 40);
          if ( (__int128 *)v9 == &v9 )
          {
            v7[1] = v7;
            *v7 = v7;
          }
          else
          {
            *(_OWORD *)v7 = v9;
            *(_QWORD *)(**(_QWORD **)(a2 + 40) + 8LL) = *(_QWORD *)(a2 + 40);
            **(_QWORD **)(*(_QWORD *)(a2 + 40) + 8LL) = *(_QWORD *)(a2 + 40);
          }
        }
      }
    }
    RtdspUnlock(*(_QWORD *)(a2 + 48));
  }
  return 0;
}

```

## disassembly

```asm
0x140009230  mov     [rsp+arg_0], rbx
0x140009235  push    rdi
0x140009236  sub     rsp, 40h
0x14000923a  lea     rax, [rsp+48h+var_28]
0x14000923f  xorps   xmm0, xmm0
0x140009242  mov     rbx, rdx
0x140009245  mov     qword ptr [rsp+48h+var_28+8], rax
0x14000924a  lea     rax, [rsp+48h+var_28]
0x14000924f  mov     edi, ecx
0x140009251  mov     qword ptr [rsp+48h+var_28], rax
0x140009256  movups  [rsp+48h+var_18], xmm0
0x14000925b  cmp     ecx, [rdx]
0x14000925d  jz      loc_14000931E
0x140009263  mov     rcx, [rdx+30h]
0x140009267  call    RtdspLock
0x14000926c  mov     rax, [rbx+18h]
0x140009270  mov     [rsp+48h+arg_8], rax
0x140009275  mov     rax, [rsp+48h+arg_8]
0x14000927a  test    rax, rax
0x14000927d  jz      loc_140009315
0x140009283  mov     rdx, [rbx+8]
0x140009287  lea     r8, [rsp+48h+var_28]
0x14000928c  mov     rcx, [rbx+10h]; pszSrc
0x140009290  mov     [rbx], edi
0x140009292  call    RtdspGetTriggerEndpoints
0x140009297  test    eax, eax
0x140009299  js      short loc_140009315
0x14000929b  mov     rcx, [rbx+28h]
0x14000929f  lea     r8, [rsp+48h+var_18]
0x1400092a4  lea     rdx, [rsp+48h+var_28]
0x1400092a9  call    RtdspGenerateEndpointChangelist
0x1400092ae  lea     rax, [rsp+48h+var_18]
0x1400092b3  cmp     qword ptr [rsp+48h+var_18], rax
0x1400092b8  jnz     short loc_1400092C6
0x1400092ba  lea     rcx, [rsp+48h+var_28]
0x1400092bf  call    RtdspFreeEndpointList
0x1400092c4  jmp     short loc_140009315
0x1400092c6  mov     rax, [rsp+48h+arg_8]
0x1400092cb  lea     rcx, [rsp+48h+var_18]
0x1400092d0  call    _guard_dispatch_icall
0x1400092d5  mov     rcx, [rbx+28h]
0x1400092d9  call    RtdspFreeEndpointList
0x1400092de  mov     rax, [rbx+28h]
0x1400092e2  lea     rcx, [rsp+48h+var_28]
0x1400092e7  cmp     qword ptr [rsp+48h+var_28], rcx
0x1400092ec  jz      short loc_14000930E
0x1400092ee  movups  xmm0, [rsp+48h+var_28]
0x1400092f3  movups  xmmword ptr [rax], xmm0
0x1400092f6  mov     rcx, [rbx+28h]
0x1400092fa  mov     rax, [rcx]
0x1400092fd  mov     [rax+8], rcx
0x140009301  mov     rcx, [rbx+28h]
0x140009305  mov     rax, [rcx+8]
0x140009309  mov     [rax], rcx
0x14000930c  jmp     short loc_140009315
0x14000930e  mov     [rax+8], rax
0x140009312  mov     [rax], rax
0x140009315  mov     rcx, [rbx+30h]
0x140009319  call    RtdspUnlock
0x14000931e  mov     rbx, [rsp+48h+arg_0]
0x140009323  xor     eax, eax
0x140009325  add     rsp, 40h
0x140009329  pop     rdi
0x14000932a  retn
```
