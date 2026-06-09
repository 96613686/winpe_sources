# CSyncMLCmdSequence::BatchUpExecution(IConfigManager2 *)

- ea: `0x18001ed20`
- end: `0x18001ef41`
- name: `?BatchUpExecution@CSyncMLCmdSequence@@UEAAJPEAUIConfigManager2@@@Z`
- size: `545`
- prototype: `__int64 __fastcall(CSyncMLCmdSequence *__hidden this, struct IConfigManager2 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180001190`
- `0x1800034d0`
- `0x1800043c0`
- `0x180004780`
- `0x18000fad0`
- `0x18001ed20`
- `0x180021624`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdSequence::BatchUpExecution(
        CSyncMLCmdSequence *this,
        struct IConfigManager2 *a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // ebx
  __int64 v8; // rbx
  int v9; // r15d
  int v10; // ebp
  CSyncMLCmd *v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // esi
  int v15; // eax
  int v16; // [rsp+68h] [rbp+10h] BYREF
  int v17; // [rsp+70h] [rbp+18h] BYREF

  if ( !a2 )
  {
    v6 = -2147467261;
    goto LABEL_3;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 40LL) )
  {
    v6 = 0;
    CSyncMLCmd::SetBypassResult(this);
    goto LABEL_5;
  }
  v6 = CSyncMLCmd::VerifyDTD(this);
  if ( v6 < 0 )
    goto LABEL_3;
  if ( *((int *)this + 14) >= 0 )
  {
    v8 = (__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 3;
    if ( !(_DWORD)v8 )
    {
      if ( (unsigned int)dword_18003E048 > 2 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18003E048,
          &word_180036EEE,
          0,
          0);
      goto LABEL_15;
    }
    v9 = 0;
    v10 = 0;
    if ( (int)v8 <= 0 )
    {
LABEL_35:
      v6 = 0;
      goto LABEL_5;
    }
    while ( 1 )
    {
      v11 = *(CSyncMLCmd **)(*((_QWORD *)this + 4) + 8LL * v10);
      if ( v9 )
      {
        CSyncMLCmd::SetBypassResult(v11);
      }
      else
      {
        if ( *((_DWORD *)v11 + 23) == 39 )
        {
          if ( (unsigned int)dword_18003E048 > 2 )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              &dword_18003E048,
              word_180036A5A,
              0,
              0);
LABEL_15:
          v6 = -2102788095;
LABEL_3:
          if ( *((int *)this + 15) >= 0 )
            *((_DWORD *)this + 15) = v6;
          break;
        }
        if ( (int)CSyncMLCmd::GetCmdPreExecHresult(v11) >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, struct IConfigManager2 *))(*(_QWORD *)v12 + 24LL))(v12, a2);
          v14 = v13;
          if ( v13 < 0 && (unsigned int)dword_18003E048 > 2 )
          {
            v16 = v13;
            v17 = v10;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (__int64)&dword_18003E048,
              (unsigned __int8 *)byte_18003706B,
              a3,
              a4,
              (__int64)&v17,
              (__int64)&v16);
          }
          if ( ((v14 + 2102722556) & 0xFFFFFFF9) != 0 || v14 == -2102722550 )
          {
            if ( v14 >= 0 && !(unsigned int)CSyncMLCmd::IsInAtomic(this) )
            {
              if ( (unsigned int)dword_18003E048 > 5 )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  &dword_18003E048,
                  byte_18003678D,
                  0,
                  0);
              v15 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 24LL))(a2);
              if ( v15 < 0 && (unsigned int)dword_18003E048 > 2 )
              {
                v16 = v15;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (__int64)&dword_18003E048,
                  (unsigned __int8 *)byte_180036BD7,
                  a3,
                  a4,
                  (__int64)&v16);
              }
            }
          }
          else
          {
            v9 = 1;
          }
        }
      }
      if ( ++v10 >= (int)v8 )
        goto LABEL_35;
    }
  }
