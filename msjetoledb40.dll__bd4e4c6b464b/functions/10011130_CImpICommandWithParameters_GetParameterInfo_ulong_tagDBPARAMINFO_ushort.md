# CImpICommandWithParameters::GetParameterInfo(ulong *,tagDBPARAMINFO * *,ushort * *)

- ea: `0x10011130`
- end: `0x10011251`
- name: `?GetParameterInfo@CImpICommandWithParameters@@UAGJPAKPAPAUtagDBPARAMINFO@@PAPAG@Z`
- size: `289`
- prototype: `int(CImpICommandWithParameters *__hidden this, unsigned int *, struct tagDBPARAMINFO **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x10011130`
- `0x100147f0`
- `0x1001c380`
- `0x10049980`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10011235`
- `KERNEL32!LeaveCriticalSection` at `0x10011235`
- `KERNEL32!EnterCriticalSection` at `0x10011174`
- `KERNEL32!EnterCriticalSection` at `0x10011174`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001115e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1001115e`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10011219`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10011219`

## pseudocode

```c
int __stdcall CImpICommandWithParameters::GetParameterInfo(
        CImpICommandWithParameters *this,
        unsigned int *a2,
        struct tagDBPARAMINFO **a3,
        unsigned __int16 **a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // esi
  int v5; // edi
  int ParameterInfo; // edi
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // eax
  const struct _GUID *v12; // [esp+0h] [ebp-24h]
  int v13; // [esp+4h] [ebp-20h]
  _BYTE v14[4]; // [esp+10h] [ebp-14h] BYREF
  LPCRITICAL_SECTION v15; // [esp+14h] [ebp-10h]
  int v16; // [esp+20h] [ebp-4h]

  SetErrorInfo(0, 0);
  v15 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v4 = v15;
  EnterCriticalSection(v15);
  v16 = 0;
  CCommand::CheckForZombieCommandAndFix(*((_DWORD *)this + 2));
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a2 && a3 )
  {
    v5 = *((_DWORD *)this + 2);
    if ( (*(_BYTE *)(v5 + 60) & 0x20) != 0 )
    {
      if ( (*(_BYTE *)(v5 + 60) & 0x10) != 0 )
      {
        ParameterInfo = CJetParameterList::GetParameterInfo((CJetParameterList *)(v5 + 84), a2, a3, a4);
        if ( ParameterInfo >= 0 )
          goto LABEL_20;
        v7 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
        v8 = *(_DWORD *)(v7 + 20);
        v9 = *(_DWORD *)(v7 + 16);
        if ( ParameterInfo == -2147024882 )
          goto LABEL_20;
        goto LABEL_18;
      }
      ParameterInfo = -2147217846;
    }
    else
    {
      ParameterInfo = -2147217908;
    }
  }
  else
  {
    ParameterInfo = -2147024809;
  }
  v10 = *(_DWORD *)(*((_DWORD *)this + 2) + 52);
  v8 = *(_DWORD *)(v10 + 20);
  v9 = *(_DWORD *)(v10 + 16);
LABEL_18:
  if ( !JetGetDatabaseInfo(v9, v8, v14, 4, 3) )
    CExtError::SendHRtoOLEAuto(ParameterInfo, (__int128 *)&IID_ICommandWithParameters, 0, v12, v13);
LABEL_20:
  if ( v4 )
    LeaveCriticalSection(v4);
  return ParameterInfo;
}

```

## disassembly

