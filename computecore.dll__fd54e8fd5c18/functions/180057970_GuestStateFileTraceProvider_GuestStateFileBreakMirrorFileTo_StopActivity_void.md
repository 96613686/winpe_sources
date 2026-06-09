# GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::StopActivity(void)

- ea: `0x180057970`
- end: `0x180057c50`
- name: `?StopActivity@GuestStateFileBreakMirrorFileTo@GuestStateFileTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180055e2c`
- `0x180057970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800579d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057ba5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800579d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057bd7`

## pseudocode

```c
void __fastcall GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo::StopActivity(
        GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  const struct _tlgProvider_t *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v13; // [rsp+C8h] [rbp-78h] BYREF
  int v14; // [rsp+CCh] [rbp-74h] BYREF
  int v15; // [rsp+D0h] [rbp-70h] BYREF
  int v16; // [rsp+D4h] [rbp-6Ch] BYREF
  int v17; // [rsp+D8h] [rbp-68h] BYREF
  int v18; // [rsp+DCh] [rbp-64h] BYREF
  int v19; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v20; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+100h] [rbp-40h] BYREF
  __int64 v24; // [rsp+108h] [rbp-38h] BYREF
  __int64 v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27; // [rsp+120h] [rbp-20h] BYREF
  __int64 v28; // [rsp+128h] [rbp-18h] BYREF
  __int64 v29; // [rsp+130h] [rbp-10h] BYREF
  __int64 v30; // [rsp+138h] [rbp-8h] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = GuestStateFileTraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x1000LL) != 0 && (v7 & 0x1000) == v7 )
      {
        v21 = *((_QWORD *)v4 + 6);
        v14 = v4[17];
        v15 = v4[4];
        v22 = *((_QWORD *)v4 + 15);
        v23 = *((_QWORD *)v4 + 14);
        v16 = v4[26];
        v24 = *((_QWORD *)v4 + 12);
        v25 = *((_QWORD *)v4 + 11);
        v17 = v4[20];
        v26 = *((_QWORD *)v4 + 9);
        v18 = v4[8];
        v27 = *((_QWORD *)v4 + 3);
        v19 = *v4;
        v28 = *((_QWORD *)v4 + 16);
        v13 = v4[16];
        v29 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v30 = 0x1000000;
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v6,
          (int)&dword_1800C9C4C,
          *((_QWORD *)this + 34) + 8,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&SRWLock,
          (__int64)&v29,
          (__int64)&v13,
          (__int64)&v28,
          (__int64)&v19,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v16,
          (__int64)&v23,
          (__int64)&v22,
          (__int64)&v15,
          (__int64)&v14,
          (__int64)&v21);
      }
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = GuestStateFileTraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x1000LL) != 0 && (v10 & 0x1000) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)&word_1800C9DA6,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((GuestStateFileTraceProvider::GuestStateFileBreakMirrorFileTo *)((char *)this + 288));
}

```

## disassembly

