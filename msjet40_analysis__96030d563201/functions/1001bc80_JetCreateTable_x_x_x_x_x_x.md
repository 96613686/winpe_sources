# JetCreateTable(x,x,x,x,x,x)

- ea: `0x1001bc80`
- end: `0x1001bebc`
- name: `_JetCreateTable@24`
- size: `572`
- prototype: `int __stdcall(int, int, void *Src, int, int, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x100991f9`
- `0x1009d992`
- `0x1009dd17`
- `0x100a7c7d`
- `0x100cf9f4`

## callees

- `0x1001bc80`
- `0x1001c400`
- `0x1003a2a0`
- `0x1003a6c0`
- `0x1003a9c0`
- `0x1003e650`
- `0x1003e7a0`
- `0x1003e870`
- `0x10042c00`
- `0x10043260`
- `0x10043840`
- `0x10045230`
- `0x1011cda3`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bcaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bd5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bd9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001be67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001be91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bea8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bcaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bd5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bd9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001be67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001be91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bea8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bc91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bc91`

## pseudocode

```c
int __stdcall JetCreateTable(void *a1, unsigned int a2, void *Src, int a4, int a5, _DWORD *a6)
{
  int Access; // ebx
  int v8; // ecx
  int v9; // [esp+Ch] [ebp-Ch] BYREF
  int v10; // [esp+10h] [ebp-8h] BYREF
  int v11; // [esp+14h] [ebp-4h] BYREF

  EnterCriticalSection(critJet);
  if ( !FValidSesid((int)a1) )
  {
    LeaveCriticalSection(critJet);
    return -1104;
  }
  if ( a2 >= dbidInit && a2 < 0x100 && (int *)mpdbidpvdbfndef[a2] != vdbfndefInvalidDbid )
  {
    if ( IsJetIsam(a1, a2) || *(&::Src + 5 * mpdbidiiscb[a2]) && (int *)mpdbidpvdbfndef[a2] != vdbfndefRdb )
    {
      Access = ErrSecGetAccess((int)a1, a2, 251658241, 0, 0, 0, &v9, 0);
      if ( Access < 0 )
      {
LABEL_23:
        LeaveCriticalSection(critJet);
        return Access;
      }
      if ( (v9 & 1) == 0 )
      {
        UtilSetErrorInfoReal((int)a1, Src, 0, 0, -8121, 0, 0, 0);
        LeaveCriticalSection(critJet);
        return -1907;
      }
    }
    if ( FTableRepSystem(Src) )
    {
      UtilSetErrorInfoReal((int)a1, Src, 0, 0, -8198, 0, 0, 0);
      LeaveCriticalSection(critJet);
      return -1002;
    }
    Access = ErrDispCreateTable(a1, a2, Src, a4, a5, &v11);
    if ( Access >= 0 )
    {
      ErrSetAcmTableid(v8, 983294);
      if ( !IsJetIsam(a1, a2) && (!*(&::Src + 5 * mpdbidiiscb[a2]) || (int *)mpdbidpvdbfndef[a2] == vdbfndefRdb)
        || (Access = ErrDispGetObjidFromName(a1, a2, L"Tables", Src, &v10), Access >= 0)
        && (Access = ErrSecSetOwner(a1, a2, v10, 0, 0), Access >= 0)
        && (Access = ErrSecBestowAccess(a1, a2, 1, a2, v10, 0, 0, 1, 1, 0, 0, 1), Access >= 0) )
      {
        *a6 = v11;
        LeaveCriticalSection(critJet);
        return Access;
      }
      ErrDispCloseTable(a1, v11);
      ErrDeleteTable(a1, a2, Src);
    }
    goto LABEL_23;
  }
  LeaveCriticalSection(critJet);
  return -1010;
}

