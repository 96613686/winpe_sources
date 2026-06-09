# LipsIpsecPolicyCreate

- ea: `0x18004bd48`
- end: `0x18004bea2`
- name: `LipsIpsecPolicyCreate`
- size: `346`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180046f60`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004bd48`
- `0x18004bea8`
- `0x18004c148`
- `0x18004c6b4`

## string_xrefs

- `0x18004be8a`: `LipsIpsecPolicyCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyCreate(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int *v9; // rdx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  _DWORD *v15; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = IpsecAllocMem(0x28u);
  v15 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v8 = 10;
    goto LABEL_5;
  }
  v9 = v4 + 4;
  v10 = *(_DWORD *)(a1 + 32);
  *v9 = 0;
  v11 = v10 & 4;
  if ( (v10 & 4) != 0 && (v10 & 0x40) != 0 )
  {
    *v9 = 4;
    v12 = 4;
  }
  else
  {
    v12 = 0;
    if ( v11 )
    {
      *v9 = 2;
      v12 = 2;
    }
  }
  if ( gcUdpEncapsulation == 1 )
  {
    v13 = v12 | 0x10;
  }
  else
  {
    if ( gcUdpEncapsulation != 2 )
      goto LABEL_16;
    v13 = v12 | 0x20;
  }
  *v9 = v13;
LABEL_16:
  LipsIpsecSetTimeoutFlags(a1, v9, 2);
  v6 = LipsIpsecPolicyProposalsCreate(*(_QWORD *)(a1 + 48), *(unsigned int *)(a1 + 40), v5 + 2, v5);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_25;
    v8 = 11;
LABEL_5:
    WPP_SF_d(v7[2], v8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, v6);
    goto LABEL_25;
  }
  if ( (*(_BYTE *)(a1 + 32) & 4) != 0 )
    v5[5] = 10;
  v5[6] = gcSaIdleTime;
  if ( !v5[7] )
    v5[7] = 60;
  *a2 = v5;
  v15 = 0;
LABEL_25:
  LipsIpsecPolicyDestroy(&v15);
  if ( v6 )
    return LipsReportError(v6, "LipsIpsecPolicyCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004bd48  push    rbx
0x18004bd4a  push    rsi
0x18004bd4b  push    rdi
0x18004bd4c  push    r14
0x18004bd4e  sub     rsp, 28h
0x18004bd52  mov     rsi, rcx
0x18004bd55  mov     qword ptr [rdx], 0
0x18004bd5c  mov     ecx, 28h ; '('
0x18004bd61  mov     r14, rdx
0x18004bd64  call    IpsecAllocMem
0x18004bd69  mov     [rsp+48h+arg_8], rax
0x18004bd6e  mov     rbx, rax
0x18004bd71  test    rax, rax
0x18004bd74  jnz     short loc_18004BDB5
0x18004bd76  lea     edi, [rax+8]
0x18004bd79  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd80  lea     rax, WPP_GLOBAL_Control
0x18004bd87  cmp     rcx, rax
0x18004bd8a  jz      loc_18004BE78
0x18004bd90  test    byte ptr [rcx+1Ch], 10h
0x18004bd94  jz      loc_18004BE78
0x18004bd9a  lea     edx, [rbx+0Ah]
0x18004bd9d  mov     rcx, [rcx+10h]
0x18004bda1  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004bda8  mov     r9d, edi
0x18004bdab  call    WPP_SF_d
0x18004bdb0  jmp     loc_18004BE78
0x18004bdb5  lea     rdx, [rax+10h]
0x18004bdb9  mov     r8d, 2
0x18004bdbf  mov     eax, [rsi+20h]
0x18004bdc2  mov     ecx, eax
0x18004bdc4  mov     dword ptr [rdx], 0
0x18004bdca  and     ecx, 4
0x18004bdcd  jz      short loc_18004BDDF
0x18004bdcf  test    al, 40h
0x18004bdd1  jz      short loc_18004BDDF
0x18004bdd3  mov     dword ptr [rdx], 4
0x18004bdd9  lea     eax, [r8+2]
0x18004bddd  jmp     short loc_18004BDEB
0x18004bddf  xor     eax, eax
0x18004bde1  test    ecx, ecx
0x18004bde3  jz      short loc_18004BDEB
0x18004bde5  mov     [rdx], r8d
0x18004bde8  mov     eax, r8d
0x18004bdeb  mov     ecx, cs:gcUdpEncapsulation
0x18004bdf1  cmp     ecx, 1
0x18004bdf4  jnz     short loc_18004BDFB
0x18004bdf6  or      eax, 10h
0x18004bdf9  jmp     short loc_18004BE03
0x18004bdfb  cmp     ecx, r8d
0x18004bdfe  jnz     short loc_18004BE05
0x18004be00  or      eax, 20h
0x18004be03  mov     [rdx], eax
0x18004be05  mov     rcx, rsi
0x18004be08  call    LipsIpsecSetTimeoutFlags
0x18004be0d  mov     rcx, [rsi+30h]
0x18004be11  lea     r8, [rbx+8]
0x18004be15  mov     edx, [rsi+28h]
0x18004be18  mov     r9, rbx
0x18004be1b  call    LipsIpsecPolicyProposalsCreate
0x18004be20  mov     edi, eax
0x18004be22  test    eax, eax
0x18004be24  jz      short loc_18004BE49
0x18004be26  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be2d  lea     rax, WPP_GLOBAL_Control
0x18004be34  cmp     rcx, rax
0x18004be37  jz      short loc_18004BE78
0x18004be39  test    byte ptr [rcx+1Ch], 10h
0x18004be3d  jz      short loc_18004BE78
0x18004be3f  mov     edx, 0Bh
0x18004be44  jmp     loc_18004BD9D
0x18004be49  test    byte ptr [rsi+20h], 4
0x18004be4d  jz      short loc_18004BE56
0x18004be4f  mov     dword ptr [rbx+14h], 0Ah
0x18004be56  mov     eax, cs:gcSaIdleTime
0x18004be5c  mov     [rbx+18h], eax
0x18004be5f  cmp     dword ptr [rbx+1Ch], 0
0x18004be63  jnz     short loc_18004BE6C
0x18004be65  mov     dword ptr [rbx+1Ch], 3Ch ; '<'
0x18004be6c  mov     [r14], rbx
0x18004be6f  mov     [rsp+48h+arg_8], 0
0x18004be78  lea     rcx, [rsp+48h+arg_8]
0x18004be7d  call    LipsIpsecPolicyDestroy
0x18004be82  test    edi, edi
0x18004be84  jnz     short loc_18004BE8A
0x18004be86  xor     eax, eax
0x18004be88  jmp     short loc_18004BE98
0x18004be8a  lea     rdx, aLipsipsecpolic_2; "LipsIpsecPolicyCreate"
0x18004be91  mov     ecx, edi
0x18004be93  call    LipsReportError
0x18004be98  add     rsp, 28h
0x18004be9c  pop     r14
0x18004be9e  pop     rdi
0x18004be9f  pop     rsi
0x18004bea0  pop     rbx
0x18004bea1  retn
```
