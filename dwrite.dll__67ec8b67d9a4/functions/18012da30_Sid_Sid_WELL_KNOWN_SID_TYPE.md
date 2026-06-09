# Sid::Sid(WELL_KNOWN_SID_TYPE)

- ea: `0x18012da30`
- end: `0x18012db1d`
- name: `??0Sid@@QEAA@W4WELL_KNOWN_SID_TYPE@@@Z`
- size: `237`
- prototype: `Sid *__fastcall(Sid *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18012d8dc`

## callees

- `0x18011ef30`
- `0x18012a85c`
- `0x18012da30`
- `0x180154068`
- `0x1801f2fe4`
- `0x180208dec`
- `0x180212f4c`

## import_xrefs

- `kernel32!GetLastError` at `0x18012da68`
- `kernel32!GetLastError` at `0x18012da68`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012da5e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012daae`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012da5e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18012daae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Sid *__fastcall Sid::Sid(Sid *this, DWORD a2)
{
  signed int LastError; // eax
  __int64 v4; // rsi
  char *v5; // rdx
  unsigned __int64 v6; // rcx
  char *v8; // rax
  unsigned int v9; // edx
  size_t v10; // rdi
  DWORD cbSid; // [rsp+48h] [rbp+10h] BYREF
  char v12; // [rsp+50h] [rbp+18h] BYREF

  cbSid = a2;
  std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(this);
  cbSid = 0;
  if ( !CreateWellKnownSid(WinLocalServiceSid, 0, 0, &cbSid) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      Exception::Exception((Exception *)&v12, v9, LastError);
      LogAndThrow<OSException>(&v12, 4475219, 40);
    }
  }
  v4 = *((_QWORD *)this + 1);
  v5 = *(char **)this;
  v6 = v4 - *(_QWORD *)this;
  if ( cbSid < v6 )
  {
    v8 = &v5[cbSid];
  }
  else
  {
    if ( cbSid <= v6 )
      goto LABEL_7;
    if ( (unsigned __int64)cbSid > *((_QWORD *)this + 2) - (_QWORD)v5 )
    {
      std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(this, cbSid);
      goto LABEL_7;
    }
    v10 = cbSid - v6;
    memset_0(*((void **)this + 1), 0, v10);
    v8 = (char *)(v10 + v4);
  }
  *((_QWORD *)this + 1) = v8;
LABEL_7:
  if ( !CreateWellKnownSid(WinLocalServiceSid, 0, *(PSID *)this, &cbSid) )
    OSException::ThrowLastError();
  return this;
}

```

## disassembly

```asm
0x18012da30  mov     [rsp+cbSid], edx
0x18012da34  mov     [rsp+arg_0], rcx
0x18012da39  push    rbx
0x18012da3a  push    rsi
0x18012da3b  push    rdi
0x18012da3c  sub     rsp, 20h
0x18012da40  mov     rbx, rcx
0x18012da43  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18012da48  nop
0x18012da49  mov     [rsp+38h+cbSid], 0
0x18012da51  lea     r9, [rsp+38h+cbSid]; cbSid
0x18012da56  xor     r8d, r8d; pSid
0x18012da59  xor     edx, edx; DomainSid
0x18012da5b  lea     ecx, [rdx+17h]; WellKnownSidType
0x18012da5e  call    cs:__imp_CreateWellKnownSid
0x18012da64  test    eax, eax
0x18012da66  jnz     short loc_18012DA73
0x18012da68  call    cs:__imp_GetLastError
0x18012da6e  cmp     eax, 7Ah ; 'z'
0x18012da71  jnz     short loc_18012DACD
0x18012da73  mov     edi, [rsp+38h+cbSid]
0x18012da77  mov     rsi, [rbx+8]
0x18012da7b  mov     rdx, [rbx]
0x18012da7e  mov     rcx, rsi
0x18012da81  sub     rcx, rdx
0x18012da84  cmp     rdi, rcx
0x18012da87  jb      short loc_18012DAC3
0x18012da89  jbe     short loc_18012DAA1
0x18012da8b  mov     rax, [rbx+10h]
0x18012da8f  sub     rax, rdx
0x18012da92  cmp     rdi, rax
0x18012da95  jbe     short loc_18012DB01
0x18012da97  mov     edx, edi
0x18012da99  mov     rcx, rbx
0x18012da9c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<char>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18012daa1  lea     r9, [rsp+38h+cbSid]; cbSid
0x18012daa6  mov     r8, [rbx]; pSid
0x18012daa9  xor     edx, edx; DomainSid
0x18012daab  lea     ecx, [rdx+17h]; WellKnownSidType
0x18012daae  call    cs:__imp_CreateWellKnownSid
0x18012dab4  test    eax, eax
0x18012dab6  jz      short loc_18012DB17
0x18012dab8  mov     rax, rbx
0x18012dabb  add     rsp, 20h
0x18012dabf  pop     rdi
0x18012dac0  pop     rsi
0x18012dac1  pop     rbx
0x18012dac2  retn
0x18012dac3  lea     rax, [rdx+rdi]
0x18012dac7  mov     [rbx+8], rax
0x18012dacb  jmp     short loc_18012DAA1
0x18012dacd  test    eax, eax
0x18012dacf  jg      short loc_18012DAF6
0x18012dad1  mov     edx, eax; int
0x18012dad3  mov     r8d, eax; unsigned int
0x18012dad6  lea     rcx, [rsp+38h+arg_10]; this
0x18012dadb  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18012dae0  mov     edx, 444953h
0x18012dae5  mov     r8d, 28h ; '('
0x18012daeb  lea     rcx, [rsp+38h+arg_10]
0x18012daf0  call    ??$LogAndThrow@VOSException@@@@YAXAEBVOSException@@VEventTag@@I@Z; LogAndThrow<OSException>(OSException const &,EventTag,uint)
0x18012daf6  movzx   edx, ax
0x18012daf9  or      edx, 80070000h
0x18012daff  jmp     short loc_18012DAD3
0x18012db01  sub     rdi, rcx
0x18012db04  mov     r8, rdi; Size
0x18012db07  xor     edx, edx; Val
0x18012db09  mov     rcx, rsi; void *
0x18012db0c  call    memset_0
0x18012db11  lea     rax, [rdi+rsi]
0x18012db15  jmp     short loc_18012DAC7
0x18012db17  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
