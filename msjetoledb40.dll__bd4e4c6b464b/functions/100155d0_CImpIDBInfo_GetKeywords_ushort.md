# CImpIDBInfo::GetKeywords(ushort * *)

- ea: `0x100155d0`
- end: `0x100156a5`
- name: `?GetKeywords@CImpIDBInfo@@UAGJPAPAG@Z`
- size: `213`
- prototype: `int(CImpIDBInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000d4a0`
- `0x100155d0`
- `0x1001c380`
- `0x1001c6d0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10015689`
- `KERNEL32!LeaveCriticalSection` at `0x10015689`
- `KERNEL32!EnterCriticalSection` at `0x1001560f`
- `KERNEL32!EnterCriticalSection` at `0x1001560f`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100155fc`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100155fc`

## string_xrefs

- `0x10015665`: `AdminDB,Alphanumeric,Autoincrement,BAND,Binary,BNOT,BOR,BXOR,Byte,Comp,Compression,Container,Counter,CreateDB,Currency,Database,DateTime,Disallow,ExclusiveConnect,Float4,Float8,General,Guid,IEEEDouble,IEEESingle,Ignore,Image,Index,Inheritable,Integer1,Integer2,Integer4,Logical,Logical1,Long,LongBinary,LongChar,LongText,Memo,Money,Note,Number,Object,OLEObject,OwnerAccess,Pad,Parameters,Password,Percent,Pivot,Proc,SelectSchema,SelectSecurity,Short,Single,Space,String,Tableid,Text,Top,Transform,Uni`

## pseudocode

```c
int __stdcall CImpIDBInfo::GetKeywords(CImpIDBInfo *this, unsigned __int16 **a2)
{
  int v2; // ebx
  struct _RTL_CRITICAL_SECTION *v3; // esi
  unsigned __int16 *v4; // ecx
  const struct _GUID *v6; // [esp+0h] [ebp-20h]
  unsigned int v7; // [esp+4h] [ebp-1Ch]

  v2 = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  if ( !a2 )
  {
    v2 = -2147024809;
    goto LABEL_8;
  }
  *a2 = 0;
  if ( !*(_DWORD *)(*((_DWORD *)this + 2) + 128) )
  {
    v2 = -2147418113;
LABEL_8:
    CExtError::SendHRtoOLEAuto(v2, (__int128 *)&IID_IDBInfo, 0, v6, v7);
    goto LABEL_9;
  }
  v4 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                             *(_DWORD *)(*(_DWORD *)Sys + 12),
                             Sys,
                             1144);
  *a2 = v4;
  if ( v4 )
    WCSCPY(
      L"AdminDB,Alphanumeric,Autoincrement,BAND,Binary,BNOT,BOR,BXOR,Byte,Comp,Compression,Container,Counter,CreateDB,Curr"
       "ency,Database,DateTime,Disallow,ExclusiveConnect,Float4,Float8,General,Guid,IEEEDouble,IEEESingle,Ignore,Image,In"
       "dex,Inheritable,Integer1,Integer2,Integer4,Logical,Logical1,Long,LongBinary,LongChar,LongText,Memo,Money,Note,Num"
       "ber,Object,OLEObject,OwnerAccess,Pad,Parameters,Password,Percent,Pivot,Proc,SelectSchema,SelectSecurity,Short,Sin"
       "gle,Space,String,Tableid,Text,Top,Transform,Uniqueidentifier,UpdateIdentity,UpdateOwner,UpdateSecurity,Varbinary,YesNo",
      v4,
      (unsigned __int16 *)0x478,
      (const unsigned __int16 *)v6,
      v7);
  else
    v2 = -2147024882;
LABEL_9:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v2;
}

```

## disassembly

```asm
0x100155d0  mov     edi, edi
0x100155d2  push    ebp
0x100155d3  mov     ebp, esp
0x100155d5  push    0FFFFFFFFh
0x100155d7  push    offset ?Unadvise@CRowsetConnectionPoint@@UAGJK@Z_SEH
0x100155dc  mov     eax, large fs:0
0x100155e2  push    eax
0x100155e3  push    ecx
0x100155e4  push    ebx
0x100155e5  push    esi
0x100155e6  push    edi; int
0x100155e7  mov     eax, ___security_cookie
0x100155ec  xor     eax, ebp
0x100155ee  push    eax; struct _GUID *
0x100155ef  lea     eax, [ebp+var_C]
0x100155f2  mov     large fs:0, eax
0x100155f8  xor     ebx, ebx
0x100155fa  push    ebx; perrinfo
0x100155fb  push    ebx; dwReserved
0x100155fc  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10015602  mov     edi, [ebp+this]
0x10015605  mov     esi, [edi+8]
0x10015608  add     esi, 64h ; 'd'
0x1001560b  push    esi; lpCriticalSection
0x1001560c  mov     [ebp+var_10], esi
0x1001560f  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10015615  mov     eax, [ebp+arg_4]
0x10015618  mov     [ebp+var_4], ebx
0x1001561b  test    eax, eax
0x1001561d  jz      short loc_10015671
0x1001561f  mov     [eax], ebx
0x10015621  mov     eax, [edi+8]
0x10015624  cmp     [eax+80h], ebx
0x1001562a  jnz     short loc_10015633
0x1001562c  mov     ebx, 8000FFFFh
0x10015631  jmp     short loc_10015676
0x10015633  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x10015639  push    478h
0x1001563e  push    ecx
0x1001563f  mov     eax, [ecx]
0x10015641  mov     edi, [eax+0Ch]
0x10015644  mov     ecx, edi
0x10015646  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001564c  call    edi
0x1001564e  mov     ecx, eax
0x10015650  mov     eax, [ebp+arg_4]
0x10015653  mov     [eax], ecx
0x10015655  test    ecx, ecx
0x10015657  jnz     short loc_10015660
0x10015659  mov     ebx, 8007000Eh
0x1001565e  jmp     short loc_10015684
0x10015660  push    478h; unsigned __int16 *
0x10015665  mov     edx, offset aAdmindbAlphanu; "AdminDB,Alphanumeric,Autoincrement,BAND"...
0x1001566a  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x1001566f  jmp     short loc_10015684
0x10015671  mov     ebx, 80070057h
0x10015676  push    0; int
0x10015678  push    offset _IID_IDBInfo; int
0x1001567d  mov     edx, ebx
0x1001567f  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10015684  test    esi, esi
0x10015686  jz      short loc_1001568F
0x10015688  push    esi; lpCriticalSection
0x10015689  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001568f  mov     eax, ebx
0x10015691  mov     ecx, [ebp+var_C]
0x10015694  mov     large fs:0, ecx
0x1001569b  pop     ecx
0x1001569c  pop     edi
0x1001569d  pop     esi
0x1001569e  pop     ebx
0x1001569f  mov     esp, ebp
0x100156a1  pop     ebp
0x100156a2  retn    8
0x1004dea0  lea     ecx, [ebp+var_10]; this
0x1004dea3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dead  nop
0x1004deae  nop
0x1004deaf  mov     edx, [esp-4+arg_4]
0x1004deb3  lea     eax, [edx+0Ch]
0x1004deb6  mov     ecx, [edx-14h]
0x1004deb9  xor     ecx, eax; StackCookie
0x1004debb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dec0  mov     eax, offset stru_1004F464
0x1004dec5  jmp     ___CxxFrameHandler3
```
