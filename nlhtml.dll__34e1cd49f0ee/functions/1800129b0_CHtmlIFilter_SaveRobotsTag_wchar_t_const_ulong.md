# CHtmlIFilter::SaveRobotsTag(wchar_t const *,ulong)

- ea: `0x1800129b0`
- end: `0x180012afc`
- name: `?SaveRobotsTag@CHtmlIFilter@@QEAAXPEB_WK@Z`
- size: `332`
- prototype: `void __fastcall(CHtmlIFilter *__hidden this, const wchar_t *Src, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b68c`

## callees

- `0x1800129b0`
- `0x180012b04`
- `0x180013500`
- `0x18001cd7c`
- `0x180023388`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a57`

## pseudocode

```c
void __fastcall CHtmlIFilter::SaveRobotsTag(CHtmlIFilter *this, const wchar_t *Src, unsigned int a3)
{
  __int64 v4; // rbx
  struct tagPROPVARIANT *v5; // rcx
  bool v7; // zf
  __int64 v8; // rax
  unsigned __int64 v9; // rax
  unsigned int v10; // ebp
  _WORD *v11; // rax
  _QWORD *v12; // rsi
  void *v13; // rax
  size_t v14; // rbx
  int v15; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  v5 = (struct tagPROPVARIANT *)*((_QWORD *)this + 639);
  if ( v5 )
  {
    FreeVariant(v5);
    *((_QWORD *)this + 639) = 0;
  }
  v7 = *((_DWORD *)this + 16) == 0;
  *((_DWORD *)this + 1274) = 0;
  *((_QWORD *)this + 638) = L"ROBOTS";
  *(_OWORD *)((char *)this + 5080) = xmmword_180030F90;
  if ( !v7 || (unsigned int)CHtmlIFilter::IsMatchProperty(this, (struct tagFULLPROPSPEC *)((char *)this + 5080)) )
  {
    v8 = (unsigned int)(v4 + 1);
    if ( (unsigned int)v8 < (unsigned int)v4 || (v9 = 2 * v8, v10 = v9, v9 > 0xFFFFFFFF) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.cxx",
        (const char *)0x80070216LL,
        v15);
    v11 = CoTaskMemAlloc(0x18u);
    v12 = v11;
    if ( !v11 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.cxx",
        (const char *)0x8007000ELL,
        v15);
    *v11 = 31;
    v13 = CoTaskMemAlloc(v10);
    v12[1] = v13;
    if ( !v13 )
    {
      CoTaskMemFree(v12);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AD,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.cxx",
        (const char *)0x8007000ELL,
        v15);
    }
    v14 = 2 * v4;
    memcpy_0(v13, Src, v14);
    *(_WORD *)(v14 + v12[1]) = 0;
    *((_QWORD *)this + 639) = v12;
  }
}

```

## disassembly

```asm
0x1800129b0  push    rbx
0x1800129b2  push    rbp
0x1800129b3  push    rsi
0x1800129b4  push    rdi
0x1800129b5  push    r14; int
0x1800129b7  sub     rsp, 20h
0x1800129bb  mov     rdi, rcx
0x1800129be  mov     ebx, r8d
0x1800129c1  mov     rcx, [rcx+13F8h]; struct tagPROPVARIANT *
0x1800129c8  mov     r14, rdx
0x1800129cb  test    rcx, rcx
0x1800129ce  jnz     loc_180012AA4
0x1800129d4  cmp     dword ptr [rdi+40h], 0
0x1800129d8  lea     rdx, [rdi+13D8h]; struct tagFULLPROPSPEC *
0x1800129df  movups  xmm0, cs:xmmword_180030F90
0x1800129e6  lea     rax, aRobots; "ROBOTS"
0x1800129ed  mov     dword ptr [rdi+13E8h], 0
0x1800129f7  mov     [rdi+13F0h], rax
0x1800129fe  movdqu  xmmword ptr [rdx], xmm0
0x180012a02  jz      loc_180012A93
0x180012a08  lea     eax, [rbx+1]
0x180012a0b  cmp     eax, ebx
0x180012a0d  jb      short loc_180012A20
0x180012a0f  add     rax, rax
0x180012a12  mov     ecx, 0FFFFFFFFh
0x180012a17  mov     ebp, eax
0x180012a19  cmp     rax, rcx
0x180012a1c  jbe     short loc_180012A3D
0x180012a1e  mov     ebp, ecx
0x180012a20  mov     rcx, [rsp+48h]; this
0x180012a25  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012a2c  mov     r9d, 80070216h; char *
0x180012a32  mov     edx, 1A1h; void *
0x180012a37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012a3d  mov     ecx, 18h; cb
0x180012a42  call    cs:__imp_CoTaskMemAlloc
0x180012a48  mov     rsi, rax
0x180012a4b  test    rax, rax
0x180012a4e  jz      short loc_180012AB9
0x180012a50  mov     ecx, ebp; cb
0x180012a52  mov     word ptr [rax], 1Fh
0x180012a57  call    cs:__imp_CoTaskMemAlloc
0x180012a5d  mov     [rsi+8], rax
0x180012a61  mov     rcx, rax; void *
0x180012a64  test    rax, rax
0x180012a67  jz      short loc_180012AD6
0x180012a69  add     rbx, rbx
0x180012a6c  mov     rdx, r14; Src
0x180012a6f  mov     r8, rbx; Size
0x180012a72  call    memcpy_0
0x180012a77  mov     rcx, [rsi+8]
0x180012a7b  xor     eax, eax
0x180012a7d  mov     [rbx+rcx], ax
0x180012a81  mov     [rdi+13F8h], rsi
0x180012a88  add     rsp, 20h
0x180012a8c  pop     r14
0x180012a8e  pop     rdi
0x180012a8f  pop     rsi
0x180012a90  pop     rbp
0x180012a91  pop     rbx
0x180012a92  retn
0x180012a93  mov     rcx, rdi; this
0x180012a96  call    ?IsMatchProperty@CHtmlIFilter@@QEAAHAEAUtagFULLPROPSPEC@@@Z; CHtmlIFilter::IsMatchProperty(tagFULLPROPSPEC &)
0x180012a9b  test    eax, eax
0x180012a9d  jz      short loc_180012A88
0x180012a9f  jmp     loc_180012A08
0x180012aa4  call    ?FreeVariant@@YAXPEAUtagPROPVARIANT@@@Z; FreeVariant(tagPROPVARIANT *)
0x180012aa9  mov     qword ptr [rdi+13F8h], 0
0x180012ab4  jmp     loc_1800129D4
0x180012ab9  mov     rcx, [rsp+48h]; this
0x180012abe  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012ac5  mov     r9d, 8007000Eh; char *
0x180012acb  mov     edx, 1A6h; void *
0x180012ad0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012ad6  mov     rcx, rsi; pv
0x180012ad9  call    cs:__imp_CoTaskMemFree
0x180012adf  mov     rcx, [rsp+48h]; this
0x180012ae4  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180012aeb  mov     r9d, 8007000Eh; char *
0x180012af1  mov     edx, 1ADh; void *
0x180012af6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
