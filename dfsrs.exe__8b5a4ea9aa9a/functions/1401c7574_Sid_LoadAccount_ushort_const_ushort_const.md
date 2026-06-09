# Sid::LoadAccount(ushort const *,ushort const *)

- ea: `0x1401c7574`
- end: `0x1401c77a0`
- name: `?LoadAccount@Sid@@QEAAPEAVFrsStatus@@PEBG0@Z`
- size: `556`
- prototype: `struct FrsStatus *__fastcall(Sid *__hidden this, LPCWSTR lpAccountName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1401c636c`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x1400046cc`
- `0x140010680`
- `0x140028eec`
- `0x1401af7c0`
- `0x1401b9494`
- `0x1401c6770`
- `0x1401c7574`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1401c7634`
- `KERNEL32!GetLastError` at `0x1401c7634`
- `KERNEL32!GetCurrentThreadId` at `0x1401c75ac`
- `KERNEL32!GetCurrentThreadId` at `0x1401c764f`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7730`
- `KERNEL32!GetCurrentThreadId` at `0x1401c75ac`
- `KERNEL32!GetCurrentThreadId` at `0x1401c764f`
- `KERNEL32!GetCurrentThreadId` at `0x1401c7730`
- `ADVAPI32!LookupAccountNameW` at `0x1401c7620`
- `ADVAPI32!LookupAccountNameW` at `0x1401c76c1`
- `ADVAPI32!LookupAccountNameW` at `0x1401c7620`
- `ADVAPI32!LookupAccountNameW` at `0x1401c76c1`
- `ADVAPI32!CopySid` at `0x1401c76e3`
- `ADVAPI32!CopySid` at `0x1401c76e3`

## string_xrefs

- `0x1401c7768`: `base\fs\remotefs\frs\src\util\securityutil.cpp`
- `0x1401c7753`: `Sid::LoadAccount`

## pseudocode

```c
struct FrsStatus *__fastcall Sid::LoadAccount(
        enum _SID_NAME_USE *this,
        LPCWSTR lpAccountName,
        const unsigned __int16 *a3)
{
  unsigned int *v3; // rbp
  DWORD CurrentThreadId; // eax
  __int64 v7; // rcx
  void *ReferencedDomainName; // rsi
  DWORD v10; // eax
  __int64 v11; // rcx
  size_t v12; // rbx
  DWORD v13; // ecx
  DWORD v14; // eax
  __int64 v15; // rcx
  DWORD v16; // [rsp+70h] [rbp+0h] BYREF

  v3 = (unsigned int *)((unsigned __int64)&v16 & 0xFFFFFFFFFFFFFFE0uLL);
  if ( !lpAccountName )
  {
    CurrentThreadId = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v7,
                                 87,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::LoadAccount",
                                 170,
                                 CurrentThreadId,
                                 0);
  }
  ReferencedDomainName = operator new(0x80u);
  memset_0(ReferencedDomainName, 0, 0x80u);
  *(_DWORD *)(((unsigned __int64)&v16 & 0xFFFFFFFFFFFFFFE0uLL) + 4) = 68;
  *v3 = 64;
  if ( !LookupAccountNameW(
          0,
          lpAccountName,
          v3 + 8,
          v3 + 1,
          (LPWSTR)ReferencedDomainName,
          (LPDWORD)((unsigned __int64)&v16 & 0xFFFFFFFFFFFFFFE0uLL),
          this + 20) )
  {
    if ( GetLastError() != 122 )
      goto LABEL_12;
    if ( *(_DWORD *)(((unsigned __int64)&v16 & 0xFFFFFFFFFFFFFFE0uLL) + 4) > 0x44u )
    {
      v10 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v11,
                                   122,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                   "Sid::LoadAccount",
                                   196,
                                   v10,
                                   0);
    }
    if ( *v3 > 0x40 )
    {
      operator delete[](ReferencedDomainName);
      v12 = 2LL * *v3;
      ReferencedDomainName = operator new(v12);
      memset_0(ReferencedDomainName, 0, v12);
    }
    if ( !LookupAccountNameW(
            0,
            lpAccountName,
            v3 + 8,
            v3 + 1,
            (LPWSTR)ReferencedDomainName,
            (LPDWORD)((unsigned __int64)&v16 & 0xFFFFFFFFFFFFFFE0uLL),
            this + 20) )
      goto LABEL_12;
  }
  v13 = *(_DWORD *)(((unsigned __int64)&v16 & 0xFFFFFFFFFFFFFFE0uLL) + 4);
  *((_DWORD *)this + 19) = 1;
  if ( CopySid(v13, this + 2, v3 + 8) )
  {
    FrsStringImpl<unsigned short,char>::Set(this + 24, ReferencedDomainName);
    FrsStringImpl<unsigned short,char>::Set(this + 22, lpAccountName);
    FrsStringImpl<unsigned short,char>::SetEmpty(this + 26);
    operator delete[](ReferencedDomainName);
    return 0;
  }
  else
  {
LABEL_12:
    Sid::Clear((Sid *)this);
    operator delete[](ReferencedDomainName);
    v14 = GetCurrentThreadId();
    return (struct FrsStatus *)FrsStatusList::PushNewError(
                                 v15,
                                 31,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\util\\securityutil.cpp",
                                 "Sid::LoadAccount",
                                 242,
                                 v14,
                                 0);
  }
}

