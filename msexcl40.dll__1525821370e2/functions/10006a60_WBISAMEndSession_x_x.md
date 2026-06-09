# WBISAMEndSession(x,x)

- ea: `0x10006a60`
- end: `0x10006bc8`
- name: `_WBISAMEndSession@8`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x10007090`

## callees

- `0x10006a60`
- `0x100279f0`
- `0x1002a80e`
- `0x1002af20`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10006b64`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10006b64`

## pseudocode

```c
int __stdcall WBISAMEndSession(int a1, int a2)
{
  _DWORD *v2; // eax
  _DWORD *v3; // ebx
  int v4; // ecx
  _DWORD *v6; // eax
  _DWORD *v7; // edi
  _DWORD *v8; // eax
  _DWORD *v9; // esi
  int v10; // eax
  _DWORD *v11; // eax
  int v12; // edx
  _DWORD *v13; // eax
  _DWORD *v14; // esi
  _DWORD *v15; // edi
  DWORD CurrentProcessId; // ecx
  _DWORD *v17; // eax
  int v18; // [esp+4h] [ebp-10h]
  _DWORD *v19; // [esp+8h] [ebp-Ch]
  int v20; // [esp+Ch] [ebp-8h]
  _DWORD *v21; // [esp+10h] [ebp-4h]

  v2 = (_DWORD *)dword_1003AE68;
  if ( !dword_1003AE68 )
    return -1104;
  while ( 1 )
  {
    v3 = (_DWORD *)v2[1];
    if ( v3 )
      break;
LABEL_6:
    v2 = (_DWORD *)*v2;
    if ( !v2 )
      return -1104;
  }
  v4 = a1;
  while ( v3[3] != a1 )
  {
    v3 = (_DWORD *)*v3;
    if ( !v3 )
      goto LABEL_6;
  }
  dword_1003AE5C = v3[4];
  v18 = v3[1];
  v6 = *(_DWORD **)(v18 + 8);
  v20 = 0;
  if ( v6 )
  {
    do
    {
      v7 = (_DWORD *)*v6;
      v8 = (_DWORD *)v6[11];
      if ( v8 )
      {
        do
        {
          v9 = (_DWORD *)*v8;
          if ( (_DWORD *)v8[2] == v3 )
          {
            v10 = WBDBCloseDatabase(v4, v8[3], 0);
            v4 = a1;
            v20 = v10;
          }
          v8 = v9;
        }
        while ( v9 );
      }
      v6 = v7;
    }
    while ( v7 );
  }
  v11 = (_DWORD *)v3[2];
  if ( v11 )
  {
    do
    {
      v19 = (_DWORD *)*v11;
      v12 = v11[3];
      v13 = (_DWORD *)dword_1003AE68;
      if ( dword_1003AE68 )
      {
        while ( 1 )
        {
          v14 = (_DWORD *)v13[1];
          if ( v14 )
            break;
LABEL_19:
          v13 = (_DWORD *)*v13;
          if ( !v13 )
            goto LABEL_31;
        }
        while ( v14[3] != v4 )
        {
          v14 = (_DWORD *)*v14;
          if ( !v14 )
            goto LABEL_19;
        }
        dword_1003AE5C = v14[4];
        v15 = (_DWORD *)v14[2];
        v21 = v15;
        if ( v15 )
        {
          while ( v15[3] != v12 )
          {
            v15 = (_DWORD *)*v15;
            v21 = v15;
            if ( !v15 )
              goto LABEL_31;
          }
          CurrentProcessId = GetCurrentProcessId();
          v17 = (_DWORD *)dword_1003AE68;
          if ( dword_1003AE68 )
          {
            v21 = v15;
            while ( v17[4] != CurrentProcessId )
            {
              v17 = (_DWORD *)*v17;
              if ( !v17 )
                goto LABEL_29;
            }
          }
          else
          {
LABEL_29:
            v17 = 0;
          }
          (*(void (__thiscall **)(_DWORD, _DWORD))(v17[7] + 68))(*(_DWORD *)(v17[7] + 68), v15[4]);
          ISAMDBDeleteVTDef(v14, v21);
        }
      }
LABEL_31:
      v11 = v19;
      v4 = a1;
    }
    while ( v19 );
  }
  ISAMDBDeleteSession(v18, v3);
  return v20;
}

