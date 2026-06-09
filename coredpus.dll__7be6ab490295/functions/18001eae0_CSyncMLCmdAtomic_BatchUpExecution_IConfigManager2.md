# CSyncMLCmdAtomic::BatchUpExecution(IConfigManager2 *)

- ea: `0x18001eae0`
- end: `0x18001ed17`
- name: `?BatchUpExecution@CSyncMLCmdAtomic@@UEAAJPEAUIConfigManager2@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(CSyncMLCmdAtomic *__hidden this, struct IConfigManager2 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180001190`
- `0x1800034d0`
- `0x1800043c0`
- `0x18000fad0`
- `0x18001eae0`
- `0x180020814`
- `0x180021624`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAtomic::BatchUpExecution(
        CSyncMLCmdAtomic *this,
        struct IConfigManager2 *a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // r12d
  int v7; // ebx
  __int64 v8; // rbp
  __int64 v9; // rsi
  __int64 v10; // rbp
  __int64 v11; // r15
  __int64 v12; // rax
  CSyncMLCmd *v13; // rsi
  CSyncMLCmd *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  CSyncMLCmd *v17; // rcx
  CSyncMLCmd *v18; // rcx
  int v20; // [rsp+60h] [rbp+8h] BYREF
  int v21; // [rsp+68h] [rbp+10h] BYREF

  v4 = 0;
  v20 = 0;
  if ( a2 )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 10) + 40LL) )
    {
      v7 = 0;
      CSyncMLCmd::SetBypassResult(this);
      goto LABEL_26;
    }
    v8 = *((_QWORD *)this + 5);
    v9 = *((_QWORD *)this + 4);
    v7 = CSyncMLCmd::VerifyDTD(this);
    if ( v7 >= 0 )
    {
      if ( *((int *)this + 14) < 0 )
        goto LABEL_26;
      v10 = (v8 - v9) >> 3;
      if ( (_DWORD)v10 )
      {
        v7 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 56LL))(a2);
        if ( v7 >= 0 )
        {
          v11 = 0;
          v4 = 1;
          if ( (int)v10 > 0 )
          {
            while ( 1 )
            {
              v12 = *((_QWORD *)this + 4);
              v13 = *(CSyncMLCmd **)(v12 + 8 * v11);
              if ( *((_DWORD *)v13 + 23) == 32 )
                break;
              if ( (int)CSyncMLCmd::GetCmdPreExecHresult(*(CSyncMLCmd **)(v12 + 8 * v11)) < 0
                || (unsigned int)CSyncMLCmd::GetFirstFailedItemPreExecHresult(v14, &v20) )
              {
                goto LABEL_24;
              }
              v7 = (*(__int64 (__fastcall **)(CSyncMLCmd *, struct IConfigManager2 *))(*(_QWORD *)v13 + 24LL))(v13, a2);
              if ( v7 < 0 || (int)CSyncMLCmd::GetCmdPreExecHresult(v13) < 0 )
              {
                if ( (unsigned int)dword_18003E048 > 2 )
                {
                  v20 = v7;
                  v21 = v11;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    (__int64)&dword_18003E048,
                    (unsigned __int8 *)&word_180036F46,
                    v15,
                    v16,
                    (__int64)&v21,
                    (__int64)&v20);
                }
                v7 = 0;
                goto LABEL_25;
              }
              if ( (int)CSyncMLCmd::GetCmdPreExecHresult(v17) < 0
                || (unsigned int)CSyncMLCmd::GetFirstFailedItemPreExecHresult(v18, &v20) )
              {
                goto LABEL_25;
              }
              v11 = (unsigned int)(v11 + 1);
              if ( (int)v11 >= (int)v10 )
                goto LABEL_21;
            }
            if ( *((int *)v13 + 15) >= 0 )
              *((_DWORD *)v13 + 15) = -2147467259;
            if ( (unsigned int)dword_18003E048 > 2 )
            {
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                &dword_18003E048,
                &word_180036CA6,
                0,
                0);
              goto LABEL_25;
            }
            goto LABEL_24;
          }
LABEL_21:
          v7 = (*(__int64 (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 64LL))(a2);
          if ( v7 >= 0 )
            goto LABEL_26;
        }
      }
      else
      {
        if ( (unsigned int)dword_18003E048 > 2 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18003E048,
            &word_180037106,
            0,
            0);
        v7 = -2102788095;
      }
    }
  }
  else
  {
    v7 = -2147467261;
  }
  if ( *((int *)this + 15) >= 0 )
    *((_DWORD *)this + 15) = v7;
