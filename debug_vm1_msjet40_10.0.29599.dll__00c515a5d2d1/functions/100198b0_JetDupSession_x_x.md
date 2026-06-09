# JetDupSession(x,x)

- ea: `0x100198b0`
- end: `0x10019b89`
- name: `_JetDupSession@8`
- size: `729`
- prototype: `JET_ERR __stdcall(JET_SESID sesid, JET_SESID *psesid)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation`

## callees

- `0x100198b0`
- `0x100292b0`
- `0x10029310`
- `0x10029360`
- `0x1002c7b0`
- `0x1003e500`
- `0x1003e5b0`
- `0x1003e6c0`
- `0x1003e860`
- `0x1003f080`
- `0x10042b60`
- `0x10048f4c`
- `0x10048fef`
- `0x10123110`
- `0x10124078`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10019a9f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10019a9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001999a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019900`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001999a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019b39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10019b6e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100198d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x100198d0`

## pseudocode

```c
JET_ERR __stdcall JetDupSession(JET_SESID sesid, JET_SESID *psesid)
{
  int v2; // esi
  int v4; // edi
  int IsibOfSesidIscb; // eax
  int v6; // edx
  unsigned __int16 *v7; // eax
  unsigned __int16 *v8; // ecx
  unsigned __int16 *v9; // eax
  int v10; // edi
  int v11; // ebx
  JET_ERR inited; // edi
  int v13; // eax
  void *v14; // ebx
  void *v15; // ecx
  int v16; // edx
  int v17; // eax
  void *v18; // ecx
  size_t *v19; // edi
  void *v20; // edx
  void *v21; // eax
  int v22; // edi
  int v23; // [esp-14h] [ebp-6Ch]
  int v24; // [esp-10h] [ebp-68h]
  int v25; // [esp+Ch] [ebp-4Ch]
  int v26; // [esp+10h] [ebp-48h]
  int v27; // [esp+14h] [ebp-44h]
  void *v28; // [esp+14h] [ebp-44h]
  int v29; // [esp+18h] [ebp-40h]
  void *Block; // [esp+1Ch] [ebp-3Ch] BYREF
  int ItibOfSesid; // [esp+20h] [ebp-38h]
  void *v32; // [esp+24h] [ebp-34h] BYREF
  unsigned __int16 v33[22]; // [esp+28h] [ebp-30h] BYREF

  EnterCriticalSection(critJet);
  v2 = isibHead;
  if ( isibHead == -1 )
  {
LABEL_4:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  while ( rgsib[26 * v2] != sesid )
  {
    v2 = dword_1016EB88[26 * v2];
    if ( v2 == -1 )
      goto LABEL_4;
  }
  ItibOfSesid = UtilGetItibOfSesid(sesid);
  v4 = 2147483646;
  IsibOfSesidIscb = UtilGetIsibOfSesidIscb((void *)sesid);
  v6 = 21;
  v7 = (unsigned __int16 *)dword_1016EB74[26 * IsibOfSesidIscb];
  v8 = v33;
  do
  {
    if ( !v4 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v4;
    --v6;
  }
  while ( v6 );
  v9 = v8 - 1;
  if ( v6 )
    v9 = v8;
  *v9 = 0;
  v10 = IsibAllocate(ItibOfSesid);
  v26 = v10;
  if ( v10 == -1 )
    goto LABEL_14;
  v11 = IiscbAllocate();
  v29 = v11;
  if ( v11 == -1 )
  {
    ReleaseIsib(v10);
LABEL_14:
    LeaveCriticalSection(critJet);
    return -1101;
  }
  Block = (void *)-1;
  v27 = 2316 * ItibOfSesid;
  inited = ErrIsamBeginSession3(*((struct Connection **)rgtib + 579 * ItibOfSesid + 570), v33, (int)&Block);
  if ( inited < 0 )
    goto LABEL_32;
  v13 = 5 * v11;
  v14 = Block;
  v25 = 4 * v13;
  *(&rgiscb + v13) = Block;
  Block = (void *)(104 * v2);
  inited = ErrInitSib(
             *(void **)((char *)dword_1016EB74 + (_DWORD)Block),
             *(void **)((char *)&dword_1016EB78 + (_DWORD)Block));
  if ( inited < 0 )
  {
    v11 = v29;
    goto LABEL_32;
  }
  v15 = Block;
  v16 = 26 * v26;
  v17 = *(int *)((char *)dword_1016EB70 + (_DWORD)Block);
  ItibOfSesid = v16 * 4;
  dword_1016EB70[v16] = v17;
  dword_1016EB98[v16] = v29;
  v18 = *(&rgiscb + 5 * *(int *)((char *)dword_1016EB70 + (_DWORD)v15) + 3);
  v32 = v18;
  if ( v18 != (void *)-1 )
  {
    inited = ErrTryOpenDatabase((int)v14, (wchar_t *)((char *)rgtib + v27), 0, (int)&v32, 0, 0);
    if ( inited < 0 )
    {
LABEL_26:
      ErrIsamEndSession(v14);
      v11 = v29;
LABEL_32:
      ReleaseIsib(v26);
      ReleaseIscb(v11, v11);
      LeaveCriticalSection(critJet);
      return inited;
    }
    v18 = v32;
  }
  v19 = (size_t *)*(&Src + 5 * *(int *)((char *)dword_1016EB70 + (_DWORD)Block));
  if ( v19 )
  {
    v21 = _malloc(v19[1]);
    v28 = v21;
    if ( v21 )
    {
      memcpy(v21, v19, v19[1]);
      v18 = v32;
      v20 = v28;
      goto LABEL_28;
    }
    inited = -1011;
    if ( v32 != (void *)-1 && (int)ErrDispCloseDatabase(v14, v32, 0) < 0 )
      ErrDispCloseDatabase(v14, v32, 1);
    goto LABEL_26;
  }
  v20 = 0;
LABEL_28:
  v22 = ItibOfSesid;
  if ( v18 != (void *)-1 )
    *(int *)((char *)dword_1016EB70 + ItibOfSesid) = mpdbidiiscb[(_DWORD)v18];
  *(void **)((char *)&rgiscb + v25 + 12) = v18;
  *(&rgiscb + 5 * *(int *)((char *)dword_1016EB70 + v22) + 3) = v18;
  InitIscb(v23, v24, v18, v20);
  *psesid = (JET_SESID)v14;
  LeaveCriticalSection(critJet);
  return 0;
}

```

