# ResolvePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x14004a4d4`
- end: `0x14004a690`
- name: `?ResolvePath@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAV12@@Z`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14004ccc4`

## callees

- `0x140002c10`
- `0x140002dd0`
- `0x140004950`
- `0x1400102a0`
- `0x14002fa90`
- `0x140033ab0`
- `0x14004a4d4`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x14004a5da`
- `KERNEL32!GetFullPathNameW` at `0x14004a5da`
- `KERNEL32!GetLastError` at `0x14004a623`
- `KERNEL32!GetLastError` at `0x14004a623`
- `VCRUNTIME140!wcsrchr` at `0x14004a52b`
- `VCRUNTIME140!wcsrchr` at `0x14004a52b`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004a5f2`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x14004a5f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ResolvePath(__int64 a1, _QWORD *a2, LPWSTR *a3)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  wchar_t *v7; // rbx
  wchar_t *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rdx
  DWORD FullPathNameW; // esi
  int v13; // eax
  unsigned int v14; // edi
  signed int LastError; // eax
  _QWORD v17[3]; // [rsp+20h] [rbp-18h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp+20h] BYREF

  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  Str = (wchar_t *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24);
  ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, a1);
  v7 = Str;
  v8 = wcsrchr(Str, 0x5Cu);
  if ( !v8 || (v9 = v8 - v7, (int)v9 < 0) )
  {
    v14 = -2147024809;
    goto LABEL_20;
  }
  _mm_lfence();
  v10 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
          &Str,
          v17,
          0,
          (unsigned int)(v9 + 1));
  ATL::CSimpleStringT<unsigned short,0>::operator=(&Str, v10);
  v11 = (_QWORD *)(v17[0] - 24LL);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17[0] - 24LL + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  }
  ATL::CSimpleStringT<unsigned short,0>::Append(&Str, *a2, *(unsigned int *)(*a2 - 16LL));
  if ( ((1 - *((_DWORD *)*a3 - 2)) | (*((_DWORD *)*a3 - 3) - 261)) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a3, 261);
  v7 = Str;
  FullPathNameW = GetFullPathNameW(Str, 0x104u, *a3, 0);
  if ( *a3 )
  {
    v13 = wcsnlen(*a3, *((int *)*a3 - 3));
    if ( v13 < 0 )
      goto LABEL_23;
  }
  else
  {
    v13 = 0;
  }
  if ( v13 > *((_DWORD *)*a3 - 3) )
LABEL_23:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)*a3 - 4) = v13;
  (*a3)[v13] = 0;
  if ( FullPathNameW <= 0x104 )
  {
    if ( FullPathNameW )
    {
      v14 = 0;
    }
    else
    {
      LastError = GetLastError();
      v14 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v14 = LastError;
    }
  }
  else
  {
    v14 = -2147467259;
  }
LABEL_20:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  return v14;
}

```

## disassembly

