# IsFormatInRange(KSDATAFORMAT *,KSDATAFORMAT *)

- ea: `0x1001e5ad`
- end: `0x1001e8e9`
- name: `?IsFormatInRange@@YGJPATKSDATAFORMAT@@0@Z`
- size: `828`
- prototype: `int __fastcall(_DWORD *, RECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1001e8ef`

## callees

- `0x100063f1`
- `0x1001e5ad`
- `0x1003aba0`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1001e6fd`
- `USER32!IsRectEmpty` at `0x1001e753`
- `USER32!IsRectEmpty` at `0x1001e6fd`
- `USER32!IsRectEmpty` at `0x1001e753`
- `USER32!SetRect` at `0x1001e718`
- `USER32!SetRect` at `0x1001e718`

## pseudocode

```c
int __fastcall IsFormatInRange(_DWORD *a1, RECT *a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int top; // esi
  int right; // edi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // edi
  signed int v13; // esi
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // edi
  int v19; // [esp+Ch] [ebp-3Ch]
  RECT *v20; // [esp+10h] [ebp-38h]
  int v21; // [esp+10h] [ebp-38h]
  RECT rc; // [esp+14h] [ebp-34h] BYREF
  struct tagRECT v23; // [esp+24h] [ebp-24h] BYREF
  RECT v24; // [esp+34h] [ebp-14h] BYREF

  v20 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(0x2Du, &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    a2 = v20;
  }
  v3 = 0;
  while ( *(&a2[1].left + v3) == *(&_GUID_73646976_0000_0010_8000_00aa00389b71.Data1 + v3) )
  {
    if ( ++v3 == 4 )
    {
      v4 = 0;
      while ( *(&a2[3].left + v4) == *(&FORMAT_VideoInfo.Data1 + v4) )
      {
        if ( ++v4 == 4 )
        {
          v5 = 0;
          while ( a1[v5 + 12] == *(&_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1 + v5) )
          {
            if ( ++v5 == 4 )
            {
              v6 = 0;
              while ( *(&a2[2].left + v6) == a1[v6 + 8] )
              {
                if ( ++v6 == 4 )
                {
                  if ( *a1 < 0x128u || a2->left < 0x98u )
                    return -2147467259;
                  v24 = a2[4];
                  rc = a2[5];
                  top = a2[7].top;
                  right = a2[7].right;
LABEL_31:
                  if ( IsRectEmpty(&rc) )
                    SetRect(&v23, 0, 0, top, abs32(right));
                  else
                    v23 = rc;
                  v12 = v24.bottom - v24.top;
                  v19 = v23.right - v23.left;
                  v21 = v24.right - v24.left;
                  v13 = abs32(v23.bottom - v23.top);
                  if ( !IsRectEmpty(&v24) )
                  {
                    if ( v21 < a1[27] || v21 > a1[29] || v12 < a1[28] || v12 > a1[30] )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                        WPP_SF_(
                          0x2Eu,
                          &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
                          *((_QWORD *)WPP_GLOBAL_Control + 2));
                      return -2147467259;
                    }
                    if ( a1[31] )
                    {
                      v14 = a1[32];
                      if ( v14 )
                      {
                        if ( v21 % a1[31] || v12 % v14 )
                        {
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                            WPP_SF_(
                              0x2Fu,
                              &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
                              *((_QWORD *)WPP_GLOBAL_Control + 2));
                          return -2147467259;
                        }
                      }
                    }
                    v15 = a1[33];
                    if ( v15 && a1[34] && v24.left % v15 || v24.top % a1[34] )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                        WPP_SF_(
                          0x30u,
                          &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
                          *((_QWORD *)WPP_GLOBAL_Control + 2));
                      return -2147467259;
                    }
                  }
                  if ( v19 < a1[35] || v19 > a1[37] || v13 < a1[36] || v13 > a1[38] )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                      WPP_SF_(
                        0x31u,
                        &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
                        *((_QWORD *)WPP_GLOBAL_Control + 2));
                  }
                  else
                  {
                    v16 = a1[39];
                    if ( !v16 )
                      return 0;
                    v17 = a1[40];
                    if ( !v17 || !(v19 % v16) && !(v13 % v17) )
                      return 0;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                      WPP_SF_(
                        0x32u,
                        &WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids,
                        *((_QWORD *)WPP_GLOBAL_Control + 2));
                  }
                  return -2147467259;
                }
              }
              goto LABEL_19;
            }
          }
          break;
        }
      }
