# ContainerProvider::ShutdownAppSilo::StopActivity(void)

- ea: `0x180011d50`
- end: `0x180011fdf`
- name: `?StopActivity@ShutdownAppSilo@ContainerProvider@@MEAAXXZ`
- size: `655`
- prototype: `void __fastcall(ContainerProvider::ShutdownAppSilo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000134c`
- `0x180001660`
- `0x180007dd0`
- `0x18000895c`
- `0x18000af0c`
- `0x180011d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011daa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011f51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011daa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011f51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f6c`

## pseudocode

```c
void __fastcall ContainerProvider::ShutdownAppSilo::StopActivity(ContainerProvider::ShutdownAppSilo *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  __int64 v8; // r8
  int v9; // r9d
  int v10; // [rsp+C0h] [rbp-80h] BYREF
  int v11; // [rsp+C4h] [rbp-7Ch] BYREF
  int v12; // [rsp+C8h] [rbp-78h] BYREF
  int v13; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v14; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v15; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v16; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+100h] [rbp-40h] BYREF
  __int64 v21; // [rsp+108h] [rbp-38h] BYREF
  __int64 v22; // [rsp+110h] [rbp-30h] BYREF
  __int64 v23; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v24[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v26; // [rsp+158h] [rbp+18h] BYREF
  __int64 v27; // [rsp+160h] [rbp+20h] BYREF
  int v28; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = ContainerProvider::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v14 = *((_QWORD *)v4 + 6);
      LODWORD(SRWLock) = v4[17];
      v26 = v4[4];
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(v27) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v28 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      v10 = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v11 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v12 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v13 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v5,
        (unsigned int)&dword_18003BE6C,
        *((_QWORD *)this + 34) + 8,
        (_DWORD)v5,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v13,
        (__int64)&v22,
        (__int64)&v12,
        (__int64)&v21,
        (__int64)&v11,
        (__int64)&v20,
        (__int64)&v10,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v26,
        (__int64)&SRWLock,
        (__int64)&v14);
    }
  }
  else
  {
    wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = ContainerProvider::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v8 = *((_QWORD *)this + 34);
      v26 = *(_DWORD *)(v8 + 72);
      v27 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&word_18003C72E,
        v8 + 8,
        v9,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((ContainerProvider::ShutdownAppSilo *)((char *)this + 288));
}

```

## disassembly