```asm
0x10011130  mov     edi, edi
0x10011132  push    ebp
0x10011133  mov     ebp, esp
0x10011135  push    0FFFFFFFFh
0x10011137  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1001113c  mov     eax, large fs:0
0x10011142  push    eax
0x10011143  sub     esp, 8
0x10011146  push    ebx
0x10011147  push    esi
0x10011148  push    edi; int
0x10011149  mov     eax, ___security_cookie
0x1001114e  xor     eax, ebp
0x10011150  push    eax; struct _GUID *
0x10011151  lea     eax, [ebp+var_C]
0x10011154  mov     large fs:0, eax
0x1001115a  push    0; perrinfo
0x1001115c  push    0; dwReserved
0x1001115e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10011164  mov     ebx, [ebp+this]
0x10011167  mov     esi, [ebx+8]
0x1001116a  add     esi, 0F8h
0x10011170  push    esi; lpCriticalSection
0x10011171  mov     [ebp+var_10], esi
0x10011174  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001117a  mov     [ebp+var_4], 0
0x10011181  mov     ecx, [ebx+8]
0x10011184  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x10011189  mov     ecx, [ebp+arg_4]
0x1001118c  test    ecx, ecx
0x1001118e  jz      short loc_10011196
0x10011190  mov     dword ptr [ecx], 0
0x10011196  mov     eax, [ebp+arg_8]
0x10011199  test    eax, eax
0x1001119b  jz      short loc_100111A3
0x1001119d  mov     dword ptr [eax], 0
0x100111a3  mov     edx, [ebp+arg_C]
0x100111a6  test    edx, edx
0x100111a8  jz      short loc_100111B0
0x100111aa  mov     dword ptr [edx], 0
0x100111b0  test    ecx, ecx
0x100111b2  jz      short loc_100111FE
0x100111b4  test    eax, eax
0x100111b6  jz      short loc_100111FE
0x100111b8  mov     edi, [ebx+8]
0x100111bb  test    byte ptr [edi+3Ch], 20h
0x100111bf  jnz     short loc_100111C8
0x100111c1  mov     edi, 80040E0Ch
0x100111c6  jmp     short loc_10011203
0x100111c8  test    byte ptr [edi+3Ch], 10h
0x100111cc  jnz     short loc_100111D5
0x100111ce  mov     edi, 80040E4Ah
0x100111d3  jmp     short loc_10011203
0x100111d5  push    edx; unsigned __int16 **
0x100111d6  push    eax; struct tagDBPARAMINFO **
0x100111d7  push    ecx; unsigned int *
0x100111d8  lea     ecx, [edi+54h]; this
0x100111db  call    ?GetParameterInfo@CJetParameterList@@QAEJPAKPAPAUtagDBPARAMINFO@@PAPAG@Z; CJetParameterList::GetParameterInfo(ulong *,tagDBPARAMINFO * *,ushort * *)
0x100111e0  mov     edi, eax
0x100111e2  mov     edx, edi
0x100111e4  test    edi, edi
0x100111e6  jns     short loc_10011230
0x100111e8  mov     eax, [ebx+8]
0x100111eb  mov     eax, [eax+34h]
0x100111ee  mov     ecx, [eax+14h]
0x100111f1  mov     eax, [eax+10h]
0x100111f4  cmp     edx, 8007000Eh
0x100111fa  jz      short loc_10011230
0x100111fc  jmp     short loc_1001120F
0x100111fe  mov     edi, 80070057h
0x10011203  mov     eax, [ebx+8]
0x10011206  mov     eax, [eax+34h]
0x10011209  mov     ecx, [eax+14h]
0x1001120c  mov     eax, [eax+10h]
0x1001120f  push    3
0x10011211  push    4
0x10011213  lea     edx, [ebp+var_14]
0x10011216  push    edx
0x10011217  push    ecx
0x10011218  push    eax
0x10011219  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x1001121f  test    eax, eax
0x10011221  jnz     short loc_10011230
0x10011223  push    eax; int
0x10011224  push    offset _IID_ICommandWithParameters; int
0x10011229  mov     edx, edi
0x1001122b  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10011230  test    esi, esi
0x10011232  jz      short loc_1001123B
0x10011234  push    esi; lpCriticalSection
0x10011235  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001123b  mov     eax, edi
0x1001123d  mov     ecx, [ebp+var_C]
0x10011240  mov     large fs:0, ecx
0x10011247  pop     ecx
0x10011248  pop     edi
0x10011249  pop     esi
0x1001124a  pop     ebx
0x1001124b  mov     esp, ebp
0x1001124d  pop     ebp
0x1001124e  retn    10h
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
