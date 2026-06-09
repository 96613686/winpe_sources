# CImpICommandWithParameters::SetParameterInfo(ulong,ulong const * const,tagDBPARAMBINDINFO const * const)

- ea: `0x10011260`
- end: `0x10011375`
- name: `?SetParameterInfo@CImpICommandWithParameters@@UAGJKQBKQBUtagDBPARAMBINDINFO@@@Z`
- size: `277`
- prototype: `int(CImpICommandWithParameters *__hidden this, unsigned int, const unsigned int *const, const struct tagDBPARAMBINDINFO *const)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x10011260`
- `0x1001c380`
- `0x100497f0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10011359`
- `KERNEL32!LeaveCriticalSection` at `0x10011359`
- `KERNEL32!EnterCriticalSection` at `0x100112aa`
- `KERNEL32!EnterCriticalSection` at `0x100112aa`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10011294`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10011294`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001133d`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x1001133d`

## pseudocode

```c
int __stdcall CImpICommandWithParameters::SetParameterInfo(
        CImpICommandWithParameters *this,
        unsigned int a2,
        unsigned int *a3,
        const struct tagDBPARAMBINDINFO *const a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  int v5; // edi
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  const struct _GUID *v13; // [esp+0h] [ebp-24h]
  int v14; // [esp+4h] [ebp-20h]
  _BYTE v15[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v16; // [esp+14h] [ebp-10h]
  int v17; // [esp+20h] [ebp-4h]

  SetErrorInfo(0, 0);
  v16 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v4 = v16;
  EnterCriticalSection(v16);
  v17 = 0;
  if ( !a2 || a3 )
  {
    v9 = 0;
    if ( a2 )
    {
      while ( a3[v9] )
      {
        if ( ++v9 >= a2 )
          goto LABEL_7;
      }
    }
    else
    {
LABEL_7:
      if ( !a4 || (v10 = 0, !a2) )
      {
LABEL_11:
        v5 = CJetParameterList::SetParameterInfo((CJetParameterList *)(*((_DWORD *)this + 2) + 84), a2, a3, a4);
        if ( v5 >= 0 )
          goto LABEL_15;
        v11 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
        v7 = *(_DWORD *)(v11 + 20);
        v8 = *(_DWORD *)(v11 + 16);
        if ( v5 == -2147024882 )
          goto LABEL_15;
        goto LABEL_13;
      }
      while ( a4[v10].pwszDataSourceType )
      {
        if ( ++v10 >= a2 )
          goto LABEL_11;
      }
    }
  }
  v5 = -2147024809;
  v6 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
  v7 = *(_DWORD *)(v6 + 20);
  v8 = *(_DWORD *)(v6 + 16);
LABEL_13:
  if ( !JetGetDatabaseInfo(v8, v7, v15, 4, 3) )
    CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_ICommandWithParameters, 0, v13, v14);
LABEL_15:
  if ( v4 )
    LeaveCriticalSection(v4);
  return v5;
}

```

## disassembly

