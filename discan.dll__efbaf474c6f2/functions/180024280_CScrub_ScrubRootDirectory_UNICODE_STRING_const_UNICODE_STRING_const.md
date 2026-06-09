# CScrub::ScrubRootDirectory(_UNICODE_STRING const *,_UNICODE_STRING const *)

- ea: `0x180024280`
- end: `0x1800247bb`
- name: `?ScrubRootDirectory@CScrub@@QEAAJPEBU_UNICODE_STRING@@0@Z`
- size: `1339`
- prototype: `__int64 __fastcall(CScrub *__hidden this, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024b24`

## callees

- `0x180001b78`
- `0x180003134`
- `0x1800032f8`
- `0x180006688`
- `0x1800188f4`
- `0x18001fde0`
- `0x180020cec`
- `0x180021ad8`
- `0x18002226c`
- `0x1800223bc`
- `0x180022450`
- `0x18002415c`
- `0x180024280`
- `0x18002892c`
- `0x180028fe4`
- `0x18002ad9c`
- `0x18002bb08`
- `0x180039010`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x180024635`
- `ntdll!RtlEqualUnicodeString` at `0x180024635`
- `ntdll!NtOpenFile` at `0x180024404`
- `ntdll!NtOpenFile` at `0x180024404`

## string_xrefs

- `0x1800242c3`: `CScrub::ScrubRootDirectory`

## pseudocode

```c
__int64 __fastcall CScrub::ScrubRootDirectory(CScrub *this, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3)
{
  struct _UNICODE_STRING *v3; // r13
  const struct _UNICODE_STRING *v6; // r9
  __int64 v7; // rdx
  USHORT v8; // dx
  USHORT Length; // cx
  USHORT v10; // ax
  struct _UNICODE_STRING *v11; // rcx
  void **v12; // rax
  void **v13; // r12
  NTSTATUS v14; // eax
  const struct _UNICODE_STRING *v15; // r9
  NTSTATUS v16; // ebx
  unsigned int v17; // ebx
  struct _SCRUB_THREAD_CONTEXT *v18; // rdx
  struct _UNICODE_STRING *v19; // r14
  __int16 v20; // r13
  CFileName *v21; // rax
  struct CFileName *v22; // r14
  const UNICODE_STRING *v23; // r13
  __int64 v24; // rax
  const char *v26; // [rsp+48h] [rbp-A0h] BYREF
  int v27; // [rsp+50h] [rbp-98h]
  struct _UNICODE_STRING v28; // [rsp+58h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-70h] BYREF
  CFileName *v33; // [rsp+108h] [rbp+20h] BYREF

  v3 = a3;
  v6 = (const struct _UNICODE_STRING *)(unsigned int)tls_index;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v7 + 16) = "CScrub::ScrubRootDirectory";
  v26 = "CScrub::ScrubRootDirectory";
  v27 = 0;
  v8 = ++*(_WORD *)(v7 + 8);
  Length = GlobalIndentString.Length;
  v10 = GlobalIndentString.Length;
  if ( v8 < GlobalIndentString.Length )
    v10 = v8;
  v28.Length = v10;
  if ( v8 < GlobalIndentString.Length )
    Length = v8;
  v28.MaximumLength = Length;
  *(_DWORD *)(&v28.MaximumLength + 1) = 0;
  v28.Buffer = (PWSTR)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubRootDirectory");
  }
  v28 = *v3;
  v28.Length = _mm_cvtsi128_si32((__m128i)v28) - 2;
  v11 = (struct _UNICODE_STRING *)(*((_QWORD *)this + 177) + 88LL);
  v11->Length = 0;
  CScrubPath::PushNameEx(v11, &EmptyUnicodeString, &v28, v6);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v12 = (void **)operator new(0x10u);
  v13 = v12;
  if ( !v12 )
  {
    v17 = -2147024882;
LABEL_52:
    v27 = v17;
    goto LABEL_53;
  }
  *v12 = 0;
  *((_DWORD *)v12 + 2) = 0;
  *((_BYTE *)v12 + 12) = 0;
  v14 = NtOpenFile(v12, 0x100081u, &ObjectAttributes, &IoStatusBlock, 7u, 0x600020u);
  v16 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        &WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        a2,
        v3,
        v14);
    }
    v17 = v16 | 0x10000000;
    goto LABEL_52;
  }
  v18 = (struct _SCRUB_THREAD_CONTEXT *)*((_QWORD *)this + 177);
  if ( !*((_WORD *)v18 + 17232) )
  {
    if ( (*((_BYTE *)this + 1260) & 1) != 0 )
    {
      v17 = -805306102;
    }
    else
    {
      v27 = CScrub::ScrubNtfsSystemFiles(this, v18, *v13);
      v17 = -805306102;
      if ( v27 == -805306102 )
        goto LABEL_53;
    }
    v19 = (struct _UNICODE_STRING *)(*((_QWORD *)this + 177) + 88LL);
    *(_QWORD *)&v28.Length = v19;
    v20 = CScrubPath::PushNameEx(v19, &BackslashString, &EmptyUnicodeString, v15);
    LOWORD(v28.Buffer) = v20;
    v27 = CScrub::ScrubData((__int64)this, *((struct _SCRUB_THREAD_CONTEXT **)this + 177), *v13, 0, 0);
    if ( v27 == -805306102
      || (*((_BYTE *)this + 1260) & 8) == 0
      && (v27 = CScrub::_ScrubAlternativeDataStreams(
                  (__int64)this,
                  *((struct _SCRUB_THREAD_CONTEXT **)this + 177),
                  *v13),
          v27 == -805306102)
      || (*((_BYTE *)this + 1260) & 2) == 0
      && (v27 = CScrub::_ScrubNtfsSystemAttributes(this, *((struct _SCRUB_THREAD_CONTEXT **)this + 177), *v13, 16),
          v27 == -805306102) )
    {
      v19->Length -= v20;
LABEL_53:
      CHResultImp::~CHResultImp((CHResultImp *)&v26);
      return v17;
    }
    v19->Length -= v20;
    v3 = a3;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL),
      (__int64)a2,
      (__int64)v3);
  }
  v21 = (CFileName *)operator new(0x30u);
  v33 = v21;
  if ( v21 )
    v22 = CFileName::CFileName(v21, 0, &EmptyUnicodeString);
  else
    v22 = 0;
  v33 = v22;
  if ( v22 )
    (*(void (__fastcall **)(struct CFileName *))(*(_QWORD *)v22 + 8LL))(v22);
  if ( *(_DWORD *)(*((_QWORD *)this + 1) + 8LL) != 1 )
    *(_QWORD *)(*((_QWORD *)this + 177) + 34432LL) = (char *)this + 1432;
  v23 = 0;
  if ( RtlEqualUnicodeString((PCUNICODE_STRING)(*((_QWORD *)this + 177) + 34464LL), &RootDirectoryString, 0) )
  {
    *(_WORD *)(*((_QWORD *)this + 177) + 34464LL) = 0;
    v24 = *((_QWORD *)this + 177);
    v23 = *(const UNICODE_STRING **)(v24 + 34480);
    *(_QWORD *)(v24 + 34480) = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)v23);
    }
  }
  CHandleT<void *,NtHandleTrait>::AddRef(v13);
  v27 = CScrub::_ScanDirectoryEntries(this, *((struct _SCRUB_THREAD_CONTEXT **)this + 177), v13, v22, 0, v23);
  CHandleT<void *,NtHandleTrait>::Release(v13);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v33);
  if ( v27 == -805306102 )
  {
    CHResultImp::~CHResultImp((CHResultImp *)&v26);
    return 3489661194LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)a2,
        (__int64)a3);
    }
    v27 = 0;
    CHResultImp::~CHResultImp((CHResultImp *)&v26);
    return 0;
  }
}

