# PsmSrvQueryCurrentApplications

- ea: `0x18002b200`
- end: `0x18002b466`
- name: `PsmSrvQueryCurrentApplications`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001fdc`
- `0x1800032a0`
- `0x180003660`
- `0x180003700`
- `0x18000436c`
- `0x18000ddf0`
- `0x180014e68`
- `0x18001b7e0`
- `0x18001c10c`
- `0x18001d0f8`
- `0x18001d688`
- `0x18001da80`
- `0x180025894`
- `0x18002834c`
- `0x18002b200`
- `0x18002dab0`
- `0x18002e17c`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18002b3df`
- `ntdll!RtlCopySid` at `0x18002b3df`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b338`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b338`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b356`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b356`

## pseudocode

```c
__int64 __fastcall PsmSrvQueryCurrentApplications(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5,
        __int64 a6,
        unsigned int *a7)
{
  const unsigned __int16 *v7; // rbx
  RPC_STATUS v10; // esi
  PVOID Heap; // rax
  void *v12; // r15
  char *i; // rcx
  __int64 j; // rdx
  __int64 k; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  struct _PSM_APPLICATION *NextApplication; // rax
  __int64 v19; // rbp
  __int64 NextUserContext; // rax
  __int64 v21; // rdi
  unsigned __int64 NextManagerContext; // r14
  unsigned int v23; // edi
  __int64 NextAppInfo; // rax
  void *v25; // rbp
  __int64 v26; // r13
  _DWORD *v27; // r14
  _DWORD *v28; // rbx
  int v30; // [rsp+30h] [rbp-118h] BYREF
  __int64 v31; // [rsp+38h] [rbp-110h] BYREF
  const unsigned __int16 *v32; // [rsp+40h] [rbp-108h]
  __int64 v33; // [rsp+48h] [rbp-100h]
  unsigned int *v34; // [rsp+50h] [rbp-F8h]
  unsigned int *v35; // [rsp+58h] [rbp-F0h]
  _BYTE DestinationSid[80]; // [rsp+60h] [rbp-E8h] BYREF
  _BYTE Sid2[80]; // [rsp+B0h] [rbp-98h] BYREF

  v35 = a5;
  v7 = a3;
  v33 = a6;
  v34 = a7;
  v32 = a3;
  v31 = 0;
  memset_0(Sid2, 0, 0x44u);
  v30 = 0;
  if ( !v7 || a2 )
  {
    memset_0(DestinationSid, 0, 0x44u);
    PsmpGetDSMASid(DestinationSid);
    v10 = PsmpQueryCallerInformation(&v30, Sid2);
    if ( v10 >= 0 )
    {
      Heap = PsmpAllocateHeap(0xC08u);
      v12 = Heap;
      if ( Heap )
      {
        PsmpInitializeHashTable(Heap);
        for ( i = 0; ; i = (char *)NextManagerContext )
        {
          NextManagerContext = PsmpGetNextManagerContext(i);
          if ( !NextManagerContext )
            break;
          for ( j = 0; ; j = v21 )
          {
            NextUserContext = PsmpGetNextUserContext(NextManagerContext, j);
            v21 = NextUserContext;
            if ( !NextUserContext )
              break;
            if ( PsmpDoesCallerHaveAccessToUserInformation(Sid2, *(PSID *)(NextUserContext + 40), DestinationSid) )
            {
              for ( k = 0; ; k = v19 )
              {
                NextApplication = (struct _PSM_APPLICATION *)PsmpGetNextApplication(v21, k);
                v19 = (__int64)NextApplication;
                if ( !NextApplication )
                  break;
                if ( PsmpDoesApplicationMatchFilter(NextApplication, a2, v7) )
                {
                  RtlAcquireSRWLockExclusive(v19 + 328);
                  PsmpAllocateOrLookupApplicationInfo((__int64)v12, v16, v17, v19, &v31);
                  RtlReleaseSRWLockExclusive(v19 + 328);
                  v7 = v32;
                }
              }
            }
          }
        }
        v23 = 0;
        NextAppInfo = PsmpGetNextAppInfo(v12, 0);
        v25 = (void *)NextAppInfo;
        if ( NextAppInfo )
        {
          v26 = v33;
          v27 = (_DWORD *)NextAppInfo;
          do
          {
            if ( v23 < a4 )
            {
              v28 = (_DWORD *)(v26 + 536LL * v23);
              v28[17] = v27[29];
              RtlCopySid(0x44u, v28, v27 + 12);
              memcpy_0(v28 + 18, v27 + 31, (unsigned int)v27[30]);
            }
            PsmpDereferenceAppInfo(v25);
            ++v23;
            v25 = (void *)PsmpGetNextAppInfo(v12, v25);
            v27 = v25;
          }
          while ( v25 );
        }
        *v34 = v23;
        if ( v23 > a4 )
        {
          v10 = -2147483643;
          v23 = a4;
        }
        *v35 = v23;
        PsmpFreeHeap(v12);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741776;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b200  mov     [rsp+arg_0], rbx
0x18002b205  push    rbp
0x18002b206  push    rsi
0x18002b207  push    rdi
0x18002b208  push    r12
0x18002b20a  push    r13
0x18002b20c  push    r14
0x18002b20e  push    r15
0x18002b210  sub     rsp, 110h
0x18002b217  mov     rax, cs:__security_cookie
0x18002b21e  xor     rax, rsp
0x18002b221  mov     [rsp+148h+var_48], rax
0x18002b229  mov     rax, [rsp+148h+arg_20]
0x18002b231  lea     rcx, [rsp+148h+Sid2]; void *
0x18002b239  mov     [rsp+148h+var_F0], rax
0x18002b23e  mov     rbx, r8
0x18002b241  mov     rax, [rsp+148h+arg_28]
0x18002b249  mov     r13, rdx
0x18002b24c  mov     [rsp+148h+var_100], rax
0x18002b251  mov     edi, 44h ; 'D'
0x18002b256  mov     rax, [rsp+148h+arg_30]
0x18002b25e  mov     r8d, edi; Size
0x18002b261  xor     edx, edx; Val
0x18002b263  mov     [rsp+148h+var_F8], rax
0x18002b268  mov     r12d, r9d
0x18002b26b  mov     [rsp+148h+var_108], rbx
0x18002b270  mov     [rsp+148h+var_110], 0
0x18002b279  call    memset_0
0x18002b27e  mov     [rsp+148h+var_118], 0
0x18002b286  test    rbx, rbx
0x18002b289  jz      short loc_18002B29A
0x18002b28b  test    r13, r13
0x18002b28e  jnz     short loc_18002B29A
0x18002b290  mov     esi, 0C0000030h
0x18002b295  jmp     loc_18002B439
0x18002b29a  mov     r8, rdi; Size
0x18002b29d  lea     rcx, [rsp+148h+DestinationSid]; void *
0x18002b2a2  xor     edx, edx; Val
0x18002b2a4  call    memset_0
0x18002b2a9  lea     rcx, [rsp+148h+DestinationSid]; DestinationSid
0x18002b2ae  call    PsmpGetDSMASid
0x18002b2b3  lea     rdx, [rsp+148h+Sid2]
0x18002b2bb  lea     rcx, [rsp+148h+var_118]
0x18002b2c0  call    PsmpQueryCallerInformation
0x18002b2c5  mov     esi, eax
0x18002b2c7  test    eax, eax
0x18002b2c9  js      loc_18002B439
0x18002b2cf  mov     ecx, 0C08h
0x18002b2d4  call    PsmpAllocateHeap
0x18002b2d9  mov     r15, rax
0x18002b2dc  test    rax, rax
0x18002b2df  jnz     short loc_18002B2EB
0x18002b2e1  mov     esi, 0C0000017h
0x18002b2e6  jmp     loc_18002B439
0x18002b2eb  mov     rcx, r15
0x18002b2ee  call    PsmpInitializeHashTable
0x18002b2f3  xor     ecx, ecx
0x18002b2f5  jmp     loc_18002B38E
0x18002b2fa  xor     edx, edx
0x18002b2fc  jmp     short loc_18002B377
0x18002b2fe  mov     rdx, [rdi+28h]; Sid1
0x18002b302  lea     r8, [rsp+148h+DestinationSid]; PSID
0x18002b307  lea     rcx, [rsp+148h+Sid2]; Sid2
0x18002b30f  call    PsmpDoesCallerHaveAccessToUserInformation
0x18002b314  test    al, al
0x18002b316  jz      short loc_18002B374
0x18002b318  xor     edx, edx
0x18002b31a  jmp     short loc_18002B364
0x18002b31c  mov     r8, rbx; unsigned __int16 *
0x18002b31f  mov     rdx, r13; unsigned __int16 *
0x18002b322  mov     rcx, rbp; struct _PSM_APPLICATION *
0x18002b325  call    ?PsmpDoesApplicationMatchFilter@@YAEPEAU_PSM_APPLICATION@@PEBG1@Z; PsmpDoesApplicationMatchFilter(_PSM_APPLICATION *,ushort const *,ushort const *)
0x18002b32a  test    al, al
0x18002b32c  jz      short loc_18002B361
0x18002b32e  lea     rbx, [rbp+148h]
0x18002b335  mov     rcx, rbx
0x18002b338  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b33e  lea     rax, [rsp+148h+var_110]
0x18002b343  mov     r9, rbp
0x18002b346  mov     rcx, r15
0x18002b349  mov     [rsp+148h+var_128], rax
0x18002b34e  call    PsmpAllocateOrLookupApplicationInfo
0x18002b353  mov     rcx, rbx
0x18002b356  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b35c  mov     rbx, [rsp+148h+var_108]
0x18002b361  mov     rdx, rbp
0x18002b364  mov     rcx, rdi
0x18002b367  call    PsmpGetNextApplication
0x18002b36c  mov     rbp, rax
0x18002b36f  test    rax, rax
0x18002b372  jnz     short loc_18002B31C
0x18002b374  mov     rdx, rdi
0x18002b377  mov     rcx, r14
0x18002b37a  call    PsmpGetNextUserContext
0x18002b37f  mov     rdi, rax
0x18002b382  test    rax, rax
0x18002b385  jnz     loc_18002B2FE
0x18002b38b  mov     rcx, r14; P
0x18002b38e  call    PsmpGetNextManagerContext
0x18002b393  mov     r14, rax
0x18002b396  test    rax, rax
0x18002b399  jnz     loc_18002B2FA
0x18002b39f  xor     edx, edx
0x18002b3a1  mov     rcx, r15
0x18002b3a4  xor     edi, edi
0x18002b3a6  call    PsmpGetNextAppInfo
0x18002b3ab  mov     rbp, rax
0x18002b3ae  test    rax, rax
0x18002b3b1  jz      short loc_18002B416
0x18002b3b3  mov     r13, [rsp+148h+var_100]
0x18002b3b8  mov     r14, rax
0x18002b3bb  cmp     edi, r12d
0x18002b3be  jnb     short loc_18002B3F6
0x18002b3c0  mov     eax, edi
0x18002b3c2  lea     r8, [r14+30h]; SourceSid
0x18002b3c6  imul    rbx, rax, 218h
0x18002b3cd  mov     eax, [r14+74h]
0x18002b3d1  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18002b3d6  add     rbx, r13
0x18002b3d9  mov     rdx, rbx; DestinationSid
0x18002b3dc  mov     [rbx+44h], eax
0x18002b3df  call    cs:__imp_RtlCopySid
0x18002b3e5  mov     r8d, [r14+78h]; Size
0x18002b3e9  lea     rdx, [r14+7Ch]; Src
0x18002b3ed  lea     rcx, [rbx+48h]; void *
0x18002b3f1  call    memcpy_0
0x18002b3f6  mov     rcx, rbp; P
0x18002b3f9  call    PsmpDereferenceAppInfo
0x18002b3fe  mov     rdx, rbp
0x18002b401  mov     rcx, r15
0x18002b404  inc     edi
0x18002b406  call    PsmpGetNextAppInfo
0x18002b40b  mov     rbp, rax
0x18002b40e  mov     r14, rax
0x18002b411  test    rax, rax
0x18002b414  jnz     short loc_18002B3BB
0x18002b416  mov     rax, [rsp+148h+var_F8]
0x18002b41b  mov     [rax], edi
0x18002b41d  cmp     edi, r12d
0x18002b420  jbe     short loc_18002B42A
0x18002b422  mov     esi, 80000005h
0x18002b427  mov     edi, r12d
0x18002b42a  mov     rax, [rsp+148h+var_F0]
0x18002b42f  mov     [rax], edi
0x18002b431  mov     rcx, r15
0x18002b434  call    PsmpFreeHeap
0x18002b439  mov     eax, esi
0x18002b43b  mov     rcx, [rsp+148h+var_48]
0x18002b443  xor     rcx, rsp; StackCookie
0x18002b446  call    __security_check_cookie
0x18002b44b  mov     rbx, [rsp+148h+arg_0]
0x18002b453  add     rsp, 110h
0x18002b45a  pop     r15
0x18002b45c  pop     r14
0x18002b45e  pop     r13
0x18002b460  pop     r12
0x18002b462  pop     rdi
0x18002b463  pop     rsi
0x18002b464  pop     rbp
0x18002b465  retn
```
