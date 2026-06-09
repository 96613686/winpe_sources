# FltpEnumerateAggregateFilterInformation

- ea: `0x180073b50`
- end: `0x180073f07`
- name: `FltpEnumerateAggregateFilterInformation`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180076d60`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x180024800`
- `0x180024c40`
- `0x18005080c`
- `0x180073b50`
- `0x180073f10`
- `0x180074080`
- `0x180074100`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180073e89`
- `ntoskrnl!KeDelayExecutionThread` at `0x180073e89`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180073be4`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180073bf4`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180073be4`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x180073bf4`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180073c8e`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180073d0c`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180073c8e`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x180073d0c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180073c73`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180073cf2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180073c73`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180073cf2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073d84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073dd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073dfb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073ec3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073ef1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007b1ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073d84`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073dd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073dfb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073ec3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180073ef1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18007b1ec`
- `ntoskrnl!ExReleaseFastResource` at `0x180073d78`
- `ntoskrnl!ExReleaseFastResource` at `0x180073dcb`
- `ntoskrnl!ExReleaseFastResource` at `0x180073def`
- `ntoskrnl!ExReleaseFastResource` at `0x180073eb7`
- `ntoskrnl!ExReleaseFastResource` at `0x180073ee5`
- `ntoskrnl!ExReleaseFastResource` at `0x18007b1e0`
- `ntoskrnl!ExReleaseFastResource` at `0x180073d78`
- `ntoskrnl!ExReleaseFastResource` at `0x180073dcb`
- `ntoskrnl!ExReleaseFastResource` at `0x180073def`
- `ntoskrnl!ExReleaseFastResource` at `0x180073eb7`
- `ntoskrnl!ExReleaseFastResource` at `0x180073ee5`
- `ntoskrnl!ExReleaseFastResource` at `0x18007b1e0`

## pseudocode

