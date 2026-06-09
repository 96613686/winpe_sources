# CSteelhead::HrEnsureRouterManager(ROUTER_MANAGER_INFO const &)

- ea: `0x18003628c`
- end: `0x180036436`
- name: `?HrEnsureRouterManager@CSteelhead@@IEAAJAEBUROUTER_MANAGER_INFO@@@Z`
- size: `426`
- prototype: `__int64 __fastcall(void **this, const struct ROUTER_MANAGER_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x180036158`

## callees

- `0x180023040`
- `0x180027da0`
- `0x180028500`
- `0x18003628c`
- `0x1800364f4`
- `0x180053010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180036412`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003641c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036412`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003641c`
- `rtutils!TracePrintfW` at `0x180036329`
- `rtutils!TracePrintfW` at `0x180036346`
- `rtutils!TracePrintfW` at `0x180036408`
- `rtutils!TracePrintfW` at `0x180036329`
- `rtutils!TracePrintfW` at `0x180036346`
- `rtutils!TracePrintfW` at `0x180036408`

## string_xrefs

- `0x1800363f7`: `HrMprConfigTransportCreate`
- `0x180036318`: `HrMprConfigTransportGetInfo`

## pseudocode

```c
__int64 __fastcall CSteelhead::HrEnsureRouterManager(void **this, const struct ROUTER_MANAGER_INFO *a2)
{
  unsigned int v3; // edx
  int Handle; // eax
  unsigned int v6; // ebx
  void *v7; // rcx
  unsigned int v8; // edi
  signed int Info; // eax
  void (__fastcall *v11)(LPBYTE *, BYTE **); // rax
  DWORD v12; // ecx
  DWORD v13; // edx
  signed int v14; // eax
  BYTE *dwGlobalInfoSize; // [rsp+80h] [rbp+30h] BYREF
  LPBYTE ppGlobalInfo; // [rsp+88h] [rbp+38h] BYREF
  HANDLE hRouterTransport; // [rsp+90h] [rbp+40h] BYREF

  ppGlobalInfo = 0;
  v3 = *(_DWORD *)a2;
  hRouterTransport = 0;
  Handle = HrMprConfigTransportGetHandle(this[13], v3, &hRouterTransport);
  v6 = Handle;
  if ( Handle == -2147023994 )
    goto LABEL_13;
  if ( Handle >= 0 )
  {
    v7 = this[13];
    v8 = 0;
    LODWORD(dwGlobalInfoSize) = 0;
    Info = MprConfigTransportGetInfo(v7, hRouterTransport, &ppGlobalInfo, (LPDWORD)&dwGlobalInfoSize, 0, 0, 0);
    v6 = Info;
    if ( Info )
    {
      if ( Info > 0 )
        v6 = (unsigned __int16)Info | 0x80070000;
      if ( (v6 & 0x80000000) != 0 )
      {
        TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrMprConfigTransportGetInfo", v6);
        goto LABEL_8;
      }
      v8 = v6;
    }
    if ( ppGlobalInfo )
    {
      v6 = v8;
      MprConfigBufferFree(ppGlobalInfo);
      goto LABEL_25;
    }
LABEL_13:
    v11 = (void (__fastcall *)(LPBYTE *, BYTE **))*((_QWORD *)a2 + 4);
    dwGlobalInfoSize = 0;
    v11(&ppGlobalInfo, &dwGlobalInfoSize);
    if ( dwGlobalInfoSize )
      v12 = *((_DWORD *)dwGlobalInfoSize + 1);
    else
      v12 = 0;
    if ( ppGlobalInfo )
      v13 = *((_DWORD *)ppGlobalInfo + 1);
    else
      v13 = 0;
    v6 = 0;
    v14 = MprConfigTransportCreate(
            this[13],
            *(_DWORD *)a2,
            *((LPWSTR *)a2 + 1),
            ppGlobalInfo,
            v13,
            dwGlobalInfoSize,
            v12,
            *((LPWSTR *)a2 + 2),
            &hRouterTransport);
    if ( v14 )
    {
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      else
        v6 = v14;
      TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "HrMprConfigTransportCreate", v6);
    }
    operator delete(ppGlobalInfo);
    operator delete(dwGlobalInfoSize);
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_8;
LABEL_25:
    TracePrintfW(g_dwTraceHandle, L"%hs succeeded : hr = %08lx", "CSteelhead::HrEnsureRouterManager", v6);
    return v6;
  }
LABEL_8:
  TracePrintfW(g_dwTraceHandle, L"%hs failed : hr = %08lx", "CSteelhead::HrEnsureRouterManager", v6);
  return v6;
}

```

## disassembly

