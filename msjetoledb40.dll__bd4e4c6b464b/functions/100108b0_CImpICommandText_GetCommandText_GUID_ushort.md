# CImpICommandText::GetCommandText(_GUID *,ushort * *)

- ea: `0x100108b0`
- end: `0x100109cd`
- name: `?GetCommandText@CImpICommandText@@UAGJPAU_GUID@@PAPAG@Z`
- size: `285`
- prototype: `int(CImpICommandText *__hidden this, struct _GUID *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x100108b0`
- `0x100147f0`
- `0x100255a0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10010969`
- `KERNEL32!LeaveCriticalSection` at `0x10010969`
- `KERNEL32!EnterCriticalSection` at `0x100108f1`
- `KERNEL32!EnterCriticalSection` at `0x100108f1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100108db`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100108db`

## pseudocode

```c
int __stdcall CImpICommandText::GetCommandText(CImpICommandText *this, struct _GUID *a2, unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // edi
  int v5; // ecx
  int String; // eax
  const GUID *v7; // ecx
  struct _GUID *v8; // edx
  unsigned int v9; // edi
  bool v10; // cf
  struct _GUID *v12; // edx
  const GUID *v13; // ecx
  unsigned int v14; // edi

  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
  EnterCriticalSection(v3);
  CCommand::CheckForZombieCommandAndFix(*((_DWORD *)this + 2));
  if ( !a3 )
  {
    v4 = -2147024809;
    goto LABEL_20;
  }
  v5 = *((_DWORD *)this + 2);
  if ( (*(_BYTE *)(v5 + 60) & 0x20) == 0 )
  {
    v4 = -2147217908;
    goto LABEL_20;
  }
  String = CopyAndAllocateString(*(unsigned __int16 **)(v5 + 108), a3);
  if ( String < 0 )
  {
    v4 = String;
LABEL_20:
    if ( a2 )
      *a2 = (struct _GUID)xmmword_100046A4;
    goto LABEL_11;
  }
  if ( a2 )
  {
    v7 = &DBGUID_SQL;
    v8 = a2;
    v9 = 12;
    while ( v7->Data1 == v8->Data1 )
    {
      v7 = (const GUID *)((char *)v7 + 4);
      v8 = (struct _GUID *)((char *)v8 + 4);
      v10 = v9 < 4;
      v9 -= 4;
      if ( v10 )
        goto LABEL_10;
    }
    v12 = a2;
    v13 = &DBGUID_DBSQL;
    v14 = 12;
    while ( v13->Data1 == v12->Data1 )
    {
      v13 = (const GUID *)((char *)v13 + 4);
      v12 = (struct _GUID *)((char *)v12 + 4);
      v10 = v14 < 4;
      v14 -= 4;
      if ( v10 )
        goto LABEL_10;
    }
    v4 = 265933;
    *a2 = DBGUID_DBSQL;
  }
  else
  {
LABEL_10:
    v4 = String;
  }
LABEL_11:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v4;
}

