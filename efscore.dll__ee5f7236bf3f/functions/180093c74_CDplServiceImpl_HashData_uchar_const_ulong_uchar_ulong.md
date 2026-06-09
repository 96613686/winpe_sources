# CDplServiceImpl::HashData(uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180093c74`
- end: `0x1800940eb`
- name: `?HashData@CDplServiceImpl@@AEAAJPEBEKPEAPEAEPEAK@Z`
- size: `1143`
- prototype: `int(CDplServiceImpl *__hidden this, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a2178`
- `0x1800a8660`
- `0x1800aa5a4`
- `0x1800b39fc`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180093c74`
- `0x1800d5af8`
- `0x1800d6064`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180093d8c`
- `bcrypt!BCryptGetProperty` at `0x180093e74`
- `bcrypt!BCryptGetProperty` at `0x180093d8c`
- `bcrypt!BCryptGetProperty` at `0x180093e74`
- `bcrypt!BCryptDestroyHash` at `0x180093fbb`
- `bcrypt!BCryptDestroyHash` at `0x180093fbb`
- `bcrypt!BCryptFinishHash` at `0x180094093`
- `bcrypt!BCryptFinishHash` at `0x180094093`
- `bcrypt!BCryptHashData` at `0x18009403e`
- `bcrypt!BCryptHashData` at `0x18009403e`
- `bcrypt!BCryptCreateHash` at `0x180093f53`
- `bcrypt!BCryptCreateHash` at `0x180093f53`
- `ntdll!RtlNtStatusToDosError` at `0x180093d9b`
- `ntdll!RtlNtStatusToDosError` at `0x180093e83`
- `ntdll!RtlNtStatusToDosError` at `0x180093f65`
- `ntdll!RtlNtStatusToDosError` at `0x18009404c`
- `ntdll!RtlNtStatusToDosError` at `0x1800940a2`
- `ntdll!RtlNtStatusToDosError` at `0x180093d9b`
- `ntdll!RtlNtStatusToDosError` at `0x180093e83`
- `ntdll!RtlNtStatusToDosError` at `0x180093f65`
- `ntdll!RtlNtStatusToDosError` at `0x18009404c`
- `ntdll!RtlNtStatusToDosError` at `0x1800940a2`

## pseudocode

