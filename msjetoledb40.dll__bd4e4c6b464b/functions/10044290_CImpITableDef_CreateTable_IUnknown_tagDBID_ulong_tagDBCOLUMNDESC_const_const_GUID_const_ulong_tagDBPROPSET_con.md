# CImpITableDef::CreateTable(IUnknown *,tagDBID *,ulong,tagDBCOLUMNDESC const * const,_GUID const &,ulong,tagDBPROPSET * const,tagDBID * *,IUnknown * *)

- ea: `0x10044290`
- end: `0x10044323`
- name: `?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z`
- size: `147`
- prototype: `int __stdcall(CImpITableDef *__hidden this, struct IUnknown *, struct tagDBID *, unsigned int, const struct tagDBCOLUMNDESC *const, const struct _GUID *, unsigned int, struct tagDBPROPSET *const, struct tagDBID **, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1000ba90`
- `0x10044290`
- `0x10044ee0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10044308`
- `KERNEL32!LeaveCriticalSection` at `0x10044308`
- `KERNEL32!EnterCriticalSection` at `0x100442ce`
- `KERNEL32!EnterCriticalSection` at `0x100442ce`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100442bb`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100442bb`

## pseudocode

```c
int __stdcall CImpITableDef::CreateTable(
        CImpITableDef *this,
        struct IUnknown *a2,
        struct tagDBID *a3,
        unsigned int a4,
        const struct tagDBCOLUMNDESC *const a5,
        const struct _GUID *a6,
        unsigned int a7,
        struct tagDBPROPSET *const a8,
        struct tagDBID **a9,
        struct IUnknown **a10)
{
  struct _RTL_CRITICAL_SECTION *v10; // esi
  int result; // eax
  int v12; // edi

  SetErrorInfo(0, 0);
  v10 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 104);
  EnterCriticalSection(v10);
  result = CImpITableDef::InternalCreateTable(this, a2, a3, a4, a5, 0, 0, a6, a7, a8, a9, a10);
  v12 = result;
  if ( v10 )
  {
    LeaveCriticalSection(v10);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x10044290  mov     edi, edi
0x10044292  push    ebp
0x10044293  mov     ebp, esp
0x10044295  push    0FFFFFFFFh
0x10044297  push    offset ?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x1004429c  mov     eax, large fs:0
0x100442a2  push    eax
0x100442a3  push    ecx
0x100442a4  push    esi
0x100442a5  push    edi
0x100442a6  mov     eax, ___security_cookie
0x100442ab  xor     eax, ebp
0x100442ad  push    eax
0x100442ae  lea     eax, [ebp+var_C]
0x100442b1  mov     large fs:0, eax
0x100442b7  push    0; perrinfo
0x100442b9  push    0; dwReserved
0x100442bb  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100442c1  mov     edi, [ebp+this]
0x100442c4  mov     esi, [edi+8]
0x100442c7  add     esi, 68h ; 'h'
0x100442ca  push    esi; lpCriticalSection
0x100442cb  mov     [ebp+var_10], esi
0x100442ce  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100442d4  push    [ebp+arg_24]; struct IUnknown **
0x100442d7  mov     ecx, edi; this
0x100442d9  mov     [ebp+var_4], 0
0x100442e0  push    [ebp+arg_20]; struct tagDBID **
0x100442e3  push    [ebp+arg_1C]; struct tagDBPROPSET *
0x100442e6  push    [ebp+arg_18]; unsigned int
0x100442e9  push    [ebp+arg_14]; struct _GUID *
0x100442ec  push    0; struct tagDBCONSTRAINTDESC *
0x100442ee  push    0; unsigned int
0x100442f0  push    [ebp+arg_10]; struct tagDBCOLUMNDESC *
0x100442f3  push    [ebp+arg_C]; unsigned int
0x100442f6  push    [ebp+arg_8]; struct tagDBID *
0x100442f9  push    [ebp+arg_4]; struct IUnknown *
0x100442fc  call    ?InternalCreateTable@CImpITableDef@@QAEJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@KQAUtagDBCONSTRAINTDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z; CImpITableDef::InternalCreateTable(IUnknown *,tagDBID *,ulong,tagDBCOLUMNDESC const * const,ulong,tagDBCONSTRAINTDESC * const,_GUID const &,ulong,tagDBPROPSET * const,tagDBID * *,IUnknown * *)
0x10044301  mov     edi, eax
0x10044303  test    esi, esi
0x10044305  jz      short loc_10044310
0x10044307  push    esi; lpCriticalSection
0x10044308  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1004430e  mov     eax, edi
0x10044310  mov     ecx, [ebp+var_C]
0x10044313  mov     large fs:0, ecx
0x1004431a  pop     ecx
0x1004431b  pop     edi
0x1004431c  pop     esi
0x1004431d  mov     esp, ebp
0x1004431f  pop     ebp
0x10044320  retn    28h ; '('
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
