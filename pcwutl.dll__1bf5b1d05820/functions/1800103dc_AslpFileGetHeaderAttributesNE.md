# AslpFileGetHeaderAttributesNE

- ea: `0x1800103dc`
- end: `0x180010575`
- name: `AslpFileGetHeaderAttributesNE`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d258`

## callees

- `0x18000dcf4`
- `0x18000e240`
- `0x18000f334`
- `0x18000f6e4`
- `0x18000f7cc`
- `0x1800103dc`

## string_xrefs

- `0x1800104c9`: `AslStringXmlSanitize failed [%x]`
- `0x180010535`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetHeaderAttributesNE(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // eax
  unsigned int v7; // edi
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v11; // rbp
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // [rsp+20h] [rbp-28h]
  __int64 v16; // [rsp+60h] [rbp+18h] BYREF
  __int64 v17; // [rsp+68h] [rbp+20h] BYREF

  v16 = 0;
  v17 = 0;
  v6 = AslFileMappingEnsure(a2, a2, a3, a4);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( *(_DWORD *)(a2 + 56) == 5 )
    {
      *(_DWORD *)(a1 + 600) |= 2u;
      *(_DWORD *)(a1 + 632) |= 2u;
      *(_DWORD *)(a1 + 728) |= 2u;
      *(_DWORD *)(a1 + 56) |= 2u;
      *(_DWORD *)(a1 + 824) |= 2u;
      *(_DWORD *)(a1 + 760) |= 2u;
      *(_DWORD *)(a1 + 952) |= 2u;
      *(_DWORD *)(a1 + 984) |= 2u;
      *(_DWORD *)(a1 + 1016) |= 2u;
      *(_DWORD *)(a1 + 1080) |= 2u;
      v11 = -1;
      if ( (int)AslpFileGet16BitDescription(&v16, a2) < 0 )
      {
        *(_DWORD *)(a1 + 664) |= 2u;
      }
      else
      {
        v6 = AslStringXmlSanitize(v16);
        v7 = v6;
        if ( v6 < 0 )
        {
          v8 = "AslStringXmlSanitize failed [%x]";
          v9 = 3525;
          goto LABEL_3;
        }
        *(_DWORD *)(a1 + 640) = 4;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(v12 + 2 * v13) );
        *(_DWORD *)(a1 + 664) |= 5u;
        *(_QWORD *)(a1 + 648) = v13;
        *(_QWORD *)(a1 + 656) = v12;
      }
      if ( (int)AslpFileGet16BitModuleName(&v17, a2) >= 0 )
      {
        v6 = AslStringXmlSanitize(v17);
        v7 = v6;
        if ( v6 < 0 )
        {
          v8 = "AslStringXmlSanitize failed [%x]";
          v9 = 3546;
          goto LABEL_3;
        }
        *(_DWORD *)(a1 + 672) = 4;
        do
          ++v11;
        while ( *(_WORD *)(v14 + 2 * v11) );
        *(_DWORD *)(a1 + 696) |= 5u;
        *(_QWORD *)(a1 + 680) = v11;
        *(_QWORD *)(a1 + 688) = v14;
        return 0;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 664) |= 2u;
    }
    *(_DWORD *)(a1 + 696) |= 2u;
    return 0;
  }
  v8 = "AslFileMappingEnsure failed [%x]";
  v9 = 3489;
LABEL_3:
  v15 = v6;
  AslLogCallPrintf(1, "AslpFileGetHeaderAttributesNE", v9, v8, v15);
  return v7;
}

```

## disassembly

