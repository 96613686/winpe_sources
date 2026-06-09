# CImpIReplication::MoveDesignMaster(tagVARIANT)

- ea: `0x10027660`
- end: `0x10027855`
- name: `?MoveDesignMaster@CImpIReplication@@UAGJUtagVARIANT@@@Z`
- size: `501`
- prototype: `int(CImpIReplication *__hidden this, struct tagVARIANT)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1000ba90`
- `0x1001bdc0`
- `0x1001c380`
- `0x1001c6d0`
- `0x10027660`
- `0x10027860`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1002782f`
- `KERNEL32!LeaveCriticalSection` at `0x1002782f`
- `KERNEL32!EnterCriticalSection` at `0x100276b1`
- `KERNEL32!EnterCriticalSection` at `0x100276b1`
- `OLEAUT32!__imp__SysStringByteLen@4` at `0x100276ff`
- `OLEAUT32!__imp__SysStringByteLen@4` at `0x100276ff`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100276a1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100276a1`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10027813`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10027813`

## pseudocode

```c
int __stdcall CImpIReplication::MoveDesignMaster(CImpIReplication *this, struct tagVARIANT a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // esi
  BSTR v3; // ebx
  int v4; // ebx
  int v5; // eax
  CReplCover *v6; // edi
  int v7; // eax
  OLECHAR *v8; // ecx
  int v9; // eax
  signed int v10; // eax
  const struct _GUID *v12; // [esp+0h] [ebp-48h]
  const struct _GUID *v13; // [esp+4h] [ebp-44h]
  int v14; // [esp+14h] [ebp-34h] BYREF
  UINT v15; // [esp+18h] [ebp-30h] BYREF
  int v16; // [esp+1Ch] [ebp-2Ch] BYREF
  CImpIReplication *v17; // [esp+20h] [ebp-28h]
  BSTR bstr; // [esp+24h] [ebp-24h] BYREF
  _BYTE v19[16]; // [esp+28h] [ebp-20h] BYREF
  int v20; // [esp+44h] [ebp-4h]

  v17 = this;
  bstr = a2.bstrVal;
  SetErrorInfo(0, 0);
  v2 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v2);
  v20 = 0;
  if ( !a2.vt || a2.vt == 1 || (v14 = 0, v15 = 0, v16 = 16, a2.vt != 8) || (v3 = bstr) == 0 )
  {
    v5 = *((_DWORD *)this + 2);
    v4 = -2147024809;
LABEL_16:
    if ( !JetGetDatabaseInfo(*(_DWORD *)(v5 + 16), *(_DWORD *)(v5 + 20), &bstr, 4, 3) )
      CExtError::SendHRtoOLEAuto(v4, (__int128 *)&IID_IReplication, 0, v12, (int)v13);
    goto LABEL_18;
  }
  v15 = SysStringByteLen(bstr);
  if ( (*(int (__thiscall **)(_DWORD, LPVOID, int, int, UINT *, int *, BSTR))(*(_DWORD *)g_pIDataConvert + 20))(
         *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 20),
         g_pIDataConvert,
         130,
         72,
         &v15,
         &v16,
         bstr) < 0 )
  {
    v4 = -2147217887;
    v5 = *((_DWORD *)v17 + 2);
    goto LABEL_16;
  }
  v4 = (*(int (__thiscall **)(_DWORD, LPVOID, int, int, UINT, BSTR *, BSTR, _BYTE *, int, int, int *, _DWORD, _DWORD, _DWORD))(*(_DWORD *)g_pIDataConvert + 12))(
         *(_DWORD *)(*(_DWORD *)g_pIDataConvert + 12),
         g_pIDataConvert,
         130,
         72,
         v15,
         &bstr,
         v3,
         v19,
         v16,
         v14,
         &v14,
         0,
         0,
         0);
  if ( v4 < 0 )
  {
    v4 = -2147217887;
    v5 = *((_DWORD *)v17 + 2);
    goto LABEL_16;
  }
  v6 = (CReplCover *)*((_DWORD *)v17 + 4);
  v7 = *((_DWORD *)v17 + 2);
  v8 = *(OLECHAR **)(v7 + 20);
  v9 = *(_DWORD *)(v7 + 16);
  bstr = v8;
  v16 = v9;
  if ( CReplCover::Initialize(v6) >= 0 )
  {
    v10 = (*(int (__thiscall **)(_DWORD, int, BSTR, _BYTE *))(*((_DWORD *)v6 + 2) + 44))(
            *(_DWORD *)(*((_DWORD *)v6 + 2) + 44),
            v16,
            bstr,
            v19);
    if ( v10 >= 0 )
    {
      if ( !v10 )
        goto LABEL_18;
    }
    else
    {
      v4 = -2147467259;
    }
  }
  else
  {
    v10 = -1029;
    v4 = -2147467259;
  }
  CExtError::SendJetErrortoOLEAuto(
    v4,
    *(char **)(*((_DWORD *)v17 + 2) + 16),
    v10,
    (int)&IID_IReplication,
    (int)v12,
    v13);
LABEL_18:
  if ( v2 )
    LeaveCriticalSection(v2);
  return v4;
}

```

