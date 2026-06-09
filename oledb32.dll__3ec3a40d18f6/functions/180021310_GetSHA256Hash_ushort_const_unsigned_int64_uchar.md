# GetSHA256Hash(ushort const *,unsigned __int64,uchar *)

- ea: `0x180021310`
- end: `0x180021523`
- name: `?GetSHA256Hash@@YAJPEBG_KPEAE@Z`
- size: `531`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f680`
- `0x180020d2c`
- `0x18005cca0`

## callees

- `0x180013870`
- `0x180021310`
- `0x18002bd74`
- `0x18007e700`
- `0x18007e7c0`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x1800213b6`
- `msvcrt!_resetstkoflw` at `0x1800213b6`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180021504`
- `MSDART!?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180021504`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180021354`
- `MSDART!?ReadLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x180021354`
- `KERNEL32!GetLastError` at `0x18002143d`
- `KERNEL32!GetLastError` at `0x18002147e`
- `KERNEL32!GetLastError` at `0x1800214bc`
- `KERNEL32!GetLastError` at `0x18002143d`
- `KERNEL32!GetLastError` at `0x18002147e`
- `KERNEL32!GetLastError` at `0x1800214bc`
- `bcrypt!BCryptHashData` at `0x180021474`
- `bcrypt!BCryptHashData` at `0x180021474`
- `bcrypt!BCryptCreateHash` at `0x180021433`
- `bcrypt!BCryptCreateHash` at `0x180021433`
- `bcrypt!BCryptFinishHash` at `0x1800214b2`
- `bcrypt!BCryptFinishHash` at `0x1800214b2`
- `bcrypt!BCryptDestroyHash` at `0x1800214f7`
- `bcrypt!BCryptDestroyHash` at `0x1800214f7`

## pseudocode

```c
__int64 __fastcall GetSHA256Hash(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  int inited; // eax
  unsigned int v7; // ebx
  unsigned int v8; // r8d
  int v9; // ecx
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  signed int LastError; // eax
  signed int v15; // eax
  signed int v16; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  int v19; // [rsp+48h] [rbp+8h]
  BCRYPT_HASH_HANDLE *p_phHash; // [rsp+50h] [rbp+10h]

  phHash = 0;
  CReaderWriterLock3AR::ReadLock((CReaderWriterLock3AR *)g_rwLockSHA256Init);
  inited = InitHashAlg();
  v7 = inited;
  v19 = inited;
  if ( inited < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_27;
    v8 = 293;
    v9 = inited;
    goto LABEL_26;
  }
  v10 = g_cbObjectLength + 15LL;
  if ( v10 <= g_cbObjectLength )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  p_phHash = &phHash;
  if ( !&phHash )
  {
    if ( (bidGblFlags & 2) != 0 )
      v7 = OLEDBTraceErr(-2147467259, L"<GetSHA256Hash|OLEDB|ERR> ", 0x137u);
    else
      v7 = -2147467259;
    goto LABEL_27;
  }
  if ( BCryptCreateHash(g_hAlgSHA256, &phHash, (PUCHAR)&phHash, g_cbObjectLength, 0, 0, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 319;
LABEL_25:
      v9 = v7;
LABEL_26:
      OLEDBTraceErr(v9, L"<GetSHA256Hash|OLEDB|ERR> ", v8);
    }
  }
  else if ( BCryptHashData(phHash, pbInput, cbInput, 0) )
  {
    v15 = GetLastError();
    v7 = v15;
    if ( v15 > 0 )
      v7 = (unsigned __int16)v15 | 0x80070000;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 327;
      goto LABEL_25;
    }
  }
  else if ( BCryptFinishHash(phHash, pbOutput, 0x20u, 0) )
  {
    v16 = GetLastError();
    v7 = v16;
    if ( v16 > 0 )
      v7 = (unsigned __int16)v16 | 0x80070000;
    if ( (bidGblFlags & 2) != 0 )
    {
      v8 = 335;
      goto LABEL_25;
    }
  }
LABEL_27:
  if ( phHash )
    BCryptDestroyHash(phHash);
  CReaderWriterLock3AR::ReadUnlock((CReaderWriterLock3AR *)g_rwLockSHA256Init);
  return v7;
}

```

