# InitSecDescInACLDesc(tagACL_DESCRIPTOR *)

- ea: `0x1801cf808`
- end: `0x1801cf97c`
- name: `?InitSecDescInACLDesc@@YAJPEAUtagACL_DESCRIPTOR@@@Z`
- size: `372`
- prototype: `HRESULT __fastcall(tagACL_DESCRIPTOR *pACLDesc)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801955e0`

## callees

- `0x1801cf808`
- `0x1801cfa4c`
- `0x1801cfa68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cf86d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cf86d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf91e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf947`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf91e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801cf947`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801cf829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801cf829`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801cf83a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801cf83a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801cf90b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1801cf90b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801cf8ee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801cf8fc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801cf8ee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801cf8fc`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801cf8c0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801cf8c0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801cf867`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801cf8b3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801cf867`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801cf8b3`

## pseudocode

```c
__int64 __fastcall InitSecDescInACLDesc(tagACL_DESCRIPTOR *pACLDesc)
{
  PSID *v1; // rdi
  void *v3; // rsi
  HANDLE CurrentProcess; // rax
  unsigned int v5; // ebx
  DWORD LengthSid; // ebp
  void *v7; // rbx
  void *v8; // rcx
  __int64 result; // rax
  unsigned int ulLen; // [rsp+58h] [rbp+10h] BYREF
  void *hToken; // [rsp+60h] [rbp+18h] BYREF

  v1 = 0;
  hToken = 0;
  v3 = 0;
  ulLen = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hToken) )
  {
    GetTokenInformation(hToken, TokenUser, 0, 0, &ulLen);
    if ( GetLastError() == 122 )
    {
      v1 = (PSID *)LocalMemAlloc(ulLen);
      if ( !v1 )
      {
LABEL_5:
        v5 = -2147024882;
        goto $Error_14;
      }
      if ( GetTokenInformation(hToken, TokenUser, v1, ulLen, &ulLen) )
      {
        LengthSid = GetLengthSid(*v1);
        v3 = LocalMemAlloc(LengthSid);
        if ( v3 )
        {
          v7 = LocalMemAlloc(LengthSid);
          if ( v7 )
          {
            CopySid(LengthSid, v3, *v1);
            CopySid(LengthSid, v7, *v1);
            InitializeSecurityDescriptor(&pACLDesc->SecDesc, 1u);
            v8 = hToken;
            pACLDesc->SecDesc.Owner = v3;
            pACLDesc->SecDesc.Group = v7;
            CloseHandle(v8);
            LocalMemFree(v1);
            result = 0;
            pACLDesc->bDirtyACL = 1;
            return result;
          }
        }
        goto LABEL_5;
      }
    }
    v5 = -2147417818;
    goto $Error_14;
  }
  v5 = -2147417796;
$Error_14:
  if ( hToken )
    CloseHandle(hToken);
  if ( v1 )
    LocalMemFree(v1);
  if ( v3 )
    LocalMemFree(v3);
  return v5;
}

```

## disassembly

