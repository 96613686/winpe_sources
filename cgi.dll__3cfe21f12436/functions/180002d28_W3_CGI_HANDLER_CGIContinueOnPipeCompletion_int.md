# W3_CGI_HANDLER::CGIContinueOnPipeCompletion(int *)

- ea: `0x180002d28`
- end: `0x180002f09`
- name: `?CGIContinueOnPipeCompletion@W3_CGI_HANDLER@@AEAAJPEAH@Z`
- size: `481`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003088`
- `0x1800047f0`

## callees

- `0x180002d28`
- `0x180002f10`
- `0x180002fb0`
- `0x18000325c`
- `0x180004e50`
- `0x180008010`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::CGIContinueOnPipeCompletion(W3_CGI_HANDLER *this, int *a2)
{
  __int64 v4; // r14
  __int64 result; // rax
  __int64 v6; // rax
  int v7; // eax
  int (__fastcall ***v8)(_QWORD, GUID **); // rax
  int (__fastcall **v9)(_QWORD, GUID **); // rcx
  __int64 *v10; // rcx
  __int64 v11; // rax
  void (__fastcall *v12)(__int64 *, _QWORD *); // rax
  GUID *v13; // [rsp+20h] [rbp-69h] BYREF
  __int128 v14; // [rsp+28h] [rbp-61h]
  int v15; // [rsp+38h] [rbp-51h]
  __int64 v16; // [rsp+40h] [rbp-49h]
  _QWORD v17[5]; // [rsp+50h] [rbp-39h] BYREF
  int v18; // [rsp+78h] [rbp-11h]
  int v19; // [rsp+7Ch] [rbp-Dh]
  __int128 v20; // [rsp+80h] [rbp-9h]
  int v21; // [rsp+90h] [rbp+7h]
  int v22; // [rsp+94h] [rbp+Bh]
  __int64 v23; // [rsp+98h] [rbp+Fh]
  GUID **v24; // [rsp+A0h] [rbp+17h]
  int v25; // [rsp+F0h] [rbp+67h] BYREF

  if ( *((_DWORD *)this + 2) == 1 )
  {
    v4 = *((_QWORD *)this + 6);
    v25 = 0;
    result = W3_CGI_HANDLER::CGIReadRequestEntity(this, &v25);
    if ( (int)result >= 0 && v25 != 1 )
    {
      if ( *((_DWORD *)this + 2090) )
      {
        v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 32LL))(v4);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 128LL))(v6);
        v7 = 3;
      }
      else
      {
        v7 = 2;
      }
      *((_DWORD *)this + 2) = v7;
      *((_DWORD *)this + 2076) = 0;
      v8 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 272LL))(v4);
      v13 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
      v9 = *v8;
      v14 = 0;
      if ( (*v9)(v8, &v13) >= 0 && DWORD2(v14) && DWORD1(v14) >= 4 && ((_DWORD)v14 == 32 || (v14 & 0x20) != 0) )
      {
        v10 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 272LL))(v4);
        v17[1] = 32;
        v17[3] = 6;
        v17[2] = &`IISCGIEvents::GetAreaGuid'::`2'::AreaGuid;
        v23 = 1;
        v17[4] = L"CGI_REQUEST_ENTITY_SENT";
        v17[0] = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
        v13 = (GUID *)L"ContextId";
        v24 = &v13;
        v11 = *v10;
        v18 = 1;
        v19 = 4;
        v20 = 0;
        v12 = *(void (__fastcall **)(__int64 *, _QWORD *))(v11 + 16);
        v21 = 0;
        v22 = 1;
        LODWORD(v14) = 72;
        *((_QWORD *)&v14 + 1) = 0;
        v15 = 16;
        v16 = 0;
        v12(v10, v17);
      }
      result = W3_CGI_HANDLER::CGIReadCGIOutput(this);
      goto LABEL_14;
    }
LABEL_19:
    *a2 = 0;
    return result;
  }
  if ( *((_DWORD *)this + 2) != 2 )
  {
    result = W3_CGI_HANDLER::CGIWriteResponseEntity(this);
    if ( (int)result >= 0 )
      return result;
    goto LABEL_19;
  }
  result = W3_CGI_HANDLER::ProcessCGIOutput(this);
LABEL_14:
  if ( (int)result < 0 )
    *a2 = 1;
  return result;
}

