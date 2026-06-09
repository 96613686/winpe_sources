# KerbUnpackData

- ea: `0x180011150`
- end: `0x1800113ea`
- name: `KerbUnpackData`
- size: `666`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `55`
- callee_count: `4`
- tags: ``

## callers

- `0x1800030fc`
- `0x1800050e4`
- `0x1800100d0`
- `0x180010b64`
- `0x180010c60`
- `0x180011064`
- `0x180014380`
- `0x180019678`
- `0x180035e80`
- `0x18003c830`
- `0x18003d3f0`
- `0x18003e9d8`
- `0x180041758`
- `0x180042470`
- `0x1800428e4`
- `0x180042a40`
- `0x180059e18`
- `0x180078db0`
- `0x1800816e0`
- `0x180088424`
- `0x18008868c`
- `0x18008e4f4`
- `0x18009a738`
- `0x18009c85c`
- `0x1800a6410`
- `0x1800a79fc`
- `0x1800a7b80`
- `0x1800a863c`
- `0x1800aa2f4`
- `0x1800ac3dc`
- `0x1800ad18c`
- `0x1800b1618`
- `0x1800ba0a4`
- `0x1800baae4`
- `0x1800bf7b8`
- `0x1800bf958`
- `0x1800bfc00`
- `0x1800c0948`
- `0x1800c2dec`
- `0x1800c2fbc`
- `0x1800c6f80`
- `0x1800c6fcc`
- `0x1800c701c`
- `0x1800c706c`
- `0x1800c78b4`
- `0x1800c7eec`
- `0x1800c82b0`
- `0x1800ca850`
- `0x1800cabf0`
- `0x1800d1564`

## callees

- `0x180011150`
- `0x18006ccec`
- `0x18006d73c`
- `0x180077804`

## import_xrefs

- `MSASN1!ASN1_CreateModule` at `0x1800111e6`
- `MSASN1!ASN1_CreateModule` at `0x1800111e6`
- `MSASN1!ASN1_CloseDecoder` at `0x18001124a`
- `MSASN1!ASN1_CloseDecoder` at `0x18001124a`
- `MSASN1!ASN1_CreateDecoder` at `0x180011206`
- `MSASN1!ASN1_CreateDecoder` at `0x180011206`
- `MSASN1!ASN1_Decode` at `0x180011234`
- `MSASN1!ASN1_Decode` at `0x180011234`

## pseudocode

```c
__int64 __fastcall KerbUnpackData(__int64 a1, int a2, unsigned int a3, _QWORD *a4)
{
  __int64 Module; // rax
  unsigned int Decoder; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  int v12; // eax
  unsigned int v13; // esi
  PVOID *v15; // rcx
  PVOID *v16; // rcx
  _QWORD v17[9]; // [rsp+50h] [rbp-48h] BYREF

  v17[0] = 0;
  if ( !a2 || !a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids);
    return 60;
  }
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(
               0x10000,
               1024,
               4096,
               81,
               off_1800F62D0,
               off_1800F6040,
               off_1800F6560,
               qword_1800FE8B0,
               895644267);
    KRB5_Module = Module;
  }
  Decoder = ASN1_CreateDecoder(Module, v17, 0, 0, 0);
  if ( Decoder )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, Decoder);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 )
      {
        v11 = 60;
        WPP_SF_D(v16[2], 39, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 60);
        return v11;
      }
    }
    return 60;
  }
  v10 = v17[0];
  v11 = 0;
  *a4 = 0;
  v12 = ASN1_Decode(v10, a4, a3, 8, a1, a2);
  v13 = v12;
  if ( v12 >= 0 )
    goto LABEL_7;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
      (unsigned int)v12);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 == -1009 )
    goto LABEL_19;
  if ( v13 != -1011 )
  {
    if ( v13 != -1002 )
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 )
        WPP_SF_d(v15[2], 42, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v13);
      goto LABEL_17;
    }
LABEL_19:
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
      WPP_SF_d(v15[2], 41, &WPP_c655c859b2e13de8f31f421519d58447_Traceguids, a3);
    v11 = -2147483647;
    goto LABEL_18;
  }
LABEL_17:
  v11 = 60;
LABEL_18:
  *a4 = 0;
LABEL_7:
  if ( v17[0] )
    ASN1_CloseDecoder();
  return v11;
}

```