```asm
0x1801cf808  mov     rax, rsp
0x1801cf80b  mov     [rax+8], rbx
0x1801cf80f  mov     [rax+20h], rbp
0x1801cf813  push    rsi
0x1801cf814  push    rdi
0x1801cf815  push    r14
0x1801cf817  sub     rsp, 30h
0x1801cf81b  xor     edi, edi
0x1801cf81d  mov     r14, pACLDesc
0x1801cf820  mov     [rax+18h], rdi
0x1801cf824  xor     esi, esi
0x1801cf826  mov     [rax+10h], edi
0x1801cf829  call    cs:__imp_GetCurrentProcess
0x1801cf82f  mov     pACLDesc, rax; ProcessHandle
0x1801cf832  lea     r8, [rsp+48h+hToken]; TokenHandle
0x1801cf837  lea     edx, [rdi+8]; DesiredAccess
0x1801cf83a  call    cs:__imp_OpenProcessToken
0x1801cf840  test    eax, eax
0x1801cf842  jnz     short loc_1801CF84E
0x1801cf844  mov     ebx, 8001013Ch
0x1801cf849  jmp     $Error_14
0x1801cf84e  mov     pACLDesc, [rsp+48h+hToken]; TokenHandle
0x1801cf853  lea     rax, [rsp+48h+ulLen]
0x1801cf858  xor     r9d, r9d; TokenInformationLength
0x1801cf85b  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1801cf860  xor     r8d, r8d; TokenInformation
0x1801cf863  lea     edx, [r9+1]; TokenInformationClass
0x1801cf867  call    cs:__imp_GetTokenInformation
0x1801cf86d  call    cs:__imp_GetLastError
0x1801cf873  cmp     eax, 7Ah ; 'z'
0x1801cf876  jnz     loc_1801CF938
0x1801cf87c  mov     ecx, [rsp+48h+ulLen]; cb
0x1801cf880  call    ?LocalMemAlloc@@YAPEAX_K@Z; LocalMemAlloc(unsigned __int64)
0x1801cf885  mov     rdi, rax
0x1801cf888  test    rax, rax
0x1801cf88b  jnz     short loc_1801CF897
0x1801cf88d  mov     ebx, 8007000Eh
0x1801cf892  jmp     $Error_14
0x1801cf897  mov     r9d, [rsp+48h+ulLen]; TokenInformationLength
0x1801cf89c  lea     rax, [rsp+48h+ulLen]
0x1801cf8a1  mov     pACLDesc, [rsp+48h+hToken]; TokenHandle
0x1801cf8a6  mov     r8, rdi; TokenInformation
0x1801cf8a9  mov     edx, 1; TokenInformationClass
0x1801cf8ae  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1801cf8b3  call    cs:__imp_GetTokenInformation
0x1801cf8b9  test    eax, eax
0x1801cf8bb  jz      short loc_1801CF938
0x1801cf8bd  mov     pACLDesc, [rdi]; pSid
0x1801cf8c0  call    cs:__imp_GetLengthSid
0x1801cf8c6  mov     ecx, eax; cb
0x1801cf8c8  mov     ebp, eax
0x1801cf8ca  call    ?LocalMemAlloc@@YAPEAX_K@Z; LocalMemAlloc(unsigned __int64)
0x1801cf8cf  mov     rsi, rax
0x1801cf8d2  test    rax, rax
0x1801cf8d5  jz      short loc_1801CF88D
0x1801cf8d7  mov     ecx, ebp; cb
0x1801cf8d9  call    ?LocalMemAlloc@@YAPEAX_K@Z; LocalMemAlloc(unsigned __int64)
0x1801cf8de  mov     rbx, rax
0x1801cf8e1  test    rax, rax
0x1801cf8e4  jz      short loc_1801CF88D
0x1801cf8e6  mov     r8, [rdi]; pSourceSid
0x1801cf8e9  mov     rdx, rsi; pDestinationSid
0x1801cf8ec  mov     ecx, ebp; nDestinationSidLength
0x1801cf8ee  call    cs:__imp_CopySid
0x1801cf8f4  mov     r8, [rdi]; pSourceSid
0x1801cf8f7  mov     rdx, rbx; pDestinationSid
0x1801cf8fa  mov     ecx, ebp; nDestinationSidLength
0x1801cf8fc  call    cs:__imp_CopySid
0x1801cf902  lea     pACLDesc, [r14+18h]; pSecurityDescriptor
0x1801cf906  mov     edx, 1; dwRevision
0x1801cf90b  call    cs:__imp_InitializeSecurityDescriptor
0x1801cf911  mov     pACLDesc, [rsp+48h+hToken]; hObject
0x1801cf916  mov     [r14+20h], rsi
0x1801cf91a  mov     [r14+28h], rbx
0x1801cf91e  call    cs:__imp_CloseHandle
0x1801cf924  mov     pACLDesc, rdi; pBlock
0x1801cf927  call    ?LocalMemFree@@YAXPEAX@Z; LocalMemFree(void *)
0x1801cf92c  xor     eax, eax
0x1801cf92e  mov     dword ptr [r14+10h], 1
0x1801cf936  jmp     short loc_1801CF969
0x1801cf938  mov     ebx, 80010126h
0x1801cf93d  mov     pACLDesc, [rsp+48h+hToken]; hObject
0x1801cf942  test    pACLDesc, pACLDesc
0x1801cf945  jz      short loc_1801CF94D
0x1801cf947  call    cs:__imp_CloseHandle
0x1801cf94d  test    rdi, rdi
0x1801cf950  jz      short loc_1801CF95A
0x1801cf952  mov     pACLDesc, rdi; pBlock
0x1801cf955  call    ?LocalMemFree@@YAXPEAX@Z; LocalMemFree(void *)
0x1801cf95a  test    rsi, rsi
0x1801cf95d  jz      short loc_1801CF967
0x1801cf95f  mov     pACLDesc, rsi; pBlock
0x1801cf962  call    ?LocalMemFree@@YAXPEAX@Z; LocalMemFree(void *)
0x1801cf967  mov     eax, ebx
0x1801cf969  mov     rbx, [rsp+48h+arg_0]
0x1801cf96e  mov     rbp, [rsp+48h+arg_18]
0x1801cf973  add     rsp, 30h
0x1801cf977  pop     r14
0x1801cf979  pop     rdi
0x1801cf97a  pop     rsi
0x1801cf97b  retn
```
