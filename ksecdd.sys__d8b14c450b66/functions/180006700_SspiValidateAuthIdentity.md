# SspiValidateAuthIdentity

- ea: `0x180006700`
- end: `0x18000682a`
- name: `SspiValidateAuthIdentity`
- size: `298`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006048`
- `0x180006420`
- `0x180008cf0`

## callees

- `0x180006700`
- `0x180006830`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiValidateAuthIdentity(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthData)
{
  char *v1; // rdx
  unsigned int v2; // eax
  unsigned int v3; // r8d
  unsigned int v4; // ecx
  unsigned int v5; // r9d
  unsigned int v6; // ecx
  unsigned int v7; // r9d
  unsigned int v8; // ecx
  unsigned int v9; // r9d
  unsigned int v10; // ecx
  __int64 v11; // r9
  unsigned int v12; // r8d
  unsigned __int16 v13; // cx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  __int64 v16; // rcx

  v1 = (char *)AuthData;
  if ( *(_DWORD *)AuthData == 513 )
  {
    v2 = *((unsigned __int16 *)AuthData + 2);
    if ( v2 < 0x30 )
      goto LABEL_21;
    v3 = *((_DWORD *)AuthData + 2);
    if ( v3 > 0xFFF7 )
      goto LABEL_21;
    if ( v3 < v2 )
      goto LABEL_21;
    v4 = *((unsigned __int16 *)AuthData + 12);
    v5 = v4 + *((_DWORD *)v1 + 5);
    if ( v5 < v4 )
      goto LABEL_21;
    if ( v5 > v3 )
      goto LABEL_21;
    v6 = *((unsigned __int16 *)v1 + 8);
    v7 = v6 + *((_DWORD *)v1 + 3);
    if ( v7 < v6 )
      goto LABEL_21;
    if ( v7 > v3 )
      goto LABEL_21;
    v8 = *((unsigned __int16 *)v1 + 22);
    v9 = v8 + *((_DWORD *)v1 + 10);
    if ( v9 < v8 )
      goto LABEL_21;
    if ( v9 > v3 )
      goto LABEL_21;
    v10 = *((unsigned __int16 *)v1 + 16);
    v11 = *((unsigned int *)v1 + 7);
    if ( v10 + (unsigned int)v11 < v10 || v10 + (unsigned int)v11 > v3 )
      goto LABEL_21;
    if ( (_DWORD)v11 )
    {
      if ( v10 < 0x1C )
        goto LABEL_21;
      if ( (*((_DWORD *)v1 + 9) & 0x10) == 0 )
      {
        v12 = *(unsigned __int16 *)&v1[v11 + 2];
        if ( v12 > v10 )
          goto LABEL_21;
        v13 = *(_WORD *)&v1[v11];
        if ( (unsigned __int16)v12 < v13 )
          goto LABEL_21;
        if ( v13 < 0x1Cu )
          goto LABEL_21;
        v14 = *(_DWORD *)&v1[v11 + 20];
        v15 = v14 + *(unsigned __int16 *)&v1[v11 + 24];
        if ( v15 < v14 || v15 > v12 )
          goto LABEL_21;
      }
LABEL_33:
      v16 = 0;
      return SspNtStatusToSecStatus(v16);
    }
    if ( !(_WORD)v10 )
      goto LABEL_33;
  }
  else
  {
    if ( *(_DWORD *)AuthData == 512 )
    {
      if ( *((_DWORD *)AuthData + 1) < 0x48u || *((_DWORD *)AuthData + 16) > 0x7FFDu )
        goto LABEL_21;
      v1 = (char *)AuthData + 8;
    }
    if ( (*((_DWORD *)v1 + 11) & 3) != 0
      && *((_DWORD *)v1 + 2) <= 0x7FFDu
      && *((_DWORD *)v1 + 6) <= 0x7FFDu
      && *((_DWORD *)v1 + 10) <= 0x7FFDu )
    {
      goto LABEL_33;
    }
  }
LABEL_21:
  v16 = 3221225485LL;
  return SspNtStatusToSecStatus(v16);
}

```

## disassembly

