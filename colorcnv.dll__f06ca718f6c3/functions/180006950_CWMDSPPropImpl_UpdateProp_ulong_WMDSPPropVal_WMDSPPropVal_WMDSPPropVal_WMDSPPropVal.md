# CWMDSPPropImpl::UpdateProp(ulong,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal,WMDSPPropVal)

- ea: `0x180006950`
- end: `0x180006ab1`
- name: `?UpdateProp@CWMDSPPropImpl@@MEAAXKTWMDSPPropVal@@000@Z`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006950`
- `0x180006ab8`
- `0x180006bcc`

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
0x180006950  push    rbx
0x180006952  push    rbp
0x180006953  push    rsi
0x180006954  push    rdi
0x180006955  push    r12
0x180006957  push    r14
0x180006959  push    r15
0x18000695b  sub     rsp, 20h
0x18000695f  mov     rax, [rcx+18h]
0x180006963  mov     rbx, rcx
0x180006966  mov     r10d, edx
0x180006969  mov     r15, r9
0x18000696c  mov     rbp, r8
0x18000696f  lea     rdi, [r10+r10*8]
0x180006973  lea     r14, [rax+rdi*8]
0x180006977  mov     rax, [rcx+10h]
0x18000697b  lea     rsi, [r10+r10*2]
0x18000697f  shl     rsi, 5
0x180006983  lea     rdx, [r14+8]
0x180006987  movzx   r12d, word ptr [rsi+rax+14h]
0x18000698d  movzx   ecx, r12w
0x180006991  call    WMDSPPropValEqual
0x180006996  test    eax, eax
0x180006998  jz      loc_180006A4D
0x18000699e  mov     rax, [rbx+18h]
0x1800069a2  mov     r8, r15
0x1800069a5  lea     rbp, [rax+rdi*8]
0x1800069a9  mov     rax, [rbx+10h]
0x1800069ad  lea     rdx, [rbp+18h]
0x1800069b1  movzx   r14d, word ptr [rsi+rax+14h]
0x1800069b7  movzx   ecx, r14w
0x1800069bb  call    WMDSPPropValEqual
0x1800069c0  test    eax, eax
0x1800069c2  jz      loc_180006A6D
0x1800069c8  mov     rax, [rbx+18h]
0x1800069cc  mov     r8, [rsp+58h+arg_20]
0x1800069d4  lea     rbp, [rax+rdi*8]
0x1800069d8  mov     rax, [rbx+10h]
0x1800069dc  lea     rdx, [rbp+28h]
0x1800069e0  movzx   r14d, word ptr [rsi+rax+14h]
0x1800069e6  movzx   ecx, r14w
0x1800069ea  call    WMDSPPropValEqual
0x1800069ef  test    eax, eax
0x1800069f1  jz      short loc_180006A2B
0x1800069f3  mov     rax, [rbx+18h]
0x1800069f7  mov     r8, [rsp+58h+arg_28]
0x1800069ff  lea     rbp, [rax+rdi*8]
0x180006a03  mov     rax, [rbx+10h]
0x180006a07  lea     rdx, [rbp+38h]
0x180006a0b  movzx   esi, word ptr [rsi+rax+14h]
0x180006a10  movzx   ecx, si
0x180006a13  call    WMDSPPropValEqual
0x180006a18  test    eax, eax
0x180006a1a  jz      short loc_180006A8D
0x180006a1c  add     rsp, 20h
0x180006a20  pop     r15
0x180006a22  pop     r14
0x180006a24  pop     r12
0x180006a26  pop     rdi
0x180006a27  pop     rsi
0x180006a28  pop     rbp
0x180006a29  pop     rbx
0x180006a2a  retn
0x180006a2b  mov     r8, [rsp+58h+arg_20]
0x180006a33  lea     rdx, [rbp+28h]
0x180006a37  movzx   ecx, r14w
0x180006a3b  call    WMDSPPropValCopy
0x180006a40  mov     rax, [rbx+18h]
0x180006a44  mov     dword ptr [rax+rdi*8], 1
0x180006a4b  jmp     short loc_1800069F3
0x180006a4d  mov     r8, rbp
0x180006a50  lea     rdx, [r14+8]
0x180006a54  movzx   ecx, r12w
0x180006a58  call    WMDSPPropValCopy
0x180006a5d  mov     rax, [rbx+18h]
0x180006a61  mov     dword ptr [rax+rdi*8], 1
0x180006a68  jmp     loc_18000699E
0x180006a6d  mov     r8, r15
0x180006a70  lea     rdx, [rbp+18h]
0x180006a74  movzx   ecx, r14w
0x180006a78  call    WMDSPPropValCopy
0x180006a7d  mov     rax, [rbx+18h]
0x180006a81  mov     dword ptr [rax+rdi*8], 1
0x180006a88  jmp     loc_1800069C8
0x180006a8d  mov     r8, [rsp+58h+arg_28]
0x180006a95  lea     rdx, [rbp+38h]
0x180006a99  movzx   ecx, si
0x180006a9c  call    WMDSPPropValCopy
0x180006aa1  mov     rax, [rbx+18h]
0x180006aa5  mov     dword ptr [rax+rdi*8], 1
0x180006aac  jmp     loc_180006A1C
```
