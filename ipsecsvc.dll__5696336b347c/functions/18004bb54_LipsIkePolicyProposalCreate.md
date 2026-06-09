# LipsIkePolicyProposalCreate

- ea: `0x18004bb54`
- end: `0x18004bc79`
- name: `LipsIkePolicyProposalCreate`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004b9a8`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x180045f1c`
- `0x18004bac4`
- `0x18004bb54`

## string_xrefs

- `0x18004bc5a`: `LipsIkePolicyProposalCreate`

## pseudocode

```c
__int64 __fastcall LipsIkePolicyProposalCreate(__int64 a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  char *v11; // r11
  unsigned int i; // esi
  char *v14; // [rsp+60h] [rbp+18h] BYREF
  SIZE_T v15; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  v15 = 0;
  v14 = 0;
  *a4 = 0;
  v8 = NsuSizeTMultiply(a2, 28, &v15);
  if ( v8 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_13;
    v10 = 12;
    goto LABEL_5;
  }
  v14 = (char *)IpsecAllocMem(v15);
  v11 = v14;
  if ( !v14 )
  {
    v8 = 8;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_13;
    v10 = 13;
LABEL_5:
    WPP_SF_d(v9[2], v10, WPP_3e1383b314ed317a37ba3448ba7d11e7_Traceguids, v8);
    goto LABEL_13;
  }
  for ( i = 0; i < a2; ++i )
    LipsIkePolicyProposalConvert(a1 + 44LL * i, &v11[28 * i]);
  *a4 = a2;
  *a3 = v11;
  v14 = 0;
LABEL_13:
  LipsIkePolicyProposalDestroy(&v14);
  if ( v8 )
    return LipsReportError(v8, "LipsIkePolicyProposalCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004bb54  mov     rax, rsp
0x18004bb57  mov     [rax+8], rbx
0x18004bb5b  push    rbp
0x18004bb5c  push    rsi
0x18004bb5d  push    rdi
0x18004bb5e  push    r14
0x18004bb60  push    r15
0x18004bb62  sub     rsp, 20h
0x18004bb66  mov     edi, edx
0x18004bb68  mov     rbp, rcx
0x18004bb6b  mov     ecx, edx
0x18004bb6d  mov     r15, r8
0x18004bb70  mov     qword ptr [r8], 0
0x18004bb77  mov     edx, 1Ch
0x18004bb7c  lea     r8, [rax+20h]
0x18004bb80  mov     qword ptr [rax+20h], 0
0x18004bb88  mov     r14, r9
0x18004bb8b  mov     qword ptr [rax+18h], 0
0x18004bb93  mov     dword ptr [r9], 0
0x18004bb9a  call    NsuSizeTMultiply
0x18004bb9f  mov     ebx, eax
0x18004bba1  test    eax, eax
0x18004bba3  jz      short loc_18004BBE0
0x18004bba5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bbac  lea     rax, WPP_GLOBAL_Control
0x18004bbb3  cmp     rcx, rax
0x18004bbb6  jz      loc_18004BC48
0x18004bbbc  test    byte ptr [rcx+1Ch], 10h
0x18004bbc0  jz      loc_18004BC48
0x18004bbc6  mov     edx, 0Ch
0x18004bbcb  mov     rcx, [rcx+10h]
0x18004bbcf  lea     r8, WPP_3e1383b314ed317a37ba3448ba7d11e7_Traceguids
0x18004bbd6  mov     r9d, ebx
0x18004bbd9  call    WPP_SF_d
0x18004bbde  jmp     short loc_18004BC48
0x18004bbe0  mov     rcx, [rsp+48h+arg_18]
0x18004bbe5  call    IpsecAllocMem
0x18004bbea  mov     [rsp+48h+arg_10], rax
0x18004bbef  mov     r11, rax
0x18004bbf2  test    rax, rax
0x18004bbf5  jnz     short loc_18004BC18
0x18004bbf7  lea     ebx, [rax+8]
0x18004bbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc01  lea     rax, WPP_GLOBAL_Control
0x18004bc08  cmp     rcx, rax
0x18004bc0b  jz      short loc_18004BC48
0x18004bc0d  test    byte ptr [rcx+1Ch], 10h
0x18004bc11  jz      short loc_18004BC48
0x18004bc13  lea     edx, [rbx+5]
0x18004bc16  jmp     short loc_18004BBCB
0x18004bc18  xor     esi, esi
0x18004bc1a  test    edi, edi
0x18004bc1c  jz      short loc_18004BC39
0x18004bc1e  mov     eax, esi
0x18004bc20  imul    rdx, rax, 1Ch
0x18004bc24  imul    rcx, rax, 2Ch ; ','
0x18004bc28  add     rdx, r11
0x18004bc2b  add     rcx, rbp
0x18004bc2e  call    LipsIkePolicyProposalConvert
0x18004bc33  inc     esi
0x18004bc35  cmp     esi, edi
0x18004bc37  jb      short loc_18004BC1E
0x18004bc39  mov     [r14], edi
0x18004bc3c  mov     [r15], r11
0x18004bc3f  mov     [rsp+48h+arg_10], 0
0x18004bc48  lea     rcx, [rsp+48h+arg_10]
0x18004bc4d  call    LipsIkePolicyProposalDestroy
0x18004bc52  test    ebx, ebx
0x18004bc54  jnz     short loc_18004BC5A
0x18004bc56  xor     eax, eax
0x18004bc58  jmp     short loc_18004BC68
0x18004bc5a  lea     rdx, aLipsikepolicyp; "LipsIkePolicyProposalCreate"
0x18004bc61  mov     ecx, ebx
0x18004bc63  call    LipsReportError
0x18004bc68  mov     rbx, [rsp+48h+arg_0]
0x18004bc6d  add     rsp, 20h
0x18004bc71  pop     r15
0x18004bc73  pop     r14
0x18004bc75  pop     rdi
0x18004bc76  pop     rsi
0x18004bc77  pop     rbp
0x18004bc78  retn
```
