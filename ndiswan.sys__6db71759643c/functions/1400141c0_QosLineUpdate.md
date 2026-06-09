# QosLineUpdate

- ea: `0x1400141c0`
- end: `0x140014322`
- name: `QosLineUpdate`
- size: `354`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140012258`
- `0x140013570`
- `0x140013ea0`

## callees

- `0x140013df0`
- `0x1400141c0`
- `0x140014328`

## pseudocode

```c
__int64 __fastcall QosLineUpdate(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  unsigned int updated; // esi
  char v6; // cl
  unsigned int v8; // edi
  int v9; // r9d
  __int64 v10; // rdx
  int v11; // edx
  unsigned __int64 v12; // rax
  unsigned int v13; // eax
  int v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned __int64 v17; // rdx

  updated = 0;
  v6 = 0;
  if ( a2 )
    *(_QWORD *)a1 = *a2;
  v8 = 1;
  if ( a4 )
  {
    v9 = *(_DWORD *)(a4 + 24);
    if ( (((unsigned __int8)v9 ^ (unsigned __int8)(*(_DWORD *)(a1 + 208) >> 1)) & 1) != 0 )
    {
      v6 = 1;
      *(_DWORD *)(a1 + 208) ^= ((unsigned __int8)*(_DWORD *)(a1 + 208) ^ (unsigned __int8)(2 * v9)) & 2;
    }
  }
  if ( a3 && a3 != *(_QWORD *)(a1 + 8) )
  {
    *(_QWORD *)(a1 + 8) = a3;
    v6 = 1;
  }
  if ( !a4 )
    goto LABEL_15;
  v10 = *(_QWORD *)(a4 + 16);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    *(_QWORD *)(a1 + 96) = v10;
    v6 = 1;
  }
  v11 = *(_DWORD *)(a4 + 8);
  if ( v11 )
  {
    updated = QosLineUpdateTotalWeight(a1, v11, *(_DWORD *)(a4 + 12), *(_DWORD *)a4, *(_DWORD *)(a4 + 4));
    if ( (updated & 0x80000000) != 0 )
      return updated;
  }
  else
  {
LABEL_15:
    if ( !v6 )
      return updated;
  }
  v12 = *(_QWORD *)(a1 + 8);
  if ( v12 > 0xC80000 )
  {
    if ( v12 > 0x8000000 )
    {
      v14 = 500;
      v8 = 10;
      *(_DWORD *)(a1 + 116) = 500;
      v13 = 12500;
    }
    else
    {
      *(_DWORD *)(a1 + 116) = 1000;
      v13 = 7000;
      v14 = 5000;
    }
  }
  else
  {
    v13 = 10000;
    *(_DWORD *)(a1 + 116) = 10000;
    v14 = 10000;
  }
  v15 = *(unsigned int *)(a1 + 104);
  if ( (unsigned int)v15 > 0xA )
  {
    if ( (unsigned int)v15 >= 0x1E )
    {
      v15 = v13 % v8;
      *(_DWORD *)(a1 + 116) = v13 / v8;
    }
    else
    {
      *(_DWORD *)(a1 + 116) = v14;
    }
  }
  QosLineComputeBufferSizes(a1, v15);
  v16 = *(_QWORD *)(a1 + 96);
  if ( !v16 || v16 == *(_QWORD *)(a1 + 8) )
    v17 = 0;
  else
    v17 = v16 * (unsigned __int64)*(unsigned int *)(a1 + 116) / 0xF4240;
  *(_QWORD *)(a1 + 192) = v17;
  return updated;
}

