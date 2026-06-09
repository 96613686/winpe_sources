# SBackendEntryUserChanged

- ea: `0x180009be0`
- end: `0x18000a06e`
- name: `SBackendEntryUserChanged`
- size: `1166`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180005440`
- `0x180007f60`
- `0x180009060`
- `0x180009be0`
- `0x18000cf70`
- `0x180010ae0`
- `0x180010d40`
- `0x1800214f0`
- `0x1800258c8`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x180009d94`
- `MobileNetworking!SetBufferAndLength` at `0x180009d94`
- `MobileNetworking!AllocateMemory` at `0x180009ed5`
- `MobileNetworking!AllocateMemory` at `0x180009ed5`

## string_xrefs

- `0x180009ec4`: `OneXCreateEvent`

## pseudocode

```c
__int64 __fastcall SBackendEntryUserChanged(__int64 a1)
{
  __int64 v1; // rsi
  unsigned int v2; // r14d
  _QWORD *v3; // rcx
  __int64 result; // rax
  unsigned int v5; // ebx
  _BYTE *v6; // rcx
  unsigned int v7; // ebp
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  unsigned int v12; // ebp
  unsigned int v13; // edi
  unsigned int v14; // eax
  _QWORD *v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // [rsp+60h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 24);
  LODWORD(v17) = 0;
  v2 = *(_DWORD *)(v1 + 20);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 38, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(v1 + 2664) )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 0x10) != 0 )
    {
      WPP_SF_d(v3[7], 39, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
      v3 = WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(v1 + 2668) )
    {
      if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 0x10) != 0 )
        WPP_SF_d(v3[7], 40, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
      result = EapChangeUseWinlogonCreds(v1 + 2496, 1, &v17);
      v5 = result;
      if ( (_DWORD)result )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return result;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_77;
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2, result);
        goto LABEL_76;
      }
      if ( (_DWORD)v17
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 42, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
      }
      *(_DWORD *)(v1 + 2668) = 0;
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 68) & 0x10) != 0 )
      WPP_SF_d(v3[7], 43, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
    *(_DWORD *)(v1 + 2664) = 0;
    v3 = WPP_GLOBAL_Control;
  }
  v7 = *(_DWORD *)(*(_QWORD *)(v1 + 2496) + 20LL);
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
    WPP_SF_(v3[7], 64, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v8 = SetBufferAndLength(v1 + 2600, v1 + 2592, 0, 0);
  v9 = v8;
  if ( !v8 )
    goto LABEL_32;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_40;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v7, v8);
LABEL_32:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v10[7], 66, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 && v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
    WPP_SF_d(v10[7], 44, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
LABEL_40:
  if ( !(unsigned int)EapDeleteMasterUserData(v1 + 2496) )
  {
LABEL_44:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2);
    goto LABEL_44;
  }
LABEL_45:
  v12 = *(_DWORD *)(v1 + 20);
  v17 = 0;
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
  {
    WPP_SF_(v11[7], 18, WPP_c98c90d098d532f46181864aabb10d65_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  v13 = *(_DWORD *)(v1 + 20);
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x800) != 0 )
    WPP_SF_(v11[7], 10, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v14 = AllocateMemory(56, &v17, "OneXCreateEvent", 67);
  v5 = v14;
  if ( !v14 )
  {
    *(_DWORD *)(v17 + 16) = 24;
    *(_DWORD *)(v17 + 32) = 0;
    *(_QWORD *)(v17 + 24) = v1;
    goto LABEL_56;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
LABEL_68:
    OneXDeleteEvent(v17);
    goto LABEL_69;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v13, v14);
LABEL_56:
    v15 = WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v15[7], 12, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v5);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 68) & 1) != 0 )
      WPP_SF_dd(v15[7], 19, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v12, v5);
    goto LABEL_68;
  }
  v16 = QueueSupplicantEvent(v17);
  v5 = v16;
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 20, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v12, v16);
    goto LABEL_68;
  }
LABEL_69:
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 21, WPP_c98c90d098d532f46181864aabb10d65_Traceguids, v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !v5 )
    goto LABEL_77;
  if ( v6 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( (v6[68] & 1) == 0 )
      goto LABEL_77;
    WPP_SF_dd(*((_QWORD *)v6 + 7), 46, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v2, v5);
LABEL_76:
    v6 = WPP_GLOBAL_Control;
LABEL_77:
    if ( v6 != (_BYTE *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 17) & 0x800) != 0 )
      WPP_SF_D(*((_QWORD *)v6 + 7), 47, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180009be0  push    rsi
0x180009be2  push    rdi
0x180009be3  push    r12
0x180009be5  push    r14
0x180009be7  push    r15
0x180009be9  sub     rsp, 30h
0x180009bed  mov     rsi, [rcx+18h]
0x180009bf1  xor     r12d, r12d
0x180009bf4  mov     dword ptr [rsp+58h+arg_0], r12d
0x180009bf9  mov     r14d, [rsi+14h]
0x180009bfd  lea     rdi, [rsi+9C0h]
0x180009c04  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c0b  lea     r15, WPP_GLOBAL_Control
0x180009c12  cmp     rcx, r15
0x180009c15  jz      short loc_180009C3C
0x180009c17  test    dword ptr [rcx+44h], 800h
0x180009c1e  jz      short loc_180009C3C
0x180009c20  mov     rcx, [rcx+38h]
0x180009c24  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009c2b  mov     edx, 26h ; '&'
0x180009c30  call    WPP_SF_
0x180009c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c3c  mov     [rsp+58h+arg_8], rbx
0x180009c41  cmp     [rdi+0A8h], r12d
0x180009c48  jz      loc_180009D58
0x180009c4e  cmp     rcx, r15
0x180009c51  jz      short loc_180009C78
0x180009c53  test    byte ptr [rcx+44h], 10h
0x180009c57  jz      short loc_180009C78
0x180009c59  mov     rcx, [rcx+38h]
0x180009c5d  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009c64  mov     edx, 27h ; '''
0x180009c69  mov     r9d, r14d
0x180009c6c  call    WPP_SF_d
0x180009c71  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c78  cmp     [rdi+0ACh], r12d
0x180009c7f  jz      loc_180009D27
0x180009c85  cmp     rcx, r15
0x180009c88  jz      short loc_180009CA8
0x180009c8a  test    byte ptr [rcx+44h], 10h
0x180009c8e  jz      short loc_180009CA8
0x180009c90  mov     rcx, [rcx+38h]
0x180009c94  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009c9b  mov     edx, 28h ; '('
0x180009ca0  mov     r9d, r14d
0x180009ca3  call    WPP_SF_d
0x180009ca8  lea     r8, [rsp+58h+arg_0]
0x180009cad  mov     edx, 1
0x180009cb2  mov     rcx, rdi
0x180009cb5  call    EapChangeUseWinlogonCreds
0x180009cba  mov     ebx, eax
0x180009cbc  test    eax, eax
0x180009cbe  jz      short loc_180009CE8
0x180009cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cc7  cmp     rcx, r15
0x180009cca  jz      loc_18000A05C
0x180009cd0  test    byte ptr [rcx+44h], 1
0x180009cd4  jz      loc_18000A034
0x180009cda  mov     edx, 29h ; ')'
0x180009cdf  mov     [rsp+58h+var_38], eax
0x180009ce3  jmp     loc_18000A01A
0x180009ce8  cmp     dword ptr [rsp+58h+arg_0], r12d
0x180009ced  jz      short loc_180009D19
0x180009cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cf6  cmp     rcx, r15
0x180009cf9  jz      short loc_180009D19
0x180009cfb  test    byte ptr [rcx+44h], 4
0x180009cff  jz      short loc_180009D19
0x180009d01  mov     rcx, [rcx+38h]
0x180009d05  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009d0c  mov     edx, 2Ah ; '*'
0x180009d11  mov     r9d, r14d
0x180009d14  call    WPP_SF_d
0x180009d19  mov     [rdi+0ACh], r12d
0x180009d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d27  cmp     rcx, r15
0x180009d2a  jz      short loc_180009D4A
0x180009d2c  test    byte ptr [rcx+44h], 10h
0x180009d30  jz      short loc_180009D4A
0x180009d32  mov     rcx, [rcx+38h]
0x180009d36  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009d3d  mov     edx, 2Bh ; '+'
0x180009d42  mov     r9d, r14d
0x180009d45  call    WPP_SF_d
0x180009d4a  mov     [rdi+0A8h], r12d
0x180009d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d58  mov     rax, [rdi]
0x180009d5b  mov     [rsp+58h+arg_10], rbp
0x180009d60  mov     ebp, [rax+14h]
0x180009d63  cmp     rcx, r15
0x180009d66  jz      short loc_180009D86
0x180009d68  test    dword ptr [rcx+44h], 800h
0x180009d6f  jz      short loc_180009D86
0x180009d71  mov     rcx, [rcx+38h]
0x180009d75  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009d7c  mov     edx, 40h ; '@'
0x180009d81  call    WPP_SF_
0x180009d86  lea     rdx, [rdi+60h]
0x180009d8a  xor     r9d, r9d
0x180009d8d  lea     rcx, [rdi+68h]
0x180009d91  xor     r8d, r8d
0x180009d94  call    cs:__imp_SetBufferAndLength
0x180009d9a  mov     ebx, eax
0x180009d9c  test    eax, eax
0x180009d9e  jz      short loc_180009DCE
0x180009da0  mov     rcx, cs:WPP_GLOBAL_Control
0x180009da7  cmp     rcx, r15
0x180009daa  jz      short loc_180009E29
0x180009dac  test    byte ptr [rcx+44h], 1
0x180009db0  jz      short loc_180009DD5
0x180009db2  mov     rcx, [rcx+38h]
0x180009db6  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009dbd  mov     edx, 41h ; 'A'
0x180009dc2  mov     [rsp+58h+var_38], eax
0x180009dc6  mov     r9d, ebp
0x180009dc9  call    WPP_SF_dd
0x180009dce  mov     rcx, cs:WPP_GLOBAL_Control
0x180009dd5  cmp     rcx, r15
0x180009dd8  jz      short loc_180009E02
0x180009dda  test    dword ptr [rcx+44h], 800h
0x180009de1  jz      short loc_180009E02
0x180009de3  mov     rcx, [rcx+38h]
0x180009de7  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009dee  mov     edx, 42h ; 'B'
0x180009df3  mov     r9d, ebx
0x180009df6  call    WPP_SF_D
0x180009dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e02  test    ebx, ebx
0x180009e04  jz      short loc_180009E29
0x180009e06  cmp     rcx, r15
0x180009e09  jz      short loc_180009E29
0x180009e0b  test    byte ptr [rcx+44h], 1
0x180009e0f  jz      short loc_180009E29
0x180009e11  mov     rcx, [rcx+38h]
0x180009e15  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009e1c  mov     edx, 2Ch ; ','
0x180009e21  mov     r9d, r14d
0x180009e24  call    WPP_SF_d
0x180009e29  mov     rcx, rdi
0x180009e2c  call    EapDeleteMasterUserData
0x180009e31  test    eax, eax
0x180009e33  jz      short loc_180009E5F
0x180009e35  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e3c  cmp     rcx, r15
0x180009e3f  jz      short loc_180009E66
0x180009e41  test    byte ptr [rcx+44h], 1
0x180009e45  jz      short loc_180009E66
0x180009e47  mov     rcx, [rcx+38h]
0x180009e4b  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x180009e52  mov     edx, 2Dh ; '-'
0x180009e57  mov     r9d, r14d
0x180009e5a  call    WPP_SF_d
0x180009e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e66  mov     ebp, [rsi+14h]
0x180009e69  mov     [rsp+58h+arg_0], r12
0x180009e6e  cmp     rcx, r15
0x180009e71  jz      short loc_180009E98
0x180009e73  test    dword ptr [rcx+44h], 800h
0x180009e7a  jz      short loc_180009E98
0x180009e7c  mov     rcx, [rcx+38h]
0x180009e80  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x180009e87  mov     edx, 12h
0x180009e8c  call    WPP_SF_
0x180009e91  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e98  mov     edi, [rsi+14h]
0x180009e9b  cmp     rcx, r15
0x180009e9e  jz      short loc_180009EBE
0x180009ea0  test    dword ptr [rcx+44h], 800h
0x180009ea7  jz      short loc_180009EBE
0x180009ea9  mov     rcx, [rcx+38h]
0x180009ead  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180009eb4  mov     edx, 0Ah
0x180009eb9  call    WPP_SF_
0x180009ebe  mov     r9d, 43h ; 'C'
0x180009ec4  lea     r8, aOnexcreateeven; "OneXCreateEvent"
0x180009ecb  lea     rdx, [rsp+58h+arg_0]
0x180009ed0  mov     ecx, 38h ; '8'
0x180009ed5  call    cs:__imp_AllocateMemory
0x180009edb  mov     ebx, eax
0x180009edd  test    eax, eax
0x180009edf  jz      short loc_180009F15
0x180009ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ee8  cmp     rcx, r15
0x180009eeb  jz      loc_180009FBF
0x180009ef1  test    byte ptr [rcx+44h], 1
0x180009ef5  jz      short loc_180009F3A
0x180009ef7  mov     rcx, [rcx+38h]
0x180009efb  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180009f02  mov     edx, 0Bh
0x180009f07  mov     [rsp+58h+var_38], eax
0x180009f0b  mov     r9d, edi
0x180009f0e  call    WPP_SF_dd
0x180009f13  jmp     short loc_180009F33
0x180009f15  mov     rax, [rsp+58h+arg_0]
0x180009f1a  mov     dword ptr [rax+10h], 18h
0x180009f21  mov     rax, [rsp+58h+arg_0]
0x180009f26  mov     [rax+20h], r12d
0x180009f2a  mov     rax, [rsp+58h+arg_0]
0x180009f2f  mov     [rax+18h], rsi
0x180009f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f3a  cmp     rcx, r15
0x180009f3d  jz      short loc_180009F67
0x180009f3f  test    dword ptr [rcx+44h], 800h
0x180009f46  jz      short loc_180009F67
0x180009f48  mov     rcx, [rcx+38h]
0x180009f4c  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x180009f53  mov     edx, 0Ch
0x180009f58  mov     r9d, ebx
0x180009f5b  call    WPP_SF_D
0x180009f60  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f67  test    ebx, ebx
0x180009f69  jz      short loc_180009F81
0x180009f6b  cmp     rcx, r15
0x180009f6e  jz      short loc_180009FBF
0x180009f70  test    byte ptr [rcx+44h], 1
0x180009f74  jz      short loc_180009FBF
0x180009f76  mov     edx, 13h
0x180009f7b  mov     [rsp+58h+var_38], ebx
0x180009f7f  jmp     short loc_180009FAC
0x180009f81  mov     rcx, [rsp+58h+arg_0]
0x180009f86  call    QueueSupplicantEvent
0x180009f8b  mov     ebx, eax
0x180009f8d  test    eax, eax
0x180009f8f  jz      short loc_180009FC9
0x180009f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f98  cmp     rcx, r15
0x180009f9b  jz      short loc_180009FBF
0x180009f9d  test    byte ptr [rcx+44h], 1
0x180009fa1  jz      short loc_180009FBF
0x180009fa3  mov     edx, 14h
0x180009fa8  mov     [rsp+58h+var_38], eax
0x180009fac  mov     rcx, [rcx+38h]
0x180009fb0  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x180009fb7  mov     r9d, ebp
0x180009fba  call    WPP_SF_dd
0x180009fbf  mov     rcx, [rsp+58h+arg_0]
0x180009fc4  call    OneXDeleteEvent
0x180009fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fd0  mov     rbp, [rsp+58h+arg_10]
0x180009fd5  cmp     rcx, r15
0x180009fd8  jz      short loc_18000A002
0x180009fda  test    dword ptr [rcx+44h], 800h
0x180009fe1  jz      short loc_18000A002
0x180009fe3  mov     rcx, [rcx+38h]
0x180009fe7  lea     r8, WPP_c98c90d098d532f46181864aabb10d65_Traceguids
0x180009fee  mov     edx, 15h
0x180009ff3  mov     r9d, ebx
0x180009ff6  call    WPP_SF_D
0x180009ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a002  test    ebx, ebx
0x18000a004  jz      short loc_18000A034
0x18000a006  cmp     rcx, r15
0x18000a009  jz      short loc_18000A05A
0x18000a00b  test    byte ptr [rcx+44h], 1
0x18000a00f  jz      short loc_18000A034
0x18000a011  mov     edx, 2Eh ; '.'
0x18000a016  mov     [rsp+58h+var_38], ebx
0x18000a01a  mov     rcx, [rcx+38h]
0x18000a01e  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x18000a025  mov     r9d, r14d
0x18000a028  call    WPP_SF_dd
0x18000a02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a034  cmp     rcx, r15
0x18000a037  jz      short loc_18000A05A
0x18000a039  test    dword ptr [rcx+44h], 800h
0x18000a040  jz      short loc_18000A05A
0x18000a042  mov     rcx, [rcx+38h]
0x18000a046  lea     r8, WPP_c8ec828f4cdd36d6b1de53ca5d1088f8_Traceguids
0x18000a04d  mov     edx, 2Fh ; '/'
0x18000a052  mov     r9d, ebx
0x18000a055  call    WPP_SF_D
0x18000a05a  mov     eax, ebx
0x18000a05c  mov     rbx, [rsp+58h+arg_8]
0x18000a061  add     rsp, 30h
0x18000a065  pop     r15
0x18000a067  pop     r14
0x18000a069  pop     r12
0x18000a06b  pop     rdi
0x18000a06c  pop     rsi
0x18000a06d  retn
```