```c
__int64 __fastcall FltpEnumerateAggregateFilterInformation(
        int a1,
        FILTER_INFORMATION_CLASS a2,
        void *a3,
        ULONG a4,
        ULONG *a5)
{
  int v5; // r12d
  unsigned int LoadedLegacyFiltersList; // eax
  unsigned int LegacyFilterInformation; // ebx
  int v8; // eax
  char *v9; // r13
  int v10; // r15d
  __int64 v11; // r8
  void *v12; // r14
  __int64 v13; // rbx
  int v14; // esi
  __int64 v15; // rdi
  __int64 v16; // r12
  __int64 v17; // r8
  _QWORD *v18; // rdi
  _QWORD *i; // rbx
  unsigned int v20; // eax
  bool v21; // zf
  void *v22; // rdx
  NTSTATUS FilterInformation; // eax
  _QWORD *v24; // rcx
  int v26; // [rsp+30h] [rbp-D0h] BYREF
  int v27; // [rsp+34h] [rbp-CCh]
  ULONG BufferSize; // [rsp+38h] [rbp-C8h]
  FILTER_INFORMATION_CLASS InformationClass; // [rsp+3Ch] [rbp-C4h]
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  LARGE_INTEGER Interval; // [rsp+48h] [rbp-B8h] BYREF
  PULONG BytesReturned; // [rsp+50h] [rbp-B0h]
  PVOID Buffer; // [rsp+58h] [rbp-A8h]
  _BYTE v34[80]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[80]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+100h] [rbp+0h] BYREF
  __int128 v37; // [rsp+108h] [rbp+8h]
  __int128 v38; // [rsp+118h] [rbp+18h]
  __int128 v39; // [rsp+128h] [rbp+28h]
  __int64 v40; // [rsp+138h] [rbp+38h]

  Buffer = a3;
  InformationClass = a2;
  v5 = a1;
  v27 = a1;
  BytesReturned = a5;
  v36 = 0;
  v40 = 0;
  v37 = 0;
  P = 0;
  v38 = 0;
  v26 = 0;
  v39 = 0;
  Interval.QuadPart = 0;
  BufferSize = a4;
  memset(v34, 0, 0x48u);
  memset(v35, 0, 0x48u);
  ExInitializeFastOwnerEntry(v34);
  ExInitializeFastOwnerEntry(v35);
  *a5 = 0;
  while ( 1 )
  {
    LoadedLegacyFiltersList = FltpGetLoadedLegacyFiltersList(&P, &v26, &v36, 64);
    LegacyFilterInformation = LoadedLegacyFiltersList;
    if ( LoadedLegacyFiltersList != -1073741267 )
      break;
    Interval.QuadPart = -20000;
    KeDelayExecutionThread(0, 0, &Interval);
  }
  v8 = FltpDbgStatus(LoadedLegacyFiltersList, "minkernel\\fs\\filtermgr\\filter\\enumerationsup.c", 3329, 0);
  v9 = (char *)P;
  if ( v8 >= 0 && v26 )
  {
    v10 = 0;
    KeEnterCriticalRegion();
    LOBYTE(v11) = 1;
    ExAcquireFastResourceShared(qword_18003ED18, v34, v11);
    v12 = (void *)qword_18003ED80;
    v13 = qword_18003ED80 - 8;
    if ( (__int64 *)qword_18003ED80 == &qword_18003ED80 )
      v13 = 0;
    v14 = v26 - 1;
    if ( (__int64 *)qword_18003ED80 == &qword_18003ED80 )
      v12 = 0;
    P = v12;
    while ( 1 )
    {
      if ( v14 < 0 )
      {
        ExReleaseFastResource(qword_18003ED18, v34);
        KeLeaveCriticalRegion();
        LegacyFilterInformation = -2147483622;
        break;
      }
      v15 = 8LL * v14;
      if ( *(PVOID *)&v9[v15] == DriverObject )
      {
        if ( !v13 )
        {
          ExReleaseFastResource(qword_18003ED18, v34);
          KeLeaveCriticalRegion();
          LegacyFilterInformation = -1071906806;
          break;
        }
        KeEnterCriticalRegion();
        v16 = v13 + 72;
        LOBYTE(v17) = 1;
        ExAcquireFastResourceShared(v13 + 72, v35, v17);
        v18 = (_QWORD *)(v13 + 176);
        for ( i = *(_QWORD **)(v13 + 176); i != v18; i = (_QWORD *)*i )
        {
          v20 = FltObjectReference(i - 2);
          if ( (int)FltpDbgStatus(v20, "minkernel\\fs\\filtermgr\\filter\\enumerationsup.c", 3431, 3223060491LL) >= 0 )
          {
            if ( v10 == v27 )
            {
              ExReleaseFastResource(v16, v35);
              KeLeaveCriticalRegion();
              ExReleaseFastResource(qword_18003ED18, v34);
              KeLeaveCriticalRegion();
              FilterInformation = FltGetFilterInformation(
                                    (PFLT_FILTER)(i - 2),
                                    InformationClass,
                                    Buffer,
                                    BufferSize,
                                    BytesReturned);
              v24 = i - 2;
              LegacyFilterInformation = FilterInformation;
              FltObjectDereference(v24);
              goto LABEL_25;
            }
            FltObjectDereference(i - 2);
            ++v10;
          }
        }
        ExReleaseFastResource(v16, v35);
        KeLeaveCriticalRegion();
        v5 = v27;
        v21 = *(_QWORD *)P == (_QWORD)&qword_18003ED80;
        v22 = *(void **)P;
        if ( *(__int64 **)P == &qword_18003ED80 )
          v22 = 0;
        v13 = *(_QWORD *)P - 8LL;
        P = v22;
        if ( v21 )
          v13 = 0;
      }
      else
      {
        if ( v10 == v5 )
        {
          ExReleaseFastResource(qword_18003ED18, v34);
          KeLeaveCriticalRegion();
          LegacyFilterInformation = FltpGetLegacyFilterInformation(
                                      *(_QWORD *)&v9[v15],
                                      InformationClass,
                                      (_DWORD)Buffer,
                                      BufferSize,
                                      (__int64)BytesReturned);
          break;
        }
        ++v10;
      }
      --v14;
    }
  }
LABEL_25:
  FltpCleanupLoadedLegacyFiltersList(v9);
  return LegacyFilterInformation;
}

```

## disassembly

