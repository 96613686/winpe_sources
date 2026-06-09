# GetFormSize(_INIFORM *,ulong)

- ea: `0x18003adb0`
- end: `0x18003b009`
- name: `?GetFormSize@@YAKPEAU_INIFORM@@K@Z`
- size: `601`
- prototype: `unsigned int __fastcall(struct _INIFORM *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180094340`
- `0x180095034`

## callees

- `0x180014870`
- `0x18001d8e0`
- `0x18001dbd0`
- `0x18001fd4c`
- `0x18003adb0`
- `0x18003ea2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003afc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003afea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003afc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003afea`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18003aee5`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x18003aee5`
- `SPOOLSS!DllFreeSplMem` at `0x18003aed1`
- `SPOOLSS!DllFreeSplMem` at `0x18003af50`
- `SPOOLSS!DllFreeSplMem` at `0x18003af5e`
- `SPOOLSS!DllFreeSplMem` at `0x18003af81`
- `SPOOLSS!DllFreeSplMem` at `0x18003aed1`
- `SPOOLSS!DllFreeSplMem` at `0x18003af50`
- `SPOOLSS!DllFreeSplMem` at `0x18003af5e`
- `SPOOLSS!DllFreeSplMem` at `0x18003af81`

## string_xrefs

- `0x18003aebb`: `Returning from GetFormSize(), because of Integer Overflow.`
- `0x18003af66`: `Returning from GetFormSize(), because of Integer Overflow.`
- `0x18003afd2`: `Returning from GetFormSize(), because of Integer Overflow.`
- `0x18003aec2`: `GetFormSize`
- `0x18003af6d`: `GetFormSize`
- `0x18003afd9`: `GetFormSize`

## pseudocode

