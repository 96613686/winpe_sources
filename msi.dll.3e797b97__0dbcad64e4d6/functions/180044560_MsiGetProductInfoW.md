# MsiGetProductInfoW

- ea: `0x180044560`
- end: `0x18004494e`
- name: `MsiGetProductInfoW`
- size: `1006`
- prototype: `UINT __stdcall(LPCWSTR szProduct, LPCWSTR szAttribute, LPWSTR lpValueBuf, LPDWORD pcchValueBuf)`
- caller_count: `8`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180006970`
- `0x180042810`
- `0x180056140`
- `0x180087e68`
- `0x180125df8`
- `0x180140058`
- `0x180191a00`
- `0x1801a51f0`

## callees

- `0x18000c4bc`
- `0x18000f930`
- `0x180044560`
- `0x180044960`
- `0x1800459c0`
- `0x180045ba4`
- `0x18004a07c`
- `0x18015cbac`
- `0x180265240`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180044886`
- `ADVAPI32!SetThreadToken` at `0x1800448e8`
- `ADVAPI32!SetThreadToken` at `0x180044886`
- `ADVAPI32!SetThreadToken` at `0x1800448e8`
- `ADVAPI32!OpenThreadToken` at `0x1800447e3`
- `ADVAPI32!OpenThreadToken` at `0x1800447e3`
- `ADVAPI32!OpenProcessToken` at `0x18004481a`
- `ADVAPI32!OpenProcessToken` at `0x18004481a`
- `KERNEL32!CloseHandle` at `0x18004486c`
- `KERNEL32!CloseHandle` at `0x1800448a0`
- `KERNEL32!CloseHandle` at `0x18004486c`
- `KERNEL32!CloseHandle` at `0x1800448a0`
- `KERNEL32!LeaveCriticalSection` at `0x180044760`
- `KERNEL32!LeaveCriticalSection` at `0x180044760`
- `KERNEL32!EnterCriticalSection` at `0x18004474b`
- `KERNEL32!EnterCriticalSection` at `0x18004474b`
- `KERNEL32!GetCurrentThread` at `0x1800447c6`
- `KERNEL32!GetCurrentThread` at `0x1800447c6`
- `KERNEL32!GetCurrentProcess` at `0x180044801`
- `KERNEL32!GetCurrentProcess` at `0x180044801`
- `KERNEL32!lstrlenW` at `0x1800445dd`
- `KERNEL32!lstrlenW` at `0x1800445dd`
- `KERNEL32!GlobalFree` at `0x180044610`
- `KERNEL32!GlobalFree` at `0x180044632`
- `KERNEL32!GlobalFree` at `0x1800446f4`
- `KERNEL32!GlobalFree` at `0x1800447b0`
- `KERNEL32!GlobalFree` at `0x180044610`
- `KERNEL32!GlobalFree` at `0x180044632`
- `KERNEL32!GlobalFree` at `0x1800446f4`
- `KERNEL32!GlobalFree` at `0x1800447b0`
- `KERNEL32!TlsSetValue` at `0x18004477f`
- `KERNEL32!TlsSetValue` at `0x18004477f`

## pseudocode

