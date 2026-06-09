# MachineNameMapper::Convert(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> &,std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> &)

- ea: `0x180020270`
- end: `0x1800206a0`
- name: `?Convert@MachineNameMapper@@AEAA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@1@Z`
- size: `1072`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800206a8`

## callees

- `0x180001c88`
- `0x18000a760`
- `0x18000c4a4`
- `0x18000c500`
- `0x18000c8e8`
- `0x18000d49c`
- `0x18000e754`
- `0x18001e11c`
- `0x18001e620`
- `0x18001e684`
- `0x18001e7b0`
- `0x18001f220`
- `0x180020270`
- `0x180020b60`
- `0x1800254a0`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `msvcrt!wcschr` at `0x180020314`
- `msvcrt!wcschr` at `0x180020314`

## string_xrefs

- `0x18002044c`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall MachineNameMapper::Convert(__int64 a1, const wchar_t *a2, _QWORD *a3, _QWORD *a4)
{
  int v8; // r9d
  __int64 v10; // rax
  __int64 v11; // rsi
  _QWORD *v12; // rcx
  DWORD v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v16; // edi
  struct IErrorInfo *v17; // rdx
  int v18; // ebx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  int v22; // r9d
  char v23; // bl
  struct IErrorInfo *v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[5]; // [rsp+48h] [rbp-B8h] BYREF
  char Buffer[256]; // [rsp+70h] [rbp-90h] BYREF

  if ( !ourRole )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Running in standalone mode, skipping machine name cracking");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids, "NPSSVC");
    }
    return 0;
  }
  if ( !wcschr(a2, 0x2Eu) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Skipping cracking since machine name is in NetBIOS format: %S");
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_281547ddfe7f34c4b0b275762f080934_Traceguids,
        v8,
        (__int64)a2);
    }
    return 0;
  }
  std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>(v27);
  v10 = std::char_traits<unsigned short>::length(a2);
  std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::append(v27, a2, v10);
  v26 = 0;
  v11 = a1 + 80;
  v12 = v27;
  if ( v27[3] >= 8u )
    v12 = (_QWORD *)v27[0];
  v13 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, _QWORD *, _QWORD, __int64 *))(*(_QWORD *)(a1 + 80) + 8LL))(
          a1 + 80,
          2,
          10,
          2,
          v12,
          0,
          &v26);
  if ( v13 )
  {
    v14 = IASFormatSysErr(v13, Buffer);
    if ( v14 < 0x100uLL )
    {
      Buffer[v14] = 0;
      v16 = 4;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s failed: %s");
        WPP_SF_sss(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"Failed to crack machine name", (__int64)Buffer);
      }
      v17 = (struct IErrorInfo *)v26;
      if ( v26 )
      {
        v18 = 7;
        if ( **(_DWORD **)(v26 + 8) != 5 )
          v18 = 4;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
        v16 = v18;
      }
      _com_raise_error(v16, v17);
    }
    _report_rangecheckfailure(v15);
  }
  v19 = *(_QWORD *)(v26 + 8);
  if ( *(_DWORD *)v19 )
  {
    v23 = 0;
    if ( *(_DWORD *)v19 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Machine name not found in AD");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids, "NPSSVC");
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Could not crack machine name, status=%d");
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids);
    }
  }
  else
  {
    v20 = *(_QWORD *)(v19 + 16);
    v21 = -1;
    do
      ++v21;
    while ( *(_WORD *)(v20 + 2 * v21) );
    if ( v21 <= 4 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 24LL))(v11, v26);
      _com_raise_error(-2147418113, v24);
    }
    std::char_traits<unsigned short>::length(v20);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::assign(a3);
    if ( a4 != a3 )
      std::basic_string<unsigned short,std::char_traits<unsigned short>,StdAllocator<unsigned short>>::assign(a4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Successfully cracked machine name: %S");
      if ( a3[3] >= 8u )
        a3 = (_QWORD *)*a3;
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_281547ddfe7f34c4b0b275762f080934_Traceguids,
        v22,
        (__int64)a3);
    }
    v23 = 1;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 24LL))(v11, v26);
  LOBYTE(v25) = 1;
  std::wstring::_Tidy(v27, v25, 0);
  return v23;
}

```

## disassembly

