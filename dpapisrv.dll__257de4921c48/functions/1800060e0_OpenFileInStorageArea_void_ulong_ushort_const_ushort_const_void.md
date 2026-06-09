# OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)

- ea: `0x1800060e0`
- end: `0x1800063ad`
- name: `?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z`
- size: `717`
- prototype: `__int64 __fastcall(void *, DWORD, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `9`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001ff0`
- `0x180003908`
- `0x180005a2c`
- `0x18000dd40`
- `0x18001b72c`
- `0x18001cd50`
- `0x180026dbc`
- `0x1800278c4`
- `0x18002dd6c`

## callees

- `0x1800060e0`
- `0x1800063c0`
- `0x180006510`
- `0x180007f60`
- `0x18001eb8c`
- `0x18002f6bc`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800062fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000634c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000634c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006282`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006282`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000616e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000616e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006227`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006227`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006390`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006390`

## string_xrefs

- `0x1800062cc`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall OpenFileInStorageArea(
        void *a1,
        DWORD a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void **a5)
{
  __int64 FileW; // r12
  int v7; // r13d
  DWORD v9; // ecx
  __int64 v10; // rax
  bool v11; // zf
  size_t v12; // rbx
  __int64 v13; // rax
  unsigned int v14; // r15d
  WCHAR *v15; // rax
  WCHAR *v16; // rbp
  DWORD v18; // r14d
  __int64 *v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // rcx
  int v22; // edx
  DWORD LastError; // r15d
  int v24; // edx
  int v25; // r8d
  int dwCreationDisposition; // [rsp+40h] [rbp-48h]
  DWORD dwShareMode; // [rsp+44h] [rbp-44h]

  FileW = -1;
  v7 = a2 & 0x40000000;
  *a5 = (void *)-1LL;
  v9 = 0;
  dwCreationDisposition = ((a2 & 0x40000000) != 0) + 3;
  if ( (a2 & 0x40000000) == 0 )
    v9 = a2 >> 31;
  v10 = -1;
  dwShareMode = v9;
  do
    v11 = a3[++v10] == 0;
  while ( !v11 );
  v12 = (unsigned int)(2 * v10);
  v13 = -1;
  do
    v11 = a4[++v13] == 0;
  while ( !v11 );
  v14 = 2 * v13;
  v15 = (WCHAR *)LocalAlloc(0, (unsigned int)(2 * v13 + v12) + 2LL);
  v16 = v15;
  if ( !v15 )
    return 8;
  v18 = 0;
  memcpy_0(v15, a3, v12);
  memcpy_0((char *)v16 + v12, a4, v14 + 2LL);
  if ( !a1 || (v18 = CPSImpersonateClient(a1)) == 0 )
  {
    v19 = qword_180041420;
    if ( !v7 )
      v19 = qword_180041408;
    v20 = 0;
    if ( *(_DWORD *)v19 )
    {
      while ( 1 )
      {
        FileW = (__int64)CreateFileW(v16, a2, dwShareMode, 0, dwCreationDisposition, 0x88000006, 0);
        if ( FileW != -1 )
          break;
        LastError = GetLastError();
        if ( LastError == 32 )
        {
          Sleep(*((_DWORD *)v19 + v20));
          v20 = (unsigned int)(v20 + 1);
          if ( *((_DWORD *)v19 + v20) )
            continue;
        }
        goto LABEL_28;
      }
    }
    else
    {
      LastError = 32;
LABEL_28:
      SetLastError(LastError);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_dSD(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v24, v25, v20, (__int64)v16, LastError);
    }
    *a5 = (void *)FileW;
    if ( FileW == -1 )
    {
      v18 = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_sDsd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          v22,
          (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
          (unsigned int)"dwLastError",
          v18,
          (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
          124);
    }
    if ( a1 )
      CPSRevertToSelf(a1);
  }
  LocalFree(v16);
  if ( v18 )
  {
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x10) != 0 )
      McTemplateU0zd_EtwEventWriteTransfer(v21, ETW_LOG_MASTERKEY_FILE_OPEN_IN_STORAGE_FAILED, a4, a2);
  }
  return v18;
}

