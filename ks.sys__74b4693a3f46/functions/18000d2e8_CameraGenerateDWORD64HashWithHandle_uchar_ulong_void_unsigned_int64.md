# CameraGenerateDWORD64HashWithHandle(uchar *,ulong,void *,unsigned __int64 *)

- ea: `0x18000d2e8`
- end: `0x18000d4a7`
- name: `?CameraGenerateDWORD64HashWithHandle@@YAJPEAEKPEAXPEA_K@Z`
- size: `447`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, BCRYPT_HANDLE hObject, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ec10`

## callees

- `0x18000d2e8`
- `0x18000d4b0`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x18000d482`
- `ntoskrnl!ExFreePool` at `0x18000d496`
- `ntoskrnl!ExFreePool` at `0x18000d482`
- `ntoskrnl!ExFreePool` at `0x18000d496`
- `ksecdd!BCryptCreateHash` at `0x18000d3fa`
- `ksecdd!BCryptCreateHash` at `0x18000d3fa`
- `ksecdd!BCryptFinishHash` at `0x18000d376`
- `ksecdd!BCryptFinishHash` at `0x18000d376`
- `ksecdd!BCryptDestroyHash` at `0x18000d3c9`
- `ksecdd!BCryptDestroyHash` at `0x18000d3c9`
- `ksecdd!BCryptHashData` at `0x18000d419`
- `ksecdd!BCryptHashData` at `0x18000d419`
- `ksecdd!BCryptGetProperty` at `0x18000d33d`
- `ksecdd!BCryptGetProperty` at `0x18000d450`
- `ksecdd!BCryptGetProperty` at `0x18000d33d`
- `ksecdd!BCryptGetProperty` at `0x18000d450`

## pseudocode

