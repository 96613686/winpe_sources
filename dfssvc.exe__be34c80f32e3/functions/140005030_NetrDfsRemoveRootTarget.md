# NetrDfsRemoveRootTarget

- ea: `0x140005030`
- end: `0x140005582`
- name: `NetrDfsRemoveRootTarget`
- size: `1362`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140002ccc`
- `0x140002d84`
- `0x140002fb4`
- `0x140005030`
- `0x140005590`
- `0x140005a94`
- `0x140005c10`
- `0x140011c54`
- `0x140012020`
- `0x14004a490`
- `0x14004ac38`
- `0x140058078`
- `0x140058a38`
- `0x14005ce70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1400050f9`
- `ntdll!RtlInitUnicodeStringEx` at `0x140005126`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000513c`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000517c`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000519c`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400051b2`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400050f9`
- `ntdll!RtlInitUnicodeStringEx` at `0x140005126`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000513c`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000517c`
- `ntdll!RtlInitUnicodeStringEx` at `0x14000519c`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400051b2`
- `ntdll!RtlNtStatusToDosError` at `0x14000510b`
- `ntdll!RtlNtStatusToDosError` at `0x14000510b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000539b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000540e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14005d45c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000539b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000540e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14005d45c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x140005466`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x140005466`
- `logoncli!DsGetDcNameW` at `0x140005338`
- `logoncli!DsGetDcNameW` at `0x140005338`
- `netutils!NetApiBufferFree` at `0x140005500`
- `netutils!NetApiBufferFree` at `0x140005500`

## pseudocode

