# CipGetVerificationInformation

- ea: `0x180057120`
- end: `0x180057402`
- name: `CipGetVerificationInformation`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d5110`

## callees

- `0x18000ee4c`
- `0x18002c040`
- `0x180057120`
- `0x180057fb0`
- `0x18005802c`
- `0x1800638d4`
- `0x18006c318`
- `0x180073edc`
- `0x180074024`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18005722c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005722c`
- `ntoskrnl!ExAllocatePool2` at `0x1800571e1`
- `ntoskrnl!ExAllocatePool2` at `0x1800571e1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005739b`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x18005739b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180057241`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x180057241`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800573e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800573e3`
- `ntoskrnl!ExGetPreviousMode` at `0x180057198`
- `ntoskrnl!ExGetPreviousMode` at `0x180057198`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800573a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800573a7`
- `ntoskrnl!ObfDereferenceObject` at `0x1800572b3`
- `ntoskrnl!ObfDereferenceObject` at `0x1800573cd`
- `ntoskrnl!ObfDereferenceObject` at `0x1800572b3`
- `ntoskrnl!ObfDereferenceObject` at `0x1800573cd`
- `ntoskrnl!ProbeForRead` at `0x1800571c7`
- `ntoskrnl!ProbeForRead` at `0x1800571c7`

## pseudocode

```c
__int64 __fastcall CipGetVerificationInformation(__int64 a1, unsigned int a2, _DWORD *a3)
{
  _DWORD *v3; // rdi
  void *v5; // rsi
  PVOID v6; // r15
  volatile void *v8; // r14
  SIZE_T v9; // r12
  int FileInfoFromSystemCodeIntegrityVerificationInformation; // edi
  void *Pool2; // rax
  __int64 v12; // r8
  void *v13; // rdx
  __int64 ActiveState; // rax
  _QWORD *v15; // rdx
  unsigned int v16; // r13d
  unsigned int v17; // ecx
  int v18; // eax
  __int64 v19; // r8
  _QWORD v20[2]; // [rsp+40h] [rbp-68h] BYREF
  _OWORD v21[5]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp+10h]
  PVOID Object; // [rsp+C0h] [rbp+18h] BYREF
  int v25; // [rsp+C8h] [rbp+20h]

  Object = a3;
  v3 = a3;
  v5 = 0;
  v6 = 0;
  v20[0] = 0;
  *a3 = 24;
  if ( a2 < 0x18 )
    return 3221225476LL;
  v8 = *(volatile void **)(a1 + 16);
  v20[1] = v8;
  v9 = *(unsigned int *)(a1 + 8);
  if ( v8 )
  {
    if ( (_DWORD)v9 )
    {
LABEL_8:
      if ( ExGetPreviousMode() && v8 && (_DWORD)v9 )
      {
        v25 = 1;
        ProbeForRead(v8, v9, 1u);
        Pool2 = (void *)ExAllocatePool2(259, v9, 1668499779);
        v5 = Pool2;
        if ( !Pool2 )
        {
          FileInfoFromSystemCodeIntegrityVerificationInformation = -1073741670;
          goto LABEL_35;
        }
        memmove(Pool2, (const void *)v8, v9);
        v3 = Object;
      }
      else
      {
        v25 = 1;
      }
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(&g_CipPolicyLock, 0);
      if ( v8 || (_DWORD)v9 )
      {
        v13 = v5;
        if ( !v5 )
          v13 = (void *)v8;
        FileInfoFromSystemCodeIntegrityVerificationInformation = CiValidateFileAsImageTypeLocked(3, v13, v9);
      }
      else
      {
        Object = 0;
        v20[0] = 0;
        *v3 = 24;
        FileInfoFromSystemCodeIntegrityVerificationInformation = CipGetFileInfoFromSystemCodeIntegrityVerificationInformation(
                                                                   a1,
                                                                   a2,
                                                                   &Object);
        if ( FileInfoFromSystemCodeIntegrityVerificationInformation >= 0 )
        {
          v6 = Object;
          FileInfoFromSystemCodeIntegrityVerificationInformation = CipQueryDynamicCodeTrustClaim(Object, v20, v12);
          Object = 0;
        }
        if ( Object )
          ObfDereferenceObject(Object);
      }
      ActiveState = SIPolicyGetActiveState();
      v15 = (_QWORD *)ActiveState;
      Object = (PVOID)ActiveState;
      if ( (*(_BYTE *)(ActiveState + 32) & 2) != 0 )
      {
        memset(v21, 0, 32);
        v16 = 0;
        v17 = *(_DWORD *)(ActiveState + 36);
        v23 = v17;
        LOBYTE(ActiveState) = 1;
        while ( v16 < v17 )
        {
          SIPolicyQueryOnePolicyInformation(*(_QWORD *)(v15[5] + 8LL * v16), v21);
          v18 = v21[0] & 0x500;
          if ( v18 == 256 )
          {
            LOBYTE(ActiveState) = 0;
            v25 = ActiveState;
            break;
          }
          LOBYTE(ActiveState) = 1;
          ++v16;
          v15 = Object;
          v17 = v23;
        }
        v19 = (__int64)v5;
        if ( !v5 )
          v19 = (__int64)v8;
        CiLogQueryDynamicCodeTrust(
          ActiveState,
          (__int64)v6,
          v19,
          v9,
          FileInfoFromSystemCodeIntegrityVerificationInformation);
        if ( (_BYTE)v25 )
          FileInfoFromSystemCodeIntegrityVerificationInformation = 0;
      }
      SIPolicyReleaseState(&Object);
      ExReleasePushLockSharedEx(&g_CipPolicyLock, 0);
      KeLeaveCriticalRegion();
      goto LABEL_35;
    }
  }
  else if ( !(_DWORD)v9 )
  {
    goto LABEL_8;
  }
  FileInfoFromSystemCodeIntegrityVerificationInformation = -1073741811;
LABEL_35:
  if ( v6 )
    ObfDereferenceObject(v6);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return (unsigned int)FileInfoFromSystemCodeIntegrityVerificationInformation;
}

```

