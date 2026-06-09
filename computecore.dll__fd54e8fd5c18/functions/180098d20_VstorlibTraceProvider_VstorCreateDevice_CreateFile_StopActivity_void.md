# VstorlibTraceProvider::VstorCreateDevice_CreateFile::StopActivity(void)

- ea: `0x180098d20`
- end: `0x180099000`
- name: `?StopActivity@VstorCreateDevice_CreateFile@VstorlibTraceProvider@@MEAAXXZ`
- size: `736`
- prototype: `void __fastcall(VstorlibTraceProvider::VstorCreateDevice_CreateFile *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x1800017a8`
- `0x180001abc`
- `0x180014a2c`
- `0x18001558c`
- `0x180097be4`
- `0x180098d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098d87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098f55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098d87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180098f55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180098f87`

## pseudocode

```c
void __fastcall VstorlibTraceProvider::VstorCreateDevice_CreateFile::StopActivity(
        VstorlibTraceProvider::VstorCreateDevice_CreateFile *this)
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
    v5 = VstorlibTraceProvider::Provider();
    v6 = v5;
    if ( *(_DWORD *)v5 > 4u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*((_QWORD *)v6 + 2) & 0x200LL) != 0 && (v7 & 0x200) == v7 )
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
          (int)&word_1800CE7D2,
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
    v8 = VstorlibTraceProvider::Provider();
    v9 = v8;
    if ( *(_DWORD *)v8 > 4u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*((_QWORD *)v9 + 2) & 0x200LL) != 0 && (v10 & 0x200) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v13 = *(_DWORD *)(v11 + 72);
        v20 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v9,
          (unsigned int)byte_1800CEB29,
          v11 + 8,
          0,
          (__int64)&v20,
          (__int64)&v13,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((VstorlibTraceProvider::VstorCreateDevice_CreateFile *)((char *)this + 288));
}

```

## disassembly