```asm
0x14004a4d4  mov     [rsp+arg_0], rbx
0x14004a4d9  mov     [rsp+arg_8], rbp
0x14004a4de  mov     [rsp+arg_10], rsi
0x14004a4e3  push    rdi
0x14004a4e4  sub     rsp, 30h
0x14004a4e8  mov     rdi, r8
0x14004a4eb  mov     rsi, rdx
0x14004a4ee  mov     rbx, rcx
0x14004a4f1  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ
0x14004a4f6  mov     rcx, rax
0x14004a4f9  xor     ebp, ebp
0x14004a4fb  test    rax, rax
0x14004a4fe  jz      loc_14004A685
0x14004a504  mov     rax, [rax]
0x14004a507  call    qword ptr [rax+18h]
0x14004a50a  add     rax, 18h
0x14004a50e  mov     [rsp+38h+Str], rax
0x14004a513  mov     rdx, rbx
0x14004a516  lea     rcx, [rsp+38h+Str]
0x14004a51b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z
0x14004a520  lea     edx, [rbp+5Ch]; Ch
0x14004a523  mov     rbx, [rsp+38h+Str]
0x14004a528  mov     rcx, rbx; Str
0x14004a52b  call    cs:__imp_wcsrchr
0x14004a531  test    rax, rax
0x14004a534  jz      loc_14004A63D
0x14004a53a  sub     rax, rbx
0x14004a53d  sar     rax, 1
0x14004a540  test    eax, eax
0x14004a542  js      loc_14004A63D
0x14004a548  lfence
0x14004a54b  lea     r9d, [rax+1]
0x14004a54f  xor     r8d, r8d
0x14004a552  lea     rdx, [rsp+38h+var_18]
0x14004a557  lea     rcx, [rsp+38h+Str]
0x14004a55c  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z
0x14004a561  nop
0x14004a562  mov     rdx, rax
0x14004a565  lea     rcx, [rsp+38h+Str]
0x14004a56a  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z
0x14004a56f  nop
0x14004a570  mov     rdx, [rsp+38h+var_18]
0x14004a575  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14004a579  or      eax, 0FFFFFFFFh
0x14004a57c  lock xadd [rdx+10h], eax
0x14004a581  sub     eax, 1
0x14004a584  jg      short loc_14004A592
0x14004a586  lfence
0x14004a589  mov     rcx, [rdx]
0x14004a58c  mov     rax, [rcx]
0x14004a58f  call    qword ptr [rax+8]
0x14004a592  mov     rdx, [rsi]
0x14004a595  mov     r8d, [rdx-10h]
0x14004a599  lea     rcx, [rsp+38h+Str]
0x14004a59e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z
0x14004a5a3  mov     rax, [rdi]
0x14004a5a6  mov     r8d, 1
0x14004a5ac  sub     r8d, [rax-8]
0x14004a5b0  mov     ecx, [rax-0Ch]
0x14004a5b3  mov     edx, 105h
0x14004a5b8  sub     ecx, edx
0x14004a5ba  or      ecx, r8d
0x14004a5bd  jge     short loc_14004A5C7
0x14004a5bf  mov     rcx, rdi
0x14004a5c2  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z
0x14004a5c7  xor     r9d, r9d; lpFilePart
0x14004a5ca  mov     r8, [rdi]; lpBuffer
0x14004a5cd  mov     edx, 104h; nBufferLength
0x14004a5d2  mov     rbx, [rsp+38h+Str]
0x14004a5d7  mov     rcx, rbx; lpFileName
0x14004a5da  call    cs:__imp_GetFullPathNameW
0x14004a5e0  mov     esi, eax
0x14004a5e2  mov     rcx, [rdi]; Source
0x14004a5e5  test    rcx, rcx
0x14004a5e8  jnz     short loc_14004A5EE
0x14004a5ea  mov     eax, ebp
0x14004a5ec  jmp     short loc_14004A5FC
0x14004a5ee  movsxd  rdx, dword ptr [rcx-0Ch]; MaxCount
0x14004a5f2  call    cs:__imp_wcsnlen
0x14004a5f8  test    eax, eax
0x14004a5fa  js      short loc_14004A677
0x14004a5fc  mov     rcx, [rdi]
0x14004a5ff  cmp     eax, [rcx-0Ch]
0x14004a602  jg      short loc_14004A677
0x14004a604  mov     [rcx-10h], eax
0x14004a607  mov     ecx, eax
0x14004a609  mov     rax, [rdi]
0x14004a60c  mov     [rax+rcx*2], bp
0x14004a610  cmp     esi, 104h
0x14004a616  jbe     short loc_14004A61F
0x14004a618  mov     edi, 80004005h
0x14004a61d  jmp     short loc_14004A642
0x14004a61f  test    esi, esi
0x14004a621  jnz     short loc_14004A639
0x14004a623  call    cs:__imp_GetLastError
0x14004a629  movzx   edi, ax
0x14004a62c  or      edi, 80070000h
0x14004a632  test    eax, eax
0x14004a634  cmovle  edi, eax
0x14004a637  jmp     short loc_14004A642
0x14004a639  mov     edi, ebp
0x14004a63b  jmp     short loc_14004A642
0x14004a63d  mov     edi, 80070057h
0x14004a642  lea     rdx, [rbx-18h]
0x14004a646  or      ecx, 0FFFFFFFFh
0x14004a649  lock xadd [rdx+10h], ecx
0x14004a64e  sub     ecx, 1
0x14004a651  jg      short loc_14004A660
0x14004a653  lfence
0x14004a656  mov     rcx, [rdx]
0x14004a659  mov     r8, [rcx]
0x14004a65c  call    qword ptr [r8+8]
0x14004a660  mov     eax, edi
0x14004a662  mov     rbx, [rsp+38h+arg_0]
0x14004a667  mov     rbp, [rsp+38h+arg_8]
0x14004a66c  mov     rsi, [rsp+38h+arg_10]
0x14004a671  add     rsp, 30h
0x14004a675  pop     rdi
0x14004a676  retn
0x14004a677  mov     ecx, 80070057h; int
0x14004a67c  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x14004a682  jmp     short $+2
0x14004a684  nop
0x14004a685  mov     ecx, 80004005h; int
0x14004a68a  call    ?AtlThrowImpl@ATL@@YAXJ@Z
```
