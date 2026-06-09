# DesktopAppXProvider::TryActivateDesktopAppXApplication::Stop(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,bool,ulong,ulong,ulong,int,ulong,long,long,long,ulong)

- ea: `0x180092a88`
- end: `0x18009306a`
- name: `?Stop@TryActivateDesktopAppXApplication@DesktopAppXProvider@@QEAAXPEBG0000KKK_NKKKHKJJJK@Z`
- size: `1506`
- prototype: `void __fastcall(DesktopAppXProvider::TryActivateDesktopAppXApplication *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, bool, unsigned int, unsigned int, unsigned int, int, unsigned int, int, int, char, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800933e0`

## callees

- `0x180003674`
- `0x180003b94`
- `0x18001031c`
- `0x18001bd34`
- `0x18001be00`
- `0x180092a88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092afb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092dfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092afb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180092dfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092ed1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180092ff7`

## string_xrefs

- `0x18009300c`: `onecore\internal\sdk\inc\wil\opensource/wil/result.h`

## pseudocode

```c
void __fastcall DesktopAppXProvider::TryActivateDesktopAppXApplication::Stop(
        DesktopAppXProvider::TryActivateDesktopAppXApplication *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        bool a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        int a14,
        unsigned int a15,
        int a16,
        int a17,
        bool a18,
        unsigned int a19)
{
  _DWORD **v19; // rdi
  __int64 v21; // rax
  int v25; // ecx
  __int64 v26; // rsi
  RTL_SRWLOCK *v27; // rcx
  __int64 v28; // r9
  _DWORD *v29; // r8
  RTL_SRWLOCK *v30; // rcx
  __int64 v31; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v33; // r8
  int v34; // r9d
  char *v35; // rbx
  __int64 *v36; // rcx
  __int64 v37; // rax
  int v38; // [rsp+20h] [rbp-190h]
  int v39; // [rsp+130h] [rbp-80h] BYREF
  unsigned int v40; // [rsp+134h] [rbp-7Ch] BYREF
  unsigned int v41; // [rsp+138h] [rbp-78h] BYREF
  unsigned int v42; // [rsp+13Ch] [rbp-74h] BYREF
  unsigned int v43; // [rsp+140h] [rbp-70h] BYREF
  unsigned int v44; // [rsp+144h] [rbp-6Ch] BYREF
  unsigned int v45; // [rsp+148h] [rbp-68h] BYREF
  int v46; // [rsp+14Ch] [rbp-64h] BYREF
  unsigned int v47; // [rsp+150h] [rbp-60h] BYREF
  int v48; // [rsp+154h] [rbp-5Ch] BYREF
  unsigned int v49; // [rsp+158h] [rbp-58h] BYREF
  int v50; // [rsp+15Ch] [rbp-54h] BYREF
  int v51; // [rsp+160h] [rbp-50h] BYREF
  unsigned int v52; // [rsp+164h] [rbp-4Ch] BYREF
  int v53; // [rsp+168h] [rbp-48h] BYREF
  unsigned int v54; // [rsp+16Ch] [rbp-44h] BYREF
  int v55[2]; // [rsp+170h] [rbp-40h] BYREF
  const unsigned __int16 *v56; // [rsp+178h] [rbp-38h] BYREF
  const unsigned __int16 *v57; // [rsp+180h] [rbp-30h] BYREF
  const unsigned __int16 *v58; // [rsp+188h] [rbp-28h] BYREF
  __int64 v59; // [rsp+190h] [rbp-20h] BYREF
  __int64 v60; // [rsp+198h] [rbp-18h] BYREF
  const unsigned __int16 *v61; // [rsp+1A0h] [rbp-10h] BYREF
  const unsigned __int16 *v62; // [rsp+1A8h] [rbp-8h] BYREF
  const unsigned __int16 *v63; // [rsp+1B0h] [rbp+0h] BYREF
  const unsigned __int16 *v64; // [rsp+1B8h] [rbp+8h] BYREF
  const unsigned __int16 *v65; // [rsp+1C0h] [rbp+10h] BYREF
  __int64 v66; // [rsp+1C8h] [rbp+18h] BYREF
  __int64 v67; // [rsp+1D0h] [rbp+20h] BYREF
  __int64 v68; // [rsp+1D8h] [rbp+28h] BYREF
  __int64 v69; // [rsp+1E0h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+68h]
  PSRWLOCK SRWLock; // [rsp+220h] [rbp+70h] BYREF

  v19 = (_DWORD **)((char *)this + 272);
  v21 = *((_QWORD *)this + 34);
  v25 = *(_DWORD *)(v21 + 72);
  if ( v25 >= 0 || v25 != *(_DWORD *)(v21 + 88) || (v26 = v21 + 80, v21 == -80) )
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v30 = SRWLock;
    **v19 = 2;
    if ( v30 )
      ReleaseSRWLockExclusive(v30);
    v31 = *((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( *(_DWORD *)v31 > 5u
      && (*(_QWORD *)(v31 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v31 + 24) & 0x400000000000LL) == *(_QWORD *)(v31 + 24) )
    {
      a19 = 0;
      v46 = 0;
      LODWORD(SRWLock) = a17;
      v50 = a16;
      v49 = a15;
      v48 = a14;
      v47 = a13;
      v45 = a12;
      v44 = a11;
      a18 = a10;
      v43 = a9;
      v42 = a8;
      v41 = a7;
      v60 = (__int64)a6;
      v59 = (__int64)a5;
      v58 = a4;
      v57 = a3;
      v56 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v33 = *((_QWORD *)this + 34);
      v40 = CurrentThreadId;
      v39 = *(_DWORD *)(v33 + 72);
      *(_QWORD *)v55 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v31,
        (unsigned int)&unk_1800EA326,
        v33 + 8,
        v34,
        (__int64)v55,
        (__int64)&v39,
        (__int64)&v40,
        (__int64)&v56,
        (__int64)&v57,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)&v60,
        (__int64)&v41,
        (__int64)&v42,
        (__int64)&v43,
        (__int64)&a18,
        (__int64)&v44,
        (__int64)&v45,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&v49,
        (__int64)&v50,
        (__int64)&SRWLock,
        (__int64)&a19);
    }
  }
  else
  {
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(this, &SRWLock);
    v27 = SRWLock;
    **v19 = 2;
    if ( v27 )
      ReleaseSRWLockExclusive(v27);
    v28 = *((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( *(_DWORD *)v28 > 5u
      && (*(_QWORD *)(v28 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v28 + 24) & 0x400000000000LL) == *(_QWORD *)(v28 + 24) )
    {
      LODWORD(SRWLock) = a17;
      v51 = a16;
      v52 = a15;
      v53 = a14;
      v54 = a13;
      a19 = 0;
      v39 = 0;
      v29 = *v19;
      v40 = a12;
      v41 = a11;
      a18 = a10;
      v42 = a9;
      v43 = a8;
      v44 = a7;
      v61 = a6;
      v62 = a5;
      v66 = *(_QWORD *)(v26 + 120);
      v67 = *(_QWORD *)(v26 + 112);
      v45 = *(_DWORD *)(v26 + 104);
      v68 = *(_QWORD *)(v26 + 96);
      v69 = *(_QWORD *)(v26 + 88);
      v46 = *(_DWORD *)(v26 + 80);
      *(_QWORD *)v55 = *(_QWORD *)(v26 + 72);
      v47 = *(_DWORD *)(v26 + 32);
      v56 = *(const unsigned __int16 **)(v26 + 24);
      v48 = *(_DWORD *)v26;
      v57 = *(const unsigned __int16 **)(v26 + 128);
      v49 = *(_DWORD *)(v26 + 64);
      v58 = *(const unsigned __int16 **)(v26 + 56);
      v50 = *(_DWORD *)(v26 + 8);
      v63 = a4;
      v64 = a3;
      v65 = a2;
      v59 = 0x1000000;
      v60 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&unk_1800EA539,
        (_DWORD)v29 + 8,
        v28,
        (__int64)&v60,
        (__int64)&v59,
        (__int64)&v50,
        (__int64)&v58,
        (__int64)&v49,
        (__int64)&v57,
        (__int64)&v48,
        (__int64)&v56,
        (__int64)&v47,
        (__int64)v55,
        (__int64)&v46,
        (__int64)&v69,
        (__int64)&v68,
        (__int64)&v45,
        (__int64)&v67,
        (__int64)&v66,
        (__int64)&v65,
        (__int64)&v64,
        (__int64)&v63,
        (__int64)&v62,
        (__int64)&v61,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&a18,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v54,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v51,
        (__int64)&SRWLock,
        (__int64)&a19);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v35 = (char *)this + 288;
    if ( *((_DWORD *)v35 + 6) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result.h",
        (const char *)0x8007029CLL,
        v38);
    *((_DWORD *)v35 + 6) = 0;
    v36 = *(__int64 **)v35;
    while ( 1 )
    {
      v37 = *v36;
      if ( !*v36 )
        break;
      if ( (char *)v37 == v35 )
      {
        *v36 = *((_QWORD *)v35 + 2);
        break;
      }
      v36 = (__int64 *)(v37 + 16);
      *(_QWORD *)v35 = v37 + 16;
    }
    *(_QWORD *)v35 = 0;
  }
}

```

