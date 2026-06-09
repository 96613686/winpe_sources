# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x1800109e0`
- end: `0x180010b28`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800109e0`
- `0x180010c74`
- `0x180010d64`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::UpdateProp(__int64 a1, unsigned int a2, int *a3, int *a4, int *a5, int *a6)
{
  __int64 v9; // rdi
  __int64 v10; // r14
  __int64 v11; // rsi
  unsigned __int16 v12; // r12
  __int64 v13; // rbp
  unsigned __int16 v14; // r14
  __int64 v15; // rbp
  unsigned __int16 v16; // r14
  __int64 v17; // rbp
  unsigned __int16 v18; // si
  __int64 result; // rax

  v9 = 9LL * a2;
  v10 = *(_QWORD *)(a1 + 24) + 72LL * a2;
  v11 = 96LL * a2;
  v12 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v12, v10 + 8) )
  {
    WMDSPPropValCopy(v12, (OLECHAR **)(v10 + 8), a3);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v13 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v14 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v14, v13 + 24) )
  {
    WMDSPPropValCopy(v14, (OLECHAR **)(v13 + 24), a4);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v15 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v16 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  if ( !(unsigned int)WMDSPPropValEqual(v16, v15 + 40) )
  {
    WMDSPPropValCopy(v16, (OLECHAR **)(v15 + 40), a5);
    *(_DWORD *)(*(_QWORD *)(a1 + 24) + 8 * v9) = 1;
  }
  v17 = *(_QWORD *)(a1 + 24) + 8 * v9;
  v18 = *(_WORD *)(v11 + *(_QWORD *)(a1 + 16) + 20);
  result = WMDSPPropValEqual(v18, v17 + 56);
  if ( !(_DWORD)result )
  {
    WMDSPPropValCopy(v18, (OLECHAR **)(v17 + 56), a6);
    result = *(_QWORD *)(a1 + 24);
    *(_DWORD *)(result + 8 * v9) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800109e0  push    rbx
0x1800109e2  push    rbp
0x1800109e3  push    rsi
0x1800109e4  push    rdi
0x1800109e5  push    r12
0x1800109e7  push    r14
0x1800109e9  push    r15
0x1800109eb  sub     rsp, 20h
0x1800109ef  mov     rax, [rcx+18h]
0x1800109f3  mov     rbx, rcx
0x1800109f6  mov     r10d, edx
0x1800109f9  mov     r15, r9
0x1800109fc  mov     rbp, r8
0x1800109ff  lea     rdi, [r10+r10*8]
0x180010a03  lea     r14, [rax+rdi*8]
0x180010a07  mov     rax, [rcx+10h]
0x180010a0b  lea     rsi, [r10+r10*2]
0x180010a0f  shl     rsi, 5
0x180010a13  lea     rdx, [r14+8]
0x180010a17  movzx   r12d, word ptr [rsi+rax+14h]
0x180010a1d  movzx   ecx, r12w
0x180010a21  call    WMDSPPropValEqual
0x180010a26  test    eax, eax
0x180010a28  jnz     short loc_180010A45
0x180010a2a  mov     r8, rbp
0x180010a2d  lea     rdx, [r14+8]
0x180010a31  movzx   ecx, r12w
0x180010a35  call    WMDSPPropValCopy
0x180010a3a  mov     rax, [rbx+18h]
0x180010a3e  mov     dword ptr [rax+rdi*8], 1
0x180010a45  mov     rax, [rbx+18h]
0x180010a49  mov     r8, r15
0x180010a4c  lea     rbp, [rax+rdi*8]
0x180010a50  mov     rax, [rbx+10h]
0x180010a54  lea     rdx, [rbp+18h]
0x180010a58  movzx   r14d, word ptr [rsi+rax+14h]
0x180010a5e  movzx   ecx, r14w
0x180010a62  call    WMDSPPropValEqual
0x180010a67  test    eax, eax
0x180010a69  jnz     short loc_180010A86
0x180010a6b  mov     r8, r15
0x180010a6e  lea     rdx, [rbp+18h]
0x180010a72  movzx   ecx, r14w
0x180010a76  call    WMDSPPropValCopy
0x180010a7b  mov     rax, [rbx+18h]
0x180010a7f  mov     dword ptr [rax+rdi*8], 1
0x180010a86  mov     rax, [rbx+18h]
0x180010a8a  mov     r8, [rsp+58h+arg_20]
0x180010a92  lea     rbp, [rax+rdi*8]
0x180010a96  mov     rax, [rbx+10h]
0x180010a9a  lea     rdx, [rbp+28h]
0x180010a9e  movzx   r14d, word ptr [rsi+rax+14h]
0x180010aa4  movzx   ecx, r14w
0x180010aa8  call    WMDSPPropValEqual
0x180010aad  test    eax, eax
0x180010aaf  jnz     short loc_180010AD1
0x180010ab1  mov     r8, [rsp+58h+arg_20]
0x180010ab9  lea     rdx, [rbp+28h]
0x180010abd  movzx   ecx, r14w
0x180010ac1  call    WMDSPPropValCopy
0x180010ac6  mov     rax, [rbx+18h]
0x180010aca  mov     dword ptr [rax+rdi*8], 1
0x180010ad1  mov     rax, [rbx+18h]
0x180010ad5  mov     r8, [rsp+58h+arg_28]
0x180010add  lea     rbp, [rax+rdi*8]
0x180010ae1  mov     rax, [rbx+10h]
0x180010ae5  lea     rdx, [rbp+38h]
0x180010ae9  movzx   esi, word ptr [rsi+rax+14h]
0x180010aee  movzx   ecx, si
0x180010af1  call    WMDSPPropValEqual
0x180010af6  test    eax, eax
0x180010af8  jnz     short loc_180010B19
0x180010afa  mov     r8, [rsp+58h+arg_28]
0x180010b02  lea     rdx, [rbp+38h]
0x180010b06  movzx   ecx, si
0x180010b09  call    WMDSPPropValCopy
0x180010b0e  mov     rax, [rbx+18h]
0x180010b12  mov     dword ptr [rax+rdi*8], 1
0x180010b19  add     rsp, 20h
0x180010b1d  pop     r15
0x180010b1f  pop     r14
0x180010b21  pop     r12
0x180010b23  pop     rdi
0x180010b24  pop     rsi
0x180010b25  pop     rbp
0x180010b26  pop     rbx
0x180010b27  retn
```
