# wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180009cc0`
- end: `0x180009f10`
- name: `?Stop@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180008b80`
- `0x180009150`
- `0x18001a9fc`

## callees

- `0x180009cc0`
- `0x18000e83c`
- `0x1800106c0`
- `0x18002a3d0`
- `0x18002ebb0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d04`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d6f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d36`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009dcb`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009ea3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009ea3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        const struct wil::FailureInfo *a2)
{
  RTL_SRWLOCK *v3; // rbx
  RTL_SRWLOCK *v4; // rbx
  __int64 v5; // rax
  int v6; // esi
  int v7; // esi
  __int64 v8; // rbx
  const GUID *v9; // r8
  DWORD CurrentThreadId; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v16; // [rsp+70h] [rbp-90h]
  __int128 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+90h] [rbp-70h]
  __int128 v19; // [rsp+A0h] [rbp-60h]
  __int128 v20; // [rsp+B0h] [rbp-50h]
  __int128 v21; // [rsp+C0h] [rbp-40h]
  __int128 v22; // [rsp+D0h] [rbp-30h]
  __int128 v23; // [rsp+E0h] [rbp-20h]
  __int64 v24; // [rsp+F0h] [rbp-10h]

  v3 = (RTL_SRWLOCK *)a1[35];
  if ( v3 )
  {
    v4 = v3 + 33;
    AcquireSRWLockExclusive(v4);
  }
  else
  {
    v12 = 0;
    v4 = 0;
  }
  v5 = a1[34];
  v6 = *(_DWORD *)(v5 + 248);
  if ( v6 < 1 )
  {
    UserData = 0;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    wil::details::WilFailFast((wil::details *)&UserData, a2);
  }
  if ( *(int *)(v5 + 72) >= 0 )
    *(_DWORD *)(v5 + 72) = 0;
  v7 = v6 - 1;
  *(_DWORD *)(v5 + 248) = v7;
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  if ( v7 )
  {
    v8 = *((_QWORD *)DesktopShellHostExtensionsLogging::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u
      && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(v12) = 0;
      v13 = 0x1000000;
      v9 = (const GUID *)(a1[34] + 8LL);
      *(_QWORD *)&v19 = &CurrentThreadId;
      *((_QWORD *)&v19 + 1) = 4;
      *(_QWORD *)&v18 = &v12;
      *((_QWORD *)&v18 + 1) = 4;
      *(_QWORD *)&v17 = &v13;
      *((_QWORD *)&v17 + 1) = 8;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 5;
      EventDescriptor.Keyword = 0x400000000000LL;
      UserData.Ptr = *(_QWORD *)(v8 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      *(_QWORD *)&v16 = byte_180099B49;
      *((_QWORD *)&v16 + 1) = 0x10000004DLL;
      EventWriteTransfer(*(_QWORD *)(v8 + 32), &EventDescriptor, v9, 0, 5u, &UserData);
    }
  }
  else
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  return wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180009cc0  mov     [rsp-8+arg_8], rbx
0x180009cc5  mov     [rsp-8+arg_10], rsi
0x180009cca  push    rbp
0x180009ccb  push    rdi
0x180009ccc  push    r14
0x180009cce  lea     rbp, [rsp-10h]
0x180009cd3  sub     rsp, 110h
0x180009cda  mov     rax, cs:__security_cookie
0x180009ce1  xor     rax, rsp
0x180009ce4  mov     [rbp+20h+var_20], rax
0x180009ce8  mov     rdi, rcx
0x180009ceb  xor     r14d, r14d
0x180009cee  mov     rbx, [rcx+118h]
0x180009cf5  test    rbx, rbx
0x180009cf8  jz      short loc_180009D24
0x180009cfa  add     rbx, 108h
0x180009d01  mov     rcx, rbx; SRWLock
0x180009d04  call    cs:__imp_AcquireSRWLockExclusive
0x180009d0a  lea     rax, [rsp+120h+SRWLock]
0x180009d0f  mov     [rax], r14
0x180009d12  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x180009d17  test    rcx, rcx
0x180009d1a  jz      short loc_180009D3F
0x180009d1c  call    cs:__imp_ReleaseSRWLockExclusive
0x180009d22  jmp     short loc_180009D3F
0x180009d24  lea     rax, [rsp+120h+var_E0]
0x180009d29  mov     [rax], r14
0x180009d2c  mov     rcx, [rsp+120h+var_E0]; SRWLock
0x180009d31  test    rcx, rcx
0x180009d34  jz      short loc_180009D3C
0x180009d36  call    cs:__imp_ReleaseSRWLockExclusive
0x180009d3c  mov     rbx, r14
0x180009d3f  mov     rax, [rdi+110h]
0x180009d46  mov     esi, [rax+0F8h]
0x180009d4c  cmp     esi, 1
0x180009d4f  jl      loc_180009ED6
0x180009d55  cmp     dword ptr [rax+48h], 0
0x180009d59  jl      short loc_180009D5F
0x180009d5b  mov     [rax+48h], r14d
0x180009d5f  dec     esi
0x180009d61  mov     [rax+0F8h], esi
0x180009d67  test    rbx, rbx
0x180009d6a  jz      short loc_180009D75
0x180009d6c  mov     rcx, rbx; SRWLock
0x180009d6f  call    cs:__imp_ReleaseSRWLockExclusive
0x180009d75  test    esi, esi
0x180009d77  jnz     short loc_180009D8D
0x180009d79  mov     rax, [rdi]
0x180009d7c  mov     rcx, rdi
0x180009d7f  mov     rax, [rax+8]
0x180009d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d88  jmp     loc_180009EA9
0x180009d8d  call    ?Instance@DesktopShellHostExtensionsLogging@@KAPEAV1@XZ; DesktopShellHostExtensionsLogging::Instance(void)
0x180009d92  mov     rbx, [rax+8]
0x180009d96  mov     eax, [rbx]
0x180009d98  cmp     eax, 5
0x180009d9b  jbe     loc_180009EA9
0x180009da1  mov     rcx, [rbx+18h]
0x180009da5  mov     rax, [rbx+10h]
0x180009da9  mov     rsi, 400000000000h
0x180009db3  test    rsi, rax
0x180009db6  jz      loc_180009EA9
0x180009dbc  mov     rax, rcx
0x180009dbf  and     rax, rsi
0x180009dc2  cmp     rax, rcx
0x180009dc5  jnz     loc_180009EA9
0x180009dcb  call    cs:__imp_GetCurrentThreadId
0x180009dd1  mov     [rsp+120h+var_E8], eax
0x180009dd5  mov     dword ptr [rsp+120h+var_E0], r14d
0x180009dda  mov     [rsp+120h+var_D8], 1000000h
0x180009de3  mov     r8, [rdi+110h]
0x180009dea  add     r8, 8; ActivityId
0x180009dee  lea     rax, [rsp+120h+var_E8]
0x180009df3  mov     qword ptr [rbp+20h+var_80], rax
0x180009df7  mov     qword ptr [rbp+20h+var_80+8], 4
0x180009dff  lea     rax, [rsp+120h+var_E0]
0x180009e04  mov     qword ptr [rbp+20h+var_90], rax
0x180009e08  mov     qword ptr [rbp+20h+var_90+8], 4
0x180009e10  lea     rax, [rsp+120h+var_D8]
0x180009e15  mov     qword ptr [rbp+20h+var_A0], rax
0x180009e19  mov     qword ptr [rbp+20h+var_A0+8], 8
0x180009e21  mov     dword ptr [rsp+120h+EventDescriptor.Id], 0B000000h
0x180009e29  movzx   eax, cs:word_180099B3F
0x180009e30  mov     dword ptr [rsp+120h+EventDescriptor.Level], eax
0x180009e34  mov     [rsp+120h+EventDescriptor.Keyword], rsi
0x180009e39  mov     rax, [rbx+8]
0x180009e3d  mov     [rsp+120h+var_C0.Ptr], rax
0x180009e42  movzx   eax, word ptr [rax]
0x180009e45  mov     [rsp+120h+var_C0.Size], eax
0x180009e49  mov     dword ptr [rsp+120h+var_C0.0Ch], 2
0x180009e51  lea     rax, byte_180099B49
0x180009e58  mov     qword ptr [rsp+120h+var_B0], rax
0x180009e5d  mov     dword ptr [rsp+120h+var_B0+8], 4Dh ; 'M'
0x180009e65  mov     dword ptr [rsp+120h+var_B0+0Ch], 1
0x180009e6d  lea     rax, _TraceLoggingMetadataEnd
0x180009e74  lea     rcx, _TraceLoggingMetadata
0x180009e7b  sub     eax, ecx
0x180009e7d  mov     dword ptr [rsp+120h+SRWLock], eax
0x180009e81  mov     eax, dword ptr [rsp+120h+SRWLock]
0x180009e85  lea     rax, [rsp+120h+var_C0]
0x180009e8a  mov     [rsp+120h+UserData], rax; UserData
0x180009e8f  mov     [rsp+120h+UserDataCount], 5; UserDataCount
0x180009e97  xor     r9d, r9d; RelatedActivityId
0x180009e9a  lea     rdx, [rsp+120h+EventDescriptor]; EventDescriptor
0x180009e9f  mov     rcx, [rbx+20h]; RegHandle
0x180009ea3  call    cs:__imp_EventWriteTransfer
0x180009ea9  mov     rcx, rdi
0x180009eac  call    ?IgnoreCurrentThread@?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180009eb1  nop
0x180009eb2  mov     rcx, [rbp+20h+var_20]
0x180009eb6  xor     rcx, rsp; StackCookie
0x180009eb9  call    __security_check_cookie
0x180009ebe  lea     r11, [rsp+120h+var_10]
0x180009ec6  mov     rbx, [r11+28h]
0x180009eca  mov     rsi, [r11+30h]
0x180009ece  mov     rsp, r11
0x180009ed1  pop     r14
0x180009ed3  pop     rdi
0x180009ed4  pop     rbp
0x180009ed5  retn
0x180009ed6  xorps   xmm0, xmm0
0x180009ed9  xor     eax, eax
0x180009edb  movups  xmmword ptr [rsp+120h+var_C0.Ptr], xmm0
0x180009ee0  movups  [rsp+120h+var_B0], xmm0
0x180009ee5  movups  [rbp+20h+var_A0], xmm0
0x180009ee9  movups  [rbp+20h+var_90], xmm0
0x180009eed  movups  [rbp+20h+var_80], xmm0
0x180009ef1  movups  [rbp+20h+var_70], xmm0
0x180009ef5  movups  [rbp+20h+var_60], xmm0
0x180009ef9  movups  [rbp+20h+var_50], xmm0
0x180009efd  movups  [rbp+20h+var_40], xmm0
0x180009f01  mov     [rbp+20h+var_30], rax
0x180009f05  lea     rcx, [rsp+120h+var_C0]; this
0x180009f0a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
