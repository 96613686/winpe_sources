# AddEnumName(utl::list<ENUM_INFO,utl::allocator<ENUM_INFO>> &,ushort const *)

- ea: `0x180042874`
- end: `0x180042986`
- name: `?AddEnumName@@YA?AV?$_DlistIt@U?$_DlistNode@UENUM_INFO@@@utl@@UENUM_INFO@@@utl@@AEAV?$list@UENUM_INFO@@V?$allocator@UENUM_INFO@@@utl@@@2@PEBG@Z`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800407d0`
- `0x18004260c`

## callees

- `0x180018318`
- `0x180020c74`
- `0x180029948`
- `0x18003edb0`
- `0x180040584`
- `0x1800405e4`
- `0x180042218`
- `0x180042844`
- `0x180042874`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800428a4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800428a4`

## pseudocode

```c
__int64 **__fastcall AddEnumName(__int64 **a1, __int64 **a2, const WCHAR *a3)
{
  __int64 **i; // rbx
  __int64 *v7; // rbp
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  _BYTE v13[24]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v14[80]; // [rsp+48h] [rbp-50h] BYREF
  _QWORD *v15; // [rsp+A8h] [rbp+10h] BYREF

  for ( i = (__int64 **)*a2; i != a2; i = (__int64 **)*i )
  {
    if ( CompareStringOrdinal((LPCWCH)i[5], -1, a3, -1, 1) == 2 )
    {
      *a1 = 0;
      return a1;
    }
  }
  utl::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>(v13);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v14);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v14,
                           a3) )
    goto LABEL_12;
  v7 = *a2;
  v8 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v8;
  v9 = v8;
  if ( v8 )
  {
    utl::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>(
      v8 + 2,
      v13);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
      v10 + 24,
      v14);
    v11 = (_QWORD *)v7[1];
    v9[1] = v11;
    *v9 = v7;
    v15 = 0;
    *v11 = v9;
    v7[1] = (__int64)v9;
    a2[2] = (__int64 *)((char *)a2[2] + 1);
  }
  else
  {
    v9 = 0;
  }
  utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<WBEM_INFO>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<WBEM_INFO>>>(&v15);
  if ( v9 )
    *a1 = *a2;
  else
LABEL_12:
    *a1 = 0;
  ENUM_INFO::~ENUM_INFO((ENUM_INFO *)v13);
  return a1;
}

```

## disassembly

```asm
0x180042874  push    rbx
0x180042876  push    rbp
0x180042877  push    rsi
0x180042878  push    rdi
0x180042879  sub     rsp, 78h
0x18004287d  mov     rbx, [rdx]
0x180042880  mov     rbp, r8
0x180042883  mov     rsi, rdx
0x180042886  mov     rdi, rcx
0x180042889  cmp     rbx, rsi
0x18004288c  jz      short loc_1800428C0
0x18004288e  mov     rcx, [rbx+28h]; lpString1
0x180042892  or      r9d, 0FFFFFFFFh; cchCount2
0x180042896  or      edx, r9d; cchCount1
0x180042899  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x1800428a1  mov     r8, rbp; lpString2
0x1800428a4  call    cs:__imp_CompareStringOrdinal
0x1800428aa  cmp     eax, 2
0x1800428ad  jz      short loc_1800428B4
0x1800428af  mov     rbx, [rbx]
0x1800428b2  jmp     short loc_180042889
0x1800428b4  mov     qword ptr [rdi], 0
0x1800428bb  jmp     loc_18004297A
0x1800428c0  lea     rcx, [rsp+98h+var_68]
0x1800428c5  call    ??0?$vector@UENUM_CHILD_INFO@@V?$allocator@UENUM_CHILD_INFO@@@utl@@@utl@@QEAA@XZ; utl::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>(void)
0x1800428ca  lea     rcx, [rsp+98h+var_50]
0x1800428cf  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800428d4  mov     rdx, rbp
0x1800428d7  lea     rcx, [rsp+98h+var_50]
0x1800428dc  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800428e1  test    al, al
0x1800428e3  jz      loc_180042969
0x1800428e9  mov     rbp, [rsi]
0x1800428ec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800428f3  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800428f8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800428fd  mov     [rsp+98h+arg_8], rax
0x180042905  mov     rbx, rax
0x180042908  test    rax, rax
0x18004290b  jz      short loc_18004294D
0x18004290d  lea     rcx, [rax+10h]
0x180042911  lea     rdx, [rsp+98h+var_68]
0x180042916  call    ??0?$vector@UENUM_CHILD_INFO@@V?$allocator@UENUM_CHILD_INFO@@@utl@@@utl@@QEAA@$$QEAV01@@Z; utl::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>>(utl::vector<ENUM_CHILD_INFO,utl::allocator<ENUM_CHILD_INFO>> &&)
0x18004291b  add     rcx, 18h
0x18004291f  lea     rdx, [rsp+98h+var_50]
0x180042924  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180042929  mov     rax, [rbp+8]
0x18004292d  mov     [rbx+8], rax
0x180042931  mov     [rbx], rbp
0x180042934  mov     [rsp+98h+arg_8], 0
0x180042940  mov     [rax], rbx
0x180042943  mov     [rbp+8], rbx
0x180042947  inc     qword ptr [rsi+10h]
0x18004294b  jmp     short loc_18004294F
0x18004294d  xor     ebx, ebx
0x18004294f  lea     rcx, [rsp+98h+arg_8]
0x180042957  call    ??1?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@UWBEM_INFO@@@utl@@@utl@@@utl@@QEAA@XZ; utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<WBEM_INFO>>>::~_UninitializedAllocation<utl::allocator<utl::_DlistNode<WBEM_INFO>>>(void)
0x18004295c  test    rbx, rbx
0x18004295f  jz      short loc_180042969
0x180042961  mov     rax, [rsi]
0x180042964  mov     [rdi], rax
0x180042967  jmp     short loc_180042970
0x180042969  mov     qword ptr [rdi], 0
0x180042970  lea     rcx, [rsp+98h+var_68]; this
0x180042975  call    ??1ENUM_INFO@@QEAA@XZ; ENUM_INFO::~ENUM_INFO(void)
0x18004297a  mov     rax, rdi
0x18004297d  add     rsp, 78h
0x180042981  pop     rdi
0x180042982  pop     rsi
0x180042983  pop     rbp
0x180042984  pop     rbx
0x180042985  retn
```