```

## disassembly

```asm
0x1001bc80  mov     edi, edi
0x1001bc82  push    ebp
0x1001bc83  mov     ebp, esp
0x1001bc85  sub     esp, 0Ch
0x1001bc88  push    ebx
0x1001bc89  push    esi
0x1001bc8a  push    edi
0x1001bc8b  push    _critJet; lpCriticalSection
0x1001bc91  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001bc97  mov     edi, [ebp+arg_0]
0x1001bc9a  push    edi
0x1001bc9b  call    _FValidSesid@4; FValidSesid(x)
0x1001bca0  test    eax, eax
0x1001bca2  jnz     short loc_1001BCBE
0x1001bca4  push    _critJet; lpCriticalSection
0x1001bcaa  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bcb0  mov     eax, 0FFFFFBB0h
0x1001bcb5  pop     edi
0x1001bcb6  pop     esi
0x1001bcb7  pop     ebx
0x1001bcb8  mov     esp, ebp
0x1001bcba  pop     ebp
0x1001bcbb  retn    18h
0x1001bcbe  mov     esi, [ebp+arg_4]
0x1001bcc1  cmp     esi, _dbidInit
0x1001bcc7  jb      loc_1001BEA2
0x1001bccd  cmp     esi, 100h
0x1001bcd3  jnb     loc_1001BEA2
0x1001bcd9  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefInvalidDbid
0x1001bce4  jz      loc_1001BEA2
0x1001bcea  mov     edx, esi
0x1001bcec  mov     ecx, edi
0x1001bcee  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1001bcf3  test    eax, eax
0x1001bcf5  jnz     short loc_1001BD18
0x1001bcf7  mov     eax, _mpdbidiiscb[esi*4]
0x1001bcfe  lea     eax, [eax+eax*4]
0x1001bd01  cmp     Src[eax*4], 0
0x1001bd09  jz      short loc_1001BD72
0x1001bd0b  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefRdb
0x1001bd16  jz      short loc_1001BD72
0x1001bd18  push    0
0x1001bd1a  lea     eax, [ebp+var_C]
0x1001bd1d  push    eax
0x1001bd1e  push    0
0x1001bd20  push    0
0x1001bd22  push    0
0x1001bd24  push    0F000001h
0x1001bd29  push    esi
0x1001bd2a  push    edi
0x1001bd2b  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x1001bd30  mov     ebx, eax
0x1001bd32  test    ebx, ebx
0x1001bd34  js      loc_1001BE8B
0x1001bd3a  test    byte ptr [ebp+var_C], 1
0x1001bd3e  jnz     short loc_1001BD72
0x1001bd40  push    0; int
0x1001bd42  push    0; int
0x1001bd44  push    0; int
0x1001bd46  push    0FFFFE047h; int
0x1001bd4b  push    0; void *
0x1001bd4d  push    0; void *
0x1001bd4f  push    [ebp+Src]; Src
0x1001bd52  push    edi; int
0x1001bd53  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001bd58  push    _critJet; lpCriticalSection
0x1001bd5e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bd64  mov     eax, 0FFFFF88Dh
0x1001bd69  pop     edi
0x1001bd6a  pop     esi
0x1001bd6b  pop     ebx
0x1001bd6c  mov     esp, ebp
0x1001bd6e  pop     ebp
0x1001bd6f  retn    18h
0x1001bd72  mov     ebx, [ebp+Src]
0x1001bd75  mov     ecx, ebx
0x1001bd77  call    _FTableRepSystem@4; FTableRepSystem(x)
0x1001bd7c  test    eax, eax
0x1001bd7e  jz      short loc_1001BDB0
0x1001bd80  push    0; int
0x1001bd82  push    0; int
0x1001bd84  push    0; int
0x1001bd86  push    0FFFFDFFAh; int
0x1001bd8b  push    0; void *
0x1001bd8d  push    0; void *
0x1001bd8f  push    ebx; Src
0x1001bd90  push    edi; int
0x1001bd91  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001bd96  push    _critJet; lpCriticalSection
0x1001bd9c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bda2  mov     eax, 0FFFFFC16h
0x1001bda7  pop     edi
0x1001bda8  pop     esi
0x1001bda9  pop     ebx
0x1001bdaa  mov     esp, ebp
0x1001bdac  pop     ebp
0x1001bdad  retn    18h
0x1001bdb0  lea     eax, [ebp+var_4]
0x1001bdb3  push    eax
0x1001bdb4  push    [ebp+arg_10]
0x1001bdb7  push    [ebp+arg_C]
0x1001bdba  push    ebx
0x1001bdbb  push    esi
0x1001bdbc  push    edi
0x1001bdbd  call    _ErrDispCreateTable@24; ErrDispCreateTable(x,x,x,x,x,x)
0x1001bdc2  mov     ebx, eax
0x1001bdc4  test    ebx, ebx
0x1001bdc6  js      loc_1001BE8B
0x1001bdcc  mov     edx, [ebp+var_4]
0x1001bdcf  push    0F00FEh
0x1001bdd4  push    ecx
0x1001bdd5  call    _ErrSetAcmTableid@16; ErrSetAcmTableid(x,x,x,x)
0x1001bdda  mov     edx, esi
0x1001bddc  mov     ecx, edi
0x1001bdde  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1001bde3  test    eax, eax
0x1001bde5  jnz     short loc_1001BE08
0x1001bde7  mov     eax, _mpdbidiiscb[esi*4]
0x1001bdee  lea     eax, [eax+eax*4]
0x1001bdf1  cmp     Src[eax*4], 0
0x1001bdf9  jz      short loc_1001BE59
0x1001bdfb  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefRdb
0x1001be06  jz      short loc_1001BE59
0x1001be08  lea     eax, [ebp+var_8]
0x1001be0b  push    eax
0x1001be0c  push    [ebp+Src]
0x1001be0f  push    offset _wszTcObject; "Tables"
0x1001be14  push    esi
0x1001be15  push    edi
0x1001be16  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1001be1b  mov     ebx, eax
0x1001be1d  test    ebx, ebx
0x1001be1f  js      short loc_1001BE78
0x1001be21  push    0
0x1001be23  push    0
0x1001be25  push    [ebp+var_8]
0x1001be28  push    esi
0x1001be29  push    edi
0x1001be2a  call    _ErrSecSetOwner@20; ErrSecSetOwner(x,x,x,x,x)
0x1001be2f  mov     ebx, eax
0x1001be31  test    ebx, ebx
0x1001be33  js      short loc_1001BE78
0x1001be35  push    1
0x1001be37  push    0
0x1001be39  push    0
0x1001be3b  push    1
0x1001be3d  push    1
0x1001be3f  push    0
0x1001be41  push    0
0x1001be43  push    [ebp+var_8]
0x1001be46  push    esi
0x1001be47  push    0F000001h
0x1001be4c  push    esi
0x1001be4d  push    edi
0x1001be4e  call    _ErrSecBestowAccess@48; ErrSecBestowAccess(x,x,x,x,x,x,x,x,x,x,x,x)
0x1001be53  mov     ebx, eax
0x1001be55  test    ebx, ebx
0x1001be57  js      short loc_1001BE78
0x1001be59  mov     ecx, [ebp+arg_14]
0x1001be5c  mov     eax, [ebp+var_4]
0x1001be5f  mov     [ecx], eax
0x1001be61  push    _critJet; lpCriticalSection
0x1001be67  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001be6d  mov     eax, ebx
0x1001be6f  pop     edi
0x1001be70  pop     esi
0x1001be71  pop     ebx
0x1001be72  mov     esp, ebp
0x1001be74  pop     ebp
0x1001be75  retn    18h
0x1001be78  push    [ebp+var_4]
0x1001be7b  push    edi
0x1001be7c  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1001be81  push    [ebp+Src]
0x1001be84  push    esi
0x1001be85  push    edi
0x1001be86  call    _ErrDeleteTable@12; ErrDeleteTable(x,x,x)
0x1001be8b  push    _critJet; lpCriticalSection
0x1001be91  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001be97  mov     eax, ebx
0x1001be99  pop     edi
0x1001be9a  pop     esi
0x1001be9b  pop     ebx
0x1001be9c  mov     esp, ebp
0x1001be9e  pop     ebp
0x1001be9f  retn    18h
0x1001bea2  push    _critJet; lpCriticalSection
0x1001bea8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001beae  pop     edi
0x1001beaf  pop     esi
0x1001beb0  mov     eax, 0FFFFFC0Eh
0x1001beb5  pop     ebx
0x1001beb6  mov     esp, ebp
0x1001beb8  pop     ebp
0x1001beb9  retn    18h
```
