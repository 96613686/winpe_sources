# LipsIpsecPolicyEspCipherCreate

- ea: `0x18004c094`
- end: `0x18004c13f`
- name: `LipsIpsecPolicyEspCipherCreate`
- size: `171`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004c3b8`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180045f1c`
- `0x18004c070`
- `0x18004c094`

## string_xrefs

- `0x18004c128`: `LipsIpsecPolicyEspCipherCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyEspCipherCreate(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  LPVOID v9; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 6;
  *a3 = 0;
  v9 = IpsecAllocMem(0x10u);
  if ( v9 )
  {
    v6 = 0;
    LipsIpsecPolicyEspCipherConvert(*(unsigned int *)(a1 + 4), v9);
    *a2 = 3;
    *a3 = v7;
    v9 = 0;
  }
  else
  {
    v6 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, 8);
  }
  LipsIkePolicyProposalDestroy(&v9);
  if ( v6 )
    return LipsReportError(v6, "LipsIpsecPolicyEspCipherCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004c094  push    rbx
0x18004c096  push    rbp
0x18004c097  push    rsi
0x18004c098  push    rdi
0x18004c099  sub     rsp, 28h
0x18004c09d  mov     rbp, rcx
0x18004c0a0  mov     dword ptr [rdx], 6
0x18004c0a6  mov     ecx, 10h
0x18004c0ab  mov     qword ptr [r8], 0
0x18004c0b2  mov     rdi, r8
0x18004c0b5  mov     rsi, rdx
0x18004c0b8  call    IpsecAllocMem
0x18004c0bd  mov     [rsp+48h+arg_8], rax
0x18004c0c2  mov     rdx, rax
0x18004c0c5  test    rax, rax
0x18004c0c8  jnz     short loc_18004C0FE
0x18004c0ca  lea     ebx, [rax+8]
0x18004c0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c0d4  lea     rax, WPP_GLOBAL_Control
0x18004c0db  cmp     rcx, rax
0x18004c0de  jz      short loc_18004C116
0x18004c0e0  test    byte ptr [rcx+1Ch], 10h
0x18004c0e4  jz      short loc_18004C116
0x18004c0e6  mov     rcx, [rcx+10h]
0x18004c0ea  lea     edx, [rbx+0Fh]
0x18004c0ed  mov     r9d, ebx
0x18004c0f0  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004c0f7  call    WPP_SF_d
0x18004c0fc  jmp     short loc_18004C116
0x18004c0fe  mov     ecx, [rbp+4]
0x18004c101  xor     ebx, ebx
0x18004c103  call    LipsIpsecPolicyEspCipherConvert
0x18004c108  mov     dword ptr [rsi], 3
0x18004c10e  mov     [rdi], rdx
0x18004c111  mov     [rsp+48h+arg_8], rbx
0x18004c116  lea     rcx, [rsp+48h+arg_8]
0x18004c11b  call    LipsIkePolicyProposalDestroy
0x18004c120  test    ebx, ebx
0x18004c122  jnz     short loc_18004C128
0x18004c124  xor     eax, eax
0x18004c126  jmp     short loc_18004C136
0x18004c128  lea     rdx, aLipsipsecpolic_5; "LipsIpsecPolicyEspCipherCreate"
0x18004c12f  mov     ecx, ebx
0x18004c131  call    LipsReportError
0x18004c136  add     rsp, 28h
0x18004c13a  pop     rdi
0x18004c13b  pop     rsi
0x18004c13c  pop     rbp
0x18004c13d  pop     rbx
0x18004c13e  retn
```
