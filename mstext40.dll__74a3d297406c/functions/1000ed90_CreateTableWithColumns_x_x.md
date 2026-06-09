# CreateTableWithColumns(x,x)

- ea: `0x1000ed90`
- end: `0x1000f02e`
- name: `_CreateTableWithColumns@8`
- size: `670`
- prototype: ``
- caller_count: `6`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000f530`
- `0x10012e70`
- `0x100130e0`
- `0x10013800`
- `0x100158b0`
- `0x10015960`

## callees

- `0x1000ad60`
- `0x1000b070`
- `0x1000e350`
- `0x1000ed90`
- `0x10013de0`
- `0x100146d0`
- `0x10016910`
- `0x1001ee70`
- `0x1001f060`
- `0x1002b81a`
- `0x1002c490`

## pseudocode

```c
int __stdcall CreateTableWithColumns(const wchar_t *a1, int a2)
{
  const wchar_t *v2; // ebp
  int v3; // ebx
  int *v4; // edi
  int result; // eax
  _DWORD *v6; // esi
  int v7; // eax
  char *v8; // eax
  char *v9; // esi
  int v10; // eax
  unsigned int v11; // eax
  _WORD *v12; // ecx
  int v13; // edx
  __int16 v14; // ax
  int File; // ebx
  wchar_t *v16; // ecx
  int v17; // edx
  wchar_t v18; // ax
  wchar_t *v19; // ecx
  int v20; // edx
  wchar_t v21; // ax
  int v22; // [esp+Ch] [ebp-430h]
  _DWORD *v23; // [esp+14h] [ebp-428h]
  int v24; // [esp+1Ch] [ebp-420h] BYREF
  wchar_t v25[262]; // [esp+20h] [ebp-41Ch] BYREF
  wchar_t pszDest[262]; // [esp+22Ch] [ebp-210h] BYREF

  v2 = a1;
  v3 = 0;
  v4 = (int *)*((_DWORD *)a1 + 229);
  if ( !v4 )
    return -1312;
  v6 = (_DWORD *)*((_DWORD *)a1 + 5);
  v22 = *((_DWORD *)a1 + 1);
  if ( v6 )
  {
    while ( 1 )
    {
      v7 = ISAMDBLocateColumn(a1, v6 + 9);
      if ( !v7 )
        return -5403;
      *(_DWORD *)(v7 + 24) = v3++;
      v6 = (_DWORD *)*v6;
      if ( !v6 )
        goto LABEL_29;
    }
  }
  v23 = 0;
  do
  {
    v8 = (char *)MemAllocate(0xF8u);
    v9 = v8;
    if ( !v8 )
    {
      TextDestroyFileList(*((_DWORD *)v2 + 5));
      return -1011;
    }
    memset(v8, 0, 0xF8u);
    *((_DWORD *)v9 + 2) = v4[4];
    if ( (v4[2] & 0x8000) != 0 )
      *((_DWORD *)v9 + 7) = 1;
    v10 = v4[4];
    if ( v10 == 10 )
    {
      v11 = (unsigned int)v4[5] >> 1;
LABEL_17:
      *((_DWORD *)v9 + 3) = v11;
      goto LABEL_18;
    }
    if ( v10 != 12 )
    {
      v11 = v4[5];
      goto LABEL_17;
    }
    *((_DWORD *)v9 + 3) = 65500;
LABEL_18:
    if ( v4[4] == 16 )
    {
      v9[244] = *((_BYTE *)v4 + 28);
      v9[245] = *((_BYTE *)v4 + 32);
    }
    v12 = v9 + 36;
    v13 = 65;
    while ( v13 != -2147483581 )
    {
      v14 = *(_WORD *)((char *)v12 + (char *)v4 - v9);
      if ( !v14 )
        break;
      *v12++ = v14;
      if ( !--v13 )
      {
        --v12;
        break;
      }
    }
    v2 = a1;
    *v12 = 0;
    *((_DWORD *)v9 + 1) = v3;
    v4[6] = v3++;
    if ( v23 )
      *v23 = v9;
    else
      *((_DWORD *)a1 + 5) = v9;
    v4 = (int *)*v4;
    v23 = v9;
  }
  while ( v4 );
LABEL_29:
  File = TextCreateFile(*(_DWORD *)(v22 + 28), v2 + 460, (int)(v2 + 6), (int)&v24);
  if ( !ReadBufferAllocate(a2) )
  {
    if ( !NetProtocolType(v22 + 578) )
      goto LABEL_42;
    v16 = pszDest;
    v17 = 261;
    while ( v17 != -2147483385 )
    {
      v18 = *(wchar_t *)((char *)v16 + v22 + 578 - (_DWORD)pszDest);
      if ( !v18 )
        break;
      *v16++ = v18;
      if ( !--v17 )
      {
        --v16;
        break;
      }
    }
    *v16 = 0;
    StringCchCatW(pszDest, 0x105u, v2 + 460);
    v19 = v25;
    v20 = 261;
    while ( v20 != -2147483385 )
    {
      v21 = *(wchar_t *)((char *)v19 + v22 - (_DWORD)v25 + 56);
      if ( !v21 )
        break;
      *v19++ = v21;
      if ( !--v20 )
      {
        --v19;
        break;
      }
    }
    *v19 = 0;
    StringCchCatW(v25, 0x105u, v2 + 460);
    if ( ISAMDBAddNetFile(v22, pszDest, v25, 1) )
    {
LABEL_42:
      *((_DWORD *)v2 + 2) = v24;
      result = File;
      *((_DWORD *)v2 + 220) = 0;
      *((_DWORD *)v2 + 222) = 1;
      return result;
    }
  }
  return -1011;
}

