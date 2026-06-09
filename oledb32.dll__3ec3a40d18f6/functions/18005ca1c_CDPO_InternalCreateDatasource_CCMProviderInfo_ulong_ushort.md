# CDPO::InternalCreateDatasource(CCMProviderInfo *,ulong,ushort *)

- ea: `0x18005ca1c`
- end: `0x18005cbb0`
- name: `?InternalCreateDatasource@CDPO@@QEAAJPEAVCCMProviderInfo@@KPEAG@Z`
- size: `404`
- prototype: `__int64 __fastcall(CDPO *__hidden this, struct CCMProviderInfo *, unsigned int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18005b5c8`
- `0x18005d5a0`

## callees

- `0x180013870`
- `0x180015704`
- `0x180029560`
- `0x18005ca1c`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18005cb8c`
- `OLEAUT32!__imp_VariantClear` at `0x18005cb8c`

## string_xrefs

- `0x18005ca4f`: `<CDPO::InternalCreateDatasource|OLEDB|ERR> `
- `0x18005cad4`: `<CDPO::InternalCreateDatasource|OLEDB|ERR> `
- `0x18005cb6a`: `<CDPO::InternalCreateDatasource|OLEDB|ERR> `
- `0x18005ca6f`: `<CDPO::InternalCreateDatasource|Trace|HR> `
- `0x18005caf4`: `<CDPO::InternalCreateDatasource|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDPO::InternalCreateDatasource(CDPO *this, struct CCMProviderInfo *a2, int a3, unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  unsigned int SetArrayShape; // esi
  __int64 v9; // rcx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  VARIANTARG *v12; // rbx

  if ( a2 )
  {
    *((_DWORD *)this + 32) = a3;
    *((_QWORD *)this + 17) = a4;
    *((_QWORD *)this + 15) = a2;
    _InterlockedIncrement((volatile signed __int32 *)a2);
    SetArrayShape = CDPOPropertySetArray::LoadSetArrayShape(
                      (CDPO *)((char *)this + 144),
                      (struct CDSLPropertySetArray *)(*((_QWORD *)this + 15) + 1208LL));
    if ( (SetArrayShape & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(SetArrayShape, L"<CDPO::InternalCreateDatasource|OLEDB|ERR> ", 0x10Au);
        if ( (bidGblFlags & 2) != 0 )
          return (unsigned int)bidTraceHR(
                                 off_1800C8410[0],
                                 272393,
                                 L"<CDPO::InternalCreateDatasource|Trace|HR> ",
                                 SetArrayShape);
      }
      return SetArrayShape;
    }
    if ( *((_QWORD *)a2 + 147) != -1 )
    {
      v9 = *((_QWORD *)this + 19);
      SetArrayShape = -2147418113;
      if ( !v9 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v10 = 275;
LABEL_18:
          OLEDBTraceErr(-2147418113, L"<CDPO::InternalCreateDatasource|OLEDB|ERR> ", v10);
          return SetArrayShape;
        }
        return SetArrayShape;
      }
      v11 = *(_QWORD *)(32LL * *((unsigned int *)a2 + 294) + v9);
      if ( !v11 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v10 = 286;
          goto LABEL_18;
        }
        return SetArrayShape;
      }
      v12 = (VARIANTARG *)(v11 + 72LL * *((unsigned int *)a2 + 295));
      VariantClear(v12 + 2);
      v12[2].vt = 2;
      v12[2].iVal = 4;
    }
    return 0;
  }
  v6 = -2147467261;
  if ( (bidGblFlags & 2) != 0 )
  {
    OLEDBTraceErr(-2147467261, L"<CDPO::InternalCreateDatasource|OLEDB|ERR> ", 0x100u);
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(
                             off_1800C8410[0],
                             262153,
                             L"<CDPO::InternalCreateDatasource|Trace|HR> ",
                             2147500035LL);
  }
  return v6;
}

