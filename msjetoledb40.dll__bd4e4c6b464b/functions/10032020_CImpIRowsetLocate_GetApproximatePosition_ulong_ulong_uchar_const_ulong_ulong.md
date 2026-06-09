# CImpIRowsetLocate::GetApproximatePosition(ulong,ulong,uchar const *,ulong *,ulong *)

- ea: `0x10032020`
- end: `0x1003226f`
- name: `?GetApproximatePosition@CImpIRowsetLocate@@UAGJKKPBEPAK1@Z`
- size: `591`
- prototype: `int(CImpIRowsetLocate *__hidden this, unsigned int, unsigned int, const unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x10032020`
- `0x100495b0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10032249`
- `KERNEL32!LeaveCriticalSection` at `0x10032249`
- `KERNEL32!EnterCriticalSection` at `0x100320ca`
- `KERNEL32!EnterCriticalSection` at `0x100320ca`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10032066`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10032066`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003211b`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1003211b`
- `msjet40!__imp__JetGetRecordPosition@16` at `0x100321de`
- `msjet40!__imp__JetGetRecordPosition@16` at `0x100321de`
- `msjet40!__imp__JetGotoBookmark@16` at `0x100321a2`
- `msjet40!__imp__JetGotoBookmark@16` at `0x100321a2`
- `msjet40!__imp__JetMove@16` at `0x1003215a`
- `msjet40!__imp__JetMove@16` at `0x1003215a`

## pseudocode

```c
int __stdcall CImpIRowsetLocate::GetApproximatePosition(
        struct _RTL_CRITICAL_SECTION **this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  int v6; // edi
  struct _RTL_CRITICAL_SECTION *v7; // esi
  struct _RTL_CRITICAL_SECTION *v8; // edx
  _DWORD *LockSemaphore; // eax
  CTransactionState *v10; // ecx
  int isZombie; // eax
  int v12; // edx
  JET_ERR RecordPosition; // eax
  const struct _GUID *v15; // [esp+0h] [ebp-40h]
  const struct _GUID *v16; // [esp+4h] [ebp-3Ch]
  void *pvBookmark; // [esp+14h] [ebp-2Ch] BYREF
  unsigned int *v18; // [esp+18h] [ebp-28h]
  CImpIRowsetLocate *v19; // [esp+1Ch] [ebp-24h]
  JET_RECPOS precpos; // [esp+20h] [ebp-20h] BYREF
  int v21; // [esp+3Ch] [ebp-4h]

  v6 = 0;
  v19 = (CImpIRowsetLocate *)this;
  pvBookmark = a4;
  v18 = a5;
  SetErrorInfo(0, 0);
  v7 = 0;
  v21 = 0;
  v8 = this[2];
  LockSemaphore = v8[2].LockSemaphore;
  if ( LockSemaphore
    && (LockSemaphore[4] != 1 || (v10 = (CTransactionState *)LockSemaphore[2]) == 0
      ? (isZombie = LockSemaphore[3])
      : (isZombie = CTransactionState::isZombie(v10)),
        isZombie == 1)
    || !v8[4].SpinCount && !v8[9].SpinCount )
  {
    v6 = -2147418113;
    goto LABEL_19;
  }
  if ( ((int)v8[4].DebugInfo & 0x400) != 0 )
  {
    v6 = -2147217888;
    goto LABEL_19;
  }
  v7 = v8 + 3;
  EnterCriticalSection(v8 + 3);
  if ( a3 )
  {
    if ( !pvBookmark )
    {
      v6 = -2147024809;
      goto LABEL_19;
    }
    if ( a3 == 1 )
    {
      if ( *(_BYTE *)pvBookmark == 1 )
      {
        v12 = 0x80000000;
      }
      else
      {
        if ( *(_BYTE *)pvBookmark != 2 )
        {
          v6 = -2147217906;
LABEL_19:
          if ( !JetGetDatabaseInfo(
                  *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v19 + 2) + 56) + 16),
                  *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v19 + 2) + 56) + 20),
                  &pvBookmark,
                  4,
                  3) )
            CExtError::SendHRtoOLEAuto(v6, (__int128 *)&IID_IRowsetScroll, 0, v15, (int)v16);
          goto LABEL_48;
        }
        v12 = 0x7FFFFFFF;
      }
      RecordPosition = JetMove(
                         *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v19 + 2) + 56) + 16),
                         *(_DWORD *)(*((_DWORD *)v19 + 2) + 108),
                         v12,
                         0);
      if ( RecordPosition == -1603 )
      {
        v6 = 0;
        if ( a6 )
          *a6 = 0;
        if ( v18 )
          *v18 = 0;
        goto LABEL_48;
      }
      if ( RecordPosition )
      {
        v6 = -2147467259;
LABEL_47:
        CExtError::SendJetErrortoOLEAuto(
          v6,
          *(char **)(*(_DWORD *)(*((_DWORD *)v19 + 2) + 56) + 16),
          RecordPosition,
          (int)&IID_IRowsetScroll,
          (int)v15,
          v16);
        goto LABEL_48;
      }
    }
    else
    {
      RecordPosition = JetGotoBookmark(
                         *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v19 + 2) + 56) + 16),
                         *(_DWORD *)(*((_DWORD *)v19 + 2) + 108),
                         pvBookmark,
                         4u);
      if ( RecordPosition )
      {
        if ( RecordPosition == -1045 || RecordPosition == -1017 )
          v6 = -2147217906;
        else
          v6 = -2147467259;
        goto LABEL_47;
      }
    }
  }
  RecordPosition = JetGetRecordPosition(
                     *(_DWORD *)(*(_DWORD *)(*((_DWORD *)v19 + 2) + 56) + 16),
                     *(_DWORD *)(*((_DWORD *)v19 + 2) + 108),
                     &precpos,
                     0x10u);
  if ( RecordPosition == -1603 )
  {
    if ( v18 )
      *v18 = 0;
    if ( a6 )
      *a6 = 0;
    goto LABEL_47;
  }
  if ( RecordPosition )
  {
    v6 = -2147467259;
    goto LABEL_47;
  }
  if ( a3 && v18 )
    *v18 = precpos.centriesLT + 1;
  if ( a6 )
    *a6 = precpos.centriesTotal;
LABEL_48:
  if ( v7 )
    LeaveCriticalSection(v7);
  return v6;
}

```

