# CreateFallbackMessage(_EVENTLOGRECORD *,ushort * *,ushort * *)

- ea: `0x18000cca8`
- end: `0x18000d070`
- name: `?CreateFallbackMessage@@YAXPEAU_EVENTLOGRECORD@@PEAPEAG1@Z`
- size: `968`
- prototype: `void __fastcall(struct _EVENTLOGRECORD *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000d814`

## callees

- `0x180001910`
- `0x18000513c`
- `0x18000536c`
- `0x180007014`
- `0x18000cca8`
- `0x18000e664`
- `0x18000f6f4`
- `0x18001f858`
- `0x180020430`
- `0x180021060`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000ce80`
- `msvcrt!wcsncpy_s` at `0x18000ce80`
- `KERNEL32!GetLastError` at `0x18000ce67`
- `KERNEL32!GetLastError` at `0x18000ce67`
- `KERNEL32!GetLocaleInfoW` at `0x18000ce5b`
- `KERNEL32!GetLocaleInfoW` at `0x18000ce5b`
- `KERNEL32!LocalAlloc` at `0x18000cd18`
- `KERNEL32!LocalAlloc` at `0x18000cda6`
- `KERNEL32!LocalAlloc` at `0x18000cf15`
- `KERNEL32!LocalAlloc` at `0x18000cd18`
- `KERNEL32!LocalAlloc` at `0x18000cda6`
- `KERNEL32!LocalAlloc` at `0x18000cf15`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CreateFallbackMessage(struct _EVENTLOGRECORD *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned __int16 **v6; // rsi
  __int64 v7; // r14
  unsigned __int64 v8; // r14
  unsigned __int16 *v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // r15
  unsigned __int16 *v12; // r12
  unsigned __int16 **v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rax
  unsigned __int16 **v17; // r8
  unsigned __int16 **v18; // rax
  __int64 v19; // r15
  __int64 v20; // r15
  __int64 wstring; // rax
  __int64 v22; // rdx
  __int64 v23; // r12
  __int64 v24; // r8
  WORD i; // cx
  __int64 v26; // rdx
  unsigned __int64 v27; // r15
  unsigned __int16 *v28; // rax
  __int64 v29; // rdx
  WORD v30; // r12
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rdx
  WCHAR *v35; // r8
  __int64 v36; // rax
  unsigned __int16 *v37[3]; // [rsp+20h] [rbp-79h] BYREF
  unsigned __int64 v38; // [rsp+38h] [rbp-61h]
  unsigned __int16 *v39[3]; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v40; // [rsp+58h] [rbp-41h]
  _BYTE v41[32]; // [rsp+60h] [rbp-39h] BYREF
  WCHAR LCData[12]; // [rsp+80h] [rbp-19h] BYREF
  wchar_t Destination[12]; // [rsp+98h] [rbp-1h] BYREF

  v6 = 0;
  if ( !(unsigned int)IsNewEventType(a1) || !*a2 || !GetDescriptionStrPtr )
  {
    *a2 = 0;
    FormatString(v37, 234, LOWORD(a1->EventID), &a1[1]);
    if ( !v37[2] )
    {
      v10 = 1;
LABEL_65:
      std::wstring::_Tidy(v37, v10, 0);
      return;
    }
    v11 = v38;
    v12 = v37[0];
    if ( a3 )
    {
      v13 = v37;
      if ( v38 >= 8 )
        v13 = (unsigned __int16 **)v37[0];
      v14 = -1;
      do
        ++v14;
      while ( *((_WORD *)v13 + v14) );
      v15 = v14 + 1;
      v16 = (unsigned __int16 *)LocalAlloc(0, 2 * (v14 + 1));
      *a3 = v16;
      if ( v16 )
      {
        v17 = v37;
        if ( v11 >= 8 )
          v17 = (unsigned __int16 **)v12;
        StringCchCopyW(v16, v15, (const unsigned __int16 *)v17);
      }
      v6 = 0;
    }
    v18 = v37;
    if ( v11 >= 8 )
      v18 = (unsigned __int16 **)v12;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = v19 + 6;
    std::wstring::wstring(v39);
    if ( a1->NumStrings )
      v6 = (unsigned __int16 **)((char *)a1 + a1->StringOffset);
    if ( !v6 )
    {
      wstring = load_wstring(v41, 291);
      std::wstring::operator=(v39, wstring);
      LOBYTE(v22) = 1;
      std::wstring::_Tidy(v41, v22, 0);
      v6 = v39;
      if ( v40 >= 8 )
        v6 = (unsigned __int16 **)v39[0];
      a1->NumStrings = 1;
    }
    if ( !GetLocaleInfoW(0x400u, 0xCu, LCData, 10) )
    {
      GetLastError();
      wcsncpy_s(LCData, 0xAu, L",", 9u);
    }
    v23 = -1;
    do
      ++v23;
    while ( LCData[v23] );
    LoadStr(0x128u, Destination, 0xAu, (wchar_t *)L".");
    v24 = -1;
    do
      ++v24;
    while ( Destination[v24] );
    if ( a1->NumStrings )
    {
      for ( i = 0; i < a1->NumStrings; ++i )
      {
        if ( !v6 )
        {
          a1->NumStrings = i - 1;
          break;
        }
        v26 = -1;
        do
          ++v26;
        while ( *((_WORD *)v6 + v26) );
        v20 += v26 + v23 + 1;
        v6 = (unsigned __int16 **)((char *)v6 + 2 * v26 + 2);
      }
    }
    else
    {
      ++v20;
    }
    v27 = v24 + v20;
    v28 = (unsigned __int16 *)LocalAlloc(0, 2 * v27);
    *a2 = v28;
    v30 = 0;
    if ( v28 )
    {
      v31 = (const unsigned __int16 *)v37;
      if ( v38 >= 8 )
        v31 = v37[0];
      StringCchCopyW(v28, v27, v31);
      if ( a1->NumStrings )
      {
        v32 = (const unsigned __int16 *)((char *)a1 + a1->StringOffset);
        if ( v32 )
        {
          if ( !a1->NumStrings )
            goto LABEL_64;
        }
        else
        {
          if ( !v39[2] )
          {
            v33 = load_wstring(v41, 291);
            std::wstring::operator=(v39, v33);
            LOBYTE(v34) = 1;
            std::wstring::_Tidy(v41, v34, 0);
          }
          v32 = (const unsigned __int16 *)v39;
          if ( v40 >= 8 )
            v32 = v39[0];
          a1->NumStrings = 1;
        }
        do
        {
          StringCchCatW(*a2, v27, L" ");
          StringCchCatW(*a2, v27, v32);
          v35 = LCData;
          if ( v30 == a1->NumStrings - 1 )
            v35 = Destination;
          StringCchCatW(*a2, v27, v35);
          v36 = -1;
          do
            ++v36;
          while ( v32[v36] );
          v32 += v36 + 1;
          ++v30;
        }
        while ( v30 < a1->NumStrings );
        goto LABEL_64;
      }
      StringCchCatW(*a2, v27, L" ");
      StringCchCatW(*a2, v27, Destination);
    }
LABEL_64:
    LOBYTE(v29) = 1;
    std::wstring::_Tidy(v39, v29, 0);
    LOBYTE(v10) = 1;
    goto LABEL_65;
  }
  v7 = -1;
  do
    ++v7;
  while ( (*a2)[v7] );
  if ( a3 )
  {
    v8 = v7 + 1;
    v9 = (unsigned __int16 *)LocalAlloc(0, 2 * v8);
    *a3 = v9;
    if ( *a2 )
    {
      if ( v9 )
        StringCchCopyW(v9, v8, *a2);
    }
  }
}

```