```

## disassembly

```asm
0x18005ca1c  mov     [rsp+arg_0], rbx
0x18005ca21  mov     [rsp+arg_8], rsi
0x18005ca26  push    rdi
0x18005ca27  sub     rsp, 20h
0x18005ca2b  mov     rbx, rdx
0x18005ca2e  mov     rdi, rcx
0x18005ca31  test    rdx, rdx
0x18005ca34  jnz     short loc_18005CA8C
0x18005ca36  mov     eax, cs:_bidGblFlags
0x18005ca3c  lea     edi, [rdx+2]
0x18005ca3f  mov     ebx, 80004003h
0x18005ca44  test    dil, al
0x18005ca47  jz      short loc_18005CA85
0x18005ca49  mov     r8d, 100h; unsigned int
0x18005ca4f  lea     rdx, aCdpoInternalcr_0; "<CDPO::InternalCreateDatasource|OLEDB|E"...
0x18005ca56  mov     ecx, ebx; int
0x18005ca58  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005ca5d  mov     eax, cs:_bidGblFlags
0x18005ca63  test    dil, al
0x18005ca66  jz      short loc_18005CA85
0x18005ca68  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005ca6f  lea     r8, aCdpoInternalcr; "<CDPO::InternalCreateDatasource|Trace|H"...
0x18005ca76  mov     r9d, ebx
0x18005ca79  mov     edx, 40009h
0x18005ca7e  call    _bidTraceHR
0x18005ca83  mov     ebx, eax
0x18005ca85  mov     eax, ebx
0x18005ca87  jmp     loc_18005CBA0
0x18005ca8c  mov     [rcx+80h], r8d
0x18005ca93  mov     [rcx+88h], r9
0x18005ca9a  mov     [rcx+78h], rbx
0x18005ca9e  lock inc dword ptr [rdx]
0x18005caa1  mov     rdx, [rcx+78h]
0x18005caa5  add     rcx, 90h; this
0x18005caac  add     rdx, 4B8h; struct CDSLPropertySetArray *
0x18005cab3  call    ?LoadSetArrayShape@CDPOPropertySetArray@@QEAAJAEAVCDSLPropertySetArray@@@Z; CDPOPropertySetArray::LoadSetArrayShape(CDSLPropertySetArray &)
0x18005cab8  mov     esi, eax
0x18005caba  test    eax, eax
0x18005cabc  jns     short loc_18005CB11
0x18005cabe  mov     eax, cs:_bidGblFlags
0x18005cac4  mov     edi, 2
0x18005cac9  test    dil, al
0x18005cacc  jz      short loc_18005CB0A
0x18005cace  mov     r8d, 10Ah; unsigned int
0x18005cad4  lea     rdx, aCdpoInternalcr_0; "<CDPO::InternalCreateDatasource|OLEDB|E"...
0x18005cadb  mov     ecx, esi; int
0x18005cadd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005cae2  mov     eax, cs:_bidGblFlags
0x18005cae8  test    dil, al
0x18005caeb  jz      short loc_18005CB0A
0x18005caed  mov     rcx, cs:off_1800C8410; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18005caf4  lea     r8, aCdpoInternalcr; "<CDPO::InternalCreateDatasource|Trace|H"...
0x18005cafb  mov     r9d, esi
0x18005cafe  mov     edx, 42809h
0x18005cb03  call    _bidTraceHR
0x18005cb08  mov     esi, eax
0x18005cb0a  mov     eax, esi
0x18005cb0c  jmp     loc_18005CBA0
0x18005cb11  mov     eax, [rbx+498h]
0x18005cb17  or      ecx, 0FFFFFFFFh
0x18005cb1a  cmp     eax, ecx
0x18005cb1c  jnz     short loc_18005CB26
0x18005cb1e  cmp     [rbx+49Ch], ecx
0x18005cb24  jz      short loc_18005CB9E
0x18005cb26  mov     rcx, [rdi+98h]
0x18005cb2d  mov     esi, 8000FFFFh
0x18005cb32  test    rcx, rcx
0x18005cb35  jnz     short loc_18005CB4B
0x18005cb37  lea     edi, [rcx+2]
0x18005cb3a  test    byte ptr cs:_bidGblFlags, dil
0x18005cb41  jz      short loc_18005CB0A
0x18005cb43  mov     r8d, 113h
0x18005cb49  jmp     short loc_18005CB6A
0x18005cb4b  shl     rax, 5
0x18005cb4f  mov     rdx, [rax+rcx]
0x18005cb53  test    rdx, rdx
0x18005cb56  jnz     short loc_18005CB7A
0x18005cb58  lea     edi, [rdx+2]
0x18005cb5b  test    byte ptr cs:_bidGblFlags, dil
0x18005cb62  jz      short loc_18005CB0A
0x18005cb64  mov     r8d, 11Eh; unsigned int
0x18005cb6a  lea     rdx, aCdpoInternalcr_0; "<CDPO::InternalCreateDatasource|OLEDB|E"...
0x18005cb71  mov     ecx, esi; int
0x18005cb73  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18005cb78  jmp     short loc_18005CB0A
0x18005cb7a  mov     eax, [rbx+49Ch]
0x18005cb80  lea     rcx, [rax+rax*8]
0x18005cb84  lea     rbx, [rdx+rcx*8]
0x18005cb88  lea     rcx, [rbx+30h]; pvarg
0x18005cb8c  call    cs:__imp_VariantClear
0x18005cb92  mov     word ptr [rbx+30h], 2
0x18005cb98  mov     word ptr [rbx+38h], 4
0x18005cb9e  xor     eax, eax
0x18005cba0  mov     rbx, [rsp+28h+arg_0]
0x18005cba5  mov     rsi, [rsp+28h+arg_8]
0x18005cbaa  add     rsp, 20h
0x18005cbae  pop     rdi
0x18005cbaf  retn
```
