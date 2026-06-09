# LsaDbpAdtTrustedDomainRem(ushort,_UNICODE_STRING *,void *,void *,_LUID *)

- ea: `0x1800345c0`
- end: `0x180034764`
- name: `?LsaDbpAdtTrustedDomainRem@@YAJGPEAU_UNICODE_STRING@@PEAX1PEAU_LUID@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(unsigned __int16, struct _UNICODE_STRING *, void *, void *, struct _LUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013cbc`
- `0x1800159b0`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x180002338`
- `0x1800345c0`

## import_xrefs

- `LSASRV!LsapFreeLsaHeap` at `0x18003472f`
- `LSASRV!LsapFreeLsaHeap` at `0x18003472f`
- `LSASRV!LsapAdtWriteLog` at `0x180034717`
- `LSASRV!LsapAdtWriteLog` at `0x180034717`
- `LSASRV!LsapAuditFailed` at `0x18003473b`
- `LSASRV!LsapAuditFailed` at `0x18003473b`
- `LSASRV!LsapQueryClientInfo` at `0x180034647`
- `LSASRV!LsapQueryClientInfo` at `0x180034647`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180034680`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x180034680`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180034707`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtInitParametersArray` at `0x180034707`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedDomainRem(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        void *a3,
        void *a4,
        struct _LUID *a5)
{
  __int64 v9; // rdx
  void **v10; // rcx
  __int64 v11; // r8
  int v12; // ebx
  int v14; // [rsp+80h] [rbp-80h] BYREF
  void **v15; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v16[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v17[1056]; // [rsp+A0h] [rbp-60h] BYREF

  v16[0] = 0;
  v15 = 0;
  memset_0(v17, 0, 0x418u);
  LOBYTE(v14) = 0;
  if ( a2 && a2->MaximumLength < a2->Length )
  {
    v12 = -1073741811;
LABEL_17:
    LsapAuditFailed((unsigned int)v12);
    return (unsigned int)v12;
  }
  v12 = 0;
  if ( !a4 )
  {
    v12 = LsapQueryClientInfo(&v15, v16);
    if ( v12 < 0 )
      goto LABEL_14;
    v10 = v15;
    a5 = (struct _LUID *)v16;
    a4 = *v15;
  }
  if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v10, v9, v11)
    || (v12 = LsapAdtAuditingEnabledByLogonId(141, a5, 8, &v14), v12 >= 0) )
  {
    if ( (_BYTE)v14 )
    {
      if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent() )
      {
        v12 = ((__int64 (__fastcall *)(_BYTE *, __int64, __int64, __int64, __int16, __int16, int, void *, int, struct _UNICODE_STRING *, int, _DWORD, int, void *, int, _QWORD, int, void **, _DWORD, _QWORD))LsapAdtInitParametersArray)(
                v17,
                6,
                4707,
                141,
                8,
                5,
                4,
                a4,
                1,
                &LsaDbpSubsystemName,
                1,
                (_DWORD)a2,
                4,
                a3,
                5,
                *a5,
                v14,
                v15,
                v16[0],
                v16[1]);
        if ( v12 >= 0 )
          v12 = LsapAdtWriteLog(v17);
      }
      else
      {
        v12 = -1073741822;
      }
    }
  }
LABEL_14:
  if ( v15 )
    LsapFreeLsaHeap(v15, v9, v11);
  if ( v12 < 0 )
    goto LABEL_17;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800345c0  push    rbp
0x1800345c2  push    rbx
0x1800345c3  push    rsi
0x1800345c4  push    rdi
0x1800345c5  push    r13
0x1800345c7  push    r14
0x1800345c9  push    r15
0x1800345cb  lea     rbp, [rsp-3D0h]
0x1800345d3  sub     rsp, 4D0h
0x1800345da  mov     rax, cs:__security_cookie
0x1800345e1  xor     rax, rsp
0x1800345e4  mov     [rbp+400h+var_40], rax
0x1800345eb  mov     r14, [rbp+400h+arg_20]
0x1800345f2  lea     rcx, [rbp+400h+var_460]; void *
0x1800345f6  mov     r15, r8
0x1800345f9  mov     [rbp+400h+var_470], 0
0x180034601  mov     rdi, rdx
0x180034604  mov     [rbp+400h+var_478], 0
0x18003460c  xor     edx, edx; Val
0x18003460e  mov     r8d, 418h; Size
0x180034614  mov     rsi, r9
0x180034617  call    memset_0
0x18003461c  mov     byte ptr [rbp+400h+var_480], 0
0x180034620  test    rdi, rdi
0x180034623  jz      short loc_180034638
0x180034625  movzx   eax, word ptr [rdi]
0x180034628  cmp     [rdi+2], ax
0x18003462c  jnb     short loc_180034638
0x18003462e  mov     ebx, 0C000000Dh
0x180034633  jmp     loc_180034739
0x180034638  xor     ebx, ebx
0x18003463a  test    rsi, rsi
0x18003463d  jnz     short loc_180034662
0x18003463f  lea     rdx, [rbp+400h+var_470]
0x180034643  lea     rcx, [rbp+400h+var_478]
0x180034647  call    cs:__imp_LsapQueryClientInfo
0x18003464d  mov     ebx, eax
0x18003464f  test    eax, eax
0x180034651  js      loc_180034726
0x180034657  mov     rcx, [rbp+400h+var_478]
0x18003465b  lea     r14, [rbp+400h+var_470]
0x18003465f  mov     rsi, [rcx]
0x180034662  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x180034667  mov     r13d, 8
0x18003466d  test    al, al
0x18003466f  jz      short loc_180034690
0x180034671  lea     r9, [rbp+400h+var_480]
0x180034675  mov     r8d, r13d
0x180034678  mov     rdx, r14
0x18003467b  mov     ecx, 8Dh
0x180034680  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x180034686  mov     ebx, eax
0x180034688  test    eax, eax
0x18003468a  js      loc_180034726
0x180034690  cmp     byte ptr [rbp+400h+var_480], 0
0x180034694  jz      loc_180034726
0x18003469a  call    IsLsapAdtInitParametersArrayPresent
0x18003469f  test    al, al
0x1800346a1  jz      short loc_180034721
0x1800346a3  mov     rax, [r14]
0x1800346a6  mov     r8d, 5
0x1800346ac  mov     [rsp+500h+var_488], rax
0x1800346b1  mov     r9d, 8Dh
0x1800346b7  mov     [rsp+500h+var_490], r8d
0x1800346bc  lea     rax, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x1800346c3  mov     [rsp+500h+var_498], r15
0x1800346c8  lea     edx, [r8-1]
0x1800346cc  mov     [rsp+500h+var_4A0], edx
0x1800346d0  lea     ecx, [rdx-3]
0x1800346d3  mov     [rsp+500h+var_4A8], rdi
0x1800346d8  mov     [rsp+500h+var_4B0], ecx
0x1800346dc  mov     [rsp+500h+var_4B8], rax
0x1800346e1  mov     [rsp+500h+var_4C0], ecx
0x1800346e5  mov     [rsp+500h+var_4C8], rsi
0x1800346ea  mov     [rsp+500h+var_4D0], edx
0x1800346ee  lea     edx, [rcx+5]
0x1800346f1  mov     [rsp+500h+var_4D8], r8w
0x1800346f7  lea     rcx, [rbp+400h+var_460]
0x1800346fb  mov     r8d, 1263h
0x180034701  mov     [rsp+500h+var_4E0], r13w
0x180034707  call    cs:__imp_LsapAdtInitParametersArray
0x18003470d  mov     ebx, eax
0x18003470f  test    eax, eax
0x180034711  js      short loc_180034726
0x180034713  lea     rcx, [rbp+400h+var_460]
0x180034717  call    cs:__imp_LsapAdtWriteLog
0x18003471d  mov     ebx, eax
0x18003471f  jmp     short loc_180034726
0x180034721  mov     ebx, 0C0000002h
0x180034726  mov     rcx, [rbp+400h+var_478]
0x18003472a  test    rcx, rcx
0x18003472d  jz      short loc_180034735
0x18003472f  call    cs:__imp_LsapFreeLsaHeap
0x180034735  test    ebx, ebx
0x180034737  jns     short loc_180034741
0x180034739  mov     ecx, ebx
0x18003473b  call    cs:__imp_LsapAuditFailed
0x180034741  mov     eax, ebx
0x180034743  mov     rcx, [rbp+400h+var_40]
0x18003474a  xor     rcx, rsp; StackCookie
0x18003474d  call    __security_check_cookie
0x180034752  add     rsp, 4D0h
0x180034759  pop     r15
0x18003475b  pop     r14
0x18003475d  pop     r13
0x18003475f  pop     rdi
0x180034760  pop     rsi
0x180034761  pop     rbx
0x180034762  pop     rbp
0x180034763  retn
```