```asm
0x10011260  mov     edi, edi
0x10011262  push    ebp
0x10011263  mov     ebp, esp
0x10011265  push    0FFFFFFFFh
0x10011267  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1001126c  mov     eax, large fs:0
0x10011272  push    eax
0x10011273  sub     esp, 8
0x10011276  push    ebx
0x10011277  push    esi
0x10011278  push    edi; int
0x10011279  mov     eax, ___security_cookie
0x1001127e  xor     eax, ebp
0x10011280  push    eax; struct _GUID *
0x10011281  lea     eax, [ebp+var_C]
0x10011284  mov     large fs:0, eax
0x1001128a  mov     edi, [ebp+arg_8]
0x1001128d  mov     ebx, [ebp+arg_C]
0x10011290  push    0; perrinfo
0x10011292  push    0; dwReserved
0x10011294  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1001129a  mov     esi, [ebp+this]
0x1001129d  mov     esi, [esi+8]
0x100112a0  add     esi, 0F8h
0x100112a6  push    esi; lpCriticalSection
0x100112a7  mov     [ebp+var_10], esi
0x100112aa  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100112b0  mov     edx, [ebp+arg_4]
0x100112b3  mov     [ebp+var_4], 0
0x100112ba  test    edx, edx
0x100112bc  jz      short loc_100112D8
0x100112be  test    edi, edi
0x100112c0  jnz     short loc_100112D8
0x100112c2  mov     eax, [ebp+this]
0x100112c5  mov     edi, 80070057h
0x100112ca  mov     eax, [eax+8]
0x100112cd  mov     eax, [eax+34h]
0x100112d0  mov     ecx, [eax+14h]
0x100112d3  mov     eax, [eax+10h]
0x100112d6  jmp     short loc_10011333
0x100112d8  xor     eax, eax
0x100112da  test    edx, edx
0x100112dc  jz      short loc_100112EB
0x100112de  mov     edi, edi
0x100112e0  cmp     dword ptr [edi+eax*4], 0
0x100112e4  jz      short loc_100112C2
0x100112e6  inc     eax
0x100112e7  cmp     eax, edx
0x100112e9  jb      short loc_100112E0
0x100112eb  test    ebx, ebx
0x100112ed  jz      short loc_10011303
0x100112ef  xor     ecx, ecx
0x100112f1  test    edx, edx
0x100112f3  jz      short loc_10011303
0x100112f5  lea     eax, [ecx+ecx*8]
0x100112f8  cmp     dword ptr [ebx+eax*2], 0
0x100112fc  jz      short loc_100112C2
0x100112fe  inc     ecx
0x100112ff  cmp     ecx, edx
0x10011301  jb      short loc_100112F5
0x10011303  mov     eax, [ebp+this]
0x10011306  push    ebx; struct tagDBPARAMBINDINFO *
0x10011307  push    edi; unsigned int *
0x10011308  push    edx; unsigned int
0x10011309  mov     ecx, [eax+8]
0x1001130c  add     ecx, 54h ; 'T'; this
0x1001130f  call    ?SetParameterInfo@CJetParameterList@@QAEJKQBKQBUtagDBPARAMBINDINFO@@@Z; CJetParameterList::SetParameterInfo(ulong,ulong const * const,tagDBPARAMBINDINFO const * const)
0x10011314  mov     edi, eax
0x10011316  mov     edx, edi
0x10011318  test    edi, edi
0x1001131a  jns     short loc_10011354
0x1001131c  mov     eax, [ebp+this]
0x1001131f  mov     eax, [eax+8]
0x10011322  mov     eax, [eax+34h]
0x10011325  mov     ecx, [eax+14h]
0x10011328  mov     eax, [eax+10h]
0x1001132b  cmp     edx, 8007000Eh
0x10011331  jz      short loc_10011354
0x10011333  push    3
0x10011335  push    4
0x10011337  lea     edx, [ebp+var_14]
0x1001133a  push    edx
0x1001133b  push    ecx
0x1001133c  push    eax
0x1001133d  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10011343  test    eax, eax
0x10011345  jnz     short loc_10011354
0x10011347  push    eax; int
0x10011348  push    offset _IID_ICommandWithParameters; int
0x1001134d  mov     edx, edi
0x1001134f  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10011354  test    esi, esi
0x10011356  jz      short loc_1001135F
0x10011358  push    esi; lpCriticalSection
0x10011359  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001135f  mov     eax, edi
0x10011361  mov     ecx, [ebp+var_C]
0x10011364  mov     large fs:0, ecx
0x1001136b  pop     ecx
0x1001136c  pop     edi
0x1001136d  pop     esi
0x1001136e  pop     ebx
0x1001136f  mov     esp, ebp
0x10011371  pop     ebp
0x10011372  retn    10h
0x1004ddb0  lea     ecx, [ebp+var_10]; this
0x1004ddb3  jmp     ??1CMutex@@QAE@XZ
0x1004ddbd  nop
0x1004ddbe  nop
0x1004ddbf  mov     edx, [esp-4+arg_4]
0x1004ddc3  lea     eax, [edx+0Ch]
0x1004ddc6  mov     ecx, [edx-18h]
0x1004ddc9  xor     ecx, eax; StackCookie
0x1004ddcb  call    @__security_check_cookie@4
0x1004ddd0  mov     eax, offset stru_1004F3AC
0x1004ddd5  jmp     ___CxxFrameHandler3
```
