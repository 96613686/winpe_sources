# CClipboardMobileDataObject::EnumFormatEtc(ulong,IEnumFORMATETC * *)

- ea: `0x1801fa850`
- end: `0x1801fa9fa`
- name: `?EnumFormatEtc@CClipboardMobileDataObject@@UEAAJKPEAPEAUIEnumFORMATETC@@@Z`
- size: `426`
- prototype: `int(CClipboardMobileDataObject *__hidden this, unsigned int, struct IEnumFORMATETC **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18001b5d0`
- `0x180038c24`
- `0x18009abd0`
- `0x1800d97c0`
- `0x180149d94`
- `0x1801fa850`
- `0x1801fb2f4`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fa932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801fa932`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa98a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa905`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801fa98a`

## pseudocode

```c
__int64 __fastcall CClipboardMobileDataObject::EnumFormatEtc(
        CClipboardMobileDataObject *this,
        int a2,
        struct IEnumFORMATETC **a3)
{
  unsigned int v4; // r15d
  __int64 v5; // rcx
  unsigned int v7; // esi
  __int64 v8; // rdi
  void (__fastcall *v9)(__int64, _QWORD, HSTRING *); // rbx
  HSTRING v10; // rcx
  __int16 v11; // bx
  _QWORD *v12; // rax
  const struct tagFORMATETC *v13; // rax
  int v14; // r10d
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  __m128i si128; // [rsp+38h] [rbp-18h]
  int v19; // [rsp+48h] [rbp-8h]
  unsigned int v20; // [rsp+90h] [rbp+40h] BYREF
  UINT32 length; // [rsp+98h] [rbp+48h] BYREF

