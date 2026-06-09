# ExecuteManagedRequestBitnessAware(ushort const *,int,_GUID,_GUID,ulong,ulong,ushort * *,ulong,ushort * *)

- ea: `0x180007604`
- end: `0x180007a45`
- name: `?ExecuteManagedRequestBitnessAware@@YAJPEBGHU_GUID@@1KKPEAPEAGK2@Z`
- size: `1089`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, struct _GUID *, struct _GUID *, unsigned int, unsigned int, unsigned __int16 **, unsigned int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003b088`
- `0x18003d5c0`
- `0x18003e5d0`

## callees

- `0x180001e60`
- `0x180007604`
- `0x180007a4c`
- `0x18000a8fc`
- `0x180012f5c`
- `0x180014bb4`
- `0x180014ec8`
- `0x180017d10`
- `0x18002afa8`
- `0x180043b94`
- `0x180043c14`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800077a6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800077a6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800077c4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800077c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000769d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000769d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078a1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800078d7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800078d7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800079c9`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800079c9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180007866`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180007866`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000783b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000783b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180007693`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180007693`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000775a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000775a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800079e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007720`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007720`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180007707`
- `OLEAUT32!__imp_SysAllocString` at `0x18000799f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000799f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079f7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800079f7`

## string_xrefs

- `0x1800076bb`: `\RunDll32.exe`
- `0x180007944`: `RunDll32.exe catsrvut.dll,ManagedRequest `

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ExecuteManagedRequestBitnessAware(
        const unsigned __int16 *a1,
        __int64 a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 **a7,
        unsigned int a8,
        unsigned __int16 **a9)
{
  unsigned int v9; // esi
  signed int LastError; // eax
  int Process; // edi
  signed int v12; // eax
  HANDLE CurrentThread; // rax
  unsigned int v14; // r8d
  unsigned __int64 v15; // rbx
  unsigned int i; // ecx
  unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  DWORD dwMaximumSizeLow; // esi
  HANDLE v20; // r15
  signed int v21; // eax
  signed int v22; // eax
  char *v23; // rax
  char *v24; // rbx
  unsigned int v25; // r10d
  int v26; // r8d
  const OLECHAR *Param; // rax
  unsigned __int16 *v28; // rax
  int v30; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  struct _GUID *v32; // [rsp+40h] [rbp-C0h]
  struct _GUID *v33; // [rsp+48h] [rbp-B8h]
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+50h] [rbp-B0h] BYREF
  void *ppInterface; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+78h] [rbp-88h]
  _SYSTEM_INFO SystemInfo; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pSecurityDescriptor[56]; // [rsp+B0h] [rbp-50h] BYREF
  GUID pguid; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Name[7]; // [rsp+100h] [rbp+0h] BYREF
  OLECHAR sz[49]; // [rsp+10Eh] [rbp+Eh] BYREF
  WCHAR CommandLine[104]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp+140h] BYREF

  v33 = a4;
  v32 = a3;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  v9 = 0;
  TokenHandle = 0;
  pguid = 0;
  memset_0(Buffer, 0, 0x20Au);
  ppInterface = 0;
  v36 = 0;
  v37 = 0;
  if ( !GetSystemDirectoryW(Buffer, 0x105u) )
  {
    LastError = GetLastError();
    Process = LastError;
    if ( LastError > 0 )
      Process = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_53;
  }
  v12 = StringCchCatW(Buffer, 0x105u, L"\\RunDll32.exe");
  if ( v12 < 0
    || (v12 = StringCchCopyW(Name, 0x32u, L"Global\\"), v12 < 0)
    || (v12 = CImpersonate::ImpersonateClient(&ppInterface), v30 = v12, v12 < 0) )
  {
LABEL_5:
    Process = v12;
    goto LABEL_53;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_5;
  }
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &v30);
  Process = v30;
  if ( v30 >= 0 )
  {
    if ( a8 )
      memset_0(a9, 0, 8LL * a8);
    CSystemAndUserDescriptor::CSystemAndUserDescriptor(pSecurityDescriptor, TokenHandle, v14, &v30);
    Process = v30;
    if ( v30 >= 0 )
    {
      Process = CoCreateGuid(&pguid);
      if ( Process >= 0 )
      {
        if ( StringFromGUID2(&pguid, sz, 43) )
        {
          FileMappingAttributes.nLength = 24;
          FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
          FileMappingAttributes.bInheritHandle = 0;
          v15 = 1616;
          for ( i = 0; i < a6; ++i )
          {
            v15 += 2LL;
            v17 = a7[i];
            if ( v17 )
            {
              v18 = -1;
              do
                ++v18;
              while ( v17[v18] );
              v15 += 2 * v18;
            }
          }
          memset(&SystemInfo, 0, sizeof(SystemInfo));
          GetSystemInfo(&SystemInfo);
          dwMaximumSizeLow = SystemInfo.dwAllocationGranularity;
          if ( v15 >= SystemInfo.dwAllocationGranularity )
            dwMaximumSizeLow = v15;
          v20 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, dwMaximumSizeLow, Name);
          if ( v20 )
          {
            if ( GetLastError() == 183 || (v23 = (char *)MapViewOfFile(v20, 6u, 0, 0, 0), (v24 = v23) == 0) )
            {
              v22 = GetLastError();
              Process = v22;
              v9 = 0;
              if ( v22 > 0 )
                Process = (unsigned __int16)v22 | 0x80070000;
            }
            else
            {
              *(_WORD *)v23 = 0;
              *((_DWORD *)v23 + 390) = dwMaximumSizeLow;
              *(struct _GUID *)(v23 + 1564) = *v32;
              *(struct _GUID *)(v23 + 1580) = *v33;
              *((_DWORD *)v23 + 399) = a5;
              *((_DWORD *)v23 + 400) = a6;
              *((_DWORD *)v23 + 401) = a8;
              v9 = 0;
              *((_DWORD *)v23 + 402) = 0;
              Process = SPR_Data::SetParams((struct SPR_Data *)v23, a6, a7);
              if ( Process >= 0 )
              {
                Process = StringCchCopyW(CommandLine, 0x64u, L"RunDll32.exe catsrvut.dll,ManagedRequest ");
                if ( Process >= 0 )
                {
                  Process = StringCchCatW(CommandLine, v25, Name);
                  if ( Process >= 0 )
                  {
                    Process = ImpersonatingCreateProcess(Buffer, CommandLine, v26);
                    if ( Process >= 0 )
                    {
                      while ( v9 < a8 )
                      {
                        Param = SPR_Data::GetParam((struct SPR_Data *)v24, v9);
                        v28 = SysAllocString(Param);
                        a9[v9] = v28;
                        if ( !v28 )
                        {
                          Process = -2147024882;
                          break;
                        }
                        ++v9;
                      }
                      v9 = 0;
                    }
                  }
                }
              }
              if ( *((int *)v24 + 402) < 0 )
                Process = *((_DWORD *)v24 + 402);
              UnmapViewOfFile(v24);
            }
            CloseHandle(v20);
          }
          else
          {
            v21 = GetLastError();
            Process = v21;
            v9 = 0;
            if ( v21 > 0 )
              Process = (unsigned __int16)v21 | 0x80070000;
          }
        }
        else
        {
          Process = -2147467259;
        }
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( Process < 0 && a8 )
    {
      do
      {
        SysFreeString(a9[v9]);
        a9[v9++] = 0;
      }
      while ( v9 < a8 );
    }
    CSystemAndUserDescriptor::~CSystemAndUserDescriptor((CSystemAndUserDescriptor *)pSecurityDescriptor);
  }
  else
  {
    CloseHandle(TokenHandle);
  }
LABEL_53:
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)Process;
}

```

