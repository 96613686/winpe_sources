# COfflineFilesCache::FindItemEx(ushort const *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,ulong,IOfflineFilesItem * *)

- ea: `0x180003ca0`
- end: `0x180004022`
- name: `?FindItemEx@COfflineFilesCache@@UEAAJPEBGPEAUIOfflineFilesItemFilter@@111KPEAPEAUIOfflineFilesItem@@@Z`
- size: `898`
- prototype: `int(COfflineFilesCache *__hidden this, const unsigned __int16 *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, unsigned int, struct IOfflineFilesItem **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002df0`
- `0x180003ca0`
- `0x1800046c0`
- `0x180008550`
- `0x180008840`
- `0x18000b7c0`
- `0x18000c174`
- `0x18000f5a4`
- `0x1800102a8`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003d77`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003d77`
- `ntdll!RtlpEnsureBufferSize` at `0x180003ef7`
- `ntdll!RtlpEnsureBufferSize` at `0x180003ef7`
- `ntdll!RtlInitUnicodeString` at `0x180003ebd`
- `ntdll!RtlInitUnicodeString` at `0x180003ebd`

## pseudocode

```c
__int64 __fastcall COfflineFilesCache::FindItemEx(
        COfflineFilesCache *this,
        const unsigned __int16 *a2,
        struct IOfflineFilesItemFilter *a3,
        struct IOfflineFilesItemFilter *a4,
        struct IOfflineFilesItemFilter *a5,
        struct IOfflineFilesItemFilter *a6,
        unsigned int a7,
        struct IOfflineFilesItem **a8)
{
  HRESULT v12; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // edi
  __int64 result; // rax
  USHORT Length; // r8
  unsigned __int16 v18; // dx
  SIZE_T v19; // rax
  unsigned __int64 v20; // rdx
  const unsigned __int16 *ConstBuffer; // rax
  int v22; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  struct IOfflineFilesService *v24; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v27[260]; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+278h] [rbp+178h]
  PUCHAR v29; // [rsp+280h] [rbp+180h]
  _RTL_BUFFER Buffer; // [rsp+288h] [rbp+188h] BYREF

  *(_QWORD *)&DestinationString.Length = a6;
  if ( a2 && a8 )
  {
    *a8 = 0;
    v12 = -2147467262;
    v13 = (_QWORD *)*((_QWORD *)this + 5);
    v24 = 0;
    v14 = *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 - *v13;
    if ( *(_QWORD *)&GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1 == *v13 )
      v14 = *(_QWORD *)GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4 - v13[1];
    if ( v14 )
      goto LABEL_12;
    v15 = *((_DWORD *)this + 12);
    if ( !v15 )
      goto LABEL_12;
    ppv = 0;
    v12 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, struct IOfflineFilesService **))(*(_QWORD *)ppv + 40LL))(
              ppv,
              v15,
              &GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce,
              &v24);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v12 < 0 )
      goto LABEL_12;
    v26[3] = *(_QWORD *)&DestinationString.Length;
    v26[0] = a3;
    v26[1] = a4;
    v26[2] = a5;
    memset_0(&Buffer.ReservedForIMalloc, 0, 0x300u);
    v12 = (*(__int64 (__fastcall **)(struct IOfflineFilesService *, _QWORD *, const unsigned __int16 *, _QWORD, PVOID *))(*(_QWORD *)v24 + 120LL))(
            v24,
            v26,
            a2,
            a7,
            &Buffer.ReservedForIMalloc);
    if ( v12 < 0 )
    {
LABEL_11:
      (*(void (__fastcall **)(struct IOfflineFilesService *))(*(_QWORD *)v24 + 16LL))(v24);
LABEL_12:
      result = 0;
      if ( v12 < 0 )
        return (unsigned int)v12;
      return result;
    }
    v28 = 34078720;
    Buffer.Size = 520;
    Buffer.Buffer = (PUCHAR)v27;
    Buffer.StaticSize = 520;
    Buffer.StaticBuffer = (PUCHAR)v27;
    v29 = (PUCHAR)v27;
    v27[0] = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    Length = DestinationString.Length;
    v18 = 0;
    LOWORD(v28) = 0;
    v19 = DestinationString.Length + 2LL;
    if ( v19 > 0xFFFE )
    {
      v22 = -1073741562;
    }
    else
    {
      if ( v19 <= Buffer.Size )
      {
LABEL_19:
        v29 = Buffer.Buffer;
        memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v18 >> 1)], DestinationString.Buffer, Length);
        v20 = (unsigned __int16)(DestinationString.Length + v28);
        LOWORD(v28) = v20;
        HIWORD(v28) = v20 + 2;
        *(_WORD *)&v29[2 * (v20 >> 1)] = 0;
        goto LABEL_20;
      }
      if ( RtlpEnsureBufferSize(0, &Buffer, DestinationString.Length + 2LL) >= 0 )
      {
        v18 = v28;
        Length = DestinationString.Length;
        goto LABEL_19;
      }
      v22 = -1073741801;
    }
    v12 = ResultFromNtStatus(v22);
    if ( v12 < 0 )
    {
LABEL_26:
      CPath::~CPath((CPath *)v27);
      goto LABEL_11;
    }
LABEL_20:
    v12 = CPath::RemoveFileSpecAndBackslash((CPath *)v27);
    if ( v12 >= 0 )
    {
      ppv = 0;
      ConstBuffer = CPath::_GetConstBuffer((CPath *)v27);
      v12 = COfflineFilesItem_CreateInstance(
              v24,
              ConstBuffer,
              (const struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)&Buffer.ReservedForIMalloc,
              &GUID_4a753da6_e044_4f12_a718_5d14d079a906,
              &ppv);
      if ( v12 >= 0 )
        *a8 = (struct IOfflineFilesItem *)ppv;
    }
    goto LABEL_26;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_91a48976ead63973ddd357b80bae3284_Traceguids);
  return 2147500035LL;
}

```