```asm
0x180006700  sub     rsp, 28h
0x180006704  mov     eax, [rcx]
0x180006706  xor     r10d, r10d
0x180006709  mov     rdx, rcx
0x18000670c  cmp     eax, 201h
0x180006711  jnz     loc_1800067F4
0x180006717  movzx   eax, word ptr [rcx+4]
0x18000671b  cmp     eax, 30h ; '0'
0x18000671e  jb      loc_1800067DD
0x180006724  mov     r8d, [rcx+8]
0x180006728  cmp     r8d, 0FFF7h
0x18000672f  ja      loc_1800067DD
0x180006735  cmp     r8d, eax
0x180006738  jb      loc_1800067DD
0x18000673e  movzx   ecx, word ptr [rcx+18h]
0x180006742  mov     r9d, [rdx+14h]
0x180006746  add     r9d, ecx
0x180006749  cmp     r9d, ecx
0x18000674c  jb      loc_1800067DD
0x180006752  cmp     r9d, r8d
0x180006755  ja      loc_1800067DD
0x18000675b  movzx   ecx, word ptr [rdx+10h]
0x18000675f  mov     r9d, [rdx+0Ch]
0x180006763  add     r9d, ecx
0x180006766  cmp     r9d, ecx
0x180006769  jb      short loc_1800067DD
0x18000676b  cmp     r9d, r8d
0x18000676e  ja      short loc_1800067DD
0x180006770  movzx   ecx, word ptr [rdx+2Ch]
0x180006774  mov     r9d, [rdx+28h]
0x180006778  add     r9d, ecx
0x18000677b  cmp     r9d, ecx
0x18000677e  jb      short loc_1800067DD
0x180006780  cmp     r9d, r8d
0x180006783  ja      short loc_1800067DD
0x180006785  movzx   ecx, word ptr [rdx+20h]
0x180006789  mov     r9d, [rdx+1Ch]
0x18000678d  lea     eax, [rcx+r9]
0x180006791  cmp     eax, ecx
0x180006793  jb      short loc_1800067DD
0x180006795  cmp     eax, r8d
0x180006798  ja      short loc_1800067DD
0x18000679a  test    r9d, r9d
0x18000679d  jz      short loc_1800067ED
0x18000679f  cmp     ecx, 1Ch
0x1800067a2  jb      short loc_1800067DD
0x1800067a4  mov     eax, [rdx+24h]
0x1800067a7  test    al, 10h
0x1800067a9  jnz     short loc_180006825
0x1800067ab  movzx   r8d, word ptr [r9+rdx+2]
0x1800067b1  cmp     r8d, ecx
0x1800067b4  ja      short loc_1800067DD
0x1800067b6  movzx   ecx, word ptr [r9+rdx]
0x1800067bb  cmp     r8w, cx
0x1800067bf  jb      short loc_1800067DD
0x1800067c1  cmp     cx, 1Ch
0x1800067c5  jb      short loc_1800067DD
0x1800067c7  mov     ecx, [r9+rdx+14h]
0x1800067cc  movzx   edx, word ptr [r9+rdx+18h]
0x1800067d2  add     edx, ecx
0x1800067d4  cmp     edx, ecx
0x1800067d6  jb      short loc_1800067DD
0x1800067d8  cmp     edx, r8d
0x1800067db  jbe     short loc_180006825
0x1800067dd  mov     ecx, 0C000000Dh
0x1800067e2  call    SspNtStatusToSecStatus
0x1800067e7  add     rsp, 28h
0x1800067eb  retn
0x1800067ed  test    cx, cx
0x1800067f0  jnz     short loc_1800067DD
0x1800067f2  jmp     short loc_180006825
0x1800067f4  mov     ecx, 7FFDh
0x1800067f9  cmp     eax, 200h
0x1800067fe  jnz     short loc_18000680F
0x180006800  cmp     dword ptr [rdx+4], 48h ; 'H'
0x180006804  jb      short loc_1800067DD
0x180006806  cmp     [rdx+40h], ecx
0x180006809  ja      short loc_1800067DD
0x18000680b  add     rdx, 8
0x18000680f  mov     eax, [rdx+2Ch]
0x180006812  test    al, 3
0x180006814  jz      short loc_1800067DD
0x180006816  cmp     [rdx+8], ecx
0x180006819  ja      short loc_1800067DD
0x18000681b  cmp     [rdx+18h], ecx
0x18000681e  ja      short loc_1800067DD
0x180006820  cmp     [rdx+28h], ecx
0x180006823  ja      short loc_1800067DD
0x180006825  mov     ecx, r10d
0x180006828  jmp     short loc_1800067E2
```
