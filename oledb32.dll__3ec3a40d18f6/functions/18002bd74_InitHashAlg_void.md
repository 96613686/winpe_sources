# InitHashAlg(void)

- ea: `0x18002bd74`
- end: `0x18002bf37`
- name: `?InitHashAlg@@YAJXZ`
- size: `451`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021310`

## callees

- `0x180013870`
- `0x18002bd74`

## import_xrefs

- `MSDART!?ConvertExclusiveToShared@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002bf29`
- `MSDART!?ConvertExclusiveToShared@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002bf29`
- `MSDART!?ConvertSharedToExclusive@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002bd94`
- `MSDART!?ConvertSharedToExclusive@CReaderWriterLock3AR@@QEAAXXZ` at `0x18002bd94`
- `KERNEL32!GetLastError` at `0x18002bdc6`
- `KERNEL32!GetLastError` at `0x18002be38`
- `KERNEL32!GetLastError` at `0x18002be95`
- `KERNEL32!GetLastError` at `0x18002bdc6`
- `KERNEL32!GetLastError` at `0x18002be38`
- `KERNEL32!GetLastError` at `0x18002be95`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002bdbc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002bdbc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002bf11`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002bf11`
- `bcrypt!BCryptGetProperty` at `0x18002be2e`
- `bcrypt!BCryptGetProperty` at `0x18002be8b`
- `bcrypt!BCryptGetProperty` at `0x18002be2e`
- `bcrypt!BCryptGetProperty` at `0x18002be8b`

## pseudocode

```c
__int64 InitHashAlg(void)
{
  unsigned int v1; // ebx
  signed int LastError; // eax
  unsigned int v3; // r8d
  signed int v4; // eax
  signed int v5; // eax
  ULONG pcbResult; // [rsp+40h] [rbp+8h] BYREF

  if ( g_fSHA256Inited )
    return 0;
  v1 = 0;
  CReaderWriterLock3AR::ConvertSharedToExclusive((CReaderWriterLock3AR *)g_rwLockSHA256Init);
  if ( !g_fSHA256Inited )
  {
    if ( BCryptOpenAlgorithmProvider(&g_hAlgSHA256, L"SHA256", 0, 0) )
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_25;
      v3 = 379;
    }
    else
    {
      pcbResult = 0;
      if ( BCryptGetProperty(g_hAlgSHA256, L"ObjectLength", (PUCHAR)&g_cbObjectLength, 4u, &pcbResult, 0) )
      {
        v4 = GetLastError();
        v1 = v4;
        if ( v4 > 0 )
          v1 = (unsigned __int16)v4 | 0x80070000;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_25;
        v3 = 389;
      }
      else
      {
        if ( !BCryptGetProperty(g_hAlgSHA256, L"HashDigestLength", &g_cbHashLength, 4u, &pcbResult, 0) )
        {
          if ( *(_DWORD *)&g_cbHashLength == 32 )
          {
            g_fSHA256Inited = 1;
          }
          else if ( (bidGblFlags & 2) != 0 )
          {
            v1 = OLEDBTraceErr(-2147418113, L"<InitHashAlg|OLEDB|ERR> ", 0x196u);
          }
          else
          {
            v1 = -2147418113;
          }
          goto LABEL_25;
        }
        v5 = GetLastError();
        v1 = v5;
        if ( v5 > 0 )
          v1 = (unsigned __int16)v5 | 0x80070000;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_25;
        v3 = 397;
      }
    }
    OLEDBTraceErr(v1, L"<InitHashAlg|OLEDB|ERR> ", v3);
  }
LABEL_25:
  if ( !g_fSHA256Inited )
  {
    if ( g_hAlgSHA256 )
    {
      BCryptCloseAlgorithmProvider(g_hAlgSHA256, 0);
      g_hAlgSHA256 = 0;
    }
  }
  CReaderWriterLock3AR::ConvertExclusiveToShared((CReaderWriterLock3AR *)g_rwLockSHA256Init);
  return v1;
}

