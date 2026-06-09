# CImpISecurityInfo::GetObjectTypes(ulong *,_GUID * *)

- ea: `0x100435c0`
- end: `0x10043724`
- name: `?GetObjectTypes@CImpISecurityInfo@@UAGJPAKPAPAU_GUID@@@Z`
- size: `356`
- prototype: `int(CImpISecurityInfo *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1001c380`
- `0x1001c6d0`
- `0x100435c0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10043709`
- `KERNEL32!LeaveCriticalSection` at `0x10043709`
- `KERNEL32!EnterCriticalSection` at `0x10043618`
- `KERNEL32!EnterCriticalSection` at `0x10043618`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10043605`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10043605`

## pseudocode

```c
int __stdcall CImpISecurityInfo::GetObjectTypes(CImpISecurityInfo *this, unsigned int *a2, struct _GUID **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  struct _GUID *v4; // eax
  int v5; // edi
  const struct _GUID *v7; // [esp+0h] [ebp-1Ch]
  int v8; // [esp+4h] [ebp-18h]

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 100);
  EnterCriticalSection(v3);
  if ( a3 && a2 )
  {
    v4 = (struct _GUID *)(*(int (__thiscall **)(_DWORD, int, int))(*(_DWORD *)Sys + 12))(
                           *(_DWORD *)(*(_DWORD *)Sys + 12),
                           Sys,
                           144);
    *a3 = v4;
    if ( v4 )
    {
      v5 = 0;
      *v4 = *(struct _GUID *)rgSecObjectMap;
      (*a3)[1] = DBOBJECT_VIEW;
      (*a3)[2] = DBOBJECT_PROCEDURE;
      (*a3)[3] = DBOBJECT_DATABASE;
      (*a3)[4] = DBOBJECT_COLUMN;
      (*a3)[5] = *(struct _GUID *)dword_10008D30;
      (*a3)[6] = *(struct _GUID *)dword_10008D10;
      (*a3)[7] = *(struct _GUID *)dword_10008D00;
      (*a3)[8] = *(struct _GUID *)dword_10008D20;
      *a2 = 9;
      goto LABEL_12;
    }
    v5 = -2147024882;
  }
  else
  {
    v5 = -2147024809;
  }
  CExtError::SendHRtoOLEAuto(v5, (__int128 *)&IID_ISecurityInfo, 0, v7, v8);
LABEL_12:
  if ( v3 )
    LeaveCriticalSection(v3);
  return v5;
}

```

## disassembly

