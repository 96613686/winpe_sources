# CMVUISelection2::GetCandidateList(ulong *,_MVUIITem * *)

- ea: `0x180027880`
- end: `0x180027aac`
- name: `?GetCandidateList@CMVUISelection2@@UEAAJPEAKPEAPEAU_MVUIITem@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(CandidateList **this, unsigned int *, struct _MVUIITem **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076a4`
- `0x180010084`
- `0x180012d80`
- `0x180012da0`
- `0x1800276b0`
- `0x180027880`
- `0x180027ab4`
- `0x180027b08`
- `0x18002b1a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800279c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800279cd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800279c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800279cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002793d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002793d`

## string_xrefs

- `0x180027a8a`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x180027a9b`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CMVUISelection2::GetCandidateList(CandidateList **this, unsigned int *a2, struct _MVUIITem **a3)
{
  CMVUISelection2 *v5; // r14
  __int64 result; // rax
  CandidateList *v7; // rcx
  unsigned int Count; // esi
  SIZE_T v9; // rax
  __int64 v10; // r9
  struct _MVUIITem *v11; // rax
  const char *v12; // r9
  struct _MVUIITem *v13; // rdi
  unsigned int i; // ebx
  __int64 v15; // r15
  ProfileSelection *v16; // rcx
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *KeyValue; // rax
  int v19; // r15d
  void **v20; // r14
  unsigned int j; // r14d
  const char *v22; // r9
  int v23; // [rsp+20h] [rbp-48h]
  int v24; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  void **v27; // [rsp+78h] [rbp+10h] BYREF
  __int64 v28; // [rsp+88h] [rbp+20h]

  v5 = (CMVUISelection2 *)this;
  if ( a2 )
  {
    if ( a3 )
    {
      try
      {
        v7 = this[3];
        if ( v7 )
        {
          Count = CandidateList::GetCount(v7);
          v27 = 0;
          v9 = 16LL * Count;
          if ( is_mul_ok(Count, 0x10u) )
          {
            v10 = 0;
          }
          else
          {
            v9 = -1;
            v10 = 2147942934LL;
          }
          if ( (int)v10 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3B,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
              (const char *)v10,
              v23);
          v11 = (struct _MVUIITem *)CoTaskMemRealloc(0, v9);
          v13 = v11;
          if ( Count && !v11 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x3F,
              (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
              v12);
          v24 = (int)v11;
          for ( i = 0; ; ++i )
          {
            if ( i >= Count )
            {
              *a3 = v13;
              *a2 = Count;
              CoTaskMemFree(0);
              result = 0;
              goto LABEL_29;
            }
            v28 = 16LL * i;
            v15 = v28 + 8;
            v16 = *CandidateList::GetAt(*((CandidateList **)v5 + 3), (ProfileSelection **)&v27, i);
            KeyValue = ProfileSelection::GetKeyValue(v16, v17);
            v19 = CoAllocString(KeyValue, (unsigned __int16 **)((char *)v13 + v15));
            v20 = v27;
            if ( v27 )
            {
              std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(v27);
              operator delete(*v20);
              operator delete(v20);
            }
            if ( v19 < 0 )
              break;
            *(_DWORD *)((char *)v13 + v28) = i;
            v5 = (CMVUISelection2 *)this;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
            (const char *)(unsigned int)v19,
            v24);
          for ( j = 0; j < Count; ++j )
          {
            CoTaskMemFree(*((LPVOID *)v13 + 2 * j + 1));
            *((_QWORD *)v13 + 2 * j + 1) = 0;
          }
          CoTaskMemFree(v13);
          result = (unsigned int)v19;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17D,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
            (const char *)0x8007139FLL,
            v23);
          result = 2147947423LL;
        }
      }
      catch ( ... )
      {
        result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x18A,
                                 (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
                                 v22);
      }
LABEL_29:
      ;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17B,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
        (const char *)0x80004003LL,
        v23);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)0x80004003LL,
      v23);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x180027880  mov     [rsp+arg_0], rcx
0x180027885  push    rbx
0x180027886  push    rsi
0x180027887  push    rdi
0x180027888  push    r12
0x18002788a  push    r13
0x18002788c  push    r14
0x18002788e  push    r15
0x180027890  sub     rsp, 30h
0x180027894  mov     r12, r8
0x180027897  mov     r13, rdx
0x18002789a  mov     r14, rcx
0x18002789d  test    rdx, rdx
0x1800278a0  jnz     short loc_1800278C7
0x1800278a2  mov     rcx, [rsp+68h]; this
0x1800278a7  mov     ebx, 80004003h
0x1800278ac  mov     r9d, ebx; char *
0x1800278af  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800278b6  mov     edx, 17Ah; void *
0x1800278bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800278c0  mov     eax, ebx
0x1800278c2  jmp     loc_180027A7A
0x1800278c7  test    r12, r12
0x1800278ca  jnz     short loc_1800278F1
0x1800278cc  mov     rcx, [rsp+68h]; this
0x1800278d1  mov     ebx, 80004003h
0x1800278d6  mov     r9d, ebx; char *
0x1800278d9  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800278e0  mov     edx, 17Bh; void *
0x1800278e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800278ea  mov     eax, ebx
0x1800278ec  jmp     loc_180027A7A
0x1800278f1  mov     rcx, [rcx+18h]; this
0x1800278f5  test    rcx, rcx
0x1800278f8  jz      loc_180027A54
0x1800278fe  call    ?GetCount@CandidateList@@QEAAKXZ; CandidateList::GetCount(void)
0x180027903  mov     esi, eax
0x180027905  mov     [rsp+68h+arg_8], 0
0x18002790e  mov     eax, 10h
0x180027913  mul     rsi
0x180027916  test    rdx, rdx
0x180027919  jnz     short loc_180027920
0x18002791b  xor     r9d, r9d
0x18002791e  jmp     short loc_18002792A
0x180027920  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027924  mov     r9d, 80070216h; char *
0x18002792a  mov     rcx, [rsp+68h]; this
0x18002792f  test    r9d, r9d
0x180027932  js      loc_180027A8A
0x180027938  mov     rdx, rax; cb
0x18002793b  xor     ecx, ecx; pv
0x18002793d  call    cs:__imp_CoTaskMemRealloc
0x180027943  mov     rdi, rax
0x180027946  test    esi, esi
0x180027948  jz      short loc_180027958
0x18002794a  mov     rcx, [rsp+68h]; this
0x18002794f  test    rax, rax
0x180027952  jz      loc_180027A9B
0x180027958  mov     qword ptr [rsp+68h+var_48], rdi; int
0x18002795d  mov     [rsp+68h+var_40], esi
0x180027961  mov     eax, [rsp+68h+var_3C]
0x180027965  mov     [rsp+68h+var_3C], eax
0x180027969  xor     ebx, ebx
0x18002796b  cmp     ebx, esi
0x18002796d  jnb     loc_180027A40
0x180027973  mov     eax, ebx
0x180027975  shl     rax, 4
0x180027979  mov     [rsp+68h+arg_18], rax
0x180027981  lea     r15, [rax+8]
0x180027985  mov     r8d, ebx
0x180027988  lea     rdx, [rsp+68h+arg_8]
0x18002798d  mov     rcx, [r14+18h]
0x180027991  call    ?GetAt@CandidateList@@QEAA?AV?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@K@Z; CandidateList::GetAt(ulong)
0x180027996  nop
0x180027997  mov     rcx, [rax]; this
0x18002799a  call    ?GetKeyValue@ProfileSelection@@IEBAPEBGPEBG@Z; ProfileSelection::GetKeyValue(ushort const *)
0x18002799f  lea     rdx, [r15+rdi]; unsigned __int16 **
0x1800279a3  mov     rcx, rax; unsigned __int16 *
0x1800279a6  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x1800279ab  mov     r15d, eax
0x1800279ae  mov     r14, [rsp+68h+arg_8]
0x1800279b3  test    r14, r14
0x1800279b6  jz      short loc_1800279D3
0x1800279b8  mov     rcx, r14
0x1800279bb  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x1800279c0  mov     rcx, [r14]
0x1800279c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800279c9  nop
0x1800279ca  mov     rcx, r14
0x1800279cd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800279d3  test    r15d, r15d
0x1800279d6  jns     short loc_180027A29
0x1800279d8  mov     rcx, [rsp+68h]; this
0x1800279dd  mov     r9d, r15d; char *
0x1800279e0  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800279e7  mov     edx, 182h; void *
0x1800279ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279f1  nop
0x1800279f2  xor     r14d, r14d
0x1800279f5  test    esi, esi
0x1800279f7  jz      short loc_180027A1B
0x1800279f9  mov     ebx, r14d
0x1800279fc  add     rbx, rbx
0x1800279ff  mov     rcx, [rdi+rbx*8+8]; pv
0x180027a04  call    cs:__imp_CoTaskMemFree
0x180027a0a  mov     qword ptr [rdi+rbx*8+8], 0
0x180027a13  inc     r14d
0x180027a16  cmp     r14d, esi
0x180027a19  jb      short loc_1800279F9
0x180027a1b  mov     rcx, rdi; pv
0x180027a1e  call    cs:__imp_CoTaskMemFree
0x180027a24  mov     eax, r15d
0x180027a27  jmp     short loc_180027A7A
0x180027a29  mov     rax, [rsp+68h+arg_18]
0x180027a31  mov     [rax+rdi], ebx
0x180027a34  inc     ebx
0x180027a36  mov     r14, [rsp+68h+arg_0]
0x180027a3b  jmp     loc_18002796B
0x180027a40  mov     [r12], rdi
0x180027a44  mov     [r13+0], esi
0x180027a48  xor     ecx, ecx; pv
0x180027a4a  call    cs:__imp_CoTaskMemFree
0x180027a50  xor     eax, eax
0x180027a52  jmp     short loc_180027A7A
0x180027a54  mov     rcx, [rsp+68h]; this
0x180027a59  mov     ebx, 8007139Fh
0x180027a5e  mov     r9d, ebx; char *
0x180027a61  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180027a68  mov     edx, 17Dh; void *
0x180027a6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a72  mov     eax, ebx
0x180027a74  jmp     short loc_180027A7A
0x180027a76  mov     eax, dword ptr [rsp+68h+arg_8]
0x180027a7a  add     rsp, 30h
0x180027a7e  pop     r15
0x180027a80  pop     r14
0x180027a82  pop     r13
0x180027a84  pop     r12
0x180027a86  pop     rdi
0x180027a87  pop     rsi
0x180027a88  pop     rbx
0x180027a89  retn
0x180027a8a  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180027a91  mov     edx, 3Bh ; ';'; void *
0x180027a96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027a9b  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180027aa2  lea     edx, [rax+3Fh]; void *
0x180027aa5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
