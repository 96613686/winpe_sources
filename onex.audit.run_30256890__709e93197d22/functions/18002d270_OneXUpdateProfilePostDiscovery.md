# OneXUpdateProfilePostDiscovery

- ea: `0x18002d270`
- end: `0x18002d4e6`
- name: `OneXUpdateProfilePostDiscovery`
- size: `630`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180004280`
- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x180025740`
- `0x18002d270`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18002d3de`
- `MobileNetworking!SetBufferAndLength` at `0x18002d3de`
- `MobileNetworking!FreeMemory` at `0x18002d498`
- `MobileNetworking!FreeMemory` at `0x18002d498`

## string_xrefs

- `0x18002d48d`: `OneXUpdateProfilePostDiscovery`

## pseudocode

```c
__int64 __fastcall OneXUpdateProfilePostDiscovery(int a1, unsigned int a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  _QWORD *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r9
  _QWORD *v13; // rdi
  unsigned int v14; // eax
  int v16; // [rsp+30h] [rbp-10h] BYREF
  _DWORD *v17; // [rsp+38h] [rbp-8h] BYREF
  int v18; // [rsp+70h] [rbp+30h] BYREF

  v17 = 0;
  v16 = 0;
  v18 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 208, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v9[7], 209, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( a1 >= 2 )
  {
    v10 = 87;
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 68) & 1) == 0 )
      goto LABEL_28;
    v11 = 210;
    v12 = 87;
LABEL_11:
    WPP_SF_d(v9[7], v11, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
LABEL_28:
    FreeMemory(&v17, "OneXUpdateProfilePostDiscovery", 2222);
    goto LABEL_29;
  }
  if ( !a3 || !a2 || (v13 = a5) == 0 || !a4 )
  {
    v10 = 87;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 68) & 1) != 0 )
      WPP_SF_(v9[7], 211, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
    goto LABEL_28;
  }
  v10 = OneXValidateProfile(a2, a3, (unsigned int)a1, &v18);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 7), 212, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10, v18);
    goto LABEL_28;
  }
  *a4 = 0;
  *v13 = 0;
  v14 = SetBufferAndLength(&v17, &v16, a3, a2);
  v10 = v14;
  if ( v14 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_28;
    v11 = 213;
    v12 = v14;
    goto LABEL_11;
  }
  v17[2] &= ~0x80u;
  v17[10] = -1;
  v17[2] &= ~0x10u;
  v17[7] = -1;
  v17[2] &= ~0x20u;
  v17[8] = -1;
  v17[2] &= ~1u;
  v17[3] = 0;
  *v13 = v17;
  *a4 = v16;
