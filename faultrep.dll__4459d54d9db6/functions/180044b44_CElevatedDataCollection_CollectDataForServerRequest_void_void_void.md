# CElevatedDataCollection::CollectDataForServerRequest(void *,void *,void *)

- ea: `0x180044b44`
- end: `0x180044f8c`
- name: `?CollectDataForServerRequest@CElevatedDataCollection@@QEAAJPEAX00@Z`
- size: `1096`
- prototype: `__int64 __fastcall(const wchar_t **this, void *, HANDLE Process, const wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001611c`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18004323c`
- `0x180043ec4`
- `0x18004415c`
- `0x1800445c4`
- `0x180044b44`
- `0x180044f94`
- `0x180045774`
- `0x180045dd8`
- `0x180045ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180044b8a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180044b8a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044ed0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044f16`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044ed0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180044f16`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180044d44`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180044d44`

## string_xrefs

- `0x180044dd3`: `ReserveMachineQueueDirectory failed: 0x%x`

## pseudocode

```c
__int64 __fastcall CElevatedDataCollection::CollectDataForServerRequest(
        const wchar_t **this,
        void *a2,
        HANDLE Process,
        const wchar_t *a4)
{
  void *v7; // r15
  DWORD ProcessId; // eax
  DWORD v9; // edi
  int v11; // eax
  unsigned int v12; // edi
  bool v13; // zf
  unsigned int v14; // r15d
  unsigned int i; // ecx
  int v16; // edx
  __int64 v17; // rax
  unsigned int j; // ecx
  int v19; // edx
  __int64 v20; // rax
  HRESULT v21; // eax
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  int v25; // eax
  unsigned int k; // ebp
  int v27; // eax
  int v28; // eax
  const wchar_t *v29; // rdx
  int v30; // eax
  _OWORD v32[2]; // [rsp+38h] [rbp-70h] BYREF
  int v33; // [rsp+58h] [rbp-50h]

  v33 = 0;
  memset(v32, 0, sizeof(v32));
  v7 = a2;
  ProcessId = GetProcessId(Process);
  v9 = ProcessId;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
    return 2147942487LL;
  }
  if ( *((_DWORD *)this + 118) == 13 )
  {
    v11 = CElevatedDataCollection::AddCrossProcessPid(
            (CElevatedDataCollection *)this,
            ProcessId,
            0,
            1073741855,
            0,
            ProcessId);
    if ( v11 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v11);
    }
  }
  CElevatedDataCollection::FinalizePendingReflectionDumps((CElevatedDataCollection *)this);
  if ( this[2] == this[3]
    && this[6] == this[7]
    && this[10] == this[11]
    && this[14] == this[15]
    && this[18] == this[19]
    && this[22] == this[23]
    && !*((_DWORD *)this + 54)
    && !*((_DWORD *)this + 86)
    && !*((_DWORD *)this + 179) )
  {
    v12 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids);
    goto LABEL_68;
  }
  v13 = *((_DWORD *)this + 118) == 13;
  v14 = 1;
  *this = (const wchar_t *)a2;
  this[1] = a4;
  if ( !v13 )
    LODWORD(v32[0]) = v9;
  for ( i = 0; i < 4; ++i )
  {
    if ( v14 >= 9 )
      break;
    v16 = (int)this[4 * i + 27];
    if ( v16 )
    {
      v17 = v14++;
      *((_DWORD *)v32 + v17) = v16;
    }
  }
  for ( j = 0; j < 4; ++j )
  {
    if ( v14 >= 9 )
      break;
    v19 = (int)this[4 * j + 43];
    if ( v19 )
    {
      v20 = v14++;
      *((_DWORD *)v32 + v20) = v19;
    }
  }
  v21 = CoInitializeEx(0, 0);
  v12 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v21);
    goto LABEL_67;
  }
  if ( *((_DWORD *)this + 179)
    || *((_DWORD *)this + 86)
    || this[22] != this[23]
    || this[18] != this[19]
    || this[14] != this[15] )
  {
    v22 = CElevatedDataCollection::ReserveMachineQueueDirectory((CElevatedDataCollection *)this, (void *)*this);
    v12 = v22;
    if ( v22 < 0 )
    {
      CElevatedDataCollection::LogDataCollectionStatus(
        (CElevatedDataCollection *)this,
        L"ReserveMachineQueueDirectory failed: 0x%x",
        (unsigned int)v22);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v24 = 74;
      goto LABEL_48;
    }
  }
  if ( !*((_DWORD *)this + 179)
    || (v25 = CElevatedDataCollection::CollectKernelDump(this, Process, *((unsigned int *)this + 181)),
        v12 = v25,
        v25 >= 0) )
  {
    for ( k = 0; k < 6; ++k )
    {
      v27 = CElevatedDataCollection::CollectCrossProcessModuleDumps(this, v32, v14, k);
      v12 = v27;
      if ( v27 < 0 )
      {
        CElevatedDataCollection::LogDataCollectionStatus(
          (CElevatedDataCollection *)this,
          L"CollectCrossProcessModuleDumps failed: 0x%x",
          (unsigned int)v27);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, k, v12);
        goto LABEL_66;
      }
    }
    if ( !*((_DWORD *)this + 118)
      || (v28 = CElevatedDataCollection::CollectCrossProcessDumps((CElevatedDataCollection *)this), v12 = v28, v28 >= 0) )
    {
      CoUninitialize();
      v12 = 0;
      goto LABEL_67;
    }
    CElevatedDataCollection::LogDataCollectionStatus(
      (CElevatedDataCollection *)this,
      L"CollectCrossProcessDumps failed: 0x%x",
      (unsigned int)v28);
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v24 = 77;
      goto LABEL_48;
    }
    goto LABEL_66;
  }
  CElevatedDataCollection::LogDataCollectionStatus(
    (CElevatedDataCollection *)this,
    L"KernelDump failed: 0x%x",
    (unsigned int)v25);
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v24 = 75;
LABEL_48:
    WPP_SF_d(v23[2], v24, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids, v12);
  }
LABEL_66:
  CoUninitialize();
LABEL_67:
  v7 = a2;
LABEL_68:
  v29 = this[100];
  if ( v29 != this[101] )
  {
    v30 = AddStringBufferToReport(v7, v29, L"ElevatedDataCollectionStatus.txt", 0);
    if ( v30 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        WPP_b503122a8e753e2116c8130bd5de03da_Traceguids,
        (unsigned int)v30);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180044b44  push    rbx
0x180044b46  push    rbp
0x180044b47  push    rdi
0x180044b48  push    r12
0x180044b4a  push    r13
0x180044b4c  push    r14
0x180044b4e  push    r15
0x180044b50  sub     rsp, 70h
0x180044b54  mov     rax, cs:__security_cookie
0x180044b5b  xor     rax, rsp
0x180044b5e  mov     [rsp+0A8h+var_48], rax
0x180044b63  xorps   xmm0, xmm0
0x180044b66  mov     [rsp+0A8h+var_78], rdx
0x180044b6b  mov     rbx, rcx
0x180044b6e  xor     eax, eax
0x180044b70  mov     rcx, r8; Process
0x180044b73  mov     [rsp+0A8h+var_50], eax
0x180044b77  movups  [rsp+0A8h+var_70], xmm0
0x180044b7c  mov     rbp, r9
0x180044b7f  mov     r13, r8
0x180044b82  movups  [rsp+0A8h+var_60], xmm0
0x180044b87  mov     r15, rdx
0x180044b8a  call    cs:__imp_GetProcessId
0x180044b90  mov     edi, eax
0x180044b92  test    r15, r15
0x180044b95  jnz     short loc_180044BCE
0x180044b97  mov     rcx, cs:WPP_GLOBAL_Control
0x180044b9e  lea     r14, WPP_GLOBAL_Control
0x180044ba5  cmp     rcx, r14
0x180044ba8  jz      short loc_180044BC4
0x180044baa  test    byte ptr [rcx+1Ch], 1
0x180044bae  jz      short loc_180044BC4
0x180044bb0  mov     rcx, [rcx+10h]
0x180044bb4  lea     edx, [r15+46h]
0x180044bb8  lea     r8, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x180044bbf  call    WPP_SF_
0x180044bc4  mov     eax, 80070057h
0x180044bc9  jmp     loc_180044F6F
0x180044bce  cmp     dword ptr [rbx+1D8h], 0Dh
0x180044bd5  lea     r12, WPP_b503122a8e753e2116c8130bd5de03da_Traceguids
0x180044bdc  lea     r14, WPP_GLOBAL_Control
0x180044be3  jnz     short loc_180044C2F
0x180044be5  mov     [rsp+0A8h+var_80], edi; unsigned int
0x180044be9  mov     r9d, 4000001Fh; unsigned int
0x180044bef  xor     r8d, r8d; unsigned int
0x180044bf2  mov     [rsp+0A8h+var_88], 0; wchar_t *
0x180044bfb  mov     edx, edi; dwProcessId
0x180044bfd  mov     rcx, rbx; this
0x180044c00  call    ?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z; CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)
0x180044c05  test    eax, eax
0x180044c07  jns     short loc_180044C2F
0x180044c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180044c10  cmp     rcx, r14
0x180044c13  jz      short loc_180044C2F
0x180044c15  test    byte ptr [rcx+1Ch], 2
0x180044c19  jz      short loc_180044C2F
0x180044c1b  mov     rcx, [rcx+10h]
0x180044c1f  mov     edx, 47h ; 'G'
0x180044c24  mov     r9d, eax
0x180044c27  mov     r8, r12
0x180044c2a  call    WPP_SF_d
0x180044c2f  mov     rcx, rbx; this
0x180044c32  call    ?FinalizePendingReflectionDumps@CElevatedDataCollection@@IEAAXXZ; CElevatedDataCollection::FinalizePendingReflectionDumps(void)
0x180044c37  mov     rax, [rbx+18h]
0x180044c3b  cmp     [rbx+10h], rax
0x180044c3f  jnz     loc_180044CCD
0x180044c45  mov     rax, [rbx+38h]
0x180044c49  cmp     [rbx+30h], rax
0x180044c4d  jnz     short loc_180044CCD
0x180044c4f  mov     rax, [rbx+58h]
0x180044c53  cmp     [rbx+50h], rax
0x180044c57  jnz     short loc_180044CCD
0x180044c59  mov     rax, [rbx+78h]
0x180044c5d  cmp     [rbx+70h], rax
0x180044c61  jnz     short loc_180044CCD
0x180044c63  mov     rax, [rbx+98h]
0x180044c6a  cmp     [rbx+90h], rax
0x180044c71  jnz     short loc_180044CCD
0x180044c73  mov     rax, [rbx+0B8h]
0x180044c7a  cmp     [rbx+0B0h], rax
0x180044c81  jnz     short loc_180044CCD
0x180044c83  xor     eax, eax
0x180044c85  cmp     [rbx+0D8h], eax
0x180044c8b  jnz     short loc_180044CCD
0x180044c8d  cmp     [rbx+158h], eax
0x180044c93  jnz     short loc_180044CCD
0x180044c95  cmp     [rbx+2CCh], eax
0x180044c9b  jnz     short loc_180044CCD
0x180044c9d  xor     edi, edi
0x180044c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ca6  cmp     rcx, r14
0x180044ca9  jz      loc_180044F21
0x180044caf  test    byte ptr [rcx+1Ch], 4
0x180044cb3  jz      loc_180044F21
0x180044cb9  mov     rcx, [rcx+10h]
0x180044cbd  lea     edx, [rax+48h]
0x180044cc0  mov     r8, r12
0x180044cc3  call    WPP_SF_
0x180044cc8  jmp     loc_180044F21
0x180044ccd  cmp     dword ptr [rbx+1D8h], 0Dh
0x180044cd4  mov     r15d, 1
0x180044cda  mov     rax, [rsp+0A8h+var_78]
0x180044cdf  mov     [rbx], rax
0x180044ce2  mov     [rbx+8], rbp
0x180044ce6  jz      short loc_180044CEC
0x180044ce8  mov     dword ptr [rsp+0A8h+var_70], edi
0x180044cec  xor     ecx, ecx
0x180044cee  cmp     r15d, 9
0x180044cf2  jnb     short loc_180044D16
0x180044cf4  mov     eax, ecx
0x180044cf6  shl     rax, 5
0x180044cfa  mov     edx, [rax+rbx+0D8h]
0x180044d01  test    edx, edx
0x180044d03  jz      short loc_180044D0F
0x180044d05  mov     eax, r15d
0x180044d08  inc     r15d
0x180044d0b  mov     dword ptr [rsp+rax*4+0A8h+var_70], edx
0x180044d0f  inc     ecx
0x180044d11  cmp     ecx, 4
0x180044d14  jb      short loc_180044CEE
0x180044d16  xor     ecx, ecx
0x180044d18  cmp     r15d, 9
0x180044d1c  jnb     short loc_180044D40
0x180044d1e  mov     eax, ecx
0x180044d20  shl     rax, 5
0x180044d24  mov     edx, [rax+rbx+158h]
0x180044d2b  test    edx, edx
0x180044d2d  jz      short loc_180044D39
0x180044d2f  mov     eax, r15d
0x180044d32  inc     r15d
0x180044d35  mov     dword ptr [rsp+rax*4+0A8h+var_70], edx
0x180044d39  inc     ecx
0x180044d3b  cmp     ecx, 4
0x180044d3e  jb      short loc_180044D18
0x180044d40  xor     edx, edx; dwCoInit
0x180044d42  xor     ecx, ecx; pvReserved
0x180044d44  call    cs:__imp_CoInitializeEx
0x180044d4a  mov     edi, eax
0x180044d4c  test    eax, eax
0x180044d4e  jns     short loc_180044D83
0x180044d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180044d57  cmp     rcx, r14
0x180044d5a  jz      loc_180044F1C
0x180044d60  test    byte ptr [rcx+1Ch], 1
0x180044d64  jz      loc_180044F1C
0x180044d6a  mov     rcx, [rcx+10h]
0x180044d6e  mov     edx, 49h ; 'I'
0x180044d73  mov     r9d, eax
0x180044d76  mov     r8, r12
0x180044d79  call    WPP_SF_d
0x180044d7e  jmp     loc_180044F1C
0x180044d83  cmp     dword ptr [rbx+2CCh], 0
0x180044d8a  jnz     short loc_180044DBF
0x180044d8c  cmp     dword ptr [rbx+158h], 0
0x180044d93  jnz     short loc_180044DBF
0x180044d95  mov     rax, [rbx+0B8h]
0x180044d9c  cmp     [rbx+0B0h], rax
0x180044da3  jnz     short loc_180044DBF
0x180044da5  mov     rax, [rbx+98h]
0x180044dac  cmp     [rbx+90h], rax
0x180044db3  jnz     short loc_180044DBF
0x180044db5  mov     rax, [rbx+78h]
0x180044db9  cmp     [rbx+70h], rax
0x180044dbd  jz      short loc_180044E15
0x180044dbf  mov     rdx, [rbx]; void *
0x180044dc2  mov     rcx, rbx; this
0x180044dc5  call    ?ReserveMachineQueueDirectory@CElevatedDataCollection@@IEAAJPEAX@Z; CElevatedDataCollection::ReserveMachineQueueDirectory(void *)
0x180044dca  mov     edi, eax
0x180044dcc  test    eax, eax
0x180044dce  jns     short loc_180044E15
0x180044dd0  mov     r8d, eax
0x180044dd3  lea     rdx, aReservemachine; "ReserveMachineQueueDirectory failed: 0x"...
0x180044dda  mov     rcx, rbx; this
0x180044ddd  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x180044de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180044de9  cmp     rcx, r14
0x180044dec  jz      loc_180044F16
0x180044df2  test    byte ptr [rcx+1Ch], 1
0x180044df6  jz      loc_180044F16
0x180044dfc  mov     edx, 4Ah ; 'J'
0x180044e01  mov     rcx, [rcx+10h]
0x180044e05  mov     r9d, edi
0x180044e08  mov     r8, r12
0x180044e0b  call    WPP_SF_d
0x180044e10  jmp     loc_180044F16
0x180044e15  cmp     dword ptr [rbx+2CCh], 0
0x180044e1c  jz      short loc_180044E69
0x180044e1e  mov     r8d, [rbx+2D4h]
0x180044e25  mov     rdx, r13
0x180044e28  mov     rcx, rbx
0x180044e2b  call    ?CollectKernelDump@CElevatedDataCollection@@IEAAJPEAXW4FAULTREP_LIVEKERNEL_DUMPTYPE@@@Z; CElevatedDataCollection::CollectKernelDump(void *,FAULTREP_LIVEKERNEL_DUMPTYPE)
0x180044e30  mov     edi, eax
0x180044e32  test    eax, eax
0x180044e34  jns     short loc_180044E69
0x180044e36  mov     r8d, eax
0x180044e39  lea     rdx, aKerneldumpFail; "KernelDump failed: 0x%x"
0x180044e40  mov     rcx, rbx; this
0x180044e43  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x180044e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180044e4f  cmp     rcx, r14
0x180044e52  jz      loc_180044F16
0x180044e58  test    byte ptr [rcx+1Ch], 1
0x180044e5c  jz      loc_180044F16
0x180044e62  mov     edx, 4Bh ; 'K'
0x180044e67  jmp     short loc_180044E01
0x180044e69  xor     ebp, ebp
0x180044e6b  mov     r9d, ebp
0x180044e6e  lea     rdx, [rsp+0A8h+var_70]
0x180044e73  mov     r8d, r15d
0x180044e76  mov     rcx, rbx
0x180044e79  call    ?CollectCrossProcessModuleDumps@CElevatedDataCollection@@IEAAJPEAKKW4FAULTREP_CROSSPROCESS_DUMPTYPE@@@Z; CElevatedDataCollection::CollectCrossProcessModuleDumps(ulong *,ulong,FAULTREP_CROSSPROCESS_DUMPTYPE)
0x180044e7e  mov     edi, eax
0x180044e80  test    eax, eax
0x180044e82  js      short loc_180044EDA
0x180044e84  inc     ebp
0x180044e86  cmp     ebp, 6
0x180044e89  jb      short loc_180044E6B
0x180044e8b  cmp     dword ptr [rbx+1D8h], 0
0x180044e92  jz      short loc_180044ED0
0x180044e94  mov     rcx, rbx; this
0x180044e97  call    ?CollectCrossProcessDumps@CElevatedDataCollection@@IEAAJXZ; CElevatedDataCollection::CollectCrossProcessDumps(void)
0x180044e9c  mov     edi, eax
0x180044e9e  test    eax, eax
0x180044ea0  jns     short loc_180044ED0
0x180044ea2  mov     r8d, eax
0x180044ea5  lea     rdx, aCollectcrosspr; "CollectCrossProcessDumps failed: 0x%x"
0x180044eac  mov     rcx, rbx; this
0x180044eaf  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x180044eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ebb  cmp     rcx, r14
0x180044ebe  jz      short loc_180044F16
0x180044ec0  test    byte ptr [rcx+1Ch], 1
0x180044ec4  jz      short loc_180044F16
0x180044ec6  mov     edx, 4Dh ; 'M'
0x180044ecb  jmp     loc_180044E01
0x180044ed0  call    cs:__imp_CoUninitialize
0x180044ed6  xor     edi, edi
0x180044ed8  jmp     short loc_180044F1C
0x180044eda  mov     r8d, edi
0x180044edd  lea     rdx, aCollectcrosspr_0; "CollectCrossProcessModuleDumps failed: "...
0x180044ee4  mov     rcx, rbx; this
0x180044ee7  call    ?LogDataCollectionStatus@CElevatedDataCollection@@IEAAJPEB_WZZ; CElevatedDataCollection::LogDataCollectionStatus(wchar_t const *,...)
0x180044eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180044ef3  cmp     rcx, r14
0x180044ef6  jz      short loc_180044F16
0x180044ef8  test    byte ptr [rcx+1Ch], 1
0x180044efc  jz      short loc_180044F16
0x180044efe  mov     rcx, [rcx+10h]
0x180044f02  mov     edx, 4Ch ; 'L'
0x180044f07  mov     r9d, ebp
0x180044f0a  mov     dword ptr [rsp+0A8h+var_88], edi
0x180044f0e  mov     r8, r12
0x180044f11  call    WPP_SF_Dd
0x180044f16  call    cs:__imp_CoUninitialize
0x180044f1c  mov     r15, [rsp+0A8h+var_78]
0x180044f21  mov     rdx, [rbx+320h]; wchar_t *
0x180044f28  cmp     rdx, [rbx+328h]
0x180044f2f  jz      short loc_180044F6D
0x180044f31  xor     r9d, r9d; wchar_t *
0x180044f34  lea     r8, aElevateddataco; "ElevatedDataCollectionStatus.txt"
0x180044f3b  mov     rcx, r15; void *
0x180044f3e  call    ?AddStringBufferToReport@@YAJPEAXPEB_W11@Z; AddStringBufferToReport(void *,wchar_t const *,wchar_t const *,wchar_t const *)
0x180044f43  test    eax, eax
0x180044f45  jns     short loc_180044F6D
0x180044f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180044f4e  cmp     rcx, r14
0x180044f51  jz      short loc_180044F6D
0x180044f53  test    byte ptr [rcx+1Ch], 1
0x180044f57  jz      short loc_180044F6D
0x180044f59  mov     rcx, [rcx+10h]
0x180044f5d  mov     edx, 4Eh ; 'N'
0x180044f62  mov     r9d, eax
0x180044f65  mov     r8, r12
0x180044f68  call    WPP_SF_d
0x180044f6d  mov     eax, edi
0x180044f6f  mov     rcx, [rsp+0A8h+var_48]
0x180044f74  xor     rcx, rsp; StackCookie
0x180044f77  call    __security_check_cookie
0x180044f7c  add     rsp, 70h
0x180044f80  pop     r15
0x180044f82  pop     r14
0x180044f84  pop     r13
0x180044f86  pop     r12
0x180044f88  pop     rdi
0x180044f89  pop     rbp
0x180044f8a  pop     rbx
0x180044f8b  retn
```