## disassembly

```asm
0x180092a88  mov     [rsp-8+arg_8], rbx
0x180092a8d  mov     [rsp-8+arg_10], rsi
0x180092a92  push    rbp
0x180092a93  push    rdi
0x180092a94  push    r12
0x180092a96  push    r14
0x180092a98  push    r15
0x180092a9a  lea     rbp, [rsp-40h]
0x180092a9f  sub     rsp, 1F0h
0x180092aa6  lea     rdi, [rcx+110h]
0x180092aad  mov     rbx, rcx
0x180092ab0  mov     rax, [rdi]
0x180092ab3  mov     r14, r9
0x180092ab6  mov     r15, r8
0x180092ab9  mov     r12, rdx
0x180092abc  mov     ecx, [rax+48h]
0x180092abf  test    ecx, ecx
0x180092ac1  jns     loc_180092DDD
0x180092ac7  cmp     ecx, [rax+58h]
0x180092aca  jnz     loc_180092DDD
0x180092ad0  lea     rsi, [rax+50h]
0x180092ad4  test    rsi, rsi
0x180092ad7  jz      loc_180092DDD
0x180092add  lea     rdx, [rbp+60h+SRWLock]
0x180092ae1  mov     rcx, rbx
0x180092ae4  call    ?LockExclusive@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180092ae9  mov     rax, [rdi]
0x180092aec  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x180092af0  mov     dword ptr [rax], 2
0x180092af6  test    rcx, rcx
0x180092af9  jz      short loc_180092B07
0x180092afb  call    cs:__imp_ReleaseSRWLockExclusive
0x180092b02  nop     dword ptr [rax+rax+00h]
0x180092b07  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180092b0c  mov     r9, [rax+8]
0x180092b10  cmp     dword ptr [r9], 5
0x180092b14  jbe     loc_180092FE7
0x180092b1a  mov     rcx, 400000000000h
0x180092b24  test    [r9+10h], rcx
0x180092b28  jz      loc_180092FE7
0x180092b2e  mov     rax, [r9+18h]
0x180092b32  and     rax, rcx
0x180092b35  cmp     rax, [r9+18h]
0x180092b39  jnz     loc_180092FE7
0x180092b3f  mov     eax, [rbp+60h+arg_80]
0x180092b45  mov     dword ptr [rbp+60h+SRWLock], eax
0x180092b48  mov     eax, [rbp+60h+arg_78]
0x180092b4e  mov     [rbp+60h+var_B0], eax
0x180092b51  mov     eax, [rbp+60h+arg_70]
0x180092b57  mov     [rbp+60h+var_AC], eax
0x180092b5a  mov     eax, [rbp+60h+arg_68]
0x180092b60  mov     [rbp+60h+var_A8], eax
0x180092b63  mov     eax, [rbp+60h+arg_60]
0x180092b69  mov     [rbp+60h+var_A4], eax
0x180092b6c  mov     eax, [rbp+60h+arg_58]
0x180092b72  and     [rbp+60h+arg_90], 0
0x180092b79  and     [rbp+60h+var_E0], 0
0x180092b7d  mov     r8, [rdi]
0x180092b80  mov     [rbp+60h+var_DC], eax
0x180092b83  add     r8, 8
0x180092b87  mov     eax, [rbp+60h+arg_50]
0x180092b8d  mov     [rbp+60h+var_D8], eax
0x180092b90  mov     al, [rbp+60h+arg_48]
0x180092b96  mov     [rbp+60h+arg_88], al
0x180092b9c  mov     eax, [rbp+60h+arg_40]
0x180092ba2  mov     [rbp+60h+var_D4], eax
0x180092ba5  mov     eax, [rbp+60h+arg_38]
0x180092bab  mov     [rbp+60h+var_D0], eax
0x180092bae  mov     eax, [rbp+60h+arg_30]
0x180092bb4  mov     [rbp+60h+var_CC], eax
0x180092bb7  mov     rax, [rbp+60h+arg_28]
0x180092bbe  mov     [rbp+60h+var_70], rax
0x180092bc2  mov     rax, [rbp+60h+arg_20]
0x180092bc9  mov     [rbp+60h+var_68], rax
0x180092bcd  mov     rax, [rsi+78h]
0x180092bd1  mov     [rbp+60h+var_48], rax
0x180092bd5  mov     rax, [rsi+70h]
0x180092bd9  mov     [rbp+60h+var_40], rax
0x180092bdd  mov     eax, [rsi+68h]
0x180092be0  mov     [rbp+60h+var_C8], eax
0x180092be3  mov     rax, [rsi+60h]
0x180092be7  mov     [rbp+60h+var_38], rax
0x180092beb  mov     rax, [rsi+58h]
0x180092bef  mov     [rbp+60h+var_30], rax
0x180092bf3  mov     eax, [rsi+50h]
0x180092bf6  mov     [rbp+60h+var_C4], eax
0x180092bf9  mov     rax, [rsi+48h]
0x180092bfd  mov     qword ptr [rbp+60h+var_A0], rax
0x180092c01  mov     eax, [rsi+20h]
0x180092c04  mov     [rbp+60h+var_C0], eax
0x180092c07  mov     rax, [rsi+18h]
0x180092c0b  mov     [rbp+60h+var_98], rax
0x180092c0f  mov     eax, [rsi]
0x180092c11  mov     [rbp+60h+var_BC], eax
0x180092c14  mov     rax, [rsi+80h]
0x180092c1b  mov     [rbp+60h+var_90], rax
0x180092c1f  mov     eax, [rsi+40h]
0x180092c22  mov     [rbp+60h+var_B8], eax
0x180092c25  mov     rax, [rsi+38h]
0x180092c29  mov     [rbp+60h+var_88], rax
0x180092c2d  mov     eax, [rsi+8]
0x180092c30  mov     [rbp+60h+var_B4], eax
0x180092c33  lea     rax, [rbp+60h+arg_90]
0x180092c3a  mov     [rsp+210h+var_E8], rax
0x180092c42  lea     rax, [rbp+60h+SRWLock]
0x180092c46  mov     [rsp+210h+var_F0], rax
0x180092c4e  lea     rax, [rbp+60h+var_B0]
0x180092c52  mov     [rsp+210h+var_F8], rax
0x180092c5a  lea     rax, [rbp+60h+var_AC]
0x180092c5e  mov     [rsp+210h+var_100], rax
0x180092c66  lea     rax, [rbp+60h+var_A8]
0x180092c6a  mov     [rsp+210h+var_108], rax
0x180092c72  lea     rax, [rbp+60h+var_A4]
0x180092c76  mov     [rsp+210h+var_110], rax
0x180092c7e  lea     rax, [rbp+60h+var_E0]
0x180092c82  mov     [rsp+210h+var_118], rax
0x180092c8a  lea     rax, [rbp+60h+var_DC]
0x180092c8e  mov     [rsp+210h+var_120], rax
0x180092c96  lea     rax, [rbp+60h+var_D8]
0x180092c9a  mov     [rsp+210h+var_128], rax
0x180092ca2  mov     [rbp+60h+var_60], r14
0x180092ca6  mov     [rbp+60h+var_58], r15
0x180092caa  mov     [rbp+60h+var_50], r12
0x180092cae  mov     [rbp+60h+var_80], 1000000h
0x180092cb6  mov     [rbp+60h+var_78], 3000000h
0x180092cbe  lea     rax, [rbp+60h+arg_88]
0x180092cc5  mov     rcx, r9
0x180092cc8  mov     [rsp+210h+var_130], rax
0x180092cd0  lea     rdx, unk_1800EA539
0x180092cd7  lea     rax, [rbp+60h+var_D4]
0x180092cdb  mov     [rsp+210h+var_138], rax
0x180092ce3  lea     rax, [rbp+60h+var_D0]
0x180092ce7  mov     [rsp+210h+var_140], rax
0x180092cef  lea     rax, [rbp+60h+var_CC]
0x180092cf3  mov     [rsp+210h+var_148], rax
0x180092cfb  lea     rax, [rbp+60h+var_70]
0x180092cff  mov     [rsp+210h+var_150], rax
0x180092d07  lea     rax, [rbp+60h+var_68]
0x180092d0b  mov     [rsp+210h+var_158], rax
0x180092d13  lea     rax, [rbp+60h+var_60]
0x180092d17  mov     [rsp+210h+var_160], rax
0x180092d1f  lea     rax, [rbp+60h+var_58]
0x180092d23  mov     [rsp+210h+var_168], rax
0x180092d2b  lea     rax, [rbp+60h+var_50]
0x180092d2f  mov     [rsp+210h+var_170], rax
0x180092d37  lea     rax, [rbp+60h+var_48]
0x180092d3b  mov     [rsp+210h+var_178], rax
0x180092d43  lea     rax, [rbp+60h+var_40]
0x180092d47  mov     [rsp+210h+var_180], rax
0x180092d4f  lea     rax, [rbp+60h+var_C8]
0x180092d53  mov     [rsp+210h+var_188], rax
0x180092d5b  lea     rax, [rbp+60h+var_38]
0x180092d5f  mov     [rsp+210h+var_190], rax
0x180092d67  lea     rax, [rbp+60h+var_30]
0x180092d6b  mov     [rsp+210h+var_198], rax
0x180092d70  lea     rax, [rbp+60h+var_C4]
0x180092d74  mov     [rsp+210h+var_1A0], rax
0x180092d79  lea     rax, [rbp+60h+var_A0]
0x180092d7d  mov     [rsp+210h+var_1A8], rax
0x180092d82  lea     rax, [rbp+60h+var_C0]
0x180092d86  mov     [rsp+210h+var_1B0], rax
0x180092d8b  lea     rax, [rbp+60h+var_98]
0x180092d8f  mov     [rsp+210h+var_1B8], rax
0x180092d94  lea     rax, [rbp+60h+var_BC]
0x180092d98  mov     [rsp+210h+var_1C0], rax
0x180092d9d  lea     rax, [rbp+60h+var_90]
0x180092da1  mov     [rsp+210h+var_1C8], rax
0x180092da6  lea     rax, [rbp+60h+var_B8]
0x180092daa  mov     [rsp+210h+var_1D0], rax
0x180092daf  lea     rax, [rbp+60h+var_88]
0x180092db3  mov     [rsp+210h+var_1D8], rax
0x180092db8  lea     rax, [rbp+60h+var_B4]
0x180092dbc  mov     [rsp+210h+var_1E0], rax
0x180092dc1  lea     rax, [rbp+60h+var_80]
0x180092dc5  mov     [rsp+210h+var_1E8], rax
0x180092dca  lea     rax, [rbp+60h+var_78]
0x180092dce  mov     qword ptr [rsp+210h+var_1F0], rax
0x180092dd3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@U4@U4@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645666666444AEBU?$_tlgWrapperByVal@$00@@444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180092dd8  jmp     loc_180092FE7
0x180092ddd  lea     rdx, [rbp+60h+SRWLock]
0x180092de1  mov     rcx, rbx
0x180092de4  call    ?LockExclusive@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180092de9  mov     rax, [rdi]
0x180092dec  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x180092df0  mov     dword ptr [rax], 2
0x180092df6  test    rcx, rcx
0x180092df9  jz      short loc_180092E07
0x180092dfb  call    cs:__imp_ReleaseSRWLockExclusive
0x180092e02  nop     dword ptr [rax+rax+00h]
0x180092e07  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180092e0c  mov     rdi, [rax+8]
0x180092e10  cmp     dword ptr [rdi], 5
0x180092e13  jbe     loc_180092FE7
0x180092e19  mov     rcx, 400000000000h
0x180092e23  test    [rdi+10h], rcx
0x180092e27  jz      loc_180092FE7
0x180092e2d  mov     rax, [rdi+18h]
0x180092e31  and     rax, rcx
0x180092e34  cmp     rax, [rdi+18h]
0x180092e38  jnz     loc_180092FE7
0x180092e3e  mov     eax, [rbp+60h+arg_80]
0x180092e44  and     [rbp+60h+arg_90], 0
0x180092e4b  and     [rbp+60h+var_C4], 0
0x180092e4f  mov     dword ptr [rbp+60h+SRWLock], eax
0x180092e52  mov     eax, [rbp+60h+arg_78]
0x180092e58  mov     [rbp+60h+var_B4], eax
0x180092e5b  mov     eax, [rbp+60h+arg_70]
0x180092e61  mov     [rbp+60h+var_B8], eax
0x180092e64  mov     eax, [rbp+60h+arg_68]
0x180092e6a  mov     [rbp+60h+var_BC], eax
0x180092e6d  mov     eax, [rbp+60h+arg_60]
0x180092e73  mov     [rbp+60h+var_C0], eax
0x180092e76  mov     eax, [rbp+60h+arg_58]
0x180092e7c  mov     [rbp+60h+var_C8], eax
0x180092e7f  mov     eax, [rbp+60h+arg_50]
0x180092e85  mov     [rbp+60h+var_CC], eax
0x180092e88  mov     al, [rbp+60h+arg_48]
0x180092e8e  mov     [rbp+60h+arg_88], al
0x180092e94  mov     eax, [rbp+60h+arg_40]
0x180092e9a  mov     [rbp+60h+var_D0], eax
0x180092e9d  mov     eax, [rbp+60h+arg_38]
0x180092ea3  mov     [rbp+60h+var_D4], eax
0x180092ea6  mov     eax, [rbp+60h+arg_30]
0x180092eac  mov     [rbp+60h+var_D8], eax
0x180092eaf  mov     rax, [rbp+60h+arg_28]
0x180092eb6  mov     [rbp+60h+var_78], rax
0x180092eba  mov     rax, [rbp+60h+arg_20]
0x180092ec1  mov     [rbp+60h+var_80], rax
0x180092ec5  mov     [rbp+60h+var_88], r14
0x180092ec9  mov     [rbp+60h+var_90], r15
0x180092ecd  mov     [rbp+60h+var_98], r12
0x180092ed1  call    cs:__imp_GetCurrentThreadId
0x180092ed8  nop     dword ptr [rax+rax+00h]
0x180092edd  mov     r8, [rbx+110h]
0x180092ee4  lea     rdx, unk_1800EA326
0x180092eeb  mov     [rbp+60h+var_DC], eax
0x180092eee  mov     eax, [r8+48h]
0x180092ef2  add     r8, 8
0x180092ef6  mov     [rbp+60h+var_E0], eax
0x180092ef9  lea     rax, [rbp+60h+arg_90]
0x180092f00  mov     [rsp+210h+var_150], rax
0x180092f08  lea     rax, [rbp+60h+SRWLock]
0x180092f0c  mov     [rsp+210h+var_158], rax
0x180092f14  lea     rax, [rbp+60h+var_B4]
0x180092f18  mov     [rsp+210h+var_160], rax
0x180092f20  lea     rax, [rbp+60h+var_B8]
0x180092f24  mov     [rsp+210h+var_168], rax
0x180092f2c  lea     rax, [rbp+60h+var_BC]
0x180092f30  mov     [rsp+210h+var_170], rax
0x180092f38  lea     rax, [rbp+60h+var_C0]
0x180092f3c  mov     [rsp+210h+var_178], rax
0x180092f44  lea     rax, [rbp+60h+var_C4]
0x180092f48  mov     [rsp+210h+var_180], rax
0x180092f50  lea     rax, [rbp+60h+var_C8]
0x180092f54  mov     [rsp+210h+var_188], rax
0x180092f5c  lea     rax, [rbp+60h+var_CC]
0x180092f60  mov     [rsp+210h+var_190], rax
0x180092f68  lea     rax, [rbp+60h+arg_88]
0x180092f6f  mov     [rsp+210h+var_198], rax
0x180092f74  lea     rax, [rbp+60h+var_D0]
0x180092f78  mov     [rsp+210h+var_1A0], rax
0x180092f7d  lea     rax, [rbp+60h+var_D4]
0x180092f81  mov     [rsp+210h+var_1A8], rax
0x180092f86  lea     rax, [rbp+60h+var_D8]
0x180092f8a  mov     [rsp+210h+var_1B0], rax
0x180092f8f  lea     rax, [rbp+60h+var_78]
0x180092f93  mov     [rsp+210h+var_1B8], rax
0x180092f98  lea     rax, [rbp+60h+var_80]
0x180092f9c  mov     [rsp+210h+var_1C0], rax
0x180092fa1  lea     rax, [rbp+60h+var_88]
0x180092fa5  mov     [rsp+210h+var_1C8], rax
0x180092faa  lea     rax, [rbp+60h+var_90]
0x180092fae  mov     [rsp+210h+var_1D0], rax
0x180092fb3  lea     rax, [rbp+60h+var_98]
0x180092fb7  mov     [rsp+210h+var_1D8], rax
0x180092fbc  lea     rax, [rbp+60h+var_DC]
0x180092fc0  mov     [rsp+210h+var_1E0], rax
0x180092fc5  lea     rax, [rbp+60h+var_E0]
0x180092fc9  mov     [rsp+210h+var_1E8], rax
0x180092fce  lea     rax, [rbp+60h+var_A0]
0x180092fd2  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x180092fd7  mov     qword ptr [rbp+60h+var_A0], 3000000h
0x180092fdf  mov     rcx, rdi
0x180092fe2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@U3@U3@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@5555444AEBU?$_tlgWrapperByVal@$00@@444444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180092fe7  cmp     dword ptr [rbx+138h], 0
0x180092fee  jz      short loc_18009304D
0x180092ff0  add     rbx, 120h
0x180092ff7  call    cs:__imp_GetCurrentThreadId
0x180092ffe  nop     dword ptr [rax+rax+00h]
0x180093003  cmp     [rbx+18h], eax
0x180093006  jz      short loc_180093023
0x180093008  mov     rcx, [rbp+68h]; this
0x18009300c  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180093013  mov     r9d, 8007029Ch; char *
0x180093019  mov     edx, 3BEh; void *
0x18009301e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180093023  and     dword ptr [rbx+18h], 0
0x180093027  mov     rcx, [rbx]
0x18009302a  jmp     short loc_180093038
0x18009302c  cmp     rax, rbx
  ... truncated ...
```