```c
__int64 __fastcall NetrDfsRemoveRootTarget(PCWSTR SourceString, __int64 a2, int a3)
{
  unsigned __int16 *v5; // r13
  unsigned __int16 *v6; // r15
  unsigned __int16 *v7; // r12
  int inited; // eax
  ULONG ErrorFromHr; // eax
  DWORD FirstComponent; // ebx
  const WCHAR *v11; // rdx
  unsigned __int16 *v12; // rax
  int v13; // eax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rax
  struct CLocalMachine *Instance; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  LPWSTR i; // rbx
  char v20; // di
  unsigned int v21; // eax
  DWORD v22; // ecx
  unsigned __int64 v23; // rax
  unsigned int Flags; // [rsp+20h] [rbp-F8h]
  unsigned int v26; // [rsp+40h] [rbp-D8h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-D0h] BYREF
  LARGE_INTEGER v28; // [rsp+50h] [rbp-C8h] BYREF
  int v29; // [rsp+58h] [rbp-C0h]
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+60h] [rbp-B8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+68h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v33; // [rsp+80h] [rbp-98h] BYREF
  struct _UNICODE_STRING v34; // [rsp+90h] [rbp-88h] BYREF
  struct _UNICODE_STRING v35; // [rsp+A0h] [rbp-78h] BYREF
  UNICODE_STRING String2; // [rsp+B0h] [rbp-68h] BYREF
  unsigned int v37[4]; // [rsp+C0h] [rbp-58h] BYREF

  v29 = a3;
  DestinationString = 0;
  String2 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  PerformanceCount.QuadPart = 0;
  v28.QuadPart = 0;
  Frequency.QuadPart = 1;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  DomainControllerInfo = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_SS(
      *((_QWORD *)pWppControl + 2),
      32,
      (unsigned int)WPP_f38d65142fb9367417e390a0ea4ff145_Traceguids,
      (_DWORD)SourceString,
      a2);
  }
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
    goto LABEL_7;
  RtlInitUnicodeStringEx(&String2, 0);
  RtlInitUnicodeStringEx(&v35, 0);
  FirstComponent = DfsGetFirstComponent(&DestinationString, &String2, &v35);
  if ( FirstComponent )
    goto LABEL_51;
  v11 = (const WCHAR *)a2;
  if ( !a2 )
    v11 = SourceString;
  inited = RtlInitUnicodeStringEx(&DestinationString, v11);
  if ( inited < 0 )
  {
LABEL_7:
    ErrorFromHr = RtlNtStatusToDosError(inited);
LABEL_50:
    FirstComponent = ErrorFromHr;
    goto LABEL_51;
  }
  RtlInitUnicodeStringEx(&v33, 0);
  RtlInitUnicodeStringEx(&v34, 0);
  FirstComponent = DfsGetFirstComponent(&DestinationString, &v33, &v34);
  if ( FirstComponent )
    goto LABEL_51;
  v12 = (unsigned __int16 *)operator new(saturated_mul(((unsigned __int64)v33.Length >> 1) + 1, 2u));
  v6 = v12;
  if ( !v12 )
    goto LABEL_14;
  v13 = StringCbCopyNW(v12, v33.Length + 2LL, v33.Buffer, v33.Length);
  if ( v13 < 0 )
  {
LABEL_16:
    ErrorFromHr = DfsGetErrorFromHr(v13);
    goto LABEL_50;
  }
  v14 = (unsigned __int16 *)operator new(saturated_mul(((unsigned __int64)v34.Length >> 1) + 1, 2u));
  v7 = v14;
  if ( !v14 )
    goto LABEL_14;
  v13 = StringCbCopyNW(v14, v34.Length + 2LL, v34.Buffer, v34.Length);
  if ( v13 < 0 )
    goto LABEL_16;
  if ( !(unsigned int)DfsIsAdDomainName(&String2) )
  {
    if ( !a2 )
    {
      ErrorFromHr = NetrDfsRemoveStdRoot(v6, v7);
      goto LABEL_50;
    }
LABEL_21:
    FirstComponent = 87;
    goto LABEL_51;
  }
  if ( !a2 )
    goto LABEL_21;
  v15 = (unsigned __int16 *)operator new(saturated_mul(((unsigned __int64)v35.Length >> 1) + 1, 2u));
  v5 = v15;
  if ( !v15 )
  {
LABEL_14:
    FirstComponent = 8;
    goto LABEL_51;
  }
  v13 = StringCbCopyNW(v15, v35.Length + 2LL, v35.Buffer, v35.Length);
  if ( v13 < 0 )
    goto LABEL_16;
  Instance = CLocalMachine::_GetInstance(0);
  FirstComponent = DsGetDcNameW(0, *((LPCWSTR *)Instance + 6), 0, 0, 0x81u, &DomainControllerInfo);
  if ( !FirstComponent )
  {
    for ( i = DomainControllerInfo->DomainControllerName; *i == 92; ++i )
      ;
    if ( (Microsoft_Windows_DFSN_ServerEnableBits & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v17, (__int64)NetrDfsRemoveFtRootArrived, v18, 1, (__int64)v37);
    if ( !QueryPerformanceCounter(&PerformanceCount) )
      PerformanceCount.QuadPart = 0;
    v20 = v29;
    if ( v29 < 0 )
      v21 = DfsRemoveDomainRootTargetForced(v6, i, v7, v5, Flags, 0);
    else
      v21 = DfsRemoveDomainRootTarget(v6, i, v7, v5, Flags, 0);
    v26 = v21;
    _InterlockedIncrement64((volatile signed __int64 *)(qword_1400713A8 + 32));
    if ( v21 )
      _InterlockedIncrement64((volatile signed __int64 *)(qword_1400713A8 + 40));
    _InterlockedIncrement64((volatile signed __int64 *)(qword_1400713A8 + 48));
    if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v28) )
    {
      v22 = v28.LowPart - PerformanceCount.LowPart;
      _InterlockedAdd64((volatile signed __int64 *)(qword_1400713A8 + 48), v28.QuadPart - PerformanceCount.QuadPart);
      _InterlockedIncrement((volatile signed __int32 *)(qword_1400713A8 + 56));
    }
    _InterlockedIncrement((volatile signed __int32 *)(qword_1400713A8 + 60));
    if ( (Microsoft_Windows_DFSN_ServerEnableBits & 0x80u) == 0 )
    {
      FirstComponent = v26;
    }
    else
    {
      if ( v28.QuadPart && PerformanceCount.QuadPart && QueryPerformanceFrequency(&Frequency) )
        v23 = (unsigned __int64)(1000 * (v28.QuadPart - PerformanceCount.QuadPart)) / Frequency.QuadPart;
      else
        LOBYTE(v23) = 0;
      FirstComponent = v26;
      McTemplateU0zzzqqx_EtwEventWriteTransfer(
        v22,
        (unsigned int)NetrDfsRemoveFtRootCompleted,
        (_DWORD)v6,
        (_DWORD)v7,
        (__int64)v5,
        v20,
        v26,
        v23);
    }
  }
LABEL_51:
  operator delete(v6);
  operator delete(v7);
  operator delete(v5);
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (FirstComponent != 0 ? 11 : 31)) | 0x40) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 33, WPP_f38d65142fb9367417e390a0ea4ff145_Traceguids, FirstComponent);
  }
  return FirstComponent;
}

```

