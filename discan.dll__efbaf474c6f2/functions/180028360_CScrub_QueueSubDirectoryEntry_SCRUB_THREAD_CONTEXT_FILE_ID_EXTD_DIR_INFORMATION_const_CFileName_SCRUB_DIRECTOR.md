# CScrub::_QueueSubDirectoryEntry(_SCRUB_THREAD_CONTEXT *,_FILE_ID_EXTD_DIR_INFORMATION const *,CFileName *,_SCRUB_DIRECTORY_ENTRY_FLAGS,bool)

- ea: `0x180028360`
- end: `0x1800288a4`
- name: `?_QueueSubDirectoryEntry@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEBU_FILE_ID_EXTD_DIR_INFORMATION@@PEAVCFileName@@W4_SCRUB_DIRECTORY_ENTRY_FLAGS@@_N@Z`
- size: `1348`
- prototype: `__int64 __fastcall(__int64, struct _SCRUB_THREAD_CONTEXT *, __int64, struct CFileName *, __int64, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002892c`

## callees

- `0x180001b78`
- `0x180003134`
- `0x1800032f8`
- `0x180006688`
- `0x1800137d4`
- `0x18001fde0`
- `0x180020cec`
- `0x180021aac`
- `0x180021c48`
- `0x180027858`
- `0x180028360`
- `0x18002bc58`
- `0x18002bddc`
- `0x18002c6f8`
- `0x180039010`

## import_xrefs