```c
__int64 __fastcall CameraGenerateDWORD64HashWithHandle(
        PUCHAR pbInput,
        ULONG cbInput,
        BCRYPT_HANDLE hObject,
        unsigned __int64 *a4)
{
  UCHAR *v5; // rdi
  UCHAR *Pool; // rsi
  bool v10; // cl
  NTSTATUS Property; // ebx
  unsigned int v12; // r8d
  bool v14; // cl
  unsigned int v15; // r8d
  UCHAR *v16; // rax
  ULONG cbOutput; // [rsp+40h] [rbp-28h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+48h] [rbp-20h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-18h]
  ULONG pbOutput; // [rsp+C8h] [rbp+60h] BYREF

  v5 = 0;
  *a4 = 0;
  hHash = 0;
  Pool = 0;
  pbOutput = 0;
  cbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hObject, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    Pool = (UCHAR *)CameraHashingUtilsAllocatePoolEx(v10, pbOutput, v12);
    if ( !Pool )
    {
LABEL_3:
      Property = -1073741670;
      goto LABEL_6;
    }
    Property = BCryptCreateHash(hObject, &hHash, Pool, pbOutput, 0, 0, 0);
    if ( Property >= 0 )
    {
      Property = BCryptHashData(hHash, pbInput, cbInput, 0);
      if ( Property >= 0 )
      {
        Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&cbOutput, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          v16 = (UCHAR *)CameraHashingUtilsAllocatePoolEx(v14, cbOutput, v15);
          v5 = v16;
          if ( !v16 )
            goto LABEL_3;
          Property = BCryptFinishHash(hHash, v16, cbOutput, 0);
          if ( Property >= 0 )
          {
            LODWORD(v20) = *((_DWORD *)v5 + 1);
            HIDWORD(v20) = *(_DWORD *)v5;
            *a4 = v20;
          }
        }
      }
    }
  }
LABEL_6:
  if ( hHash )
  {
    BCryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( Pool )
    ExFreePool(Pool);
  if ( v5 )
    ExFreePool(v5);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18000d2e8  push    rbp
0x18000d2ea  push    rbx
0x18000d2eb  push    rsi
0x18000d2ec  push    rdi
0x18000d2ed  push    r12
0x18000d2ef  push    r13
0x18000d2f1  push    r14
0x18000d2f3  push    r15
0x18000d2f5  mov     rbp, rsp
0x18000d2f8  sub     rsp, 68h
0x18000d2fc  xor     eax, eax
0x18000d2fe  mov     r14, r8
0x18000d301  mov     edi, eax
0x18000d303  mov     [r9], rax
0x18000d306  mov     [rsp+68h+dwFlags], eax; dwFlags
0x18000d30a  lea     r8, [rbp+pbOutput]; pbOutput
0x18000d30e  mov     [rbp+hHash], rax
0x18000d312  mov     esi, eax
0x18000d314  mov     [rbp+pbOutput], eax
0x18000d317  mov     r15, r9
0x18000d31a  mov     [rbp+cbOutput], eax
0x18000d31d  lea     r9d, [rdi+4]; cbOutput
0x18000d321  mov     [rbp+var_24], eax
0x18000d324  mov     r12d, edx
0x18000d327  mov     r13, rcx
0x18000d32a  lea     rax, [rbp+var_24]
0x18000d32e  lea     rdx, pszProperty; "ObjectLength"
0x18000d335  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18000d33a  mov     rcx, r14; hObject
0x18000d33d  call    cs:__imp_BCryptGetProperty
0x18000d344  nop     dword ptr [rax+rax+00h]
0x18000d349  mov     ebx, eax
0x18000d34b  test    eax, eax
0x18000d34d  js      short loc_18000D39A
0x18000d34f  mov     edx, [rbp+pbOutput]; unsigned __int64
0x18000d352  call    ?CameraHashingUtilsAllocatePoolEx@@YAPEAX_N_KK@Z; CameraHashingUtilsAllocatePoolEx(bool,unsigned __int64,ulong)
0x18000d357  mov     rsi, rax
0x18000d35a  xor     eax, eax
0x18000d35c  test    rsi, rsi
0x18000d35f  jnz     short loc_18000D3DF
0x18000d361  mov     ebx, 0C000009Ah
0x18000d366  jmp     short loc_18000D39A
0x18000d368  mov     r8d, [rbp+cbOutput]; cbOutput
0x18000d36c  xor     r9d, r9d; dwFlags
0x18000d36f  mov     rcx, [rbp+hHash]; hHash
0x18000d373  mov     rdx, rdi; pbOutput
0x18000d376  call    cs:__imp_BCryptFinishHash
0x18000d37d  nop     dword ptr [rax+rax+00h]
0x18000d382  mov     ebx, eax
0x18000d384  test    eax, eax
0x18000d386  js      short loc_18000D39A
0x18000d388  mov     eax, [rdi+4]
0x18000d38b  mov     dword ptr [rbp+var_18], eax
0x18000d38e  mov     eax, [rdi]
0x18000d390  mov     dword ptr [rbp+var_18+4], eax
0x18000d393  mov     rax, [rbp+var_18]
0x18000d397  mov     [r15], rax
0x18000d39a  mov     rcx, [rbp+hHash]; hHash
0x18000d39e  test    rcx, rcx
0x18000d3a1  jnz     short loc_18000D3C9
0x18000d3a3  test    rsi, rsi
0x18000d3a6  jnz     loc_18000D47F
0x18000d3ac  test    rdi, rdi
0x18000d3af  jnz     loc_18000D493
0x18000d3b5  mov     eax, ebx
0x18000d3b7  add     rsp, 68h
0x18000d3bb  pop     r15
0x18000d3bd  pop     r14
0x18000d3bf  pop     r13
0x18000d3c1  pop     r12
0x18000d3c3  pop     rdi
0x18000d3c4  pop     rsi
0x18000d3c5  pop     rbx
0x18000d3c6  pop     rbp
0x18000d3c7  retn
0x18000d3c9  call    cs:__imp_BCryptDestroyHash
0x18000d3d0  nop     dword ptr [rax+rax+00h]
0x18000d3d5  mov     [rbp+hHash], 0
0x18000d3dd  jmp     short loc_18000D3A3
0x18000d3df  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18000d3e3  lea     rdx, [rbp+hHash]; phHash
0x18000d3e7  mov     [rsp+68h+var_38], eax; dwFlags
0x18000d3eb  mov     r8, rsi; pbHashObject
0x18000d3ee  mov     [rsp+68h+dwFlags], eax; cbSecret
0x18000d3f2  mov     rcx, r14; hAlgorithm
0x18000d3f5  mov     [rsp+68h+pcbResult], rax; pbSecret
0x18000d3fa  call    cs:__imp_BCryptCreateHash
0x18000d401  nop     dword ptr [rax+rax+00h]
0x18000d406  mov     ebx, eax
0x18000d408  test    eax, eax
0x18000d40a  js      short loc_18000D39A
0x18000d40c  mov     rcx, [rbp+hHash]; hHash
0x18000d410  xor     r9d, r9d; dwFlags
0x18000d413  mov     r8d, r12d; cbInput
0x18000d416  mov     rdx, r13; pbInput
0x18000d419  call    cs:__imp_BCryptHashData
0x18000d420  nop     dword ptr [rax+rax+00h]
0x18000d425  mov     ebx, eax
0x18000d427  test    eax, eax
0x18000d429  js      loc_18000D39A
0x18000d42f  lea     rax, [rbp+var_24]
0x18000d433  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18000d437  mov     r9d, 4; cbOutput
0x18000d43d  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18000d442  lea     r8, [rbp+cbOutput]; pbOutput
0x18000d446  mov     rcx, r14; hObject
0x18000d449  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000d450  call    cs:__imp_BCryptGetProperty
0x18000d457  nop     dword ptr [rax+rax+00h]
0x18000d45c  mov     ebx, eax
0x18000d45e  test    eax, eax
0x18000d460  js      loc_18000D39A
0x18000d466  mov     edx, [rbp+cbOutput]; unsigned __int64
0x18000d469  call    ?CameraHashingUtilsAllocatePoolEx@@YAPEAX_N_KK@Z; CameraHashingUtilsAllocatePoolEx(bool,unsigned __int64,ulong)
0x18000d46e  mov     rdi, rax
0x18000d471  test    rax, rax
0x18000d474  jnz     loc_18000D368
0x18000d47a  jmp     loc_18000D361
0x18000d47f  mov     rcx, rsi; P
0x18000d482  call    cs:__imp_ExFreePool
0x18000d489  nop     dword ptr [rax+rax+00h]
0x18000d48e  jmp     loc_18000D3AC
0x18000d493  mov     rcx, rdi; P
0x18000d496  call    cs:__imp_ExFreePool
0x18000d49d  nop     dword ptr [rax+rax+00h]
0x18000d4a2  jmp     loc_18000D3B5
```
