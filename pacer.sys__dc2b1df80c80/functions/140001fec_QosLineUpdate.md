# QosLineUpdate

- ea: `0x140001fec`
- end: `0x1400020de`
- name: `QosLineUpdate`
- size: `242`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005578`

## callees

- `0x140001fec`
- `0x1400023d0`
- `0x140002484`
- `0x140011a8c`

## pseudocode

```c
__int64 __fastcall QosLineUpdate(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int updated; // edi
  char v6; // cl
  int v8; // r9d
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rax
  unsigned __int64 v13; // rdx

  updated = 0;
  v6 = 0;
  if ( a2 )
    *(_QWORD *)a1 = *a2;
  if ( a4 )
  {
    v8 = *(_DWORD *)(a4 + 24);
    if ( (((unsigned __int8)v8 ^ (unsigned __int8)(*(_DWORD *)(a1 + 208) >> 1)) & 1) != 0 )
    {
      v6 = 1;
      *(_DWORD *)(a1 + 208) ^= ((unsigned __int8)*(_DWORD *)(a1 + 208) ^ (unsigned __int8)(2 * v8)) & 2;
    }
  }
  if ( a3 && a3 != *(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 8) = a3;
    v6 = 1;
  }
  if ( !a4 )
    goto LABEL_13;
  v9 = *(_QWORD *)(a4 + 16);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_QWORD *)(a1 + 96) = v9;
    v6 = 1;
  }
  v10 = *(_DWORD *)(a4 + 8);
  if ( v10 )
  {
    updated = QosLineUpdateTotalWeight(a1, v10, *(_DWORD *)(a4 + 12), *(_DWORD *)a4, *(_DWORD *)(a4 + 4));
    if ( (updated & 0x80000000) != 0 )
      return updated;
  }
  else
  {
LABEL_13:
    if ( !v6 )
      return updated;
  }
  QosLineComputeControlInterval(a1);
  QosLineComputeBufferSizes(v11);
  v12 = *(_QWORD *)(a1 + 96);
  if ( !v12 || v12 == *(_QWORD *)(a1 + 8) )
    v13 = 0;
  else
    v13 = v12 * (unsigned __int64)*(unsigned int *)(a1 + 116) / 0xF4240;
  *(_QWORD *)(a1 + 192) = v13;
  return updated;
}

```

## disassembly

```asm
0x140001fec  mov     [rsp+arg_0], rbx
0x140001ff1  push    rdi
0x140001ff2  sub     rsp, 30h
0x140001ff6  mov     rbx, rcx
0x140001ff9  xor     edi, edi
0x140001ffb  xor     cl, cl
0x140001ffd  mov     r10, r9
0x140002000  test    rdx, rdx
0x140002003  jz      short loc_14000200B
0x140002005  mov     rax, [rdx]
0x140002008  mov     [rbx], rax
0x14000200b  test    r10, r10
0x14000200e  jz      short loc_140002025
0x140002010  mov     edx, [rbx+0D0h]
0x140002016  mov     eax, edx
0x140002018  mov     r9d, [r9+18h]
0x14000201c  shr     eax, 1
0x14000201e  xor     eax, r9d
0x140002021  test    al, 1
0x140002023  jnz     short loc_140002082
0x140002025  test    r8, r8
0x140002028  jz      short loc_140002036
0x14000202a  cmp     r8, [rbx+8]
0x14000202e  jz      short loc_140002036
0x140002030  mov     [rbx+8], r8
0x140002034  mov     cl, 1
0x140002036  test    r10, r10
0x140002039  jz      short loc_140002051
0x14000203b  mov     rdx, [r10+10h]
0x14000203f  lea     rax, [rdx-1]
0x140002043  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002047  jbe     short loc_140002097
0x140002049  mov     edx, [r10+8]
0x14000204d  test    edx, edx
0x14000204f  jnz     short loc_14000209F
0x140002051  test    cl, cl
0x140002053  jz      short loc_140002074
0x140002055  mov     rcx, rbx
0x140002058  call    QosLineComputeControlInterval
0x14000205d  call    QosLineComputeBufferSizes
0x140002062  mov     rax, [rbx+60h]
0x140002066  test    rax, rax
0x140002069  jnz     short loc_1400020BE
0x14000206b  xor     edx, edx
0x14000206d  mov     [rbx+0C0h], rdx
0x140002074  mov     rbx, [rsp+38h+arg_0]
0x140002079  mov     eax, edi
0x14000207b  add     rsp, 30h
0x14000207f  pop     rdi
0x140002080  retn
0x140002082  lea     eax, [r9+r9]
0x140002086  mov     cl, 1
0x140002088  xor     eax, edx
0x14000208a  and     eax, 2
0x14000208d  xor     eax, edx
0x14000208f  mov     [rbx+0D0h], eax
0x140002095  jmp     short loc_140002025
0x140002097  mov     [rbx+60h], rdx
0x14000209b  mov     cl, 1
0x14000209d  jmp     short loc_140002049
0x14000209f  mov     eax, [r10+4]
0x1400020a3  mov     rcx, rbx
0x1400020a6  mov     r8d, [r10+0Ch]
0x1400020aa  mov     r9d, [r10]
0x1400020ad  mov     [rsp+38h+var_18], eax
0x1400020b1  call    QosLineUpdateTotalWeight
0x1400020b6  mov     edi, eax
0x1400020b8  test    eax, eax
0x1400020ba  js      short loc_140002074
0x1400020bc  jmp     short loc_140002055
0x1400020be  cmp     rax, [rbx+8]
0x1400020c2  jz      short loc_14000206B
0x1400020c4  mov     ecx, [rbx+74h]
0x1400020c7  imul    rcx, rax
0x1400020cb  mov     rax, 431BDE82D7B634DBh
0x1400020d5  mul     rcx
0x1400020d8  shr     rdx, 12h
0x1400020dc  jmp     short loc_14000206D
```
