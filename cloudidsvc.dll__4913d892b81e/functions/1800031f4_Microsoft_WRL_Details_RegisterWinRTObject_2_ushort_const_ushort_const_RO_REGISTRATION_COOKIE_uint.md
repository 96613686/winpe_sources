# Microsoft::WRL::Details::RegisterWinRTObject<2>(ushort const *,ushort const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x1800031f4`
- end: `0x1800032f4`
- name: `??$RegisterWinRTObject@$01@Details@WRL@Microsoft@@YAJPEBGPEAPEBGPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006a10`

## callees

- `0x180001a74`
- `0x180001e2c`
- `0x1800031f4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800032be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800032be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000328b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000328b`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800032a9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x1800032a9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterWinRTObject<2>(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v7; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  unsigned __int64 v11; // rdx
  HSTRING *v12; // r14
  int v13; // ebx
  unsigned int v14; // esi
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  HRESULT String; // eax
  unsigned int i; // edi
  unsigned __int64 v19; // rdx

  v5 = a4;
  v7 = 8LL * a4;
  if ( !is_mul_ok(a4, 8u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8 * v5;
  if ( !is_mul_ok(v5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v10;
  if ( v8 && v10 )
  {
    v13 = 0;
    v14 = 0;
    if ( (_DWORD)v5 )
    {
      while ( v13 >= 0 )
      {
        v15 = -1;
        v8[v14] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v16 = *(const WCHAR **)(a2 + 8LL * v14);
        do
          ++v15;
        while ( v16[v15] );
        String = WindowsCreateString(v16, v15, &v12[v14++]);
        v13 = String;
        if ( v14 >= (unsigned int)v5 )
        {
          if ( String < 0 )
            break;
          goto LABEL_13;
        }
      }
    }
    else
    {
LABEL_13:
      v13 = RoRegisterActivationFactories(v12, v8, (unsigned int)v5, a3);
    }
    for ( i = 0; i < v14; ++i )
      WindowsDeleteString(v12[i]);
  }
  else
  {
    v13 = -2147024882;
  }
  operator delete(v8, v11);
  operator delete(v12, v19);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800031f4  push    rbx
0x1800031f6  push    rbp
0x1800031f7  push    rsi
0x1800031f8  push    rdi
0x1800031f9  push    r12
0x1800031fb  push    r13
0x1800031fd  push    r14
0x1800031ff  push    r15
0x180003201  sub     rsp, 28h
0x180003205  mov     r12, rdx
0x180003208  mov     edi, r9d
0x18000320b  mov     esi, 8
0x180003210  mov     rbp, r8
0x180003213  mov     eax, esi
0x180003215  mul     rdi
0x180003218  lea     r14, [rsi-9]
0x18000321c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003223  cmovb   rax, r14
0x180003227  mov     rcx, rax; unsigned __int64
0x18000322a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000322f  mov     r15, rax
0x180003232  mov     eax, esi
0x180003234  mul     rdi
0x180003237  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000323e  cmovb   rax, r14
0x180003242  mov     rcx, rax; unsigned __int64
0x180003245  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000324a  xor     r13d, r13d
0x18000324d  mov     r14, rax
0x180003250  test    r15, r15
0x180003253  jz      short loc_1800032CC
0x180003255  test    rax, rax
0x180003258  jz      short loc_1800032CC
0x18000325a  mov     ebx, r13d
0x18000325d  mov     esi, r13d
0x180003260  test    edi, edi
0x180003262  jz      short loc_18000329D
0x180003264  test    ebx, ebx
0x180003266  js      short loc_1800032B1
0x180003268  mov     eax, esi
0x18000326a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180003271  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180003275  mov     [r15+rax*8], rcx
0x180003279  mov     rcx, [r12+rax*8]; sourceString
0x18000327d  inc     rdx; length
0x180003280  cmp     [rcx+rdx*2], r13w
0x180003285  jnz     short loc_18000327D
0x180003287  lea     r8, [r14+rax*8]; string
0x18000328b  call    cs:__imp_WindowsCreateString
0x180003291  inc     esi
0x180003293  mov     ebx, eax
0x180003295  cmp     esi, edi
0x180003297  jb      short loc_180003264
0x180003299  test    eax, eax
0x18000329b  js      short loc_1800032B1
0x18000329d  mov     r9, rbp
0x1800032a0  mov     r8d, edi
0x1800032a3  mov     rdx, r15
0x1800032a6  mov     rcx, r14
0x1800032a9  call    cs:__imp_RoRegisterActivationFactories
0x1800032af  mov     ebx, eax
0x1800032b1  mov     edi, r13d
0x1800032b4  test    esi, esi
0x1800032b6  jz      short loc_1800032D1
0x1800032b8  mov     ecx, edi
0x1800032ba  mov     rcx, [r14+rcx*8]; string
0x1800032be  call    cs:__imp_WindowsDeleteString
0x1800032c4  inc     edi
0x1800032c6  cmp     edi, esi
0x1800032c8  jb      short loc_1800032B8
0x1800032ca  jmp     short loc_1800032D1
0x1800032cc  mov     ebx, 8007000Eh
0x1800032d1  mov     rcx, r15; void *
0x1800032d4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800032d9  mov     rcx, r14; void *
0x1800032dc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800032e1  mov     eax, ebx
0x1800032e3  add     rsp, 28h
0x1800032e7  pop     r15
0x1800032e9  pop     r14
0x1800032eb  pop     r13
0x1800032ed  pop     r12
0x1800032ef  pop     rdi
0x1800032f0  pop     rsi
0x1800032f1  pop     rbp
0x1800032f2  pop     rbx
0x1800032f3  retn
```
