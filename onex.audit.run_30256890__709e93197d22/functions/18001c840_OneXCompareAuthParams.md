# OneXCompareAuthParams

- ea: `0x18001c840`
- end: `0x18001ce3e`
- name: `OneXCompareAuthParams`
- size: `1534`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180010ae0`
- `0x18001a6cc`
- `0x18001a7c8`
- `0x18001c124`
- `0x18001c840`
- `0x1800214f0`
- `0x18002f6f9`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001cccc`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001cccc`
- `MobileNetworking!FreeMemory` at `0x18001cddf`
- `MobileNetworking!FreeMemory` at `0x18001cdf7`
- `MobileNetworking!FreeMemory` at `0x18001cddf`
- `MobileNetworking!FreeMemory` at `0x18001cdf7`

## string_xrefs

- `0x18001cdd3`: `OneXCompareAuthParams`
- `0x18001cdeb`: `OneXCompareAuthParams`

## pseudocode

```c
__int64 __fastcall OneXCompareAuthParams(int a1, unsigned int a2, __int64 a3, int a4, HANDLE *Buf2, int *a6)
{
  size_t v7; // r12
  _QWORD *v10; // rbx
  int v11; // esi
  unsigned int v12; // r15d
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // ebx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int v20; // ecx
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // ecx
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  PSID *v32; // [rsp+30h] [rbp-58h] BYREF
  LPVOID v33[10]; // [rsp+38h] [rbp-50h] BYREF

  v7 = a2;
  v32 = 0;
  v33[0] = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 166, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x100) != 0 )
    {
      WPP_SF_(v10[7], 167, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
  }
  v11 = 1;
  if ( a1 != 1 )
  {
    v12 = 50;
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
      WPP_SF_d(v10[7], 168, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, 50);
    goto LABEL_98;
  }
  if ( (_DWORD)v7 && a3 && a4 && Buf2 && a6 )
  {
    v12 = 0;
    if ( (_DWORD)v7 != a4 )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 4) != 0 )
        WPP_SF_dd(v10[7], 170, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, (unsigned int)v7, a4);
      goto LABEL_91;
    }
    if ( !memcmp_0((const void *)a3, Buf2, v7) )
    {
      if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 68) & 4) == 0 )
        goto LABEL_80;
      v13 = v10[7];
      v14 = 171;
LABEL_79:
      WPP_SF_(v13, v14, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
LABEL_80:
      *a6 = 0;
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_98;
      v30 = 186;
LABEL_94:
      WPP_SF_(v29[7], v30, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      goto LABEL_98;
    }
    if ( memcmp_0((const void *)a3, Buf2, 0x20u) )
    {
      if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 68) & 4) == 0 )
        goto LABEL_91;
      v15 = v10[7];
      v16 = 172;
      goto LABEL_90;
    }
    v17 = AreVariableBlobsDifferent(a3, a3 + 4, Buf2, (char *)Buf2 + 4);
    if ( v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_46;
      v19 = 173;
LABEL_45:
      WPP_SF_(v18[7], v19, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
LABEL_46:
      v11 = v17;
      goto LABEL_91;
    }
    v17 = AreVariableBlobsDifferent(a3, a3 + 48, Buf2, Buf2 + 6);
    if ( v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_46;
      v19 = 174;
      goto LABEL_45;
    }
    v17 = AreVariableBlobsDifferent(a3, a3 + 64, Buf2, Buf2 + 8);
    if ( v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_46;
      v19 = 175;
      goto LABEL_45;
    }
    v17 = AreVariableBlobsDifferent(a3, a3 + 56, Buf2, Buf2 + 7);
    if ( v17 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_46;
      v19 = 176;
      goto LABEL_45;
    }
    v20 = (*(_DWORD *)(a3 + 20) >> 2) & 1;
    if ( v20 == ((*((_DWORD *)Buf2 + 5) >> 2) & 1) )
    {
      if ( v20 )
      {
        v21 = UnmarshalOneXUserData(a3, (unsigned int)v7);
        v22 = UnmarshalOneXUserData(Buf2, (unsigned int)v7);
        if ( v21 )
        {
          if ( v22 )
          {
            v23 = *(_DWORD *)(v21 + 784);
            if ( v23 != *(_DWORD *)(v22 + 784) )
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
              {
                goto LABEL_91;
              }
              v16 = 177;
              goto LABEL_89;
            }
            if ( v23 && memcmp_0((const void *)(v21 + 788), (const void *)(v22 + 788), *(unsigned int *)(v21 + 784)) )
            {
              v24 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
              {
                goto LABEL_91;
              }
              v16 = 178;
              goto LABEL_89;
            }
          }
        }
      }
    }
    if ( ((*(_BYTE *)(a3 + 20) | *((_BYTE *)Buf2 + 20)) & 2) == 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_80;
      v14 = 179;
      goto LABEL_78;
    }
    if ( (*(_BYTE *)(a3 + 20) & (unsigned __int8)*((_DWORD *)Buf2 + 5) & 2) != 0 )
    {
      v26 = OneXGetTokenInformation(*(HANDLE *)(a3 + 32), (LPVOID *)&v32);
      v12 = v26;
      if ( v26 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_98;
        v28 = 180;
        goto LABEL_69;
      }
      v26 = OneXGetTokenInformation(Buf2[4], v33);
      v12 = v26;
      if ( v26 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_98;
        v28 = 181;
LABEL_69:
        WPP_SF_d(v27[7], v28, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v26);
        goto LABEL_98;
      }
      if ( EqualSid(*v32, *(PSID *)v33[0]) )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
          goto LABEL_80;
        v14 = 182;
LABEL_78:
        v13 = v25[7];
        goto LABEL_79;
      }
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_91;
      v16 = 183;
    }
    else
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
        goto LABEL_91;
      v16 = 184;
    }
