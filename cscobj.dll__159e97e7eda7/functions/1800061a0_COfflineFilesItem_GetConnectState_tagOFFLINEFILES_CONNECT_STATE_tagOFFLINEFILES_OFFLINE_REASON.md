# COfflineFilesItem::_GetConnectState(tagOFFLINEFILES_CONNECT_STATE *,tagOFFLINEFILES_OFFLINE_REASON *)

- ea: `0x1800061a0`
- end: `0x1800064f7`
- name: `?_GetConnectState@COfflineFilesItem@@IEAAJPEAW4tagOFFLINEFILES_CONNECT_STATE@@PEAW4tagOFFLINEFILES_OFFLINE_REASON@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(COfflineFilesItem *__hidden this, enum tagOFFLINEFILES_CONNECT_STATE *, enum tagOFFLINEFILES_OFFLINE_REASON *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000f960`
- `0x18000f970`

## callees

- `0x1800061a0`
- `0x180008b14`
- `0x18000b7c0`
- `0x18000fea4`
- `0x1800102a8`
- `0x18002ac30`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180006429`
- `ntdll!RtlFreeUnicodeString` at `0x180006429`
- `ntdll!RtlpEnsureBufferSize` at `0x1800062cd`
- `ntdll!RtlpEnsureBufferSize` at `0x1800062cd`
- `ntdll!RtlAppendPathElement` at `0x180006379`
- `ntdll!RtlAppendPathElement` at `0x180006379`
- `ntdll!RtlpApplyLengthFunction` at `0x1800063a8`
- `ntdll!RtlpApplyLengthFunction` at `0x1800063a8`
- `ntdll!RtlGetLengthWithoutTrailingPathSeperators` at `0x180006390`
- `ntdll!RtlInitUnicodeString` at `0x18000628f`
- `ntdll!RtlInitUnicodeString` at `0x180006362`
- `ntdll!RtlInitUnicodeString` at `0x18000628f`
- `ntdll!RtlInitUnicodeString` at `0x180006362`

## pseudocode

```c
__int64 __fastcall COfflineFilesItem::_GetConnectState(
        COfflineFilesItem *this,
        enum tagOFFLINEFILES_CONNECT_STATE *a2,
        enum tagOFFLINEFILES_OFFLINE_REASON *a3)
{
  int v6; // edi
  char *v7; // rbx
  bool v8; // zf
  const WCHAR *v9; // rdx
  USHORT Length; // r8
  unsigned __int16 v11; // dx
  SIZE_T v12; // rax
  int v13; // ecx
  unsigned __int64 v14; // rdx
  int appended; // eax
  NTSTATUS v16; // eax
  PUCHAR v17; // rdx
  PUCHAR StaticBuffer; // rcx
  int v19; // ecx
  enum tagOFFLINEFILES_CONNECT_STATE v20; // eax
  struct _UNICODE_STRING DestinationString_8; // [rsp+38h] [rbp-D0h] BYREF
  char *v23; // [rsp+48h] [rbp-C0h] BYREF
  _WORD v24[260]; // [rsp+58h] [rbp-B0h] BYREF
  int UnicodeStringOrUnicodeStringBuffer; // [rsp+260h] [rbp+158h] BYREF
  PUCHAR v26; // [rsp+268h] [rbp+160h]
  struct _RTL_BUFFER Buffer; // [rsp+270h] [rbp+168h] BYREF