## disassembly

```asm
0x180021310  mov     [rsp-8+arg_10], r8
0x180021315  mov     [rsp-8+arg_8], rdx
0x18002131a  mov     [rsp-8+arg_0], rcx
0x18002131f  push    rbp
0x180021320  push    rbx
0x180021321  push    rsi
0x180021322  push    rdi
0x180021323  push    r14
0x180021325  sub     rsp, 60h
0x180021329  lea     rbp, [rsp+40h]
0x18002132e  mov     rax, cs:__security_cookie
0x180021335  xor     rax, rbp
0x180021338  mov     [rbp+40h+var_28], rax
0x18002133c  mov     rdi, r8
0x18002133f  mov     rsi, rdx
0x180021342  mov     r14, rcx
0x180021345  mov     [rbp+40h+phHash], 0
0x18002134d  lea     rcx, ?g_rwLockSHA256Init@@3VCReaderWriterLock3AR@@A; CReaderWriterLock3AR g_rwLockSHA256Init
0x180021354  call    cs:__imp_?ReadLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadLock(void)
0x18002135a  call    ?InitHashAlg@@YAJXZ; InitHashAlg(void)
0x18002135f  mov     ebx, eax
0x180021361  mov     [rbp+40h+var_38], eax
0x180021364  test    eax, eax
0x180021366  jns     short loc_180021382
0x180021368  test    byte ptr cs:_bidGblFlags, 2
0x18002136f  jz      loc_1800214EE
0x180021375  mov     r8d, 125h
0x18002137b  mov     ecx, eax
0x18002137d  jmp     loc_1800214E2
0x180021382  mov     r9d, cs:?g_cbObjectLength@@3KA; ulong g_cbObjectLength
0x180021389  lea     rcx, [r9+0Fh]
0x18002138d  cmp     rcx, r9
0x180021390  ja      short loc_18002139C
0x180021392  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18002139c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800213a0  mov     rax, rcx
0x1800213a3  call    _alloca_probe
0x1800213a8  sub     rsp, rcx
0x1800213ab  lea     r8, [rsp+80h+phHash]
0x1800213b0  mov     [rbp+40h+var_30], r8
0x1800213b4  jmp     short loc_1800213D9
0x1800213b6  call    cs:__imp__resetstkoflw
0x1800213bc  xor     r8d, r8d; pbHashObject
0x1800213bf  mov     [rbp+40h+var_30], r8
0x1800213c3  mov     rdi, [rbp+40h+arg_10]
0x1800213c7  mov     rsi, [rbp+40h+arg_8]
0x1800213cb  mov     r14, [rbp+40h+arg_0]
0x1800213cf  mov     ebx, [rbp+40h+var_38]
0x1800213d2  mov     r9d, cs:?g_cbObjectLength@@3KA; cbHashObject
0x1800213d9  test    r8, r8
0x1800213dc  jnz     short loc_18002140F
0x1800213de  test    byte ptr cs:_bidGblFlags, 2
0x1800213e5  jz      short loc_180021405
0x1800213e7  mov     r8d, 137h; unsigned int
0x1800213ed  lea     rdx, aGetsha256hashO; "<GetSHA256Hash|OLEDB|ERR> "
0x1800213f4  mov     ecx, 80004005h; int
0x1800213f9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800213fe  mov     ebx, eax
0x180021400  jmp     loc_1800214EE
0x180021405  mov     ebx, 80004005h
0x18002140a  jmp     loc_1800214EE
0x18002140f  mov     [rsp+80h+dwFlags], 0; dwFlags
0x180021417  mov     [rsp+80h+cbSecret], 0; cbSecret
0x18002141f  mov     [rsp+80h+pbSecret], 0; pbSecret
0x180021428  lea     rdx, [rbp+40h+phHash]; phHash
0x18002142c  mov     rcx, cs:?g_hAlgSHA256@@3PEAXEA; hAlgorithm
0x180021433  call    cs:__imp_BCryptCreateHash
0x180021439  test    eax, eax
0x18002143b  jz      short loc_180021467
0x18002143d  call    cs:__imp_GetLastError
0x180021443  mov     ebx, eax
0x180021445  test    eax, eax
0x180021447  jle     short loc_180021452
0x180021449  movzx   ebx, ax
0x18002144c  or      ebx, 80070000h
0x180021452  test    byte ptr cs:_bidGblFlags, 2
0x180021459  jz      loc_1800214EE
0x18002145f  mov     r8d, 13Fh
0x180021465  jmp     short loc_1800214E0
0x180021467  mov     r8d, esi; cbInput
0x18002146a  xor     r9d, r9d; dwFlags
0x18002146d  mov     rdx, r14; pbInput
0x180021470  mov     rcx, [rbp+40h+phHash]; hHash
0x180021474  call    cs:__imp_BCryptHashData
0x18002147a  test    eax, eax
0x18002147c  jz      short loc_1800214A4
0x18002147e  call    cs:__imp_GetLastError
0x180021484  mov     ebx, eax
0x180021486  test    eax, eax
0x180021488  jle     short loc_180021493
0x18002148a  movzx   ebx, ax
0x18002148d  or      ebx, 80070000h
0x180021493  test    byte ptr cs:_bidGblFlags, 2
0x18002149a  jz      short loc_1800214EE
0x18002149c  mov     r8d, 147h
0x1800214a2  jmp     short loc_1800214E0
0x1800214a4  xor     r9d, r9d; dwFlags
0x1800214a7  lea     r8d, [r9+20h]; cbOutput
0x1800214ab  mov     rdx, rdi; pbOutput
0x1800214ae  mov     rcx, [rbp+40h+phHash]; hHash
0x1800214b2  call    cs:__imp_BCryptFinishHash
0x1800214b8  test    eax, eax
0x1800214ba  jz      short loc_1800214EE
0x1800214bc  call    cs:__imp_GetLastError
0x1800214c2  mov     ebx, eax
0x1800214c4  test    eax, eax
0x1800214c6  jle     short loc_1800214D1
0x1800214c8  movzx   ebx, ax
0x1800214cb  or      ebx, 80070000h
0x1800214d1  test    byte ptr cs:_bidGblFlags, 2
0x1800214d8  jz      short loc_1800214EE
0x1800214da  mov     r8d, 14Fh; unsigned int
0x1800214e0  mov     ecx, ebx; int
0x1800214e2  lea     rdx, aGetsha256hashO; "<GetSHA256Hash|OLEDB|ERR> "
0x1800214e9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800214ee  mov     rcx, [rbp+40h+phHash]; hHash
0x1800214f2  test    rcx, rcx
0x1800214f5  jz      short loc_1800214FD
0x1800214f7  call    cs:__imp_BCryptDestroyHash
0x1800214fd  lea     rcx, ?g_rwLockSHA256Init@@3VCReaderWriterLock3AR@@A; CReaderWriterLock3AR g_rwLockSHA256Init
0x180021504  call    cs:__imp_?ReadUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ReadUnlock(void)
0x18002150a  mov     eax, ebx
0x18002150c  mov     rcx, [rbp+40h+var_28]
0x180021510  xor     rcx, rbp; StackCookie
0x180021513  call    __security_check_cookie
0x180021518  lea     rsp, [rbp+20h]
0x18002151c  pop     r14
0x18002151e  pop     rdi
0x18002151f  pop     rsi
0x180021520  pop     rbx
0x180021521  pop     rbp
0x180021522  retn
0x18007f740  push    rbp
0x18007f742  sub     rsp, 40h
0x18007f746  lea     rbp, [rdx+40h]
0x18007f74a  mov     rax, [rcx]
0x18007f74d  xor     ecx, ecx
0x18007f74f  cmp     dword ptr [rax], 0C00000FDh
0x18007f755  setz    cl
0x18007f758  mov     eax, ecx
0x18007f75a  add     rsp, 40h
0x18007f75e  pop     rbp
0x18007f75f  retn
```
