# CRpcResolver::GetSystemSecurityDescriptors(tagCOMSD,void * *)

- ea: `0x1801ac954`
- end: `0x1801acaac`
- name: `?GetSystemSecurityDescriptors@CRpcResolver@@QEAAJW4tagCOMSD@@PEAPEAX@Z`
- size: `344`
- prototype: `HRESULT __fastcall(CRpcResolver *this, tagCOMSD comSDType, void **ppSD)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801b3cf0`

## callees

- `0x180006250`
- `0x180006390`
- `0x180028958`
- `0x1801ac954`
- `0x1802135e9`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801ac9ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801aca02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801aca2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801aca5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801ac9ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801aca02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801aca2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801aca5c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801ac9bf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801ac9f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801aca20`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801aca4d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801ac9bf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801ac9f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801aca20`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1801aca4d`

## string_xrefs

- `0x1801ac97d`: `onecore\com\combase\dcomrem\resolver.cxx`

## pseudocode

```c
HRESULT __fastcall CRpcResolver::GetSystemSecurityDescriptors(CRpcResolver *this, tagCOMSD comSDType, void **ppSD)
{
  HRESULT result; // eax
  const char *v6; // r9
  int v7; // ebx
  int v8; // ebx
  SIZE_T SecurityDescriptorLength; // rbx
  HLOCAL v10; // rax
  HLOCAL v11; // rdx
  unsigned int v12; // ebx

  result = CRpcResolver::GetConnection(this);
  if ( result >= 0 )
  {
    *ppSD = 0;
    COleStaticMutexSem::Request(&CRpcResolver::_mxsResolver, "onecore\\com\\combase\\dcomrem\\resolver.cxx", 0xE65u, v6);
    if ( (CRpcResolver::_dwFlags & 1) == 0 )
    {
      v12 = -2147467259;
      goto LABEL_18;
    }
    if ( comSDType )
    {
      v7 = comSDType - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 != 1 )
            goto LABEL_16;
          SecurityDescriptorLength = GetSecurityDescriptorLength(CRpcResolver::_pNoRegAccessRestrictionsSD);
          v10 = LocalAlloc(0x40u, SecurityDescriptorLength);
          *ppSD = v10;
          if ( !v10 )
            goto LABEL_16;
          v11 = CRpcResolver::_pNoRegAccessRestrictionsSD;
          goto LABEL_15;
        }
        SecurityDescriptorLength = GetSecurityDescriptorLength(CRpcResolver::_pNoRegLaunchRestrictionsSD);
        v10 = LocalAlloc(0x40u, SecurityDescriptorLength);
        *ppSD = v10;
        if ( v10 )
        {
          v11 = CRpcResolver::_pNoRegLaunchRestrictionsSD;
LABEL_15:
          memcpy_0(v10, v11, SecurityDescriptorLength);
        }
      }
      else
      {
        SecurityDescriptorLength = GetSecurityDescriptorLength(CRpcResolver::_pNoRegAccessPermissionsSD);
        v10 = LocalAlloc(0x40u, SecurityDescriptorLength);
        *ppSD = v10;
        if ( v10 )
        {
          v11 = CRpcResolver::_pNoRegAccessPermissionsSD;
          goto LABEL_15;
        }
      }
    }
    else
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(CRpcResolver::_pNoRegLaunchPermissionsSD);
      v10 = LocalAlloc(0x40u, SecurityDescriptorLength);
      *ppSD = v10;
      if ( v10 )
      {
        v11 = CRpcResolver::_pNoRegLaunchPermissionsSD;
        goto LABEL_15;
      }
    }
LABEL_16:
    v12 = *ppSD == 0 ? 0x8007000E : 0;
LABEL_18:
    COleStaticMutexSem::Release(&CRpcResolver::_mxsResolver);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x1801ac954  mov     [rsp+arg_0], rbx
