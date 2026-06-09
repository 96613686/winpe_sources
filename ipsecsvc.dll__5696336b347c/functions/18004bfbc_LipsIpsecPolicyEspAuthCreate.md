# LipsIpsecPolicyEspAuthCreate

- ea: `0x18004bfbc`
- end: `0x18004c067`
- name: `LipsIpsecPolicyEspAuthCreate`
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
- `0x18004bf98`
- `0x18004bfbc`

## string_xrefs

- `0x18004c050`: `LipsIpsecPolicyEspAuthCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyEspAuthCreate(__int64 a1, _DWORD *a2, _QWORD *a3)
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
    LipsIpsecPolicyEspAuthConvert(*(unsigned int *)(a1 + 8), v9);
    *a2 = 2;
    *a3 = v7;
    v9 = 0;
  }
  else
  {
    v6 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, 8);
  }
  LipsIkePolicyProposalDestroy(&v9);
  if ( v6 )
    return LipsReportError(v6, "LipsIpsecPolicyEspAuthCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004bfbc  push    rbx
0x18004bfbe  push    rbp
0x18004bfbf  push    rsi
0x18004bfc0  push    rdi
0x18004bfc1  sub     rsp, 28h
0x18004bfc5  mov     rbp, rcx
0x18004bfc8  mov     dword ptr [rdx], 6
0x18004bfce  mov     ecx, 10h
0x18004bfd3  mov     qword ptr [r8], 0
0x18004bfda  mov     rdi, r8
0x18004bfdd  mov     rsi, rdx
0x18004bfe0  call    IpsecAllocMem
0x18004bfe5  mov     [rsp+48h+arg_8], rax
0x18004bfea  mov     rdx, rax
0x18004bfed  test    rax, rax
0x18004bff0  jnz     short loc_18004C026
0x18004bff2  lea     ebx, [rax+8]
0x18004bff5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bffc  lea     rax, WPP_GLOBAL_Control
0x18004c003  cmp     rcx, rax
0x18004c006  jz      short loc_18004C03E
0x18004c008  test    byte ptr [rcx+1Ch], 10h
0x18004c00c  jz      short loc_18004C03E
0x18004c00e  mov     rcx, [rcx+10h]
0x18004c012  lea     edx, [rbx+0Eh]
0x18004c015  mov     r9d, ebx
0x18004c018  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004c01f  call    WPP_SF_d
0x18004c024  jmp     short loc_18004C03E
0x18004c026  mov     ecx, [rbp+8]
0x18004c029  xor     ebx, ebx
0x18004c02b  call    LipsIpsecPolicyEspAuthConvert
0x18004c030  mov     dword ptr [rsi], 2
0x18004c036  mov     [rdi], rdx
0x18004c039  mov     [rsp+48h+arg_8], rbx
0x18004c03e  lea     rcx, [rsp+48h+arg_8]
0x18004c043  call    LipsIkePolicyProposalDestroy
0x18004c048  test    ebx, ebx
0x18004c04a  jnz     short loc_18004C050
0x18004c04c  xor     eax, eax
0x18004c04e  jmp     short loc_18004C05E
0x18004c050  lea     rdx, aLipsipsecpolic_6; "LipsIpsecPolicyEspAuthCreate"
0x18004c057  mov     ecx, ebx
0x18004c059  call    LipsReportError
0x18004c05e  add     rsp, 28h
0x18004c062  pop     rdi
0x18004c063  pop     rsi
0x18004c064  pop     rbp
0x18004c065  pop     rbx
0x18004c066  retn
```
