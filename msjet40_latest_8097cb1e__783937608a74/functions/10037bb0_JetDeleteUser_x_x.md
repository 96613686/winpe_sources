# JetDeleteUser(x,x)

- ea: `0x10037bb0`
- end: `0x10037f4d`
- name: `_JetDeleteUser@8`
- size: `925`
- prototype: `int __stdcall(int, void *Src)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100cfb84`

## callees

- `0x10037bb0`
- `0x10039d80`
- `0x1003cc90`
- `0x1003d230`
- `0x1003d260`
- `0x1003d550`
- `0x1003da50`
- `0x1003db70`
- `0x1003e9b0`
- `0x1003ea00`
- `0x100433f0`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037ec5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037f1f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037ec5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037f1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037cd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037d40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037dbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037df3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037ef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c0c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037cd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037d40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037dbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037df3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037ef2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037f2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10037bd8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10037bd8`

## pseudocode

```c
int __stdcall JetDeleteUser(int a1, unsigned __int16 *Src)
{
  int v2; // esi
  int v4; // esi
  _DWORD *v5; // eax
  int SidFromName; // esi
  size_t v7; // esi
  int NumMembers; // ebx
  _BYTE *v9; // edx
  char *v10; // esi
  int v11; // ecx
  int ObjidFromName; // [esp+Ch] [ebp-124h] BYREF
  void *Block; // [esp+10h] [ebp-120h] BYREF
  size_t Size; // [esp+14h] [ebp-11Ch] BYREF
  int v15; // [esp+18h] [ebp-118h] BYREF
  int v16; // [esp+1Ch] [ebp-114h] BYREF
  char *v17; // [esp+20h] [ebp-110h]
  size_t v18; // [esp+24h] [ebp-10Ch]
  int v19[32]; // [esp+28h] [ebp-108h] BYREF
  int v20[33]; // [esp+A8h] [ebp-88h] BYREF

  EnterCriticalSection(critJet);
  v2 = isibHead;
  if ( isibHead == -1 )
  {
LABEL_4:
    LeaveCriticalSection(critJet);
    return -1104;
  }
  while ( rgsib[26 * v2] != a1 )
  {
    v2 = dword_1016EB88[26 * v2];
    if ( v2 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  v4 = (int)*(&rgiscb + 5 * dword_1016EB70[26 * v2] + 3);
  if ( v4 == -1 )
  {
    LeaveCriticalSection(critJet);
    return -1802;
  }
  ObjidFromName = ErrDispGetObjidFromName(a1, v4, L"Tables", L"MSysAccounts", &v15);
  if ( ObjidFromName < 0 )
  {
    LeaveCriticalSection(critJet);
    return ObjidFromName;
  }
  v5 = *(&::Src + 5 * mpdbidiiscb[v4]);
  if ( !v5 )
  {
    LeaveCriticalSection(critJet);
    return -1001;
  }
  SidFromName = ErrSecCollectAccess(a1, v4, v15, v5, 0, &ObjidFromName, 0);
  if ( SidFromName < 0 )
    goto LABEL_32;
  if ( (ObjidFromName & 0x80u) == 0 )
  {
    UtilSetErrorInfoReal(a1, L"MSysAccounts", 0, 0, -8170, 0, 0, 0);
    LeaveCriticalSection(critJet);
    return -1907;
  }
  SidFromName = ErrSecGetSidFromName(a1, 0xFFFFFFFF, Src, v19, 0x80u, &Size, &ObjidFromName);
  if ( SidFromName < 0 )
  {
LABEL_32:
    LeaveCriticalSection(critJet);
    return SidFromName;
  }
  v7 = Size;
  v18 = Size;
  if ( ObjidFromName )
  {
    if ( Src )
    {
      if ( *Src )
        UtilSetErrorInfoReal(a1, Src, 0, 0, -8275, 0, 0, 0);
    }
    LeaveCriticalSection(critJet);
    return -1903;
  }
  if ( SecFSystemSid(v19) || (ErrSecGetSidFromName(a1, 0xFFFFFFFF, 0, v20, 0x80u, &Size, 0), SecFSameSid(v19, v7)) )
  {
LABEL_21:
    LeaveCriticalSection(critJet);
    return -1906;
  }
  ObjidFromName = 0;
  NumMembers = ErrSecBuildUserToken(a1, -1, (int)v19, v7, &Block);
  if ( NumMembers < 0 )
    goto LABEL_35;
  v9 = Block;
  v10 = (char *)Block + 16;
  v17 = (char *)Block + 4 * *((_DWORD *)Block + 2) + 12;
  if ( (char *)Block + 16 >= v17 )
  {
LABEL_30:
    _free(Block);
    if ( !ObjidFromName )
    {
      SidFromName = ErrSecDeleteAccount(a1, (int)v19, v18, 0);
      goto LABEL_32;
    }
    goto LABEL_21;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v10;
    v10 += 4;
    if ( v9[v11] != 1 )
      goto LABEL_29;
    NumMembers = ErrSecGetNumMembers(a1, (int)&v9[v11], *(_DWORD *)v10 - v11, &v16);
    if ( NumMembers < 0 )
      break;
    if ( v16 == 1 )
    {
      ObjidFromName = 1;
      goto LABEL_30;
    }
    v9 = Block;
LABEL_29:
    if ( v10 >= v17 )
      goto LABEL_30;
  }
  _free(Block);
LABEL_35:
  LeaveCriticalSection(critJet);
  return NumMembers;
}

```

## disassembly

```asm
0x10037bb0  mov     edi, edi
0x10037bb2  push    ebp
0x10037bb3  mov     ebp, esp
0x10037bb5  and     esp, 0FFFFFFF8h
0x10037bb8  sub     esp, 124h
0x10037bbe  mov     eax, ___security_cookie
0x10037bc3  xor     eax, esp
0x10037bc5  mov     [esp+124h+var_4], eax
0x10037bcc  push    ebx
0x10037bcd  mov     ebx, [ebp+Src]
0x10037bd0  push    esi
0x10037bd1  push    edi
0x10037bd2  push    _critJet; lpCriticalSection
0x10037bd8  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10037bde  mov     esi, _isibHead
0x10037be4  cmp     esi, 0FFFFFFFFh
0x10037be7  jz      short loc_10037C06
0x10037be9  mov     edi, [ebp+arg_0]
0x10037bec  nop     dword ptr [eax+00h]
0x10037bf0  imul    eax, esi, 68h ; 'h'
0x10037bf3  cmp     _rgsib[eax], edi
0x10037bf9  jz      short loc_10037C2E
0x10037bfb  mov     esi, dword_1016EB88[eax]
0x10037c01  cmp     esi, 0FFFFFFFFh
0x10037c04  jnz     short loc_10037BF0
0x10037c06  push    _critJet; lpCriticalSection
0x10037c0c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037c12  mov     eax, 0FFFFFBB0h
0x10037c17  pop     edi
0x10037c18  pop     esi
0x10037c19  pop     ebx
0x10037c1a  mov     ecx, [esp+124h+var_4]
0x10037c21  xor     ecx, esp; StackCookie
0x10037c23  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037c28  mov     esp, ebp
0x10037c2a  pop     ebp
0x10037c2b  retn    8
0x10037c2e  push    edi
0x10037c2f  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10037c34  imul    eax, esi, 68h ; 'h'
0x10037c37  mov     eax, dword_1016EB70[eax]
0x10037c3d  lea     eax, [eax+eax*4]
0x10037c40  mov     esi, dword ptr (_rgiscb+0Ch)[eax*4]
0x10037c47  cmp     esi, 0FFFFFFFFh
0x10037c4a  jnz     short loc_10037C74
0x10037c4c  push    _critJet; lpCriticalSection
0x10037c52  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037c58  mov     eax, 0FFFFF8F6h
0x10037c5d  pop     edi
0x10037c5e  pop     esi
0x10037c5f  pop     ebx
0x10037c60  mov     ecx, [esp+124h+var_4]
0x10037c67  xor     ecx, esp; StackCookie
0x10037c69  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037c6e  mov     esp, ebp
0x10037c70  pop     ebp
0x10037c71  retn    8
0x10037c74  lea     eax, [esp+130h+var_118]
0x10037c78  push    eax
0x10037c79  push    offset _wszSaTable; "MSysAccounts"
0x10037c7e  push    offset _wszTcObject; "Tables"
0x10037c83  push    esi
0x10037c84  push    edi
0x10037c85  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10037c8a  mov     [esp+130h+var_124], eax
0x10037c8e  test    eax, eax
0x10037c90  jns     short loc_10037CB9
0x10037c92  push    _critJet; lpCriticalSection
0x10037c98  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037c9e  mov     eax, [esp+130h+var_124]
0x10037ca2  pop     edi
0x10037ca3  pop     esi
0x10037ca4  pop     ebx
0x10037ca5  mov     ecx, [esp+124h+var_4]
0x10037cac  xor     ecx, esp; StackCookie
0x10037cae  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037cb3  mov     esp, ebp
0x10037cb5  pop     ebp
0x10037cb6  retn    8
0x10037cb9  mov     eax, _mpdbidiiscb[esi*4]
0x10037cc0  lea     eax, [eax+eax*4]
0x10037cc3  mov     eax, Src[eax*4]
0x10037cca  test    eax, eax
0x10037ccc  jnz     short loc_10037CF8
0x10037cce  push    _critJet; lpCriticalSection
0x10037cd4  mov     esi, 0FFFFFC17h
0x10037cd9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037cdf  mov     eax, esi
0x10037ce1  pop     edi
0x10037ce2  pop     esi
0x10037ce3  pop     ebx
0x10037ce4  mov     ecx, [esp+124h+var_4]
0x10037ceb  xor     ecx, esp; StackCookie
0x10037ced  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037cf2  mov     esp, ebp
0x10037cf4  pop     ebp
0x10037cf5  retn    8
0x10037cf8  push    0
0x10037cfa  lea     ecx, [esp+134h+var_124]
0x10037cfe  mov     edx, esi
0x10037d00  push    ecx
0x10037d01  push    0
0x10037d03  push    eax
0x10037d04  push    [esp+140h+var_118]
0x10037d08  mov     ecx, edi
0x10037d0a  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x10037d0f  mov     esi, eax
0x10037d11  test    esi, esi
0x10037d13  js      loc_10037EEC
0x10037d19  test    byte ptr [esp+130h+var_124], 80h
0x10037d1e  jnz     short loc_10037D62
0x10037d20  push    0; int
0x10037d22  push    0; int
0x10037d24  push    0; int
0x10037d26  push    0FFFFE016h; int
0x10037d2b  push    0; void *
0x10037d2d  push    0; void *
0x10037d2f  push    offset _wszSaTable; "MSysAccounts"
0x10037d34  push    edi; int
0x10037d35  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10037d3a  push    _critJet; lpCriticalSection
0x10037d40  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037d46  mov     eax, 0FFFFF88Dh
0x10037d4b  pop     edi
0x10037d4c  pop     esi
0x10037d4d  pop     ebx
0x10037d4e  mov     ecx, [esp+124h+var_4]
0x10037d55  xor     ecx, esp; StackCookie
0x10037d57  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037d5c  mov     esp, ebp
0x10037d5e  pop     ebp
0x10037d5f  retn    8
0x10037d62  lea     eax, [esp+130h+var_124]
0x10037d66  push    eax; int
0x10037d67  lea     eax, [esp+134h+Size]
0x10037d6b  push    eax; int
0x10037d6c  push    80h; Size
0x10037d71  lea     eax, [esp+13Ch+var_108]
0x10037d75  push    eax; int
0x10037d76  push    ebx; Src
0x10037d77  push    0FFFFFFFFh; int
0x10037d79  push    edi; int
0x10037d7a  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10037d7f  mov     esi, eax
0x10037d81  test    esi, esi
0x10037d83  js      loc_10037EEC
0x10037d89  cmp     [esp+130h+var_124], 0
0x10037d8e  mov     esi, [esp+130h+Size]
0x10037d92  mov     [esp+130h+var_10C], esi
0x10037d96  jz      short loc_10037DE0
0x10037d98  test    ebx, ebx
0x10037d9a  jz      short loc_10037DB8
0x10037d9c  cmp     word ptr [ebx], 0
0x10037da0  jz      short loc_10037DB8
0x10037da2  push    0; int
0x10037da4  push    0; int
0x10037da6  push    0; int
0x10037da8  push    0FFFFDFADh; int
0x10037dad  push    0; void *
0x10037daf  push    0; void *
0x10037db1  push    ebx; Src
0x10037db2  push    edi; int
0x10037db3  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10037db8  push    _critJet; lpCriticalSection
0x10037dbe  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037dc4  mov     eax, 0FFFFF891h
0x10037dc9  pop     edi
0x10037dca  pop     esi
0x10037dcb  pop     ebx
0x10037dcc  mov     ecx, [esp+124h+var_4]
0x10037dd3  xor     ecx, esp; StackCookie
0x10037dd5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037dda  mov     esp, ebp
0x10037ddc  pop     ebp
0x10037ddd  retn    8
0x10037de0  lea     ecx, [esp+130h+var_108]
0x10037de4  call    _SecFSystemSid@8; SecFSystemSid(x,x)
0x10037de9  test    eax, eax
0x10037deb  jz      short loc_10037E15
0x10037ded  push    _critJet; lpCriticalSection
0x10037df3  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037df9  mov     eax, 0FFFFF88Eh
0x10037dfe  pop     edi
0x10037dff  pop     esi
0x10037e00  pop     ebx
0x10037e01  mov     ecx, [esp+124h+var_4]
0x10037e08  xor     ecx, esp; StackCookie
0x10037e0a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037e0f  mov     esp, ebp
0x10037e11  pop     ebp
0x10037e12  retn    8
0x10037e15  push    0; int
0x10037e17  lea     eax, [esp+134h+Size]
0x10037e1b  push    eax; int
0x10037e1c  push    80h; Size
0x10037e21  lea     eax, [esp+13Ch+var_88]
0x10037e28  push    eax; int
0x10037e29  push    0; Src
0x10037e2b  push    0FFFFFFFFh; int
0x10037e2d  push    edi; int
0x10037e2e  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10037e33  mov     edx, [esp+130h+Size]
0x10037e37  lea     eax, [esp+130h+var_108]
0x10037e3b  push    esi
0x10037e3c  push    eax
0x10037e3d  lea     ecx, [esp+138h+var_88]
0x10037e44  call    _SecFSameSid@16; SecFSameSid(x,x,x,x)
0x10037e49  test    eax, eax
0x10037e4b  jnz     short loc_10037DED
0x10037e4d  mov     [esp+130h+var_124], eax
0x10037e51  or      edx, 0FFFFFFFFh
0x10037e54  lea     eax, [esp+130h+Block]
0x10037e58  mov     ecx, edi
0x10037e5a  push    eax; int
0x10037e5b  push    esi; Size
0x10037e5c  lea     eax, [esp+138h+var_108]
0x10037e60  push    eax; int
0x10037e61  call    _ErrSecBuildUserToken@20; ErrSecBuildUserToken(x,x,x,x,x)
0x10037e66  mov     ebx, eax
0x10037e68  test    ebx, ebx
0x10037e6a  js      loc_10037F28
0x10037e70  mov     edx, [esp+130h+Block]
0x10037e74  mov     eax, [edx+8]
0x10037e77  lea     esi, [edx+10h]
0x10037e7a  add     eax, 3
0x10037e7d  lea     eax, [edx+eax*4]
0x10037e80  mov     [esp+130h+var_110], eax
0x10037e84  cmp     esi, eax
0x10037e86  jnb     short loc_10037EC1
0x10037e88  mov     ecx, [esi]
0x10037e8a  lea     eax, [esi+4]
0x10037e8d  mov     esi, eax
0x10037e8f  lea     ebx, [ecx+edx]
0x10037e92  mov     eax, [eax]
0x10037e94  sub     eax, ecx
0x10037e96  cmp     byte ptr [ebx], 1
0x10037e99  jnz     short loc_10037EBB
0x10037e9b  lea     ecx, [esp+130h+var_114]
0x10037e9f  mov     edx, ebx
0x10037ea1  push    ecx
0x10037ea2  push    eax
0x10037ea3  mov     ecx, edi
0x10037ea5  call    _ErrSecGetNumMembers@16; ErrSecGetNumMembers(x,x,x,x)
0x10037eaa  mov     ebx, eax
0x10037eac  test    ebx, ebx
0x10037eae  js      short loc_10037F1B
0x10037eb0  cmp     [esp+130h+var_114], 1
0x10037eb5  jz      short loc_10037F11
0x10037eb7  mov     edx, [esp+130h+Block]
0x10037ebb  cmp     esi, [esp+130h+var_110]
0x10037ebf  jb      short loc_10037E88
0x10037ec1  push    [esp+130h+Block]; Block
0x10037ec5  call    ds:__imp__free
0x10037ecb  add     esp, 4
0x10037ece  cmp     [esp+130h+var_124], 0
0x10037ed3  jnz     loc_10037DED
0x10037ed9  push    0
0x10037edb  push    [esp+134h+var_10C]
0x10037edf  lea     edx, [esp+138h+var_108]
0x10037ee3  mov     ecx, edi
0x10037ee5  call    _ErrSecDeleteAccount@16; ErrSecDeleteAccount(x,x,x,x)
0x10037eea  mov     esi, eax
0x10037eec  push    _critJet; lpCriticalSection
0x10037ef2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037ef8  mov     eax, esi
0x10037efa  pop     edi
0x10037efb  pop     esi
0x10037efc  pop     ebx
0x10037efd  mov     ecx, [esp+124h+var_4]
0x10037f04  xor     ecx, esp; StackCookie
0x10037f06  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037f0b  mov     esp, ebp
0x10037f0d  pop     ebp
0x10037f0e  retn    8
0x10037f11  mov     [esp+130h+var_124], 1
0x10037f19  jmp     short loc_10037EC1
0x10037f1b  push    [esp+130h+Block]; Block
0x10037f1f  call    ds:__imp__free
0x10037f25  add     esp, 4
0x10037f28  push    _critJet; lpCriticalSection
0x10037f2e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037f34  mov     ecx, [esp+130h+var_4]
0x10037f3b  mov     eax, ebx
0x10037f3d  pop     edi
0x10037f3e  pop     esi
0x10037f3f  pop     ebx
0x10037f40  xor     ecx, esp; StackCookie
0x10037f42  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037f47  mov     esp, ebp
0x10037f49  pop     ebp
0x10037f4a  retn    8
```
