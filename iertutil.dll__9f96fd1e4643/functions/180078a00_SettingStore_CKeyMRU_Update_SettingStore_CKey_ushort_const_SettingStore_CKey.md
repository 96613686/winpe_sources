# SettingStore::CKeyMRU::Update(SettingStore::CKey *,ushort const *,SettingStore::CKey *)

- ea: `0x180078a00`
- end: `0x180078b2e`
- name: `?Update@CKeyMRU@SettingStore@@QEAAJPEAVCKey@2@PEBG0@Z`
- size: `302`
- prototype: `int(SettingStore::CKeyMRU *__hidden this, struct SettingStore::CKey *, const unsigned __int16 *, struct SettingStore::CKey *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d940`
- `0x18004b0dc`

## callees

- `0x180042aa0`
- `0x180078a00`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078a35`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180078a35`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180078a7d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180078a7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180078af7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180078af7`

## pseudocode

```c
__int64 __fastcall SettingStore::CKeyMRU::Update(
        RTL_SRWLOCK *this,
        struct SettingStore::CKey *a2,
        const unsigned __int16 *a3,
        struct SettingStore::CKey *a4)
{
  unsigned int v8; // r15d
  unsigned int i; // esi
  __int64 v10; // rbp
  int v11; // ebx
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-58h] BYREF
  int v14; // [rsp+38h] [rbp-50h]
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp+8h] BYREF

  v13 = this;
  v14 = 0;
  v8 = -2147024894;
  if ( this )
  {
    AcquireSRWLockExclusive(this);
    v14 = 1;
  }
  for ( i = 0; i < 0xC; ++i )
  {
    v10 = 68LL * i;
    if ( this[v10 + 1].Ptr == a2 && CompareStringW(0x7Fu, 1u, (PCNZWCH)&this[v10 + 2], -1, a3, -1) == 2 )
    {
      v11 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)this[v10 + 67].Ptr + 88LL))(this[v10 + 67].Ptr);
      if ( v11 == (*(unsigned int (__fastcall **)(struct SettingStore::CKey *))(*(_QWORD *)a4 + 88LL))(a4) )
      {
        _mm_lfence();
        (*(void (__fastcall **)(PVOID))(*(_QWORD *)this[v10 + 67].Ptr + 80LL))(this[v10 + 67].Ptr);
        this[v10 + 67].Ptr = a4;
        (*(void (__fastcall **)(struct SettingStore::CKey *))(*(_QWORD *)a4 + 72LL))(a4);
        PerformanceCount.QuadPart = 0;
        QueryPerformanceCounter(&PerformanceCount);
        v8 = 0;
        this[v10 + 68] = (RTL_SRWLOCK)PerformanceCount;
        break;
      }
    }
  }
  SettingStore::CRWLock2Handler<&public: void CRWLock2::AcquireExclusive(void),&public: void CRWLock2::ReleaseExclusive(void)>::~CRWLock2Handler<&public: void CRWLock2::AcquireExclusive(void),&public: void CRWLock2::ReleaseExclusive(void)>(&v13);
  return v8;
}

```

## disassembly

```asm
0x180078a00  push    rbx
0x180078a02  push    rbp
0x180078a03  push    rsi
0x180078a04  push    rdi
0x180078a05  push    r12
0x180078a07  push    r13
0x180078a09  push    r14
0x180078a0b  push    r15
0x180078a0d  sub     rsp, 48h
0x180078a11  mov     [rsp+88h+var_58], rcx
0x180078a16  mov     r14, r9
0x180078a19  mov     [rsp+88h+var_50], 0
0x180078a21  mov     r13, r8
0x180078a24  mov     r12, rdx
0x180078a27  mov     rdi, rcx
0x180078a2a  mov     r15d, 80070002h
0x180078a30  test    rcx, rcx
0x180078a33  jz      short loc_180078A43
0x180078a35  call    cs:__imp_AcquireSRWLockExclusive
0x180078a3b  mov     [rsp+88h+var_50], 1
0x180078a43  xor     esi, esi
0x180078a45  cmp     esi, 0Ch
0x180078a48  jnb     loc_180078B10
0x180078a4e  mov     eax, esi
0x180078a50  imul    rbp, rax, 220h
0x180078a57  cmp     [rdi+rbp+8], r12
0x180078a5c  jnz     short loc_180078AB1
0x180078a5e  or      r9d, 0FFFFFFFFh; cchCount1
0x180078a62  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x180078a6a  lea     r8, [rdi+10h]
0x180078a6e  mov     [rsp+88h+lpString2], r13; lpString2
0x180078a73  add     r8, rbp; lpString1
0x180078a76  lea     edx, [r9+2]; dwCmpFlags
0x180078a7a  lea     ecx, [rdx+7Eh]; Locale
0x180078a7d  call    cs:__imp_CompareStringW
0x180078a83  cmp     eax, 2
0x180078a86  jnz     short loc_180078AB1
0x180078a88  mov     rcx, [rdi+rbp+218h]
0x180078a90  mov     rax, [rcx]
0x180078a93  mov     rax, [rax+58h]
0x180078a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a9c  mov     rcx, [r14]
0x180078a9f  mov     ebx, eax
0x180078aa1  mov     rax, [rcx+58h]
0x180078aa5  mov     rcx, r14
0x180078aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078aad  cmp     ebx, eax
0x180078aaf  jz      short loc_180078AB5
0x180078ab1  inc     esi
0x180078ab3  jmp     short loc_180078A45
0x180078ab5  lfence
0x180078ab8  mov     rcx, [rdi+rbp+218h]
0x180078ac0  mov     rax, [rcx]
0x180078ac3  mov     rax, [rax+50h]
0x180078ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078acc  mov     [rdi+rbp+218h], r14
0x180078ad4  mov     rcx, r14
0x180078ad7  mov     rax, [r14]
0x180078ada  mov     rax, [rax+48h]
0x180078ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078ae3  lea     rcx, [rsp+88h+PerformanceCount]; lpPerformanceCount
0x180078aeb  mov     qword ptr [rsp+88h+PerformanceCount], 0
0x180078af7  call    cs:__imp_QueryPerformanceCounter
0x180078afd  mov     rax, qword ptr [rsp+88h+PerformanceCount]
0x180078b05  xor     r15d, r15d
0x180078b08  mov     [rdi+rbp+220h], rax
0x180078b10  lea     rcx, [rsp+88h+var_58]
0x180078b15  call    ??1?$CRWLock2Handler@$1?AcquireExclusive@CRWLock2@@QEAAXXZ$1?ReleaseExclusive@2@QEAAXXZ@SettingStore@@QEAA@XZ; SettingStore::CRWLock2Handler<&CRWLock2::AcquireExclusive(void),&CRWLock2::ReleaseExclusive(void)>::~CRWLock2Handler<&CRWLock2::AcquireExclusive(void),&CRWLock2::ReleaseExclusive(void)>(void)
0x180078b1a  mov     eax, r15d
0x180078b1d  add     rsp, 48h
0x180078b21  pop     r15
0x180078b23  pop     r14
0x180078b25  pop     r13
0x180078b27  pop     r12
0x180078b29  pop     rdi
0x180078b2a  pop     rsi
0x180078b2b  pop     rbp
0x180078b2c  pop     rbx
0x180078b2d  retn
```