  v4 = -2147024809;
  if ( a3 )
  {
    *a3 = 0;
    if ( a2 == 1 )
    {
      v5 = *((_QWORD *)this + 1);
      v16 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 72LL))(v5, &v16);
      v20 = 0;
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 56LL))(v16, &v20);
      if ( !v20 )
      {
        Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v16);
        return 0;
      }
      v7 = 0;
      v17 = 0;
      v19 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      do
      {
        v8 = v16;
        string = 0;
        v9 = *(void (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v16 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v9(v8, v7, &string);
        length = 0;
        WindowsGetStringRawBuffer(string, &length);
        v10 = string;
        if ( length )
        {
          v11 = SupportedFormat(string);
          if ( v11 )
          {
            v12 = CArrayBase::ArAdd((CArrayBase *)&v17, 1, 0);
            if ( v12 )
            {
              *(_WORD *)v12 = v11;
              v12[1] = 0;
              *((_DWORD *)v12 + 4) = 1;
              *((_DWORD *)v12 + 5) = -1;
              *((_DWORD *)v12 + 6) = 1;
            }
          }
          v10 = string;
        }
        WindowsDeleteString(v10);
        ++v7;
      }
      while ( v7 < v20 );
      if ( si128.m128i_i32[0] > 0 )
      {
        v13 = (const struct tagFORMATETC *)CArrayBase::Elem((CArrayBase *)&v17, 0);
        v4 = RichEdit::CEnumFormatEtc::Create(v13, v14, a3);
      }
      CArrayBase::Clear(&v17, 2);
      Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(&v16);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1801fa850  mov     [rsp-28h+arg_0], rbx
0x1801fa855  mov     [rsp-28h+arg_8], rsi
0x1801fa85a  push    rbp
0x1801fa85b  push    rdi
0x1801fa85c  push    r12
0x1801fa85e  push    r14
0x1801fa860  push    r15
0x1801fa862  mov     rbp, rsp
0x1801fa865  sub     rsp, 50h
0x1801fa869  xor     r12d, r12d
0x1801fa86c  mov     r14, r8
0x1801fa86f  mov     r15d, 80070057h
0x1801fa875  test    r8, r8
0x1801fa878  jz      loc_1801FA9DD
0x1801fa87e  mov     [r8], r12
0x1801fa881  cmp     edx, 1
0x1801fa884  jnz     loc_1801FA9DD
0x1801fa88a  mov     rcx, [rcx+8]
0x1801fa88e  lea     rdx, [rbp+var_28]
0x1801fa892  mov     [rbp+var_28], r12
0x1801fa896  mov     rax, [rcx]
0x1801fa899  mov     rax, [rax+48h]
0x1801fa89d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa8a2  mov     rcx, [rbp+var_28]
0x1801fa8a6  lea     rdx, [rbp+arg_10]
0x1801fa8aa  mov     r15d, eax
0x1801fa8ad  mov     [rbp+arg_10], r12d
0x1801fa8b1  mov     rax, [rcx]
0x1801fa8b4  mov     rax, [rax+38h]
0x1801fa8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa8bd  mov     eax, [rbp+arg_10]
0x1801fa8c0  test    eax, eax
0x1801fa8c2  jnz     short loc_1801FA8D4
0x1801fa8c4  lea     rcx, [rbp+var_28]; void *
0x1801fa8c8  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa8cd  xor     eax, eax
0x1801fa8cf  jmp     loc_1801FA9E0
0x1801fa8d4  movdqa  xmm0, cs:__xmm@00000000000000200000000000000000
0x1801fa8dc  mov     esi, r12d
0x1801fa8df  mov     [rbp+var_20], r12
0x1801fa8e3  mov     [rbp+var_8], r12d
0x1801fa8e7  movdqu  [rbp+var_18], xmm0
0x1801fa8ec  test    eax, eax
0x1801fa8ee  jz      loc_1801FA9A1
0x1801fa8f4  mov     rdi, [rbp+var_28]
0x1801fa8f8  xor     ecx, ecx; string
0x1801fa8fa  mov     [rbp+string], r12
0x1801fa8fe  mov     rax, [rdi]
0x1801fa901  mov     rbx, [rax+30h]
0x1801fa905  call    cs:__imp_WindowsDeleteString
0x1801fa90c  nop     dword ptr [rax+rax+00h]
0x1801fa911  lea     r8, [rbp+string]
0x1801fa915  mov     [rbp+string], r12
0x1801fa919  mov     edx, esi
0x1801fa91b  mov     rcx, rdi
0x1801fa91e  mov     rax, rbx
0x1801fa921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fa926  mov     rcx, [rbp+string]; string
0x1801fa92a  lea     rdx, [rbp+length]; length
0x1801fa92e  mov     [rbp+length], r12d
0x1801fa932  call    cs:__imp_WindowsGetStringRawBuffer
0x1801fa939  nop     dword ptr [rax+rax+00h]
0x1801fa93e  mov     rcx, [rbp+string]
0x1801fa942  cmp     [rbp+length], r12d
0x1801fa946  jz      short loc_1801FA98A
0x1801fa948  call    SupportedFormat
0x1801fa94d  movzx   ebx, ax
0x1801fa950  test    ax, ax
0x1801fa953  jz      short loc_1801FA986
0x1801fa955  xor     r8d, r8d; int *
0x1801fa958  lea     rcx, [rbp+var_20]; this
0x1801fa95c  lea     edx, [r8+1]; int
0x1801fa960  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x1801fa965  test    rax, rax
0x1801fa968  jz      short loc_1801FA986
0x1801fa96a  mov     [rax], bx
0x1801fa96d  mov     [rax+8], r12
0x1801fa971  mov     dword ptr [rax+10h], 1
0x1801fa978  mov     dword ptr [rax+14h], 0FFFFFFFFh
0x1801fa97f  mov     dword ptr [rax+18h], 1
0x1801fa986  mov     rcx, [rbp+string]; string
0x1801fa98a  call    cs:__imp_WindowsDeleteString
0x1801fa991  nop     dword ptr [rax+rax+00h]
0x1801fa996  inc     esi
0x1801fa998  cmp     esi, [rbp+arg_10]
0x1801fa99b  jb      loc_1801FA8F4
0x1801fa9a1  mov     r10d, dword ptr [rbp+var_18]
0x1801fa9a5  test    r10d, r10d
0x1801fa9a8  jle     short loc_1801FA9C6
0x1801fa9aa  xor     edx, edx; int
0x1801fa9ac  lea     rcx, [rbp+var_20]; this
0x1801fa9b0  call    ?Elem@CArrayBase@@IEBAPEAXJ@Z; CArrayBase::Elem(long)
0x1801fa9b5  mov     rcx, rax; Src
0x1801fa9b8  mov     r8, r14; struct IEnumFORMATETC **
0x1801fa9bb  mov     edx, r10d; int
0x1801fa9be  call    ?Create@CEnumFormatEtc@RichEdit@@SAJPEBUtagFORMATETC@@JPEAPEAUIEnumFORMATETC@@@Z; RichEdit::CEnumFormatEtc::Create(tagFORMATETC const *,long,IEnumFORMATETC * *)
0x1801fa9c3  mov     r15d, eax
0x1801fa9c6  mov     edx, 2
0x1801fa9cb  lea     rcx, [rbp+var_20]
0x1801fa9cf  call    ?Clear@CArrayBase@@QEAAXW4tagArrayFlag@@@Z; CArrayBase::Clear(tagArrayFlag)
0x1801fa9d4  lea     rcx, [rbp+var_28]; void *
0x1801fa9d8  call    ??1?$TCntPtr@UIDataObject@@@Resp@@QEAA@XZ; Resp::TCntPtr<IDataObject>::~TCntPtr<IDataObject>(void)
0x1801fa9dd  mov     eax, r15d
0x1801fa9e0  lea     r11, [rsp+50h+var_s0]
0x1801fa9e5  mov     rbx, [r11+30h]
0x1801fa9e9  mov     rsi, [r11+38h]
0x1801fa9ed  mov     rsp, r11
0x1801fa9f0  pop     r15
0x1801fa9f2  pop     r14
0x1801fa9f4  pop     r12
0x1801fa9f6  pop     rdi
0x1801fa9f7  pop     rbp
0x1801fa9f8  retn
```