LABEL_19:
      v9 = 0;
      while ( *(&a2[3].left + v9) == *(&FORMAT_VideoInfo2.Data1 + v9) )
      {
        if ( ++v9 == 4 )
        {
          v10 = 0;
          while ( a1[v10 + 12] == *(&_GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1 + v10) )
          {
            if ( ++v10 == 4 )
            {
              v11 = 0;
              while ( *(&a2[2].left + v11) == a1[v11 + 8] )
              {
                if ( ++v11 == 4 )
                {
                  if ( *a1 >= 0x140u && a2->left >= 0xB0u )
                  {
                    v24 = a2[4];
                    rc = a2[5];
                    top = a2[8].bottom;
                    right = a2[9].left;
                    goto LABEL_31;
                  }
                  return -2147467259;
                }
              }
              return -2147467259;
            }
          }
          return -2147467259;
        }
      }
      return -2147467259;
    }
  }
  return -2147467259;
}

```

## disassembly

```asm
0x1001e5ad  mov     edi, edi
0x1001e5af  push    ebp
0x1001e5b0  mov     ebp, esp
0x1001e5b2  sub     esp, 3Ch
0x1001e5b5  mov     eax, ___security_cookie
0x1001e5ba  xor     eax, ebp
0x1001e5bc  mov     [ebp+var_4], eax
0x1001e5bf  push    ebx
0x1001e5c0  push    esi
0x1001e5c1  push    edi
0x1001e5c2  mov     [ebp+var_38], edx
0x1001e5c5  mov     ebx, ecx
0x1001e5c7  mov     eax, _WPP_GLOBAL_Control
0x1001e5cc  cmp     eax, offset _WPP_GLOBAL_Control
0x1001e5d1  jz      short loc_1001E5EF
0x1001e5d3  cmp     byte ptr [eax+19h], 3
0x1001e5d7  jb      short loc_1001E5EF
0x1001e5d9  push    dword ptr [eax+14h]
0x1001e5dc  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001e5e1  push    dword ptr [eax+10h]; LoggerHandle
0x1001e5e4  push    2Dh ; '-'
0x1001e5e6  pop     ecx; MessageNumber
0x1001e5e7  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1001e5ec  mov     edx, [ebp+var_38]
0x1001e5ef  push    4
0x1001e5f1  mov     edi, offset __GUID_73646976_0000_0010_8000_00aa00389b71
0x1001e5f6  xor     ecx, ecx
0x1001e5f8  pop     esi
0x1001e5f9  mov     eax, [edx+ecx*4+10h]
0x1001e5fd  cmp     eax, [edi+ecx*4]
0x1001e600  jnz     loc_1001E8D5
0x1001e606  inc     ecx
0x1001e607  cmp     ecx, esi
0x1001e609  jnz     short loc_1001E5F9
0x1001e60b  mov     edi, offset _FORMAT_VideoInfo
0x1001e610  xor     ecx, ecx
0x1001e612  mov     eax, [edx+ecx*4+30h]
0x1001e616  cmp     eax, [edi+ecx*4]
0x1001e619  jnz     short loc_1001E67A
0x1001e61b  inc     ecx
0x1001e61c  cmp     ecx, esi
0x1001e61e  jnz     short loc_1001E612
0x1001e620  mov     edi, offset __GUID_05589f80_c356_11ce_bf01_00aa0055595a
0x1001e625  xor     ecx, ecx
0x1001e627  mov     eax, [ebx+ecx*4+30h]
0x1001e62b  cmp     eax, [edi+ecx*4]
0x1001e62e  jnz     short loc_1001E67A
0x1001e630  inc     ecx
0x1001e631  cmp     ecx, esi
0x1001e633  jnz     short loc_1001E627
0x1001e635  xor     ecx, ecx
0x1001e637  mov     eax, [edx+ecx*4+20h]
0x1001e63b  cmp     eax, [ebx+ecx*4+20h]
0x1001e63f  jnz     short loc_1001E67A
0x1001e641  inc     ecx
0x1001e642  cmp     ecx, esi
0x1001e644  jnz     short loc_1001E637
0x1001e646  cmp     dword ptr [ebx], 128h
0x1001e64c  jb      loc_1001E8D5
0x1001e652  cmp     dword ptr [edx], 98h
0x1001e658  jb      loc_1001E8D5
0x1001e65e  lea     esi, [edx+40h]
0x1001e661  lea     edi, [ebp+var_14]
0x1001e664  movsd
0x1001e665  movsd
0x1001e666  movsd
0x1001e667  movsd
0x1001e668  lea     esi, [edx+50h]
0x1001e66b  lea     edi, [ebp+rc]
0x1001e66e  movsd
0x1001e66f  movsd
0x1001e670  movsd
0x1001e671  movsd
0x1001e672  mov     esi, [edx+74h]
0x1001e675  mov     edi, [edx+78h]
0x1001e678  jmp     short loc_1001E6F9
0x1001e67a  mov     edi, offset _FORMAT_VideoInfo2
0x1001e67f  xor     ecx, ecx
0x1001e681  mov     eax, [edx+ecx*4+30h]
0x1001e685  cmp     eax, [edi+ecx*4]
0x1001e688  jnz     loc_1001E8D5
0x1001e68e  inc     ecx
0x1001e68f  cmp     ecx, esi
0x1001e691  jnz     short loc_1001E681
0x1001e693  mov     edi, offset __GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba
0x1001e698  xor     ecx, ecx
0x1001e69a  mov     eax, [ebx+ecx*4+30h]
0x1001e69e  cmp     eax, [edi+ecx*4]
0x1001e6a1  jnz     loc_1001E8D5
0x1001e6a7  inc     ecx
0x1001e6a8  cmp     ecx, esi
0x1001e6aa  jnz     short loc_1001E69A
0x1001e6ac  xor     ecx, ecx
0x1001e6ae  mov     eax, [edx+ecx*4+20h]
0x1001e6b2  cmp     eax, [ebx+ecx*4+20h]
0x1001e6b6  jnz     loc_1001E8D5
0x1001e6bc  inc     ecx
0x1001e6bd  cmp     ecx, esi
0x1001e6bf  jnz     short loc_1001E6AE
0x1001e6c1  cmp     dword ptr [ebx], 140h
0x1001e6c7  jb      loc_1001E8D5
0x1001e6cd  cmp     dword ptr [edx], 0B0h
0x1001e6d3  jb      loc_1001E8D5
0x1001e6d9  lea     esi, [edx+40h]
0x1001e6dc  lea     edi, [ebp+var_14]
0x1001e6df  movsd
0x1001e6e0  movsd
0x1001e6e1  movsd
0x1001e6e2  movsd
0x1001e6e3  lea     esi, [edx+50h]
0x1001e6e6  lea     edi, [ebp+rc]
0x1001e6e9  movsd
0x1001e6ea  movsd
0x1001e6eb  movsd
0x1001e6ec  movsd
0x1001e6ed  mov     esi, [edx+8Ch]
0x1001e6f3  mov     edi, [edx+90h]
0x1001e6f9  lea     eax, [ebp+rc]
0x1001e6fc  push    eax; lprc
0x1001e6fd  call    ds:__imp__IsRectEmpty@4; IsRectEmpty(x)
0x1001e703  test    eax, eax
0x1001e705  jz      short loc_1001E720
0x1001e707  mov     eax, edi
0x1001e709  cdq
0x1001e70a  xor     eax, edx
0x1001e70c  sub     eax, edx
0x1001e70e  push    eax; yBottom
0x1001e70f  push    esi; xRight
0x1001e710  push    0; yTop
0x1001e712  push    0; xLeft
0x1001e714  lea     eax, [ebp+var_24]
0x1001e717  push    eax; lprc
0x1001e718  call    ds:__imp__SetRect@20; SetRect(x,x,x,x,x)
0x1001e71e  jmp     short loc_1001E72A
0x1001e720  lea     esi, [ebp+rc]
0x1001e723  lea     edi, [ebp+var_24]
0x1001e726  movsd
0x1001e727  movsd
0x1001e728  movsd
0x1001e729  movsd
0x1001e72a  mov     eax, [ebp+var_24.right]
0x1001e72d  sub     eax, [ebp+var_24.left]
0x1001e730  mov     edi, [ebp+var_14.bottom]
0x1001e733  sub     edi, [ebp+var_14.top]
0x1001e736  mov     [ebp+var_3C], eax
0x1001e739  mov     eax, [ebp+var_24.bottom]
0x1001e73c  sub     eax, [ebp+var_24.top]
0x1001e73f  cdq
0x1001e740  mov     esi, eax
0x1001e742  mov     eax, [ebp+var_14.right]
0x1001e745  sub     eax, [ebp+var_14.left]
0x1001e748  xor     esi, edx
0x1001e74a  mov     [ebp+var_38], eax
0x1001e74d  sub     esi, edx
0x1001e74f  lea     eax, [ebp+var_14]
0x1001e752  push    eax; lprc
0x1001e753  call    ds:__imp__IsRectEmpty@4; IsRectEmpty(x)
0x1001e759  test    eax, eax
0x1001e75b  jnz     loc_1001E849
0x1001e761  mov     eax, [ebp+var_38]
0x1001e764  cmp     eax, [ebx+6Ch]
0x1001e767  jl      loc_1001E822
0x1001e76d  cmp     eax, [ebx+74h]
0x1001e770  jg      loc_1001E822
0x1001e776  cmp     edi, [ebx+70h]
0x1001e779  jl      loc_1001E822
0x1001e77f  cmp     edi, [ebx+78h]
0x1001e782  jg      loc_1001E822
0x1001e788  cmp     dword ptr [ebx+7Ch], 0
0x1001e78c  jz      short loc_1001E7D0
0x1001e78e  mov     ecx, [ebx+80h]
0x1001e794  test    ecx, ecx
0x1001e796  jz      short loc_1001E7D0
0x1001e798  cdq
0x1001e799  idiv    dword ptr [ebx+7Ch]
0x1001e79c  test    edx, edx
0x1001e79e  jnz     short loc_1001E7A9
0x1001e7a0  mov     eax, edi
0x1001e7a2  cdq
0x1001e7a3  idiv    ecx
0x1001e7a5  test    edx, edx
0x1001e7a7  jz      short loc_1001E7D0
0x1001e7a9  mov     eax, _WPP_GLOBAL_Control
0x1001e7ae  cmp     eax, offset _WPP_GLOBAL_Control
0x1001e7b3  jz      loc_1001E8D5
0x1001e7b9  cmp     byte ptr [eax+19h], 5
0x1001e7bd  jb      loc_1001E8D5
0x1001e7c3  push    dword ptr [eax+14h]
0x1001e7c6  push    dword ptr [eax+10h]
0x1001e7c9  push    2Fh ; '/'
0x1001e7cb  jmp     loc_1001E8CA
0x1001e7d0  mov     ecx, [ebx+84h]
0x1001e7d6  test    ecx, ecx
0x1001e7d8  jz      short loc_1001E7ED
0x1001e7da  cmp     dword ptr [ebx+88h], 0
0x1001e7e1  jz      short loc_1001E7ED
0x1001e7e3  mov     eax, [ebp+var_14.left]
0x1001e7e6  cdq
0x1001e7e7  idiv    ecx
0x1001e7e9  test    edx, edx
0x1001e7eb  jnz     short loc_1001E7FB
0x1001e7ed  mov     eax, [ebp+var_14.top]
0x1001e7f0  cdq
0x1001e7f1  idiv    dword ptr [ebx+88h]
0x1001e7f7  test    edx, edx
0x1001e7f9  jz      short loc_1001E849
0x1001e7fb  mov     eax, _WPP_GLOBAL_Control
0x1001e800  cmp     eax, offset _WPP_GLOBAL_Control
0x1001e805  jz      loc_1001E8D5
0x1001e80b  cmp     byte ptr [eax+19h], 5
0x1001e80f  jb      loc_1001E8D5
0x1001e815  push    dword ptr [eax+14h]
0x1001e818  push    dword ptr [eax+10h]
0x1001e81b  push    30h ; '0'
0x1001e81d  jmp     loc_1001E8CA
0x1001e822  mov     eax, _WPP_GLOBAL_Control
0x1001e827  cmp     eax, offset _WPP_GLOBAL_Control
0x1001e82c  jz      loc_1001E8D5
0x1001e832  cmp     byte ptr [eax+19h], 5
0x1001e836  jb      loc_1001E8D5
0x1001e83c  push    dword ptr [eax+14h]
0x1001e83f  push    dword ptr [eax+10h]
0x1001e842  push    2Eh ; '.'
0x1001e844  jmp     loc_1001E8CA
0x1001e849  mov     eax, [ebp+var_3C]
0x1001e84c  cmp     eax, [ebx+8Ch]
0x1001e852  jl      short loc_1001E8B0
0x1001e854  cmp     eax, [ebx+94h]
0x1001e85a  jg      short loc_1001E8B0
0x1001e85c  cmp     esi, [ebx+90h]
0x1001e862  jl      short loc_1001E8B0
0x1001e864  cmp     esi, [ebx+98h]
0x1001e86a  jg      short loc_1001E8B0
0x1001e86c  mov     ecx, [ebx+9Ch]
0x1001e872  test    ecx, ecx
0x1001e874  jz      short loc_1001E8AC
0x1001e876  mov     edi, [ebx+0A0h]
0x1001e87c  test    edi, edi
0x1001e87e  jz      short loc_1001E8AC
0x1001e880  cdq
0x1001e881  idiv    ecx
0x1001e883  test    edx, edx
0x1001e885  jnz     short loc_1001E890
0x1001e887  mov     eax, esi
0x1001e889  cdq
0x1001e88a  idiv    edi
0x1001e88c  test    edx, edx
0x1001e88e  jz      short loc_1001E8AC
0x1001e890  mov     eax, _WPP_GLOBAL_Control
0x1001e895  cmp     eax, offset _WPP_GLOBAL_Control
0x1001e89a  jz      short loc_1001E8D5
0x1001e89c  cmp     byte ptr [eax+19h], 5
0x1001e8a0  jb      short loc_1001E8D5
0x1001e8a2  push    dword ptr [eax+14h]
0x1001e8a5  push    dword ptr [eax+10h]
0x1001e8a8  push    32h ; '2'
0x1001e8aa  jmp     short loc_1001E8CA
0x1001e8ac  xor     eax, eax
0x1001e8ae  jmp     short loc_1001E8DA
0x1001e8b0  mov     eax, _WPP_GLOBAL_Control
0x1001e8b5  cmp     eax, offset _WPP_GLOBAL_Control
0x1001e8ba  jz      short loc_1001E8D5
0x1001e8bc  cmp     byte ptr [eax+19h], 5
0x1001e8c0  jb      short loc_1001E8D5
0x1001e8c2  push    dword ptr [eax+14h]
0x1001e8c5  push    dword ptr [eax+10h]; LoggerHandle
0x1001e8c8  push    31h ; '1'
0x1001e8ca  mov     edx, offset _WPP_4461f5f2318c3c9afea4e63d8c8a6ec1_Traceguids; MessageGuid
0x1001e8cf  pop     ecx; MessageNumber
0x1001e8d0  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1001e8d5  mov     eax, 80004005h
0x1001e8da  mov     ecx, [ebp+var_4]
0x1001e8dd  pop     edi
0x1001e8de  pop     esi
0x1001e8df  xor     ecx, ebp; StackCookie
0x1001e8e1  pop     ebx
0x1001e8e2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001e8e7  leave
0x1001e8e8  retn
```
