# SecLmfSetSysvolAccessPolicyConfiguration

- ea: `0x14003f4cc`
- end: `0x14003f710`
- name: `SecLmfSetSysvolAccessPolicyConfiguration`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140022dc0`

## callees

- `0x14001041f`
- `0x14001042b`
- `0x140011610`
- `0x14003e3e4`
- `0x14003eedc`
- `0x14003f4cc`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f547`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f547`

## pseudocode

```c
__int64 __fastcall SecLmfSetSysvolAccessPolicyConfiguration(__int64 a1, unsigned int a2, int a3, int a4)
{
  void *v4; // rbx
  int DriverConfigurationNamesArray; // edi
  int v7; // ebp
  SIZE_T v9; // rdx
  bool v10; // zf
  _DWORD *PoolWithTag; // rax
  int v12; // r9d
  __int64 v13; // r15
  _DWORD *v14; // r12
  _DWORD *v15; // r14
  int v16; // r9d
  int v17; // r9d
  __int64 v19; // [rsp+38h] [rbp-50h]
  int v20; // [rsp+40h] [rbp-48h]
  PVOID P; // [rsp+48h] [rbp-40h]

  v4 = 0;
  DriverConfigurationNamesArray = 0;
  P = 0;
  v7 = 0;
  if ( SecLmfInitialized )
  {
    if ( a2 )
    {
      v7 = a2;
      v9 = 40LL * a2;
      v10 = qword_140020008 == 0;
      _mm_lfence();
      if ( v10 )
        PoolWithTag = ExAllocatePoolWithTag(PagedPool, v9, 0x634C6353u);
      else
        PoolWithTag = (_DWORD *)qword_140020008(256, v9, 1665950547);
      v4 = PoolWithTag;
      if ( PoolWithTag )
      {
        v13 = 0;
        _mm_lfence();
        v14 = PoolWithTag + 1;
        v15 = (_DWORD *)(a1 + 4);
        while ( *(v15 - 1) == 3 )
        {
          *(v14 - 1) = 3;
          LOBYTE(v12) = 1;
          v14[1] = v15[1];
          *v14 = *v15;
          v19 = 5 * v13;
          v20 = (_DWORD)v13 << 6;
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            a4,
                                            ((_DWORD)v13 << 6) + (int)a1 + 16,
                                            v12,
                                            word_14001B724,
                                            (__int64)v4 + 40 * v13 + 16);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_15;
          _mm_lfence();
          LOBYTE(v16) = 1;
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            a4,
                                            (int)a1 + v20 + 32,
                                            v16,
                                            word_14001B724,
                                            (__int64)v4 + 8 * v19 + 24);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_15;
          _mm_lfence();
          LOBYTE(v17) = 1;
          DriverConfigurationNamesArray = SecRetrieveDriverConfigurationNamesArray(
                                            a3,
                                            a4,
                                            (int)a1 + v20 + 48,
                                            v17,
                                            word_14001B724,
                                            (__int64)v4 + 8 * v19 + 32);
          if ( DriverConfigurationNamesArray < 0 )
            goto LABEL_15;
          v13 = (unsigned int)(v13 + 1);
          v15 += 16;
          v14 += 10;
          if ( (unsigned int)v13 >= a2 )
            goto LABEL_14;
        }
        DriverConfigurationNamesArray = -1073741735;
      }
      else
      {
        DriverConfigurationNamesArray = -1073741801;
      }
    }
    else
    {
LABEL_14:
      FltAcquirePushLockExclusiveEx_0(&SecLmfPolicyConfigLock, 0);
      P = (PVOID)SecLmfSysvolAccessPolicyConfig;
      SecLmfSysvolAccessPolicyConfigCount = v7;
      SecLmfSysvolAccessPolicyConfig = (__int64)v4;
      v4 = 0;
      FltReleasePushLockEx_0(&SecLmfPolicyConfigLock, 0);
    }
  }
LABEL_15:
  SecLmfFreeSysvolAccessPolicyConfiguration(P);
  SecLmfFreeSysvolAccessPolicyConfiguration(v4);
  return (unsigned int)DriverConfigurationNamesArray;
}