## disassembly

```asm
0x180003ca0  push    rbp
0x180003ca2  push    rsi
0x180003ca3  push    r12
0x180003ca5  push    r13
0x180003ca7  push    r14
0x180003ca9  push    r15
0x180003cab  lea     rbp, [rsp-4D8h]
0x180003cb3  sub     rsp, 5D8h
0x180003cba  mov     rax, cs:__security_cookie
0x180003cc1  xor     rax, rsp
0x180003cc4  mov     [rbp+500h+var_50], rax
0x180003ccb  mov     rax, [rbp+500h+arg_28]
0x180003cd2  mov     r14, rdx
0x180003cd5  mov     r13, [rbp+500h+arg_20]
0x180003cdc  mov     r12, r9
0x180003cdf  mov     rsi, [rbp+500h+arg_38]
0x180003ce6  mov     r15, r8
0x180003ce9  mov     qword ptr [rsp+600h+DestinationString.Length], rax
0x180003cee  mov     rdx, rcx
0x180003cf1  test    r14, r14
0x180003cf4  jz      loc_180003FC0
0x180003cfa  test    rsi, rsi
0x180003cfd  jz      loc_180003FC0
0x180003d03  xor     r8d, r8d
0x180003d06  mov     [rsp+600h+var_30], rbx
0x180003d0e  mov     [rsi], r8
0x180003d11  mov     ebx, 80004002h
0x180003d16  mov     rcx, [rcx+28h]
0x180003d1a  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data1
0x180003d21  mov     [rsp+600h+var_5C8], r8
0x180003d26  sub     rax, [rcx]
0x180003d29  jnz     short loc_180003D36
0x180003d2b  mov     rax, qword ptr cs:_GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce.Data4
0x180003d32  sub     rax, [rcx+8]
0x180003d36  test    rax, rax
0x180003d39  jnz     loc_180003E34
0x180003d3f  mov     [rsp+600h+var_38], rdi
0x180003d47  mov     edi, [rdx+30h]
0x180003d4a  test    edi, edi
0x180003d4c  jz      loc_180003E2C
0x180003d52  mov     [rsp+600h+var_5D0], r8
0x180003d57  lea     rax, [rsp+600h+var_5D0]
0x180003d5c  mov     r8d, 1; dwClsContext
0x180003d62  mov     [rsp+600h+ppv], rax; ppv
0x180003d67  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003d6e  xor     edx, edx; pUnkOuter
0x180003d70  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003d77  call    cs:__imp_CoCreateInstance
0x180003d7d  mov     ebx, eax
0x180003d7f  test    eax, eax
0x180003d81  js      short loc_180003DB5
0x180003d83  mov     rcx, [rsp+600h+var_5D0]
0x180003d88  lea     r9, [rsp+600h+var_5C8]
0x180003d8d  lea     r8, _GUID_ab4edee5_0f23_4619_8d33_cee9f4277dce
0x180003d94  mov     edx, edi
0x180003d96  mov     rax, [rcx]
0x180003d99  mov     rax, [rax+28h]
0x180003d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da2  mov     rcx, [rsp+600h+var_5D0]
0x180003da7  mov     ebx, eax
0x180003da9  mov     rax, [rcx]
0x180003dac  mov     rax, [rax+10h]
0x180003db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003db5  test    ebx, ebx
0x180003db7  js      short loc_180003E29
0x180003db9  mov     rax, qword ptr [rsp+600h+DestinationString.Length]
0x180003dbe  lea     rcx, [rbp+500h+Buffer.ReservedForIMalloc]; void *
0x180003dc5  xor     edx, edx; Val
0x180003dc7  mov     [rsp+600h+var_598], rax
0x180003dcc  mov     r8d, 300h; Size
0x180003dd2  mov     [rsp+600h+var_5B0], r15
0x180003dd7  mov     [rsp+600h+var_5A8], r12
0x180003ddc  mov     [rsp+600h+var_5A0], r13
0x180003de1  call    memset_0
0x180003de6  mov     rcx, [rsp+600h+var_5C8]
0x180003deb  lea     rdx, [rbp+500h+Buffer.ReservedForIMalloc]
0x180003df2  mov     r9d, [rbp+500h+arg_30]
0x180003df9  mov     r8, r14
0x180003dfc  mov     [rsp+600h+ppv], rdx
0x180003e01  lea     rdx, [rsp+600h+var_5B0]
0x180003e06  mov     rax, [rcx]
0x180003e09  mov     rax, [rax+78h]
0x180003e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e12  mov     ebx, eax
0x180003e14  test    eax, eax
0x180003e16  jns     short loc_180003E65
0x180003e18  mov     rcx, [rsp+600h+var_5C8]
0x180003e1d  mov     rax, [rcx]
0x180003e20  mov     rax, [rax+10h]
0x180003e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e29  xor     r8d, r8d
0x180003e2c  mov     rdi, [rsp+600h+var_38]
0x180003e34  test    ebx, ebx
0x180003e36  mov     eax, r8d
0x180003e39  cmovs   eax, ebx
0x180003e3c  mov     rbx, [rsp+600h+var_30]
0x180003e44  mov     rcx, [rbp+500h+var_50]
0x180003e4b  xor     rcx, rsp; StackCookie
0x180003e4e  call    __security_check_cookie
0x180003e53  add     rsp, 5D8h
0x180003e5a  pop     r15
0x180003e5c  pop     r14
0x180003e5e  pop     r13
0x180003e60  pop     r12
0x180003e62  pop     rsi
0x180003e63  pop     rbp
0x180003e64  retn
0x180003e65  mov     ecx, 208h
0x180003e6a  mov     [rbp+500h+var_388], 2080000h
0x180003e74  lea     rax, [rsp+600h+var_590]
0x180003e79  mov     [rbp+500h+Buffer.Size], rcx
0x180003e80  mov     [rbp+500h+Buffer.Buffer], rax
0x180003e87  xorps   xmm0, xmm0
0x180003e8a  lea     rax, [rsp+600h+var_590]
0x180003e8f  mov     [rbp+500h+Buffer.StaticSize], rcx
0x180003e96  mov     [rbp+500h+Buffer.StaticBuffer], rax
0x180003e9d  lea     rcx, [rsp+600h+DestinationString]; DestinationString
0x180003ea2  lea     rax, [rsp+600h+var_590]
0x180003ea7  mov     rdx, r14; SourceString
0x180003eaa  mov     [rbp+500h+var_380], rax
0x180003eb1  xor     eax, eax
0x180003eb3  mov     [rsp+600h+var_590], ax
0x180003eb8  movups  xmmword ptr [rsp+600h+DestinationString.Length], xmm0
0x180003ebd  call    cs:__imp_RtlInitUnicodeString
0x180003ec3  movzx   r8d, [rsp+600h+DestinationString.Length]
0x180003ec9  xor     edx, edx
0x180003ecb  mov     word ptr [rbp+500h+var_388], dx
0x180003ed2  lea     rax, [r8+2]
0x180003ed6  cmp     rax, 0FFFEh
0x180003edc  ja      loc_180003FF7
0x180003ee2  cmp     rax, [rbp+500h+Buffer.Size]
0x180003ee9  jbe     short loc_180003F12
0x180003eeb  mov     r8, rax; RequiredSize
0x180003eee  lea     rdx, [rbp+500h+Buffer]; Buffer
0x180003ef5  xor     ecx, ecx; Flags
0x180003ef7  call    cs:__imp_RtlpEnsureBufferSize
0x180003efd  test    eax, eax
0x180003eff  js      loc_180003FFE
0x180003f05  movzx   edx, word ptr [rbp+500h+var_388]
0x180003f0c  movzx   r8d, [rsp+600h+DestinationString.Length]
0x180003f12  mov     rcx, [rbp+500h+Buffer.Buffer]
0x180003f19  movzx   eax, dx
0x180003f1c  mov     rdx, [rsp+600h+DestinationString.Buffer]; Src
0x180003f21  shr     rax, 1
0x180003f24  mov     [rbp+500h+var_380], rcx
0x180003f2b  movzx   r8d, r8w; Size
0x180003f2f  lea     rcx, [rcx+rax*2]; void *
0x180003f33  call    memmove_0
0x180003f38  movzx   eax, word ptr [rbp+500h+var_388]
0x180003f3f  add     ax, [rsp+600h+DestinationString.Length]
0x180003f44  movzx   edx, ax
0x180003f47  mov     word ptr [rbp+500h+var_388], dx
0x180003f4e  lea     eax, [rdx+2]
0x180003f51  shr     rdx, 1
0x180003f54  mov     word ptr [rbp+500h+var_388+2], ax
0x180003f5b  xor     ecx, ecx
0x180003f5d  mov     rax, [rbp+500h+var_380]
0x180003f64  mov     [rax+rdx*2], cx
0x180003f68  lea     rcx, [rsp+600h+var_590]; this
0x180003f6d  call    ?RemoveFileSpecAndBackslash@CPath@@QEAAJXZ; CPath::RemoveFileSpecAndBackslash(void)
0x180003f72  mov     ebx, eax
0x180003f74  test    eax, eax
0x180003f76  js      short loc_180003FE8
0x180003f78  lea     rcx, [rsp+600h+var_590]; this
0x180003f7d  mov     [rsp+600h+var_5D0], 0
0x180003f86  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180003f8b  mov     rcx, [rsp+600h+var_5C8]; struct IOfflineFilesService *
0x180003f90  lea     r9, _GUID_4a753da6_e044_4f12_a718_5d14d079a906; struct _GUID *
0x180003f97  mov     rdx, rax; unsigned __int16 *
0x180003f9a  lea     r8, [rbp+500h+Buffer.ReservedForIMalloc]; struct tagOFFLINEFILES_ITEM_DESCRIPTOR *
0x180003fa1  lea     rax, [rsp+600h+var_5D0]
0x180003fa6  mov     [rsp+600h+ppv], rax; void **
0x180003fab  call    ?COfflineFilesItem_CreateInstance@@YAJPEAUIOfflineFilesService@@PEBGAEBUtagOFFLINEFILES_ITEM_DESCRIPTOR@@AEBU_GUID@@PEAPEAX@Z; COfflineFilesItem_CreateInstance(IOfflineFilesService *,ushort const *,tagOFFLINEFILES_ITEM_DESCRIPTOR const &,_GUID const &,void * *)
0x180003fb0  mov     ebx, eax
0x180003fb2  test    eax, eax
0x180003fb4  js      short loc_180003FE8
0x180003fb6  mov     rax, [rsp+600h+var_5D0]
0x180003fbb  mov     [rsi], rax
0x180003fbe  jmp     short loc_180003FE8
0x180003fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fc7  lea     rax, WPP_GLOBAL_Control
0x180003fce  cmp     rcx, rax
0x180003fd1  jnz     short loc_180004005
0x180003fd3  mov     eax, 80004003h
0x180003fd8  jmp     loc_180003E44
0x180003fdd  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180003fe2  mov     ebx, eax
0x180003fe4  test    eax, eax
0x180003fe6  jns     short loc_180003F68
0x180003fe8  lea     rcx, [rsp+600h+var_590]; this
0x180003fed  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x180003ff2  jmp     loc_180003E18
0x180003ff7  mov     ecx, 0C0000106h; int
0x180003ffc  jmp     short loc_180003FDD
0x180003ffe  mov     ecx, 0C0000017h
0x180004003  jmp     short loc_180003FDD
0x180004005  test    byte ptr [rcx+1Ch], 2
0x180004009  jz      short loc_180003FD3
0x18000400b  mov     rcx, [rcx+10h]
0x18000400f  lea     r8, WPP_91a48976ead63973ddd357b80bae3284_Traceguids
0x180004016  mov     edx, 19h
0x18000401b  call    WPP_SF_
0x180004020  jmp     short loc_180003FD3
```
