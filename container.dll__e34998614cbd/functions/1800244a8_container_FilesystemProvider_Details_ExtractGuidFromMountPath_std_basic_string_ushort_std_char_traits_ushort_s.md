# container::FilesystemProvider::Details::ExtractGuidFromMountPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID &)

- ea: `0x1800244a8`
- end: `0x18002465c`
- name: `?ExtractGuidFromMountPath@Details@FilesystemProvider@container@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z`
- size: `436`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1800243c4`
- `0x180024a84`

## callees

- `0x180002640`
- `0x180002ad0`
- `0x180004b70`
- `0x1800051b0`
- `0x18000ca10`
- `0x1800120d0`
- `0x1800215cc`
- `0x1800244a8`
- `0x180025220`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800245d8`
- `RPCRT4!UuidFromStringW` at `0x1800245d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall container::FilesystemProvider::Details::ExtractGuidFromMountPath(_QWORD *a1, UUID *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // r14
  char *v6; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v8; // rsi
  __int64 v9; // rax
  _QWORD *v10; // r14
  char *v11; // rbx
  __int64 v12; // rax
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  unsigned int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  int v19; // [rsp+20h] [rbp-68h]
  RPC_WSTR StringUuid[2]; // [rsp+28h] [rbp-60h] BYREF
  __int128 v21; // [rsp+38h] [rbp-50h]
  UUID Uuid; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = a1[2];
  if ( a1[3] <= 7u )
    v5 = a1;
  else
    v5 = (_QWORD *)*a1;
  if ( !v4 || (v6 = (char *)v5 + 2 * v4, trivial_2 = _std_find_trivial_2(v5, v6, 123), (char *)trivial_2 == v6) )
    v8 = -1;
  else
    v8 = (trivial_2 - (__int64)v5) >> 1;
  v9 = a1[2];
  if ( a1[3] <= 7u )
    v10 = a1;
  else
    v10 = (_QWORD *)*a1;
  if ( !v9 || (v11 = (char *)v10 + 2 * v9, v12 = _std_find_trivial_2(v10, v11, 125), (char *)v12 == v11) )
    v13 = -1;
  else
    v13 = (v12 - (__int64)v10) >> 1;
  if ( v8 == -1 || v13 == -1 || v8 >= v13 )
  {
    v16 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(retaddr, v17, v18, (const char *)v16, v19);
  }
  *(_OWORD *)StringUuid = 0;
  v21 = 0;
  if ( a1[2] < v8 + 1 )
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
    JUMPOUT(0x18002465BLL);
  }
  std::wstring::_Construct<1,unsigned short const *>(StringUuid);
  Uuid = 0;
  v14 = (unsigned __int16 *)StringUuid;
  if ( *((_QWORD *)&v21 + 1) > 7u )
    v14 = StringUuid[0];
  if ( UuidFromStringW(v14, &Uuid) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\filesystem_provider.cpp",
      (const char *)0x80070057LL,
      v19);
  *a2 = Uuid;
  std::wstring::~wstring(StringUuid);
  return 0;
}

```

## disassembly

