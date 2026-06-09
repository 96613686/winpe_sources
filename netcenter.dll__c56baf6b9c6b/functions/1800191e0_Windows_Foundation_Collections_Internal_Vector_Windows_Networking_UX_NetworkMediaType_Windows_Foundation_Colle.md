# Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>::ReplaceAll(uint,Windows::Networking::UX::NetworkMediaType *)

- ea: `0x1800191e0`
- end: `0x1800192eb`
- name: `?ReplaceAll@?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@Windows@@UEAAJIPEAW4NetworkMediaType@UX@Networking@5@@Z`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18001697c`
- `0x180018c60`
- `0x1800191e0`
- `0x180019550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800192ad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800192ad`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001920c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001920c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001929f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001929f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>::ReplaceAll(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  unsigned int v3; // ebp
  _DWORD *v6; // rsi
  int v7; // ebx
  __int64 v8; // r14
  _DWORD *v9; // rax
  RTL_SRWLOCK *v10; // rcx
  RTL_SRWLOCK *v12; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+78h] [rbp+20h] BYREF

  v3 = a2;
  v13 = 0;
  if ( a2 )
  {
    v6 = malloc(4LL * a2);
    if ( !v6 )
      return (unsigned int)-2147024882;
    v8 = 0;
    do
    {
      v6[v8] = *(_DWORD *)(a3 + 4 * v8);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < v3 );
  }
  else
  {
    LODWORD(v8) = 0;
    v6 = 0;
    v3 = 0;
  }
  XWinRT::SerializingLockPolicy::Write(&v12, a1 + 80, &v13);
  v7 = v13;
  if ( v13 >= 0 )
  {
    XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v13, *(unsigned __int8 *)(a1 + 101), a1 + 104);
    *(_DWORD *)(a1 + 48) = v8;
    v7 = 0;
    *(_DWORD *)(a1 + 52) = v3;
    v9 = *(_DWORD **)(a1 + 64);
    *(_QWORD *)(a1 + 64) = v6;
    v6 = v9;
    ++*(_DWORD *)(a1 + 96);
  }
  if ( v12 )
  {
    v10 = v12 + 1;
    if ( LODWORD(v12->Ptr) == 1 )
      LODWORD(v10->Ptr) += 0x10000000;
    else
      ReleaseSRWLockExclusive(v10);
  }
  if ( v6 )
    free(v6);
  if ( v7 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::VectorOptions<enum Windows::Networking::UX::NetworkMediaType,0,0,0>::RaiseEvent(
                           (unsigned __int8)v13,
                           *(unsigned __int8 *)(a1 + 100),
                           a1,
                           0,
                           0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800191e0  mov     [rsp+arg_0], rbx
0x1800191e5  mov     [rsp+arg_8], rbp
0x1800191ea  push    rsi
0x1800191eb  push    rdi
0x1800191ec  push    r14
0x1800191ee  sub     rsp, 40h
0x1800191f2  mov     ebp, edx
0x1800191f4  mov     rbx, r8
0x1800191f7  mov     [rsp+58h+arg_18], 0
0x1800191ff  mov     rdi, rcx
0x180019202  test    edx, edx
0x180019204  jz      short loc_180019239
0x180019206  mov     ecx, ebp
0x180019208  shl     rcx, 2; Size
0x18001920c  call    cs:__imp_malloc
0x180019212  mov     rsi, rax
0x180019215  test    rax, rax
0x180019218  jnz     short loc_180019224
0x18001921a  mov     ebx, 8007000Eh
0x18001921f  jmp     loc_1800192D6
0x180019224  xor     r14d, r14d
0x180019227  mov     eax, [rbx+r14*4]
0x18001922b  mov     [rsi+r14*4], eax
0x18001922f  inc     r14d
0x180019232  cmp     r14d, ebp
0x180019235  jb      short loc_180019227
0x180019237  jmp     short loc_180019240
0x180019239  xor     r14d, r14d
0x18001923c  xor     esi, esi
0x18001923e  xor     ebp, ebp
0x180019240  lea     rdx, [rdi+50h]
0x180019244  lea     r8, [rsp+58h+arg_18]
0x180019249  lea     rcx, [rsp+58h+var_28]
0x18001924e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180019253  mov     ebx, [rsp+58h+arg_18]
0x180019257  test    ebx, ebx
0x180019259  js      short loc_180019284
0x18001925b  movzx   edx, byte ptr [rdi+65h]
0x18001925f  lea     r8, [rdi+68h]
0x180019263  lea     rcx, [rsp+58h+arg_18]
0x180019268  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x18001926d  mov     [rdi+30h], r14d
0x180019271  xor     ebx, ebx
0x180019273  mov     [rdi+34h], ebp
0x180019276  mov     rax, [rdi+40h]
0x18001927a  mov     [rdi+40h], rsi
0x18001927e  mov     rsi, rax
0x180019281  inc     dword ptr [rdi+60h]
0x180019284  mov     rax, [rsp+58h+var_28]
0x180019289  test    rax, rax
0x18001928c  jz      short loc_1800192A5
0x18001928e  cmp     dword ptr [rax], 1
0x180019291  lea     rcx, [rax+8]; SRWLock
0x180019295  jnz     short loc_18001929F
0x180019297  add     dword ptr [rcx], 10000000h
0x18001929d  jmp     short loc_1800192A5
0x18001929f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800192a5  test    rsi, rsi
0x1800192a8  jz      short loc_1800192B3
0x1800192aa  mov     rcx, rsi; Block
0x1800192ad  call    cs:__imp_free
0x1800192b3  test    ebx, ebx
0x1800192b5  js      short loc_1800192D6
0x1800192b7  movzx   edx, byte ptr [rdi+64h]
0x1800192bb  xor     r9d, r9d
0x1800192be  movzx   ecx, byte ptr [rsp+58h+arg_18]
0x1800192c3  mov     r8, rdi
0x1800192c6  mov     [rsp+58h+var_38], 0
0x1800192cf  call    ?RaiseEvent@?$VectorOptions@W4NetworkMediaType@UX@Networking@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::NetworkMediaType,0,0,0>::RaiseEvent(...)
0x1800192d4  mov     ebx, eax
0x1800192d6  mov     rbp, [rsp+58h+arg_8]
0x1800192db  mov     eax, ebx
0x1800192dd  mov     rbx, [rsp+58h+arg_0]
0x1800192e2  add     rsp, 40h
0x1800192e6  pop     r14
0x1800192e8  pop     rdi
0x1800192e9  pop     rsi
0x1800192ea  retn
```
