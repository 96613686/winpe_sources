# EdpResolveAppHashForAppKeyCaching

- ea: `0x180003854`
- end: `0x180003b6c`
- name: `EdpResolveAppHashForAppKeyCaching`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004630`

## callees

- `0x180003854`
- `0x18000b230`
- `0x18000b4e4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003b15`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003959`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b37`
- `bcrypt!BCryptFinishHash` at `0x180003a5c`
- `bcrypt!BCryptFinishHash` at `0x180003af0`
- `bcrypt!BCryptFinishHash` at `0x180003a5c`
- `bcrypt!BCryptFinishHash` at `0x180003af0`
- `bcrypt!BCryptCreateHash` at `0x180003a11`
- `bcrypt!BCryptCreateHash` at `0x180003a96`
- `bcrypt!BCryptCreateHash` at `0x180003a11`
- `bcrypt!BCryptCreateHash` at `0x180003a96`
- `bcrypt!BCryptHashData` at `0x180003a3f`
- `bcrypt!BCryptHashData` at `0x180003ab3`
- `bcrypt!BCryptHashData` at `0x180003ad0`
- `bcrypt!BCryptHashData` at `0x180003a3f`
- `bcrypt!BCryptHashData` at `0x180003ab3`
- `bcrypt!BCryptHashData` at `0x180003ad0`
- `bcrypt!BCryptDestroyHash` at `0x180003a6c`
- `bcrypt!BCryptDestroyHash` at `0x180003b28`
- `bcrypt!BCryptDestroyHash` at `0x180003a6c`
- `bcrypt!BCryptDestroyHash` at `0x180003b28`

## pseudocode

```c
__int64 __fastcall EdpResolveAppHashForAppKeyCaching(void *a1, UCHAR *a2, __int64 a3, __int64 a4)
{
  UCHAR *v4; // rax
  UCHAR *v7; // rsi
  unsigned int v8; // ebx
  __int64 v9; // rcx
  unsigned __int64 v10; // r12
  RPC_STATUS v11; // ebx
  int v12; // eax
  __int64 v13; // rcx
  PUCHAR v14; // rax
  unsigned __int64 v15; // rdi
  NTSTATUS v16; // eax
  bool v17; // cc
  HANDLE ProcessHeap; // rax
  _DWORD v20[2]; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  void *ClientProcess; // [rsp+50h] [rbp-10h] BYREF
  PUCHAR v23; // [rsp+58h] [rbp-8h]

  v4 = a2;
  v20[0] = 1;
  ClientProcess = 0;
  v20[1] = 0;
  v7 = 0;
  v23 = 0;
  phHash = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  if ( !a3 || !a4 )
    return (unsigned int)-2147467261;
  *(_OWORD *)a3 = 0;
  *(_OWORD *)(a3 + 16) = 0;
  v9 = 0x7FFFFFFF;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  do
  {
    if ( !*(_WORD *)v4 )
      break;
    v4 += 2;
    --v9;
  }
  while ( v9 );
  v8 = v9 == 0 ? 0x80070057 : 0;
  if ( v9 )
  {
    v10 = (2 * (0x7FFFFFFF - v9)) & -(__int64)(v9 != 0);
    if ( v10 > 0xFFFFFFFF )
      return (unsigned int)-2147024362;
    if ( (unsigned int)v10 < 2 )
      return 1;
    if ( !(unsigned int)EfsDplAppKeyCachingFeatureEnabled(v20) )
      goto LABEL_14;
    v11 = I_RpcOpenClientProcess(a1, 0x1000u, &ClientProcess);
    if ( v11 )
    {
      v8 = v11 | 0x80010000;
      goto LABEL_38;
    }
    v12 = EfsResolveProcessInfo(ClientProcess);
    v7 = v23;
    v8 = v12;
    if ( v12 < 0 )
      goto LABEL_38;
    if ( v23 )
    {
      v13 = 0x7FFFFFFF;
      v14 = v23;
      do
      {
        if ( !*(_WORD *)v14 )
          break;
        v14 += 2;
        --v13;
      }
      while ( v13 );
      v8 = v13 == 0 ? 0x80070057 : 0;
      if ( !v13 )
        goto LABEL_38;
      v15 = (2 * (0x7FFFFFFF - v13)) & -(__int64)(v13 != 0);
      if ( v15 > 0xFFFFFFFF )
      {
        v8 = -2147024362;
        goto LABEL_38;
      }
      if ( (unsigned int)v15 >= 2 )
      {
        v16 = BCryptCreateHash(g_hSha256Alg, &phHash, 0, 0, 0, 0, 0);
        v8 = v16;
        v17 = v16 <= 0;
        if ( v16 )
          goto LABEL_27;
        v16 = BCryptHashData(phHash, a2, v10, 0);
        v8 = v16;
        v17 = v16 <= 0;
        if ( v16 )
          goto LABEL_27;
        v16 = BCryptFinishHash(phHash, (PUCHAR)a3, 0x20u, 0);
        v8 = v16;
        v17 = v16 <= 0;
        if ( v16 )
          goto LABEL_27;
        BCryptDestroyHash(phHash);
        phHash = 0;
        v16 = BCryptCreateHash(g_hSha256Alg, &phHash, 0, 0, 0, 0, 0);
        v8 = v16;
        v17 = v16 <= 0;
        if ( v16
          || (v16 = BCryptHashData(phHash, (PUCHAR)a3, 0x20u, 0), v8 = v16, v17 = v16 <= 0, v16)
          || (v16 = BCryptHashData(phHash, v7, v15, 0), v8 = v16, v17 = v16 <= 0, v16) )
        {
LABEL_27:
          if ( v17 )
            goto LABEL_38;
        }
        else
        {
          v8 = 0;
          v16 = BCryptFinishHash(phHash, (PUCHAR)a4, 0x20u, 0);
          if ( !v16 )
            goto LABEL_38;
          if ( v16 <= 0 )
          {
            v8 = v16;
            goto LABEL_38;
          }
        }
        v8 = (unsigned __int16)v16 | 0x80070000;
        goto LABEL_38;
      }
      v8 = 1;
    }
    else
    {
LABEL_14:
      v8 = 1;
    }
LABEL_38:
    if ( ClientProcess )
    {
      CloseHandle(ClientProcess);
      ClientProcess = 0;
    }
    if ( phHash )
    {
      BCryptDestroyHash(phHash);
      phHash = 0;
    }
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180003854  mov     [rsp-38h+arg_10], rbx
0x180003859  mov     [rsp-38h+pbInput], rdx
0x18000385e  mov     [rsp-38h+Binding], rcx
0x180003863  push    rbp
0x180003864  push    rsi
0x180003865  push    rdi
0x180003866  push    r12
0x180003868  push    r13
0x18000386a  push    r14
0x18000386c  push    r15
0x18000386e  mov     rbp, rsp
0x180003871  sub     rsp, 60h
0x180003875  mov     rax, rdx
0x180003878  mov     [rbp+var_20], 1
0x18000387f  xor     edx, edx
0x180003881  mov     r13, r9
0x180003884  mov     [rbp+ClientProcess], rdx
0x180003888  mov     r15, r8
0x18000388b  mov     [rbp+var_1C], edx
0x18000388e  mov     esi, edx
0x180003890  mov     [rbp+var_8], rdx
0x180003894  mov     [rbp+phHash], rdx
0x180003898  test    rax, rax
0x18000389b  jnz     short loc_1800038A7
0x18000389d  mov     ebx, 80070057h
0x1800038a2  jmp     loc_180003B52
0x1800038a7  test    r15, r15
0x1800038aa  jnz     short loc_1800038B6
0x1800038ac  mov     ebx, 80004003h
0x1800038b1  jmp     loc_180003B52
0x1800038b6  test    r13, r13
0x1800038b9  jz      short loc_1800038AC
0x1800038bb  xorps   xmm0, xmm0
0x1800038be  xorps   xmm1, xmm1
0x1800038c1  movups  xmmword ptr [r8], xmm0
0x1800038c5  mov     r14d, 7FFFFFFFh
0x1800038cb  movups  xmmword ptr [r8+10h], xmm0
0x1800038d0  mov     ecx, r14d
0x1800038d3  movups  xmmword ptr [r9], xmm1
0x1800038d7  movups  xmmword ptr [r9+10h], xmm1
0x1800038dc  cmp     [rax], dx
0x1800038df  jz      short loc_1800038EB
0x1800038e1  add     rax, 2
0x1800038e5  sub     rcx, 1
0x1800038e9  jnz     short loc_1800038DC
0x1800038eb  mov     rax, rcx
0x1800038ee  mov     edi, 80070057h
0x1800038f3  neg     rax
0x1800038f6  sbb     ebx, ebx
0x1800038f8  not     ebx
0x1800038fa  and     ebx, edi
0x1800038fc  test    rcx, rcx
0x1800038ff  jz      loc_180003B52
0x180003905  mov     rax, r14
0x180003908  sub     rax, rcx
0x18000390b  add     rax, rax
0x18000390e  neg     rcx
0x180003911  sbb     r12, r12
0x180003914  and     r12, rax
0x180003917  mov     eax, 0FFFFFFFFh
0x18000391c  cmp     r12, rax
0x18000391f  ja      loc_180003B4D
0x180003925  cmp     r12d, 2
0x180003929  jnb     short loc_180003935
0x18000392b  mov     ebx, 1
0x180003930  jmp     loc_180003B52
0x180003935  lea     rcx, [rbp+var_20]
0x180003939  call    EfsDplAppKeyCachingFeatureEnabled
0x18000393e  test    eax, eax
0x180003940  jnz     short loc_18000394C
0x180003942  mov     ebx, 1
0x180003947  jmp     loc_180003B09
0x18000394c  mov     rcx, [rbp+Binding]; Binding
0x180003950  lea     r8, [rbp+ClientProcess]; ClientProcess
0x180003954  mov     edx, 1000h; DesiredAccess
0x180003959  call    cs:__imp_I_RpcOpenClientProcess
0x18000395f  mov     ebx, eax
0x180003961  test    eax, eax
0x180003963  jz      short loc_180003970
0x180003965  or      ebx, 80010000h
0x18000396b  jmp     loc_180003B09
0x180003970  mov     edx, [rbp+var_20]
0x180003973  lea     r9, [rbp+var_8]
0x180003977  mov     rcx, [rbp+ClientProcess]; ProcessHandle
0x18000397b  lea     r8, [rbp+var_1C]
0x18000397f  call    EfsResolveProcessInfo
0x180003984  mov     rsi, [rbp+var_8]
0x180003988  xor     edx, edx
0x18000398a  mov     ebx, eax
0x18000398c  test    eax, eax
0x18000398e  js      loc_180003B09
0x180003994  test    rsi, rsi
0x180003997  jz      short loc_180003942
0x180003999  mov     rcx, r14
0x18000399c  mov     rax, rsi
0x18000399f  cmp     [rax], dx
0x1800039a2  jz      short loc_1800039AE
0x1800039a4  add     rax, 2
0x1800039a8  sub     rcx, 1
0x1800039ac  jnz     short loc_18000399F
0x1800039ae  mov     rax, rcx
0x1800039b1  neg     rax
0x1800039b4  sbb     ebx, ebx
0x1800039b6  not     ebx
0x1800039b8  and     ebx, edi
0x1800039ba  test    rcx, rcx
0x1800039bd  jz      loc_180003B09
0x1800039c3  sub     r14, rcx
0x1800039c6  mov     eax, 0FFFFFFFFh
0x1800039cb  add     r14, r14
0x1800039ce  neg     rcx
0x1800039d1  sbb     rdi, rdi
0x1800039d4  and     rdi, r14
0x1800039d7  cmp     rdi, rax
0x1800039da  ja      loc_180003B04
0x1800039e0  xor     r14d, r14d
0x1800039e3  cmp     edi, 2
0x1800039e6  jnb     short loc_1800039F1
0x1800039e8  lea     ebx, [r14+1]
0x1800039ec  jmp     loc_180003B0C
0x1800039f1  mov     rcx, cs:g_hSha256Alg; hAlgorithm
0x1800039f8  lea     rdx, [rbp+phHash]; phHash
0x1800039fc  mov     [rsp+60h+dwFlags], r14d; dwFlags
0x180003a01  xor     r9d, r9d; cbHashObject
0x180003a04  mov     [rsp+60h+cbSecret], r14d; cbSecret
0x180003a09  xor     r8d, r8d; pbHashObject
0x180003a0c  mov     [rsp+60h+pbSecret], r14; pbSecret
0x180003a11  call    cs:__imp_BCryptCreateHash
0x180003a17  mov     ebx, eax
0x180003a19  test    eax, eax
0x180003a1b  jz      short loc_180003A31
0x180003a1d  jle     loc_180003B0C
0x180003a23  movzx   ebx, ax
0x180003a26  or      ebx, 80070000h
0x180003a2c  jmp     loc_180003B0C
0x180003a31  mov     rdx, [rbp+pbInput]; pbInput
0x180003a35  xor     r9d, r9d; dwFlags
0x180003a38  mov     rcx, [rbp+phHash]; hHash
0x180003a3c  mov     r8d, r12d; cbInput
0x180003a3f  call    cs:__imp_BCryptHashData
0x180003a45  mov     ebx, eax
0x180003a47  test    eax, eax
0x180003a49  jnz     short loc_180003A1D
0x180003a4b  mov     rcx, [rbp+phHash]; hHash
0x180003a4f  lea     r12d, [rax+20h]
0x180003a53  mov     r8d, r12d; cbOutput
0x180003a56  xor     r9d, r9d; dwFlags
0x180003a59  mov     rdx, r15; pbOutput
0x180003a5c  call    cs:__imp_BCryptFinishHash
0x180003a62  mov     ebx, eax
0x180003a64  test    eax, eax
0x180003a66  jnz     short loc_180003A1D
0x180003a68  mov     rcx, [rbp+phHash]; hHash
0x180003a6c  call    cs:__imp_BCryptDestroyHash
0x180003a72  mov     rcx, cs:g_hSha256Alg; hAlgorithm
0x180003a79  lea     rdx, [rbp+phHash]; phHash
0x180003a7d  mov     [rsp+60h+dwFlags], r14d; dwFlags
0x180003a82  xor     r9d, r9d; cbHashObject
0x180003a85  mov     [rsp+60h+cbSecret], r14d; cbSecret
0x180003a8a  xor     r8d, r8d; pbHashObject
0x180003a8d  mov     [rsp+60h+pbSecret], r14; pbSecret
0x180003a92  mov     [rbp+phHash], r14
0x180003a96  call    cs:__imp_BCryptCreateHash
0x180003a9c  mov     ebx, eax
0x180003a9e  test    eax, eax
0x180003aa0  jnz     loc_180003A1D
0x180003aa6  mov     rcx, [rbp+phHash]; hHash
0x180003aaa  xor     r9d, r9d; dwFlags
0x180003aad  mov     r8d, r12d; cbInput
0x180003ab0  mov     rdx, r15; pbInput
0x180003ab3  call    cs:__imp_BCryptHashData
0x180003ab9  mov     ebx, eax
0x180003abb  test    eax, eax
0x180003abd  jnz     loc_180003A1D
0x180003ac3  mov     rcx, [rbp+phHash]; hHash
0x180003ac7  xor     r9d, r9d; dwFlags
0x180003aca  mov     r8d, edi; cbInput
0x180003acd  mov     rdx, rsi; pbInput
0x180003ad0  call    cs:__imp_BCryptHashData
0x180003ad6  mov     ebx, eax
0x180003ad8  test    eax, eax
0x180003ada  jnz     loc_180003A1D
0x180003ae0  mov     rcx, [rbp+phHash]; hHash
0x180003ae4  xor     r9d, r9d; dwFlags
0x180003ae7  mov     r8d, r12d; cbOutput
0x180003aea  mov     rdx, r13; pbOutput
0x180003aed  mov     ebx, r14d
0x180003af0  call    cs:__imp_BCryptFinishHash
0x180003af6  test    eax, eax
0x180003af8  jz      short loc_180003B0C
0x180003afa  jg      loc_180003A23
0x180003b00  mov     ebx, eax
0x180003b02  jmp     short loc_180003B0C
0x180003b04  mov     ebx, 80070216h
0x180003b09  xor     r14d, r14d
0x180003b0c  mov     rcx, [rbp+ClientProcess]; hObject
0x180003b10  test    rcx, rcx
0x180003b13  jz      short loc_180003B1F
0x180003b15  call    cs:__imp_CloseHandle
0x180003b1b  mov     [rbp+ClientProcess], r14
0x180003b1f  mov     rcx, [rbp+phHash]; hHash
0x180003b23  test    rcx, rcx
0x180003b26  jz      short loc_180003B32
0x180003b28  call    cs:__imp_BCryptDestroyHash
0x180003b2e  mov     [rbp+phHash], r14
0x180003b32  test    rsi, rsi
0x180003b35  jz      short loc_180003B52
0x180003b37  call    cs:__imp_GetProcessHeap
0x180003b3d  mov     r8, rsi; lpMem
0x180003b40  xor     edx, edx; dwFlags
0x180003b42  mov     rcx, rax; hHeap
0x180003b45  call    cs:__imp_HeapFree
0x180003b4b  jmp     short loc_180003B52
0x180003b4d  mov     ebx, 80070216h
0x180003b52  mov     eax, ebx
0x180003b54  mov     rbx, [rsp+60h+arg_10]
0x180003b5c  add     rsp, 60h
0x180003b60  pop     r15
0x180003b62  pop     r14
0x180003b64  pop     r13
0x180003b66  pop     r12
0x180003b68  pop     rdi
0x180003b69  pop     rsi
0x180003b6a  pop     rbp
0x180003b6b  retn
```
