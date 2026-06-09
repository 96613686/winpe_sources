# ExcelMIUpdateName(x,x,x,x,x,x,x)

- ea: `0x1000bba0`
- end: `0x1000be59`
- name: `_ExcelMIUpdateName@28`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10016240`

## callees

- `0x1000bba0`
- `0x1000e440`
- `0x10035510`
- `0x10035b40`
- `0x10035f40`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1000bcf9`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1000bcf9`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1000bd00`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1000bd00`

## pseudocode

```c
int __fastcall ExcelMIUpdateName(int a1, int a2, int a3, __int16 a4, __int16 a5, int a6, int a7)
{
  int v7; // edi
  int v8; // eax
  int *v9; // esi
  __int16 *v11; // ecx
  __int16 v12; // bx
  _WORD *v13; // ecx
  WCHAR *v14; // eax
  int v15; // edi
  _WORD *v16; // eax
  LCID UserDefaultLCID; // eax
  __int16 v18; // ax
  unsigned int v19; // edx
  int v20; // edi
  int v21; // esi
  char v22; // al
  int v23; // [esp+10h] [ebp-21Ch]
  int v25; // [esp+1Ch] [ebp-210h]
  _BYTE v26[516]; // [esp+20h] [ebp-20Ch] BYREF

  v7 = a1;
  v8 = 1;
  v25 = a1;
  v9 = *(int **)(a1 + 4);
  if ( !v9 )
    return -10;
  while ( *((_WORD *)v9 + 2) != 24 || --v8 )
  {
    v9 = (int *)*v9;
    if ( !v9 )
      return -10;
  }
  while ( 1 )
  {
    v11 = (__int16 *)(v9 + 2);
    if ( *((_WORD *)v9 + 2) != 24 )
      break;
    v12 = *v11;
    v23 = *((__int16 *)v9 + 8);
    ExcelExtractString(
      *(_DWORD *)(v7 + 36),
      *(_DWORD *)(v7 + 44),
      (__m128i *)&ExcelRecordTextBuffer,
      512,
      (LPCCH)v9 + 22,
      *((unsigned __int8 *)v9 + 11));
    if ( (v12 & 0x20) != 0 && NameLocalizer )
    {
      NameLocalizer(NameLocalizer, &ExcelRecordTextBuffer, v26, 256);
    }
    else
    {
      memset(v26, 0, 0x200u);
      v13 = v26;
      v14 = &ExcelRecordTextBuffer;
      v15 = 256;
      do
      {
        if ( !*v14 )
          break;
        *v13++ = *v14++;
        --v15;
      }
      while ( v15 );
      v16 = v13 - 1;
      if ( v15 )
        v16 = v13;
      *v16 = 0;
    }
    UserDefaultLCID = GetUserDefaultLCID();
    if ( DBCompareStringW(UserDefaultLCID, 196609, a3, -1, v26, -1) == 2 && a2 == v23 )
    {
      v11 = (__int16 *)(v9 + 2);
      break;
    }
    v9 = (int *)*v9;
    v7 = v25;
    if ( !v9 )
      return -10;
  }
  v18 = *((_WORD *)v9 + 3);
  if ( v18 < 0 )
    return -10;
  v19 = v18;
  if ( (unsigned int)v18 < 4 )
    return -1;
  v20 = *((unsigned __int8 *)v11 + 3);
  *v11 = a5 | a4 & *v11;
  if ( *(int *)(v25 + 36) < 8 )
  {
    if ( v18 < (unsigned int)(v20 + 35) )
      return -1;
    *(__int16 *)((char *)v11 + v20 + 29) = a6;
    *(__int16 *)((char *)v11 + v20 + 31) = a7;
    *((_BYTE *)v11 + v20 + 33) = BYTE2(a6);
    *((_BYTE *)v11 + v20 + 34) = BYTE2(a7);
    return 0;
  }
  else
  {
    if ( (unsigned int)v18 < 0xF )
      return -1;
    v21 = 2 * v20;
    if ( (v11[7] & 0xF3) != 1 )
      v21 = v20;
    if ( v18 < (unsigned int)(v21 + 16) )
      return -1;
    v22 = *((_BYTE *)v11 + v21 + 15);
    if ( v22 == 59 )
    {
      if ( v19 >= v21 + 26 )
      {
        *(__int16 *)((char *)v11 + v21 + 18) = a6;
        *(__int16 *)((char *)v11 + v21 + 20) = a7;
        *(__int16 *)((char *)v11 + v21 + 22) = HIWORD(a6);
        *(__int16 *)((char *)v11 + v21 + 24) = HIWORD(a7);
        return 0;
      }
      return -1;
    }
    if ( v22 != 58 || v19 < v21 + 22 )
      return -1;
    *(_DWORD *)((char *)v11 + v21 + 18) = a6;
    return 0;
  }
}