```

## disassembly

```asm
0x180002d28  push    rbp
0x180002d2a  push    rsi
0x180002d2b  push    rdi
0x180002d2c  push    r12
0x180002d2e  push    r14
0x180002d30  push    r15
0x180002d32  lea     rbp, [rsp-2Fh]
0x180002d37  sub     rsp, 0B8h
0x180002d3e  mov     r15d, 1
0x180002d44  mov     rsi, rdx
0x180002d47  mov     rdi, rcx
0x180002d4a  cmp     [rcx+8], r15d
0x180002d4e  jnz     loc_180002ED8
0x180002d54  mov     r14, [rcx+30h]
0x180002d58  lea     rdx, [rbp+57h+arg_0]; int *
0x180002d5c  mov     [rbp+57h+arg_0], 0
0x180002d63  call    ?CGIReadRequestEntity@W3_CGI_HANDLER@@AEAAJPEAH@Z; W3_CGI_HANDLER::CGIReadRequestEntity(int *)
0x180002d68  test    eax, eax
0x180002d6a  js      loc_180002EF2
0x180002d70  cmp     [rbp+57h+arg_0], r15d
0x180002d74  jz      loc_180002EF2
0x180002d7a  cmp     dword ptr [rdi+20A8h], 0
0x180002d81  jz      short loc_180002DAD
0x180002d83  mov     rax, [r14]
0x180002d86  mov     rcx, r14
0x180002d89  mov     rax, [rax+20h]
0x180002d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d92  mov     rdx, rax
0x180002d95  mov     rcx, [rax]
0x180002d98  mov     rax, [rcx+80h]
0x180002d9f  mov     rcx, rdx
0x180002da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da7  lea     eax, [r15+2]
0x180002dab  jmp     short loc_180002DB2
0x180002dad  mov     eax, 2
0x180002db2  mov     [rdi+8], eax
0x180002db5  mov     rcx, r14
0x180002db8  mov     dword ptr [rdi+2070h], 0
0x180002dc2  mov     rax, [r14]
0x180002dc5  mov     rax, [rax+110h]
0x180002dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd1  mov     r8, rax
0x180002dd4  lea     r12, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180002ddb  xorps   xmm0, xmm0
0x180002dde  mov     [rbp+57h+var_C0], r12
0x180002de2  lea     rdx, [rbp+57h+var_C0]
0x180002de6  mov     rcx, [rax]
0x180002de9  movdqu  [rbp+57h+var_B8], xmm0
0x180002dee  mov     rax, [rcx]
0x180002df1  mov     rcx, r8
0x180002df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df9  test    eax, eax
0x180002dfb  js      loc_180002EC7
0x180002e01  cmp     dword ptr [rbp+57h+var_B8+8], 0
0x180002e05  jz      loc_180002EC7
0x180002e0b  cmp     dword ptr [rbp+57h+var_B8+4], 4
0x180002e0f  jb      loc_180002EC7
0x180002e15  cmp     dword ptr [rbp+57h+var_B8], 20h ; ' '
0x180002e19  jz      short loc_180002E25
0x180002e1b  test    byte ptr [rbp+57h+var_B8], 20h
0x180002e1f  jz      loc_180002EC7
0x180002e25  mov     rax, [r14]
0x180002e28  mov     rcx, r14
0x180002e2b  mov     rax, [rax+110h]
0x180002e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e37  mov     rcx, rax
0x180002e3a  mov     [rbp+57h+var_88], 20h ; ' '
0x180002e42  lea     rax, ?AreaGuid@?1??GetAreaGuid@IISCGIEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `IISCGIEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180002e49  mov     [rbp+57h+var_78], 6
0x180002e51  mov     [rbp+57h+var_80], rax
0x180002e55  lea     rdx, [rbp+57h+var_90]
0x180002e59  lea     rax, aCgiRequestEnti; "CGI_REQUEST_ENTITY_SENT"
0x180002e60  mov     [rbp+57h+var_48], r15
0x180002e64  mov     [rbp+57h+var_70], rax
0x180002e68  xorps   xmm0, xmm0
0x180002e6b  lea     rax, aContextid; "ContextId"
0x180002e72  mov     [rbp+57h+var_90], r12
0x180002e76  mov     [rbp+57h+var_C0], rax
0x180002e7a  lea     rax, [rbp+57h+var_C0]
0x180002e7e  mov     [rbp+57h+var_40], rax
0x180002e82  mov     rax, [rcx]
0x180002e85  mov     [rbp+57h+var_68], r15d
0x180002e89  mov     [rbp+57h+var_64], 4
0x180002e90  movdqa  [rbp+57h+var_60], xmm0
0x180002e95  mov     rax, [rax+10h]
0x180002e99  mov     [rbp+57h+var_50], 0
0x180002ea0  mov     [rbp+57h+var_4C], r15d
0x180002ea4  mov     dword ptr [rbp+57h+var_B8], 48h ; 'H'
0x180002eab  mov     qword ptr [rbp+57h+var_B8+8], 0
0x180002eb3  mov     [rbp+57h+var_A8], 10h
0x180002eba  mov     [rbp+57h+var_A0], 0
0x180002ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec7  mov     rcx, rdi; this
0x180002eca  call    ?CGIReadCGIOutput@W3_CGI_HANDLER@@AEAAJXZ; W3_CGI_HANDLER::CGIReadCGIOutput(void)
0x180002ecf  test    eax, eax
0x180002ed1  jns     short loc_180002EF8
0x180002ed3  mov     [rsi], r15d
0x180002ed6  jmp     short loc_180002EF8
0x180002ed8  mov     eax, 2
0x180002edd  cmp     [rcx+8], eax
0x180002ee0  jnz     short loc_180002EE9
0x180002ee2  call    ?ProcessCGIOutput@W3_CGI_HANDLER@@AEAAJXZ; W3_CGI_HANDLER::ProcessCGIOutput(void)
0x180002ee7  jmp     short loc_180002ECF
0x180002ee9  call    ?CGIWriteResponseEntity@W3_CGI_HANDLER@@AEAAJXZ; W3_CGI_HANDLER::CGIWriteResponseEntity(void)
0x180002eee  test    eax, eax
0x180002ef0  jns     short loc_180002EF8
0x180002ef2  mov     dword ptr [rsi], 0
0x180002ef8  add     rsp, 0B8h
0x180002eff  pop     r15
0x180002f01  pop     r14
0x180002f03  pop     r12
0x180002f05  pop     rdi
0x180002f06  pop     rsi
0x180002f07  pop     rbp
0x180002f08  retn
```
