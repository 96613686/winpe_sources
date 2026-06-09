# LipsIpsecFilterLayerCreate

- ea: `0x18004a530`
- end: `0x18004a7a4`
- name: `LipsIpsecFilterLayerCreate`
- size: `628`
- prototype: `__int64 __fastcall(__int64, _OWORD *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004a228`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004a530`
- `0x18004a7ac`
- `0x18004b410`
- `0x18004b5b8`

## string_xrefs

- `0x18004a77d`: `LipsIpsecFilterLayerCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecFilterLayerCreate(__int64 a1, _OWORD *a2, int a3, _QWORD *a4)
{
  __int64 v4; // rsi
  unsigned int v5; // r14d
  const GUID *v6; // rdi
  int v11; // ecx
  __int64 v12; // rcx
  BOOL v13; // edx
  int v14; // r8d
  int v15; // ecx
  BOOL v16; // ecx
  char *v17; // rcx
  LPVOID v19[2]; // [rsp+50h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  v5 = 0;
  v6 = 0;
  v19[0] = 0;
  v21 = 0;
  *a4 = 0;
  switch ( a3 )
  {
    case 0:
      if ( *(_DWORD *)(a1 + 156) != 4 || *(_DWORD *)(a1 + 144) != 3 && *(_DWORD *)(a1 + 148) != 3 )
        goto LABEL_44;
      v11 = 72;
      goto LABEL_33;
    case 1:
      if ( *(_DWORD *)(a1 + 156) != 4 )
        goto LABEL_44;
      v20 = 1;
      goto LABEL_27;
    case 2:
      if ( *(_DWORD *)(a1 + 156) != 8 )
        goto LABEL_44;
      v20 = 2;
LABEL_27:
      LipsIpsecFilterOptionsGet(a1, &v21, &v20);
      goto LABEL_28;
  }
  if ( a3 != 3 )
  {
    if ( a3 == 4 )
    {
      v4 = 2;
      v11 = 416;
    }
    else
    {
      if ( a3 != 5 )
        goto LABEL_44;
      v11 = 656;
    }
    v6 = &FWPM_SUBLAYER_LIPS;
    goto LABEL_33;
  }
  v12 = *(_QWORD *)(a1 + 184);
  v13 = 0;
  v14 = 0;
  if ( v12 )
    v13 = (*(_BYTE *)(v12 + 32) & 4) != 0;
  v15 = *(_DWORD *)(a1 + 144);
  if ( v15 == 3 )
  {
    v16 = *(_DWORD *)(a1 + 148) == 3;
  }
  else if ( v15 == 1 )
  {
    v16 = 0;
    if ( *(_DWORD *)(a1 + 148) == 1 )
      v14 = 1;
  }
  else
  {
    v16 = 0;
  }
  if ( *(_DWORD *)(a1 + 156) == 4 && (v13 && v16 || v14) )
  {
    v20 = 128;
    LipsIpsecFilterOptionsGet(a1, &v21, &v20);
    v6 = &FWPM_SUBLAYER_LIPS;
LABEL_28:
    v11 = v20;
    v4 = v21;
LABEL_33:
    v5 = LipsFilterCreate(v11, a1 + 40, a1 + 80, a1 + 128, a1 + 136, *(_BYTE *)(a1 + 124), 0, v4, v19);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6aaaced537c833a4c6f456c9c9a48105_Traceguids, v5);
    }
    else
    {
      v17 = (char *)v19[0];
      if ( !v4 && a2 && !a3 )
      {
        *((_DWORD *)v19[0] + 8) |= 4u;
        *(_OWORD *)(v17 + 152) = *a2;
      }
      *((_QWORD *)v17 + 2) = *(_QWORD *)(a1 + 24);
      *((_QWORD *)v17 + 3) = *(_QWORD *)(a1 + 24);
      if ( v6 )
        *((GUID *)v17 + 5) = *v6;
      *a4 = v17;
      v19[0] = 0;
    }
  }
