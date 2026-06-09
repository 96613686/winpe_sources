# SecLmfSetNetworkSharePolicyConfiguration

- ea: `0x14003efbc`
- end: `0x14003f3f7`
- name: `SecLmfSetNetworkSharePolicyConfiguration`
- size: `1083`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140022d5c`

## callees

- `0x14001041f`
- `0x14001042b`
- `0x140011610`
- `0x140011700`
- `0x14003e3e4`
- `0x14003ed24`
- `0x14003efbc`

## import_xrefs

- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14003f2bf`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14003f2bf`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003f2d6`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003f2d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f042`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f220`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f314`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f042`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f220`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f314`

## pseudocode

```c
__int64 __fastcall SecLmfSetNetworkSharePolicyConfiguration(
        __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        unsigned int a4)
{
  unsigned int v4; // r15d
  int DriverConfigurationNamesArray; // ebx
  _DWORD *v8; // rdi
  int v9; // esi
  SIZE_T v10; // rdx
  bool v11; // zf
  _DWORD *PoolWithTag; // rax
  int v13; // r9d
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // r14
  int v18; // r9d
  int v19; // r9d
  int v20; // r9d
  unsigned int v21; // eax
  SIZE_T v22; // rdx
  PVOID v23; // rax
  unsigned int v24; // eax
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // r13
  __int64 v27; // r8
  char *v28; // r15
  char *v29; // rax
  PVOID v30; // rax
  void *v31; // rcx
  unsigned int v33; // [rsp+34h] [rbp-64h]
  unsigned int NumberOfBytes; // [rsp+38h] [rbp-60h]
  int NumberOfBytes_4; // [rsp+3Ch] [rbp-5Ch]
  PVOID P; // [rsp+48h] [rbp-50h]
  unsigned __int64 v37; // [rsp+50h] [rbp-48h]

  v4 = a4;
  P = 0;
  DriverConfigurationNamesArray = 0;
  v8 = 0;
  v9 = 0;
  if ( SecLmfInitialized )
  {
    if ( a2 )
    {
      v10 = 72LL * a2;
      v11 = qword_140020008 == 0;
      _mm_lfence();
      if ( v11 )
        PoolWithTag = ExAllocatePoolWithTag(PagedPool, v10, 0x634C6353u);
      else
        PoolWithTag = (_DWORD *)qword_140020008(256, v10, 1665950547);
      v8 = PoolWithTag;
      if ( PoolWithTag )
      {
        v15 = 0;
        NumberOfBytes_4 = 0;
        _mm_lfence();
        while ( 1 )
        {
          v16 = 96 * v15;
          if ( *(_DWORD *)(96 * v15 + a1) != 4 )
          {
            DriverConfigurationNamesArray = -1073741735;
            goto LABEL_8;
          }
          v17 = 9 * v15;
          LOBYTE(v13) = 1;
          v8[2 * v17] = 4;
          v8[2 * v17 + 1] = *(_DWORD *)(v16 + a1 + 4);
          LOBYTE(v8[2 * v17 + 2]) = *(_BYTE *)(v16 + a1 + 8);
          BYTE1(v8[2 * v17 + 2]) = *(_BYTE *)(v16 + a1 + 9);
          BYTE2(v8[2 * v17 + 2]) = *(_BYTE *)(v16 + a1 + 10);
          HIBYTE(v8[2 * v17 + 2]) = *(_BYTE *)(v16 + a1 + 11);
          v8[2 * v17 + 3] = *(_DWORD *)(v16 + a1 + 12);
          LOBYTE(v8[2 * v17 + 12]) = *(_BYTE *)(v16 + a1 + 56);
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            v4,
                                            (int)v16 + (int)a1 + 16,
                                            v13,
                                            word_14001B724,
                                            (__int64)&v8[18 * v15 + 4]);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_8;
          _mm_lfence();
          LOBYTE(v18) = 1;
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            v4,
                                            (int)v16 + (int)a1 + 32,
                                            v18,
                                            word_14001B724,
                                            (__int64)&v8[2 * v17 + 6]);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_8;
          _mm_lfence();
          LOBYTE(v19) = 1;
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            v4,
                                            (int)v16 + (int)a1 + 64,
                                            v19,
                                            word_14001B724,
                                            (__int64)&v8[2 * v17 + 14]);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_8;
          _mm_lfence();
          LOBYTE(v20) = 1;
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            v4,
                                            (int)v16 + (int)a1 + 80,
                                            v20,
                                            word_14001B724,
                                            (__int64)&v8[2 * v17 + 16]);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_8;
          _mm_lfence();
          *(_QWORD *)&v8[2 * v17 + 10] = 0;
          v21 = *(_DWORD *)(v16 + a1 + 48);
          v8[2 * v17 + 8] = v21;
          if ( *(_DWORD *)(v16 + a1 + 48) )
          {
            v22 = 8LL * v21;
            if ( qword_140020008 )
              v23 = (PVOID)qword_140020008(256, v22, 1665950547);
            else
              v23 = ExAllocatePoolWithTag(PagedPool, v22, 0x634C6353u);
            *(_QWORD *)&v8[2 * v17 + 10] = v23;
            if ( !v23 )
              goto LABEL_7;
            v24 = 0;
            v25 = a3 + *(unsigned int *)(v16 + a1 + 52);
            v33 = 0;
            v37 = v25;
            if ( *(_DWORD *)(v16 + a1 + 48) )
              break;
          }
LABEL_36:
          v15 = (unsigned int)(NumberOfBytes_4 + 1);
          NumberOfBytes_4 = v15;
          if ( (unsigned int)v15 >= a2 )
          {
            v9 = a2;
            goto LABEL_38;
          }
        }
        v26 = a3 + v4;
        while ( 1 )
        {
          *(_QWORD *)(*(_QWORD *)&v8[2 * v17 + 10] + 8LL * v24) = 0;
          v27 = *(unsigned int *)(v25 + 8LL * v24);
          v28 = (char *)(a3 + *(unsigned int *)(v25 + 8LL * v24 + 4));
          NumberOfBytes = *(_DWORD *)(v25 + 8LL * v24);
          v29 = v28 + 40;
          if ( v26 <= a3
            || v29 <= v28
            || (unsigned __int64)v28 < a3
            || (unsigned __int64)v29 > v26
            || &v28[v27] <= v28
            || (unsigned __int64)&v28[v27] > v26 )
          {
            break;
          }
          if ( !RtlValidSecurityDescriptor(v28) || RtlLengthSecurityDescriptor(v28) != NumberOfBytes )
          {
            DriverConfigurationNamesArray = -1073741703;
            goto LABEL_8;
          }
          if ( qword_140020008 )
            v30 = (PVOID)qword_140020008(256, NumberOfBytes, 1665950547);
          else
            v30 = ExAllocatePoolWithTag(PagedPool, NumberOfBytes, 0x634C6353u);
          *(_QWORD *)(*(_QWORD *)&v8[2 * v17 + 10] + 8LL * v33) = v30;
          v31 = *(void **)(*(_QWORD *)&v8[2 * v17 + 10] + 8LL * v33);
          if ( !v31 )
            goto LABEL_7;
          memmove(v31, v28, NumberOfBytes);
          v25 = v37;
          v24 = v33 + 1;
          v33 = v24;
          if ( v24 >= *(_DWORD *)(v16 + a1 + 48) )
          {
            v4 = a4;
            goto LABEL_36;
          }
        }
        DriverConfigurationNamesArray = -1073741684;
      }
      else
      {
LABEL_7:
        DriverConfigurationNamesArray = -1073741801;
      }
    }
    else
    {
LABEL_38:
      FltAcquirePushLockExclusiveEx_0(&SecLmfPolicyConfigLock, 0);
      P = SecLmfNetworkSharePolicyConfig;
      SecLmfNetworkSharePolicyConfig = v8;
      v8 = 0;
      SecLmfNetworkSharePolicyConfigCount = v9;
      FltReleasePushLockEx_0(&SecLmfPolicyConfigLock, 0);
    }
  }
LABEL_8:
  SecLmfFreeNetworkSharePolicyConfiguration(P);
  SecLmfFreeNetworkSharePolicyConfiguration(v8);
  return (unsigned int)DriverConfigurationNamesArray;
}

```

