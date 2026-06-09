# COfflineFilesItem::_CreateItemEnumerator(IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,ulong,ulong,IEnumOfflineFilesItems * *)

- ea: `0x180004cf0`
- end: `0x1800052ab`
- name: `?_CreateItemEnumerator@COfflineFilesItem@@IEAAJPEAUIOfflineFilesItemFilter@@000KKPEAPEAUIEnumOfflineFilesItems@@@Z`
- size: `1467`
- prototype: `__int64 __fastcall(COfflineFilesItem *__hidden this, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, unsigned int, unsigned int, struct IEnumOfflineFilesItems **)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f930`
- `0x18000f940`

## callees

- `0x180004cf0`
- `0x180005410`
- `0x18000b390`
- `0x18000b7c0`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800102a8`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180005269`
- `ntdll!RtlFreeUnicodeString` at `0x180005269`
- `ntdll!RtlpEnsureBufferSize` at `0x180004ea2`
- `ntdll!RtlpEnsureBufferSize` at `0x180005139`
- `ntdll!RtlpEnsureBufferSize` at `0x180004ea2`
- `ntdll!RtlpEnsureBufferSize` at `0x180005139`
- `ntdll!RtlAppendPathElement` at `0x180004f4f`
- `ntdll!RtlAppendPathElement` at `0x180004f4f`
- `ntdll!RtlpApplyLengthFunction` at `0x180004f81`
- `ntdll!RtlpApplyLengthFunction` at `0x180004f81`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180004f6a`
- `ntdll!RtlInitUnicodeString` at `0x180004e67`
- `ntdll!RtlInitUnicodeString` at `0x180004f38`
- `ntdll!RtlInitUnicodeString` at `0x1800050f7`
- `ntdll!RtlInitUnicodeString` at `0x180004e67`
- `ntdll!RtlInitUnicodeString` at `0x180004f38`
- `ntdll!RtlInitUnicodeString` at `0x1800050f7`

## pseudocode

```c
__int64 __fastcall COfflineFilesItem::_CreateItemEnumerator(
        COfflineFilesItem *this,
        struct IOfflineFilesItemFilter *a2,
        struct IOfflineFilesItemFilter *a3,
        struct IOfflineFilesItemFilter *a4,
        struct IOfflineFilesItemFilter *a5,
        unsigned int a6,
        unsigned int a7,
        struct IEnumOfflineFilesItems **a8)
{
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rdx
  const WCHAR *v15; // rdx
  USHORT Length; // r9
  unsigned __int16 v17; // dx
  unsigned __int64 v18; // r8
  int v19; // ecx
  int v20; // edi
  unsigned __int64 v21; // rdx
  int appended; // eax
  NTSTATUS v23; // eax
  PUCHAR v24; // rcx
  __int64 v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rbx
  __int64 v28; // rdx
  struct IOfflineFilesItemFilter *v29; // rcx
  __int64 v30; // rsi
  const WCHAR *v31; // rdx
  __int64 v32; // r8
  int v33; // ecx
  __int64 v34; // rcx
  PWSTR v35; // rdx
  unsigned __int64 v36; // rax
  __int64 v37; // rcx
  unsigned __int64 v38; // r8
  unsigned int v39; // edx
  unsigned int v40; // r8d
  int v41; // r9d
  unsigned int v42; // ebx
  PUCHAR StaticBuffer; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h]
  struct IOfflineFilesItemFilter *v46; // [rsp+58h] [rbp-A8h]
  _WORD v47[260]; // [rsp+60h] [rbp-A0h] BYREF
  int UnicodeStringOrUnicodeStringBuffer; // [rsp+268h] [rbp+168h] BYREF
  PUCHAR v49; // [rsp+270h] [rbp+170h]
  struct _RTL_BUFFER Buffer; // [rsp+278h] [rbp+178h] BYREF

  v46 = a2;
  if ( !a8 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_1c311fa2e65f36529bf5a765a9f50f48_Traceguids);
    return 2147500035LL;
  }
  v12 = a6 & 0xFFFFFFFC;
  if ( (a6 & 0xFFFFFFFC) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      return 2147942487LL;
    v14 = 12;
LABEL_14:
    WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_1c311fa2e65f36529bf5a765a9f50f48_Traceguids, v12);
    return 2147942487LL;
  }
  v12 = a7 & 0x7FFFFFC0;
  if ( (a7 & 0x7FFFFFC0) != 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      return 2147942487LL;
    v14 = 13;
    goto LABEL_14;
  }
  v15 = (const WCHAR *)*((_QWORD *)this + 70);
  Buffer.Buffer = (PUCHAR)v47;
  Buffer.StaticBuffer = (PUCHAR)v47;
  v49 = (PUCHAR)v47;
  Buffer.Size = 520;
  Buffer.StaticSize = 520;
  v47[0] = 0;
  UnicodeStringOrUnicodeStringBuffer = 34078720;
  if ( v15 == *((const WCHAR **)this + 71) )
    v15 = (const WCHAR *)*((_QWORD *)this + 69);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v15);
  Length = DestinationString.Length;
  v17 = 0;
  LOWORD(UnicodeStringOrUnicodeStringBuffer) = 0;
  v18 = DestinationString.Length + 2LL;
  if ( v18 > 0xFFFE )
  {
    v19 = -1073741562;
    goto LABEL_23;
  }
  if ( v18 <= Buffer.Size )
  {
LABEL_26:
    v49 = Buffer.Buffer;
    memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v17 >> 1)], DestinationString.Buffer, Length);
    v21 = (unsigned __int16)(DestinationString.Length + UnicodeStringOrUnicodeStringBuffer);
    LOWORD(UnicodeStringOrUnicodeStringBuffer) = v21;
    HIWORD(UnicodeStringOrUnicodeStringBuffer) = v21 + 2;
    *(_WORD *)&v49[2 * (v21 >> 1)] = 0;
    goto LABEL_27;
  }
  if ( RtlpEnsureBufferSize(0, &Buffer, v18) >= 0 )
  {
    v17 = UnicodeStringOrUnicodeStringBuffer;
    Length = DestinationString.Length;
    goto LABEL_26;
  }
  v19 = -1073741801;
