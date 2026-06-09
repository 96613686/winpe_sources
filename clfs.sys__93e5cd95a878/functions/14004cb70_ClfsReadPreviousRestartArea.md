# ClfsReadPreviousRestartArea

- ea: `0x14004cb70`
- end: `0x14004ce0b`
- name: `ClfsReadPreviousRestartArea`
- size: `667`
- prototype: `NTSTATUS __stdcall(PVOID pvReadContext, PVOID *ppvRestartBuffer, PULONG pcbRestartBuffer, PCLFS_LSN plsnRestart)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x14004cb70`
- `0x14005a380`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14004cc83`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004cc83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007cd60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd3e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007cd60`

## string_xrefs

- `0x14004cbc7`: `ClfsReadPreviousRestartArea`
- `0x14004cd03`: `ClfsReadPreviousRestartArea`
- `0x14004cd70`: `ClfsReadPreviousRestartArea`
- `0x14004cde1`: `ClfsReadPreviousRestartArea`

## pseudocode

```c
NTSTATUS __stdcall ClfsReadPreviousRestartArea(
        PVOID pvReadContext,
        PVOID *ppvRestartBuffer,
        PULONG pcbRestartBuffer,
        PCLFS_LSN plsnRestart)
{
  NTSTATUS v8; // edi
  struct _CLFS_RECORD_HEADER *v9; // rdx
  struct _CLFS_RECORD_HEADER *v11; // [rsp+70h] [rbp+8h] BYREF
  PVOID *v12; // [rsp+78h] [rbp+10h]
  PULONG v13; // [rsp+80h] [rbp+18h]
  PCLFS_LSN v14; // [rsp+88h] [rbp+20h]

  v14 = plsnRestart;
  v13 = pcbRestartBuffer;
  v12 = ppvRestartBuffer;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      166,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadPreviousRestartArea",
      117);
  }
  if ( !pvReadContext || !ppvRestartBuffer || !pcbRestartBuffer || !plsnRestart )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        167,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadPreviousRestartArea",
        128,
        -1073741811);
    }
    return -1073741811;
  }
  *ppvRestartBuffer = 0;
  *pcbRestartBuffer = 0;
  *plsnRestart = CLFS_LSN_NULL;
  if ( *(_DWORD *)pvReadContext != -1040322545
    || *((_DWORD *)pvReadContext + 1) != 176
    || (*((_DWORD *)pvReadContext + 32) & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        168,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadPreviousRestartArea",
        153,
        -1073741811);
    }
    return -1073741811;
  }
  if ( !*((_QWORD *)pvReadContext + 19) )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        169,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadPreviousRestartArea",
        167,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  v8 = CClfsKernelMarshallingContext::ReadNextLogRecord(
         *((CClfsKernelMarshallingContext **)pvReadContext + 19),
         (struct _LOGIOCB *)pvReadContext,
         2u,
         0,
         &v11);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        170,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsReadPreviousRestartArea",
        206,
        v8,
        v8);
    }
  }
  else
  {
    v9 = v11;
    *ppvRestartBuffer = (char *)v11 + *((unsigned __int16 *)v11 + 17);
    *pcbRestartBuffer = *((_DWORD *)v9 + 6) - *((unsigned __int16 *)v9 + 17);
    *plsnRestart = *(PCLFS_LSN)v9;
  }
  KeLeaveCriticalRegion();
  if ( v8 >= 0
    && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      171,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsReadPreviousRestartArea",
      237);
  }
  return v8;
}

```

## disassembly

