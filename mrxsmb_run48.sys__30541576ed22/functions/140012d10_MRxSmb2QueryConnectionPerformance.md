# MRxSmb2QueryConnectionPerformance

- ea: `0x140012d10`
- end: `0x14001346a`
- name: `MRxSmb2QueryConnectionPerformance`
- size: `1882`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140012d10`
- `0x140013470`
- `0x140037fa4`
- `0x14003838c`
- `0x140039fa8`
- `0x14003e14c`
- `0x140042290`
- `0x140059dc0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400131d9`
- `ntoskrnl!KeBugCheckEx` at `0x1400131d9`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012eb1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001316a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140013260`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140012eb1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001316a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140013260`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012d65`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140012d65`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012d75`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012d75`
- `rdbss!RxDiagnosticTrace` at `0x140012e72`
- `rdbss!RxDiagnosticTrace` at `0x140012e72`
- `NETIO!NsiGetAllParameters` at `0x140012f41`
- `NETIO!NsiGetAllParameters` at `0x140012f99`
- `NETIO!NsiGetAllParameters` at `0x140012f41`
- `NETIO!NsiGetAllParameters` at `0x140012f99`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryConnectionPerformance(__int64 a1)
{
  __int64 v1; // rax
  __int64 v3; // rsi
  __int64 v4; // rbx
  KIRQL v5; // r15
  __int64 v6; // rax
  __int64 v7; // rcx
  int *v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // rdi
  int **v11; // r8
  ULONG_PTR v12; // r8
  signed __int32 v13; // ebx
  int AllParameters; // ecx
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int128 v19; // [rsp+60h] [rbp-29h] BYREF
  __int128 v20; // [rsp+70h] [rbp-19h]
  __int64 v21; // [rsp+80h] [rbp-9h]
  __int128 v22; // [rsp+88h] [rbp-1h] BYREF

  v1 = *(_QWORD *)(a1 + 40);
  v3 = *(_QWORD *)(v1 + 24);
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v4 = *(_QWORD *)(v1 + 416);
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920));
  *(_DWORD *)(v3 + 2352) = (unsigned int)PsGetCurrentThreadId();
  if ( !*(_DWORD *)(v4 + 12) )
  {
    v6 = *(unsigned __int16 *)(v4 + 2);
    if ( (_WORD)v6 )
    {
      v7 = v4 + v6 + 8;
      if ( !v7 )
        goto LABEL_68;
    }
    else
    {
      v7 = 8;
    }
    v8 = *(int **)v7;
    if ( *(_QWORD *)v7 )
    {
      v9 = *(_QWORD **)(v7 + 8);
      if ( v9 )
      {
        if ( *((_QWORD *)v8 + 1) == v7 )
        {
          v10 = 0;
          if ( *v9 == v7 )
          {
            while ( v8 != (int *)v7 )
            {
              if ( !v8 )
                goto LABEL_68;
              if ( !*(_QWORD *)v8 )
                goto LABEL_68;
              v11 = (int **)*((_QWORD *)v8 + 1);
              if ( !v11 || *(int **)(*(_QWORD *)v8 + 8LL) != v8 || *v11 != v8 )
                goto LABEL_68;
              v12 = (ULONG_PTR)(v8 - 100);
              if ( *(v8 - 98) < 0 )
                KeBugCheckEx(0x27u, 0xA0001u, v12, *(v8 - 98), 0);
              if ( *(_WORD *)v12 != 0xE2FF )
              {
                if ( v8 != (int *)400 )
                {
                  v10 = *(_QWORD *)(v12 + 392);
                  if ( v10 )
                  {
                    v13 = _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
                    RxDiagnosticTrace(*(_QWORD *)(v10 + 16), 16, "Ref %d->%d", v13 - 1, v13);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_qDD(
                        WPP_GLOBAL_Control->AttachedDevice,
                        28,
                        &WPP_39c16dc859303064795977fd63584161_Traceguids,
                        v10,
                        v13 - 1,
                        v13);
                      *(_DWORD *)(v3 + 2352) = -1;
                      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v5);
                      goto LABEL_21;
                    }
                  }
                }
                break;
              }
              v8 = *(int **)v8;
            }
            *(_DWORD *)(v3 + 2352) = -1;
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v5);
            if ( !v10 )
              return (unsigned int)-1073741300;
LABEL_21:
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 120LL) = 0;
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 112LL) = 0;
            if ( *(_BYTE *)(v10 + 264) && *(_BYTE *)(v10 + 324) )
            {
              AllParameters = NsiGetAllParameters(1, &NPI_MS_TCP_MODULEID, 14, v10 + 400, 56, 0, 0, &v19, 40, 0, 0);
              if ( AllParameters >= 0 )
                AllParameters = NsiGetAllParameters(1, &NPI_MS_TCP_MODULEID, 15, v10 + 400, 56, 0, 0, &v22, 16, 0, 0);
              v16 = AllParameters;
              if ( AllParameters >= 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      WPP_SF_I(WPP_GLOBAL_Control->AttachedDevice, 20, v15, v19);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        WPP_SF_I(WPP_GLOBAL_Control->AttachedDevice, 21, v15, v20);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            22,
                            &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                            (_BYTE)v21 != 0);
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                        {
                          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                            WPP_SF_(
                              WPP_GLOBAL_Control->AttachedDevice,
                              23,
                              &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids);
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                          {
                            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                              WPP_SF_I(WPP_GLOBAL_Control->AttachedDevice, 24, v15, *((_QWORD *)&v19 + 1));
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                            {
                              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                              {
                                WPP_SF_I(WPP_GLOBAL_Control->AttachedDevice, 25, v15, *((_QWORD *)&v20 + 1));
                              }
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                              {
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  26,
                                  &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                                  BYTE1(v21) != 0);
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                if ( (_BYTE)v21 )
                {
                  if ( BYTE1(v21) )
                  {
                    v17 = *((_QWORD *)&v19 + 1);
                    if ( (unsigned __int64)v19 < *((_QWORD *)&v19 + 1) )
                      v17 = v19;
                  }
                  else
                  {
                    v17 = v19;
                  }
                }
                else
                {
                  v17 = *((_QWORD *)&v19 + 1);
                  if ( !BYTE1(v21) && (unsigned __int64)v19 > *((_QWORD *)&v19 + 1) )
                    v17 = v19;
                }
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 112LL) = v17;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        28,
                        &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                        (unsigned int)v22);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                    {
                      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          29,
                          &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                          DWORD1(v22));
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                      {
                        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            30,
                            &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                            DWORD2(v22));
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            31,
                            &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                            HIDWORD(v22) / 0x3E8);
                        }
                      }
                    }
                  }
                }
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 32LL) + 120LL) = HIDWORD(v22) / 0x3E8;
LABEL_57:
                VctDereferenceEndpoint((PVOID)v10);
                return v16;
              }
            }
            else
            {
              v16 = -1073741822;
              AllParameters = -1073741822;
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                32,
                &WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
                a1,
                AllParameters);
            }
            goto LABEL_57;
          }
        }
      }
    }
LABEL_68:
    __fastfail(3u);
  }
  *(_DWORD *)(v3 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v3 + 1920), v5);
  return (unsigned int)-1073741300;
}

```

