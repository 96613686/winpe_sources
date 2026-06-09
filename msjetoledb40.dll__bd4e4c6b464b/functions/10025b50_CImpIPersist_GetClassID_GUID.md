# CImpIPersist::GetClassID(_GUID *)

- ea: `0x10025b50`
- end: `0x10025bdc`
- name: `?GetClassID@CImpIPersist@@UAGJPAU_GUID@@@Z`
- size: `140`
- prototype: `int(CImpIPersist *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x10025b50`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10025bc1`
- `KERNEL32!LeaveCriticalSection` at `0x10025bc1`
- `KERNEL32!EnterCriticalSection` at `0x10025b8e`
- `KERNEL32!EnterCriticalSection` at `0x10025b8e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10025b7b`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10025b7b`

## pseudocode

```c
int __stdcall CImpIPersist::GetClassID(CImpIPersist *this, struct _GUID *a2)
{
  int v2; // edi
  struct _RTL_CRITICAL_SECTION *v3; // esi
  const struct _GUID *v5; // [esp+0h] [ebp-1Ch]
  int v6; // [esp+4h] [ebp-18h]

  v2 = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  if ( a2 )
  {
    *a2 = CLSID_JOLT;
  }
  else
  {
    v2 = -2147467259;
    CExtError::SendHRtoOLEAuto(-2147467259, (__int128 *)&IID_IPersist, 0, v5, v6);
  }
  if ( v3 )
    LeaveCriticalSection(v3);
  return v2;
}

```

## disassembly

```asm
0x10025b50  mov     edi, edi
0x10025b52  push    ebp
0x10025b53  mov     ebp, esp
0x10025b55  push    0FFFFFFFFh
0x10025b57  push    offset ?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x10025b5c  mov     eax, large fs:0
0x10025b62  push    eax
0x10025b63  push    ecx
0x10025b64  push    esi
0x10025b65  push    edi; int
0x10025b66  mov     eax, ___security_cookie
0x10025b6b  xor     eax, ebp
0x10025b6d  push    eax; struct _GUID *
0x10025b6e  lea     eax, [ebp+var_C]
0x10025b71  mov     large fs:0, eax
0x10025b77  xor     edi, edi
0x10025b79  push    edi; perrinfo
0x10025b7a  push    edi; dwReserved
0x10025b7b  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10025b81  mov     esi, [ebp+this]
0x10025b84  mov     esi, [esi+8]
0x10025b87  add     esi, 64h ; 'd'
0x10025b8a  push    esi; lpCriticalSection
0x10025b8b  mov     [ebp+var_10], esi
0x10025b8e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10025b94  mov     eax, [ebp+arg_4]
0x10025b97  mov     [ebp+var_4], edi
0x10025b9a  test    eax, eax
0x10025b9c  jnz     short loc_10025BB2
0x10025b9e  push    eax; int
0x10025b9f  mov     edi, 80004005h
0x10025ba4  push    offset _IID_IPersist; int
0x10025ba9  mov     edx, edi
0x10025bab  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10025bb0  jmp     short loc_10025BBC
0x10025bb2  movups  xmm0, xmmword ptr ds:?CLSID_JOLT@@3U_GUID@@B.Data1; _GUID const CLSID_JOLT ...
0x10025bb9  movups  xmmword ptr [eax], xmm0
0x10025bbc  test    esi, esi
0x10025bbe  jz      short loc_10025BC7
0x10025bc0  push    esi; lpCriticalSection
0x10025bc1  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10025bc7  mov     eax, edi
0x10025bc9  mov     ecx, [ebp+var_C]
0x10025bcc  mov     large fs:0, ecx
0x10025bd3  pop     ecx
0x10025bd4  pop     edi
0x10025bd5  pop     esi
0x10025bd6  mov     esp, ebp
0x10025bd8  pop     ebp
0x10025bd9  retn    8
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
