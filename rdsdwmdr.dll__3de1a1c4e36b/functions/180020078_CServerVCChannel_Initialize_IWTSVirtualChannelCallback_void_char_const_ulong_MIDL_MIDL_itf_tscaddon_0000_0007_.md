# CServerVCChannel::Initialize(IWTSVirtualChannelCallback *,void *,char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int,IAPCThread *,ChannelType)

- ea: `0x180020078`
- end: `0x1800205b1`
- name: `?Initialize@CServerVCChannel@@QEAAJPEAUIWTSVirtualChannelCallback@@PEAXPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@HPEAVIAPCThread@@W4ChannelType@@@Z`
- size: `1337`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const CHAR *, unsigned int, int, int, __int64, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001fa10`

## callees

- `0x1800032d4`
- `0x180003314`
- `0x18000f068`
- `0x18000f08c`
- `0x180014044`
- `0x18001d04c`
- `0x18001d098`
- `0x18001d114`
- `0x18001ef44`
- `0x18001fd68`
- `0x180020078`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020537`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020306`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180020306`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180020313`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180020313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002031d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002031d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203bc`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800202fb`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800202fb`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800203b1`
- `WINSTA!WinStationVirtualOpenEx` at `0x1800203b1`
- `WTSAPI32!WTSVirtualChannelClose` at `0x18002051c`
- `WTSAPI32!WTSVirtualChannelClose` at `0x18002051c`

## string_xrefs

- `0x18002018f`: `StringCbCopyA failed`
- `0x18002040e`: `CServerVCChannel::CreateDynamicChannel`
- `0x18002047d`: `CServerVCChannel::CreateStaticChannel`
- `0x1800204ff`: `pAPCThread->PostAPC(static_IssueARead) failed`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const CHAR *a4,
        unsigned int a5,
        int a6,
        int a7,
        __int64 a8,
        int a9)
{
  __int64 v13; // rdx
  _QWORD *v15; // rsi
  WCHAR *v16; // r12
  __int64 v17; // rbx
  _QWORD *v18; // r14
  _BYTE *v19; // rcx
  __int64 v20; // rax
  const CHAR *v21; // r8
  _BYTE *v22; // rax
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v25; // edx
  const char *v26; // rcx
  void *v27; // rax
  unsigned int v28; // eax
  int v29; // edx
  const char *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  int v33; // r15d
  DWORD CurrentProcessId; // eax
  unsigned int v35; // eax
  bool v36; // cf
  __int64 v37; // rax
  signed int v38; // eax
  __int64 v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  int v43; // eax
  DWORD pSessionId[22]; // [rsp+30h] [rbp-58h] BYREF
  ULONG BytesInUnicodeString; // [rsp+90h] [rbp+8h] BYREF

  if ( !(unsigned int)CTSCriticalSection::Initialize((CTSCriticalSection *)(a1 + 56)) )
    return 2147500037LL;
  v15 = (_QWORD *)(a1 + 72);
  v16 = 0;
  if ( a2 != *(_QWORD *)(a1 + 72) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(a1 + 72);
    *v15 = a2;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(a1 + 72);
  }
  v17 = a8;
  v18 = (_QWORD *)(a1 + 400);
  if ( a8 != *(_QWORD *)(a1 + 400) )
  {
    TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(a1 + 400);
    *v18 = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  }
  v19 = (_BYTE *)(a1 + 80);
  if ( a4 )
  {
    v20 = 2147483646;
    v21 = a4;
    v13 = 260;
    do
    {
      if ( !v20 )
        break;
      if ( !*v21 )
        break;
      *v19++ = *v21++;
      --v20;
      --v13;
    }
    while ( v13 );
    v22 = v19 - 1;
    LastError = v13 == 0 ? 0x8007007A : 0;
    if ( v13 )
      v22 = v19;
    *v22 = 0;
    if ( !v13 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v25 = 20;
        v26 = "StringCbCopyA failed";
LABEL_20:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v26,
          LastError,
          *(_QWORD *)pSessionId);
        goto LABEL_74;
      }
      goto LABEL_74;
    }
  }
  else
  {
    *v19 = 0;
  }
  *(_DWORD *)(a1 + 36) |= 2u;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 344) = a3;
LABEL_24:
    *(_DWORD *)(a1 + 360) = 1;
    goto LABEL_25;
  }
  if ( a9 == 1 )
  {
    v31 = -1;
    v32 = -1;
    do
      ++v32;
    while ( a4[v32] );
    v33 = v32 + 1;
    v16 = (WCHAR *)operator new(saturated_mul((unsigned int)(v32 + 1), 2u));
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_39;
      }
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      v29 = 22;
      v30 = "WCHAR[]";
      goto LABEL_38;
    }
    BytesInUnicodeString = 0;
    do
      ++v31;
    while ( a4[v31] );
    RtlMultiByteToUnicodeN(v16, 2 * v33, &BytesInUnicodeString, a4, v31 + 1);
    pSessionId[0] = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, pSessionId) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v35 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v35,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      goto LABEL_74;
    }
    v36 = a7 != 0;
    a7 = -a7;
    v37 = WinStationVirtualOpenEx(0, a5, a4, (2 * a6) | (v36 ? 9 : 1));
    if ( v37 )
    {
      *(_QWORD *)(a1 + 344) = v37;
      goto LABEL_24;
    }
    v38 = GetLastError();
    LastError = v38;
    if ( v38 > 0 )
      LastError = (unsigned __int16)v38 | 0x80070000;
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v25 = 24;
        v26 = "CServerVCChannel::CreateDynamicChannel";
        goto LABEL_20;
      }
LABEL_74:
      v40 = *(void **)(a1 + 352);
      if ( v40 )
      {
        WTSVirtualChannelClose(v40);
        *(_QWORD *)(a1 + 352) = 0;
      }
      else
      {
        v41 = *(void **)(a1 + 344);
        if ( !v41 )
        {
LABEL_79:
          if ( *v18 )
          {
            TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(a1 + 400);
            *v18 = 0;
          }
          if ( *v15 )
          {
            TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(a1 + 72);
            *v15 = 0;
            TCntPtr<ITSAsyncCallback>::SafeAddRef(a1 + 72);
          }
          v42 = *(void **)(a1 + 368);
          if ( v42 )
          {
            operator delete(v42);
            *(_QWORD *)(a1 + 368) = 0;
          }
          v43 = *(_DWORD *)(a1 + 36);
          if ( (v43 & 2) != 0 )
            *(_DWORD *)(a1 + 36) = v43 | 4;
          goto LABEL_87;
        }
        CloseHandle(v41);
      }
      *(_QWORD *)(a1 + 344) = 0;
      goto LABEL_79;
    }
  }
  else
  {
    if ( a9 )
    {
      LastError = -2147024809;
      goto LABEL_74;
    }
    LastError = CServerVCChannel::CreateStaticChannel((CHAR *)a1, (const char *)v13, a5);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v25 = 25;
        v26 = "CServerVCChannel::CreateStaticChannel";
        goto LABEL_20;
      }
      goto LABEL_74;
    }
  }
LABEL_25:
  v27 = operator new(0x648u);
  *(_QWORD *)(a1 + 368) = v27;
  if ( !v27 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
    v29 = 26;
    v30 = "BYTE[]";
LABEL_38:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v29,
      (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v28,
      (__int64)v30);
LABEL_39:
    LastError = -2147024882;
    goto LABEL_74;
  }
  v39 = *(_QWORD *)(a1 + 40);
  *(_DWORD *)(a1 + 376) = 1608;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
  LastError = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(unsigned __int64), __int64))(*(_QWORD *)*v18 + 24LL))(
                *v18,
                CServerVCChannel::static_IssueARead,
                a1);
  if ( LastError )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 16LL))(*(_QWORD *)(a1 + 40));
    if ( LastError < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 27;
      v26 = "pAPCThread->PostAPC(static_IssueARead) failed";
      goto LABEL_20;
    }
    goto LABEL_74;
  }
LABEL_87:
  if ( v16 )
    operator delete(v16);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180020078  push    rbx
0x18002007a  push    rbp
0x18002007b  push    rsi
0x18002007c  push    rdi
0x18002007d  push    r12
0x18002007f  push    r13
0x180020081  push    r14
0x180020083  push    r15
0x180020085  sub     rsp, 48h
0x180020089  mov     rdi, rcx
0x18002008c  mov     rbp, r9
0x18002008f  add     rcx, 38h ; '8'; this
0x180020093  mov     r15, r8
0x180020096  mov     rbx, rdx
0x180020099  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18002009e  xor     r13d, r13d
0x1800200a1  test    eax, eax
0x1800200a3  jnz     short loc_1800200AF
0x1800200a5  mov     eax, 80004005h
0x1800200aa  jmp     loc_1800205A0
0x1800200af  lea     rsi, [rdi+48h]
0x1800200b3  mov     r12, r13
0x1800200b6  cmp     rbx, [rsi]
0x1800200b9  jz      short loc_1800200CE
0x1800200bb  mov     rcx, rsi
0x1800200be  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800200c3  mov     rcx, rsi
0x1800200c6  mov     [rsi], rbx
0x1800200c9  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800200ce  mov     rbx, [rsp+88h+arg_38]
0x1800200d6  lea     r14, [rdi+190h]
0x1800200dd  cmp     rbx, [r14]
0x1800200e0  jz      short loc_180020101
0x1800200e2  mov     rcx, r14
0x1800200e5  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x1800200ea  mov     [r14], rbx
0x1800200ed  test    rbx, rbx
0x1800200f0  jz      short loc_180020101
0x1800200f2  mov     rax, [rbx]
0x1800200f5  mov     rcx, rbx
0x1800200f8  mov     rax, [rax+8]
0x1800200fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020101  lea     rcx, [rdi+50h]
0x180020105  test    rbp, rbp
0x180020108  jz      loc_1800201BE
0x18002010e  mov     eax, 7FFFFFFEh
0x180020113  mov     r8, rbp
0x180020116  mov     edx, 104h
0x18002011b  test    rax, rax
0x18002011e  jz      short loc_18002013A
0x180020120  mov     r9b, [r8]
0x180020123  test    r9b, r9b
0x180020126  jz      short loc_18002013A
0x180020128  mov     [rcx], r9b
0x18002012b  inc     r8
0x18002012e  inc     rcx
0x180020131  dec     rax
0x180020134  sub     rdx, 1
0x180020138  jnz     short loc_18002011B
0x18002013a  mov     rax, rdx
0x18002013d  neg     rax
0x180020140  lea     rax, [rcx-1]
0x180020144  sbb     ebx, ebx
0x180020146  not     ebx
0x180020148  and     ebx, 8007007Ah
0x18002014e  test    rdx, rdx
0x180020151  cmovnz  rax, rcx
0x180020155  mov     [rax], r13b
0x180020158  jnz     short loc_1800201C1
0x18002015a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020161  lea     rax, WPP_GLOBAL_Control
0x180020168  cmp     rcx, rax
0x18002016b  jz      loc_180020510
0x180020171  test    byte ptr [rcx+1Ch], 8
0x180020175  jz      loc_180020510
0x18002017b  cmp     byte ptr [rcx+19h], 2
0x18002017f  jb      loc_180020510
0x180020185  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002018a  mov     edx, 14h
0x18002018f  lea     rcx, aStringcbcopyaF; "StringCbCopyA failed"
0x180020196  mov     [rsp+88h+var_60], ebx
0x18002019a  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1800201a1  mov     qword ptr [rsp+88h+BytesInMultiByteString], rcx
0x1800201a6  mov     r9d, eax
0x1800201a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201b0  mov     rcx, [rcx+10h]
0x1800201b4  call    WPP_SF_DsD
0x1800201b9  jmp     loc_180020510
0x1800201be  mov     [rcx], r13b
0x1800201c1  or      dword ptr [rdi+24h], 2
0x1800201c5  test    r15, r15
0x1800201c8  jz      short loc_180020235
0x1800201ca  mov     [rdi+158h], r15
0x1800201d1  mov     dword ptr [rdi+168h], 1
0x1800201db  mov     ebx, 648h
0x1800201e0  mov     ecx, ebx; Size
0x1800201e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800201e7  mov     [rdi+170h], rax
0x1800201ee  test    rax, rax
0x1800201f1  jnz     loc_180020489
0x1800201f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201fe  lea     rax, WPP_GLOBAL_Control
0x180020205  cmp     rcx, rax
0x180020208  jz      loc_1800202C7
0x18002020e  test    byte ptr [rcx+1Ch], 8
0x180020212  jz      loc_1800202C7
0x180020218  cmp     byte ptr [rcx+19h], 2
0x18002021c  jb      loc_1800202C7
0x180020222  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020227  mov     edx, 1Ah
0x18002022c  lea     rcx, aByte; "BYTE[]"
0x180020233  jmp     short loc_1800202A8
0x180020235  mov     eax, [rsp+88h+arg_40]
0x18002023c  cmp     eax, 1
0x18002023f  jnz     loc_180020426
0x180020245  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020249  mov     rax, rbx
0x18002024c  inc     rax
0x18002024f  cmp     [rax+rbp], r13b
0x180020253  jnz     short loc_18002024C
0x180020255  lea     r15d, [rax+1]
0x180020259  mov     eax, 2
0x18002025e  mov     ecx, r15d
0x180020261  mul     rcx
0x180020264  cmovb   rax, rbx
0x180020268  mov     rcx, rax; Size
0x18002026b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020270  mov     r12, rax
0x180020273  test    rax, rax
0x180020276  jnz     short loc_1800202D1
0x180020278  mov     rcx, cs:WPP_GLOBAL_Control
0x18002027f  lea     rax, WPP_GLOBAL_Control
0x180020286  cmp     rcx, rax
0x180020289  jz      short loc_1800202C7
0x18002028b  test    byte ptr [rcx+1Ch], 8
0x18002028f  jz      short loc_1800202C7
0x180020291  cmp     byte ptr [rcx+19h], 2
0x180020295  jb      short loc_1800202C7
0x180020297  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002029c  lea     edx, [r12+16h]
0x1800202a1  lea     rcx, aWchar; "WCHAR[]"
0x1800202a8  mov     qword ptr [rsp+88h+BytesInMultiByteString], rcx
0x1800202ad  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1800202b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202bb  mov     r9d, eax
0x1800202be  mov     rcx, [rcx+10h]
0x1800202c2  call    WPP_SF_Ds
0x1800202c7  mov     ebx, 8007000Eh
0x1800202cc  jmp     loc_180020510
0x1800202d1  mov     [rsp+88h+BytesInUnicodeString], r13d
0x1800202d9  inc     rbx
0x1800202dc  cmp     [rbx+rbp], r13b
0x1800202e0  jnz     short loc_1800202D9
0x1800202e2  lea     eax, [rbx+1]
0x1800202e5  mov     r9, rbp; MultiByteString
0x1800202e8  lea     edx, [r15+r15]; MaxBytesInUnicodeString
0x1800202ec  mov     [rsp+88h+BytesInMultiByteString], eax; BytesInMultiByteString
0x1800202f0  lea     r8, [rsp+88h+BytesInUnicodeString]; BytesInUnicodeString
0x1800202f8  mov     rcx, r12; UnicodeString
0x1800202fb  call    cs:__imp_RtlMultiByteToUnicodeN
0x180020301  mov     [rsp+88h+pSessionId], r13d
0x180020306  call    cs:__imp_GetCurrentProcessId
0x18002030c  mov     ecx, eax; dwProcessId
0x18002030e  lea     rdx, [rsp+88h+pSessionId]; pSessionId
0x180020313  call    cs:__imp_ProcessIdToSessionId
0x180020319  test    eax, eax
0x18002031b  jnz     short loc_180020388
0x18002031d  call    cs:__imp_GetLastError
0x180020323  mov     ebx, eax
0x180020325  mov     rcx, cs:WPP_GLOBAL_Control
0x18002032c  lea     rax, WPP_GLOBAL_Control
0x180020333  cmp     rcx, rax
0x180020336  jz      short loc_18002036C
0x180020338  test    byte ptr [rcx+1Ch], 8
0x18002033c  jz      short loc_18002036C
0x18002033e  cmp     byte ptr [rcx+19h], 2
0x180020342  jb      short loc_18002036C
0x180020344  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020349  mov     rcx, cs:WPP_GLOBAL_Control
0x180020350  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x180020357  mov     edx, 17h
0x18002035c  mov     [rsp+88h+BytesInMultiByteString], ebx
0x180020360  mov     r9d, eax
0x180020363  mov     rcx, [rcx+10h]
0x180020367  call    WPP_SF_Dd
0x18002036c  test    ebx, ebx
0x18002036e  jle     short loc_180020379
0x180020370  movzx   ebx, bx
0x180020373  or      ebx, 80070000h
0x180020379  test    ebx, ebx
0x18002037b  mov     eax, 80004005h
0x180020380  cmovns  ebx, eax
0x180020383  jmp     loc_180020510
0x180020388  mov     eax, [rsp+88h+arg_28]
0x18002038f  mov     r8, rbp
0x180020392  neg     [rsp+88h+arg_30]
0x180020399  mov     edx, [rsp+88h+arg_20]
0x1800203a0  sbb     r9d, r9d
0x1800203a3  add     eax, eax
0x1800203a5  and     r9d, 8
0x1800203a9  xor     ecx, ecx
0x1800203ab  inc     r9d
0x1800203ae  or      r9d, eax
0x1800203b1  call    cs:__imp_WinStationVirtualOpenEx
0x1800203b7  test    rax, rax
0x1800203ba  jnz     short loc_18002041A
0x1800203bc  call    cs:__imp_GetLastError
0x1800203c2  mov     ebx, eax
0x1800203c4  test    eax, eax
0x1800203c6  jle     short loc_1800203D1
0x1800203c8  movzx   ebx, ax
0x1800203cb  or      ebx, 80070000h
0x1800203d1  test    ebx, ebx
0x1800203d3  jns     loc_1800201DB
0x1800203d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800203e0  lea     rax, WPP_GLOBAL_Control
0x1800203e7  cmp     rcx, rax
0x1800203ea  jz      loc_180020510
0x1800203f0  test    byte ptr [rcx+1Ch], 8
0x1800203f4  jz      loc_180020510
0x1800203fa  cmp     byte ptr [rcx+19h], 2
0x1800203fe  jb      loc_180020510
0x180020404  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020409  mov     edx, 18h
0x18002040e  lea     rcx, aCservervcchann_0; "CServerVCChannel::CreateDynamicChannel"
0x180020415  jmp     loc_180020196
0x18002041a  mov     [rdi+158h], rax
0x180020421  jmp     loc_1800201D1
0x180020426  test    eax, eax
0x180020428  jnz     loc_18002050B
0x18002042e  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x180020436  mov     rcx, rdi; this
0x180020439  call    ?CreateStaticChannel@CServerVCChannel@@QEAAJPEBDK@Z; CServerVCChannel::CreateStaticChannel(char const *,ulong)
0x18002043e  mov     ebx, eax
0x180020440  test    eax, eax
0x180020442  jns     loc_1800201DB
0x180020448  mov     rcx, cs:WPP_GLOBAL_Control
0x18002044f  lea     rax, WPP_GLOBAL_Control
0x180020456  cmp     rcx, rax
0x180020459  jz      loc_180020510
0x18002045f  test    byte ptr [rcx+1Ch], 8
0x180020463  jz      loc_180020510
0x180020469  cmp     byte ptr [rcx+19h], 2
0x18002046d  jb      loc_180020510
0x180020473  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180020478  mov     edx, 19h
0x18002047d  lea     rcx, aCservervcchann; "CServerVCChannel::CreateStaticChannel"
0x180020484  jmp     loc_180020196
0x180020489  mov     rcx, [rdi+28h]
0x18002048d  mov     [rdi+178h], ebx
0x180020493  mov     rax, [rcx]
0x180020496  mov     rax, [rax+8]
0x18002049a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002049f  mov     rcx, [r14]
0x1800204a2  lea     rdx, ?static_IssueARead@CServerVCChannel@@CAX_K@Z; CServerVCChannel::static_IssueARead(unsigned __int64)
0x1800204a9  mov     r8, rdi
0x1800204ac  mov     rax, [rcx]
0x1800204af  mov     rax, [rax+18h]
0x1800204b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204b8  mov     ebx, eax
0x1800204ba  test    eax, eax
0x1800204bc  jz      loc_180020591
0x1800204c2  mov     rcx, [rdi+28h]
0x1800204c6  mov     rax, [rcx]
0x1800204c9  mov     rax, [rax+10h]
0x1800204cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204d2  test    ebx, ebx
0x1800204d4  jns     short loc_180020510
0x1800204d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204dd  lea     rax, WPP_GLOBAL_Control
0x1800204e4  cmp     rcx, rax
0x1800204e7  jz      short loc_180020510
0x1800204e9  test    byte ptr [rcx+1Ch], 8
0x1800204ed  jz      short loc_180020510
0x1800204ef  cmp     byte ptr [rcx+19h], 2
0x1800204f3  jb      short loc_180020510
0x1800204f5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800204fa  mov     edx, 1Bh
0x1800204ff  lea     rcx, aPapcthreadPost; "pAPCThread->PostAPC(static_IssueARead) "...
0x180020506  jmp     loc_180020196
0x18002050b  mov     ebx, 80070057h
0x180020510  mov     rcx, [rdi+160h]; hChannelHandle
0x180020517  test    rcx, rcx
0x18002051a  jz      short loc_18002052B
0x18002051c  call    cs:__imp_WTSVirtualChannelClose
0x180020522  mov     [rdi+160h], r13
0x180020529  jmp     short loc_18002053D
0x18002052b  mov     rcx, [rdi+158h]; hObject
0x180020532  test    rcx, rcx
0x180020535  jz      short loc_180020544
0x180020537  call    cs:__imp_CloseHandle
0x18002053d  mov     [rdi+158h], r13
0x180020544  cmp     [r14], r13
0x180020547  jz      short loc_180020554
0x180020549  mov     rcx, r14
0x18002054c  call    ?SafeRelease@?$TCntPtr@UIRdsDWMDirectSharedMemory@@@@AEAAXXZ; TCntPtr<IRdsDWMDirectSharedMemory>::SafeRelease(void)
0x180020551  mov     [r14], r13
0x180020554  cmp     [rsi], r13
0x180020557  jz      short loc_18002056C
0x180020559  mov     rcx, rsi
  ... truncated ...
```
