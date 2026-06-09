# CGlobalPipeMgr::CreatePipeServer(char const *,void * *)

- ea: `0x1800746a8`
- end: `0x180074987`
- name: `?CreatePipeServer@CGlobalPipeMgr@@AEAAJPEBDPEAPEAX@Z`
- size: `735`
- prototype: `__int64 __fastcall(WCHAR *this, const char *, void **, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180074230`

## callees

- `0x1800091a8`
- `0x18000c4ec`
- `0x180017e80`
- `0x180017f34`
- `0x18002e600`
- `0x180059838`
- `0x180059878`
- `0x1800746a8`
- `0x180074c9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074910`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074963`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074963`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180074851`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180074851`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180074864`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180074864`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180074901`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180074901`

## string_xrefs

- `0x18007494b`: `Failed CreateNamedPipe Call`
- `0x180074817`: `GetNpAcl`

## pseudocode

```c
__int64 __fastcall CGlobalPipeMgr::CreatePipeServer(WCHAR *this, const char *a2, void **a3, int a4)
{
  signed int v7; // eax
  bool v8; // sf
  bool v9; // sf
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int NpAcl; // esi
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  DWORD v15; // ebx
  DWORD v16; // edi
  unsigned int v17; // eax
  HANDLE v18; // rbx
  signed int LastError; // eax
  unsigned int nOutBufferSize; // [rsp+20h] [rbp-59h]
  PACL pDacl; // [rsp+40h] [rbp-39h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-31h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-19h] BYREF
  int v25; // [rsp+68h] [rbp-11h]
  _OWORD pSecurityDescriptor[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+A8h] [rbp+2Fh]
  DWORD nInBufferSize; // [rsp+F0h] [rbp+77h] BYREF
  DWORD v29; // [rsp+F8h] [rbp+7Fh] BYREF

  v27 = 0;
  pDacl = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  *a3 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  nInBufferSize = 0;
  v29 = 0;
  CTSRegEntry::CTSRegEntry(&phkResult, (const unsigned __int16 *)a2, (HKEY)a3, a4, nOutBufferSize);
  v7 = v25;
  if ( v25 > 0 )
    v7 = (unsigned __int16)v25 | 0x80070000;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    nInBufferSize = 0x10000;
    goto LABEL_19;
  }
  CTSRegEntry::GetNumber((CTSRegEntry *)&phkResult, L"PipeNMPInBufferSize", 0x10000, (int *)&nInBufferSize);
  v8 = v25 < 0;
  if ( v25 > 0 )
    v8 = 1;
  if ( v8 || (int)nInBufferSize <= 0 )
    nInBufferSize = 0x10000;
  CTSRegEntry::GetNumber((CTSRegEntry *)&phkResult, L"PipeNMPOutBufferSize", 0x10000, (int *)&v29);
  v9 = v25 < 0;
  if ( v25 > 0 )
    v9 = 1;
  if ( v9 || (int)v29 <= 0 )
LABEL_19:
    v29 = 0x10000;
  CTSRegEntry::~CTSRegEntry((CTSRegEntry *)&phkResult);
  NpAcl = CGlobalPipeMgr::GetNpAcl((CGlobalPipeMgr *)this, a2, &pDacl);
  if ( NpAcl >= 0 )
  {
    InitializeSecurityDescriptor(pSecurityDescriptor, 1u);
    SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0);
    SecurityAttributes.bInheritHandle = 0;
    SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
    SecurityAttributes.nLength = 24;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v15 = v29;
      v16 = nInBufferSize;
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        &WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
        v17,
        v16,
        v15);
    }
    v18 = CreateNamedPipeW(this + 44, 0x40080003u, 0xEu, 0xFFu, v29, nInBufferSize, 0, &SecurityAttributes);
    if ( v18 != (HANDLE)-1LL )
      goto LABEL_38;
    LastError = GetLastError();
    NpAcl = LastError;
    if ( LastError > 0 )
      NpAcl = (unsigned __int16)LastError | 0x80070000;
    if ( NpAcl < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 35;
        v14 = "Failed CreateNamedPipe Call";
        goto LABEL_25;
      }
    }
    else
    {
LABEL_38:
      *a3 = v18;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 33;
    v14 = "GetNpAcl";
LABEL_25:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      v12,
      (__int64)v14,
      NpAcl);
  }
  if ( pDacl )
    LocalFree(pDacl);
  return (unsigned int)NpAcl;
}

```

## disassembly