LABEL_24:
  if ( v4 )
LABEL_25:
    (*(void (__fastcall **)(struct IConfigManager2 *))(*(_QWORD *)a2 + 72LL))(a2);
LABEL_26:
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v20 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_180036F85,
      a3,
      a4,
      (__int64)&v20);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001eae0  mov     [rsp+arg_10], rbx
0x18001eae5  mov     [rsp+arg_18], rbp
0x18001eaea  push    rsi
0x18001eaeb  push    rdi
0x18001eaec  push    r12
0x18001eaee  push    r14
0x18001eaf0  push    r15
0x18001eaf2  sub     rsp, 30h
0x18001eaf6  xor     r12d, r12d
0x18001eaf9  mov     [rsp+58h+arg_0], 0
0x18001eb01  mov     r14, rdx
0x18001eb04  mov     rdi, rcx
0x18001eb07  test    rdx, rdx
0x18001eb0a  jnz     short loc_18001EB16
0x18001eb0c  mov     ebx, 80004003h
0x18001eb11  jmp     loc_18001EC38
0x18001eb16  mov     rax, [rcx+50h]
0x18001eb1a  cmp     [rax+28h], r12d
0x18001eb1e  jz      short loc_18001EB2C
0x18001eb20  xor     ebx, ebx
0x18001eb22  call    ?SetBypassResult@CSyncMLCmd@@QEAAXXZ; CSyncMLCmd::SetBypassResult(void)
0x18001eb27  jmp     loc_18001EC55
0x18001eb2c  mov     rbp, [rcx+28h]
0x18001eb30  mov     rsi, [rcx+20h]
0x18001eb34  call    ?VerifyDTD@CSyncMLCmd@@IEBAJXZ; CSyncMLCmd::VerifyDTD(void)
0x18001eb39  mov     ebx, eax
0x18001eb3b  test    eax, eax
0x18001eb3d  js      loc_18001EC38
0x18001eb43  cmp     [rdi+38h], r12d
0x18001eb47  jl      loc_18001EC55
0x18001eb4d  sub     rbp, rsi
0x18001eb50  sar     rbp, 3
0x18001eb54  test    ebp, ebp
0x18001eb56  jnz     short loc_18001EB86
0x18001eb58  mov     eax, cs:dword_18003E048
0x18001eb5e  cmp     eax, 2
0x18001eb61  jbe     short loc_18001EB7C
0x18001eb63  xor     r9d, r9d
0x18001eb66  lea     rdx, word_180037106
0x18001eb6d  xor     r8d, r8d
0x18001eb70  lea     rcx, dword_18003E048
0x18001eb77  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001eb7c  mov     ebx, 82AA0001h
0x18001eb81  jmp     loc_18001EC38
0x18001eb86  mov     rax, [r14]
0x18001eb89  mov     rcx, r14
0x18001eb8c  mov     rax, [rax+38h]
0x18001eb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb95  mov     ebx, eax
0x18001eb97  test    eax, eax
0x18001eb99  js      loc_18001EC38
0x18001eb9f  xor     r15d, r15d
0x18001eba2  mov     r12d, 1
0x18001eba8  test    ebp, ebp
0x18001ebaa  jle     short loc_18001EC23
0x18001ebac  mov     rax, [rdi+20h]
0x18001ebb0  mov     rsi, [rax+r15*8]
0x18001ebb4  cmp     dword ptr [rsi+5Ch], 20h ; ' '
0x18001ebb8  jz      loc_18001ECDD
0x18001ebbe  mov     rcx, rsi; this
0x18001ebc1  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x18001ebc6  test    eax, eax
0x18001ebc8  js      short loc_18001EC41
0x18001ebca  lea     rdx, [rsp+58h+arg_0]; int *
0x18001ebcf  call    ?GetFirstFailedItemPreExecHresult@CSyncMLCmd@@QEBAHPEAJ@Z; CSyncMLCmd::GetFirstFailedItemPreExecHresult(long *)
0x18001ebd4  test    eax, eax
0x18001ebd6  jnz     short loc_18001EC41
0x18001ebd8  mov     rax, [rsi]
0x18001ebdb  mov     rdx, r14
0x18001ebde  mov     rcx, rsi
0x18001ebe1  mov     rax, [rax+18h]
0x18001ebe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebea  mov     ebx, eax
0x18001ebec  test    eax, eax
0x18001ebee  js      loc_18001EC9B
0x18001ebf4  mov     rcx, rsi; this
0x18001ebf7  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x18001ebfc  test    eax, eax
0x18001ebfe  js      loc_18001EC9B
0x18001ec04  call    ?GetCmdPreExecHresult@CSyncMLCmd@@QEBAJXZ; CSyncMLCmd::GetCmdPreExecHresult(void)
0x18001ec09  test    eax, eax
0x18001ec0b  js      short loc_18001EC46
0x18001ec0d  lea     rdx, [rsp+58h+arg_0]; int *
0x18001ec12  call    ?GetFirstFailedItemPreExecHresult@CSyncMLCmd@@QEBAHPEAJ@Z; CSyncMLCmd::GetFirstFailedItemPreExecHresult(long *)
0x18001ec17  test    eax, eax
0x18001ec19  jnz     short loc_18001EC46
0x18001ec1b  add     r15d, r12d
0x18001ec1e  cmp     r15d, ebp
0x18001ec21  jl      short loc_18001EBAC
0x18001ec23  mov     rax, [r14]
0x18001ec26  mov     rcx, r14
0x18001ec29  mov     rax, [rax+40h]
0x18001ec2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec32  mov     ebx, eax
0x18001ec34  test    eax, eax
0x18001ec36  jns     short loc_18001EC55
0x18001ec38  cmp     dword ptr [rdi+3Ch], 0
0x18001ec3c  jl      short loc_18001EC41
0x18001ec3e  mov     [rdi+3Ch], ebx
0x18001ec41  test    r12d, r12d
0x18001ec44  jz      short loc_18001EC55
0x18001ec46  mov     rax, [r14]
0x18001ec49  mov     rcx, r14
0x18001ec4c  mov     rax, [rax+48h]
0x18001ec50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec55  mov     eax, cs:dword_18003E048
0x18001ec5b  cmp     eax, 5
0x18001ec5e  jbe     short loc_18001EC81
0x18001ec60  lea     rax, [rsp+58h+arg_0]
0x18001ec65  mov     [rsp+58h+arg_0], ebx
0x18001ec69  lea     rdx, byte_180036F85
0x18001ec70  mov     [rsp+58h+var_38], rax
0x18001ec75  lea     rcx, dword_18003E048
0x18001ec7c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001ec81  mov     rbp, [rsp+58h+arg_18]
0x18001ec86  mov     eax, ebx
0x18001ec88  mov     rbx, [rsp+58h+arg_10]
0x18001ec8d  add     rsp, 30h
0x18001ec91  pop     r15
0x18001ec93  pop     r14
0x18001ec95  pop     r12
0x18001ec97  pop     rdi
0x18001ec98  pop     rsi
0x18001ec99  retn
0x18001ec9b  mov     eax, cs:dword_18003E048
0x18001eca1  cmp     eax, 2
0x18001eca4  jbe     short loc_18001ECD6
0x18001eca6  lea     rax, [rsp+58h+arg_0]
0x18001ecab  mov     [rsp+58h+arg_0], ebx
0x18001ecaf  mov     [rsp+58h+var_30], rax
0x18001ecb4  lea     rdx, word_180036F46
0x18001ecbb  lea     rax, [rsp+58h+arg_8]
0x18001ecc0  mov     [rsp+58h+arg_8], r15d
0x18001ecc5  lea     rcx, dword_18003E048
0x18001eccc  mov     [rsp+58h+var_38], rax
0x18001ecd1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ecd6  xor     ebx, ebx
0x18001ecd8  jmp     loc_18001EC46
0x18001ecdd  cmp     dword ptr [rsi+3Ch], 0
0x18001ece1  jl      short loc_18001ECEA
0x18001ece3  mov     dword ptr [rsi+3Ch], 80004005h
0x18001ecea  mov     eax, cs:dword_18003E048
0x18001ecf0  cmp     eax, 2
0x18001ecf3  jbe     loc_18001EC41
0x18001ecf9  xor     r9d, r9d
0x18001ecfc  lea     rdx, word_180036CA6
0x18001ed03  xor     r8d, r8d
0x18001ed06  lea     rcx, dword_18003E048
0x18001ed0d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001ed12  jmp     loc_18001EC46
```
