# DoRemovePassphrase(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180006c30`
- end: `0x180006ddd`
- name: `?DoRemovePassphrase@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `429`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180006c30`

## import_xrefs

- `KERNEL32!HeapSize` at `0x180006d83`
- `KERNEL32!HeapSize` at `0x180006d83`
- `KERNEL32!HeapFree` at `0x180006db1`
- `KERNEL32!HeapFree` at `0x180006db1`
- `KERNEL32!HeapAlloc` at `0x180006ce7`
- `KERNEL32!HeapAlloc` at `0x180006ce7`
- `KERNEL32!GetProcessHeap` at `0x180006cd6`
- `KERNEL32!GetProcessHeap` at `0x180006d75`
- `KERNEL32!GetProcessHeap` at `0x180006da3`
- `KERNEL32!GetProcessHeap` at `0x180006cd6`
- `KERNEL32!GetProcessHeap` at `0x180006d75`
- `KERNEL32!GetProcessHeap` at `0x180006da3`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006cb3`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006d2c`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006cb3`
- `FVEAPI!FveGetAuthMethodInformation` at `0x180006d2c`
- `FVEAPI!FveDeleteAuthMethod` at `0x180006d40`
- `FVEAPI!FveDeleteAuthMethod` at `0x180006d40`
- `FVEAPI!FveCloseVolume` at `0x180006d62`
- `FVEAPI!FveCloseVolume` at `0x180006d62`
- `FVEAPI!FveCommitChanges` at `0x180006d50`
- `FVEAPI!FveCommitChanges` at `0x180006d50`
- `FVEAPI!FveOpenVolumeW` at `0x180006c81`
- `FVEAPI!FveOpenVolumeW` at `0x180006c81`

## pseudocode

```c
__int64 __fastcall DoRemovePassphrase(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  VARIANTARG *rgvarg; // rcx
  char *v4; // rdi
  LONG v5; // ebx
  int AuthMethodInformation; // eax
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  char *v9; // rax
  HANDLE v10; // rax
  SIZE_T v11; // rax
  _BYTE *i; // rcx
  HANDLE v13; // rax
  __int64 result; // rax
  __int64 v15; // [rsp+20h] [rbp-50h] BYREF
  SIZE_T dwBytes; // [rsp+28h] [rbp-48h] BYREF
  __int128 v17; // [rsp+30h] [rbp-40h] BYREF
  __int128 v18; // [rsp+40h] [rbp-30h]
  __int128 v19; // [rsp+50h] [rbp-20h]
  __int64 v20; // [rsp+60h] [rbp-10h]

  rgvarg = a1->rgvarg;
  v15 = -1;
  v20 = 0;
  dwBytes = 0;
  v17 = 0;
  v4 = 0;
  v18 = 0;
  v19 = 0;
  v5 = FveOpenVolumeW(rgvarg->llVal, 1, &v15);
  if ( v5 >= 0 )
  {
    LODWORD(v17) = 56;
    *(_QWORD *)((char *)&v17 + 4) = 0x80000000000001LL;
    AuthMethodInformation = FveGetAuthMethodInformation(v15, &v17, 56, &dwBytes);
    v5 = AuthMethodInformation;
    if ( AuthMethodInformation == -2147024774 )
    {
      v7 = dwBytes;
      ProcessHeap = GetProcessHeap();
      v9 = (char *)HeapAlloc(ProcessHeap, 8u, v7);
      v4 = v9;
      if ( v9 )
      {
        *(_OWORD *)v9 = v17;
        *((_OWORD *)v9 + 1) = v18;
        *((_OWORD *)v9 + 2) = v19;
        *((_QWORD *)v9 + 6) = v20;
        v5 = FveGetAuthMethodInformation(v15, v9, dwBytes, &dwBytes);
        if ( v5 >= 0 )
        {
          v5 = FveDeleteAuthMethod(v15, v4 + 40);
          if ( v5 >= 0 )
            v5 = FveCommitChanges(v15);
        }
      }
      else
      {
        v5 = -2147024882;
      }
    }
    else if ( AuthMethodInformation >= 0 )
    {
      v5 = 1;
    }
  }
  if ( v15 != -1 )
  {
    FveCloseVolume();
    v15 = -1;
  }
  if ( v4 )
  {
    v10 = GetProcessHeap();
    v11 = HeapSize(v10, 0, v4);
    if ( v11 != -1 )
    {
      for ( i = v4; v11; --v11 )
        *i++ = 0;
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v4);
    }
  }
  a2->vt = 19;
  result = (unsigned int)v5;
  a2->lVal = v5;
  return result;
}

