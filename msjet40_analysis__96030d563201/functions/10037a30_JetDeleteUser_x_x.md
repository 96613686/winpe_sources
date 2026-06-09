# JetDeleteUser(x,x)

- ea: `0x10037a30`
- end: `0x10037dcd`
- name: `_JetDeleteUser@8`
- size: `925`
- prototype: `int __stdcall(int, void *Src)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, installer_update`

## callers

- `0x100cf9f4`

## callees

- `0x10037a30`
- `0x10039c00`
- `0x1003cb10`
- `0x1003d0b0`
- `0x1003d0e0`
- `0x1003d3d0`
- `0x1003d8d0`
- `0x1003d9f0`
- `0x1003e820`
- `0x1003e870`
- `0x10043260`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037d45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037d9f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037d45`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10037d9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037a8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037ad2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037b18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037b59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037bc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037d72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037dae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037a8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037ad2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037b18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037b59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037bc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037c73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037d72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10037dae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10037a58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10037a58`

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
    v2 = dword_1016EAE8[26 * v2];
    if ( v2 == -1 )
      goto LABEL_4;
  }
  ClearErrorInfo(a1);
  v4 = (int)*(&rgiscb + 5 * dword_1016EAD0[26 * v2] + 3);
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
0x10037a30  mov     edi, edi
0x10037a32  push    ebp
0x10037a33  mov     ebp, esp
0x10037a35  and     esp, 0FFFFFFF8h
0x10037a38  sub     esp, 124h
0x10037a3e  mov     eax, ___security_cookie
0x10037a43  xor     eax, esp
0x10037a45  mov     [esp+124h+var_4], eax
0x10037a4c  push    ebx
0x10037a4d  mov     ebx, [ebp+Src]
0x10037a50  push    esi
0x10037a51  push    edi
0x10037a52  push    _critJet; lpCriticalSection
0x10037a58  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10037a5e  mov     esi, _isibHead
0x10037a64  cmp     esi, 0FFFFFFFFh
0x10037a67  jz      short loc_10037A86
0x10037a69  mov     edi, [ebp+arg_0]
0x10037a6c  nop     dword ptr [eax+00h]
0x10037a70  imul    eax, esi, 68h ; 'h'
0x10037a73  cmp     _rgsib[eax], edi
0x10037a79  jz      short loc_10037AAE
0x10037a7b  mov     esi, dword_1016EAE8[eax]
0x10037a81  cmp     esi, 0FFFFFFFFh
0x10037a84  jnz     short loc_10037A70
0x10037a86  push    _critJet; lpCriticalSection
0x10037a8c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037a92  mov     eax, 0FFFFFBB0h
0x10037a97  pop     edi
0x10037a98  pop     esi
0x10037a99  pop     ebx
0x10037a9a  mov     ecx, [esp+124h+var_4]
0x10037aa1  xor     ecx, esp; StackCookie
0x10037aa3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037aa8  mov     esp, ebp
0x10037aaa  pop     ebp
0x10037aab  retn    8
0x10037aae  push    edi
0x10037aaf  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10037ab4  imul    eax, esi, 68h ; 'h'
0x10037ab7  mov     eax, dword_1016EAD0[eax]
0x10037abd  lea     eax, [eax+eax*4]
0x10037ac0  mov     esi, dword ptr (_rgiscb+0Ch)[eax*4]
0x10037ac7  cmp     esi, 0FFFFFFFFh
0x10037aca  jnz     short loc_10037AF4
0x10037acc  push    _critJet; lpCriticalSection
0x10037ad2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037ad8  mov     eax, 0FFFFF8F6h
0x10037add  pop     edi
0x10037ade  pop     esi
0x10037adf  pop     ebx
0x10037ae0  mov     ecx, [esp+124h+var_4]
0x10037ae7  xor     ecx, esp; StackCookie
0x10037ae9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037aee  mov     esp, ebp
0x10037af0  pop     ebp
0x10037af1  retn    8
0x10037af4  lea     eax, [esp+130h+var_118]
0x10037af8  push    eax
0x10037af9  push    offset _wszSaTable; "MSysAccounts"
0x10037afe  push    offset _wszTcObject; "Tables"
0x10037b03  push    esi
0x10037b04  push    edi
0x10037b05  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x10037b0a  mov     [esp+130h+var_124], eax
0x10037b0e  test    eax, eax
0x10037b10  jns     short loc_10037B39
0x10037b12  push    _critJet; lpCriticalSection
0x10037b18  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037b1e  mov     eax, [esp+130h+var_124]
0x10037b22  pop     edi
0x10037b23  pop     esi
0x10037b24  pop     ebx
0x10037b25  mov     ecx, [esp+124h+var_4]
0x10037b2c  xor     ecx, esp; StackCookie
0x10037b2e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037b33  mov     esp, ebp
0x10037b35  pop     ebp
0x10037b36  retn    8
0x10037b39  mov     eax, _mpdbidiiscb[esi*4]
0x10037b40  lea     eax, [eax+eax*4]
0x10037b43  mov     eax, Src[eax*4]
0x10037b4a  test    eax, eax
0x10037b4c  jnz     short loc_10037B78
0x10037b4e  push    _critJet; lpCriticalSection
0x10037b54  mov     esi, 0FFFFFC17h
0x10037b59  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037b5f  mov     eax, esi
0x10037b61  pop     edi
0x10037b62  pop     esi
0x10037b63  pop     ebx
0x10037b64  mov     ecx, [esp+124h+var_4]
0x10037b6b  xor     ecx, esp; StackCookie
0x10037b6d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037b72  mov     esp, ebp
0x10037b74  pop     ebp
0x10037b75  retn    8
0x10037b78  push    0
0x10037b7a  lea     ecx, [esp+134h+var_124]
0x10037b7e  mov     edx, esi
0x10037b80  push    ecx
0x10037b81  push    0
0x10037b83  push    eax
0x10037b84  push    [esp+140h+var_118]
0x10037b88  mov     ecx, edi
0x10037b8a  call    _ErrSecCollectAccess@28; ErrSecCollectAccess(x,x,x,x,x,x,x)
0x10037b8f  mov     esi, eax
0x10037b91  test    esi, esi
0x10037b93  js      loc_10037D6C
0x10037b99  test    byte ptr [esp+130h+var_124], 80h
0x10037b9e  jnz     short loc_10037BE2
0x10037ba0  push    0; int
0x10037ba2  push    0; int
0x10037ba4  push    0; int
0x10037ba6  push    0FFFFE016h; int
0x10037bab  push    0; void *
0x10037bad  push    0; void *
0x10037baf  push    offset _wszSaTable; "MSysAccounts"
0x10037bb4  push    edi; int
0x10037bb5  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10037bba  push    _critJet; lpCriticalSection
0x10037bc0  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037bc6  mov     eax, 0FFFFF88Dh
0x10037bcb  pop     edi
0x10037bcc  pop     esi
0x10037bcd  pop     ebx
0x10037bce  mov     ecx, [esp+124h+var_4]
0x10037bd5  xor     ecx, esp; StackCookie
0x10037bd7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037bdc  mov     esp, ebp
0x10037bde  pop     ebp
0x10037bdf  retn    8
0x10037be2  lea     eax, [esp+130h+var_124]
0x10037be6  push    eax; int
0x10037be7  lea     eax, [esp+134h+Size]
0x10037beb  push    eax; int
0x10037bec  push    80h; Size
0x10037bf1  lea     eax, [esp+13Ch+var_108]
0x10037bf5  push    eax; int
0x10037bf6  push    ebx; Src
0x10037bf7  push    0FFFFFFFFh; int
0x10037bf9  push    edi; int
0x10037bfa  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10037bff  mov     esi, eax
0x10037c01  test    esi, esi
0x10037c03  js      loc_10037D6C
0x10037c09  cmp     [esp+130h+var_124], 0
0x10037c0e  mov     esi, [esp+130h+Size]
0x10037c12  mov     [esp+130h+var_10C], esi
0x10037c16  jz      short loc_10037C60
0x10037c18  test    ebx, ebx
0x10037c1a  jz      short loc_10037C38
0x10037c1c  cmp     word ptr [ebx], 0
0x10037c20  jz      short loc_10037C38
0x10037c22  push    0; int
0x10037c24  push    0; int
0x10037c26  push    0; int
0x10037c28  push    0FFFFDFADh; int
0x10037c2d  push    0; void *
0x10037c2f  push    0; void *
0x10037c31  push    ebx; Src
0x10037c32  push    edi; int
0x10037c33  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x10037c38  push    _critJet; lpCriticalSection
0x10037c3e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037c44  mov     eax, 0FFFFF891h
0x10037c49  pop     edi
0x10037c4a  pop     esi
0x10037c4b  pop     ebx
0x10037c4c  mov     ecx, [esp+124h+var_4]
0x10037c53  xor     ecx, esp; StackCookie
0x10037c55  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037c5a  mov     esp, ebp
0x10037c5c  pop     ebp
0x10037c5d  retn    8
0x10037c60  lea     ecx, [esp+130h+var_108]
0x10037c64  call    _SecFSystemSid@8; SecFSystemSid(x,x)
0x10037c69  test    eax, eax
0x10037c6b  jz      short loc_10037C95
0x10037c6d  push    _critJet; lpCriticalSection
0x10037c73  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037c79  mov     eax, 0FFFFF88Eh
0x10037c7e  pop     edi
0x10037c7f  pop     esi
0x10037c80  pop     ebx
0x10037c81  mov     ecx, [esp+124h+var_4]
0x10037c88  xor     ecx, esp; StackCookie
0x10037c8a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037c8f  mov     esp, ebp
0x10037c91  pop     ebp
0x10037c92  retn    8
0x10037c95  push    0; int
0x10037c97  lea     eax, [esp+134h+Size]
0x10037c9b  push    eax; int
0x10037c9c  push    80h; Size
0x10037ca1  lea     eax, [esp+13Ch+var_88]
0x10037ca8  push    eax; int
0x10037ca9  push    0; Src
0x10037cab  push    0FFFFFFFFh; int
0x10037cad  push    edi; int
0x10037cae  call    _ErrSecGetSidFromName@28; ErrSecGetSidFromName(x,x,x,x,x,x,x)
0x10037cb3  mov     edx, [esp+130h+Size]
0x10037cb7  lea     eax, [esp+130h+var_108]
0x10037cbb  push    esi
0x10037cbc  push    eax
0x10037cbd  lea     ecx, [esp+138h+var_88]
0x10037cc4  call    _SecFSameSid@16; SecFSameSid(x,x,x,x)
0x10037cc9  test    eax, eax
0x10037ccb  jnz     short loc_10037C6D
0x10037ccd  mov     [esp+130h+var_124], eax
0x10037cd1  or      edx, 0FFFFFFFFh
0x10037cd4  lea     eax, [esp+130h+Block]
0x10037cd8  mov     ecx, edi
0x10037cda  push    eax; int
0x10037cdb  push    esi; Size
0x10037cdc  lea     eax, [esp+138h+var_108]
0x10037ce0  push    eax; int
0x10037ce1  call    _ErrSecBuildUserToken@20; ErrSecBuildUserToken(x,x,x,x,x)
0x10037ce6  mov     ebx, eax
0x10037ce8  test    ebx, ebx
0x10037cea  js      loc_10037DA8
0x10037cf0  mov     edx, [esp+130h+Block]
0x10037cf4  mov     eax, [edx+8]
0x10037cf7  lea     esi, [edx+10h]
0x10037cfa  add     eax, 3
0x10037cfd  lea     eax, [edx+eax*4]
0x10037d00  mov     [esp+130h+var_110], eax
0x10037d04  cmp     esi, eax
0x10037d06  jnb     short loc_10037D41
0x10037d08  mov     ecx, [esi]
0x10037d0a  lea     eax, [esi+4]
0x10037d0d  mov     esi, eax
0x10037d0f  lea     ebx, [ecx+edx]
0x10037d12  mov     eax, [eax]
0x10037d14  sub     eax, ecx
0x10037d16  cmp     byte ptr [ebx], 1
0x10037d19  jnz     short loc_10037D3B
0x10037d1b  lea     ecx, [esp+130h+var_114]
0x10037d1f  mov     edx, ebx
0x10037d21  push    ecx
0x10037d22  push    eax
0x10037d23  mov     ecx, edi
0x10037d25  call    _ErrSecGetNumMembers@16; ErrSecGetNumMembers(x,x,x,x)
0x10037d2a  mov     ebx, eax
0x10037d2c  test    ebx, ebx
0x10037d2e  js      short loc_10037D9B
0x10037d30  cmp     [esp+130h+var_114], 1
0x10037d35  jz      short loc_10037D91
0x10037d37  mov     edx, [esp+130h+Block]
0x10037d3b  cmp     esi, [esp+130h+var_110]
0x10037d3f  jb      short loc_10037D08
0x10037d41  push    [esp+130h+Block]; Block
0x10037d45  call    ds:__imp__free
0x10037d4b  add     esp, 4
0x10037d4e  cmp     [esp+130h+var_124], 0
0x10037d53  jnz     loc_10037C6D
0x10037d59  push    0
0x10037d5b  push    [esp+134h+var_10C]
0x10037d5f  lea     edx, [esp+138h+var_108]
0x10037d63  mov     ecx, edi
0x10037d65  call    _ErrSecDeleteAccount@16; ErrSecDeleteAccount(x,x,x,x)
0x10037d6a  mov     esi, eax
0x10037d6c  push    _critJet; lpCriticalSection
0x10037d72  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037d78  mov     eax, esi
0x10037d7a  pop     edi
0x10037d7b  pop     esi
0x10037d7c  pop     ebx
0x10037d7d  mov     ecx, [esp+124h+var_4]
0x10037d84  xor     ecx, esp; StackCookie
0x10037d86  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037d8b  mov     esp, ebp
0x10037d8d  pop     ebp
0x10037d8e  retn    8
0x10037d91  mov     [esp+130h+var_124], 1
0x10037d99  jmp     short loc_10037D41
0x10037d9b  push    [esp+130h+Block]; Block
0x10037d9f  call    ds:__imp__free
0x10037da5  add     esp, 4
0x10037da8  push    _critJet; lpCriticalSection
0x10037dae  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10037db4  mov     ecx, [esp+130h+var_4]
0x10037dbb  mov     eax, ebx
0x10037dbd  pop     edi
0x10037dbe  pop     esi
0x10037dbf  pop     ebx
0x10037dc0  xor     ecx, esp; StackCookie
0x10037dc2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10037dc7  mov     esp, ebp
0x10037dc9  pop     ebp
0x10037dca  retn    8
```
