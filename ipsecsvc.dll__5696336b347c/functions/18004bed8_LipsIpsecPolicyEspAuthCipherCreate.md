# LipsIpsecPolicyEspAuthCipherCreate

- ea: `0x18004bed8`
- end: `0x18004bf8f`
- name: `LipsIpsecPolicyEspAuthCipherCreate`
- size: `183`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004c3b8`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180045f1c`
- `0x18004bed8`
- `0x18004bf98`
- `0x18004c070`

## string_xrefs

- `0x18004bf78`: `LipsIpsecPolicyEspAuthCipherCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyEspAuthCipherCreate(__int64 a1, _DWORD *a2, __int64 *a3)
{
  char *v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  void *v11; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 6;
  *a3 = 0;
  v6 = (char *)IpsecAllocMem(0x20u);
  v11 = v6;
  if ( v6 )
  {
    v7 = 0;
    v8 = LipsIpsecPolicyEspCipherConvert(*(unsigned int *)(a1 + 4), v6 + 16);
    v9 = LipsIpsecPolicyEspAuthConvert(*(unsigned int *)(a1 + 8), v8);
    *a2 = 4;
    *a3 = v9;
    v11 = 0;
  }
  else
  {
    v7 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, 8);
  }
  LipsIkePolicyProposalDestroy(&v11);
  if ( v7 )
    return LipsReportError(v7, "LipsIpsecPolicyEspAuthCipherCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004bed8  push    rbx
0x18004beda  push    rbp
0x18004bedb  push    rsi
0x18004bedc  push    rdi
0x18004bedd  sub     rsp, 28h
0x18004bee1  mov     rbp, rcx
0x18004bee4  mov     dword ptr [rdx], 6
0x18004beea  mov     ecx, 20h ; ' '
0x18004beef  mov     qword ptr [r8], 0
0x18004bef6  mov     rdi, r8
0x18004bef9  mov     rsi, rdx
0x18004befc  call    IpsecAllocMem
0x18004bf01  mov     [rsp+48h+arg_8], rax
0x18004bf06  test    rax, rax
0x18004bf09  jnz     short loc_18004BF3F
0x18004bf0b  lea     ebx, [rax+8]
0x18004bf0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bf15  lea     rax, WPP_GLOBAL_Control
0x18004bf1c  cmp     rcx, rax
0x18004bf1f  jz      short loc_18004BF66
0x18004bf21  test    byte ptr [rcx+1Ch], 10h
0x18004bf25  jz      short loc_18004BF66
0x18004bf27  mov     rcx, [rcx+10h]
0x18004bf2b  lea     edx, [rbx+10h]
0x18004bf2e  mov     r9d, ebx
0x18004bf31  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004bf38  call    WPP_SF_d
0x18004bf3d  jmp     short loc_18004BF66
0x18004bf3f  mov     ecx, [rbp+4]
0x18004bf42  lea     rdx, [rax+10h]
0x18004bf46  xor     ebx, ebx
0x18004bf48  call    LipsIpsecPolicyEspCipherConvert
0x18004bf4d  mov     ecx, [rbp+8]
0x18004bf50  mov     rdx, rax
0x18004bf53  call    LipsIpsecPolicyEspAuthConvert
0x18004bf58  mov     dword ptr [rsi], 4
0x18004bf5e  mov     [rdi], rax
0x18004bf61  mov     [rsp+48h+arg_8], rbx
0x18004bf66  lea     rcx, [rsp+48h+arg_8]
0x18004bf6b  call    LipsIkePolicyProposalDestroy
0x18004bf70  test    ebx, ebx
0x18004bf72  jnz     short loc_18004BF78
0x18004bf74  xor     eax, eax
0x18004bf76  jmp     short loc_18004BF86
0x18004bf78  lea     rdx, aLipsipsecpolic_1; "LipsIpsecPolicyEspAuthCipherCreate"
0x18004bf7f  mov     ecx, ebx
0x18004bf81  call    LipsReportError
0x18004bf86  add     rsp, 28h
0x18004bf8a  pop     rdi
0x18004bf8b  pop     rsi
0x18004bf8c  pop     rbp
0x18004bf8d  pop     rbx
0x18004bf8e  retn
```