LABEL_5:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v16 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&dword_180036E5C,
      a3,
      a4,
      (__int64)&v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ed20  mov     [rsp+arg_0], rbx
0x18001ed25  mov     [rsp+arg_18], rbp
0x18001ed2a  push    rsi
0x18001ed2b  push    rdi
0x18001ed2c  push    r13
0x18001ed2e  push    r14
0x18001ed30  push    r15
0x18001ed32  sub     rsp, 30h
0x18001ed36  lea     r13, dword_18003E048
0x18001ed3d  mov     r14, rdx
0x18001ed40  mov     rdi, rcx
0x18001ed43  test    rdx, rdx
0x18001ed46  jnz     short loc_18001ED98
0x18001ed48  mov     ebx, 80004003h
0x18001ed4d  cmp     dword ptr [rdi+3Ch], 0
0x18001ed51  jl      short loc_18001ED56
0x18001ed53  mov     [rdi+3Ch], ebx
0x18001ed56  mov     eax, cs:dword_18003E048
0x18001ed5c  cmp     eax, 5
0x18001ed5f  jbe     short loc_18001ED7E
0x18001ed61  lea     rax, [rsp+58h+arg_8]
0x18001ed66  mov     [rsp+58h+arg_8], ebx
0x18001ed6a  lea     rdx, dword_180036E5C
0x18001ed71  mov     [rsp+58h+var_38], rax
0x18001ed76  mov     rcx, r13
0x18001ed79  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001ed7e  mov     rbp, [rsp+58h+arg_18]
0x18001ed83  mov     eax, ebx
0x18001ed85  mov     rbx, [rsp+58h+arg_0]
0x18001ed8a  add     rsp, 30h
0x18001ed8e  pop     r15
0x18001ed90  pop     r14
0x18001ed92  pop     r13
0x18001ed94  pop     rdi
0x18001ed95  pop     rsi
0x18001ed96  retn
0x18001ed98  mov     rax, [rcx+50h]
0x18001ed9c  cmp     dword ptr [rax+28h], 0
0x18001eda0  jz      short loc_18001EDAB
0x18001eda2  xor     ebx, ebx
0x18001eda4  call    ?SetBypassResult@CSyncMLCmd@@QEAAXXZ; CSyncMLCmd::SetBypassResult(void)
0x18001eda9  jmp     short loc_18001ED56
0x18001edab  call    ?VerifyDTD@CSyncMLCmd@@IEBAJXZ; CSyncMLCmd::VerifyDTD(void)
0x18001edb0  mov     ebx, eax
0x18001edb2  test    eax, eax
0x18001edb4  js      short loc_18001ED4D
0x18001edb6  cmp     dword ptr [rdi+38h], 0
0x18001edba  jl      short loc_18001ED56
0x18001edbc  mov     rbx, [rdi+28h]
0x18001edc0  sub     rbx, [rdi+20h]
0x18001edc4  sar     rbx, 3
0x18001edc8  test    ebx, ebx
0x18001edca  jnz     short loc_18001EDF6
0x18001edcc  mov     eax, cs:dword_18003E048
0x18001edd2  cmp     eax, 2
0x18001edd5  jbe     short loc_18001EDEC
0x18001edd7  xor     r9d, r9d
0x18001edda  lea     rdx, word_180036EEE
0x18001ede1  xor     r8d, r8d
0x18001ede4  mov     rcx, r13
0x18001ede7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001edec  mov     ebx, 82AA0001h
0x18001edf1  jmp     loc_18001ED4D
0x18001edf6  xor     r15d, r15d
0x18001edf9  xor     ebp, ebp
0x18001edfb  test    ebx, ebx
0x18001edfd  jle     loc_18001EF11
0x18001ee03  mov     rax, [rdi+20h]
0x18001ee07  movsxd  rcx, ebp
0x18001ee0a  mov     rcx, [rax+rcx*8]; this
0x18001ee0e  test    r15d, r15d
0x18001ee11  jz      short loc_18001EE1D
0x18001ee13  call    ?SetBypassResult@CSyncMLCmd@@QEAAXXZ; CSyncMLCmd::SetBypassResult(void)
0x18001ee18  jmp     loc_18001EF07
0x18001ee1d  cmp     dword ptr [rcx+5Ch], 27h ; '''
0x18001ee21  jz      loc_18001EF18
0x18001ee27  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x18001ee2c  test    eax, eax
0x18001ee2e  js      loc_18001EF07
0x18001ee34  mov     rax, [rcx]
0x18001ee37  mov     rdx, r14
0x18001ee3a  mov     rax, [rax+18h]
0x18001ee3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee43  mov     esi, eax
0x18001ee45  test    eax, eax
0x18001ee47  jns     short loc_18001EE7F
0x18001ee49  mov     ecx, cs:dword_18003E048
0x18001ee4f  cmp     ecx, 2
0x18001ee52  jbe     short loc_18001EE7F
0x18001ee54  mov     [rsp+58h+arg_8], eax
0x18001ee58  lea     rdx, byte_18003706B
0x18001ee5f  lea     rax, [rsp+58h+arg_8]
0x18001ee64  mov     [rsp+58h+arg_10], ebp
0x18001ee68  mov     [rsp+58h+var_30], rax
0x18001ee6d  mov     rcx, r13
0x18001ee70  lea     rax, [rsp+58h+arg_10]
0x18001ee75  mov     [rsp+58h+var_38], rax
0x18001ee7a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ee7f  lea     eax, [rsi+7D54FFFCh]
0x18001ee85  test    eax, 0FFFFFFF9h
0x18001ee8a  jnz     short loc_18001EE9C
0x18001ee8c  cmp     esi, 82AB000Ah
0x18001ee92  jz      short loc_18001EE9C
0x18001ee94  mov     r15d, 1
0x18001ee9a  jmp     short loc_18001EF07
0x18001ee9c  test    esi, esi
0x18001ee9e  js      short loc_18001EF07
0x18001eea0  mov     rcx, rdi; this
0x18001eea3  call    ?IsInAtomic@CSyncMLCmd@@IEBAHXZ; CSyncMLCmd::IsInAtomic(void)
0x18001eea8  test    eax, eax
0x18001eeaa  jnz     short loc_18001EF07
0x18001eeac  mov     eax, cs:dword_18003E048
0x18001eeb2  cmp     eax, 5
0x18001eeb5  jbe     short loc_18001EECC
0x18001eeb7  xor     r9d, r9d
0x18001eeba  lea     rdx, byte_18003678D
0x18001eec1  xor     r8d, r8d
0x18001eec4  mov     rcx, r13
0x18001eec7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001eecc  mov     rax, [r14]
0x18001eecf  mov     rcx, r14
0x18001eed2  mov     rax, [rax+18h]
0x18001eed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eedb  test    eax, eax
0x18001eedd  jns     short loc_18001EF07
0x18001eedf  mov     ecx, cs:dword_18003E048
0x18001eee5  cmp     ecx, 2
0x18001eee8  jbe     short loc_18001EF07
0x18001eeea  mov     [rsp+58h+arg_8], eax
0x18001eeee  lea     rdx, byte_180036BD7
0x18001eef5  lea     rax, [rsp+58h+arg_8]
0x18001eefa  mov     rcx, r13
0x18001eefd  mov     [rsp+58h+var_38], rax
0x18001ef02  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001ef07  inc     ebp
0x18001ef09  cmp     ebp, ebx
0x18001ef0b  jl      loc_18001EE03
0x18001ef11  xor     ebx, ebx
0x18001ef13  jmp     loc_18001ED56
0x18001ef18  mov     eax, cs:dword_18003E048
0x18001ef1e  cmp     eax, 2
0x18001ef21  jbe     loc_18001EDEC
0x18001ef27  xor     r9d, r9d
0x18001ef2a  lea     rdx, word_180036A5A
0x18001ef31  xor     r8d, r8d
0x18001ef34  mov     rcx, r13
0x18001ef37  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001ef3c  jmp     loc_18001EDEC
```
