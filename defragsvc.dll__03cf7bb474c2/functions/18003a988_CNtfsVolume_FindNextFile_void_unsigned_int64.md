# CNtfsVolume::_FindNextFile(void * *,unsigned __int64 *)

- ea: `0x18003a988`
- end: `0x18003ab54`
- name: `?_FindNextFile@CNtfsVolume@@AEAAJPEAPEAXPEA_K@Z`
- size: `460`
- prototype: `__int64 __fastcall(CNtfsVolume *this, char **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ae04`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18003a988`
- `0x180061a74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aaf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a9ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aaf1`
- `ntdll!NtQueryDirectoryFileEx` at `0x18003aaa9`
- `ntdll!NtQueryDirectoryFileEx` at `0x18003aaa9`
- `ntdll!RtlEnterCriticalSection` at `0x18003aa1e`
- `ntdll!RtlEnterCriticalSection` at `0x18003aa1e`
- `ntdll!RtlLeaveCriticalSection` at `0x18003ab1b`
- `ntdll!RtlLeaveCriticalSection` at `0x18003ab1b`
- `ntdll!RtlNtStatusToDosError` at `0x18003aae9`
- `ntdll!RtlNtStatusToDosError` at `0x18003aae9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003aa34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003aa34`

## pseudocode

```c
__int64 __fastcall CNtfsVolume::_FindNextFile(CNtfsVolume *this, char **a2, unsigned __int64 *a3)
{
  char *v5; // rbx
  __int16 v6; // ax
  __int16 v7; // ax
  unsigned int *v8; // rax
  LPVOID v9; // rax
  bool v10; // zf
  unsigned int *v11; // rdi
  NTSTATUS v12; // eax
  unsigned int *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned int *v15; // rdx
  char *v16; // rax
  DWORD v17; // eax
  CNtfsVolume *v18; // rcx
  unsigned int v19; // edi
  __int128 v21; // [rsp+50h] [rbp-19h] BYREF
  int v22; // [rsp+60h] [rbp-9h] BYREF
  __int16 v23; // [rsp+64h] [rbp-5h]
  __int16 v24; // [rsp+66h] [rbp-3h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "CNtfsVolume::_FindNextFile", 2253, 1);
  v21 = 0;
  v5 = *a2;
  v23 = 2261;
  v6 = 2262;
  if ( !a3 )
  {
    v22 = -2147024809;
LABEL_3:
    v24 = v6;
    goto LABEL_23;
  }
  v22 = 0;
  v23 = 2262;
  if ( v5 != (char *)-1LL )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 32));
    v8 = (unsigned int *)*((_QWORD *)v5 + 1);
    if ( !v8 )
    {
      v9 = CoTaskMemAlloc(0x1000u);
      *((_QWORD *)v5 + 1) = v9;
      v10 = v9 == 0;
      v6 = 2280;
      if ( v10 )
      {
        v22 = -2147024882;
        goto LABEL_3;
      }
      v22 = 0;
      v23 = 2280;
      v8 = (unsigned int *)*((_QWORD *)v5 + 1);
      *((_QWORD *)v5 + 2) = v8;
      *((_DWORD *)v5 + 6) = 4096;
    }
    v11 = (unsigned int *)*((_QWORD *)v5 + 2);
    if ( v8 == v11 )
    {
      v12 = NtQueryDirectoryFileEx(*(_QWORD *)v5, 0, 0, 0, &v21, v11, *((_DWORD *)v5 + 6), 60, 8, 0);
      if ( v12 == -2147483643 )
      {
        v13 = v11;
        v14 = *v11;
        if ( (_DWORD)v14 )
        {
          do
          {
            v15 = v13;
            v13 += v14 >> 2;
            v14 = *v13;
          }
          while ( (_DWORD)v14 );
          if ( v15 )
            *v15 = 0;
        }
      }
      else if ( v12 < 0 )
      {
        v17 = RtlNtStatusToDosError(v12);
        SetLastError(v17);
        v7 = 2334;
        goto LABEL_6;
      }
    }
    if ( *v11 )
      v16 = (char *)v11 + *v11;
    else
      v16 = (char *)*((_QWORD *)v5 + 1);
    *((_QWORD *)v5 + 2) = v16;
    *a3 = *((_QWORD *)v11 + 9);
    v22 = 0;
    goto LABEL_23;
  }
  SetLastError(6u);
  v7 = 2267;