## disassembly

```asm
0x18000cca8  mov     [rsp-8+arg_18], rbx
0x18000ccad  push    rbp
0x18000ccae  push    rsi
0x18000ccaf  push    rdi
0x18000ccb0  push    r12
0x18000ccb2  push    r13
0x18000ccb4  push    r14
0x18000ccb6  push    r15
0x18000ccb8  lea     rbp, [rsp-27h]
0x18000ccbd  sub     rsp, 0C0h
0x18000ccc4  mov     rax, cs:__security_cookie
0x18000cccb  xor     rax, rsp
0x18000ccce  mov     [rbp+57h+var_40], rax
0x18000ccd2  mov     rbx, r8
0x18000ccd5  mov     r13, rdx
0x18000ccd8  mov     rdi, rcx
0x18000ccdb  call    ?IsNewEventType@@YAHPEAU_EVENTLOGRECORD@@@Z; IsNewEventType(_EVENTLOGRECORD *)
0x18000cce0  xor     esi, esi
0x18000cce2  test    eax, eax
0x18000cce4  jz      short loc_18000CD47
0x18000cce6  mov     rax, [r13+0]
0x18000ccea  test    rax, rax
0x18000cced  jz      short loc_18000CD47
0x18000ccef  cmp     cs:?GetDescriptionStrPtr@@3P6AHPEAU_EVENTLOGRECORD@@KPEAPEAG@ZEA, rsi; int (*GetDescriptionStrPtr)(_EVENTLOGRECORD *,ulong,ushort * *)
0x18000ccf6  jz      short loc_18000CD47
0x18000ccf8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ccfc  inc     r14
0x18000ccff  cmp     [rax+r14*2], si
0x18000cd04  jnz     short loc_18000CCFC
0x18000cd06  test    rbx, rbx
0x18000cd09  jz      loc_18000D049
0x18000cd0f  inc     r14
0x18000cd12  lea     rdx, [r14+r14]; uBytes
0x18000cd16  xor     ecx, ecx; uFlags
0x18000cd18  call    cs:__imp_LocalAlloc
0x18000cd1e  mov     [rbx], rax
0x18000cd21  mov     r8, [r13+0]; unsigned __int16 *
0x18000cd25  test    r8, r8
0x18000cd28  jz      loc_18000D049
0x18000cd2e  test    rax, rax
0x18000cd31  jz      loc_18000D049
0x18000cd37  mov     rdx, r14; unsigned __int64
0x18000cd3a  mov     rcx, rax; unsigned __int16 *
0x18000cd3d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cd42  jmp     loc_18000D049
0x18000cd47  mov     [r13+0], rsi
0x18000cd4b  lea     r9, [rdi+38h]
0x18000cd4f  movzx   r8d, word ptr [rdi+14h]
0x18000cd54  mov     edx, 0EAh
0x18000cd59  lea     rcx, [rbp+57h+var_D0]
0x18000cd5d  call    ?FormatString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IZZ; FormatString(uint,...)
0x18000cd62  nop
0x18000cd63  cmp     [rbp+57h+var_C0], rsi
0x18000cd67  jnz     short loc_18000CD73
0x18000cd69  mov     edx, 1
0x18000cd6e  jmp     loc_18000D03D
0x18000cd73  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000cd77  mov     r15, [rbp+57h+var_B8]
0x18000cd7b  mov     r12, [rbp+57h+var_D0]
0x18000cd7f  test    rbx, rbx
0x18000cd82  jz      short loc_18000CDCD
0x18000cd84  lea     rcx, [rbp+57h+var_D0]
0x18000cd88  cmp     r15, 8
0x18000cd8c  cmovnb  rcx, r12
0x18000cd90  mov     rax, r14
0x18000cd93  inc     rax
0x18000cd96  cmp     [rcx+rax*2], si
0x18000cd9a  jnz     short loc_18000CD93
0x18000cd9c  lea     rsi, [rax+1]
0x18000cda0  lea     rdx, [rsi+rsi]; uBytes
0x18000cda4  xor     ecx, ecx; uFlags
0x18000cda6  call    cs:__imp_LocalAlloc
0x18000cdac  mov     [rbx], rax
0x18000cdaf  test    rax, rax
0x18000cdb2  jz      short loc_18000CDCB
0x18000cdb4  lea     r8, [rbp+57h+var_D0]
0x18000cdb8  cmp     r15, 8
0x18000cdbc  cmovnb  r8, r12; unsigned __int16 *
0x18000cdc0  mov     rdx, rsi; unsigned __int64
0x18000cdc3  mov     rcx, rax; unsigned __int16 *
0x18000cdc6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cdcb  xor     esi, esi
0x18000cdcd  lea     rax, [rbp+57h+var_D0]
0x18000cdd1  cmp     r15, 8
0x18000cdd5  cmovnb  rax, r12
0x18000cdd9  mov     r15, r14
0x18000cddc  inc     r15
0x18000cddf  cmp     [rax+r15*2], si
0x18000cde4  jnz     short loc_18000CDDC
0x18000cde6  add     r15, 6
0x18000cdea  lea     rcx, [rbp+57h+var_B0]
0x18000cdee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000cdf3  nop
0x18000cdf4  cmp     [rdi+1Ah], si
0x18000cdf8  jz      short loc_18000CE00
0x18000cdfa  mov     esi, [rdi+24h]
0x18000cdfd  add     rsi, rdi
0x18000ce00  mov     ebx, 1
0x18000ce05  test    rsi, rsi
0x18000ce08  jnz     short loc_18000CE44
0x18000ce0a  mov     edx, 123h
0x18000ce0f  lea     rcx, [rbp+57h+var_90]
0x18000ce13  call    ?load_wstring@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; load_wstring(int)
0x18000ce18  mov     rdx, rax
0x18000ce1b  lea     rcx, [rbp+57h+var_B0]
0x18000ce1f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ce24  xor     r8d, r8d
0x18000ce27  mov     dl, bl
0x18000ce29  lea     rcx, [rbp+57h+var_90]
0x18000ce2d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ce32  lea     rsi, [rbp+57h+var_B0]
0x18000ce36  cmp     [rbp+57h+var_98], 8
0x18000ce3b  cmovnb  rsi, [rbp+57h+var_B0]
0x18000ce40  mov     [rdi+1Ah], bx
0x18000ce44  mov     r12d, 0Ah
0x18000ce4a  mov     r9d, r12d; cchData
0x18000ce4d  lea     r8, [rbp+57h+LCData]; lpLCData
0x18000ce51  lea     edx, [r12+2]; LCType
0x18000ce56  mov     ecx, 400h; Locale
0x18000ce5b  call    cs:__imp_GetLocaleInfoW
0x18000ce61  xor     ecx, ecx
0x18000ce63  test    eax, eax
0x18000ce65  jnz     short loc_18000CE88
0x18000ce67  call    cs:__imp_GetLastError
0x18000ce6d  lea     r9d, [r12-1]; MaxCount
0x18000ce72  lea     r8, Source; ","
0x18000ce79  mov     edx, r12d; SizeInWords
0x18000ce7c  lea     rcx, [rbp+57h+LCData]; Destination
0x18000ce80  call    cs:__imp_wcsncpy_s
0x18000ce86  xor     ecx, ecx
0x18000ce88  lea     rax, [rbp+57h+LCData]
0x18000ce8c  mov     r12, r14
0x18000ce8f  inc     r12
0x18000ce92  cmp     [rax+r12*2], cx
0x18000ce97  jnz     short loc_18000CE8F
0x18000ce99  lea     r9, asc_180028E04; "."
0x18000cea0  mov     r8d, 0Ah; SizeInWords
0x18000cea6  lea     rdx, [rbp+57h+Destination]; Destination
0x18000ceaa  mov     ecx, 128h; uID
0x18000ceaf  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18000ceb4  lea     rcx, [rbp+57h+Destination]
0x18000ceb8  mov     r8, r14
0x18000cebb  xor     eax, eax
0x18000cebd  inc     r8
0x18000cec0  cmp     [rcx+r8*2], ax
0x18000cec5  jnz     short loc_18000CEBD
0x18000cec7  cmp     [rdi+1Ah], ax
0x18000cecb  jnz     short loc_18000CED2
0x18000cecd  add     r15, rbx
0x18000ced0  jmp     short loc_18000CF0C
0x18000ced2  mov     ecx, eax
0x18000ced4  cmp     cx, [rdi+1Ah]
0x18000ced8  jnb     short loc_18000CF0C
0x18000ceda  test    rsi, rsi
0x18000cedd  jz      short loc_18000CF05
0x18000cedf  mov     rdx, r14
0x18000cee2  inc     rdx
0x18000cee5  cmp     [rsi+rdx*2], ax
0x18000cee9  jnz     short loc_18000CEE2
0x18000ceeb  lea     rax, [r12+1]
0x18000cef0  add     rax, rdx
0x18000cef3  add     r15, rax
0x18000cef6  lea     rsi, [rsi+rdx*2]
0x18000cefa  add     rsi, 2
0x18000cefe  add     cx, bx
0x18000cf01  xor     eax, eax
0x18000cf03  jmp     short loc_18000CED4
0x18000cf05  sub     cx, bx
0x18000cf08  mov     [rdi+1Ah], cx
0x18000cf0c  add     r15, r8
0x18000cf0f  lea     rdx, [r15+r15]; uBytes
0x18000cf13  xor     ecx, ecx; uFlags
0x18000cf15  call    cs:__imp_LocalAlloc
0x18000cf1b  mov     [r13+0], rax
0x18000cf1f  xor     r12d, r12d
0x18000cf22  test    rax, rax
0x18000cf25  jz      loc_18000D02C
0x18000cf2b  lea     r8, [rbp+57h+var_D0]
0x18000cf2f  cmp     [rbp+57h+var_B8], 8
0x18000cf34  cmovnb  r8, [rbp+57h+var_D0]; unsigned __int16 *
0x18000cf39  mov     rdx, r15; unsigned __int64
0x18000cf3c  mov     rcx, rax; unsigned __int16 *
0x18000cf3f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cf44  cmp     [rdi+1Ah], r12w
0x18000cf49  jnz     short loc_18000CF73
0x18000cf4b  lea     r8, asc_180028E08; " "
0x18000cf52  mov     rdx, r15; unsigned __int64
0x18000cf55  mov     rcx, [r13+0]; unsigned __int16 *
0x18000cf59  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cf5e  lea     r8, [rbp+57h+Destination]; unsigned __int16 *
0x18000cf62  mov     rdx, r15; unsigned __int64
0x18000cf65  mov     rcx, [r13+0]; unsigned __int16 *
0x18000cf69  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cf6e  jmp     loc_18000D02C
0x18000cf73  mov     esi, [rdi+24h]
0x18000cf76  add     rsi, rdi
0x18000cf79  jnz     short loc_18000CFBD
0x18000cf7b  cmp     [rbp+57h+var_A0], r12
0x18000cf7f  jnz     short loc_18000CFA9
0x18000cf81  mov     edx, 123h
0x18000cf86  lea     rcx, [rbp+57h+var_90]
0x18000cf8a  call    ?load_wstring@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z; load_wstring(int)
0x18000cf8f  mov     rdx, rax
0x18000cf92  lea     rcx, [rbp+57h+var_B0]
0x18000cf96  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000cf9b  xor     r8d, r8d
0x18000cf9e  mov     dl, bl
0x18000cfa0  lea     rcx, [rbp+57h+var_90]
0x18000cfa4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000cfa9  lea     rsi, [rbp+57h+var_B0]
0x18000cfad  cmp     [rbp+57h+var_98], 8
0x18000cfb2  cmovnb  rsi, [rbp+57h+var_B0]
0x18000cfb7  mov     [rdi+1Ah], bx
0x18000cfbb  jmp     short loc_18000CFC5
0x18000cfbd  xor     eax, eax
0x18000cfbf  cmp     ax, [rdi+1Ah]
0x18000cfc3  jnb     short loc_18000D02C
0x18000cfc5  lea     r8, asc_180028E08; " "
0x18000cfcc  mov     rdx, r15; unsigned __int64
0x18000cfcf  mov     rcx, [r13+0]; unsigned __int16 *
0x18000cfd3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cfd8  mov     r8, rsi; unsigned __int16 *
0x18000cfdb  mov     rdx, r15; unsigned __int64
0x18000cfde  mov     rcx, [r13+0]; unsigned __int16 *
0x18000cfe2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000cfe7  movzx   ecx, word ptr [rdi+1Ah]
0x18000cfeb  sub     ecx, ebx
0x18000cfed  movzx   eax, r12w
0x18000cff1  lea     r8, [rbp+57h+LCData]
0x18000cff5  lea     rdx, [rbp+57h+Destination]
0x18000cff9  cmp     eax, ecx
0x18000cffb  cmovz   r8, rdx; unsigned __int16 *
0x18000cfff  mov     rdx, r15; unsigned __int64
0x18000d002  mov     rcx, [r13+0]; unsigned __int16 *
0x18000d006  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000d00b  mov     rax, r14
0x18000d00e  xor     ecx, ecx
0x18000d010  inc     rax
0x18000d013  cmp     [rsi+rax*2], cx
0x18000d017  jnz     short loc_18000D010
0x18000d019  lea     rsi, [rsi+rax*2]
0x18000d01d  add     rsi, 2
0x18000d021  add     r12w, bx
0x18000d025  cmp     r12w, [rdi+1Ah]
0x18000d02a  jb      short loc_18000CFC5
0x18000d02c  xor     r8d, r8d
0x18000d02f  mov     dl, bl
0x18000d031  lea     rcx, [rbp+57h+var_B0]
0x18000d035  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d03a  nop
0x18000d03b  mov     dl, bl
0x18000d03d  xor     r8d, r8d
0x18000d040  lea     rcx, [rbp+57h+var_D0]
0x18000d044  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d049  mov     rcx, [rbp+57h+var_40]
0x18000d04d  xor     rcx, rsp; StackCookie
0x18000d050  call    __security_check_cookie
0x18000d055  mov     rbx, [rsp+0F0h+arg_18]
0x18000d05d  add     rsp, 0C0h
0x18000d064  pop     r15
0x18000d066  pop     r14
0x18000d068  pop     r13
0x18000d06a  pop     r12
0x18000d06c  pop     rdi
0x18000d06d  pop     rsi
0x18000d06e  pop     rbp
0x18000d06f  retn
```
