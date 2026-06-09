# CStandardData::GetKernelSendParams(DCOMPOSITION_DWM_LPC_EXTRA_DATA *)

- ea: `0x1800151c0`
- end: `0x1800151ed`
- name: `?GetKernelSendParams@CStandardData@@UEBAXPEAUDCOMPOSITION_DWM_LPC_EXTRA_DATA@@@Z`
- size: `45`
- prototype: `void __fastcall(CStandardData *__hidden this, struct DCOMPOSITION_DWM_LPC_EXTRA_DATA *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800151c0`

## pseudocode

```c
void __fastcall CStandardData::GetKernelSendParams(CStandardData *this, struct DCOMPOSITION_DWM_LPC_EXTRA_DATA *a2)
{
  _QWORD *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // r8

  *(_OWORD *)a2 = 0;
  *((_QWORD *)a2 + 2) = 0;
  v2 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = v2[3];
    v4 = v2[5];
    *(_QWORD *)a2 = v2[2];
    *((_QWORD *)a2 + 1) = v3;
    *((_QWORD *)a2 + 2) = v4;
  }
}

```

## disassembly

```asm
0x1800151c0  xor     eax, eax
0x1800151c2  xorps   xmm0, xmm0
0x1800151c5  movups  xmmword ptr [rdx], xmm0
0x1800151c8  mov     [rdx+10h], rax
0x1800151cc  mov     rax, [rcx+10h]
0x1800151d0  test    rax, rax
0x1800151d3  jz      short locret_1800151EC
0x1800151d5  mov     rcx, [rax+18h]
0x1800151d9  mov     r8, [rax+28h]
0x1800151dd  mov     rax, [rax+10h]
0x1800151e1  mov     [rdx], rax
0x1800151e4  mov     [rdx+8], rcx
0x1800151e8  mov     [rdx+10h], r8
0x1800151ec  retn
```