```

## disassembly

```asm
0x1000bba0  mov     edi, edi
0x1000bba2  push    ebp
0x1000bba3  mov     ebp, esp
0x1000bba5  sub     esp, 220h
0x1000bbab  mov     eax, ___security_cookie
0x1000bbb0  xor     eax, ebp
0x1000bbb2  mov     [ebp+var_8], eax
0x1000bbb5  mov     eax, [ebp+arg_0]
0x1000bbb8  push    ebx
0x1000bbb9  push    esi
0x1000bbba  push    edi
0x1000bbbb  mov     edi, ecx
0x1000bbbd  mov     [ebp+var_214], eax
0x1000bbc3  mov     [ebp+var_218], edx
0x1000bbc9  mov     eax, 1
0x1000bbce  mov     [ebp+var_210], edi
0x1000bbd4  mov     esi, [edi+4]
0x1000bbd7  test    esi, esi
0x1000bbd9  jz      short loc_1000BBF6
0x1000bbdb  nop     dword ptr [eax+eax+00h]
0x1000bbe0  cmp     word ptr [esi+4], 18h
0x1000bbe5  jnz     short loc_1000BBF0
0x1000bbe7  test    eax, eax
0x1000bbe9  jz      short loc_1000BC0E
0x1000bbeb  sub     eax, 1
0x1000bbee  jz      short loc_1000BC21
0x1000bbf0  mov     esi, [esi]
0x1000bbf2  test    esi, esi
0x1000bbf4  jnz     short loc_1000BBE0
0x1000bbf6  mov     eax, 0FFFFFFF6h
0x1000bbfb  pop     edi
0x1000bbfc  pop     esi
0x1000bbfd  pop     ebx
0x1000bbfe  mov     ecx, [ebp+var_8]
0x1000bc01  xor     ecx, ebp; StackCookie
0x1000bc03  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000bc08  mov     esp, ebp
0x1000bc0a  pop     ebp
0x1000bc0b  retn    14h
0x1000bc0e  mov     eax, esi
0x1000bc10  cmp     word ptr [esi+4], 18h
0x1000bc15  jnz     short loc_1000BC1F
0x1000bc17  mov     eax, esi
0x1000bc19  mov     esi, [esi]
0x1000bc1b  test    esi, esi
0x1000bc1d  jnz     short loc_1000BC10
0x1000bc1f  mov     esi, eax
0x1000bc21  test    esi, esi
0x1000bc23  jz      short loc_1000BBF6
0x1000bc25  nop     word ptr [eax+eax+00000000h]
0x1000bc30  cmp     word ptr [esi+4], 18h
0x1000bc35  lea     ecx, [esi+8]
0x1000bc38  jnz     loc_1000BD31
0x1000bc3e  movsx   eax, word ptr [ecx+8]
0x1000bc42  movzx   ebx, word ptr [ecx]
0x1000bc45  mov     edx, [edi+2Ch]
0x1000bc48  mov     [ebp+var_21C], eax
0x1000bc4e  movzx   eax, byte ptr [ecx+3]
0x1000bc52  push    eax; cbMultiByte
0x1000bc53  lea     eax, [ecx+0Eh]
0x1000bc56  mov     ecx, [edi+24h]
0x1000bc59  push    eax; lpMultiByteStr
0x1000bc5a  push    200h; cchWideChar
0x1000bc5f  push    offset _ExcelRecordTextBuffer; lpWideCharStr
0x1000bc64  call    _ExcelExtractString@24; ExcelExtractString(x,x,x,x,x,x)
0x1000bc69  test    bl, 20h
0x1000bc6c  jz      short loc_1000BC95
0x1000bc6e  mov     edi, _NameLocalizer
0x1000bc74  test    edi, edi
0x1000bc76  jz      short loc_1000BC95
0x1000bc78  push    100h
0x1000bc7d  lea     eax, [ebp+var_20C]
0x1000bc83  mov     ecx, edi
0x1000bc85  push    eax
0x1000bc86  push    offset _ExcelRecordTextBuffer
0x1000bc8b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000bc91  call    edi ; _NameLocalizer
0x1000bc93  jmp     short loc_1000BCE3
0x1000bc95  push    200h; Size
0x1000bc9a  lea     eax, [ebp+var_20C]
0x1000bca0  push    0; Val
0x1000bca2  push    eax; void *
0x1000bca3  call    _memset
0x1000bca8  add     esp, 0Ch
0x1000bcab  lea     ecx, [ebp+var_20C]
0x1000bcb1  mov     eax, offset _ExcelRecordTextBuffer
0x1000bcb6  mov     edi, 100h
0x1000bcbb  nop     dword ptr [eax+eax+00h]
0x1000bcc0  movzx   edx, word ptr [eax]
0x1000bcc3  test    dx, dx
0x1000bcc6  jz      short loc_1000BCD6
0x1000bcc8  mov     [ecx], dx
0x1000bccb  add     eax, 2
0x1000bcce  add     ecx, 2
0x1000bcd1  sub     edi, 1
0x1000bcd4  jnz     short loc_1000BCC0
0x1000bcd6  test    edi, edi
0x1000bcd8  lea     eax, [ecx-2]
0x1000bcdb  cmovnz  eax, ecx
0x1000bcde  xor     ecx, ecx
0x1000bce0  mov     [eax], cx
0x1000bce3  push    0FFFFFFFFh
0x1000bce5  lea     eax, [ebp+var_20C]
0x1000bceb  push    eax
0x1000bcec  push    0FFFFFFFFh
0x1000bcee  push    [ebp+var_214]
0x1000bcf4  push    30001h
0x1000bcf9  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1000bcff  push    eax
0x1000bd00  call    ds:__imp__DBCompareStringW@24; DBCompareStringW(x,x,x,x,x,x)
0x1000bd06  sub     eax, 2
0x1000bd09  jnz     short loc_1000BD19
0x1000bd0b  mov     eax, [ebp+var_218]
0x1000bd11  cmp     eax, [ebp+var_21C]
0x1000bd17  jz      short loc_1000BD2E
0x1000bd19  mov     esi, [esi]
0x1000bd1b  mov     edi, [ebp+var_210]
0x1000bd21  test    esi, esi
0x1000bd23  jnz     loc_1000BC30
0x1000bd29  jmp     loc_1000BBF6
0x1000bd2e  lea     ecx, [esi+8]
0x1000bd31  movzx   eax, word ptr [esi+6]
0x1000bd35  test    ax, ax
0x1000bd38  js      loc_1000BBF6
0x1000bd3e  movsx   edx, ax
0x1000bd41  cmp     edx, 4
0x1000bd44  jnb     short loc_1000BD5C
0x1000bd46  or      eax, 0FFFFFFFFh
0x1000bd49  pop     edi
0x1000bd4a  pop     esi
0x1000bd4b  pop     ebx
0x1000bd4c  mov     ecx, [ebp+var_8]
0x1000bd4f  xor     ecx, ebp; StackCookie
0x1000bd51  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000bd56  mov     esp, ebp
0x1000bd58  pop     ebp
0x1000bd59  retn    14h
0x1000bd5c  mov     ax, [ecx]
0x1000bd5f  and     ax, [ebp+arg_4]
0x1000bd63  or      ax, [ebp+arg_8]
0x1000bd67  movzx   edi, byte ptr [ecx+3]
0x1000bd6b  mov     [ecx], ax
0x1000bd6e  mov     eax, [ebp+var_210]
0x1000bd74  cmp     dword ptr [eax+24h], 8
0x1000bd78  jl      loc_1000BE19
0x1000bd7e  cmp     edx, 0Fh
0x1000bd81  jb      short loc_1000BD46
0x1000bd83  mov     al, [ecx+0Eh]
0x1000bd86  lea     esi, [edi+edi]
0x1000bd89  and     al, 0F3h
0x1000bd8b  cmp     al, 1
0x1000bd8d  cmovnz  esi, edi
0x1000bd90  lea     eax, [esi+10h]
0x1000bd93  cmp     edx, eax
0x1000bd95  jb      short loc_1000BD46
0x1000bd97  mov     al, [esi+ecx+0Fh]
0x1000bd9b  cmp     al, 3Bh ; ';'
0x1000bd9d  jnz     short loc_1000BDDF
0x1000bd9f  lea     eax, [esi+1Ah]
0x1000bda2  cmp     edx, eax
0x1000bda4  jb      short loc_1000BD46
0x1000bda6  mov     ax, word ptr [ebp+arg_C]
0x1000bdaa  mov     [esi+ecx+12h], ax
0x1000bdaf  mov     ax, [ebp+arg_10]
0x1000bdb3  mov     [esi+ecx+14h], ax
0x1000bdb8  mov     ax, word ptr [ebp+arg_C+2]
0x1000bdbc  mov     [esi+ecx+16h], ax
0x1000bdc1  mov     ax, [ebp+arg_12]
0x1000bdc5  mov     [esi+ecx+18h], ax
0x1000bdca  xor     eax, eax
0x1000bdcc  pop     edi
0x1000bdcd  pop     esi
0x1000bdce  pop     ebx
0x1000bdcf  mov     ecx, [ebp+var_8]
0x1000bdd2  xor     ecx, ebp; StackCookie
0x1000bdd4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000bdd9  mov     esp, ebp
0x1000bddb  pop     ebp
0x1000bddc  retn    14h
0x1000bddf  cmp     al, 3Ah ; ':'
0x1000bde1  jnz     loc_1000BD46
0x1000bde7  lea     eax, [esi+16h]
0x1000bdea  cmp     edx, eax
0x1000bdec  jb      loc_1000BD46
0x1000bdf2  mov     ax, word ptr [ebp+arg_C]
0x1000bdf6  mov     [esi+ecx+12h], ax
0x1000bdfb  mov     ax, word ptr [ebp+arg_C+2]
0x1000bdff  mov     [esi+ecx+14h], ax
0x1000be04  xor     eax, eax
0x1000be06  pop     edi
0x1000be07  pop     esi
0x1000be08  pop     ebx
0x1000be09  mov     ecx, [ebp+var_8]
0x1000be0c  xor     ecx, ebp; StackCookie
0x1000be0e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000be13  mov     esp, ebp
0x1000be15  pop     ebp
0x1000be16  retn    14h
0x1000be19  lea     eax, [edi+23h]
0x1000be1c  cmp     edx, eax
0x1000be1e  jb      loc_1000BD46
0x1000be24  mov     ax, word ptr [ebp+arg_C]
0x1000be28  mov     [edi+ecx+1Dh], ax
0x1000be2d  mov     ax, [ebp+arg_10]
0x1000be31  mov     [edi+ecx+1Fh], ax
0x1000be36  mov     al, byte ptr [ebp+arg_C+2]
0x1000be39  mov     [edi+ecx+21h], al
0x1000be3d  mov     al, byte ptr [ebp+arg_12]
0x1000be40  mov     [edi+ecx+22h], al
0x1000be44  xor     eax, eax
0x1000be46  mov     ecx, [ebp+var_8]
0x1000be49  pop     edi
0x1000be4a  pop     esi
0x1000be4b  xor     ecx, ebp; StackCookie
0x1000be4d  pop     ebx
0x1000be4e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000be53  mov     esp, ebp
0x1000be55  pop     ebp
0x1000be56  retn    14h
```