```

## disassembly

```asm
0x10006a60  mov     edi, edi
0x10006a62  push    ebp
0x10006a63  mov     ebp, esp
0x10006a65  mov     eax, dword_1003AE68
0x10006a6a  sub     esp, 10h
0x10006a6d  push    ebx
0x10006a6e  test    eax, eax
0x10006a70  jz      short loc_10006A91
0x10006a72  mov     ebx, [eax+4]
0x10006a75  test    ebx, ebx
0x10006a77  jz      short loc_10006A8B
0x10006a79  mov     ecx, [ebp+arg_0]
0x10006a7c  nop     dword ptr [eax+00h]
0x10006a80  cmp     [ebx+0Ch], ecx
0x10006a83  jz      short loc_10006A9D
0x10006a85  mov     ebx, [ebx]
0x10006a87  test    ebx, ebx
0x10006a89  jnz     short loc_10006A80
0x10006a8b  mov     eax, [eax]
0x10006a8d  test    eax, eax
0x10006a8f  jnz     short loc_10006A72
0x10006a91  mov     eax, 0FFFFFBB0h
0x10006a96  pop     ebx
0x10006a97  mov     esp, ebp
0x10006a99  pop     ebp
0x10006a9a  retn    8
0x10006a9d  mov     eax, [ebx+10h]
0x10006aa0  mov     dword_1003AE5C, eax
0x10006aa5  test    ebx, ebx
0x10006aa7  jz      short loc_10006A91
0x10006aa9  mov     eax, [ebx+4]
0x10006aac  mov     [ebp+var_10], eax
0x10006aaf  push    esi
0x10006ab0  push    edi
0x10006ab1  mov     eax, [eax+8]
0x10006ab4  mov     [ebp+var_8], 0
0x10006abb  test    eax, eax
0x10006abd  jz      short loc_10006AF4
0x10006abf  nop
0x10006ac0  mov     edi, [eax]
0x10006ac2  mov     eax, [eax+2Ch]
0x10006ac5  test    eax, eax
0x10006ac7  jz      short loc_10006AEE
0x10006ac9  nop     dword ptr [eax+00000000h]
0x10006ad0  mov     esi, [eax]
0x10006ad2  cmp     [eax+8], ebx
0x10006ad5  jnz     short loc_10006AE8
0x10006ad7  push    0
0x10006ad9  push    dword ptr [eax+0Ch]
0x10006adc  push    ecx
0x10006add  call    _WBDBCloseDatabase@12; WBDBCloseDatabase(x,x,x)
0x10006ae2  mov     ecx, [ebp+arg_0]
0x10006ae5  mov     [ebp+var_8], eax
0x10006ae8  mov     eax, esi
0x10006aea  test    esi, esi
0x10006aec  jnz     short loc_10006AD0
0x10006aee  mov     eax, edi
0x10006af0  test    edi, edi
0x10006af2  jnz     short loc_10006AC0
0x10006af4  mov     eax, [ebx+8]
0x10006af7  test    eax, eax
0x10006af9  jz      loc_10006BB2
0x10006aff  nop
0x10006b00  mov     edx, [eax]
0x10006b02  mov     [ebp+var_C], edx
0x10006b05  mov     edx, [eax+0Ch]
0x10006b08  mov     eax, dword_1003AE68
0x10006b0d  test    eax, eax
0x10006b0f  jz      loc_10006BA2
0x10006b15  mov     esi, [eax+4]
0x10006b18  test    esi, esi
0x10006b1a  jz      short loc_10006B2B
0x10006b1c  nop     dword ptr [eax+00h]
0x10006b20  cmp     [esi+0Ch], ecx
0x10006b23  jz      short loc_10006B33
0x10006b25  mov     esi, [esi]
0x10006b27  test    esi, esi
0x10006b29  jnz     short loc_10006B20
0x10006b2b  mov     eax, [eax]
0x10006b2d  test    eax, eax
0x10006b2f  jnz     short loc_10006B15
0x10006b31  jmp     short loc_10006BA2
0x10006b33  mov     eax, [esi+10h]
0x10006b36  mov     dword_1003AE5C, eax
0x10006b3b  test    esi, esi
0x10006b3d  jz      short loc_10006BA2
0x10006b3f  mov     edi, [esi+8]
0x10006b42  mov     [ebp+var_4], edi
0x10006b45  test    edi, edi
0x10006b47  jz      short loc_10006BA2
0x10006b49  nop     dword ptr [eax+00000000h]
0x10006b50  cmp     [edi+0Ch], edx
0x10006b53  jz      short loc_10006B60
0x10006b55  mov     edi, [edi]
0x10006b57  mov     [ebp+var_4], edi
0x10006b5a  test    edi, edi
0x10006b5c  jnz     short loc_10006B50
0x10006b5e  jmp     short loc_10006BA2
0x10006b60  test    edi, edi
0x10006b62  jz      short loc_10006BA2
0x10006b64  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10006b6a  mov     ecx, eax
0x10006b6c  mov     eax, dword_1003AE68
0x10006b71  test    eax, eax
0x10006b73  jz      short loc_10006B83
0x10006b75  mov     [ebp+var_4], edi
0x10006b78  cmp     [eax+10h], ecx
0x10006b7b  jz      short loc_10006B85
0x10006b7d  mov     eax, [eax]
0x10006b7f  test    eax, eax
0x10006b81  jnz     short loc_10006B78
0x10006b83  xor     eax, eax
0x10006b85  mov     eax, [eax+1Ch]
0x10006b88  push    dword ptr [edi+10h]
0x10006b8b  mov     edi, [eax+44h]
0x10006b8e  mov     ecx, edi
0x10006b90  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10006b96  call    edi
0x10006b98  mov     edx, [ebp+var_4]
0x10006b9b  mov     ecx, esi
0x10006b9d  call    _ISAMDBDeleteVTDef@8; ISAMDBDeleteVTDef(x,x)
0x10006ba2  mov     ecx, [ebp+var_C]
0x10006ba5  mov     eax, ecx
0x10006ba7  test    ecx, ecx
0x10006ba9  mov     ecx, [ebp+arg_0]
0x10006bac  jnz     loc_10006B00
0x10006bb2  mov     ecx, [ebp+var_10]
0x10006bb5  mov     edx, ebx
0x10006bb7  call    _ISAMDBDeleteSession@8; ISAMDBDeleteSession(x,x)
0x10006bbc  mov     eax, [ebp+var_8]
0x10006bbf  pop     edi
0x10006bc0  pop     esi
0x10006bc1  pop     ebx
0x10006bc2  mov     esp, ebp
0x10006bc4  pop     ebp
0x10006bc5  retn    8
```
