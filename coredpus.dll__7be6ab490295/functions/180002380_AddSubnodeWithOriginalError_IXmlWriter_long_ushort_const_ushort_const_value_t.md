# AddSubnodeWithOriginalError(IXmlWriter *,long,ushort const *,ushort const *,value_t,...)

- ea: `0x180002380`
- end: `0x180002547`
- name: `?AddSubnodeWithOriginalError@@YAJPEAUIXmlWriter@@JPEBG1W4value_t@@ZZ`
- size: `455`
- prototype: `int __high(struct IXmlWriter *, int, const unsigned __int16 *, const unsigned __int16 *, enum value_t, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002590`

## callees

- `0x180002380`
- `0x1800029b0`
- `0x180014330`
- `0x180016428`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x1800024d6`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x1800024d6`

## pseudocode

```c
HRESULT __fastcall AddSubnodeWithOriginalError(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        const wchar_t *a4,
        int a5,
        unsigned __int16 *a6)
{
  HRESULT result; // eax
  __int64 v9; // r10
  __int64 v10; // r11
  unsigned __int16 *p_Buffer; // rsi
  size_t pcchLength; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 v13[2]; // [rsp+38h] [rbp-90h] BYREF
  wchar_t v14; // [rsp+3Ch] [rbp-8Ch]
  __int128 v15; // [rsp+3Eh] [rbp-8Ah]
  wchar_t Buffer; // [rsp+50h] [rbp-78h] BYREF
  __int128 v17; // [rsp+52h] [rbp-76h]
  __int128 v18; // [rsp+62h] [rbp-66h]
  _BYTE v19[30]; // [rsp+72h] [rbp-56h] BYREF

  pcchLength = 0;
  Buffer = 0;
  *(_DWORD *)v13 = *(_DWORD *)L"0x";
  v14 = a0x[2];
  memset(v19, 0, sizeof(v19));
  v17 = 0;
  v18 = 0;
  v15 = 0;
  if ( !a1 || !a4 )
    return -2147024809;
  result = StringLengthWorkerW(a4, 0x7FFFFFFFu, &pcchLength);
  if ( result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)a1 + 216LL))(a1, 0, v9, v10);
    if ( result >= 0 )
    {
      p_Buffer = 0;
      if ( a2 )
      {
        if ( (unsigned int)StringCchPrintfW(v13, 0xBu, L"0x%08X", a2) )
          return -2147024809;
        p_Buffer = v13;
        (*(void (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, _QWORD, unsigned __int16 *))(*(_QWORD *)a1 + 56LL))(
          a1,
          L"msft",
          L"originalerror",
          0,
          v13);
      }
      if ( !a5 )
        return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
      if ( a5 != 1 )
      {
        if ( a5 == 2 )
          p_Buffer = a6;
LABEL_16:
        result = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)a1 + 224LL))(a1, p_Buffer);
        if ( result < 0 )
          return result;
        return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 120LL))(a1);
      }
      if ( !_ltow_s((int)a6, &Buffer, 0x20u, 10) )
      {
        p_Buffer = &Buffer;
        goto LABEL_16;
      }
      return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002380  push    rbp
0x180002382  push    rdi
0x180002383  push    r14
0x180002385  sub     rsp, 0B0h
0x18000238c  mov     rax, cs:__security_cookie
0x180002393  xor     rax, rsp
0x180002396  mov     [rsp+0C8h+var_38], rax
0x18000239e  xorps   xmm0, xmm0
0x1800023a1  mov     [rsp+0C8h+pcchLength], 0
0x1800023aa  xor     eax, eax
0x1800023ac  lea     r14, [rsp+0C8h+arg_28]
0x1800023b4  mov     [rsp+0C8h+Buffer], ax
0x1800023b9  mov     r10, r9
0x1800023bc  mov     eax, dword ptr cs:a0x; "0x"
0x1800023c2  mov     r11, r8
0x1800023c5  mov     dword ptr [rsp+0C8h+var_90], eax
0x1800023c9  mov     ebp, edx
0x1800023cb  movzx   eax, word ptr cs:a0x+4; ""
0x1800023d2  mov     rdi, rcx
0x1800023d5  mov     [rsp+0C8h+var_8C], ax
0x1800023da  movups  xmmword ptr [rsp+0C8h+var_56], xmm0
0x1800023df  movups  [rsp+0C8h+var_76], xmm0
0x1800023e4  movups  [rsp+0C8h+var_66], xmm0
0x1800023e9  movups  xmmword ptr [rsp+0C8h+var_56+0Eh], xmm0
0x1800023f1  movups  [rsp+0C8h+var_8A], xmm0
0x1800023f6  test    rcx, rcx
0x1800023f9  jnz     short loc_180002405
0x1800023fb  mov     eax, 80070057h
0x180002400  jmp     loc_18000252A
0x180002405  test    r10, r10
0x180002408  jz      short loc_1800023FB
0x18000240a  lea     r8, [rsp+0C8h+pcchLength]; pcchLength
0x18000240f  mov     edx, 7FFFFFFFh; cchMax
0x180002414  mov     rcx, r10; psz
0x180002417  call    StringLengthWorkerW
0x18000241c  test    eax, eax
0x18000241e  js      loc_18000252A
0x180002424  mov     rax, [rdi]
0x180002427  mov     r9, r11
0x18000242a  mov     [rsp+0C8h+var_20], rbx
0x180002432  mov     r8, r10
0x180002435  mov     ebx, [rsp+0C8h+arg_20]
0x18000243c  xor     edx, edx
0x18000243e  mov     rcx, rdi
0x180002441  mov     rax, [rax+0D8h]
0x180002448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000244d  test    eax, eax
0x18000244f  js      loc_180002522
0x180002455  mov     [rsp+0C8h+var_28], rsi
0x18000245d  xor     esi, esi
0x18000245f  test    ebp, ebp
0x180002461  jz      short loc_1800024AF
0x180002463  mov     r9d, ebp
0x180002466  lea     r8, a0x08x; "0x%08X"
0x18000246d  mov     edx, 0Bh; unsigned __int64
0x180002472  lea     rcx, [rsp+0C8h+var_90]; unsigned __int16 *
0x180002477  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000247c  test    eax, eax
0x18000247e  jnz     short loc_1800024E6
0x180002480  mov     rax, [rdi]
0x180002483  lea     rcx, [rsp+0C8h+var_90]
0x180002488  mov     [rsp+0C8h+var_A8], rcx
0x18000248d  lea     r8, ?gc_szOrginalErrorAttribute@@3QBGB; "originalerror"
0x180002494  xor     r9d, r9d
0x180002497  lea     rdx, ?gc_szOrginalErrorNamespace@@3QBGB; "msft"
0x18000249e  mov     rcx, rdi
0x1800024a1  lea     rsi, [rsp+0C8h+var_90]
0x1800024a6  mov     rax, [rax+38h]
0x1800024aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024af  test    ebx, ebx
0x1800024b1  jz      short loc_18000250B
0x1800024b3  sub     ebx, 1
0x1800024b6  jz      short loc_1800024C2
0x1800024b8  cmp     ebx, 1
0x1800024bb  jnz     short loc_1800024F2
0x1800024bd  mov     rsi, [r14]
0x1800024c0  jmp     short loc_1800024F2
0x1800024c2  mov     ecx, [r14]; Value
0x1800024c5  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x1800024ca  mov     r9d, 0Ah; Radix
0x1800024d0  mov     r8d, 20h ; ' '; BufferCount
0x1800024d6  call    cs:__imp__ltow_s
0x1800024dd  nop     dword ptr [rax+rax+00h]
0x1800024e2  test    eax, eax
0x1800024e4  jz      short loc_1800024ED
0x1800024e6  mov     eax, 80070057h
0x1800024eb  jmp     short loc_18000251A
0x1800024ed  lea     rsi, [rsp+0C8h+Buffer]
0x1800024f2  mov     rax, [rdi]
0x1800024f5  mov     rdx, rsi
0x1800024f8  mov     rcx, rdi
0x1800024fb  mov     rax, [rax+0E0h]
0x180002502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002507  test    eax, eax
0x180002509  js      short loc_18000251A
0x18000250b  mov     rax, [rdi]
0x18000250e  mov     rcx, rdi
0x180002511  mov     rax, [rax+78h]
0x180002515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000251a  mov     rsi, [rsp+0C8h+var_28]
0x180002522  mov     rbx, [rsp+0C8h+var_20]
0x18000252a  mov     rcx, [rsp+0C8h+var_38]
0x180002532  xor     rcx, rsp; StackCookie
0x180002535  call    __security_check_cookie
0x18000253a  add     rsp, 0B0h
0x180002541  pop     r14
0x180002543  pop     rdi
0x180002544  pop     rbp
0x180002545  retn
```