## disassembly

```asm
0x10027660  mov     edi, edi
0x10027662  push    ebp
0x10027663  mov     ebp, esp
0x10027665  push    0FFFFFFFFh
0x10027667  push    offset ?MoveDesignMaster@CImpIReplication@@UAGJUtagVARIANT@@@Z_SEH
0x1002766c  mov     eax, large fs:0
0x10027672  push    eax
0x10027673  sub     esp, 2Ch
0x10027676  mov     eax, ___security_cookie
0x1002767b  xor     eax, ebp
0x1002767d  mov     [ebp+var_10], eax
0x10027680  push    ebx
0x10027681  push    esi
0x10027682  push    edi; int
0x10027683  push    eax; struct _GUID *
0x10027684  lea     eax, [ebp+var_C]
0x10027687  mov     large fs:0, eax
0x1002768d  mov     eax, dword ptr [ebp+arg_4+8]
0x10027690  mov     edi, [ebp+this]
0x10027693  movzx   ebx, word ptr [ebp+arg_4]
0x10027697  push    0; perrinfo
0x10027699  push    0; dwReserved
0x1002769b  mov     [ebp+var_28], edi
0x1002769e  mov     [ebp+bstr], eax
0x100276a1  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100276a7  mov     esi, [edi+8]
0x100276aa  add     esi, 68h ; 'h'
0x100276ad  push    esi; lpCriticalSection
0x100276ae  mov     [ebp+var_38], esi
0x100276b1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100276b7  mov     [ebp+var_4], 0
0x100276be  test    bx, bx
0x100276c1  jz      loc_100277FB
0x100276c7  cmp     ebx, 1
0x100276ca  jz      loc_100277FB
0x100276d0  mov     eax, 8
0x100276d5  mov     [ebp+var_34], 0
0x100276dc  mov     [ebp+var_30], 0
0x100276e3  mov     [ebp+var_2C], 10h
0x100276ea  cmp     ax, bx
0x100276ed  jnz     loc_100277FB
0x100276f3  mov     ebx, [ebp+bstr]
0x100276f6  test    ebx, ebx
0x100276f8  jz      loc_100277FB
0x100276fe  push    ebx; bstr
0x100276ff  call    ds:__imp__SysStringByteLen@4; SysStringByteLen(x)
0x10027705  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x1002770b  mov     [ebp+var_30], eax
0x1002770e  push    ebx
0x1002770f  mov     eax, [ecx]
0x10027711  mov     edi, [eax+14h]
0x10027714  lea     eax, [ebp+var_2C]
0x10027717  push    eax
0x10027718  lea     eax, [ebp+var_30]
0x1002771b  push    eax
0x1002771c  push    48h ; 'H'
0x1002771e  push    82h
0x10027723  push    ecx
0x10027724  mov     ecx, edi
0x10027726  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002772c  call    edi
0x1002772e  test    eax, eax
0x10027730  jns     short loc_10027742
0x10027732  mov     ecx, [ebp+var_28]
0x10027735  mov     ebx, 80040E21h
0x1002773a  mov     eax, [ecx+8]
0x1002773d  jmp     loc_10027803
0x10027742  mov     ecx, ?g_pIDataConvert@@3PAUIDataConvert@@A; IDataConvert * g_pIDataConvert
0x10027748  push    0
0x1002774a  push    0
0x1002774c  push    0
0x1002774e  mov     eax, [ecx]
0x10027750  mov     edi, [eax+0Ch]
0x10027753  lea     eax, [ebp+var_34]
0x10027756  push    eax
0x10027757  push    [ebp+var_34]
0x1002775a  lea     eax, [ebp+var_20]
0x1002775d  push    [ebp+var_2C]
0x10027760  push    eax
0x10027761  push    ebx
0x10027762  lea     eax, [ebp+bstr]
0x10027765  push    eax
0x10027766  push    [ebp+var_30]
0x10027769  push    48h ; 'H'
0x1002776b  push    82h
0x10027770  push    ecx
0x10027771  mov     ecx, edi
0x10027773  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10027779  call    edi
0x1002777b  mov     ebx, eax
0x1002777d  test    ebx, ebx
0x1002777f  jns     short loc_1002778E
0x10027781  mov     ecx, [ebp+var_28]
0x10027784  mov     ebx, 80040E21h
0x10027789  mov     eax, [ecx+8]
0x1002778c  jmp     short loc_10027803
0x1002778e  mov     eax, [ebp+var_28]
0x10027791  mov     edi, [eax+10h]
0x10027794  mov     eax, [eax+8]
0x10027797  mov     ecx, [eax+14h]
0x1002779a  mov     eax, [eax+10h]
0x1002779d  mov     [ebp+bstr], ecx
0x100277a0  mov     ecx, edi; this
0x100277a2  mov     [ebp+var_2C], eax
0x100277a5  call    ?Initialize@CReplCover@@QAEJXZ; CReplCover::Initialize(void)
0x100277aa  test    eax, eax
0x100277ac  jns     short loc_100277BA
0x100277ae  mov     eax, 0FFFFFBFBh
0x100277b3  mov     ebx, 80004005h
0x100277b8  jmp     short loc_100277E3
0x100277ba  mov     eax, [edi+8]
0x100277bd  mov     edi, [eax+2Ch]
0x100277c0  lea     eax, [ebp+var_20]
0x100277c3  push    eax
0x100277c4  push    [ebp+bstr]
0x100277c7  mov     ecx, edi
0x100277c9  push    [ebp+var_2C]
0x100277cc  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100277d2  call    edi
0x100277d4  mov     ecx, eax
0x100277d6  test    ecx, ecx
0x100277d8  jns     short loc_100277E1
0x100277da  mov     ebx, 80004005h
0x100277df  jmp     short loc_100277E3
0x100277e1  jz      short loc_1002782A
0x100277e3  mov     ecx, [ebp+var_28]
0x100277e6  mov     edx, ebx
0x100277e8  push    offset _IID_IReplication; int
0x100277ed  push    eax; unsigned int
0x100277ee  mov     ecx, [ecx+8]
0x100277f1  mov     ecx, [ecx+10h]
0x100277f4  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x100277f9  jmp     short loc_1002782A
0x100277fb  mov     eax, [edi+8]
0x100277fe  mov     ebx, 80070057h
0x10027803  mov     ecx, [eax+14h]
0x10027806  lea     edx, [ebp+bstr]
0x10027809  mov     eax, [eax+10h]
0x1002780c  push    3
0x1002780e  push    4
0x10027810  push    edx
0x10027811  push    ecx
0x10027812  push    eax
0x10027813  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10027819  test    eax, eax
0x1002781b  jnz     short loc_1002782A
0x1002781d  push    eax; int
0x1002781e  push    offset _IID_IReplication; int
0x10027823  mov     edx, ebx
0x10027825  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x1002782a  test    esi, esi
0x1002782c  jz      short loc_10027835
0x1002782e  push    esi; lpCriticalSection
0x1002782f  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10027835  mov     eax, ebx
0x10027837  mov     ecx, [ebp+var_C]
0x1002783a  mov     large fs:0, ecx
0x10027841  pop     ecx
0x10027842  pop     edi
0x10027843  pop     esi
0x10027844  pop     ebx
0x10027845  mov     ecx, [ebp+var_10]
0x10027848  xor     ecx, ebp; StackCookie
0x1002784a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002784f  mov     esp, ebp
0x10027851  pop     ebp
0x10027852  retn    14h
0x1004ea30  lea     ecx, [ebp+var_38]; this
0x1004ea33  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004ea3d  nop
0x1004ea3e  nop
0x1004ea3f  mov     edx, dword ptr [esp-4+arg_4]
0x1004ea43  lea     eax, [edx+0Ch]
0x1004ea46  mov     ecx, [edx-3Ch]
0x1004ea49  xor     ecx, eax; StackCookie
0x1004ea4b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ea50  mov     ecx, [edx-4]
0x1004ea53  xor     ecx, eax; StackCookie
0x1004ea55  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004ea5a  mov     eax, offset stru_1004FD10
0x1004ea5f  jmp     ___CxxFrameHandler3
```
