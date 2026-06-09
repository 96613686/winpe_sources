# PlaliUpdateServiceMode(ushort const *)

- ea: `0x180132f38`
- end: `0x180133270`
- name: `?PlaliUpdateServiceMode@@YAKPEBG@Z`
- size: `824`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800b16b0`
- `0x18012ec18`
- `0x18012edd0`

## callees

- `0x18012f050`
- `0x18012f530`
- `0x180132f38`
- `0x18013ae9a`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133060`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180133060`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180133230`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18013323e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180133230`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18013323e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180133052`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180133052`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801330bc`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1801330bc`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180133160`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180133160`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801330da`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1801330da`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1801331e5`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1801331e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180132fba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180133087`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180132fba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180133087`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180132fa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180133076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801331fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180133214`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180132fa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180133076`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801331fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180133214`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133222`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133209`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180133222`

## pseudocode

```c
__int64 __fastcall PlaliUpdateServiceMode(const unsigned __int16 *a1)
{
  SC_HANDLE v2; // rsi
  int v3; // eax
  DWORD v4; // ebx
  SIZE_T v5; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r13
  SC_HANDLE v9; // r14
  struct _QUERY_SERVICE_CONFIGW *v10; // r15
  int v11; // r12d
  const unsigned __int16 *i; // rbx
  int InfoW; // eax
  __int64 v14; // rcx
  DWORD LastError; // edi
  HANDLE v16; // rax
  struct _QUERY_SERVICE_CONFIGW *v17; // rax
  SC_HANDLE v18; // rax
  BOOL v19; // eax
  HANDLE v20; // rax
  HANDLE v21; // rax
  size_t Size; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD Info[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 *v25; // [rsp+88h] [rbp-78h]
  _DWORD v26[72]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v27; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v28; // [rsp+1C0h] [rbp+C0h]

  v2 = 0;
  LODWORD(Size) = 0;
  memset_0(v26, 0, 0x118u);
  v3 = PlaliEnumCollectionsW(a1, (unsigned int *)&Size, 0);
  if ( v3 && v3 != -1073738814 )
    return 2;
  v5 = 2LL * (unsigned int)Size;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v5);
  v8 = v7;
  if ( !v7 )
    return 14;
  v9 = 0;
  v10 = 0;
  if ( (unsigned int)PlaliEnumCollectionsW(a1, (unsigned int *)&Size, v7) )
  {
    LastError = 2;
    goto LABEL_33;
  }
  v11 = 0;
  for ( i = v8; *i; i += v14 + 1 )
  {
    v26[0] = 1024;
    LODWORD(Size) = 280;
    InfoW = PlaliGetInfoW(i, a1, (unsigned int *)&Size, (struct _PDH_PLALI_INFO_W *)v26);
    v14 = -1;
    do
      ++v14;
    while ( i[v14] );
    if ( !InfoW && (v26[0] & 0x400) != 0 && v26[27] )
    {
      v11 = 1;
      break;
    }
  }
  v2 = OpenSCManagerW(a1, 0, 0x80000000);
  if ( v2 )
  {
    LODWORD(Size) = 4096;
    v16 = GetProcessHeap();
    v17 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(v16, 8u, 0x1000u);
    v10 = v17;
    if ( !v17 )
    {
      LastError = 14;
      goto LABEL_33;
    }
    memset_0(v17, 0, (unsigned int)Size);
    v18 = OpenServiceW(v2, L"SysmonLog", 0x13u);
    v9 = v18;
    if ( v18 && QueryServiceConfigW(v18, v10, Size, (LPDWORD)&Size) )
    {
      LastError = 0;
      if ( v11 )
      {
        v19 = v10->dwStartType == 3;
      }
      else
      {
        if ( v10->dwStartType != 2 )
          goto LABEL_33;
        v19 = 1;
      }
      if ( !v19 )
        goto LABEL_33;
      v25 = 0;
      memset(Info, 0, sizeof(Info));
      if ( ChangeServiceConfigW(v9, 0xFFFFFFFF, (v11 ^ 1) + 2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
      {
        v28 = 0;
        HIDWORD(Info[1]) = 0;
        v27 = 0;
        memset((char *)Info + 4, 0, 20);
        if ( v11 )
        {
          LODWORD(v27) = 1;
          DWORD2(v27) = 1;
          LODWORD(v28) = 1;
        }
        else
        {
          LODWORD(v27) = 0;
          DWORD2(v27) = 0;
          LODWORD(v28) = 0;
        }
        LODWORD(Info[0]) = 60;
        v25 = &v27;
        DWORD2(Info[1]) = 3;
        if ( ChangeServiceConfig2W(v9, 2u, Info) )
          goto LABEL_33;
      }
    }
  }
  LastError = GetLastError();
LABEL_33:
  v4 = LastError;
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v8);
  if ( v10 )
  {
    v21 = GetProcessHeap();
    HeapFree(v21, 0, v10);
  }
  if ( v9 )
    CloseServiceHandle(v9);
  if ( v2 )
    CloseServiceHandle(v2);
  return v4;
}

```

