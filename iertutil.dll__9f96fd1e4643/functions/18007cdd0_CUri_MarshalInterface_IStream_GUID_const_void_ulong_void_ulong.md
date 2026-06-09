# CUri::MarshalInterface(IStream *,_GUID const &,void *,ulong,void *,ulong)

- ea: `0x18007cdd0`
- end: `0x18007cf76`
- name: `?MarshalInterface@CUri@@UEAAJPEAUIStream@@AEBU_GUID@@PEAXK2K@Z`
- size: `422`
- prototype: `int(CUri *__hidden this, struct IStream *, const struct _GUID *, void *, unsigned int, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18007c67c`
- `0x18007cdd0`
- `0x18007cf80`
- `0x18007d4c0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cf04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cf04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ced2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007ced2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007cee7`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18007cee7`

## pseudocode

```c
__int64 __fastcall CUri::MarshalInterface(
        CUri *this,
        struct IStream *a2,
        struct _GUID *a3,
        void *a4,
        unsigned int a5,
        void *a6,
        unsigned int a7)
{
  volatile signed __int32 *v7; // rsi
  HRESULT MarshalSizeMaxHelper; // ebx
  unsigned int v11; // r9d
  void *v14; // [rsp+20h] [rbp-48h]
  volatile signed __int32 *v15; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+8h] BYREF

  v7 = (volatile signed __int32 *)((char *)this - 24);
  if ( *((int *)this + 6) >= 0 )
    return (unsigned int)-2147418113;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v15 = 0;
  MarshalSizeMaxHelper = CUri::ValidateMarshalParams(this, a3, a3, a5, v14, a7);
  v16 = 0;
  if ( MarshalSizeMaxHelper >= 0 )
  {
    MarshalSizeMaxHelper = CUri::GetMarshalSizeMaxHelper((CUri *)v7, v11, &v16);
    if ( MarshalSizeMaxHelper >= 0 )
    {
      MarshalSizeMaxHelper = (*(__int64 (__fastcall **)(struct IStream *, unsigned int *, __int64))(*(_QWORD *)a2 + 32LL))(
                               a2,
                               &v16,
                               4);
      if ( MarshalSizeMaxHelper >= 0 )
      {
        MarshalSizeMaxHelper = (*(__int64 (__fastcall **)(struct IStream *, unsigned int *, __int64))(*(_QWORD *)a2 + 32LL))(
                                 a2,
                                 &a5,
                                 4);
        if ( MarshalSizeMaxHelper >= 0 )
        {
          if ( a5 < 2 )
            return (unsigned int)CUri::Save((CUri *)((char *)this + 8), a2, 1);
          if ( a5 != 3 )
            return (unsigned int)-2147024809;
          if ( CUri::s_fSecretInit )
            goto LABEL_23;
          MarshalSizeMaxHelper = 0;
          EnterCriticalSection(&CUri::s_csSecretBlock);
          if ( !CUri::s_fSecretInit )
          {
            MarshalSizeMaxHelper = CoCreateGuid(&CUri::s_SecretBlock);
            if ( MarshalSizeMaxHelper >= 0 )
              CUri::s_fSecretInit = 1;
          }
          LeaveCriticalSection(&CUri::s_csSecretBlock);
          if ( MarshalSizeMaxHelper >= 0 )
          {
LABEL_23:
            MarshalSizeMaxHelper = (*(__int64 (__fastcall **)(struct IStream *, GUID *, __int64))(*(_QWORD *)a2 + 32LL))(
                                     a2,
                                     &CUri::s_SecretBlock,
                                     16);
            if ( MarshalSizeMaxHelper >= 0 )
            {
              v15 = v7;
              _InterlockedIncrement(v7 + 2);
              return (unsigned int)(*(__int64 (__fastcall **)(struct IStream *, volatile signed __int32 **, __int64))(*(_QWORD *)a2 + 32LL))(
                                     a2,
                                     &v15,
                                     8);
            }
          }
        }
      }
    }
  }
  return (unsigned int)MarshalSizeMaxHelper;
}