0x1801ac959  push    rdi
0x1801ac95a  sub     rsp, 20h
0x1801ac95e  mov     rdi, ppSD
0x1801ac961  mov     ebx, comSDType
0x1801ac963  call    ?GetConnection@CRpcResolver@@QEAAJXZ; CRpcResolver::GetConnection(void)
0x1801ac968  test    eax, eax
0x1801ac96a  js      loc_1801ACAA1
0x1801ac970  mov     r8d, 0E65h; dwLine
0x1801ac976  mov     qword ptr [rdi], 0
0x1801ac97d  lea     rdx, aOnecoreComComb_138; "onecore\\com\\combase\\dcomrem\\resolve"...
0x1801ac984  lea     rcx, ?_mxsResolver@CRpcResolver@@0VCOleStaticMutexSem@@A; this
0x1801ac98b  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x1801ac990  test    byte ptr cs:?_dwFlags@CRpcResolver@@0KA, 1; ulong CRpcResolver::_dwFlags
0x1801ac997  jz      loc_1801ACA8E
0x1801ac99d  test    ebx, ebx
0x1801ac99f  jz      loc_1801ACA46
0x1801ac9a5  sub     ebx, 1
0x1801ac9a8  jz      short loc_1801ACA19
0x1801ac9aa  sub     ebx, 1
0x1801ac9ad  jz      short loc_1801AC9EC
0x1801ac9af  cmp     ebx, 1
0x1801ac9b2  jnz     loc_1801ACA7C
0x1801ac9b8  mov     rcx, cs:?_pNoRegAccessRestrictionsSD@CRpcResolver@@0PEAXEA; pSecurityDescriptor
0x1801ac9bf  call    cs:__imp_GetSecurityDescriptorLength
0x1801ac9c5  mov     comSDType, eax; uBytes
0x1801ac9c7  mov     ecx, 40h ; '@'; uFlags
0x1801ac9cc  mov     ebx, eax
0x1801ac9ce  call    cs:__imp_LocalAlloc
0x1801ac9d4  mov     [rdi], rax
0x1801ac9d7  test    rax, rax
0x1801ac9da  jz      loc_1801ACA7C
0x1801ac9e0  mov     rdx, cs:?_pNoRegAccessRestrictionsSD@CRpcResolver@@0PEAXEA; void * CRpcResolver::_pNoRegAccessRestrictionsSD
0x1801ac9e7  jmp     loc_1801ACA71
0x1801ac9ec  mov     rcx, cs:?_pNoRegLaunchRestrictionsSD@CRpcResolver@@0PEAXEA; pSecurityDescriptor
0x1801ac9f3  call    cs:__imp_GetSecurityDescriptorLength
0x1801ac9f9  mov     comSDType, eax; uBytes
0x1801ac9fb  mov     ecx, 40h ; '@'; uFlags
0x1801aca00  mov     ebx, eax
0x1801aca02  call    cs:__imp_LocalAlloc
0x1801aca08  mov     [rdi], rax
0x1801aca0b  test    rax, rax
0x1801aca0e  jz      short loc_1801ACA7C
0x1801aca10  mov     rdx, cs:?_pNoRegLaunchRestrictionsSD@CRpcResolver@@0PEAXEA; void * CRpcResolver::_pNoRegLaunchRestrictionsSD
0x1801aca17  jmp     short loc_1801ACA71
0x1801aca19  mov     rcx, cs:?_pNoRegAccessPermissionsSD@CRpcResolver@@0PEAXEA; pSecurityDescriptor
0x1801aca20  call    cs:__imp_GetSecurityDescriptorLength
0x1801aca26  mov     comSDType, eax; uBytes
0x1801aca28  mov     ecx, 40h ; '@'; uFlags
0x1801aca2d  mov     ebx, eax
0x1801aca2f  call    cs:__imp_LocalAlloc
0x1801aca35  mov     [rdi], rax
0x1801aca38  test    rax, rax
0x1801aca3b  jz      short loc_1801ACA7C
0x1801aca3d  mov     rdx, cs:?_pNoRegAccessPermissionsSD@CRpcResolver@@0PEAXEA; void * CRpcResolver::_pNoRegAccessPermissionsSD
0x1801aca44  jmp     short loc_1801ACA71
0x1801aca46  mov     rcx, cs:?_pNoRegLaunchPermissionsSD@CRpcResolver@@0PEAXEA; pSecurityDescriptor
0x1801aca4d  call    cs:__imp_GetSecurityDescriptorLength
0x1801aca53  mov     comSDType, eax; uBytes
0x1801aca55  mov     ecx, 40h ; '@'; uFlags
0x1801aca5a  mov     ebx, eax
0x1801aca5c  call    cs:__imp_LocalAlloc
0x1801aca62  mov     [rdi], rax
0x1801aca65  test    rax, rax
0x1801aca68  jz      short loc_1801ACA7C
0x1801aca6a  mov     rdx, cs:?_pNoRegLaunchPermissionsSD@CRpcResolver@@0PEAXEA; Src
0x1801aca71  mov     ppSD, rbx; Size
0x1801aca74  mov     rcx, rax; void *
0x1801aca77  call    memcpy_0
0x1801aca7c  mov     rax, [rdi]
0x1801aca7f  neg     rax
0x1801aca82  sbb     ebx, ebx
0x1801aca84  not     ebx
0x1801aca86  and     ebx, 8007000Eh
0x1801aca8c  jmp     short loc_1801ACA93
0x1801aca8e  mov     ebx, 80004005h
0x1801aca93  lea     rcx, ?_mxsResolver@CRpcResolver@@0VCOleStaticMutexSem@@A; this
0x1801aca9a  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x1801aca9f  mov     eax, ebx
0x1801acaa1  mov     rbx, [rsp+28h+arg_0]
0x1801acaa6  add     rsp, 20h
0x1801acaaa  pop     rdi
0x1801acaab  retn
```
