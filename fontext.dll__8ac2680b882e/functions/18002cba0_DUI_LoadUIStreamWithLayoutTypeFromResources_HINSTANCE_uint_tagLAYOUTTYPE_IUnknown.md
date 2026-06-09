# DUI_LoadUIStreamWithLayoutTypeFromResources(HINSTANCE__ *,uint,tagLAYOUTTYPE,IUnknown * *)

- ea: `0x18002cba0`
- end: `0x18002ccb2`
- name: `?DUI_LoadUIStreamWithLayoutTypeFromResources@@YAJPEAUHINSTANCE__@@IW4tagLAYOUTTYPE@@PEAPEAUIUnknown@@@Z`
- size: `274`
- prototype: `int __high(HINSTANCE, unsigned int, enum tagLAYOUTTYPE, struct IUnknown **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800166c0`

## callees

- `0x180004190`
- `0x18002cadc`
- `0x18002cba0`
- `0x18002cd40`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18002cbf8`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18002cbf8`
- `SHLWAPI!__imp_QISearch` at `0x18002cc6d`
- `SHLWAPI!__imp_QISearch` at `0x18002cc6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cc9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cc9d`

## pseudocode

```c
__int64 __fastcall DUI_LoadUIStreamWithLayoutTypeFromResources(__int64 a1, unsigned int a2, __int64 a3, void **a4)
{
  HINSTANCE v4; // rcx
  HRESULT UIFileFromResources; // ebx
  BYTE *v7; // rbp
  __int64 v8; // rdx
  IStream *v9; // rdi
  _QWORD *v10; // rax
  void *v11; // rsi
  BYTE *pInit; // [rsp+60h] [rbp+8h] BYREF

  v4 = g_hInstance;
  *a4 = 0;
  pInit = 0;
  UIFileFromResources = DUI_LoadUIFileFromResources(v4, a2, (unsigned __int16 **)&pInit);
  if ( UIFileFromResources >= 0 )
  {
    v7 = pInit;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&pInit[2 * v8] );
    v9 = SHCreateMemStream(pInit, 2 * (int)v8 + 2);
    if ( v9 )
    {
      v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      v11 = v10;
      if ( v10 )
      {
        *((_DWORD *)v10 + 4) = 1;
        *v10 = &CStreamWithLayoutType::`vftable'{for `IStream'};
        v10[1] = &CStreamWithLayoutType::`vftable'{for `ILayoutType'};
        *((_DWORD *)v10 + 5) = 3;
        v10[3] = v9;
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 8LL))(v9);
        UIFileFromResources = QISearch(
                                v11,
                                &`CStreamWithLayoutType::QueryInterface'::`2'::qit,
                                &GUID_00000000_0000_0000_c000_000000000046,
                                a4);
        CStreamWithLayoutType::Release((CStreamWithLayoutType *)v11);
      }
      else
      {
        UIFileFromResources = -2147024882;
      }
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      UIFileFromResources = -2147024882;
    }
    LocalFree(v7);
  }
  return (unsigned int)UIFileFromResources;
}

```

## disassembly

```asm
0x18002cba0  mov     [rsp+pInit], rcx
0x18002cba5  push    rbx
0x18002cba6  push    rbp
0x18002cba7  push    rsi
0x18002cba8  push    rdi
0x18002cba9  push    r14
0x18002cbab  push    r15
0x18002cbad  sub     rsp, 28h
0x18002cbb1  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18002cbb8  lea     r8, [rsp+58h+pInit]; unsigned __int16 **
0x18002cbbd  xor     r15d, r15d
0x18002cbc0  mov     r14, r9
0x18002cbc3  mov     [r9], r15
0x18002cbc6  mov     [rsp+58h+pInit], r15
0x18002cbcb  call    ?DUI_LoadUIFileFromResources@@YAJPEAUHINSTANCE__@@IPEAPEAG@Z; DUI_LoadUIFileFromResources(HINSTANCE__ *,uint,ushort * *)
0x18002cbd0  mov     ebx, eax
0x18002cbd2  test    eax, eax
0x18002cbd4  js      loc_18002CCA3
0x18002cbda  mov     rbp, [rsp+58h+pInit]
0x18002cbdf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002cbe3  inc     rdx
0x18002cbe6  cmp     [rbp+rdx*2+0], r15w
0x18002cbec  jnz     short loc_18002CBE3
0x18002cbee  lea     edx, ds:2[rdx*2]; cbInit
0x18002cbf5  mov     rcx, rbp; pInit
0x18002cbf8  call    cs:__imp_SHCreateMemStream
0x18002cbfe  mov     rdi, rax
0x18002cc01  test    rax, rax
0x18002cc04  jz      loc_18002CC95
0x18002cc0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cc11  mov     ecx, 20h ; ' '; unsigned __int64
0x18002cc16  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002cc1b  mov     rsi, rax
0x18002cc1e  test    rax, rax
0x18002cc21  jz      short loc_18002CC7F
0x18002cc23  lea     rax, ??_7CStreamWithLayoutType@@6BIStream@@@; const CStreamWithLayoutType::`vftable'{for `IStream'}
0x18002cc2a  mov     dword ptr [rsi+10h], 1
0x18002cc31  mov     [rsi], rax
0x18002cc34  lea     rax, ??_7CStreamWithLayoutType@@6BILayoutType@@@; const CStreamWithLayoutType::`vftable'{for `ILayoutType'}
0x18002cc3b  mov     [rsi+8], rax
0x18002cc3f  mov     dword ptr [rsi+14h], 3
0x18002cc46  mov     [rsi+18h], rdi
0x18002cc4a  mov     rcx, [rdi]
0x18002cc4d  mov     rax, [rcx+8]
0x18002cc51  mov     rcx, rdi
0x18002cc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc59  mov     r9, r14; ppv
0x18002cc5c  lea     r8, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18002cc63  lea     rdx, ?qit@?1??QueryInterface@CStreamWithLayoutType@@UEAAJAEBU_GUID@@PEAPEAX@Z@4QBUQITAB@@B; pqit
0x18002cc6a  mov     rcx, rsi; that
0x18002cc6d  call    cs:__imp_QISearch
0x18002cc73  mov     rcx, rsi; this
0x18002cc76  mov     ebx, eax
0x18002cc78  call    ?Release@CStreamWithLayoutType@@UEAAKXZ; CStreamWithLayoutType::Release(void)
0x18002cc7d  jmp     short loc_18002CC84
0x18002cc7f  mov     ebx, 8007000Eh
0x18002cc84  mov     rax, [rdi]
0x18002cc87  mov     rcx, rdi
0x18002cc8a  mov     rax, [rax+10h]
0x18002cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc93  jmp     short loc_18002CC9A
0x18002cc95  mov     ebx, 8007000Eh
0x18002cc9a  mov     rcx, rbp; hMem
0x18002cc9d  call    cs:__imp_LocalFree
0x18002cca3  mov     eax, ebx
0x18002cca5  add     rsp, 28h
0x18002cca9  pop     r15
0x18002ccab  pop     r14
0x18002ccad  pop     rdi
0x18002ccae  pop     rsi
0x18002ccaf  pop     rbp
0x18002ccb0  pop     rbx
0x18002ccb1  retn
```