```

## disassembly

```asm
0x18002bd74  push    rbx
0x18002bd76  sub     rsp, 30h
0x18002bd7a  mov     al, cs:?g_fSHA256Inited@@3_NC; bool volatile g_fSHA256Inited
0x18002bd80  test    al, al
0x18002bd82  jz      short loc_18002BD8B
0x18002bd84  xor     eax, eax
0x18002bd86  jmp     loc_18002BF31
0x18002bd8b  lea     rcx, ?g_rwLockSHA256Init@@3VCReaderWriterLock3AR@@A; CReaderWriterLock3AR g_rwLockSHA256Init
0x18002bd92  xor     ebx, ebx
0x18002bd94  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ConvertSharedToExclusive(void)
0x18002bd9a  mov     al, cs:?g_fSHA256Inited@@3_NC; bool volatile g_fSHA256Inited
0x18002bda0  test    al, al
0x18002bda2  jnz     loc_18002BEF9
0x18002bda8  xor     r9d, r9d; dwFlags
0x18002bdab  lea     rdx, pszAlgId; "SHA256"
0x18002bdb2  xor     r8d, r8d; pszImplementation
0x18002bdb5  lea     rcx, ?g_hAlgSHA256@@3PEAXEA; phAlgorithm
0x18002bdbc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002bdc2  test    eax, eax
0x18002bdc4  jz      short loc_18002BE01
0x18002bdc6  call    cs:__imp_GetLastError
0x18002bdcc  mov     ebx, eax
0x18002bdce  test    eax, eax
0x18002bdd0  jle     short loc_18002BDDB
0x18002bdd2  movzx   ebx, ax
0x18002bdd5  or      ebx, 80070000h
0x18002bddb  test    byte ptr cs:_bidGblFlags, 2
0x18002bde2  jz      loc_18002BEF9
0x18002bde8  mov     r8d, 17Bh; unsigned int
0x18002bdee  lea     rdx, aInithashalgOle; "<InitHashAlg|OLEDB|ERR> "
0x18002bdf5  mov     ecx, ebx; int
0x18002bdf7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002bdfc  jmp     loc_18002BEF9
0x18002be01  mov     rcx, cs:?g_hAlgSHA256@@3PEAXEA; hObject
0x18002be08  lea     rax, [rsp+38h+arg_0]
0x18002be0d  mov     [rsp+38h+dwFlags], ebx; dwFlags
0x18002be11  lea     r8, ?g_cbObjectLength@@3KA; pbOutput
0x18002be18  mov     r9d, 4; cbOutput
0x18002be1e  mov     [rsp+38h+pcbResult], rax; pcbResult
0x18002be23  lea     rdx, pszProperty; "ObjectLength"
0x18002be2a  mov     [rsp+38h+arg_0], ebx
0x18002be2e  call    cs:__imp_BCryptGetProperty
0x18002be34  test    eax, eax
0x18002be36  jz      short loc_18002BE62
0x18002be38  call    cs:__imp_GetLastError
0x18002be3e  mov     ebx, eax
0x18002be40  test    eax, eax
0x18002be42  jle     short loc_18002BE4D
0x18002be44  movzx   ebx, ax
0x18002be47  or      ebx, 80070000h
0x18002be4d  test    byte ptr cs:_bidGblFlags, 2
0x18002be54  jz      loc_18002BEF9
0x18002be5a  mov     r8d, 185h
0x18002be60  jmp     short loc_18002BDEE
0x18002be62  mov     rcx, cs:?g_hAlgSHA256@@3PEAXEA; hObject
0x18002be69  lea     rax, [rsp+38h+arg_0]
0x18002be6e  mov     [rsp+38h+dwFlags], ebx; dwFlags
0x18002be72  lea     r8, ?g_cbHashLength@@3KA; pbOutput
0x18002be79  mov     r9d, 4; cbOutput
0x18002be7f  mov     [rsp+38h+pcbResult], rax; pcbResult
0x18002be84  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18002be8b  call    cs:__imp_BCryptGetProperty
0x18002be91  test    eax, eax
0x18002be93  jz      short loc_18002BEBE
0x18002be95  call    cs:__imp_GetLastError
0x18002be9b  mov     ebx, eax
0x18002be9d  test    eax, eax
0x18002be9f  jle     short loc_18002BEAA
0x18002bea1  movzx   ebx, ax
0x18002bea4  or      ebx, 80070000h
0x18002beaa  test    byte ptr cs:_bidGblFlags, 2
0x18002beb1  jz      short loc_18002BEF9
0x18002beb3  mov     r8d, 18Dh
0x18002beb9  jmp     loc_18002BDEE
0x18002bebe  cmp     cs:?g_cbHashLength@@3KA, 20h ; ' '; ulong g_cbHashLength
0x18002bec5  jz      short loc_18002BEF2
0x18002bec7  test    byte ptr cs:_bidGblFlags, 2
0x18002bece  jz      short loc_18002BEEB
0x18002bed0  mov     r8d, 196h; unsigned int
0x18002bed6  lea     rdx, aInithashalgOle; "<InitHashAlg|OLEDB|ERR> "
0x18002bedd  mov     ecx, 8000FFFFh; int
0x18002bee2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18002bee7  mov     ebx, eax
0x18002bee9  jmp     short loc_18002BEF9
0x18002beeb  mov     ebx, 8000FFFFh
0x18002bef0  jmp     short loc_18002BEF9
0x18002bef2  mov     cs:?g_fSHA256Inited@@3_NC, 1; bool volatile g_fSHA256Inited
0x18002bef9  mov     al, cs:?g_fSHA256Inited@@3_NC; bool volatile g_fSHA256Inited
0x18002beff  test    al, al
0x18002bf01  jnz     short loc_18002BF22
0x18002bf03  mov     rcx, cs:?g_hAlgSHA256@@3PEAXEA; hAlgorithm
0x18002bf0a  test    rcx, rcx
0x18002bf0d  jz      short loc_18002BF22
0x18002bf0f  xor     edx, edx; dwFlags
0x18002bf11  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002bf17  mov     cs:?g_hAlgSHA256@@3PEAXEA, 0; void * g_hAlgSHA256
0x18002bf22  lea     rcx, ?g_rwLockSHA256Init@@3VCReaderWriterLock3AR@@A; CReaderWriterLock3AR g_rwLockSHA256Init
0x18002bf29  call    cs:__imp_?ConvertExclusiveToShared@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::ConvertExclusiveToShared(void)
0x18002bf2f  mov     eax, ebx
0x18002bf31  add     rsp, 30h
0x18002bf35  pop     rbx
0x18002bf36  retn
```