LABEL_23:
  v20 = ResultFromNtStatus(v19);
  if ( v20 < 0 )
    goto LABEL_60;
LABEL_27:
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 407);
  appended = RtlAppendPathElement(1, &UnicodeStringOrUnicodeStringBuffer, &DestinationString);
  if ( appended < 0 )
  {
    v20 = ResultFromNtStatus(appended);
    if ( v20 < 0 )
      goto LABEL_60;
  }
  v20 = 0;
  v23 = RtlpApplyLengthFunction(
          0,
          0x38u,
          &UnicodeStringOrUnicodeStringBuffer,
          RtlGetLengthWithoutTrailingPathSeperators);
  if ( v23 < 0 )
    v20 = ResultFromNtStatus(v23);
  if ( v20 < 0 )
    goto LABEL_60;
  v20 = -2147024882;
  v24 = v49;
  if ( Buffer.Buffer != Buffer.StaticBuffer )
    v24 = Buffer.Buffer;
  v25 = *((_QWORD *)this + 2);
  *(_QWORD *)&DestinationString.Length = v24;
  v45 = v25;
  *a8 = 0;
  v26 = operator new(0x288u);
  v27 = v26;
  if ( !v26 )
    goto LABEL_60;
  v28 = v45;
  v26[2] = v45;
  *((_DWORD *)v26 + 2) = 1;
  *v26 = &CEnumOfflineFilesItems::`vftable';
  v26[3] = 0;
  v26[71] = v26 + 4;
  v26[73] = 520;
  v26[72] = v26 + 4;
  v26[74] = 520;
  v26[70] = v26 + 4;
  if ( v26 != (_QWORD *)-32LL )
    *((_WORD *)v26 + 16) = 0;
  *((_DWORD *)v26 + 138) = 34078720;
  *((_DWORD *)v26 + 153) = a7;
  *((_DWORD *)v26 + 152) = a6;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  v29 = v46;
  v27[77] = v46;
  v27[78] = a3;
  v27[79] = a4;
  v27[80] = a5;
  if ( v29 )
    ((void (__fastcall *)(struct IOfflineFilesItemFilter *))v29->lpVtbl->AddRef)(v29);
  if ( a3 )
    ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a3->lpVtbl->AddRef)(a3);
  if ( a4 )
    ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a4->lpVtbl->AddRef)(a4);
  if ( a5 )
    ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a5->lpVtbl->AddRef)(a5);
  v30 = *(_QWORD *)&DestinationString.Length;
  if ( !*(_QWORD *)&DestinationString.Length )
    goto LABEL_56;
  v31 = *(const WCHAR **)&DestinationString.Length;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v31);
  v32 = DestinationString.Length;
  *((_WORD *)v27 + 276) = 0;
  if ( (unsigned __int64)(v32 + 2) > 0xFFFE )
  {
    v33 = -1073741562;
    goto LABEL_52;
  }
  if ( v27 != (_QWORD *)-568LL && (unsigned __int64)(v32 + 2) <= v27[73] )
  {
LABEL_55:
    v34 = v27[71];
    v35 = DestinationString.Buffer;
    v36 = (unsigned __int64)*((unsigned __int16 *)v27 + 276) >> 1;
    v27[70] = v34;
    memmove_0((void *)(v34 + 2 * v36), v35, (unsigned __int16)v32);
    v37 = v27[70];
    v38 = (unsigned __int16)(*((_WORD *)v27 + 276) + DestinationString.Length);
    *((_WORD *)v27 + 276) = v38;
    *((_WORD *)v27 + 277) = v38 + 2;
    *(_WORD *)(v37 + 2 * (v38 >> 1)) = 0;
    goto LABEL_56;
  }
  if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)(v27 + 71), v32 + 2) >= 0 )
  {
    LOWORD(v32) = DestinationString.Length;
    goto LABEL_55;
  }
  v33 = -1073741801;
LABEL_52:
  v20 = ResultFromNtStatus(v33);
  if ( v20 >= 0 )
  {
LABEL_56:
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, _QWORD, _DWORD, _QWORD *))(*(_QWORD *)v27[2] + 112LL))(
            v27[2],
            v27 + 77,
            v30,
            *((unsigned int *)v27 + 152),
            *((_DWORD *)v27 + 153),
            v27 + 3);
    if ( v20 >= 0 )
    {
      v20 = CscCom_SetClientProxyBlanket((IUnknown *)v27[3], v39, v40, v41);
      if ( v20 >= 0 )
        v20 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct IEnumOfflineFilesItems **))*v27)(
                v27,
                &IID_IEnumOfflineFilesItems,
                a8);
    }
  }
  (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
LABEL_60:
  v42 = 0;
  StaticBuffer = Buffer.StaticBuffer;
  if ( v20 < 0 )
    v42 = v20;
  if ( Buffer.Buffer && Buffer.Buffer != Buffer.StaticBuffer )
  {
    DestinationString.Buffer = (PWSTR)Buffer.Buffer;
    *(_QWORD *)&DestinationString.Length = 0;
    RtlFreeUnicodeString(&DestinationString);
    StaticBuffer = Buffer.StaticBuffer;
  }
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  return v42;
}

```