## disassembly

```asm
0x140012d10  push    rbp
0x140012d12  push    rbx
0x140012d13  push    rsi
0x140012d14  push    rdi
0x140012d15  push    r12
0x140012d17  push    r13
0x140012d19  push    r14
0x140012d1b  push    r15
0x140012d1d  lea     rbp, [rsp-1Fh]
0x140012d22  sub     rsp, 0A8h
0x140012d29  mov     rax, cs:__security_cookie
0x140012d30  xor     rax, rsp
0x140012d33  mov     [rbp+57h+var_48], rax
0x140012d37  mov     rax, [rcx+28h]
0x140012d3b  xorps   xmm0, xmm0
0x140012d3e  mov     r13, rcx
0x140012d41  xor     ecx, ecx
0x140012d43  mov     rsi, [rax+18h]
0x140012d47  mov     [rbp+57h+var_60], rcx
0x140012d4b  movups  [rbp+57h+var_80], xmm0
0x140012d4f  movups  [rbp+57h+var_70], xmm0
0x140012d53  lea     rcx, [rsi+780h]; SpinLock
0x140012d5a  movups  [rbp+57h+var_58], xmm0
0x140012d5e  mov     rbx, [rax+1A0h]
0x140012d65  call    cs:__imp_ExAcquireSpinLockExclusive
0x140012d6c  nop     dword ptr [rax+rax+00h]
0x140012d71  movzx   r15d, al
0x140012d75  call    cs:__imp_PsGetCurrentThreadId
0x140012d7c  nop     dword ptr [rax+rax+00h]
0x140012d81  mov     [rsi+930h], eax
0x140012d87  cmp     dword ptr [rbx+0Ch], 0
0x140012d8b  jnz     loc_140013155
0x140012d91  movzx   eax, word ptr [rbx+2]
0x140012d95  test    ax, ax
0x140012d98  jz      loc_1400131E6
0x140012d9e  lea     rcx, [rax+8]
0x140012da2  add     rcx, rbx
0x140012da5  jz      loc_1400131F0
0x140012dab  mov     rax, [rcx]
0x140012dae  test    rax, rax
0x140012db1  jz      loc_1400131F0
0x140012db7  mov     rdx, [rcx+8]
0x140012dbb  test    rdx, rdx
0x140012dbe  jz      loc_1400131F0
0x140012dc4  cmp     [rax+8], rcx
0x140012dc8  jnz     loc_1400131F0
0x140012dce  xor     edi, edi
0x140012dd0  cmp     [rdx], rcx
0x140012dd3  jnz     loc_1400131F0
0x140012dd9  mov     r9d, 0E2FFh
0x140012ddf  cmp     rax, rcx
0x140012de2  jz      loc_140012E9C
0x140012de8  test    rax, rax
0x140012deb  jz      loc_1400131F0
0x140012df1  mov     rdx, [rax]
0x140012df4  test    rdx, rdx
0x140012df7  jz      loc_1400131F0
0x140012dfd  mov     r8, [rax+8]
0x140012e01  test    r8, r8
0x140012e04  jz      loc_1400131F0
0x140012e0a  cmp     [rdx+8], rax
0x140012e0e  jnz     loc_1400131F0
0x140012e14  cmp     [r8], rax
0x140012e17  jnz     loc_1400131F0
0x140012e1d  lea     r8, [rax-190h]; BugCheckParameter2
0x140012e24  movsxd  rdx, dword ptr [r8+8]
0x140012e28  test    edx, edx
0x140012e2a  js      loc_1400131C7
0x140012e30  cmp     [r8], r9w
0x140012e34  jz      loc_140013206
0x140012e3a  test    r8, r8
0x140012e3d  jz      short loc_140012E9C
0x140012e3f  mov     rdi, [r8+188h]
0x140012e46  test    rdi, rdi
0x140012e49  jz      short loc_140012E9C
0x140012e4b  mov     ebx, 1
0x140012e50  lock xadd [rdi+8], ebx
0x140012e55  mov     rcx, [rdi+10h]
0x140012e59  lea     r8, aRefDD; "Ref %d->%d"
0x140012e60  inc     ebx
0x140012e62  mov     edx, 10h
0x140012e67  mov     dword ptr [rsp+0E0h+BugCheckParameter4], ebx
0x140012e6b  lea     r12d, [rbx-1]
0x140012e6f  mov     r9d, r12d
0x140012e72  call    cs:__imp_RxDiagnosticTrace
0x140012e79  nop     dword ptr [rax+rax+00h]
0x140012e7e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012e85  lea     rax, WPP_GLOBAL_Control
0x140012e8c  cmp     rcx, rax
0x140012e8f  jz      short loc_140012E9C
0x140012e91  mov     eax, [rcx+2Ch]
0x140012e94  test    al, 4
0x140012e96  jnz     loc_140013220
0x140012e9c  movzx   edx, r15b; OldIrql
0x140012ea0  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140012eaa  lea     rcx, [rsi+780h]; SpinLock
0x140012eb1  call    cs:__imp_ExReleaseSpinLockExclusive
0x140012eb8  nop     dword ptr [rax+rax+00h]
0x140012ebd  test    rdi, rdi
0x140012ec0  jz      loc_140013176
0x140012ec6  mov     rax, [r13+20h]
0x140012eca  xor     r14d, r14d
0x140012ecd  mov     rcx, [rax+20h]
0x140012ed1  mov     [rcx+78h], r14d
0x140012ed5  mov     rax, [r13+20h]
0x140012ed9  mov     rcx, [rax+20h]
0x140012edd  mov     [rcx+70h], r14
0x140012ee1  cmp     [rdi+108h], r14b
0x140012ee8  jz      loc_14001317D
0x140012eee  cmp     [rdi+144h], r14b
0x140012ef5  jz      loc_14001317D
0x140012efb  mov     [rsp+0E0h+var_90], r14d
0x140012f00  lea     rax, [rbp+57h+var_80]
0x140012f04  mov     [rsp+0E0h+var_98], r14
0x140012f09  lea     r9, [rdi+190h]
0x140012f10  mov     [rsp+0E0h+var_A0], 28h ; '('
0x140012f18  lea     rdx, NPI_MS_TCP_MODULEID
0x140012f1f  mov     [rsp+0E0h+var_A8], rax
0x140012f24  mov     r8d, 0Eh
0x140012f2a  mov     [rsp+0E0h+var_B0], r14d
0x140012f2f  mov     ecx, 1
0x140012f34  mov     [rsp+0E0h+var_B8], r14
0x140012f39  mov     dword ptr [rsp+0E0h+BugCheckParameter4], 38h ; '8'
0x140012f41  call    cs:__imp_NsiGetAllParameters
0x140012f48  nop     dword ptr [rax+rax+00h]
0x140012f4d  mov     ecx, eax
0x140012f4f  test    eax, eax
0x140012f51  js      short loc_140012FA7
0x140012f53  mov     [rsp+0E0h+var_90], r14d
0x140012f58  lea     rax, [rbp+57h+var_58]
0x140012f5c  mov     [rsp+0E0h+var_98], r14
0x140012f61  lea     r9, [rdi+190h]
0x140012f68  mov     [rsp+0E0h+var_A0], 10h
0x140012f70  lea     rdx, NPI_MS_TCP_MODULEID
0x140012f77  mov     [rsp+0E0h+var_A8], rax
0x140012f7c  mov     r8d, 0Fh
0x140012f82  mov     [rsp+0E0h+var_B0], r14d
0x140012f87  mov     ecx, 1
0x140012f8c  mov     [rsp+0E0h+var_B8], r14
0x140012f91  mov     dword ptr [rsp+0E0h+BugCheckParameter4], 38h ; '8'
0x140012f99  call    cs:__imp_NsiGetAllParameters
0x140012fa0  nop     dword ptr [rax+rax+00h]
0x140012fa5  mov     ecx, eax
0x140012fa7  mov     ebx, ecx
0x140012fa9  test    ecx, ecx
0x140012fab  js      loc_140013184
0x140012fb1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012fb8  lea     rsi, WPP_GLOBAL_Control
0x140012fbf  cmp     rcx, rsi
0x140012fc2  jz      loc_140013078
0x140012fc8  mov     eax, [rcx+2Ch]
0x140012fcb  test    al, 4
0x140012fcd  jnz     loc_140013271
0x140012fd3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012fda  cmp     rcx, rsi
0x140012fdd  jz      loc_140013078
0x140012fe3  mov     eax, [rcx+2Ch]
0x140012fe6  test    al, 4
0x140012fe8  jnz     loc_140013295
0x140012fee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012ff5  cmp     rcx, rsi
0x140012ff8  jz      short loc_140013078
0x140012ffa  mov     eax, [rcx+2Ch]
0x140012ffd  test    al, 4
0x140012fff  jnz     loc_1400132B6
0x140013005  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001300c  cmp     rcx, rsi
0x14001300f  jz      short loc_140013078
0x140013011  mov     eax, [rcx+2Ch]
0x140013014  test    al, 4
0x140013016  jnz     loc_1400132D7
0x14001301c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013023  cmp     rcx, rsi
0x140013026  jz      short loc_140013078
0x140013028  mov     eax, [rcx+2Ch]
0x14001302b  test    al, 4
0x14001302d  jnz     loc_140013306
0x140013033  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001303a  cmp     rcx, rsi
0x14001303d  jz      short loc_140013078
0x14001303f  mov     eax, [rcx+2Ch]
0x140013042  test    al, 4
0x140013044  jnz     loc_14001332A
0x14001304a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013051  cmp     rcx, rsi
0x140013054  jz      short loc_140013078
0x140013056  mov     eax, [rcx+2Ch]
0x140013059  test    al, 4
0x14001305b  jnz     loc_14001334B
0x140013061  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013068  cmp     rcx, rsi
0x14001306b  jz      short loc_140013078
0x14001306d  mov     eax, [rcx+2Ch]
0x140013070  test    al, 4
0x140013072  jnz     loc_14001336C
0x140013078  cmp     byte ptr [rbp+57h+var_60], r14b
0x14001307c  jnz     loc_1400131F7
0x140013082  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x140013086  cmp     byte ptr [rbp+57h+var_60+1], r14b
0x14001308a  jnz     short loc_140013095
0x14001308c  cmp     qword ptr [rbp+57h+var_80], rdx
0x140013090  cmova   rdx, qword ptr [rbp+57h+var_80]
0x140013095  mov     rax, [r13+20h]
0x140013099  mov     rcx, [rax+20h]
0x14001309d  mov     [rcx+70h], rdx
0x1400130a1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400130a8  cmp     rcx, rsi
0x1400130ab  jz      short loc_140013114
0x1400130ad  mov     eax, [rcx+2Ch]
0x1400130b0  test    al, 4
0x1400130b2  jnz     loc_14001339B
0x1400130b8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400130bf  cmp     rcx, rsi
0x1400130c2  jz      short loc_140013114
0x1400130c4  mov     eax, [rcx+2Ch]
0x1400130c7  test    al, 4
0x1400130c9  jnz     loc_1400133BF
0x1400130cf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400130d6  cmp     rcx, rsi
0x1400130d9  jz      short loc_140013114
0x1400130db  mov     eax, [rcx+2Ch]
0x1400130de  test    al, 4
0x1400130e0  jnz     loc_1400133E7
0x1400130e6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400130ed  cmp     rcx, rsi
0x1400130f0  jz      short loc_140013114
0x1400130f2  mov     eax, [rcx+2Ch]
0x1400130f5  test    al, 4
0x1400130f7  jnz     loc_14001340F
0x1400130fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013104  cmp     rcx, rsi
0x140013107  jz      short loc_140013114
0x140013109  mov     eax, [rcx+2Ch]
0x14001310c  test    al, 4
0x14001310e  jnz     loc_140013437
0x140013114  mov     eax, 10624DD3h
0x140013119  mul     dword ptr [rbp+57h+var_58+0Ch]
0x14001311c  mov     rax, [r13+20h]
0x140013120  shr     edx, 6
0x140013123  mov     rcx, [rax+20h]
0x140013127  mov     [rcx+78h], edx
0x14001312a  mov     rcx, rdi; pContext
0x14001312d  call    VctDereferenceEndpoint
0x140013132  mov     eax, ebx
0x140013134  mov     rcx, [rbp+57h+var_48]
0x140013138  xor     rcx, rsp; StackCookie
0x14001313b  call    __security_check_cookie
0x140013140  add     rsp, 0A8h
0x140013147  pop     r15
0x140013149  pop     r14
0x14001314b  pop     r13
0x14001314d  pop     r12
0x14001314f  pop     rdi
0x140013150  pop     rsi
0x140013151  pop     rbx
0x140013152  pop     rbp
0x140013153  retn
0x140013155  movzx   edx, r15b; OldIrql
0x140013159  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140013163  lea     rcx, [rsi+780h]; SpinLock
0x14001316a  call    cs:__imp_ExReleaseSpinLockExclusive
0x140013171  nop     dword ptr [rax+rax+00h]
0x140013176  mov     ebx, 0C000020Ch
0x14001317b  jmp     short loc_140013132
0x14001317d  mov     ebx, 0C0000002h
0x140013182  mov     ecx, ebx
0x140013184  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001318b  lea     rax, WPP_GLOBAL_Control
0x140013192  cmp     r10, rax
0x140013195  jz      short loc_14001312A
0x140013197  mov     eax, [r10+2Ch]
0x14001319b  test    al, 1
0x14001319d  jz      short loc_14001312A
0x14001319f  cmp     byte ptr [r10+29h], 1
0x1400131a4  jb      short loc_14001312A
0x1400131a6  mov     dword ptr [rsp+0E0h+BugCheckParameter4], ecx
0x1400131aa  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x1400131b1  mov     rcx, [r10+18h]
0x1400131b5  mov     edx, 20h ; ' '
0x1400131ba  mov     r9, r13
0x1400131bd  call    WPP_SF_qD
0x1400131c2  jmp     loc_14001312A
0x1400131c7  mov     r9, rdx; BugCheckParameter3
0x1400131ca  mov     [rsp+0E0h+BugCheckParameter4], rdi; BugCheckParameter4
0x1400131cf  mov     edx, 0A0001h; BugCheckParameter1
0x1400131d4  mov     ecx, 27h ; '''; BugCheckCode
0x1400131d9  call    cs:__imp_KeBugCheckEx
0x1400131e6  mov     ecx, 8
0x1400131eb  jmp     loc_140012DAB
0x1400131f0  mov     ecx, 3
0x1400131f5  int     29h; Win8: RtlFailFast(ecx)
0x1400131f7  cmp     byte ptr [rbp+57h+var_60+1], r14b
0x1400131fb  jnz     short loc_14001320E
0x1400131fd  mov     rdx, qword ptr [rbp+57h+var_80]
0x140013201  jmp     loc_140013095
0x140013206  mov     rax, [rax]
0x140013209  jmp     loc_140012DDF
0x14001320e  mov     rdx, qword ptr [rbp+57h+var_80+8]
0x140013212  cmp     qword ptr [rbp+57h+var_80], rdx
0x140013216  cmovb   rdx, qword ptr [rbp+57h+var_80]
  ... truncated ...
```