LABEL_29:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 214, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18002d270  mov     [rsp-28h+arg_8], rbx
0x18002d275  mov     [rsp-28h+arg_10], rsi
0x18002d27a  push    rbp
0x18002d27b  push    rdi
0x18002d27c  push    r13
0x18002d27e  push    r14
0x18002d280  push    r15
0x18002d282  mov     rbp, rsp
0x18002d285  sub     rsp, 40h
0x18002d289  mov     r15, r9
0x18002d28c  mov     [rbp+var_8], 0
0x18002d294  mov     rsi, r8
0x18002d297  mov     [rbp+var_10], 0
0x18002d29e  mov     r14d, edx
0x18002d2a1  mov     [rbp+arg_0], 0
0x18002d2a8  mov     ebx, ecx
0x18002d2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2b1  lea     r13, WPP_GLOBAL_Control
0x18002d2b8  cmp     rcx, r13
0x18002d2bb  jz      short loc_18002D30C
0x18002d2bd  test    dword ptr [rcx+44h], 800h
0x18002d2c4  jz      short loc_18002D2E2
0x18002d2c6  mov     rcx, [rcx+38h]
0x18002d2ca  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002d2d1  mov     edx, 0D0h
0x18002d2d6  call    WPP_SF_
0x18002d2db  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2e2  cmp     rcx, r13
0x18002d2e5  jz      short loc_18002D30C
0x18002d2e7  test    dword ptr [rcx+44h], 100h
0x18002d2ee  jz      short loc_18002D30C
0x18002d2f0  mov     rcx, [rcx+38h]
0x18002d2f4  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002d2fb  mov     edx, 0D1h
0x18002d300  call    WPP_SF_
0x18002d305  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d30c  cmp     ebx, 2
0x18002d30f  jl      short loc_18002D344
0x18002d311  mov     ebx, 57h ; 'W'
0x18002d316  cmp     rcx, r13
0x18002d319  jz      loc_18002D487
0x18002d31f  test    byte ptr [rcx+44h], 1
0x18002d323  jz      loc_18002D487
0x18002d329  lea     edx, [rbx+7Bh]
0x18002d32c  mov     r9d, ebx
0x18002d32f  mov     rcx, [rcx+38h]
0x18002d333  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002d33a  call    WPP_SF_d
0x18002d33f  jmp     loc_18002D487
0x18002d344  test    rsi, rsi
0x18002d347  jz      loc_18002D464
0x18002d34d  test    r14d, r14d
0x18002d350  jz      loc_18002D464
0x18002d356  mov     rdi, [rbp+arg_20]
0x18002d35a  test    rdi, rdi
0x18002d35d  jz      loc_18002D464
0x18002d363  test    r15, r15
0x18002d366  jz      loc_18002D464
0x18002d36c  lea     r9, [rbp+arg_0]
0x18002d370  mov     r8d, ebx
0x18002d373  mov     rdx, rsi
0x18002d376  mov     ecx, r14d
0x18002d379  call    OneXValidateProfile
0x18002d37e  mov     ebx, eax
0x18002d380  test    eax, eax
0x18002d382  jz      short loc_18002D3C2
0x18002d384  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d38b  cmp     rcx, r13
0x18002d38e  jz      loc_18002D487
0x18002d394  test    byte ptr [rcx+44h], 1
0x18002d398  jz      loc_18002D487
0x18002d39e  mov     eax, [rbp+arg_0]
0x18002d3a1  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002d3a8  mov     rcx, [rcx+38h]
0x18002d3ac  mov     edx, 0D4h
0x18002d3b1  mov     r9d, ebx
0x18002d3b4  mov     [rsp+40h+var_20], eax
0x18002d3b8  call    WPP_SF_dD
0x18002d3bd  jmp     loc_18002D487
0x18002d3c2  mov     dword ptr [r15], 0
0x18002d3c9  lea     rdx, [rbp+var_10]
0x18002d3cd  mov     r9d, r14d
0x18002d3d0  mov     qword ptr [rdi], 0
0x18002d3d7  mov     r8, rsi
0x18002d3da  lea     rcx, [rbp+var_8]
0x18002d3de  call    cs:__imp_SetBufferAndLength
0x18002d3e4  mov     ebx, eax
0x18002d3e6  test    eax, eax
0x18002d3e8  jz      short loc_18002D411
0x18002d3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d3f1  cmp     rcx, r13
0x18002d3f4  jz      loc_18002D487
0x18002d3fa  test    byte ptr [rcx+44h], 1
0x18002d3fe  jz      loc_18002D487
0x18002d404  mov     edx, 0D5h
0x18002d409  mov     r9d, eax
0x18002d40c  jmp     loc_18002D32F
0x18002d411  mov     rax, [rbp+var_8]
0x18002d415  or      ecx, 0FFFFFFFFh
0x18002d418  btr     dword ptr [rax+8], 7
0x18002d41d  mov     rax, [rbp+var_8]
0x18002d421  mov     [rax+28h], ecx
0x18002d424  mov     rax, [rbp+var_8]
0x18002d428  and     dword ptr [rax+8], 0FFFFFFEFh
0x18002d42c  mov     rax, [rbp+var_8]
0x18002d430  mov     [rax+1Ch], ecx
0x18002d433  mov     rax, [rbp+var_8]
0x18002d437  and     dword ptr [rax+8], 0FFFFFFDFh
0x18002d43b  mov     rax, [rbp+var_8]
0x18002d43f  mov     [rax+20h], ecx
0x18002d442  mov     rax, [rbp+var_8]
0x18002d446  and     dword ptr [rax+8], 0FFFFFFFEh
0x18002d44a  mov     rax, [rbp+var_8]
0x18002d44e  mov     dword ptr [rax+0Ch], 0
0x18002d455  mov     rax, [rbp+var_8]
0x18002d459  mov     [rdi], rax
0x18002d45c  mov     eax, [rbp+var_10]
0x18002d45f  mov     [r15], eax
0x18002d462  jmp     short loc_18002D49E
0x18002d464  mov     ebx, 57h ; 'W'
0x18002d469  cmp     rcx, r13
0x18002d46c  jz      short loc_18002D487
0x18002d46e  test    byte ptr [rcx+44h], 1
0x18002d472  jz      short loc_18002D487
0x18002d474  mov     rcx, [rcx+38h]
0x18002d478  lea     edx, [rbx+7Ch]
0x18002d47b  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002d482  call    WPP_SF_
0x18002d487  mov     r8d, 8AEh
0x18002d48d  lea     rdx, aOnexupdateprof_0; "OneXUpdateProfilePostDiscovery"
0x18002d494  lea     rcx, [rbp+var_8]
0x18002d498  call    cs:__imp_FreeMemory
0x18002d49e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4a5  cmp     rcx, r13
0x18002d4a8  jz      short loc_18002D4CB
0x18002d4aa  test    dword ptr [rcx+44h], 800h
0x18002d4b1  jz      short loc_18002D4CB
0x18002d4b3  mov     rcx, [rcx+38h]
0x18002d4b7  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18002d4be  mov     edx, 0D6h
0x18002d4c3  mov     r9d, ebx
0x18002d4c6  call    WPP_SF_D
0x18002d4cb  lea     r11, [rsp+40h+var_s0]
0x18002d4d0  mov     eax, ebx
0x18002d4d2  mov     rbx, [r11+38h]
0x18002d4d6  mov     rsi, [r11+40h]
0x18002d4da  mov     rsp, r11
0x18002d4dd  pop     r15
0x18002d4df  pop     r14
0x18002d4e1  pop     r13
0x18002d4e3  pop     rdi
0x18002d4e4  pop     rbp
0x18002d4e5  retn
```
