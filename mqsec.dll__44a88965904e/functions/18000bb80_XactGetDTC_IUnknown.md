# XactGetDTC(IUnknown * *)

- ea: `0x18000bb80`
- end: `0x18000bfce`
- name: `?XactGetDTC@@YAJPEAPEAUIUnknown@@@Z`
- size: `1102`
- prototype: `__int64 __fastcall(struct IUnknown **)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bfe0`

## callees

- `0x1800049ac`
- `0x18000b6c0`
- `0x18000b76c`
- `0x18000b95c`
- `0x18000b97c`
- `0x18000ba9c`
- `0x18000bb80`
- `0x18000c39c`
- `0x18000c3c4`
- `0x18000d650`
- `0x18000d940`
- `0x18002f096`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000bcd2`
- `KERNEL32!GetProcAddress` at `0x18000bcd2`
- `KERNEL32!CompareStringW` at `0x18000bdbb`
- `KERNEL32!CompareStringW` at `0x18000bdbb`
- `KERNEL32!LoadLibraryW` at `0x18000bc4d`
- `KERNEL32!LoadLibraryW` at `0x18000bc4d`
- `KERNEL32!LeaveCriticalSection` at `0x18000bc00`
- `KERNEL32!LeaveCriticalSection` at `0x18000bf37`
- `KERNEL32!LeaveCriticalSection` at `0x18000bc00`
- `KERNEL32!LeaveCriticalSection` at `0x18000bf37`
- `KERNEL32!GetLastError` at `0x18000bc77`
- `KERNEL32!GetLastError` at `0x18000bc77`

## string_xrefs

- `0x18000bc46`: `xolehlp.dll`
- `0x18000bdff`: `MachineCache\ClusterResourceGuid`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall XactGetDTC(struct IUnknown **a1)
{
  struct IUnknown *v2; // rdi
  HMODULE v4; // rcx
  _RTL_CRITICAL_SECTION *v5; // rbx
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  FARPROC ProcAddress; // rbx
  int FalconServiceName; // eax
  __int64 v10; // rcx
  _BYTE *v11; // rax
  int v12; // eax
  _RTL_CRITICAL_SECTION *v13; // [rsp+40h] [rbp-C0h] BYREF
  struct IUnknown *v14; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v15; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v16[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v17; // [rsp+60h] [rbp-A0h]
  GUID Buf1; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v19[10]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR String1[304]; // [rsp+A0h] [rbp-60h] BYREF

  *a1 = 0;
  v17 = 0;
  v13 = &stru_180042510;
  CCriticalSection::Lock((CCriticalSection *)&stru_180042510);
  v2 = g_pDTCIUnknown;
  if ( g_pDTCIUnknown )
    ((void (__fastcall *)(struct IUnknown *))g_pDTCIUnknown->lpVtbl->AddRef)(g_pDTCIUnknown);
  SafeRelease<IUnknown>(0);
  v17 = v2;
  LeaveCriticalSection(&stru_180042510);
  if ( v2 && (unsigned int)SafeVerifyCurDTC(v2) )
  {
    *a1 = v2;
    SafeRelease<IUnknown>(0);
    return 0;
  }
  SafeXactFreeDTC();
  v4 = g_DtcHlib;
  v5 = 0;
  v13 = 0;
  if ( !g_DtcHlib )
  {
    LibraryW = LoadLibraryW(L"xolehlp.dll");
    v4 = LibraryW;
    if ( !LibraryW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 15, WPP_f8138a78677f34b3e5f704385132758d_Traceguids, LastError);
      }
      goto LABEL_42;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_DtcHlib, (signed __int64)LibraryW, 0) )
      v5 = (_RTL_CRITICAL_SECTION *)LibraryW;
    v13 = v5;
  }
  ProcAddress = GetProcAddress(v4, "DtcGetTransactionManagerExW");
  if ( ProcAddress )
  {
    v14 = 0;
    FalconServiceName = GetFalconServiceName(String1, 0x12Cu);
    if ( FalconServiceName >= 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, String1, -1, L"MSMQ", -1) == 2 )
      {
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, GUID *, __int64, _QWORD, struct IUnknown **))ProcAddress)(
                0,
                0,
                &IID_IUnknown,
                0x80000000LL,
                0,
                &v14);
      }
      else
      {
        Buf1 = GUID_NULL;
        v16[0] = 3;
        v15 = 16;
        if ( GetFalconKeyValue(L"MachineCache\\ClusterResourceGuid", v16, &Buf1, &v15, 0) < 0
          || !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 18, WPP_f8138a78677f34b3e5f704385132758d_Traceguids);
          goto LABEL_42;
        }
        memset(v19, 0, 28);
        v10 = 28;
        v11 = v19;
        do
        {
          *v11++ = 0;
          --v10;
        }
        while ( v10 );
        v19[0] = 2;
        v19[2] = 1;
        *(GUID *)&v19[3] = Buf1;
        v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, GUID *, __int64, _DWORD *, struct IUnknown **))ProcAddress)(
                0,
                0,
                &IID_IUnknown,
                0x80000000LL,
                v19,
                &v14);
      }
      if ( v12 >= 0 && v14 )
      {
        *(_QWORD *)v16 = &stru_180042510;
        CCriticalSection::Lock((CCriticalSection *)&stru_180042510);
        g_pDTCIUnknown = v14;
        ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->AddRef)(v14);
        *a1 = g_pDTCIUnknown;
        LeaveCriticalSection(&stru_180042510);
        CAutoFreeLibrary::~CAutoFreeLibrary((CAutoFreeLibrary *)&v13);
        SafeRelease<IUnknown>(v2);
        return 1;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          19,
          WPP_f8138a78677f34b3e5f704385132758d_Traceguids,
          (unsigned int)v12);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        17,
        WPP_f8138a78677f34b3e5f704385132758d_Traceguids,
        (unsigned int)FalconServiceName);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 42), 16, WPP_f8138a78677f34b3e5f704385132758d_Traceguids, 0);
  }
LABEL_42:
  CAutoFreeLibrary::~CAutoFreeLibrary((CAutoFreeLibrary *)&v13);
  SafeRelease<IUnknown>(v2);
  return 3222143052LL;
}

```