```

## disassembly

```asm
0x18007cdd0  push    rbx
0x18007cdd2  push    rbp
0x18007cdd3  push    rsi
0x18007cdd4  push    rdi
0x18007cdd5  sub     rsp, 48h
0x18007cdd9  lea     rsi, [rcx-18h]
0x18007cddd  mov     rdi, rdx
0x18007cde0  cmp     dword ptr [rsi+30h], 0
0x18007cde4  mov     rbp, rcx
0x18007cde7  jl      short loc_18007CDF3
0x18007cde9  mov     ebx, 8000FFFFh
0x18007cdee  jmp     loc_18007CF6B
0x18007cdf3  test    rdi, rdi
0x18007cdf6  jnz     short loc_18007CE02
0x18007cdf8  mov     ebx, 80070057h
0x18007cdfd  jmp     loc_18007CF6B
0x18007ce02  mov     eax, [rsp+68h+arg_30]
0x18007ce09  mov     rdx, r8; struct _GUID *
0x18007ce0c  mov     r9d, [rsp+68h+arg_20]; unsigned int
0x18007ce14  mov     [rsp+68h+var_40], eax; unsigned int
0x18007ce18  call    ?ValidateMarshalParams@CUri@@AEAAJAEBU_GUID@@PEAXK1K@Z; CUri::ValidateMarshalParams(_GUID const &,void *,ulong,void *,ulong)
0x18007ce1d  mov     [rsp+68h+var_38], 0
0x18007ce26  mov     ebx, eax
0x18007ce28  mov     [rsp+68h+arg_0], 0
0x18007ce30  test    eax, eax
0x18007ce32  js      loc_18007CF6B
0x18007ce38  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18007ce3d  mov     edx, r9d; unsigned int
0x18007ce40  mov     rcx, rsi; this
0x18007ce43  call    ?GetMarshalSizeMaxHelper@CUri@@QEAAJKPEAK@Z; CUri::GetMarshalSizeMaxHelper(ulong,ulong *)
0x18007ce48  mov     ebx, eax
0x18007ce4a  test    eax, eax
0x18007ce4c  js      loc_18007CF6B
0x18007ce52  mov     rax, [rdi]
0x18007ce55  lea     rdx, [rsp+68h+arg_0]
0x18007ce5a  xor     r9d, r9d
0x18007ce5d  mov     rcx, rdi
0x18007ce60  mov     rax, [rax+20h]
0x18007ce64  lea     r8d, [r9+4]
0x18007ce68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce6d  mov     ebx, eax
0x18007ce6f  test    eax, eax
0x18007ce71  js      loc_18007CF6B
0x18007ce77  mov     rax, [rdi]
0x18007ce7a  lea     rdx, [rsp+68h+arg_20]
0x18007ce82  xor     r9d, r9d
0x18007ce85  mov     rcx, rdi
0x18007ce88  mov     rax, [rax+20h]
0x18007ce8c  lea     r8d, [r9+4]
0x18007ce90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ce95  mov     ebx, eax
0x18007ce97  test    eax, eax
0x18007ce99  js      loc_18007CF6B
0x18007ce9f  mov     eax, [rsp+68h+arg_20]
0x18007cea6  test    eax, eax
0x18007cea8  jz      loc_18007CF57
0x18007ceae  sub     eax, 1
0x18007ceb1  jz      loc_18007CF57
0x18007ceb7  cmp     eax, 2
0x18007ceba  jnz     loc_18007CDF8
0x18007cec0  cmp     cs:?s_fSecretInit@CUri@@0HA, 0; int CUri::s_fSecretInit
0x18007cec7  jnz     short loc_18007CF0E
0x18007cec9  lea     rcx, ?s_csSecretBlock@CUri@@0VCMutexSem@@A; lpCriticalSection
0x18007ced0  xor     ebx, ebx
0x18007ced2  call    cs:__imp_EnterCriticalSection
0x18007ced8  cmp     cs:?s_fSecretInit@CUri@@0HA, ebx; int CUri::s_fSecretInit
0x18007cede  jnz     short loc_18007CEFD
0x18007cee0  lea     rcx, ?s_SecretBlock@CUri@@0PAEA; pguid
0x18007cee7  call    cs:__imp_CoCreateGuid
0x18007ceed  mov     ebx, eax
0x18007ceef  test    eax, eax
0x18007cef1  js      short loc_18007CEFD
0x18007cef3  mov     cs:?s_fSecretInit@CUri@@0HA, 1; int CUri::s_fSecretInit
0x18007cefd  lea     rcx, ?s_csSecretBlock@CUri@@0VCMutexSem@@A; lpCriticalSection
0x18007cf04  call    cs:__imp_LeaveCriticalSection
0x18007cf0a  test    ebx, ebx
0x18007cf0c  js      short loc_18007CF6B
0x18007cf0e  mov     rax, [rdi]
0x18007cf11  lea     rdx, ?s_SecretBlock@CUri@@0PAEA; uchar near * CUri::s_SecretBlock
0x18007cf18  xor     r9d, r9d
0x18007cf1b  mov     rcx, rdi
0x18007cf1e  mov     rax, [rax+20h]
0x18007cf22  lea     r8d, [r9+10h]
0x18007cf26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf2b  mov     ebx, eax
0x18007cf2d  test    eax, eax
0x18007cf2f  js      short loc_18007CF6B
0x18007cf31  mov     [rsp+68h+var_38], rsi
0x18007cf36  lock inc dword ptr [rsi+8]
0x18007cf3a  mov     rax, [rdi]
0x18007cf3d  lea     rdx, [rsp+68h+var_38]
0x18007cf42  xor     r9d, r9d
0x18007cf45  mov     rcx, rdi
0x18007cf48  mov     rax, [rax+20h]
0x18007cf4c  lea     r8d, [r9+8]
0x18007cf50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf55  jmp     short loc_18007CF69
0x18007cf57  lea     rcx, [rbp+8]; this
0x18007cf5b  mov     r8d, 1; int
0x18007cf61  mov     rdx, rdi; struct IStream *
0x18007cf64  call    ?Save@CUri@@UEAAJPEAUIStream@@H@Z; CUri::Save(IStream *,int)
0x18007cf69  mov     ebx, eax
0x18007cf6b  mov     eax, ebx
0x18007cf6d  add     rsp, 48h
0x18007cf71  pop     rdi
0x18007cf72  pop     rsi
0x18007cf73  pop     rbp
0x18007cf74  pop     rbx
0x18007cf75  retn
```
