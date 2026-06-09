# LString::Compare(uchar *,uint,LSpec)

- ea: `0x1004dbb0`
- end: `0x1004e029`
- name: `?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z`
- size: `1145`
- prototype: `int __thiscall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `11`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10026200`
- `0x1002dc90`
- `0x10036dc0`
- `0x10037710`
- `0x10043210`
- `0x10043450`
- `0x10054c30`
- `0x10055bc0`
- `0x10056280`
- `0x10056ff0`
- `0x10057150`

## callees

- `0x10008260`
- `0x1000f750`
- `0x10025ee0`
- `0x1004dbb0`
- `0x1004e050`
- `0x1004e290`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`

## import_xrefs

- `mswstr10!__imp__DBCompareStringW@24` at `0x1004dcee`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1004dcee`

## pseudocode

```c
int __thiscall LString::Compare(_DWORD *this, const WCHAR *lpWideCharStr, unsigned int a3, int a4)
{
  int v4; // esi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  void *v7; // edi
  int v8; // ecx
  int v9; // eax
  int v10; // ecx
  void *v11; // eax
  int v12; // ecx
  int v13; // edi
  UINT v14; // ecx
  int v15; // ecx
  unsigned int v16; // ebx
  int v17; // eax
  const WCHAR *v18; // esi
  int v19; // eax
  const unsigned __int8 **v20; // eax
  unsigned int v21; // ebx
  int v22; // ecx
  unsigned int v23; // edi
  unsigned __int8 *v24; // eax
  int v25; // edx
  unsigned __int8 v26; // al
  int v27; // eax
  unsigned int v28; // ecx
  unsigned __int8 *v29; // edx
  unsigned int v30; // eax
  unsigned __int8 v31; // al
  const unsigned __int8 **v32; // edx
  unsigned __int8 v33; // ch
  int v34; // eax
  int v35; // eax
  unsigned __int8 v36; // cl
  const unsigned __int8 *v37; // edx
  unsigned __int8 v38; // al
  unsigned __int8 v39; // cl
  const unsigned __int8 *v40; // edx
  unsigned __int8 v41; // ch
  int v42; // edx
  bool v43; // cf
  int v45; // [esp-8h] [ebp-74h]
  int v46; // [esp-4h] [ebp-70h]
  int v47; // [esp-4h] [ebp-70h]
  const unsigned __int8 *v48; // [esp+0h] [ebp-6Ch]
  unsigned int *v49; // [esp+4h] [ebp-68h]
  int v50[3]; // [esp+10h] [ebp-5Ch] BYREF
  void *v51; // [esp+1Ch] [ebp-50h]
  void *v52; // [esp+20h] [ebp-4Ch]
  unsigned __int8 ***v53; // [esp+24h] [ebp-48h]
  unsigned __int8 *v54; // [esp+28h] [ebp-44h]
  int v55; // [esp+2Ch] [ebp-40h] BYREF
  unsigned int v56; // [esp+30h] [ebp-3Ch]
  void *v57; // [esp+34h] [ebp-38h]
  void *Block; // [esp+38h] [ebp-34h]
  int v59; // [esp+3Ch] [ebp-30h] BYREF
  const unsigned __int8 **v60; // [esp+40h] [ebp-2Ch]
  _DWORD *v61; // [esp+44h] [ebp-28h]
  int v62; // [esp+48h] [ebp-24h]
  unsigned __int8 *v63; // [esp+4Ch] [ebp-20h]
  unsigned __int8 *v64; // [esp+50h] [ebp-1Ch]
  unsigned int v65; // [esp+54h] [ebp-18h] BYREF
  unsigned int v66; // [esp+58h] [ebp-14h] BYREF
  unsigned __int8 v67; // [esp+5Ch] [ebp-10h]
  unsigned __int8 v68; // [esp+5Dh] [ebp-Fh]
  unsigned __int8 v69; // [esp+5Eh] [ebp-Eh]
  unsigned __int8 v70; // [esp+5Fh] [ebp-Dh]
  int v71; // [esp+68h] [ebp-4h]

  v61 = this;
  v50[0] = 1;
  v4 = 0;
  v71 = 0;
  v5 = this[1];
  v6 = this[2] & 0x80000000;
  v55 = a3;
  v59 = v5;
  if ( a3 )
  {
    if ( v5 )
    {
      v7 = operator new[](v5);
      Block = v7;
      v9 = ErrGenericWideNToCbMultiByte(
             *((unsigned __int16 *)v61 + 6),
             (LPCWCH)*v61,
             v61[1] >> 1,
             (LPSTR)v7,
             (int)&v59,
             v8,
             v46);
      if ( v9 >= 0 )
      {
        v11 = operator new[](a3);
        v45 = v12;
        v13 = a3 >> 1;
        v14 = *((unsigned __int16 *)v61 + 6);
        v57 = v11;
        if ( ErrGenericWideNToCbMultiByte(v14, lpWideCharStr, a3 >> 1, (LPSTR)v11, (int)&v55, v45, v47) >= 0 )
        {
          v15 = v61[2];
          v56 = v15;
          if ( v15 <= 256 )
          {
            v20 = (&Collate::m_pAddress)[v15];
            v21 = v59;
            v22 = v59;
            v23 = v55;
            v60 = v20;
            v24 = (unsigned __int8 *)Block;
            v63 = (unsigned __int8 *)v57;
            v25 = v55;
            v62 = (int)Block;
            if ( a4 != 1 )
            {
              if ( v59 )
              {
                do
                {
                  if ( *((char *)Block + v22 - 1) != 32 )
                    break;
                  --v22;
                }
                while ( v22 );
              }
              if ( v55 )
              {
                do
                {
                  if ( *((char *)v57 + v25 - 1) != 32 )
                    break;
                  --v25;
                }
                while ( v25 );
                v24 = (unsigned __int8 *)v62;
              }
            }
            for ( ; v22; --v22 )
            {
              if ( !v25 )
                break;
              v4 = 0;
              v67 = *((_BYTE *)v60 + *v24);
              if ( v67 == 0xFF )
                break;
              v26 = *((_BYTE *)v60 + *v63);
              v21 = v59;
              if ( v26 == 0xFF )
                break;
              if ( v67 != v26 )
              {
                v4 = v67 < v26 ? -1 : 1;
                goto LABEL_78;
              }
              --v25;
              ++v63;
              v24 = (unsigned __int8 *)++v62;
            }
            v64 = (unsigned __int8 *)Block;
            v27 = dword_10004020[v56];
            v63 = (unsigned __int8 *)v57;
            v53 = &(&off_10066050)[v27];
            if ( a4 != 1 )
            {
              for ( ; v21; --v21 )
              {
                if ( *((char *)Block + v21 - 1) != 32 )
                  break;
              }
              if ( v55 )
              {
                do
                {
                  if ( *((char *)v57 + v23 - 1) != 32 )
                    break;
                  --v23;
                }
                while ( v23 );
              }
            }
            v28 = 0;
            v55 = 1;
            v29 = 0;
            v65 = 0;
            v30 = 0;
            v59 = 0;
            v56 = 0;
            v66 = 0;
            v62 = 0;
            while ( (v21 || v28) && (v23 || v30) )
            {
              if ( v28 )
              {
                v70 = *v29;
                v31 = v29[1];
                v59 = (int)(v29 + 2);
                v32 = v60;
                v65 = v28 - 1;
                v33 = v70;
              }
              else
              {
                v32 = v60;
                v34 = *v64;
                v33 = *((_BYTE *)v60 + v34);
                v31 = *((_BYTE *)v60 + v34 + 256);
                v70 = v33;
              }
              v69 = v31;
              if ( v66 )
              {
                v67 = *(_BYTE *)v56;
                v68 = *(_BYTE *)(v56 + 1);
                v56 += 2;
                --v66;
              }
              else
              {
                v35 = *v63;
                v36 = *((_BYTE *)v32 + v35);
                LOBYTE(v35) = *((_BYTE *)v32 + v35 + 256);
                v67 = v36;
                v68 = v35;
              }
              if ( v33 == 0xFF )
              {
                v59 = (int)(v64 + 1);
                v54 = (unsigned __int8 *)(v21 - 1);
                v37 = SetException(v53[v69], &v65, v48, v49);
                --v65;
                v64 = (unsigned __int8 *)(v59 - 1);
                v38 = v37[1];
                v70 = *v37;
                v69 = v38;
                v59 = (int)(v37 + 2);
                if ( !v70 )
                {
LABEL_57:
                  v4 = LString::ArabicBailout(v61, lpWideCharStr, a3);
                  goto LABEL_78;
                }
              }
              v39 = v67;
              if ( v67 == 0xFF )
              {
                v54 = v63 + 1;
                v56 = v23 - 1;
                v40 = SetException(v53[v68], &v66, v48, v49);
                v23 = v56 + 1;
                v63 = v54 - 1;
                v39 = *v40;
                v30 = v66 - 1;
                v41 = v40[1];
                v56 = (unsigned int)(v40 + 2);
                --v66;
                if ( !v39 )
                  goto LABEL_57;
              }
              else
              {
                v30 = v66;
                v41 = v68;
              }
              if ( v70 < v39 )
              {
LABEL_77:
                v4 = -1;
                goto LABEL_78;
              }
              if ( v70 > v39 )
              {
                v4 = 1;
                goto LABEL_78;
              }
              v42 = v62;
              if ( !v62 )
              {
                if ( v69 >= v41 )
                {
                  if ( v69 > v41 )
                    v42 = v55;
                  v62 = v42;
                }
                else
                {
                  v62 = -1;
                }
              }
              v28 = v65;
              if ( !v65 )
              {
                ++v64;
                --v21;
              }
              v29 = (unsigned __int8 *)v59;
              if ( !v30 )
              {
                ++v63;
                --v23;
              }
            }
            switch ( a4 )
            {
              case 0:
                if ( v21 < v23 )
                  goto LABEL_77;
                v4 = v62;
                if ( v21 > v23 )
                  v4 = v55;
                break;
              case 1:
                v4 = v55;
                if ( v21 <= v23 )
                  v4 = v62;
                break;
              case 2:
                v43 = v23 < v21;
                if ( v23 > v21 )
                  goto LABEL_77;
                goto LABEL_90;
              case 3:
                v43 = v23 < v21;
LABEL_90:
                v4 = v43;
                break;
              default:
                break;
            }
          }
          else
          {
            v16 = v6 + 196609;
            v17 = v61[1] >> 1;
            if ( (v15 & 0xA0000000) != 0 )
            {
              v18 = lpWideCharStr;
            }
            else
            {
              if ( v17 )
              {
                do
                {
                  if ( *(_BYTE *)(*v61 + v17 - 1) != 32 )
                    break;
                  --v17;
                }
                while ( v17 > 0 );
                v15 = v56;
              }
              v18 = lpWideCharStr;
              if ( v13 )
              {
                do
                {
                  if ( *((_BYTE *)lpWideCharStr + v13 - 1) != 32 )
                    break;
                  --v13;
                }
                while ( v13 > 0 );
              }
            }
            v19 = DBCompareStringW(v15 & 0xFFFEFF, v16, *v61, v17, v18, v13);
            v4 = v19 != 0 ? v19 - 2 : 0;
          }
        }
LABEL_78:
        operator delete[](Block);
        if ( v57 )
          operator delete[](v57);
      }
      else
      {
        Err::SetError(v50, v9, v10);
        operator delete[](v7);
      }
    }
    else
    {
      v4 = -1;
    }
  }
  else
  {
    v4 = v5 != 0;
  }
  if ( (v50[0] & 0xFFFFFFFE) != 0 )
  {
    if ( v51 )
      operator delete[](v51);
    if ( v52 )
      operator delete[](v52);
  }
  return v4;
}

```

