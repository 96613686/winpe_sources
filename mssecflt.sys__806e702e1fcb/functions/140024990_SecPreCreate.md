# SecPreCreate

- ea: `0x140024990`
- end: `0x140024d0a`
- name: `SecPreCreate`
- size: `890`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140009b80`
- `0x1400102ff`
- `0x140010437`
- `0x140011610`
- `0x140011650`
- `0x140024990`
- `0x140024d0c`
- `0x140028dd4`
- `0x140028f58`
- `0x14002ae0c`
- `0x14002b3a4`
- `0x14003b584`
- `0x14003b894`
- `0x14003fa28`

## import_xrefs

- `ntoskrnl!IoGetStackLimits` at `0x140024a06`
- `ntoskrnl!IoGetStackLimits` at `0x140024a06`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140024cd6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140024cd6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140024a9c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140024a9c`
- `ntoskrnl!ExQueryDepthSList` at `0x140024caa`
- `ntoskrnl!ExQueryDepthSList` at `0x140024caa`

## pseudocode

```c
__int64 __fastcall SecPreCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2, PSLIST_ENTRY *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  unsigned int v5; // r14d
  PSLIST_ENTRY v6; // rdi
  unsigned __int64 TargetFileObject; // r13
  UNICODE_STRING *p_Name; // r12
  char *v9; // rsi
  union _SLIST_HEADER *v10; // rcx
  void *v11; // rcx
  char *v12; // rsi
  USHORT v13; // bx
  char IsPrefetchEcpPresent; // [rsp+20h] [rbp-40h]
  int v16; // [rsp+24h] [rbp-3Ch]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+38h] [rbp-28h] BYREF
  char v20; // [rsp+40h] [rbp-20h]
  unsigned __int64 LowLimit; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 HighLimit; // [rsp+50h] [rbp-10h] BYREF

  Iopb = CallbackData->Iopb;
  LowLimit = 0;
  HighLimit = 0;
  v5 = 1;
  FileNameInformation = 0;
  v6 = 0;
  v20 = 0;
  TargetFileObject = (unsigned __int64)Iopb->TargetFileObject;
  p_Name = (UNICODE_STRING *)(TargetFileObject + 88);
  v16 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
  if ( !TargetFileObject )
    return v5;
  IoGetStackLimits(&LowLimit, &HighLimit);
  if ( (TargetFileObject <= LowLimit || TargetFileObject >= HighLimit) && (CallbackData->Iopb->OperationFlags & 2) == 0 )
  {
    IsPrefetchEcpPresent = SecIsPrefetchEcpPresent(*((_QWORD *)SecData + 3), CallbackData);
    if ( IsPrefetchEcpPresent || !(unsigned __int8)SecLmfShouldEnforcePolicy(CallbackData) )
    {
      if ( (CallbackData->Iopb->OperationFlags & 4) != 0 )
        goto LABEL_44;
      v9 = (char *)SecData + 1024;
      v10 = (union _SLIST_HEADER *)((char *)SecData + 1024);
      ++*((_DWORD *)SecData + 261);
      v6 = ExpInterlockedPopEntrySList(v10);
      if ( !v6 )
      {
        ++*((_DWORD *)v9 + 6);
        v6 = (PSLIST_ENTRY)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v9 + 6))(
                             *((unsigned int *)v9 + 9),
                             *((unsigned int *)v9 + 11),
                             *((unsigned int *)v9 + 10));
      }
      if ( !v6 )
        goto LABEL_44;
      *v6 = 0;
      if ( IsPrefetchEcpPresent )
      {
        v6->Next = (struct _SLIST_ENTRY *)2;
      }
      else if ( v20 )
      {
        v6->Next = (struct _SLIST_ENTRY *)64;
      }
      else
      {
        if ( (((unsigned __int8)xmmword_14001B740
             | ((unsigned __int8)(xmmword_14001B740
                                | ((unsigned __int8)(xmmword_14001B740
                                                   | (((unsigned __int64)xmmword_14001B740
                                                     | (((unsigned __int64)xmmword_14001B740
                                                       | ((unsigned __int64)xmmword_14001B740 >> 33)) >> 1)) >> 1)) >> 1)) >> 1))
            & 0x20) == 0
          && (xmmword_14001B740 & 8) == 0
          && (!SecData || (*((_DWORD *)SecData + 318) & 0x80u) == 0)
          || (dword_140020004 & 4) != 0 && (unsigned __int8)SecIsCsvDlEcpPresent(*(_QWORD *)(a2 + 8), CallbackData) )
        {
          goto LABEL_44;
        }
        if ( (v16 & 0x2000021) != 0 )
          v6->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v6->Next | 8);
        if ( (v16 & 0x10003) != 0 )
        {
          if ( !p_Name->Length
            && *(_QWORD *)(TargetFileObject + 64)
            && FltGetFileNameInformation_0(CallbackData, 0x102u, &FileNameInformation) >= 0
            && FileNameInformation->Name.Length )
          {
            p_Name = &FileNameInformation->Name;
          }
          if ( (unsigned __int8)SecIsDlpAdsStreamName(p_Name) )
          {
            if ( (v16 & 0x10002) != 0
              && (unsigned __int8)SecShouldBlockDlpAdsFileOperation(TargetFileObject, CallbackData->Thread) )
            {
              CallbackData->IoStatus.Status = -1073741790;
              v5 = 4;
              CallbackData->IoStatus.Information = 0;
              goto LABEL_44;
            }
            if ( (unsigned __int8)SecIsAdsExcludeFileOperations() )
              goto LABEL_44;
          }
        }
        if ( (_bittest64((const signed __int64 *)&xmmword_14001B740, 0x2Au)
           || (unsigned __int8)SecIsJitEnforcementEnabled())
          && ((__int64)v6->Next & 8) != 0 )
        {
          if ( qword_140020050 )
          {
            if ( (int)((__int64 (__fastcall *)(_QWORD, PFLT_CALLBACK_DATA, __int64))qword_140020050)(
                        *(_QWORD *)(a2 + 8),
                        CallbackData,
                        4) >= 0 )
              v6->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v6->Next | 0x10);
          }
          else
          {
            v6->Next = (struct _SLIST_ENTRY *)((unsigned __int64)v6->Next | 0x10);
          }
        }
        SecPreCreateHandleAppCompat(CallbackData, a2, v6);
      }
      v5 = 5;
      *a3 = v6;
      v6 = 0;
      goto LABEL_44;
    }
    CallbackData->IoStatus.Status = -1073741790;
    v5 = 4;
    CallbackData->IoStatus.Information = 0;
  }
LABEL_44:
  if ( FileNameInformation )
    FltReleaseFileNameInformation_0(FileNameInformation);
  if ( v6 )
  {
    v11 = (void *)*((_QWORD *)&v6->Next + 1);
    if ( v11 )
      SecFreePool(v11, 0x74736353u);
    v12 = (char *)SecData + 1024;
    ++*((_DWORD *)SecData + 263);
    v13 = *((_WORD *)v12 + 8);
    if ( ExQueryDepthSList((PSLIST_HEADER)v12) < v13 )
    {
      _mm_lfence();
      ExpInterlockedPushEntrySList((PSLIST_HEADER)v12, v6);
    }
    else
    {
      ++*((_DWORD *)v12 + 8);
      (*((void (__fastcall **)(PSLIST_ENTRY))v12 + 7))(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140024990  mov     [rsp-38h+arg_18], rbx
0x140024995  push    rbp
0x140024996  push    rsi
0x140024997  push    rdi
0x140024998  push    r12
0x14002499a  push    r13
0x14002499c  push    r14
0x14002499e  push    r15
0x1400249a0  mov     rbp, rsp
0x1400249a3  sub     rsp, 60h
0x1400249a7  mov     rax, cs:__security_cookie
0x1400249ae  xor     rax, rsp
0x1400249b1  mov     [rbp+var_8], rax
0x1400249b5  mov     rbx, rcx
0x1400249b8  mov     [rbp+var_30], r8
0x1400249bc  mov     rcx, [rcx+10h]
0x1400249c0  xor     r8d, r8d
0x1400249c3  mov     [rbp+LowLimit], r8
0x1400249c7  mov     rsi, rdx
0x1400249ca  mov     [rbp+HighLimit], r8
0x1400249ce  mov     r14d, 1
0x1400249d4  mov     [rbp+FileNameInformation], r8
0x1400249d8  mov     edi, r8d
0x1400249db  mov     [rbp+var_20], r8b
0x1400249df  mov     r13, [rcx+8]
0x1400249e3  mov     rax, [rcx+18h]
0x1400249e7  mov     [rbp+var_38], rdx
0x1400249eb  lea     r12, [r13+58h]
0x1400249ef  mov     edx, [rax+10h]
0x1400249f2  mov     [rbp+var_3C], edx
0x1400249f5  test    r13, r13
0x1400249f8  jz      loc_140024CE2
0x1400249fe  lea     rdx, [rbp+HighLimit]; HighLimit
0x140024a02  lea     rcx, [rbp+LowLimit]; LowLimit
0x140024a06  call    cs:__imp_IoGetStackLimits
0x140024a0d  nop     dword ptr [rax+rax+00h]
0x140024a12  cmp     r13, [rbp+LowLimit]
0x140024a16  jbe     short loc_140024A22
0x140024a18  cmp     r13, [rbp+HighLimit]
0x140024a1c  jb      loc_140024C6C
0x140024a22  mov     rax, [rbx+10h]
0x140024a26  test    byte ptr [rax+6], 2
0x140024a2a  jnz     loc_140024C6C
0x140024a30  mov     rcx, cs:SecData
0x140024a37  mov     rdx, rbx
0x140024a3a  mov     rcx, [rcx+18h]
0x140024a3e  call    SecIsPrefetchEcpPresent
0x140024a43  xor     r15d, r15d
0x140024a46  mov     [rbp+var_40], al
0x140024a49  test    al, al
0x140024a4b  jnz     short loc_140024A74
0x140024a4d  lea     r8, [rbp+var_20]
0x140024a51  mov     rdx, rsi
0x140024a54  mov     rcx, rbx; CallbackData
0x140024a57  call    SecLmfShouldEnforcePolicy
0x140024a5c  test    al, al
0x140024a5e  jz      short loc_140024A74
0x140024a60  mov     dword ptr [rbx+18h], 0C0000022h
0x140024a67  lea     r14d, [r15+4]
0x140024a6b  mov     [rbx+20h], r15
0x140024a6f  jmp     loc_140024C6C
0x140024a74  mov     rax, [rbx+10h]
0x140024a78  mov     r15d, 4
0x140024a7e  test    [rax+6], r15b
0x140024a82  jnz     loc_140024C6C
0x140024a88  mov     rsi, cs:SecData
0x140024a8f  add     rsi, 400h
0x140024a96  mov     rcx, rsi; ListHead
0x140024a99  inc     dword ptr [rsi+14h]
0x140024a9c  call    cs:__imp_ExpInterlockedPopEntrySList
0x140024aa3  nop     dword ptr [rax+rax+00h]
0x140024aa8  mov     rdi, rax
0x140024aab  test    rax, rax
0x140024aae  jnz     short loc_140024ACA
0x140024ab0  inc     dword ptr [rsi+18h]
0x140024ab3  mov     edx, [rsi+2Ch]
0x140024ab6  mov     rax, [rsi+30h]
0x140024aba  mov     r8d, [rsi+28h]
0x140024abe  mov     ecx, [rsi+24h]
0x140024ac1  call    cs:__guard_dispatch_icall_fptr
0x140024ac7  mov     rdi, rax
0x140024aca  xor     esi, esi
0x140024acc  test    rdi, rdi
0x140024acf  jz      loc_140024C6C
0x140024ad5  xorps   xmm0, xmm0
0x140024ad8  movups  xmmword ptr [rdi], xmm0
0x140024adb  cmp     [rbp+var_40], sil
0x140024adf  jz      short loc_140024AED
0x140024ae1  mov     qword ptr [rdi], 2
0x140024ae8  jmp     loc_140024C5C
0x140024aed  cmp     [rbp+var_20], sil
0x140024af1  jz      short loc_140024AFF
0x140024af3  mov     qword ptr [rdi], 40h ; '@'
0x140024afa  jmp     loc_140024C5C
0x140024aff  mov     rcx, qword ptr cs:xmmword_14001B740
0x140024b06  mov     rax, rcx
0x140024b09  shr     rax, 21h
0x140024b0d  or      rax, rcx
0x140024b10  shr     rax, 1
0x140024b13  or      rax, rcx
0x140024b16  shr     rax, 1
0x140024b19  or      al, cl
0x140024b1b  shr     al, 1
0x140024b1d  or      al, cl
0x140024b1f  shr     al, 1
0x140024b21  or      al, cl
0x140024b23  test    al, 20h
0x140024b25  jnz     short loc_140024B4A
0x140024b27  test    cl, 8
0x140024b2a  jnz     short loc_140024B4A
0x140024b2c  mov     rax, cs:SecData
0x140024b33  test    rax, rax
0x140024b36  jz      loc_140024C6C
0x140024b3c  mov     eax, [rax+4F8h]
0x140024b42  test    al, al
0x140024b44  jns     loc_140024C6C
0x140024b4a  mov     eax, cs:dword_140020004
0x140024b50  test    r15b, al
0x140024b53  jz      short loc_140024B6D
0x140024b55  mov     rcx, [rbp+var_38]
0x140024b59  mov     rdx, rbx
0x140024b5c  mov     rcx, [rcx+8]
0x140024b60  call    SecIsCsvDlEcpPresent
0x140024b65  test    al, al
0x140024b67  jnz     loc_140024C6C
0x140024b6d  mov     esi, [rbp+var_3C]
0x140024b70  test    esi, 2000021h
0x140024b76  jz      short loc_140024B7C
0x140024b78  or      qword ptr [rdi], 8
0x140024b7c  test    esi, 10003h
0x140024b82  jz      short loc_140024BFC
0x140024b84  xor     eax, eax
0x140024b86  cmp     [r12], ax
0x140024b8b  jnz     short loc_140024BB9
0x140024b8d  cmp     [r13+40h], rax
0x140024b91  jz      short loc_140024BB9
0x140024b93  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140024b97  mov     edx, 102h; NameOptions
0x140024b9c  mov     rcx, rbx; CallbackData
0x140024b9f  call    FltGetFileNameInformation_0
0x140024ba4  xor     ecx, ecx
0x140024ba6  test    eax, eax
0x140024ba8  js      short loc_140024BB9
0x140024baa  mov     rax, [rbp+FileNameInformation]
0x140024bae  add     rax, 8
0x140024bb2  cmp     [rax], cx
0x140024bb5  cmovnz  r12, rax
0x140024bb9  mov     rcx, r12
0x140024bbc  call    SecIsDlpAdsStreamName
0x140024bc1  test    al, al
0x140024bc3  jz      short loc_140024BFC
0x140024bc5  test    esi, 10002h
0x140024bcb  jz      short loc_140024BEF
0x140024bcd  mov     rdx, [rbx+8]
0x140024bd1  mov     rcx, r13
0x140024bd4  call    SecShouldBlockDlpAdsFileOperation
0x140024bd9  xor     esi, esi
0x140024bdb  test    al, al
0x140024bdd  jz      short loc_140024BF1
0x140024bdf  mov     dword ptr [rbx+18h], 0C0000022h
0x140024be6  mov     r14d, r15d
0x140024be9  mov     [rbx+20h], rsi
0x140024bed  jmp     short loc_140024C6C
0x140024bef  xor     esi, esi
0x140024bf1  call    SecIsAdsExcludeFileOperations
0x140024bf6  test    al, al
0x140024bf8  jnz     short loc_140024C6C
0x140024bfa  jmp     short loc_140024BFE
0x140024bfc  xor     esi, esi
0x140024bfe  bt      qword ptr cs:xmmword_14001B740, 2Ah ; '*'
0x140024c07  jb      short loc_140024C12
0x140024c09  call    SecIsJitEnforcementEnabled
0x140024c0e  test    al, al
0x140024c10  jz      short loc_140024C4D
0x140024c12  mov     rax, [rdi]
0x140024c15  test    al, 8
0x140024c17  jz      short loc_140024C4D
0x140024c19  mov     r9, cs:qword_140020050
0x140024c20  test    r9, r9
0x140024c23  jz      short loc_140024C46
0x140024c25  mov     rax, [rbp+var_38]
0x140024c29  mov     r8d, r15d
0x140024c2c  mov     rdx, rbx
0x140024c2f  mov     rcx, [rax+8]
0x140024c33  mov     rax, r9
0x140024c36  call    cs:__guard_dispatch_icall_fptr
0x140024c3c  test    eax, eax
0x140024c3e  js      short loc_140024C4D
0x140024c40  or      qword ptr [rdi], 10h
0x140024c44  jmp     short loc_140024C4D
0x140024c46  or      rax, 10h
0x140024c4a  mov     [rdi], rax
0x140024c4d  mov     rdx, [rbp+var_38]
0x140024c51  mov     r8, rdi
0x140024c54  mov     rcx, rbx
0x140024c57  call    SecPreCreateHandleAppCompat
0x140024c5c  mov     rax, [rbp+var_30]
0x140024c60  mov     r14d, 5
0x140024c66  mov     [rax], rdi
0x140024c69  mov     rdi, rsi
0x140024c6c  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140024c70  test    rcx, rcx
0x140024c73  jz      short loc_140024C7A
0x140024c75  call    FltReleaseFileNameInformation_0
0x140024c7a  test    rdi, rdi
0x140024c7d  jz      short loc_140024CE2
0x140024c7f  mov     rcx, [rdi+8]; P
0x140024c83  test    rcx, rcx
0x140024c86  jz      short loc_140024C92
0x140024c88  mov     edx, 74736353h; Tag
0x140024c8d  call    SecFreePool
0x140024c92  mov     rsi, cs:SecData
0x140024c99  add     rsi, 400h
0x140024ca0  mov     rcx, rsi; SListHead
0x140024ca3  inc     dword ptr [rsi+1Ch]
0x140024ca6  movzx   ebx, word ptr [rsi+10h]
0x140024caa  call    cs:__imp_ExQueryDepthSList
0x140024cb1  nop     dword ptr [rax+rax+00h]
0x140024cb6  cmp     ax, bx
0x140024cb9  jb      short loc_140024CCD
0x140024cbb  inc     dword ptr [rsi+20h]
0x140024cbe  mov     rcx, rdi
0x140024cc1  mov     rax, [rsi+38h]
0x140024cc5  call    cs:__guard_dispatch_icall_fptr
0x140024ccb  jmp     short loc_140024CE2
0x140024ccd  lfence
0x140024cd0  mov     rdx, rdi; ListEntry
0x140024cd3  mov     rcx, rsi; ListHead
0x140024cd6  call    cs:__imp_ExpInterlockedPushEntrySList
0x140024cdd  nop     dword ptr [rax+rax+00h]
0x140024ce2  mov     eax, r14d
0x140024ce5  mov     rcx, [rbp+var_8]
0x140024ce9  xor     rcx, rsp; StackCookie
0x140024cec  call    __security_check_cookie
0x140024cf1  mov     rbx, [rsp+60h+arg_18]
0x140024cf9  add     rsp, 60h
0x140024cfd  pop     r15
0x140024cff  pop     r14
0x140024d01  pop     r13
0x140024d03  pop     r12
0x140024d05  pop     rdi
0x140024d06  pop     rsi
0x140024d07  pop     rbp
0x140024d08  retn
```