```

## disassembly

```asm
0x180024280  mov     [rsp+arg_10], r8
0x180024285  mov     [rsp+arg_8], rdx
0x18002428a  mov     [rsp+arg_0], rcx
0x18002428f  push    rbx
0x180024290  push    rsi
0x180024291  push    rdi
0x180024292  push    r12
0x180024294  push    r13
0x180024296  push    r14
0x180024298  push    r15
0x18002429a  sub     rsp, 0B0h
0x1800242a1  mov     r13, r8
0x1800242a4  mov     rbx, rdx
0x1800242a7  mov     rdi, rcx
0x1800242aa  mov     r9d, cs:_tls_index
0x1800242b1  mov     rax, gs:58h
0x1800242ba  mov     rdx, [rax+r9*8]
0x1800242be  mov     eax, 10h
0x1800242c3  lea     r8, aCscrubScrubroo; "CScrub::ScrubRootDirectory"
0x1800242ca  mov     [rax+rdx], r8
0x1800242ce  mov     [rsp+0E8h+var_A0], r8
0x1800242d3  xor     esi, esi
0x1800242d5  mov     [rsp+0E8h+var_98], esi
0x1800242d9  mov     eax, 8
0x1800242de  lea     r15d, [rsi+1]
0x1800242e2  add     [rax+rdx], r15w
0x1800242e7  movzx   edx, word ptr [rax+rdx]
0x1800242eb  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800242f2  movzx   eax, cx
0x1800242f5  cmp     dx, cx
0x1800242f8  cmovb   ax, dx
0x1800242fc  mov     [rsp+0E8h+var_90.Length], ax
0x180024301  cmovb   cx, dx
0x180024305  mov     [rsp+0E8h+var_90.MaximumLength], cx
0x18002430a  xor     eax, eax
0x18002430c  mov     dword ptr [rsp+0E8h+var_90+4], eax
0x180024310  mov     rax, cs:off_180047060; "                                       "...
0x180024317  mov     [rsp+0E8h+var_90.Buffer], rax
0x18002431c  lea     r14, WPP_GLOBAL_Control
0x180024323  mov     rcx, cs:WPP_GLOBAL_Control
0x18002432a  cmp     rcx, r14
0x18002432d  jz      short loc_180024352
0x18002432f  test    [rcx+1Ch], r15b
0x180024333  jz      short loc_180024352
0x180024335  cmp     byte ptr [rcx+19h], 5
0x180024339  jb      short loc_180024352
0x18002433b  lea     edx, [rsi+0Dh]
0x18002433e  mov     qword ptr [rsp+0E8h+ShareAccess], r8; __int64
0x180024343  lea     r9, [rsp+0E8h+var_90]
0x180024348  mov     rcx, [rcx+10h]; LoggerHandle
0x18002434c  call    WPP_SF_aZs
0x180024351  nop
0x180024352  movups  xmm0, xmmword ptr [r13+0]
0x180024357  movups  xmmword ptr [rsp+0E8h+var_90.Length], xmm0
0x18002435c  mov     ecx, 0FFFEh
0x180024361  movd    eax, xmm0
0x180024365  add     ax, cx
0x180024368  mov     [rsp+0E8h+var_90.Length], ax
0x18002436d  mov     rcx, [rdi+588h]
0x180024374  add     rcx, 58h ; 'X'; this
0x180024378  mov     [rcx], si
0x18002437b  lea     r8, [rsp+0E8h+var_90]; struct _UNICODE_STRING *
0x180024380  lea     rdx, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180024387  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002438c  mov     qword ptr [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x180024395  mov     qword ptr [rsp+0E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800243a1  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], rsi
0x1800243a9  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rbx
0x1800243b1  xorps   xmm0, xmm0
0x1800243b4  movdqu  xmmword ptr [rsp+0E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800243bd  movups  xmmword ptr [rsp+0E8h+IoStatusBlock], xmm0
0x1800243c2  mov     ecx, 10h; Size
0x1800243c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800243cc  mov     r12, rax
0x1800243cf  test    rax, rax
0x1800243d2  jz      loc_180024793
0x1800243d8  mov     [rax], rsi
0x1800243db  mov     [rax+8], esi
0x1800243de  mov     [rax+0Ch], sil
0x1800243e2  mov     [rsp+0E8h+OpenOptions], 600020h; OpenOptions
0x1800243ea  mov     [rsp+0E8h+ShareAccess], 7; ShareAccess
0x1800243f2  lea     r9, [rsp+0E8h+IoStatusBlock]; IoStatusBlock
0x1800243f7  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x1800243fc  mov     edx, 100081h; DesiredAccess
0x180024401  mov     rcx, rax; FileHandle
0x180024404  call    cs:__imp_NtOpenFile
0x18002440a  mov     ebx, eax
0x18002440c  test    eax, eax
0x18002440e  jns     short loc_180024457
0x180024410  mov     rcx, cs:WPP_GLOBAL_Control
0x180024417  cmp     rcx, r14
0x18002441a  jz      short loc_18002444E
0x18002441c  test    [rcx+1Ch], r15b
0x180024420  jz      short loc_18002444E
0x180024422  cmp     byte ptr [rcx+19h], 2
0x180024426  jb      short loc_18002444E
0x180024428  mov     edx, 67h ; 'g'
0x18002442d  mov     [rsp+0E8h+OpenOptions], eax
0x180024431  mov     qword ptr [rsp+0E8h+ShareAccess], r13
0x180024436  mov     r9, [rsp+0E8h+arg_8]
0x18002443e  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024445  mov     rcx, [rcx+10h]
0x180024449  call    WPP_SF_ZZd
0x18002444e  bts     ebx, 1Ch
0x180024452  jmp     loc_180024798
0x180024457  mov     rdx, [rdi+588h]; struct _SCRUB_THREAD_CONTEXT *
0x18002445e  cmp     [rdx+86A0h], si
0x180024465  ja      loc_180024555
0x18002446b  test    [rdi+4ECh], r15b
0x180024472  jnz     short loc_180024492
0x180024474  mov     r8, [r12]; void *
0x180024478  mov     rcx, rdi; this
0x18002447b  call    ?ScrubNtfsSystemFiles@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAX@Z; CScrub::ScrubNtfsSystemFiles(_SCRUB_THREAD_CONTEXT *,void *)
0x180024480  mov     [rsp+0E8h+var_98], eax
0x180024484  mov     ebx, 0D000010Ah
0x180024489  cmp     eax, ebx
0x18002448b  jnz     short loc_180024497
0x18002448d  jmp     loc_18002479C
0x180024492  mov     ebx, 0D000010Ah
0x180024497  mov     r14, [rdi+588h]
0x18002449e  add     r14, 58h ; 'X'
0x1800244a2  mov     qword ptr [rsp+0E8h+var_90.Length], r14
0x1800244a7  lea     r8, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800244ae  lea     rdx, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800244b5  mov     rcx, r14; this
0x1800244b8  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800244bd  movzx   r13d, ax
0x1800244c1  mov     word ptr [rsp+0E8h+var_90.Buffer], ax
0x1800244c6  mov     qword ptr [rsp+0E8h+ShareAccess], rsi
0x1800244cb  xor     r9d, r9d
0x1800244ce  mov     r8, [r12]
0x1800244d2  mov     rdx, [rdi+588h]
0x1800244d9  mov     rcx, rdi
0x1800244dc  call    ?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)
0x1800244e1  mov     [rsp+0E8h+var_98], eax
0x1800244e5  cmp     eax, ebx
0x1800244e7  jnz     short loc_1800244F2
0x1800244e9  sub     [r14], r13w
0x1800244ed  jmp     loc_18002479C
0x1800244f2  test    byte ptr [rdi+4ECh], 8
0x1800244f9  jnz     short loc_180024516
0x1800244fb  mov     r8, [r12]
0x1800244ff  mov     rdx, [rdi+588h]
0x180024506  mov     rcx, rdi
0x180024509  call    ?_ScrubAlternativeDataStreams@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXKW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@@Z; CScrub::_ScrubAlternativeDataStreams(_SCRUB_THREAD_CONTEXT *,void *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS)
0x18002450e  mov     [rsp+0E8h+var_98], eax
0x180024512  cmp     eax, ebx
0x180024514  jz      short loc_1800244E9
0x180024516  test    byte ptr [rdi+4ECh], 2
0x18002451d  jnz     short loc_180024540
0x18002451f  mov     r9d, 10h; unsigned int
0x180024525  mov     r8, [r12]; void *
0x180024529  mov     rdx, [rdi+588h]; struct _SCRUB_THREAD_CONTEXT *
0x180024530  mov     rcx, rdi; this
0x180024533  call    ?_ScrubNtfsSystemAttributes@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXK@Z; CScrub::_ScrubNtfsSystemAttributes(_SCRUB_THREAD_CONTEXT *,void *,ulong)
0x180024538  mov     [rsp+0E8h+var_98], eax
0x18002453c  cmp     eax, ebx
0x18002453e  jz      short loc_1800244E9
0x180024540  sub     [r14], r13w
0x180024544  lea     r14, WPP_GLOBAL_Control
0x18002454b  mov     r13, [rsp+0E8h+arg_10]
0x180024553  jmp     short loc_18002455A
0x180024555  mov     ebx, 0D000010Ah
0x18002455a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024561  cmp     rcx, r14
0x180024564  jz      short loc_1800245AE
0x180024566  test    [rcx+1Ch], r15b
0x18002456a  jz      short loc_1800245AE
0x18002456c  cmp     byte ptr [rcx+19h], 4
0x180024570  jb      short loc_1800245AE
0x180024572  mov     rax, [rdi]
0x180024575  mov     r9, [rax]
0x180024578  mov     edx, 68h ; 'h'
0x18002457d  mov     [rsp+0E8h+var_B0], r13; __int64
0x180024582  mov     r8, [rsp+0E8h+arg_8]
0x18002458a  mov     [rsp+0E8h+var_B8], r8; __int64
0x18002458f  mov     rax, [rax+40h]
0x180024593  mov     qword ptr [rsp+0E8h+OpenOptions], rax; __int64
0x180024598  mov     eax, [r9+24h]
0x18002459c  mov     [rsp+0E8h+ShareAccess], eax; char
0x1800245a0  mov     r9d, [r9+10h]
0x1800245a4  mov     rcx, [rcx+10h]; LoggerHandle
0x1800245a8  call    WPP_SF_DDZZZ
0x1800245ad  nop
0x1800245ae  mov     ecx, 30h ; '0'; Size
0x1800245b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800245b8  mov     [rsp+0E8h+arg_18], rax
0x1800245c0  test    rax, rax
0x1800245c3  jz      short loc_1800245DB
0x1800245c5  lea     r8, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800245cc  xor     edx, edx; struct CFileName *
0x1800245ce  mov     rcx, rax; this
0x1800245d1  call    ??0CFileName@@QEAA@PEAV0@PEBU_UNICODE_STRING@@@Z; CFileName::CFileName(CFileName *,_UNICODE_STRING const *)
0x1800245d6  mov     r14, rax
0x1800245d9  jmp     short loc_1800245DE
0x1800245db  mov     r14, rsi
0x1800245de  mov     [rsp+0E8h+arg_18], r14
0x1800245e6  test    r14, r14
0x1800245e9  jz      short loc_1800245FB
0x1800245eb  mov     rax, [r14]
0x1800245ee  mov     rcx, r14
0x1800245f1  mov     rax, [rax+8]
0x1800245f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245fa  nop
0x1800245fb  mov     rax, [rdi+8]
0x1800245ff  cmp     [rax+8], r15d
0x180024603  jz      short loc_18002461A
0x180024605  lea     rcx, [rdi+598h]
0x18002460c  mov     rax, [rdi+588h]
0x180024613  mov     [rax+8680h], rcx
0x18002461a  mov     r13, rsi
0x18002461d  mov     rcx, [rdi+588h]
0x180024624  add     rcx, 86A0h; String1
0x18002462b  xor     r8d, r8d; CaseInsensitive
0x18002462e  lea     rdx, ?RootDirectoryString@@3U_UNICODE_STRING@@B; String2
0x180024635  call    cs:__imp_RtlEqualUnicodeString
0x18002463b  test    al, al
0x18002463d  jz      short loc_1800246B6
0x18002463f  mov     rax, [rdi+588h]
0x180024646  mov     [rax+86A0h], si
0x18002464d  mov     rax, [rdi+588h]
0x180024654  mov     r13, [rax+86B0h]
0x18002465b  mov     [rax+86B0h], rsi
0x180024662  mov     rcx, cs:WPP_GLOBAL_Control
0x180024669  lea     rax, WPP_GLOBAL_Control
0x180024670  cmp     rcx, rax
0x180024673  jz      short loc_1800246B6
0x180024675  test    [rcx+1Ch], r15b
0x180024679  jz      short loc_1800246B6
0x18002467b  cmp     byte ptr [rcx+19h], 4
0x18002467f  jb      short loc_1800246B6
0x180024681  mov     rax, [rdi]
0x180024684  mov     r9, [rax]
0x180024687  mov     edx, 69h ; 'i'
0x18002468c  mov     [rsp+0E8h+var_B8], r13; __int64
0x180024691  mov     rax, [rax+40h]
0x180024695  mov     qword ptr [rsp+0E8h+OpenOptions], rax; __int64
0x18002469a  mov     eax, [r9+24h]
0x18002469e  mov     [rsp+0E8h+ShareAccess], eax; char
0x1800246a2  mov     r9d, [r9+10h]
0x1800246a6  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x1800246ad  mov     rcx, [rcx+10h]; LoggerHandle
0x1800246b1  call    WPP_SF_DDZZ
0x1800246b6  mov     rcx, r12
0x1800246b9  call    ?AddRef@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAXXZ; CHandleT<void *,NtHandleTrait>::AddRef(void)
0x1800246be  mov     qword ptr [rsp+0E8h+OpenOptions], r13; __int64
0x1800246c3  mov     [rsp+0E8h+ShareAccess], esi; int
0x1800246c7  mov     r9, r14
0x1800246ca  mov     r8, r12
0x1800246cd  mov     rdx, [rdi+588h]; struct _SCRUB_THREAD_CONTEXT *
0x1800246d4  mov     rcx, rdi; this
0x1800246d7  call    ?_ScanDirectoryEntries@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAV?$CHandleT@PEAXUNtHandleTrait@@@@PEAVCFileName@@W4_SCRUB_DIRECTORY_ENTRY_FLAGS@@PEBU_UNICODE_STRING@@@Z; CScrub::_ScanDirectoryEntries(_SCRUB_THREAD_CONTEXT *,CHandleT<void *,NtHandleTrait> *,CFileName *,_SCRUB_DIRECTORY_ENTRY_FLAGS,_UNICODE_STRING const *)
0x1800246dc  mov     r14d, eax
0x1800246df  mov     [rsp+0E8h+var_98], eax
0x1800246e3  mov     rcx, r12; Block
0x1800246e6  call    ?Release@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAEXZ; CHandleT<void *,NtHandleTrait>::Release(void)
0x1800246eb  nop
0x1800246ec  lea     rcx, [rsp+0E8h+arg_18]
0x1800246f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800246f9  cmp     r14d, ebx
0x1800246fc  jnz     short loc_18002470F
0x1800246fe  lea     rcx, [rsp+0E8h+var_A0]; this
0x180024703  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180024708  mov     eax, ebx
0x18002470a  jmp     loc_1800247A8
0x18002470f  jmp     short loc_18002471F
0x180024711  xor     esi, esi
0x180024713  lea     r15d, [rsi+1]
0x180024717  mov     rdi, [rsp+0E8h+arg_0]
0x18002471f  lea     rax, WPP_GLOBAL_Control
0x180024726  mov     rcx, cs:WPP_GLOBAL_Control
0x18002472d  cmp     rcx, rax
0x180024730  jz      short loc_180024781
0x180024732  test    [rcx+1Ch], r15b
0x180024736  jz      short loc_180024781
0x180024738  cmp     byte ptr [rcx+19h], 4
0x18002473c  jb      short loc_180024781
0x18002473e  mov     rax, [rdi]
0x180024741  mov     r9, [rax]
0x180024744  mov     edx, 6Bh ; 'k'
0x180024749  mov     r8, [rsp+0E8h+arg_10]
0x180024751  mov     [rsp+0E8h+var_B0], r8; __int64
0x180024756  mov     r8, [rsp+0E8h+arg_8]
0x18002475e  mov     [rsp+0E8h+var_B8], r8; __int64
0x180024763  mov     rax, [rax+40h]
0x180024767  mov     qword ptr [rsp+0E8h+OpenOptions], rax; __int64
0x18002476c  mov     eax, [r9+24h]
0x180024770  mov     [rsp+0E8h+ShareAccess], eax; char
0x180024774  mov     r9d, [r9+10h]
0x180024778  mov     rcx, [rcx+10h]; LoggerHandle
0x18002477c  call    WPP_SF_DDZZZ
0x180024781  mov     [rsp+0E8h+var_98], esi
0x180024785  lea     rcx, [rsp+0E8h+var_A0]; this
0x18002478a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002478f  xor     eax, eax
0x180024791  jmp     short loc_1800247A8
0x180024793  mov     ebx, 8007000Eh
0x180024798  mov     [rsp+0E8h+var_98], ebx
0x18002479c  lea     rcx, [rsp+0E8h+var_A0]; this
0x1800247a1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
  ... truncated ...
```