## disassembly

```asm
0x140005030  mov     r11, rsp
0x140005033  push    rbx
0x140005034  push    rsi
0x140005035  push    rdi
0x140005036  push    r12
0x140005038  push    r13
0x14000503a  push    r14
0x14000503c  push    r15
0x14000503e  sub     rsp, 0E0h
0x140005045  mov     rax, cs:__security_cookie
0x14000504c  xor     rax, rsp
0x14000504f  mov     [rsp+118h+var_48], rax
0x140005057  mov     [rsp+118h+var_C0], r8d
0x14000505c  mov     rdi, rdx
0x14000505f  mov     rsi, rcx
0x140005062  xorps   xmm0, xmm0
0x140005065  movups  xmmword ptr [rsp+118h+DestinationString.Length], xmm0
0x14000506a  xorps   xmm1, xmm1
0x14000506d  movups  xmmword ptr [r11-68h], xmm1
0x140005072  movups  xmmword ptr [rsp+118h+var_98.Length], xmm0
0x14000507a  movups  xmmword ptr [r11-78h], xmm1
0x14000507f  movups  xmmword ptr [rsp+118h+var_88.Length], xmm0
0x140005087  xor     ebx, ebx
0x140005089  mov     qword ptr [rsp+118h+PerformanceCount], rbx
0x14000508e  mov     qword ptr [rsp+118h+var_C8], rbx
0x140005093  mov     qword ptr [rsp+118h+Frequency], 1
0x14000509c  mov     r13d, ebx
0x14000509f  mov     r15d, ebx
0x1400050a2  mov     r12d, ebx
0x1400050a5  mov     [rsp+118h+var_B8], rbx
0x1400050aa  lea     rax, WPP_GLOBAL_Control
0x1400050b1  lea     r14d, [rbx+40h]
0x1400050b5  cmp     cs:WPP_GLOBAL_Control, rax
0x1400050bc  jz      short loc_1400050F1
0x1400050be  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400050c5  test    rcx, rcx
0x1400050c8  jz      short loc_1400050F1
0x1400050ca  test    [rcx+1Ch], r14b
0x1400050ce  jz      short loc_1400050F1
0x1400050d0  cmp     byte ptr [rcx+19h], 1
0x1400050d4  jb      short loc_1400050F1
0x1400050d6  lea     edx, [rbx+20h]
0x1400050d9  mov     qword ptr [rsp+118h+Flags], rdi
0x1400050de  mov     r9, rsi
0x1400050e1  lea     r8, WPP_f38d65142fb9367417e390a0ea4ff145_Traceguids
0x1400050e8  mov     rcx, [rcx+10h]
0x1400050ec  call    WPP_SF_SS
0x1400050f1  mov     rdx, rsi; SourceString
0x1400050f4  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x1400050f9  call    cs:__imp_RtlInitUnicodeStringEx
0x140005100  nop     dword ptr [rax+rax+00h]
0x140005105  test    eax, eax
0x140005107  jns     short loc_14000511C
0x140005109  mov     ecx, eax; Status
0x14000510b  call    cs:__imp_RtlNtStatusToDosError
0x140005112  nop     dword ptr [rax+rax+00h]
0x140005117  jmp     loc_1400054DC
0x14000511c  xor     edx, edx; SourceString
0x14000511e  lea     rcx, [rsp+118h+String2]; DestinationString
0x140005126  call    cs:__imp_RtlInitUnicodeStringEx
0x14000512d  nop     dword ptr [rax+rax+00h]
0x140005132  xor     edx, edx; SourceString
0x140005134  lea     rcx, [rsp+118h+var_78]; DestinationString
0x14000513c  call    cs:__imp_RtlInitUnicodeStringEx
0x140005143  nop     dword ptr [rax+rax+00h]
0x140005148  lea     r8, [rsp+118h+var_78]
0x140005150  lea     rdx, [rsp+118h+String2]
0x140005158  lea     rcx, [rsp+118h+DestinationString]
0x14000515d  call    DfsGetFirstComponent
0x140005162  mov     ebx, eax
0x140005164  test    eax, eax
0x140005166  jnz     loc_1400054DE
0x14000516c  lea     rcx, [rsp+118h+DestinationString]; DestinationString
0x140005171  test    rdi, rdi
0x140005174  mov     rdx, rdi
0x140005177  jnz     short loc_14000517C
0x140005179  mov     rdx, rsi; SourceString
0x14000517c  call    cs:__imp_RtlInitUnicodeStringEx
0x140005183  nop     dword ptr [rax+rax+00h]
0x140005188  xor     esi, esi
0x14000518a  test    eax, eax
0x14000518c  js      loc_140005109
0x140005192  xor     edx, edx; SourceString
0x140005194  lea     rcx, [rsp+118h+var_98]; DestinationString
0x14000519c  call    cs:__imp_RtlInitUnicodeStringEx
0x1400051a3  nop     dword ptr [rax+rax+00h]
0x1400051a8  xor     edx, edx; SourceString
0x1400051aa  lea     rcx, [rsp+118h+var_88]; DestinationString
0x1400051b2  call    cs:__imp_RtlInitUnicodeStringEx
0x1400051b9  nop     dword ptr [rax+rax+00h]
0x1400051be  lea     r8, [rsp+118h+var_88]
0x1400051c6  lea     rdx, [rsp+118h+var_98]
0x1400051ce  lea     rcx, [rsp+118h+DestinationString]
0x1400051d3  call    DfsGetFirstComponent
0x1400051d8  mov     ebx, eax
0x1400051da  test    eax, eax
0x1400051dc  jnz     loc_1400054DE
0x1400051e2  movzx   ecx, [rsp+118h+var_98.Length]
0x1400051ea  shr     rcx, 1
0x1400051ed  inc     rcx
0x1400051f0  lea     ebx, [rsi+2]
0x1400051f3  mov     eax, ebx
0x1400051f5  mul     rcx
0x1400051f8  lea     rcx, [rsi-1]
0x1400051fc  cmovo   rax, rcx
0x140005200  mov     rcx, rax; Size
0x140005203  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005208  mov     r15, rax
0x14000520b  test    rax, rax
0x14000520e  jnz     short loc_14000521A
0x140005210  mov     ebx, 8
0x140005215  jmp     loc_1400054DE
0x14000521a  movzx   r9d, [rsp+118h+var_98.Length]; unsigned __int64
0x140005223  lea     rdx, [r9+2]; unsigned __int64
0x140005227  mov     r8, [rsp+118h+var_98.Buffer]; unsigned __int16 *
0x14000522f  mov     rcx, r15; unsigned __int16 *
0x140005232  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140005237  test    eax, eax
0x140005239  jns     short loc_140005247
0x14000523b  mov     ecx, eax; int
0x14000523d  call    ?DfsGetErrorFromHr@@YAKJ@Z; DfsGetErrorFromHr(long)
0x140005242  jmp     loc_1400054DC
0x140005247  movzx   ecx, [rsp+118h+var_88.Length]
0x14000524f  shr     rcx, 1
0x140005252  inc     rcx
0x140005255  mov     rax, rbx
0x140005258  mul     rcx
0x14000525b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140005262  cmovo   rax, rcx
0x140005266  mov     rcx, rax; Size
0x140005269  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000526e  mov     r12, rax
0x140005271  test    rax, rax
0x140005274  jz      short loc_140005210
0x140005276  movzx   r9d, [rsp+118h+var_88.Length]; unsigned __int64
0x14000527f  lea     rdx, [r9+2]; unsigned __int64
0x140005283  mov     r8, [rsp+118h+var_88.Buffer]; unsigned __int16 *
0x14000528b  mov     rcx, rax; unsigned __int16 *
0x14000528e  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x140005293  test    eax, eax
0x140005295  js      short loc_14000523B
0x140005297  lea     rcx, [rsp+118h+String2]; String2
0x14000529f  call    ?DfsIsAdDomainName@@YAHPEBU_UNICODE_STRING@@@Z; DfsIsAdDomainName(_UNICODE_STRING const *)
0x1400052a4  test    eax, eax
0x1400052a6  jz      loc_1400054C3
0x1400052ac  test    rdi, rdi
0x1400052af  jnz     short loc_1400052BB
0x1400052b1  mov     ebx, 57h ; 'W'
0x1400052b6  jmp     loc_1400054DE
0x1400052bb  movzx   ecx, [rsp+118h+var_78.Length]
0x1400052c3  shr     rcx, 1
0x1400052c6  inc     rcx
0x1400052c9  mov     rax, rbx
0x1400052cc  mul     rcx
0x1400052cf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400052d6  cmovo   rax, rcx
0x1400052da  mov     rcx, rax; Size
0x1400052dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400052e2  mov     r13, rax
0x1400052e5  test    rax, rax
0x1400052e8  jz      loc_140005210
0x1400052ee  movzx   r9d, [rsp+118h+var_78.Length]; unsigned __int64
0x1400052f7  lea     rdx, [r9+2]; unsigned __int64
0x1400052fb  mov     r8, [rsp+118h+var_78.Buffer]; unsigned __int16 *
0x140005303  mov     rcx, rax; unsigned __int16 *
0x140005306  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000530b  test    eax, eax
0x14000530d  js      loc_14000523B
0x140005313  xor     ecx, ecx; unsigned int *
0x140005315  call    ?_GetInstance@CLocalMachine@@SAPEAV1@PEAK@Z; CLocalMachine::_GetInstance(ulong *)
0x14000531a  lea     rcx, [rsp+118h+var_B8]
0x14000531f  mov     [rsp+118h+DomainControllerInfo], rcx; DomainControllerInfo
0x140005324  mov     [rsp+118h+Flags], 81h; Flags
0x14000532c  xor     r9d, r9d; SiteName
0x14000532f  xor     r8d, r8d; DomainGuid
0x140005332  mov     rdx, [rax+30h]; DomainName
0x140005336  xor     ecx, ecx; ComputerName
0x140005338  call    cs:__imp_DsGetDcNameW
0x14000533f  nop     dword ptr [rax+rax+00h]
0x140005344  mov     ebx, eax
0x140005346  mov     [rsp+118h+var_D8], eax
0x14000534a  test    eax, eax
0x14000534c  jnz     loc_1400054DE
0x140005352  mov     rax, [rsp+118h+var_B8]
0x140005357  mov     rbx, [rax]
0x14000535a  jmp     short loc_140005366
0x14000535c  cmp     ax, 5Ch ; '\'
0x140005360  jnz     short loc_14000536E
0x140005362  add     rbx, 2
0x140005366  movzx   eax, word ptr [rbx]
0x140005369  test    ax, ax
0x14000536c  jnz     short loc_14000535C
0x14000536e  test    byte ptr cs:Microsoft_Windows_DFSN_ServerEnableBits, 2
0x140005375  jz      short loc_140005396
0x140005377  lea     rax, [rsp+118h+var_58]
0x14000537f  mov     qword ptr [rsp+118h+Flags], rax; unsigned int
0x140005384  mov     r9d, 1
0x14000538a  lea     rdx, NetrDfsRemoveFtRootArrived
0x140005391  call    McGenEventWrite_EtwEventWriteTransfer
0x140005396  lea     rcx, [rsp+118h+PerformanceCount]; lpPerformanceCount
0x14000539b  call    cs:__imp_QueryPerformanceCounter
0x1400053a2  nop     dword ptr [rax+rax+00h]
0x1400053a7  test    eax, eax
0x1400053a9  jnz     short loc_1400053B0
0x1400053ab  mov     qword ptr [rsp+118h+PerformanceCount], rsi
0x1400053b0  mov     edi, [rsp+118h+var_C0]
0x1400053b4  mov     dword ptr [rsp+118h+DomainControllerInfo], esi; unsigned int
0x1400053b8  mov     r9, r13; unsigned __int16 *
0x1400053bb  mov     r8, r12; unsigned __int16 *
0x1400053be  mov     rdx, rbx; unsigned __int16 *
0x1400053c1  mov     rcx, r15; unsigned __int16 *
0x1400053c4  test    edi, edi
0x1400053c6  js      short loc_1400053CF
0x1400053c8  call    ?DfsRemoveDomainRootTarget@@YAKPEBG000KK@Z; DfsRemoveDomainRootTarget(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1400053cd  jmp     short loc_1400053D4
0x1400053cf  call    ?DfsRemoveDomainRootTargetForced@@YAKPEBG000KK@Z; DfsRemoveDomainRootTargetForced(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1400053d4  mov     [rsp+118h+var_D8], eax
0x1400053d8  mov     rax, cs:qword_1400713A8
0x1400053df  lock inc qword ptr [rax+20h]
0x1400053e4  cmp     [rsp+118h+var_D8], esi
0x1400053e8  jz      short loc_1400053F6
0x1400053ea  mov     rax, cs:qword_1400713A8
0x1400053f1  lock inc qword ptr [rax+28h]
0x1400053f6  mov     rax, cs:qword_1400713A8
0x1400053fd  lock inc qword ptr [rax+30h]
0x140005402  cmp     qword ptr [rsp+118h+PerformanceCount], rsi
0x140005407  jz      short loc_14000543F
0x140005409  lea     rcx, [rsp+118h+var_C8]; lpPerformanceCount
0x14000540e  call    cs:__imp_QueryPerformanceCounter
0x140005415  nop     dword ptr [rax+rax+00h]
0x14000541a  test    eax, eax
0x14000541c  jz      short loc_14000543F
0x14000541e  mov     rcx, qword ptr [rsp+118h+var_C8]
0x140005423  sub     rcx, qword ptr [rsp+118h+PerformanceCount]
0x140005428  mov     rax, cs:qword_1400713A8
0x14000542f  lock add [rax+30h], rcx
0x140005434  mov     rax, cs:qword_1400713A8
0x14000543b  lock inc dword ptr [rax+38h]
0x14000543f  mov     rax, cs:qword_1400713A8
0x140005446  lock inc dword ptr [rax+3Ch]
0x14000544a  test    byte ptr cs:Microsoft_Windows_DFSN_ServerEnableBits, 80h
0x140005451  jz      short loc_1400054BD
0x140005453  cmp     qword ptr [rsp+118h+var_C8], rsi
0x140005458  jz      short loc_140005490
0x14000545a  cmp     qword ptr [rsp+118h+PerformanceCount], rsi
0x14000545f  jz      short loc_140005490
0x140005461  lea     rcx, [rsp+118h+Frequency]; lpFrequency
0x140005466  call    cs:__imp_QueryPerformanceFrequency
0x14000546d  nop     dword ptr [rax+rax+00h]
0x140005472  test    eax, eax
0x140005474  jz      short loc_140005490
0x140005476  mov     rax, qword ptr [rsp+118h+var_C8]
0x14000547b  sub     rax, qword ptr [rsp+118h+PerformanceCount]
0x140005480  imul    rax, 3E8h
0x140005487  xor     edx, edx
0x140005489  div     qword ptr [rsp+118h+Frequency]
0x14000548e  jmp     short loc_140005493
0x140005490  mov     rax, rsi
0x140005493  mov     [rsp+118h+var_E0], rax
0x140005498  mov     ebx, [rsp+118h+var_D8]
0x14000549c  mov     [rsp+118h+var_E8], ebx
0x1400054a0  mov     dword ptr [rsp+118h+DomainControllerInfo], edi
0x1400054a4  mov     qword ptr [rsp+118h+Flags], r13
0x1400054a9  mov     r9, r12
0x1400054ac  mov     r8, r15
0x1400054af  lea     rdx, NetrDfsRemoveFtRootCompleted
0x1400054b6  call    McTemplateU0zzzqqx_EtwEventWriteTransfer
0x1400054bb  jmp     short loc_1400054DE
0x1400054bd  mov     ebx, [rsp+118h+var_D8]
0x1400054c1  jmp     short loc_1400054DE
0x1400054c3  test    rdi, rdi
0x1400054c6  jnz     loc_1400052B1
0x1400054cc  mov     r8d, [rsp+118h+var_C0]
0x1400054d1  mov     rdx, r12; unsigned __int16 *
0x1400054d4  mov     rcx, r15; unsigned __int16 *
0x1400054d7  call    NetrDfsRemoveStdRoot
0x1400054dc  mov     ebx, eax
0x1400054de  mov     rcx, r15; Block
0x1400054e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400054e6  mov     rcx, r12; Block
0x1400054e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400054ee  mov     rcx, r13; Block
0x1400054f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400054f6  mov     rcx, [rsp+118h+var_B8]; Buffer
0x1400054fb  test    rcx, rcx
0x1400054fe  jz      short loc_14000550C
0x140005500  call    cs:__imp_NetApiBufferFree
0x140005507  nop     dword ptr [rax+rax+00h]
0x14000550c  lea     rax, WPP_GLOBAL_Control
0x140005513  cmp     cs:WPP_GLOBAL_Control, rax
0x14000551a  jz      short loc_14000555C
0x14000551c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140005523  test    rcx, rcx
0x140005526  jz      short loc_14000555C
0x140005528  mov     eax, ebx
0x14000552a  neg     eax
0x14000552c  sbb     edx, edx
0x14000552e  and     edx, 0FFFFFFECh
0x140005531  add     edx, 1Fh
0x140005534  bts     r14d, edx
  ... truncated ...
```