```

## disassembly

```asm
0x180006c30  mov     [rsp-18h+arg_10], rbx
0x180006c35  push    rbp
0x180006c36  push    rsi
0x180006c37  push    rdi
0x180006c38  mov     rbp, rsp
0x180006c3b  sub     rsp, 70h
0x180006c3f  mov     rax, cs:__security_cookie
0x180006c46  xor     rax, rsp
0x180006c49  mov     [rbp+var_8], rax
0x180006c4d  mov     rcx, [rcx]
0x180006c50  lea     r8, [rbp+var_50]
0x180006c54  xor     eax, eax
0x180006c56  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFFh
0x180006c5e  xorps   xmm0, xmm0
0x180006c61  mov     [rbp+var_10], rax
0x180006c65  mov     rsi, rdx
0x180006c68  mov     [rbp+dwBytes], rax
0x180006c6c  movups  [rbp+var_40], xmm0
0x180006c70  lea     edx, [rax+1]
0x180006c73  xor     edi, edi
0x180006c75  movups  [rbp+var_30], xmm0
0x180006c79  movups  [rbp+var_20], xmm0
0x180006c7d  mov     rcx, [rcx+8]
0x180006c81  call    cs:__imp_FveOpenVolumeW
0x180006c87  mov     ebx, eax
0x180006c89  test    eax, eax
0x180006c8b  js      loc_180006D58
0x180006c91  mov     rcx, [rbp+var_50]
0x180006c95  lea     r8d, [rdi+38h]
0x180006c99  lea     r9, [rbp+dwBytes]
0x180006c9d  mov     dword ptr [rbp+var_40], r8d
0x180006ca1  lea     rdx, [rbp+var_40]
0x180006ca5  mov     dword ptr [rbp+var_40+4], 1
0x180006cac  mov     dword ptr [rbp+var_40+8], 800000h
0x180006cb3  call    cs:__imp_FveGetAuthMethodInformation
0x180006cb9  mov     ebx, eax
0x180006cbb  cmp     eax, 8007007Ah
0x180006cc0  jz      short loc_180006CD2
0x180006cc2  test    eax, eax
0x180006cc4  js      loc_180006D58
0x180006cca  lea     ebx, [rdi+1]
0x180006ccd  jmp     loc_180006D58
0x180006cd2  mov     rbx, [rbp+dwBytes]
0x180006cd6  call    cs:__imp_GetProcessHeap
0x180006cdc  mov     r8, rbx; dwBytes
0x180006cdf  mov     edx, 8; dwFlags
0x180006ce4  mov     rcx, rax; hHeap
0x180006ce7  call    cs:__imp_HeapAlloc
0x180006ced  mov     rdi, rax
0x180006cf0  test    rax, rax
0x180006cf3  jnz     short loc_180006CFC
0x180006cf5  mov     ebx, 8007000Eh
0x180006cfa  jmp     short loc_180006D58
0x180006cfc  movups  xmm0, [rbp+var_40]
0x180006d00  lea     r9, [rbp+dwBytes]
0x180006d04  mov     rdx, rdi
0x180006d07  movups  xmmword ptr [rax], xmm0
0x180006d0a  movups  xmm1, [rbp+var_30]
0x180006d0e  movups  xmmword ptr [rax+10h], xmm1
0x180006d12  movups  xmm0, [rbp+var_20]
0x180006d16  movups  xmmword ptr [rax+20h], xmm0
0x180006d1a  movsd   xmm1, [rbp+var_10]
0x180006d1f  movsd   qword ptr [rax+30h], xmm1
0x180006d24  mov     r8, [rbp+dwBytes]
0x180006d28  mov     rcx, [rbp+var_50]
0x180006d2c  call    cs:__imp_FveGetAuthMethodInformation
0x180006d32  mov     ebx, eax
0x180006d34  test    eax, eax
0x180006d36  js      short loc_180006D58
0x180006d38  mov     rcx, [rbp+var_50]
0x180006d3c  lea     rdx, [rdi+28h]
0x180006d40  call    cs:__imp_FveDeleteAuthMethod
0x180006d46  mov     ebx, eax
0x180006d48  test    eax, eax
0x180006d4a  js      short loc_180006D58
0x180006d4c  mov     rcx, [rbp+var_50]
0x180006d50  call    cs:__imp_FveCommitChanges
0x180006d56  mov     ebx, eax
0x180006d58  mov     rcx, [rbp+var_50]
0x180006d5c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006d60  jz      short loc_180006D70
0x180006d62  call    cs:__imp_FveCloseVolume
0x180006d68  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFFh
0x180006d70  test    rdi, rdi
0x180006d73  jz      short loc_180006DB7
0x180006d75  call    cs:__imp_GetProcessHeap
0x180006d7b  mov     r8, rdi; lpMem
0x180006d7e  xor     edx, edx; dwFlags
0x180006d80  mov     rcx, rax; hHeap
0x180006d83  call    cs:__imp_HeapSize
0x180006d89  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006d8d  jz      short loc_180006DB7
0x180006d8f  mov     rcx, rdi
0x180006d92  test    rax, rax
0x180006d95  jz      short loc_180006DA3
0x180006d97  mov     byte ptr [rcx], 0
0x180006d9a  inc     rcx
0x180006d9d  sub     rax, 1
0x180006da1  jnz     short loc_180006D97
0x180006da3  call    cs:__imp_GetProcessHeap
0x180006da9  mov     r8, rdi; lpMem
0x180006dac  xor     edx, edx; dwFlags
0x180006dae  mov     rcx, rax; hHeap
0x180006db1  call    cs:__imp_HeapFree
0x180006db7  mov     word ptr [rsi], 13h
0x180006dbc  mov     eax, ebx
0x180006dbe  mov     [rsi+8], ebx
0x180006dc1  mov     rcx, [rbp+var_8]
0x180006dc5  xor     rcx, rsp; StackCookie
0x180006dc8  call    __security_check_cookie
0x180006dcd  mov     rbx, [rsp+70h+arg_10]
0x180006dd5  add     rsp, 70h
0x180006dd9  pop     rdi
0x180006dda  pop     rsi
0x180006ddb  pop     rbp
0x180006ddc  retn
```