```

## disassembly

```asm
0x1000ed90  sub     esp, 430h
0x1000ed96  mov     eax, ___security_cookie
0x1000ed9b  xor     eax, esp
0x1000ed9d  mov     [esp+430h+var_4], eax
0x1000eda4  mov     eax, [esp+430h+arg_4]
0x1000edab  push    ebx
0x1000edac  push    ebp
0x1000edad  mov     ebp, [esp+438h+arg_0]
0x1000edb4  xor     ebx, ebx
0x1000edb6  push    edi
0x1000edb7  mov     [esp+43Ch+var_42C], ebp
0x1000edbb  mov     [esp+43Ch+var_424], eax
0x1000edbf  mov     edi, [ebp+394h]
0x1000edc5  test    edi, edi
0x1000edc7  jnz     short loc_1000EDD3
0x1000edc9  mov     eax, 0FFFFFAE0h
0x1000edce  jmp     loc_1000F014
0x1000edd3  mov     eax, [ebp+4]
0x1000edd6  push    esi
0x1000edd7  mov     esi, [ebp+14h]
0x1000edda  mov     [esp+440h+var_430], eax
0x1000edde  test    esi, esi
0x1000ede0  jz      short loc_1000EE09
0x1000ede2  lea     eax, [esi+24h]
0x1000ede5  push    eax
0x1000ede6  push    ebp
0x1000ede7  call    _ISAMDBLocateColumn@8; ISAMDBLocateColumn(x,x)
0x1000edec  test    eax, eax
0x1000edee  jz      short loc_1000EDFF
0x1000edf0  mov     [eax+18h], ebx
0x1000edf3  inc     ebx
0x1000edf4  mov     esi, [esi]
0x1000edf6  test    esi, esi
0x1000edf8  jnz     short loc_1000EDE2
0x1000edfa  jmp     loc_1000EEE6
0x1000edff  mov     eax, 0FFFFEAE5h
0x1000ee04  jmp     loc_1000F013
0x1000ee09  mov     [esp+440h+var_428], ebx
0x1000ee0d  lea     ecx, [ecx+0]
0x1000ee10  push    0F8h; Size
0x1000ee15  call    _MemAllocate@4; MemAllocate(x)
0x1000ee1a  mov     esi, eax
0x1000ee1c  test    esi, esi
0x1000ee1e  jz      loc_1000F006
0x1000ee24  push    0F8h; Size
0x1000ee29  push    0; Val
0x1000ee2b  push    esi; void *
0x1000ee2c  call    _memset
0x1000ee31  mov     eax, [edi+10h]
0x1000ee34  add     esp, 0Ch
0x1000ee37  mov     [esi+8], eax
0x1000ee3a  test    dword ptr [edi+8], 8000h
0x1000ee41  jz      short loc_1000EE4A
0x1000ee43  mov     dword ptr [esi+1Ch], 1
0x1000ee4a  mov     eax, [edi+10h]
0x1000ee4d  cmp     eax, 0Ah
0x1000ee50  jnz     short loc_1000EE59
0x1000ee52  mov     eax, [edi+14h]
0x1000ee55  shr     eax, 1
0x1000ee57  jmp     short loc_1000EE6A
0x1000ee59  cmp     eax, 0Ch
0x1000ee5c  jnz     short loc_1000EE67
0x1000ee5e  mov     dword ptr [esi+0Ch], 0FFDCh
0x1000ee65  jmp     short loc_1000EE6D
0x1000ee67  mov     eax, [edi+14h]
0x1000ee6a  mov     [esi+0Ch], eax
0x1000ee6d  cmp     dword ptr [edi+10h], 10h
0x1000ee71  jnz     short loc_1000EE87
0x1000ee73  movzx   eax, byte ptr [edi+1Ch]
0x1000ee77  mov     [esi+0F4h], al
0x1000ee7d  movzx   eax, byte ptr [edi+20h]
0x1000ee81  mov     [esi+0F5h], al
0x1000ee87  lea     ecx, [esi+24h]
0x1000ee8a  mov     ebp, edi
0x1000ee8c  mov     edx, 41h ; 'A'
0x1000ee91  sub     ebp, ecx
0x1000ee93  lea     eax, [edx+7FFFFFBDh]
0x1000ee99  test    eax, eax
0x1000ee9b  jz      short loc_1000EEB2
0x1000ee9d  movzx   eax, word ptr [ecx+ebp+24h]
0x1000eea2  test    ax, ax
0x1000eea5  jz      short loc_1000EEB2
0x1000eea7  mov     [ecx], ax
0x1000eeaa  add     ecx, 2
0x1000eead  dec     edx
0x1000eeae  jnz     short loc_1000EE93
0x1000eeb0  jmp     short loc_1000EEB6
0x1000eeb2  test    edx, edx
0x1000eeb4  jnz     short loc_1000EEB9
0x1000eeb6  sub     ecx, 2
0x1000eeb9  mov     ebp, [esp+440h+var_42C]
0x1000eebd  xor     eax, eax
0x1000eebf  mov     [ecx], ax
0x1000eec2  mov     eax, [esp+440h+var_428]
0x1000eec6  mov     [esi+4], ebx
0x1000eec9  mov     [edi+18h], ebx
0x1000eecc  inc     ebx
0x1000eecd  test    eax, eax
0x1000eecf  jnz     short loc_1000EED6
0x1000eed1  mov     [ebp+14h], esi
0x1000eed4  jmp     short loc_1000EED8
0x1000eed6  mov     [eax], esi
0x1000eed8  mov     edi, [edi]
0x1000eeda  mov     [esp+440h+var_428], esi
0x1000eede  test    edi, edi
0x1000eee0  jnz     loc_1000EE10
0x1000eee6  mov     esi, [esp+440h+var_430]
0x1000eeea  lea     eax, [esp+440h+var_420]
0x1000eeee  push    eax; int
0x1000eeef  lea     eax, [ebp+0Ch]
0x1000eef2  push    eax; int
0x1000eef3  lea     edi, [ebp+398h]
0x1000eef9  push    edi; pszSrc
0x1000eefa  push    dword ptr [esi+1Ch]; int
0x1000eefd  call    _TextCreateFile@16; TextCreateFile(x,x,x,x)
0x1000ef02  push    [esp+440h+var_424]
0x1000ef06  mov     ebx, eax
0x1000ef08  call    _ReadBufferAllocate@4; ReadBufferAllocate(x)
0x1000ef0d  test    eax, eax
0x1000ef0f  jnz     loc_1000F00E
0x1000ef15  add     esi, 242h
0x1000ef1b  push    esi
0x1000ef1c  call    _NetProtocolType@4; NetProtocolType(x)
0x1000ef21  test    eax, eax
0x1000ef23  jz      loc_1000EFE7
0x1000ef29  lea     ecx, [esp+440h+pszDest]
0x1000ef30  mov     edx, 105h
0x1000ef35  mov     eax, ecx
0x1000ef37  sub     esi, eax
0x1000ef39  lea     esp, [esp+0]
0x1000ef40  lea     eax, [edx+7FFFFEF9h]
0x1000ef46  test    eax, eax
0x1000ef48  jz      short loc_1000EF5E
0x1000ef4a  movzx   eax, word ptr [esi+ecx]
0x1000ef4e  test    ax, ax
0x1000ef51  jz      short loc_1000EF5E
0x1000ef53  mov     [ecx], ax
0x1000ef56  add     ecx, 2
0x1000ef59  dec     edx
0x1000ef5a  jnz     short loc_1000EF40
0x1000ef5c  jmp     short loc_1000EF62
0x1000ef5e  test    edx, edx
0x1000ef60  jnz     short loc_1000EF65
0x1000ef62  sub     ecx, 2
0x1000ef65  xor     eax, eax
0x1000ef67  push    edi; pszSrc
0x1000ef68  mov     [ecx], ax
0x1000ef6b  lea     eax, [esp+444h+pszDest]
0x1000ef72  push    105h; cchDest
0x1000ef77  push    eax; pszDest
0x1000ef78  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000ef7d  mov     eax, [esp+440h+var_430]
0x1000ef81  lea     ecx, [esp+440h+var_41C]
0x1000ef85  mov     esi, ecx
0x1000ef87  mov     edx, 105h
0x1000ef8c  sub     eax, esi
0x1000ef8e  lea     esi, [eax+38h]
0x1000ef91  lea     eax, [edx+7FFFFEF9h]
0x1000ef97  test    eax, eax
0x1000ef99  jz      short loc_1000EFAF
0x1000ef9b  movzx   eax, word ptr [esi+ecx]
0x1000ef9f  test    ax, ax
0x1000efa2  jz      short loc_1000EFAF
0x1000efa4  mov     [ecx], ax
0x1000efa7  add     ecx, 2
0x1000efaa  dec     edx
0x1000efab  jnz     short loc_1000EF91
0x1000efad  jmp     short loc_1000EFB3
0x1000efaf  test    edx, edx
0x1000efb1  jnz     short loc_1000EFB6
0x1000efb3  sub     ecx, 2
0x1000efb6  xor     eax, eax
0x1000efb8  push    edi; pszSrc
0x1000efb9  mov     [ecx], ax
0x1000efbc  lea     eax, [esp+444h+var_41C]
0x1000efc0  push    105h; cchDest
0x1000efc5  push    eax; pszDest
0x1000efc6  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000efcb  push    1; int
0x1000efcd  lea     eax, [esp+444h+var_41C]
0x1000efd1  push    eax; STRSAFE_LPCWSTR
0x1000efd2  lea     eax, [esp+448h+pszDest]
0x1000efd9  push    eax; pszSrc
0x1000efda  push    [esp+44Ch+var_430]; int
0x1000efde  call    _ISAMDBAddNetFile@16; ISAMDBAddNetFile(x,x,x,x)
0x1000efe3  test    eax, eax
0x1000efe5  jz      short loc_1000F00E
0x1000efe7  mov     eax, [esp+440h+var_420]
0x1000efeb  mov     [ebp+8], eax
0x1000efee  mov     eax, ebx
0x1000eff0  mov     dword ptr [ebp+370h], 0
0x1000effa  mov     dword ptr [ebp+378h], 1
0x1000f004  jmp     short loc_1000F013
0x1000f006  push    dword ptr [ebp+14h]
0x1000f009  call    _TextDestroyFileList@4; TextDestroyFileList(x)
0x1000f00e  mov     eax, 0FFFFFC0Dh
0x1000f013  pop     esi
0x1000f014  mov     ecx, [esp+43Ch+var_4]
0x1000f01b  pop     edi
0x1000f01c  pop     ebp
0x1000f01d  pop     ebx
0x1000f01e  xor     ecx, esp; StackCookie
0x1000f020  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f025  add     esp, 430h
0x1000f02b  retn    8
```