  if ( a2 && a3 )
  {
    *a2 = OFFLINEFILES_CONNECT_STATE_UNKNOWN;
    *a3 = OFFLINEFILES_OFFLINE_REASON_UNKNOWN;
    if ( *((_DWORD *)this + 2) == 3 )
      return (unsigned int)-2147024846;
    v6 = 0;
    v7 = (char *)this + 600;
    v8 = (*((_BYTE *)this + 600) & 0x10) == 0;
    v23 = (char *)this + 600;
    if ( !v8 )
    {
LABEL_32:
      v19 = *((_DWORD *)v7 + 51);
      if ( (unsigned int)(v19 - 2) <= 2 || (unsigned int)(*((_DWORD *)v7 + 52) - 2) <= 2 )
      {
        if ( (unsigned int)CCacheItemInfo::IsItemOffline((CCacheItemInfo *)&v23) )
        {
          *a2 = OFFLINEFILES_CONNECT_STATE_OFFLINE;
          *a3 = CCacheItemInfo::OfflineReason((CCacheItemInfo *)&v23);
        }
        else
        {
          return (unsigned int)-2147467259;
        }
      }
      else if ( v19 == 5 )
      {
        *a2 = OFFLINEFILES_CONNECT_STATE_TRANSPARENTLY_CACHED;
        *a3 = OFFLINEFILES_OFFLINE_REASON_NOT_APPLICABLE;
      }
      else
      {
        v20 = OFFLINEFILES_CONNECT_STATE_ONLINE;
        if ( v19 == 6 )
          v20 = OFFLINEFILES_CONNECT_STATE_PARTLY_TRANSPARENTLY_CACHED;
        *a2 = v20;
        *a3 = OFFLINEFILES_OFFLINE_REASON_NOT_APPLICABLE;
      }
      return (unsigned int)v6;
    }
    v9 = (const WCHAR *)*((_QWORD *)this + 70);
    Buffer.Buffer = (PUCHAR)v24;
    Buffer.Size = 520;
    Buffer.StaticBuffer = (PUCHAR)v24;
    v26 = (PUCHAR)v24;
    Buffer.StaticSize = 520;
    v24[0] = 0;
    UnicodeStringOrUnicodeStringBuffer = 34078720;
    if ( v9 == *((const WCHAR **)this + 71) )
      v9 = (const WCHAR *)*((_QWORD *)this + 69);
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, v9);
    Length = DestinationString_8.Length;
    v11 = 0;
    LOWORD(UnicodeStringOrUnicodeStringBuffer) = 0;
    v12 = DestinationString_8.Length + 2LL;
    if ( v12 > 0xFFFE )
    {
      v13 = -1073741562;
      goto LABEL_13;
    }
    if ( v12 > Buffer.Size )
    {
      if ( RtlpEnsureBufferSize(0, &Buffer, DestinationString_8.Length + 2LL) < 0 )
      {
        v13 = -1073741801;
LABEL_13:
        v6 = ResultFromNtStatus(v13);
        if ( v6 < 0 )
          goto LABEL_26;
        goto LABEL_17;
      }
      v11 = UnicodeStringOrUnicodeStringBuffer;
      Length = DestinationString_8.Length;
    }
    v26 = Buffer.Buffer;
    memmove_0(&Buffer.Buffer[2 * ((unsigned __int64)v11 >> 1)], DestinationString_8.Buffer, Length);
    v14 = (unsigned __int16)(DestinationString_8.Length + UnicodeStringOrUnicodeStringBuffer);
    LOWORD(UnicodeStringOrUnicodeStringBuffer) = v14;
    HIWORD(UnicodeStringOrUnicodeStringBuffer) = v14 + 2;
    *(_WORD *)&v26[2 * (v14 >> 1)] = 0;
LABEL_17:
    DestinationString_8 = 0;
    RtlInitUnicodeString(&DestinationString_8, (PCWSTR)v7 + 107);
    appended = RtlAppendPathElement(1, &UnicodeStringOrUnicodeStringBuffer, &DestinationString_8);
    if ( appended >= 0 || (v6 = ResultFromNtStatus(appended), v6 >= 0) )
    {
      v6 = 0;
      v16 = RtlpApplyLengthFunction(
              0,
              0x38u,
              &UnicodeStringOrUnicodeStringBuffer,
              RtlGetLengthWithoutTrailingPathSeperators);
      if ( v16 < 0 )
        v6 = ResultFromNtStatus(v16);
      if ( v6 >= 0 )
      {
        v17 = v26;
        if ( Buffer.Buffer != Buffer.StaticBuffer )
          v17 = Buffer.Buffer;
        v6 = (*(__int64 (__fastcall **)(_QWORD, PUCHAR, char *, char *))(**((_QWORD **)this + 2) + 168LL))(
               *((_QWORD *)this + 2),
               v17,
               (char *)this + 804,
               (char *)this + 808);
        if ( v6 >= 0 )
          *(_DWORD *)v7 |= 0x10u;
      }
    }
LABEL_26:
    StaticBuffer = Buffer.StaticBuffer;
    if ( Buffer.Buffer && Buffer.Buffer != Buffer.StaticBuffer )
    {
      *(_QWORD *)&DestinationString_8.Length = 0;
      DestinationString_8.Buffer = (PWSTR)Buffer.Buffer;
      RtlFreeUnicodeString(&DestinationString_8);
      StaticBuffer = Buffer.StaticBuffer;
    }
    if ( StaticBuffer )
      *(_WORD *)StaticBuffer = 0;
    if ( v6 < 0 )
      return (unsigned int)v6;
    goto LABEL_32;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x1800061a0  mov     r11, rsp
0x1800061a3  push    rbp
0x1800061a4  push    rsi
0x1800061a5  push    r14
0x1800061a7  push    r15
0x1800061a9  lea     rbp, [r11-1D8h]
0x1800061b0  sub     rsp, 2B8h
0x1800061b7  mov     rax, cs:__security_cookie
0x1800061be  xor     rax, rsp
0x1800061c1  mov     [rbp+1D0h+Buffer.ReservedForIMalloc], rax
0x1800061c8  mov     r14, r8
0x1800061cb  mov     r15, rdx
0x1800061ce  mov     rsi, rcx
0x1800061d1  test    rdx, rdx
0x1800061d4  jz      loc_1800064D5
0x1800061da  test    r8, r8
0x1800061dd  jz      loc_1800064D5
0x1800061e3  mov     [r11-30h], rdi
0x1800061e7  mov     [r11-38h], r12
0x1800061eb  xor     r12d, r12d
0x1800061ee  mov     [rdx], r12d
0x1800061f1  mov     [r8], r12d
0x1800061f4  cmp     dword ptr [rcx+8], 3
0x1800061f8  jnz     short loc_180006204
0x1800061fa  mov     edi, 80070032h
0x1800061ff  jmp     loc_1800064C1
0x180006204  mov     [rsp+2B0h], rbx
0x18000620c  mov     edi, r12d
0x18000620f  lea     rbx, [rcx+258h]
0x180006216  test    byte ptr [rbx], 10h
0x180006219  mov     [rsp+2D0h+var_290], rbx
0x18000621e  jnz     loc_180006443
0x180006224  mov     rdx, [rsi+230h]
0x18000622b  lea     rax, [rsp+50h]
0x180006230  mov     ecx, 208h
0x180006235  mov     [rbp+1D0h+Buffer.Buffer], rax
0x18000623c  lea     rax, [rsp+50h]
0x180006241  mov     [rbp+1D0h+Buffer.Size], rcx
0x180006248  mov     [rbp+1D0h+Buffer.StaticBuffer], rax
0x18000624f  lea     rax, [rsp+50h]
0x180006254  mov     [rbp+1D0h+var_70], rax
0x18000625b  mov     [rbp+1D0h+Buffer.StaticSize], rcx
0x180006262  mov     [rsp+50h], r12w
0x180006268  mov     [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer], 2080000h
0x180006272  cmp     rdx, [rsi+238h]
0x180006279  jnz     short loc_180006282
0x18000627b  mov     rdx, [rsi+228h]; SourceString
0x180006282  xorps   xmm0, xmm0
0x180006285  lea     rcx, [rsp+2D0h+DestinationString.Buffer]; DestinationString
0x18000628a  movups  xmmword ptr [rsp+2D0h+DestinationString.Buffer], xmm0
0x18000628f  call    cs:__imp_RtlInitUnicodeString
0x180006295  movzx   r8d, word ptr [rsp+2D0h+DestinationString.Buffer]
0x18000629b  mov     edx, r12d
0x18000629e  mov     word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer], dx
0x1800062a5  lea     rax, [r8+2]
0x1800062a9  cmp     rax, 0FFFEh
0x1800062af  jbe     short loc_1800062B8
0x1800062b1  mov     ecx, 0C0000106h
0x1800062b6  jmp     short loc_1800062DC
0x1800062b8  cmp     rax, [rbp+1D0h+Buffer.Size]
0x1800062bf  jbe     short loc_1800062F9
0x1800062c1  mov     r8, rax; RequiredSize
0x1800062c4  lea     rdx, [rbp+1D0h+Buffer]; Buffer
0x1800062cb  xor     ecx, ecx; Flags
0x1800062cd  call    cs:__imp_RtlpEnsureBufferSize
0x1800062d3  test    eax, eax
0x1800062d5  jns     short loc_1800062EC
0x1800062d7  mov     ecx, 0C0000017h; int
0x1800062dc  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800062e1  mov     edi, eax
0x1800062e3  test    eax, eax
0x1800062e5  jns     short loc_18000634E
0x1800062e7  jmp     loc_180006402
0x1800062ec  movzx   edx, word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]
0x1800062f3  movzx   r8d, word ptr [rsp+2D0h+DestinationString.Buffer]
0x1800062f9  mov     rcx, [rbp+1D0h+Buffer.Buffer]
0x180006300  movzx   eax, dx
0x180006303  mov     rdx, [rsp+2D0h+Src]; Src
0x180006308  shr     rax, 1
0x18000630b  mov     [rbp+1D0h+var_70], rcx
0x180006312  movzx   r8d, r8w; Size
0x180006316  lea     rcx, [rcx+rax*2]; void *
0x18000631a  call    memmove_0
0x18000631f  movzx   eax, word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]
0x180006326  add     ax, word ptr [rsp+2D0h+DestinationString.Buffer]
0x18000632b  movzx   edx, ax
0x18000632e  mov     word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer], dx
0x180006335  lea     eax, [rdx+2]
0x180006338  shr     rdx, 1
0x18000633b  mov     word ptr [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer+2], ax
0x180006342  mov     rax, [rbp+1D0h+var_70]
0x180006349  mov     [rax+rdx*2], r12w
0x18000634e  xorps   xmm0, xmm0
0x180006351  lea     rdx, [rbx+0D6h]; SourceString
0x180006358  lea     rcx, [rsp+2D0h+DestinationString.Buffer]; DestinationString
0x18000635d  movups  xmmword ptr [rsp+2D0h+DestinationString.Buffer], xmm0
0x180006362  call    cs:__imp_RtlInitUnicodeString
0x180006368  lea     r8, [rsp+2D0h+DestinationString.Buffer]
0x18000636d  mov     ecx, 1
0x180006372  lea     rdx, [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]
0x180006379  call    cs:__imp_RtlAppendPathElement
0x18000637f  test    eax, eax
0x180006381  jns     short loc_180006390
0x180006383  mov     ecx, eax; int
0x180006385  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000638a  mov     edi, eax
0x18000638c  test    eax, eax
0x18000638e  js      short loc_180006402
0x180006390  mov     r9, cs:__imp_RtlGetLengthWithoutTrailingPathSeperators; LengthFunction
0x180006397  lea     r8, [rbp+1D0h+UnicodeStringOrUnicodeStringBuffer]; UnicodeStringOrUnicodeStringBuffer
0x18000639e  mov     edx, 38h ; '8'; Type
0x1800063a3  xor     ecx, ecx; Flags
0x1800063a5  mov     edi, r12d
0x1800063a8  call    cs:__imp_RtlpApplyLengthFunction
0x1800063ae  test    eax, eax
0x1800063b0  jns     short loc_1800063BB
0x1800063b2  mov     ecx, eax; int
0x1800063b4  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800063b9  mov     edi, eax
0x1800063bb  test    edi, edi
0x1800063bd  js      short loc_180006402
0x1800063bf  mov     r8, [rbp+1D0h+Buffer.Buffer]
0x1800063c6  lea     r9, [rsi+328h]
0x1800063cd  cmp     r8, [rbp+1D0h+Buffer.StaticBuffer]
0x1800063d4  mov     rcx, [rsi+10h]
0x1800063d8  mov     rdx, [rbp+1D0h+var_70]
0x1800063df  cmovnz  rdx, r8
0x1800063e3  lea     r8, [rsi+324h]
0x1800063ea  mov     rax, [rcx]
0x1800063ed  mov     rax, [rax+0A8h]
0x1800063f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f9  mov     edi, eax
0x1800063fb  test    eax, eax
0x1800063fd  js      short loc_180006402
0x1800063ff  or      dword ptr [rbx], 10h
0x180006402  mov     rax, [rbp+1D0h+Buffer.Buffer]
0x180006409  mov     rcx, [rbp+1D0h+Buffer.StaticBuffer]
0x180006410  test    rax, rax
0x180006413  jz      short loc_180006436
0x180006415  cmp     rax, rcx
0x180006418  jz      short loc_180006436
0x18000641a  lea     rcx, [rsp+2D0h+DestinationString.Buffer]; UnicodeString
0x18000641f  mov     [rsp+2D0h+DestinationString.Buffer], r12
0x180006424  mov     [rsp+2D0h+Src], rax
0x180006429  call    cs:__imp_RtlFreeUnicodeString
0x18000642f  mov     rcx, [rbp+1D0h+Buffer.StaticBuffer]
0x180006436  test    rcx, rcx
0x180006439  jz      short loc_18000643F
0x18000643b  mov     [rcx], r12w
0x18000643f  test    edi, edi
0x180006441  js      short loc_1800064B9
0x180006443  mov     ecx, [rbx+0CCh]
0x180006449  lea     eax, [rcx-2]
0x18000644c  cmp     eax, 2
0x18000644f  jbe     short loc_180006490
0x180006451  mov     eax, [rbx+0D0h]
0x180006457  sub     eax, 2
0x18000645a  cmp     eax, 2
0x18000645d  jbe     short loc_180006490
0x18000645f  cmp     ecx, 5
0x180006462  jnz     short loc_180006474
0x180006464  mov     dword ptr [r15], 3
0x18000646b  mov     dword ptr [r14], 1
0x180006472  jmp     short loc_1800064B9
0x180006474  cmp     ecx, 6
0x180006477  mov     eax, 2
0x18000647c  mov     edx, 4
0x180006481  cmovz   eax, edx
0x180006484  mov     [r15], eax
0x180006487  mov     dword ptr [r14], 1
0x18000648e  jmp     short loc_1800064B9
0x180006490  lea     rcx, [rsp+2D0h+var_290]; this
0x180006495  call    ?IsItemOffline@CCacheItemInfo@@QEBAHXZ; CCacheItemInfo::IsItemOffline(void)
0x18000649a  test    eax, eax
0x18000649c  jz      short loc_1800064B4
0x18000649e  lea     rcx, [rsp+2D0h+var_290]; this
0x1800064a3  mov     dword ptr [r15], 1
0x1800064aa  call    ?OfflineReason@CCacheItemInfo@@QEBA?AW4tagOFFLINEFILES_OFFLINE_REASON@@XZ; CCacheItemInfo::OfflineReason(void)
0x1800064af  mov     [r14], eax
0x1800064b2  jmp     short loc_1800064B9
0x1800064b4  mov     edi, 80004005h
0x1800064b9  mov     rbx, [rsp+2B0h]
0x1800064c1  mov     r12, [rsp+2D0h+var_30]
0x1800064c9  mov     eax, edi
0x1800064cb  mov     rdi, [rsp+2D0h+var_28]
0x1800064d3  jmp     short loc_1800064DA
0x1800064d5  mov     eax, 80004003h
0x1800064da  mov     rcx, [rbp+1D0h+Buffer.ReservedForIMalloc]
0x1800064e1  xor     rcx, rsp; StackCookie
0x1800064e4  call    __security_check_cookie
0x1800064e9  add     rsp, 2B8h
0x1800064f0  pop     r15
0x1800064f2  pop     r14
0x1800064f4  pop     rsi
0x1800064f5  pop     rbp
0x1800064f6  retn
```