## disassembly

```asm
0x14003efbc  mov     [rsp+arg_0], rbx
0x14003efc1  mov     [rsp+arg_18], r9d
0x14003efc6  mov     [rsp+arg_8], edx
0x14003efca  push    rbp
0x14003efcb  push    rsi
0x14003efcc  push    rdi
0x14003efcd  push    r12
0x14003efcf  push    r13
0x14003efd1  push    r14
0x14003efd3  push    r15
0x14003efd5  sub     rsp, 60h
0x14003efd9  xor     r13d, r13d
0x14003efdc  mov     eax, edx
0x14003efde  cmp     cs:SecLmfInitialized, r13b
0x14003efe5  mov     r15d, r9d
0x14003efe8  mov     r12, r8
0x14003efeb  mov     [rsp+98h+P], r13
0x14003eff0  mov     rbp, rcx
0x14003eff3  mov     [rsp+98h+var_58], r13d
0x14003eff8  mov     ebx, r13d
0x14003effb  mov     edi, r13d
0x14003effe  mov     esi, r13d
0x14003f001  jz      short loc_14003F05F
0x14003f003  test    edx, edx
0x14003f005  jz      loc_14003F38F
0x14003f00b  lea     rdx, [rax+rax*8]
0x14003f00f  mov     [rsp+98h+var_68], eax
0x14003f013  shl     rdx, 3; NumberOfBytes
0x14003f017  mov     r8d, 634C6353h; Tag
0x14003f01d  cmp     cs:qword_140020008, r13
0x14003f024  lfence
0x14003f027  jz      short loc_14003F03D
0x14003f029  mov     rax, cs:qword_140020008
0x14003f030  mov     ecx, 100h
0x14003f035  call    cs:__guard_dispatch_icall_fptr
0x14003f03b  jmp     short loc_14003F04E
0x14003f03d  mov     ecx, 1; PoolType
0x14003f042  call    cs:__imp_ExAllocatePoolWithTag
0x14003f049  nop     dword ptr [rax+rax+00h]
0x14003f04e  mov     rdi, rax
0x14003f051  test    rax, rax
0x14003f054  jnz     short loc_14003F092
0x14003f056  mov     ebx, 0C0000017h
0x14003f05b  mov     esi, [rsp+98h+var_68]
0x14003f05f  mov     edx, [rsp+98h+var_58]
0x14003f063  mov     rcx, [rsp+98h+P]; P
0x14003f068  call    SecLmfFreeNetworkSharePolicyConfiguration
0x14003f06d  mov     edx, esi
0x14003f06f  mov     rcx, rdi; P
0x14003f072  call    SecLmfFreeNetworkSharePolicyConfiguration
0x14003f077  mov     eax, ebx
0x14003f079  mov     rbx, [rsp+98h+arg_0]
0x14003f081  add     rsp, 60h
0x14003f085  pop     r15
0x14003f087  pop     r14
0x14003f089  pop     r13
0x14003f08b  pop     r12
0x14003f08d  pop     rdi
0x14003f08e  pop     rsi
0x14003f08f  pop     rbp
0x14003f090  retn
0x14003f092  mov     eax, r13d
0x14003f095  mov     dword ptr [rsp+98h+NumberOfBytes+4], eax
0x14003f099  lfence
0x14003f09c  lea     rsi, [rax+rax*2]
0x14003f0a0  shl     rsi, 5
0x14003f0a4  cmp     dword ptr [rsi+rbp], 4
0x14003f0a8  jnz     loc_14003F3ED
0x14003f0ae  lea     r14, [rax+rax*8]
0x14003f0b2  mov     r9b, 1
0x14003f0b5  mov     dword ptr [rdi+r14*8], 4
0x14003f0bd  lea     r8, [rbp+10h]
0x14003f0c1  mov     eax, [rsi+rbp+4]
0x14003f0c5  add     r8, rsi
0x14003f0c8  mov     [rdi+r14*8+4], eax
0x14003f0cd  mov     edx, r15d
0x14003f0d0  mov     al, [rsi+rbp+8]
0x14003f0d4  mov     rcx, r12
0x14003f0d7  mov     [rdi+r14*8+8], al
0x14003f0dc  mov     al, [rsi+rbp+9]
0x14003f0e0  mov     [rdi+r14*8+9], al
0x14003f0e5  mov     al, [rsi+rbp+0Ah]
0x14003f0e9  mov     [rdi+r14*8+0Ah], al
0x14003f0ee  mov     al, [rsi+rbp+0Bh]
0x14003f0f2  mov     [rdi+r14*8+0Bh], al
0x14003f0f7  mov     eax, [rsi+rbp+0Ch]
0x14003f0fb  mov     [rdi+r14*8+0Ch], eax
0x14003f100  mov     al, [rsi+rbp+38h]
0x14003f104  mov     [rdi+r14*8+30h], al
0x14003f109  lea     rax, [r14+2]
0x14003f10d  lea     rax, [rdi+rax*8]
0x14003f111  mov     [rsp+98h+var_70], rax
0x14003f116  mov     al, byte ptr cs:word_14001B724
0x14003f11c  mov     [rsp+98h+var_78], al
0x14003f120  call    SecRetrieveDriverConfigurationNamesArray
0x14003f125  mov     ebx, eax
0x14003f127  test    eax, eax
0x14003f129  js      loc_14003F05B
0x14003f12f  lfence
0x14003f132  lea     rax, [r14+3]
0x14003f136  mov     r9b, 1
0x14003f139  lea     rax, [rdi+rax*8]
0x14003f13d  mov     edx, r15d
0x14003f140  mov     [rsp+98h+var_70], rax
0x14003f145  lea     r8, [rbp+20h]
0x14003f149  mov     al, byte ptr cs:word_14001B724
0x14003f14f  add     r8, rsi
0x14003f152  mov     rcx, r12
0x14003f155  mov     [rsp+98h+var_78], al
0x14003f159  call    SecRetrieveDriverConfigurationNamesArray
0x14003f15e  mov     ebx, eax
0x14003f160  test    eax, eax
0x14003f162  js      loc_14003F05B
0x14003f168  lfence
0x14003f16b  lea     rax, [r14+7]
0x14003f16f  mov     r9b, 1
0x14003f172  lea     rax, [rdi+rax*8]
0x14003f176  mov     edx, r15d
0x14003f179  mov     [rsp+98h+var_70], rax
0x14003f17e  lea     r8, [rbp+40h]
0x14003f182  mov     al, byte ptr cs:word_14001B724
0x14003f188  add     r8, rsi
0x14003f18b  mov     rcx, r12
0x14003f18e  mov     [rsp+98h+var_78], al
0x14003f192  call    SecRetrieveDriverConfigurationNamesArray
0x14003f197  mov     ebx, eax
0x14003f199  test    eax, eax
0x14003f19b  js      loc_14003F05B
0x14003f1a1  lfence
0x14003f1a4  lea     rax, [r14+8]
0x14003f1a8  mov     r9b, 1
0x14003f1ab  lea     rax, [rdi+rax*8]
0x14003f1af  mov     edx, r15d
0x14003f1b2  mov     [rsp+98h+var_70], rax
0x14003f1b7  lea     r8, [rbp+50h]
0x14003f1bb  mov     al, byte ptr cs:word_14001B724
0x14003f1c1  add     r8, rsi
0x14003f1c4  mov     rcx, r12
0x14003f1c7  mov     [rsp+98h+var_78], al
0x14003f1cb  call    SecRetrieveDriverConfigurationNamesArray
0x14003f1d0  mov     ebx, eax
0x14003f1d2  test    eax, eax
0x14003f1d4  js      loc_14003F05B
0x14003f1da  lfence
0x14003f1dd  mov     [rdi+r14*8+28h], r13
0x14003f1e2  mov     eax, [rsi+rbp+30h]
0x14003f1e6  mov     [rdi+r14*8+20h], eax
0x14003f1eb  cmp     [rsi+rbp+30h], r13d
0x14003f1f0  jbe     loc_14003F374
0x14003f1f6  mov     edx, eax
0x14003f1f8  mov     r8d, 634C6353h; Tag
0x14003f1fe  mov     rax, cs:qword_140020008
0x14003f205  shl     rdx, 3; NumberOfBytes
0x14003f209  test    rax, rax
0x14003f20c  jz      short loc_14003F21B
0x14003f20e  mov     ecx, 100h
0x14003f213  call    cs:__guard_dispatch_icall_fptr
0x14003f219  jmp     short loc_14003F22C
0x14003f21b  mov     ecx, 1; PoolType
0x14003f220  call    cs:__imp_ExAllocatePoolWithTag
0x14003f227  nop     dword ptr [rax+rax+00h]
0x14003f22c  mov     [rdi+r14*8+28h], rax
0x14003f231  test    rax, rax
0x14003f234  jz      loc_14003F056
0x14003f23a  mov     edx, [rsi+rbp+34h]
0x14003f23e  mov     eax, r13d
0x14003f241  add     rdx, r12
0x14003f244  mov     [rsp+98h+var_64], eax
0x14003f248  mov     [rsp+98h+var_48], rdx
0x14003f24d  cmp     [rsi+rbp+30h], r13d
0x14003f252  jbe     loc_14003F374
0x14003f258  mov     r13d, r15d
0x14003f25b  add     r13, r12
0x14003f25e  mov     ecx, eax
0x14003f260  mov     rax, [rdi+r14*8+28h]
0x14003f265  mov     qword ptr [rax+rcx*8], 0
0x14003f26d  mov     r15d, [rdx+rcx*8+4]
0x14003f272  mov     r8d, [rdx+rcx*8]
0x14003f276  add     r15, r12
0x14003f279  mov     dword ptr [rsp+98h+NumberOfBytes], r8d
0x14003f27e  lea     rax, [r15+28h]
0x14003f282  cmp     r13, r12
0x14003f285  jbe     loc_14003F3E3
0x14003f28b  cmp     rax, r15
0x14003f28e  jbe     loc_14003F3E3
0x14003f294  cmp     r15, r12
0x14003f297  jb      loc_14003F3E3
0x14003f29d  cmp     rax, r13
0x14003f2a0  ja      loc_14003F3E3
0x14003f2a6  lea     rcx, [r15+r8]
0x14003f2aa  cmp     rcx, r15
0x14003f2ad  jbe     loc_14003F3E3
0x14003f2b3  cmp     rcx, r13
0x14003f2b6  ja      loc_14003F3E3
0x14003f2bc  mov     rcx, r15; SecurityDescriptor
0x14003f2bf  call    cs:__imp_RtlValidSecurityDescriptor
0x14003f2c6  nop     dword ptr [rax+rax+00h]
0x14003f2cb  test    al, al
0x14003f2cd  jz      loc_14003F3D9
0x14003f2d3  mov     rcx, r15; SecurityDescriptor
0x14003f2d6  call    cs:__imp_RtlLengthSecurityDescriptor
0x14003f2dd  nop     dword ptr [rax+rax+00h]
0x14003f2e2  mov     ecx, dword ptr [rsp+98h+NumberOfBytes]
0x14003f2e6  cmp     eax, ecx
0x14003f2e8  jnz     loc_14003F3D9
0x14003f2ee  mov     rax, cs:qword_140020008
0x14003f2f5  mov     r8d, 634C6353h; Tag
0x14003f2fb  mov     edx, ecx; NumberOfBytes
0x14003f2fd  test    rax, rax
0x14003f300  jz      short loc_14003F30F
0x14003f302  mov     ecx, 100h
0x14003f307  call    cs:__guard_dispatch_icall_fptr
0x14003f30d  jmp     short loc_14003F320
0x14003f30f  mov     ecx, 1; PoolType
0x14003f314  call    cs:__imp_ExAllocatePoolWithTag
0x14003f31b  nop     dword ptr [rax+rax+00h]
0x14003f320  mov     r8d, [rsp+98h+var_64]
0x14003f325  mov     rdx, rax
0x14003f328  mov     rax, [rdi+r14*8+28h]
0x14003f32d  mov     [rax+r8*8], rdx
0x14003f331  mov     rax, [rdi+r14*8+28h]
0x14003f336  mov     rcx, [rax+r8*8]; void *
0x14003f33a  test    rcx, rcx
0x14003f33d  jz      loc_14003F056
0x14003f343  mov     r8d, dword ptr [rsp+98h+NumberOfBytes]; Size
0x14003f348  mov     rdx, r15; Src
0x14003f34b  call    memmove
0x14003f350  mov     eax, [rsp+98h+var_64]
0x14003f354  mov     rdx, [rsp+98h+var_48]
0x14003f359  inc     eax
0x14003f35b  mov     [rsp+98h+var_64], eax
0x14003f35f  cmp     eax, [rsi+rbp+30h]
0x14003f363  jb      loc_14003F25E
0x14003f369  mov     r15d, [rsp+98h+arg_18]
0x14003f371  xor     r13d, r13d
0x14003f374  mov     eax, dword ptr [rsp+98h+NumberOfBytes+4]
0x14003f378  inc     eax
0x14003f37a  mov     dword ptr [rsp+98h+NumberOfBytes+4], eax
0x14003f37e  cmp     eax, [rsp+98h+arg_8]
0x14003f385  jb      loc_14003F09C
0x14003f38b  mov     esi, [rsp+98h+var_68]
0x14003f38f  xor     edx, edx
0x14003f391  lea     rcx, SecLmfPolicyConfigLock
0x14003f398  call    FltAcquirePushLockExclusiveEx_0
0x14003f39d  mov     rax, cs:SecLmfNetworkSharePolicyConfig
0x14003f3a4  lea     rcx, SecLmfPolicyConfigLock
0x14003f3ab  mov     [rsp+98h+P], rax
0x14003f3b0  xor     edx, edx
0x14003f3b2  mov     eax, cs:SecLmfNetworkSharePolicyConfigCount
0x14003f3b8  mov     cs:SecLmfNetworkSharePolicyConfig, rdi
0x14003f3bf  mov     rdi, r13
0x14003f3c2  mov     [rsp+98h+var_58], eax
0x14003f3c6  mov     cs:SecLmfNetworkSharePolicyConfigCount, esi
0x14003f3cc  call    FltReleasePushLockEx_0
0x14003f3d1  mov     esi, r13d
0x14003f3d4  jmp     loc_14003F05F
0x14003f3d9  mov     ebx, 0C0000079h
0x14003f3de  jmp     loc_14003F05B
0x14003f3e3  mov     ebx, 0C000008Ch
0x14003f3e8  jmp     loc_14003F05B
0x14003f3ed  mov     ebx, 0C0000059h
0x14003f3f2  jmp     loc_14003F05B
```
