# CShareInfo::Copy(_SHARE_INFO_503 const *)

- ea: `0x180011790`
- end: `0x180011ad0`
- name: `?Copy@CShareInfo@@QEAAJPEBU_SHARE_INFO_503@@@Z`
- size: `832`
- prototype: `__int64 __fastcall(CShareInfo *__hidden this, const struct _SHARE_INFO_503 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180010fa0`
- `0x180011480`
- `0x18002ad40`

## callees

- `0x180011790`
- `0x180011ae0`
- `0x1800238d8`
- `0x1800259bc`
- `0x18002637c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001181c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001183d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001181c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001183d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011809`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001182a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001184b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011809`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001182a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001184b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a21`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180011978`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180011978`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001199e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001199e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800119ab`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800119ab`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180011aa5`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180011aa5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800119bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800119bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001185e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011ac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001185e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011ac5`

## pseudocode

```c
__int64 __fastcall CShareInfo::Copy(CShareInfo *this, const struct _SHARE_INFO_503 *a2)
{
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  void *v6; // rsi
  HANDLE v7; // rax
  void *v8; // rsi
  HANDLE v9; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  void *v14; // rcx
  __int64 v15; // rax
  const unsigned __int16 *shi503_servername; // rcx
  const unsigned __int16 *shi503_remark; // rcx
  const unsigned __int16 *shi503_path; // rcx
  const unsigned __int16 *shi503_passwd; // rcx
  PSECURITY_DESCRIPTOR shi503_security_descriptor; // rdi
  __int64 result; // rax
  _QWORD *v22; // rsi
  HLOCAL v23; // rbp
  unsigned int Error; // ebx
  signed int LastError; // eax
  void *v26; // rax
  WORD pControl; // [rsp+50h] [rbp+8h] BYREF
  size_t Size; // [rsp+60h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+68h] [rbp+20h] BYREF

  if ( *((_DWORD *)this + 4) )
  {
    v4 = *(void **)(*((_QWORD *)this + 3) + 56LL);
    if ( v4 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    v6 = (void *)**((_QWORD **)this + 3);
    if ( v6 )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
    v8 = *(void **)(*((_QWORD *)this + 3) + 16LL);
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
    }
    v10 = *(void **)(*((_QWORD *)this + 3) + 40LL);
    if ( v10 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
    v12 = *(void **)(*((_QWORD *)this + 3) + 48LL);
    if ( v12 )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v12);
    }
    v14 = *(void **)(*((_QWORD *)this + 3) + 72LL);
    if ( v14 )
    {
      LocalFree(v14);
      *(_QWORD *)(*((_QWORD *)this + 3) + 72LL) = 0;
    }
  }
  else
  {
    v26 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
    *((_QWORD *)this + 3) = v26;
    if ( !v26 )
      return 2147942414LL;
  }
  v15 = *((_QWORD *)this + 3);
  *((_DWORD *)this + 4) = 1;
  *(_QWORD *)(v15 + 56) = 0;
  **((_QWORD **)this + 3) = 0;
  *(_DWORD *)(*((_QWORD *)this + 3) + 8LL) = a2->shi503_type;
  *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 3) + 24LL) = a2->shi503_permissions;
  *(_DWORD *)(*((_QWORD *)this + 3) + 28LL) = a2->shi503_max_uses;
  *(_QWORD *)(*((_QWORD *)this + 3) + 40LL) = 0;
  *(_QWORD *)(*((_QWORD *)this + 3) + 48LL) = 0;
  *(_DWORD *)(*((_QWORD *)this + 3) + 64LL) = a2->shi503_reserved;
  *(_QWORD *)(*((_QWORD *)this + 3) + 72LL) = 0;
  shi503_servername = a2->shi503_servername;
  if ( shi503_servername )
  {
    *(_QWORD *)(*((_QWORD *)this + 3) + 56LL) = NewDup(shi503_servername);
    if ( !*(_QWORD *)(*((_QWORD *)this + 3) + 56LL) )
      return 2147942414LL;
  }
  if ( a2->shi503_netname )
  {
    **((_QWORD **)this + 3) = NewDup(a2->shi503_netname);
    if ( !**((_QWORD **)this + 3) )
      return 2147942414LL;
  }
  shi503_remark = a2->shi503_remark;
  if ( shi503_remark )
  {
    *(_QWORD *)(*((_QWORD *)this + 3) + 16LL) = NewDup(shi503_remark);
    if ( !*(_QWORD *)(*((_QWORD *)this + 3) + 16LL) )
      return 2147942414LL;
  }
  shi503_path = a2->shi503_path;
  if ( shi503_path )
  {
    *(_QWORD *)(*((_QWORD *)this + 3) + 40LL) = NewDup(shi503_path);
    if ( !*(_QWORD *)(*((_QWORD *)this + 3) + 40LL) )
      return 2147942414LL;
  }
  shi503_passwd = a2->shi503_passwd;
  if ( shi503_passwd )
  {
    *(_QWORD *)(*((_QWORD *)this + 3) + 48LL) = NewDup(shi503_passwd);
    if ( !*(_QWORD *)(*((_QWORD *)this + 3) + 48LL) )
      return 2147942414LL;
  }
  shi503_security_descriptor = a2->shi503_security_descriptor;
  result = 0;
  if ( shi503_security_descriptor )
  {
    v22 = (_QWORD *)(*((_QWORD *)this + 3) + 72LL);
    if ( *((_QWORD *)this + 3) == -72 )
      return (unsigned int)-2147467261;
    *v22 = 0;
    if ( IsValidSecurityDescriptor(shi503_security_descriptor) )
    {
      pControl = 0;
      dwRevision = 0;
      if ( !GetSecurityDescriptorControl(shi503_security_descriptor, &pControl, &dwRevision) )
      {
        LastError = GetLastError();
        Error = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return Error;
      }
      LODWORD(Size) = GetSecurityDescriptorLength(shi503_security_descriptor);
      v23 = LocalAlloc(0x40u, (unsigned int)Size);
      if ( v23 )
      {
        Error = 0;
        if ( (pControl & 0x8000u) == 0 )
        {
          if ( !MakeSelfRelativeSD(shi503_security_descriptor, v23, (LPDWORD)&Size) )
          {
            Error = ResultFromLastError();
            if ( (Error & 0x80000000) != 0 )
            {
              LocalFree(v23);
              return Error;
            }
          }
        }
        else
        {
          memcpy_0(v23, shi503_security_descriptor, (unsigned int)Size);
        }
        *v22 = v23;
        return Error;
      }
      return 2147942414LL;
    }
    else
    {
      return 2147942487LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011790  push    rbx
0x180011792  push    rsi
0x180011793  push    rdi
0x180011794  push    r14
0x180011796  sub     rsp, 28h
0x18001179a  xor     r14d, r14d
0x18001179d  mov     rdi, rdx
0x1800117a0  mov     rbx, rcx
0x1800117a3  cmp     [rcx+10h], r14d
0x1800117a7  jz      loc_180011A54
0x1800117ad  mov     rax, [rcx+18h]
0x1800117b1  mov     rsi, [rax+38h]
0x1800117b5  test    rsi, rsi
0x1800117b8  jz      short loc_1800117CE
0x1800117ba  call    cs:__imp_GetProcessHeap
0x1800117c0  mov     r8, rsi; lpMem
0x1800117c3  xor     edx, edx; dwFlags
0x1800117c5  mov     rcx, rax; hHeap
0x1800117c8  call    cs:__imp_HeapFree
0x1800117ce  mov     rax, [rbx+18h]
0x1800117d2  mov     rsi, [rax]
0x1800117d5  test    rsi, rsi
0x1800117d8  jz      short loc_1800117EE
0x1800117da  call    cs:__imp_GetProcessHeap
0x1800117e0  mov     r8, rsi; lpMem
0x1800117e3  xor     edx, edx; dwFlags
0x1800117e5  mov     rcx, rax; hHeap
0x1800117e8  call    cs:__imp_HeapFree
0x1800117ee  mov     rax, [rbx+18h]
0x1800117f2  mov     rsi, [rax+10h]
0x1800117f6  test    rsi, rsi
0x1800117f9  jz      short loc_18001180F
0x1800117fb  call    cs:__imp_GetProcessHeap
0x180011801  mov     r8, rsi; lpMem
0x180011804  xor     edx, edx; dwFlags
0x180011806  mov     rcx, rax; hHeap
0x180011809  call    cs:__imp_HeapFree
0x18001180f  mov     rax, [rbx+18h]
0x180011813  mov     rsi, [rax+28h]
0x180011817  test    rsi, rsi
0x18001181a  jz      short loc_180011830
0x18001181c  call    cs:__imp_GetProcessHeap
0x180011822  mov     r8, rsi; lpMem
0x180011825  xor     edx, edx; dwFlags
0x180011827  mov     rcx, rax; hHeap
0x18001182a  call    cs:__imp_HeapFree
0x180011830  mov     rax, [rbx+18h]
0x180011834  mov     rsi, [rax+30h]
0x180011838  test    rsi, rsi
0x18001183b  jz      short loc_180011851
0x18001183d  call    cs:__imp_GetProcessHeap
0x180011843  mov     r8, rsi; lpMem
0x180011846  xor     edx, edx; dwFlags
0x180011848  mov     rcx, rax; hHeap
0x18001184b  call    cs:__imp_HeapFree
0x180011851  mov     rax, [rbx+18h]
0x180011855  mov     rcx, [rax+48h]; hMem
0x180011859  test    rcx, rcx
0x18001185c  jz      short loc_18001186C
0x18001185e  call    cs:__imp_LocalFree
0x180011864  mov     rax, [rbx+18h]
0x180011868  mov     [rax+48h], r14
0x18001186c  mov     rax, [rbx+18h]
0x180011870  mov     dword ptr [rbx+10h], 1
0x180011877  mov     [rax+38h], r14
0x18001187b  mov     rax, [rbx+18h]
0x18001187f  mov     [rax], r14
0x180011882  mov     rcx, [rbx+18h]
0x180011886  mov     eax, [rdi+8]
0x180011889  mov     [rcx+8], eax
0x18001188c  mov     rax, [rbx+18h]
0x180011890  mov     [rax+10h], r14
0x180011894  mov     eax, [rdi+18h]
0x180011897  mov     rcx, [rbx+18h]
0x18001189b  mov     [rcx+18h], eax
0x18001189e  mov     rcx, [rbx+18h]
0x1800118a2  mov     eax, [rdi+1Ch]
0x1800118a5  mov     [rcx+1Ch], eax
0x1800118a8  mov     rax, [rbx+18h]
0x1800118ac  mov     [rax+28h], r14
0x1800118b0  mov     rax, [rbx+18h]
0x1800118b4  mov     [rax+30h], r14
0x1800118b8  mov     rcx, [rbx+18h]
0x1800118bc  mov     eax, [rdi+40h]
0x1800118bf  mov     [rcx+40h], eax
0x1800118c2  mov     rax, [rbx+18h]
0x1800118c6  mov     [rax+48h], r14
0x1800118ca  mov     rcx, [rdi+38h]; unsigned __int16 *
0x1800118ce  test    rcx, rcx
0x1800118d1  jz      short loc_1800118EE
0x1800118d3  call    ?NewDup@@YAPEAGPEBG@Z; NewDup(ushort const *)
0x1800118d8  mov     rcx, [rbx+18h]
0x1800118dc  mov     [rcx+38h], rax
0x1800118e0  mov     rax, [rbx+18h]
0x1800118e4  cmp     [rax+38h], r14
0x1800118e8  jz      loc_180011A12
0x1800118ee  mov     rcx, [rdi]; unsigned __int16 *
0x1800118f1  test    rcx, rcx
0x1800118f4  jnz     loc_1800119F9
0x1800118fa  mov     rcx, [rdi+10h]; unsigned __int16 *
0x1800118fe  test    rcx, rcx
0x180011901  jz      short loc_18001191E
0x180011903  call    ?NewDup@@YAPEAGPEBG@Z; NewDup(ushort const *)
0x180011908  mov     rcx, [rbx+18h]
0x18001190c  mov     [rcx+10h], rax
0x180011910  mov     rax, [rbx+18h]
0x180011914  cmp     [rax+10h], r14
0x180011918  jz      loc_180011A12
0x18001191e  mov     rcx, [rdi+28h]; unsigned __int16 *
0x180011922  test    rcx, rcx
0x180011925  jz      short loc_180011942
0x180011927  call    ?NewDup@@YAPEAGPEBG@Z; NewDup(ushort const *)
0x18001192c  mov     rcx, [rbx+18h]
0x180011930  mov     [rcx+28h], rax
0x180011934  mov     rax, [rbx+18h]
0x180011938  cmp     [rax+28h], r14
0x18001193c  jz      loc_180011A12
0x180011942  mov     rcx, [rdi+30h]; unsigned __int16 *
0x180011946  test    rcx, rcx
0x180011949  jnz     loc_180011A74
0x18001194f  mov     rdi, [rdi+48h]
0x180011953  mov     eax, r14d
0x180011956  test    rdi, rdi
0x180011959  jz      loc_180011A17
0x18001195f  mov     rsi, [rbx+18h]
0x180011963  mov     [rsp+48h+var_28], rbp
0x180011968  add     rsi, 48h ; 'H'
0x18001196c  jz      loc_180011A90
0x180011972  mov     rcx, rdi; pSecurityDescriptor
0x180011975  mov     [rsi], r14
0x180011978  call    cs:__imp_IsValidSecurityDescriptor
0x18001197e  test    eax, eax
0x180011980  jz      loc_180011A46
0x180011986  lea     r8, [rsp+48h+dwRevision]; lpdwRevision
0x18001198b  mov     [rsp+48h+pControl], r14w
0x180011991  lea     rdx, [rsp+48h+pControl]; pControl
0x180011996  mov     [rsp+48h+dwRevision], r14d
0x18001199b  mov     rcx, rdi; pSecurityDescriptor
0x18001199e  call    cs:__imp_GetSecurityDescriptorControl
0x1800119a4  test    eax, eax
0x1800119a6  jz      short loc_180011A21
0x1800119a8  mov     rcx, rdi; pSecurityDescriptor
0x1800119ab  call    cs:__imp_GetSecurityDescriptorLength
0x1800119b1  mov     edx, eax; uBytes
0x1800119b3  mov     ecx, 40h ; '@'; uFlags
0x1800119b8  mov     dword ptr [rsp+48h+Size], edx
0x1800119bc  call    cs:__imp_LocalAlloc
0x1800119c2  mov     rbp, rax
0x1800119c5  test    rax, rax
0x1800119c8  jz      short loc_180011A38
0x1800119ca  mov     eax, 8000h
0x1800119cf  mov     ebx, r14d
0x1800119d2  test    [rsp+48h+pControl], ax
0x1800119d7  jz      loc_180011A9A
0x1800119dd  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x1800119e2  mov     rdx, rdi; Src
0x1800119e5  mov     rcx, rbp; void *
0x1800119e8  call    memcpy_0
0x1800119ed  mov     [rsi], rbp
0x1800119f0  mov     rbp, [rsp+48h+var_28]
0x1800119f5  mov     eax, ebx
0x1800119f7  jmp     short loc_180011A17
0x1800119f9  call    ?NewDup@@YAPEAGPEBG@Z; NewDup(ushort const *)
0x1800119fe  mov     rcx, [rbx+18h]
0x180011a02  mov     [rcx], rax
0x180011a05  mov     rax, [rbx+18h]
0x180011a09  cmp     [rax], r14
0x180011a0c  jnz     loc_1800118FA
0x180011a12  mov     eax, 8007000Eh
0x180011a17  add     rsp, 28h
0x180011a1b  pop     r14
0x180011a1d  pop     rdi
0x180011a1e  pop     rsi
0x180011a1f  pop     rbx
0x180011a20  retn
0x180011a21  call    cs:__imp_GetLastError
0x180011a27  mov     ebx, eax
0x180011a29  test    eax, eax
0x180011a2b  jle     short loc_1800119F0
0x180011a2d  movzx   ebx, ax
0x180011a30  or      ebx, 80070000h
0x180011a36  jmp     short loc_1800119F0
0x180011a38  mov     rbp, [rsp+48h+var_28]
0x180011a3d  mov     ebx, 8007000Eh
0x180011a42  mov     eax, ebx
0x180011a44  jmp     short loc_180011A17
0x180011a46  mov     rbp, [rsp+48h+var_28]
0x180011a4b  mov     ebx, 80070057h
0x180011a50  mov     eax, ebx
0x180011a52  jmp     short loc_180011A17
0x180011a54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011a5b  mov     ecx, 50h ; 'P'; unsigned __int64
0x180011a60  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011a65  mov     [rbx+18h], rax
0x180011a69  test    rax, rax
0x180011a6c  jnz     loc_18001186C
0x180011a72  jmp     short loc_180011A12
0x180011a74  call    ?NewDup@@YAPEAGPEBG@Z; NewDup(ushort const *)
0x180011a79  mov     rcx, [rbx+18h]
0x180011a7d  mov     [rcx+30h], rax
0x180011a81  mov     rax, [rbx+18h]
0x180011a85  cmp     [rax+30h], r14
0x180011a89  jz      short loc_180011A12
0x180011a8b  jmp     loc_18001194F
0x180011a90  mov     ebx, 80004003h
0x180011a95  jmp     loc_1800119F0
0x180011a9a  lea     r8, [rsp+48h+Size]; lpdwBufferLength
0x180011a9f  mov     rdx, rbp; pSelfRelativeSecurityDescriptor
0x180011aa2  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180011aa5  call    cs:__imp_MakeSelfRelativeSD
0x180011aab  test    eax, eax
0x180011aad  jnz     loc_1800119ED
0x180011ab3  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180011ab8  mov     ebx, eax
0x180011aba  test    eax, eax
0x180011abc  jns     loc_1800119ED
0x180011ac2  mov     rcx, rbp; hMem
0x180011ac5  call    cs:__imp_LocalFree
0x180011acb  jmp     loc_1800119F0
```