## disassembly

```asm
0x180011150  push    rbx
0x180011152  push    rbp
0x180011153  push    rsi
0x180011154  push    rdi
0x180011155  push    r14
0x180011157  push    r15
0x180011159  sub     rsp, 68h
0x18001115d  xor     r15d, r15d
0x180011160  mov     r14, r9
0x180011163  mov     [rsp+98h+var_48], r15
0x180011168  mov     ebp, r8d
0x18001116b  mov     ebx, edx
0x18001116d  mov     rsi, rcx
0x180011170  test    edx, edx
0x180011172  jz      loc_18001125F
0x180011178  test    rcx, rcx
0x18001117b  jz      loc_18001125F
0x180011181  cmp     cs:?fKRB5ModuleStarted@@3HA, r15d; int fKRB5ModuleStarted
0x180011188  jnz     loc_1800112C8
0x18001118e  mov     [rsp+98h+var_58], 3562726Bh
0x180011196  lea     rax, qword_1800FE8B0
0x18001119d  mov     [rsp+98h+var_60], rax
0x1800111a2  mov     edx, 400h
0x1800111a7  lea     rax, off_1800F6560
0x1800111ae  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x1800111b8  mov     [rsp+98h+var_68], rax
0x1800111bd  mov     ecx, 10000h
0x1800111c2  lea     rax, off_1800F6040
0x1800111c9  mov     r9d, 51h ; 'Q'
0x1800111cf  mov     [rsp+98h+var_70], rax
0x1800111d4  mov     r8d, 1000h
0x1800111da  lea     rax, off_1800F62D0
0x1800111e1  mov     [rsp+98h+var_78], rax
0x1800111e6  call    cs:__imp_ASN1_CreateModule
0x1800111ec  mov     cs:KRB5_Module, rax
0x1800111f3  xor     r9d, r9d
0x1800111f6  mov     [rsp+98h+var_78], r15
0x1800111fb  xor     r8d, r8d
0x1800111fe  lea     rdx, [rsp+98h+var_48]
0x180011203  mov     rcx, rax
0x180011206  call    cs:__imp_ASN1_CreateDecoder
0x18001120c  test    eax, eax
0x18001120e  jnz     loc_180011301
0x180011214  mov     rcx, [rsp+98h+var_48]
0x180011219  mov     r9d, 8
0x18001121f  mov     dword ptr [rsp+98h+var_70], ebx
0x180011223  mov     r8d, ebp
0x180011226  mov     rdx, r14
0x180011229  mov     [rsp+98h+var_78], rsi
0x18001122e  mov     edi, r15d
0x180011231  mov     [r14], r15
0x180011234  call    cs:__imp_ASN1_Decode
0x18001123a  mov     esi, eax
0x18001123c  test    eax, eax
0x18001123e  js      short loc_18001127D
0x180011240  mov     rcx, [rsp+98h+var_48]
0x180011245  test    rcx, rcx
0x180011248  jz      short loc_180011250
0x18001124a  call    cs:__imp_ASN1_CloseDecoder
0x180011250  mov     eax, edi
0x180011252  add     rsp, 68h
0x180011256  pop     r15
0x180011258  pop     r14
0x18001125a  pop     rdi
0x18001125b  pop     rsi
0x18001125c  pop     rbp
0x18001125d  pop     rbx
0x18001125e  retn
0x18001125f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011266  lea     rbx, WPP_GLOBAL_Control
0x18001126d  cmp     rcx, rbx
0x180011270  jnz     loc_1800113C6
0x180011276  mov     edi, 3Ch ; '<'
0x18001127b  jmp     short loc_180011250
0x18001127d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011284  lea     rbx, WPP_GLOBAL_Control
0x18001128b  cmp     rcx, rbx
0x18001128e  jz      short loc_18001129A
0x180011290  test    byte ptr [rcx+1Ch], 4
0x180011294  jnz     loc_18001133F
0x18001129a  cmp     esi, 0FFFFFC0Fh
0x1800112a0  jz      short loc_1800112B8
0x1800112a2  cmp     esi, 0FFFFFC0Dh
0x1800112a8  jnz     loc_180011363
0x1800112ae  mov     edi, 3Ch ; '<'
0x1800112b3  mov     [r14], r15
0x1800112b6  jmp     short loc_180011240
0x1800112b8  cmp     rcx, rbx
0x1800112bb  jnz     loc_18001139F
0x1800112c1  mov     edi, 80000001h
0x1800112c6  jmp     short loc_1800112B3
0x1800112c8  mov     rax, cs:KRB5_Module
0x1800112cf  jmp     loc_1800111F3
0x1800112d4  cmp     rcx, rbx
0x1800112d7  jz      short loc_180011276
0x1800112d9  test    byte ptr [rcx+1Ch], 1
0x1800112dd  jz      short loc_180011276
0x1800112df  mov     rcx, [rcx+10h]
0x1800112e3  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800112ea  mov     edi, 3Ch ; '<'
0x1800112ef  mov     edx, 27h ; '''
0x1800112f4  mov     r9d, edi
0x1800112f7  call    WPP_SF_D
0x1800112fc  jmp     loc_180011250
0x180011301  mov     rcx, cs:WPP_GLOBAL_Control
0x180011308  lea     rbx, WPP_GLOBAL_Control
0x18001130f  cmp     rcx, rbx
0x180011312  jz      loc_180011276
0x180011318  test    byte ptr [rcx+1Ch], 1
0x18001131c  jz      short loc_1800112D4
0x18001131e  mov     rcx, [rcx+10h]
0x180011322  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180011329  mov     edx, 24h ; '$'
0x18001132e  mov     r9d, eax
0x180011331  call    WPP_SF_D
0x180011336  mov     rcx, cs:WPP_GLOBAL_Control
0x18001133d  jmp     short loc_1800112D4
0x18001133f  mov     rcx, [rcx+10h]
0x180011343  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001134a  mov     edx, 28h ; '('
0x18001134f  mov     r9d, esi
0x180011352  call    WPP_SF_D
0x180011357  mov     rcx, cs:WPP_GLOBAL_Control
0x18001135e  jmp     loc_18001129A
0x180011363  cmp     esi, 0FFFFFC16h
0x180011369  jz      loc_1800112B8
0x18001136f  cmp     rcx, rbx
0x180011372  jz      loc_1800112AE
0x180011378  test    byte ptr [rcx+1Ch], 1
0x18001137c  jz      loc_1800112AE
0x180011382  mov     rcx, [rcx+10h]
0x180011386  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18001138d  mov     edx, 2Ah ; '*'
0x180011392  mov     r9d, esi
0x180011395  call    WPP_SF_d
0x18001139a  jmp     loc_1800112AE
0x18001139f  test    byte ptr [rcx+1Ch], 4
0x1800113a3  jz      loc_1800112C1
0x1800113a9  mov     rcx, [rcx+10h]
0x1800113ad  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800113b4  mov     edx, 29h ; ')'
0x1800113b9  mov     r9d, ebp
0x1800113bc  call    WPP_SF_d
0x1800113c1  jmp     loc_1800112C1
0x1800113c6  test    byte ptr [rcx+1Ch], 1
0x1800113ca  jz      loc_180011276
0x1800113d0  mov     rcx, [rcx+10h]
0x1800113d4  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800113db  mov     edx, 26h ; '&'
0x1800113e0  call    WPP_SF_
0x1800113e5  jmp     loc_180011276
```
