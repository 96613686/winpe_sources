# NhpQueryServiceStartType(SC_HANDLE__ *,ulong *)

- ea: `0x1800768c0`
- end: `0x180076a8f`
- name: `?NhpQueryServiceStartType@@YAKPEAUSC_HANDLE__@@PEAK@Z`
- size: `463`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18004f0a0`

## callees

- `0x18000ca20`
- `0x1800202e0`
- `0x1800768c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800769bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076a25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800769bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076a25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007692f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800769cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007692f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800769cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800769a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076a39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800769a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007697f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076a09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007697f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076a09`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007695d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800769f9`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007695d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800769f9`

## pseudocode

```c
__int64 __fastcall NhpQueryServiceStartType(SC_HANDLE hService, unsigned int *a2)
{
  HANDLE ProcessHeap; // rax
  DWORD v5; // edi
  struct _QUERY_SERVICE_CONFIGW *v6; // rax
  struct _QUERY_SERVICE_CONFIGW *v7; // rbx
  DWORD LastError; // esi
  HANDLE v9; // rax
  DWORD v10; // ebx
  HANDLE v11; // rax
  struct _QUERY_SERVICE_CONFIGW *v12; // rax
  HANDLE v13; // rax
  DWORD pcbBytesNeeded; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  pcbBytesNeeded = 384;
  ProcessHeap = GetProcessHeap();
  v5 = 8;
  v6 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(ProcessHeap, 8u, 0x180u);
  v7 = v6;
  if ( v6 )
  {
    if ( !QueryServiceConfigW(hService, v6, pcbBytesNeeded, &pcbBytesNeeded) )
    {
      LastError = GetLastError();
      if ( GetLastError() != 122 )
      {
        v5 = LastError;
        goto LABEL_13;
      }
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v7);
      v10 = pcbBytesNeeded;
      v11 = GetProcessHeap();
      v12 = (struct _QUERY_SERVICE_CONFIGW *)HeapAlloc(v11, 8u, v10);
      v7 = v12;
      if ( !v12 )
      {
LABEL_14:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5, *a2);
        }
        return v5;
      }
      if ( !QueryServiceConfigW(hService, v12, pcbBytesNeeded, &pcbBytesNeeded) )
      {
        v5 = GetLastError();
LABEL_13:
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v7);
        goto LABEL_14;
      }
    }
    v5 = 0;
    *a2 = v7->dwStartType;
    goto LABEL_13;
  }
  return v5;
}

