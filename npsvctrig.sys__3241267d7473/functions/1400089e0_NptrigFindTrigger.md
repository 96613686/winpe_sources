# NptrigFindTrigger

- ea: `0x1400089e0`
- end: `0x140008a74`
- name: `NptrigFindTrigger`
- size: `148`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001010`

## callees

- `0x1400089e0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140008a54`
- `ntoskrnl!RtlCompareMemory` at `0x140008a54`

## pseudocode

```c
__int64 __fastcall NptrigFindTrigger(unsigned __int16 *a1, _QWORD *a2)
{
  _WORD *v2; // rax
  const void *v4; // rbp
  unsigned int v5; // esi
  _QWORD *v6; // rbx
  __int64 result; // rax

  v2 = (_WORD *)*((_QWORD *)a1 + 1);
  v4 = v2 + 1;
  v5 = *a1 - 2;
  v6 = (_QWORD *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
  if ( *v2 != 92 )
  {
    v4 = (const void *)*((_QWORD *)a1 + 1);
    v5 = *a1;
  }
  while ( 1 )
  {
    if ( v6 == (_QWORD *)WPP_MAIN_CB.DeviceExtension + 1 )
      return 0;
    if ( *((unsigned __int16 *)v6 + 8) == v5 && RtlCompareMemory(v4, (const void *)v6[3], v5) == v5 )
      break;
    v6 = (_QWORD *)*v6;
  }
  result = 1;
  if ( a2 )
    *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x1400089e0  push    rbx
0x1400089e2  push    rbp
0x1400089e3  push    rsi
0x1400089e4  push    r14
0x1400089e6  sub     rsp, 28h
0x1400089ea  mov     rax, [rcx+8]
0x1400089ee  mov     r14, rdx
0x1400089f1  movzx   r9d, word ptr [rcx]
0x1400089f5  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x1400089fc  mov     [rsp+48h+arg_0], rdi
0x140008a01  cmp     word ptr [rax], 5Ch ; '\'
0x140008a05  lea     rbp, [rax+2]
0x140008a09  lea     esi, [r9-2]
0x140008a0d  mov     rbx, [rbx+8]
0x140008a11  cmovnz  rbp, rax
0x140008a15  cmovnz  esi, r9d
0x140008a19  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x140008a20  add     rax, 8
0x140008a24  cmp     rbx, rax
0x140008a27  jz      short loc_140008A36
0x140008a29  movzx   eax, word ptr [rbx+10h]
0x140008a2d  cmp     eax, esi
0x140008a2f  jz      short loc_140008A48
0x140008a31  mov     rbx, [rbx]
0x140008a34  jmp     short loc_140008A19
0x140008a36  xor     eax, eax
0x140008a38  mov     rdi, [rsp+48h+arg_0]
0x140008a3d  add     rsp, 28h
0x140008a41  pop     r14
0x140008a43  pop     rsi
0x140008a44  pop     rbp
0x140008a45  pop     rbx
0x140008a46  retn
0x140008a48  mov     rdx, [rbx+18h]; Source2
0x140008a4c  mov     rcx, rbp; Source1
0x140008a4f  mov     r8d, esi; Length
0x140008a52  mov     edi, esi
0x140008a54  call    cs:__imp_RtlCompareMemory
0x140008a5b  nop     dword ptr [rax+rax+00h]
0x140008a60  cmp     rax, rdi
0x140008a63  jnz     short loc_140008A31
0x140008a65  mov     eax, 1
0x140008a6a  test    r14, r14
0x140008a6d  jz      short loc_140008A38
0x140008a6f  mov     [r14], rbx
0x140008a72  jmp     short loc_140008A38
```
