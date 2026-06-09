# LipsIpsecPolicyProposalsCreate

- ea: `0x18004c148`
- end: `0x18004c34f`
- name: `LipsIpsecPolicyProposalsCreate`
- size: `519`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180049dec`
- `0x18004bd48`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x18004c148`
- `0x18004c358`
- `0x18004c530`

## string_xrefs

- `0x18004c32a`: `LipsIpsecPolicyProposalsCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyProposalsCreate(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  char *v11; // rbx
  unsigned int i; // esi
  __int64 v13; // r10
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  int v17; // edx
  char *v19; // [rsp+60h] [rbp+18h] BYREF
  SIZE_T v20; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  v20 = 0;
  v19 = 0;
  *a4 = 0;
  v8 = NsuSizeTMultiply(a2, 32, &v20);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_33;
    v10 = 12;
    goto LABEL_5;
  }
  v19 = (char *)IpsecAllocMem(v20);
  v11 = v19;
  if ( !v19 )
  {
    v8 = 8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_33;
    v10 = 13;
LABEL_5:
    WPP_SF_d(v9[2], v10, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, v8);
    goto LABEL_33;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= a2 )
    {
      *a4 = a2;
      *a3 = v11;
      v19 = 0;
      goto LABEL_33;
    }
    v13 = 100LL * i;
    v14 = 32LL * i;
    v15 = *(_DWORD *)(v13 + a1 + 16);
    *(_DWORD *)&v11[v14 + 24] = 0;
    if ( v15 )
    {
      switch ( v15 )
      {
        case 1:
          *(_DWORD *)&v11[v14 + 24] = 1;
          break;
        case 2:
          *(_DWORD *)&v11[v14 + 24] = 2;
          break;
        case 0x10000001:
          *(_DWORD *)&v11[v14 + 24] = 3;
          break;
        case 0x80000000:
          *(_DWORD *)&v11[v14 + 24] = 6;
          break;
      }
    }
    v16 = *(_DWORD *)(v13 + a1 + 4);
    *(_DWORD *)&v11[v14 + 4] = v16;
    v17 = *(_DWORD *)(v13 + a1);
    *(_DWORD *)&v11[v14] = v17;
    if ( !v16 )
      *(_DWORD *)&v11[v14 + 4] = 100000;
    if ( !v17 )
      *(_DWORD *)&v11[v14] = 3600;
    if ( !*(_DWORD *)&v11[v14 + 8] )
      *(_DWORD *)&v11[v14 + 8] = 0x7FFFFFFF;
    v8 = LipsIpsecPolicyTransformsCreate(
           v13 + a1 + 24,
           *(unsigned int *)(v13 + a1 + 20),
           &v11[v14 + 16],
           &v11[v14 + 12]);
    if ( v8 )
      break;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v10 = 14;
    goto LABEL_5;
  }
LABEL_33:
  LipsIpsecPolicyProposalsDestroy(&v19, a2);
  if ( v8 )
    return LipsReportError(v8, "LipsIpsecPolicyProposalsCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004c148  mov     rax, rsp
0x18004c14b  mov     [rax+8], rbx
0x18004c14f  mov     [rax+10h], rbp
0x18004c153  push    rsi
0x18004c154  push    rdi
0x18004c155  push    r12
0x18004c157  push    r14
0x18004c159  push    r15
0x18004c15b  sub     rsp, 20h
0x18004c15f  mov     ebp, edx
0x18004c161  mov     r14, rcx
0x18004c164  mov     ecx, edx
0x18004c166  mov     r12, r8
0x18004c169  mov     qword ptr [r8], 0
0x18004c170  mov     edx, 20h ; ' '
0x18004c175  lea     r8, [rax+20h]
0x18004c179  mov     qword ptr [rax+20h], 0
0x18004c181  mov     r15, r9
0x18004c184  mov     qword ptr [rax+18h], 0
0x18004c18c  mov     dword ptr [r9], 0
0x18004c193  call    NsuSizeTMultiply
0x18004c198  mov     edi, eax
0x18004c19a  test    eax, eax
0x18004c19c  jz      short loc_18004C1DC
0x18004c19e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c1a5  lea     rax, WPP_GLOBAL_Control
0x18004c1ac  cmp     rcx, rax
0x18004c1af  jz      loc_18004C316
0x18004c1b5  test    byte ptr [rcx+1Ch], 10h
0x18004c1b9  jz      loc_18004C316
0x18004c1bf  mov     edx, 0Ch
0x18004c1c4  mov     rcx, [rcx+10h]
0x18004c1c8  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004c1cf  mov     r9d, edi
0x18004c1d2  call    WPP_SF_d
0x18004c1d7  jmp     loc_18004C316
0x18004c1dc  mov     rcx, [rsp+48h+arg_18]
0x18004c1e1  call    IpsecAllocMem
0x18004c1e6  mov     [rsp+48h+arg_10], rax
0x18004c1eb  mov     rbx, rax
0x18004c1ee  test    rax, rax
0x18004c1f1  jnz     short loc_18004C21C
0x18004c1f3  lea     edi, [rax+8]
0x18004c1f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c1fd  lea     rax, WPP_GLOBAL_Control
0x18004c204  cmp     rcx, rax
0x18004c207  jz      loc_18004C316
0x18004c20d  test    byte ptr [rcx+1Ch], 10h
0x18004c211  jz      loc_18004C316
0x18004c217  lea     edx, [rbx+0Dh]
0x18004c21a  jmp     short loc_18004C1C4
0x18004c21c  xor     esi, esi
0x18004c21e  cmp     esi, ebp
0x18004c220  jnb     loc_18004C306
0x18004c226  mov     eax, esi
0x18004c228  imul    r10, rax, 64h ; 'd'
0x18004c22c  mov     ecx, esi
0x18004c22e  shl     rcx, 5
0x18004c232  mov     eax, [r10+r14+10h]
0x18004c237  mov     dword ptr [rcx+rbx+18h], 0
0x18004c23f  test    eax, eax
0x18004c241  jz      short loc_18004C281
0x18004c243  cmp     eax, 1
0x18004c246  jz      short loc_18004C279
0x18004c248  cmp     eax, 2
0x18004c24b  jz      short loc_18004C26F
0x18004c24d  cmp     eax, 10000001h
0x18004c252  jz      short loc_18004C265
0x18004c254  cmp     eax, 80000000h
0x18004c259  jnz     short loc_18004C281
0x18004c25b  mov     dword ptr [rcx+rbx+18h], 6
0x18004c263  jmp     short loc_18004C281
0x18004c265  mov     dword ptr [rcx+rbx+18h], 3
0x18004c26d  jmp     short loc_18004C281
0x18004c26f  mov     dword ptr [rcx+rbx+18h], 2
0x18004c277  jmp     short loc_18004C281
0x18004c279  mov     dword ptr [rcx+rbx+18h], 1
0x18004c281  mov     eax, [r10+r14+4]
0x18004c286  mov     [rcx+rbx+4], eax
0x18004c28a  mov     edx, [r10+r14]
0x18004c28e  mov     [rcx+rbx], edx
0x18004c291  test    eax, eax
0x18004c293  jnz     short loc_18004C29D
0x18004c295  mov     dword ptr [rcx+rbx+4], 186A0h
0x18004c29d  test    edx, edx
0x18004c29f  jnz     short loc_18004C2A8
0x18004c2a1  mov     dword ptr [rcx+rbx], 0E10h
0x18004c2a8  cmp     dword ptr [rcx+rbx+8], 0
0x18004c2ad  jnz     short loc_18004C2B7
0x18004c2af  mov     dword ptr [rcx+rbx+8], 7FFFFFFFh
0x18004c2b7  mov     edx, [r10+r14+14h]
0x18004c2bc  lea     r9, [rbx+0Ch]
0x18004c2c0  add     r9, rcx
0x18004c2c3  lea     r8, [rbx+10h]
0x18004c2c7  add     r8, rcx
0x18004c2ca  lea     rcx, [r14+18h]
0x18004c2ce  add     rcx, r10
0x18004c2d1  call    LipsIpsecPolicyTransformsCreate
0x18004c2d6  mov     edi, eax
0x18004c2d8  test    eax, eax
0x18004c2da  jnz     short loc_18004C2E3
0x18004c2dc  inc     esi
0x18004c2de  jmp     loc_18004C21E
0x18004c2e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c2ea  lea     rax, WPP_GLOBAL_Control
0x18004c2f1  cmp     rcx, rax
0x18004c2f4  jz      short loc_18004C316
0x18004c2f6  test    byte ptr [rcx+1Ch], 10h
0x18004c2fa  jz      short loc_18004C316
0x18004c2fc  mov     edx, 0Eh
0x18004c301  jmp     loc_18004C1C4
0x18004c306  mov     [r15], ebp
0x18004c309  mov     [r12], rbx
0x18004c30d  mov     [rsp+48h+arg_10], 0
0x18004c316  mov     edx, ebp
0x18004c318  lea     rcx, [rsp+48h+arg_10]
0x18004c31d  call    LipsIpsecPolicyProposalsDestroy
0x18004c322  test    edi, edi
0x18004c324  jnz     short loc_18004C32A
0x18004c326  xor     eax, eax
0x18004c328  jmp     short loc_18004C338
0x18004c32a  lea     rdx, aLipsipsecpolic_3; "LipsIpsecPolicyProposalsCreate"
0x18004c331  mov     ecx, edi
0x18004c333  call    LipsReportError
0x18004c338  mov     rbx, [rsp+48h+arg_0]
0x18004c33d  mov     rbp, [rsp+48h+arg_8]
0x18004c342  add     rsp, 20h
0x18004c346  pop     r15
0x18004c348  pop     r14
0x18004c34a  pop     r12
0x18004c34c  pop     rdi
0x18004c34d  pop     rsi
0x18004c34e  retn
```