- `ntdll!NtSetEvent` at `0x18002876a`
- `ntdll!NtSetEvent` at `0x18002876a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002883a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002883a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180028692`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180028692`
- `KERNEL32!SubmitThreadpoolWork` at `0x180028831`
- `KERNEL32!SubmitThreadpoolWork` at `0x180028831`

## pseudocode

```c
__int64 __fastcall CScrub::_QueueSubDirectoryEntry(
        __int64 a1,
        struct _SCRUB_THREAD_CONTEXT *a2,
        __int64 a3,
        struct CFileName *a4,
        __int64 a5,
        char a6)
{
  __int64 v10; // rdx
  USHORT v11; // dx
  USHORT Length; // cx
  USHORT v13; // ax
  _OWORD *v14; // rax
  __int64 v15; // rdi
  __int64 result; // rax
  RTL_SRWLOCK *v17; // rax
  CFileName *v18; // r14
  const struct _UNICODE_STRING *FullPathName; // rax
  __int64 v20; // rbx
  __int64 v21; // r10
  __int64 *v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rax
  __int64 *v26; // rdi
  __int64 v27; // rcx
  int v28; // ebx
  unsigned int v29; // [rsp+50h] [rbp-68h] BYREF
  RTL_SRWLOCK *v30[2]; // [rsp+58h] [rbp-60h] BYREF
  const struct _UNICODE_STRING *v31; // [rsp+68h] [rbp-50h] BYREF
  int v32; // [rsp+70h] [rbp-48h]
  struct _UNICODE_STRING v33; // [rsp+78h] [rbp-40h] BYREF
  __int64 v35; // [rsp+D0h] [rbp+18h] BYREF

  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v10 + 16) = &stru_18003EDC0;
  v31 = &stru_18003EDC0;
  v32 = 0;
  v11 = ++*(_WORD *)(v10 + 8);
  Length = GlobalIndentString.Length;
  v13 = GlobalIndentString.Length;
  if ( v11 < GlobalIndentString.Length )
    v13 = v11;
  LOWORD(v30[0]) = v13;
  if ( v11 < GlobalIndentString.Length )
    Length = v11;
  WORD1(v30[0]) = Length;
  HIDWORD(v30[0]) = 0;
  v30[1] = (RTL_SRWLOCK *)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&stru_18003EDC0);
  }
  try
  {
    *(_QWORD *)&v33.Length = 0;
    v33.Buffer = (PWSTR)(a3 + 88);
    v33.MaximumLength = *(_WORD *)(a3 + 60);
    v33.Length = v33.MaximumLength;
    v14 = operator new(0x30u);
    v15 = (__int64)v14;
    if ( v14 )
    {
      *v14 = 0;
      v14[1] = 0;
      v14[2] = 0;
    }
    else
    {
      v15 = 0;
    }
    v35 = v15;
    if ( !v15 )
    {
      v32 = -2147024882;
      CHResultImp::~CHResultImp((CHResultImp *)&v31);
      return 2147942414LL;
    }
    v17 = (RTL_SRWLOCK *)operator new(0x30u);
    v30[0] = v17;
    if ( v17 )
      v18 = CFileName::CFileName((CFileName *)v17, a4, &v33);
    else
      v18 = 0;
    if ( v18 )
      (*(void (__fastcall **)(CFileName *))(*(_QWORD *)v18 + 8LL))(v18);
    *(_QWORD *)(v15 + 16) = *(unsigned int *)(a3 + 56);
    *(_OWORD *)(v15 + 24) = *(_OWORD *)(a3 + 72);
    v35 = 0;
    ATL::CComPtrBase<CFileName>::Attach(v15 + 40, v18);
    FullPathName = CScrub::_GetFullPathName((CScrub *)a1, a2, *(struct CFileName **)(v15 + 40), 0);
    v20 = (__int64)FullPathName;
    if ( !FullPathName )
    {
      v32 = -2147024882;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'((_SCRUB_DIRECTORY_ENTRY *)v15);
      CHResultImp::~CHResultImp((CHResultImp *)&v31);
      return 2147942414LL;
    }
    v21 = *(_QWORD *)(v15 + 32);
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZZii(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          (__int64)FullPathName,
          v21,
          *(_QWORD *)(v15 + 24));
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZi(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        (__int64)FullPathName,
        *(_QWORD *)(v15 + 24));
    }
    if ( a6 )
    {
      *((_QWORD *)a2 + 4311) = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          v20);
      }
    }
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 1448));
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 8LL) == 1 )
    {
      v22 = *(__int64 **)(a1 + 1440);
      if ( *v22 != a1 + 1432 )
        goto LABEL_55;
      *(_QWORD *)v15 = a1 + 1432;
      *(_QWORD *)(v15 + 8) = v22;
      *v22 = v15;
      *(_QWORD *)(a1 + 1440) = v15;
    }
    else
    {
      v23 = (__int64 *)*((_QWORD *)a2 + 4304);
      v24 = *v23;
      if ( *(__int64 **)(*v23 + 8) != v23 )
        goto LABEL_55;
      *(_QWORD *)v15 = v24;
      *(_QWORD *)(v15 + 8) = v23;
      *(_QWORD *)(v24 + 8) = v15;
      *v23 = v15;
      *((_QWORD *)a2 + 4304) = v15;
    }
    if ( *(_DWORD *)(a1 + 1344) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZdd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          157,
          ((unsigned __int64)a2 - *(_QWORD *)(a1 + 1416)) / 0x88D0,
          *(_DWORD *)(**(_QWORD **)a1 + 16LL),
          *(_DWORD *)(**(_QWORD **)a1 + 36LL),
          *(_QWORD *)(*(_QWORD *)a1 + 64LL),
          ((unsigned __int64)a2 - *(_QWORD *)(a1 + 1416)) / 0x88D0,
          *(_DWORD *)(a1 + 1344));
      }
      NtSetEvent(*(HANDLE *)(a1 + 1168), 0);
      goto LABEL_54;
    }
    v25 = (_QWORD *)(a1 + 1352);
    v26 = *(__int64 **)(a1 + 1352);
    if ( v26 == (__int64 *)(a1 + 1352) )
    {
LABEL_54:
      ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 1448));
      v30[0] = 0;
      CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(v30);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      v32 = 0;
      CHResultImp::~CHResultImp((CHResultImp *)&v31);
      return 0;
    }
    if ( (_QWORD *)v26[1] == v25 )
    {
      v27 = *v26;
      if ( *(__int64 **)(*v26 + 8) == v26 )
      {
        *v25 = v27;
        *(_QWORD *)(v27 + 8) = v25;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDZdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            158,
            ((unsigned __int64)a2 - *(_QWORD *)(a1 + 1416)) / 0x88D0,
            *(_DWORD *)(**(_QWORD **)a1 + 16LL),
            *(_DWORD *)(**(_QWORD **)a1 + 36LL),
            *(_QWORD *)(*(_QWORD *)a1 + 64LL),
            ((unsigned __int64)a2 - *(_QWORD *)(a1 + 1416)) / 0x88D0,
            ((unsigned __int64)v26 - *(_QWORD *)(a1 + 1416)) / 0x88D0);
        }
        SubmitThreadpoolWork((PTP_WORK)v26[2]);
        goto LABEL_54;
      }
    }