```c
UINT __stdcall MsiGetProductInfoW(LPCWSTR szProduct, LPCWSTR szAttribute, LPWSTR lpValueBuf, LPDWORD pcchValueBuf)
{
  int v8; // ecx
  __int64 v9; // rax
  unsigned int v11; // r10d
  __int64 *v12; // r8
  _WORD *v13; // r9
  unsigned int v14; // edx
  __int64 v15; // rax
  UINT Info; // edi
  int v17; // eax
  DWORD v18; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v21; // ebx
  int v22; // [rsp+38h] [rbp-C8h]
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpTlsValue; // [rsp+70h] [rbp-90h] BYREF
  char v26; // [rsp+78h] [rbp-88h]
  HGLOBAL hMem; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  _BYTE v29[80]; // [rsp+90h] [rbp-70h] BYREF
  HGLOBAL v30; // [rsp+E0h] [rbp-20h]
  int v31; // [rsp+E8h] [rbp-18h]
  _BYTE v32[80]; // [rsp+F0h] [rbp-10h] BYREF

  CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall((CForbidTokenChangesDuringCall *)&lpTlsValue);
  v31 = 33;
  v30 = v32;
  if ( !szProduct || !szAttribute || lpValueBuf && !pcchValueBuf )
  {
LABEL_13:
    CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(&lpTlsValue);
    return 87;
  }
  v28 = 39;
  hMem = v29;
  if ( lstrlenW(szProduct) != 38 )
  {
    if ( !DecomposeDescriptor(szProduct, 1, (unsigned __int16 *)hMem, 0, 0, 0, 0, 0) )
    {
LABEL_8:
      if ( v28 > 39 )
        GlobalFree(hMem);
      hMem = v29;
      v28 = 39;
      if ( v31 > 33 )
        GlobalFree(v30);
      v31 = 33;
      v30 = v32;
      goto LABEL_13;
    }
    szProduct = (LPCWSTR)hMem;
  }
  v8 = 0;
  while ( v8 < 38 )
  {
    v9 = v8++;
    if ( !szProduct[v9] )
      goto LABEL_8;
  }
  if ( *szProduct != 123 || szProduct[37] != 125 )
    goto LABEL_8;
  v11 = v31;
  v12 = qword_1802796B8;
  v13 = v30;
  v14 = 0;
  while ( v12 < &qword_1802796D8 )
  {
    if ( v14 >= v11 )
      goto LABEL_8;
    v15 = *(unsigned __int8 *)v12;
    v12 = (__int64 *)((char *)v12 + 1);
    *v13++ = szProduct[v15];
    ++v14;
  }
  if ( v14 >= v11 )
    goto LABEL_8;
  *v13 = 0;
  LOBYTE(v22) = 0;
  Info = GetInfo(v30, 0, 3, 1, szAttribute, lpValueBuf, pcchValueBuf, v22, -1);
  if ( v28 > 39 )
    GlobalFree(hMem);
  hMem = v29;
  v28 = 39;
  if ( v31 > 33 )
    GlobalFree(v30);
  v31 = 33;
  v30 = v32;
  v17 = dword_180310D00;
  if ( dword_180310D00 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v21 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180310D00 = v21;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v17 = dword_180310D00;
  }
  if ( v17 == 1 && g_scServerContext != 2 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v18 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v26 )
    {
      if ( v18 != -1 )
        TlsSetValue(v18, lpTlsValue);
    }
  }
  return Info;
}

```

## disassembly

