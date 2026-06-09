# vComputeSimulatedGLYPHDATA

- ea: `0x140048754`
- end: `0x14004890f`
- name: `vComputeSimulatedGLYPHDATA`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140047aa8`

## callees

- `0x140048754`
- `0x140048918`

## pseudocode

```c
__int64 __fastcall vComputeSimulatedGLYPHDATA(
        __int64 a1,
        unsigned __int64 a2,
        int a3,
        unsigned int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8)
{
  int v8; // r11d
  unsigned int v9; // edi
  int v10; // r14d
  int v11; // r10d
  unsigned __int64 v14; // r15
  unsigned __int64 i; // rsi
  unsigned __int64 j; // rsi
  int v17; // edx
  int v18; // r10d
  int v19; // r8d
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // edx
  __int64 result; // rax

  v8 = 0;
  v9 = a4;
  v10 = 0;
  v11 = a3;
  if ( a2 )
  {
    v14 = a4 + a2;
    for ( i = a2; i < v14; ++i )
    {
      if ( (unsigned int)bNonZeroRow(i, v9) )
      {
        v10 = i - a2;
        goto LABEL_7;
      }
    }
    if ( i == v14 )
      goto LABEL_12;
LABEL_7:
    for ( j = a2 + v9 - 1; j >= a2; --j )
    {
      if ( (unsigned int)bNonZeroRow(j, v9) )
      {
        v8 = j - a2 + 1;
        break;
      }
    }
  }
LABEL_12:
  v17 = a5;
  if ( a7 != 1 )
  {
    v10 *= a7;
    v8 *= a7;
    v9 *= a7;
    v17 = a7 * a5;
  }
  v18 = a6 * v11;
  v19 = v8;
  *(_QWORD *)a1 = 0;
  if ( v10 == v8 )
    v8 = a7 * v9;
  v20 = 0;
  if ( v10 != v19 )
    v20 = v10;
  *(_DWORD *)(a1 + 36) = v20 - v17;
  *(_DWORD *)(a1 + 44) = v8 - v17;
  *(_DWORD *)(a1 + 28) = 16 * v17 - 16 * v8;
  *(_DWORD *)(a1 + 24) = 16 * v17 - 16 * v20;
  v21 = *(_DWORD *)(a8 + 12) & 0x6000;
  switch ( v21 )
  {
    case 0:
      v22 = v18;
LABEL_20:
      v23 = v18;
      break;
    case 8192:
      v23 = v18 + 1;
      v22 = v18 + 1;
      break;
    case 16384:
      v22 = v18 + ((v9 - 1) >> 1);
      goto LABEL_20;
    case 24576:
      v23 = v18 + 1;
      v22 = v18 + ((v9 + 1) >> 1);
      break;
    default:
      v23 = 0;
      v22 = 1;
      break;
  }
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  if ( !v18 )
    v22 = 1;
  *(_DWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = v22;
  *(_DWORD *)(a1 + 16) = 0;
  result = 16 * (v23 & (unsigned int)-(v18 != 0));
  *(_DWORD *)(a1 + 20) = 16 * v22;
  *(_DWORD *)(a1 + 12) = result;
  *(_DWORD *)(a1 + 52) = result;
  return result;
}

```

## disassembly

```asm
0x140048754  push    rbx
0x140048756  push    rbp
0x140048757  push    rsi
0x140048758  push    rdi
0x140048759  push    r13
0x14004875b  push    r14
0x14004875d  push    r15
0x14004875f  sub     rsp, 20h
0x140048763  xor     r11d, r11d
0x140048766  mov     edi, r9d
0x140048769  xor     r14d, r14d
0x14004876c  mov     r10d, r8d
0x14004876f  mov     rbp, rdx
0x140048772  mov     rbx, rcx
0x140048775  lea     r13d, [r11+1]
0x140048779  test    rdx, rdx
0x14004877c  jz      short loc_1400487D6
0x14004877e  add     r8d, 7
0x140048782  lea     r15, [rdi+rdx]
0x140048786  shr     r8d, 3
0x14004878a  mov     rsi, rdx
0x14004878d  cmp     rsi, r15
0x140048790  jnb     loc_1400488BD
0x140048796  mov     edx, edi
0x140048798  mov     rcx, rsi
0x14004879b  call    bNonZeroRow
0x1400487a0  test    eax, eax
0x1400487a2  jnz     short loc_1400487A9
0x1400487a4  add     rsi, r13
0x1400487a7  jmp     short loc_14004878D
0x1400487a9  mov     r14d, esi
0x1400487ac  sub     r14d, ebp
0x1400487af  lea     esi, [rdi-1]
0x1400487b2  add     rsi, rbp
0x1400487b5  cmp     rsi, rbp
0x1400487b8  jb      short loc_1400487D6
0x1400487ba  mov     edx, edi
0x1400487bc  mov     rcx, rsi
0x1400487bf  call    bNonZeroRow
0x1400487c4  test    eax, eax
0x1400487c6  jnz     short loc_1400487CD
0x1400487c8  sub     rsi, r13
0x1400487cb  jmp     short loc_1400487B5
0x1400487cd  mov     r11d, esi
0x1400487d0  sub     r11d, ebp
0x1400487d3  add     r11d, r13d
0x1400487d6  mov     eax, [rsp+58h+arg_30]
0x1400487dd  mov     edx, [rsp+58h+arg_20]
0x1400487e4  cmp     eax, r13d
0x1400487e7  jnz     loc_1400488AA
0x1400487ed  imul    r10d, [rsp+58h+arg_28]
0x1400487f6  mov     r8d, r11d
0x1400487f9  mov     qword ptr [rbx], 0
0x140048800  cmp     r14d, r11d
0x140048803  jz      loc_14004889E
0x140048809  xor     ecx, ecx
0x14004880b  cmp     r14d, r8d
0x14004880e  cmovnz  ecx, r14d
0x140048812  mov     eax, ecx
0x140048814  shl     ecx, 4
0x140048817  sub     eax, edx
0x140048819  mov     [rbx+24h], eax
0x14004881c  mov     eax, r11d
0x14004881f  sub     eax, edx
0x140048821  shl     r11d, 4
0x140048825  mov     [rbx+2Ch], eax
0x140048828  shl     edx, 4
0x14004882b  mov     eax, edx
0x14004882d  sub     edx, r11d
0x140048830  sub     eax, ecx
0x140048832  mov     [rbx+1Ch], edx
0x140048835  mov     [rbx+18h], eax
0x140048838  mov     rax, [rsp+58h+arg_38]
0x140048840  mov     ecx, [rax+0Ch]
0x140048843  mov     eax, 6000h
0x140048848  and     ecx, eax
0x14004884a  jnz     short loc_1400488C8
0x14004884c  mov     ecx, r10d
0x14004884f  mov     edx, r10d
0x140048852  test    r10d, r10d
0x140048855  mov     dword ptr [rbx+30h], 0
0x14004885c  mov     qword ptr [rbx+38h], 0
0x140048864  cmovz   ecx, r13d
0x140048868  mov     dword ptr [rbx+20h], 0
0x14004886f  neg     r10d
0x140048872  mov     [rbx+28h], ecx
0x140048875  mov     dword ptr [rbx+10h], 0
0x14004887c  sbb     eax, eax
0x14004887e  and     eax, edx
0x140048880  shl     eax, 4
0x140048883  shl     ecx, 4
0x140048886  mov     [rbx+14h], ecx
0x140048889  mov     [rbx+0Ch], eax
0x14004888c  mov     [rbx+34h], eax
0x14004888f  add     rsp, 20h
0x140048893  pop     r15
0x140048895  pop     r14
0x140048897  pop     r13
0x140048899  pop     rdi
0x14004889a  pop     rsi
0x14004889b  pop     rbp
0x14004889c  pop     rbx
0x14004889d  retn
0x14004889e  mov     r11d, edi
0x1400488a1  imul    r11d, eax
0x1400488a5  jmp     loc_140048809
0x1400488aa  imul    r14d, eax
0x1400488ae  imul    r11d, eax
0x1400488b2  imul    edi, eax
0x1400488b5  imul    edx, eax
0x1400488b8  jmp     loc_1400487ED
0x1400488bd  jnz     loc_1400487AF
0x1400488c3  jmp     loc_1400487D6
0x1400488c8  cmp     ecx, 2000h
0x1400488ce  jz      short loc_140048904
0x1400488d0  cmp     ecx, 4000h
0x1400488d6  jz      short loc_1400488F7
0x1400488d8  cmp     ecx, eax
0x1400488da  jz      short loc_1400488E6
0x1400488dc  xor     edx, edx
0x1400488de  mov     ecx, r13d
0x1400488e1  jmp     loc_140048852
0x1400488e6  lea     ecx, [rdi+1]
0x1400488e9  shr     ecx, 1
0x1400488eb  lea     edx, [r10+1]
0x1400488ef  add     ecx, r10d
0x1400488f2  jmp     loc_140048852
0x1400488f7  lea     ecx, [rdi-1]
0x1400488fa  shr     ecx, 1
0x1400488fc  add     ecx, r10d
0x1400488ff  jmp     loc_14004884F
0x140048904  lea     edx, [r10+1]
0x140048908  mov     ecx, edx
0x14004890a  jmp     loc_140048852
```