```asm
0x1800103dc  mov     rax, rsp
0x1800103df  mov     [rax+8], rbx
0x1800103e3  mov     [rax+10h], rbp
0x1800103e7  push    rdi
0x1800103e8  push    r14
0x1800103ea  push    r15
0x1800103ec  sub     rsp, 30h
0x1800103f0  mov     rbx, rcx
0x1800103f3  xor     r15d, r15d
0x1800103f6  mov     rcx, rdx
0x1800103f9  mov     [rax+18h], r15
0x1800103fd  mov     [rax+20h], r15
0x180010401  mov     r14, rdx
0x180010404  call    AslFileMappingEnsure
0x180010409  mov     edi, eax
0x18001040b  test    eax, eax
0x18001040d  jns     short loc_180010433
0x18001040f  lea     r9, aAslfilemapping_2; "AslFileMappingEnsure failed [%x]"
0x180010416  mov     r8d, 0DA1h
0x18001041c  lea     rdx, aAslpfilegethea_1; "AslpFileGetHeaderAttributesNE"
0x180010423  mov     [rsp+48h+var_28], eax
0x180010427  mov     ecx, 1
0x18001042c  call    AslLogCallPrintf
0x180010431  jmp     short loc_18001044B
0x180010433  cmp     dword ptr [r14+38h], 5
0x180010438  jz      short loc_180010461
0x18001043a  or      dword ptr [rbx+298h], 2
0x180010441  or      dword ptr [rbx+2B8h], 2
0x180010448  mov     edi, r15d
0x18001044b  mov     rbx, [rsp+48h+arg_0]
0x180010450  mov     eax, edi
0x180010452  mov     rbp, [rsp+48h+arg_8]
0x180010457  add     rsp, 30h
0x18001045b  pop     r15
0x18001045d  pop     r14
0x18001045f  pop     rdi
0x180010460  retn
0x180010461  or      dword ptr [rbx+258h], 2
0x180010468  lea     rcx, [rsp+48h+arg_10]
0x18001046d  or      dword ptr [rbx+278h], 2
0x180010474  mov     rdx, r14
0x180010477  or      dword ptr [rbx+2D8h], 2
0x18001047e  or      dword ptr [rbx+38h], 2
0x180010482  or      dword ptr [rbx+338h], 2
0x180010489  or      dword ptr [rbx+2F8h], 2
0x180010490  or      dword ptr [rbx+3B8h], 2
0x180010497  or      dword ptr [rbx+3D8h], 2
0x18001049e  or      dword ptr [rbx+3F8h], 2
0x1800104a5  or      dword ptr [rbx+438h], 2
0x1800104ac  call    AslpFileGet16BitDescription
0x1800104b1  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800104b5  test    eax, eax
0x1800104b7  js      short loc_180010509
0x1800104b9  mov     rcx, [rsp+48h+arg_10]
0x1800104be  call    AslStringXmlSanitize
0x1800104c3  mov     edi, eax
0x1800104c5  test    eax, eax
0x1800104c7  jns     short loc_1800104DB
0x1800104c9  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x1800104d0  mov     r8d, 0DC5h
0x1800104d6  jmp     loc_18001041C
0x1800104db  mov     dword ptr [rbx+280h], 4
0x1800104e5  mov     rax, rbp
0x1800104e8  inc     rax
0x1800104eb  cmp     [rcx+rax*2], r15w
0x1800104f0  jnz     short loc_1800104E8
0x1800104f2  or      dword ptr [rbx+298h], 5
0x1800104f9  mov     [rbx+288h], rax
0x180010500  mov     [rbx+290h], rcx
0x180010507  jmp     short loc_180010510
0x180010509  or      dword ptr [rbx+298h], 2
0x180010510  mov     rdx, r14
0x180010513  lea     rcx, [rsp+48h+arg_18]
0x180010518  call    AslpFileGet16BitModuleName
0x18001051d  test    eax, eax
0x18001051f  js      loc_180010441
0x180010525  mov     rcx, [rsp+48h+arg_18]
0x18001052a  call    AslStringXmlSanitize
0x18001052f  mov     edi, eax
0x180010531  test    eax, eax
0x180010533  jns     short loc_180010547
0x180010535  lea     r9, aAslstringxmlsa; "AslStringXmlSanitize failed [%x]"
0x18001053c  mov     r8d, 0DDAh
0x180010542  jmp     loc_18001041C
0x180010547  mov     dword ptr [rbx+2A0h], 4
0x180010551  inc     rbp
0x180010554  cmp     [rcx+rbp*2], r15w
0x180010559  jnz     short loc_180010551
0x18001055b  or      dword ptr [rbx+2B8h], 5
0x180010562  mov     [rbx+2A8h], rbp
0x180010569  mov     [rbx+2B0h], rcx
0x180010570  jmp     loc_180010448
```
