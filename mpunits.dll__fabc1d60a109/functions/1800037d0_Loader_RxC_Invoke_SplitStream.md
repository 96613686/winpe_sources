# Loader_RxC_Invoke_SplitStream

- ea: `0x1800037d0`
- end: `0x180003b8f`
- name: `Loader_RxC_Invoke_SplitStream`
- size: `959`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b44`
- `0x1800037d0`
- `0x180006e64`
- `0x180006ef8`
- `0x180007c80`
- `0x180008ea0`
- `0x180008f20`
- `0x180036aa0`
- `0x180036c80`
- `0x18003bee0`
- `0x18003bf00`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003975`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003b21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003975`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180003b21`

## string_xrefs

- `0x180003966`: `mpunits.dll`
- `0x180003b16`: `mpunits.dll`

## pseudocode

```c
__int64 __fastcall Loader_RxC_Invoke_SplitStream(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 *a7)
{
  __int64 v7; // rdi
  __int64 v9; // r10
  char v10; // cl
  __int64 result; // rax
  unsigned int v12; // ebx
  bool v13; // zf
  const wchar_t *v14; // rsi
  const wchar_t *v15; // rcx
  char v16; // al
  int v17; // ecx
  char v18; // al
  const wchar_t *v19; // rsi
  HMODULE ModuleHandleA; // rax
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 *v24; // rsi
  __int64 v25; // rax
  HMODULE v26; // rax
  __int64 *v27; // [rsp+88h] [rbp+40h] BYREF

  v7 = (__int64)a7;
  v27 = 0;
  if ( !*((_BYTE *)a7 + 88) || !a7[10] || (v9 = Observable_FromInstance()) == 0 )
  {
    result = MI_ReportErrorDetails_MandatoryParameterMissing(L"upstreamPipe");
    goto LABEL_52;
  }
  v10 = *(_BYTE *)(v7 + 172);
  if ( !*(_BYTE *)(v7 + 180) )
  {
    if ( v10 )
    {
      v16 = *(_BYTE *)(v7 + 188);
      if ( v16 || *(_BYTE *)(v7 + 200) || *(_BYTE *)(v7 + 216) )
      {
        v12 = 4;
        if ( v16 )
        {
          v14 = L"IntervalCount";
        }
        else
        {
          v14 = L"Property";
          if ( !*(_BYTE *)(v7 + 200) )
            v14 = L"Until";
        }
        v15 = L"Duration";
        goto LABEL_18;
      }
      v17 = *(_DWORD *)(v7 + 136);
      if ( !v17 )
      {
        v18 = *(_BYTE *)(v7 + 132);
        if ( !v18 || !*(_DWORD *)(v7 + 96) )
        {
          result = RxcWindowInterval(v9, (int)v7 + 140, (unsigned int)v7 + (v18 != 0 ? 100 : 140), 0, (__int64)&v27);
          goto LABEL_10;
        }
      }
      v19 = L"Duration";
      if ( !v17 )
        v19 = L"Interval";
      ModuleHandleA = GetModuleHandleA("mpunits.dll");
      Intlstr_FormatString_FormatMessage(ModuleHandleA, 2103, v19);
    }
    else
    {
      if ( *(_BYTE *)(v7 + 200) )
      {
        v21 = *(_QWORD *)(v7 + 192);
        a7 = 0;
        result = DelegateFromPropertyArgument(v21, &a7);
        v12 = result;
        if ( (_DWORD)result )
          goto LABEL_53;
        if ( *(_BYTE *)(v7 + 216) )
        {
          v22 = ((__int64 (__fastcall *)(_QWORD))Delegate_FromInstance)(*(_QWORD *)(v7 + 208));
          v23 = ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(v7 + 80));
          v24 = a7;
          result = RxcGroupByUntil(v23, a7, v22, &v27);
        }
        else
        {
          v25 = ((__int64 (__fastcall *)(_QWORD))Observable_FromInstance)(*(_QWORD *)(v7 + 80));
          v24 = a7;
          result = RxcGroupBy(v25, a7, &v27);
        }
        v12 = result;
        if ( v24 )
        {
          result = *v24;
          if ( *v24 )
            result = (*(__int64 (__fastcall **)(__int64 *))(result + 16))(v24);
        }
        v13 = v12 == 0;
        goto LABEL_45;
      }
      v26 = GetModuleHandleA("mpunits.dll");
      Intlstr_GetString_LoadString(v26, 2102);
    }
    v12 = 4;
    result = MI_ReportErrorDetails_ForCustomError(4, (int)L"MI", 0, 0);
    goto LABEL_53;
  }
  if ( v10 || *(_BYTE *)(v7 + 132) || *(_BYTE *)(v7 + 200) || *(_BYTE *)(v7 + 216) )
  {
    v12 = 4;
    if ( v10 )
    {
      v14 = L"Duration";
    }
    else if ( *(_BYTE *)(v7 + 132) )
    {
      v14 = L"Interval";
    }
    else
    {
      v14 = L"Property";
      if ( !*(_BYTE *)(v7 + 200) )
        v14 = L"Until";
    }
    v15 = L"Count";
LABEL_18:
    result = MI_ReportErrorDetails_MutuallyExclusiveParameters(v15, v14);
    goto LABEL_53;
  }
  result = RxcWindowN(
             v9,
             *(unsigned int *)(v7 + 176),
             *(unsigned int *)((*(_BYTE *)(v7 + 188) != 0 ? 8 : 0) + v7 + 176),
             &v27);
LABEL_10:
  v12 = result;
  v13 = (_DWORD)result == 0;
LABEL_45:
  if ( v13 )
  {
    a7 = v27;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **, __int64, int))(*(_QWORD *)v7 + 80LL))(
               v7,
               0,
               &a7,
               15,
               0x40000000);
    v12 = result;
    if ( !(_DWORD)result )
    {
      if ( a2 )
      {
        result = *a2;
        if ( *a2 )
        {
          result = (*(__int64 (__fastcall **)(__int64 *, __int64))(result + 8))(a2, v7);
          v12 = result;
          goto LABEL_53;
        }
      }
LABEL_52:
      v12 = 4;
    }
  }
LABEL_53:
  if ( v27 )
  {
    result = *v27;
    if ( *v27 )
      result = (*(__int64 (**)(void))(result + 16))();
  }
  if ( a2 )
  {
    result = *a2;
    if ( *a2 )
      return (*(__int64 (__fastcall **)(__int64 *, _QWORD))result)(a2, v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800037d0  push    rbp
0x1800037d2  push    rbx
0x1800037d3  push    rsi
0x1800037d4  push    rdi
0x1800037d5  push    r14
0x1800037d7  push    r15
0x1800037d9  mov     rbp, rsp
0x1800037dc  sub     rsp, 48h
0x1800037e0  mov     rdi, [rbp+arg_30]
0x1800037e4  xor     r15d, r15d
0x1800037e7  mov     r14, rdx
0x1800037ea  mov     [rbp+arg_8], r15
0x1800037ee  cmp     [rdi+58h], r15b
0x1800037f2  jz      loc_180003B3D
0x1800037f8  mov     rcx, [rdi+50h]
0x1800037fc  test    rcx, rcx
0x1800037ff  jz      loc_180003B3D
0x180003805  mov     rax, cs:off_180047B90
0x18000380c  mov     rax, [rax+8]
0x180003810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003815  mov     r10, rax
0x180003818  test    rax, rax
0x18000381b  jz      loc_180003B3D
0x180003821  mov     cl, [rdi+0ACh]
0x180003827  cmp     [rdi+0B4h], r15b
0x18000382e  jz      loc_1800038D6
0x180003834  test    cl, cl
0x180003836  jnz     short loc_180003885
0x180003838  cmp     [rdi+84h], r15b
0x18000383f  jnz     short loc_180003885
0x180003841  cmp     [rdi+0C8h], r15b
0x180003848  jnz     short loc_180003885
0x18000384a  cmp     [rdi+0D8h], r15b
0x180003851  jnz     short loc_180003885
0x180003853  mov     al, [rdi+0BCh]
0x180003859  lea     r9, [rbp+arg_8]
0x18000385d  mov     edx, [rdi+0B0h]
0x180003863  neg     al
0x180003865  mov     rcx, r10
0x180003868  sbb     r8, r8
0x18000386b  and     r8d, 8
0x18000386f  mov     r8d, [r8+rdi+0B0h]
0x180003877  call    RxcWindowN
0x18000387c  mov     ebx, eax
0x18000387e  test    eax, eax
0x180003880  jmp     loc_180003ABC
0x180003885  mov     ebx, 4
0x18000388a  test    cl, cl
0x18000388c  jz      short loc_180003897
0x18000388e  lea     rsi, aDuration_0; "Duration"
0x180003895  jmp     short loc_1800038C2
0x180003897  cmp     [rdi+84h], r15b
0x18000389e  jz      short loc_1800038A9
0x1800038a0  lea     rsi, aInterval_0; "Interval"
0x1800038a7  jmp     short loc_1800038C2
0x1800038a9  cmp     [rdi+0C8h], r15b
0x1800038b0  lea     rsi, aProperty; "Property"
0x1800038b7  lea     rax, aUntil; "Until"
0x1800038be  cmovz   rsi, rax
0x1800038c2  lea     rcx, aCount_0; "Count"
0x1800038c9  mov     rdx, rsi
0x1800038cc  call    MI_ReportErrorDetails_MutuallyExclusiveParameters
0x1800038d1  jmp     loc_180003B4E
0x1800038d6  test    cl, cl
0x1800038d8  jz      loc_1800039FE
0x1800038de  mov     al, [rdi+0BCh]
0x1800038e4  test    al, al
0x1800038e6  jnz     loc_1800039C7
0x1800038ec  cmp     [rdi+0C8h], r15b
0x1800038f3  jnz     loc_1800039C7
0x1800038f9  cmp     [rdi+0D8h], r15b
0x180003900  jnz     loc_1800039C7
0x180003906  mov     ecx, [rdi+88h]
0x18000390c  test    ecx, ecx
0x18000390e  jnz     short loc_180003953
0x180003910  mov     al, [rdi+84h]
0x180003916  test    al, al
0x180003918  jz      short loc_180003920
0x18000391a  cmp     [rdi+60h], r15d
0x18000391e  jnz     short loc_180003953
0x180003920  neg     al
0x180003922  lea     rdx, [rdi+8Ch]
0x180003929  lea     rax, [rbp+arg_8]
0x18000392d  mov     rcx, r10
0x180003930  sbb     r8, r8
0x180003933  mov     [rsp+48h+var_28], rax
0x180003938  and     r8, 0FFFFFFFFFFFFFFD8h
0x18000393c  xor     r9d, r9d
0x18000393f  add     r8, 8Ch
0x180003946  add     r8, rdi
0x180003949  call    RxcWindowInterval
0x18000394e  jmp     loc_18000387C
0x180003953  test    ecx, ecx
0x180003955  lea     rax, aInterval_0; "Interval"
0x18000395c  xorps   xmm0, xmm0
0x18000395f  lea     rsi, aDuration_0; "Duration"
0x180003966  lea     rcx, ModuleName; "mpunits.dll"
0x18000396d  cmovz   rsi, rax
0x180003971  movups  [rbp+var_18], xmm0
0x180003975  call    cs:__imp_GetModuleHandleA
0x18000397b  mov     r8, rsi
0x18000397e  mov     edx, 837h
0x180003983  mov     rcx, rax
0x180003986  call    _Intlstr_FormatString_FormatMessage
0x18000398b  mov     byte ptr [rbp+var_18+8], 1
0x18000398f  mov     qword ptr [rbp+var_18], rax
0x180003993  lea     r9, [rbp+var_18]
0x180003997  movaps  xmm0, [rbp+var_18]
0x18000399b  lea     rdx, aMi; "MI"
0x1800039a2  mov     r8d, 5
0x1800039a8  mov     [rsp+48h+var_20], r15; __int64
0x1800039ad  movdqa  [rbp+var_18], xmm0
0x1800039b2  mov     [rsp+48h+var_28], r15; __int64
0x1800039b7  lea     ebx, [r8-1]
0x1800039bb  mov     ecx, ebx; int
0x1800039bd  call    MI_ReportErrorDetails_ForCustomError
0x1800039c2  jmp     loc_180003B4E
0x1800039c7  mov     ebx, 4
0x1800039cc  test    al, al
0x1800039ce  jz      short loc_1800039D9
0x1800039d0  lea     rsi, aIntervalcount; "IntervalCount"
0x1800039d7  jmp     short loc_1800039F2
0x1800039d9  cmp     [rdi+0C8h], r15b
0x1800039e0  lea     rsi, aProperty; "Property"
0x1800039e7  lea     rax, aUntil; "Until"
0x1800039ee  cmovz   rsi, rax
0x1800039f2  lea     rcx, aDuration_0; "Duration"
0x1800039f9  jmp     loc_1800038C9
0x1800039fe  cmp     [rdi+0C8h], r15b
0x180003a05  jz      loc_180003B13
0x180003a0b  mov     rcx, [rdi+0C0h]
0x180003a12  lea     rdx, [rbp+arg_30]
0x180003a16  mov     [rbp+arg_30], r15
0x180003a1a  call    DelegateFromPropertyArgument
0x180003a1f  mov     ebx, eax
0x180003a21  test    eax, eax
0x180003a23  jnz     loc_180003B4E
0x180003a29  cmp     [rdi+0D8h], r15b
0x180003a30  jz      short loc_180003A78
0x180003a32  mov     rax, cs:off_180047B98
0x180003a39  mov     rcx, [rdi+0D0h]
0x180003a40  mov     rax, [rax+8]
0x180003a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a49  mov     rcx, cs:off_180047B90
0x180003a50  mov     rbx, rax
0x180003a53  mov     rax, [rcx+8]
0x180003a57  mov     rcx, [rdi+50h]
0x180003a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a60  mov     rsi, [rbp+arg_30]
0x180003a64  lea     r9, [rbp+arg_8]
0x180003a68  mov     rdx, rsi
0x180003a6b  mov     rcx, rax
0x180003a6e  mov     r8, rbx
0x180003a71  call    RxcGroupByUntil
0x180003a76  jmp     short loc_180003A9F
0x180003a78  mov     rax, cs:off_180047B90
0x180003a7f  mov     rcx, [rdi+50h]
0x180003a83  mov     rax, [rax+8]
0x180003a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a8c  mov     rsi, [rbp+arg_30]
0x180003a90  lea     r8, [rbp+arg_8]
0x180003a94  mov     rdx, rsi
0x180003a97  mov     rcx, rax
0x180003a9a  call    RxcGroupBy
0x180003a9f  mov     ebx, eax
0x180003aa1  test    rsi, rsi
0x180003aa4  jz      short loc_180003ABA
0x180003aa6  mov     rax, [rsi]
0x180003aa9  test    rax, rax
0x180003aac  jz      short loc_180003ABA
0x180003aae  mov     rax, [rax+10h]
0x180003ab2  mov     rcx, rsi
0x180003ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aba  test    ebx, ebx
0x180003abc  jnz     loc_180003B4E
0x180003ac2  mov     rax, [rbp+arg_8]
0x180003ac6  lea     r8, [rbp+arg_30]
0x180003aca  mov     [rbp+arg_30], rax
0x180003ace  mov     r9d, 0Fh
0x180003ad4  mov     rax, [rdi]
0x180003ad7  xor     edx, edx
0x180003ad9  mov     rcx, rdi
0x180003adc  mov     dword ptr [rsp+48h+var_28], 40000000h
0x180003ae4  mov     rax, [rax+50h]
0x180003ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aed  mov     ebx, eax
0x180003aef  test    eax, eax
0x180003af1  jnz     short loc_180003B4E
0x180003af3  test    r14, r14
0x180003af6  jz      short loc_180003B49
0x180003af8  mov     rax, [r14]
0x180003afb  test    rax, rax
0x180003afe  jz      short loc_180003B49
0x180003b00  mov     rax, [rax+8]
0x180003b04  mov     rdx, rdi
0x180003b07  mov     rcx, r14
0x180003b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b0f  mov     ebx, eax
0x180003b11  jmp     short loc_180003B4E
0x180003b13  xorps   xmm0, xmm0
0x180003b16  lea     rcx, ModuleName; "mpunits.dll"
0x180003b1d  movups  [rbp+var_18], xmm0
0x180003b21  call    cs:__imp_GetModuleHandleA
0x180003b27  mov     rcx, rax
0x180003b2a  mov     edx, 836h
0x180003b2f  call    _Intlstr_GetString_LoadString
0x180003b34  mov     byte ptr [rbp+var_18+8], r15b
0x180003b38  jmp     loc_18000398F
0x180003b3d  lea     rcx, aUpstreampipe; "upstreamPipe"
0x180003b44  call    MI_ReportErrorDetails_MandatoryParameterMissing
0x180003b49  mov     ebx, 4
0x180003b4e  mov     rcx, [rbp+arg_8]
0x180003b52  test    rcx, rcx
0x180003b55  jz      short loc_180003B68
0x180003b57  mov     rax, [rcx]
0x180003b5a  test    rax, rax
0x180003b5d  jz      short loc_180003B68
0x180003b5f  mov     rax, [rax+10h]
0x180003b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b68  test    r14, r14
0x180003b6b  jz      short loc_180003B82
0x180003b6d  mov     rax, [r14]
0x180003b70  test    rax, rax
0x180003b73  jz      short loc_180003B82
0x180003b75  mov     rax, [rax]
0x180003b78  mov     edx, ebx
0x180003b7a  mov     rcx, r14
0x180003b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b82  add     rsp, 48h
0x180003b86  pop     r15
0x180003b88  pop     r14
0x180003b8a  pop     rdi
0x180003b8b  pop     rsi
0x180003b8c  pop     rbx
0x180003b8d  pop     rbp
0x180003b8e  retn
```