```asm
0x180020270  push    rbp
0x180020272  push    rbx
0x180020273  push    rsi
0x180020274  push    rdi
0x180020275  push    r14
0x180020277  push    r15
0x180020279  lea     rbp, [rsp-88h]
0x180020281  sub     rsp, 188h
0x180020288  mov     rax, cs:__security_cookie
0x18002028f  xor     rax, rsp
0x180020292  mov     [rbp+0B0h+var_40], rax
0x180020296  mov     r14, r9
0x180020299  mov     rbx, r8
0x18002029c  mov     rsi, rdx
0x18002029f  mov     rdi, rcx
0x1800202a2  xor     r15d, r15d
0x1800202a5  cmp     cs:ourRole, r15d
0x1800202ac  jnz     short loc_18002030C
0x1800202ae  lea     rax, WPP_GLOBAL_Control
0x1800202b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800202bc  cmp     rcx, rax
0x1800202bf  jz      loc_180020371
0x1800202c5  cmp     byte ptr [rcx+19h], 2
0x1800202c9  jb      loc_180020371
0x1800202cf  lea     edi, [r15+4]
0x1800202d3  test    [rcx+1Ch], dil
0x1800202d7  jz      loc_180020371
0x1800202dd  lea     rcx, aRunningInStand; "Running in standalone mode, skipping ma"...
0x1800202e4  call    WppDbgPrint
0x1800202e9  lea     edx, [rdi+0Bh]
0x1800202ec  lea     r9, aNpssvc; "NPSSVC"
0x1800202f3  lea     r8, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids
0x1800202fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180020301  mov     rcx, [rcx+10h]
0x180020305  call    WPP_SF_s
0x18002030a  jmp     short loc_180020371
0x18002030c  mov     edx, 2Eh ; '.'; Ch
0x180020311  mov     rcx, rsi; Str
0x180020314  call    cs:__imp_wcschr
0x18002031a  test    rax, rax
0x18002031d  jnz     short loc_180020378
0x18002031f  lea     rax, WPP_GLOBAL_Control
0x180020326  mov     rcx, cs:WPP_GLOBAL_Control
0x18002032d  cmp     rcx, rax
0x180020330  jz      short loc_180020371
0x180020332  cmp     byte ptr [rcx+19h], 2
0x180020336  jb      short loc_180020371
0x180020338  mov     edi, 4
0x18002033d  test    [rcx+1Ch], dil
0x180020341  jz      short loc_180020371
0x180020343  mov     rdx, rsi
0x180020346  lea     rcx, aSkippingCracki; "Skipping cracking since machine name is"...
0x18002034d  call    WppDbgPrint
0x180020352  lea     edx, [rdi+0Ch]
0x180020355  mov     [rsp+1B0h+var_190], rsi
0x18002035a  lea     r8, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids
0x180020361  mov     rcx, cs:WPP_GLOBAL_Control
0x180020368  mov     rcx, [rcx+10h]
0x18002036c  call    WPP_SF_sS
0x180020371  xor     al, al
0x180020373  jmp     loc_180020684
0x180020378  lea     rdx, aHost; "host/"
0x18002037f  lea     rcx, [rsp+1B0h+var_168]; void *
0x180020384  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAA@PEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>(ushort const *)
0x180020389  nop
0x18002038a  mov     rcx, rsi
0x18002038d  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180020392  mov     r8, rax
0x180020395  mov     rdx, rsi
0x180020398  lea     rcx, [rsp+1B0h+var_168]
0x18002039d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800203a2  mov     [rsp+1B0h+var_170], r15
0x1800203a7  lea     rsi, [rdi+50h]
0x1800203ab  mov     rax, [rsi]
0x1800203ae  lea     rcx, [rsp+1B0h+var_168]
0x1800203b3  cmp     [rsp+1B0h+var_150], 8
0x1800203b9  cmovnb  rcx, [rsp+1B0h+var_168]
0x1800203bf  lea     rdx, [rsp+1B0h+var_170]
0x1800203c4  mov     [rsp+1B0h+var_180], rdx
0x1800203c9  mov     [rsp+1B0h+var_188], r15
0x1800203ce  mov     [rsp+1B0h+var_190], rcx
0x1800203d3  mov     edx, 2
0x1800203d8  mov     r9d, edx
0x1800203db  lea     r8d, [rdx+8]
0x1800203df  mov     rcx, rsi
0x1800203e2  mov     rax, [rax+8]
0x1800203e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203eb  test    eax, eax
0x1800203ed  jz      loc_1800204B9
0x1800203f3  lea     rdx, [rsp+1B0h+Buffer]; Buffer
0x1800203f8  mov     ecx, eax; dwMessageId
0x1800203fa  call    IASFormatSysErr
0x1800203ff  mov     eax, eax
0x180020401  cmp     rax, 100h
0x180020407  jnb     loc_1800204B3
0x18002040d  mov     [rsp+rax+1B0h+Buffer], r15b
0x180020412  lea     rax, WPP_GLOBAL_Control
0x180020419  mov     edi, 4
0x18002041e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020425  cmp     rcx, rax
0x180020428  jz      short loc_180020481
0x18002042a  cmp     byte ptr [rcx+19h], 2
0x18002042e  jb      short loc_180020481
0x180020430  test    [rcx+1Ch], dil
0x180020434  jz      short loc_180020481
0x180020436  lea     r9, [rsp+1B0h+Buffer]
0x18002043b  lea     rbx, aFailedToCrackM; "Failed to crack machine name"
0x180020442  mov     r8, rbx
0x180020445  lea     rdx, aNpssvc; "NPSSVC"
0x18002044c  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180020453  call    WppDbgPrint
0x180020458  lea     edx, [rdi+0Dh]
0x18002045b  lea     rax, [rsp+1B0h+Buffer]
0x180020460  mov     [rsp+1B0h+var_188], rax; __int64
0x180020465  mov     [rsp+1B0h+var_190], rbx; __int64
0x18002046a  lea     r8, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids
0x180020471  mov     rcx, cs:WPP_GLOBAL_Control
0x180020478  mov     rcx, [rcx+10h]; LoggerHandle
0x18002047c  call    WPP_SF_sss
0x180020481  mov     rdx, [rsp+1B0h+var_170]
0x180020486  test    rdx, rdx
0x180020489  jz      short loc_1800204AB
0x18002048b  mov     rax, [rdx+8]
0x18002048f  mov     ebx, 7
0x180020494  cmp     dword ptr [rax], 5
0x180020497  cmovnz  ebx, edi
0x18002049a  mov     rax, [rsi]
0x18002049d  mov     rcx, rsi
0x1800204a0  mov     rax, [rax+18h]
0x1800204a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204a9  mov     edi, ebx
0x1800204ab  mov     ecx, edi; int
0x1800204ad  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800204b3  call    __report_rangecheckfailure
0x1800204b9  mov     rax, [rsp+1B0h+var_170]
0x1800204be  mov     rcx, [rax+8]
0x1800204c2  mov     edx, [rcx]
0x1800204c4  test    edx, edx
0x1800204c6  jnz     loc_1800205A1
0x1800204cc  mov     rcx, [rcx+10h]
0x1800204d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800204d4  inc     rax
0x1800204d7  cmp     [rcx+rax*2], r15w
0x1800204dc  jnz     short loc_1800204D4
0x1800204de  mov     edi, 4
0x1800204e3  cmp     rax, rdi
0x1800204e6  jbe     loc_180020582
0x1800204ec  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800204f1  mov     r8, rax
0x1800204f4  mov     rdx, rcx
0x1800204f7  mov     rcx, rbx; void *
0x1800204fa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@PEBG_K@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800204ff  cmp     r14, rbx
0x180020502  jz      short loc_180020516
0x180020504  or      r9, 0FFFFFFFFFFFFFFFFh
0x180020508  xor     r8d, r8d
0x18002050b  mov     rdx, rbx
0x18002050e  mov     rcx, r14; void *
0x180020511  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$StdAllocator@G@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,StdAllocator<ushort>> const &,unsigned __int64,unsigned __int64)
0x180020516  lea     rax, WPP_GLOBAL_Control
0x18002051d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020524  cmp     rcx, rax
0x180020527  jz      short loc_18002057B
0x180020529  cmp     byte ptr [rcx+19h], 2
0x18002052d  jb      short loc_18002057B
0x18002052f  test    [rcx+1Ch], dil
0x180020533  jz      short loc_18002057B
0x180020535  cmp     qword ptr [rbx+18h], 8
0x18002053a  jb      short loc_180020541
0x18002053c  mov     rdx, [rbx]
0x18002053f  jmp     short loc_180020544
0x180020541  mov     rdx, rbx
0x180020544  lea     rcx, aSuccessfullyCr_1; "Successfully cracked machine name: %S"
0x18002054b  call    WppDbgPrint
0x180020550  cmp     qword ptr [rbx+18h], 8
0x180020555  jb      short loc_18002055A
0x180020557  mov     rbx, [rbx]
0x18002055a  mov     edx, 12h
0x18002055f  mov     [rsp+1B0h+var_190], rbx
0x180020564  lea     r8, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids
0x18002056b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020572  mov     rcx, [rcx+10h]
0x180020576  call    WPP_SF_sS
0x18002057b  mov     bl, 1
0x18002057d  jmp     loc_18002065E
0x180020582  mov     rax, [rsi]
0x180020585  mov     rdx, [rsp+1B0h+var_170]
0x18002058a  mov     rcx, rsi
0x18002058d  mov     rax, [rax+18h]
0x180020591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020596  mov     ecx, 8000FFFFh; int
0x18002059b  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
0x1800205a1  mov     bl, r15b
0x1800205a4  cmp     edx, 2
0x1800205a7  jnz     short loc_180020605
0x1800205a9  lea     rax, WPP_GLOBAL_Control
0x1800205b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205b7  cmp     rcx, rax
0x1800205ba  jz      loc_18002065E
0x1800205c0  cmp     [rcx+19h], dl
0x1800205c3  jb      loc_18002065E
0x1800205c9  lea     edi, [rdx+2]
0x1800205cc  test    [rcx+1Ch], dil
0x1800205d0  jz      loc_18002065E
0x1800205d6  lea     rcx, aMachineNameNot; "Machine name not found in AD"
0x1800205dd  call    WppDbgPrint
0x1800205e2  lea     edx, [rdi+0Fh]
0x1800205e5  lea     r9, aNpssvc; "NPSSVC"
0x1800205ec  lea     r8, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids
0x1800205f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205fa  mov     rcx, [rcx+10h]
0x1800205fe  call    WPP_SF_s
0x180020603  jmp     short loc_18002065E
0x180020605  lea     rax, WPP_GLOBAL_Control
0x18002060c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020613  cmp     rcx, rax
0x180020616  jz      short loc_18002065E
0x180020618  cmp     byte ptr [rcx+19h], 2
0x18002061c  jb      short loc_18002065E
0x18002061e  mov     edi, 4
0x180020623  test    [rcx+1Ch], dil
0x180020627  jz      short loc_18002065E
0x180020629  lea     rcx, aCouldNotCrackM; "Could not crack machine name, status=%d"
0x180020630  call    WppDbgPrint
0x180020635  mov     rax, [rsp+1B0h+var_170]
0x18002063a  mov     rax, [rax+8]
0x18002063e  lea     edx, [rdi+10h]
0x180020641  mov     eax, [rax]
0x180020643  mov     dword ptr [rsp+1B0h+var_190], eax
0x180020647  lea     r8, WPP_281547ddfe7f34c4b0b275762f080934_Traceguids
0x18002064e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020655  mov     rcx, [rcx+10h]
0x180020659  call    WPP_SF_sd
0x18002065e  mov     rcx, [rsi]
0x180020661  mov     rax, [rcx+18h]
0x180020665  mov     rdx, [rsp+1B0h+var_170]
0x18002066a  mov     rcx, rsi
0x18002066d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020672  nop
0x180020673  xor     r8d, r8d
0x180020676  mov     dl, 1
0x180020678  lea     rcx, [rsp+1B0h+var_168]
0x18002067d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180020682  mov     al, bl
0x180020684  mov     rcx, [rbp+0B0h+var_40]
0x180020688  xor     rcx, rsp; StackCookie
0x18002068b  call    __security_check_cookie
0x180020690  add     rsp, 188h
0x180020697  pop     r15
0x180020699  pop     r14
0x18002069b  pop     rdi
0x18002069c  pop     rsi
0x18002069d  pop     rbx
0x18002069e  pop     rbp
0x18002069f  retn
```