```asm
0x1800746a8  mov     [rsp-8+arg_0], rbx
0x1800746ad  mov     [rsp-8+arg_8], rsi
0x1800746b2  push    rbp
0x1800746b3  push    rdi
0x1800746b4  push    r13
0x1800746b6  push    r14
0x1800746b8  push    r15
0x1800746ba  lea     rbp, [rsp-37h]
0x1800746bf  sub     rsp, 0B0h
0x1800746c6  xor     eax, eax
0x1800746c8  xorps   xmm1, xmm1
0x1800746cb  mov     r15, rcx
0x1800746ce  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x1800746d2  xorps   xmm0, xmm0
0x1800746d5  mov     [rbp+57h+var_28], rax
0x1800746d9  lea     rcx, [rbp+57h+phkResult]; phkResult
0x1800746dd  mov     [rbp+57h+pDacl], rax
0x1800746e1  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x1800746e5  mov     [r8], rax
0x1800746e8  mov     r14, r8
0x1800746eb  movups  [rbp+57h+pSecurityDescriptor], xmm1
0x1800746ef  mov     [rbp+57h+arg_10], eax
0x1800746f2  mov     rdi, rdx
0x1800746f5  movups  [rbp+57h+var_38], xmm1
0x1800746f9  mov     [rbp+57h+arg_18], eax
0x1800746fc  call    ??0CTSRegEntry@@QEAA@PEBGPEAUHKEY__@@HK@Z; CTSRegEntry::CTSRegEntry(ushort const *,HKEY__ *,int,ulong)
0x180074701  mov     eax, [rbp+57h+var_68]
0x180074704  mov     esi, 80070000h
0x180074709  test    eax, eax
0x18007470b  jle     short loc_180074712
0x18007470d  movzx   eax, ax
0x180074710  or      eax, esi
0x180074712  lea     r13, WPP_GLOBAL_Control
0x180074719  test    eax, eax
0x18007471b  js      short loc_180074781
0x18007471d  mov     ebx, 10000h
0x180074722  lea     r9, [rbp+57h+arg_10]; int *
0x180074726  mov     r8d, ebx; int
0x180074729  lea     rdx, aPipenmpinbuffe; "PipeNMPInBufferSize"
0x180074730  lea     rcx, [rbp+57h+phkResult]; this
0x180074734  call    ?GetNumber@CTSRegEntry@@QEAAJPEBGJPEAJ@Z; CTSRegEntry::GetNumber(ushort const *,long,long *)
0x180074739  mov     eax, [rbp+57h+var_68]
0x18007473c  test    eax, eax
0x18007473e  jle     short loc_180074747
0x180074740  movzx   eax, ax
0x180074743  or      eax, esi
0x180074745  test    eax, eax
0x180074747  js      short loc_18007474F
0x180074749  cmp     [rbp+57h+arg_10], 0
0x18007474d  jg      short loc_180074752
0x18007474f  mov     [rbp+57h+arg_10], ebx
0x180074752  lea     r9, [rbp+57h+arg_18]; int *
0x180074756  mov     r8d, ebx; int
0x180074759  lea     rdx, aPipenmpoutbuff; "PipeNMPOutBufferSize"
0x180074760  lea     rcx, [rbp+57h+phkResult]; this
0x180074764  call    ?GetNumber@CTSRegEntry@@QEAAJPEBGJPEAJ@Z; CTSRegEntry::GetNumber(ushort const *,long,long *)
0x180074769  mov     eax, [rbp+57h+var_68]
0x18007476c  test    eax, eax
0x18007476e  jle     short loc_180074777
0x180074770  movzx   eax, ax
0x180074773  or      eax, esi
0x180074775  test    eax, eax
0x180074777  js      short loc_1800747C8
0x180074779  cmp     [rbp+57h+arg_18], 0
0x18007477d  jg      short loc_1800747CB
0x18007477f  jmp     short loc_1800747C8
0x180074781  mov     rax, cs:WPP_GLOBAL_Control
0x180074788  cmp     rax, r13
0x18007478b  jz      short loc_1800747C0
0x18007478d  test    dword ptr [rax+1Ch], 800h
0x180074794  jz      short loc_1800747C0
0x180074796  cmp     byte ptr [rax+19h], 4
0x18007479a  jb      short loc_1800747C0
0x18007479c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800747a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800747a8  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800747af  mov     edx, 20h ; ' '
0x1800747b4  mov     r9d, eax
0x1800747b7  mov     rcx, [rcx+10h]
0x1800747bb  call    WPP_SF_d
0x1800747c0  mov     ebx, 10000h
0x1800747c5  mov     [rbp+57h+arg_10], ebx
0x1800747c8  mov     [rbp+57h+arg_18], ebx
0x1800747cb  lea     rcx, [rbp+57h+phkResult]; this
0x1800747cf  call    ??1CTSRegEntry@@QEAA@XZ; CTSRegEntry::~CTSRegEntry(void)
0x1800747d4  lea     r8, [rbp+57h+pDacl]; struct _ACL **
0x1800747d8  mov     rdx, rdi; char *
0x1800747db  mov     rcx, r15; this
0x1800747de  call    ?GetNpAcl@CGlobalPipeMgr@@AEAAJPEBDPEAPEAU_ACL@@@Z; CGlobalPipeMgr::GetNpAcl(char const *,_ACL * *)
0x1800747e3  mov     esi, eax
0x1800747e5  test    eax, eax
0x1800747e7  jns     short loc_180074846
0x1800747e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800747f0  cmp     rax, r13
0x1800747f3  jz      loc_18007495A
0x1800747f9  test    byte ptr [rax+1Ch], 8
0x1800747fd  jz      loc_18007495A
0x180074803  cmp     byte ptr [rax+19h], 2
0x180074807  jb      loc_18007495A
0x18007480d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074812  mov     edx, 21h ; '!'
0x180074817  lea     rcx, aGetnpacl; "GetNpAcl"
0x18007481e  mov     [rsp+0D0h+nInBufferSize], esi
0x180074822  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x180074829  mov     qword ptr [rsp+0D0h+nOutBufferSize], rcx
0x18007482e  mov     r9d, eax
0x180074831  mov     rcx, cs:WPP_GLOBAL_Control
0x180074838  mov     rcx, [rcx+10h]
0x18007483c  call    WPP_SF_DsD
0x180074841  jmp     loc_18007495A
0x180074846  mov     ebx, 1
0x18007484b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007484f  mov     edx, ebx; dwRevision
0x180074851  call    cs:__imp_InitializeSecurityDescriptor
0x180074857  mov     r8, [rbp+57h+pDacl]; pDacl
0x18007485b  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18007485f  xor     r9d, r9d; bDaclDefaulted
0x180074862  mov     edx, ebx; bDaclPresent
0x180074864  call    cs:__imp_SetSecurityDescriptorDacl
0x18007486a  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18007486e  mov     [rbp+57h+SecurityAttributes.bInheritHandle], 0
0x180074875  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x180074879  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x180074880  mov     rax, cs:WPP_GLOBAL_Control
0x180074887  cmp     rax, r13
0x18007488a  jz      short loc_1800748CD
0x18007488c  test    dword ptr [rax+1Ch], 800h
0x180074893  jz      short loc_1800748CD
0x180074895  cmp     byte ptr [rax+19h], 4
0x180074899  jb      short loc_1800748CD
0x18007489b  mov     ebx, [rbp+57h+arg_18]
0x18007489e  mov     edi, [rbp+57h+arg_10]
0x1800748a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800748a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800748ad  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x1800748b4  mov     edx, 22h ; '"'
0x1800748b9  mov     [rsp+0D0h+nInBufferSize], ebx
0x1800748bd  mov     r9d, eax
0x1800748c0  mov     [rsp+0D0h+nOutBufferSize], edi
0x1800748c4  mov     rcx, [rcx+10h]
0x1800748c8  call    WPP_SF_DdD
0x1800748cd  lea     rax, [rbp+57h+SecurityAttributes]
0x1800748d1  mov     edx, 40080003h; dwOpenMode
0x1800748d6  mov     [rsp+0D0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800748db  lea     rcx, [r15+58h]; lpName
0x1800748df  mov     eax, [rbp+57h+arg_10]
0x1800748e2  mov     r9d, 0FFh; nMaxInstances
0x1800748e8  mov     [rsp+0D0h+nDefaultTimeOut], 0; nDefaultTimeOut
0x1800748f0  mov     r8d, 0Eh; dwPipeMode
0x1800748f6  mov     [rsp+0D0h+nInBufferSize], eax; nInBufferSize
0x1800748fa  mov     eax, [rbp+57h+arg_18]
0x1800748fd  mov     [rsp+0D0h+nOutBufferSize], eax; nOutBufferSize
0x180074901  call    cs:__imp_CreateNamedPipeW
0x180074907  mov     rbx, rax
0x18007490a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007490e  jnz     short loc_180074957
0x180074910  call    cs:__imp_GetLastError
0x180074916  mov     esi, eax
0x180074918  test    eax, eax
0x18007491a  jle     short loc_180074925
0x18007491c  movzx   esi, ax
0x18007491f  or      esi, 80070000h
0x180074925  test    esi, esi
0x180074927  jns     short loc_180074957
0x180074929  mov     rax, cs:WPP_GLOBAL_Control
0x180074930  cmp     rax, r13
0x180074933  jz      short loc_18007495A
0x180074935  test    byte ptr [rax+1Ch], 8
0x180074939  jz      short loc_18007495A
0x18007493b  cmp     byte ptr [rax+19h], 2
0x18007493f  jb      short loc_18007495A
0x180074941  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180074946  mov     edx, 23h ; '#'
0x18007494b  lea     rcx, aFailedCreatena; "Failed CreateNamedPipe Call"
0x180074952  jmp     loc_18007481E
0x180074957  mov     [r14], rbx
0x18007495a  mov     rcx, [rbp+57h+pDacl]; hMem
0x18007495e  test    rcx, rcx
0x180074961  jz      short loc_180074969
0x180074963  call    cs:__imp_LocalFree
0x180074969  lea     r11, [rsp+0D0h+var_20]
0x180074971  mov     eax, esi
0x180074973  mov     rbx, [r11+30h]
0x180074977  mov     rsi, [r11+38h]
0x18007497b  mov     rsp, r11
0x18007497e  pop     r15
0x180074980  pop     r14
0x180074982  pop     r13
0x180074984  pop     rdi
0x180074985  pop     rbp
0x180074986  retn
```