```

## disassembly

```asm
0x1400141c0  mov     [rsp+arg_0], rbx
0x1400141c5  mov     [rsp+arg_8], rsi
0x1400141ca  push    rdi
0x1400141cb  sub     rsp, 30h
0x1400141cf  mov     rbx, rcx
0x1400141d2  xor     esi, esi
0x1400141d4  xor     cl, cl
0x1400141d6  mov     r10, r9
0x1400141d9  test    rdx, rdx
0x1400141dc  jz      short loc_1400141E4
0x1400141de  mov     rax, [rdx]
0x1400141e1  mov     [rbx], rax
0x1400141e4  mov     edi, 1
0x1400141e9  test    r10, r10
0x1400141ec  jz      short loc_140014218
0x1400141ee  mov     edx, [rbx+0D0h]
0x1400141f4  mov     eax, edx
0x1400141f6  mov     r9d, [r9+18h]
0x1400141fa  shr     eax, 1
0x1400141fc  xor     eax, r9d
0x1400141ff  test    dil, al
0x140014202  jz      short loc_140014218
0x140014204  lea     eax, [r9+r9]
0x140014208  mov     cl, dil
0x14001420b  xor     eax, edx
0x14001420d  and     eax, 2
0x140014210  xor     eax, edx
0x140014212  mov     [rbx+0D0h], eax
0x140014218  test    r8, r8
0x14001421b  jz      short loc_14001422A
0x14001421d  cmp     r8, [rbx+8]
0x140014221  jz      short loc_14001422A
0x140014223  mov     [rbx+8], r8
0x140014227  mov     cl, dil
0x14001422a  test    r10, r10
0x14001422d  jz      short loc_14001426F
0x14001422f  mov     rdx, [r10+10h]
0x140014233  lea     rax, [rdx-1]
0x140014237  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001423b  ja      short loc_140014244
0x14001423d  mov     [rbx+60h], rdx
0x140014241  mov     cl, dil
0x140014244  mov     edx, [r10+8]
0x140014248  test    edx, edx
0x14001424a  jz      short loc_14001426F
0x14001424c  mov     eax, [r10+4]
0x140014250  mov     rcx, rbx
0x140014253  mov     r8d, [r10+0Ch]
0x140014257  mov     r9d, [r10]
0x14001425a  mov     [rsp+38h+var_18], eax
0x14001425e  call    QosLineUpdateTotalWeight
0x140014263  mov     esi, eax
0x140014265  test    eax, eax
0x140014267  js      loc_14001430F
0x14001426d  jmp     short loc_140014277
0x14001426f  test    cl, cl
0x140014271  jz      loc_14001430F
0x140014277  mov     rax, [rbx+8]
0x14001427b  cmp     rax, 0C80000h
0x140014281  ja      short loc_14001428F
0x140014283  mov     eax, 2710h
0x140014288  mov     [rbx+74h], eax
0x14001428b  mov     ecx, eax
0x14001428d  jmp     short loc_1400142BC
0x14001428f  cmp     rax, 8000000h
0x140014295  ja      short loc_1400142AA
0x140014297  mov     dword ptr [rbx+74h], 3E8h
0x14001429e  mov     eax, 1B58h
0x1400142a3  mov     ecx, 1388h
0x1400142a8  jmp     short loc_1400142BC
0x1400142aa  mov     ecx, 1F4h
0x1400142af  mov     edi, 0Ah
0x1400142b4  mov     [rbx+74h], ecx
0x1400142b7  mov     eax, 30D4h
0x1400142bc  mov     edx, [rbx+68h]
0x1400142bf  cmp     edx, 0Ah
0x1400142c2  jbe     short loc_1400142D5
0x1400142c4  cmp     edx, 1Eh
0x1400142c7  jnb     short loc_1400142CE
0x1400142c9  mov     [rbx+74h], ecx
0x1400142cc  jmp     short loc_1400142D5
0x1400142ce  xor     edx, edx
0x1400142d0  div     edi
0x1400142d2  mov     [rbx+74h], eax
0x1400142d5  mov     rcx, rbx
0x1400142d8  call    QosLineComputeBufferSizes
0x1400142dd  mov     rax, [rbx+60h]
0x1400142e1  test    rax, rax
0x1400142e4  jz      short loc_140014306
0x1400142e6  cmp     rax, [rbx+8]
0x1400142ea  jz      short loc_140014306
0x1400142ec  mov     ecx, [rbx+74h]
0x1400142ef  imul    rcx, rax
0x1400142f3  mov     rax, 431BDE82D7B634DBh
0x1400142fd  mul     rcx
0x140014300  shr     rdx, 12h
0x140014304  jmp     short loc_140014308
0x140014306  xor     edx, edx
0x140014308  mov     [rbx+0C0h], rdx
0x14001430f  mov     rbx, [rsp+38h+arg_0]
0x140014314  mov     eax, esi
0x140014316  mov     rsi, [rsp+38h+arg_8]
0x14001431b  add     rsp, 30h
0x14001431f  pop     rdi
0x140014320  retn
```
