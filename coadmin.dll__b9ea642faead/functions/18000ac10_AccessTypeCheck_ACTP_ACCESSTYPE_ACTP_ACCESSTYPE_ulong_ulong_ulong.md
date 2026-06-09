# AccessTypeCheck(ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,ulong,ulong,ulong *)

- ea: `0x18000ac10`
- end: `0x18000aef5`
- name: `?AccessTypeCheck@@YAJW4ACTP_ACCESSTYPE@@0KKPEAK@Z`
- size: `741`
- prototype: `__int64 __fastcall(int, int, int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001cec`

## callees

- `0x18000ac10`
- `0x18000b86c`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000ae6a`
- `IisRTL!PuDbgPrint` at `0x18000ae95`
- `IisRTL!PuDbgPrint` at `0x18000aee4`
- `IisRTL!PuDbgPrint` at `0x18000ae6a`
- `IisRTL!PuDbgPrint` at `0x18000ae95`
- `IisRTL!PuDbgPrint` at `0x18000aee4`

## string_xrefs

- `0x18000ac41`: `inetsrv\iis\mb\coadmin\admacl.cxx`

## pseudocode

```c
__int64 __fastcall AccessTypeCheck(int a1, int a2, int a3, unsigned int a4, int *a5)
{
  int *v5; // r11
  unsigned int v8; // ebx
  int v9; // ecx
  unsigned int v10; // r9d
  int v11; // r10d
  int v12; // r10d
  int v13; // r10d
  int v14; // r10d
  __int64 v15; // r8
  int v16; // edx
  int v17; // edx
  int v18; // ecx

  v5 = a5;
  if ( a5 )
    *a5 = 0;
  if ( !a1 && !a2 )
  {
    v8 = -2147024809;
    goto LABEL_52;
  }
  v9 = a3 | 0x40002;
  if ( (a3 & 0x20) == 0 )
    v9 = a3;
  v10 = v9 | 0x80;
  if ( (v9 & 1) == 0 )
    v10 = v9;
  if ( !a1 )
    goto LABEL_30;
  v11 = a1 - 1;
  if ( !v11 )
    goto LABEL_27;
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
        {
          v8 = -2147024809;
          if ( (g_dwDebugFlags & 4) != 0 )
            PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2407, &word_1800127E6, "*%08x\n", -2147024809);
          goto LABEL_52;
        }
LABEL_27:
        if ( (v10 & 0x81) == 0 )
        {
          v8 = -2147024891;
          if ( (g_dwDebugFlags & 4) == 0 )
            goto LABEL_52;
          v15 = 2387;
          goto LABEL_51;
        }
        goto LABEL_30;
      }
      if ( (v10 & 0x89) == 0 )
      {
        v8 = -2147024891;
        if ( (g_dwDebugFlags & 4) == 0 )
          goto LABEL_52;
        v15 = 2402;
        goto LABEL_51;
      }
    }
    else if ( (v10 & 8) == 0 )
    {
      v8 = -2147024891;
      if ( (g_dwDebugFlags & 4) == 0 )
        goto LABEL_52;
      v15 = 2397;
      goto LABEL_51;
    }
  }
  else if ( (v10 & 0x81) != 0x81 )
  {
    v8 = -2147024891;
    if ( (g_dwDebugFlags & 4) == 0 )
      goto LABEL_52;
    v15 = 2392;
    goto LABEL_51;
  }
LABEL_30:
  if ( !a2 )
    goto LABEL_54;
  v16 = a2 - 1;
  if ( !v16 )
  {
    if ( (v10 & 0x22) != 0 )
      goto LABEL_54;
    v8 = -2147024891;
    if ( (g_dwDebugFlags & 4) == 0 )
      goto LABEL_52;
    v15 = 2420;
LABEL_51:
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", v15, &word_1800127E6, "*%08x\n", -2147024891);
LABEL_52:
    if ( (g_dwDebugFlags & 8) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2470, &word_1800127E6, "*%08x\n", v8);
    return v8;
  }
  v17 = v16 - 1;
  if ( v17 )
  {
    if ( v17 != 3 )
    {
      v8 = -2147024809;
      if ( (g_dwDebugFlags & 4) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2447, &word_1800127E6, "*%08x\n", -2147024809);
      goto LABEL_52;
    }
    if ( (v10 & 0x22) == 0 )
    {
      v8 = -2147024891;
      if ( (g_dwDebugFlags & 4) == 0 )
        goto LABEL_52;
      v15 = 2431;
      goto LABEL_51;
    }
    if ( (v10 & 0x20) == 0 && (a4 != 6027 || (v10 & 0x40000) == 0) && (unsigned int)IsSchemaRestrictedProperty(a4) )
    {
      v8 = -2147024891;
      if ( (g_dwDebugFlags & 4) == 0 )
        goto LABEL_52;
      v15 = 2441;
      goto LABEL_51;
    }
  }
  else if ( (v10 & 0x22) != 0x22 )
  {
    v8 = -2147024891;
    if ( (g_dwDebugFlags & 4) == 0 )
      goto LABEL_52;
    v15 = 2425;
    goto LABEL_51;
  }
