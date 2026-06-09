# CScrub::_ScrubDirectoryInternal(_SCRUB_THREAD_CONTEXT *,_SCRUB_FILE_ID_128 *,CFileName *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS,_UNICODE_STRING const *)

- ea: `0x1800293d4`
- end: `0x1800299df`
- name: `?_ScrubDirectoryInternal@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAT_SCRUB_FILE_ID_128@@PEAVCFileName@@KW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@PEBU_UNICODE_STRING@@@Z`
- size: `1547`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, struct CFileName *, unsigned int, int, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800299f0`

## callees

- `0x180001b78`
- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x180009088`
- `0x180012048`
- `0x180012158`
- `0x1800129b0`
- `0x18001fde0`
- `0x180021ad8`
- `0x18002226c`
- `0x1800223bc`
- `0x180022450`
- `0x180027858`
- `0x18002892c`
- `0x180028fe4`
- `0x1800293d4`
- `0x18002ad9c`
- `0x18002bf78`
- `0x18002c0a0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800295da`
- `ntdll!NtOpenFile` at `0x1800295da`
- `KERNEL32!SetEvent` at `0x1800297af`
- `KERNEL32!SetEvent` at `0x1800297af`

## pseudocode

```c
__int64 __fastcall CScrub::_ScrubDirectoryInternal(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        struct CFileName *a4,
        unsigned int a5,
        int a6,
        const UNICODE_STRING *a7)
{
  __int64 v11; // rdx
  USHORT v12; // dx
  USHORT Length; // cx
  USHORT v14; // ax
  const struct _UNICODE_STRING *FullPathName; // rax
  const struct _UNICODE_STRING *v16; // r9
  struct _UNICODE_STRING *v17; // r14
  unsigned int v18; // ebx
  _WORD *v19; // rdi
  unsigned __int16 v20; // r15
  int v21; // r12d
  __int64 v22; // r8
  NTSTATUS v23; // eax
  int v24; // r8d
  int v25; // eax
  _DWORD *v26; // r12
  unsigned int v27; // r13d
  void *FileHandle; // [rsp+50h] [rbp-81h] BYREF
  int v30; // [rsp+58h] [rbp-79h]
  char v31; // [rsp+5Ch] [rbp-75h]
  const struct _UNICODE_STRING *v32; // [rsp+60h] [rbp-71h] BYREF
  int v33; // [rsp+68h] [rbp-69h]
  __int64 v34; // [rsp+70h] [rbp-61h]
  char *v35; // [rsp+78h] [rbp-59h]
  __int128 v36; // [rsp+80h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-31h] BYREF

  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v11 + 16) = &stru_18003ECF0;
  v32 = &stru_18003ECF0;
  v33 = 0;
  v12 = ++*(_WORD *)(v11 + 8);
  Length = GlobalIndentString.Length;
  v14 = GlobalIndentString.Length;
  if ( v12 < GlobalIndentString.Length )
    v14 = v12;
  LOWORD(v34) = v14;
  if ( v12 < GlobalIndentString.Length )
    Length = v12;
  WORD1(v34) = Length;
  HIDWORD(v34) = 0;
  v35 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&stru_18003ECF0);
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FullPathName = CScrub::_GetFullPathName((CScrub *)a1, (struct _SCRUB_THREAD_CONTEXT *)a2, a4, 0);
  v17 = (struct _UNICODE_STRING *)FullPathName;
  if ( FullPathName )
  {
    v19 = (_WORD *)(a2 + 88);
    v34 = a2 + 88;
    v20 = CScrubPath::PushNameEx((struct _UNICODE_STRING *)(a2 + 88), &EmptyUnicodeString, FullPathName, v16);
    LOWORD(v35) = v20;
    v36 = 0;
    if ( a3 )
    {
      v21 = 6316032;
      *((_QWORD *)&v36 + 1) = a3;
      LODWORD(v36) = 1048592;
      v17 = (struct _UNICODE_STRING *)&v36;
      v22 = a3[1];
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDZZii(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            a2 + 88,
            v22,
            *a3);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZi(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          a2 + 88,
          *a3);
      }
    }
    else
    {
      v21 = 6307840;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          a2 + 88);
      }
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = *(HANDLE *)(a1 + 24);
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = v17;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    IoStatusBlock = 0;
    FileHandle = 0;
    v30 = 0;
    v31 = 0;
    v23 = NtOpenFile(&FileHandle, 0x100081u, &ObjectAttributes, &IoStatusBlock, 7u, v21 | 0x20);
    if ( v23 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          112,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          a2 + 88,
          v23);
      }
      CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
      v18 = 0;
      goto LABEL_64;
    }
    v18 = -805306102;
    if ( a7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          (__int64)a7);
      }
      goto LABEL_54;
    }
    if ( !*(_WORD *)(a2 + 34464) )
    {
      v24 = CScrub::ScrubData(a1, a2, FileHandle, 0, 0);
      v33 = v24;
      if ( v24 == -805306102 )
      {
        SetEvent(*(HANDLE *)(a1 + 16));
LABEL_63:
        CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
LABEL_64:
        *v19 -= v20;
        goto LABEL_65;
      }
      if ( v24 >= 0 )
      {
        ++*(_QWORD *)(a2 + 1512);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          a2 + 88,
          v24);
      }
      if ( (*(_BYTE *)(a1 + 1260) & 8) == 0 )
      {
        v25 = CScrub::_ScrubAlternativeDataStreams(a1, (struct _SCRUB_THREAD_CONTEXT *)a2, FileHandle);
        v33 = v25;
        if ( v25 == -805306102 )
          goto LABEL_63;
        if ( v25 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DDZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            115,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            v25);
        }
      }
      if ( (*(_BYTE *)(a1 + 1260) & 2) == 0 )
      {
        v33 = CScrub::_ScrubNtfsSystemAttributes((CScrub *)a1, (struct _SCRUB_THREAD_CONTEXT *)a2, FileHandle, a5);
        if ( v33 == -805306102 )
          goto LABEL_63;
      }
    }
LABEL_54:
    v26 = operator new(0x10u);
    if ( v26 )
    {
      *(_QWORD *)v26 = 0;
      v26[2] = 0;
      *((_BYTE *)v26 + 12) = 0;
      *(_QWORD *)v26 = CHandleT<void *,NtHandleTrait>::Detach(&FileHandle);
      CHandleT<void *,NtHandleTrait>::AddRef(v26);
      v27 = CScrub::_ScanDirectoryEntries((CScrub *)a1, (struct _SCRUB_THREAD_CONTEXT *)a2, (HANDLE *)v26, a4, a6, a7);
      v33 = v27;
      if ( (int)(v27 + 0x80000000) >= 0
        && v27 != -805306102
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)a1 + 16LL),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          v27);
      }
      CHandleT<void *,NtHandleTrait>::Release(v26);
      CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
      v18 = v27;
      goto LABEL_64;
    }
    v18 = -2147024882;
    v33 = -2147024882;
    goto LABEL_63;
  }
  v18 = -2147024882;
  v33 = -2147024882;
LABEL_65:
  CHResultImp::~CHResultImp((CHResultImp *)&v32);
  return v18;
}

```