```asm
0x180098d20  mov     [rsp-8+arg_8], rbx
0x180098d25  mov     [rsp-8+arg_10], rdi
0x180098d2a  push    rbp
0x180098d2b  mov     rbp, rsp
0x180098d2e  sub     rsp, 140h
0x180098d35  mov     rbx, rcx
0x180098d38  mov     rdi, [rcx+110h]
0x180098d3f  mov     eax, [rdi+48h]
0x180098d42  test    eax, eax
0x180098d44  jns     loc_180098F2E
0x180098d4a  add     rdi, 50h ; 'P'
0x180098d4e  cmp     eax, [rdi+8]
0x180098d51  jnz     loc_180098F2E
0x180098d57  test    rdi, rdi
0x180098d5a  jz      loc_180098F2E
0x180098d60  mov     [rbp+SRWLock], 0
0x180098d68  lea     rdx, [rbp+SRWLock]
0x180098d6c  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180098d71  mov     rax, [rbx+110h]
0x180098d78  mov     dword ptr [rax], 2
0x180098d7e  mov     rcx, [rbp+SRWLock]; SRWLock
0x180098d82  test    rcx, rcx
0x180098d85  jz      short loc_180098D8D
0x180098d87  call    cs:__imp_ReleaseSRWLockExclusive
0x180098d8d  call    ?Provider@VstorlibTraceProvider@@SAPEBU_tlgProvider_t@@XZ; VstorlibTraceProvider::Provider(void)
0x180098d92  mov     r9, rax
0x180098d95  mov     ecx, [rax]
0x180098d97  cmp     ecx, 4
0x180098d9a  jbe     loc_180098FD8
0x180098da0  mov     rax, [rax+18h]
0x180098da4  mov     rcx, [r9+10h]
0x180098da8  mov     edx, 200h
0x180098dad  test    rdx, rcx
0x180098db0  jz      loc_180098FD8
0x180098db6  mov     rcx, rax
0x180098db9  and     rcx, rdx
0x180098dbc  cmp     rcx, rax
0x180098dbf  jnz     loc_180098FD8
0x180098dc5  mov     rax, [rdi+30h]
0x180098dc9  mov     [rbp+var_50], rax
0x180098dcd  mov     eax, [rdi+44h]
0x180098dd0  mov     dword ptr [rbp+var_78+4], eax
0x180098dd3  mov     eax, [rdi+10h]
0x180098dd6  mov     dword ptr [rbp+var_70], eax
0x180098dd9  mov     rax, [rdi+78h]
0x180098ddd  mov     [rbp+var_48], rax
0x180098de1  mov     rax, [rdi+70h]
0x180098de5  mov     [rbp+var_40], rax
0x180098de9  mov     eax, [rdi+68h]
0x180098dec  mov     dword ptr [rbp+var_70+4], eax
0x180098def  mov     rax, [rdi+60h]
0x180098df3  mov     [rbp+var_38], rax
0x180098df7  mov     rax, [rdi+58h]
0x180098dfb  mov     [rbp+var_30], rax
0x180098dff  mov     eax, [rdi+50h]
0x180098e02  mov     dword ptr [rbp+var_68], eax
0x180098e05  mov     rax, [rdi+48h]
0x180098e09  mov     [rbp+var_28], rax
0x180098e0d  mov     eax, [rdi+20h]
0x180098e10  mov     dword ptr [rbp+var_68+4], eax
0x180098e13  mov     rax, [rdi+18h]
0x180098e17  mov     [rbp+var_20], rax
0x180098e1b  mov     eax, [rdi]
0x180098e1d  mov     [rbp+var_60], eax
0x180098e20  mov     rax, [rdi+80h]
0x180098e27  mov     [rbp+var_18], rax
0x180098e2b  mov     eax, [rdi+40h]
0x180098e2e  mov     dword ptr [rbp+var_78], eax
0x180098e31  mov     rax, [rdi+38h]
0x180098e35  mov     [rbp+var_10], rax
0x180098e39  mov     eax, [rdi+8]
0x180098e3c  mov     dword ptr [rbp+SRWLock], eax
0x180098e3f  mov     [rbp+var_8], 1000000h
0x180098e47  mov     [rbp+var_58], 0
0x180098e4f  mov     r8, [rbx+110h]
0x180098e56  add     r8, 8; int
0x180098e5a  lea     rax, [rbp+var_50]
0x180098e5e  mov     [rsp+140h+var_90], rax; __int64
0x180098e66  lea     rax, [rbp+var_78+4]
0x180098e6a  mov     [rsp+140h+var_98], rax; __int64
0x180098e72  lea     rax, [rbp+var_70]
0x180098e76  mov     [rsp+140h+var_A0], rax; __int64
0x180098e7e  lea     rax, [rbp+var_48]
0x180098e82  mov     [rsp+140h+var_A8], rax; __int64
0x180098e8a  lea     rax, [rbp+var_40]
0x180098e8e  mov     [rsp+140h+var_B0], rax; __int64
0x180098e96  lea     rax, [rbp+var_70+4]
0x180098e9a  mov     [rsp+140h+var_B8], rax; __int64
0x180098ea2  lea     rax, [rbp+var_38]
0x180098ea6  mov     [rsp+140h+var_C0], rax; __int64
0x180098eae  lea     rax, [rbp+var_30]
0x180098eb2  mov     [rsp+140h+var_C8], rax; __int64
0x180098eb7  lea     rax, [rbp+var_68]
0x180098ebb  mov     [rsp+140h+var_D0], rax; __int64
0x180098ec0  lea     rax, [rbp+var_28]
0x180098ec4  mov     [rsp+140h+var_D8], rax; __int64
0x180098ec9  lea     rax, [rbp+var_68+4]
0x180098ecd  mov     [rsp+140h+var_E0], rax; __int64
0x180098ed2  lea     rax, [rbp+var_20]
0x180098ed6  mov     [rsp+140h+var_E8], rax; __int64
0x180098edb  lea     rax, [rbp+var_60]
0x180098edf  mov     [rsp+140h+var_F0], rax; __int64
0x180098ee4  lea     rax, [rbp+var_18]
0x180098ee8  mov     [rsp+140h+var_F8], rax; __int64
0x180098eed  lea     rax, [rbp+var_78]
0x180098ef1  mov     [rsp+140h+var_100], rax; __int64
0x180098ef6  lea     rax, [rbp+var_10]
0x180098efa  mov     [rsp+140h+var_108], rax; __int64
0x180098eff  lea     rax, [rbp+SRWLock]
0x180098f03  mov     [rsp+140h+var_110], rax; __int64
0x180098f08  lea     rax, [rbp+var_8]
0x180098f0c  mov     [rsp+140h+var_118], rax; __int64
0x180098f11  lea     rax, [rbp+var_58]
0x180098f15  mov     [rsp+140h+var_120], rax; __int64
0x180098f1a  lea     rdx, word_1800CE7D2; int
0x180098f21  mov     rcx, r9; int
0x180098f24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180098f29  jmp     loc_180098FD8
0x180098f2e  mov     [rbp+SRWLock], 0
0x180098f36  lea     rdx, [rbp+SRWLock]
0x180098f3a  call    ?LockExclusive@?$ActivityBase@VHyperVStorageTrace@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<HyperVStorageTrace,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180098f3f  mov     rax, [rbx+110h]
0x180098f46  mov     dword ptr [rax], 2
0x180098f4c  mov     rcx, [rbp+SRWLock]; SRWLock
0x180098f50  test    rcx, rcx
0x180098f53  jz      short loc_180098F5B
0x180098f55  call    cs:__imp_ReleaseSRWLockExclusive
0x180098f5b  call    ?Provider@VstorlibTraceProvider@@SAPEBU_tlgProvider_t@@XZ; VstorlibTraceProvider::Provider(void)
0x180098f60  mov     rdi, rax
0x180098f63  mov     ecx, [rax]
0x180098f65  cmp     ecx, 4
0x180098f68  jbe     short loc_180098FD8
0x180098f6a  mov     rax, [rax+18h]
0x180098f6e  mov     rcx, [rdi+10h]
0x180098f72  mov     edx, 200h
0x180098f77  test    rdx, rcx
0x180098f7a  jz      short loc_180098FD8
0x180098f7c  mov     rcx, rax
0x180098f7f  and     rcx, rdx
0x180098f82  cmp     rcx, rax
0x180098f85  jnz     short loc_180098FD8
0x180098f87  call    cs:__imp_GetCurrentThreadId
0x180098f8d  mov     dword ptr [rbp+SRWLock], eax
0x180098f90  mov     r8, [rbx+110h]
0x180098f97  mov     eax, [r8+48h]
0x180098f9b  mov     dword ptr [rbp+var_78], eax
0x180098f9e  mov     [rbp+var_58], 0
0x180098fa6  add     r8, 8
0x180098faa  lea     rax, [rbp+SRWLock]
0x180098fae  mov     [rsp+140h+var_110], rax
0x180098fb3  lea     rax, [rbp+var_78]
0x180098fb7  mov     [rsp+140h+var_118], rax
0x180098fbc  lea     rax, [rbp+var_58]
0x180098fc0  mov     [rsp+140h+var_120], rax
0x180098fc5  xor     r9d, r9d
0x180098fc8  lea     rdx, byte_1800CEB29
0x180098fcf  mov     rcx, rdi
0x180098fd2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180098fd7  nop
0x180098fd8  lea     rcx, [rbx+120h]; this
0x180098fdf  cmp     dword ptr [rcx+18h], 0
0x180098fe3  jz      short loc_180098FEB
0x180098fe5  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180098fea  nop
0x180098feb  lea     r11, [rsp+140h+var_s0]
0x180098ff3  mov     rbx, [r11+18h]
0x180098ff7  mov     rdi, [r11+20h]
0x180098ffb  mov     rsp, r11
0x180098ffe  pop     rbp
0x180098fff  retn
```