```

## disassembly

```asm
0x100108b0  mov     edi, edi
0x100108b2  push    ebp
0x100108b3  mov     ebp, esp
0x100108b5  push    0FFFFFFFFh
0x100108b7  push    offset ?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x100108bc  mov     eax, large fs:0
0x100108c2  push    eax
0x100108c3  push    ecx
0x100108c4  push    esi
0x100108c5  push    edi; unsigned __int16 **
0x100108c6  mov     eax, ___security_cookie
0x100108cb  xor     eax, ebp
0x100108cd  push    eax; unsigned __int16 *
0x100108ce  lea     eax, [ebp+var_C]
0x100108d1  mov     large fs:0, eax
0x100108d7  push    0; perrinfo
0x100108d9  push    0; dwReserved
0x100108db  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100108e1  mov     edi, [ebp+this]
0x100108e4  mov     esi, [edi+8]
0x100108e7  add     esi, 0F8h
0x100108ed  push    esi; lpCriticalSection
0x100108ee  mov     [ebp+var_10], esi
0x100108f1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100108f7  mov     [ebp+var_4], 0
0x100108fe  mov     ecx, [edi+8]
0x10010901  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x10010906  mov     edx, [ebp+arg_8]
0x10010909  test    edx, edx
0x1001090b  jnz     short loc_10010917
0x1001090d  mov     edi, 80070057h
0x10010912  jmp     loc_100109BA
0x10010917  mov     ecx, [edi+8]
0x1001091a  test    byte ptr [ecx+3Ch], 20h
0x1001091e  jnz     short loc_1001092A
0x10010920  mov     edi, 80040E0Ch
0x10010925  jmp     loc_100109BA
0x1001092a  mov     ecx, [ecx+6Ch]
0x1001092d  call    ?CopyAndAllocateString@@YGJPBGPAPAG@Z; CopyAndAllocateString(ushort const *,ushort * *)
0x10010932  mov     [ebp+var_10], eax
0x10010935  test    eax, eax
0x10010937  js      short loc_100109B8
0x10010939  mov     eax, [ebp+arg_4]
0x1001093c  test    eax, eax
0x1001093e  jz      short loc_10010961
0x10010940  mov     ecx, offset _DBGUID_SQL
0x10010945  mov     edx, eax
0x10010947  mov     edi, 0Ch
0x1001094c  nop     dword ptr [eax+00h]
0x10010950  mov     eax, [ecx]
0x10010952  cmp     eax, [edx]
0x10010954  jnz     short loc_10010984
0x10010956  add     ecx, 4
0x10010959  add     edx, 4
0x1001095c  sub     edi, 4
0x1001095f  jnb     short loc_10010950
0x10010961  mov     edi, [ebp+var_10]
0x10010964  test    esi, esi
0x10010966  jz      short loc_1001096F
0x10010968  push    esi; lpCriticalSection
0x10010969  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001096f  mov     eax, edi
0x10010971  mov     ecx, [ebp+var_C]
0x10010974  mov     large fs:0, ecx
0x1001097b  pop     ecx
0x1001097c  pop     edi
0x1001097d  pop     esi
0x1001097e  mov     esp, ebp
0x10010980  pop     ebp
0x10010981  retn    0Ch
0x10010984  mov     edx, [ebp+arg_4]
0x10010987  mov     ecx, offset _DBGUID_DBSQL
0x1001098c  mov     edi, 0Ch
0x10010991  mov     eax, [ecx]
0x10010993  cmp     eax, [edx]
0x10010995  jnz     short loc_100109A4
0x10010997  add     ecx, 4
0x1001099a  add     edx, 4
0x1001099d  sub     edi, 4
0x100109a0  jnb     short loc_10010991
0x100109a2  jmp     short loc_10010961
0x100109a4  mov     eax, [ebp+arg_4]
0x100109a7  mov     edi, 40ECDh
0x100109ac  movups  xmm0, xmmword ptr ds:_DBGUID_DBSQL.Data1
0x100109b3  movups  xmmword ptr [eax], xmm0
0x100109b6  jmp     short loc_10010964
0x100109b8  mov     edi, eax
0x100109ba  mov     eax, [ebp+arg_4]
0x100109bd  test    eax, eax
0x100109bf  jz      short loc_10010964
0x100109c1  movups  xmm0, ds:xmmword_100046A4
0x100109c8  movups  xmmword ptr [eax], xmm0
0x100109cb  jmp     short loc_10010964
0x1004df10  lea     ecx, [ebp+var_10]; this
0x1004df13  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004df1d  nop
0x1004df1e  nop
0x1004df1f  mov     edx, [esp-4+arg_4]
0x1004df23  lea     eax, [edx+0Ch]
0x1004df26  mov     ecx, [edx-10h]
0x1004df29  xor     ecx, eax; StackCookie
0x1004df2b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004df30  mov     eax, offset stru_1004F4C4
0x1004df35  jmp     ___CxxFrameHandler3
```