## disassembly

```asm
0x10032020  mov     edi, edi
0x10032022  push    ebp
0x10032023  mov     ebp, esp
0x10032025  push    0FFFFFFFFh
0x10032027  push    offset ?GetApproximatePosition@CImpIRowsetLocate@@UAGJKKPBEPAK1@Z_SEH
0x1003202c  mov     eax, large fs:0
0x10032032  push    eax
0x10032033  sub     esp, 24h
0x10032036  mov     eax, ___security_cookie
0x1003203b  xor     eax, ebp
0x1003203d  mov     [ebp+var_10], eax
0x10032040  push    ebx
0x10032041  push    esi
0x10032042  push    edi; struct _GUID *
0x10032043  push    eax; int
0x10032044  lea     eax, [ebp+var_C]
0x10032047  mov     large fs:0, eax
0x1003204d  mov     eax, [ebp+this]
0x10032050  xor     edi, edi
0x10032052  mov     ebx, [ebp+arg_14]
0x10032055  mov     [ebp+var_24], eax
0x10032058  mov     eax, [ebp+arg_C]
0x1003205b  push    edi; perrinfo
0x1003205c  mov     [ebp+pvBookmark], eax
0x1003205f  mov     eax, [ebp+arg_10]
0x10032062  push    edi; dwReserved
0x10032063  mov     [ebp+var_28], eax
0x10032066  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1003206c  xor     esi, esi
0x1003206e  mov     [ebp+var_30], esi
0x10032071  mov     edx, [ebp+var_24]
0x10032074  mov     [ebp+var_4], esi
0x10032077  mov     edx, [edx+8]
0x1003207a  mov     eax, [edx+40h]
0x1003207d  test    eax, eax
0x1003207f  jz      short loc_1003209D
0x10032081  cmp     dword ptr [eax+10h], 1
0x10032085  jnz     short loc_10032095
0x10032087  mov     ecx, [eax+8]; this
0x1003208a  test    ecx, ecx
0x1003208c  jz      short loc_10032095
0x1003208e  call    ?isZombie@CTransactionState@@QAEHXZ; CTransactionState::isZombie(void)
0x10032093  jmp     short loc_10032098
0x10032095  mov     eax, [eax+0Ch]
0x10032098  cmp     eax, 1
0x1003209b  jz      short loc_100320AC
0x1003209d  cmp     dword ptr [edx+74h], 0
0x100320a1  jnz     short loc_100320B3
0x100320a3  cmp     dword ptr [edx+0ECh], 0
0x100320aa  jnz     short loc_100320B3
0x100320ac  mov     edi, 8000FFFFh
0x100320b1  jmp     short loc_10032104
0x100320b3  test    dword ptr [edx+60h], 400h
0x100320ba  jz      short loc_100320C3
0x100320bc  mov     edi, 80040E20h
0x100320c1  jmp     short loc_10032104
0x100320c3  lea     esi, [edx+48h]
0x100320c6  push    esi; lpCriticalSection
0x100320c7  mov     [ebp+var_30], esi
0x100320ca  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100320d0  mov     eax, [ebp+arg_8]
0x100320d3  test    eax, eax
0x100320d5  jz      loc_100321C8
0x100320db  mov     edx, [ebp+pvBookmark]
0x100320de  test    edx, edx
0x100320e0  jnz     short loc_100320E9
0x100320e2  mov     edi, 80070057h
0x100320e7  jmp     short loc_10032104
0x100320e9  cmp     eax, 1
0x100320ec  jnz     loc_1003218F
0x100320f2  movzx   eax, byte ptr [edx]
0x100320f5  sub     eax, 1
0x100320f8  jz      short loc_10032142
0x100320fa  sub     eax, 1
0x100320fd  jz      short loc_1003213B
0x100320ff  mov     edi, 80040E0Eh
0x10032104  mov     eax, [ebp+var_24]
0x10032107  lea     ecx, [ebp+pvBookmark]
0x1003210a  push    3
0x1003210c  push    4
0x1003210e  push    ecx
0x1003210f  mov     eax, [eax+8]
0x10032112  mov     eax, [eax+38h]
0x10032115  push    dword ptr [eax+14h]
0x10032118  push    dword ptr [eax+10h]
0x1003211b  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10032121  test    eax, eax
0x10032123  jnz     loc_10032244
0x10032129  push    eax; int
0x1003212a  push    offset _IID_IRowsetScroll; int
0x1003212f  mov     edx, edi
0x10032131  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10032136  jmp     loc_10032244
0x1003213b  mov     edx, 7FFFFFFFh
0x10032140  jmp     short loc_10032147
0x10032142  mov     edx, 80000000h
0x10032147  mov     eax, [ebp+var_24]
0x1003214a  push    0; grbit
0x1003214c  push    edx; cRow
0x1003214d  mov     eax, [eax+8]
0x10032150  mov     ecx, [eax+6Ch]
0x10032153  mov     eax, [eax+38h]
0x10032156  push    ecx; tableid
0x10032157  push    dword ptr [eax+10h]; sesid
0x1003215a  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x10032160  cmp     eax, 0FFFFF9BDh
0x10032165  jnz     short loc_10032181
0x10032167  xor     edi, edi
0x10032169  test    ebx, ebx
0x1003216b  jz      short loc_1003216F
0x1003216d  mov     [ebx], edi
0x1003216f  mov     eax, [ebp+var_28]
0x10032172  test    eax, eax
0x10032174  jz      loc_10032244
0x1003217a  mov     [eax], edi
0x1003217c  jmp     loc_10032244
0x10032181  test    eax, eax
0x10032183  jz      short loc_100321C8
0x10032185  mov     edi, 80004005h
0x1003218a  jmp     loc_1003222B
0x1003218f  mov     eax, [ebp+var_24]
0x10032192  push    4; cbBookmark
0x10032194  push    edx; pvBookmark
0x10032195  mov     eax, [eax+8]
0x10032198  mov     ecx, [eax+6Ch]
0x1003219b  mov     eax, [eax+38h]
0x1003219e  push    ecx; tableid
0x1003219f  push    dword ptr [eax+10h]; sesid
0x100321a2  call    ds:__imp__JetGotoBookmark@16; JetGotoBookmark(x,x,x,x)
0x100321a8  test    eax, eax
0x100321aa  jz      short loc_100321C8
0x100321ac  cmp     eax, 0FFFFFBEBh
0x100321b1  jz      short loc_100321C1
0x100321b3  cmp     eax, 0FFFFFC07h
0x100321b8  jz      short loc_100321C1
0x100321ba  mov     edi, 80004005h
0x100321bf  jmp     short loc_1003222B
0x100321c1  mov     edi, 80040E0Eh
0x100321c6  jmp     short loc_1003222B
0x100321c8  mov     eax, [ebp+var_24]
0x100321cb  lea     edx, [ebp+precpos]
0x100321ce  push    10h; cbRecpos
0x100321d0  push    edx; precpos
0x100321d1  mov     eax, [eax+8]
0x100321d4  mov     ecx, [eax+6Ch]
0x100321d7  mov     eax, [eax+38h]
0x100321da  push    ecx; tableid
0x100321db  push    dword ptr [eax+10h]; sesid
0x100321de  call    ds:__imp__JetGetRecordPosition@16; JetGetRecordPosition(x,x,x,x)
0x100321e4  cmp     eax, 0FFFFF9BDh
0x100321e9  jz      short loc_10032214
0x100321eb  test    eax, eax
0x100321ed  jz      short loc_100321F6
0x100321ef  mov     edi, 80004005h
0x100321f4  jmp     short loc_1003222B
0x100321f6  cmp     [ebp+arg_8], 0
0x100321fa  jz      short loc_10032209
0x100321fc  mov     ecx, [ebp+var_28]
0x100321ff  test    ecx, ecx
0x10032201  jz      short loc_10032209
0x10032203  mov     eax, [ebp+precpos.centriesLT]
0x10032206  inc     eax
0x10032207  mov     [ecx], eax
0x10032209  test    ebx, ebx
0x1003220b  jz      short loc_10032244
0x1003220d  mov     eax, [ebp+precpos.centriesTotal]
0x10032210  mov     [ebx], eax
0x10032212  jmp     short loc_10032244
0x10032214  mov     ecx, [ebp+var_28]
0x10032217  test    ecx, ecx
0x10032219  jz      short loc_10032221
0x1003221b  mov     dword ptr [ecx], 0
0x10032221  test    ebx, ebx
0x10032223  jz      short loc_1003222B
0x10032225  mov     dword ptr [ebx], 0
0x1003222b  push    offset _IID_IRowsetScroll; int
0x10032230  push    eax; unsigned int
0x10032231  mov     eax, [ebp+var_24]
0x10032234  mov     edx, edi
0x10032236  mov     eax, [eax+8]
0x10032239  mov     ecx, [eax+38h]
0x1003223c  mov     ecx, [ecx+10h]
0x1003223f  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10032244  test    esi, esi
0x10032246  jz      short loc_1003224F
0x10032248  push    esi; lpCriticalSection
0x10032249  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1003224f  mov     eax, edi
0x10032251  mov     ecx, [ebp+var_C]
0x10032254  mov     large fs:0, ecx
0x1003225b  pop     ecx
0x1003225c  pop     edi
0x1003225d  pop     esi
0x1003225e  pop     ebx
0x1003225f  mov     ecx, [ebp+var_10]
0x10032262  xor     ecx, ebp; StackCookie
0x10032264  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10032269  mov     esp, ebp
0x1003226b  pop     ebp
0x1003226c  retn    18h
0x1004ecb0  lea     ecx, [ebp+var_30]; this
0x1004ecb3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004ecbd  nop
0x1004ecbe  nop
0x1004ecbf  mov     edx, [esp-4+arg_4]
0x1004ecc3  lea     eax, [edx+0Ch]
0x1004ecc6  mov     ecx, [edx-34h]
0x1004ecc9  xor     ecx, eax; StackCookie
0x1004eccb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ecd0  mov     ecx, [edx-4]
0x1004ecd3  xor     ecx, eax; StackCookie
0x1004ecd5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ecda  mov     eax, offset stru_1004FED0
0x1004ecdf  jmp     ___CxxFrameHandler3
```
