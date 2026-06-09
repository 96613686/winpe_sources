# CNG_ComputeHash

- ea: `0x18001c690`
- end: `0x18001c808`
- name: `CNG_ComputeHash`
- size: `376`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, size_t Size, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001550`
- `0x180016e90`

## callees

- `0x180005fa0`
- `0x18000e120`
- `0x18001c690`
- `0x18001f175`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001c7a0`
- `bcrypt!BCryptHashData` at `0x18001c7a0`
- `bcrypt!BCryptDestroyHash` at `0x18001c7f3`
- `bcrypt!BCryptDestroyHash` at `0x18001c7f3`
- `bcrypt!BCryptCreateHash` at `0x18001c77e`
- `bcrypt!BCryptCreateHash` at `0x18001c77e`
- `bcrypt!BCryptFinishHash` at `0x18001c7c2`
- `bcrypt!BCryptFinishHash` at `0x18001c7c2`
- `bcrypt!BCryptGetProperty` at `0x18001c725`
- `bcrypt!BCryptGetProperty` at `0x18001c725`

## string_xrefs

- `0x18001c7d6`: `onecore\ds\security\cryptoapi\ncrypt\common\provider.c`

## pseudocode

```c
__int64 __fastcall CNG_ComputeHash(PUCHAR pbInput, ULONG cbInput, __int64 a3, void *a4, size_t Size, ULONG *pbOutput)
{
  ULONG v6; // esi
  unsigned int v7; // ebx
  unsigned int BCryptHandle; // eax
  __int64 v13; // r9
  ULONG *v14; // rdi
  __int64 v15; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_HANDLE hObject[8]; // [rsp+48h] [rbp-40h] BYREF
  ULONG pcbResult; // [rsp+90h] [rbp+8h] BYREF

  v6 = Size;
  v7 = 0;
  hObject[0] = 0;
  phHash = 0;
  pcbResult = 0;
  memset_0(a4, 0, (unsigned int)Size);
  if ( !pbInput )
    return v7;
  BCryptHandle = CNG_GetBCryptHandle(a3, hObject);
  v7 = BCryptHandle;
  if ( BCryptHandle )
  {
    v13 = 178;
LABEL_14:
    v15 = BCryptHandle;
    goto LABEL_15;
  }
  v14 = pbOutput;
  BCryptHandle = BCryptGetProperty(hObject[0], L"HashDigestLength", (PUCHAR)pbOutput, 4u, &pcbResult, 0);
  v7 = BCryptHandle;
  if ( BCryptHandle )
  {
    v13 = 192;
    goto LABEL_14;
  }
  if ( v6 >= *v14 )
  {
    BCryptHandle = BCryptCreateHash(hObject[0], &phHash, 0, 0, 0, 0, 0);
    v7 = BCryptHandle;
    if ( BCryptHandle )
    {
      v13 = 213;
    }
    else
    {
      BCryptHandle = BCryptHashData(phHash, pbInput, cbInput, 0);
      v7 = BCryptHandle;
      if ( BCryptHandle )
      {
        v13 = 224;
      }
      else
      {
        BCryptHandle = BCryptFinishHash(phHash, (PUCHAR)a4, *v14, 0);
        v7 = BCryptHandle;
        if ( !BCryptHandle )
          goto LABEL_16;
        v13 = 236;
      }
    }
    goto LABEL_14;
  }
  v7 = -2146893784;
  v13 = 199;
  v15 = 2148073512LL;
LABEL_15:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\provider.c", v13);
LABEL_16:
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v7;
}

```

## disassembly

