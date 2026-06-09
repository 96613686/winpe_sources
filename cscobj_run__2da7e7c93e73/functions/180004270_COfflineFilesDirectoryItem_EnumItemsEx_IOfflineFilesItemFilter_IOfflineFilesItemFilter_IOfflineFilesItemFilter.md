# COfflineFilesDirectoryItem::EnumItemsEx(IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,IOfflineFilesItemFilter *,ulong,ulong,IEnumOfflineFilesItems * *)

- ea: `0x180004270`
- end: `0x1800046b6`
- name: `?EnumItemsEx@COfflineFilesDirectoryItem@@UEAAJPEAUIOfflineFilesItemFilter@@000KKPEAPEAUIEnumOfflineFilesItems@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(COfflineFilesDirectoryItem *__hidden this, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, struct IOfflineFilesItemFilter *, unsigned int, unsigned int, struct IEnumOfflineFilesItems **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180004270`
- `0x1800046c0`
- `0x1800052c0`
- `0x18000b390`
- `0x18000b7c0`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800102a8`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180004417`
- `ntdll!RtlpEnsureBufferSize` at `0x180004417`
- `ntdll!RtlAppendPathElement` at `0x1800044c4`
- `ntdll!RtlAppendPathElement` at `0x1800044c4`
- `ntdll!RtlpApplyLengthFunction` at `0x1800044f4`
- `ntdll!RtlpApplyLengthFunction` at `0x1800044f4`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x1800044df`
- `ntdll!RtlInitUnicodeString` at `0x1800043dc`
- `ntdll!RtlInitUnicodeString` at `0x1800044ad`
- `ntdll!RtlInitUnicodeString` at `0x1800043dc`
- `ntdll!RtlInitUnicodeString` at `0x1800044ad`

## pseudocode

```c
__int64 __fastcall COfflineFilesDirectoryItem::EnumItemsEx(
        COfflineFilesDirectoryItem *this,
        struct IOfflineFilesItemFilter *a2,
        struct IOfflineFilesItemFilter *a3,
        struct IOfflineFilesItemFilter *a4,
        struct IOfflineFilesItemFilter *a5,
        unsigned int a6,
        unsigned int a7,
        struct IEnumOfflineFilesItems **a8)
{
  __int64 result; // rax
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
  const unsigned __int16 *v24; // r13
  __int64 v25; // r15
  CEnumOfflineFilesItems *v26; // rax
  CEnumOfflineFilesItems *v27; // rbx
  struct IOfflineFilesItemFilter *v28; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-E0h] BYREF
  struct IEnumOfflineFilesItems **v30; // [rsp+30h] [rbp-D0h]
  struct IOfflineFilesItemFilter *v31; // [rsp+38h] [rbp-C8h]
  _WORD v32[260]; // [rsp+40h] [rbp-C0h] BYREF
  int UnicodeStringOrUnicodeStringBuffer; // [rsp+248h] [rbp+148h] BYREF
  PUCHAR v34; // [rsp+250h] [rbp+150h]
  struct _RTL_BUFFER Buffer; // [rsp+258h] [rbp+158h] BYREF

  v31 = a2;
  v30 = a8;
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
LABEL_10:
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
    goto LABEL_10;
  }
  v15 = (const WCHAR *)*((_QWORD *)this + 80);
  Buffer.Buffer = (PUCHAR)v32;
  Buffer.Size = 520;
  Buffer.StaticBuffer = (PUCHAR)v32;
  v34 = (PUCHAR)v32;
  Buffer.StaticSize = 520;
  v32[0] = 0;
  UnicodeStringOrUnicodeStringBuffer = 34078720;
  if ( v15 == *((const WCHAR **)this + 81) )
    v15 = (const WCHAR *)*((_QWORD *)this + 79);
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
    v34 = Buffer.Buffer;
    memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v17 >> 1)], DestinationString.Buffer, Length);
    v21 = (unsigned __int16)(DestinationString.Length + UnicodeStringOrUnicodeStringBuffer);
    LOWORD(UnicodeStringOrUnicodeStringBuffer) = v21;
    HIWORD(UnicodeStringOrUnicodeStringBuffer) = v21 + 2;
    *(_WORD *)&v34[2 * (v21 >> 1)] = 0;
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
  if ( v20 >= 0 )
  {
LABEL_27:
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)this + 447);
    appended = RtlAppendPathElement(1, &UnicodeStringOrUnicodeStringBuffer, &DestinationString);
    if ( appended >= 0 || (v20 = ResultFromNtStatus(appended), v20 >= 0) )
    {
      v20 = 0;
      v23 = RtlpApplyLengthFunction(
              0,
              0x38u,
              &UnicodeStringOrUnicodeStringBuffer,
              RtlGetLengthWithoutTrailingPathSeperators);
      if ( v23 < 0 )
        v20 = ResultFromNtStatus(v23);
      if ( v20 >= 0 )
      {
        v20 = -2147024882;
        v24 = (const unsigned __int16 *)v34;
        v25 = *((_QWORD *)this + 12);
        if ( Buffer.Buffer != Buffer.StaticBuffer )
          v24 = (const unsigned __int16 *)Buffer.Buffer;
        *v30 = 0;
        v26 = (CEnumOfflineFilesItems *)operator new(0x288u);
        v27 = v26;
        if ( v26 )
        {
          *((_DWORD *)v26 + 2) = 1;
          *((_QWORD *)v26 + 2) = v25;
          *((_QWORD *)v26 + 3) = 0;
          *(_QWORD *)v26 = &CEnumOfflineFilesItems::`vftable';
          *((_QWORD *)v26 + 71) = (char *)v26 + 32;
          *((_QWORD *)v26 + 73) = 520;
          *((_QWORD *)v26 + 72) = (char *)v26 + 32;
          *((_QWORD *)v26 + 74) = 520;
          *((_QWORD *)v26 + 70) = (char *)v26 + 32;
          if ( v26 != (CEnumOfflineFilesItems *)-32LL )
            *((_WORD *)v26 + 16) = 0;
          *((_DWORD *)v26 + 138) = 34078720;
          *((_DWORD *)v26 + 152) = a6;
          *((_DWORD *)v26 + 153) = a7;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
          v28 = v31;
          *((_QWORD *)v27 + 77) = v31;
          *((_QWORD *)v27 + 78) = a3;
          *((_QWORD *)v27 + 79) = a4;
          *((_QWORD *)v27 + 80) = a5;
          if ( v28 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))v28->lpVtbl->AddRef)(v28);
          if ( a3 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a3->lpVtbl->AddRef)(a3);
          if ( a4 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a4->lpVtbl->AddRef)(a4);
          if ( a5 )
            ((void (__fastcall *)(struct IOfflineFilesItemFilter *))a5->lpVtbl->AddRef)(a5);
          v20 = CEnumOfflineFilesItems::_Initialize(v27, v24);
          if ( v20 >= 0 )
            v20 = (**(__int64 (__fastcall ***)(CEnumOfflineFilesItems *, GUID *, struct IEnumOfflineFilesItems **))v27)(
                    v27,
                    &IID_IEnumOfflineFilesItems,
                    v30);
          (*(void (__fastcall **)(CEnumOfflineFilesItems *))(*(_QWORD *)v27 + 16LL))(v27);
        }
      }
    }
  }
  CPath::~CPath((CPath *)v32);
  result = 0;
  if ( v20 < 0 )
    return (unsigned int)v20;
  return result;
}

```

## disassembly

```asm
0x180004270  push    rbp
0x180004272  push    rbx
0x180004273  push    rsi
0x180004274  push    rdi
0x180004275  push    r12
0x180004277  push    r13
0x180004279  push    r14
0x18000427b  push    r15
0x18000427d  lea     rbp, [rsp-198h]
0x180004285  sub     rsp, 298h
0x18000428c  mov     rax, cs:__security_cookie
0x180004293  xor     rax, rsp
0x180004296  mov     [rbp+1D0h+Buffer.ReservedForIMalloc], rax
0x18000429d  mov     rax, [rbp+1D0h+arg_38]
0x1800042a4  mov     r14, r9
0x1800042a7  mov     rsi, [rbp+1D0h+arg_20]
0x1800042ae  mov     r12, r8
0x1800042b1  mov     [rsp+2D0h+var_298], rdx
0x1800042b6  mov     rbx, rcx
0x1800042b9  mov     [rsp+2D0h+var_2A0], rax
0x1800042be  test    rax, rax
0x1800042c1  jnz     short loc_1800042FB
0x1800042c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042ca  lea     rax, WPP_GLOBAL_Control
0x1800042d1  cmp     rcx, rax
0x1800042d4  jz      short loc_1800042F1
0x1800042d6  test    byte ptr [rcx+1Ch], 2
0x1800042da  jz      short loc_1800042F1
0x1800042dc  mov     rcx, [rcx+10h]
0x1800042e0  lea     r8, WPP_1c311fa2e65f36529bf5a765a9f50f48_Traceguids
0x1800042e7  mov     edx, 0Bh
0x1800042ec  call    WPP_SF_
0x1800042f1  mov     eax, 80004003h
0x1800042f6  jmp     loc_180004693
0x1800042fb  mov     r9d, [rbp+1D0h+arg_28]
0x180004302  and     r9d, 0FFFFFFFCh
0x180004306  jz      short loc_180004340
0x180004308  mov     rcx, cs:WPP_GLOBAL_Control
0x18000430f  lea     rax, WPP_GLOBAL_Control
0x180004316  cmp     rcx, rax
0x180004319  jz      short loc_180004336
0x18000431b  test    byte ptr [rcx+1Ch], 2
0x18000431f  jz      short loc_180004336
0x180004321  mov     edx, 0Ch
0x180004326  mov     rcx, [rcx+10h]
0x18000432a  lea     r8, WPP_1c311fa2e65f36529bf5a765a9f50f48_Traceguids
0x180004331  call    WPP_SF_d
0x180004336  mov     eax, 80070057h
0x18000433b  jmp     loc_180004693
0x180004340  mov     r9d, [rbp+1D0h+arg_30]
0x180004347  and     r9d, 7FFFFFC0h
0x18000434e  jz      short loc_180004370
0x180004350  mov     rcx, cs:WPP_GLOBAL_Control
0x180004357  lea     rax, WPP_GLOBAL_Control
0x18000435e  cmp     rcx, rax
0x180004361  jz      short loc_180004336
0x180004363  test    byte ptr [rcx+1Ch], 2
0x180004367  jz      short loc_180004336
0x180004369  mov     edx, 0Dh
0x18000436e  jmp     short loc_180004326
0x180004370  mov     rdx, [rbx+280h]
0x180004377  lea     rax, [rsp+2D0h+var_290]
0x18000437c  mov     [rbp+1D0h+Buffer.Buffer], rax
0x180004383  mov     ecx, 208h
0x180004388  lea     rax, [rsp+2D0h+var_290]
0x18000438d  mov     [rbp+1D0h+Buffer.Size], rcx
0x180004394  mov     [rbp+1D0h+Buffer.StaticBuffer], rax
0x18000439b  lea     rax, [rsp+2D0h+var_290]
0x1800043a0  mov     [rbp+1D0h+var_80], rax
0x1800043a7  xor     eax, eax
0x1800043a9  mov     [rbp+1D0h+Buffer.StaticSize], rcx
0x1800043b0  mov     [rsp+2D0h+var_290], ax
0x1800043b5  mov     [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer], 2080000h
0x1800043bf  cmp     rdx, [rbx+288h]
0x1800043c6  jnz     short loc_1800043CF
0x1800043c8  mov     rdx, [rbx+278h]; SourceString
0x1800043cf  xorps   xmm0, xmm0
0x1800043d2  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x1800043d7  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x1800043dc  call    cs:__imp_RtlInitUnicodeString
0x1800043e2  movzx   r9d, [rsp+2D0h+DestinationString.Length]
0x1800043e8  xor     edx, edx
0x1800043ea  mov     word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer], dx
0x1800043f1  lea     r8, [r9+2]; RequiredSize
0x1800043f5  cmp     r8, 0FFFEh
0x1800043fc  jbe     short loc_180004405
0x1800043fe  mov     ecx, 0C0000106h
0x180004403  jmp     short loc_180004426
0x180004405  cmp     r8, [rbp+1D0h+Buffer.Size]
0x18000440c  jbe     short loc_180004443
0x18000440e  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x180004415  xor     ecx, ecx; Flags
0x180004417  call    cs:__imp_RtlpEnsureBufferSize
0x18000441d  test    eax, eax
0x18000441f  jns     short loc_180004436
0x180004421  mov     ecx, 0C0000017h; int
0x180004426  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000442b  mov     edi, eax
0x18000442d  test    eax, eax
0x18000442f  jns     short loc_180004499
0x180004431  jmp     loc_180004682
0x180004436  movzx   edx, word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]
0x18000443d  movzx   r9d, [rsp+2D0h+DestinationString.Length]
0x180004443  mov     rcx, [rbp+1D0h+Buffer.Buffer]
0x18000444a  movzx   eax, dx
0x18000444d  mov     rdx, [rsp+2D0h+DestinationString.Buffer]; Src
0x180004452  shr     rax, 1
0x180004455  mov     [rbp+1D0h+var_80], rcx
0x18000445c  movzx   r8d, r9w; Size
0x180004460  lea     rcx, [rcx+rax*2]; void *
0x180004464  call    memmove_0
0x180004469  movzx   eax, word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]
0x180004470  add     ax, [rsp+2D0h+DestinationString.Length]
0x180004475  movzx   edx, ax
0x180004478  mov     word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer], dx
0x18000447f  lea     eax, [rdx+2]
0x180004482  shr     rdx, 1
0x180004485  mov     word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x18000448c  xor     ecx, ecx
0x18000448e  mov     rax, [rbp+1D0h+var_80]
0x180004495  mov     [rax+rdx*2], cx
0x180004499  xorps   xmm0, xmm0
0x18000449c  lea     rdx, [rbx+37Eh]; SourceString
0x1800044a3  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x1800044a8  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x1800044ad  call    cs:__imp_RtlInitUnicodeString
0x1800044b3  lea     r8, [rsp+2D0h+DestinationString]
0x1800044b8  mov     ecx, 1
0x1800044bd  lea     rdx, [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]
0x1800044c4  call    cs:__imp_RtlAppendPathElement
0x1800044ca  test    eax, eax
0x1800044cc  jns     short loc_1800044DF
0x1800044ce  mov     ecx, eax; int
0x1800044d0  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800044d5  mov     edi, eax
0x1800044d7  test    eax, eax
0x1800044d9  js      loc_180004682
0x1800044df  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x1800044e6  lea     r8, [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x1800044ed  xor     edi, edi
0x1800044ef  xor     ecx, ecx; Flags
0x1800044f1  lea     edx, [rdi+38h]; Type
0x1800044f4  call    cs:__imp_RtlpApplyLengthFunction
0x1800044fa  test    eax, eax
0x1800044fc  jns     short loc_180004507
0x1800044fe  mov     ecx, eax; int
0x180004500  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x180004505  mov     edi, eax
0x180004507  test    edi, edi
0x180004509  js      loc_180004682
0x18000450f  mov     rax, [rbp+1D0h+Buffer.Buffer]
0x180004516  mov     ecx, 288h; Size
0x18000451b  cmp     rax, [rbp+1D0h+Buffer.StaticBuffer]
0x180004522  mov     edi, 8007000Eh
0x180004527  mov     r13, [rbp+1D0h+var_80]
0x18000452e  mov     r15, [rbx+60h]
0x180004532  cmovnz  r13, rax
0x180004536  mov     rax, [rsp+2D0h+var_2A0]
0x18000453b  mov     qword ptr [rax], 0
0x180004542  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004547  mov     rbx, rax
0x18000454a  test    rax, rax
0x18000454d  jz      loc_180004682
0x180004553  mov     dword ptr [rbx+8], 1
0x18000455a  lea     rdx, [rbx+20h]
0x18000455e  mov     [rbx+10h], r15
0x180004562  mov     ecx, 208h
0x180004567  mov     qword ptr [rbx+18h], 0
0x18000456f  lea     rax, ??_7CEnumOfflineFilesItems@@6B@; const CEnumOfflineFilesItems::`vftable'
0x180004576  mov     [rbx], rax
0x180004579  mov     [rbx+238h], rdx
0x180004580  mov     [rbx+248h], rcx
0x180004587  mov     [rbx+240h], rdx
0x18000458e  mov     [rbx+250h], rcx
0x180004595  mov     [rbx+230h], rdx
0x18000459c  test    rdx, rdx
0x18000459f  jz      short loc_1800045A6
0x1800045a1  xor     eax, eax
0x1800045a3  mov     [rdx], ax
0x1800045a6  mov     eax, [rbp+1D0h+arg_28]
0x1800045ac  mov     rcx, r15
0x1800045af  mov     dword ptr [rbx+228h], 2080000h
0x1800045b9  mov     [rbx+260h], eax
0x1800045bf  mov     eax, [rbp+1D0h+arg_30]
0x1800045c5  mov     [rbx+264h], eax
0x1800045cb  mov     rax, [r15]
0x1800045ce  mov     rax, [rax+8]
0x1800045d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d7  mov     rcx, [rsp+2D0h+var_298]
0x1800045dc  mov     [rbx+268h], rcx
0x1800045e3  mov     [rbx+270h], r12
0x1800045ea  mov     [rbx+278h], r14
0x1800045f1  mov     [rbx+280h], rsi
0x1800045f8  test    rcx, rcx
0x1800045fb  jz      short loc_180004609
0x1800045fd  mov     rax, [rcx]
0x180004600  mov     rax, [rax+8]
0x180004604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004609  test    r12, r12
0x18000460c  jz      short loc_18000461E
0x18000460e  mov     rax, [r12]
0x180004612  mov     rcx, r12
0x180004615  mov     rax, [rax+8]
0x180004619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000461e  test    r14, r14
0x180004621  jz      short loc_180004632
0x180004623  mov     rax, [r14]
0x180004626  mov     rcx, r14
0x180004629  mov     rax, [rax+8]
0x18000462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004632  test    rsi, rsi
0x180004635  jz      short loc_180004646
0x180004637  mov     rax, [rsi]
0x18000463a  mov     rcx, rsi
0x18000463d  mov     rax, [rax+8]
0x180004641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004646  mov     rdx, r13; unsigned __int16 *
0x180004649  mov     rcx, rbx; this
0x18000464c  call    ?_Initialize@CEnumOfflineFilesItems@@AEAAJPEBG@Z; CEnumOfflineFilesItems::_Initialize(ushort const *)
0x180004651  mov     edi, eax
0x180004653  test    eax, eax
0x180004655  js      short loc_180004673
0x180004657  mov     rax, [rbx]
0x18000465a  lea     rdx, IID_IEnumOfflineFilesItems
0x180004661  mov     r8, [rsp+2D0h+var_2A0]
0x180004666  mov     rcx, rbx
0x180004669  mov     rax, [rax]
0x18000466c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004671  mov     edi, eax
0x180004673  mov     rax, [rbx]
0x180004676  mov     rcx, rbx
0x180004679  mov     rax, [rax+10h]
0x18000467d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004682  lea     rcx, [rsp+2D0h+var_290]; this
0x180004687  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18000468c  xor     eax, eax
0x18000468e  test    edi, edi
0x180004690  cmovs   eax, edi
0x180004693  mov     rcx, [rbp+1D0h+Buffer.ReservedForIMalloc]
0x18000469a  xor     rcx, rsp; StackCookie
0x18000469d  call    __security_check_cookie
0x1800046a2  add     rsp, 298h
0x1800046a9  pop     r15
0x1800046ab  pop     r14
0x1800046ad  pop     r13
0x1800046af  pop     r12
0x1800046b1  pop     rdi
0x1800046b2  pop     rsi
0x1800046b3  pop     rbx
0x1800046b4  pop     rbp
0x1800046b5  retn
```
