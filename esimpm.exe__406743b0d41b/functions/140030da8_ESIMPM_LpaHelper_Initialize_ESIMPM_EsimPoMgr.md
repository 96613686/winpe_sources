# ESIMPM::LpaHelper::Initialize(ESIMPM::EsimPoMgr *)

- ea: `0x140030da8`
- end: `0x140030ed9`
- name: `?Initialize@LpaHelper@ESIMPM@@QEAAKPEAVEsimPoMgr@2@@Z`
- size: `305`
- prototype: `unsigned int __fastcall(ESIMPM::LpaHelper *__hidden this, struct ESIMPM::EsimPoMgr *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140024d88`

## callees

- `0x140001278`
- `0x140001308`
- `0x140030da8`

## import_xrefs

- `luiapi!LuiOpenHandle` at `0x140030dfa`
- `luiapi!LuiOpenHandle` at `0x140030dfa`
- `luiapi!LuiRegisterForLpaNotifications` at `0x140030e5f`
- `luiapi!LuiRegisterForLpaNotifications` at `0x140030e5f`

## pseudocode

```c
__int64 __fastcall ESIMPM::LpaHelper::Initialize(
        ESIMPM::LpaHelper *this,
        struct ESIMPM::EsimPoMgr *a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  int v10; // edi
  bool v11; // zf
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  const char *v18; // [rsp+60h] [rbp+30h] BYREF
  int v19; // [rsp+70h] [rbp+40h] BYREF
  const char *v20; // [rsp+78h] [rbp+48h] BYREF

  if ( (unsigned int)dword_140075078 > 4 )
  {
    v18 = "ESIMPM::LpaHelper::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)byte_14006C643,
      a3,
      a4,
      (const unsigned __int16 **)&v18);
  }
  v6 = LuiOpenHandle(this, 5, &ESIMPM::LpaHelper::s_LpaCallbackRoutine, this);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v12 = *(_QWORD *)this;
    v19 = 0;
    v13 = LuiRegisterForLpaNotifications(v12, &v19);
    v9 = v13;
    if ( v13 < 0 && (unsigned int)dword_140075078 > 2 )
    {
      v20 = "ESIMPM::LpaHelper::Initialize";
      v16 = v13 & 0x1FFF0000;
      if ( (_DWORD)v16 == 458752 )
        v13 = (unsigned __int16)v13;
      LODWORD(v18) = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v16,
        (__int64)&dword_14006C5CC,
        v14,
        v15,
        (__int64)&v18,
        (const unsigned __int16 **)&v20);
    }
    *((_QWORD *)this + 1) = a2;
    if ( v9 >= 0 )
      return 0;
    v11 = (v9 & 0x1FFF0000) == 458752;
  }
  else
  {
    v10 = v6 & 0x1FFF0000;
    if ( (unsigned int)dword_140075078 > 2 )
    {
      v20 = "ESIMPM::LpaHelper::Initialize";
      if ( v10 == 458752 )
        v6 = (unsigned __int16)v6;
      LODWORD(v18) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_140075078,
        (__int64)&unk_14006C610,
        v7,
        v8,
        (__int64)&v18,
        (const unsigned __int16 **)&v20);
    }
    v11 = v10 == 458752;
  }
  if ( v11 )
    return (unsigned __int16)v9;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140030da8  push    rbp
0x140030daa  push    rbx
0x140030dab  push    rdi
0x140030dac  push    r12
0x140030dae  push    r15
0x140030db0  mov     rbp, rsp
0x140030db3  sub     rsp, 30h
0x140030db7  mov     eax, cs:dword_140075078
0x140030dbd  lea     r12, aEsimpmLpahelpe_6; "ESIMPM::LpaHelper::Initialize"
0x140030dc4  mov     r15, rdx
0x140030dc7  mov     rdi, rcx
0x140030dca  cmp     eax, 4
0x140030dcd  jbe     short loc_140030DE8
0x140030dcf  lea     rax, [rbp+arg_0]
0x140030dd3  mov     [rbp+arg_0], r12
0x140030dd7  lea     rdx, byte_14006C643
0x140030dde  mov     [rsp+30h+var_10], rax
0x140030de3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x140030de8  mov     r9, rdi
0x140030deb  lea     r8, ?s_LpaCallbackRoutine@LpaHelper@ESIMPM@@CAXPEAX0W4LPALUIMSGTYPE@@_KPEAE@Z; ESIMPM::LpaHelper::s_LpaCallbackRoutine(void *,void *,LPALUIMSGTYPE,unsigned __int64,uchar *)
0x140030df2  mov     edx, 5
0x140030df7  mov     rcx, rdi
0x140030dfa  call    cs:__imp_LuiOpenHandle
0x140030e00  mov     ebx, eax
0x140030e02  test    eax, eax
0x140030e04  jns     short loc_140030E51
0x140030e06  mov     ecx, cs:dword_140075078
0x140030e0c  mov     edi, eax
0x140030e0e  and     edi, 1FFF0000h
0x140030e14  cmp     ecx, 2
0x140030e17  jbe     short loc_140030E49
0x140030e19  mov     [rbp+arg_18], r12
0x140030e1d  cmp     edi, 70000h
0x140030e23  jnz     short loc_140030E28
0x140030e25  movzx   eax, bx
0x140030e28  mov     dword ptr [rbp+arg_0], eax
0x140030e2b  lea     rdx, unk_14006C610
0x140030e32  lea     rax, [rbp+arg_18]
0x140030e36  mov     [rsp+30h+var_8], rax
0x140030e3b  lea     rax, [rbp+arg_0]
0x140030e3f  mov     [rsp+30h+var_10], rax
0x140030e44  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140030e49  cmp     edi, 70000h
0x140030e4f  jmp     short loc_140030EC6
0x140030e51  mov     rcx, [rdi]
0x140030e54  lea     rdx, [rbp+arg_10]
0x140030e58  mov     [rbp+arg_10], 0
0x140030e5f  call    cs:__imp_LuiRegisterForLpaNotifications
0x140030e65  mov     ebx, eax
0x140030e67  test    eax, eax
0x140030e69  jns     short loc_140030EAE
0x140030e6b  mov     ecx, cs:dword_140075078
0x140030e71  cmp     ecx, 2
0x140030e74  jbe     short loc_140030EAE
0x140030e76  mov     ecx, eax
0x140030e78  mov     [rbp+arg_18], r12
0x140030e7c  and     ecx, 1FFF0000h
0x140030e82  cmp     ecx, 70000h
0x140030e88  jnz     short loc_140030E8D
0x140030e8a  movzx   eax, bx
0x140030e8d  mov     dword ptr [rbp+arg_0], eax
0x140030e90  lea     rdx, dword_14006C5CC
0x140030e97  lea     rax, [rbp+arg_18]
0x140030e9b  mov     [rsp+30h+var_8], rax
0x140030ea0  lea     rax, [rbp+arg_0]
0x140030ea4  mov     [rsp+30h+var_10], rax
0x140030ea9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140030eae  mov     [rdi+8], r15
0x140030eb2  test    ebx, ebx
0x140030eb4  js      short loc_140030EBA
0x140030eb6  xor     ebx, ebx
0x140030eb8  jmp     short loc_140030ECB
0x140030eba  mov     eax, ebx
0x140030ebc  and     eax, 1FFF0000h
0x140030ec1  cmp     eax, 70000h
0x140030ec6  jnz     short loc_140030ECB
0x140030ec8  movzx   ebx, bx
0x140030ecb  mov     eax, ebx
0x140030ecd  add     rsp, 30h
0x140030ed1  pop     r15
0x140030ed3  pop     r12
0x140030ed5  pop     rdi
0x140030ed6  pop     rbx
0x140030ed7  pop     rbp
0x140030ed8  retn
```