## disassembly

```asm
0x180057120  mov     rax, rsp
0x180057123  mov     [rax+18h], r8
0x180057127  mov     [rax+10h], edx
0x18005712a  push    rbx
0x18005712b  push    rsi
0x18005712c  push    rdi
0x18005712d  push    r12
0x18005712f  push    r13
0x180057131  push    r14
0x180057133  push    r15
0x180057135  sub     rsp, 70h
0x180057139  mov     rdi, r8
0x18005713c  mov     r13, rcx
0x18005713f  xor     ebx, ebx
0x180057141  mov     esi, ebx
0x180057143  mov     [rax-70h], rbx
0x180057147  mov     r15d, ebx
0x18005714a  mov     [rax-68h], rbx
0x18005714e  mov     dword ptr [r8], 18h
0x180057155  cmp     edx, 18h
0x180057158  jnb     short loc_180057164
0x18005715a  mov     eax, 0C0000004h
0x18005715f  jmp     loc_1800573F1
0x180057164  mov     r14, [rcx+10h]
0x180057168  mov     [rsp+0A8h+var_60], r14
0x18005716d  mov     r12d, [rcx+8]
0x180057171  mov     [rsp+0A8h+var_74], r12d
0x180057176  test    r14, r14
0x180057179  jnz     short loc_180057185
0x18005717b  test    r12d, r12d
0x18005717e  jnz     short loc_18005718A
0x180057180  test    r14, r14
0x180057183  jz      short loc_180057198
0x180057185  test    r12d, r12d
0x180057188  jnz     short loc_180057198
0x18005718a  mov     edi, 0C000000Dh
0x18005718f  mov     [rsp+0A8h+var_78], edi
0x180057193  jmp     loc_1800573C5
0x180057198  call    cs:__imp_ExGetPreviousMode
0x18005719f  nop     dword ptr [rax+rax+00h]
0x1800571a4  test    al, al
0x1800571a6  jz      short loc_180057220
0x1800571a8  test    r14, r14
0x1800571ab  jz      short loc_180057220
0x1800571ad  test    r12d, r12d
0x1800571b0  jz      short loc_180057220
0x1800571b2  mov     edi, 1
0x1800571b7  mov     [rsp+0A8h+arg_18], edi
0x1800571be  mov     r8d, edi; Alignment
0x1800571c1  mov     rdx, r12; Length
0x1800571c4  mov     rcx, r14; Address
0x1800571c7  call    cs:__imp_ProbeForRead
0x1800571ce  nop     dword ptr [rax+rax+00h]
0x1800571d3  mov     r8d, 63734943h
0x1800571d9  mov     rdx, r12
0x1800571dc  mov     ecx, 103h
0x1800571e1  call    cs:__imp_ExAllocatePool2
0x1800571e8  nop     dword ptr [rax+rax+00h]
0x1800571ed  mov     rsi, rax
0x1800571f0  mov     [rsp+0A8h+var_70], rax
0x1800571f5  test    rax, rax
0x1800571f8  jnz     short loc_180057208
0x1800571fa  mov     edi, 0C000009Ah
0x1800571ff  mov     [rsp+0A8h+var_78], edi
0x180057203  jmp     loc_1800573C5
0x180057208  mov     r8, r12; Size
0x18005720b  mov     rdx, r14; Src
0x18005720e  mov     rcx, rax; void *
0x180057211  call    memmove
0x180057216  mov     rdi, [rsp+0A8h+Object]
0x18005721e  jmp     short loc_18005722C
0x180057220  mov     eax, 1
0x180057225  mov     [rsp+0A8h+arg_18], eax
0x18005722c  call    cs:__imp_KeEnterCriticalRegion
0x180057233  nop     dword ptr [rax+rax+00h]
0x180057238  xor     edx, edx
0x18005723a  lea     rcx, g_CipPolicyLock
0x180057241  call    cs:__imp_ExAcquirePushLockSharedEx
0x180057248  nop     dword ptr [rax+rax+00h]
0x18005724d  test    r14, r14
0x180057250  jnz     short loc_1800572C1
0x180057252  test    r12d, r12d
0x180057255  jnz     short loc_1800572C1
0x180057257  mov     [rsp+0A8h+Object], rbx
0x18005725f  mov     [rsp+0A8h+var_68], rbx
0x180057264  mov     dword ptr [rdi], 18h
0x18005726a  lea     r8, [rsp+0A8h+Object]
0x180057272  mov     edx, [rsp+0A8h+arg_8]
0x180057279  mov     rcx, r13
0x18005727c  call    CipGetFileInfoFromSystemCodeIntegrityVerificationInformation
0x180057281  mov     edi, eax
0x180057283  test    eax, eax
0x180057285  js      short loc_1800572A6
0x180057287  lea     rdx, [rsp+0A8h+var_68]
0x18005728c  mov     r15, [rsp+0A8h+Object]
0x180057294  mov     rcx, r15
0x180057297  call    CipQueryDynamicCodeTrustClaim
0x18005729c  mov     edi, eax
0x18005729e  mov     [rsp+0A8h+Object], rbx
0x1800572a6  mov     rcx, [rsp+0A8h+Object]; Object
0x1800572ae  test    rcx, rcx
0x1800572b1  jz      short loc_1800572DA
0x1800572b3  call    cs:__imp_ObfDereferenceObject
0x1800572ba  nop     dword ptr [rax+rax+00h]
0x1800572bf  jmp     short loc_1800572DA
0x1800572c1  mov     rdx, rsi
0x1800572c4  test    rsi, rsi
0x1800572c7  cmovz   rdx, r14
0x1800572cb  mov     r8, r12
0x1800572ce  mov     ecx, 3
0x1800572d3  call    CiValidateFileAsImageTypeLocked
0x1800572d8  mov     edi, eax
0x1800572da  call    SIPolicyGetActiveState
0x1800572df  mov     rdx, rax
0x1800572e2  mov     [rsp+0A8h+Object], rax
0x1800572ea  test    byte ptr [rax+20h], 2
0x1800572ee  jz      loc_180057385
0x1800572f4  xorps   xmm0, xmm0
0x1800572f7  movups  [rsp+0A8h+var_58], xmm0
0x1800572fc  movups  [rsp+0A8h+var_48], xmm0
0x180057301  mov     r13d, ebx
0x180057304  mov     ecx, [rax+24h]
0x180057307  mov     [rsp+0A8h+arg_8], ecx
0x18005730e  mov     eax, 1
0x180057313  cmp     r13d, ecx
0x180057316  jnb     short loc_18005735F
0x180057318  mov     eax, r13d
0x18005731b  mov     rcx, [rdx+28h]
0x18005731f  lea     rdx, [rsp+0A8h+var_58]
0x180057324  mov     rcx, [rcx+rax*8]
0x180057328  call    SIPolicyQueryOnePolicyInformation
0x18005732d  mov     eax, dword ptr [rsp+0A8h+var_58]
0x180057331  and     eax, 500h
0x180057336  cmp     eax, 100h
0x18005733b  jz      short loc_180057356
0x18005733d  mov     eax, 1
0x180057342  add     r13d, eax
0x180057345  mov     rdx, [rsp+0A8h+Object]
0x18005734d  mov     ecx, [rsp+0A8h+arg_8]
0x180057354  jmp     short loc_180057313
0x180057356  mov     al, bl
0x180057358  mov     [rsp+0A8h+arg_18], eax
0x18005735f  mov     r8, rsi
0x180057362  test    rsi, rsi
0x180057365  cmovz   r8, r14
0x180057369  mov     [rsp+0A8h+var_88], edi
0x18005736d  mov     r9d, r12d
0x180057370  mov     rdx, r15
0x180057373  mov     cl, al
0x180057375  call    CiLogQueryDynamicCodeTrust
0x18005737a  cmp     byte ptr [rsp+0A8h+arg_18], 0
0x180057382  cmovnz  edi, ebx
0x180057385  lea     rcx, [rsp+0A8h+Object]
0x18005738d  call    SIPolicyReleaseState
0x180057392  xor     edx, edx
0x180057394  lea     rcx, g_CipPolicyLock
0x18005739b  call    cs:__imp_ExReleasePushLockSharedEx
0x1800573a2  nop     dword ptr [rax+rax+00h]
0x1800573a7  call    cs:__imp_KeLeaveCriticalRegion
0x1800573ae  nop     dword ptr [rax+rax+00h]
0x1800573b3  jmp     short loc_1800573C5
0x1800573b5  mov     edi, eax
0x1800573b7  mov     [rsp+0A8h+var_78], eax
0x1800573bb  mov     rsi, [rsp+0A8h+var_70]
0x1800573c0  mov     r15, [rsp+0A8h+var_68]
0x1800573c5  test    r15, r15
0x1800573c8  jz      short loc_1800573D9
0x1800573ca  mov     rcx, r15; Object
0x1800573cd  call    cs:__imp_ObfDereferenceObject
0x1800573d4  nop     dword ptr [rax+rax+00h]
0x1800573d9  test    rsi, rsi
0x1800573dc  jz      short loc_1800573EF
0x1800573de  xor     edx, edx; Tag
0x1800573e0  mov     rcx, rsi; P
0x1800573e3  call    cs:__imp_ExFreePoolWithTag
0x1800573ea  nop     dword ptr [rax+rax+00h]
0x1800573ef  mov     eax, edi
0x1800573f1  add     rsp, 70h
0x1800573f5  pop     r15
0x1800573f7  pop     r14
0x1800573f9  pop     r13
0x1800573fb  pop     r12
0x1800573fd  pop     rdi
0x1800573fe  pop     rsi
0x1800573ff  pop     rbx
0x180057400  retn
0x1800e8325  push    rbp
0x1800e8327  sub     rsp, 30h
0x1800e832b  mov     rbp, rdx
0x1800e832e  call    cs:__imp_ExSystemExceptionFilter
0x1800e8335  nop     dword ptr [rax+rax+00h]
0x1800e833a  nop
0x1800e833b  add     rsp, 30h
0x1800e833f  pop     rbp
0x1800e8340  retn
```
