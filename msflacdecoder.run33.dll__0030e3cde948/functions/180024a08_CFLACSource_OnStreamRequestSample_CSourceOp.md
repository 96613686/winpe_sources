# CFLACSource::OnStreamRequestSample(CSourceOp *)

- ea: `0x180024a08`
- end: `0x180024b4c`
- name: `?OnStreamRequestSample@CFLACSource@@AEAAJPEAVCSourceOp@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(CFLACSource *__hidden this, struct CSourceOp *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800229e0`

## callees

- `0x180020398`
- `0x180020484`
- `0x180021440`
- `0x180021a68`
- `0x180024a08`
- `0x180024c60`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180024a95`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180024a95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFLACSource::OnStreamRequestSample(LONG *this, struct CSourceOp *a2)
{
  unsigned int v4; // r8d
  __int64 v5; // rdx
  HRESULT v6; // eax
  __int64 v7; // rdx
  PROPVARIANT pvarSrc; // [rsp+40h] [rbp-20h] BYREF
  int v10; // [rsp+70h] [rbp+10h]

  v10 = CFLACSource::BeginAsyncOp((CFLACSource *)this, a2);
  if ( v10 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v5 = 170;
LABEL_14:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids, this, v4);
      return (unsigned int)v10;
    }
    return v4;
  }
  if ( *((_QWORD *)this + 33) )
  {
LABEL_11:
    v4 = CFLACSource::CompleteAsyncOp((CFLACSource *)this, a2);
    v10 = v4;
    if ( (v4 & 0x80000000) != 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v5 = 173;
      goto LABEL_14;
    }
    return v4;
  }
  memset(&pvarSrc, 0, sizeof(pvarSrc));
  pvarSrc.vt = 19;
  pvarSrc.lVal = this[70];
  *((_DWORD *)a2 + 10) = 0;
  v6 = PropVariantCopy((PROPVARIANT *)((char *)a2 + 16), &pvarSrc);
  v10 = v6;
  if ( v6 >= 0 )
  {
    *((_QWORD *)this + 33) = a2;
    (*(void (__fastcall **)(struct CSourceOp *, __int64, _QWORD))(*(_QWORD *)a2 + 8LL))(a2, v7, (unsigned int)v6);
    v10 = CFLACSource::ParseSampleData((CFLACSource *)this);
    if ( v10 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v5 = 172;
        goto LABEL_14;
      }
      return v4;
    }
    goto LABEL_11;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v5 = 171;
    goto LABEL_14;
  }
  return v4;
}

```

## disassembly

```asm
0x180024a08  mov     [rsp-8+arg_8], rbx
0x180024a0d  mov     [rsp-8+arg_10], rdi
0x180024a12  push    rbp
0x180024a13  mov     rbp, rsp
0x180024a16  sub     rsp, 60h
0x180024a1a  mov     rdi, rdx
0x180024a1d  mov     rbx, rcx
0x180024a20  mov     [rbp+arg_0], 0
0x180024a27  mov     [rbp+var_30], rcx
0x180024a2b  lea     rax, [rbp+arg_0]
0x180024a2f  mov     [rbp+var_28], rax
0x180024a33  call    ?BeginAsyncOp@CFLACSource@@AEAAJPEAVCSourceOp@@@Z; CFLACSource::BeginAsyncOp(CSourceOp *)
0x180024a38  mov     r8d, eax
0x180024a3b  mov     [rbp+arg_0], eax
0x180024a3e  test    eax, eax
0x180024a40  jns     short loc_180024A59
0x180024a42  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024a47  cmp     al, 1
0x180024a49  jb      loc_180024B37
0x180024a4f  mov     edx, 0AAh
0x180024a54  jmp     loc_180024B14
0x180024a59  cmp     qword ptr [rbx+108h], 0
0x180024a61  jnz     loc_180024AF1
0x180024a67  xorps   xmm0, xmm0
0x180024a6a  xor     eax, eax
0x180024a6c  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180024a70  mov     qword ptr [rbp+pvarSrc+10h], rax
0x180024a74  mov     eax, 13h
0x180024a79  mov     word ptr [rbp+pvarSrc], ax
0x180024a7d  mov     eax, [rbx+118h]
0x180024a83  mov     dword ptr [rbp+pvarSrc+8], eax
0x180024a86  mov     dword ptr [rdi+28h], 0
0x180024a8d  lea     rcx, [rdi+10h]; pvarDest
0x180024a91  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x180024a95  call    cs:__imp_PropVariantCopy
0x180024a9b  mov     r8d, eax
0x180024a9e  mov     [rbp+arg_0], eax
0x180024aa1  test    eax, eax
0x180024aa3  jns     short loc_180024AB9
0x180024aa5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024aaa  cmp     al, 1
0x180024aac  jb      loc_180024B37
0x180024ab2  mov     edx, 0ABh
0x180024ab7  jmp     short loc_180024B14
0x180024ab9  mov     [rbx+108h], rdi
0x180024ac0  mov     rax, [rdi]
0x180024ac3  mov     rcx, rdi
0x180024ac6  mov     rax, [rax+8]
0x180024aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024acf  mov     rcx, rbx; this
0x180024ad2  call    ?ParseSampleData@CFLACSource@@AEAAJXZ; CFLACSource::ParseSampleData(void)
0x180024ad7  mov     r8d, eax
0x180024ada  mov     [rbp+arg_0], eax
0x180024add  test    eax, eax
0x180024adf  jns     short loc_180024AF1
0x180024ae1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024ae6  cmp     al, 1
0x180024ae8  jb      short loc_180024B37
0x180024aea  mov     edx, 0ACh
0x180024aef  jmp     short loc_180024B14
0x180024af1  mov     rdx, rdi; struct CSourceOp *
0x180024af4  mov     rcx, rbx; this
0x180024af7  call    ?CompleteAsyncOp@CFLACSource@@AEAAJPEAVCSourceOp@@@Z; CFLACSource::CompleteAsyncOp(CSourceOp *)
0x180024afc  mov     r8d, eax
0x180024aff  mov     [rbp+arg_0], eax
0x180024b02  test    eax, eax
0x180024b04  jns     short loc_180024B37
0x180024b06  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180024b0b  cmp     al, 1
0x180024b0d  jb      short loc_180024B37
0x180024b0f  mov     edx, 0ADh
0x180024b14  mov     [rsp+60h+var_40], r8d
0x180024b19  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b20  mov     r9, rbx
0x180024b23  lea     r8, WPP_f10eb131cfa23f3cf4b620a531988b67_Traceguids
0x180024b2a  mov     rcx, [rcx+10h]
0x180024b2e  call    WPP_SF_qd
0x180024b33  mov     r8d, [rbp+arg_0]
0x180024b37  mov     eax, r8d
0x180024b3a  lea     r11, [rsp+60h+var_s0]
0x180024b3f  mov     rbx, [r11+18h]
0x180024b43  mov     rdi, [r11+20h]
0x180024b47  mov     rsp, r11
0x180024b4a  pop     rbp
0x180024b4b  retn
```
