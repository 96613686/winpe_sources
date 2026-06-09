# StringUtility::CreateGuid(void)

- ea: `0x140012cb4`
- end: `0x140012ddd`
- name: `?CreateGuid@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ`
- size: `297`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140017104`
- `0x140017340`
- `0x14001749c`

## callees

- `0x140001b60`
- `0x140002390`
- `0x140002814`
- `0x1400061dc`
- `0x14000caac`
- `0x140012cb4`
- `0x14002c3e8`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140012d15`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x140012d15`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012d3e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140012d3e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall StringUtility::CreateGuid(_QWORD *a1)
{
  int v2; // eax
  unsigned __int64 v3; // rcx
  __int64 v4; // r8
  OLECHAR *p_sz; // rdx
  _BYTE pExceptionObject[16]; // [rsp+30h] [rbp-39h] BYREF
  GUID pguid; // [rsp+40h] [rbp-29h] BYREF
  OLECHAR sz; // [rsp+50h] [rbp-19h] BYREF
  _WORD v10[47]; // [rsp+52h] [rbp-17h] BYREF

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  pguid = 0;
  if ( CoCreateGuid(&pguid) < 0 )
  {
    Exception::Exception((Exception *)pExceptionObject, -895418324);
    throw (Exception *)pExceptionObject;
  }
  memset_0(&sz, 0, 0x52u);
  v2 = StringFromGUID2(&pguid, &sz, 40);
  if ( v2 <= 3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v10[v4 - 1] );
    p_sz = &sz;
  }
  else
  {
    v3 = 2LL * v2 - 4;
    if ( v3 >= 0x52 )
      _report_rangecheckfailure(v3);
    *(_WORD *)((char *)&v10[-1] + v3) = 0;
    v4 = -1;
    do
      ++v4;
    while ( v10[v4] );
    p_sz = v10;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(a1, p_sz, v4);
  return a1;
}

```

## disassembly

```asm
0x140012cb4  mov     [rsp-8+arg_8], rbx
0x140012cb9  mov     [rsp-8+arg_10], rdi
0x140012cbe  push    rbp
0x140012cbf  lea     rbp, [rsp-57h]
0x140012cc4  sub     rsp, 0C0h
0x140012ccb  mov     rax, cs:__security_cookie
0x140012cd2  xor     rax, rsp
0x140012cd5  mov     [rbp+57h+var_10], rax
0x140012cd9  mov     rbx, rcx
0x140012cdc  mov     [rbp+57h+var_98], rcx
0x140012ce0  xor     edi, edi
0x140012ce2  mov     [rbp+57h+var_A0], edi
0x140012ce5  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140012cec  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140012cf3  mov     rax, [rax+18h]
0x140012cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012cfc  add     rax, 18h
0x140012d00  mov     [rbx], rax
0x140012d03  mov     [rbp+57h+var_A0], 1
0x140012d0a  xorps   xmm0, xmm0
0x140012d0d  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x140012d11  lea     rcx, [rbp+57h+pguid]; pguid
0x140012d15  call    cs:__imp_CoCreateGuid
0x140012d1b  test    eax, eax
0x140012d1d  js      loc_140012DBE
0x140012d23  xor     edx, edx; Val
0x140012d25  lea     r8d, [rdi+52h]; Size
0x140012d29  lea     rcx, [rbp+57h+sz]; void *
0x140012d2d  call    memset_0
0x140012d32  lea     r8d, [rdi+28h]; cchMax
0x140012d36  lea     rdx, [rbp+57h+sz]; lpsz
0x140012d3a  lea     rcx, [rbp+57h+pguid]; rguid
0x140012d3e  call    cs:__imp_StringFromGUID2
0x140012d44  cmp     eax, 3
0x140012d47  jle     short loc_140012D76
0x140012d49  cdqe
0x140012d4b  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rax*2]
0x140012d53  cmp     rcx, 52h ; 'R'
0x140012d57  jnb     short loc_140012DB8
0x140012d59  mov     [rbp+rcx+57h+sz], di
0x140012d5e  lea     rax, [rbp+57h+var_6E]
0x140012d62  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012d66  inc     r8
0x140012d69  cmp     [rax+r8*2], di
0x140012d6e  jnz     short loc_140012D66
0x140012d70  lea     rdx, [rbp+57h+var_6E]
0x140012d74  jmp     short loc_140012D8C
0x140012d76  lea     rax, [rbp+57h+sz]
0x140012d7a  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012d7e  inc     r8
0x140012d81  cmp     [rax+r8*2], di
0x140012d86  jnz     short loc_140012D7E
0x140012d88  lea     rdx, [rbp+57h+sz]
0x140012d8c  mov     rcx, rbx
0x140012d8f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140012d94  mov     rax, rbx
0x140012d97  mov     rcx, [rbp+57h+var_10]
0x140012d9b  xor     rcx, rsp; StackCookie
0x140012d9e  call    __security_check_cookie
0x140012da3  lea     r11, [rsp+0C0h+var_s0]
0x140012dab  mov     rbx, [r11+18h]
0x140012daf  mov     rdi, [r11+20h]
0x140012db3  mov     rsp, r11
0x140012db6  pop     rbp
0x140012db7  retn
0x140012db8  call    __report_rangecheckfailure
0x140012dbe  mov     edx, 0CAA1002Ch; unsigned int
0x140012dc3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140012dc7  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x140012dcc  lea     rdx, _TI1?AVException@@; pThrowInfo
0x140012dd3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140012dd7  call    _CxxThrowException_0
```
