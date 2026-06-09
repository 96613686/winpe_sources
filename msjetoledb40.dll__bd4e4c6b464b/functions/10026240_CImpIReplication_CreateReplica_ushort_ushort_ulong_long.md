# CImpIReplication::CreateReplica(ushort *,ushort *,ulong,long)

- ea: `0x10026240`
- end: `0x10026376`
- name: `?CreateReplica@CImpIReplication@@UAGJPAG0KJ@Z`
- size: `310`
- prototype: `int(CImpIReplication *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10026240`
- `0x10027860`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1002635a`
- `KERNEL32!LeaveCriticalSection` at `0x1002635a`
- `KERNEL32!EnterCriticalSection` at `0x10026290`
- `KERNEL32!EnterCriticalSection` at `0x10026290`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10026280`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10026280`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100262b4`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100262b4`

## pseudocode

```c
int __stdcall CImpIReplication::CreateReplica(
        CImpIReplication *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        int a5)
{
  int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  struct _RTL_CRITICAL_SECTION *v9; // esi
  CReplCover *v10; // edi
  signed int v11; // eax
  const struct _GUID *v13; // [esp+0h] [ebp-28h]
  const struct _GUID *v14; // [esp+4h] [ebp-24h]
  int v15; // [esp+14h] [ebp-14h] BYREF
  int v16; // [esp+18h] [ebp-10h]
  int v17; // [esp+24h] [ebp-4h]

  v5 = 0;
  v6 = *((_DWORD *)this + 2);
  v7 = *(_DWORD *)(v6 + 16);
  v8 = *(_DWORD *)(v6 + 20);
  v15 = v7;
  v16 = v8;
  SetErrorInfo(0, 0);
  v9 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v9);
  v17 = 0;
  if ( a2 )
  {
    v10 = (CReplCover *)*((_DWORD *)this + 4);
    if ( CReplCover::Initialize(v10) >= 0 )
    {
      v11 = (*(int (__thiscall **)(_DWORD, int, int, unsigned __int16 *, unsigned __int16 *, int, unsigned int))(*((_DWORD *)v10 + 2) + 16))(
              *(_DWORD *)(*((_DWORD *)v10 + 2) + 16),
              v15,
              v16,
              a2,
              a3,
              a5,
              a4);
      if ( !v11 )
        goto LABEL_14;
      if ( v11 > -1201 )
      {
        v5 = -2147467259;
        if ( v11 == -1011 )
          v5 = -2147024882;
      }
      else if ( v11 == -1201 )
      {
        v5 = -2147217897;
      }
      else
      {
        v5 = -2147467259;
      }
    }
    else
    {
      v11 = -1029;
      v5 = -2147467259;
    }
    CExtError::SendJetErrortoOLEAuto(
      v5,
      *(char **)(*((_DWORD *)this + 2) + 16),
      v11,
      (int)&IID_IReplication,
      (int)v13,
      v14);
  }
  else
  {
    v5 = -2147024809;
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*((_DWORD *)this + 2) + 16),
            *(_DWORD *)(*((_DWORD *)this + 2) + 20),
            &v15,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(-2147024809, (__int128 *)&IID_IReplication, 0, v13, (int)v14);
  }
LABEL_14:
  if ( v9 )
    LeaveCriticalSection(v9);
  return v5;
}

