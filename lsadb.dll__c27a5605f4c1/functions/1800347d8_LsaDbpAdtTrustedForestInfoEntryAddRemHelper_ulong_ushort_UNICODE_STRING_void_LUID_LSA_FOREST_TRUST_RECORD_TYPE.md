# LsaDbpAdtTrustedForestInfoEntryAddRemHelper(ulong,ushort,_UNICODE_STRING *,void *,_LUID *,LSA_FOREST_TRUST_RECORD_TYPE,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,void *)

- ea: `0x1800347d8`
- end: `0x180034a56`
- name: `?LsaDbpAdtTrustedForestInfoEntryAddRemHelper@@YAJKGPEAU_UNICODE_STRING@@PEAXPEAU_LUID@@W4LSA_FOREST_TRUST_RECORD_TYPE@@K0001@Z`
- size: `638`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16, struct _UNICODE_STRING *, void *, struct _LUID *, enum LSA_FOREST_TRUST_RECORD_TYPE, unsigned int, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034770`
- `0x180034e80`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x180002338`
- `0x1800347d8`

## import_xrefs

- `LSASRV!LsapFreeLsaHeap` at `0x180034a18`
- `LSASRV!LsapFreeLsaHeap` at `0x180034a18`
- `LSASRV!LsapAdtWriteLog` at `0x180034a00`
- `LSASRV!LsapAdtWriteLog` at `0x180034a00`
- `LSASRV!LsapAuditFailed` at `0x180034a24`
- `LSASRV!LsapAuditFailed` at `0x180034a24`
- `LSASRV!LsapQueryClientInfo` at `0x1800348a8`
- `LSASRV!LsapQueryClientInfo` at `0x1800348a8`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x1800348d4`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x1800348d4`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x1800349f0`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x1800349f0`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedForestInfoEntryAddRemHelper(
        unsigned int a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        struct _LUID *a5,
        enum LSA_FOREST_TRUST_RECORD_TYPE a6,
        unsigned int a7,
        struct _UNICODE_STRING *a8,
        struct _UNICODE_STRING *a9,
        struct _UNICODE_STRING *a10,
        void *a11)
{
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int16 v19; // [rsp+20h] [rbp-150h]
  __int16 v20; // [rsp+28h] [rbp-148h]
  _BYTE v23[8]; // [rsp+F0h] [rbp-80h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-78h] BYREF
  _QWORD v25[2]; // [rsp+100h] [rbp-70h] BYREF
  struct _LUID *v26; // [rsp+110h] [rbp-60h]
  _BYTE v27[1056]; // [rsp+120h] [rbp-50h] BYREF

  v26 = a5;
  v25[1] = a11;
  v24 = 0;
  v25[0] = 0;
  memset_0(v27, 0, 0x418u);
  v23[0] = 0;
  if ( a3 && a3->MaximumLength < a3->Length
    || a8 && a8->MaximumLength < a8->Length
    || a9 && a9->MaximumLength < a9->Length
    || a10 && a10->MaximumLength < a10->Length )
  {
    v14 = -1073741811;
LABEL_21:
    LsapAuditFailed((unsigned int)v14);
    return (unsigned int)v14;
  }
  v14 = LsapQueryClientInfo(v25, &v24);
  if ( v14 >= 0 )
  {
    if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v16, v15, v17)
      || (v14 = LsapAdtAuditingEnabledByLogonId(141, &v24, 8, v23), v14 >= 0) )
    {
      if ( v23[0] )
      {
        if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent() )
        {
          v20 = 12;
          v19 = 8;
          v14 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _WORD, _WORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))LsapAdtInitParametersArray)(
                  v27,
                  6,
                  a1,
                  141,
                  v19,
                  v20,
                  4,
                  *(_QWORD *)v25[0],
                  1,
                  &LsaDbpSubsystemName,
                  1,
                  (_DWORD)a3,
                  4,
                  a4,
                  14,
                  *v26,
                  27,
                  a6,
                  27,
                  a7,
                  1,
                  a8,
                  1,
                  a9,
                  1,
                  (_DWORD)a10);
          if ( v14 >= 0 )
            v14 = LsapAdtWriteLog(v27);
        }
        else
        {
          v14 = -1073741822;
        }
      }
    }
  }
  if ( v25[0] )
    LsapFreeLsaHeap(v25[0], v15, v17);
  if ( v14 < 0 )
    goto LABEL_21;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800347d8  mov     [rsp-8+arg_8], rbx