```asm
0x180073b50  push    rbp
0x180073b52  push    rbx
0x180073b53  push    rdi
0x180073b54  push    r12
0x180073b56  push    r13
0x180073b58  lea     rbp, [rsp-50h]
0x180073b5d  sub     rsp, 150h
0x180073b64  mov     rax, cs:__security_cookie
0x180073b6b  xor     rax, rsp
0x180073b6e  mov     [rbp+70h+var_30], rax
0x180073b72  mov     rbx, [rbp+70h+arg_20]
0x180073b79  xor     edi, edi
0x180073b7b  xorps   xmm0, xmm0
0x180073b7e  mov     [rsp+170h+Buffer], r8
0x180073b83  mov     [rsp+170h+InformationClass], edx
0x180073b87  mov     r12d, ecx
0x180073b8a  mov     [rsp+170h+var_13C], ecx
0x180073b8e  xor     eax, eax
0x180073b90  xor     edx, edx; Val
0x180073b92  mov     [rsp+170h+var_120], rbx
0x180073b97  mov     r8d, 48h ; 'H'; Size
0x180073b9d  mov     [rbp+70h+var_70], rdi
0x180073ba1  lea     rcx, [rsp+170h+var_110]; void *
0x180073ba6  mov     [rbp+70h+var_38], rax
0x180073baa  movups  [rbp+70h+var_68], xmm0
0x180073bae  mov     [rsp+170h+P], rdi
0x180073bb3  movups  [rbp+70h+var_58], xmm0
0x180073bb7  mov     [rsp+170h+var_140], edi
0x180073bbb  movups  [rbp+70h+var_48], xmm0
0x180073bbf  mov     qword ptr [rsp+170h+Interval], rdi
0x180073bc4  mov     [rsp+170h+BufferSize], r9d
0x180073bc9  call    memset
0x180073bce  xor     edx, edx; Val
0x180073bd0  lea     rcx, [rbp+70h+var_C0]; void *
0x180073bd4  mov     r8d, 48h ; 'H'; Size
0x180073bda  call    memset
0x180073bdf  lea     rcx, [rsp+170h+var_110]
0x180073be4  call    cs:__imp_ExInitializeFastOwnerEntry
0x180073beb  nop     dword ptr [rax+rax+00h]
0x180073bf0  lea     rcx, [rbp+70h+var_C0]
0x180073bf4  call    cs:__imp_ExInitializeFastOwnerEntry
0x180073bfb  nop     dword ptr [rax+rax+00h]
0x180073c00  mov     [rbx], edi
0x180073c02  mov     r9d, 40h ; '@'
0x180073c08  lea     r8, [rbp+70h+var_70]
0x180073c0c  lea     rdx, [rsp+170h+var_140]
0x180073c11  lea     rcx, [rsp+170h+P]
0x180073c16  call    FltpGetLoadedLegacyFiltersList
0x180073c1b  mov     ebx, eax
0x180073c1d  cmp     eax, 0C000022Dh
0x180073c22  jz      loc_180073E77
0x180073c28  mov     [rsp+170h+arg_0], rsi
0x180073c30  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x180073c37  mov     [rsp+170h+arg_8], r14
0x180073c3f  mov     r8d, 0D01h
0x180073c45  xor     r9d, r9d
0x180073c48  mov     [rsp+170h+arg_18], r15
0x180073c50  mov     ecx, eax
0x180073c52  call    FltpDbgStatus
0x180073c57  mov     r13, [rsp+170h+P]
0x180073c5c  mov     edx, [rsp+170h+var_140]
0x180073c60  test    eax, eax
0x180073c62  js      loc_180073E35
0x180073c68  test    edx, edx
0x180073c6a  jz      loc_180073E35
0x180073c70  mov     r15d, edi
0x180073c73  call    cs:__imp_KeEnterCriticalRegion
0x180073c7a  nop     dword ptr [rax+rax+00h]
0x180073c7f  mov     r8b, 1
0x180073c82  lea     rdx, [rsp+170h+var_110]
0x180073c87  lea     rcx, qword_18003ED18
0x180073c8e  call    cs:__imp_ExAcquireFastResourceShared
0x180073c95  nop     dword ptr [rax+rax+00h]
0x180073c9a  mov     r14, cs:qword_18003ED80
0x180073ca1  lea     rcx, qword_18003ED80
0x180073ca8  mov     esi, [rsp+170h+var_140]
0x180073cac  cmp     r14, rcx
0x180073caf  lea     rbx, [r14-8]
0x180073cb3  cmovz   rbx, rdi
0x180073cb7  dec     esi
0x180073cb9  cmp     r14, rcx
0x180073cbc  cmovz   r14, rdi
0x180073cc0  mov     [rsp+170h+P], r14
0x180073cc5  test    esi, esi
0x180073cc7  js      loc_180073ED9
0x180073ccd  movsxd  rax, esi
0x180073cd0  lea     rdi, ds:0[rax*8]
0x180073cd8  mov     rax, cs:DriverObject
0x180073cdf  cmp     [rdi+r13], rax
0x180073ce3  jnz     loc_180073E9A
0x180073ce9  test    rbx, rbx
0x180073cec  jz      loc_180073EAB
0x180073cf2  call    cs:__imp_KeEnterCriticalRegion
0x180073cf9  nop     dword ptr [rax+rax+00h]
0x180073cfe  lea     r12, [rbx+48h]
0x180073d02  mov     r8b, 1
0x180073d05  mov     rcx, r12
0x180073d08  lea     rdx, [rbp+70h+var_C0]
0x180073d0c  call    cs:__imp_ExAcquireFastResourceShared
0x180073d13  nop     dword ptr [rax+rax+00h]
0x180073d18  lea     rdi, [rbx+0B0h]
0x180073d1f  mov     rbx, [rdi]
0x180073d22  cmp     rbx, rdi
0x180073d25  jz      short loc_180073D71
0x180073d27  lea     r14, [rbx-10h]
0x180073d2b  mov     rcx, r14; FltObject
0x180073d2e  call    FltObjectReference
0x180073d33  mov     ecx, eax
0x180073d35  mov     [rsp+170h+BytesReturned], 0
0x180073d3e  mov     r9d, 0C01C000Bh
0x180073d44  lea     rdx, aMinkernelFsFil_29; "minkernel\\fs\\filtermgr\\filter\\enume"...
0x180073d4b  mov     r8d, 0D67h
0x180073d51  call    FltpDbgStatus
0x180073d56  test    eax, eax
0x180073d58  js      short loc_180073D6C
0x180073d5a  cmp     r15d, [rsp+170h+var_13C]
0x180073d5f  jz      short loc_180073DC4
0x180073d61  mov     rcx, r14; FltObject
0x180073d64  call    FltObjectDereference
0x180073d69  inc     r15d
0x180073d6c  mov     rbx, [rbx]
0x180073d6f  jmp     short loc_180073D22
0x180073d71  lea     rdx, [rbp+70h+var_C0]
0x180073d75  mov     rcx, r12
0x180073d78  call    cs:__imp_ExReleaseFastResource
0x180073d7f  nop     dword ptr [rax+rax+00h]
0x180073d84  call    cs:__imp_KeLeaveCriticalRegion
0x180073d8b  nop     dword ptr [rax+rax+00h]
0x180073d90  mov     rax, [rsp+170h+P]
0x180073d95  lea     r8, qword_18003ED80
0x180073d9c  mov     r12d, [rsp+170h+var_13C]
0x180073da1  mov     rcx, [rax]
0x180073da4  xor     eax, eax
0x180073da6  cmp     rcx, r8
0x180073da9  mov     rdx, rcx
0x180073dac  cmovz   rdx, rax
0x180073db0  lea     rbx, [rcx-8]
0x180073db4  mov     [rsp+170h+P], rdx
0x180073db9  cmovz   rbx, rax
0x180073dbd  dec     esi
0x180073dbf  jmp     loc_180073CC5
0x180073dc4  lea     rdx, [rbp+70h+var_C0]
0x180073dc8  mov     rcx, r12
0x180073dcb  call    cs:__imp_ExReleaseFastResource
0x180073dd2  nop     dword ptr [rax+rax+00h]
0x180073dd7  call    cs:__imp_KeLeaveCriticalRegion
0x180073dde  nop     dword ptr [rax+rax+00h]
0x180073de3  lea     rdx, [rsp+170h+var_110]
0x180073de8  lea     rcx, qword_18003ED18
0x180073def  call    cs:__imp_ExReleaseFastResource
0x180073df6  nop     dword ptr [rax+rax+00h]
0x180073dfb  call    cs:__imp_KeLeaveCriticalRegion
0x180073e02  nop     dword ptr [rax+rax+00h]
0x180073e07  mov     rax, [rsp+170h+var_120]
0x180073e0c  mov     rcx, r14; Filter
0x180073e0f  mov     r9d, [rsp+170h+BufferSize]; BufferSize
0x180073e14  mov     r8, [rsp+170h+Buffer]; Buffer
0x180073e19  mov     edx, [rsp+170h+InformationClass]; InformationClass
0x180073e1d  mov     [rsp+170h+BytesReturned], rax; BytesReturned
0x180073e22  call    FltGetFilterInformation
0x180073e27  mov     rcx, r14; FltObject
0x180073e2a  mov     ebx, eax
0x180073e2c  call    FltObjectDereference
0x180073e31  mov     edx, [rsp+170h+var_140]
0x180073e35  lea     r8, [rbp+70h+var_70]
0x180073e39  mov     rcx, r13; P
0x180073e3c  call    FltpCleanupLoadedLegacyFiltersList
0x180073e41  mov     r15, [rsp+170h+arg_18]
0x180073e49  mov     eax, ebx
0x180073e4b  mov     r14, [rsp+170h+arg_8]
0x180073e53  mov     rsi, [rsp+170h+arg_0]
0x180073e5b  mov     rcx, [rbp+70h+var_30]
0x180073e5f  xor     rcx, rsp; StackCookie
0x180073e62  call    __security_check_cookie
0x180073e67  add     rsp, 150h
0x180073e6e  pop     r13
0x180073e70  pop     r12
0x180073e72  pop     rdi
0x180073e73  pop     rbx
0x180073e74  pop     rbp
0x180073e75  retn
0x180073e77  lea     r8, [rsp+170h+Interval]; Interval
0x180073e7c  mov     qword ptr [rsp+170h+Interval], 0FFFFFFFFFFFFB1E0h
0x180073e85  xor     edx, edx; Alertable
0x180073e87  xor     ecx, ecx; WaitMode
0x180073e89  call    cs:__imp_KeDelayExecutionThread
0x180073e90  nop     dword ptr [rax+rax+00h]
0x180073e95  jmp     loc_180073C02
0x180073e9a  cmp     r15d, r12d
0x180073e9d  jz      loc_18007B1D4
0x180073ea3  inc     r15d
0x180073ea6  jmp     loc_180073DBD
0x180073eab  lea     rdx, [rsp+170h+var_110]
0x180073eb0  lea     rcx, qword_18003ED18
0x180073eb7  call    cs:__imp_ExReleaseFastResource
0x180073ebe  nop     dword ptr [rax+rax+00h]
0x180073ec3  call    cs:__imp_KeLeaveCriticalRegion
0x180073eca  nop     dword ptr [rax+rax+00h]
0x180073ecf  mov     ebx, 0C01C000Ah
0x180073ed4  jmp     loc_180073E31
0x180073ed9  lea     rdx, [rsp+170h+var_110]
0x180073ede  lea     rcx, qword_18003ED18
0x180073ee5  call    cs:__imp_ExReleaseFastResource
0x180073eec  nop     dword ptr [rax+rax+00h]
0x180073ef1  call    cs:__imp_KeLeaveCriticalRegion
0x180073ef8  nop     dword ptr [rax+rax+00h]
0x180073efd  mov     ebx, 8000001Ah
0x180073f02  jmp     loc_180073E31
0x18007b1d4  lea     rdx, [rsp+170h+var_110]
0x18007b1d9  lea     rcx, qword_18003ED18
0x18007b1e0  call    cs:__imp_ExReleaseFastResource
0x18007b1e7  nop     dword ptr [rax+rax+00h]
0x18007b1ec  call    cs:__imp_KeLeaveCriticalRegion
0x18007b1f3  nop     dword ptr [rax+rax+00h]
0x18007b1f8  mov     rax, [rsp+170h+var_120]
0x18007b1fd  mov     r9d, [rsp+170h+BufferSize]
0x18007b202  mov     r8, [rsp+170h+Buffer]
0x18007b207  mov     edx, [rsp+170h+InformationClass]
0x18007b20b  mov     rcx, [rdi+r13]
0x18007b20f  mov     [rsp+170h+BytesReturned], rax
0x18007b214  call    FltpGetLegacyFilterInformation
0x18007b219  mov     ebx, eax
0x18007b21b  jmp     loc_180073E31
```