```c
__int64 __fastcall CDplServiceImpl::HashData(
        BCRYPT_HANDLE *this,
        UCHAR *a2,
        ULONG a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned __int8 *v5; // rdi
  unsigned int *v10; // rsi
  unsigned int v11; // ebx
  int v12; // r8d
  int Property; // eax
  int v14; // ecx
  int v15; // r14d
  signed int v16; // eax
  int v17; // eax
  int v18; // ecx
  int v19; // r14d
  signed int v20; // eax
  int v21; // eax
  int v22; // edi
  signed int v23; // eax
  int v25; // eax
  int v26; // edi
  signed int v27; // eax
  int v28; // eax
  int v29; // r14d
  signed int v30; // eax
  ULONG v31; // eax
  char pcbResult; // [rsp+20h] [rbp-40h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-20h] BYREF
  ULONG v34; // [rsp+44h] [rbp-1Ch] BYREF
  PUCHAR v35; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  PUCHAR pbHashObject; // [rsp+58h] [rbp-8h] BYREF
  ULONG v39; // [rsp+B8h] [rbp+58h] BYREF

  v5 = 0;
  v34 = 0;
  *(_DWORD *)pbOutput = 0;
  pbHashObject = 0;
  v39 = 0;
  v35 = 0;
  phHash = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 37, 252);
  if ( a4 )
    *a4 = 0;
  v10 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
  {
    pcbResult = 0;
LABEL_7:
    v11 = -2147024809;
    v12 = -2147024809;
LABEL_8:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 37, pcbResult);
    goto LABEL_41;
  }
  if ( !a4 )
  {
    pcbResult = 1;
LABEL_11:
    v11 = -2147467261;
    v12 = -2147467261;
    goto LABEL_8;
  }
  if ( !v10 )
  {
    pcbResult = 2;
    goto LABEL_11;
  }
  if ( !a3 )
  {
    pcbResult = 5;
    goto LABEL_7;
  }
  Property = BCryptGetProperty(this[30], L"ObjectLength", pbOutput, 4u, &v34, 0);
  v15 = Property;
  if ( Property < 0 )
  {
    v16 = RtlNtStatusToDosError(Property);
    v11 = v16;
    if ( !v16 || v16 == 317 )
    {
      v11 = v15 | 0x10000000;
    }
    else if ( v16 > 0 )
    {
      v11 = (unsigned __int16)v16 | 0x80070000;
    }
    pcbResult = 16;
LABEL_23:
    v12 = v11;
    goto LABEL_8;
  }
  fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 19);
  v11 = DplibpMemAllocEx(*(unsigned int *)pbOutput, 1, 1, &pbHashObject);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v11,
              37,
              19) >= 0 )
  {
    v17 = BCryptGetProperty(this[30], L"HashDigestLength", (PUCHAR)&v39, 4u, &v34, 0);
    v19 = v17;
    if ( v17 < 0 )
    {
      v20 = RtlNtStatusToDosError(v17);
      v11 = v20;
      if ( !v20 || v20 == 317 )
      {
        v11 = v19 | 0x10000000;
      }
      else if ( v20 > 0 )
      {
        v11 = (unsigned __int16)v20 | 0x80070000;
      }
      pcbResult = 29;
      goto LABEL_23;
    }
    fnEfsLogTrace1Strings(v18, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 37, 32);
    v11 = DplibpMemAllocEx(v39, 0, 0, &v35);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v11,
                37,
                32) < 0 )
      goto LABEL_40;
    v21 = BCryptCreateHash(this[30], &phHash, pbHashObject, *(ULONG *)pbOutput, 0, 0, 0);
    v22 = v21;
    if ( v21 < 0 )
    {
      v23 = RtlNtStatusToDosError(v21);
      v11 = v23;
      if ( !v23 || v23 == 317 )
      {
        v11 = v22 | 0x10000000;
      }
      else if ( v23 > 0 )
      {
        v11 = (unsigned __int16)v23 | 0x80070000;
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 37, 43);
LABEL_40:
      v5 = v35;
      goto LABEL_41;
    }
    v25 = BCryptHashData(phHash, a2, a3, 0);
    v26 = v25;
    if ( v25 < 0 )
    {
      v27 = RtlNtStatusToDosError(v25);
      v11 = v27;
      if ( !v27 || v27 == 317 )
      {
        v11 = v26 | 0x10000000;
      }
      else if ( v27 > 0 )
      {
        v11 = (unsigned __int16)v27 | 0x80070000;
      }
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 37, 49);
      goto LABEL_40;
    }
    v5 = v35;
    v28 = BCryptFinishHash(phHash, v35, v39, 0);
    v29 = v28;
    if ( v28 < 0 )
    {
      v30 = RtlNtStatusToDosError(v28);
      v11 = v30;
      if ( !v30 || v30 == 317 )
      {
        v11 = v29 | 0x10000000;
      }
      else if ( v30 > 0 )
      {
        v11 = (unsigned __int16)v30 | 0x80070000;
      }
      pcbResult = 55;
      goto LABEL_23;
    }
    v31 = v39;
    *a4 = v5;
    v5 = 0;
    *v10 = v31;
  }
LABEL_41:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( pbHashObject )
    DplibMemFree(pbHashObject);
  if ( v5 )
    DplibMemFree(v5);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v11,
    37,
    72);
  return v11;
}

```

## disassembly

