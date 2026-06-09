# LipsIpsecPolicyTransformsCreate

- ea: `0x18004c530`
- end: `0x18004c63b`
- name: `LipsIpsecPolicyTransformsCreate`
- size: `267`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004c148`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004c3b8`
- `0x18004c530`
- `0x18004c644`

## string_xrefs

- `0x18004c616`: `LipsIpsecPolicyTransformsCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyTransformsCreate(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  LPVOID v8; // rbp
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 i; // rdi
  LPVOID v14; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  *a4 = 0;
  v14 = IpsecAllocMem(16LL * a2);
  v8 = v14;
  if ( v14 )
  {
    v9 = 0;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= a2 )
      {
        *a4 = a2;
        *a3 = v8;
        v14 = 0;
        goto LABEL_14;
      }
      v9 = LipsIpsecPolicyTransformCreate((_DWORD *)(a1 + 36 * i), (__int64)v8 + 16 * (unsigned int)i);
      if ( v9 )
        break;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = 16;
      goto LABEL_5;
    }
  }
  else
  {
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v11 = 15;
LABEL_5:
      WPP_SF_d(v10[2], v11, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, v9);
    }
  }
LABEL_14:
  LipsIpsecPolicyTransformsDestroy(&v14, a2);
  if ( v9 )
    return LipsReportError(v9, "LipsIpsecPolicyTransformsCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004c530  mov     [rsp+arg_0], rbx
0x18004c535  mov     [rsp+arg_8], rbp
0x18004c53a  push    rsi
0x18004c53b  push    rdi
0x18004c53c  push    r12
0x18004c53e  push    r14
0x18004c540  push    r15
0x18004c542  sub     rsp, 20h
0x18004c546  mov     r12, rcx
0x18004c549  mov     qword ptr [r8], 0
0x18004c550  mov     ecx, edx
0x18004c552  mov     r14, r9
0x18004c555  shl     rcx, 4
0x18004c559  mov     r15, r8
0x18004c55c  mov     esi, edx
0x18004c55e  mov     dword ptr [r9], 0
0x18004c565  call    IpsecAllocMem
0x18004c56a  mov     [rsp+48h+arg_10], rax
0x18004c56f  mov     rbp, rax
0x18004c572  test    rax, rax
0x18004c575  jnz     short loc_18004C5AB
0x18004c577  lea     ebx, [rax+8]
0x18004c57a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c581  lea     rax, WPP_GLOBAL_Control
0x18004c588  cmp     rcx, rax
0x18004c58b  jz      short loc_18004C602
0x18004c58d  test    byte ptr [rcx+1Ch], 10h
0x18004c591  jz      short loc_18004C602
0x18004c593  lea     edx, [rbp+0Fh]
0x18004c596  mov     rcx, [rcx+10h]
0x18004c59a  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004c5a1  mov     r9d, ebx
0x18004c5a4  call    WPP_SF_d
0x18004c5a9  jmp     short loc_18004C602
0x18004c5ab  xor     ebx, ebx
0x18004c5ad  xor     edi, edi
0x18004c5af  cmp     edi, esi
0x18004c5b1  jnb     short loc_18004C5F3
0x18004c5b3  lea     rax, [rdi+rdi*8]
0x18004c5b7  mov     edx, edi
0x18004c5b9  shl     rdx, 4
0x18004c5bd  lea     rcx, [r12+rax*4]
0x18004c5c1  add     rdx, rbp
0x18004c5c4  call    LipsIpsecPolicyTransformCreate
0x18004c5c9  mov     ebx, eax
0x18004c5cb  test    eax, eax
0x18004c5cd  jnz     short loc_18004C5D3
0x18004c5cf  inc     edi
0x18004c5d1  jmp     short loc_18004C5AF
0x18004c5d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c5da  lea     rax, WPP_GLOBAL_Control
0x18004c5e1  cmp     rcx, rax
0x18004c5e4  jz      short loc_18004C602
0x18004c5e6  test    byte ptr [rcx+1Ch], 10h
0x18004c5ea  jz      short loc_18004C602
0x18004c5ec  mov     edx, 10h
0x18004c5f1  jmp     short loc_18004C596
0x18004c5f3  mov     [r14], esi
0x18004c5f6  mov     [r15], rbp
0x18004c5f9  mov     [rsp+48h+arg_10], 0
0x18004c602  mov     edx, esi
0x18004c604  lea     rcx, [rsp+48h+arg_10]
0x18004c609  call    LipsIpsecPolicyTransformsDestroy
0x18004c60e  test    ebx, ebx
0x18004c610  jnz     short loc_18004C616
0x18004c612  xor     eax, eax
0x18004c614  jmp     short loc_18004C624
0x18004c616  lea     rdx, aLipsipsecpolic_4; "LipsIpsecPolicyTransformsCreate"
0x18004c61d  mov     ecx, ebx
0x18004c61f  call    LipsReportError
0x18004c624  mov     rbx, [rsp+48h+arg_0]
0x18004c629  mov     rbp, [rsp+48h+arg_8]
0x18004c62e  add     rsp, 20h
0x18004c632  pop     r15
0x18004c634  pop     r14
0x18004c636  pop     r12
0x18004c638  pop     rdi
0x18004c639  pop     rsi
0x18004c63a  retn
```