```c
__int64 __fastcall GetFormSize(struct _INIFORM *a1, int a2)
{
  unsigned int v3; // ebx
  int v4; // edx
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // edx
  unsigned int v12; // ecx
  unsigned int v13; // eax
  const unsigned __int16 *v14; // rcx
  unsigned __int16 *ResourceNameID; // rsi
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int16 *v18; // r14
  LANGID ThreadUILanguage; // ax
  struct _LANGPAIRNODE *v20; // rcx
  unsigned __int16 *DisplayName; // rax
  unsigned __int16 *v22; // rcx
  __int64 v23; // rdi
  unsigned __int16 v25; // [rsp+58h] [rbp+38h] BYREF
  unsigned int v26; // [rsp+60h] [rbp+40h] BYREF

  v25 = 0;
  v3 = 0;
  v26 = 0;
  v4 = a2 - 1;
  if ( !v4 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(*((_QWORD *)a1 + 3) + 2 * v23) );
    if ( (int)ULongLongToULong(2LL * (unsigned int)v23, &v26) >= 0 && v26 + 40 >= v26 )
    {
      v3 = v26 + 42;
      if ( v26 + 42 >= v26 + 40 )
        goto LABEL_44;
    }
    goto LABEL_45;
  }
  if ( v4 != 1 )
    goto LABEL_44;
  v5 = *((_QWORD *)a1 + 3);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v5 + 2 * v7) );
  v8 = (unsigned int)(v7 + 262);
  if ( (unsigned int)v8 < (unsigned int)v7 )
    goto LABEL_45;
  v26 = v7 + 262;
  if ( (int)ULongLongToULong(2 * v8, &v26) < 0 )
    goto LABEL_45;
  v3 = v26 + 88;
  if ( v26 + 88 < v26 )
    goto LABEL_45;
  v9 = *((_QWORD *)a1 + 9);
  if ( v9 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(v9 + v10) );
    v11 = v3 + v10;
    if ( v3 + (unsigned int)v10 < (unsigned int)v10
      || (v12 = v11 + 1, v11 + 1 < v11)
      || (v13 = v12 & 1, v3 = v13 + v12, v13 + v12 < v13) )
    {
LABEL_45:
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "GetFormSize",
        L"Returning from GetFormSize(), because of Integer Overflow.");
      goto LABEL_46;
    }
  }
  v14 = (const unsigned __int16 *)*((_QWORD *)a1 + 10);
  ResourceNameID = 0;
  if ( !v14 )
    goto LABEL_49;
  ResourceNameID = GetResourceNameID(v14, &v26);
  if ( !ResourceNameID )
    goto LABEL_49;
  v16 = -1;
  do
    ++v16;
  while ( ResourceNameID[v16] );
  v17 = (unsigned int)(v16 + 1);
  if ( (unsigned int)v17 >= (unsigned int)v16 )
  {
    v26 = v16 + 1;
    if ( (int)ULongLongToULong(2 * v17, &v26) >= 0 )
    {
      v3 += v26;
      if ( v3 >= v26 )
      {
LABEL_49:
        if ( *((_QWORD *)a1 + 11) )
        {
          v18 = 0;
          ThreadUILanguage = GetThreadUILanguage();
          v20 = (struct _LANGPAIRNODE *)*((_QWORD *)a1 + 11);
          v25 = ThreadUILanguage;
          DisplayName = GetDisplayName(v20, ThreadUILanguage);
          if ( DisplayName )
            goto LABEL_50;
        }
        v22 = (unsigned __int16 *)*((_QWORD *)a1 + 10);
        if ( v22 )
        {
          DisplayName = GetDisplayNameFromMuiDll(v22, &v25);
          v18 = DisplayName;
          if ( DisplayName )
          {
LABEL_50:
            do
              ++v6;
            while ( DisplayName[v6] );
            if ( (int)v6 + 1 < (unsigned int)v6
              || (v26 = v6 + 1, (int)ULongLongToULong(2LL * (unsigned int)(v6 + 1), &v26) < 0)
              || (v3 += v26, v3 < v26) )
            {
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "GetFormSize",
                L"Returning from GetFormSize(), because of Integer Overflow.");
              if ( v18 )
                DllFreeSplMem(v18);
              if ( !ResourceNameID )
                goto LABEL_46;
              goto LABEL_22;
            }
            if ( v18 )
              DllFreeSplMem(v18);
          }
        }
        if ( ResourceNameID )
          DllFreeSplMem(ResourceNameID);
LABEL_44:
        SetLastError(0);
        return v3;
      }
    }
  }
  LocalSpoolerTelemetry::WriteDbgTraceError(
    "GetFormSize",
    L"Returning from GetFormSize(), because of Integer Overflow.");
LABEL_22:
  DllFreeSplMem(ResourceNameID);
LABEL_46:
  SetLastError(0x216u);
  return 0;
}

```

## disassembly

