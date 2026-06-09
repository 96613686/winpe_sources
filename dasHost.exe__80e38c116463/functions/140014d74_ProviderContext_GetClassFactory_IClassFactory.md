# ProviderContext::GetClassFactory(IClassFactory * *)

- ea: `0x140014d74`
- end: `0x140014e10`
- name: `?GetClassFactory@ProviderContext@@QEAAJPEAPEAUIClassFactory@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct IClassFactory **)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140009850`
- `0x14000afa4`
- `0x14000d1f0`
- `0x14000d590`
- `0x14000fea4`
- `0x1400160d8`

## callees

- `0x140014d74`
- `0x140014e18`
- `0x1400158b4`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014d8d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140014d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014dff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140014dff`

## pseudocode

```c
__int64 __fastcall ProviderContext::GetClassFactory(RTL_SRWLOCK *this, struct IClassFactory **a2)
{
  RTL_SRWLOCK *v4; // rsi
  int v5; // ebx

  v4 = this + 16;
  AcquireSRWLockExclusive(this + 16);
  if ( this[17].Ptr || (v5 = ProviderContext::LoadAndInitializeDll((ProviderContext *)this), v5 >= 0) )
  {
    v5 = ((__int64 (__fastcall *)(RTL_SRWLOCK *, GUID *, struct IClassFactory **))this[17].Ptr)(
           &this[3],
           &IID_IClassFactory,
           a2);
    if ( v5 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_91edd21030e531619c269f99d7a31287_Traceguids,
        (unsigned int)v5);
  }
  ReleaseSRWLockExclusive(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140014d74  push    rbx
0x140014d76  push    rbp
0x140014d77  push    rsi
0x140014d78  push    rdi
0x140014d79  sub     rsp, 28h
0x140014d7d  mov     rbp, rdx
0x140014d80  mov     rdi, rcx
0x140014d83  lea     rsi, [rcx+80h]
0x140014d8a  mov     rcx, rsi; SRWLock
0x140014d8d  call    cs:__imp_AcquireSRWLockExclusive
0x140014d93  cmp     qword ptr [rdi+88h], 0
0x140014d9b  jnz     short loc_140014DAB
0x140014d9d  mov     rcx, rdi; this
0x140014da0  call    ?LoadAndInitializeDll@ProviderContext@@IEAAJXZ; ProviderContext::LoadAndInitializeDll(void)
0x140014da5  mov     ebx, eax
0x140014da7  test    eax, eax
0x140014da9  js      short loc_140014DFC
0x140014dab  lea     rcx, [rdi+18h]
0x140014daf  mov     r8, rbp
0x140014db2  lea     rdx, IID_IClassFactory
0x140014db9  mov     rax, [rdi+88h]
0x140014dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014dc5  mov     ebx, eax
0x140014dc7  test    eax, eax
0x140014dc9  jns     short loc_140014DFC
0x140014dcb  lea     rax, WPP_GLOBAL_Control
0x140014dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dd9  cmp     rcx, rax
0x140014ddc  jz      short loc_140014DFC
0x140014dde  cmp     byte ptr [rcx+19h], 2
0x140014de2  jb      short loc_140014DFC
0x140014de4  mov     edx, 11h
0x140014de9  mov     r9d, ebx
0x140014dec  lea     r8, WPP_91edd21030e531619c269f99d7a31287_Traceguids
0x140014df3  mov     rcx, [rcx+10h]
0x140014df7  call    WPP_SF_D
0x140014dfc  mov     rcx, rsi; SRWLock
0x140014dff  call    cs:__imp_ReleaseSRWLockExclusive
0x140014e05  mov     eax, ebx
0x140014e07  add     rsp, 28h
0x140014e0b  pop     rdi
0x140014e0c  pop     rsi
0x140014e0d  pop     rbp
0x140014e0e  pop     rbx
0x140014e0f  retn
```
