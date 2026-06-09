# CImpISecurityInfo::GetPermissions(_GUID,ulong *)

- ea: `0x10043730`
- end: `0x10043804`
- name: `?GetPermissions@CImpISecurityInfo@@UAGJU_GUID@@PAK@Z`
- size: `212`
- prototype: `int(CImpISecurityInfo *__hidden this, struct _GUID, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x10043730`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x100437e8`
- `KERNEL32!LeaveCriticalSection` at `0x100437e8`
- `KERNEL32!EnterCriticalSection` at `0x10043771`
- `KERNEL32!EnterCriticalSection` at `0x10043771`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004375e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1004375e`

## pseudocode

```c
int __stdcall CImpISecurityInfo::GetPermissions(CImpISecurityInfo *this, struct _GUID a2, unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // ebx
  unsigned int i; // ebx
  unsigned int v6; // edi
  _DWORD *v7; // edx
  struct _GUID *v8; // eax
  bool v9; // cf
  const struct _GUID *v11; // [esp+0h] [ebp-24h]
  int v12; // [esp+4h] [ebp-20h]
  int v13; // [esp+14h] [ebp-10h]

  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  if ( a3 )
  {
    for ( i = 0; i < 9; ++i )
    {
      v6 = 12;
      v13 = 3 * i;
      v7 = (_DWORD *)*((_DWORD *)&rgSecObjectMap + 3 * i);
      v8 = &a2;
      while ( *v7 == v8->Data1 )
      {
        ++v7;
        v8 = (struct _GUID *)((char *)v8 + 4);
        v9 = v6 < 4;
        v6 -= 4;
        if ( v9 )
        {
          v4 = 0;
          *a3 = dword_10003788[v13];
          goto LABEL_11;
        }
      }
    }
    v4 = -2147217811;
  }
  else
  {
    v4 = -2147024809;
  }
  CExtError::SendHRtoOLEAuto(v4, (__int128 *)&IID_ISecurityInfo, 0, v11, v12);
LABEL_11:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v4;
}

```

## disassembly

```asm
0x10043730  mov     edi, edi
0x10043732  push    ebp
0x10043733  mov     ebp, esp
0x10043735  push    0FFFFFFFFh
0x10043737  push    offset ?Abort@CImpITransactionLocal@@UAGJPAUBOID@@HH@Z_SEH
0x1004373c  mov     eax, large fs:0
0x10043742  push    eax
0x10043743  sub     esp, 8
0x10043746  push    ebx
0x10043747  push    esi
0x10043748  push    edi; int
0x10043749  mov     eax, ___security_cookie
0x1004374e  xor     eax, ebp
0x10043750  push    eax; struct _GUID *
0x10043751  lea     eax, [ebp+var_C]
0x10043754  mov     large fs:0, eax
0x1004375a  push    0; perrinfo
0x1004375c  push    0; dwReserved
0x1004375e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10043764  mov     esi, [ebp+this]
0x10043767  mov     esi, [esi+8]
0x1004376a  add     esi, 64h ; 'd'
0x1004376d  push    esi; lpCriticalSection
0x1004376e  mov     [ebp+var_14], esi
0x10043771  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10043777  cmp     [ebp+arg_14], 0
0x1004377b  mov     [ebp+var_4], 0
0x10043782  jnz     short loc_1004378B
0x10043784  mov     ebx, 80070057h
0x10043789  jmp     short loc_100437D5
0x1004378b  xor     ebx, ebx
0x1004378d  nop     dword ptr [eax]
0x10043790  lea     eax, [ebx+ebx*2]
0x10043793  mov     edi, 0Ch
0x10043798  shl     eax, 2
0x1004379b  mov     [ebp+var_10], eax
0x1004379e  mov     edx, ds:?rgSecObjectMap@@3QBUjetsecobjectmap@@B[eax]; jetsecobjectmap const * const rgSecObjectMap
0x100437a4  lea     eax, [ebp+arg_4]
0x100437a7  mov     ecx, [edx]
0x100437a9  cmp     ecx, [eax]
0x100437ab  jnz     short loc_100437CA
0x100437ad  add     edx, 4
0x100437b0  add     eax, 4
0x100437b3  sub     edi, 4
0x100437b6  jnb     short loc_100437A7
0x100437b8  mov     eax, [ebp+var_10]
0x100437bb  xor     ebx, ebx
0x100437bd  mov     ecx, [ebp+arg_14]
0x100437c0  mov     eax, ds:dword_10003788[eax]
0x100437c6  mov     [ecx], eax
0x100437c8  jmp     short loc_100437E3
0x100437ca  inc     ebx
0x100437cb  cmp     ebx, 9
0x100437ce  jb      short loc_10043790
0x100437d0  mov     ebx, 80040E6Dh
0x100437d5  push    0; int
0x100437d7  push    offset _IID_ISecurityInfo; int
0x100437dc  mov     edx, ebx
0x100437de  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100437e3  test    esi, esi
0x100437e5  jz      short loc_100437EE
0x100437e7  push    esi; lpCriticalSection
0x100437e8  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100437ee  mov     eax, ebx
0x100437f0  mov     ecx, [ebp+var_C]
0x100437f3  mov     large fs:0, ecx
0x100437fa  pop     ecx
0x100437fb  pop     edi
0x100437fc  pop     esi
0x100437fd  pop     ebx
0x100437fe  mov     esp, ebp
0x10043800  pop     ebp
0x10043801  retn    18h
0x1004dde0  lea     ecx, [ebp+var_14]; this
0x1004dde3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dded  nop
0x1004ddee  nop
0x1004ddef  mov     edx, [esp-4+arg_4]
0x1004ddf3  lea     eax, [edx+0Ch]
0x1004ddf6  mov     ecx, [edx-18h]
0x1004ddf9  xor     ecx, eax; StackCookie
0x1004ddfb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004de00  mov     eax, offset stru_1004F3D8
0x1004de05  jmp     ___CxxFrameHandler3
```