## disassembly

```asm
0x180007604  push    rbp
0x180007606  push    rbx
0x180007607  push    rsi
0x180007608  push    rdi
0x180007609  push    r12
0x18000760b  push    r13
0x18000760d  push    r14
0x18000760f  push    r15
0x180007611  lea     rbp, [rsp-368h]
0x180007619  sub     rsp, 468h
0x180007620  mov     rax, cs:__security_cookie
0x180007627  xor     rax, rsp
0x18000762a  mov     [rbp+3A0h+var_50], rax
0x180007631  mov     [rsp+4A0h+var_458], r9
0x180007636  mov     [rsp+4A0h+var_460], r8
0x18000763b  mov     r12, [rbp+3A0h+arg_40]
0x180007642  mov     r13, [rbp+3A0h+arg_30]
0x180007649  xorps   xmm0, xmm0
0x18000764c  xor     eax, eax
0x18000764e  movups  xmmword ptr [rsp+4A0h+FileMappingAttributes.nLength], xmm0
0x180007653  mov     qword ptr [rsp+4A0h+FileMappingAttributes.bInheritHandle], rax
0x180007658  xor     esi, esi
0x18000765a  mov     [rsp+4A0h+TokenHandle], rsi
0x18000765f  movups  xmmword ptr [rbp+3A0h+pguid.Data1], xmm0
0x180007663  xor     edx, edx; Val
0x180007665  mov     r8d, 20Ah; Size
0x18000766b  lea     rcx, [rbp+3A0h+Buffer]; void *
0x180007672  call    memset_0
0x180007677  mov     [rsp+4A0h+ppInterface], rsi
0x18000767c  mov     [rsp+4A0h+var_430], esi
0x180007680  mov     [rsp+4A0h+var_428], rsi
0x180007685  mov     ebx, 105h
0x18000768a  mov     edx, ebx; uSize
0x18000768c  lea     rcx, [rbp+3A0h+Buffer]; lpBuffer
0x180007693  call    cs:__imp_GetSystemDirectoryW
0x180007699  test    eax, eax
0x18000769b  jnz     short loc_1800076BB
0x18000769d  call    cs:__imp_GetLastError
0x1800076a3  mov     edi, eax
0x1800076a5  test    eax, eax
0x1800076a7  jle     loc_180007A16
0x1800076ad  movzx   edi, ax
0x1800076b0  or      edi, 80070000h
0x1800076b6  jmp     loc_180007A16
0x1800076bb  lea     r8, aRundll32Exe; "\\RunDll32.exe"
0x1800076c2  mov     rdx, rbx; unsigned __int64
0x1800076c5  lea     rcx, [rbp+3A0h+Buffer]; unsigned __int16 *
0x1800076cc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800076d1  test    eax, eax
0x1800076d3  jns     short loc_1800076DC
0x1800076d5  mov     edi, eax
0x1800076d7  jmp     loc_180007A16
0x1800076dc  lea     r8, aGlobal; "Global\\"
0x1800076e3  mov     edx, 32h ; '2'; unsigned __int64
0x1800076e8  lea     rcx, [rbp+3A0h+Name]; unsigned __int16 *
0x1800076ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800076f1  test    eax, eax
0x1800076f3  js      short loc_1800076D5
0x1800076f5  lea     rcx, [rsp+4A0h+ppInterface]; ppInterface
0x1800076fa  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x1800076ff  mov     [rsp+4A0h+var_470], eax
0x180007703  test    eax, eax
0x180007705  js      short loc_1800076D5
0x180007707  call    cs:__imp_GetCurrentThread
0x18000770d  mov     rcx, rax; ThreadHandle
0x180007710  lea     r9, [rsp+4A0h+TokenHandle]; TokenHandle
0x180007715  mov     edx, 0F01FFh; DesiredAccess
0x18000771a  mov     r8d, 1; OpenAsSelf
0x180007720  call    cs:__imp_OpenThreadToken
0x180007726  test    eax, eax
0x180007728  jnz     short loc_18000773E
0x18000772a  call    cs:__imp_GetLastError
0x180007730  test    eax, eax
0x180007732  jle     short loc_1800076D5
0x180007734  movzx   eax, ax
0x180007737  or      eax, 80070000h
0x18000773c  jmp     short loc_1800076D5
0x18000773e  lea     rdx, [rsp+4A0h+var_470]; int *
0x180007743  lea     rcx, [rsp+4A0h+ppInterface]; this
0x180007748  call    ?Cleanup@CImpersonate@@QEAAXPEAJ@Z; CImpersonate::Cleanup(long *)
0x18000774d  mov     edi, [rsp+4A0h+var_470]
0x180007751  test    edi, edi
0x180007753  jns     short loc_180007765
0x180007755  mov     rcx, [rsp+4A0h+TokenHandle]; hObject
0x18000775a  call    cs:__imp_CloseHandle
0x180007760  jmp     loc_180007A16
0x180007765  mov     r14d, [rbp+3A0h+arg_38]
0x18000776c  test    r14d, r14d
0x18000776f  jz      short loc_180007782
0x180007771  mov     r8d, r14d
0x180007774  shl     r8, 3; Size
0x180007778  xor     edx, edx; Val
0x18000777a  mov     rcx, r12; void *
0x18000777d  call    memset_0
0x180007782  lea     r9, [rsp+4A0h+var_470]; int *
0x180007787  mov     rdx, [rsp+4A0h+TokenHandle]; TokenHandle
0x18000778c  lea     rcx, [rbp+3A0h+pSecurityDescriptor]; pSecurityDescriptor
0x180007790  call    ??0CSystemAndUserDescriptor@@QEAA@PEAXKPEAJ@Z; CSystemAndUserDescriptor::CSystemAndUserDescriptor(void *,ulong,long *)
0x180007795  nop
0x180007796  mov     edi, [rsp+4A0h+var_470]
0x18000779a  test    edi, edi
0x18000779c  js      loc_1800079D8
0x1800077a2  lea     rcx, [rbp+3A0h+pguid]; pguid
0x1800077a6  call    cs:__imp_CoCreateGuid
0x1800077ac  mov     edi, eax
0x1800077ae  test    eax, eax
0x1800077b0  js      loc_1800079D8
0x1800077b6  mov     r8d, 2Bh ; '+'; cchMax
0x1800077bc  lea     rdx, [rbp+3A0h+sz]; lpsz
0x1800077c0  lea     rcx, [rbp+3A0h+pguid]; rguid
0x1800077c4  call    cs:__imp_StringFromGUID2
0x1800077ca  test    eax, eax
0x1800077cc  jnz     short loc_1800077D8
0x1800077ce  mov     edi, 80004005h
0x1800077d3  jmp     loc_1800079D8
0x1800077d8  mov     [rsp+4A0h+FileMappingAttributes.nLength], 18h
0x1800077e0  lea     rax, [rbp+3A0h+pSecurityDescriptor]
0x1800077e4  mov     [rsp+4A0h+FileMappingAttributes.lpSecurityDescriptor], rax
0x1800077e9  mov     [rsp+4A0h+FileMappingAttributes.bInheritHandle], esi
0x1800077ed  mov     ebx, 650h
0x1800077f2  mov     ecx, esi
0x1800077f4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800077f8  mov     edi, [rbp+3A0h+arg_28]
0x1800077fe  test    edi, edi
0x180007800  jz      short loc_180007828
0x180007802  add     rbx, 2
0x180007806  mov     eax, ecx
0x180007808  mov     rdx, [r13+rax*8+0]
0x18000780d  test    rdx, rdx
0x180007810  jz      short loc_180007822
0x180007812  mov     rax, r15
0x180007815  inc     rax
0x180007818  cmp     [rdx+rax*2], si
0x18000781c  jnz     short loc_180007815
0x18000781e  lea     rbx, [rbx+rax*2]
0x180007822  inc     ecx
0x180007824  cmp     ecx, edi
0x180007826  jb      short loc_180007802
0x180007828  xorps   xmm0, xmm0
0x18000782b  movups  xmmword ptr [rbp+3A0h+SystemInfo], xmm0
0x18000782f  movups  xmmword ptr [rbp+3A0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180007833  movups  xmmword ptr [rbp+3A0h+SystemInfo.dwNumberOfProcessors], xmm0
0x180007837  lea     rcx, [rbp+3A0h+SystemInfo]; lpSystemInfo
0x18000783b  call    cs:__imp_GetSystemInfo
0x180007841  mov     esi, [rbp+3A0h+SystemInfo.dwAllocationGranularity]
0x180007844  cmp     rbx, rsi
0x180007847  cmovnb  esi, ebx
0x18000784a  lea     rax, [rbp+3A0h+Name]
0x18000784e  mov     [rsp+4A0h+lpName], rax; lpName
0x180007853  mov     [rsp+4A0h+dwMaximumSizeLow], esi; dwMaximumSizeLow
0x180007857  xor     r9d, r9d; dwMaximumSizeHigh
0x18000785a  lea     r8d, [r9+4]; flProtect
0x18000785e  lea     rdx, [rsp+4A0h+FileMappingAttributes]; lpFileMappingAttributes
0x180007863  mov     rcx, r15; hFile
0x180007866  call    cs:__imp_CreateFileMappingW
0x18000786c  mov     r15, rax
0x18000786f  test    rax, rax
0x180007872  jnz     short loc_180007894
0x180007874  call    cs:__imp_GetLastError
0x18000787a  mov     edi, eax
0x18000787c  xor     esi, esi
0x18000787e  test    eax, eax
0x180007880  jle     loc_1800079D8
0x180007886  movzx   edi, ax
0x180007889  or      edi, 80070000h
0x18000788f  jmp     loc_1800079D8
0x180007894  call    cs:__imp_GetLastError
0x18000789a  cmp     eax, 0B7h
0x18000789f  jnz     short loc_1800078C1
0x1800078a1  call    cs:__imp_GetLastError
0x1800078a7  mov     edi, eax
0x1800078a9  xor     esi, esi
0x1800078ab  test    eax, eax
0x1800078ad  jle     loc_1800079CF
0x1800078b3  movzx   edi, ax
0x1800078b6  or      edi, 80070000h
0x1800078bc  jmp     loc_1800079CF
0x1800078c1  mov     qword ptr [rsp+4A0h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800078ca  xor     r9d, r9d; dwFileOffsetLow
0x1800078cd  xor     r8d, r8d; dwFileOffsetHigh
0x1800078d0  lea     edx, [r9+6]; dwDesiredAccess
0x1800078d4  mov     rcx, r15; hFileMappingObject
0x1800078d7  call    cs:__imp_MapViewOfFile
0x1800078dd  mov     rbx, rax
0x1800078e0  test    rax, rax
0x1800078e3  jz      short loc_1800078A1
0x1800078e5  xor     eax, eax
0x1800078e7  mov     [rbx], ax
0x1800078ea  mov     [rbx+618h], esi
0x1800078f0  mov     rax, [rsp+4A0h+var_460]
0x1800078f5  movaps  xmm0, xmmword ptr [rax]
0x1800078f8  movdqu  xmmword ptr [rbx+61Ch], xmm0
0x180007900  mov     rax, [rsp+4A0h+var_458]
0x180007905  movaps  xmm1, xmmword ptr [rax]
0x180007908  movdqu  xmmword ptr [rbx+62Ch], xmm1
0x180007910  mov     eax, [rbp+3A0h+arg_20]
0x180007916  mov     [rbx+63Ch], eax
0x18000791c  mov     [rbx+640h], edi
0x180007922  mov     [rbx+644h], r14d
0x180007929  xor     esi, esi
0x18000792b  mov     [rbx+648h], esi
0x180007931  mov     r8, r13; unsigned __int16 **
0x180007934  mov     edx, edi; unsigned int
0x180007936  mov     rcx, rbx; struct SPR_Data *
0x180007939  call    ?SetParams@SPR_Data@@SAJPEAU1@KPEAPEAG@Z; SPR_Data::SetParams(SPR_Data *,ulong,ushort * *)
0x18000793e  mov     edi, eax
0x180007940  test    eax, eax
0x180007942  js      short loc_1800079BB
0x180007944  lea     r8, aRundll32ExeCat; "RunDll32.exe catsrvut.dll,ManagedReques"...
0x18000794b  lea     r10d, [rsi+64h]
0x18000794f  mov     edx, r10d; unsigned __int64
0x180007952  lea     rcx, [rbp+3A0h+CommandLine]; unsigned __int16 *
0x180007956  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000795b  mov     edi, eax
0x18000795d  test    eax, eax
0x18000795f  js      short loc_1800079BB
0x180007961  lea     r8, [rbp+3A0h+Name]; unsigned __int16 *
0x180007965  mov     edx, r10d; unsigned __int64
0x180007968  lea     rcx, [rbp+3A0h+CommandLine]; unsigned __int16 *
0x18000796c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007971  mov     edi, eax
0x180007973  test    eax, eax
0x180007975  js      short loc_1800079BB
0x180007977  lea     rdx, [rbp+3A0h+CommandLine]; lpCommandLine
0x18000797b  lea     rcx, [rbp+3A0h+Buffer]; lpApplicationName
0x180007982  call    ?ImpersonatingCreateProcess@@YAJPEAG0H@Z; ImpersonatingCreateProcess(ushort *,ushort *,int)
0x180007987  mov     edi, eax
0x180007989  test    eax, eax
0x18000798b  js      short loc_1800079BB
0x18000798d  cmp     esi, r14d
0x180007990  jnb     short loc_1800079B9
0x180007992  mov     edx, esi; unsigned int
0x180007994  mov     rcx, rbx; struct SPR_Data *
0x180007997  call    ?GetParam@SPR_Data@@SAPEBGPEAU1@K@Z; SPR_Data::GetParam(SPR_Data *,ulong)
0x18000799c  mov     rcx, rax; psz
0x18000799f  call    cs:__imp_SysAllocString
0x1800079a5  mov     ecx, esi
0x1800079a7  mov     [r12+rcx*8], rax
0x1800079ab  test    rax, rax
0x1800079ae  jz      short loc_1800079B4
0x1800079b0  inc     esi
0x1800079b2  jmp     short loc_18000798D
0x1800079b4  mov     edi, 8007000Eh
0x1800079b9  xor     esi, esi
0x1800079bb  mov     eax, [rbx+648h]
0x1800079c1  test    eax, eax
0x1800079c3  cmovs   edi, eax
0x1800079c6  mov     rcx, rbx; lpBaseAddress
0x1800079c9  call    cs:__imp_UnmapViewOfFile
0x1800079cf  mov     rcx, r15; hObject
0x1800079d2  call    cs:__imp_CloseHandle
0x1800079d8  mov     rcx, [rsp+4A0h+TokenHandle]; hObject
0x1800079dd  test    rcx, rcx
0x1800079e0  jz      short loc_1800079E8
0x1800079e2  call    cs:__imp_CloseHandle
0x1800079e8  test    edi, edi
0x1800079ea  jns     short loc_180007A0C
0x1800079ec  test    r14d, r14d
0x1800079ef  jz      short loc_180007A0C
0x1800079f1  mov     ebx, esi
0x1800079f3  mov     rcx, [r12+rbx*8]; bstrString
0x1800079f7  call    cs:__imp_SysFreeString
0x1800079fd  mov     qword ptr [r12+rbx*8], 0
0x180007a05  inc     esi
0x180007a07  cmp     esi, r14d
0x180007a0a  jb      short loc_1800079F1
0x180007a0c  lea     rcx, [rbp+3A0h+pSecurityDescriptor]; this
0x180007a10  call    ??1CSystemAndUserDescriptor@@QEAA@XZ; CSystemAndUserDescriptor::~CSystemAndUserDescriptor(void)
0x180007a15  nop
0x180007a16  lea     rcx, [rsp+4A0h+ppInterface]; this
0x180007a1b  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x180007a20  mov     eax, edi
0x180007a22  mov     rcx, [rbp+3A0h+var_50]
0x180007a29  xor     rcx, rsp; StackCookie
0x180007a2c  call    __security_check_cookie
0x180007a31  add     rsp, 468h
0x180007a38  pop     r15
0x180007a3a  pop     r14
0x180007a3c  pop     r13
0x180007a3e  pop     r12
0x180007a40  pop     rdi
0x180007a41  pop     rsi
0x180007a42  pop     rbx
0x180007a43  pop     rbp
0x180007a44  retn
```
