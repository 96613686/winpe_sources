# FveDiskVerify

- ea: `0x140027b28`
- end: `0x140027fa0`
- name: `FveDiskVerify`
- size: `1144`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x14002f430`

## callees

- `0x1400077a8`
- `0x140008b00`
- `0x140008dc0`
- `0x140008df0`
- `0x140008e44`
- `0x1400093dc`
- `0x14000eac0`
- `0x1400218c0`
- `0x140021d00`
- `0x140024040`
- `0x140027b28`
- `0x14002845c`
- `0x1400294e4`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027c8c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027e95`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027f03`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027f6e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027c8c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027e95`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027f03`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140027f6e`
- `ntoskrnl!IofCompleteRequest` at `0x140027ca3`
- `ntoskrnl!IofCompleteRequest` at `0x140027ca3`

## pseudocode

```c
__int64 __fastcall FveDiskVerify(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  char v5; // r12
  int v6; // ebx
  char v7; // r14
  __int64 v8; // r13
  signed __int64 *v10; // r14
  int v11; // eax
  __int64 v12; // rax
  ULONGLONG v13; // r9
  ULONGLONG v14; // r15
  signed __int64 v15; // r9
  unsigned __int64 v16; // r12
  unsigned int v17; // r12d
  char v18; // [rsp+31h] [rbp-A8h]
  unsigned __int8 v19; // [rsp+34h] [rbp-A5h]
  unsigned int v20; // [rsp+38h] [rbp-A1h]
  ULONGLONG pullResult; // [rsp+40h] [rbp-99h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-91h]
  _BYTE v23[144]; // [rsp+50h] [rbp-89h] BYREF
  ULONG pulResult[4]; // [rsp+E0h] [rbp+7h] BYREF

  memset(v23, 0, sizeof(v23));
  pullResult = 0;
  *(_OWORD *)pulResult = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
  }
  v4 = *(_QWORD *)(a1 + 64);
  v19 = 0;
  v5 = 0;
  FvepAcquireDevFveLock(v4, v23, 0);
  v18 = 1;
  *(_OWORD *)(a2 + 120) = 0;
  *(_OWORD *)(a2 + 136) = 0;
  v6 = FvepAcquireRundownProtectionOrHold(v4, (_QWORD *)a2, 2u);
  if ( !v6 )
  {
    v19 = BYTE1(*(_DWORD *)(a2 + 120));
    if ( (*(_DWORD *)(v4 + 808) & 0x17F) == 0 || (*(_DWORD *)(v4 + 808) & 0x40) != 0 )
    {
LABEL_36:
      v7 = 0;
      goto LABEL_12;
    }
    if ( *(_WORD *)(*(_QWORD *)(v4 + 976) + 10LL) != 2 )
    {
LABEL_8:
      v7 = v5;
LABEL_12:
      FvepInformRundownFinishedWithDisk(v4, a2, v19);
      goto LABEL_13;
    }
    v8 = *(_QWORD *)(a2 + 184);
    v20 = *(_DWORD *)(v8 + 16);
    if ( v20 < 0x10 )
    {
      v6 = -1073741811;
LABEL_11:
      v7 = 1;
      goto LABEL_12;
    }
    v10 = *(signed __int64 **)(a2 + 24);
    v11 = FveProtectedNoOverlapWithConvOrHold(v4, a2, *v10, *((unsigned int *)v10 + 2));
    v6 = v11;
    if ( v11 < 0 )
      goto LABEL_11;
    if ( v11 == 259 )
      goto LABEL_19;
    v12 = *(_QWORD *)(v4 + 976);
    v22 = *(_QWORD *)(v12 + 56);
    if ( v22 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v6 = -1073741675;
      goto LABEL_11;
    }
    v5 = 1;
    v6 = RtlULongLongMult(*(unsigned int *)(v12 + 28), *(unsigned int *)(v4 + 1308), &pullResult);
    if ( v6 >= 0 )
    {
      v14 = pullResult;
      if ( pullResult > v13 )
      {
        v6 = -1073741675;
        goto LABEL_8;
      }
      v15 = *v10;
      v16 = *v10 + *((unsigned int *)v10 + 2);
      if ( v16 < *v10 )
      {
        v6 = -1073741675;
        v7 = 1;
        goto LABEL_12;
      }
      if ( v15 >= (__int64)pullResult )
      {
        v6 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_ii(
            WPP_GLOBAL_Control->AttachedDevice,
            44,
            WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids,
            v15,
            *v10 + *((unsigned int *)v10 + 2));
        }
        goto LABEL_36;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_iii(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
      }
      FvepInformRundownFinishedWithDisk(v4, a2, v19);
      FvepReleaseDevFveLock(v23);
      v18 = 0;
      if ( v16 > v14 )
      {
        *(_QWORD *)pulResult = v14;
        v6 = RtlLongLongToULong(v16 - v14, &pulResult[2]);
        if ( v6 < 0 )
          goto LABEL_45;
        *(_QWORD *)(a2 + 24) = pulResult;
        *(_DWORD *)(v8 + 16) = 16;
        IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v4 + 112), (PIRP)a2);
        v6 = *(_DWORD *)(a2 + 48);
        v17 = v20;
        *(_QWORD *)(a2 + 24) = v10;
        *(_DWORD *)(v8 + 16) = v20;
        if ( v6 < 0 )
          goto LABEL_45;
        v6 = RtlLongLongAdd(*v10, v22);
        if ( v6 < 0 )
          goto LABEL_45;
        v6 = RtlLongLongToULong(v14 - *v10, &pulResult[2]);
        if ( v6 < 0 )
          goto LABEL_45;
        *(_QWORD *)(a2 + 24) = pulResult;
        *(_DWORD *)(v8 + 16) = 16;
        IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v4 + 112), (PIRP)a2);
      }
      else
      {
        v6 = RtlLongLongAdd(*v10, v22);
        if ( v6 < 0 )
        {
LABEL_45:
          v5 = 0;
          goto LABEL_46;
        }
        pulResult[2] = *((_DWORD *)v10 + 2);
        *(_QWORD *)(a2 + 24) = pulResult;
        *(_DWORD *)(v8 + 16) = 16;
        IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v4 + 112), (PIRP)a2);
        v17 = v20;
      }
      v6 = *(_DWORD *)(a2 + 48);
      *(_QWORD *)(a2 + 24) = v10;
      *(_DWORD *)(v8 + 16) = v17;
      goto LABEL_45;
    }
  }
LABEL_46:
  if ( v6 == 259 )
    goto LABEL_18;
  v7 = 1;
  if ( v5 )
    goto LABEL_12;
LABEL_13:
  if ( v18 )
  {
    FvepReleaseDevFveLock(v23);
    v18 = 0;
  }
  if ( !v7 )
  {
    IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v4 + 112), (PIRP)a2);
    v6 = *(_DWORD *)(a2 + 48);
  }
  *(_DWORD *)(a2 + 48) = v6;
  IofCompleteRequest((PIRP)a2, 0);
LABEL_18:
  if ( v18 )
LABEL_19:
    FvepReleaseDevFveLock(v23);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140027b28  mov     [rsp-8+arg_10], rbx
0x140027b2d  push    rbp
0x140027b2e  push    rsi
0x140027b2f  push    rdi
0x140027b30  push    r12
0x140027b32  push    r13
0x140027b34  push    r14
0x140027b36  push    r15
0x140027b38  lea     rbp, [rsp-27h]
0x140027b3d  sub     rsp, 100h
0x140027b44  mov     rax, cs:__security_cookie
0x140027b4b  xor     rax, rsp
0x140027b4e  mov     [rbp+57h+var_40], rax
0x140027b52  mov     rdi, rdx
0x140027b55  mov     rsi, rcx
0x140027b58  xor     edx, edx; Val
0x140027b5a  lea     rcx, [rsp+130h+var_E0]; void *
0x140027b5f  mov     r8d, 90h; Size
0x140027b65  call    memset
0x140027b6a  xorps   xmm0, xmm0
0x140027b6d  mov     [rsp+130h+pullResult], 0
0x140027b76  movups  xmmword ptr [rbp+57h+pulResult], xmm0
0x140027b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140027b81  lea     rax, WPP_GLOBAL_Control
0x140027b88  cmp     rcx, rax
0x140027b8b  jz      short loc_140027BAF
0x140027b8d  mov     eax, [rcx+2Ch]
0x140027b90  test    al, 40h
0x140027b92  jz      short loc_140027BAF
0x140027b94  cmp     byte ptr [rcx+29h], 5
0x140027b98  jb      short loc_140027BAF
0x140027b9a  mov     rcx, [rcx+18h]
0x140027b9e  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x140027ba5  mov     edx, 2Bh ; '+'
0x140027baa  call    WPP_SF_
0x140027baf  mov     rsi, [rsi+40h]
0x140027bb3  lea     rdx, [rsp+130h+var_E0]
0x140027bb8  mov     rcx, rsi
0x140027bbb  mov     [rsp+130h+var_FC], 0
0x140027bc3  xor     r8d, r8d
0x140027bc6  mov     r15b, 1
0x140027bc9  xor     r12b, r12b
0x140027bcc  call    FvepAcquireDevFveLock
0x140027bd1  xorps   xmm0, xmm0
0x140027bd4  mov     [rsp+130h+var_FF], r15b
0x140027bd9  movups  xmmword ptr [rdi+78h], xmm0
0x140027bdd  mov     r8b, 2
0x140027be0  mov     rdx, rdi
0x140027be3  mov     rcx, rsi
0x140027be6  movups  xmmword ptr [rdi+88h], xmm0
0x140027bed  call    FvepAcquireRundownProtectionOrHold
0x140027bf2  mov     ebx, eax
0x140027bf4  test    eax, eax
0x140027bf6  jnz     loc_140027EB6
0x140027bfc  mov     ecx, [rdi+78h]
0x140027bff  shr     rcx, 8
0x140027c03  movzx   ecx, cl
0x140027c06  mov     [rsp+130h+var_FC], ecx
0x140027c0a  mov     ecx, [rsi+328h]
0x140027c10  test    ecx, 17Fh
0x140027c16  setnz   dl
0x140027c19  test    cl, 40h
0x140027c1c  setz    cl
0x140027c1f  test    cl, dl
0x140027c21  jz      loc_140027DF0
0x140027c27  mov     rax, [rsi+3D0h]
0x140027c2e  cmp     word ptr [rax+0Ah], 2
0x140027c33  jz      short loc_140027C3A
0x140027c35  mov     r14b, r12b
0x140027c38  jmp     short loc_140027C5A
0x140027c3a  mov     r13, [rdi+0B8h]
0x140027c41  mov     eax, [r13+10h]
0x140027c45  mov     [rsp+130h+var_F8], eax
0x140027c49  cmp     eax, 10h
0x140027c4c  jnb     loc_140027D22
0x140027c52  mov     ebx, 0C000000Dh
0x140027c57  mov     r14b, r15b
0x140027c5a  mov     r8b, byte ptr [rsp+130h+var_FC]
0x140027c5f  mov     rdx, rdi
0x140027c62  mov     rcx, rsi
0x140027c65  call    FvepInformRundownFinishedWithDisk
0x140027c6a  cmp     [rsp+130h+var_FF], 0
0x140027c6f  jz      short loc_140027C80
0x140027c71  lea     rcx, [rsp+130h+var_E0]
0x140027c76  call    FvepReleaseDevFveLock
0x140027c7b  mov     [rsp+130h+var_FF], 0
0x140027c80  test    r14b, r14b
0x140027c83  jnz     short loc_140027C9B
0x140027c85  mov     rcx, [rsi+70h]; DeviceObject
0x140027c89  mov     rdx, rdi; Irp
0x140027c8c  call    cs:__imp_IoForwardIrpSynchronously
0x140027c93  nop     dword ptr [rax+rax+00h]
0x140027c98  mov     ebx, [rdi+30h]
0x140027c9b  xor     edx, edx; PriorityBoost
0x140027c9d  mov     [rdi+30h], ebx
0x140027ca0  mov     rcx, rdi; Irp
0x140027ca3  call    cs:__imp_IofCompleteRequest
0x140027caa  nop     dword ptr [rax+rax+00h]
0x140027caf  cmp     [rsp+130h+var_FF], 0
0x140027cb4  jz      short loc_140027CC0
0x140027cb6  lea     rcx, [rsp+130h+var_E0]
0x140027cbb  call    FvepReleaseDevFveLock
0x140027cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x140027cc7  lea     rax, WPP_GLOBAL_Control
0x140027cce  cmp     rcx, rax
0x140027cd1  jz      short loc_140027CF8
0x140027cd3  mov     eax, [rcx+2Ch]
0x140027cd6  test    al, 40h
0x140027cd8  jz      short loc_140027CF8
0x140027cda  cmp     byte ptr [rcx+29h], 5
0x140027cde  jb      short loc_140027CF8
0x140027ce0  mov     rcx, [rcx+18h]
0x140027ce4  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x140027ceb  mov     edx, 2Eh ; '.'
0x140027cf0  mov     r9d, ebx
0x140027cf3  call    WPP_SF_d
0x140027cf8  mov     eax, ebx
0x140027cfa  mov     rcx, [rbp+57h+var_40]
0x140027cfe  xor     rcx, rsp; StackCookie
0x140027d01  call    __security_check_cookie
0x140027d06  mov     rbx, [rsp+130h+arg_10]
0x140027d0e  add     rsp, 100h
0x140027d15  pop     r15
0x140027d17  pop     r14
0x140027d19  pop     r13
0x140027d1b  pop     r12
0x140027d1d  pop     rdi
0x140027d1e  pop     rsi
0x140027d1f  pop     rbp
0x140027d20  retn
0x140027d22  mov     r14, [rdi+18h]
0x140027d26  mov     rdx, rdi
0x140027d29  mov     rcx, rsi
0x140027d2c  mov     r9d, [r14+8]
0x140027d30  mov     r8, [r14]
0x140027d33  call    FveProtectedNoOverlapWithConvOrHold
0x140027d38  mov     ebx, eax
0x140027d3a  test    eax, eax
0x140027d3c  js      loc_140027C57
0x140027d42  cmp     eax, 103h
0x140027d47  jz      loc_140027CB6
0x140027d4d  mov     rax, [rsi+3D0h]
0x140027d54  mov     r9, 7FFFFFFFFFFFFFFFh
0x140027d5e  mov     rcx, [rax+38h]
0x140027d62  mov     [rsp+130h+var_E8], rcx
0x140027d67  cmp     rcx, r9
0x140027d6a  ja      loc_140027F96
0x140027d70  mov     edx, [rsi+51Ch]; ullMultiplier
0x140027d76  lea     r8, [rsp+130h+pullResult]; pullResult
0x140027d7b  mov     ecx, [rax+1Ch]; ullMultiplicand
0x140027d7e  mov     r12b, r15b
0x140027d81  call    RtlULongLongMult
0x140027d86  mov     ebx, eax
0x140027d88  test    eax, eax
0x140027d8a  js      loc_140027EB6
0x140027d90  mov     r15, [rsp+130h+pullResult]
0x140027d95  cmp     r15, r9
0x140027d98  ja      loc_140027F8C
0x140027d9e  mov     r9, [r14]
0x140027da1  mov     r12d, [r14+8]
0x140027da5  add     r12, r9
0x140027da8  cmp     r12, r9
0x140027dab  jb      loc_140027F7F
0x140027db1  cmp     r9, r15
0x140027db4  jl      short loc_140027DF8
0x140027db6  xor     ebx, ebx
0x140027db8  mov     rcx, cs:WPP_GLOBAL_Control
0x140027dbf  lea     rax, WPP_GLOBAL_Control
0x140027dc6  cmp     rcx, rax
0x140027dc9  jz      short loc_140027DF0
0x140027dcb  mov     eax, [rcx+2Ch]
0x140027dce  test    al, 40h
0x140027dd0  jz      short loc_140027DF0
0x140027dd2  cmp     byte ptr [rcx+29h], 5
0x140027dd6  jb      short loc_140027DF0
0x140027dd8  mov     rcx, [rcx+18h]
0x140027ddc  lea     edx, [rbx+2Ch]
0x140027ddf  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x140027de6  mov     [rsp+130h+var_110], r12
0x140027deb  call    WPP_SF_ii
0x140027df0  xor     r14b, r14b
0x140027df3  jmp     loc_140027C5A
0x140027df8  mov     rcx, cs:WPP_GLOBAL_Control
0x140027dff  lea     rax, WPP_GLOBAL_Control
0x140027e06  cmp     rcx, rax
0x140027e09  jz      short loc_140027E37
0x140027e0b  mov     eax, [rcx+2Ch]
0x140027e0e  test    al, 40h
0x140027e10  jz      short loc_140027E37
0x140027e12  cmp     byte ptr [rcx+29h], 5
0x140027e16  jb      short loc_140027E37
0x140027e18  mov     rcx, [rcx+18h]
0x140027e1c  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x140027e23  mov     edx, 2Dh ; '-'
0x140027e28  mov     [rsp+130h+var_108], r15
0x140027e2d  mov     [rsp+130h+var_110], r12
0x140027e32  call    WPP_SF_iii
0x140027e37  mov     r8b, byte ptr [rsp+130h+var_FC]
0x140027e3c  mov     rdx, rdi
0x140027e3f  mov     rcx, rsi
0x140027e42  call    FvepInformRundownFinishedWithDisk
0x140027e47  lea     rcx, [rsp+130h+var_E0]
0x140027e4c  mov     [rsp+130h+var_100], 0
0x140027e51  call    FvepReleaseDevFveLock
0x140027e56  mov     [rsp+130h+var_FF], 0
0x140027e5b  cmp     r12, r15
0x140027e5e  ja      short loc_140027ED3
0x140027e60  mov     rdx, [rsp+130h+var_E8]
0x140027e65  lea     r8, [rbp+57h+pulResult]
0x140027e69  mov     rcx, [r14]
0x140027e6c  call    RtlLongLongAdd
0x140027e71  mov     ebx, eax
0x140027e73  test    eax, eax
0x140027e75  js      short loc_140027EB1
0x140027e77  mov     eax, [r14+8]
0x140027e7b  mov     rdx, rdi; Irp
0x140027e7e  mov     [rbp+57h+pulResult+8], eax
0x140027e81  lea     rax, [rbp+57h+pulResult]
0x140027e85  mov     [rdi+18h], rax
0x140027e89  mov     dword ptr [r13+10h], 10h
0x140027e91  mov     rcx, [rsi+70h]; DeviceObject
0x140027e95  call    cs:__imp_IoForwardIrpSynchronously
0x140027e9c  nop     dword ptr [rax+rax+00h]
0x140027ea1  mov     r12d, [rsp+130h+var_F8]
0x140027ea6  mov     ebx, [rdi+30h]
0x140027ea9  mov     [rdi+18h], r14
0x140027ead  mov     [r13+10h], r12d
0x140027eb1  mov     r12b, [rsp+130h+var_100]
0x140027eb6  cmp     ebx, 103h
0x140027ebc  jz      loc_140027CAF
0x140027ec2  mov     r14b, 1
0x140027ec5  test    r12b, r12b
0x140027ec8  jnz     loc_140027C5A
0x140027ece  jmp     loc_140027C6A
0x140027ed3  sub     r12, r15
0x140027ed6  mov     qword ptr [rbp+57h+pulResult], r15
0x140027eda  mov     rcx, r12; llOperand
0x140027edd  lea     rdx, [rbp+57h+pulResult+8]; pulResult
0x140027ee1  call    RtlLongLongToULong
0x140027ee6  mov     ebx, eax
0x140027ee8  test    eax, eax
0x140027eea  js      short loc_140027EB1
0x140027eec  lea     rax, [rbp+57h+pulResult]
0x140027ef0  mov     rdx, rdi; Irp
0x140027ef3  mov     [rdi+18h], rax
0x140027ef7  mov     dword ptr [r13+10h], 10h
0x140027eff  mov     rcx, [rsi+70h]; DeviceObject
0x140027f03  call    cs:__imp_IoForwardIrpSynchronously
0x140027f0a  nop     dword ptr [rax+rax+00h]
0x140027f0f  mov     ebx, [rdi+30h]
0x140027f12  mov     r12d, [rsp+130h+var_F8]
0x140027f17  mov     [rdi+18h], r14
0x140027f1b  mov     [r13+10h], r12d
0x140027f1f  test    ebx, ebx
0x140027f21  js      short loc_140027EB1
0x140027f23  mov     rdx, [rsp+130h+var_E8]
0x140027f28  lea     r8, [rbp+57h+pulResult]
0x140027f2c  mov     rcx, [r14]
0x140027f2f  call    RtlLongLongAdd
0x140027f34  mov     ebx, eax
0x140027f36  test    eax, eax
0x140027f38  js      loc_140027EB1
0x140027f3e  sub     r15, [r14]
0x140027f41  lea     rdx, [rbp+57h+pulResult+8]; pulResult
0x140027f45  mov     rcx, r15; llOperand
0x140027f48  call    RtlLongLongToULong
0x140027f4d  mov     ebx, eax
0x140027f4f  test    eax, eax
0x140027f51  js      loc_140027EB1
0x140027f57  lea     rax, [rbp+57h+pulResult]
0x140027f5b  mov     rdx, rdi; Irp
0x140027f5e  mov     [rdi+18h], rax
0x140027f62  mov     dword ptr [r13+10h], 10h
0x140027f6a  mov     rcx, [rsi+70h]; DeviceObject
0x140027f6e  call    cs:__imp_IoForwardIrpSynchronously
0x140027f75  nop     dword ptr [rax+rax+00h]
0x140027f7a  jmp     loc_140027EA6
0x140027f7f  mov     ebx, 0C0000095h
0x140027f84  mov     r14b, 1
0x140027f87  jmp     loc_140027C5A
0x140027f8c  mov     ebx, 0C0000095h
0x140027f91  jmp     loc_140027C35
0x140027f96  mov     ebx, 0C0000095h
0x140027f9b  jmp     loc_140027C57
```