## disassembly

```asm
0x18000bb80  mov     [rsp-8+arg_8], rbx
0x18000bb85  mov     [rsp-8+arg_10], rsi
0x18000bb8a  push    rbp
0x18000bb8b  push    rdi
0x18000bb8c  push    r15
0x18000bb8e  lea     rbp, [rsp-210h]
0x18000bb96  sub     rsp, 310h
0x18000bb9d  mov     rax, cs:__security_cookie
0x18000bba4  xor     rax, rsp
0x18000bba7  mov     [rbp+220h+var_20], rax
0x18000bbae  mov     rsi, rcx
0x18000bbb1  mov     qword ptr [rcx], 0
0x18000bbb8  mov     [rsp+320h+var_2C0], 0
0x18000bbc1  lea     r15, stru_180042510
0x18000bbc8  mov     [rsp+320h+var_2E0], r15
0x18000bbcd  mov     rcx, r15; this
0x18000bbd0  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000bbd5  nop
0x18000bbd6  mov     rdi, cs:?g_pDTCIUnknown@@3PEAUIUnknown@@EA; IUnknown * g_pDTCIUnknown
0x18000bbdd  test    rdi, rdi
0x18000bbe0  jz      short loc_18000BBF1
0x18000bbe2  mov     rax, [rdi]
0x18000bbe5  mov     rcx, rdi
0x18000bbe8  mov     rax, [rax+8]
0x18000bbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbf1  xor     ecx, ecx
0x18000bbf3  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bbf8  mov     [rsp+320h+var_2C0], rdi
0x18000bbfd  mov     rcx, r15; lpCriticalSection
0x18000bc00  call    cs:__imp_LeaveCriticalSection
0x18000bc06  nop
0x18000bc07  test    rdi, rdi
0x18000bc0a  jz      short loc_18000BC2A
0x18000bc0c  mov     rcx, rdi
0x18000bc0f  call    SafeVerifyCurDTC
0x18000bc14  test    eax, eax
0x18000bc16  jz      short loc_18000BC2A
0x18000bc18  mov     [rsi], rdi
0x18000bc1b  xor     ecx, ecx
0x18000bc1d  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bc22  nop
0x18000bc23  xor     eax, eax
0x18000bc25  jmp     loc_18000BFA7
0x18000bc2a  call    ?SafeXactFreeDTC@@YAXXZ; SafeXactFreeDTC(void)
0x18000bc2f  mov     rcx, cs:?g_DtcHlib@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_DtcHlib
0x18000bc36  xor     ebx, ebx
0x18000bc38  mov     [rsp+320h+var_2E0], rbx
0x18000bc3d  test    rcx, rcx
0x18000bc40  jnz     loc_18000BCCB
0x18000bc46  lea     rcx, aXolehlpDll; "xolehlp.dll"
0x18000bc4d  call    cs:__imp_LoadLibraryW
0x18000bc53  mov     rcx, rax; hModule
0x18000bc56  test    rax, rax
0x18000bc59  jnz     short loc_18000BCB7
0x18000bc5b  lea     rax, WPP_GLOBAL_Control
0x18000bc62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc69  cmp     rcx, rax
0x18000bc6c  jz      short loc_18000BC9E
0x18000bc6e  test    byte ptr [rcx+15Ch], 1
0x18000bc75  jz      short loc_18000BC9E
0x18000bc77  call    cs:__imp_GetLastError
0x18000bc7d  lea     edx, [rbx+0Fh]
0x18000bc80  mov     r9d, eax
0x18000bc83  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000bc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc91  mov     rcx, [rcx+150h]
0x18000bc98  call    WPP_SF_d
0x18000bc9d  nop
0x18000bc9e  lea     rcx, [rsp+320h+var_2E0]; this
0x18000bca3  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000bca8  nop
0x18000bca9  mov     rcx, rdi
0x18000bcac  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bcb1  nop
0x18000bcb2  jmp     loc_18000BFA2
0x18000bcb7  xor     eax, eax
0x18000bcb9  lock cmpxchg cs:?g_DtcHlib@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_DtcHlib
0x18000bcc2  cmovnz  rbx, rcx
0x18000bcc6  mov     [rsp+320h+var_2E0], rbx
0x18000bccb  lea     rdx, aDtcgettransact; "DtcGetTransactionManagerExW"
0x18000bcd2  call    cs:__imp_GetProcAddress
0x18000bcd8  mov     rbx, rax
0x18000bcdb  test    rax, rax
0x18000bcde  jnz     short loc_18000BD2F
0x18000bce0  lea     rax, WPP_GLOBAL_Control
0x18000bce7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcee  cmp     rcx, rax
0x18000bcf1  jz      short loc_18000BD16
0x18000bcf3  test    byte ptr [rcx+15Ch], 1
0x18000bcfa  jz      short loc_18000BD16
0x18000bcfc  lea     edx, [rbx+10h]
0x18000bcff  xor     r9d, r9d
0x18000bd02  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000bd09  mov     rcx, [rcx+150h]
0x18000bd10  call    WPP_SF_q
0x18000bd15  nop
0x18000bd16  lea     rcx, [rsp+320h+var_2E0]; this
0x18000bd1b  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000bd20  nop
0x18000bd21  mov     rcx, rdi
0x18000bd24  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bd29  nop
0x18000bd2a  jmp     loc_18000BFA2
0x18000bd2f  mov     [rsp+320h+var_2D8], 0
0x18000bd38  mov     edx, 12Ch; unsigned int
0x18000bd3d  lea     rcx, [rbp+220h+String1]; wchar_t *
0x18000bd41  call    ?GetFalconServiceName@@YAJPEA_WK@Z; GetFalconServiceName(wchar_t *,ulong)
0x18000bd46  mov     r9d, eax
0x18000bd49  test    eax, eax
0x18000bd4b  jns     short loc_18000BD9B
0x18000bd4d  lea     rax, WPP_GLOBAL_Control
0x18000bd54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd5b  cmp     rcx, rax
0x18000bd5e  jz      short loc_18000BD82
0x18000bd60  test    byte ptr [rcx+15Ch], 1
0x18000bd67  jz      short loc_18000BD82
0x18000bd69  mov     edx, 11h
0x18000bd6e  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000bd75  mov     rcx, [rcx+150h]
0x18000bd7c  call    WPP_SF_d
0x18000bd81  nop
0x18000bd82  lea     rcx, [rsp+320h+var_2E0]; this
0x18000bd87  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000bd8c  nop
0x18000bd8d  mov     rcx, rdi
0x18000bd90  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bd95  nop
0x18000bd96  jmp     loc_18000BFA2
0x18000bd9b  or      r9d, 0FFFFFFFFh; cchCount1
0x18000bd9f  mov     [rsp+320h+cchCount2], r9d; cchCount2
0x18000bda4  lea     rax, SubsystemName; "MSMQ"
0x18000bdab  mov     [rsp+320h+lpString2], rax; lpString2
0x18000bdb0  lea     r8, [rbp+220h+String1]; lpString1
0x18000bdb4  lea     edx, [r9+2]; dwCmpFlags
0x18000bdb8  lea     ecx, [rdx+7Eh]; Locale
0x18000bdbb  call    cs:__imp_CompareStringW
0x18000bdc1  cmp     eax, 2
0x18000bdc4  jz      loc_18000BEC9
0x18000bdca  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000bdd1  movdqu  [rsp+320h+Buf1], xmm0
0x18000bdd7  mov     [rsp+320h+var_2C8], 3
0x18000bddf  mov     [rsp+320h+var_2D0], 10h
0x18000bde7  mov     [rsp+320h+lpString2], 0; wchar_t *
0x18000bdf0  lea     r9, [rsp+320h+var_2D0]; unsigned int *
0x18000bdf5  lea     r8, [rsp+320h+Buf1]; void *
0x18000bdfa  lea     rdx, [rsp+320h+var_2C8]; unsigned int *
0x18000bdff  lea     rcx, aMachinecacheCl; "MachineCache\\ClusterResourceGuid"
0x18000be06  call    ?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x18000be0b  test    eax, eax
0x18000be0d  js      short loc_18000BE7B
0x18000be0f  mov     r8d, 10h; Size
0x18000be15  lea     rdx, GUID_NULL; Buf2
0x18000be1c  lea     rcx, [rsp+320h+Buf1]; Buf1
0x18000be21  call    memcmp_0
0x18000be26  test    eax, eax
0x18000be28  jz      short loc_18000BE7B
0x18000be2a  xorps   xmm0, xmm0
0x18000be2d  movups  xmmword ptr [rsp+320h+var_2A8], xmm0
0x18000be32  movups  xmmword ptr [rbp+220h+var_2A8+0Ch], xmm0
0x18000be36  mov     ecx, 1Ch
0x18000be3b  lea     rax, [rsp+320h+var_2A8]
0x18000be40  mov     byte ptr [rax], 0
0x18000be43  inc     rax
0x18000be46  sub     rcx, 1
0x18000be4a  jnz     short loc_18000BE40
0x18000be4c  mov     [rsp+320h+var_2A8], 2
0x18000be54  mov     [rbp+220h+var_2A8+8], 1
0x18000be5b  movups  xmm0, [rsp+320h+Buf1]
0x18000be60  movdqu  xmmword ptr [rbp+220h+var_2A8+0Ch], xmm0
0x18000be65  lea     rax, [rsp+320h+var_2D8]
0x18000be6a  mov     qword ptr [rsp+320h+cchCount2], rax
0x18000be6f  lea     rax, [rsp+320h+var_2A8]
0x18000be74  mov     [rsp+320h+lpString2], rax
0x18000be79  jmp     short loc_18000BEDC
0x18000be7b  lea     rax, WPP_GLOBAL_Control
0x18000be82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be89  cmp     rcx, rax
0x18000be8c  jz      short loc_18000BEB0
0x18000be8e  test    byte ptr [rcx+15Ch], 1
0x18000be95  jz      short loc_18000BEB0
0x18000be97  mov     edx, 12h
0x18000be9c  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000bea3  mov     rcx, [rcx+150h]
0x18000beaa  call    WPP_SF_
0x18000beaf  nop
0x18000beb0  lea     rcx, [rsp+320h+var_2E0]; this
0x18000beb5  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000beba  nop
0x18000bebb  mov     rcx, rdi
0x18000bebe  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bec3  nop
0x18000bec4  jmp     loc_18000BFA2
0x18000bec9  lea     rax, [rsp+320h+var_2D8]
0x18000bece  mov     qword ptr [rsp+320h+cchCount2], rax
0x18000bed3  mov     [rsp+320h+lpString2], 0
0x18000bedc  mov     r9d, 80000000h
0x18000bee2  lea     r8, IID_IUnknown
0x18000bee9  xor     edx, edx
0x18000beeb  xor     ecx, ecx
0x18000beed  mov     rax, rbx
0x18000bef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bef5  mov     r9d, eax
0x18000bef8  test    eax, eax
0x18000befa  js      short loc_18000BF59
0x18000befc  cmp     [rsp+320h+var_2D8], 0
0x18000bf02  jz      short loc_18000BF59
0x18000bf04  mov     qword ptr [rsp+320h+var_2C8], r15
0x18000bf09  mov     rcx, r15; this
0x18000bf0c  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000bf11  nop
0x18000bf12  mov     rcx, [rsp+320h+var_2D8]
0x18000bf17  mov     cs:?g_pDTCIUnknown@@3PEAUIUnknown@@EA, rcx; IUnknown * g_pDTCIUnknown
0x18000bf1e  mov     rax, [rcx]
0x18000bf21  mov     rax, [rax+8]
0x18000bf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2a  mov     rax, cs:?g_pDTCIUnknown@@3PEAUIUnknown@@EA; IUnknown * g_pDTCIUnknown
0x18000bf31  mov     [rsi], rax
0x18000bf34  mov     rcx, r15; lpCriticalSection
0x18000bf37  call    cs:__imp_LeaveCriticalSection
0x18000bf3d  nop
0x18000bf3e  lea     rcx, [rsp+320h+var_2E0]; this
0x18000bf43  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000bf48  nop
0x18000bf49  mov     rcx, rdi
0x18000bf4c  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bf51  nop
0x18000bf52  mov     eax, 1
0x18000bf57  jmp     short loc_18000BFA7
0x18000bf59  lea     rax, WPP_GLOBAL_Control
0x18000bf60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf67  cmp     rcx, rax
0x18000bf6a  jz      short loc_18000BF8E
0x18000bf6c  test    byte ptr [rcx+15Ch], 1
0x18000bf73  jz      short loc_18000BF8E
0x18000bf75  mov     edx, 13h
0x18000bf7a  lea     r8, WPP_f8138a78677f34b3e5f704385132758d_Traceguids
0x18000bf81  mov     rcx, [rcx+150h]
0x18000bf88  call    WPP_SF_d
0x18000bf8d  nop
0x18000bf8e  lea     rcx, [rsp+320h+var_2E0]; this
0x18000bf93  call    ??1CAutoFreeLibrary@@QEAA@XZ; CAutoFreeLibrary::~CAutoFreeLibrary(void)
0x18000bf98  nop
0x18000bf99  mov     rcx, rdi
0x18000bf9c  call    ??$SafeRelease@UIUnknown@@@@YAXPEAUIUnknown@@@Z; SafeRelease<IUnknown>(IUnknown *)
0x18000bfa1  nop
0x18000bfa2  mov     eax, 0C00E004Ch
0x18000bfa7  mov     rcx, [rbp+220h+var_20]
0x18000bfae  xor     rcx, rsp; StackCookie
0x18000bfb1  call    __security_check_cookie
0x18000bfb6  lea     r11, [rsp+320h+var_10]
0x18000bfbe  mov     rbx, [r11+28h]
0x18000bfc2  mov     rsi, [r11+30h]
0x18000bfc6  mov     rsp, r11
0x18000bfc9  pop     r15
0x18000bfcb  pop     rdi
0x18000bfcc  pop     rbp
0x18000bfcd  retn
```