```asm
0x180093c74  mov     [rsp-38h+arg_0], rbx
0x180093c79  mov     [rsp-38h+pbInput], rdx
0x180093c7e  push    rbp
0x180093c7f  push    rsi
0x180093c80  push    rdi
0x180093c81  push    r12
0x180093c83  push    r13
0x180093c85  push    r14
0x180093c87  push    r15
0x180093c89  mov     rbp, rsp
0x180093c8c  sub     rsp, 60h
0x180093c90  xor     edi, edi
0x180093c92  mov     [rbp+var_1C], 0
0x180093c99  mov     r15, r9
0x180093c9c  mov     dword ptr [rbp+pbOutput], 0
0x180093ca3  mov     r12d, r8d
0x180093ca6  mov     [rbp+pbHashObject], 0
0x180093cae  mov     rbx, rdx
0x180093cb1  mov     [rbp+arg_18], 0
0x180093cb8  lea     r14d, [rdi+25h]
0x180093cbc  mov     [rbp+var_18], rdi
0x180093cc0  mov     r9d, r14d
0x180093cc3  mov     [rbp+phHash], rdi
0x180093cc7  lea     r8, sourceString
0x180093cce  mov     dword ptr [rsp+60h+pcbResult], 5FCh
0x180093cd6  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180093cdd  mov     r13, rcx
0x180093ce0  call    fnEfsLogTrace1Strings
0x180093ce5  test    r15, r15
0x180093ce8  jz      short loc_180093CEF
0x180093cea  xor     eax, eax
0x180093cec  mov     [r15], rax
0x180093cef  mov     rsi, [rbp+arg_20]
0x180093cf3  test    rsi, rsi
0x180093cf6  jz      short loc_180093CFC
0x180093cf8  xor     eax, eax
0x180093cfa  mov     [rsi], eax
0x180093cfc  test    rbx, rbx
0x180093cff  jnz     short loc_180093D2F
0x180093d01  mov     dword ptr [rsp+60h+pcbResult], 600h
0x180093d09  mov     ebx, 80070057h
0x180093d0e  mov     r8d, 80070057h
0x180093d14  mov     rcx, cs:g_hPublisher
0x180093d1b  lea     rdx, EFS_TRACE_ERROR
0x180093d22  mov     r9d, r14d
0x180093d25  call    fnEfsLogTrace1
0x180093d2a  jmp     loc_180093FB2
0x180093d2f  test    r15, r15
0x180093d32  jnz     short loc_180093D49
0x180093d34  mov     dword ptr [rsp+60h+pcbResult], 601h
0x180093d3c  mov     ebx, 80004003h
0x180093d41  mov     r8d, 80004003h
0x180093d47  jmp     short loc_180093D14
0x180093d49  test    rsi, rsi
0x180093d4c  jnz     short loc_180093D58
0x180093d4e  mov     dword ptr [rsp+60h+pcbResult], 602h
0x180093d56  jmp     short loc_180093D3C
0x180093d58  test    r12d, r12d
0x180093d5b  jnz     short loc_180093D67
0x180093d5d  mov     dword ptr [rsp+60h+pcbResult], 605h
0x180093d65  jmp     short loc_180093D09
0x180093d67  mov     rcx, [r13+0F0h]; hObject
0x180093d6e  lea     rax, [rbp+var_1C]
0x180093d72  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180093d76  lea     r8, [rbp+pbOutput]; pbOutput
0x180093d7a  mov     r9d, 4; cbOutput
0x180093d80  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180093d85  lea     rdx, aObjectlength; "ObjectLength"
0x180093d8c  call    cs:__imp_BCryptGetProperty
0x180093d92  mov     r14d, eax
0x180093d95  test    eax, eax
0x180093d97  jns     short loc_180093DDA
0x180093d99  mov     ecx, eax; Status
0x180093d9b  call    cs:__imp_RtlNtStatusToDosError
0x180093da1  mov     ebx, eax
0x180093da3  test    eax, eax
0x180093da5  jz      short loc_180093DBD
0x180093da7  cmp     eax, 13Dh
0x180093dac  jz      short loc_180093DBD
0x180093dae  test    eax, eax
0x180093db0  jle     short loc_180093DC4
0x180093db2  movzx   ebx, ax
0x180093db5  or      ebx, 80070000h
0x180093dbb  jmp     short loc_180093DC4
0x180093dbd  mov     ebx, r14d
0x180093dc0  bts     ebx, 1Ch
0x180093dc4  mov     dword ptr [rsp+60h+pcbResult], 610h
0x180093dcc  mov     r14d, 25h ; '%'
0x180093dd2  mov     r8d, ebx
0x180093dd5  jmp     loc_180093D14
0x180093dda  mov     r14d, 613h
0x180093de0  lea     r8, sourceString
0x180093de7  mov     r9d, 25h ; '%'
0x180093ded  mov     dword ptr [rsp+60h+pcbResult], r14d
0x180093df2  lea     rdx, EFS_TRACE_START_EVENT
0x180093df9  call    fnEfsLogTrace1Strings
0x180093dfe  mov     ecx, dword ptr [rbp+pbOutput]
0x180093e01  lea     r9, [rbp+pbHashObject]
0x180093e05  mov     edx, 1
0x180093e0a  mov     r8d, edx
0x180093e0d  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x180093e12  mov     rcx, cs:g_hPublisher
0x180093e19  lea     r9, sourceString
0x180093e20  mov     [rsp+60h+var_30], r14d
0x180093e25  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180093e2c  mov     r14d, 25h ; '%'
0x180093e32  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180093e39  mov     [rsp+60h+dwFlags], r14d
0x180093e3e  mov     ebx, eax
0x180093e40  mov     dword ptr [rsp+60h+pcbResult], eax
0x180093e44  call    fnEfsLogTrace1String1Dword
0x180093e49  test    eax, eax
0x180093e4b  js      loc_180093FB2
0x180093e51  mov     rcx, [r13+0F0h]; hObject
0x180093e58  lea     rax, [rbp+var_1C]
0x180093e5c  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180093e60  lea     r9d, [r14-21h]; cbOutput
0x180093e64  lea     r8, [rbp+arg_18]; pbOutput
0x180093e68  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180093e6d  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180093e74  call    cs:__imp_BCryptGetProperty
0x180093e7a  mov     r14d, eax
0x180093e7d  test    eax, eax
0x180093e7f  jns     short loc_180093EB9
0x180093e81  mov     ecx, eax; Status
0x180093e83  call    cs:__imp_RtlNtStatusToDosError
0x180093e89  mov     ebx, eax
0x180093e8b  test    eax, eax
0x180093e8d  jz      short loc_180093EA5
0x180093e8f  cmp     eax, 13Dh
0x180093e94  jz      short loc_180093EA5
0x180093e96  test    eax, eax
0x180093e98  jle     short loc_180093EAC
0x180093e9a  movzx   ebx, ax
0x180093e9d  or      ebx, 80070000h
0x180093ea3  jmp     short loc_180093EAC
0x180093ea5  mov     ebx, r14d
0x180093ea8  bts     ebx, 1Ch
0x180093eac  mov     dword ptr [rsp+60h+pcbResult], 61Dh
0x180093eb4  jmp     loc_180093DCC
0x180093eb9  mov     r14d, 25h ; '%'
0x180093ebf  lea     r8, sourceString
0x180093ec6  mov     edi, 620h
0x180093ecb  lea     rdx, EFS_TRACE_START_EVENT
0x180093ed2  mov     r9d, r14d
0x180093ed5  mov     dword ptr [rsp+60h+pcbResult], edi
0x180093ed9  call    fnEfsLogTrace1Strings
0x180093ede  mov     ecx, [rbp+arg_18]
0x180093ee1  lea     r9, [rbp+var_18]
0x180093ee5  xor     r8d, r8d
0x180093ee8  xor     edx, edx
0x180093eea  call    ?DplibpMemAllocEx@@YAJ_KW4_DPLIB_ALLOC_QOS_LEVEL@@HPEAPEAX@Z; DplibpMemAllocEx(unsigned __int64,_DPLIB_ALLOC_QOS_LEVEL,int,void * *)
0x180093eef  mov     rcx, cs:g_hPublisher
0x180093ef6  lea     r9, sourceString
0x180093efd  mov     [rsp+60h+var_30], edi
0x180093f01  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180093f08  mov     [rsp+60h+dwFlags], r14d
0x180093f0d  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180093f14  mov     dword ptr [rsp+60h+pcbResult], eax
0x180093f18  mov     ebx, eax
0x180093f1a  call    fnEfsLogTrace1String1Dword
0x180093f1f  test    eax, eax
0x180093f21  js      loc_180093FAE
0x180093f27  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x180093f2b  lea     rdx, [rbp+phHash]; phHash
0x180093f2f  mov     r8, [rbp+pbHashObject]; pbHashObject
0x180093f33  mov     rcx, [r13+0F0h]; hAlgorithm
0x180093f3a  mov     [rsp+60h+var_30], 0; dwFlags
0x180093f42  mov     [rsp+60h+dwFlags], 0; cbSecret
0x180093f4a  mov     [rsp+60h+pcbResult], 0; pbSecret
0x180093f53  call    cs:__imp_BCryptCreateHash
0x180093f59  mov     edi, eax
0x180093f5b  test    eax, eax
0x180093f5d  jns     loc_180094030
0x180093f63  mov     ecx, eax; Status
0x180093f65  call    cs:__imp_RtlNtStatusToDosError
0x180093f6b  mov     ebx, eax
0x180093f6d  test    eax, eax
0x180093f6f  jz      short loc_180093F87
0x180093f71  cmp     eax, 13Dh
0x180093f76  jz      short loc_180093F87
0x180093f78  test    eax, eax
0x180093f7a  jle     short loc_180093F8D
0x180093f7c  movzx   ebx, ax
0x180093f7f  or      ebx, 80070000h
0x180093f85  jmp     short loc_180093F8D
0x180093f87  mov     ebx, edi
0x180093f89  bts     ebx, 1Ch
0x180093f8d  mov     dword ptr [rsp+60h+pcbResult], 62Bh
0x180093f95  mov     rcx, cs:g_hPublisher
0x180093f9c  lea     rdx, EFS_TRACE_ERROR
0x180093fa3  mov     r9d, r14d
0x180093fa6  mov     r8d, ebx
0x180093fa9  call    fnEfsLogTrace1
0x180093fae  mov     rdi, [rbp+var_18]
0x180093fb2  mov     rcx, [rbp+phHash]; hHash
0x180093fb6  test    rcx, rcx
0x180093fb9  jz      short loc_180093FC9
0x180093fbb  call    cs:__imp_BCryptDestroyHash
0x180093fc1  mov     [rbp+phHash], 0
0x180093fc9  mov     rcx, [rbp+pbHashObject]; void *
0x180093fcd  test    rcx, rcx
0x180093fd0  jz      short loc_180093FD7
0x180093fd2  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180093fd7  test    rdi, rdi
0x180093fda  jz      short loc_180093FE4
0x180093fdc  mov     rcx, rdi; void *
0x180093fdf  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x180093fe4  mov     rcx, cs:g_hPublisher
0x180093feb  lea     r9, sourceString
0x180093ff2  mov     [rsp+60h+var_30], 648h
0x180093ffa  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180094001  mov     [rsp+60h+dwFlags], r14d
0x180094006  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x18009400d  mov     dword ptr [rsp+60h+pcbResult], ebx
0x180094011  call    fnEfsLogTrace1String1Dword
0x180094016  mov     eax, ebx
0x180094018  mov     rbx, [rsp+60h+arg_0]
0x180094020  add     rsp, 60h
0x180094024  pop     r15
0x180094026  pop     r14
0x180094028  pop     r13
0x18009402a  pop     r12
0x18009402c  pop     rdi
0x18009402d  pop     rsi
0x18009402e  pop     rbp
0x18009402f  retn
0x180094030  mov     rdx, [rbp+pbInput]; pbInput
0x180094034  xor     r9d, r9d; dwFlags
0x180094037  mov     rcx, [rbp+phHash]; hHash
0x18009403b  mov     r8d, r12d; cbInput
0x18009403e  call    cs:__imp_BCryptHashData
0x180094044  mov     edi, eax
0x180094046  test    eax, eax
0x180094048  jns     short loc_180094081
0x18009404a  mov     ecx, eax; Status
0x18009404c  call    cs:__imp_RtlNtStatusToDosError
0x180094052  mov     ebx, eax
0x180094054  test    eax, eax
0x180094056  jz      short loc_18009406E
0x180094058  cmp     eax, 13Dh
0x18009405d  jz      short loc_18009406E
0x18009405f  test    eax, eax
0x180094061  jle     short loc_180094074
0x180094063  movzx   ebx, ax
0x180094066  or      ebx, 80070000h
0x18009406c  jmp     short loc_180094074
0x18009406e  mov     ebx, edi
0x180094070  bts     ebx, 1Ch
0x180094074  mov     dword ptr [rsp+60h+pcbResult], 631h
0x18009407c  jmp     loc_180093F95
0x180094081  mov     rdi, [rbp+var_18]
0x180094085  xor     r9d, r9d; dwFlags
0x180094088  mov     r8d, [rbp+arg_18]; cbOutput
0x18009408c  mov     rdx, rdi; pbOutput
0x18009408f  mov     rcx, [rbp+phHash]; hHash
0x180094093  call    cs:__imp_BCryptFinishHash
0x180094099  mov     r14d, eax
0x18009409c  test    eax, eax
0x18009409e  jns     short loc_1800940D8
0x1800940a0  mov     ecx, eax; Status
0x1800940a2  call    cs:__imp_RtlNtStatusToDosError
0x1800940a8  mov     ebx, eax
0x1800940aa  test    eax, eax
0x1800940ac  jz      short loc_1800940C4
0x1800940ae  cmp     eax, 13Dh
0x1800940b3  jz      short loc_1800940C4
0x1800940b5  test    eax, eax
0x1800940b7  jle     short loc_1800940CB
0x1800940b9  movzx   ebx, ax
0x1800940bc  or      ebx, 80070000h
0x1800940c2  jmp     short loc_1800940CB
0x1800940c4  mov     ebx, r14d
0x1800940c7  bts     ebx, 1Ch
0x1800940cb  mov     dword ptr [rsp+60h+pcbResult], 637h
0x1800940d3  jmp     loc_180093DCC
0x1800940d8  mov     eax, [rbp+arg_18]
0x1800940db  mov     [r15], rdi
0x1800940de  xor     edi, edi
0x1800940e0  mov     [rsi], eax
0x1800940e2  lea     r14d, [rdi+25h]
0x1800940e6  jmp     loc_180093FB2
```