```asm
0x180044560  push    rbp
0x180044562  push    rbx
0x180044563  push    rsi
0x180044564  push    rdi
0x180044565  push    r12
0x180044567  push    r14
0x180044569  push    r15
0x18004456b  lea     rbp, [rsp-50h]
0x180044570  sub     rsp, 150h
0x180044577  mov     rax, cs:__security_cookie
0x18004457e  xor     rax, rsp
0x180044581  mov     [rbp+80h+var_40], rax
0x180044585  mov     rbx, rcx
0x180044588  mov     r14, r9
0x18004458b  lea     rcx, [rsp+180h+lpTlsValue]; this
0x180044590  mov     rsi, r8
0x180044593  mov     rdi, rdx
0x180044596  call    ??0CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall(void)
0x18004459b  xor     r15d, r15d
0x18004459e  mov     [rbp+80h+var_98], 21h ; '!'
0x1800445a5  lea     rax, [rbp+80h+var_90]
0x1800445a9  mov     [rbp+80h+var_A0], rax
0x1800445ad  test    rbx, rbx
0x1800445b0  jz      loc_18004464D
0x1800445b6  test    rdi, rdi
0x1800445b9  jz      loc_18004464D
0x1800445bf  test    rsi, rsi
0x1800445c2  jnz     loc_18004484C
0x1800445c8  lea     rax, [rbp+80h+var_F0]
0x1800445cc  mov     r12d, 27h ; '''
0x1800445d2  mov     rcx, rbx; lpString
0x1800445d5  mov     [rbp+80h+var_F8], r12d
0x1800445d9  mov     [rbp+80h+hMem], rax
0x1800445dd  call    cs:__imp_lstrlenW
0x1800445e4  nop     dword ptr [rax+rax+00h]
0x1800445e9  cmp     eax, 26h ; '&'
0x1800445ec  jnz     loc_1800448AE
0x1800445f2  mov     ecx, r15d
0x1800445f5  cmp     ecx, 26h ; '&'
0x1800445f8  jge     short loc_180044661
0x1800445fa  movsxd  rax, ecx
0x1800445fd  inc     ecx
0x1800445ff  cmp     [rbx+rax*2], r15w
0x180044604  jnz     short loc_1800445F5
0x180044606  cmp     [rbp+80h+var_F8], r12d
0x18004460a  jle     short loc_18004461C
0x18004460c  mov     rcx, [rbp+80h+hMem]; hMem
0x180044610  call    cs:__imp_GlobalFree
0x180044617  nop     dword ptr [rax+rax+00h]
0x18004461c  cmp     [rbp+80h+var_98], 21h ; '!'
0x180044620  lea     rax, [rbp+80h+var_F0]
0x180044624  mov     [rbp+80h+hMem], rax
0x180044628  mov     [rbp+80h+var_F8], r12d
0x18004462c  jle     short loc_18004463E
0x18004462e  mov     rcx, [rbp+80h+var_A0]; hMem
0x180044632  call    cs:__imp_GlobalFree
0x180044639  nop     dword ptr [rax+rax+00h]
0x18004463e  lea     rax, [rbp+80h+var_90]
0x180044642  mov     [rbp+80h+var_98], 21h ; '!'
0x180044649  mov     [rbp+80h+var_A0], rax
0x18004464d  lea     rcx, [rsp+180h+lpTlsValue]; this
0x180044652  call    ??1CForbidTokenChangesDuringCall@@QEAA@XZ; CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)
0x180044657  mov     eax, 57h ; 'W'
0x18004465c  jmp     loc_18004478D
0x180044661  cmp     word ptr [rbx], 7Bh ; '{'
0x180044665  jnz     short loc_180044606
0x180044667  cmp     word ptr [rbx+4Ah], 7Dh ; '}'
0x18004466c  jnz     short loc_180044606
0x18004466e  mov     r10d, [rbp+80h+var_98]
0x180044672  lea     r8, qword_1802796B8
0x180044679  mov     r9, [rbp+80h+var_A0]
0x18004467d  mov     edx, r15d
0x180044680  lea     rax, qword_1802796D8
0x180044687  cmp     r8, rax
0x18004468a  jnb     short loc_1800446AC
0x18004468c  cmp     edx, r10d
0x18004468f  jnb     loc_180044606
0x180044695  movzx   eax, byte ptr [r8]
0x180044699  inc     r8
0x18004469c  movzx   ecx, word ptr [rbx+rax*2]
0x1800446a0  mov     [r9], cx
0x1800446a4  add     r9, 2
0x1800446a8  inc     edx
0x1800446aa  jmp     short loc_180044680
0x1800446ac  cmp     edx, r10d
0x1800446af  jnb     loc_180044606
0x1800446b5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800446b9  mov     [r9], r15w
0x1800446bd  mov     rcx, [rbp+80h+var_A0]
0x1800446c1  xor     edx, edx
0x1800446c3  mov     dword ptr [rsp+180h+var_140], ebx
0x1800446c7  mov     byte ptr [rsp+180h+var_148], r15b
0x1800446cc  mov     [rsp+180h+var_150], r14
0x1800446d1  lea     r9d, [rbx+2]
0x1800446d5  mov     [rsp+180h+var_158], rsi
0x1800446da  lea     r8d, [rbx+4]
0x1800446de  mov     [rsp+180h+var_160], rdi
0x1800446e3  call    ?GetInfo@@YAIPEBG0W4iaaAppAssignment@@W4ptPropertyType@@0PEAGPEAK_NW4tagINSTALLSTATE@@@Z; GetInfo(ushort const *,ushort const *,iaaAppAssignment,ptPropertyType,ushort const *,ushort *,ulong *,bool,tagINSTALLSTATE)
0x1800446e8  mov     edi, eax
0x1800446ea  cmp     [rbp+80h+var_F8], r12d
0x1800446ee  jle     short loc_180044700
0x1800446f0  mov     rcx, [rbp+80h+hMem]; hMem
0x1800446f4  call    cs:__imp_GlobalFree
0x1800446fb  nop     dword ptr [rax+rax+00h]
0x180044700  cmp     [rbp+80h+var_98], 21h ; '!'
0x180044704  lea     rax, [rbp+80h+var_F0]
0x180044708  mov     [rbp+80h+hMem], rax
0x18004470c  mov     [rbp+80h+var_F8], r12d
0x180044710  jg      loc_1800447AC
0x180044716  lea     rax, [rbp+80h+var_90]
0x18004471a  mov     [rbp+80h+var_98], 21h ; '!'
0x180044721  mov     [rbp+80h+var_A0], rax
0x180044725  mov     eax, cs:dword_180310D00
0x18004472b  cmp     eax, ebx
0x18004472d  jz      loc_1800447C1
0x180044733  cmp     eax, 1
0x180044736  jnz     short loc_18004478B
0x180044738  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004473f  jz      short loc_18004478B
0x180044741  lea     rsi, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csImpersonationLock
0x180044748  mov     rcx, rsi; lpCriticalSection
0x18004474b  call    cs:__imp_EnterCriticalSection
0x180044752  nop     dword ptr [rax+rax+00h]
0x180044757  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18004475d  mov     rcx, rsi; lpCriticalSection
0x180044760  call    cs:__imp_LeaveCriticalSection
0x180044767  nop     dword ptr [rax+rax+00h]
0x18004476c  cmp     [rsp+180h+var_108], r15b
0x180044771  jz      short loc_18004478B
0x180044773  cmp     ebx, 0FFFFFFFFh
0x180044776  jz      short loc_18004478B
0x180044778  mov     rdx, [rsp+180h+lpTlsValue]; lpTlsValue
0x18004477d  mov     ecx, ebx; dwTlsIndex
0x18004477f  call    cs:__imp_TlsSetValue
0x180044786  nop     dword ptr [rax+rax+00h]
0x18004478b  mov     eax, edi
0x18004478d  mov     rcx, [rbp+80h+var_40]
0x180044791  xor     rcx, rsp; StackCookie
0x180044794  call    __security_check_cookie
0x180044799  add     rsp, 150h
0x1800447a0  pop     r15
0x1800447a2  pop     r14
0x1800447a4  pop     r12
0x1800447a6  pop     rdi
0x1800447a7  pop     rsi
0x1800447a8  pop     rbx
0x1800447a9  pop     rbp
0x1800447aa  retn
0x1800447ac  mov     rcx, [rbp+80h+var_A0]; hMem
0x1800447b0  call    cs:__imp_GlobalFree
0x1800447b7  nop     dword ptr [rax+rax+00h]
0x1800447bc  jmp     loc_180044716
0x1800447c1  mov     [rsp+180h+TokenHandle], rbx
0x1800447c6  call    cs:__imp_GetCurrentThread
0x1800447cd  nop     dword ptr [rax+rax+00h]
0x1800447d2  mov     edx, 4; DesiredAccess
0x1800447d7  lea     r9, [rsp+180h+TokenHandle]; TokenHandle
0x1800447dc  mov     rcx, rax; ThreadHandle
0x1800447df  lea     r8d, [rdx-3]; OpenAsSelf
0x1800447e3  call    cs:__imp_OpenThreadToken
0x1800447ea  nop     dword ptr [rax+rax+00h]
0x1800447ef  test    eax, eax
0x1800447f1  jnz     loc_1800448E4
0x1800447f7  mov     [rsp+180h+TokenHandle], rbx
0x1800447fc  mov     [rsp+180h+hObject], r15
0x180044801  call    cs:__imp_GetCurrentProcess
0x180044808  nop     dword ptr [rax+rax+00h]
0x18004480d  lea     r8, [rsp+180h+hObject]; TokenHandle
0x180044812  mov     edx, 8; DesiredAccess
0x180044817  mov     rcx, rax; ProcessHandle
0x18004481a  call    cs:__imp_OpenProcessToken
0x180044821  nop     dword ptr [rax+rax+00h]
0x180044826  test    eax, eax
0x180044828  jnz     short loc_18004485A
0x18004482a  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180044831  jnz     loc_180044906
0x180044837  mov     rdx, [rsp+180h+TokenHandle]; Token
0x18004483c  cmp     rdx, rbx
0x18004483f  jnz     short loc_180044884
0x180044841  mov     eax, cs:dword_180310D00
0x180044847  jmp     loc_180044733
0x18004484c  test    r14, r14
0x18004484f  jnz     loc_1800445C8
0x180044855  jmp     loc_18004464D
0x18004485a  mov     rcx, [rsp+180h+hObject]; void *
0x18004485f  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x180044864  mov     rcx, [rsp+180h+hObject]; hObject
0x180044869  movzx   ebx, al
0x18004486c  call    cs:__imp_CloseHandle
0x180044873  nop     dword ptr [rax+rax+00h]
0x180044878  mov     cs:dword_180310D00, ebx
0x18004487e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180044882  jmp     short loc_180044837
0x180044884  xor     ecx, ecx; Thread
0x180044886  call    cs:__imp_SetThreadToken
0x18004488d  nop     dword ptr [rax+rax+00h]
0x180044892  test    eax, eax
0x180044894  jnz     short loc_18004489B
0x180044896  call    ExitProcessIfNotClient
0x18004489b  mov     rcx, [rsp+180h+TokenHandle]; hObject
0x1800448a0  call    cs:__imp_CloseHandle
0x1800448a7  nop     dword ptr [rax+rax+00h]
0x1800448ac  jmp     short loc_180044841
0x1800448ae  mov     r8, [rbp+80h+hMem]; unsigned __int16 *
0x1800448b2  xor     r9d, r9d; unsigned __int16 *
0x1800448b5  mov     [rsp+180h+var_148], r15; bool *
0x1800448ba  mov     dl, 1; bool
0x1800448bc  mov     [rsp+180h+var_150], r15; unsigned int *
0x1800448c1  mov     rcx, rbx; unsigned __int16 *
0x1800448c4  mov     [rsp+180h+var_158], r15; unsigned int *
0x1800448c9  mov     [rsp+180h+var_160], r15; unsigned __int16 *
0x1800448ce  call    ?DecomposeDescriptor@@YAHPEBG_NPEAG22PEAK3PEA_N@Z; DecomposeDescriptor(ushort const *,bool,ushort *,ushort *,ushort *,ulong *,ulong *,bool *)
0x1800448d3  test    eax, eax
0x1800448d5  jz      loc_180044606
0x1800448db  mov     rbx, [rbp+80h+hMem]
0x1800448df  jmp     loc_1800445F2
0x1800448e4  xor     edx, edx; Token
0x1800448e6  xor     ecx, ecx; Thread
0x1800448e8  call    cs:__imp_SetThreadToken
0x1800448ef  nop     dword ptr [rax+rax+00h]
0x1800448f4  test    eax, eax
0x1800448f6  jnz     loc_1800447FC
0x1800448fc  call    ExitProcessIfNotClient
0x180044901  jmp     loc_1800447FC
0x180044906  mov     [rsp+180h+var_128], r15; void *
0x18004490b  lea     rax, aNull; "(NULL)"
0x180044912  mov     [rsp+180h+var_130], r15d; unsigned int
0x180044917  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x18004491e  mov     [rsp+180h+var_138], rax; unsigned __int16 *
0x180044923  xor     edx, edx; unsigned __int16
0x180044925  mov     [rsp+180h+var_140], rax; unsigned __int16 *
0x18004492a  xor     r8d, r8d; int
0x18004492d  mov     [rsp+180h+var_148], rax; unsigned __int16 *
0x180044932  mov     [rsp+180h+var_150], rax; unsigned __int16 *
0x180044937  mov     [rsp+180h+var_158], rax; unsigned __int16 *
0x18004493c  lea     ecx, [rdx+9]; int
0x18004493f  mov     [rsp+180h+var_160], rax; unsigned __int16 *
0x180044944  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180044949  jmp     loc_180044837
```