LABEL_6:
  v22 = 1;
  v23 = v7;
LABEL_23:
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 32));
  v19 = v22;
  if ( v22 == 1 )
  {
    CNtfsVolume::_FindClose(v18, v5);
    *a2 = (char *)-1LL;
    v19 = v22;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22);
  return v19;
}

```

## disassembly

```asm
0x18003a988  push    rbp
0x18003a98a  push    rbx
0x18003a98b  push    rsi
0x18003a98c  push    rdi
0x18003a98d  push    r14
0x18003a98f  lea     rbp, [rsp-37h]
0x18003a994  sub     rsp, 0A0h
0x18003a99b  mov     rsi, r8
0x18003a99e  mov     r14, rdx
0x18003a9a1  mov     r9d, 1; unsigned __int16
0x18003a9a7  mov     r8d, 8CDh; unsigned __int16
0x18003a9ad  lea     rdx, aCntfsvolumeFin_1; "CNtfsVolume::_FindNextFile"
0x18003a9b4  lea     rcx, [rbp+57h+var_60]; this
0x18003a9b8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003a9bd  nop
0x18003a9be  xorps   xmm0, xmm0
0x18003a9c1  movups  [rbp+57h+var_70], xmm0
0x18003a9c5  mov     rbx, [r14]
0x18003a9c8  mov     eax, 8D5h
0x18003a9cd  mov     [rbp+57h+var_5C], ax
0x18003a9d1  mov     eax, 8D6h
0x18003a9d6  test    rsi, rsi
0x18003a9d9  jnz     short loc_18003A9EB
0x18003a9db  mov     [rbp+57h+var_60], 80070057h
0x18003a9e2  mov     [rbp+57h+var_5A], ax
0x18003a9e6  jmp     loc_18003AB17
0x18003a9eb  mov     [rbp+57h+var_60], 0
0x18003a9f2  mov     [rbp+57h+var_5C], ax
0x18003a9f6  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003a9fa  jnz     short loc_18003AA1A
0x18003a9fc  lea     ecx, [rbx+7]; dwErrCode
0x18003a9ff  call    cs:__imp_SetLastError
0x18003aa05  mov     eax, 8DBh
0x18003aa0a  mov     [rbp+57h+var_60], 1
0x18003aa11  mov     [rbp+57h+var_5C], ax
0x18003aa15  jmp     loc_18003AB17
0x18003aa1a  lea     rcx, [rbx+20h]; CriticalSection
0x18003aa1e  call    cs:__imp_RtlEnterCriticalSection
0x18003aa24  mov     rax, [rbx+8]
0x18003aa28  test    rax, rax
0x18003aa2b  jnz     short loc_18003AA67
0x18003aa2d  mov     edi, 1000h
0x18003aa32  mov     ecx, edi; cb
0x18003aa34  call    cs:__imp_CoTaskMemAlloc
0x18003aa3a  mov     [rbx+8], rax
0x18003aa3e  test    rax, rax
0x18003aa41  mov     eax, 8E8h
0x18003aa46  jnz     short loc_18003AA51
0x18003aa48  mov     [rbp+57h+var_60], 8007000Eh
0x18003aa4f  jmp     short loc_18003A9E2
0x18003aa51  mov     [rbp+57h+var_60], 0
0x18003aa58  mov     [rbp+57h+var_5C], ax
0x18003aa5c  mov     rax, [rbx+8]
0x18003aa60  mov     [rbx+10h], rax
0x18003aa64  mov     [rbx+18h], edi
0x18003aa67  mov     rdi, [rbx+10h]
0x18003aa6b  cmp     rax, rdi
0x18003aa6e  jnz     short loc_18003AAD7
0x18003aa70  mov     [rsp+0C0h+var_78], 0
0x18003aa79  mov     [rsp+0C0h+var_80], 8
0x18003aa81  mov     [rsp+0C0h+var_88], 3Ch ; '<'
0x18003aa89  mov     eax, [rbx+18h]
0x18003aa8c  mov     [rsp+0C0h+var_90], eax
0x18003aa90  mov     [rsp+0C0h+var_98], rdi
0x18003aa95  lea     rax, [rbp+57h+var_70]
0x18003aa99  mov     [rsp+0C0h+var_A0], rax
0x18003aa9e  xor     r9d, r9d
0x18003aaa1  xor     r8d, r8d
0x18003aaa4  xor     edx, edx
0x18003aaa6  mov     rcx, [rbx]
0x18003aaa9  call    cs:__imp_NtQueryDirectoryFileEx
0x18003aaaf  cmp     eax, 80000005h
0x18003aab4  jnz     short loc_18003AAE3
0x18003aab6  mov     rcx, rdi
0x18003aab9  mov     eax, [rdi]
0x18003aabb  test    eax, eax
0x18003aabd  jz      short loc_18003AAD7
0x18003aabf  mov     rdx, rcx
0x18003aac2  shr     rax, 2
0x18003aac6  lea     rcx, [rcx+rax*4]
0x18003aaca  mov     eax, [rcx]
0x18003aacc  test    eax, eax
0x18003aace  jnz     short loc_18003AABF
0x18003aad0  test    rdx, rdx
0x18003aad3  jz      short loc_18003AAD7
0x18003aad5  mov     [rdx], eax
0x18003aad7  cmp     dword ptr [rdi], 0
0x18003aada  jz      short loc_18003AB01
0x18003aadc  mov     eax, [rdi]
0x18003aade  add     rax, rdi
0x18003aae1  jmp     short loc_18003AB05
0x18003aae3  test    eax, eax
0x18003aae5  jns     short loc_18003AAD7
0x18003aae7  mov     ecx, eax; Status
0x18003aae9  call    cs:__imp_RtlNtStatusToDosError
0x18003aaef  mov     ecx, eax; dwErrCode
0x18003aaf1  call    cs:__imp_SetLastError
0x18003aaf7  mov     eax, 91Eh
0x18003aafc  jmp     loc_18003AA0A
0x18003ab01  mov     rax, [rbx+8]
0x18003ab05  mov     [rbx+10h], rax
0x18003ab09  mov     rax, [rdi+48h]
0x18003ab0d  mov     [rsi], rax
0x18003ab10  mov     [rbp+57h+var_60], 0
0x18003ab17  lea     rcx, [rbx+20h]; CriticalSection
0x18003ab1b  call    cs:__imp_RtlLeaveCriticalSection
0x18003ab21  mov     edi, [rbp+57h+var_60]
0x18003ab24  cmp     edi, 1
0x18003ab27  jnz     short loc_18003AB3B
0x18003ab29  mov     rdx, rbx; void *
0x18003ab2c  call    ?_FindClose@CNtfsVolume@@AEAAJPEAX@Z; CNtfsVolume::_FindClose(void *)
0x18003ab31  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18003ab38  mov     edi, [rbp+57h+var_60]
0x18003ab3b  lea     rcx, [rbp+57h+var_60]; this
0x18003ab3f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003ab44  mov     eax, edi
0x18003ab46  add     rsp, 0A0h
0x18003ab4d  pop     r14
0x18003ab4f  pop     rdi
0x18003ab50  pop     rsi
0x18003ab51  pop     rbx
0x18003ab52  pop     rbp
0x18003ab53  retn
```
