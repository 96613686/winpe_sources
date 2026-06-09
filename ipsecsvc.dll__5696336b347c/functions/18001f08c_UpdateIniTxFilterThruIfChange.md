# UpdateIniTxFilterThruIfChange

- ea: `0x18001f08c`
- end: `0x18001f3d9`
- name: `UpdateIniTxFilterThruIfChange`
- size: `845`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180001710`
- `0x1800074f0`

## callees

- `0x180006f60`
- `0x18000c9fc`
- `0x18000e510`
- `0x18000f638`
- `0x180019df8`
- `0x180019e74`
- `0x18001cc98`
- `0x18001e12c`
- `0x18001e810`
- `0x18001e988`
- `0x18001f08c`
- `0x18001f3e0`
- `0x18002088c`
- `0x1800208d4`
- `0x180044c20`

## pseudocode

```c
__int64 __fastcall UpdateIniTxFilterThruIfChange(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r12
  _QWORD *v4; // r15
  void *v5; // rdi
  unsigned int v7; // eax
  unsigned int v8; // esi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  _QWORD *v16; // r8
  __int64 i; // rdx
  _QWORD *j; // rdx
  __int64 v19; // rdx
  LPVOID v21; // [rsp+30h] [rbp-30h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-28h] BYREF
  __int64 v23; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v24; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v25; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+A8h] [rbp+48h] BYREF

  v3 = 0;
  v24 = 0;
  v4 = 0;
  v23 = 0;
  v5 = 0;
  v25 = 0;
  v21 = 0;
  v26 = 0;
  lpMem = 0;
  v7 = FormIniTxSFilters(a1, a2, a3, &v24);
  v8 = v7;
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v10 = 95;
        v11 = v7;
LABEL_35:
        WPP_SF_d(v9[2], v10, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, v11);
        goto LABEL_36;
      }
LABEL_37:
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
        WPP_SF_S_guid_D(
          v9[2],
          101,
          (unsigned int)WPP_d3e4a8f1960430b115941304a22a5749_Traceguids,
          *(_QWORD *)(a1 + 24),
          a1 + 4,
          v8);
    }
  }
  else
  {
    RemoveTxSFilters(a1, &v23);
    ProcessIniTxSFilters(&v24, &v23, &v25, &v21);
    v4 = v25;
    v3 = v23;
    v12 = AllocateTxSFilterLinks(v23, (__int64)v25, &v26, &lpMem);
    v8 = v12;
    if ( !v12 )
    {
      v13 = *(_QWORD *)(a1 + 184);
      if ( v13 )
      {
        LinkTxSpecificFilters(v13, v3);
        LinkTxSpecificFilters(*(_QWORD *)(a1 + 184), (__int64)v4);
      }
      v5 = v21;
      v8 = LipsApiIpsecFilterUpdate((__int64)v21, (__int64)v4);
      if ( v8 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_40;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          goto LABEL_37;
        v10 = 97;
      }
      else
      {
        v14 = v26;
        v15 = 0;
        v16 = lpMem;
        for ( i = v3; (unsigned int)v15 < v14; i = *(_QWORD *)(i + 208) )
        {
          if ( !i )
            break;
          v16[v15] = i;
          v15 = (unsigned int)(v15 + 1);
        }
        for ( j = v4; (unsigned int)v15 < v14 && j; j = (_QWORD *)j[26] )
        {
          v16[v15] = j;
          v15 = (unsigned int)(v15 + 1);
        }
        UpdateTxSFilterLinks(a1, v14, lpMem);
        v19 = 0;
        *(_DWORD *)(a1 + 208) = 1;
        while ( 1 )
        {
          if ( (unsigned int)v19 >= v14 )
          {
            AddToSpecificTxList((__int64 *)&gpIniTxSFilter, v3);
            AddToSpecificTxList((__int64 *)&gpIniTxSFilter, (__int64)v4);
            if ( v5 )
              FreeIniTxSFilterList(v5);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_S_guid_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                100,
                (unsigned int)WPP_d3e4a8f1960430b115941304a22a5749_Traceguids,
                *(_QWORD *)(a1 + 24),
                a1 + 4);
            return v8;
          }
          if ( !*((_QWORD *)lpMem + v19) )
            break;
          v19 = (unsigned int)(v19 + 1);
        }
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids);
          v9 = WPP_GLOBAL_Control;
        }
        v8 = 13;
        if ( v9 == &WPP_GLOBAL_Control )
          goto LABEL_40;
        if ( (*((_BYTE *)v9 + 28) & 0x10) == 0 )
          goto LABEL_37;
        v10 = 99;
      }
      v11 = v8;
      goto LABEL_35;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, v12);
        v5 = v21;