## disassembly

```asm
0x1004dbb0  mov     edi, edi
0x1004dbb2  push    ebp
0x1004dbb3  mov     ebp, esp
0x1004dbb5  push    0FFFFFFFFh
0x1004dbb7  push    offset ?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z_SEH
0x1004dbbc  mov     eax, large fs:0
0x1004dbc2  push    eax
0x1004dbc3  sub     esp, 50h
0x1004dbc6  push    ebx
0x1004dbc7  push    esi
0x1004dbc8  push    edi; unsigned int *
0x1004dbc9  mov     eax, ___security_cookie
0x1004dbce  xor     eax, ebp
0x1004dbd0  push    eax; unsigned __int8 *
0x1004dbd1  lea     eax, [ebp+var_C]
0x1004dbd4  mov     large fs:0, eax
0x1004dbda  mov     eax, ecx
0x1004dbdc  mov     [ebp+var_28], eax
0x1004dbdf  mov     [ebp+var_5C], 1
0x1004dbe6  mov     ecx, [ebp+arg_4]
0x1004dbe9  xor     esi, esi
0x1004dbeb  mov     [ebp+var_4], 0
0x1004dbf2  mov     ebx, [eax+8]
0x1004dbf5  mov     eax, [eax+4]
0x1004dbf8  and     ebx, 80000000h
0x1004dbfe  mov     [ebp+var_40], ecx
0x1004dc01  mov     [ebp+var_30], eax
0x1004dc04  test    ecx, ecx
0x1004dc06  jnz     short loc_1004DC1A
0x1004dc08  test    eax, eax
0x1004dc0a  jz      loc_1004DFD0
0x1004dc10  mov     esi, 1
0x1004dc15  jmp     loc_1004DFD0
0x1004dc1a  test    eax, eax
0x1004dc1c  jnz     short loc_1004DC26
0x1004dc1e  or      esi, 0FFFFFFFFh
0x1004dc21  jmp     loc_1004DFD0
0x1004dc26  push    eax; int
0x1004dc27  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1004dc2c  push    ecx; int
0x1004dc2d  mov     ecx, [ebp+var_28]
0x1004dc30  mov     edi, eax
0x1004dc32  lea     eax, [ebp+var_30]
0x1004dc35  mov     [ebp+Block], edi
0x1004dc38  push    eax; int
0x1004dc39  push    edi; lpMultiByteStr
0x1004dc3a  mov     eax, [ecx+4]
0x1004dc3d  shr     eax, 1
0x1004dc3f  push    eax; cchWideChar
0x1004dc40  push    dword ptr [ecx]; lpWideCharStr
0x1004dc42  movzx   ecx, word ptr [ecx+0Ch]; CodePage
0x1004dc46  call    _ErrGenericWideNToCbMultiByte@32; ErrGenericWideNToCbMultiByte(x,x,x,x,x,x,x,x)
0x1004dc4b  test    eax, eax
0x1004dc4d  jns     short loc_1004DC5F
0x1004dc4f  push    ecx
0x1004dc50  push    eax
0x1004dc51  lea     ecx, [ebp+var_5C]
0x1004dc54  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004dc59  push    edi
0x1004dc5a  jmp     loc_1004DFC8
0x1004dc5f  mov     edi, [ebp+arg_4]
0x1004dc62  push    edi; int
0x1004dc63  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1004dc68  push    ecx; int
0x1004dc69  lea     ecx, [ebp+var_40]
0x1004dc6c  shr     edi, 1
0x1004dc6e  push    ecx; int
0x1004dc6f  mov     ecx, [ebp+var_28]
0x1004dc72  push    eax; lpMultiByteStr
0x1004dc73  push    edi; cchWideChar
0x1004dc74  push    [ebp+lpWideCharStr]; lpWideCharStr
0x1004dc77  movzx   ecx, word ptr [ecx+0Ch]; CodePage
0x1004dc7b  mov     [ebp+var_38], eax
0x1004dc7e  call    _ErrGenericWideNToCbMultiByte@32; ErrGenericWideNToCbMultiByte(x,x,x,x,x,x,x,x)
0x1004dc83  test    eax, eax
0x1004dc85  js      def_1004DF9A; jumptable 1004DF9A default case
0x1004dc8b  mov     edx, [ebp+var_28]
0x1004dc8e  mov     ecx, [edx+8]
0x1004dc91  mov     [ebp+var_3C], ecx
0x1004dc94  cmp     ecx, 100h
0x1004dc9a  jle     short loc_1004DD04
0x1004dc9c  mov     eax, [edx+4]
0x1004dc9f  add     ebx, 30001h
0x1004dca5  shr     eax, 1
0x1004dca7  test    ecx, 0A0000000h
0x1004dcad  jnz     short loc_1004DCDE
0x1004dcaf  test    eax, eax
0x1004dcb1  jz      short loc_1004DCC4
0x1004dcb3  mov     ecx, [edx]
0x1004dcb5  cmp     byte ptr [ecx+eax-1], 20h ; ' '
0x1004dcba  jnz     short loc_1004DCC1
0x1004dcbc  dec     eax
0x1004dcbd  test    eax, eax
0x1004dcbf  jg      short loc_1004DCB5
0x1004dcc1  mov     ecx, [ebp+var_3C]
0x1004dcc4  mov     esi, [ebp+lpWideCharStr]
0x1004dcc7  test    edi, edi
0x1004dcc9  jz      short loc_1004DCE1
0x1004dccb  nop     dword ptr [eax+eax+00h]
0x1004dcd0  cmp     byte ptr [esi+edi-1], 20h ; ' '
0x1004dcd5  jnz     short loc_1004DCE1
0x1004dcd7  dec     edi
0x1004dcd8  test    edi, edi
0x1004dcda  jg      short loc_1004DCD0
0x1004dcdc  jmp     short loc_1004DCE1
0x1004dcde  mov     esi, [ebp+lpWideCharStr]
0x1004dce1  push    edi
0x1004dce2  push    esi
0x1004dce3  push    eax
0x1004dce4  push    dword ptr [edx]
0x1004dce6  and     ecx, 0FFFEFFh
0x1004dcec  push    ebx
0x1004dced  push    ecx
0x1004dcee  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1004dcf4  mov     esi, eax
0x1004dcf6  lea     eax, [esi-2]
0x1004dcf9  neg     esi
0x1004dcfb  sbb     esi, esi
0x1004dcfd  and     esi, eax
0x1004dcff  jmp     def_1004DF9A; jumptable 1004DF9A default case
0x1004dd04  cmp     [ebp+arg_8], 1
0x1004dd08  mov     eax, ds:?m_pAddress@Collate@@0PAPBEA[ecx*4]; uchar const * * Collate::m_pAddress
0x1004dd0f  mov     edx, [ebp+var_38]
0x1004dd12  mov     ebx, [ebp+var_30]
0x1004dd15  mov     ecx, ebx
0x1004dd17  mov     edi, [ebp+var_40]
0x1004dd1a  mov     [ebp+var_2C], eax
0x1004dd1d  mov     eax, [ebp+Block]
0x1004dd20  mov     [ebp+var_20], edx
0x1004dd23  mov     edx, edi
0x1004dd25  mov     [ebp+var_24], eax
0x1004dd28  jz      short loc_1004DD52
0x1004dd2a  test    ecx, ecx
0x1004dd2c  jz      short loc_1004DD3C
0x1004dd2e  mov     edi, edi
0x1004dd30  cmp     byte ptr [eax+ecx-1], 20h ; ' '
0x1004dd35  jnz     short loc_1004DD3C
0x1004dd37  sub     ecx, 1
0x1004dd3a  jnz     short loc_1004DD30
0x1004dd3c  test    edx, edx
0x1004dd3e  jz      short loc_1004DD52
0x1004dd40  mov     eax, [ebp+var_38]
0x1004dd43  cmp     byte ptr [eax+edx-1], 20h ; ' '
0x1004dd48  jnz     short loc_1004DD4F
0x1004dd4a  sub     edx, 1
0x1004dd4d  jnz     short loc_1004DD43
0x1004dd4f  mov     eax, [ebp+var_24]
0x1004dd52  test    ecx, ecx
0x1004dd54  jz      short loc_1004DD9D
0x1004dd56  test    edx, edx
0x1004dd58  jz      short loc_1004DD9D
0x1004dd5a  mov     esi, [ebp+var_2C]
0x1004dd5d  movzx   eax, byte ptr [eax]
0x1004dd60  mov     al, [eax+esi]
0x1004dd63  mov     esi, 0
0x1004dd68  mov     [ebp+var_10], al
0x1004dd6b  cmp     al, 0FFh
0x1004dd6d  jz      short loc_1004DD9D
0x1004dd6f  mov     eax, [ebp+var_20]
0x1004dd72  mov     ebx, [ebp+var_2C]
0x1004dd75  movzx   eax, byte ptr [eax]
0x1004dd78  mov     al, [eax+ebx]
0x1004dd7b  mov     ebx, [ebp+var_30]
0x1004dd7e  cmp     al, 0FFh
0x1004dd80  jz      short loc_1004DD9D
0x1004dd82  mov     ah, [ebp+var_10]
0x1004dd85  cmp     ah, al
0x1004dd87  jnz     loc_1004DE36
0x1004dd8d  mov     eax, [ebp+var_24]
0x1004dd90  dec     edx
0x1004dd91  inc     [ebp+var_20]
0x1004dd94  inc     eax
0x1004dd95  mov     [ebp+var_24], eax
0x1004dd98  sub     ecx, 1
0x1004dd9b  jnz     short loc_1004DD56
0x1004dd9d  cmp     [ebp+arg_8], 1
0x1004dda1  mov     eax, [ebp+var_3C]
0x1004dda4  mov     edx, [ebp+Block]
0x1004dda7  mov     ecx, [ebp+var_38]
0x1004ddaa  mov     [ebp+var_1C], edx
0x1004ddad  mov     eax, ds:dword_10004020[eax*4]
0x1004ddb4  mov     [ebp+var_20], ecx
0x1004ddb7  lea     eax, off_10066050[eax*4]
0x1004ddbe  mov     [ebp+var_48], eax
0x1004ddc1  jz      short loc_1004DDE3
0x1004ddc3  test    ebx, ebx
0x1004ddc5  jz      short loc_1004DDD3
0x1004ddc7  cmp     byte ptr [edx+ebx-1], 20h ; ' '
0x1004ddcc  jnz     short loc_1004DDD3
0x1004ddce  sub     ebx, 1
0x1004ddd1  jnz     short loc_1004DDC7
0x1004ddd3  test    edi, edi
0x1004ddd5  jz      short loc_1004DDE3
0x1004ddd7  cmp     byte ptr [ecx+edi-1], 20h ; ' '
0x1004dddc  jnz     short loc_1004DDE3
0x1004ddde  sub     edi, 1
0x1004dde1  jnz     short loc_1004DDD7
0x1004dde3  xor     ecx, ecx
0x1004dde5  mov     [ebp+var_40], 1
0x1004ddec  xor     edx, edx
0x1004ddee  mov     [ebp+var_18], ecx
0x1004ddf1  xor     eax, eax
0x1004ddf3  mov     [ebp+var_30], edx
0x1004ddf6  mov     [ebp+var_3C], ecx
0x1004ddf9  mov     [ebp+var_14], eax
0x1004ddfc  mov     [ebp+var_24], eax
0x1004ddff  nop
0x1004de00  test    ebx, ebx
0x1004de02  jnz     short loc_1004DE0C
0x1004de04  test    ecx, ecx
0x1004de06  jz      loc_1004DF92
0x1004de0c  test    edi, edi
0x1004de0e  jnz     short loc_1004DE18
0x1004de10  test    eax, eax
0x1004de12  jz      loc_1004DF92
0x1004de18  test    ecx, ecx
0x1004de1a  jz      short loc_1004DE41
0x1004de1c  mov     al, [edx]
0x1004de1e  mov     [ebp+var_D], al
0x1004de21  mov     al, [edx+1]
0x1004de24  add     edx, 2
0x1004de27  dec     ecx
0x1004de28  mov     [ebp+var_30], edx
0x1004de2b  mov     edx, [ebp+var_2C]
0x1004de2e  mov     [ebp+var_18], ecx
0x1004de31  mov     ch, [ebp+var_D]
0x1004de34  jmp     short loc_1004DE57
0x1004de36  sbb     esi, esi
0x1004de38  and     esi, 0FFFFFFFEh
0x1004de3b  inc     esi
0x1004de3c  jmp     def_1004DF9A; jumptable 1004DF9A default case
0x1004de41  mov     eax, [ebp+var_1C]
0x1004de44  mov     edx, [ebp+var_2C]
0x1004de47  movzx   eax, byte ptr [eax]
0x1004de4a  mov     ch, [eax+edx]
0x1004de4d  mov     al, [eax+edx+100h]
0x1004de54  mov     [ebp+var_D], ch
0x1004de57  mov     [ebp+var_E], al
0x1004de5a  mov     eax, [ebp+var_14]
0x1004de5d  test    eax, eax
0x1004de5f  jz      short loc_1004DE7B
0x1004de61  mov     edx, [ebp+var_3C]
0x1004de64  mov     cl, [edx]
0x1004de66  mov     [ebp+var_10], cl
0x1004de69  mov     cl, [edx+1]
0x1004de6c  add     edx, 2
0x1004de6f  dec     eax
0x1004de70  mov     [ebp+var_F], cl
0x1004de73  mov     [ebp+var_3C], edx
0x1004de76  mov     [ebp+var_14], eax
0x1004de79  jmp     short loc_1004DE91
0x1004de7b  mov     eax, [ebp+var_20]
0x1004de7e  movzx   eax, byte ptr [eax]
0x1004de81  mov     cl, [eax+edx]
0x1004de84  mov     al, [eax+edx+100h]
0x1004de8b  mov     [ebp+var_10], cl
0x1004de8e  mov     [ebp+var_F], al
0x1004de91  cmp     ch, 0FFh
0x1004de94  jnz     short loc_1004DEE1
0x1004de96  mov     eax, [ebp+var_1C]
0x1004de99  lea     edx, [ebp+var_44]
0x1004de9c  mov     ecx, [ebp+var_48]
0x1004de9f  inc     eax
0x1004dea0  mov     [ebp+var_30], eax
0x1004dea3  lea     eax, [ebx-1]
0x1004dea6  mov     [ebp+var_44], eax
0x1004dea9  lea     eax, [ebp+var_18]
0x1004deac  push    eax; unsigned int *
0x1004dead  movzx   eax, [ebp+var_E]
0x1004deb1  push    dword ptr [ecx+eax*4]; unsigned __int8 **
0x1004deb4  lea     ecx, [ebp+var_30]
0x1004deb7  call    ?SetException@@YGPBEPAPAEPAIPBE1@Z; SetException(uchar * *,uint *,uchar const *,uint *)
0x1004debc  mov     ebx, [ebp+var_44]
0x1004debf  mov     edx, eax
0x1004dec1  mov     eax, [ebp+var_30]
0x1004dec4  inc     ebx
0x1004dec5  dec     [ebp+var_18]
0x1004dec8  dec     eax
0x1004dec9  mov     [ebp+var_1C], eax
0x1004decc  mov     ch, [edx]
0x1004dece  mov     al, [edx+1]
0x1004ded1  add     edx, 2
0x1004ded4  mov     [ebp+var_D], ch
0x1004ded7  mov     [ebp+var_E], al
0x1004deda  mov     [ebp+var_30], edx
0x1004dedd  test    ch, ch
0x1004dedf  jz      short loc_1004DF32
0x1004dee1  mov     cl, [ebp+var_10]
0x1004dee4  cmp     cl, 0FFh
0x1004dee7  jnz     short loc_1004DF44
0x1004dee9  mov     eax, [ebp+var_20]
0x1004deec  lea     edx, [ebp+var_3C]
0x1004deef  mov     ecx, [ebp+var_48]
0x1004def2  inc     eax
0x1004def3  mov     [ebp+var_44], eax
0x1004def6  lea     eax, [edi-1]
0x1004def9  mov     [ebp+var_3C], eax
0x1004defc  lea     eax, [ebp+var_14]
0x1004deff  push    eax; unsigned int *
0x1004df00  movzx   eax, [ebp+var_F]
  ... truncated ...
```