```asm
0x14004cb70  mov     rax, rsp
0x14004cb73  mov     [rax+20h], r9
0x14004cb77  mov     [rax+18h], r8
0x14004cb7b  mov     [rax+10h], rdx
0x14004cb7f  push    rsi
0x14004cb80  push    rdi
0x14004cb81  push    r12
0x14004cb83  push    r14
0x14004cb85  push    r15
0x14004cb87  sub     rsp, 40h
0x14004cb8b  mov     r14, r9
0x14004cb8e  mov     r15, r8
0x14004cb91  mov     r12, rdx
0x14004cb94  mov     rdi, rcx
0x14004cb97  mov     qword ptr [rax+8], 0
0x14004cb9f  lea     rsi, WPP_GLOBAL_Control
0x14004cba6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cbad  cmp     rcx, rsi
0x14004cbb0  jz      short loc_14004CBDE
0x14004cbb2  test    dword ptr [rcx+2Ch], 4000000h
0x14004cbb9  jz      short loc_14004CBDE
0x14004cbbb  mov     edx, 0A6h
0x14004cbc0  mov     dword ptr [rax-48h], 1375h
0x14004cbc7  lea     r9, aClfsreadprevio; "ClfsReadPreviousRestartArea"
0x14004cbce  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004cbd5  mov     rcx, [rcx+18h]
0x14004cbd9  call    WPP_SF_sd
0x14004cbde  test    rdi, rdi
0x14004cbe1  jz      loc_14004CDB7
0x14004cbe7  test    r12, r12
0x14004cbea  jz      loc_14004CDB7
0x14004cbf0  test    r15, r15
0x14004cbf3  jz      loc_14004CDB7
0x14004cbf9  test    r14, r14
0x14004cbfc  jz      loc_14004CDB7
0x14004cc02  mov     qword ptr [r12], 0
0x14004cc0a  mov     dword ptr [r15], 0
0x14004cc11  mov     rax, qword ptr cs:CLFS_LSN_NULL
0x14004cc18  mov     [r14], rax
0x14004cc1b  cmp     dword ptr [rdi], 0C1FDF00Fh
0x14004cc21  jnz     loc_14004CD8B
0x14004cc27  cmp     dword ptr [rdi+4], 0B0h
0x14004cc2e  jnz     loc_14004CD8B
0x14004cc34  mov     eax, [rdi+80h]
0x14004cc3a  test    al, 10h
0x14004cc3c  jz      loc_14004CD8B
0x14004cc42  cmp     qword ptr [rdi+98h], 0
0x14004cc4a  jnz     short loc_14004CC83
0x14004cc4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cc53  cmp     rcx, rsi
0x14004cc56  jz      loc_14004CDF8
0x14004cc5c  test    dword ptr [rcx+2Ch], 4000000h
0x14004cc63  jz      loc_14004CDF8
0x14004cc69  mov     edx, 0A9h
0x14004cc6e  mov     [rsp+68h+var_40], 0C000000Dh
0x14004cc76  mov     dword ptr [rsp+68h+var_48], 13A7h
0x14004cc7e  jmp     loc_14004CDE1
0x14004cc83  call    cs:__imp_KeEnterCriticalRegion
0x14004cc8a  nop     dword ptr [rax+rax+00h]
0x14004cc8f  nop
0x14004cc90  lea     rax, [rsp+68h+arg_0]
0x14004cc95  mov     [rsp+68h+var_48], rax; struct _CLFS_RECORD_HEADER **
0x14004cc9a  xor     r9d, r9d; union _CLS_LSN *
0x14004cc9d  mov     r8b, 2; unsigned __int8
0x14004cca0  mov     rdx, rdi; struct _LOGIOCB *
0x14004cca3  mov     rcx, [rdi+98h]; this
0x14004ccaa  call    ?ReadNextLogRecord@CClfsKernelMarshallingContext@@QEAAJQEAXEQEAT_CLS_LSN@@AEAPEAU_CLFS_RECORD_HEADER@@@Z; CClfsKernelMarshallingContext::ReadNextLogRecord(void * const,uchar,_CLS_LSN * const,_CLFS_RECORD_HEADER * &)
0x14004ccaf  mov     edi, eax
0x14004ccb1  mov     [rsp+68h+var_38], eax
0x14004ccb5  jmp     short loc_14004CCD9
0x14004ccb7  mov     edi, eax
0x14004ccb9  mov     [rsp+68h+var_38], eax
0x14004ccbd  lea     rsi, WPP_GLOBAL_Control
0x14004ccc4  mov     r14, [rsp+68h+arg_18]
0x14004cccc  mov     r15, [rsp+68h+arg_10]
0x14004ccd4  mov     r12, [rsp+68h+arg_8]
0x14004ccd9  test    edi, edi
0x14004ccdb  jz      short loc_14004CD1C
0x14004ccdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cce4  cmp     rcx, rsi
0x14004cce7  jz      short loc_14004CD3E
0x14004cce9  mov     eax, [rcx+2Ch]
0x14004ccec  bt      eax, 1Ah
0x14004ccf0  jnb     short loc_14004CD3E
0x14004ccf2  mov     edx, 0AAh
0x14004ccf7  mov     [rsp+68h+var_40], edi
0x14004ccfb  mov     dword ptr [rsp+68h+var_48], 13CEh
0x14004cd03  lea     r9, aClfsreadprevio; "ClfsReadPreviousRestartArea"
0x14004cd0a  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004cd11  mov     rcx, [rcx+18h]
0x14004cd15  call    WPP_SF_slD
0x14004cd1a  jmp     short loc_14004CD3E
0x14004cd1c  mov     rdx, [rsp+68h+arg_0]
0x14004cd21  movzx   eax, word ptr [rdx+22h]
0x14004cd25  add     rax, rdx
0x14004cd28  mov     [r12], rax
0x14004cd2c  movzx   eax, word ptr [rdx+22h]
0x14004cd30  mov     ecx, [rdx+18h]
0x14004cd33  sub     ecx, eax
0x14004cd35  mov     [r15], ecx
0x14004cd38  mov     rax, [rdx]
0x14004cd3b  mov     [r14], rax
0x14004cd3e  call    cs:__imp_KeLeaveCriticalRegion
0x14004cd45  nop     dword ptr [rax+rax+00h]
0x14004cd4a  test    edi, edi
0x14004cd4c  js      short loc_14004CD87
0x14004cd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cd55  cmp     rcx, rsi
0x14004cd58  jz      short loc_14004CD87
0x14004cd5a  test    dword ptr [rcx+2Ch], 4000000h
0x14004cd61  jz      short loc_14004CD87
0x14004cd63  mov     edx, 0ABh
0x14004cd68  mov     dword ptr [rsp+68h+var_48], 13EDh
0x14004cd70  lea     r9, aClfsreadprevio; "ClfsReadPreviousRestartArea"
0x14004cd77  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004cd7e  mov     rcx, [rcx+18h]
0x14004cd82  call    WPP_SF_sd
0x14004cd87  mov     eax, edi
0x14004cd89  jmp     short loc_14004CDFD
0x14004cd8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cd92  cmp     rcx, rsi
0x14004cd95  jz      short loc_14004CDF8
0x14004cd97  test    dword ptr [rcx+2Ch], 4000000h
0x14004cd9e  jz      short loc_14004CDF8
0x14004cda0  mov     edx, 0A8h
0x14004cda5  mov     [rsp+68h+var_40], 0C000000Dh
0x14004cdad  mov     dword ptr [rsp+68h+var_48], 1399h
0x14004cdb5  jmp     short loc_14004CDE1
0x14004cdb7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cdbe  cmp     rcx, rsi
0x14004cdc1  jz      short loc_14004CDF8
0x14004cdc3  test    dword ptr [rcx+2Ch], 4000000h
0x14004cdca  jz      short loc_14004CDF8
0x14004cdcc  mov     edx, 0A7h
0x14004cdd1  mov     [rsp+68h+var_40], 0C000000Dh
0x14004cdd9  mov     dword ptr [rsp+68h+var_48], 1380h
0x14004cde1  lea     r9, aClfsreadprevio; "ClfsReadPreviousRestartArea"
0x14004cde8  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004cdef  mov     rcx, [rcx+18h]
0x14004cdf3  call    WPP_SF_slD
0x14004cdf8  mov     eax, 0C000000Dh
0x14004cdfd  add     rsp, 40h
0x14004ce01  pop     r15
0x14004ce03  pop     r14
0x14004ce05  pop     r12
0x14004ce07  pop     rdi
0x14004ce08  pop     rsi
0x14004ce09  retn
0x14007cd57  push    rbp
0x14007cd59  sub     rsp, 30h
0x14007cd5d  mov     rbp, rdx
0x14007cd60  call    cs:__imp_KeLeaveCriticalRegion
0x14007cd67  nop     dword ptr [rax+rax+00h]
0x14007cd6c  nop
0x14007cd6d  add     rsp, 30h
0x14007cd71  pop     rbp
0x14007cd72  retn
```
