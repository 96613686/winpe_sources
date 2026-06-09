# NhpQueryServiceStartType(SC_HANDLE__ *,ulong *)

- ea: `0x180070ecc`
- end: `0x180071044`
- name: `?NhpQueryServiceStartType@@YAKPEAUSC_HANDLE__@@PEAK@Z`
- size: `376`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18004b358`

## callees

- `0x18000c110`
- `0x18001ec08`
- `0x180070ecc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070f22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070fe7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070f22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070f95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180070fe7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180070f35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180070fa3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180070f35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180070fa3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070ff5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180070ff5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070f6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070fd1`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180070f5d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180070fc7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180070f5d`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180070fc7`

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
0x180070ecc  push    rbx
0x180070ece  push    rbp
0x180070ecf  push    rsi
0x180070ed0  push    rdi
0x180070ed1  push    r12
0x180070ed3  push    r14
0x180070ed5  sub     rsp, 38h
0x180070ed9  mov     r14, rdx
0x180070edc  mov     rbp, rcx
0x180070edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180070ee6  lea     r12, WPP_GLOBAL_Control
0x180070eed  cmp     rcx, r12
0x180070ef0  jz      short loc_180070F16
0x180070ef2  test    dword ptr [rcx+1Ch], 200h
0x180070ef9  jz      short loc_180070F16
0x180070efb  cmp     byte ptr [rcx+19h], 6
0x180070eff  jb      short loc_180070F16
0x180070f01  mov     rcx, [rcx+10h]
0x180070f05  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180070f0c  mov     edx, 37h ; '7'
0x180070f11  call    WPP_SF_
0x180070f16  mov     ebx, 180h
0x180070f1b  mov     [rsp+68h+pcbBytesNeeded], ebx
0x180070f22  call    cs:__imp_GetProcessHeap
0x180070f28  mov     edi, 8
0x180070f2d  mov     r8d, ebx; dwBytes
0x180070f30  mov     edx, edi; dwFlags
0x180070f32  mov     rcx, rax; hHeap
0x180070f35  call    cs:__imp_HeapAlloc
0x180070f3b  mov     rbx, rax
0x180070f3e  test    rax, rax
0x180070f41  jz      loc_180071035
0x180070f47  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x180070f4f  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x180070f57  mov     rdx, rax; lpServiceConfig
0x180070f5a  mov     rcx, rbp; hService
0x180070f5d  call    cs:__imp_QueryServiceConfigW
0x180070f63  test    eax, eax
0x180070f65  jnz     short loc_180070FDF
0x180070f67  call    cs:__imp_GetLastError
0x180070f6d  mov     esi, eax
0x180070f6f  call    cs:__imp_GetLastError
0x180070f75  cmp     eax, 7Ah ; 'z'
0x180070f78  jnz     short loc_180070FDB
0x180070f7a  call    cs:__imp_GetProcessHeap
0x180070f80  mov     r8, rbx; lpMem
0x180070f83  xor     edx, edx; dwFlags
0x180070f85  mov     rcx, rax; hHeap
0x180070f88  call    cs:__imp_HeapFree
0x180070f8e  mov     ebx, [rsp+68h+pcbBytesNeeded]
0x180070f95  call    cs:__imp_GetProcessHeap
0x180070f9b  mov     r8d, ebx; dwBytes
0x180070f9e  mov     edx, edi; dwFlags
0x180070fa0  mov     rcx, rax; hHeap
0x180070fa3  call    cs:__imp_HeapAlloc
0x180070fa9  mov     rbx, rax
0x180070fac  test    rax, rax
0x180070faf  jz      short loc_180070FFB
0x180070fb1  mov     r8d, [rsp+68h+pcbBytesNeeded]; cbBufSize
0x180070fb9  lea     r9, [rsp+68h+pcbBytesNeeded]; pcbBytesNeeded
0x180070fc1  mov     rdx, rax; lpServiceConfig
0x180070fc4  mov     rcx, rbp; hService
0x180070fc7  call    cs:__imp_QueryServiceConfigW
0x180070fcd  test    eax, eax
0x180070fcf  jnz     short loc_180070FDF
0x180070fd1  call    cs:__imp_GetLastError
0x180070fd7  mov     edi, eax
0x180070fd9  jmp     short loc_180070FE7
0x180070fdb  mov     edi, esi
0x180070fdd  jmp     short loc_180070FE7
0x180070fdf  mov     eax, [rbx+4]
0x180070fe2  xor     edi, edi
0x180070fe4  mov     [r14], eax
0x180070fe7  call    cs:__imp_GetProcessHeap
0x180070fed  mov     r8, rbx; lpMem
0x180070ff0  xor     edx, edx; dwFlags
0x180070ff2  mov     rcx, rax; hHeap
0x180070ff5  call    cs:__imp_HeapFree
0x180070ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180071002  cmp     rcx, r12
0x180071005  jz      short loc_180071035
0x180071007  test    dword ptr [rcx+1Ch], 200h
0x18007100e  jz      short loc_180071035
0x180071010  cmp     byte ptr [rcx+19h], 6
0x180071014  jb      short loc_180071035
0x180071016  mov     eax, [r14]
0x180071019  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180071020  mov     rcx, [rcx+10h]
0x180071024  mov     edx, 38h ; '8'
0x180071029  mov     r9d, edi
0x18007102c  mov     [rsp+68h+var_48], eax
0x180071030  call    WPP_SF_Dd
0x180071035  mov     eax, edi
0x180071037  add     rsp, 38h
0x18007103b  pop     r14
0x18007103d  pop     r12
0x18007103f  pop     rdi
0x180071040  pop     rsi
0x180071041  pop     rbp
0x180071042  pop     rbx
0x180071043  retn
```
