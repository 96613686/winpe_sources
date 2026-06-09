# _AttributesFromPath(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800763b0`
- end: `0x180076825`
- name: `?_AttributesFromPath@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `1141`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180005e40`
- `0x180006e94`
- `0x180006ec4`
- `0x180066c10`
- `0x1800763b0`
- `0x18007778c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180076707`
- `ntdll!RtlAllocateHeap` at `0x180076707`
- `ntdll!RtlFreeHeap` at `0x1800767a2`
- `ntdll!RtlFreeHeap` at `0x1800767a2`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800766ad`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800766ad`

## string_xrefs

- `0x180076680`: `StringCchCopyW failed to copy full path [%x]`
- `0x180076691`: `_AttributesFromPath`
- `0x1800764cc`: `_SetFileAttributeValue`
- `0x1800765d7`: `_SetFileAttributeValue`
- `0x18007672b`: `_SetFileAttributeValue`
- `0x180076778`: `_SetFileAttributeValue`
- `0x180076766`: `Failed to copy attribute value (index %d) [%x]`
- `0x1800764d3`: `StringCbCopy failed to copy string attribute (index %d) [%x]`
- `0x1800765c2`: `StringCbCopy failed to copy string attribute (index %d) [%x]`

## pseudocode

```c
__int64 __fastcall _AttributesFromPath(LPCWSTR **a1, __int64 a2, int a3)
{
  unsigned int v6; // edi
  __int64 v7; // rdi
  int IsOsComponent; // eax
  int v9; // r10d
  __int64 v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rdx
  _WORD *v13; // r8
  _WORD *v14; // rcx
  int v15; // r11d
  unsigned __int64 *v16; // rax
  __int64 v17; // rdx
  _WORD *v18; // r9
  _WORD *v19; // rcx
  WCHAR *v20; // r9
  __int64 v21; // rcx
  __int64 v22; // r8
  _WORD *v23; // rdx
  WCHAR *v24; // rdx
  int v25; // edi
  wchar_t *Heap; // rax
  int v27; // eax
  void *v28; // r8
  __int64 v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  LODWORD(v30) = 0;
  memset_0(pszPath, 0, 0x208u);
  if ( a2 )
  {
    v7 = 4;
    if ( (a3 & 4) == 0 )
      goto LABEL_18;
    IsOsComponent = _IsOsComponent(**a1);
    v9 = dword_1801553B4;
    LODWORD(v30) = IsOsComponent;
    if ( (unsigned int)dword_1801553B4 <= 2 )
    {
      *(_DWORD *)(a2 + 1088) = IsOsComponent;
    }
    else if ( dword_1801553B4 == 3 )
    {
      *(_QWORD *)(a2 + 1088) = v30;
    }
    else
    {
      if ( dword_1801553B4 != 4 )
        goto LABEL_18;
      v10 = 2;
      v11 = &v30;
      v12 = 260;
      v13 = (_WORD *)(a2 + 1088);
      do
      {
        if ( !v10 )
          break;
        if ( !*(_WORD *)v11 )
          break;
        *v13 = *(_WORD *)v11;
        v11 = (__int64 *)((char *)v11 + 2);
        ++v13;
        --v10;
        --v12;
      }
      while ( v12 );
      v14 = v13 - 1;
      if ( v12 )
        v14 = v13;
      *v14 = 0;
      if ( !v12 )
      {
        AslLogCallPrintf(
          1,
          "_SetFileAttributeValue",
          3178,
          "StringCbCopy failed to copy string attribute (index %d) [%x]",
          2,
          -2147024774);
        goto LABEL_18;
      }
    }
    *(_DWORD *)(a2 + 1608) = 2;
    *(_DWORD *)(a2 + 1612) = v9;
    *(_DWORD *)(a2 + 1616) = 1;
LABEL_18:
    if ( (*(_QWORD *)&a3 & 0x40000LL) != 0 )
    {
      v15 = dword_180155534;
      v31 = 0xBAD0BAD0BAD0BAD0uLL;
      switch ( dword_180155534 )
      {
        case 0:
          *(_DWORD *)(a2 + 9792) = -1160725808;
          goto LABEL_35;
        case 1:
        case 2:
          *(_DWORD *)(a2 + 9792) = -1160725808;
          goto LABEL_35;
        case 3:
          *(_QWORD *)(a2 + 9792) = 0xBAD0BAD0BAD0BAD0uLL;
          goto LABEL_35;
        case 4:
          v16 = &v31;
          v17 = 260;
          v18 = (_WORD *)(a2 + 9792);
          do
          {
            if ( !v7 )
              break;
            if ( !*(_WORD *)v16 )
              break;
            *v18 = *(_WORD *)v16;
            v16 = (unsigned __int64 *)((char *)v16 + 2);
            ++v18;
            --v7;
            --v17;
          }
          while ( v17 );
          v19 = v18 - 1;
          if ( v17 )
            v19 = v18;
          *v19 = 0;
          if ( !v17 )
          {
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3178,
              "StringCbCopy failed to copy string attribute (index %d) [%x]",
              18,
              -2147024774);
            break;
          }
LABEL_35:
          *(_DWORD *)(a2 + 10312) = 18;
          *(_DWORD *)(a2 + 10316) = v15;
          *(_DWORD *)(a2 + 10320) = 1;
          break;
      }
    }
    if ( (a3 & 2) != 0 )
    {
      v20 = pszPath;
      v21 = 2147483646;
      v22 = 260;
      v23 = **a1;
      do
      {
        if ( !v21 )
          break;
        if ( !*v23 )
          break;
        *v20++ = *v23++;
        --v21;
        --v22;
      }
      while ( v22 );
      v24 = v20 - 1;
      v6 = v22 == 0 ? 0x8007007A : 0;
      if ( v22 )
        v24 = v20;
      *v24 = 0;
      if ( !v22 )
      {
        AslLogCallPrintf(1, "_AttributesFromPath", 1415, "StringCchCopyW failed to copy full path [%x]", -2147024774);
        return v6;
      }
      if ( PathCchRemoveFileSpec(pszPath, 0x104u) >= 0 )
      {
        v25 = dword_18015539C;
        if ( (unsigned int)dword_18015539C <= 2 )
        {
          *(_DWORD *)(a2 + 544) = *(_DWORD *)pszPath;
          goto LABEL_59;
        }
        if ( dword_18015539C == 3 )
        {
          *(_QWORD *)(a2 + 544) = *(_QWORD *)pszPath;
          goto LABEL_59;
        }
        if ( dword_18015539C == 4 )
        {
          Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x20Au);
          *(_QWORD *)(a2 + 1080) = Heap;
          if ( !Heap )
          {
            AslLogCallPrintf(1, "_SetFileAttributeValue", 3144, "Failed to alloc memory for string value (index %d)", 1);
            return 0;
          }
          v27 = o_wmemcpy_s_0(Heap, 0x105u, pszPath, 0x104u);
          if ( v27 )
          {
            if ( v27 > 0 )
              v27 = (unsigned __int16)v27 | 0x80070000;
            AslLogCallPrintf(
              1,
              "_SetFileAttributeValue",
              3156,
              "Failed to copy attribute value (index %d) [%x]",
              1,
              v27);
            v28 = *(void **)(a2 + 1080);
            if ( v28 )
            {
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
              *(_QWORD *)(a2 + 1080) = 0;
            }
            return 0;
          }
          *(_WORD *)(*(_QWORD *)(a2 + 1080) + 520LL) = 0;
          *(_WORD *)(a2 + 544) = 0;
LABEL_59:
          *(_DWORD *)(a2 + 1064) = 1;
          *(_DWORD *)(a2 + 1068) = v25;
          *(_DWORD *)(a2 + 1072) = 1;
        }
      }
    }
    return 0;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800763b0  mov     [rsp-8+arg_10], rbx
0x1800763b5  push    rbp
0x1800763b6  push    rsi
0x1800763b7  push    rdi
0x1800763b8  push    r12
0x1800763ba  push    r13
0x1800763bc  push    r14
0x1800763be  push    r15
0x1800763c0  lea     rbp, [rsp-160h]
0x1800763c8  sub     rsp, 260h
0x1800763cf  mov     rax, cs:__security_cookie
0x1800763d6  xor     rax, rsp
0x1800763d9  mov     [rbp+190h+var_40], rax
0x1800763e0  mov     rsi, r8
0x1800763e3  mov     rbx, rdx
0x1800763e6  mov     r14, rcx
0x1800763e9  xor     r15d, r15d
0x1800763ec  xor     edx, edx; Val
0x1800763ee  mov     dword ptr [rsp+290h+var_260], r15d
0x1800763f3  mov     r8d, 208h; Size
0x1800763f9  lea     rcx, [rsp+290h+pszPath]; void *
0x1800763fe  call    memset_0
0x180076403  test    rbx, rbx
0x180076406  jnz     short loc_180076412
0x180076408  mov     edi, 80070057h
0x18007640d  jmp     loc_1800767F9
0x180076412  mov     edi, 4
0x180076417  lea     r13d, [rdi-2]
0x18007641b  lea     r12d, [rdi-3]
0x18007641f  test    dil, sil
0x180076422  jz      loc_180076518
0x180076428  mov     rcx, [r14]
0x18007642b  mov     rcx, [rcx]; lpFileName
0x18007642e  call    ?_IsOsComponent@@YAHPEBG@Z; _IsOsComponent(ushort const *)
0x180076433  mov     r10d, cs:dword_1801553B4
0x18007643a  mov     ecx, r10d
0x18007643d  mov     dword ptr [rsp+290h+var_260], eax
0x180076441  test    r10d, r10d
0x180076444  jz      loc_1800764FD
0x18007644a  sub     ecx, r12d
0x18007644d  jz      loc_1800764FD
0x180076453  sub     ecx, r12d
0x180076456  jz      loc_1800764FD
0x18007645c  sub     ecx, r12d
0x18007645f  jz      loc_1800764EF
0x180076465  cmp     ecx, r12d
0x180076468  jnz     loc_180076518
0x18007646e  mov     eax, r13d
0x180076471  lea     rcx, [rsp+290h+var_260]
0x180076476  mov     edx, 104h
0x18007647b  lea     r8, [rbx+440h]
0x180076482  test    rax, rax
0x180076485  jz      short loc_1800764A3
0x180076487  movzx   r9d, word ptr [rcx]
0x18007648b  test    r9w, r9w
0x18007648f  jz      short loc_1800764A3
0x180076491  mov     [r8], r9w
0x180076495  add     rcx, r13
0x180076498  add     r8, r13
0x18007649b  sub     rax, r12
0x18007649e  sub     rdx, r12
0x1800764a1  jnz     short loc_180076482
0x1800764a3  mov     rax, rdx
0x1800764a6  lea     rcx, [r8-2]
0x1800764aa  neg     rax
0x1800764ad  sbb     r9d, r9d
0x1800764b0  not     r9d
0x1800764b3  and     r9d, 8007007Ah
0x1800764ba  test    rdx, rdx
0x1800764bd  cmovnz  rcx, r8
0x1800764c1  mov     [rcx], r15w
0x1800764c5  jnz     short loc_180076503
0x1800764c7  mov     [rsp+290h+var_268], r9d
0x1800764cc  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800764d3  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800764da  mov     [rsp+290h+var_270], r13d
0x1800764df  mov     r8d, 0C6Ah
0x1800764e5  mov     ecx, r12d
0x1800764e8  call    AslLogCallPrintf
0x1800764ed  jmp     short loc_180076518
0x1800764ef  mov     rax, [rsp+290h+var_260]
0x1800764f4  mov     [rbx+440h], rax
0x1800764fb  jmp     short loc_180076503
0x1800764fd  mov     [rbx+440h], eax
0x180076503  mov     [rbx+648h], r13d
0x18007650a  mov     [rbx+64Ch], r10d
0x180076511  mov     [rbx+650h], r12d
0x180076518  bt      rsi, 12h
0x18007651d  jnb     loc_18007661F
0x180076523  mov     r11d, cs:dword_180155534
0x18007652a  mov     rdx, 0BAD0BAD0BAD0BAD0h
0x180076534  mov     [rsp+290h+var_258], rdx
0x180076539  mov     ecx, r11d
0x18007653c  test    r11d, r11d
0x18007653f  jz      loc_1800765FD
0x180076545  sub     ecx, r12d
0x180076548  jz      loc_1800765F1
0x18007654e  sub     ecx, r12d
0x180076551  jz      loc_1800765F1
0x180076557  sub     ecx, r12d
0x18007655a  jz      loc_1800765E8
0x180076560  cmp     ecx, r12d
0x180076563  jnz     loc_18007661F
0x180076569  lea     rax, [rsp+290h+var_258]
0x18007656e  mov     edx, 104h
0x180076573  lea     r9, [rbx+2640h]
0x18007657a  test    rdi, rdi
0x18007657d  jz      short loc_180076599
0x18007657f  movzx   ecx, word ptr [rax]
0x180076582  test    cx, cx
0x180076585  jz      short loc_180076599
0x180076587  mov     [r9], cx
0x18007658b  add     rax, r13
0x18007658e  add     r9, r13
0x180076591  sub     rdi, r12
0x180076594  sub     rdx, r12
0x180076597  jnz     short loc_18007657A
0x180076599  mov     rax, rdx
0x18007659c  lea     rcx, [r9-2]
0x1800765a0  neg     rax
0x1800765a3  sbb     r10d, r10d
0x1800765a6  not     r10d
0x1800765a9  and     r10d, 8007007Ah
0x1800765b0  test    rdx, rdx
0x1800765b3  cmovnz  rcx, r9
0x1800765b7  mov     [rcx], r15w
0x1800765bb  jnz     short loc_180076607
0x1800765bd  mov     [rsp+290h+var_268], r10d
0x1800765c2  lea     r9, aStringcbcopyFa; "StringCbCopy failed to copy string attr"...
0x1800765c9  mov     r8d, 0C6Ah
0x1800765cf  mov     [rsp+290h+var_270], 12h
0x1800765d7  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x1800765de  mov     ecx, r12d
0x1800765e1  call    AslLogCallPrintf
0x1800765e6  jmp     short loc_18007661F
0x1800765e8  mov     [rbx+2640h], rdx
0x1800765ef  jmp     short loc_180076607
0x1800765f1  mov     dword ptr [rbx+2640h], 0BAD0BAD0h
0x1800765fb  jmp     short loc_180076607
0x1800765fd  mov     dword ptr [rbx+2640h], 0BAD0BAD0h
0x180076607  mov     dword ptr [rbx+2848h], 12h
0x180076611  mov     [rbx+284Ch], r11d
0x180076618  mov     [rbx+2850h], r12d
0x18007661f  test    r13b, sil
0x180076622  jz      loc_1800767F6
0x180076628  mov     rax, [r14]
0x18007662b  lea     r9, [rsp+290h+pszPath]
0x180076630  mov     esi, 104h
0x180076635  mov     ecx, 7FFFFFFEh
0x18007663a  mov     r8d, esi
0x18007663d  mov     rdx, [rax]
0x180076640  test    rcx, rcx
0x180076643  jz      short loc_18007665F
0x180076645  movzx   eax, word ptr [rdx]
0x180076648  test    ax, ax
0x18007664b  jz      short loc_18007665F
0x18007664d  mov     [r9], ax
0x180076651  add     rdx, r13
0x180076654  add     r9, r13
0x180076657  sub     rcx, r12
0x18007665a  sub     r8, r12
0x18007665d  jnz     short loc_180076640
0x18007665f  mov     rax, r8
0x180076662  lea     rdx, [r9-2]
0x180076666  neg     rax
0x180076669  sbb     edi, edi
0x18007666b  not     edi
0x18007666d  and     edi, 8007007Ah
0x180076673  test    r8, r8
0x180076676  cmovnz  rdx, r9
0x18007667a  mov     [rdx], r15w
0x18007667e  jnz     short loc_1800766A5
0x180076680  lea     r9, aStringcchcopyw_0; "StringCchCopyW failed to copy full path"...
0x180076687  mov     [rsp+290h+var_270], edi
0x18007668b  mov     r8d, 587h
0x180076691  lea     rdx, aAttributesfrom; "_AttributesFromPath"
0x180076698  mov     ecx, r12d
0x18007669b  call    AslLogCallPrintf
0x1800766a0  jmp     loc_1800767F9
0x1800766a5  mov     rdx, rsi; cchPath
0x1800766a8  lea     rcx, [rsp+290h+pszPath]; pszPath
0x1800766ad  call    cs:__imp_PathCchRemoveFileSpec
0x1800766b3  test    eax, eax
0x1800766b5  js      loc_1800767F6
0x1800766bb  mov     edi, cs:dword_18015539C
0x1800766c1  mov     ecx, edi
0x1800766c3  test    edi, edi
0x1800766c5  jz      loc_1800767D8
0x1800766cb  sub     ecx, r12d
0x1800766ce  jz      loc_1800767D8
0x1800766d4  sub     ecx, r12d
0x1800766d7  jz      loc_1800767D8
0x1800766dd  sub     ecx, r12d
0x1800766e0  jz      loc_1800767CA
0x1800766e6  cmp     ecx, r12d
0x1800766e9  jnz     loc_1800767F6
0x1800766ef  mov     rcx, gs:60h
0x1800766f8  mov     edx, 8; Flags
0x1800766fd  mov     r8d, 20Ah; Size
0x180076703  mov     rcx, [rcx+30h]; HeapHandle
0x180076707  call    cs:__imp_RtlAllocateHeap
0x18007670d  mov     [rbx+438h], rax
0x180076714  test    rax, rax
0x180076717  jnz     short loc_18007673F
0x180076719  lea     r9, aFailedToAllocM; "Failed to alloc memory for string value"...
0x180076720  mov     [rsp+290h+var_270], r12d
0x180076725  mov     r8d, 0C48h
0x18007672b  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x180076732  mov     ecx, r12d
0x180076735  call    AslLogCallPrintf
0x18007673a  jmp     loc_1800767F6
0x18007673f  mov     r9, rsi; N
0x180076742  lea     r8, [rsp+290h+pszPath]; S2
0x180076747  mov     edx, 105h; N1
0x18007674c  mov     rcx, rax; S1
0x18007674f  call    _o_wmemcpy_s_0
0x180076754  test    eax, eax
0x180076756  jz      short loc_1800767B1
0x180076758  jle     short loc_180076762
0x18007675a  movzx   eax, ax
0x18007675d  or      eax, 80070000h
0x180076762  mov     [rsp+290h+var_268], eax
0x180076766  lea     r9, aFailedToCopyAt; "Failed to copy attribute value (index %"...
0x18007676d  mov     r8d, 0C54h
0x180076773  mov     [rsp+290h+var_270], r12d
0x180076778  lea     rdx, aSetfileattribu_0; "_SetFileAttributeValue"
0x18007677f  mov     ecx, r12d
0x180076782  call    AslLogCallPrintf
0x180076787  mov     r8, [rbx+438h]; P
0x18007678e  test    r8, r8
0x180076791  jz      short loc_1800767F6
0x180076793  mov     rcx, gs:60h
0x18007679c  xor     edx, edx; Flags
0x18007679e  mov     rcx, [rcx+30h]; HeapHandle
0x1800767a2  call    cs:__imp_RtlFreeHeap
0x1800767a8  mov     [rbx+438h], r15
0x1800767af  jmp     short loc_1800767F6
0x1800767b1  mov     rcx, [rbx+438h]
0x1800767b8  mov     [rcx+208h], r15w
0x1800767c0  mov     [rbx+220h], r15w
0x1800767c8  jmp     short loc_1800767E2
0x1800767ca  mov     rax, qword ptr [rsp+290h+pszPath]
0x1800767cf  mov     [rbx+220h], rax
0x1800767d6  jmp     short loc_1800767E2
0x1800767d8  mov     eax, dword ptr [rsp+290h+pszPath]
0x1800767dc  mov     [rbx+220h], eax
0x1800767e2  mov     [rbx+428h], r12d
0x1800767e9  mov     [rbx+42Ch], edi
0x1800767ef  mov     [rbx+430h], r12d
0x1800767f6  mov     edi, r15d
0x1800767f9  mov     eax, edi
0x1800767fb  mov     rcx, [rbp+190h+var_40]
0x180076802  xor     rcx, rsp; StackCookie
0x180076805  call    __security_check_cookie
0x18007680a  mov     rbx, [rsp+290h+arg_10]
0x180076812  add     rsp, 260h
0x180076819  pop     r15
0x18007681b  pop     r14
0x18007681d  pop     r13
0x18007681f  pop     r12
0x180076821  pop     rdi
0x180076822  pop     rsi
0x180076823  pop     rbp
0x180076824  retn
```
