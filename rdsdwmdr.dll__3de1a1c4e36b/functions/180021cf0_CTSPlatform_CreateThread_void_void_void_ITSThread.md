# CTSPlatform::CreateThread(void (*)(void *),void *,ITSThread * *)

- ea: `0x180021cf0`
- end: `0x180021e07`
- name: `?CreateThread@CTSPlatform@@UEAAJP6AXPEAX@Z0PEAPEAVITSThread@@@Z`
- size: `279`
- prototype: `__int64 __fastcall(CTSPlatform *__hidden this, void (*)(void *), void *, struct ITSThread **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000160c`
- `0x1800032d4`
- `0x180021a98`
- `0x180021cf0`
- `0x1800226ec`
- `0x180025520`
- `0x18002c010`

## string_xrefs

- `0x180021d9d`: `onecore\termsrv\rdpplatform\common\devplatform\platform\platform.cpp`
- `0x180021d7f`: `CreateThread`
- `0x180021db1`: `OOM on new CTSThread`

## pseudocode

```c
__int64 __fastcall CTSPlatform::CreateThread(CTSPlatform *this, void (*a2)(void *), void *a3, struct ITSThread **a4)
{
  int v8; // ebx
  CTSThread *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  CTSThread *v13; // rax
  CTSThread *v14; // rdi
  int v16; // [rsp+50h] [rbp-48h] BYREF
  const char *v17; // [rsp+58h] [rbp-40h] BYREF
  const char *v18; // [rsp+60h] [rbp-38h] BYREF
  const char *v19; // [rsp+68h] [rbp-30h] BYREF
  int v20; // [rsp+B8h] [rbp+20h] BYREF

  if ( a4 )
  {
    v9 = (CTSThread *)operator new(0x2E8u);
    if ( v9 && (v13 = CTSThread::CTSThread(v9, a2, a3, this), (v14 = v13) != 0) )
    {
      v8 = CTSThread::Initialize((CTSThread *)((char *)v13 + 16));
      if ( v8 < 0 )
      {
        CTSThread::`scalar deleting destructor'(v14, 1);
      }
      else
      {
        *a4 = v14;
        (*(void (__fastcall **)(CTSThread *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v20 = 160;
        v17 = "CreateThread";
        v16 = -2147467259;
        v18 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\platform.cpp";
        v19 = "OOM on new CTSThread";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (__int64)word_18003F17A,
          v11,
          v12,
          (const unsigned __int16 **)&v19,
          (__int64)&v16,
          (const unsigned __int16 **)&v18,
          (__int64)&v20,
          (const unsigned __int16 **)&v17);
      }
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180021cf0  push    rbx
0x180021cf2  push    rbp
0x180021cf3  push    rsi
0x180021cf4  push    rdi
0x180021cf5  sub     rsp, 78h
0x180021cf9  mov     rsi, r9
0x180021cfc  mov     rbx, r8
0x180021cff  mov     rdi, rdx
0x180021d02  mov     rbp, rcx
0x180021d05  test    r9, r9
0x180021d08  jnz     short loc_180021D14
0x180021d0a  mov     ebx, 80070057h
0x180021d0f  jmp     loc_180021DFC
0x180021d14  mov     ecx, 2E8h; Size
0x180021d19  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021d1e  test    rax, rax
0x180021d21  jz      short loc_180021D74
0x180021d23  mov     r9, rbp; struct ITSPlatform *
0x180021d26  mov     r8, rbx; void *
0x180021d29  mov     rdx, rdi; void (*)(void *)
0x180021d2c  mov     rcx, rax; this
0x180021d2f  call    ??0CTSThread@@QEAA@P6AXPEAX@Z0PEAVITSPlatform@@@Z; CTSThread::CTSThread(void (*)(void *),void *,ITSPlatform *)
0x180021d34  mov     rdi, rax
0x180021d37  test    rax, rax
0x180021d3a  jz      short loc_180021D74
0x180021d3c  lea     rcx, [rax+10h]; this
0x180021d40  call    ?Initialize@CTSThread@@UEAAJXZ; CTSThread::Initialize(void)
0x180021d45  mov     ebx, eax
0x180021d47  test    eax, eax
0x180021d49  js      short loc_180021D62
0x180021d4b  mov     [rsi], rdi
0x180021d4e  mov     rcx, [rdi]
0x180021d51  mov     rax, [rcx+8]
0x180021d55  mov     rcx, rdi
0x180021d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d5d  jmp     loc_180021DFC
0x180021d62  mov     edx, 1; unsigned int
0x180021d67  mov     rcx, rdi; this
0x180021d6a  call    ??_GCTSThread@@UEAAPEAXI@Z; CTSThread::`scalar deleting destructor'(uint)
0x180021d6f  jmp     loc_180021DFC
0x180021d74  mov     eax, cs:dword_180044008
0x180021d7a  cmp     eax, 2
0x180021d7d  jbe     short loc_180021DF7
0x180021d7f  lea     rax, aCreatethread; "CreateThread"
0x180021d86  mov     [rsp+98h+arg_18], 0A0h
0x180021d91  mov     [rsp+98h+var_40], rax
0x180021d96  lea     rdx, word_18003F17A
0x180021d9d  lea     rax, aOnecoreTermsrv_2; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180021da4  mov     [rsp+98h+var_48], 80004005h
0x180021dac  mov     [rsp+98h+var_38], rax
0x180021db1  lea     rax, aOomOnNewCtsthr; "OOM on new CTSThread"
0x180021db8  mov     [rsp+98h+var_30], rax
0x180021dbd  lea     rax, [rsp+98h+var_40]
0x180021dc2  mov     [rsp+98h+var_58], rax
0x180021dc7  lea     rax, [rsp+98h+arg_18]
0x180021dcf  mov     [rsp+98h+var_60], rax
0x180021dd4  lea     rax, [rsp+98h+var_38]
0x180021dd9  mov     [rsp+98h+var_68], rax
0x180021dde  lea     rax, [rsp+98h+var_48]
0x180021de3  mov     [rsp+98h+var_70], rax
0x180021de8  lea     rax, [rsp+98h+var_30]
0x180021ded  mov     [rsp+98h+var_78], rax
0x180021df2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180021df7  mov     ebx, 8007000Eh
0x180021dfc  mov     eax, ebx
0x180021dfe  add     rsp, 78h
0x180021e02  pop     rdi
0x180021e03  pop     rsi
0x180021e04  pop     rbp
0x180021e05  pop     rbx
0x180021e06  retn
```
