# JetCreateTable(x,x,x,x,x,x)

- ea: `0x1001bdd0`
- end: `0x1001c00c`
- name: `_JetCreateTable@24`
- size: `572`
- prototype: `int __stdcall(int, int, void *Src, int, int, int)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x10099389`
- `0x1009db22`
- `0x1009dea7`
- `0x100a7e0d`
- `0x100cfb84`

## callees

- `0x1001bdd0`
- `0x1001c550`
- `0x1003a420`
- `0x1003a840`
- `0x1003ab40`
- `0x1003e7e0`
- `0x1003e930`
- `0x1003ea00`
- `0x10042d90`
- `0x100433f0`
- `0x100439d0`
- `0x100453b0`
- `0x1011cf53`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bdfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001beae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001beec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bfb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bfe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bff8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bdfa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001beae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001beec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bfb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bfe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1001bff8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bde1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1001bde1`

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
0x1001bdd0  mov     edi, edi
0x1001bdd2  push    ebp
0x1001bdd3  mov     ebp, esp
0x1001bdd5  sub     esp, 0Ch
0x1001bdd8  push    ebx
0x1001bdd9  push    esi
0x1001bdda  push    edi
0x1001bddb  push    _critJet; lpCriticalSection
0x1001bde1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001bde7  mov     edi, [ebp+arg_0]
0x1001bdea  push    edi
0x1001bdeb  call    _FValidSesid@4; FValidSesid(x)
0x1001bdf0  test    eax, eax
0x1001bdf2  jnz     short loc_1001BE0E
0x1001bdf4  push    _critJet; lpCriticalSection
0x1001bdfa  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001be00  mov     eax, 0FFFFFBB0h
0x1001be05  pop     edi
0x1001be06  pop     esi
0x1001be07  pop     ebx
0x1001be08  mov     esp, ebp
0x1001be0a  pop     ebp
0x1001be0b  retn    18h
0x1001be0e  mov     esi, [ebp+arg_4]
0x1001be11  cmp     esi, _dbidInit
0x1001be17  jb      loc_1001BFF2
0x1001be1d  cmp     esi, 100h
0x1001be23  jnb     loc_1001BFF2
0x1001be29  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefInvalidDbid
0x1001be34  jz      loc_1001BFF2
0x1001be3a  mov     edx, esi
0x1001be3c  mov     ecx, edi
0x1001be3e  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1001be43  test    eax, eax
0x1001be45  jnz     short loc_1001BE68
0x1001be47  mov     eax, _mpdbidiiscb[esi*4]
0x1001be4e  lea     eax, [eax+eax*4]
0x1001be51  cmp     Src[eax*4], 0
0x1001be59  jz      short loc_1001BEC2
0x1001be5b  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefRdb
0x1001be66  jz      short loc_1001BEC2
0x1001be68  push    0
0x1001be6a  lea     eax, [ebp+var_C]
0x1001be6d  push    eax
0x1001be6e  push    0
0x1001be70  push    0
0x1001be72  push    0
0x1001be74  push    0F000001h
0x1001be79  push    esi
0x1001be7a  push    edi
0x1001be7b  call    _ErrSecGetAccess@32; ErrSecGetAccess(x,x,x,x,x,x,x,x)
0x1001be80  mov     ebx, eax
0x1001be82  test    ebx, ebx
0x1001be84  js      loc_1001BFDB
0x1001be8a  test    byte ptr [ebp+var_C], 1
0x1001be8e  jnz     short loc_1001BEC2
0x1001be90  push    0; int
0x1001be92  push    0; int
0x1001be94  push    0; int
0x1001be96  push    0FFFFE047h; int
0x1001be9b  push    0; void *
0x1001be9d  push    0; void *
0x1001be9f  push    [ebp+Src]; Src
0x1001bea2  push    edi; int
0x1001bea3  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001bea8  push    _critJet; lpCriticalSection
0x1001beae  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001beb4  mov     eax, 0FFFFF88Dh
0x1001beb9  pop     edi
0x1001beba  pop     esi
0x1001bebb  pop     ebx
0x1001bebc  mov     esp, ebp
0x1001bebe  pop     ebp
0x1001bebf  retn    18h
0x1001bec2  mov     ebx, [ebp+Src]
0x1001bec5  mov     ecx, ebx
0x1001bec7  call    _FTableRepSystem@4; FTableRepSystem(x)
0x1001becc  test    eax, eax
0x1001bece  jz      short loc_1001BF00
0x1001bed0  push    0; int
0x1001bed2  push    0; int
0x1001bed4  push    0; int
0x1001bed6  push    0FFFFDFFAh; int
0x1001bedb  push    0; void *
0x1001bedd  push    0; void *
0x1001bedf  push    ebx; Src
0x1001bee0  push    edi; int
0x1001bee1  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x1001bee6  push    _critJet; lpCriticalSection
0x1001beec  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bef2  mov     eax, 0FFFFFC16h
0x1001bef7  pop     edi
0x1001bef8  pop     esi
0x1001bef9  pop     ebx
0x1001befa  mov     esp, ebp
0x1001befc  pop     ebp
0x1001befd  retn    18h
0x1001bf00  lea     eax, [ebp+var_4]
0x1001bf03  push    eax
0x1001bf04  push    [ebp+arg_10]
0x1001bf07  push    [ebp+arg_C]
0x1001bf0a  push    ebx
0x1001bf0b  push    esi
0x1001bf0c  push    edi
0x1001bf0d  call    _ErrDispCreateTable@24; ErrDispCreateTable(x,x,x,x,x,x)
0x1001bf12  mov     ebx, eax
0x1001bf14  test    ebx, ebx
0x1001bf16  js      loc_1001BFDB
0x1001bf1c  mov     edx, [ebp+var_4]
0x1001bf1f  push    0F00FEh
0x1001bf24  push    ecx
0x1001bf25  call    _ErrSetAcmTableid@16; ErrSetAcmTableid(x,x,x,x)
0x1001bf2a  mov     edx, esi
0x1001bf2c  mov     ecx, edi
0x1001bf2e  call    _IsJetIsam@8; IsJetIsam(x,x)
0x1001bf33  test    eax, eax
0x1001bf35  jnz     short loc_1001BF58
0x1001bf37  mov     eax, _mpdbidiiscb[esi*4]
0x1001bf3e  lea     eax, [eax+eax*4]
0x1001bf41  cmp     Src[eax*4], 0
0x1001bf49  jz      short loc_1001BFA9
0x1001bf4b  cmp     _mpdbidpvdbfndef[esi*4], offset _vdbfndefRdb
0x1001bf56  jz      short loc_1001BFA9
0x1001bf58  lea     eax, [ebp+var_8]
0x1001bf5b  push    eax
0x1001bf5c  push    [ebp+Src]
0x1001bf5f  push    offset _wszTcObject; "Tables"
0x1001bf64  push    esi
0x1001bf65  push    edi
0x1001bf66  call    _ErrDispGetObjidFromName@20; ErrDispGetObjidFromName(x,x,x,x,x)
0x1001bf6b  mov     ebx, eax
0x1001bf6d  test    ebx, ebx
0x1001bf6f  js      short loc_1001BFC8
0x1001bf71  push    0
0x1001bf73  push    0
0x1001bf75  push    [ebp+var_8]
0x1001bf78  push    esi
0x1001bf79  push    edi
0x1001bf7a  call    _ErrSecSetOwner@20; ErrSecSetOwner(x,x,x,x,x)
0x1001bf7f  mov     ebx, eax
0x1001bf81  test    ebx, ebx
0x1001bf83  js      short loc_1001BFC8
0x1001bf85  push    1
0x1001bf87  push    0
0x1001bf89  push    0
0x1001bf8b  push    1
0x1001bf8d  push    1
0x1001bf8f  push    0
0x1001bf91  push    0
0x1001bf93  push    [ebp+var_8]
0x1001bf96  push    esi
0x1001bf97  push    0F000001h
0x1001bf9c  push    esi
0x1001bf9d  push    edi
0x1001bf9e  call    _ErrSecBestowAccess@48; ErrSecBestowAccess(x,x,x,x,x,x,x,x,x,x,x,x)
0x1001bfa3  mov     ebx, eax
0x1001bfa5  test    ebx, ebx
0x1001bfa7  js      short loc_1001BFC8
0x1001bfa9  mov     ecx, [ebp+arg_14]
0x1001bfac  mov     eax, [ebp+var_4]
0x1001bfaf  mov     [ecx], eax
0x1001bfb1  push    _critJet; lpCriticalSection
0x1001bfb7  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bfbd  mov     eax, ebx
0x1001bfbf  pop     edi
0x1001bfc0  pop     esi
0x1001bfc1  pop     ebx
0x1001bfc2  mov     esp, ebp
0x1001bfc4  pop     ebp
0x1001bfc5  retn    18h
0x1001bfc8  push    [ebp+var_4]
0x1001bfcb  push    edi
0x1001bfcc  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1001bfd1  push    [ebp+Src]
0x1001bfd4  push    esi
0x1001bfd5  push    edi
0x1001bfd6  call    _ErrDeleteTable@12; ErrDeleteTable(x,x,x)
0x1001bfdb  push    _critJet; lpCriticalSection
0x1001bfe1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bfe7  mov     eax, ebx
0x1001bfe9  pop     edi
0x1001bfea  pop     esi
0x1001bfeb  pop     ebx
0x1001bfec  mov     esp, ebp
0x1001bfee  pop     ebp
0x1001bfef  retn    18h
0x1001bff2  push    _critJet; lpCriticalSection
0x1001bff8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001bffe  pop     edi
0x1001bfff  pop     esi
0x1001c000  mov     eax, 0FFFFFC0Eh
0x1001c005  pop     ebx
0x1001c006  mov     esp, ebp
0x1001c008  pop     ebp
0x1001c009  retn    18h
```