```asm
0x18003628c  push    rbp
0x18003628e  push    rbx
0x18003628f  push    rsi
0x180036290  push    rdi
0x180036291  push    r14
0x180036293  mov     rbp, rsp
0x180036296  sub     rsp, 50h
0x18003629a  mov     rsi, rdx
0x18003629d  mov     [rbp+ppGlobalInfo], 0
0x1800362a5  mov     edx, [rdx]; unsigned int
0x1800362a7  lea     r8, [rbp+hRouterTransport]; void **
0x1800362ab  mov     r14, rcx
0x1800362ae  mov     [rbp+hRouterTransport], 0
0x1800362b6  mov     rcx, [rcx+68h]; void *
0x1800362ba  call    ?HrMprConfigTransportGetHandle@@YAJPEAXKPEAPEAX@Z; HrMprConfigTransportGetHandle(void *,ulong,void * *)
0x1800362bf  mov     ebx, eax
0x1800362c1  cmp     eax, 80070386h
0x1800362c6  jz      loc_180036370
0x1800362cc  test    eax, eax
0x1800362ce  js      short loc_18003632F
0x1800362d0  mov     rdx, [rbp+hRouterTransport]; hRouterTransport
0x1800362d4  lea     r9, [rbp+dwGlobalInfoSize]; lpdwGlobalInfoSize
0x1800362d8  mov     rcx, [r14+68h]; hMprConfig
0x1800362dc  lea     r8, [rbp+ppGlobalInfo]; ppGlobalInfo
0x1800362e0  xor     edi, edi
0x1800362e2  mov     dword ptr [rbp+dwGlobalInfoSize], 0
0x1800362e9  mov     [rsp+50h+lplpwsDLLPath], rdi; lplpwsDLLPath
0x1800362ee  mov     [rsp+50h+lpdwClientInterfaceInfoSize], rdi; lpdwClientInterfaceInfoSize
0x1800362f3  mov     [rsp+50h+ppClientInterfaceInfo], rdi; ppClientInterfaceInfo
0x1800362f8  call    MprConfigTransportGetInfo
0x1800362fd  mov     ebx, eax
0x1800362ff  test    eax, eax
0x180036301  jz      short loc_18003635B
0x180036303  jle     short loc_18003630E
0x180036305  movzx   ebx, ax
0x180036308  or      ebx, 80070000h
0x18003630e  test    ebx, ebx
0x180036310  jns     short loc_180036359
0x180036312  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x180036318  lea     r8, aHrmprconfigtra_4; "HrMprConfigTransportGetInfo"
0x18003631f  mov     r9d, ebx
0x180036322  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180036329  call    cs:__imp_TracePrintfW
0x18003632f  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180036336  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x18003633c  lea     r8, aCsteelheadHren_3; "CSteelhead::HrEnsureRouterManager"
0x180036343  mov     r9d, ebx
0x180036346  call    cs:__imp_TracePrintfW
0x18003634c  mov     eax, ebx
0x18003634e  add     rsp, 50h
0x180036352  pop     r14
0x180036354  pop     rdi
0x180036355  pop     rsi
0x180036356  pop     rbx
0x180036357  pop     rbp
0x180036358  retn
0x180036359  mov     edi, ebx
0x18003635b  mov     rcx, [rbp+ppGlobalInfo]; pBuffer
0x18003635f  test    rcx, rcx
0x180036362  jz      short loc_180036370
0x180036364  mov     ebx, edi
0x180036366  call    MprConfigBufferFree
0x18003636b  jmp     loc_18003642A
0x180036370  mov     rax, [rsi+20h]
0x180036374  lea     rdx, [rbp+dwGlobalInfoSize]
0x180036378  lea     rcx, [rbp+ppGlobalInfo]
0x18003637c  mov     [rbp+dwGlobalInfoSize], 0
0x180036384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036389  mov     rax, [rbp+dwGlobalInfoSize]
0x18003638d  mov     r8, [rsi+10h]
0x180036391  test    rax, rax
0x180036394  jz      short loc_18003639B
0x180036396  mov     ecx, [rax+4]
0x180036399  jmp     short loc_18003639D
0x18003639b  xor     ecx, ecx
0x18003639d  mov     r9, [rbp+ppGlobalInfo]; pGlobalInfo
0x1800363a1  test    r9, r9
0x1800363a4  jz      short loc_1800363AC
0x1800363a6  mov     edx, [r9+4]
0x1800363aa  jmp     short loc_1800363AE
0x1800363ac  xor     edx, edx
0x1800363ae  lea     r10, [rbp+hRouterTransport]
0x1800363b2  xor     ebx, ebx
0x1800363b4  mov     [rsp+50h+phRouterTransport], r10; phRouterTransport
0x1800363b9  mov     [rsp+50h+lpwsDLLPath], r8; lpwsDLLPath
0x1800363be  mov     r8, [rsi+8]; lpwsTransportName
0x1800363c2  mov     dword ptr [rsp+50h+lplpwsDLLPath], ecx; dwClientInterfaceInfoSize
0x1800363c6  mov     rcx, [r14+68h]; hMprConfig
0x1800363ca  mov     [rsp+50h+lpdwClientInterfaceInfoSize], rax; pClientInterfaceInfo
0x1800363cf  mov     dword ptr [rsp+50h+ppClientInterfaceInfo], edx; dwGlobalInfoSize
0x1800363d3  mov     edx, [rsi]; dwTransportId
0x1800363d5  call    MprConfigTransportCreate
0x1800363da  test    eax, eax
0x1800363dc  jz      short loc_18003640E
0x1800363de  jg      short loc_1800363E4
0x1800363e0  mov     ebx, eax
0x1800363e2  jmp     short loc_1800363ED
0x1800363e4  movzx   ebx, ax
0x1800363e7  or      ebx, 80070000h
0x1800363ed  test    ebx, ebx
0x1800363ef  jns     short loc_18003640E
0x1800363f1  mov     ecx, cs:g_dwTraceHandle; dwTraceID
0x1800363f7  lea     r8, aHrmprconfigtra_5; "HrMprConfigTransportCreate"
0x1800363fe  mov     r9d, ebx
0x180036401  lea     rdx, aHsFailedHr08lx; "%hs failed : hr = %08lx"
0x180036408  call    cs:__imp_TracePrintfW
0x18003640e  mov     rcx, [rbp+ppGlobalInfo]
0x180036412  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180036418  mov     rcx, [rbp+dwGlobalInfoSize]
0x18003641c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180036422  test    ebx, ebx
0x180036424  js      loc_18003632F
0x18003642a  lea     rdx, szFormat; "%hs succeeded : hr = %08lx"
0x180036431  jmp     loc_180036336
```