LABEL_89:
    v15 = v24[7];
LABEL_90:
    WPP_SF_(v15, v16, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
LABEL_91:
    *a6 = v11;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) == 0 )
      goto LABEL_98;
    v30 = 185;
    goto LABEL_94;
  }
  v12 = 87;
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 68) & 1) != 0 )
    WPP_SF_(v10[7], 169, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
LABEL_98:
  FreeMemory(&v32, "OneXCompareAuthParams", 1774);
  FreeMemory(v33, "OneXCompareAuthParams", 1775);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 187, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x18001c840  push    rbx
0x18001c842  push    rbp
0x18001c843  push    rsi
0x18001c844  push    rdi
0x18001c845  push    r12
0x18001c847  push    r13
0x18001c849  push    r14
0x18001c84b  push    r15
0x18001c84d  sub     rsp, 48h
0x18001c851  mov     r13d, r9d
0x18001c854  mov     r12d, edx
0x18001c857  mov     r14, r8
0x18001c85a  mov     [rsp+88h+var_58], 0
0x18001c863  mov     edi, ecx
0x18001c865  mov     [rsp+88h+var_50], 0
0x18001c86e  mov     rbx, cs:WPP_GLOBAL_Control
0x18001c875  lea     rax, WPP_GLOBAL_Control
0x18001c87c  cmp     rbx, rax
0x18001c87f  jz      short loc_18001C8DE
0x18001c881  test    dword ptr [rbx+44h], 800h
0x18001c888  jz      short loc_18001C8AD
0x18001c88a  mov     rcx, [rbx+38h]
0x18001c88e  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001c895  mov     edx, 0A6h
0x18001c89a  call    WPP_SF_
0x18001c89f  mov     rbx, cs:WPP_GLOBAL_Control
0x18001c8a6  lea     rax, WPP_GLOBAL_Control
0x18001c8ad  cmp     rbx, rax
0x18001c8b0  jz      short loc_18001C8DE
0x18001c8b2  test    dword ptr [rbx+44h], 100h
0x18001c8b9  jz      short loc_18001C8DE
0x18001c8bb  mov     rcx, [rbx+38h]
0x18001c8bf  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001c8c6  mov     edx, 0A7h
0x18001c8cb  call    WPP_SF_
0x18001c8d0  mov     rbx, cs:WPP_GLOBAL_Control
0x18001c8d7  lea     rax, WPP_GLOBAL_Control
0x18001c8de  mov     esi, 1
0x18001c8e3  cmp     edi, esi
0x18001c8e5  jz      short loc_18001C91A
0x18001c8e7  lea     r15d, [rsi+31h]
0x18001c8eb  cmp     rbx, rax
0x18001c8ee  jz      loc_18001CDC6
0x18001c8f4  test    [rbx+44h], sil
0x18001c8f8  jz      loc_18001CDC6
0x18001c8fe  mov     rcx, [rbx+38h]
0x18001c902  lea     edx, [r15+76h]
0x18001c906  mov     r9d, r15d
0x18001c909  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001c910  call    WPP_SF_d
0x18001c915  jmp     loc_18001CDC6
0x18001c91a  test    r12d, r12d
0x18001c91d  jz      loc_18001CDA1
0x18001c923  test    r14, r14
0x18001c926  jz      loc_18001CDA1
0x18001c92c  test    r13d, r13d
0x18001c92f  jz      loc_18001CDA1
0x18001c935  mov     rbp, [rsp+88h+Buf2]
0x18001c93d  test    rbp, rbp
0x18001c940  jz      loc_18001CDA1
0x18001c946  mov     rdi, [rsp+88h+arg_28]
0x18001c94e  test    rdi, rdi
0x18001c951  jz      loc_18001CDA1
0x18001c957  xor     r15d, r15d
0x18001c95a  cmp     r12d, r13d
0x18001c95d  jz      short loc_18001C993
0x18001c95f  cmp     rbx, rax
0x18001c962  jz      short loc_18001C987
0x18001c964  test    byte ptr [rbx+44h], 4
0x18001c968  jz      short loc_18001C987
0x18001c96a  mov     rcx, [rbx+38h]
0x18001c96e  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001c975  mov     edx, 0AAh
0x18001c97a  mov     [rsp+88h+var_68], r13d
0x18001c97f  mov     r9d, r12d
0x18001c982  call    WPP_SF_dd
0x18001c987  lea     rbp, WPP_GLOBAL_Control
0x18001c98e  jmp     loc_18001CD76
0x18001c993  mov     r8, r12; Size
0x18001c996  mov     rdx, rbp; Buf2
0x18001c999  mov     rcx, r14; Buf1
0x18001c99c  call    memcmp_0
0x18001c9a1  xor     r13d, r13d
0x18001c9a4  test    eax, eax
0x18001c9a6  jnz     short loc_18001C9D0
0x18001c9a8  lea     rbp, WPP_GLOBAL_Control
0x18001c9af  cmp     rbx, rbp
0x18001c9b2  jz      loc_18001CD04
0x18001c9b8  test    byte ptr [rbx+44h], 4
0x18001c9bc  jz      loc_18001CD04
0x18001c9c2  mov     rcx, [rbx+38h]
0x18001c9c6  mov     edx, 0ABh
0x18001c9cb  jmp     loc_18001CCF8
0x18001c9d0  mov     r8d, 20h ; ' '; Size
0x18001c9d6  mov     rdx, rbp; Buf2
0x18001c9d9  mov     rcx, r14; Buf1
0x18001c9dc  call    memcmp_0
0x18001c9e1  test    eax, eax
0x18001c9e3  jz      short loc_18001CA0D
0x18001c9e5  lea     rbp, WPP_GLOBAL_Control
0x18001c9ec  cmp     rbx, rbp
0x18001c9ef  jz      loc_18001CD76
0x18001c9f5  test    byte ptr [rbx+44h], 4
0x18001c9f9  jz      loc_18001CD76
0x18001c9ff  mov     rcx, [rbx+38h]
0x18001ca03  mov     edx, 0ACh
0x18001ca08  jmp     loc_18001CD6A
0x18001ca0d  lea     r9, [rbp+4]
0x18001ca11  mov     r8, rbp
0x18001ca14  lea     rdx, [r14+4]
0x18001ca18  mov     rcx, r14
0x18001ca1b  call    AreVariableBlobsDifferent
0x18001ca20  mov     ebx, eax
0x18001ca22  test    eax, eax
0x18001ca24  jz      short loc_18001CA51
0x18001ca26  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca2d  lea     rbp, WPP_GLOBAL_Control
0x18001ca34  cmp     rcx, rbp
0x18001ca37  jz      loc_18001CB12
0x18001ca3d  test    byte ptr [rcx+44h], 4
0x18001ca41  jz      loc_18001CB12
0x18001ca47  mov     edx, 0ADh
0x18001ca4c  jmp     loc_18001CB02
0x18001ca51  lea     r9, [rbp+30h]
0x18001ca55  mov     r8, rbp
0x18001ca58  lea     rdx, [r14+30h]
0x18001ca5c  mov     rcx, r14
0x18001ca5f  call    AreVariableBlobsDifferent
0x18001ca64  mov     ebx, eax
0x18001ca66  test    eax, eax
0x18001ca68  jz      short loc_18001CA92
0x18001ca6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ca71  lea     rbp, WPP_GLOBAL_Control
0x18001ca78  cmp     rcx, rbp
0x18001ca7b  jz      loc_18001CB12
0x18001ca81  test    byte ptr [rcx+44h], 4
0x18001ca85  jz      loc_18001CB12
0x18001ca8b  mov     edx, 0AEh
0x18001ca90  jmp     short loc_18001CB02
0x18001ca92  lea     r9, [rbp+40h]
0x18001ca96  mov     r8, rbp
0x18001ca99  lea     rdx, [r14+40h]
0x18001ca9d  mov     rcx, r14
0x18001caa0  call    AreVariableBlobsDifferent
0x18001caa5  mov     ebx, eax
0x18001caa7  test    eax, eax
0x18001caa9  jz      short loc_18001CACB
0x18001caab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cab2  lea     rbp, WPP_GLOBAL_Control
0x18001cab9  cmp     rcx, rbp
0x18001cabc  jz      short loc_18001CB12
0x18001cabe  test    byte ptr [rcx+44h], 4
0x18001cac2  jz      short loc_18001CB12
0x18001cac4  mov     edx, 0AFh
0x18001cac9  jmp     short loc_18001CB02
0x18001cacb  lea     r9, [rbp+38h]
0x18001cacf  mov     r8, rbp
0x18001cad2  lea     rdx, [r14+38h]
0x18001cad6  mov     rcx, r14
0x18001cad9  call    AreVariableBlobsDifferent
0x18001cade  mov     ebx, eax
0x18001cae0  test    eax, eax
0x18001cae2  jz      short loc_18001CB19
0x18001cae4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caeb  lea     rbp, WPP_GLOBAL_Control
0x18001caf2  cmp     rcx, rbp
0x18001caf5  jz      short loc_18001CB12
0x18001caf7  test    byte ptr [rcx+44h], 4
0x18001cafb  jz      short loc_18001CB12
0x18001cafd  mov     edx, 0B0h
0x18001cb02  mov     rcx, [rcx+38h]
0x18001cb06  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001cb0d  call    WPP_SF_
0x18001cb12  mov     esi, ebx
0x18001cb14  jmp     loc_18001CD76
0x18001cb19  mov     ecx, [r14+14h]
0x18001cb1d  mov     eax, [rbp+14h]
0x18001cb20  shr     ecx, 2
0x18001cb23  shr     eax, 2
0x18001cb26  and     ecx, esi
0x18001cb28  and     eax, esi
0x18001cb2a  cmp     ecx, eax
0x18001cb2c  jnz     loc_18001CBE7
0x18001cb32  test    ecx, ecx
0x18001cb34  jz      loc_18001CBE7
0x18001cb3a  mov     edx, r12d
0x18001cb3d  mov     rcx, r14
0x18001cb40  call    UnmarshalOneXUserData
0x18001cb45  mov     edx, r12d
0x18001cb48  mov     rcx, rbp
0x18001cb4b  mov     rbx, rax
0x18001cb4e  call    UnmarshalOneXUserData
0x18001cb53  test    rbx, rbx
0x18001cb56  jz      loc_18001CBE7
0x18001cb5c  test    rax, rax
0x18001cb5f  jz      loc_18001CBE7
0x18001cb65  mov     ecx, [rbx+310h]
0x18001cb6b  cmp     ecx, [rax+310h]
0x18001cb71  jz      short loc_18001CB9E
0x18001cb73  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb7a  lea     rbp, WPP_GLOBAL_Control
0x18001cb81  cmp     rcx, rbp
0x18001cb84  jz      loc_18001CD76
0x18001cb8a  test    byte ptr [rcx+44h], 4
0x18001cb8e  jz      loc_18001CD76
0x18001cb94  mov     edx, 0B1h
0x18001cb99  jmp     loc_18001CD66
0x18001cb9e  test    ecx, ecx
0x18001cba0  jz      short loc_18001CBE7
0x18001cba2  mov     r8, rcx; Size
0x18001cba5  lea     rdx, [rax+314h]; Buf2
0x18001cbac  lea     rcx, [rbx+314h]; Buf1
0x18001cbb3  call    memcmp_0
0x18001cbb8  test    eax, eax
0x18001cbba  jz      short loc_18001CBE7
0x18001cbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbc3  lea     rbp, WPP_GLOBAL_Control
0x18001cbca  cmp     rcx, rbp
0x18001cbcd  jz      loc_18001CD76
0x18001cbd3  test    byte ptr [rcx+44h], 4
0x18001cbd7  jz      loc_18001CD76
0x18001cbdd  mov     edx, 0B2h
0x18001cbe2  jmp     loc_18001CD66
0x18001cbe7  mov     ecx, [rbp+14h]
0x18001cbea  mov     eax, ecx
0x18001cbec  or      eax, [r14+14h]
0x18001cbf0  test    al, 2
0x18001cbf2  jnz     short loc_18001CC1F
0x18001cbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cbfb  lea     rbp, WPP_GLOBAL_Control
0x18001cc02  cmp     rcx, rbp
0x18001cc05  jz      loc_18001CD04
0x18001cc0b  test    byte ptr [rcx+44h], 4
0x18001cc0f  jz      loc_18001CD04
0x18001cc15  mov     edx, 0B3h
0x18001cc1a  jmp     loc_18001CCF4
0x18001cc1f  and     ecx, [r14+14h]
0x18001cc23  test    cl, 2
0x18001cc26  jz      loc_18001CD48
0x18001cc2c  mov     rcx, [r14+20h]; TokenHandle
0x18001cc30  lea     rdx, [rsp+88h+var_58]
0x18001cc35  call    OneXGetTokenInformation
0x18001cc3a  mov     r15d, eax
0x18001cc3d  test    eax, eax
0x18001cc3f  jz      short loc_18001CC7F
0x18001cc41  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc48  lea     rbp, WPP_GLOBAL_Control
0x18001cc4f  cmp     rcx, rbp
0x18001cc52  jz      loc_18001CDCD
0x18001cc58  test    [rcx+44h], sil
0x18001cc5c  jz      loc_18001CDCD
0x18001cc62  mov     edx, 0B4h
0x18001cc67  mov     rcx, [rcx+38h]
0x18001cc6b  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001cc72  mov     r9d, eax
0x18001cc75  call    WPP_SF_d
0x18001cc7a  jmp     loc_18001CDCD
0x18001cc7f  mov     rcx, [rbp+20h]; TokenHandle
0x18001cc83  lea     rdx, [rsp+88h+var_50]
0x18001cc88  call    OneXGetTokenInformation
0x18001cc8d  mov     r15d, eax
0x18001cc90  test    eax, eax
0x18001cc92  jz      short loc_18001CCBC
0x18001cc94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc9b  lea     rbp, WPP_GLOBAL_Control
0x18001cca2  cmp     rcx, rbp
0x18001cca5  jz      loc_18001CDCD
0x18001ccab  test    [rcx+44h], sil
0x18001ccaf  jz      loc_18001CDCD
0x18001ccb5  mov     edx, 0B5h
0x18001ccba  jmp     short loc_18001CC67
0x18001ccbc  mov     rdx, [rsp+88h+var_50]
0x18001ccc1  mov     rcx, [rsp+88h+var_58]
0x18001ccc6  mov     rdx, [rdx]; pSid2
0x18001ccc9  mov     rcx, [rcx]; pSid1
0x18001cccc  call    cs:__imp_EqualSid
0x18001ccd2  test    eax, eax
0x18001ccd4  jz      short loc_18001CD28
0x18001ccd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccdd  lea     rbp, WPP_GLOBAL_Control
0x18001cce4  cmp     rcx, rbp
0x18001cce7  jz      short loc_18001CD04
0x18001cce9  test    byte ptr [rcx+44h], 4
0x18001cced  jz      short loc_18001CD04
0x18001ccef  mov     edx, 0B6h
0x18001ccf4  mov     rcx, [rcx+38h]
0x18001ccf8  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001ccff  call    WPP_SF_
0x18001cd04  mov     [rdi], r13d
0x18001cd07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd0e  cmp     rcx, rbp
0x18001cd11  jz      loc_18001CDCD
0x18001cd17  test    byte ptr [rcx+44h], 4
0x18001cd1b  jz      loc_18001CDCD
0x18001cd21  mov     edx, 0BAh
0x18001cd26  jmp     short loc_18001CD8F
0x18001cd28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd2f  lea     rbp, WPP_GLOBAL_Control
0x18001cd36  cmp     rcx, rbp
0x18001cd39  jz      short loc_18001CD76
  ... truncated ...
```