LABEL_54:
  v18 = (v10 >> 4) & 2 | 1;
  if ( (v10 & 1) == 0 )
    v18 = (v10 >> 4) & 2;
  if ( v5 )
    *v5 = v18;
  v8 = 0;
  if ( (g_dwDebugFlags & 1) != 0 )
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\admacl.cxx", 2470, &word_1800127E6, "\n");
  return v8;
}

```

## disassembly

```asm
0x18000ac10  push    rbx
0x18000ac12  push    rbp
0x18000ac13  push    rsi
0x18000ac14  push    rdi
0x18000ac15  sub     rsp, 38h
0x18000ac19  mov     r11, [rsp+58h+arg_20]
0x18000ac21  mov     ebx, r9d
0x18000ac24  mov     r10d, ecx
0x18000ac27  test    r11, r11
0x18000ac2a  jz      short loc_18000AC33
0x18000ac2c  mov     dword ptr [r11], 0
0x18000ac33  lea     rbp, a08x; "*%08x\n"
0x18000ac3a  lea     rdi, word_1800127E6
0x18000ac41  lea     rsi, aInetsrvIisMbCo; "inetsrv\\iis\\mb\\coadmin\\admacl.cxx"
0x18000ac48  test    r10d, r10d
0x18000ac4b  jnz     short loc_18000AC5B
0x18000ac4d  test    edx, edx
0x18000ac4f  jnz     short loc_18000AC5B
0x18000ac51  mov     ebx, 80070057h
0x18000ac56  jmp     loc_18000AE70
0x18000ac5b  mov     ecx, r8d
0x18000ac5e  or      ecx, 40002h
0x18000ac64  test    r8b, 20h
0x18000ac68  cmovz   ecx, r8d
0x18000ac6c  mov     r9d, ecx
0x18000ac6f  bts     r9d, 7
0x18000ac74  test    cl, 1
0x18000ac77  cmovz   r9d, ecx
0x18000ac7b  test    r10d, r10d
0x18000ac7e  jz      loc_18000AD6D
0x18000ac84  sub     r10d, 1
0x18000ac88  jz      loc_18000AD48
0x18000ac8e  sub     r10d, 1
0x18000ac92  jz      loc_18000AD1D
0x18000ac98  sub     r10d, 1
0x18000ac9c  jz      short loc_18000ACF8
0x18000ac9e  sub     r10d, 1
0x18000aca2  jz      short loc_18000ACCF
0x18000aca4  cmp     r10d, 1
0x18000aca8  jz      loc_18000AD48
0x18000acae  test    byte ptr cs:g_dwDebugFlags, 4
0x18000acb5  mov     ebx, 80070057h
0x18000acba  jz      loc_18000AE70
0x18000acc0  mov     [rsp+58h+var_30], ebx
0x18000acc4  mov     r8d, 967h
0x18000acca  jmp     loc_18000AE58
0x18000accf  test    r9b, 89h
0x18000acd3  jnz     loc_18000AD6D
0x18000acd9  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ace0  mov     eax, 80070005h
0x18000ace5  mov     ebx, eax
0x18000ace7  jz      loc_18000AE70
0x18000aced  mov     r8d, 962h
0x18000acf3  jmp     loc_18000AE54
0x18000acf8  test    r9b, 8
0x18000acfc  jnz     short loc_18000AD6D
0x18000acfe  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ad05  mov     eax, 80070005h
0x18000ad0a  mov     ebx, eax
0x18000ad0c  jz      loc_18000AE70
0x18000ad12  mov     r8d, 95Dh
0x18000ad18  jmp     loc_18000AE54
0x18000ad1d  mov     eax, r9d
0x18000ad20  and     eax, 81h
0x18000ad25  cmp     al, 81h
0x18000ad27  jz      short loc_18000AD6D
0x18000ad29  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ad30  mov     eax, 80070005h
0x18000ad35  mov     ebx, eax
0x18000ad37  jz      loc_18000AE70
0x18000ad3d  mov     r8d, 958h
0x18000ad43  jmp     loc_18000AE54
0x18000ad48  test    r9b, 81h
0x18000ad4c  jnz     short loc_18000AD6D
0x18000ad4e  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ad55  mov     eax, 80070005h
0x18000ad5a  mov     ebx, eax
0x18000ad5c  jz      loc_18000AE70
0x18000ad62  mov     r8d, 953h
0x18000ad68  jmp     loc_18000AE54
0x18000ad6d  test    edx, edx
0x18000ad6f  jz      loc_18000AE9D
0x18000ad75  sub     edx, 1
0x18000ad78  jz      loc_18000AE38
0x18000ad7e  sub     edx, 1
0x18000ad81  jz      loc_18000AE16
0x18000ad87  cmp     edx, 3
0x18000ad8a  jz      short loc_18000ADAD
0x18000ad8c  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ad93  mov     ebx, 80070057h
0x18000ad98  jz      loc_18000AE70
0x18000ad9e  mov     [rsp+58h+var_30], ebx
0x18000ada2  mov     r8d, 98Fh
0x18000ada8  jmp     loc_18000AE58
0x18000adad  test    r9b, 22h
0x18000adb1  jnz     short loc_18000ADD2
0x18000adb3  test    byte ptr cs:g_dwDebugFlags, 4
0x18000adba  mov     eax, 80070005h
0x18000adbf  mov     ebx, eax
0x18000adc1  jz      loc_18000AE70
0x18000adc7  mov     r8d, 97Fh
0x18000adcd  jmp     loc_18000AE54
0x18000add2  test    r9b, 20h
0x18000add6  jnz     loc_18000AE9D
0x18000addc  cmp     ebx, 178Bh
0x18000ade2  jnz     short loc_18000ADEF
0x18000ade4  bt      r9d, 12h
0x18000ade9  jb      loc_18000AE9D
0x18000adef  mov     ecx, ebx; unsigned int
0x18000adf1  call    ?IsSchemaRestrictedProperty@@YAHK@Z; IsSchemaRestrictedProperty(ulong)
0x18000adf6  test    eax, eax
0x18000adf8  jz      loc_18000AE9D
0x18000adfe  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ae05  mov     eax, 80070005h
0x18000ae0a  mov     ebx, eax
0x18000ae0c  jz      short loc_18000AE70
0x18000ae0e  mov     r8d, 989h
0x18000ae14  jmp     short loc_18000AE54
0x18000ae16  mov     eax, r9d
0x18000ae19  and     eax, 22h
0x18000ae1c  cmp     al, 22h ; '"'
0x18000ae1e  jz      short loc_18000AE9D
0x18000ae20  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ae27  mov     eax, 80070005h
0x18000ae2c  mov     ebx, eax
0x18000ae2e  jz      short loc_18000AE70
0x18000ae30  mov     r8d, 979h
0x18000ae36  jmp     short loc_18000AE54
0x18000ae38  test    r9b, 22h
0x18000ae3c  jnz     short loc_18000AE9D
0x18000ae3e  test    byte ptr cs:g_dwDebugFlags, 4
0x18000ae45  mov     eax, 80070005h
0x18000ae4a  mov     ebx, eax
0x18000ae4c  jz      short loc_18000AE70
0x18000ae4e  mov     r8d, 974h
0x18000ae54  mov     [rsp+58h+var_30], eax
0x18000ae58  mov     rcx, cs:g_pDebug
0x18000ae5f  mov     r9, rdi
0x18000ae62  mov     rdx, rsi
0x18000ae65  mov     [rsp+58h+var_38], rbp
0x18000ae6a  call    cs:__imp_PuDbgPrint
0x18000ae70  test    byte ptr cs:g_dwDebugFlags, 8
0x18000ae77  jz      short loc_18000AEEA
0x18000ae79  mov     rcx, cs:g_pDebug
0x18000ae80  mov     r9, rdi
0x18000ae83  mov     [rsp+58h+var_30], ebx
0x18000ae87  mov     r8d, 9A6h
0x18000ae8d  mov     rdx, rsi
0x18000ae90  mov     [rsp+58h+var_38], rbp
0x18000ae95  call    cs:__imp_PuDbgPrint
0x18000ae9b  jmp     short loc_18000AEEA
0x18000ae9d  mov     eax, r9d
0x18000aea0  shr     eax, 4
0x18000aea3  and     eax, 2
0x18000aea6  mov     ecx, eax
0x18000aea8  or      ecx, 1
0x18000aeab  test    r9b, 1
0x18000aeaf  cmovz   ecx, eax
0x18000aeb2  test    r11, r11
0x18000aeb5  jz      short loc_18000AEBA
0x18000aeb7  mov     [r11], ecx
0x18000aeba  xor     ebx, ebx
0x18000aebc  test    byte ptr cs:g_dwDebugFlags, 1
0x18000aec3  jz      short loc_18000AEEA
0x18000aec5  mov     rcx, cs:g_pDebug
0x18000aecc  lea     rax, asc_1800127E4; "\n"
0x18000aed3  mov     r9, rdi
0x18000aed6  mov     [rsp+58h+var_38], rax
0x18000aedb  mov     r8d, 9A6h
0x18000aee1  mov     rdx, rsi
0x18000aee4  call    cs:__imp_PuDbgPrint
0x18000aeea  mov     eax, ebx
0x18000aeec  add     rsp, 38h
0x18000aef0  pop     rdi
0x18000aef1  pop     rsi
0x18000aef2  pop     rbp
0x18000aef3  pop     rbx
0x18000aef4  retn
```