```

## disassembly

```asm
0x1800768c0  push    rbx
0x1800768c2  push    rbp
0x1800768c3  push    rsi
0x1800768c4  push    rdi
0x1800768c5  push    r12
0x1800768c7  push    r14
0x1800768c9  sub     rsp, 38h
0x1800768cd  mov     r14, rdx
0x1800768d0  mov     rbp, rcx
0x1800768d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800768da  lea     r12, WPP_GLOBAL_Control
0x1800768e1  cmp     rcx, r12
0x1800768e4  jz      short loc_18007690A
0x1800768e6  test    dword ptr [rcx+1Ch], 200h
0x1800768ed  jz      short loc_18007690A
0x1800768ef  cmp     byte ptr [rcx+19h], 6
0x1800768f3  jb      short loc_18007690A
0x1800768f5  mov     rcx, [rcx+10h]
0x1800768f9  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180076900  mov     edx, 37h ; '7'
0x180076905  call    WPP_SF_
0x18007690a  mov     ebx, 180h
0x18007690f  mov     [rsp+68h+pcbBytesNeeded], ebx
0x180076916  call    cs:__imp_GetProcessHeap
0x18007691d  nop     dword ptr [rax+rax+00h]
0x180076922  mov     edi, 8
0x180076927  mov     r8d, ebx; dwBytes
0x18007692a  mov     edx, edi; dwFlags
0x18007692c  mov     rcx, rax; hHeap
0x18007692f  call    cs:__imp_HeapAlloc
0x180076936  nop     dword ptr [rax+rax+00h]
0x18007693b  mov     rbx, rax
0x18007693e  test    rax, rax
0x180076941  jz      loc_180076A7F
0x180076947  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x18007694f  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x180076957  mov     rdx, rax; lpServiceConfig
0x18007695a  mov     rcx, rbp; hService
0x18007695d  call    cs:__imp_QueryServiceConfigW
0x180076964  nop     dword ptr [rax+rax+00h]
0x180076969  test    eax, eax
0x18007696b  jnz     loc_180076A1D
0x180076971  call    cs:__imp_GetLastError
0x180076978  nop     dword ptr [rax+rax+00h]
0x18007697d  mov     esi, eax
0x18007697f  call    cs:__imp_GetLastError
0x180076986  nop     dword ptr [rax+rax+00h]
0x18007698b  cmp     eax, 7Ah ; 'z'
0x18007698e  jnz     loc_180076A19
0x180076994  call    cs:__imp_GetProcessHeap
0x18007699b  nop     dword ptr [rax+rax+00h]
0x1800769a0  mov     r8, rbx; lpMem
0x1800769a3  xor     edx, edx; dwFlags
0x1800769a5  mov     rcx, rax; hHeap
0x1800769a8  call    cs:__imp_HeapFree
0x1800769af  nop     dword ptr [rax+rax+00h]
0x1800769b4  mov     ebx, [rsp+68h+pcbBytesNeeded]
0x1800769bb  call    cs:__imp_GetProcessHeap
0x1800769c2  nop     dword ptr [rax+rax+00h]
0x1800769c7  mov     r8d, ebx; dwBytes
0x1800769ca  mov     edx, edi; dwFlags
0x1800769cc  mov     rcx, rax; hHeap
0x1800769cf  call    cs:__imp_HeapAlloc
0x1800769d6  nop     dword ptr [rax+rax+00h]
0x1800769db  mov     rbx, rax
0x1800769de  test    rax, rax
0x1800769e1  jz      short loc_180076A45
0x1800769e3  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x1800769eb  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x1800769f3  mov     rdx, rax; lpServiceConfig
0x1800769f6  mov     rcx, rbp; hService
0x1800769f9  call    cs:__imp_QueryServiceConfigW
0x180076a00  nop     dword ptr [rax+rax+00h]
0x180076a05  test    eax, eax
0x180076a07  jnz     short loc_180076A1D
0x180076a09  call    cs:__imp_GetLastError
0x180076a10  nop     dword ptr [rax+rax+00h]
0x180076a15  mov     edi, eax
0x180076a17  jmp     short loc_180076A25
0x180076a19  mov     edi, esi
0x180076a1b  jmp     short loc_180076A25
0x180076a1d  mov     eax, [rbx+4]
0x180076a20  xor     edi, edi
0x180076a22  mov     [r14], eax
0x180076a25  call    cs:__imp_GetProcessHeap
0x180076a2c  nop     dword ptr [rax+rax+00h]
0x180076a31  mov     r8, rbx; lpMem
0x180076a34  xor     edx, edx; dwFlags
0x180076a36  mov     rcx, rax; hHeap
0x180076a39  call    cs:__imp_HeapFree
0x180076a40  nop     dword ptr [rax+rax+00h]
0x180076a45  mov     rcx, cs:WPP_GLOBAL_Control
0x180076a4c  cmp     rcx, r12
0x180076a4f  jz      short loc_180076A7F
0x180076a51  test    dword ptr [rcx+1Ch], 200h
0x180076a58  jz      short loc_180076A7F
0x180076a5a  cmp     byte ptr [rcx+19h], 6
0x180076a5e  jb      short loc_180076A7F
0x180076a60  mov     eax, [r14]
0x180076a63  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180076a6a  mov     rcx, [rcx+10h]
0x180076a6e  mov     edx, 38h ; '8'
0x180076a73  mov     r9d, edi
0x180076a76  mov     [rsp+68h+var_48], eax
0x180076a7a  call    WPP_SF_Dd
0x180076a7f  mov     eax, edi
0x180076a81  add     rsp, 38h
0x180076a85  pop     r14
0x180076a87  pop     r12
0x180076a89  pop     rdi
0x180076a8a  pop     rsi
0x180076a8b  pop     rbp
0x180076a8c  pop     rbx
0x180076a8d  retn
```