## disassembly

```asm
0x100198b0  mov     edi, edi
0x100198b2  push    ebp
0x100198b3  mov     ebp, esp
0x100198b5  sub     esp, 50h
0x100198b8  mov     eax, ___security_cookie
0x100198bd  xor     eax, ebp
0x100198bf  mov     [ebp+var_4], eax
0x100198c2  mov     eax, [ebp+psesid]
0x100198c5  push    ebx
0x100198c6  push    esi
0x100198c7  push    _critJet; lpCriticalSection
0x100198cd  mov     [ebp+var_50], eax
0x100198d0  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100198d6  mov     esi, _isibHead
0x100198dc  cmp     esi, 0FFFFFFFFh
0x100198df  jz      short loc_100198FA
0x100198e1  mov     ebx, [ebp+sesid]
0x100198e4  imul    eax, esi, 68h ; 'h'
0x100198e7  cmp     _rgsib[eax], ebx
0x100198ed  jz      short loc_1001991D
0x100198ef  mov     esi, dword_1016EB88[eax]
0x100198f5  cmp     esi, 0FFFFFFFFh
0x100198f8  jnz     short loc_100198E4
0x100198fa  push    _critJet; lpCriticalSection
0x10019900  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019906  pop     esi
0x10019907  mov     eax, 0FFFFFBB0h
0x1001990c  pop     ebx
0x1001990d  mov     ecx, [ebp+var_4]
0x10019910  xor     ecx, ebp; StackCookie
0x10019912  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019917  mov     esp, ebp
0x10019919  pop     ebp
0x1001991a  retn    8
0x1001991d  push    edi
0x1001991e  push    ebx
0x1001991f  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x10019924  mov     ecx, ebx
0x10019926  mov     [ebp+var_38], eax
0x10019929  mov     edi, 7FFFFFFEh
0x1001992e  call    _UtilGetIsibOfSesidIscb@4; UtilGetIsibOfSesidIscb(x)
0x10019933  imul    ecx, eax, 68h ; 'h'
0x10019936  mov     edx, 15h
0x1001993b  mov     eax, dword_1016EB74[ecx]
0x10019941  lea     ecx, [ebp+var_30]
0x10019944  test    edi, edi
0x10019946  jz      short loc_1001995F
0x10019948  movzx   ebx, word ptr [eax]
0x1001994b  test    bx, bx
0x1001994e  jz      short loc_1001995F
0x10019950  mov     [ecx], bx
0x10019953  add     eax, 2
0x10019956  add     ecx, 2
0x10019959  dec     edi
0x1001995a  sub     edx, 1
0x1001995d  jnz     short loc_10019944
0x1001995f  lea     eax, [ecx-2]
0x10019962  test    edx, edx
0x10019964  cmovnz  eax, ecx
0x10019967  xor     ecx, ecx
0x10019969  mov     [eax], cx
0x1001996c  mov     ecx, [ebp+var_38]
0x1001996f  call    _IsibAllocate@4; IsibAllocate(x)
0x10019974  mov     edi, eax
0x10019976  mov     [ebp+var_48], edi
0x10019979  cmp     edi, 0FFFFFFFFh
0x1001997c  jz      short loc_10019994
0x1001997e  call    _IiscbAllocate@0; IiscbAllocate()
0x10019983  mov     ebx, eax
0x10019985  mov     [ebp+var_40], ebx
0x10019988  cmp     ebx, 0FFFFFFFFh
0x1001998b  jnz     short loc_100199B8
0x1001998d  mov     ecx, edi
0x1001998f  call    _ReleaseIsib@4; ReleaseIsib(x)
0x10019994  push    _critJet; lpCriticalSection
0x1001999a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100199a0  pop     edi
0x100199a1  pop     esi
0x100199a2  mov     eax, 0FFFFFBB3h
0x100199a7  pop     ebx
0x100199a8  mov     ecx, [ebp+var_4]
0x100199ab  xor     ecx, ebp; StackCookie
0x100199ad  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100199b2  mov     esp, ebp
0x100199b4  pop     ebp
0x100199b5  retn    8
0x100199b8  imul    eax, [ebp+var_38], 90Ch
0x100199bf  lea     ecx, [ebp+Block]
0x100199c2  push    ecx; int
0x100199c3  mov     ecx, _rgtib
0x100199c9  lea     edx, [ebp+var_30]; unsigned __int16 *
0x100199cc  mov     [ebp+Block], 0FFFFFFFFh
0x100199d3  mov     [ebp+var_44], eax
0x100199d6  mov     ecx, [eax+ecx+8E8h]; struct Connection *
0x100199dd  call    _ErrIsamBeginSession3@12; ErrIsamBeginSession3(x,x,x)
0x100199e2  mov     edi, eax
0x100199e4  test    edi, edi
0x100199e6  js      loc_10019B57
0x100199ec  lea     eax, [ebx+ebx*4]
0x100199ef  mov     ebx, [ebp+Block]
0x100199f2  shl     eax, 2
0x100199f5  mov     ecx, ebx
0x100199f7  mov     [ebp+var_4C], eax
0x100199fa  mov     dword ptr _rgiscb[eax], ebx
0x10019a00  imul    eax, esi, 68h ; 'h'
0x10019a03  mov     esi, [ebp+var_48]
0x10019a06  mov     edx, esi
0x10019a08  mov     [ebp+Block], eax
0x10019a0b  push    dword_1016EB78[eax]; void *
0x10019a11  push    dword_1016EB74[eax]; Src
0x10019a17  call    _ErrInitSib@16; ErrInitSib(x,x,x,x)
0x10019a1c  mov     edi, eax
0x10019a1e  test    edi, edi
0x10019a20  js      loc_10019B54
0x10019a26  mov     ecx, [ebp+Block]
0x10019a29  imul    edx, esi, 68h ; 'h'
0x10019a2c  mov     esi, [ebp+var_40]
0x10019a2f  mov     eax, dword_1016EB70[ecx]
0x10019a35  mov     [ebp+var_38], edx
0x10019a38  mov     dword_1016EB70[edx], eax
0x10019a3e  mov     dword_1016EB98[edx], esi
0x10019a44  mov     eax, dword_1016EB70[ecx]
0x10019a4a  lea     eax, [eax+eax*4]
0x10019a4d  mov     ecx, dword ptr (_rgiscb+0Ch)[eax*4]
0x10019a54  mov     [ebp+var_34], ecx
0x10019a57  cmp     ecx, 0FFFFFFFFh
0x10019a5a  jz      short loc_10019A81
0x10019a5c  mov     edx, [ebp+var_44]
0x10019a5f  lea     eax, [ebp+var_34]
0x10019a62  push    0
0x10019a64  push    0
0x10019a66  push    eax
0x10019a67  mov     eax, _rgtib
0x10019a6c  mov     ecx, ebx
0x10019a6e  push    0
0x10019a70  lea     edx, [edx+eax]
0x10019a73  call    _ErrTryOpenDatabase@24; ErrTryOpenDatabase(x,x,x,x,x,x)
0x10019a78  mov     edi, eax
0x10019a7a  test    edi, edi
0x10019a7c  js      short loc_10019AD4
0x10019a7e  mov     ecx, [ebp+var_34]
0x10019a81  mov     eax, [ebp+Block]
0x10019a84  mov     eax, dword_1016EB70[eax]
0x10019a8a  lea     eax, [eax+eax*4]
0x10019a8d  mov     edi, Src[eax*4]
0x10019a94  test    edi, edi
0x10019a96  jnz     short loc_10019A9C
0x10019a98  xor     edx, edx
0x10019a9a  jmp     short loc_10019AF2
0x10019a9c  push    dword ptr [edi+4]; Size
0x10019a9f  call    ds:__imp__malloc
0x10019aa5  add     esp, 4
0x10019aa8  mov     [ebp+var_44], eax
0x10019aab  test    eax, eax
0x10019aad  jnz     short loc_10019ADF
0x10019aaf  mov     eax, [ebp+var_34]
0x10019ab2  mov     edi, 0FFFFFC0Dh
0x10019ab7  cmp     eax, 0FFFFFFFFh
0x10019aba  jz      short loc_10019AD4
0x10019abc  push    0
0x10019abe  push    eax
0x10019abf  push    ebx
0x10019ac0  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019ac5  test    eax, eax
0x10019ac7  jns     short loc_10019AD4
0x10019ac9  push    1
0x10019acb  push    [ebp+var_34]
0x10019ace  push    ebx
0x10019acf  call    _ErrDispCloseDatabase@12; ErrDispCloseDatabase(x,x,x)
0x10019ad4  mov     ecx, ebx; Block
0x10019ad6  call    _ErrIsamEndSession@8; ErrIsamEndSession(x,x)
0x10019adb  mov     ebx, esi
0x10019add  jmp     short loc_10019B57
0x10019adf  push    dword ptr [edi+4]; Size
0x10019ae2  push    edi; Src
0x10019ae3  push    eax; void *
0x10019ae4  call    _memcpy
0x10019ae9  mov     ecx, [ebp+var_34]
0x10019aec  add     esp, 0Ch
0x10019aef  mov     edx, [ebp+var_44]
0x10019af2  mov     edi, [ebp+var_38]
0x10019af5  cmp     ecx, 0FFFFFFFFh
0x10019af8  jz      short loc_10019B07
0x10019afa  mov     eax, _mpdbidiiscb[ecx*4]
0x10019b01  mov     dword_1016EB70[edi], eax
0x10019b07  mov     eax, [ebp+var_4C]
0x10019b0a  push    edx
0x10019b0b  push    ecx
0x10019b0c  sub     esp, 8
0x10019b0f  mov     edx, ebx
0x10019b11  mov     dword ptr (_rgiscb+0Ch)[eax], ecx
0x10019b17  mov     eax, dword_1016EB70[edi]
0x10019b1d  lea     eax, [eax+eax*4]
0x10019b20  mov     dword ptr (_rgiscb+0Ch)[eax*4], ecx
0x10019b27  mov     ecx, esi
0x10019b29  call    _InitIscb@24; InitIscb(x,x,x,x,x,x)
0x10019b2e  mov     eax, [ebp+var_50]
0x10019b31  mov     [eax], ebx
0x10019b33  push    _critJet; lpCriticalSection
0x10019b39  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019b3f  pop     edi
0x10019b40  pop     esi
0x10019b41  xor     eax, eax
0x10019b43  pop     ebx
0x10019b44  mov     ecx, [ebp+var_4]
0x10019b47  xor     ecx, ebp; StackCookie
0x10019b49  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019b4e  mov     esp, ebp
0x10019b50  pop     ebp
0x10019b51  retn    8
0x10019b54  mov     ebx, [ebp+var_40]
0x10019b57  mov     ecx, [ebp+var_48]
0x10019b5a  call    _ReleaseIsib@4; ReleaseIsib(x)
0x10019b5f  mov     edx, ebx
0x10019b61  mov     ecx, ebx
0x10019b63  call    _ReleaseIscb@8; ReleaseIscb(x,x)
0x10019b68  push    _critJet; lpCriticalSection
0x10019b6e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10019b74  mov     ecx, [ebp+var_4]
0x10019b77  mov     eax, edi
0x10019b79  pop     edi
0x10019b7a  pop     esi
0x10019b7b  xor     ecx, ebp; StackCookie
0x10019b7d  pop     ebx
0x10019b7e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10019b83  mov     esp, ebp
0x10019b85  pop     ebp
0x10019b86  retn    8
```