```

## disassembly

```asm
0x1401c7574  mov     [rsp-8+arg_10], rbx
0x1401c7579  push    rbp
0x1401c757a  push    rsi
0x1401c757b  push    rdi
0x1401c757c  push    r12
0x1401c757e  push    r14
0x1401c7580  sub     rsp, 100h
0x1401c7587  lea     rbp, [rsp+70h]
0x1401c758c  and     rbp, 0FFFFFFFFFFFFFFE0h
0x1401c7590  mov     rax, cs:__security_cookie
0x1401c7597  xor     rax, rsp
0x1401c759a  mov     [rbp+0B0h+var_30], rax
0x1401c75a1  mov     r14, rdx
0x1401c75a4  mov     rdi, rcx
0x1401c75a7  test    rdx, rdx
0x1401c75aa  jnz     short loc_1401C75D2
0x1401c75ac  call    cs:__imp_GetCurrentThreadId
0x1401c75b3  nop     dword ptr [rax+rax+00h]
0x1401c75b8  and     [rsp+120h+var_E0], r14
0x1401c75bd  lea     edx, [r14+57h]
0x1401c75c1  mov     [rsp+120h+var_E8], eax
0x1401c75c5  mov     dword ptr [rsp+120h+peUse], 0AAh
0x1401c75cd  jmp     loc_1401C7753
0x1401c75d2  mov     ebx, 80h
0x1401c75d7  mov     ecx, ebx; Size
0x1401c75d9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401c75de  mov     r8d, ebx; Size
0x1401c75e1  xor     edx, edx; Val
0x1401c75e3  mov     rcx, rax; void *
0x1401c75e6  mov     rsi, rax
0x1401c75e9  call    memset_0
0x1401c75ee  lea     rax, [rbp+0B0h+var_B0]
0x1401c75f2  mov     [rbp+0B0h+cbSid], 44h ; 'D'
0x1401c75f9  lea     r12, [rdi+50h]
0x1401c75fd  mov     [rbp+0B0h+var_B0], 40h ; '@'
0x1401c7604  mov     [rsp+120h+peUse], r12; peUse
0x1401c7609  lea     r9, [rbp+0B0h+cbSid]; cbSid
0x1401c760d  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1401c7612  lea     r8, [rbp+0B0h+Sid]; Sid
0x1401c7616  mov     rdx, r14; lpAccountName
0x1401c7619  mov     [rsp+120h+ReferencedDomainName], rsi; ReferencedDomainName
0x1401c761e  xor     ecx, ecx; lpSystemName
0x1401c7620  call    cs:__imp_LookupAccountNameW
0x1401c7627  nop     dword ptr [rax+rax+00h]
0x1401c762c  test    eax, eax
0x1401c762e  jnz     loc_1401C76D1
0x1401c7634  call    cs:__imp_GetLastError
0x1401c763b  nop     dword ptr [rax+rax+00h]
0x1401c7640  cmp     eax, 7Ah ; 'z'
0x1401c7643  jnz     loc_1401C7720
0x1401c7649  cmp     [rbp+0B0h+cbSid], 44h ; 'D'
0x1401c764d  jbe     short loc_1401C7675
0x1401c764f  call    cs:__imp_GetCurrentThreadId
0x1401c7656  nop     dword ptr [rax+rax+00h]
0x1401c765b  and     [rsp+120h+var_E0], 0
0x1401c7661  lea     edx, [rbx-6]
0x1401c7664  mov     [rsp+120h+var_E8], eax
0x1401c7668  mov     dword ptr [rsp+120h+peUse], 0C4h
0x1401c7670  jmp     loc_1401C7753
0x1401c7675  cmp     [rbp+0B0h+var_B0], 40h ; '@'
0x1401c7679  jbe     short loc_1401C76A1
0x1401c767b  mov     rcx, rsi; Block
0x1401c767e  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c7683  mov     ebx, [rbp+0B0h+var_B0]
0x1401c7686  add     rbx, rbx
0x1401c7689  mov     rcx, rbx; Size
0x1401c768c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401c7691  mov     r8, rbx; Size
0x1401c7694  xor     edx, edx; Val
0x1401c7696  mov     rcx, rax; void *
0x1401c7699  mov     rsi, rax
0x1401c769c  call    memset_0
0x1401c76a1  lea     rax, [rbp+0B0h+var_B0]
0x1401c76a5  mov     [rsp+120h+peUse], r12; peUse
0x1401c76aa  mov     [rsp+120h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1401c76af  lea     r9, [rbp+0B0h+cbSid]; cbSid
0x1401c76b3  lea     r8, [rbp+0B0h+Sid]; Sid
0x1401c76b7  mov     [rsp+120h+ReferencedDomainName], rsi; ReferencedDomainName
0x1401c76bc  mov     rdx, r14; lpAccountName
0x1401c76bf  xor     ecx, ecx; lpSystemName
0x1401c76c1  call    cs:__imp_LookupAccountNameW
0x1401c76c8  nop     dword ptr [rax+rax+00h]
0x1401c76cd  test    eax, eax
0x1401c76cf  jz      short loc_1401C7720
0x1401c76d1  mov     ecx, [rbp+0B0h+cbSid]; nDestinationSidLength
0x1401c76d4  lea     rdx, [rdi+8]; pDestinationSid
0x1401c76d8  lea     r8, [rbp+0B0h+Sid]; pSourceSid
0x1401c76dc  mov     dword ptr [rdi+4Ch], 1
0x1401c76e3  call    cs:__imp_CopySid
0x1401c76ea  nop     dword ptr [rax+rax+00h]
0x1401c76ef  test    eax, eax
0x1401c76f1  jz      short loc_1401C7720
0x1401c76f3  lea     rcx, [rdi+60h]
0x1401c76f7  mov     rdx, rsi
0x1401c76fa  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401c76ff  lea     rcx, [rdi+58h]
0x1401c7703  mov     rdx, r14
0x1401c7706  call    ?Set@?$FrsStringImpl@GD@@QEAA_NPEBG@Z; FrsStringImpl<ushort,char>::Set(ushort const *)
0x1401c770b  lea     rcx, [rdi+68h]
0x1401c770f  call    ?SetEmpty@?$FrsStringImpl@GD@@QEAAXXZ; FrsStringImpl<ushort,char>::SetEmpty(void)
0x1401c7714  mov     rcx, rsi; Block
0x1401c7717  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c771c  xor     eax, eax
0x1401c771e  jmp     short loc_1401C7779
0x1401c7720  mov     rcx, rdi; this
0x1401c7723  call    ?Clear@Sid@@IEAAXXZ; Sid::Clear(void)
0x1401c7728  mov     rcx, rsi; Block
0x1401c772b  call    ??_V@YAXPEAXAEBUZeroFill@@@Z; operator delete[](void *,ZeroFill const &)
0x1401c7730  call    cs:__imp_GetCurrentThreadId
0x1401c7737  nop     dword ptr [rax+rax+00h]
0x1401c773c  and     [rsp+120h+var_E0], 0
0x1401c7742  mov     edx, 1Fh
0x1401c7747  mov     [rsp+120h+var_E8], eax
0x1401c774b  mov     dword ptr [rsp+120h+peUse], 0F2h
0x1401c7753  lea     rax, aSidLoadaccount; "Sid::LoadAccount"
0x1401c775a  mov     r9d, 1
0x1401c7760  mov     [rsp+120h+cchReferencedDomainName], rax
0x1401c7765  xor     r8d, r8d
0x1401c7768  lea     rax, aBaseFsRemotefs_41; "base\\fs\\remotefs\\frs\\src\\util\\sec"...
0x1401c776f  mov     [rsp+120h+ReferencedDomainName], rax
0x1401c7774  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401c7779  mov     rcx, [rbp+0B0h+var_30]
0x1401c7780  xor     rcx, rsp; StackCookie
0x1401c7783  call    __security_check_cookie
0x1401c7788  mov     rbx, [rsp+120h+arg_10]
0x1401c7790  add     rsp, 100h
0x1401c7797  pop     r14
0x1401c7799  pop     r12
0x1401c779b  pop     rdi
0x1401c779c  pop     rsi
0x1401c779d  pop     rbp
0x1401c779e  retn
```