LABEL_55:
    __fastfail(3u);
  }
  catch ( ATL::CAtlException v29 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v28 = v29;
    }
    else
    {
      v28 = v29;
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        159,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)a1 + 16LL),
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        v29);
    }
    v32 = v28;
    CHResultImp::~CHResultImp((CHResultImp *)&v31);
    return v29;
  }
  *(_QWORD *)&v33.Length = 0;
}

```

## disassembly

```asm
0x180028360  mov     r11, rsp
0x180028363  mov     [r11+10h], rbx
0x180028367  mov     [r11+8], rcx
0x18002836b  push    rsi
0x18002836c  push    rdi
0x18002836d  push    r12
0x18002836f  push    r14
0x180028371  push    r15
0x180028373  sub     rsp, 90h
0x18002837a  mov     r14, r9
0x18002837d  mov     rbx, r8
0x180028380  mov     r15, rdx
0x180028383  mov     rsi, rcx
0x180028386  mov     r10d, cs:_tls_index
0x18002838d  mov     rax, gs:58h
0x180028396  mov     rdx, [rax+r10*8]
0x18002839a  mov     eax, 10h
0x18002839f  lea     r8, stru_18003EDC0
0x1800283a6  mov     [rax+rdx], r8
0x1800283aa  mov     [r11-50h], r8
0x1800283ae  mov     [rsp+0B8h+var_48], 0
0x1800283b6  mov     eax, 8
0x1800283bb  mov     r12d, 1
0x1800283c1  add     [rax+rdx], r12w
0x1800283c6  movzx   edx, word ptr [rax+rdx]
0x1800283ca  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800283d1  movzx   eax, cx
0x1800283d4  cmp     dx, cx
0x1800283d7  cmovb   ax, dx
0x1800283db  mov     word ptr [rsp+0B8h+var_60], ax
0x1800283e0  cmovb   cx, dx
0x1800283e4  mov     word ptr [rsp+0B8h+var_60+2], cx
0x1800283e9  xor     eax, eax
0x1800283eb  mov     dword ptr [rsp+0B8h+var_60+4], eax
0x1800283ef  mov     rax, cs:off_180047060; "                                       "...
0x1800283f6  mov     [r11-58h], rax
0x1800283fa  lea     rax, WPP_GLOBAL_Control
0x180028401  mov     rcx, cs:WPP_GLOBAL_Control
0x180028408  cmp     rcx, rax
0x18002840b  jz      short loc_180028431
0x18002840d  test    [rcx+1Ch], r12b
0x180028411  jz      short loc_180028431
0x180028413  cmp     byte ptr [rcx+19h], 5
0x180028417  jb      short loc_180028431
0x180028419  lea     edx, [r12+0Ch]
0x18002841e  mov     [rsp+0B8h+var_98], r8; struct _UNICODE_STRING *
0x180028423  lea     r9, [r11-60h]
0x180028427  mov     rcx, [rcx+10h]; LoggerHandle
0x18002842b  call    WPP_SF_aZs
0x180028430  nop
0x180028431  xorps   xmm0, xmm0
0x180028434  movups  xmmword ptr [rsp+0B8h+var_40.Length], xmm0
0x180028439  lea     rax, [rbx+58h]
0x18002843d  mov     [rsp+0B8h+var_40.Buffer], rax
0x180028445  movzx   eax, word ptr [rbx+3Ch]
0x180028449  mov     [rsp+0B8h+var_40.MaximumLength], ax
0x18002844e  mov     [rsp+0B8h+var_40.Length], ax
0x180028453  mov     ecx, 30h ; '0'; Size
0x180028458  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002845d  mov     rdi, rax
0x180028460  test    rax, rax
0x180028463  jz      short loc_180028475
0x180028465  xorps   xmm0, xmm0
0x180028468  movups  xmmword ptr [rax], xmm0
0x18002846b  movups  xmmword ptr [rax+10h], xmm0
0x18002846f  movups  xmmword ptr [rax+20h], xmm0
0x180028473  jmp     short loc_180028477
0x180028475  xor     edi, edi
0x180028477  mov     [rsp+0B8h+arg_10], rdi
0x18002847f  test    rdi, rdi
0x180028482  jnz     short loc_18002849E
0x180028484  mov     ebx, 8007000Eh
0x180028489  mov     [rsp+0B8h+var_48], ebx
0x18002848d  lea     rcx, [rsp+0B8h+var_50]; this
0x180028492  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180028497  mov     eax, ebx
0x180028499  jmp     loc_18002888C
0x18002849e  mov     ecx, 30h ; '0'; Size
0x1800284a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800284a8  mov     [rsp+0B8h+var_60], rax
0x1800284ad  test    rax, rax
0x1800284b0  jz      short loc_1800284C7
0x1800284b2  lea     r8, [rsp+0B8h+var_40]; struct _UNICODE_STRING *
0x1800284b7  mov     rdx, r14; struct CFileName *
0x1800284ba  mov     rcx, rax; this
0x1800284bd  call    ??0CFileName@@QEAA@PEAV0@PEBU_UNICODE_STRING@@@Z; CFileName::CFileName(CFileName *,_UNICODE_STRING const *)
0x1800284c2  mov     r14, rax
0x1800284c5  jmp     short loc_1800284CA
0x1800284c7  xor     r14d, r14d
0x1800284ca  test    r14, r14
0x1800284cd  jz      short loc_1800284DF
0x1800284cf  mov     rax, [r14]
0x1800284d2  mov     rcx, r14
0x1800284d5  mov     rax, [rax+8]
0x1800284d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284de  nop
0x1800284df  mov     eax, [rbx+38h]
0x1800284e2  mov     [rdi+10h], eax
0x1800284e5  mov     dword ptr [rdi+14h], 0
0x1800284ec  movups  xmm0, xmmword ptr [rbx+48h]
0x1800284f0  movdqu  xmmword ptr [rdi+18h], xmm0
0x1800284f5  mov     [rsp+0B8h+arg_10], 0
0x180028501  mov     rdx, r14
0x180028504  lea     rcx, [rdi+28h]
0x180028508  call    ?Attach@?$CComPtrBase@VCFileName@@@ATL@@QEAAXPEAVCFileName@@@Z; ATL::CComPtrBase<CFileName>::Attach(CFileName *)
0x18002850d  xor     r9d, r9d; struct _UNICODE_STRING *
0x180028510  mov     r8, [rdi+28h]; struct CFileName *
0x180028514  mov     rdx, r15; struct _SCRUB_THREAD_CONTEXT *
0x180028517  mov     rcx, rsi; this
0x18002851a  call    ?_GetFullPathName@CScrub@@AEAAPEBU_UNICODE_STRING@@PEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU2@2@Z; CScrub::_GetFullPathName(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002851f  mov     rbx, rax
0x180028522  test    rax, rax
0x180028525  jnz     short loc_180028558
0x180028527  mov     ebx, 8007000Eh
0x18002852c  mov     [rsp+0B8h+var_48], ebx
0x180028530  lea     rcx, [rsp+0B8h+arg_10]
0x180028538  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002853d  nop
0x18002853e  mov     rcx, rdi; this
0x180028541  call    ??_G_SCRUB_DIRECTORY_ENTRY@@QEAAPEAXI@Z; _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'(uint)
0x180028546  nop
0x180028547  lea     rcx, [rsp+0B8h+var_50]; this
0x18002854c  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180028551  mov     eax, ebx
0x180028553  jmp     loc_18002888C
0x180028558  mov     r10, [rdi+20h]
0x18002855c  test    r10, r10
0x18002855f  jnz     short loc_1800285CA
0x180028561  mov     rcx, cs:WPP_GLOBAL_Control
0x180028568  lea     r14, WPP_GLOBAL_Control
0x18002856f  cmp     rcx, r14
0x180028572  jz      loc_18002862A
0x180028578  test    [rcx+1Ch], r12b
0x18002857c  jz      loc_18002862A
0x180028582  cmp     byte ptr [rcx+19h], 4
0x180028586  jb      loc_18002862A
0x18002858c  mov     rax, [rsi]
0x18002858f  mov     r8, [rax+40h]
0x180028593  mov     r9, [rax]
0x180028596  mov     edx, 99h
0x18002859b  mov     rax, [rdi+18h]
0x18002859f  mov     qword ptr [rsp+0B8h+var_78], rax; char
0x1800285a4  mov     [rsp+0B8h+var_80], rbx; __int64
0x1800285a9  mov     [rsp+0B8h+var_88], r8; __int64
0x1800285ae  mov     [rsp+0B8h+var_90], r8; __int64
0x1800285b3  mov     eax, [r9+24h]
0x1800285b7  mov     dword ptr [rsp+0B8h+var_98], eax; char
0x1800285bb  mov     r9d, [r9+10h]
0x1800285bf  mov     rcx, [rcx+10h]; LoggerHandle
0x1800285c3  call    WPP_SF_DDZZZi
0x1800285c8  jmp     short loc_18002862A
0x1800285ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285d1  lea     r14, WPP_GLOBAL_Control
0x1800285d8  cmp     rcx, r14
0x1800285db  jz      short loc_18002862A
0x1800285dd  test    [rcx+1Ch], r12b
0x1800285e1  jz      short loc_18002862A
0x1800285e3  cmp     byte ptr [rcx+19h], 4
0x1800285e7  jb      short loc_18002862A
0x1800285e9  mov     rax, [rsi]
0x1800285ec  mov     r8, [rax+40h]
0x1800285f0  mov     r9, [rax]
0x1800285f3  mov     edx, 9Ah
0x1800285f8  mov     rax, [rdi+18h]
0x1800285fc  mov     qword ptr [rsp+0B8h+var_70], rax; char
0x180028601  mov     qword ptr [rsp+0B8h+var_78], r10; char
0x180028606  mov     [rsp+0B8h+var_80], rbx; __int64
0x18002860b  mov     [rsp+0B8h+var_88], r8; __int64
0x180028610  mov     [rsp+0B8h+var_90], r8; __int64
0x180028615  mov     eax, [r9+24h]
0x180028619  mov     dword ptr [rsp+0B8h+var_98], eax; char
0x18002861d  mov     r9d, [r9+10h]
0x180028621  mov     rcx, [rcx+10h]; LoggerHandle
0x180028625  call    WPP_SF_DDZZZii
0x18002862a  cmp     [rsp+0B8h+arg_28], 0
0x180028632  jz      short loc_180028688
0x180028634  mov     [r15+86B8h], rdi
0x18002863b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028642  cmp     rcx, r14
0x180028645  jz      short loc_180028688
0x180028647  test    [rcx+1Ch], r12b
0x18002864b  jz      short loc_180028688
0x18002864d  cmp     byte ptr [rcx+19h], 4
0x180028651  jb      short loc_180028688
0x180028653  mov     rax, [rsi]
0x180028656  mov     r9, [rax]
0x180028659  mov     edx, 9Ch
0x18002865e  mov     [rsp+0B8h+var_88], rbx; __int64
0x180028663  mov     rax, [rax+40h]
0x180028667  mov     [rsp+0B8h+var_90], rax; __int64
0x18002866c  mov     eax, [r9+24h]
0x180028670  mov     dword ptr [rsp+0B8h+var_98], eax; char
0x180028674  mov     r9d, [r9+10h]
0x180028678  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002867f  mov     rcx, [rcx+10h]; LoggerHandle
0x180028683  call    WPP_SF_DDZZ
0x180028688  lea     rbx, [rsi+5A8h]
0x18002868f  mov     rcx, rbx; SRWLock
0x180028692  call    cs:__imp_AcquireSRWLockExclusive
0x180028698  mov     rax, [rsi+8]
0x18002869c  cmp     [rax+8], r12d
0x1800286a0  jnz     short loc_1800286C6
0x1800286a2  lea     rax, [rsi+598h]
0x1800286a9  mov     rcx, [rax+8]
0x1800286ad  cmp     [rcx], rax
0x1800286b0  jnz     loc_180028877
0x1800286b6  mov     [rdi], rax
0x1800286b9  mov     [rdi+8], rcx
0x1800286bd  mov     [rcx], rdi
0x1800286c0  mov     [rax+8], rdi
0x1800286c4  jmp     short loc_1800286EF
0x1800286c6  mov     rax, [r15+8680h]
0x1800286cd  mov     rcx, [rax]
0x1800286d0  cmp     [rcx+8], rax
0x1800286d4  jnz     loc_180028877
0x1800286da  mov     [rdi], rcx
0x1800286dd  mov     [rdi+8], rax
0x1800286e1  mov     [rcx+8], rdi
0x1800286e5  mov     [rax], rdi
0x1800286e8  mov     [r15+8680h], rdi
0x1800286ef  mov     r11d, [rsi+540h]
0x1800286f6  test    r11d, r11d
0x1800286f9  jz      short loc_180028775
0x1800286fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180028702  cmp     rcx, r14
0x180028705  jz      short loc_180028761
0x180028707  test    [rcx+1Ch], r12b
0x18002870b  jz      short loc_180028761
0x18002870d  cmp     byte ptr [rcx+19h], 4
0x180028711  jb      short loc_180028761
0x180028713  mov     r10, [rsi]
0x180028716  mov     r9, [r10]
0x180028719  sub     r15, [rsi+588h]
0x180028720  mov     rax, 77C150CFB348283Bh
0x18002872a  mul     r15
0x18002872d  mov     r8, rdx
0x180028730  shr     r8, 0Eh
0x180028734  mov     edx, 9Dh
0x180028739  mov     dword ptr [rsp+0B8h+var_80], r11d
0x18002873e  mov     dword ptr [rsp+0B8h+var_88], r8d
0x180028743  mov     rax, [r10+40h]
0x180028747  mov     [rsp+0B8h+var_90], rax
0x18002874c  mov     eax, [r9+24h]
0x180028750  mov     dword ptr [rsp+0B8h+var_98], eax
0x180028754  mov     r9d, [r9+10h]
0x180028758  mov     rcx, [rcx+10h]
0x18002875c  call    WPP_SF_DDZdd
0x180028761  xor     edx, edx; PreviousState
0x180028763  mov     rcx, [rsi+490h]; EventHandle
0x18002876a  call    cs:__imp_NtSetEvent
0x180028770  jmp     loc_180028837
0x180028775  lea     rax, [rsi+548h]
0x18002877c  mov     rdi, [rax]
0x18002877f  cmp     rdi, rax
0x180028782  jz      loc_180028837
0x180028788  cmp     [rdi+8], rax
0x18002878c  jnz     loc_180028877
0x180028792  mov     rcx, [rdi]
0x180028795  cmp     [rcx+8], rdi
0x180028799  jnz     loc_180028877
0x18002879f  mov     [rax], rcx
0x1800287a2  mov     [rcx+8], rax
0x1800287a6  mov     r14, cs:WPP_GLOBAL_Control
0x1800287ad  lea     rax, WPP_GLOBAL_Control
0x1800287b4  cmp     r14, rax
0x1800287b7  jz      short loc_18002882D
0x1800287b9  test    [r14+1Ch], r12b
0x1800287bd  jz      short loc_18002882D
0x1800287bf  cmp     byte ptr [r14+19h], 4
0x1800287c4  jb      short loc_18002882D
0x1800287c6  mov     r8, [rsi+588h]
0x1800287cd  mov     r11, [rsi]
0x1800287d0  mov     r9, [r11]
0x1800287d3  mov     rcx, rdi
0x1800287d6  sub     rcx, r8
0x1800287d9  mov     r12, 77C150CFB348283Bh
0x1800287e3  mov     rax, r12
0x1800287e6  mul     rcx
0x1800287e9  mov     r10, rdx
0x1800287ec  shr     r10, 0Eh
0x1800287f0  sub     r15, r8
0x1800287f3  mov     rax, r12
0x1800287f6  mul     r15
0x1800287f9  mov     r8, rdx
0x1800287fc  shr     r8, 0Eh
0x180028800  mov     edx, 9Eh
0x180028805  mov     dword ptr [rsp+0B8h+var_80], r10d
0x18002880a  mov     dword ptr [rsp+0B8h+var_88], r8d
0x18002880f  mov     rax, [r11+40h]
0x180028813  mov     [rsp+0B8h+var_90], rax
0x180028818  mov     eax, [r9+24h]
0x18002881c  mov     dword ptr [rsp+0B8h+var_98], eax
0x180028820  mov     r9d, [r9+10h]
0x180028824  mov     rcx, [r14+10h]
0x180028828  call    WPP_SF_DDZdd
0x18002882d  mov     rcx, [rdi+10h]; pwk
0x180028831  call    cs:__imp_SubmitThreadpoolWork
0x180028837  mov     rcx, rbx; SRWLock
0x18002883a  call    cs:__imp_ReleaseSRWLockExclusive
0x180028840  mov     [rsp+0B8h+var_60], 0
  ... truncated ...
```
