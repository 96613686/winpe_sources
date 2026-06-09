# LipsIkePolicyCreate

- ea: `0x18004b9a8`
- end: `0x18004ba8d`
- name: `LipsIkePolicyCreate`
- size: `229`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180046edc`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x18004b9a8`
- `0x18004ba94`
- `0x18004bb54`

## string_xrefs

- `0x18004ba75`: `LipsIkePolicyCreate`

## pseudocode

```c
__int64 __fastcall LipsIkePolicyCreate(__int64 a1, _QWORD *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _DWORD *v10; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v4 = IpsecAllocMem(0x28u);
  v10 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = 8;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_11;
    v8 = 10;
    goto LABEL_5;
  }
  v6 = LipsIkePolicyProposalCreate(*(_QWORD *)(a1 + 48), *(unsigned int *)(a1 + 40), v4 + 6, v4 + 5);
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_11;
    v8 = 11;
LABEL_5:
    WPP_SF_d(v7[2], v8, WPP_3e1383b314ed317a37ba3448ba7d11e7_Traceguids, v6);
    goto LABEL_11;
  }
  v5[8] = 0;
  *v5 = *(_DWORD *)(a1 + 36);
  v5[9] = 5;
  *a2 = v5;
  v10 = 0;
LABEL_11:
  LipsIkePolicyDestroy(&v10);
  if ( v6 )
    return LipsReportError(v6, "LipsIkePolicyCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004b9a8  push    rbx
0x18004b9aa  push    rsi
0x18004b9ab  push    rdi
0x18004b9ac  push    r14
0x18004b9ae  sub     rsp, 28h
0x18004b9b2  mov     rsi, rcx
0x18004b9b5  mov     qword ptr [rdx], 0
0x18004b9bc  mov     ecx, 28h ; '('
0x18004b9c1  mov     r14, rdx
0x18004b9c4  call    IpsecAllocMem
0x18004b9c9  mov     [rsp+48h+arg_8], rax
0x18004b9ce  mov     rbx, rax
0x18004b9d1  test    rax, rax
0x18004b9d4  jnz     short loc_18004BA0A
0x18004b9d6  lea     edi, [rax+8]
0x18004b9d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9e0  lea     rax, WPP_GLOBAL_Control
0x18004b9e7  cmp     rcx, rax
0x18004b9ea  jz      short loc_18004BA63
0x18004b9ec  test    byte ptr [rcx+1Ch], 10h
0x18004b9f0  jz      short loc_18004BA63
0x18004b9f2  lea     edx, [rbx+0Ah]
0x18004b9f5  mov     rcx, [rcx+10h]
0x18004b9f9  lea     r8, WPP_3e1383b314ed317a37ba3448ba7d11e7_Traceguids
0x18004ba00  mov     r9d, edi
0x18004ba03  call    WPP_SF_d
0x18004ba08  jmp     short loc_18004BA63
0x18004ba0a  mov     edx, [rsi+28h]
0x18004ba0d  lea     r9, [rax+14h]
0x18004ba11  mov     rcx, [rsi+30h]
0x18004ba15  lea     r8, [rax+18h]
0x18004ba19  call    LipsIkePolicyProposalCreate
0x18004ba1e  mov     edi, eax
0x18004ba20  test    eax, eax
0x18004ba22  jz      short loc_18004BA44
0x18004ba24  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba2b  lea     rax, WPP_GLOBAL_Control
0x18004ba32  cmp     rcx, rax
0x18004ba35  jz      short loc_18004BA63
0x18004ba37  test    byte ptr [rcx+1Ch], 10h
0x18004ba3b  jz      short loc_18004BA63
0x18004ba3d  mov     edx, 0Bh
0x18004ba42  jmp     short loc_18004B9F5
0x18004ba44  mov     dword ptr [rbx+20h], 0
0x18004ba4b  mov     eax, [rsi+24h]
0x18004ba4e  mov     [rbx], eax
0x18004ba50  mov     dword ptr [rbx+24h], 5
0x18004ba57  mov     [r14], rbx
0x18004ba5a  mov     [rsp+48h+arg_8], 0
0x18004ba63  lea     rcx, [rsp+48h+arg_8]
0x18004ba68  call    LipsIkePolicyDestroy
0x18004ba6d  test    edi, edi
0x18004ba6f  jnz     short loc_18004BA75
0x18004ba71  xor     eax, eax
0x18004ba73  jmp     short loc_18004BA83
0x18004ba75  lea     rdx, aLipsikepolicyc; "LipsIkePolicyCreate"
0x18004ba7c  mov     ecx, edi
0x18004ba7e  call    LipsReportError
0x18004ba83  add     rsp, 28h
0x18004ba87  pop     r14
0x18004ba89  pop     rdi
0x18004ba8a  pop     rsi
0x18004ba8b  pop     rbx
0x18004ba8c  retn
```