```asm
0x18003adb0  mov     [rsp-28h+arg_0], rbx
0x18003adb5  mov     [rsp-28h+arg_18], rsi
0x18003adba  push    rbp
0x18003adbb  push    rdi
0x18003adbc  push    r12
0x18003adbe  push    r14
0x18003adc0  push    r15
0x18003adc2  mov     rbp, rsp
0x18003adc5  sub     rsp, 20h
0x18003adc9  xor     r12d, r12d
0x18003adcc  mov     r15, rcx
0x18003adcf  mov     [rbp+arg_8], r12w
0x18003add4  mov     ebx, r12d
0x18003add7  mov     [rbp+arg_10], ebx
0x18003adda  sub     edx, 1
0x18003addd  jz      loc_18003AF91
0x18003ade3  cmp     edx, 1
0x18003ade6  jnz     loc_18003AFC6
0x18003adec  mov     rcx, [rcx+18h]
0x18003adf0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003adf4  mov     rax, rdi
0x18003adf7  inc     rax
0x18003adfa  cmp     [rcx+rax*2], r12w
0x18003adff  jnz     short loc_18003ADF7
0x18003ae01  lea     ecx, [rax+106h]
0x18003ae07  cmp     ecx, eax
0x18003ae09  jb      loc_18003AFD2
0x18003ae0f  mov     [rbp+arg_10], ecx
0x18003ae12  lea     rdx, [rbp+arg_10]; unsigned int *
0x18003ae16  add     rcx, rcx; unsigned __int64
0x18003ae19  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003ae1e  test    eax, eax
0x18003ae20  js      loc_18003AFD2
0x18003ae26  mov     eax, [rbp+arg_10]
0x18003ae29  lea     ebx, [rax+58h]
0x18003ae2c  cmp     ebx, eax
0x18003ae2e  jb      loc_18003AFD2
0x18003ae34  mov     rcx, [r15+48h]
0x18003ae38  test    rcx, rcx
0x18003ae3b  jz      short loc_18003AE6F
0x18003ae3d  mov     rax, rdi
0x18003ae40  inc     rax
0x18003ae43  cmp     [rcx+rax], r12b
0x18003ae47  jnz     short loc_18003AE40
0x18003ae49  lea     edx, [rbx+rax]
0x18003ae4c  cmp     edx, eax
0x18003ae4e  jb      loc_18003AFD2
0x18003ae54  lea     ecx, [rdx+1]
0x18003ae57  cmp     ecx, edx
0x18003ae59  jb      loc_18003AFD2
0x18003ae5f  mov     eax, ecx
0x18003ae61  and     eax, 1
0x18003ae64  lea     ebx, [rax+rcx]
0x18003ae67  cmp     ebx, eax
0x18003ae69  jb      loc_18003AFD2
0x18003ae6f  mov     rcx, [r15+50h]; unsigned __int16 *
0x18003ae73  mov     rsi, r12
0x18003ae76  test    rcx, rcx
0x18003ae79  jz      short loc_18003AEDC
0x18003ae7b  lea     rdx, [rbp+arg_10]; unsigned int *
0x18003ae7f  call    ?GetResourceNameID@@YAPEAGPEBGPEAK@Z; GetResourceNameID(ushort const *,ulong *)
0x18003ae84  mov     rsi, rax
0x18003ae87  test    rax, rax
0x18003ae8a  jz      short loc_18003AEDC
0x18003ae8c  mov     rax, rdi
0x18003ae8f  inc     rax
0x18003ae92  cmp     [rsi+rax*2], r12w
0x18003ae97  jnz     short loc_18003AE8F
0x18003ae99  lea     ecx, [rax+1]
0x18003ae9c  cmp     ecx, eax
0x18003ae9e  jb      short loc_18003AEBB
0x18003aea0  mov     [rbp+arg_10], ecx
0x18003aea3  lea     rdx, [rbp+arg_10]; unsigned int *
0x18003aea7  add     rcx, rcx; unsigned __int64
0x18003aeaa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003aeaf  test    eax, eax
0x18003aeb1  js      short loc_18003AEBB
0x18003aeb3  add     ebx, [rbp+arg_10]
0x18003aeb6  cmp     ebx, [rbp+arg_10]
0x18003aeb9  jnb     short loc_18003AEDC
0x18003aebb  lea     rdx, aReturningFromG_1; "Returning from GetFormSize(), because o"...
0x18003aec2  lea     rcx, aGetformsize; "GetFormSize"
0x18003aec9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003aece  mov     rcx, rsi
0x18003aed1  call    cs:__imp_DllFreeSplMem
0x18003aed7  jmp     loc_18003AFE5
0x18003aedc  cmp     [r15+58h], r12
0x18003aee0  jz      short loc_18003AF00
0x18003aee2  mov     r14, r12
0x18003aee5  call    cs:__imp_GetThreadUILanguage
0x18003aeeb  mov     rcx, [r15+58h]; struct _LANGPAIRNODE *
0x18003aeef  movzx   edx, ax; unsigned __int16
0x18003aef2  mov     [rbp+arg_8], ax
0x18003aef6  call    ?GetDisplayName@@YAPEAGPEAU_LANGPAIRNODE@@G@Z; GetDisplayName(_LANGPAIRNODE *,ushort)
0x18003aefb  test    rax, rax
0x18003aefe  jnz     short loc_18003AF1A
0x18003af00  mov     rcx, [r15+50h]; unsigned __int16 *
0x18003af04  test    rcx, rcx
0x18003af07  jz      short loc_18003AF56
0x18003af09  lea     rdx, [rbp+arg_8]; unsigned __int16 *
0x18003af0d  call    ?GetDisplayNameFromMuiDll@@YAPEAGPEAG0@Z; GetDisplayNameFromMuiDll(ushort *,ushort *)
0x18003af12  mov     r14, rax
0x18003af15  test    rax, rax
0x18003af18  jz      short loc_18003AF56
0x18003af1a  inc     rdi
0x18003af1d  cmp     [rax+rdi*2], r12w
0x18003af22  jnz     short loc_18003AF1A
0x18003af24  lea     eax, [rdi+1]
0x18003af27  cmp     eax, edi
0x18003af29  jb      short loc_18003AF66
0x18003af2b  mov     ecx, eax
0x18003af2d  lea     rdx, [rbp+arg_10]; unsigned int *
0x18003af31  add     rcx, rcx; unsigned __int64
0x18003af34  mov     [rbp+arg_10], eax
0x18003af37  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003af3c  test    eax, eax
0x18003af3e  js      short loc_18003AF66
0x18003af40  add     ebx, [rbp+arg_10]
0x18003af43  cmp     ebx, [rbp+arg_10]
0x18003af46  jb      short loc_18003AF66
0x18003af48  test    r14, r14
0x18003af4b  jz      short loc_18003AF56
0x18003af4d  mov     rcx, r14
0x18003af50  call    cs:__imp_DllFreeSplMem
0x18003af56  test    rsi, rsi
0x18003af59  jz      short loc_18003AFC6
0x18003af5b  mov     rcx, rsi
0x18003af5e  call    cs:__imp_DllFreeSplMem
0x18003af64  jmp     short loc_18003AFC6
0x18003af66  lea     rdx, aReturningFromG_1; "Returning from GetFormSize(), because o"...
0x18003af6d  lea     rcx, aGetformsize; "GetFormSize"
0x18003af74  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003af79  test    r14, r14
0x18003af7c  jz      short loc_18003AF87
0x18003af7e  mov     rcx, r14
0x18003af81  call    cs:__imp_DllFreeSplMem
0x18003af87  test    rsi, rsi
0x18003af8a  jz      short loc_18003AFE5
0x18003af8c  jmp     loc_18003AECE
0x18003af91  mov     rax, [rcx+18h]
0x18003af95  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003af99  inc     rdi
0x18003af9c  cmp     [rax+rdi*2], r12w
0x18003afa1  jnz     short loc_18003AF99
0x18003afa3  mov     ecx, edi
0x18003afa5  lea     rdx, [rbp+arg_10]; unsigned int *
0x18003afa9  add     rcx, rcx; unsigned __int64
0x18003afac  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18003afb1  test    eax, eax
0x18003afb3  js      short loc_18003AFD2
0x18003afb5  mov     eax, [rbp+arg_10]
0x18003afb8  lea     ecx, [rax+28h]
0x18003afbb  cmp     ecx, eax
0x18003afbd  jb      short loc_18003AFD2
0x18003afbf  lea     ebx, [rcx+2]
0x18003afc2  cmp     ebx, ecx
0x18003afc4  jb      short loc_18003AFD2
0x18003afc6  xor     ecx, ecx; dwErrCode
0x18003afc8  call    cs:__imp_SetLastError
0x18003afce  mov     eax, ebx
0x18003afd0  jmp     short loc_18003AFF2
0x18003afd2  lea     rdx, aReturningFromG_1; "Returning from GetFormSize(), because o"...
0x18003afd9  lea     rcx, aGetformsize; "GetFormSize"
0x18003afe0  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003afe5  mov     ecx, 216h; dwErrCode
0x18003afea  call    cs:__imp_SetLastError
0x18003aff0  xor     eax, eax
0x18003aff2  mov     rbx, [rsp+20h+arg_0]
0x18003aff7  mov     rsi, [rsp+20h+arg_18]
0x18003affc  add     rsp, 20h
0x18003b000  pop     r15
0x18003b002  pop     r14
0x18003b004  pop     r12
0x18003b006  pop     rdi
0x18003b007  pop     rbp
0x18003b008  retn
```
