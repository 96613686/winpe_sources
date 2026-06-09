# Microsoft::WRL::Module<2,HgServiceModule>::RegisterWinRTObject(wchar_t const *,wchar_t const * *,_RO_REGISTRATION_COOKIE * *,uint)

- ea: `0x180009e00`
- end: `0x180009f04`
- name: `?RegisterWinRTObject@?$Module@$01VHgServiceModule@@@WRL@Microsoft@@UEAAJPEB_WPEAPEB_WPEAPEAU_RO_REGISTRATION_COOKIE@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180002ac8`
- `0x180009e00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180009e9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009ece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009ece`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180009eb9`
- `api-ms-win-core-winrt-l1-1-0!RoRegisterActivationFactories` at `0x180009eb9`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,HgServiceModule>::RegisterWinRTObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned __int64 v6; // rax
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  HSTRING *v10; // rax
  HSTRING *v11; // r14
  int v12; // ebx
  unsigned int v13; // esi
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HRESULT String; // eax
  unsigned int i; // edi

  v6 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v6 = -1;
  v8 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v9 = 8LL * a5;
  if ( !is_mul_ok(a5, 8u) )
    v9 = -1;
  v10 = (HSTRING *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v8 && v10 )
  {
    v12 = 0;
    v13 = 0;
    if ( a5 )
    {
      while ( v12 >= 0 )
      {
        v14 = -1;
        v8[v13] = Microsoft::WRL::Details::ActivationFactoryCallback<2>;
        v15 = *(const WCHAR **)(a3 + 8LL * v13);
        do
          ++v14;
        while ( v15[v14] );
        String = WindowsCreateString(v15, v14, &v11[v13++]);
        v12 = String;
        if ( v13 >= a5 )
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
      v12 = RoRegisterActivationFactories(v11, v8, a5, a4);
    }
    for ( i = 0; i < v13; ++i )
      WindowsDeleteString(v11[i]);
  }
  else
  {
    v12 = -2147024882;
  }
  operator delete(v8);
  operator delete(v11);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180009e00  push    rbx
0x180009e02  push    rbp
0x180009e03  push    rsi
0x180009e04  push    rdi
0x180009e05  push    r12
0x180009e07  push    r13
0x180009e09  push    r14
0x180009e0b  push    r15
0x180009e0d  sub     rsp, 28h
0x180009e11  mov     edi, [rsp+68h+arg_20]
0x180009e18  mov     esi, 8
0x180009e1d  mov     eax, esi
0x180009e1f  mov     rbp, r9
0x180009e22  mul     rdi
0x180009e25  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e2c  mov     r12, r8
0x180009e2f  lea     r14, [rsi-9]
0x180009e33  cmovb   rax, r14
0x180009e37  mov     rcx, rax; unsigned __int64
0x180009e3a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009e3f  mov     r15, rax
0x180009e42  mov     eax, esi
0x180009e44  mul     rdi
0x180009e47  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e4e  cmovb   rax, r14
0x180009e52  mov     rcx, rax; unsigned __int64
0x180009e55  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009e5a  xor     r13d, r13d
0x180009e5d  mov     r14, rax
0x180009e60  test    r15, r15
0x180009e63  jz      short loc_180009EDC
0x180009e65  test    rax, rax
0x180009e68  jz      short loc_180009EDC
0x180009e6a  mov     ebx, r13d
0x180009e6d  mov     esi, r13d
0x180009e70  test    edi, edi
0x180009e72  jz      short loc_180009EAD
0x180009e74  test    ebx, ebx
0x180009e76  js      short loc_180009EC1
0x180009e78  mov     eax, esi
0x180009e7a  lea     rcx, ??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z; Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)
0x180009e81  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009e85  mov     [r15+rax*8], rcx
0x180009e89  mov     rcx, [r12+rax*8]; sourceString
0x180009e8d  inc     rdx; length
0x180009e90  cmp     [rcx+rdx*2], r13w
0x180009e95  jnz     short loc_180009E8D
0x180009e97  lea     r8, [r14+rax*8]; string
0x180009e9b  call    cs:__imp_WindowsCreateString
0x180009ea1  inc     esi
0x180009ea3  mov     ebx, eax
0x180009ea5  cmp     esi, edi
0x180009ea7  jb      short loc_180009E74
0x180009ea9  test    eax, eax
0x180009eab  js      short loc_180009EC1
0x180009ead  mov     r9, rbp
0x180009eb0  mov     r8d, edi
0x180009eb3  mov     rdx, r15
0x180009eb6  mov     rcx, r14
0x180009eb9  call    cs:__imp_RoRegisterActivationFactories
0x180009ebf  mov     ebx, eax
0x180009ec1  mov     edi, r13d
0x180009ec4  test    esi, esi
0x180009ec6  jz      short loc_180009EE1
0x180009ec8  mov     ecx, edi
0x180009eca  mov     rcx, [r14+rcx*8]; string
0x180009ece  call    cs:__imp_WindowsDeleteString
0x180009ed4  inc     edi
0x180009ed6  cmp     edi, esi
0x180009ed8  jb      short loc_180009EC8
0x180009eda  jmp     short loc_180009EE1
0x180009edc  mov     ebx, 8007000Eh
0x180009ee1  mov     rcx, r15; Block
0x180009ee4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009ee9  mov     rcx, r14; Block
0x180009eec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009ef1  mov     eax, ebx
0x180009ef3  add     rsp, 28h
0x180009ef7  pop     r15
0x180009ef9  pop     r14
0x180009efb  pop     r13
0x180009efd  pop     r12
0x180009eff  pop     rdi
0x180009f00  pop     rsi
0x180009f01  pop     rbp
0x180009f02  pop     rbx
0x180009f03  retn
```
