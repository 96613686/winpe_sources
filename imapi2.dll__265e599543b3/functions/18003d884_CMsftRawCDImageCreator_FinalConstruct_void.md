# CMsftRawCDImageCreator::FinalConstruct(void)

- ea: `0x18003d884`
- end: `0x18003da06`
- name: `?FinalConstruct@CMsftRawCDImageCreator@@QEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(CMsftRawCDImageCreator *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003cc58`

## callees

- `0x18000ea20`
- `0x1800140f4`
- `0x18003d884`
- `0x180040bb0`
- `0x180040d54`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003d90b`
- `ole32!CoCreateInstance` at `0x18003d90b`

## pseudocode

```c
__int64 __fastcall CMsftRawCDImageCreator::FinalConstruct(CMsftRawCDImageCreator *this)
{
  struct IUnknown **v1; // rdi
  __int64 v2; // rbx
  int Instance; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned __int8 *v6; // r9
  struct IStream *ppv; // [rsp+40h] [rbp+8h] BYREF

  *((_DWORD *)this + 19) = 2;
  *((_DWORD *)this + 10832) = 0;
  v1 = (struct IUnknown **)((char *)this + 128);
  *((_WORD *)this + 21666) = 0;
  v2 = 0;
  *((_WORD *)this + 36) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 10) = 443099;
  *((_QWORD *)this + 13) = 1;
  do
    CTrackData::Clear((CTrackData *)&v1[54 * v2++]);
  while ( v2 != 100 );
  ppv = 0;
  Instance = CoCreateInstance(
               &CLSID_MsftStreamZero,
               0,
               0x17u,
               &GUID_0000000c_0000_0000_c000_000000000046,
               (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(struct IStream *, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 352800);
    if ( Instance >= 0 )
    {
      Instance = CTrackData::Init(v1, IMAPI_CD_SECTOR_AUDIO, ppv, v6);
      if ( Instance < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
        {
          v5 = 12;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
      {
        v5 = 11;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 708) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 705) >= 3u )
    {
      v5 = 10;
LABEL_18:
      WPP_SF_d(v4[87], v5, &WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids, (unsigned int)Instance);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003d884  mov     [rsp+arg_8], rbx
0x18003d889  push    rdi
0x18003d88a  sub     rsp, 30h
0x18003d88e  xor     eax, eax
0x18003d890  mov     dword ptr [rcx+4Ch], 2
0x18003d897  mov     [rcx+0A940h], eax
0x18003d89d  lea     rdi, [rcx+80h]
0x18003d8a4  mov     [rcx+0A944h], ax
0x18003d8ab  xor     ebx, ebx
0x18003d8ad  mov     [rcx+48h], ax
0x18003d8b1  mov     [rcx+58h], rax
0x18003d8b5  mov     [rcx+78h], eax
0x18003d8b8  mov     [rcx+70h], rax
0x18003d8bc  mov     qword ptr [rcx+50h], 6C2DBh
0x18003d8c4  mov     qword ptr [rcx+68h], 1
0x18003d8cc  imul    rcx, rbx, 1B0h
0x18003d8d3  add     rcx, rdi; this
0x18003d8d6  call    ?Clear@CTrackData@@QEAAXXZ; CTrackData::Clear(void)
0x18003d8db  inc     rbx
0x18003d8de  cmp     rbx, 64h ; 'd'
0x18003d8e2  jnz     short loc_18003D8CC
0x18003d8e4  lea     rax, [rsp+38h+arg_0]
0x18003d8e9  mov     [rsp+38h+arg_0], 0
0x18003d8f2  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046; riid
0x18003d8f9  mov     [rsp+38h+ppv], rax; ppv
0x18003d8fe  xor     edx, edx; pUnkOuter
0x18003d900  lea     r8d, [rbx-4Dh]; dwClsContext
0x18003d904  lea     rcx, CLSID_MsftStreamZero; rclsid
0x18003d90b  call    cs:__imp_CoCreateInstance
0x18003d911  mov     ebx, eax
0x18003d913  test    eax, eax
0x18003d915  jns     short loc_18003D952
0x18003d917  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d91e  lea     rax, WPP_GLOBAL_Control
0x18003d925  cmp     rcx, rax
0x18003d928  jz      loc_18003D9EF
0x18003d92e  test    byte ptr [rcx+2C4h], 10h
0x18003d935  jz      loc_18003D9EF
0x18003d93b  cmp     byte ptr [rcx+2C1h], 3
0x18003d942  jb      loc_18003D9EF
0x18003d948  mov     edx, 0Ah
0x18003d94d  jmp     loc_18003D9D9
0x18003d952  mov     rcx, [rsp+38h+arg_0]
0x18003d957  mov     edx, 56220h
0x18003d95c  mov     rax, [rcx]
0x18003d95f  mov     rax, [rax+30h]
0x18003d963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d968  mov     ebx, eax
0x18003d96a  test    eax, eax
0x18003d96c  jns     short loc_18003D99A
0x18003d96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d975  lea     rax, WPP_GLOBAL_Control
0x18003d97c  cmp     rcx, rax
0x18003d97f  jz      short loc_18003D9EF
0x18003d981  test    byte ptr [rcx+2C4h], 10h
0x18003d988  jz      short loc_18003D9EF
0x18003d98a  cmp     byte ptr [rcx+2C1h], 3
0x18003d991  jb      short loc_18003D9EF
0x18003d993  mov     edx, 0Bh
0x18003d998  jmp     short loc_18003D9D9
0x18003d99a  mov     r8, [rsp+38h+arg_0]; struct IStream *
0x18003d99f  xor     edx, edx; enum _IMAPI_CD_SECTOR_TYPE
0x18003d9a1  mov     rcx, rdi; this
0x18003d9a4  call    ?Init@CTrackData@@QEAAJW4_IMAPI_CD_SECTOR_TYPE@@PEAUIStream@@@Z; CTrackData::Init(_IMAPI_CD_SECTOR_TYPE,IStream *)
0x18003d9a9  mov     ebx, eax
0x18003d9ab  test    eax, eax
0x18003d9ad  jns     short loc_18003D9EF
0x18003d9af  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d9b6  lea     rax, WPP_GLOBAL_Control
0x18003d9bd  cmp     rcx, rax
0x18003d9c0  jz      short loc_18003D9EF
0x18003d9c2  test    byte ptr [rcx+2C4h], 10h
0x18003d9c9  jz      short loc_18003D9EF
0x18003d9cb  cmp     byte ptr [rcx+2C1h], 3
0x18003d9d2  jb      short loc_18003D9EF
0x18003d9d4  mov     edx, 0Ch
0x18003d9d9  mov     rcx, [rcx+2B8h]
0x18003d9e0  lea     r8, WPP_0ebd0c07e14a34f97cce10201c72be14_Traceguids
0x18003d9e7  mov     r9d, ebx
0x18003d9ea  call    WPP_SF_d
0x18003d9ef  lea     rcx, [rsp+38h+arg_0]
0x18003d9f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d9f9  mov     eax, ebx
0x18003d9fb  mov     rbx, [rsp+38h+arg_8]
0x18003da00  add     rsp, 30h
0x18003da04  pop     rdi
0x18003da05  retn
```
