# win_musl::GetGuidAsCompactString(void)

- ea: `0x180062fd0`
- end: `0x180063160`
- name: `?GetGuidAsCompactString@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800629f8`
- `0x1800f9d94`

## callees

- `0x180012468`
- `0x180017320`
- `0x18002db70`
- `0x180062fd0`
- `0x1800cd6fc`
- `0x1800cdbe8`
- `0x1800d6354`
- `0x1801178c6`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180063010`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180063010`

## string_xrefs

- `0x180063106`: `Call to CoCreateGuid failed with HResult 0x%X.`

## pseudocode

```c
__int64 __fastcall win_musl::GetGuidAsCompactString(__int64 a1)
{
  HRESULT v2; // ebx
  signed int i; // ebx
  unsigned __int8 v4; // r9
  __int64 j; // r10
  unsigned int v6; // r9d
  __int64 v7; // rcx
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v11[32]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v12[512]; // [rsp+140h] [rbp+40h] BYREF

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
  {
    memset_0(v12, 0, sizeof(v12));
    StringCchPrintfW(v12, 0x200u, L"Call to CoCreateGuid failed with HResult 0x%X.", (unsigned int)v2);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x63u,
      v2,
      (struct win_musl::TStringEllipseBase *)v12);
    throw (SplException::THResultException *)pExceptionObject;
  }
  for ( i = 0; memcmp_0(&pguid, &GUID_NULL, 0x10u) && (unsigned int)i < 0x1D; ++i )
  {
    v4 = 0;
    for ( j = 0; j != 16; ++j )
    {
      v6 = *((unsigned __int8 *)&pguid.Data1 + j) + (v4 << 8);
      *((_BYTE *)&pguid.Data1 + j) = v6 / 0x25;
      v4 = v6 % 0x25;
    }
    v7 = i;
    v11[v7] = aAbcdefghijklmn[v4];
  }
  if ( (unsigned __int64)(2LL * i) >= 0x3C )
    _report_rangecheckfailure();
  v11[i] = 0;
  std::wstring::wstring(a1, v11);
  return a1;
}

```

## disassembly

```asm
0x180062fd0  mov     [rsp-8+arg_8], rbx
0x180062fd5  mov     [rsp-8+arg_10], rdi
0x180062fda  push    rbp
0x180062fdb  lea     rbp, [rsp-450h]
0x180062fe3  sub     rsp, 550h
0x180062fea  mov     rax, cs:__security_cookie
0x180062ff1  xor     rax, rsp
0x180062ff4  mov     [rbp+450h+var_10], rax
0x180062ffb  mov     qword ptr [rsp+550h+pguid.Data1], rcx
0x180063000  mov     rdi, rcx
0x180063003  xorps   xmm0, xmm0
0x180063006  lea     rcx, [rsp+550h+pguid]; pguid
0x18006300b  movups  xmmword ptr [rsp+550h+pguid.Data1], xmm0
0x180063010  call    cs:__imp_CoCreateGuid
0x180063016  mov     ebx, eax
0x180063018  test    eax, eax
0x18006301a  js      loc_1800630F2
0x180063020  xor     ebx, ebx
0x180063022  mov     r8d, 10h; Size
0x180063028  lea     rdx, GUID_NULL; Buf2
0x18006302f  lea     rcx, [rsp+550h+pguid]; Buf1
0x180063034  call    memcmp_0
0x180063039  test    eax, eax
0x18006303b  jz      short loc_1800630A7
0x18006303d  cmp     ebx, 1Dh
0x180063040  jnb     short loc_1800630A7
0x180063042  xor     r9b, r9b
0x180063045  xor     r10d, r10d
0x180063048  movzx   eax, byte ptr [rsp+r10+550h+pguid.Data1]
0x18006304e  movzx   r9d, r9b
0x180063052  shl     r9d, 8
0x180063056  add     r9d, eax
0x180063059  mov     eax, 0BACF914Dh
0x18006305e  mul     r9d
0x180063061  mov     r8d, r9d
0x180063064  sub     r8d, edx
0x180063067  shr     r8d, 1
0x18006306a  add     r8d, edx
0x18006306d  shr     r8d, 5
0x180063071  movzx   eax, r8b
0x180063075  imul    ecx, eax, 25h ; '%'
0x180063078  mov     byte ptr [rsp+r10+550h+pguid.Data1], r8b
0x18006307d  inc     r10
0x180063080  sub     r9b, cl
0x180063083  cmp     r10, 10h
0x180063087  jnz     short loc_180063048
0x180063089  movsxd  rcx, ebx
0x18006308c  lea     rdx, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyz_0123456789"
0x180063093  movzx   eax, r9b
0x180063097  inc     ebx
0x180063099  movzx   eax, word ptr [rdx+rax*2]
0x18006309d  mov     [rbp+rcx*2+450h+var_450], ax
0x1800630a2  jmp     loc_180063022
0x1800630a7  movsxd  rcx, ebx
0x1800630aa  lea     rax, [rcx+rcx]
0x1800630ae  cmp     rax, 3Ch ; '<'
0x1800630b2  jnb     loc_18006315A
0x1800630b8  xor     ecx, ecx
0x1800630ba  lea     rdx, [rbp+450h+var_450]
0x1800630be  mov     [rbp+rax+450h+var_450], cx
0x1800630c3  mov     rcx, rdi
0x1800630c6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800630cb  mov     rax, rdi
0x1800630ce  mov     rcx, [rbp+450h+var_10]
0x1800630d5  xor     rcx, rsp; StackCookie
0x1800630d8  call    __security_check_cookie
0x1800630dd  lea     r11, [rsp+550h+var_s0]
0x1800630e5  mov     rbx, [r11+18h]
0x1800630e9  mov     rdi, [r11+20h]
0x1800630ed  mov     rsp, r11
0x1800630f0  pop     rbp
0x1800630f1  retn
0x1800630f2  xor     edx, edx; Val
0x1800630f4  lea     rcx, [rbp+450h+var_410]; void *
0x1800630f8  mov     r8d, 400h; Size
0x1800630fe  call    memset_0
0x180063103  mov     r9d, ebx
0x180063106  lea     r8, aCallToCocreate; "Call to CoCreateGuid failed with HResul"...
0x18006310d  mov     edx, 200h; unsigned __int64
0x180063112  lea     rcx, [rbp+450h+var_410]; wchar_t *
0x180063116  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18006311b  lea     rax, [rbp+450h+var_410]
0x18006311f  mov     [rsp+550h+var_520], rax; struct win_musl::TStringEllipseBase *
0x180063124  lea     r9, word_180139126
0x18006312b  mov     [rsp+550h+var_528], ebx; unsigned int
0x18006312f  lea     r8, aNoFilename; "(no filename)"
0x180063136  lea     rcx, [rsp+550h+pExceptionObject]; this
0x18006313b  mov     [rsp+550h+var_530], 63h ; 'c'; unsigned int
0x180063143  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180063148  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006314f  lea     rcx, [rsp+550h+pExceptionObject]; pExceptionObject
0x180063154  call    _CxxThrowException_0
0x18006315a  call    __report_rangecheckfailure
```