```asm
0x100435c0  mov     edi, edi
0x100435c2  push    ebp
0x100435c3  mov     ebp, esp
0x100435c5  push    0FFFFFFFFh
0x100435c7  push    offset ?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x100435cc  mov     eax, large fs:0
0x100435d2  push    eax
0x100435d3  push    ecx
0x100435d4  push    esi
0x100435d5  push    edi; int
0x100435d6  mov     eax, ___security_cookie
0x100435db  xor     eax, ebp
0x100435dd  push    eax; struct _GUID *
0x100435de  lea     eax, [ebp+var_C]
0x100435e1  mov     large fs:0, eax
0x100435e7  mov     eax, [ebp+arg_4]
0x100435ea  test    eax, eax
0x100435ec  jz      short loc_100435F4
0x100435ee  mov     dword ptr [eax], 0
0x100435f4  mov     edi, [ebp+arg_8]
0x100435f7  test    edi, edi
0x100435f9  jz      short loc_10043601
0x100435fb  mov     dword ptr [edi], 0
0x10043601  push    0; perrinfo
0x10043603  push    0; dwReserved
0x10043605  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1004360b  mov     esi, [ebp+this]
0x1004360e  mov     esi, [esi+8]
0x10043611  add     esi, 64h ; 'd'
0x10043614  push    esi; lpCriticalSection
0x10043615  mov     [ebp+var_10], esi
0x10043618  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1004361e  mov     [ebp+var_4], 0
0x10043625  test    edi, edi
0x10043627  jz      loc_100436F1
0x1004362d  cmp     [ebp+arg_4], 0
0x10043631  jz      loc_100436F1
0x10043637  mov     eax, ?Sys@@3VSystem@@A; System Sys
0x1004363c  push    90h
0x10043641  push    eax
0x10043642  mov     ecx, [eax]
0x10043644  mov     edi, [ecx+0Ch]
0x10043647  mov     ecx, edi
0x10043649  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1004364f  call    edi
0x10043651  mov     edx, [ebp+arg_8]
0x10043654  mov     ecx, eax
0x10043656  mov     [edx], ecx
0x10043658  test    ecx, ecx
0x1004365a  jnz     short loc_10043666
0x1004365c  mov     edi, 8007000Eh
0x10043661  jmp     loc_100436F6
0x10043666  mov     eax, ds:?rgSecObjectMap@@3QBUjetsecobjectmap@@B; jetsecobjectmap const * const rgSecObjectMap
0x1004366b  xor     edi, edi
0x1004366d  movups  xmm0, xmmword ptr [eax]
0x10043670  movups  xmmword ptr [ecx], xmm0
0x10043673  mov     eax, ds:off_1000378C
0x10043678  mov     ecx, [edx]
0x1004367a  movups  xmm0, xmmword ptr [eax]
0x1004367d  movups  xmmword ptr [ecx+10h], xmm0
0x10043681  mov     eax, ds:off_10003798
0x10043686  mov     ecx, [edx]
0x10043688  movups  xmm0, xmmword ptr [eax]
0x1004368b  movups  xmmword ptr [ecx+20h], xmm0
0x1004368f  mov     eax, ds:off_100037A4
0x10043694  mov     ecx, [edx]
0x10043696  movups  xmm0, xmmword ptr [eax]
0x10043699  movups  xmmword ptr [ecx+30h], xmm0
0x1004369d  mov     eax, ds:off_100037B0
0x100436a2  mov     ecx, [edx]
0x100436a4  movups  xmm0, xmmword ptr [eax]
0x100436a7  movups  xmmword ptr [ecx+40h], xmm0
0x100436ab  mov     eax, ds:off_100037BC
0x100436b0  mov     ecx, [edx]
0x100436b2  movups  xmm0, xmmword ptr [eax]
0x100436b5  movups  xmmword ptr [ecx+50h], xmm0
0x100436b9  mov     eax, ds:off_100037C8
0x100436be  mov     ecx, [edx]
0x100436c0  movups  xmm0, xmmword ptr [eax]
0x100436c3  movups  xmmword ptr [ecx+60h], xmm0
0x100436c7  mov     eax, ds:off_100037D4
0x100436cc  mov     ecx, [edx]
0x100436ce  movups  xmm0, xmmword ptr [eax]
0x100436d1  movups  xmmword ptr [ecx+70h], xmm0
0x100436d5  mov     eax, ds:off_100037E0
0x100436da  mov     ecx, [edx]
0x100436dc  movups  xmm0, xmmword ptr [eax]
0x100436df  mov     eax, [ebp+arg_4]
0x100436e2  movups  xmmword ptr [ecx+80h], xmm0
0x100436e9  mov     dword ptr [eax], 9
0x100436ef  jmp     short loc_10043704
0x100436f1  mov     edi, 80070057h
0x100436f6  push    0; int
0x100436f8  push    offset _IID_ISecurityInfo; int
0x100436fd  mov     edx, edi
0x100436ff  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x10043704  test    esi, esi
0x10043706  jz      short loc_1004370F
0x10043708  push    esi; lpCriticalSection
0x10043709  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004370f  mov     eax, edi
0x10043711  mov     ecx, [ebp+var_C]
0x10043714  mov     large fs:0, ecx
0x1004371b  pop     ecx
0x1004371c  pop     edi
0x1004371d  pop     esi
0x1004371e  mov     esp, ebp
0x10043720  pop     ebp
0x10043721  retn    0Ch
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