```asm
0x1800244a8  mov     [rsp+arg_10], rbx
0x1800244ad  push    rbp
0x1800244ae  push    rsi
0x1800244af  push    rdi
0x1800244b0  push    r14
0x1800244b2  push    r15
0x1800244b4  sub     rsp, 60h
0x1800244b8  mov     rax, cs:__security_cookie
0x1800244bf  xor     rax, rsp
0x1800244c2  mov     [rsp+88h+var_30], rax
0x1800244c7  mov     rbp, rdx
0x1800244ca  mov     rdi, rcx
0x1800244cd  mov     rax, [rcx+10h]
0x1800244d1  cmp     qword ptr [rcx+18h], 7
0x1800244d6  jbe     short loc_1800244DD
0x1800244d8  mov     r14, [rcx]
0x1800244db  jmp     short loc_1800244E0
0x1800244dd  mov     r14, rdi
0x1800244e0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800244e4  test    rax, rax
0x1800244e7  jz      short loc_18002450C
0x1800244e9  lea     rbx, [r14+rax*2]
0x1800244ed  lea     r8d, [r15+7Ch]
0x1800244f1  mov     rdx, rbx
0x1800244f4  mov     rcx, r14
0x1800244f7  call    __std_find_trivial_2
0x1800244fc  mov     rsi, rax
0x1800244ff  cmp     rax, rbx
0x180024502  jz      short loc_18002450C
0x180024504  sub     rsi, r14
0x180024507  sar     rsi, 1
0x18002450a  jmp     short loc_18002450F
0x18002450c  mov     rsi, r15
0x18002450f  mov     rax, [rdi+10h]
0x180024513  cmp     qword ptr [rdi+18h], 7
0x180024518  jbe     short loc_18002451F
0x18002451a  mov     r14, [rdi]
0x18002451d  jmp     short loc_180024522
0x18002451f  mov     r14, rdi
0x180024522  test    rax, rax
0x180024525  jz      short loc_180024549
0x180024527  lea     rbx, [r14+rax*2]
0x18002452b  mov     r8d, 7Dh ; '}'
0x180024531  mov     rdx, rbx
0x180024534  mov     rcx, r14
0x180024537  call    __std_find_trivial_2
0x18002453c  cmp     rax, rbx
0x18002453f  jz      short loc_180024549
0x180024541  sub     rax, r14
0x180024544  sar     rax, 1
0x180024547  jmp     short loc_18002454C
0x180024549  mov     rax, r15
0x18002454c  cmp     rsi, r15
0x18002454f  jz      loc_18002463B
0x180024555  cmp     rax, r15
0x180024558  jz      loc_18002463B
0x18002455e  cmp     rsi, rax
0x180024561  jnb     loc_18002463B
0x180024567  lea     rcx, [rsi+1]
0x18002456b  xorps   xmm0, xmm0
0x18002456e  movups  xmmword ptr [rsp+88h+StringUuid], xmm0
0x180024573  xorps   xmm1, xmm1
0x180024576  movdqu  [rsp+88h+var_50], xmm1
0x18002457c  mov     r8, [rdi+10h]
0x180024580  cmp     r8, rcx
0x180024583  jb      loc_180024656
0x180024589  sub     rax, rsi
0x18002458c  dec     rax
0x18002458f  sub     r8, rcx
0x180024592  cmp     r8, rax
0x180024595  cmovnb  r8, rax
0x180024599  cmp     qword ptr [rdi+18h], 7
0x18002459e  jbe     short loc_1800245A3
0x1800245a0  mov     rdi, [rdi]
0x1800245a3  lea     rdx, [rdi+rcx*2]
0x1800245a7  lea     rcx, [rsp+88h+StringUuid]
0x1800245ac  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800245b1  nop
0x1800245b2  xorps   xmm0, xmm0
0x1800245b5  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x1800245ba  lea     rcx, [rsp+88h+StringUuid]
0x1800245bf  cmp     qword ptr [rsp+88h+var_50+8], 7
0x1800245c5  cmova   rcx, [rsp+88h+StringUuid]; StringUuid
0x1800245cb  mov     rbx, [rsp+88h]
0x1800245d3  lea     rdx, [rsp+88h+Uuid]; Uuid
0x1800245d8  call    cs:__imp_UuidFromStringW
0x1800245df  nop     dword ptr [rax+rax+00h]
0x1800245e4  test    eax, eax
0x1800245e6  jnz     short loc_180024620
0x1800245e8  movups  xmm0, xmmword ptr [rsp+88h+Uuid.Data1]
0x1800245ed  movdqu  xmmword ptr [rbp+0], xmm0
0x1800245f2  lea     rcx, [rsp+88h+StringUuid]
0x1800245f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800245fc  xor     eax, eax
0x1800245fe  mov     rcx, [rsp+88h+var_30]
0x180024603  xor     rcx, rsp; StackCookie
0x180024606  call    __security_check_cookie
0x18002460b  mov     rbx, [rsp+88h+arg_10]
0x180024613  add     rsp, 60h
0x180024617  pop     r15
0x180024619  pop     r14
0x18002461b  pop     rdi
0x18002461c  pop     rsi
0x18002461d  pop     rbp
0x18002461e  retn
0x180024620  mov     r9d, 80070057h; char *
0x180024626  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\container"...
0x18002462d  mov     edx, 0B2h; void *
0x180024632  mov     rcx, rbx; this
0x180024635  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002463b  mov     ecx, 80070057h
0x180024640  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180024645  mov     r9d, eax; char *
0x180024648  mov     rcx, [rsp+88h]; this
0x180024650  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024656  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