LABEL_36:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_37;
      }
      v5 = v21;
      goto LABEL_37;
    }
    v5 = v21;
  }
LABEL_40:
  if ( v24 )
    FreeIniTxSFilterList(v24);
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( v3 )
    AddToSpecificTxList((__int64 *)&gpIniTxSFilter, v3);
  if ( v4 )
    FreeIniTxSFilterList(v4);
  if ( v5 )
    AddToSpecificTxList((__int64 *)&gpIniTxSFilter, (__int64)v5);
  return v8;
}

```

## disassembly

```asm
0x18001f08c  mov     [rsp-28h+arg_0], rbx
0x18001f091  mov     [rsp-28h+arg_8], rsi
0x18001f096  push    rbp
0x18001f097  push    rdi
0x18001f098  push    r12
0x18001f09a  push    r14
0x18001f09c  push    r15
0x18001f09e  mov     rbp, rsp
0x18001f0a1  sub     rsp, 60h
0x18001f0a5  xor     r12d, r12d
0x18001f0a8  mov     [rbp+var_18], 0
0x18001f0b0  xor     r15d, r15d
0x18001f0b3  mov     [rbp+var_20], r12
0x18001f0b7  xor     edi, edi
0x18001f0b9  mov     [rbp+var_10], r15
0x18001f0bd  lea     r9, [rbp+var_18]
0x18001f0c1  mov     [rbp+var_30], rdi
0x18001f0c5  mov     r14, rcx
0x18001f0c8  mov     [rbp+arg_18], 0
0x18001f0cf  mov     [rbp+lpMem], 0
0x18001f0d7  call    FormIniTxSFilters
0x18001f0dc  mov     esi, eax
0x18001f0de  test    eax, eax
0x18001f0e0  jz      short loc_18001F10E
0x18001f0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0e9  lea     rbx, WPP_GLOBAL_Control
0x18001f0f0  cmp     rcx, rbx
0x18001f0f3  jz      loc_18001F305
0x18001f0f9  test    byte ptr [rcx+1Ch], 10h
0x18001f0fd  jz      loc_18001F2D4
0x18001f103  lea     edx, [rdi+5Fh]
0x18001f106  mov     r9d, eax
0x18001f109  jmp     loc_18001F2BD
0x18001f10e  lea     rdx, [rbp+var_20]
0x18001f112  mov     rcx, r14
0x18001f115  call    RemoveTxSFilters
0x18001f11a  lea     r9, [rbp+var_30]
0x18001f11e  lea     r8, [rbp+var_10]
0x18001f122  lea     rdx, [rbp+var_20]
0x18001f126  lea     rcx, [rbp+var_18]
0x18001f12a  call    ProcessIniTxSFilters
0x18001f12f  mov     r15, [rbp+var_10]
0x18001f133  lea     r9, [rbp+lpMem]
0x18001f137  mov     r12, [rbp+var_20]
0x18001f13b  lea     r8, [rbp+arg_18]
0x18001f13f  mov     rdx, r15
0x18001f142  mov     rcx, r12
0x18001f145  call    AllocateTxSFilterLinks
0x18001f14a  mov     esi, eax
0x18001f14c  test    eax, eax
0x18001f14e  jz      short loc_18001F19C
0x18001f150  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f157  lea     rbx, WPP_GLOBAL_Control
0x18001f15e  cmp     rcx, rbx
0x18001f161  jz      short loc_18001F193
0x18001f163  test    byte ptr [rcx+1Ch], 10h
0x18001f167  jz      short loc_18001F18A
0x18001f169  mov     rcx, [rcx+10h]
0x18001f16d  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001f174  mov     edx, 60h ; '`'
0x18001f179  mov     r9d, eax
0x18001f17c  call    WPP_SF_d
0x18001f181  mov     rdi, [rbp+var_30]
0x18001f185  jmp     loc_18001F2CD
0x18001f18a  mov     rdi, [rbp+var_30]
0x18001f18e  jmp     loc_18001F2D4
0x18001f193  mov     rdi, [rbp+var_30]
0x18001f197  jmp     loc_18001F305
0x18001f19c  mov     rcx, [r14+0B8h]
0x18001f1a3  test    rcx, rcx
0x18001f1a6  jz      short loc_18001F1BF
0x18001f1a8  mov     rdx, r12
0x18001f1ab  call    LinkTxSpecificFilters
0x18001f1b0  mov     rcx, [r14+0B8h]
0x18001f1b7  mov     rdx, r15
0x18001f1ba  call    LinkTxSpecificFilters
0x18001f1bf  mov     rdi, [rbp+var_30]
0x18001f1c3  mov     rdx, r15
0x18001f1c6  mov     rcx, rdi
0x18001f1c9  call    LipsApiIpsecFilterUpdate
0x18001f1ce  mov     esi, eax
0x18001f1d0  test    eax, eax
0x18001f1d2  jz      short loc_18001F1FF
0x18001f1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1db  lea     rbx, WPP_GLOBAL_Control
0x18001f1e2  cmp     rcx, rbx
0x18001f1e5  jz      loc_18001F305
0x18001f1eb  test    byte ptr [rcx+1Ch], 10h
0x18001f1ef  jz      loc_18001F2D4
0x18001f1f5  mov     edx, 61h ; 'a'
0x18001f1fa  jmp     loc_18001F2BA
0x18001f1ff  mov     ebx, [rbp+arg_18]
0x18001f202  xor     ecx, ecx
0x18001f204  mov     r8, [rbp+lpMem]
0x18001f208  mov     rdx, r12
0x18001f20b  test    ebx, ebx
0x18001f20d  jz      short loc_18001F225
0x18001f20f  test    rdx, rdx
0x18001f212  jz      short loc_18001F225
0x18001f214  mov     [r8+rcx*8], rdx
0x18001f218  inc     ecx
0x18001f21a  mov     rdx, [rdx+0D0h]
0x18001f221  cmp     ecx, ebx
0x18001f223  jb      short loc_18001F20F
0x18001f225  mov     rdx, r15
0x18001f228  jmp     short loc_18001F23C
0x18001f22a  test    rdx, rdx
0x18001f22d  jz      short loc_18001F240
0x18001f22f  mov     [r8+rcx*8], rdx
0x18001f233  inc     ecx
0x18001f235  mov     rdx, [rdx+0D0h]
0x18001f23c  cmp     ecx, ebx
0x18001f23e  jb      short loc_18001F22A
0x18001f240  mov     r8, [rbp+lpMem]
0x18001f244  mov     edx, ebx
0x18001f246  mov     rcx, r14
0x18001f249  call    UpdateTxSFilterLinks
0x18001f24e  xor     edx, edx
0x18001f250  mov     dword ptr [r14+0D0h], 1
0x18001f25b  cmp     edx, ebx
0x18001f25d  jnb     loc_18001F358
0x18001f263  mov     rax, [rbp+lpMem]
0x18001f267  cmp     qword ptr [rax+rdx*8], 0
0x18001f26c  jz      short loc_18001F272
0x18001f26e  inc     edx
0x18001f270  jmp     short loc_18001F25B
0x18001f272  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f279  lea     rbx, WPP_GLOBAL_Control
0x18001f280  cmp     rcx, rbx
0x18001f283  jz      short loc_18001F2A7
0x18001f285  test    byte ptr [rcx+1Ch], 10h
0x18001f289  jz      short loc_18001F2A7
0x18001f28b  mov     rcx, [rcx+10h]
0x18001f28f  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001f296  mov     edx, 62h ; 'b'
0x18001f29b  call    WPP_SF_
0x18001f2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2a7  mov     esi, 0Dh
0x18001f2ac  cmp     rcx, rbx
0x18001f2af  jz      short loc_18001F305
0x18001f2b1  test    byte ptr [rcx+1Ch], 10h
0x18001f2b5  jz      short loc_18001F2D4
0x18001f2b7  lea     edx, [rsi+56h]
0x18001f2ba  mov     r9d, esi
0x18001f2bd  mov     rcx, [rcx+10h]
0x18001f2c1  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001f2c8  call    WPP_SF_d
0x18001f2cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2d4  cmp     rcx, rbx
0x18001f2d7  jz      short loc_18001F305
0x18001f2d9  test    byte ptr [rcx+1Ch], 10h
0x18001f2dd  jz      short loc_18001F305
0x18001f2df  mov     r9, [r14+18h]
0x18001f2e3  lea     rax, [r14+4]
0x18001f2e7  mov     rcx, [rcx+10h]
0x18001f2eb  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001f2f2  mov     edx, 65h ; 'e'
0x18001f2f7  mov     [rsp+60h+var_38], esi
0x18001f2fb  mov     [rsp+60h+var_40], rax
0x18001f300  call    WPP_SF_S_guid_D
0x18001f305  mov     rcx, [rbp+var_18]; lpMem
0x18001f309  test    rcx, rcx
0x18001f30c  jz      short loc_18001F313
0x18001f30e  call    FreeIniTxSFilterList
0x18001f313  mov     rcx, [rbp+lpMem]; lpMem
0x18001f317  test    rcx, rcx
0x18001f31a  jz      short loc_18001F321
0x18001f31c  call    IpsecFreeMem
0x18001f321  test    r12, r12
0x18001f324  jz      short loc_18001F335
0x18001f326  mov     rdx, r12
0x18001f329  lea     rcx, gpIniTxSFilter
0x18001f330  call    AddToSpecificTxList
0x18001f335  test    r15, r15
0x18001f338  jz      short loc_18001F342
0x18001f33a  mov     rcx, r15; lpMem
0x18001f33d  call    FreeIniTxSFilterList
0x18001f342  test    rdi, rdi
0x18001f345  jz      short loc_18001F3BE
0x18001f347  mov     rdx, rdi
0x18001f34a  lea     rcx, gpIniTxSFilter
0x18001f351  call    AddToSpecificTxList
0x18001f356  jmp     short loc_18001F3BE
0x18001f358  mov     rdx, r12
0x18001f35b  lea     rcx, gpIniTxSFilter
0x18001f362  call    AddToSpecificTxList
0x18001f367  mov     rdx, r15
0x18001f36a  lea     rcx, gpIniTxSFilter
0x18001f371  call    AddToSpecificTxList
0x18001f376  test    rdi, rdi
0x18001f379  jz      short loc_18001F383
0x18001f37b  mov     rcx, rdi; lpMem
0x18001f37e  call    FreeIniTxSFilterList
0x18001f383  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f38a  lea     rbx, WPP_GLOBAL_Control
0x18001f391  cmp     rcx, rbx
0x18001f394  jz      short loc_18001F3BE
0x18001f396  test    byte ptr [rcx+1Ch], 4
0x18001f39a  jz      short loc_18001F3BE
0x18001f39c  mov     r9, [r14+18h]
0x18001f3a0  lea     rax, [r14+4]
0x18001f3a4  mov     rcx, [rcx+10h]
0x18001f3a8  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001f3af  mov     edx, 64h ; 'd'
0x18001f3b4  mov     [rsp+60h+var_40], rax
0x18001f3b9  call    WPP_SF_S_guid_
0x18001f3be  lea     r11, [rsp+60h+var_s0]
0x18001f3c3  mov     eax, esi
0x18001f3c5  mov     rbx, [r11+30h]
0x18001f3c9  mov     rsi, [r11+38h]
0x18001f3cd  mov     rsp, r11
0x18001f3d0  pop     r15
0x18001f3d2  pop     r14
0x18001f3d4  pop     r12
0x18001f3d6  pop     rdi
0x18001f3d7  pop     rbp
0x18001f3d8  retn
```