0x1800347dd  push    rbp
0x1800347de  push    rsi
0x1800347df  push    rdi
0x1800347e0  push    r12
0x1800347e2  push    r13
0x1800347e4  push    r14
0x1800347e6  push    r15
0x1800347e8  lea     rbp, [rsp-3E0h]
0x1800347f0  sub     rsp, 550h
0x1800347f7  mov     rax, cs:__security_cookie
0x1800347fe  xor     rax, rsp
0x180034801  mov     [rbp+410h+var_40], rax
0x180034808  mov     rax, [rbp+410h+arg_20]
0x18003480f  mov     r15, r8
0x180034812  mov     rdi, [rbp+410h+arg_48]
0x180034819  mov     r12d, ecx
0x18003481c  mov     rsi, [rbp+410h+arg_40]
0x180034823  lea     rcx, [rbp+410h+var_460]; void *
0x180034827  mov     r14, [rbp+410h+arg_38]
0x18003482e  xor     ebx, ebx
0x180034830  mov     [rbp+410h+var_470], rax
0x180034834  xor     edx, edx; Val
0x180034836  mov     rax, [rbp+410h+arg_50]
0x18003483d  mov     r8d, 418h; Size
0x180034843  mov     [rbp+410h+var_478], rax
0x180034847  mov     r13, r9
0x18003484a  mov     [rbp+410h+var_488], rbx
0x18003484e  mov     [rbp+410h+var_480], rbx
0x180034852  call    memset_0
0x180034857  mov     [rbp+410h+var_490], bl
0x18003485a  test    r15, r15
0x18003485d  jz      short loc_18003486A
0x18003485f  movzx   eax, word ptr [r15]
0x180034863  cmp     [r15+2], ax
0x180034868  jb      short loc_180034896
0x18003486a  test    r14, r14
0x18003486d  jz      short loc_18003487A
0x18003486f  movzx   eax, word ptr [r14]
0x180034873  cmp     [r14+2], ax
0x180034878  jb      short loc_180034896
0x18003487a  test    rsi, rsi
0x18003487d  jz      short loc_180034888
0x18003487f  movzx   eax, word ptr [rsi]
0x180034882  cmp     [rsi+2], ax
0x180034886  jb      short loc_180034896
0x180034888  test    rdi, rdi
0x18003488b  jz      short loc_1800348A0
0x18003488d  movzx   eax, word ptr [rdi]
0x180034890  cmp     [rdi+2], ax
0x180034894  jnb     short loc_1800348A0
0x180034896  mov     ebx, 0C000000Dh
0x18003489b  jmp     loc_180034A22
0x1800348a0  lea     rdx, [rbp+410h+var_488]
0x1800348a4  lea     rcx, [rbp+410h+var_480]
0x1800348a8  call    cs:__imp_LsapQueryClientInfo
0x1800348ae  mov     ebx, eax
0x1800348b0  test    eax, eax
0x1800348b2  js      loc_180034A0F
0x1800348b8  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x1800348bd  test    al, al
0x1800348bf  jz      short loc_1800348E4
0x1800348c1  lea     r9, [rbp+410h+var_490]
0x1800348c5  mov     r8d, 8
0x1800348cb  lea     rdx, [rbp+410h+var_488]
0x1800348cf  mov     ecx, 8Dh
0x1800348d4  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x1800348da  mov     ebx, eax
0x1800348dc  test    eax, eax
0x1800348de  js      loc_180034A0F
0x1800348e4  cmp     [rbp+410h+var_490], 0
0x1800348e8  jz      loc_180034A0F
0x1800348ee  call    IsLsapAdtInitParametersArrayPresent
0x1800348f3  test    al, al
0x1800348f5  jz      loc_180034A0A
0x1800348fb  mov     rax, [rbp+410h+var_488]
0x1800348ff  mov     r8d, 4
0x180034905  mov     [rsp+580h+var_498], rax
0x18003490d  mov     r9d, 8Dh
0x180034913  mov     rax, [rbp+410h+var_478]
0x180034917  mov     [rsp+580h+var_4A0], 5
0x180034922  mov     [rsp+580h+var_4A8], rax
0x18003492a  lea     edx, [r8-3]
0x18003492e  mov     eax, [rbp+410h+arg_30]
0x180034934  lea     ecx, [rdx+1Ah]
0x180034937  mov     [rsp+580h+var_4B0], r8d
0x18003493f  mov     [rsp+580h+var_4B8], rdi
0x180034947  mov     [rsp+580h+var_4C0], edx
0x18003494e  mov     [rsp+580h+var_4C8], rsi
0x180034956  mov     [rsp+580h+var_4D0], edx
0x18003495d  mov     [rsp+580h+var_4D8], r14
0x180034965  mov     [rsp+580h+var_4E0], edx
0x18003496c  mov     [rsp+580h+var_4E8], eax
0x180034973  mov     eax, [rbp+410h+arg_28]
0x180034979  mov     [rsp+580h+var_4F0], ecx
0x180034980  mov     [rsp+580h+var_4F8], eax
0x180034987  mov     rax, [rbp+410h+var_470]
0x18003498b  mov     [rsp+580h+var_500], ecx
0x180034992  mov     rax, [rax]
0x180034995  mov     [rsp+580h+var_508], rax
0x18003499a  lea     rax, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x1800349a1  mov     [rsp+580h+var_510], 0Eh
0x1800349a9  mov     [rsp+580h+var_518], r13
0x1800349ae  mov     [rsp+580h+var_520], r8d
0x1800349b3  mov     [rsp+580h+var_528], r15
0x1800349b8  mov     [rsp+580h+var_530], edx
0x1800349bc  mov     [rsp+580h+var_538], rax
0x1800349c1  mov     rax, [rbp+410h+var_480]
0x1800349c5  mov     [rsp+580h+var_540], edx
0x1800349c9  mov     edx, 6
0x1800349ce  mov     rcx, [rax]
0x1800349d1  mov     [rsp+580h+var_548], rcx
0x1800349d6  lea     rcx, [rbp+410h+var_460]
0x1800349da  mov     [rsp+580h+var_550], r8d
0x1800349df  mov     r8d, r12d
0x1800349e2  mov     [rsp+580h+var_558], 0Ch
0x1800349e9  mov     [rsp+580h+var_560], 8
0x1800349f0  call    cs:__imp_LsapAdtInitParametersArray
0x1800349f6  mov     ebx, eax
0x1800349f8  test    eax, eax
0x1800349fa  js      short loc_180034A0F
0x1800349fc  lea     rcx, [rbp+410h+var_460]
0x180034a00  call    cs:__imp_LsapAdtWriteLog
0x180034a06  mov     ebx, eax
0x180034a08  jmp     short loc_180034A0F
0x180034a0a  mov     ebx, 0C0000002h
0x180034a0f  mov     rcx, [rbp+410h+var_480]
0x180034a13  test    rcx, rcx
0x180034a16  jz      short loc_180034A1E
0x180034a18  call    cs:__imp_LsapFreeLsaHeap
0x180034a1e  test    ebx, ebx
0x180034a20  jns     short loc_180034A2A
0x180034a22  mov     ecx, ebx
0x180034a24  call    cs:__imp_LsapAuditFailed
0x180034a2a  mov     eax, ebx
0x180034a2c  mov     rcx, [rbp+410h+var_40]
0x180034a33  xor     rcx, rsp; StackCookie
0x180034a36  call    __security_check_cookie
0x180034a3b  mov     rbx, [rsp+580h+arg_8]
0x180034a43  add     rsp, 550h
0x180034a4a  pop     r15
0x180034a4c  pop     r14
0x180034a4e  pop     r13
0x180034a50  pop     r12
0x180034a52  pop     rdi
0x180034a53  pop     rsi
0x180034a54  pop     rbp
0x180034a55  retn
```