LABEL_44:
  LipsFilterDestroy(v19);
  if ( v5 )
    return LipsReportError(v5, "LipsIpsecFilterLayerCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004a530  mov     [rsp-38h+arg_0], rbx
0x18004a535  push    rbp
0x18004a536  push    rsi
0x18004a537  push    rdi
0x18004a538  push    r12
0x18004a53a  push    r13
0x18004a53c  push    r14
0x18004a53e  push    r15
0x18004a540  mov     rbp, rsp
0x18004a543  sub     rsp, 60h
0x18004a547  xor     esi, esi
0x18004a549  xor     r14d, r14d
0x18004a54c  xor     edi, edi
0x18004a54e  mov     [rbp+var_10], r14
0x18004a552  mov     [rbp+arg_18], rsi
0x18004a556  mov     rbx, rcx
0x18004a559  mov     [r9], rsi
0x18004a55c  mov     r13, r9
0x18004a55f  mov     r15d, r8d
0x18004a562  mov     r12, rdx
0x18004a565  mov     ecx, r8d
0x18004a568  test    r8d, r8d
0x18004a56b  jz      loc_18004A680
0x18004a571  sub     ecx, 1
0x18004a574  jz      loc_18004A652
0x18004a57a  sub     ecx, 1
0x18004a57d  jz      loc_18004A63B
0x18004a583  sub     ecx, 1
0x18004a586  jz      short loc_18004A5B3
0x18004a588  sub     ecx, 1
0x18004a58b  jz      short loc_18004A5A7
0x18004a58d  cmp     ecx, 1
0x18004a590  jnz     loc_18004A76B
0x18004a596  mov     ecx, 290h
0x18004a59b  lea     rdi, FWPM_SUBLAYER_LIPS
0x18004a5a2  jmp     loc_18004A6A8
0x18004a5a7  mov     esi, 2
0x18004a5ac  mov     ecx, 1A0h
0x18004a5b1  jmp     short loc_18004A59B
0x18004a5b3  mov     rcx, [rbx+0B8h]
0x18004a5ba  xor     edx, edx
0x18004a5bc  xor     r8d, r8d
0x18004a5bf  lea     eax, [rdx+1]
0x18004a5c2  test    rcx, rcx
0x18004a5c5  jz      short loc_18004A5CE
0x18004a5c7  test    byte ptr [rcx+20h], 4
0x18004a5cb  cmovnz  edx, eax
0x18004a5ce  mov     ecx, [rbx+90h]
0x18004a5d4  cmp     ecx, 3
0x18004a5d7  jnz     short loc_18004A5E8
0x18004a5d9  xor     ecx, ecx
0x18004a5db  cmp     dword ptr [rbx+94h], 3
0x18004a5e2  jnz     short loc_18004A5FD
0x18004a5e4  mov     ecx, eax
0x18004a5e6  jmp     short loc_18004A5FD
0x18004a5e8  cmp     ecx, eax
0x18004a5ea  jnz     short loc_18004A5FB
0x18004a5ec  xor     ecx, ecx
0x18004a5ee  cmp     [rbx+94h], eax
0x18004a5f4  jnz     short loc_18004A5FD
0x18004a5f6  mov     r8d, eax
0x18004a5f9  jmp     short loc_18004A5FD
0x18004a5fb  xor     ecx, ecx
0x18004a5fd  cmp     dword ptr [rbx+9Ch], 4
0x18004a604  jnz     loc_18004A76B
0x18004a60a  test    edx, edx
0x18004a60c  jz      short loc_18004A612
0x18004a60e  test    ecx, ecx
0x18004a610  jnz     short loc_18004A61B
0x18004a612  test    r8d, r8d
0x18004a615  jz      loc_18004A76B
0x18004a61b  lea     r8, [rbp+arg_10]
0x18004a61f  mov     [rbp+arg_10], 80h
0x18004a626  lea     rdx, [rbp+arg_18]
0x18004a62a  mov     rcx, rbx
0x18004a62d  call    LipsIpsecFilterOptionsGet
0x18004a632  lea     rdi, FWPM_SUBLAYER_LIPS
0x18004a639  jmp     short loc_18004A677
0x18004a63b  cmp     dword ptr [rbx+9Ch], 8
0x18004a642  jnz     loc_18004A76B
0x18004a648  mov     esi, 2
0x18004a64d  mov     [rbp+arg_10], esi
0x18004a650  jmp     short loc_18004A667
0x18004a652  cmp     dword ptr [rbx+9Ch], 4
0x18004a659  jnz     loc_18004A76B
0x18004a65f  mov     eax, 1
0x18004a664  mov     [rbp+arg_10], eax
0x18004a667  lea     r8, [rbp+arg_10]
0x18004a66b  mov     rcx, rbx
0x18004a66e  lea     rdx, [rbp+arg_18]
0x18004a672  call    LipsIpsecFilterOptionsGet
0x18004a677  mov     ecx, [rbp+arg_10]
0x18004a67a  mov     rsi, [rbp+arg_18]
0x18004a67e  jmp     short loc_18004A6A8
0x18004a680  cmp     dword ptr [rbx+9Ch], 4
0x18004a687  jnz     loc_18004A76B
0x18004a68d  cmp     dword ptr [rbx+90h], 3
0x18004a694  jz      short loc_18004A6A3
0x18004a696  cmp     dword ptr [rbx+94h], 3
0x18004a69d  jnz     loc_18004A76B
0x18004a6a3  mov     ecx, 48h ; 'H'
0x18004a6a8  xor     eax, eax
0x18004a6aa  lea     r11, [rbp+var_10]
0x18004a6ae  mov     [rsp+60h+var_20], r11
0x18004a6b3  lea     r10, [rbx+88h]
0x18004a6ba  mov     [rsp+60h+var_28], rsi
0x18004a6bf  lea     r9, [rbx+80h]
0x18004a6c6  mov     [rsp+60h+var_30], ax
0x18004a6cb  lea     r8, [rbx+50h]
0x18004a6cf  mov     al, [rbx+7Ch]
0x18004a6d2  lea     rdx, [rbx+28h]
0x18004a6d6  mov     [rsp+60h+var_38], al
0x18004a6da  mov     [rsp+60h+var_40], r10
0x18004a6df  call    LipsFilterCreate
0x18004a6e4  mov     r14d, eax
0x18004a6e7  test    eax, eax
0x18004a6e9  jz      short loc_18004A71E
0x18004a6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a6f2  lea     rax, WPP_GLOBAL_Control
0x18004a6f9  cmp     rcx, rax
0x18004a6fc  jz      short loc_18004A76B
0x18004a6fe  test    byte ptr [rcx+1Ch], 10h
0x18004a702  jz      short loc_18004A76B
0x18004a704  mov     rcx, [rcx+10h]
0x18004a708  lea     r8, WPP_6aaaced537c833a4c6f456c9c9a48105_Traceguids
0x18004a70f  mov     edx, 11h
0x18004a714  mov     r9d, r14d
0x18004a717  call    WPP_SF_d
0x18004a71c  jmp     short loc_18004A76B
0x18004a71e  mov     rcx, [rbp+var_10]
0x18004a722  test    rsi, rsi
0x18004a725  jnz     short loc_18004A742
0x18004a727  test    r12, r12
0x18004a72a  jz      short loc_18004A742
0x18004a72c  test    r15d, r15d
0x18004a72f  jnz     short loc_18004A742
0x18004a731  or      dword ptr [rcx+20h], 4
0x18004a735  movups  xmm0, xmmword ptr [r12]
0x18004a73a  movdqu  xmmword ptr [rcx+98h], xmm0
0x18004a742  mov     rax, [rbx+18h]
0x18004a746  mov     [rcx+10h], rax
0x18004a74a  mov     rax, [rbx+18h]
0x18004a74e  mov     [rcx+18h], rax
0x18004a752  test    rdi, rdi
0x18004a755  jz      short loc_18004A75F
0x18004a757  movups  xmm0, xmmword ptr [rdi]
0x18004a75a  movdqu  xmmword ptr [rcx+50h], xmm0
0x18004a75f  mov     [r13+0], rcx
0x18004a763  mov     [rbp+var_10], 0
0x18004a76b  lea     rcx, [rbp+var_10]
0x18004a76f  call    LipsFilterDestroy
0x18004a774  test    r14d, r14d
0x18004a777  jnz     short loc_18004A77D
0x18004a779  xor     eax, eax
0x18004a77b  jmp     short loc_18004A78C
0x18004a77d  lea     rdx, aLipsipsecfilte; "LipsIpsecFilterLayerCreate"
0x18004a784  mov     ecx, r14d
0x18004a787  call    LipsReportError
0x18004a78c  mov     rbx, [rsp+60h+arg_0]
0x18004a794  add     rsp, 60h
0x18004a798  pop     r15
0x18004a79a  pop     r14
0x18004a79c  pop     r13
0x18004a79e  pop     r12
0x18004a7a0  pop     rdi
0x18004a7a1  pop     rsi
0x18004a7a2  pop     rbp
0x18004a7a3  retn
```