## disassembly

```asm
0x180004cf0  push    rbp
0x180004cf2  push    rbx
0x180004cf3  push    r12
0x180004cf5  push    r13
0x180004cf7  push    r14
0x180004cf9  push    r15
0x180004cfb  lea     rbp, [rsp-1C8h]
0x180004d03  sub     rsp, 2C8h
0x180004d0a  mov     rax, cs:__security_cookie
0x180004d11  xor     rax, rsp
0x180004d14  mov     [rbp+1F0h+Buffer.ReservedForIMalloc], rax
0x180004d1b  mov     r14, [rbp+1F0h+arg_38]
0x180004d22  mov     r12, r9
0x180004d25  mov     r13, [rbp+1F0h+arg_20]
0x180004d2c  mov     r15, r8
0x180004d2f  mov     [rsp+2F0h+var_298], rdx
0x180004d34  mov     rbx, rcx
0x180004d37  test    r14, r14
0x180004d3a  jnz     short loc_180004D74
0x180004d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d43  lea     rax, WPP_GLOBAL_Control
0x180004d4a  cmp     rcx, rax
0x180004d4d  jz      short loc_180004D6A
0x180004d4f  test    byte ptr [rcx+1Ch], 2
0x180004d53  jz      short loc_180004D6A
0x180004d55  mov     rcx, [rcx+10h]
0x180004d59  lea     r8, WPP_1c311fa2e65f36529bf5a765a9f50f48_Traceguids
0x180004d60  mov     edx, 0Bh
0x180004d65  call    WPP_SF_
0x180004d6a  mov     eax, 80004003h
0x180004d6f  jmp     loc_18000528A
0x180004d74  mov     [rsp+2F0h+var_30], rsi
0x180004d7c  mov     esi, [rbp+1F0h+arg_28]
0x180004d82  mov     r9d, esi
0x180004d85  and     r9d, 0FFFFFFFCh
0x180004d89  jz      short loc_180004DAB
0x180004d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d92  lea     rax, WPP_GLOBAL_Control
0x180004d99  cmp     rcx, rax
0x180004d9c  jz      short loc_180004DE9
0x180004d9e  test    byte ptr [rcx+1Ch], 2
0x180004da2  jz      short loc_180004DE9
0x180004da4  mov     edx, 0Ch
0x180004da9  jmp     short loc_180004DD9
0x180004dab  mov     r9d, [rbp+1F0h+arg_30]
0x180004db2  and     r9d, 7FFFFFC0h
0x180004db9  jz      short loc_180004DF3
0x180004dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dc2  lea     rax, WPP_GLOBAL_Control
0x180004dc9  cmp     rcx, rax
0x180004dcc  jz      short loc_180004DE9
0x180004dce  test    byte ptr [rcx+1Ch], 2
0x180004dd2  jz      short loc_180004DE9
0x180004dd4  mov     edx, 0Dh
0x180004dd9  mov     rcx, [rcx+10h]
0x180004ddd  lea     r8, WPP_1c311fa2e65f36529bf5a765a9f50f48_Traceguids
0x180004de4  call    WPP_SF_d
0x180004de9  mov     eax, 80070057h
0x180004dee  jmp     loc_180005282
0x180004df3  mov     rdx, [rbx+230h]
0x180004dfa  lea     rax, [rsp+2F0h+var_290]
0x180004dff  mov     [rbp+1F0h+Buffer.Buffer], rax
0x180004e06  mov     ecx, 208h
0x180004e0b  lea     rax, [rsp+2F0h+var_290]
0x180004e10  mov     [rsp+2F0h+var_38], rdi
0x180004e18  mov     [rbp+1F0h+Buffer.StaticBuffer], rax
0x180004e1f  lea     rax, [rsp+2F0h+var_290]
0x180004e24  mov     [rbp+1F0h+var_80], rax
0x180004e2b  xor     eax, eax
0x180004e2d  mov     [rbp+1F0h+Buffer.Size], rcx
0x180004e34  mov     [rbp+1F0h+Buffer.StaticSize], rcx
0x180004e3b  mov     [rsp+2F0h+var_290], ax
0x180004e40  mov     [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer], 2080000h
0x180004e4a  cmp     rdx, [rbx+238h]
0x180004e51  jnz     short loc_180004E5A
0x180004e53  mov     rdx, [rbx+228h]; SourceString
0x180004e5a  xorps   xmm0, xmm0
0x180004e5d  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x180004e62  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x180004e67  call    cs:__imp_RtlInitUnicodeString
0x180004e6d  movzx   r9d, [rsp+2F0h+DestinationString.Length]
0x180004e73  xor     edx, edx
0x180004e75  mov     word ptr [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer], dx
0x180004e7c  lea     r8, [r9+2]; RequiredSize
0x180004e80  cmp     r8, 0FFFEh
0x180004e87  jbe     short loc_180004E90
0x180004e89  mov     ecx, 0C0000106h
0x180004e8e  jmp     short loc_180004EB1
0x180004e90  cmp     r8, [rbp+1F0h+Buffer.Size]
0x180004e97  jbe     short loc_180004ECE
0x180004e99  lea     rdx, [rbp+1F0h+Buffer]; Buffer
0x180004ea0  xor     ecx, ecx; Flags
0x180004ea2  call    cs:__imp_RtlpEnsureBufferSize
0x180004ea8  test    eax, eax
0x180004eaa  jns     short loc_180004EC1
0x180004eac  mov     ecx, 0C0000017h; int
0x180004eb1  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180004eb6  mov     edi, eax
0x180004eb8  test    eax, eax
0x180004eba  jns     short loc_180004F24
0x180004ebc  jmp     loc_18000522F
0x180004ec1  movzx   edx, word ptr [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer]
0x180004ec8  movzx   r9d, [rsp+2F0h+DestinationString.Length]
0x180004ece  mov     rcx, [rbp+1F0h+Buffer.Buffer]
0x180004ed5  movzx   eax, dx
0x180004ed8  mov     rdx, [rsp+2F0h+DestinationString.Buffer]; Src
0x180004edd  shr     rax, 1
0x180004ee0  mov     [rbp+1F0h+var_80], rcx
0x180004ee7  movzx   r8d, r9w; Size
0x180004eeb  lea     rcx, [rcx+rax*2]; void *
0x180004eef  call    memmove_0
0x180004ef4  movzx   eax, word ptr [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer]
0x180004efb  add     ax, [rsp+2F0h+DestinationString.Length]
0x180004f00  movzx   edx, ax
0x180004f03  mov     word ptr [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer], dx
0x180004f0a  lea     eax, [rdx+2]
0x180004f0d  shr     rdx, 1
0x180004f10  mov     word ptr [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180004f17  xor     ecx, ecx
0x180004f19  mov     rax, [rbp+1F0h+var_80]
0x180004f20  mov     [rax+rdx*2], cx
0x180004f24  xorps   xmm0, xmm0
0x180004f27  lea     rdx, [rbx+32Eh]; SourceString
0x180004f2e  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x180004f33  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x180004f38  call    cs:__imp_RtlInitUnicodeString
0x180004f3e  lea     r8, [rsp+2F0h+DestinationString]
0x180004f43  mov     ecx, 1
0x180004f48  lea     rdx, [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer]
0x180004f4f  call    cs:__imp_RtlAppendPathElement
0x180004f55  test    eax, eax
0x180004f57  jns     short loc_180004F6A
0x180004f59  mov     ecx, eax; int
0x180004f5b  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180004f60  mov     edi, eax
0x180004f62  test    eax, eax
0x180004f64  js      loc_18000522F
0x180004f6a  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180004f71  lea     r8, [rbp+1F0h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x180004f78  mov     edx, 38h ; '8'; Type
0x180004f7d  xor     ecx, ecx; Flags
0x180004f7f  xor     edi, edi
0x180004f81  call    cs:__imp_RtlpApplyLengthFunction
0x180004f87  test    eax, eax
0x180004f89  jns     short loc_180004F94
0x180004f8b  mov     ecx, eax; int
0x180004f8d  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180004f92  mov     edi, eax
0x180004f94  test    edi, edi
0x180004f96  js      loc_18000522F
0x180004f9c  mov     rax, [rbp+1F0h+Buffer.Buffer]
0x180004fa3  mov     edi, 8007000Eh
0x180004fa8  cmp     rax, [rbp+1F0h+Buffer.StaticBuffer]
0x180004faf  mov     rcx, [rbp+1F0h+var_80]
0x180004fb6  cmovnz  rcx, rax
0x180004fba  mov     rax, [rbx+10h]
0x180004fbe  mov     qword ptr [rsp+2F0h+DestinationString.Length], rcx
0x180004fc3  mov     ecx, 288h; Size
0x180004fc8  mov     [rsp+2F0h+var_2A0], rax
0x180004fcd  mov     qword ptr [r14], 0
0x180004fd4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004fd9  mov     rbx, rax
0x180004fdc  test    rax, rax
0x180004fdf  jz      loc_18000522F
0x180004fe5  mov     rdx, [rsp+2F0h+var_2A0]
0x180004fea  lea     rcx, [rbx+20h]
0x180004fee  mov     [rbx+10h], rdx
0x180004ff2  mov     r8d, 208h
0x180004ff8  mov     dword ptr [rbx+8], 1
0x180004fff  lea     rax, ??_7CEnumOfflineFilesItems@@6B@; const CEnumOfflineFilesItems::`vftable'
0x180005006  mov     [rbx], rax
0x180005009  mov     qword ptr [rbx+18h], 0
0x180005011  mov     [rbx+238h], rcx
0x180005018  mov     [rbx+248h], r8
0x18000501f  mov     [rbx+240h], rcx
0x180005026  mov     [rbx+250h], r8
0x18000502d  mov     [rbx+230h], rcx
0x180005034  test    rcx, rcx
0x180005037  jz      short loc_18000503E
0x180005039  xor     eax, eax
0x18000503b  mov     [rcx], ax
0x18000503e  mov     eax, [rbp+1F0h+arg_30]
0x180005044  mov     rcx, rdx
0x180005047  mov     dword ptr [rbx+228h], 2080000h
0x180005051  mov     [rbx+264h], eax
0x180005057  mov     [rbx+260h], esi
0x18000505d  mov     rax, [rdx]
0x180005060  mov     rax, [rax+8]
0x180005064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005069  mov     rcx, [rsp+2F0h+var_298]
0x18000506e  mov     [rbx+268h], rcx
0x180005075  mov     [rbx+270h], r15
0x18000507c  mov     [rbx+278h], r12
0x180005083  mov     [rbx+280h], r13
0x18000508a  test    rcx, rcx
0x18000508d  jz      short loc_18000509B
0x18000508f  mov     rax, [rcx]
0x180005092  mov     rax, [rax+8]
0x180005096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509b  test    r15, r15
0x18000509e  jz      short loc_1800050AF
0x1800050a0  mov     rax, [r15]
0x1800050a3  mov     rcx, r15
0x1800050a6  mov     rax, [rax+8]
0x1800050aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050af  test    r12, r12
0x1800050b2  jz      short loc_1800050C4
0x1800050b4  mov     rax, [r12]
0x1800050b8  mov     rcx, r12
0x1800050bb  mov     rax, [rax+8]
0x1800050bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c4  test    r13, r13
0x1800050c7  jz      short loc_1800050D9
0x1800050c9  mov     rax, [r13+0]
0x1800050cd  mov     rcx, r13
0x1800050d0  mov     rax, [rax+8]
0x1800050d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d9  mov     rsi, qword ptr [rsp+2F0h+DestinationString.Length]
0x1800050de  test    rsi, rsi
0x1800050e1  jz      loc_1800051BC
0x1800050e7  xorps   xmm0, xmm0
0x1800050ea  lea     rcx, [rsp+2F0h+DestinationString]; DestinationString
0x1800050ef  mov     rdx, rsi; SourceString
0x1800050f2  movups  xmmword ptr [rsp+2F0h+DestinationString.Length], xmm0
0x1800050f7  call    cs:__imp_RtlInitUnicodeString
0x1800050fd  movzx   r8d, [rsp+2F0h+DestinationString.Length]
0x180005103  xor     eax, eax
0x180005105  mov     [rbx+228h], ax
0x18000510c  lea     rax, [r8+2]
0x180005110  cmp     rax, 0FFFEh
0x180005116  jbe     short loc_18000511F
0x180005118  mov     ecx, 0C0000106h
0x18000511d  jmp     short loc_180005148
0x18000511f  lea     rdx, [rbx+238h]; Buffer
0x180005126  test    rdx, rdx
0x180005129  jz      short loc_180005134
0x18000512b  cmp     rax, [rbx+248h]
0x180005132  jbe     short loc_18000515E
0x180005134  mov     r8, rax; RequiredSize
0x180005137  xor     ecx, ecx; Flags
0x180005139  call    cs:__imp_RtlpEnsureBufferSize
0x18000513f  test    eax, eax
0x180005141  jns     short loc_180005158
0x180005143  mov     ecx, 0C0000017h; int
0x180005148  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000514d  mov     edi, eax
0x18000514f  test    eax, eax
0x180005151  jns     short loc_1800051BC
0x180005153  jmp     loc_180005220
0x180005158  movzx   r8d, [rsp+2F0h+DestinationString.Length]
0x18000515e  mov     rcx, [rbx+238h]
0x180005165  movzx   eax, word ptr [rbx+228h]
0x18000516c  mov     rdx, [rsp+2F0h+DestinationString.Buffer]; Src
0x180005171  shr     rax, 1
0x180005174  mov     [rbx+230h], rcx
0x18000517b  movzx   r8d, r8w; Size
0x18000517f  lea     rcx, [rcx+rax*2]; void *
0x180005183  call    memmove_0
0x180005188  movzx   eax, [rsp+2F0h+DestinationString.Length]
0x18000518d  add     ax, [rbx+228h]
0x180005194  mov     rcx, [rbx+230h]
0x18000519b  movzx   r8d, ax
0x18000519f  mov     [rbx+228h], r8w
0x1800051a7  lea     eax, [r8+2]
0x1800051ab  shr     r8, 1
0x1800051ae  mov     [rbx+22Ah], ax
0x1800051b5  xor     eax, eax
0x1800051b7  mov     [rcx+r8*2], ax
0x1800051bc  mov     r8d, [rbx+264h]
0x1800051c3  lea     r15, [rbx+18h]
0x1800051c7  mov     rcx, [rbx+10h]
0x1800051cb  lea     rdx, [rbx+268h]
0x1800051d2  mov     r9d, [rbx+260h]
0x1800051d9  mov     [rsp+2F0h+var_2C8], r15
0x1800051de  mov     [rsp+2F0h+var_2D0], r8d
0x1800051e3  mov     r8, rsi
0x1800051e6  mov     rax, [rcx]
0x1800051e9  mov     rax, [rax+70h]
0x1800051ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f2  mov     edi, eax
0x1800051f4  test    eax, eax
0x1800051f6  js      short loc_180005220
0x1800051f8  mov     rcx, [r15]; pProxy
0x1800051fb  call    ?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z; CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)
0x180005200  mov     edi, eax
0x180005202  test    eax, eax
0x180005204  js      short loc_180005220
0x180005206  mov     rax, [rbx]
0x180005209  lea     rdx, IID_IEnumOfflineFilesItems
0x180005210  mov     r8, r14
0x180005213  mov     rcx, rbx
0x180005216  mov     rax, [rax]
0x180005219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000521e  mov     edi, eax
0x180005220  mov     rax, [rbx]
0x180005223  mov     rcx, rbx
0x180005226  mov     rax, [rax+10h]
0x18000522a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000522f  mov     rcx, [rbp+1F0h+Buffer.Buffer]
0x180005236  xor     ebx, ebx
  ... truncated ...
```