## disassembly

```asm
0x180132f38  push    rbp
0x180132f3a  push    rbx
0x180132f3b  push    rsi
0x180132f3c  push    rdi
0x180132f3d  push    r12
0x180132f3f  push    r13
0x180132f41  push    r14
0x180132f43  push    r15
0x180132f45  lea     rbp, [rsp-0D8h]
0x180132f4d  sub     rsp, 1D8h
0x180132f54  mov     rax, cs:__security_cookie
0x180132f5b  xor     rax, rsp
0x180132f5e  mov     [rbp+110h+var_48], rax
0x180132f65  mov     rdi, rcx
0x180132f68  xor     esi, esi
0x180132f6a  lea     rcx, [rbp+110h+var_180]; void *
0x180132f6e  mov     dword ptr [rsp+210h+Size], esi
0x180132f72  xor     edx, edx; Val
0x180132f74  mov     r8d, 118h; Size
0x180132f7a  call    memset_0
0x180132f7f  xor     r8d, r8d; unsigned __int16 *
0x180132f82  lea     rdx, [rsp+210h+Size]; unsigned int *
0x180132f87  mov     rcx, rdi; lpMachineName
0x180132f8a  call    ?PlaliEnumCollectionsW@@YAJPEBGPEAKPEAG@Z; PlaliEnumCollectionsW(ushort const *,ulong *,ushort *)
0x180132f8f  test    eax, eax
0x180132f91  jz      short loc_180132FA2
0x180132f93  cmp     eax, 0C0000BC2h
0x180132f98  jz      short loc_180132FA2
0x180132f9a  lea     ebx, [rsi+2]
0x180132f9d  jmp     loc_18013324B
0x180132fa2  mov     ebx, dword ptr [rsp+210h+Size]
0x180132fa6  add     rbx, rbx
0x180132fa9  call    cs:__imp_GetProcessHeap
0x180132faf  mov     r8, rbx; dwBytes
0x180132fb2  mov     edx, 8; dwFlags
0x180132fb7  mov     rcx, rax; hHeap
0x180132fba  call    cs:__imp_HeapAlloc
0x180132fc0  mov     r13, rax
0x180132fc3  test    rax, rax
0x180132fc6  jz      loc_180133246
0x180132fcc  mov     r8, rax; unsigned __int16 *
0x180132fcf  lea     rdx, [rsp+210h+Size]; unsigned int *
0x180132fd4  mov     rcx, rdi; lpMachineName
0x180132fd7  mov     r14, rsi
0x180132fda  mov     r15, rsi
0x180132fdd  call    ?PlaliEnumCollectionsW@@YAJPEBGPEAKPEAG@Z; PlaliEnumCollectionsW(ushort const *,ulong *,ushort *)
0x180132fe2  test    eax, eax
0x180132fe4  jnz     loc_1801331F4
0x180132fea  mov     r12d, esi
0x180132fed  mov     rbx, r13
0x180132ff0  cmp     [rbx], si
0x180132ff3  jz      short loc_180133047
0x180132ff5  lea     r9, [rbp+110h+var_180]; struct _PDH_PLALI_INFO_W *
0x180132ff9  mov     [rbp+110h+var_180], 400h
0x180133000  lea     r8, [rsp+210h+Size]; unsigned int *
0x180133005  mov     dword ptr [rsp+210h+Size], 118h
0x18013300d  mov     rdx, rdi; unsigned __int16 *
0x180133010  mov     rcx, rbx; unsigned __int16 *
0x180133013  call    ?PlaliGetInfoW@@YAJPEBG0PEAKPEAU_PDH_PLALI_INFO_W@@@Z; PlaliGetInfoW(ushort const *,ushort const *,ulong *,_PDH_PLALI_INFO_W *)
0x180133018  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18013301c  inc     rcx
0x18013301f  cmp     [rbx+rcx*2], si
0x180133023  jnz     short loc_18013301C
0x180133025  test    eax, eax
0x180133027  jnz     short loc_180133037
0x180133029  test    [rbp+110h+var_180], 400h
0x180133030  jz      short loc_180133037
0x180133032  cmp     [rbp+110h+var_114], esi
0x180133035  jnz     short loc_180133041
0x180133037  lea     rbx, [rbx+rcx*2]
0x18013303b  add     rbx, 2
0x18013303f  jmp     short loc_180132FF0
0x180133041  mov     r12d, 1
0x180133047  xor     edx, edx; lpDatabaseName
0x180133049  mov     r8d, 80000000h; dwDesiredAccess
0x18013304f  mov     rcx, rdi; lpMachineName
0x180133052  call    cs:__imp_OpenSCManagerW
0x180133058  mov     rsi, rax
0x18013305b  test    rax, rax
0x18013305e  jnz     short loc_18013306D
0x180133060  call    cs:__imp_GetLastError
0x180133066  mov     edi, eax
0x180133068  jmp     loc_1801331F9
0x18013306d  mov     ebx, 1000h
0x180133072  mov     dword ptr [rsp+210h+Size], ebx
0x180133076  call    cs:__imp_GetProcessHeap
0x18013307c  mov     r8d, ebx; dwBytes
0x18013307f  mov     edx, 8; dwFlags
0x180133084  mov     rcx, rax; hHeap
0x180133087  call    cs:__imp_HeapAlloc
0x18013308d  mov     r15, rax
0x180133090  test    rax, rax
0x180133093  jnz     short loc_18013309D
0x180133095  lea     edi, [rax+0Eh]
0x180133098  jmp     loc_1801331F9
0x18013309d  mov     r8d, dword ptr [rsp+210h+Size]; Size
0x1801330a2  xor     edx, edx; Val
0x1801330a4  mov     rcx, r15; void *
0x1801330a7  call    memset_0
0x1801330ac  mov     r8d, 13h; dwDesiredAccess
0x1801330b2  lea     rdx, aSysmonlog_0; "SysmonLog"
0x1801330b9  mov     rcx, rsi; hSCManager
0x1801330bc  call    cs:__imp_OpenServiceW
0x1801330c2  mov     r14, rax
0x1801330c5  test    rax, rax
0x1801330c8  jz      short loc_180133060
0x1801330ca  mov     r8d, dword ptr [rsp+210h+Size]; cbBufSize
0x1801330cf  lea     r9, [rsp+210h+Size]; pcbBytesNeeded
0x1801330d4  mov     rdx, r15; lpServiceConfig
0x1801330d7  mov     rcx, rax; hService
0x1801330da  call    cs:__imp_QueryServiceConfigW
0x1801330e0  xor     ecx, ecx
0x1801330e2  test    eax, eax
0x1801330e4  jz      loc_180133060
0x1801330ea  lea     ebx, [rcx+2]
0x1801330ed  mov     edi, ecx
0x1801330ef  test    r12d, r12d
0x1801330f2  jz      short loc_180133100
0x1801330f4  cmp     dword ptr [r15+4], 3
0x1801330f9  mov     eax, ecx
0x1801330fb  setz    al
0x1801330fe  jmp     short loc_18013310F
0x180133100  cmp     [r15+4], ebx
0x180133104  jnz     loc_1801331F9
0x18013310a  mov     eax, 1
0x18013310f  test    eax, eax
0x180133111  jz      loc_1801331F9
0x180133117  mov     [rsp+210h+lpDisplayName], rcx; lpDisplayName
0x18013311c  xorps   xmm0, xmm0
0x18013311f  mov     [rsp+210h+lpPassword], rcx; lpPassword
0x180133124  mov     r8d, r12d
0x180133127  mov     [rsp+210h+lpServiceStartName], rcx; lpServiceStartName
0x18013312c  xor     r8d, 1
0x180133130  mov     [rsp+210h+lpDependencies], rcx; lpDependencies
0x180133135  or      edx, 0FFFFFFFFh; dwServiceType
0x180133138  mov     [rsp+210h+lpdwTagId], rcx; lpdwTagId
0x18013313d  xor     eax, eax
0x18013313f  mov     [rsp+210h+lpLoadOrderGroup], rcx; lpLoadOrderGroup
0x180133144  add     r8d, ebx; dwStartType
0x180133147  mov     [rsp+210h+lpBinaryPathName], rcx; lpBinaryPathName
0x18013314c  mov     r9d, edx; dwErrorControl
0x18013314f  mov     rcx, r14; hService
0x180133152  mov     [rbp+110h+var_188], rax
0x180133156  movups  [rsp+210h+Info], xmm0
0x18013315b  movups  [rsp+210h+var_198], xmm0
0x180133160  call    cs:__imp_ChangeServiceConfigW
0x180133166  xor     ecx, ecx
0x180133168  test    eax, eax
0x18013316a  jz      loc_180133060
0x180133170  xor     eax, eax
0x180133172  mov     dword ptr [rsp+210h+var_198+4], ecx
0x180133176  mov     [rbp+110h+var_50], rax
0x18013317d  xorps   xmm0, xmm0
0x180133180  mov     dword ptr [rbp+110h+var_198+0Ch], ecx
0x180133183  xorps   xmm1, xmm1
0x180133186  movups  [rbp+110h+var_60], xmm0
0x18013318d  movdqu  [rsp+210h+Info+4], xmm1
0x180133193  test    r12d, r12d
0x180133196  jz      short loc_1801331AF
0x180133198  lea     eax, [rcx+1]
0x18013319b  mov     dword ptr [rbp+110h+var_60], eax
0x1801331a1  mov     dword ptr [rbp+110h+var_60+8], eax
0x1801331a7  mov     dword ptr [rbp+110h+var_50], eax
0x1801331ad  jmp     short loc_1801331C1
0x1801331af  mov     dword ptr [rbp+110h+var_60], ecx
0x1801331b5  mov     dword ptr [rbp+110h+var_60+8], ecx
0x1801331bb  mov     dword ptr [rbp+110h+var_50], ecx
0x1801331c1  lea     rax, [rbp+110h+var_60]
0x1801331c8  mov     dword ptr [rsp+210h+Info], 3Ch ; '<'
0x1801331d0  lea     r8, [rsp+210h+Info]; lpInfo
0x1801331d5  mov     [rbp+110h+var_188], rax
0x1801331d9  mov     edx, ebx; dwInfoLevel
0x1801331db  mov     dword ptr [rbp+110h+var_198+8], 3
0x1801331e2  mov     rcx, r14; hService
0x1801331e5  call    cs:__imp_ChangeServiceConfig2W
0x1801331eb  test    eax, eax
0x1801331ed  jnz     short loc_1801331F9
0x1801331ef  jmp     loc_180133060
0x1801331f4  mov     edi, 2
0x1801331f9  mov     ebx, edi
0x1801331fb  call    cs:__imp_GetProcessHeap
0x180133201  mov     r8, r13; lpMem
0x180133204  xor     edx, edx; dwFlags
0x180133206  mov     rcx, rax; hHeap
0x180133209  call    cs:__imp_HeapFree
0x18013320f  test    r15, r15
0x180133212  jz      short loc_180133228
0x180133214  call    cs:__imp_GetProcessHeap
0x18013321a  mov     r8, r15; lpMem
0x18013321d  xor     edx, edx; dwFlags
0x18013321f  mov     rcx, rax; hHeap
0x180133222  call    cs:__imp_HeapFree
0x180133228  test    r14, r14
0x18013322b  jz      short loc_180133236
0x18013322d  mov     rcx, r14; hSCObject
0x180133230  call    cs:__imp_CloseServiceHandle
0x180133236  test    rsi, rsi
0x180133239  jz      short loc_18013324B
0x18013323b  mov     rcx, rsi; hSCObject
0x18013323e  call    cs:__imp_CloseServiceHandle
0x180133244  jmp     short loc_18013324B
0x180133246  mov     ebx, 0Eh
0x18013324b  mov     eax, ebx
0x18013324d  mov     rcx, [rbp+110h+var_48]
0x180133254  xor     rcx, rsp; StackCookie
0x180133257  call    __security_check_cookie
0x18013325c  add     rsp, 1D8h
0x180133263  pop     r15
0x180133265  pop     r14
0x180133267  pop     r13
0x180133269  pop     r12
0x18013326b  pop     rdi
0x18013326c  pop     rsi
0x18013326d  pop     rbx
0x18013326e  pop     rbp
0x18013326f  retn
```