```asm
0x180011d50  push    rbp
0x180011d52  push    rbx
0x180011d53  push    rdi
0x180011d54  lea     rbp, [rsp+10h]
0x180011d59  sub     rsp, 130h
0x180011d60  mov     rbx, rcx
0x180011d63  mov     rdi, [rcx+110h]
0x180011d6a  mov     eax, [rdi+48h]
0x180011d6d  test    eax, eax
0x180011d6f  jns     loc_180011F32
0x180011d75  add     rdi, 50h ; 'P'
0x180011d79  cmp     eax, [rdi+8]
0x180011d7c  jnz     loc_180011F32
0x180011d82  test    rdi, rdi
0x180011d85  jz      loc_180011F32
0x180011d8b  lea     rdx, [rbp+SRWLock]
0x180011d8f  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011d94  mov     rax, [rbx+110h]
0x180011d9b  mov     dword ptr [rax], 2
0x180011da1  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011da5  test    rcx, rcx
0x180011da8  jz      short loc_180011DB6
0x180011daa  call    cs:__imp_ReleaseSRWLockExclusive
0x180011db1  nop     dword ptr [rax+rax+00h]
0x180011db6  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011dbb  mov     r9, rax
0x180011dbe  mov     ecx, [rax]
0x180011dc0  cmp     ecx, 5
0x180011dc3  jbe     loc_180011FC0
0x180011dc9  mov     rcx, [rdi+30h]
0x180011dcd  mov     [rbp+var_70], rcx
0x180011dd1  mov     ecx, [rdi+44h]
0x180011dd4  mov     dword ptr [rbp+SRWLock], ecx
0x180011dd7  mov     ecx, [rdi+10h]
0x180011dda  mov     [rbp+arg_8], ecx
0x180011ddd  mov     rcx, [rdi+78h]
0x180011de1  mov     [rbp+var_68], rcx
0x180011de5  mov     rax, [rdi+70h]
0x180011de9  mov     [rbp+var_60], rax
0x180011ded  mov     eax, [rdi+68h]
0x180011df0  mov     dword ptr [rbp+arg_10], eax
0x180011df3  mov     rax, [rdi+60h]
0x180011df7  mov     [rbp+var_58], rax
0x180011dfb  mov     rax, [rdi+58h]
0x180011dff  mov     [rbp+var_50], rax
0x180011e03  mov     eax, [rdi+50h]
0x180011e06  mov     [rbp+arg_18], eax
0x180011e09  mov     rax, [rdi+48h]
0x180011e0d  mov     [rbp+var_48], rax
0x180011e11  mov     eax, [rdi+20h]
0x180011e14  mov     [rbp+var_80], eax
0x180011e17  mov     rax, [rdi+18h]
0x180011e1b  mov     [rbp+var_40], rax
0x180011e1f  mov     eax, [rdi]
0x180011e21  mov     [rbp+var_7C], eax
0x180011e24  mov     rax, [rdi+80h]
0x180011e2b  mov     [rbp+var_38], rax
0x180011e2f  mov     eax, [rdi+40h]
0x180011e32  mov     [rbp+var_78], eax
0x180011e35  mov     rax, [rdi+38h]
0x180011e39  mov     [rbp+var_30], rax
0x180011e3d  mov     eax, [rdi+8]
0x180011e40  mov     [rbp+var_74], eax
0x180011e43  mov     [rbp+var_28], 1000000h
0x180011e4b  mov     [rbp+var_20], 0
0x180011e53  mov     r8, [rbx+110h]
0x180011e5a  add     r8, 8
0x180011e5e  lea     rax, [rbp+var_70]
0x180011e62  mov     [rsp+140h+var_90], rax
0x180011e6a  lea     rax, [rbp+SRWLock]
0x180011e6e  mov     [rsp+140h+var_98], rax
0x180011e76  lea     rax, [rbp+arg_8]
0x180011e7a  mov     [rsp+140h+var_A0], rax
0x180011e82  lea     rax, [rbp+var_68]
0x180011e86  mov     [rsp+140h+var_A8], rax
0x180011e8e  lea     rax, [rbp+var_60]
0x180011e92  mov     [rsp+140h+var_B0], rax
0x180011e9a  lea     rax, [rbp+arg_10]
0x180011e9e  mov     [rsp+140h+var_B8], rax
0x180011ea6  lea     rax, [rbp+var_58]
0x180011eaa  mov     [rsp+140h+var_C0], rax
0x180011eb2  lea     rax, [rbp+var_50]
0x180011eb6  mov     [rsp+140h+var_C8], rax
0x180011ebb  lea     rax, [rbp+arg_18]
0x180011ebf  mov     [rsp+140h+var_D0], rax
0x180011ec4  lea     rax, [rbp+var_48]
0x180011ec8  mov     [rsp+140h+var_D8], rax
0x180011ecd  lea     rax, [rbp+var_80]
0x180011ed1  mov     [rsp+140h+var_E0], rax
0x180011ed6  lea     rax, [rbp+var_40]
0x180011eda  mov     [rsp+140h+var_E8], rax
0x180011edf  lea     rax, [rbp+var_7C]
0x180011ee3  mov     [rsp+140h+var_F0], rax
0x180011ee8  lea     rax, [rbp+var_38]
0x180011eec  mov     [rsp+140h+var_F8], rax
0x180011ef1  lea     rax, [rbp+var_78]
0x180011ef5  mov     [rsp+140h+var_100], rax
0x180011efa  lea     rax, [rbp+var_30]
0x180011efe  mov     [rsp+140h+var_108], rax
0x180011f03  lea     rax, [rbp+var_74]
0x180011f07  mov     [rsp+140h+var_110], rax
0x180011f0c  lea     rax, [rbp+var_28]
0x180011f10  mov     [rsp+140h+var_118], rax
0x180011f15  lea     rax, [rbp+var_20]
0x180011f19  mov     [rsp+140h+var_120], rax
0x180011f1e  lea     rdx, dword_18003BE6C
0x180011f25  mov     rcx, r9
0x180011f28  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180011f2d  jmp     loc_180011FC0
0x180011f32  lea     rdx, [rbp+SRWLock]
0x180011f36  call    ?LockExclusive@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011f3b  mov     rax, [rbx+110h]
0x180011f42  mov     dword ptr [rax], 2
0x180011f48  mov     rcx, [rbp+SRWLock]; SRWLock
0x180011f4c  test    rcx, rcx
0x180011f4f  jz      short loc_180011F5D
0x180011f51  call    cs:__imp_ReleaseSRWLockExclusive
0x180011f58  nop     dword ptr [rax+rax+00h]
0x180011f5d  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180011f62  mov     rdi, rax
0x180011f65  mov     ecx, [rax]
0x180011f67  cmp     ecx, 5
0x180011f6a  jbe     short loc_180011FC0
0x180011f6c  call    cs:__imp_GetCurrentThreadId
0x180011f73  nop     dword ptr [rax+rax+00h]
0x180011f78  mov     dword ptr [rbp+SRWLock], eax
0x180011f7b  mov     r8, [rbx+110h]
0x180011f82  mov     ecx, [r8+48h]
0x180011f86  mov     [rbp+arg_8], ecx
0x180011f89  mov     [rbp+arg_10], 0
0x180011f91  add     r8, 8
0x180011f95  lea     rax, [rbp+SRWLock]
0x180011f99  mov     [rsp+140h+var_110], rax
0x180011f9e  lea     rax, [rbp+arg_8]
0x180011fa2  mov     [rsp+140h+var_118], rax
0x180011fa7  lea     rax, [rbp+arg_10]
0x180011fab  mov     [rsp+140h+var_120], rax
0x180011fb0  lea     rdx, word_18003C72E
0x180011fb7  mov     rcx, rdi
0x180011fba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011fbf  nop
0x180011fc0  lea     rcx, [rbx+120h]; this
0x180011fc7  cmp     dword ptr [rcx+18h], 0
0x180011fcb  jz      short loc_180011FD3
0x180011fcd  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180011fd2  nop
0x180011fd3  add     rsp, 130h
0x180011fda  pop     rdi
0x180011fdb  pop     rbx
0x180011fdc  pop     rbp
0x180011fdd  retn
```