## disassembly

```asm
0x1800293d4  mov     [rsp-8+arg_18], r9
0x1800293d9  push    rbp
0x1800293da  push    rbx
0x1800293db  push    rsi
0x1800293dc  push    rdi
0x1800293dd  push    r12
0x1800293df  push    r13
0x1800293e1  push    r14
0x1800293e3  push    r15
0x1800293e5  lea     rbp, [rsp-7]
0x1800293ea  sub     rsp, 0D8h
0x1800293f1  mov     rdi, r9
0x1800293f4  mov     rbx, r8
0x1800293f7  mov     r13, rdx
0x1800293fa  mov     rsi, rcx
0x1800293fd  mov     r10d, cs:_tls_index
0x180029404  mov     rax, gs:58h
0x18002940d  mov     rdx, [rax+r10*8]
0x180029411  mov     eax, 10h
0x180029416  lea     r9, stru_18003ECF0
0x18002941d  mov     [rax+rdx], r9
0x180029421  mov     [rbp+3Fh+var_B0], r9
0x180029425  xor     r12d, r12d
0x180029428  mov     [rbp+3Fh+var_A8], r12d
0x18002942c  mov     eax, 8
0x180029431  lea     r8d, [r12+1]
0x180029436  add     [rax+rdx], r8w
0x18002943b  movzx   edx, word ptr [rax+rdx]
0x18002943f  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180029446  movzx   eax, cx
0x180029449  cmp     dx, cx
0x18002944c  cmovb   ax, dx
0x180029450  mov     word ptr [rbp+3Fh+var_A0], ax
0x180029454  cmovb   cx, dx
0x180029458  mov     word ptr [rbp+3Fh+var_A0+2], cx
0x18002945c  xor     eax, eax
0x18002945e  mov     dword ptr [rbp+3Fh+var_A0+4], eax
0x180029461  mov     rax, cs:off_180047060; "                                       "...
0x180029468  mov     [rbp+3Fh+var_98], rax
0x18002946c  lea     rax, WPP_GLOBAL_Control
0x180029473  mov     rcx, cs:WPP_GLOBAL_Control
0x18002947a  cmp     rcx, rax
0x18002947d  jz      short loc_1800294A3
0x18002947f  test    [rcx+1Ch], r8b
0x180029483  jz      short loc_1800294A3
0x180029485  cmp     byte ptr [rcx+19h], 5
0x180029489  jb      short loc_1800294A3
0x18002948b  lea     edx, [r12+0Dh]
0x180029490  mov     qword ptr [rsp+110h+ShareAccess], r9; struct _UNICODE_STRING *
0x180029495  lea     r9, [rbp+3Fh+var_A0]
0x180029499  mov     rcx, [rcx+10h]; LoggerHandle
0x18002949d  call    WPP_SF_aZs
0x1800294a2  nop
0x1800294a3  xorps   xmm0, xmm0
0x1800294a6  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x1800294aa  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x1800294ae  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800294b2  xor     r9d, r9d; struct _UNICODE_STRING *
0x1800294b5  mov     r8, rdi; struct CFileName *
0x1800294b8  mov     rdx, r13; struct _SCRUB_THREAD_CONTEXT *
0x1800294bb  mov     rcx, rsi; this
0x1800294be  call    ?_GetFullPathName@CScrub@@AEAAPEBU_UNICODE_STRING@@PEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU2@2@Z; CScrub::_GetFullPathName(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800294c3  mov     r14, rax
0x1800294c6  test    rax, rax
0x1800294c9  jnz     short loc_1800294D8
0x1800294cb  mov     ebx, 8007000Eh
0x1800294d0  mov     [rbp+3Fh+var_A8], ebx
0x1800294d3  jmp     loc_1800299C0
0x1800294d8  lea     rdi, [r13+58h]
0x1800294dc  mov     [rbp+3Fh+var_A0], rdi
0x1800294e0  mov     r8, rax; struct _UNICODE_STRING *
0x1800294e3  lea     rdx, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800294ea  mov     rcx, rdi; this
0x1800294ed  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800294f2  movzx   r15d, ax
0x1800294f6  mov     word ptr [rbp+3Fh+var_98], ax
0x1800294fa  xorps   xmm0, xmm0
0x1800294fd  movups  [rbp+3Fh+var_90], xmm0
0x180029501  mov     dl, 4
0x180029503  test    rbx, rbx
0x180029506  jz      loc_18002969B
0x18002950c  mov     r12d, 606000h
0x180029512  mov     qword ptr [rbp+3Fh+var_90+8], rbx
0x180029516  mov     dword ptr [rbp+3Fh+var_90], 100010h
0x18002951d  lea     r14, [rbp+3Fh+var_90]
0x180029521  mov     r8, [rbx+8]
0x180029525  test    r8, r8
0x180029528  jnz     loc_180029636
0x18002952e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029535  lea     rax, WPP_GLOBAL_Control
0x18002953c  cmp     rcx, rax
0x18002953f  jz      short loc_18002957D
0x180029541  test    byte ptr [rcx+1Ch], 1
0x180029545  jz      short loc_18002957D
0x180029547  cmp     [rcx+19h], dl
0x18002954a  jb      short loc_18002957D
0x18002954c  mov     rdx, [rsi]
0x18002954f  mov     r9, [rdx]
0x180029552  mov     rax, [rbx]
0x180029555  mov     qword ptr [rsp+110h+var_D8], rax; char
0x18002955a  mov     [rsp+110h+var_E0], rdi; __int64
0x18002955f  mov     rax, [rdx+40h]
0x180029563  mov     qword ptr [rsp+110h+OpenOptions], rax; __int64
0x180029568  mov     eax, [r9+24h]
0x18002956c  mov     [rsp+110h+ShareAccess], eax; char
0x180029570  mov     r9d, [r9+10h]
0x180029574  mov     rcx, [rcx+10h]; LoggerHandle
0x180029578  call    WPP_SF_DDZZi
0x18002957d  lea     rbx, WPP_GLOBAL_Control
0x180029584  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18002958b  mov     rax, [rsi+18h]
0x18002958f  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rax
0x180029593  mov     [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18002959a  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r14
0x18002959e  xorps   xmm0, xmm0
0x1800295a1  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800295a6  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x1800295aa  xor     eax, eax
0x1800295ac  mov     [rsp+110h+FileHandle], rax
0x1800295b1  mov     [rbp+3Fh+var_B8], eax
0x1800295b4  mov     [rbp+3Fh+var_B4], al
0x1800295b7  or      r12d, 20h
0x1800295bb  mov     [rsp+110h+OpenOptions], r12d; OpenOptions
0x1800295c0  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800295c8  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x1800295cc  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1800295d0  mov     edx, 100081h; DesiredAccess
0x1800295d5  lea     rcx, [rsp+110h+FileHandle]; FileHandle
0x1800295da  call    cs:__imp_NtOpenFile
0x1800295e0  xor     r12d, r12d
0x1800295e3  test    eax, eax
0x1800295e5  jns     loc_180029705
0x1800295eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800295f2  cmp     rcx, rbx
0x1800295f5  jz      short loc_180029623
0x1800295f7  test    byte ptr [rcx+1Ch], 1
0x1800295fb  jz      short loc_180029623
0x1800295fd  mov     r14b, 2
0x180029600  cmp     [rcx+19h], r14b
0x180029604  jb      short loc_180029623
0x180029606  lea     edx, [r12+70h]
0x18002960b  mov     [rsp+110h+ShareAccess], eax
0x18002960f  mov     r9, rdi
0x180029612  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180029619  mov     rcx, [rcx+10h]
0x18002961d  call    WPP_SF_Zd
0x180029622  nop
0x180029623  lea     rcx, [rsp+110h+FileHandle]
0x180029628  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x18002962d  nop
0x18002962e  mov     ebx, r12d
0x180029631  jmp     loc_1800299BC
0x180029636  mov     rcx, cs:WPP_GLOBAL_Control
0x18002963d  lea     rax, WPP_GLOBAL_Control
0x180029644  cmp     rcx, rax
0x180029647  jz      loc_18002957D
0x18002964d  test    byte ptr [rcx+1Ch], 1
0x180029651  jz      loc_18002957D
0x180029657  cmp     [rcx+19h], dl
0x18002965a  jb      loc_18002957D
0x180029660  mov     rdx, [rsi]
0x180029663  mov     r9, [rdx]
0x180029666  mov     rax, [rbx]
0x180029669  mov     qword ptr [rsp+110h+var_D0], rax; char
0x18002966e  mov     qword ptr [rsp+110h+var_D8], r8; char
0x180029673  mov     [rsp+110h+var_E0], rdi; __int64
0x180029678  mov     rax, [rdx+40h]
0x18002967c  mov     qword ptr [rsp+110h+OpenOptions], rax; __int64
0x180029681  mov     eax, [r9+24h]
0x180029685  mov     [rsp+110h+ShareAccess], eax; char
0x180029689  mov     r9d, [r9+10h]
0x18002968d  mov     rcx, [rcx+10h]; LoggerHandle
0x180029691  call    WPP_SF_DDZZii
0x180029696  jmp     loc_18002957D
0x18002969b  mov     r12d, 604000h
0x1800296a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296a8  lea     rbx, WPP_GLOBAL_Control
0x1800296af  cmp     rcx, rbx
0x1800296b2  jz      loc_180029584
0x1800296b8  test    byte ptr [rcx+1Ch], 1
0x1800296bc  jz      loc_180029584
0x1800296c2  cmp     [rcx+19h], dl
0x1800296c5  jb      loc_180029584
0x1800296cb  mov     rax, [rsi]
0x1800296ce  mov     r9, [rax]
0x1800296d1  mov     edx, 6Fh ; 'o'
0x1800296d6  mov     [rsp+110h+var_E0], rdi; __int64
0x1800296db  mov     rax, [rax+40h]
0x1800296df  mov     qword ptr [rsp+110h+OpenOptions], rax; __int64
0x1800296e4  mov     eax, [r9+24h]
0x1800296e8  mov     [rsp+110h+ShareAccess], eax; char
0x1800296ec  mov     r9d, [r9+10h]
0x1800296f0  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x1800296f7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800296fb  call    WPP_SF_DDZZ
0x180029700  jmp     loc_180029584
0x180029705  mov     r14b, 2
0x180029708  mov     ebx, 0D000010Ah
0x18002970d  mov     r8, [rbp+3Fh+arg_30]
0x180029711  test    r8, r8
0x180029714  jz      short loc_18002977B
0x180029716  mov     rcx, cs:WPP_GLOBAL_Control
0x18002971d  lea     rax, WPP_GLOBAL_Control
0x180029724  cmp     rcx, rax
0x180029727  jz      loc_1800298C8
0x18002972d  test    byte ptr [rcx+1Ch], 1
0x180029731  jz      loc_1800298C8
0x180029737  cmp     byte ptr [rcx+19h], 4
0x18002973b  jb      loc_1800298C8
0x180029741  mov     rax, [rsi]
0x180029744  mov     r9, [rax]
0x180029747  mov     edx, 71h ; 'q'
0x18002974c  mov     [rsp+110h+var_E0], r8; __int64
0x180029751  mov     rax, [rax+40h]
0x180029755  mov     qword ptr [rsp+110h+OpenOptions], rax; __int64
0x18002975a  mov     eax, [r9+24h]
0x18002975e  mov     [rsp+110h+ShareAccess], eax; char
0x180029762  mov     r9d, [r9+10h]
0x180029766  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002976d  mov     rcx, [rcx+10h]; LoggerHandle
0x180029771  call    WPP_SF_DDZZ
0x180029776  jmp     loc_1800298C8
0x18002977b  cmp     [r13+86A0h], r12w
0x180029783  ja      loc_1800298C8
0x180029789  mov     qword ptr [rsp+110h+ShareAccess], r12
0x18002978e  xor     r9d, r9d
0x180029791  mov     r8, [rsp+110h+FileHandle]
0x180029796  mov     rdx, r13
0x180029799  mov     rcx, rsi
0x18002979c  call    ?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)
0x1800297a1  mov     r8d, eax
0x1800297a4  mov     [rbp+3Fh+var_A8], eax
0x1800297a7  cmp     eax, ebx
0x1800297a9  jnz     short loc_1800297BA
0x1800297ab  mov     rcx, [rsi+10h]; hEvent
0x1800297af  call    cs:__imp_SetEvent
0x1800297b5  jmp     loc_1800299B1
0x1800297ba  test    r8d, r8d
0x1800297bd  jns     short loc_18002981A
0x1800297bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297c6  lea     rax, WPP_GLOBAL_Control
0x1800297cd  cmp     rcx, rax
0x1800297d0  jz      short loc_180029821
0x1800297d2  test    byte ptr [rcx+1Ch], 1
0x1800297d6  jz      short loc_180029821
0x1800297d8  cmp     [rcx+19h], r14b
0x1800297dc  jb      short loc_180029821
0x1800297de  mov     rax, [rsi]
0x1800297e1  mov     r9, [rax]
0x1800297e4  mov     edx, 72h ; 'r'
0x1800297e9  mov     dword ptr [rsp+110h+var_D8], r8d; char
0x1800297ee  mov     [rsp+110h+var_E0], rdi; __int64
0x1800297f3  mov     rax, [rax+40h]
0x1800297f7  mov     qword ptr [rsp+110h+OpenOptions], rax; __int64
0x1800297fc  mov     eax, [r9+24h]
0x180029800  mov     [rsp+110h+ShareAccess], eax; char
0x180029804  mov     r9d, [r9+10h]
0x180029808  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002980f  mov     rcx, [rcx+10h]; LoggerHandle
0x180029813  call    WPP_SF_DDZZd
0x180029818  jmp     short loc_180029821
0x18002981a  inc     qword ptr [r13+5E8h]
0x180029821  test    byte ptr [rsi+4ECh], 8
0x180029828  jnz     short loc_1800298A0
0x18002982a  mov     r8, [rsp+110h+FileHandle]
0x18002982f  mov     rdx, r13
0x180029832  mov     rcx, rsi
0x180029835  call    ?_ScrubAlternativeDataStreams@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXKW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@@Z; CScrub::_ScrubAlternativeDataStreams(_SCRUB_THREAD_CONTEXT *,void *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS)
0x18002983a  mov     r8d, eax
0x18002983d  mov     [rbp+3Fh+var_A8], eax
0x180029840  cmp     eax, ebx
0x180029842  jz      loc_1800299B1
0x180029848  test    eax, eax
0x18002984a  jns     short loc_1800298A0
0x18002984c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029853  lea     rax, WPP_GLOBAL_Control
0x18002985a  cmp     rcx, rax
0x18002985d  jz      short loc_1800298A0
0x18002985f  test    byte ptr [rcx+1Ch], 1
0x180029863  jz      short loc_1800298A0
0x180029865  cmp     [rcx+19h], r14b
0x180029869  jb      short loc_1800298A0
0x18002986b  mov     rax, [rsi]
0x18002986e  mov     r9, [rax]
0x180029871  mov     edx, 73h ; 's'
0x180029876  mov     dword ptr [rsp+110h+var_E0], r8d
0x18002987b  mov     rax, [rax+40h]
0x18002987f  mov     qword ptr [rsp+110h+OpenOptions], rax
0x180029884  mov     eax, [r9+24h]
0x180029888  mov     [rsp+110h+ShareAccess], eax
0x18002988c  mov     r9d, [r9+10h]
0x180029890  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180029897  mov     rcx, [rcx+10h]
0x18002989b  call    WPP_SF_DDZd
0x1800298a0  test    [rsi+4ECh], r14b
0x1800298a7  jnz     short loc_1800298C8
0x1800298a9  mov     r9d, [rbp+3Fh+arg_20]; unsigned int
0x1800298ad  mov     r8, [rsp+110h+FileHandle]; void *
0x1800298b2  mov     rdx, r13; struct _SCRUB_THREAD_CONTEXT *
0x1800298b5  mov     rcx, rsi; this
  ... truncated ...
```