```asm
0x180057970  mov     [rsp-8+arg_8], rbx
0x180057975  mov     [rsp-8+arg_10], rdi
0x18005797a  push    rbp
0x18005797b  mov     rbp, rsp
0x18005797e  sub     rsp, 140h
0x180057985  mov     rbx, rcx
0x180057988  mov     rdi, [rcx+110h]
0x18005798f  mov     eax, [rdi+48h]
0x180057992  test    eax, eax
0x180057994  jns     loc_180057B7E
0x18005799a  add     rdi, 50h ; 'P'
0x18005799e  cmp     eax, [rdi+8]
0x1800579a1  jnz     loc_180057B7E
0x1800579a7  test    rdi, rdi
0x1800579aa  jz      loc_180057B7E
0x1800579b0  mov     [rbp+SRWLock], 0
0x1800579b8  lea     rdx, [rbp+SRWLock]
0x1800579bc  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800579c1  mov     rax, [rbx+110h]
0x1800579c8  mov     dword ptr [rax], 2
0x1800579ce  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800579d2  test    rcx, rcx
0x1800579d5  jz      short loc_1800579DD
0x1800579d7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800579dd  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x1800579e2  mov     r9, rax
0x1800579e5  mov     ecx, [rax]
0x1800579e7  cmp     ecx, 4
0x1800579ea  jbe     loc_180057C28
0x1800579f0  mov     rax, [rax+18h]
0x1800579f4  mov     rcx, [r9+10h]
0x1800579f8  mov     edx, 1000h
0x1800579fd  test    rdx, rcx
0x180057a00  jz      loc_180057C28
0x180057a06  mov     rcx, rax
0x180057a09  and     rcx, rdx
0x180057a0c  cmp     rcx, rax
0x180057a0f  jnz     loc_180057C28
0x180057a15  mov     rax, [rdi+30h]
0x180057a19  mov     [rbp+var_50], rax
0x180057a1d  mov     eax, [rdi+44h]
0x180057a20  mov     dword ptr [rbp+var_78+4], eax
0x180057a23  mov     eax, [rdi+10h]
0x180057a26  mov     dword ptr [rbp+var_70], eax
0x180057a29  mov     rax, [rdi+78h]
0x180057a2d  mov     [rbp+var_48], rax
0x180057a31  mov     rax, [rdi+70h]
0x180057a35  mov     [rbp+var_40], rax
0x180057a39  mov     eax, [rdi+68h]
0x180057a3c  mov     dword ptr [rbp+var_70+4], eax
0x180057a3f  mov     rax, [rdi+60h]
0x180057a43  mov     [rbp+var_38], rax
0x180057a47  mov     rax, [rdi+58h]
0x180057a4b  mov     [rbp+var_30], rax
0x180057a4f  mov     eax, [rdi+50h]
0x180057a52  mov     dword ptr [rbp+var_68], eax
0x180057a55  mov     rax, [rdi+48h]
0x180057a59  mov     [rbp+var_28], rax
0x180057a5d  mov     eax, [rdi+20h]
0x180057a60  mov     dword ptr [rbp+var_68+4], eax
0x180057a63  mov     rax, [rdi+18h]
0x180057a67  mov     [rbp+var_20], rax
0x180057a6b  mov     eax, [rdi]
0x180057a6d  mov     [rbp+var_60], eax
0x180057a70  mov     rax, [rdi+80h]
0x180057a77  mov     [rbp+var_18], rax
0x180057a7b  mov     eax, [rdi+40h]
0x180057a7e  mov     dword ptr [rbp+var_78], eax
0x180057a81  mov     rax, [rdi+38h]
0x180057a85  mov     [rbp+var_10], rax
0x180057a89  mov     eax, [rdi+8]
0x180057a8c  mov     dword ptr [rbp+SRWLock], eax
0x180057a8f  mov     [rbp+var_8], 1000000h
0x180057a97  mov     [rbp+var_58], 0
0x180057a9f  mov     r8, [rbx+110h]
0x180057aa6  add     r8, 8; int
0x180057aaa  lea     rax, [rbp+var_50]
0x180057aae  mov     [rsp+140h+var_90], rax; __int64
0x180057ab6  lea     rax, [rbp+var_78+4]
0x180057aba  mov     [rsp+140h+var_98], rax; __int64
0x180057ac2  lea     rax, [rbp+var_70]
0x180057ac6  mov     [rsp+140h+var_A0], rax; __int64
0x180057ace  lea     rax, [rbp+var_48]
0x180057ad2  mov     [rsp+140h+var_A8], rax; __int64
0x180057ada  lea     rax, [rbp+var_40]
0x180057ade  mov     [rsp+140h+var_B0], rax; __int64
0x180057ae6  lea     rax, [rbp+var_70+4]
0x180057aea  mov     [rsp+140h+var_B8], rax; __int64
0x180057af2  lea     rax, [rbp+var_38]
0x180057af6  mov     [rsp+140h+var_C0], rax; __int64
0x180057afe  lea     rax, [rbp+var_30]
0x180057b02  mov     [rsp+140h+var_C8], rax; __int64
0x180057b07  lea     rax, [rbp+var_68]
0x180057b0b  mov     [rsp+140h+var_D0], rax; __int64
0x180057b10  lea     rax, [rbp+var_28]
0x180057b14  mov     [rsp+140h+var_D8], rax; __int64
0x180057b19  lea     rax, [rbp+var_68+4]
0x180057b1d  mov     [rsp+140h+var_E0], rax; __int64
0x180057b22  lea     rax, [rbp+var_20]
0x180057b26  mov     [rsp+140h+var_E8], rax; __int64
0x180057b2b  lea     rax, [rbp+var_60]
0x180057b2f  mov     [rsp+140h+var_F0], rax; __int64
0x180057b34  lea     rax, [rbp+var_18]
0x180057b38  mov     [rsp+140h+var_F8], rax; __int64
0x180057b3d  lea     rax, [rbp+var_78]
0x180057b41  mov     [rsp+140h+var_100], rax; __int64
0x180057b46  lea     rax, [rbp+var_10]
0x180057b4a  mov     [rsp+140h+var_108], rax; __int64
0x180057b4f  lea     rax, [rbp+SRWLock]
0x180057b53  mov     [rsp+140h+var_110], rax; __int64
0x180057b58  lea     rax, [rbp+var_8]
0x180057b5c  mov     [rsp+140h+var_118], rax; __int64
0x180057b61  lea     rax, [rbp+var_58]
0x180057b65  mov     [rsp+140h+var_120], rax; __int64
0x180057b6a  lea     rdx, dword_1800C9C4C; int
0x180057b71  mov     rcx, r9; int
0x180057b74  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180057b79  jmp     loc_180057C28
0x180057b7e  mov     [rbp+SRWLock], 0
0x180057b86  lea     rdx, [rbp+SRWLock]
0x180057b8a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180057b8f  mov     rax, [rbx+110h]
0x180057b96  mov     dword ptr [rax], 2
0x180057b9c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180057ba0  test    rcx, rcx
0x180057ba3  jz      short loc_180057BAB
0x180057ba5  call    cs:__imp_ReleaseSRWLockExclusive
0x180057bab  call    ?Provider@GuestStateFileTraceProvider@@SAPEBU_tlgProvider_t@@XZ; GuestStateFileTraceProvider::Provider(void)
0x180057bb0  mov     rdi, rax
0x180057bb3  mov     ecx, [rax]
0x180057bb5  cmp     ecx, 4
0x180057bb8  jbe     short loc_180057C28
0x180057bba  mov     rax, [rax+18h]
0x180057bbe  mov     rcx, [rdi+10h]
0x180057bc2  mov     edx, 1000h
0x180057bc7  test    rdx, rcx
0x180057bca  jz      short loc_180057C28
0x180057bcc  mov     rcx, rax
0x180057bcf  and     rcx, rdx
0x180057bd2  cmp     rcx, rax
0x180057bd5  jnz     short loc_180057C28
0x180057bd7  call    cs:__imp_GetCurrentThreadId
0x180057bdd  mov     dword ptr [rbp+SRWLock], eax
0x180057be0  mov     r8, [rbx+110h]
0x180057be7  mov     eax, [r8+48h]
0x180057beb  mov     dword ptr [rbp+var_78], eax
0x180057bee  mov     [rbp+var_58], 0
0x180057bf6  add     r8, 8
0x180057bfa  lea     rax, [rbp+SRWLock]
0x180057bfe  mov     [rsp+140h+var_110], rax
0x180057c03  lea     rax, [rbp+var_78]
0x180057c07  mov     [rsp+140h+var_118], rax
0x180057c0c  lea     rax, [rbp+var_58]
0x180057c10  mov     [rsp+140h+var_120], rax
0x180057c15  xor     r9d, r9d
0x180057c18  lea     rdx, word_1800C9DA6
0x180057c1f  mov     rcx, rdi
0x180057c22  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180057c27  nop
0x180057c28  lea     rcx, [rbx+120h]; this
0x180057c2f  cmp     dword ptr [rcx+18h], 0
0x180057c33  jz      short loc_180057C3B
0x180057c35  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180057c3a  nop
0x180057c3b  lea     r11, [rsp+140h+var_s0]
0x180057c43  mov     rbx, [r11+18h]
0x180057c47  mov     rdi, [r11+20h]
0x180057c4b  mov     rsp, r11
0x180057c4e  pop     rbp
0x180057c4f  retn
```