```

## disassembly

```asm
0x1800060e0  mov     [rsp+dwDesiredAccess], edx
0x1800060e4  mov     [rsp+arg_0], rcx
0x1800060e9  push    rbx
0x1800060ea  push    rbp
0x1800060eb  push    rsi
0x1800060ec  push    rdi
0x1800060ed  push    r12
0x1800060ef  push    r13
0x1800060f1  push    r15
0x1800060f3  sub     rsp, 50h
0x1800060f7  mov     rax, [rsp+88h+arg_20]
0x1800060ff  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180006106  mov     r13d, edx
0x180006109  mov     rsi, r9
0x18000610c  and     r13d, 40000000h
0x180006113  mov     rdi, r8
0x180006116  mov     [rax], r12
0x180006119  mov     eax, 0
0x18000611e  setnz   al
0x180006121  xor     ecx, ecx
0x180006123  add     eax, 3
0x180006126  mov     [rsp+88h+var_48], eax
0x18000612a  mov     eax, edx
0x18000612c  shr     eax, 1Fh
0x18000612f  test    r13d, r13d
0x180006132  cmovz   ecx, eax
0x180006135  mov     rax, r12
0x180006138  mov     [rsp+88h+dwShareMode], ecx
0x18000613c  nop     dword ptr [rax+00h]
0x180006140  cmp     word ptr [r8+rax*2+2], 0
0x180006147  lea     rax, [rax+1]
0x18000614b  jnz     short loc_180006140
0x18000614d  lea     ebx, [rax+rax]
0x180006150  mov     rax, r12
0x180006153  cmp     word ptr [r9+rax*2+2], 0
0x18000615a  lea     rax, [rax+1]
0x18000615e  jnz     short loc_180006153
0x180006160  lea     r15d, [rax+rax]
0x180006164  xor     ecx, ecx; uFlags
0x180006166  lea     edx, [r15+rbx]
0x18000616a  add     rdx, 2; uBytes
0x18000616e  call    cs:__imp_LocalAlloc
0x180006175  nop     dword ptr [rax+rax+00h]
0x18000617a  mov     rbp, rax
0x18000617d  test    rax, rax
0x180006180  jnz     short loc_180006197
0x180006182  mov     eax, 8
0x180006187  add     rsp, 50h
0x18000618b  pop     r15
0x18000618d  pop     r13
0x18000618f  pop     r12
0x180006191  pop     rdi
0x180006192  pop     rsi
0x180006193  pop     rbp
0x180006194  pop     rbx
0x180006195  retn
0x180006197  mov     [rsp+88h+arg_10], r14
0x18000619f  mov     r8, rbx; Size
0x1800061a2  mov     rdx, rdi; Src
0x1800061a5  mov     rcx, rbp; void *
0x1800061a8  xor     r14d, r14d
0x1800061ab  call    memcpy_0
0x1800061b0  mov     r8d, r15d
0x1800061b3  lea     rcx, [rbx+rbp]; void *
0x1800061b7  add     r8, 2; Size
0x1800061bb  mov     rdx, rsi; Src
0x1800061be  call    memcpy_0
0x1800061c3  mov     rcx, [rsp+88h+arg_0]; void *
0x1800061cb  test    rcx, rcx
0x1800061ce  jnz     loc_18000626F
0x1800061d4  test    r13d, r13d
0x1800061d7  lea     rax, qword_180041408
0x1800061de  lea     rbx, qword_180041420
0x1800061e5  cmovz   rbx, rax
0x1800061e9  lea     r13, WPP_GLOBAL_Control
0x1800061f0  xor     edi, edi
0x1800061f2  cmp     [rbx], edi
0x1800061f4  jz      loc_180006343
0x1800061fa  mov     r13d, [rsp+88h+var_48]
0x1800061ff  mov     r8d, [rsp+88h+dwShareMode]; dwShareMode
0x180006204  xor     r9d, r9d; lpSecurityAttributes
0x180006207  mov     edx, [rsp+88h+dwDesiredAccess]; dwDesiredAccess
0x18000620e  mov     rcx, rbp; lpFileName
0x180006211  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18000621a  mov     [rsp+88h+dwFlagsAndAttributes], 88000006h; dwFlagsAndAttributes
0x180006222  mov     [rsp+88h+dwCreationDisposition], r13d; dwCreationDisposition
0x180006227  call    cs:__imp_CreateFileW
0x18000622e  nop     dword ptr [rax+rax+00h]
0x180006233  mov     r12, rax
0x180006236  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000623a  jz      loc_1800062FD
0x180006240  lea     r13, WPP_GLOBAL_Control
0x180006247  mov     rax, [rsp+88h+arg_20]
0x18000624f  mov     [rax], r12
0x180006252  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180006256  jz      short loc_1800062A7
0x180006258  mov     rax, [rsp+88h+arg_0]
0x180006260  test    rax, rax
0x180006263  jz      short loc_18000627F
0x180006265  mov     rcx, rax; void *
0x180006268  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x18000626d  jmp     short loc_18000627F
0x18000626f  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180006274  mov     r14d, eax
0x180006277  test    eax, eax
0x180006279  jz      loc_1800061D4
0x18000627f  mov     rcx, rbp; hMem
0x180006282  call    cs:__imp_LocalFree
0x180006289  nop     dword ptr [rax+rax+00h]
0x18000628e  test    r14d, r14d
0x180006291  jnz     loc_18000631A
0x180006297  mov     eax, r14d
0x18000629a  mov     r14, [rsp+88h+arg_10]
0x1800062a2  jmp     loc_180006187
0x1800062a7  call    cs:__imp_GetLastError
0x1800062ae  nop     dword ptr [rax+rax+00h]
0x1800062b3  mov     r14d, eax
0x1800062b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062bd  cmp     rcx, r13
0x1800062c0  jz      short loc_180006258
0x1800062c2  test    byte ptr [rcx+1Ch], 1
0x1800062c6  jz      short loc_180006258
0x1800062c8  mov     rcx, [rcx+10h]
0x1800062cc  lea     rax, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800062d3  mov     dword ptr [rsp+88h+hTemplateFile], 1D7Ch
0x1800062db  lea     r9, aDwlasterror; "dwLastError"
0x1800062e2  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax
0x1800062e7  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x1800062ee  mov     [rsp+88h+dwCreationDisposition], r14d
0x1800062f3  call    WPP_SF_sDsd
0x1800062f8  jmp     loc_180006258
0x1800062fd  call    cs:__imp_GetLastError
0x180006304  nop     dword ptr [rax+rax+00h]
0x180006309  mov     r15d, eax
0x18000630c  cmp     eax, 20h ; ' '
0x18000630f  jz      short loc_18000638D
0x180006311  lea     r13, WPP_GLOBAL_Control
0x180006318  jmp     short loc_180006349
0x18000631a  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 10h
0x180006321  jz      loc_180006297
0x180006327  mov     r9d, [rsp+88h+dwDesiredAccess]
0x18000632f  lea     rdx, ETW_LOG_MASTERKEY_FILE_OPEN_IN_STORAGE_FAILED
0x180006336  mov     r8, rsi
0x180006339  call    McTemplateU0zd_EtwEventWriteTransfer
0x18000633e  jmp     loc_180006297
0x180006343  mov     r15d, 20h ; ' '
0x180006349  mov     ecx, r15d; dwErrCode
0x18000634c  call    cs:__imp_SetLastError
0x180006353  nop     dword ptr [rax+rax+00h]
0x180006358  mov     rcx, cs:WPP_GLOBAL_Control
0x18000635f  cmp     rcx, r13
0x180006362  jz      loc_180006247
0x180006368  test    byte ptr [rcx+1Ch], 8
0x18000636c  jz      loc_180006247
0x180006372  mov     rcx, [rcx+10h]
0x180006376  mov     r9d, edi
0x180006379  mov     [rsp+88h+dwFlagsAndAttributes], r15d
0x18000637e  mov     qword ptr [rsp+88h+dwCreationDisposition], rbp
0x180006383  call    WPP_SF_dSD
0x180006388  jmp     loc_180006247
0x18000638d  mov     ecx, [rbx+rdi*4]; dwMilliseconds
0x180006390  call    cs:__imp_Sleep
0x180006397  nop     dword ptr [rax+rax+00h]
0x18000639c  inc     edi
0x18000639e  cmp     dword ptr [rbx+rdi*4], 0
0x1800063a2  jz      loc_180006311
0x1800063a8  jmp     loc_1800061FF
```