```

## disassembly

```asm
0x14003f4cc  mov     [rsp+arg_0], rbx
0x14003f4d1  mov     [rsp+arg_18], r9d
0x14003f4d6  mov     [rsp+arg_10], r8
0x14003f4db  push    rbp
0x14003f4dc  push    rsi
0x14003f4dd  push    rdi
0x14003f4de  push    r12
0x14003f4e0  push    r13
0x14003f4e2  push    r14
0x14003f4e4  push    r15
0x14003f4e6  sub     rsp, 50h
0x14003f4ea  xor     ebx, ebx
0x14003f4ec  mov     esi, edx
0x14003f4ee  xor     edi, edi
0x14003f4f0  mov     [rsp+88h+P], rbx
0x14003f4f5  xor     ebp, ebp
0x14003f4f7  mov     [rsp+88h+var_58], ebx
0x14003f4fb  cmp     cs:SecLmfInitialized, bl
0x14003f501  mov     r13, rcx
0x14003f504  jz      loc_14003F6D6
0x14003f50a  test    edx, edx
0x14003f50c  jz      loc_14003F693
0x14003f512  lea     rdx, [rsi+rsi*4]
0x14003f516  mov     ebp, esi
0x14003f518  shl     rdx, 3; NumberOfBytes
0x14003f51c  mov     r8d, 634C6353h; Tag
0x14003f522  cmp     cs:qword_140020008, rbx
0x14003f529  lfence
0x14003f52c  jz      short loc_14003F542
0x14003f52e  mov     rax, cs:qword_140020008
0x14003f535  mov     ecx, 100h
0x14003f53a  call    cs:__guard_dispatch_icall_fptr
0x14003f540  jmp     short loc_14003F553
0x14003f542  mov     ecx, 1; PoolType
0x14003f547  call    cs:__imp_ExAllocatePoolWithTag
0x14003f54e  nop     dword ptr [rax+rax+00h]
0x14003f553  mov     rbx, rax
0x14003f556  test    rax, rax
0x14003f559  jnz     short loc_14003F565
0x14003f55b  mov     edi, 0C0000017h
0x14003f560  jmp     loc_14003F6D6
0x14003f565  xor     r15d, r15d
0x14003f568  lfence
0x14003f56b  lea     r12, [rbx+4]
0x14003f56f  lea     r14, [r13+4]
0x14003f573  cmp     dword ptr [r14-4], 3
0x14003f578  jnz     loc_14003F709
0x14003f57e  mov     edx, [rsp+88h+arg_18]
0x14003f585  lea     r8, [r13+10h]
0x14003f589  mov     dword ptr [r12-4], 3
0x14003f592  mov     r9b, 1
0x14003f595  mov     eax, [r14+4]
0x14003f599  mov     [r12+4], eax
0x14003f59e  mov     eax, [r14]
0x14003f5a1  mov     [r12], eax
0x14003f5a5  lea     rax, [r15+r15*4]
0x14003f5a9  mov     [rsp+88h+var_50], rax
0x14003f5ae  add     rax, 2
0x14003f5b2  mov     ecx, r15d
0x14003f5b5  shl     rcx, 6
0x14003f5b9  mov     [rsp+88h+var_48], rcx
0x14003f5be  add     r8, rcx
0x14003f5c1  mov     rcx, [rsp+88h+arg_10]
0x14003f5c9  lea     rax, [rbx+rax*8]
0x14003f5cd  mov     [rsp+88h+var_60], rax
0x14003f5d2  mov     al, byte ptr cs:word_14001B724
0x14003f5d8  mov     [rsp+88h+var_68], al
0x14003f5dc  call    SecRetrieveDriverConfigurationNamesArray
0x14003f5e1  mov     edi, eax
0x14003f5e3  test    eax, eax
0x14003f5e5  js      loc_14003F6D6
0x14003f5eb  lfence
0x14003f5ee  mov     rax, [rsp+88h+var_50]
0x14003f5f3  mov     r9b, 1
0x14003f5f6  mov     r8, [rsp+88h+var_48]
0x14003f5fb  add     rax, 3
0x14003f5ff  mov     edx, [rsp+88h+arg_18]
0x14003f606  add     r8, 20h ; ' '
0x14003f60a  mov     rcx, [rsp+88h+arg_10]
0x14003f612  add     r8, r13
0x14003f615  lea     rax, [rbx+rax*8]
0x14003f619  mov     [rsp+88h+var_60], rax
0x14003f61e  mov     al, byte ptr cs:word_14001B724
0x14003f624  mov     [rsp+88h+var_68], al
0x14003f628  call    SecRetrieveDriverConfigurationNamesArray
0x14003f62d  mov     edi, eax
0x14003f62f  test    eax, eax
0x14003f631  js      loc_14003F6D6
0x14003f637  lfence
0x14003f63a  mov     rax, [rsp+88h+var_50]
0x14003f63f  mov     r9b, 1
0x14003f642  mov     r8, [rsp+88h+var_48]
0x14003f647  add     rax, 4
0x14003f64b  mov     edx, [rsp+88h+arg_18]
0x14003f652  add     r8, 30h ; '0'
0x14003f656  mov     rcx, [rsp+88h+arg_10]
0x14003f65e  add     r8, r13
0x14003f661  lea     rax, [rbx+rax*8]
0x14003f665  mov     [rsp+88h+var_60], rax
0x14003f66a  mov     al, byte ptr cs:word_14001B724
0x14003f670  mov     [rsp+88h+var_68], al
0x14003f674  call    SecRetrieveDriverConfigurationNamesArray
0x14003f679  mov     edi, eax
0x14003f67b  test    eax, eax
0x14003f67d  js      short loc_14003F6D6
0x14003f67f  inc     r15d
0x14003f682  add     r14, 40h ; '@'
0x14003f686  add     r12, 28h ; '('
0x14003f68a  cmp     r15d, esi
0x14003f68d  jb      loc_14003F573
0x14003f693  xor     edx, edx
0x14003f695  lea     rcx, SecLmfPolicyConfigLock
0x14003f69c  call    FltAcquirePushLockExclusiveEx_0
0x14003f6a1  mov     rax, cs:SecLmfSysvolAccessPolicyConfig
0x14003f6a8  lea     rcx, SecLmfPolicyConfigLock
0x14003f6af  mov     [rsp+88h+P], rax
0x14003f6b4  xor     edx, edx
0x14003f6b6  mov     eax, cs:SecLmfSysvolAccessPolicyConfigCount
0x14003f6bc  mov     cs:SecLmfSysvolAccessPolicyConfigCount, ebp
0x14003f6c2  xor     ebp, ebp
0x14003f6c4  mov     cs:SecLmfSysvolAccessPolicyConfig, rbx
0x14003f6cb  xor     ebx, ebx
0x14003f6cd  mov     [rsp+88h+var_58], eax
0x14003f6d1  call    FltReleasePushLockEx_0
0x14003f6d6  mov     edx, [rsp+88h+var_58]
0x14003f6da  mov     rcx, [rsp+88h+P]; P
0x14003f6df  call    SecLmfFreeSysvolAccessPolicyConfiguration
0x14003f6e4  mov     edx, ebp
0x14003f6e6  mov     rcx, rbx; P
0x14003f6e9  call    SecLmfFreeSysvolAccessPolicyConfiguration
0x14003f6ee  mov     rbx, [rsp+88h+arg_0]
0x14003f6f6  mov     eax, edi
0x14003f6f8  add     rsp, 50h
0x14003f6fc  pop     r15
0x14003f6fe  pop     r14
0x14003f700  pop     r13
0x14003f702  pop     r12
0x14003f704  pop     rdi
0x14003f705  pop     rsi
0x14003f706  pop     rbp
0x14003f707  retn
0x14003f709  mov     edi, 0C0000059h
0x14003f70e  jmp     short loc_14003F6D6
```