```asm
0x18001c690  mov     rax, rsp
0x18001c693  push    rbx
0x18001c694  push    rbp
0x18001c695  push    rsi
0x18001c696  push    rdi
0x18001c697  push    r14
0x18001c699  push    r15
0x18001c69b  sub     rsp, 58h
0x18001c69f  mov     esi, dword ptr [rsp+88h+Size]
0x18001c6a6  xor     ebx, ebx
0x18001c6a8  mov     rdi, r8
0x18001c6ab  mov     [rax-40h], rbx
0x18001c6af  mov     r15d, edx
0x18001c6b2  mov     [rax-48h], rbx
0x18001c6b6  mov     r14, rcx
0x18001c6b9  mov     [rax+8], ebx
0x18001c6bc  mov     r8d, esi; Size
0x18001c6bf  xor     edx, edx; Val
0x18001c6c1  mov     rcx, r9; void *
0x18001c6c4  mov     rbp, r9
0x18001c6c7  call    memset_0
0x18001c6cc  test    r14, r14
0x18001c6cf  jz      loc_18001C7F9
0x18001c6d5  lea     rdx, [rsp+88h+hObject]
0x18001c6da  mov     rcx, rdi
0x18001c6dd  call    CNG_GetBCryptHandle
0x18001c6e2  mov     ebx, eax
0x18001c6e4  test    eax, eax
0x18001c6e6  jz      short loc_18001C6F3
0x18001c6e8  mov     r9d, 0B2h
0x18001c6ee  jmp     loc_18001C7D4
0x18001c6f3  mov     rdi, [rsp+88h+pbOutput]
0x18001c6fb  lea     rax, [rsp+88h+arg_0]
0x18001c703  mov     rcx, [rsp+88h+hObject]; hObject
0x18001c708  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001c70f  mov     r8, rdi; pbOutput
0x18001c712  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18001c71a  mov     r9d, 4; cbOutput
0x18001c720  mov     [rsp+88h+pcbResult], rax; pcbResult
0x18001c725  call    cs:__imp_BCryptGetProperty
0x18001c72b  mov     ebx, eax
0x18001c72d  test    eax, eax
0x18001c72f  jz      short loc_18001C73C
0x18001c731  mov     r9d, 0C0h
0x18001c737  jmp     loc_18001C7D4
0x18001c73c  cmp     esi, [rdi]
0x18001c73e  jnb     short loc_18001C755
0x18001c740  mov     ebx, 80090028h
0x18001c745  mov     r9d, 0C7h
0x18001c74b  mov     ecx, 80090028h
0x18001c750  jmp     loc_18001C7D6
0x18001c755  mov     rcx, [rsp+88h+hObject]; hAlgorithm
0x18001c75a  lea     rdx, [rsp+88h+phHash]; phHash
0x18001c75f  mov     [rsp+88h+var_58], 0; dwFlags
0x18001c767  xor     r9d, r9d; cbHashObject
0x18001c76a  mov     [rsp+88h+dwFlags], 0; cbSecret
0x18001c772  xor     r8d, r8d; pbHashObject
0x18001c775  mov     [rsp+88h+pcbResult], 0; pbSecret
0x18001c77e  call    cs:__imp_BCryptCreateHash
0x18001c784  mov     ebx, eax
0x18001c786  test    eax, eax
0x18001c788  jz      short loc_18001C792
0x18001c78a  mov     r9d, 0D5h
0x18001c790  jmp     short loc_18001C7D4
0x18001c792  mov     rcx, [rsp+88h+phHash]; hHash
0x18001c797  xor     r9d, r9d; dwFlags
0x18001c79a  mov     r8d, r15d; cbInput
0x18001c79d  mov     rdx, r14; pbInput
0x18001c7a0  call    cs:__imp_BCryptHashData
0x18001c7a6  mov     ebx, eax
0x18001c7a8  test    eax, eax
0x18001c7aa  jz      short loc_18001C7B4
0x18001c7ac  mov     r9d, 0E0h
0x18001c7b2  jmp     short loc_18001C7D4
0x18001c7b4  mov     r8d, [rdi]; cbOutput
0x18001c7b7  xor     r9d, r9d; dwFlags
0x18001c7ba  mov     rcx, [rsp+88h+phHash]; hHash
0x18001c7bf  mov     rdx, rbp; pbOutput
0x18001c7c2  call    cs:__imp_BCryptFinishHash
0x18001c7c8  mov     ebx, eax
0x18001c7ca  test    eax, eax
0x18001c7cc  jz      short loc_18001C7E9
0x18001c7ce  mov     r9d, 0ECh
0x18001c7d4  mov     ecx, eax
0x18001c7d6  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001c7dd  lea     rdx, aStatus; "Status"
0x18001c7e4  call    DebugTraceError
0x18001c7e9  mov     rcx, [rsp+88h+phHash]; hHash
0x18001c7ee  test    rcx, rcx
0x18001c7f1  jz      short loc_18001C7F9
0x18001c7f3  call    cs:__imp_BCryptDestroyHash
0x18001c7f9  mov     eax, ebx
0x18001c7fb  add     rsp, 58h
0x18001c7ff  pop     r15
0x18001c801  pop     r14
0x18001c803  pop     rdi
0x18001c804  pop     rsi
0x18001c805  pop     rbp
0x18001c806  pop     rbx
0x18001c807  retn
```
