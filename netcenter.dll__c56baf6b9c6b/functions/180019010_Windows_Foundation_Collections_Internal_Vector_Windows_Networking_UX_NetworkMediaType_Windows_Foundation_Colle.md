# Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::RemoveAtInternal(uint,bool)

- ea: `0x180019010`
- end: `0x18001915e`
- name: `?RemoveAtInternal@?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@Windows@@AEAAJI_N@Z`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180018ff0`
- `0x180019000`

## callees

- `0x18001697c`
- `0x180018c60`
- `0x180019010`
- `0x1800192f4`
- `0x180019550`
- `0x180019800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019122`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019122`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019069`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800190c3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019069`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800190c3`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>::RemoveAtInternal(
        __int64 a1,
        unsigned int a2,
        char a3)
{
  int v6; // ebx
  unsigned int *v7; // rsi
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  RTL_SRWLOCK *v10; // rcx
  int v12; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+68h] [rbp+20h] BYREF

  v12 = 0;
  XWinRT::SerializingLockPolicy::Write(&v13, a1 + 80, &v12);
  v6 = v12;
  if ( v12 >= 0 )
  {
    v7 = (unsigned int *)(a1 + 48);
    if ( a3 )
      a2 = *v7 - 1;
    if ( a2 >= *v7 )
    {
      v6 = -2147483637;
      RoOriginateError(2147483659LL, 0);
    }
    if ( v6 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v12, *(unsigned __int8 *)(a1 + 101), a1 + 104);
      v6 = 0;
      if ( a2 < *v7 - 1
        && memmove_s(
             (void *const)(*(_QWORD *)(a1 + 64) + 4LL * a2),
             4LL * (*v7 - a2 - 1),
             (const void *const)(*(_QWORD *)(a1 + 64) + 4LL * (a2 + 1)),
             4LL * (*v7 - a2 - 1)) )
      {
        v6 = -2147418113;
        RoOriginateError(2147549183LL, 0);
      }
      else
      {
        v8 = *(_DWORD *)(a1 + 52);
        ++*(_DWORD *)(a1 + 96);
        if ( --*v7 < v8 / 3 )
        {
          v9 = 1;
          if ( v8 - 1 >= v8 - v8 / 3 )
            v9 = v8 / 3;
          v6 = Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>::ResizeStorage(
                 a1,
                 v8 - v9);
        }
      }
    }
  }
  if ( v13 )
  {
    v10 = v13 + 1;
    if ( LODWORD(v13->Ptr) == 1 )
      LODWORD(v10->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v10);
  }
  if ( v6 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<enum Windows::Networking::UX::NetworkMediaType,0,0,0>::RaiseEvent(
                           (unsigned __int8)v12,
                           *(unsigned __int8 *)(a1 + 100),
                           a1,
                           2,
                           a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180019010  mov     rax, rsp
0x180019013  mov     [rax+10h], rbx
0x180019017  mov     [rax+18h], rbp
0x18001901b  push    rsi
0x18001901c  push    rdi
0x18001901d  push    r14
0x18001901f  sub     rsp, 30h
0x180019023  mov     ebp, edx
0x180019025  mov     dword ptr [rax+8], 0
0x18001902c  lea     rdx, [rcx+50h]
0x180019030  mov     r14b, r8b
0x180019033  mov     rdi, rcx
0x180019036  lea     r8, [rax+8]
0x18001903a  lea     rcx, [rax+20h]
0x18001903e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180019043  mov     ebx, [rsp+48h+arg_0]
0x180019047  test    ebx, ebx
0x180019049  js      loc_180019107
0x18001904f  lea     rsi, [rdi+30h]
0x180019053  test    r14b, r14b
0x180019056  jz      short loc_18001905C
0x180019058  mov     ebp, [rsi]
0x18001905a  dec     ebp
0x18001905c  cmp     ebp, [rsi]
0x18001905e  jb      short loc_18001906F
0x180019060  mov     ebx, 8000000Bh
0x180019065  xor     edx, edx
0x180019067  mov     ecx, ebx
0x180019069  call    cs:__imp_RoOriginateError
0x18001906f  test    ebx, ebx
0x180019071  js      loc_180019107
0x180019077  movzx   edx, byte ptr [rdi+65h]
0x18001907b  lea     r8, [rdi+68h]
0x18001907f  lea     rcx, [rsp+48h+arg_0]
0x180019084  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180019089  mov     ecx, [rsi]
0x18001908b  xor     ebx, ebx
0x18001908d  lea     eax, [rcx-1]
0x180019090  cmp     ebp, eax
0x180019092  jnb     short loc_1800190CB
0x180019094  mov     r9, [rdi+40h]
0x180019098  lea     eax, [rbp+1]
0x18001909b  sub     ecx, ebp
0x18001909d  lea     r8, [r9+rax*4]; Source
0x1800190a1  mov     eax, ebp
0x1800190a3  lea     edx, [rcx-1]
0x1800190a6  shl     rdx, 2; DestinationSize
0x1800190aa  lea     rcx, [r9+rax*4]; Destination
0x1800190ae  mov     r9, rdx; SourceSize
0x1800190b1  call    memmove_s
0x1800190b6  test    eax, eax
0x1800190b8  jz      short loc_1800190CB
0x1800190ba  mov     ebx, 8000FFFFh
0x1800190bf  xor     edx, edx
0x1800190c1  mov     ecx, ebx
0x1800190c3  call    cs:__imp_RoOriginateError
0x1800190c9  jmp     short loc_180019107
0x1800190cb  mov     r9d, [rdi+34h]
0x1800190cf  mov     eax, 0AAAAAAABh
0x1800190d4  inc     dword ptr [rdi+60h]
0x1800190d7  dec     dword ptr [rsi]
0x1800190d9  mul     r9d
0x1800190dc  shr     edx, 1
0x1800190de  cmp     [rsi], edx
0x1800190e0  jnb     short loc_180019107
0x1800190e2  mov     ecx, r9d
0x1800190e5  lea     eax, [r9-1]
0x1800190e9  sub     ecx, edx
0x1800190eb  mov     r8d, 1
0x1800190f1  cmp     eax, ecx
0x1800190f3  mov     rcx, rdi
0x1800190f6  cmovnb  r8d, edx
0x1800190fa  sub     r9d, r8d
0x1800190fd  mov     edx, r9d
0x180019100  call    ?ResizeStorage@?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@Windows@@AEAAJI@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::ResizeStorage(uint)
0x180019105  mov     ebx, eax
0x180019107  mov     rax, [rsp+48h+arg_18]
0x18001910c  test    rax, rax
0x18001910f  jz      short loc_180019128
0x180019111  cmp     dword ptr [rax], 1
0x180019114  lea     rcx, [rax+8]; SRWLock
0x180019118  jnz     short loc_180019122
0x18001911a  add     dword ptr [rcx], 10000000h
0x180019120  jmp     short loc_180019128
0x180019122  call    cs:__imp_ReleaseSRWLockExclusive
0x180019128  test    ebx, ebx
0x18001912a  js      short loc_180019149
0x18001912c  movzx   edx, byte ptr [rdi+64h]
0x180019130  mov     r9d, 2
0x180019136  movzx   ecx, byte ptr [rsp+48h+arg_0]
0x18001913b  mov     r8, rdi
0x18001913e  mov     [rsp+48h+var_28], ebp
0x180019142  call    ?RaiseEvent@?$VectorOptions@W4NetworkMediaType@UX@Networking@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::NetworkMediaType,0,0,0>::RaiseEvent(...)
0x180019147  mov     ebx, eax
0x180019149  mov     rbp, [rsp+48h+arg_10]
0x18001914e  mov     eax, ebx
0x180019150  mov     rbx, [rsp+48h+arg_8]
0x180019155  add     rsp, 30h
0x180019159  pop     r14
0x18001915b  pop     rdi
0x18001915c  pop     rsi
0x18001915d  retn
```
