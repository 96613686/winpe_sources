# CImpITableDef::CreateTableWithConstraints(IUnknown *,tagDBID *,ulong,tagDBCOLUMNDESC * const,ulong,tagDBCONSTRAINTDESC * const,_GUID const &,ulong,tagDBPROPSET * const,tagDBID * *,IUnknown * *)

- ea: `0x10044a20`
- end: `0x10044ab5`
- name: `?CreateTableWithConstraints@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQAUtagDBCOLUMNDESC@@KQAUtagDBCONSTRAINTDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z`
- size: `149`
- prototype: `int __stdcall(CImpITableDef *__hidden this, struct IUnknown *, struct tagDBID *, unsigned int, struct tagDBCOLUMNDESC *const, unsigned int, struct tagDBCONSTRAINTDESC *const, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct tagDBID **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1000ba90`
- `0x10044a20`
- `0x10044ee0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10044a9a`
- `KERNEL32!LeaveCriticalSection` at `0x10044a9a`
- `KERNEL32!EnterCriticalSection` at `0x10044a5e`
- `KERNEL32!EnterCriticalSection` at `0x10044a5e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10044a4b`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10044a4b`

## pseudocode

```c
int __stdcall CImpITableDef::CreateTableWithConstraints(
        CImpITableDef *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        unsigned int a4,
        struct tagDBCOLUMNDESC *const a5,
        unsigned int a6,
        struct tagDBCONSTRAINTDESC *const a7,
        const struct _GUID *a8,
        unsigned int a9,
        struct tagDBPROPSET *const a10,
        struct tagDBID **a11,
        struct IUnknown **a12)
{
  struct _RTL_CRITICAL_SECTION *v12; // esi
  int result; // eax
  int v14; // edi

  SetErrorInfo(0, 0);
  v12 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v12);
  result = CImpITableDef::InternalCreateTable(this, a2, a3, a4, a5, a6, a7, a8, a9, a10, a11, a12);
  v14 = result;
  if ( v12 )
  {
    LeaveCriticalSection(v12);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x10044a20  mov     edi, edi
0x10044a22  push    ebp
0x10044a23  mov     ebp, esp
0x10044a25  push    0FFFFFFFFh
0x10044a27  push    offset ?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x10044a2c  mov     eax, large fs:0
0x10044a32  push    eax
0x10044a33  push    ecx
0x10044a34  push    esi
0x10044a35  push    edi
0x10044a36  mov     eax, ___security_cookie
0x10044a3b  xor     eax, ebp
0x10044a3d  push    eax
0x10044a3e  lea     eax, [ebp+var_C]
0x10044a41  mov     large fs:0, eax
0x10044a47  push    0; perrinfo
0x10044a49  push    0; dwReserved
0x10044a4b  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10044a51  mov     edi, [ebp+this]
0x10044a54  mov     esi, [edi+8]
0x10044a57  add     esi, 68h ; 'h'
0x10044a5a  push    esi; lpCriticalSection
0x10044a5b  mov     [ebp+var_10], esi
0x10044a5e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10044a64  push    [ebp+arg_2C]; struct IUnknown **
0x10044a67  mov     ecx, edi; this
0x10044a69  mov     [ebp+var_4], 0
0x10044a70  push    [ebp+arg_28]; struct tagDBID **
0x10044a73  push    [ebp+arg_24]; struct tagDBPROPSET *
0x10044a76  push    [ebp+arg_20]; unsigned int
0x10044a79  push    [ebp+arg_1C]; struct _GUID *
0x10044a7c  push    [ebp+arg_18]; struct tagDBCONSTRAINTDESC *
0x10044a7f  push    [ebp+arg_14]; unsigned int
0x10044a82  push    [ebp+arg_10]; struct tagDBCOLUMNDESC *
0x10044a85  push    [ebp+arg_C]; unsigned int
0x10044a88  push    [ebp+arg_8]; struct tagDBID *
0x10044a8b  push    [ebp+arg_4]; struct IUnknown *
0x10044a8e  call    ?InternalCreateTable@CImpITableDef@@QAEJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@KQAUtagDBCONSTRAINTDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z; CImpITableDef::InternalCreateTable(IUnknown *,tagDBID *,ulong,tagDBCOLUMNDESC const * const,ulong,tagDBCONSTRAINTDESC * const,_GUID const &,ulong,tagDBPROPSET * const,tagDBID * *,IUnknown * *)
0x10044a93  mov     edi, eax
0x10044a95  test    esi, esi
0x10044a97  jz      short loc_10044AA2
0x10044a99  push    esi; lpCriticalSection
0x10044a9a  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10044aa0  mov     eax, edi
0x10044aa2  mov     ecx, [ebp+var_C]
0x10044aa5  mov     large fs:0, ecx
0x10044aac  pop     ecx
0x10044aad  pop     edi
0x10044aae  pop     esi
0x10044aaf  mov     esp, ebp
0x10044ab1  pop     ebp
0x10044ab2  retn    30h ; '0'
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