```

## disassembly

```asm
0x10026240  mov     edi, edi
0x10026242  push    ebp
0x10026243  mov     ebp, esp
0x10026245  push    0FFFFFFFFh
0x10026247  push    offset ?DropColumn@CImpITableDef@@UAGJPAUtagDBID@@0@Z_SEH
0x1002624c  mov     eax, large fs:0
0x10026252  push    eax
0x10026253  sub     esp, 0Ch
0x10026256  push    ebx
0x10026257  push    esi
0x10026258  push    edi; struct _GUID *
0x10026259  mov     eax, ___security_cookie
0x1002625e  xor     eax, ebp
0x10026260  push    eax; int
0x10026261  lea     eax, [ebp+var_C]
0x10026264  mov     large fs:0, eax
0x1002626a  mov     edi, [ebp+this]
0x1002626d  xor     ebx, ebx
0x1002626f  push    ebx; perrinfo
0x10026270  push    ebx; dwReserved
0x10026271  mov     eax, [edi+8]
0x10026274  mov     ecx, [eax+10h]
0x10026277  mov     eax, [eax+14h]
0x1002627a  mov     [ebp+var_14], ecx
0x1002627d  mov     [ebp+var_10], eax
0x10026280  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10026286  mov     esi, [edi+8]
0x10026289  add     esi, 68h ; 'h'
0x1002628c  push    esi; lpCriticalSection
0x1002628d  mov     [ebp+var_18], esi
0x10026290  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10026296  mov     [ebp+var_4], ebx
0x10026299  cmp     [ebp+arg_4], ebx
0x1002629c  jnz     short loc_100262D4
0x1002629e  mov     eax, [edi+8]
0x100262a1  lea     ecx, [ebp+var_14]
0x100262a4  push    3
0x100262a6  push    4
0x100262a8  push    ecx
0x100262a9  push    dword ptr [eax+14h]
0x100262ac  mov     ebx, 80070057h
0x100262b1  push    dword ptr [eax+10h]
0x100262b4  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100262ba  test    eax, eax
0x100262bc  jnz     loc_10026355
0x100262c2  push    eax; int
0x100262c3  push    offset _IID_IReplication; int
0x100262c8  mov     edx, ebx
0x100262ca  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100262cf  jmp     loc_10026355
0x100262d4  mov     edi, [edi+10h]
0x100262d7  mov     ecx, edi; this
0x100262d9  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x100262de  test    eax, eax
0x100262e0  jns     short loc_100262EE
0x100262e2  mov     eax, 0FFFFFBFBh
0x100262e7  mov     ebx, 80004005h
0x100262ec  jmp     short loc_1002633F
0x100262ee  push    [ebp+arg_C]
0x100262f1  mov     eax, [edi+8]
0x100262f4  push    [ebp+arg_10]
0x100262f7  push    [ebp+arg_8]
0x100262fa  mov     edi, [eax+10h]
0x100262fd  mov     ecx, edi
0x100262ff  push    [ebp+arg_4]
0x10026302  push    [ebp+var_10]
0x10026305  push    [ebp+var_14]
0x10026308  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002630e  call    edi
0x10026310  test    eax, eax
0x10026312  jz      short loc_10026355
0x10026314  mov     ecx, eax
0x10026316  cmp     eax, 0FFFFFB4Fh
0x1002631b  jg      short loc_1002632D
0x1002631d  jz      short loc_10026326
0x1002631f  mov     ebx, 80004005h
0x10026324  jmp     short loc_1002633F
0x10026326  mov     ebx, 80040E17h
0x1002632b  jmp     short loc_1002633F
0x1002632d  mov     ebx, 80004005h
0x10026332  cmp     ecx, 0FFFFFC0Dh
0x10026338  jnz     short loc_1002633F
0x1002633a  mov     ebx, 8007000Eh
0x1002633f  mov     ecx, [ebp+this]
0x10026342  mov     edx, ebx
0x10026344  push    offset _IID_IReplication; int
0x10026349  push    eax; unsigned int
0x1002634a  mov     ecx, [ecx+8]
0x1002634d  mov     ecx, [ecx+10h]
0x10026350  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x10026355  test    esi, esi
0x10026357  jz      short loc_10026360
0x10026359  push    esi; lpCriticalSection
0x1002635a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10026360  mov     eax, ebx
0x10026362  mov     ecx, [ebp+var_C]
0x10026365  mov     large fs:0, ecx
0x1002636c  pop     ecx
0x1002636d  pop     edi
0x1002636e  pop     esi
0x1002636f  pop     ebx
0x10026370  mov     esp, ebp
0x10026372  pop     ebp
0x10026373  retn    14h
0x1004dd50  lea     ecx, [ebp+var_18]; this
0x1004dd53  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd5d  nop
0x1004dd5e  nop
0x1004dd5f  mov     edx, [esp-4+arg_4]
0x1004dd63  lea     eax, [edx+0Ch]
0x1004dd66  mov     ecx, [edx-1Ch]
0x1004dd69  xor     ecx, eax; StackCookie
0x1004dd6b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd70  mov     eax, offset stru_1004F354
0x1004dd75  jmp     ___CxxFrameHandler3
```
