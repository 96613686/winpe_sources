# EdpResolveAppHashForAppKeyCaching

- ea: `0x180003a60`
- end: `0x180003dc7`
- name: `EdpResolveAppHashForAppKeyCaching`
- size: `871`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004900`

## callees

- `0x180003a60`
- `0x18000be2c`
- `0x18000c108`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003d57`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003b65`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180003b65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d85`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d85`
- `bcrypt!BCryptFinishHash` at `0x180003c7a`
- `bcrypt!BCryptFinishHash` at `0x180003d2c`
- `bcrypt!BCryptFinishHash` at `0x180003c7a`
- `bcrypt!BCryptFinishHash` at `0x180003d2c`
- `bcrypt!BCryptCreateHash` at `0x180003c23`
- `bcrypt!BCryptCreateHash` at `0x180003cc0`
- `bcrypt!BCryptCreateHash` at `0x180003c23`
- `bcrypt!BCryptCreateHash` at `0x180003cc0`
- `bcrypt!BCryptHashData` at `0x180003c57`
- `bcrypt!BCryptHashData` at `0x180003ce3`
- `bcrypt!BCryptHashData` at `0x180003d06`
- `bcrypt!BCryptHashData` at `0x180003c57`
- `bcrypt!BCryptHashData` at `0x180003ce3`
- `bcrypt!BCryptHashData` at `0x180003d06`
- `bcrypt!BCryptDestroyHash` at `0x180003c90`
- `bcrypt!BCryptDestroyHash` at `0x180003d70`
- `bcrypt!BCryptDestroyHash` at `0x180003c90`
- `bcrypt!BCryptDestroyHash` at `0x180003d70`

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
0x180003a60  mov     [rsp-38h+arg_10], rbx
0x180003a65  mov     [rsp-38h+pbInput], rdx
0x180003a6a  mov     [rsp-38h+Binding], rcx
0x180003a6f  push    rbp
0x180003a70  push    rsi
0x180003a71  push    rdi
0x180003a72  push    r12
0x180003a74  push    r13
0x180003a76  push    r14
0x180003a78  push    r15
0x180003a7a  mov     rbp, rsp
0x180003a7d  sub     rsp, 60h
0x180003a81  mov     rax, rdx
0x180003a84  mov     [rbp+var_20], 1
0x180003a8b  xor     edx, edx
0x180003a8d  mov     r13, r9
0x180003a90  mov     [rbp+ClientProcess], rdx
0x180003a94  mov     r15, r8
0x180003a97  mov     [rbp+var_1C], edx
0x180003a9a  mov     esi, edx
0x180003a9c  mov     [rbp+var_8], rdx
0x180003aa0  mov     [rbp+phHash], rdx
0x180003aa4  test    rax, rax
0x180003aa7  jnz     short loc_180003AB3
0x180003aa9  mov     ebx, 80070057h
0x180003aae  jmp     loc_180003DAC
0x180003ab3  test    r15, r15
0x180003ab6  jnz     short loc_180003AC2
0x180003ab8  mov     ebx, 80004003h
0x180003abd  jmp     loc_180003DAC
0x180003ac2  test    r13, r13
0x180003ac5  jz      short loc_180003AB8
0x180003ac7  xorps   xmm0, xmm0
0x180003aca  xorps   xmm1, xmm1
0x180003acd  movups  xmmword ptr [r8], xmm0
0x180003ad1  mov     r14d, 7FFFFFFFh
0x180003ad7  movups  xmmword ptr [r8+10h], xmm0
0x180003adc  mov     ecx, r14d
0x180003adf  movups  xmmword ptr [r9], xmm1
0x180003ae3  movups  xmmword ptr [r9+10h], xmm1
0x180003ae8  cmp     [rax], dx
0x180003aeb  jz      short loc_180003AF7
0x180003aed  add     rax, 2
0x180003af1  sub     rcx, 1
0x180003af5  jnz     short loc_180003AE8
0x180003af7  mov     rax, rcx
0x180003afa  mov     edi, 80070057h
0x180003aff  neg     rax
0x180003b02  sbb     ebx, ebx
0x180003b04  not     ebx
0x180003b06  and     ebx, edi
0x180003b08  test    rcx, rcx
0x180003b0b  jz      loc_180003DAC
0x180003b11  mov     rax, r14
0x180003b14  sub     rax, rcx
0x180003b17  add     rax, rax
0x180003b1a  neg     rcx
0x180003b1d  sbb     r12, r12
0x180003b20  and     r12, rax
0x180003b23  mov     eax, 0FFFFFFFFh
0x180003b28  cmp     r12, rax
0x180003b2b  ja      loc_180003DA7
0x180003b31  cmp     r12d, 2
0x180003b35  jnb     short loc_180003B41
0x180003b37  mov     ebx, 1
0x180003b3c  jmp     loc_180003DAC
0x180003b41  lea     rcx, [rbp+var_20]
0x180003b45  call    EfsDplAppKeyCachingFeatureEnabled
0x180003b4a  test    eax, eax
0x180003b4c  jnz     short loc_180003B58
0x180003b4e  mov     ebx, 1
0x180003b53  jmp     loc_180003D4B
0x180003b58  mov     rcx, [rbp+Binding]; Binding
0x180003b5c  lea     r8, [rbp+ClientProcess]; ClientProcess
0x180003b60  mov     edx, 1000h; DesiredAccess
0x180003b65  call    cs:__imp_I_RpcOpenClientProcess
0x180003b6c  nop     dword ptr [rax+rax+00h]
0x180003b71  mov     ebx, eax
0x180003b73  test    eax, eax
0x180003b75  jz      short loc_180003B82
0x180003b77  or      ebx, 80010000h
0x180003b7d  jmp     loc_180003D4B
0x180003b82  mov     edx, [rbp+var_20]
0x180003b85  lea     r9, [rbp+var_8]
0x180003b89  mov     rcx, [rbp+ClientProcess]; ProcessHandle
0x180003b8d  lea     r8, [rbp+var_1C]
0x180003b91  call    EfsResolveProcessInfo
0x180003b96  mov     rsi, [rbp+var_8]
0x180003b9a  xor     edx, edx
0x180003b9c  mov     ebx, eax
0x180003b9e  test    eax, eax
0x180003ba0  js      loc_180003D4B
0x180003ba6  test    rsi, rsi
0x180003ba9  jz      short loc_180003B4E
0x180003bab  mov     rcx, r14
0x180003bae  mov     rax, rsi
0x180003bb1  cmp     [rax], dx
0x180003bb4  jz      short loc_180003BC0
0x180003bb6  add     rax, 2
0x180003bba  sub     rcx, 1
0x180003bbe  jnz     short loc_180003BB1
0x180003bc0  mov     rax, rcx
0x180003bc3  neg     rax
0x180003bc6  sbb     ebx, ebx
0x180003bc8  not     ebx
0x180003bca  and     ebx, edi
0x180003bcc  test    rcx, rcx
0x180003bcf  jz      loc_180003D4B
0x180003bd5  sub     r14, rcx
0x180003bd8  mov     eax, 0FFFFFFFFh
0x180003bdd  add     r14, r14
0x180003be0  neg     rcx
0x180003be3  sbb     rdi, rdi
0x180003be6  and     rdi, r14
0x180003be9  cmp     rdi, rax
0x180003bec  ja      loc_180003D46
0x180003bf2  xor     r14d, r14d
0x180003bf5  cmp     edi, 2
0x180003bf8  jnb     short loc_180003C03
0x180003bfa  lea     ebx, [r14+1]
0x180003bfe  jmp     loc_180003D4E
0x180003c03  mov     rcx, cs:g_hSha256Alg; hAlgorithm
0x180003c0a  lea     rdx, [rbp+phHash]; phHash
0x180003c0e  mov     [rsp+60h+dwFlags], r14d; dwFlags
0x180003c13  xor     r9d, r9d; cbHashObject
0x180003c16  mov     [rsp+60h+cbSecret], r14d; cbSecret
0x180003c1b  xor     r8d, r8d; pbHashObject
0x180003c1e  mov     [rsp+60h+pbSecret], r14; pbSecret
0x180003c23  call    cs:__imp_BCryptCreateHash
0x180003c2a  nop     dword ptr [rax+rax+00h]
0x180003c2f  mov     ebx, eax
0x180003c31  test    eax, eax
0x180003c33  jz      short loc_180003C49
0x180003c35  jle     loc_180003D4E
0x180003c3b  movzx   ebx, ax
0x180003c3e  or      ebx, 80070000h
0x180003c44  jmp     loc_180003D4E
0x180003c49  mov     rdx, [rbp+pbInput]; pbInput
0x180003c4d  xor     r9d, r9d; dwFlags
0x180003c50  mov     rcx, [rbp+phHash]; hHash
0x180003c54  mov     r8d, r12d; cbInput
0x180003c57  call    cs:__imp_BCryptHashData
0x180003c5e  nop     dword ptr [rax+rax+00h]
0x180003c63  mov     ebx, eax
0x180003c65  test    eax, eax
0x180003c67  jnz     short loc_180003C35
0x180003c69  mov     rcx, [rbp+phHash]; hHash
0x180003c6d  lea     r12d, [rax+20h]
0x180003c71  mov     r8d, r12d; cbOutput
0x180003c74  xor     r9d, r9d; dwFlags
0x180003c77  mov     rdx, r15; pbOutput
0x180003c7a  call    cs:__imp_BCryptFinishHash
0x180003c81  nop     dword ptr [rax+rax+00h]
0x180003c86  mov     ebx, eax
0x180003c88  test    eax, eax
0x180003c8a  jnz     short loc_180003C35
0x180003c8c  mov     rcx, [rbp+phHash]; hHash
0x180003c90  call    cs:__imp_BCryptDestroyHash
0x180003c97  nop     dword ptr [rax+rax+00h]
0x180003c9c  mov     rcx, cs:g_hSha256Alg; hAlgorithm
0x180003ca3  lea     rdx, [rbp+phHash]; phHash
0x180003ca7  mov     [rsp+60h+dwFlags], r14d; dwFlags
0x180003cac  xor     r9d, r9d; cbHashObject
0x180003caf  mov     [rsp+60h+cbSecret], r14d; cbSecret
0x180003cb4  xor     r8d, r8d; pbHashObject
0x180003cb7  mov     [rsp+60h+pbSecret], r14; pbSecret
0x180003cbc  mov     [rbp+phHash], r14
0x180003cc0  call    cs:__imp_BCryptCreateHash
0x180003cc7  nop     dword ptr [rax+rax+00h]
0x180003ccc  mov     ebx, eax
0x180003cce  test    eax, eax
0x180003cd0  jnz     loc_180003C35
0x180003cd6  mov     rcx, [rbp+phHash]; hHash
0x180003cda  xor     r9d, r9d; dwFlags
0x180003cdd  mov     r8d, r12d; cbInput
0x180003ce0  mov     rdx, r15; pbInput
0x180003ce3  call    cs:__imp_BCryptHashData
0x180003cea  nop     dword ptr [rax+rax+00h]
0x180003cef  mov     ebx, eax
0x180003cf1  test    eax, eax
0x180003cf3  jnz     loc_180003C35
0x180003cf9  mov     rcx, [rbp+phHash]; hHash
0x180003cfd  xor     r9d, r9d; dwFlags
0x180003d00  mov     r8d, edi; cbInput
0x180003d03  mov     rdx, rsi; pbInput
0x180003d06  call    cs:__imp_BCryptHashData
0x180003d0d  nop     dword ptr [rax+rax+00h]
0x180003d12  mov     ebx, eax
0x180003d14  test    eax, eax
0x180003d16  jnz     loc_180003C35
0x180003d1c  mov     rcx, [rbp+phHash]; hHash
0x180003d20  xor     r9d, r9d; dwFlags
0x180003d23  mov     r8d, r12d; cbOutput
0x180003d26  mov     rdx, r13; pbOutput
0x180003d29  mov     ebx, r14d
0x180003d2c  call    cs:__imp_BCryptFinishHash
0x180003d33  nop     dword ptr [rax+rax+00h]
0x180003d38  test    eax, eax
0x180003d3a  jz      short loc_180003D4E
0x180003d3c  jg      loc_180003C3B
0x180003d42  mov     ebx, eax
0x180003d44  jmp     short loc_180003D4E
0x180003d46  mov     ebx, 80070216h
0x180003d4b  xor     r14d, r14d
0x180003d4e  mov     rcx, [rbp+ClientProcess]; hObject
0x180003d52  test    rcx, rcx
0x180003d55  jz      short loc_180003D67
0x180003d57  call    cs:__imp_CloseHandle
0x180003d5e  nop     dword ptr [rax+rax+00h]
0x180003d63  mov     [rbp+ClientProcess], r14
0x180003d67  mov     rcx, [rbp+phHash]; hHash
0x180003d6b  test    rcx, rcx
0x180003d6e  jz      short loc_180003D80
0x180003d70  call    cs:__imp_BCryptDestroyHash
0x180003d77  nop     dword ptr [rax+rax+00h]
0x180003d7c  mov     [rbp+phHash], r14
0x180003d80  test    rsi, rsi
0x180003d83  jz      short loc_180003DAC
0x180003d85  call    cs:__imp_GetProcessHeap
0x180003d8c  nop     dword ptr [rax+rax+00h]
0x180003d91  mov     r8, rsi; lpMem
0x180003d94  xor     edx, edx; dwFlags
0x180003d96  mov     rcx, rax; hHeap
0x180003d99  call    cs:__imp_HeapFree
0x180003da0  nop     dword ptr [rax+rax+00h]
0x180003da5  jmp     short loc_180003DAC
0x180003da7  mov     ebx, 80070216h
0x180003dac  mov     eax, ebx
0x180003dae  mov     rbx, [rsp+60h+arg_10]
0x180003db6  add     rsp, 60h
0x180003dba  pop     r15
0x180003dbc  pop     r14
0x180003dbe  pop     r13
0x180003dc0  pop     r12
0x180003dc2  pop     rdi
0x180003dc3  pop     rsi
0x180003dc4  pop     rbp
0x180003dc5  retn
```
