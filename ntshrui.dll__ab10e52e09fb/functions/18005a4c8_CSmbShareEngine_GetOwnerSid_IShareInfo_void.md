# CSmbShareEngine::_GetOwnerSid(IShareInfo *,void * *)

- ea: `0x18005a4c8`
- end: `0x18005a65b`
- name: `?_GetOwnerSid@CSmbShareEngine@@AEAAJPEAUIShareInfo@@PEAPEAX@Z`
- size: `403`
- prototype: `int(CSmbShareEngine *__hidden this, struct IShareInfo *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005c7ac`

## callees

- `0x180009830`
- `0x18000a430`
- `0x18002ad00`
- `0x18005a4c8`
- `0x18005e070`
- `0x1800727d0`
- `0x180078010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005a573`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18005a573`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a5e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005a5e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a617`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a617`

## pseudocode

```c
__int64 __fastcall CSmbShareEngine::_GetOwnerSid(CSmbShareEngine *this, struct IShareInfo *a2, void **a3)
{
  __int64 v3; // rax
  int v5; // ebx
  const unsigned __int16 *v6; // rcx
  PSID v7; // rax
  int CurrentUserSid; // eax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-10h] BYREF
  CSmbShareEngine *bOwnerDefaulted; // [rsp+50h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+58h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+68h] [rbp+38h] BYREF

  bOwnerDefaulted = this;
  v3 = *(_QWORD *)a2;
  pv = 0;
  v5 = (*(__int64 (__fastcall **)(struct IShareInfo *, LPVOID *))(v3 + 64))(a2, &pv);
  if ( v5 < 0 )
    goto LABEL_23;
  v6 = (const unsigned __int16 *)pv;
  if ( pv )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58);
      v6 = (const unsigned __int16 *)pv;
    }
    pSecurityDescriptor = 0;
    v5 = ConvertSDDLToSD(v6, &pSecurityDescriptor);
    if ( v5 >= 0 )
    {
      pOwner = 0;
      LODWORD(bOwnerDefaulted) = 0;
      GetSecurityDescriptorOwner(pSecurityDescriptor, &pOwner, (LPBOOL)&bOwnerDefaulted);
      v7 = pOwner;
      if ( pOwner )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59);
          v7 = pOwner;
        }
        CurrentUserSid = AllocAndCopySid(v7, a3);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60);
        CurrentUserSid = GetCurrentUserSid(a3);
      }
      v5 = CurrentUserSid;
      LocalFree(pSecurityDescriptor);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61);
    v5 = GetCurrentUserSid(a3);
  }
  CoTaskMemFree(pv);
  if ( v5 < 0 )
  {
LABEL_23:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        62,
        WPP_055da27402593bc4c79a5720b75a8198_Traceguids,
        (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005a4c8  mov     [rsp-18h+arg_10], rbx
0x18005a4cd  mov     [rsp-18h+bOwnerDefaulted], rcx
0x18005a4d2  push    rbp
0x18005a4d3  push    rdi
0x18005a4d4  push    r14
0x18005a4d6  mov     rbp, rsp
0x18005a4d9  sub     rsp, 30h
0x18005a4dd  mov     rax, [rdx]
0x18005a4e0  mov     rcx, rdx
0x18005a4e3  lea     rdx, [rbp+pv]
0x18005a4e7  mov     [rbp+pv], 0
0x18005a4ef  mov     rdi, r8
0x18005a4f2  mov     rax, [rax+40h]
0x18005a4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4fb  lea     r14, WPP_GLOBAL_Control
0x18005a502  mov     ebx, eax
0x18005a504  test    eax, eax
0x18005a506  js      loc_18005A621
0x18005a50c  mov     rcx, [rbp+pv]
0x18005a510  test    rcx, rcx
0x18005a513  jz      loc_18005A5E9
0x18005a519  mov     rax, cs:WPP_GLOBAL_Control
0x18005a520  cmp     rax, r14
0x18005a523  jz      short loc_18005A53D
0x18005a525  test    byte ptr [rax+1Ch], 8
0x18005a529  jz      short loc_18005A53D
0x18005a52b  mov     rcx, [rax+10h]
0x18005a52f  mov     edx, 3Ah ; ':'
0x18005a534  call    WPP_SF_
0x18005a539  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18005a53d  lea     rdx, [rbp+pSecurityDescriptor]; void **
0x18005a541  mov     [rbp+pSecurityDescriptor], 0
0x18005a549  call    ?ConvertSDDLToSD@@YAJPEBGPEAPEAX@Z; ConvertSDDLToSD(ushort const *,void * *)
0x18005a54e  mov     ebx, eax
0x18005a550  test    eax, eax
0x18005a552  js      loc_18005A613
0x18005a558  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18005a55c  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18005a560  lea     rdx, [rbp+pOwner]; pOwner
0x18005a564  mov     [rbp+pOwner], 0
0x18005a56c  mov     dword ptr [rbp+bOwnerDefaulted], 0
0x18005a573  call    cs:__imp_GetSecurityDescriptorOwner
0x18005a579  mov     rax, [rbp+pOwner]
0x18005a57d  test    rax, rax
0x18005a580  jz      short loc_18005A5B3
0x18005a582  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a589  cmp     rcx, r14
0x18005a58c  jz      short loc_18005A5A6
0x18005a58e  test    byte ptr [rcx+1Ch], 8
0x18005a592  jz      short loc_18005A5A6
0x18005a594  mov     rcx, [rcx+10h]
0x18005a598  mov     edx, 3Bh ; ';'
0x18005a59d  call    WPP_SF_
0x18005a5a2  mov     rax, [rbp+pOwner]
0x18005a5a6  mov     rdx, rdi; void **
0x18005a5a9  mov     rcx, rax; pSourceSid
0x18005a5ac  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x18005a5b1  jmp     short loc_18005A5DB
0x18005a5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5ba  cmp     rcx, r14
0x18005a5bd  jz      short loc_18005A5D3
0x18005a5bf  test    byte ptr [rcx+1Ch], 8
0x18005a5c3  jz      short loc_18005A5D3
0x18005a5c5  mov     rcx, [rcx+10h]
0x18005a5c9  mov     edx, 3Ch ; '<'
0x18005a5ce  call    WPP_SF_
0x18005a5d3  mov     rcx, rdi; void **
0x18005a5d6  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18005a5db  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x18005a5df  mov     ebx, eax
0x18005a5e1  call    cs:__imp_LocalFree
0x18005a5e7  jmp     short loc_18005A613
0x18005a5e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5f0  cmp     rcx, r14
0x18005a5f3  jz      short loc_18005A609
0x18005a5f5  test    byte ptr [rcx+1Ch], 8
0x18005a5f9  jz      short loc_18005A609
0x18005a5fb  mov     rcx, [rcx+10h]
0x18005a5ff  mov     edx, 3Dh ; '='
0x18005a604  call    WPP_SF_
0x18005a609  mov     rcx, rdi; void **
0x18005a60c  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18005a611  mov     ebx, eax
0x18005a613  mov     rcx, [rbp+pv]; pv
0x18005a617  call    cs:__imp_CoTaskMemFree
0x18005a61d  test    ebx, ebx
0x18005a61f  jns     short loc_18005A64B
0x18005a621  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a628  cmp     rcx, r14
0x18005a62b  jz      short loc_18005A64B
0x18005a62d  test    byte ptr [rcx+1Ch], 2
0x18005a631  jz      short loc_18005A64B
0x18005a633  mov     rcx, [rcx+10h]
0x18005a637  lea     r8, WPP_055da27402593bc4c79a5720b75a8198_Traceguids
0x18005a63e  mov     edx, 3Eh ; '>'
0x18005a643  mov     r9d, ebx
0x18005a646  call    WPP_SF_d
0x18005a64b  mov     eax, ebx
0x18005a64d  mov     rbx, [rsp+30h+arg_10]
0x18005a652  add     rsp, 30h
0x18005a656  pop     r14
0x18005a658  pop     rdi
0x18005a659  pop     rbp
0x18005a65a  retn
```
