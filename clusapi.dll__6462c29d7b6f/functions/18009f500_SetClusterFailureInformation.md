# SetClusterFailureInformation

- ea: `0x18009f500`
- end: `0x18009f6f5`
- name: `SetClusterFailureInformation`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18009f420`

## callees

- `0x18009ef60`
- `0x18009f500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f6c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f6c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f621`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f5a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009f5a2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009f580`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009f580`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009f55e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009f55e`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009f693`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009f6b8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009f693`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009f6b8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18009f616`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18009f643`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18009f616`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18009f643`

## string_xrefs

- `0x18009f6a1`: `[ClRtl] Couldn't get SC handle to Cluster Service %1!u!\n`

## pseudocode

```c
__int64 __fastcall SetClusterFailureInformation(
        const WCHAR *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5)
{
  int v5; // ebx
  unsigned int v6; // esi
  unsigned int i; // eax
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rbp
  SC_HANDLE v10; // rdi
  int v11; // r15d
  _DWORD *v12; // r14
  int v13; // ebx
  __int64 j; // rdx
  bool v15; // cc
  BOOL v16; // ebx
  __int64 LastError; // rbx
  DWORD v18; // eax
  const char *v19; // rdx
  _OWORD Info[2]; // [rsp+20h] [rbp-58h] BYREF
  _DWORD *v22; // [rsp+40h] [rbp-38h]
  int v23; // [rsp+90h] [rbp+18h] BYREF

  v5 = 0;
  v23 = 0;
  v6 = a4;
  memset(Info, 0, sizeof(Info));
  v22 = 0;
  for ( i = a4; i < a5; ++v5 )
    i *= 2;
  v8 = OpenSCManagerW(a1, 0, 0xF003Fu);
  v9 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
    ClRtlDbgPrint(1, "[ClRtl] Couldn't get a handle to the SC Manager %1!u!\n", LastError);
    return (unsigned int)LastError;
  }
  v10 = OpenServiceW(v8, L"ClusSvc", 0xF01FFu);
  if ( !v10 )
  {
    LastError = GetLastError();
    ClRtlDbgPrint(1, "[ClRtl] Couldn't get SC handle to Cluster Service %1!u!\n", LastError);
    goto LABEL_19;
  }
  v11 = v5;
  v12 = LocalAlloc(0x40u, 8LL * v5 + 8);
  if ( !v12 )
  {
    LODWORD(LastError) = 14;
    ClRtlDbgPrint(1, "[ClRtl] Couldn't allocate memory to set SM Failure actions\n");
    goto LABEL_17;
  }
  v13 = v5 + 1;
  for ( j = 0; (int)j < v11; j = (unsigned int)(j + 1) )
  {
    v12[2 * j + 1] = v6;
    v15 = 2 * v6 <= a5;
    v6 *= 2;
    v12[2 * j] = 1;
    if ( !v15 )
      v6 = a5;
  }
  v12[2 * (int)j] = 1;
  v12[2 * (int)j + 1] = v6;
  LODWORD(Info[0]) = 1800;
  *(_OWORD *)((char *)Info + 8) = 0;
  DWORD2(Info[1]) = v13;
  v22 = v12;
  v16 = ChangeServiceConfig2W(v10, 2u, Info);
  LocalFree(v12);
  if ( !v16 )
  {
    v18 = GetLastError();
    v19 = "[ClRtl] Couldn't set SC failure info %1!u!\n";
    goto LABEL_15;
  }
  v23 = 1;
  if ( !ChangeServiceConfig2W(v10, 4u, &v23) )
  {
    v18 = GetLastError();
    v19 = "[ClRtl] Couldn't set SC failure actions flag %1!u!\n";
LABEL_15:
    LODWORD(LastError) = v18;
    ClRtlDbgPrint(1, v19, v18);
    goto LABEL_17;
  }
  LODWORD(LastError) = 0;
LABEL_17:
  CloseServiceHandle(v10);
LABEL_19:
  CloseServiceHandle(v9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18009f500  mov     r11, rsp
0x18009f503  mov     [r11+8], rbx
0x18009f507  mov     [r11+10h], rbp
0x18009f50b  mov     [r11+18h], r8d
0x18009f50f  push    rsi
0x18009f510  push    rdi
0x18009f511  push    r13
0x18009f513  push    r14
0x18009f515  push    r15
0x18009f517  sub     rsp, 50h
0x18009f51b  xor     eax, eax
0x18009f51d  xor     ebx, ebx
0x18009f51f  xorps   xmm0, xmm0
0x18009f522  mov     [r11+18h], eax
0x18009f526  mov     esi, r9d
0x18009f529  movups  [rsp+78h+Info], xmm0
0x18009f52e  lea     r13d, [rbx+1]
0x18009f532  movups  [rsp+78h+var_48], xmm0
0x18009f537  mov     [r11-38h], rax
0x18009f53b  mov     eax, r9d
0x18009f53e  cmp     r9d, [rsp+78h+arg_20]
0x18009f546  jnb     short loc_18009F556
0x18009f548  add     eax, eax
0x18009f54a  add     ebx, r13d
0x18009f54d  cmp     eax, [rsp+78h+arg_20]
0x18009f554  jb      short loc_18009F548
0x18009f556  xor     edx, edx; lpDatabaseName
0x18009f558  mov     r8d, 0F003Fh; dwDesiredAccess
0x18009f55e  call    cs:__imp_OpenSCManagerW
0x18009f564  mov     rbp, rax
0x18009f567  test    rax, rax
0x18009f56a  jz      loc_18009F6C0
0x18009f570  mov     r8d, 0F01FFh; dwDesiredAccess
0x18009f576  lea     rdx, aClussvc; "ClusSvc"
0x18009f57d  mov     rcx, rax; hSCManager
0x18009f580  call    cs:__imp_OpenServiceW
0x18009f586  mov     rdi, rax
0x18009f589  test    rax, rax
0x18009f58c  jz      loc_18009F69B
0x18009f592  movsxd  r15, ebx
0x18009f595  mov     ecx, 40h ; '@'; uFlags
0x18009f59a  lea     rdx, ds:8[r15*8]; uBytes
0x18009f5a2  call    cs:__imp_LocalAlloc
0x18009f5a8  mov     r14, rax
0x18009f5ab  test    rax, rax
0x18009f5ae  jz      loc_18009F67C
0x18009f5b4  add     ebx, r13d
0x18009f5b7  xor     edx, edx
0x18009f5b9  test    r15d, r15d
0x18009f5bc  jle     short loc_18009F5E3
0x18009f5be  lea     eax, [rsi+rsi]
0x18009f5c1  mov     [r14+rdx*8+4], esi
0x18009f5c6  cmp     eax, [rsp+78h+arg_20]
0x18009f5cd  mov     esi, eax
0x18009f5cf  mov     [r14+rdx*8], r13d
0x18009f5d3  cmova   esi, [rsp+78h+arg_20]
0x18009f5db  add     edx, r13d
0x18009f5de  cmp     edx, r15d
0x18009f5e1  jl      short loc_18009F5BE
0x18009f5e3  movsxd  rax, edx
0x18009f5e6  lea     r8, [rsp+78h+Info]; lpInfo
0x18009f5eb  xorps   xmm0, xmm0
0x18009f5ee  mov     edx, 2; dwInfoLevel
0x18009f5f3  mov     rcx, rdi; hService
0x18009f5f6  mov     [r14+rax*8], r13d
0x18009f5fa  mov     [r14+rax*8+4], esi
0x18009f5ff  mov     dword ptr [rsp+78h+Info], 708h
0x18009f607  movdqu  [rsp+78h+Info+8], xmm0
0x18009f60d  mov     dword ptr [rsp+78h+var_48+8], ebx
0x18009f611  mov     [rsp+78h+var_38], r14
0x18009f616  call    cs:__imp_ChangeServiceConfig2W
0x18009f61c  mov     rcx, r14; hMem
0x18009f61f  mov     ebx, eax
0x18009f621  call    cs:__imp_LocalFree
0x18009f627  test    ebx, ebx
0x18009f629  jz      short loc_18009F660
0x18009f62b  lea     r8, [rsp+78h+arg_10]; lpInfo
0x18009f633  mov     [rsp+78h+arg_10], r13d
0x18009f63b  mov     edx, 4; dwInfoLevel
0x18009f640  mov     rcx, rdi; hService
0x18009f643  call    cs:__imp_ChangeServiceConfig2W
0x18009f649  test    eax, eax
0x18009f64b  jz      short loc_18009F651
0x18009f64d  xor     ebx, ebx
0x18009f64f  jmp     short loc_18009F690
0x18009f651  call    cs:__imp_GetLastError
0x18009f657  lea     rdx, aClrtlCouldnTSe_0; "[ClRtl] Couldn't set SC failure actions"...
0x18009f65e  jmp     short loc_18009F66D
0x18009f660  call    cs:__imp_GetLastError
0x18009f666  lea     rdx, aClrtlCouldnTSe; "[ClRtl] Couldn't set SC failure info %1"...
0x18009f66d  mov     r8d, eax
0x18009f670  mov     ecx, r13d
0x18009f673  mov     ebx, eax
0x18009f675  call    ClRtlDbgPrint
0x18009f67a  jmp     short loc_18009F690
0x18009f67c  lea     rdx, aClrtlCouldnTAl; "[ClRtl] Couldn't allocate memory to set"...
0x18009f683  mov     ecx, r13d
0x18009f686  mov     ebx, 0Eh
0x18009f68b  call    ClRtlDbgPrint
0x18009f690  mov     rcx, rdi; hSCObject
0x18009f693  call    cs:__imp_CloseServiceHandle
0x18009f699  jmp     short loc_18009F6B5
0x18009f69b  call    cs:__imp_GetLastError
0x18009f6a1  lea     rdx, aClrtlCouldnTGe_0; "[ClRtl] Couldn't get SC handle to Clust"...
0x18009f6a8  mov     ecx, r13d
0x18009f6ab  mov     r8d, eax
0x18009f6ae  mov     ebx, eax
0x18009f6b0  call    ClRtlDbgPrint
0x18009f6b5  mov     rcx, rbp; hSCObject
0x18009f6b8  call    cs:__imp_CloseServiceHandle
0x18009f6be  jmp     short loc_18009F6DA
0x18009f6c0  call    cs:__imp_GetLastError
0x18009f6c6  lea     rdx, aClrtlCouldnTGe; "[ClRtl] Couldn't get a handle to the SC"...
0x18009f6cd  mov     ecx, r13d
0x18009f6d0  mov     r8d, eax
0x18009f6d3  mov     ebx, eax
0x18009f6d5  call    ClRtlDbgPrint
0x18009f6da  lea     r11, [rsp+78h+var_28]
0x18009f6df  mov     eax, ebx
0x18009f6e1  mov     rbx, [r11+30h]
0x18009f6e5  mov     rbp, [r11+38h]
0x18009f6e9  mov     rsp, r11
0x18009f6ec  pop     r15
0x18009f6ee  pop     r14
0x18009f6f0  pop     r13
0x18009f6f2  pop     rdi
0x18009f6f3  pop     rsi
0x18009f6f4  retn
```
