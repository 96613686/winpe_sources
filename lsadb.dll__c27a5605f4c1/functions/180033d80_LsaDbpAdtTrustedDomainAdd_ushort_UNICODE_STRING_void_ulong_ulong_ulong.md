# LsaDbpAdtTrustedDomainAdd(ushort,_UNICODE_STRING *,void *,ulong,ulong,ulong)

- ea: `0x180033d80`
- end: `0x180033f7a`
- name: `?LsaDbpAdtTrustedDomainAdd@@YAJGPEAU_UNICODE_STRING@@PEAXKKK@Z`
- size: `506`
- prototype: `__int64 __fastcall(unsigned __int16, struct _UNICODE_STRING *, void *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a2bc`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x180002338`
- `0x180033d80`

## import_xrefs

- `LSASRV!LsapFreeLsaHeap` at `0x180033f45`
- `LSASRV!LsapFreeLsaHeap` at `0x180033f45`
- `LSASRV!LsapAdtWriteLog` at `0x180033f2d`
- `LSASRV!LsapAdtWriteLog` at `0x180033f2d`
- `LSASRV!LsapAuditFailed` at `0x180033f51`
- `LSASRV!LsapAuditFailed` at `0x180033f51`
- `LSASRV!LsapQueryClientInfo` at `0x180033df9`
- `LSASRV!LsapQueryClientInfo` at `0x180033df9`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180033e2c`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180033e2c`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180033f1d`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180033f1d`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedDomainAdd(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        void *a3,
        int a4,
        unsigned int a5,
        unsigned int a6)
{
  int inited; // ebx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int16 v14; // [rsp+20h] [rbp-120h]
  __int16 v15; // [rsp+28h] [rbp-118h]
  int v16; // [rsp+88h] [rbp-B8h]
  int v19; // [rsp+B8h] [rbp-88h]
  int v20; // [rsp+C0h] [rbp-80h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-78h] BYREF
  _QWORD *v22; // [rsp+D0h] [rbp-70h] BYREF
  _BYTE v23[1056]; // [rsp+E0h] [rbp-60h] BYREF

  v21 = 0;
  v22 = 0;
  memset_0(v23, 0, 0x418u);
  LOBYTE(v20) = 0;
  if ( a2 && a2->MaximumLength < a2->Length )
  {
    inited = -1073741811;
LABEL_15:
    LsapAuditFailed((unsigned int)inited);
    return (unsigned int)inited;
  }
  inited = LsapQueryClientInfo(&v22, &v21);
  if ( inited >= 0 )
  {
    if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v11, v10, v12)
      || (inited = LsapAdtAuditingEnabledByLogonId(141, &v21, 8, &v20), inited >= 0) )
    {
      if ( (_BYTE)v20 )
      {
        if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent() )
        {
          v19 = 1796 - ((a6 & 4) != 0);
          v16 = a4;
          v15 = 9;
          v14 = 8;
          inited = LsapAdtInitParametersArray(
                     v23,
                     6,
                     4706,
                     141,
                     v14,
                     v15,
                     4,
                     *v22,
                     1,
                     &LsaDbpSubsystemName,
                     1,
                     (_DWORD)a2,
                     4,
                     a3,
                     5,
                     v21,
                     27,
                     v16,
                     27,
                     a5,
                     27,
                     a6,
                     21,
                     v19,
                     v20,
                     v21);
          if ( inited >= 0 )
            inited = LsapAdtWriteLog(v23);
        }
        else
        {
          inited = -1073741822;
        }
      }
    }
  }
  if ( v22 )
    LsapFreeLsaHeap(v22, v10, v12);
  if ( inited < 0 )
    goto LABEL_15;
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180033d80  push    rbp
0x180033d82  push    rbx
0x180033d83  push    rsi
0x180033d84  push    rdi
0x180033d85  push    r12
0x180033d87  push    r13
0x180033d89  push    r14
0x180033d8b  lea     rbp, [rsp-3D0h]
0x180033d93  sub     rsp, 510h
0x180033d9a  mov     rax, cs:__security_cookie
0x180033da1  xor     rax, rsp
0x180033da4  mov     [rbp+400h+var_40], rax
0x180033dab  mov     rsi, r8
0x180033dae  mov     [rbp+400h+var_478], 0
0x180033db6  mov     rdi, rdx
0x180033db9  mov     [rbp+400h+var_470], 0
0x180033dc1  xor     edx, edx; Val
0x180033dc3  lea     rcx, [rbp+400h+var_460]; void *
0x180033dc7  mov     r8d, 418h; Size
0x180033dcd  mov     r14d, r9d
0x180033dd0  call    memset_0
0x180033dd5  mov     byte ptr [rbp+400h+var_480], 0
0x180033dd9  test    rdi, rdi
0x180033ddc  jz      short loc_180033DF1
0x180033dde  movzx   eax, word ptr [rdi]
0x180033de1  cmp     [rdi+2], ax
0x180033de5  jnb     short loc_180033DF1
0x180033de7  mov     ebx, 0C000000Dh
0x180033dec  jmp     loc_180033F4F
0x180033df1  lea     rdx, [rbp+400h+var_478]
0x180033df5  lea     rcx, [rbp+400h+var_470]
0x180033df9  call    cs:__imp_LsapQueryClientInfo
0x180033dff  mov     ebx, eax
0x180033e01  test    eax, eax
0x180033e03  js      loc_180033F3C
0x180033e09  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180033e0e  mov     r12d, 8
0x180033e14  mov     r13d, 8Dh
0x180033e1a  test    al, al
0x180033e1c  jz      short loc_180033E3C
0x180033e1e  lea     r9, [rbp+400h+var_480]
0x180033e22  mov     r8d, r12d
0x180033e25  lea     rdx, [rbp+400h+var_478]
0x180033e29  mov     ecx, r13d
0x180033e2c  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180033e32  mov     ebx, eax
0x180033e34  test    eax, eax
0x180033e36  js      loc_180033F3C
0x180033e3c  cmp     byte ptr [rbp+400h+var_480], 0
0x180033e40  jz      loc_180033F3C
0x180033e46  call    IsLsapAdtInitParametersArrayPresent
0x180033e4b  test    al, al
0x180033e4d  jz      loc_180033F37
0x180033e53  mov     edx, [rbp+400h+arg_28]
0x180033e59  mov     r9d, 4
0x180033e5f  mov     eax, edx
0x180033e61  mov     r8d, 1262h
0x180033e67  and     al, r9b
0x180033e6a  neg     al
0x180033e6c  mov     eax, [rbp+400h+arg_20]
0x180033e72  sbb     ecx, ecx
0x180033e74  add     ecx, 704h
0x180033e7a  mov     [rsp+540h+var_488], ecx
0x180033e81  lea     ecx, [r9+17h]
0x180033e85  mov     [rsp+540h+var_490], 15h
0x180033e90  mov     [rsp+540h+var_498], edx
0x180033e97  mov     edx, 6
0x180033e9c  mov     [rsp+540h+var_4A0], ecx
0x180033ea3  mov     [rsp+540h+var_4A8], eax
0x180033eaa  mov     rax, [rbp+400h+var_478]
0x180033eae  mov     [rsp+540h+var_4B0], ecx
0x180033eb5  mov     [rsp+540h+var_4B8], r14d
0x180033ebd  mov     [rsp+540h+var_4C0], ecx
0x180033ec4  lea     ecx, [r9-3]
0x180033ec8  mov     [rsp+540h+var_4C8], rax
0x180033ecd  lea     rax, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x180033ed4  mov     [rsp+540h+var_4D0], 5
0x180033edc  mov     [rsp+540h+var_4D8], rsi
0x180033ee1  mov     [rsp+540h+var_4E0], r9d
0x180033ee6  mov     [rsp+540h+var_4E8], rdi
0x180033eeb  mov     [rsp+540h+var_4F0], ecx
0x180033eef  mov     [rsp+540h+var_4F8], rax
0x180033ef4  mov     rax, [rbp+400h+var_470]
0x180033ef8  mov     [rsp+540h+var_500], ecx
0x180033efc  mov     rcx, [rax]
0x180033eff  mov     [rsp+540h+var_508], rcx
0x180033f04  lea     rcx, [rbp+400h+var_460]
0x180033f08  mov     [rsp+540h+var_510], r9d
0x180033f0d  mov     r9d, r13d
0x180033f10  mov     [rsp+540h+var_518], 9
0x180033f17  mov     [rsp+540h+var_520], r12w
0x180033f1d  call    cs:__imp_LsapAdtInitParametersArray
0x180033f23  mov     ebx, eax
0x180033f25  test    eax, eax
0x180033f27  js      short loc_180033F3C
0x180033f29  lea     rcx, [rbp+400h+var_460]
0x180033f2d  call    cs:__imp_LsapAdtWriteLog
0x180033f33  mov     ebx, eax
0x180033f35  jmp     short loc_180033F3C
0x180033f37  mov     ebx, 0C0000002h
0x180033f3c  mov     rcx, [rbp+400h+var_470]
0x180033f40  test    rcx, rcx
0x180033f43  jz      short loc_180033F4B
0x180033f45  call    cs:__imp_LsapFreeLsaHeap
0x180033f4b  test    ebx, ebx
0x180033f4d  jns     short loc_180033F57
0x180033f4f  mov     ecx, ebx
0x180033f51  call    cs:__imp_LsapAuditFailed
0x180033f57  mov     eax, ebx
0x180033f59  mov     rcx, [rbp+400h+var_40]
0x180033f60  xor     rcx, rsp; StackCookie
0x180033f63  call    __security_check_cookie
0x180033f68  add     rsp, 510h
0x180033f6f  pop     r14
0x180033f71  pop     r13
0x180033f73  pop     r12
0x180033f75  pop     rdi
0x180033f76  pop     rsi
0x180033f77  pop     rbx
0x180033f78  pop     rbp
0x180033f79  retn
```
