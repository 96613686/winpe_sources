# CTxtBreaker::SetBreaks(CTxtPtr const &,long,uchar)

- ea: `0x18006a9f0`
- end: `0x18006ad10`
- name: `?SetBreaks@CTxtBreaker@@QEAA_NAEBVCTxtPtr@@JE@Z`
- size: `800`
- prototype: `bool(CTxtBreaker *__hidden this, const struct CTxtPtr *, int, unsigned __int8)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180069d60`

## callees

- `0x180043f84`
- `0x18006a468`
- `0x18006a9f0`
- `0x18006ad18`
- `0x18006af48`
- `0x18006afa0`
- `0x18008b5e8`
- `0x18010db70`
- `0x18013ce80`
- `0x18013d250`
- `0x18013dce6`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006abf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ac32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ac93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006abf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ac32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ac93`

## pseudocode

```c
char __fastcall CTxtBreaker::SetBreaks(CBreakArray **this, const struct CTxtPtr *a2, unsigned int a3, char a4)
{
  const struct CTxtPtr *v4; // r12
  __int64 v7; // rsi
  unsigned __int16 *Buf; // rdi
  int (__fastcall *v10)(__int64, HSTRING, __int64 *); // rbx
  int v11; // r12d
  unsigned int v12; // r14d
  int v13; // r15d
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // edi
  int i; // ebx
  __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  __int64 v25; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v28; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v29[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[256]; // [rsp+50h] [rbp-B0h] BYREF
  void *v31; // [rsp+150h] [rbp+50h]
  int v32; // [rsp+158h] [rbp+58h]

  v4 = a2;
  LOBYTE(a2) = a4;
  GetSegmenter(&v28, a2);
  v7 = v28;
  Buf = 0;
  if ( !v28 )
    return 0;
  if ( a3 )
  {
    v29[0] = 0;
    v31 = v30;
    v32 = 256;
    v25 = 0;
    memset_0(v30, 0, sizeof(v30));
    if ( a3 + 1 < 0x3FFFFFFF )
      Buf = (unsigned __int16 *)CTempBuf::GetBuf((CTempBuf *)v30, 2 * (a3 + 1));
    CTxtPtr::GetText(v4, a3, Buf);
    string = 0;
    if ( (unsigned int)Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, Buf, a3)
      || (v10 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v7 + 64LL),
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25),
          v10(v7, string, &v25) < 0)
      || (*(int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v25 + 56LL))(v25, v29) < 0 )
    {
      WindowsDeleteString(string);
      string = 0;
      if ( v31 != v30 )
        operator delete(v31, v24);
      v21 = v25;
      if ( v25 )
      {
        v25 = 0;
LABEL_35:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    else
    {
      v11 = *((_DWORD *)v4 + 4);
      v12 = 0;
      v13 = v11;
      while ( 1 )
      {
        if ( v12 >= v29[0] )
        {
          WindowsDeleteString(string);
          string = 0;
          if ( v31 != v30 )
            operator delete(v31, v22);
          v23 = v25;
          if ( v25 )
          {
            v25 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          return 1;
        }
        v27 = 0;
        v28 = 0;
        v14 = v25;
        v15 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
        if ( v15(v14, v12, &v27) < 0
          || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 56LL))(v27, &v28) < 0 )
        {
          break;
        }
        v16 = v11 + v28;
        for ( i = v11 + v28 + HIDWORD(v28) - v13; i; --i )
        {
          CBreakArray::SetBreak(this[3], v13, v13 == v16);
          ++v13;
        }
        v18 = v27;
        if ( v27 )
        {
          v27 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        ++v12;
      }
      v19 = v27;
      if ( v27 )
      {
        v27 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      WindowsDeleteString(string);
      string = 0;
      if ( v31 != v30 )
        operator delete(v31, v20);
      v21 = v25;
      if ( v25 )
      {
        v25 = 0;
        goto LABEL_35;
      }
    }
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return 0;
  }
  Microsoft::WRL::ComPtr<Windows::Data::Text::ISelectableWordsSegmenter>::InternalRelease(&v28);
  return 1;
}

```

## disassembly

```asm
0x18006a9f0  mov     [rsp-8+arg_18], rbx
0x18006a9f5  push    rbp
0x18006a9f6  push    rsi
0x18006a9f7  push    rdi
0x18006a9f8  push    r12
0x18006a9fa  push    r13
0x18006a9fc  push    r14
0x18006a9fe  push    r15
0x18006aa00  lea     rbp, [rsp-70h]
0x18006aa05  sub     rsp, 170h
0x18006aa0c  mov     rax, cs:__security_cookie
0x18006aa13  xor     rax, rsp
0x18006aa16  mov     [rbp+0A0h+var_40], rax
0x18006aa1a  mov     r12, rdx
0x18006aa1d  mov     r13, rcx
0x18006aa20  mov     dl, r9b
0x18006aa23  lea     rcx, [rsp+1A0h+var_168]
0x18006aa28  mov     ebx, r8d
0x18006aa2b  call    ?GetSegmenter@@YA?AV?$ComPtr@UISelectableWordsSegmenter@Text@Data@Windows@@@WRL@Microsoft@@E@Z; GetSegmenter(uchar)
0x18006aa30  mov     rsi, [rsp+1A0h+var_168]
0x18006aa35  xor     edi, edi
0x18006aa37  test    rsi, rsi
0x18006aa3a  jz      loc_18006ACE6
0x18006aa40  test    ebx, ebx
0x18006aa42  jnz     short loc_18006AA55
0x18006aa44  lea     rcx, [rsp+1A0h+var_168]
0x18006aa49  call    ?InternalRelease@?$ComPtr@UISelectableWordsSegmenter@Text@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Text::ISelectableWordsSegmenter>::InternalRelease(void)
0x18006aa4e  mov     al, 1
0x18006aa50  jmp     loc_18006ACE8
0x18006aa55  lea     rax, [rsp+1A0h+var_150]
0x18006aa5a  mov     [rsp+1A0h+var_160], edi
0x18006aa5e  mov     r8d, 100h; Size
0x18006aa64  mov     [rbp+0A0h+var_50], rax
0x18006aa68  xor     edx, edx; Val
0x18006aa6a  mov     [rbp+0A0h+var_48], r8d
0x18006aa6e  lea     rcx, [rsp+1A0h+var_150]; void *
0x18006aa73  mov     [rsp+1A0h+var_180], rdi
0x18006aa78  call    memset_0
0x18006aa7d  lea     edx, [rbx+1]
0x18006aa80  cmp     edx, 3FFFFFFFh
0x18006aa86  jnb     short loc_18006AA97
0x18006aa88  add     edx, edx; int
0x18006aa8a  lea     rcx, [rsp+1A0h+var_150]; this
0x18006aa8f  call    ?GetBuf@CTempBuf@@QEAAPEAXJ@Z; CTempBuf::GetBuf(long)
0x18006aa94  mov     rdi, rax
0x18006aa97  mov     r8, rdi; unsigned __int16 *
0x18006aa9a  mov     edx, ebx; int
0x18006aa9c  mov     rcx, r12; this
0x18006aa9f  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x18006aaa4  mov     r8d, ebx; unsigned int
0x18006aaa7  mov     [rsp+1A0h+string], 0
0x18006aab0  mov     rdx, rdi; unsigned __int16 *
0x18006aab3  lea     rcx, [rsp+1A0h+string]; this
0x18006aab8  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18006aabd  xor     edi, edi
0x18006aabf  test    eax, eax
0x18006aac1  jnz     loc_18006AC8E
0x18006aac7  mov     rax, [rsi]
0x18006aaca  lea     rcx, [rsp+1A0h+var_180]
0x18006aacf  mov     rbx, [rax+40h]
0x18006aad3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006aad8  mov     rdx, [rsp+1A0h+string]
0x18006aadd  lea     r8, [rsp+1A0h+var_180]
0x18006aae2  mov     rcx, rsi
0x18006aae5  mov     rax, rbx
0x18006aae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006aaed  test    eax, eax
0x18006aaef  js      loc_18006AC8E
0x18006aaf5  mov     rcx, [rsp+1A0h+var_180]
0x18006aafa  lea     rdx, [rsp+1A0h+var_160]
0x18006aaff  mov     rax, [rcx]
0x18006ab02  mov     rax, [rax+38h]
0x18006ab06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab0b  test    eax, eax
0x18006ab0d  js      loc_18006AC8E
0x18006ab13  mov     r12d, [r12+10h]
0x18006ab18  mov     r14d, edi
0x18006ab1b  mov     r15d, r12d
0x18006ab1e  cmp     r14d, [rsp+1A0h+var_160]
0x18006ab23  jnb     loc_18006AC2D
0x18006ab29  mov     [rsp+1A0h+var_170], rdi
0x18006ab2e  lea     rcx, [rsp+1A0h+var_170]
0x18006ab33  mov     [rsp+1A0h+var_168], rdi
0x18006ab38  mov     rdi, [rsp+1A0h+var_180]
0x18006ab3d  mov     rax, [rdi]
0x18006ab40  mov     rbx, [rax+30h]
0x18006ab44  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ab49  lea     r8, [rsp+1A0h+var_170]
0x18006ab4e  mov     edx, r14d
0x18006ab51  mov     rcx, rdi
0x18006ab54  mov     rax, rbx
0x18006ab57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab5c  xor     ebx, ebx
0x18006ab5e  test    eax, eax
0x18006ab60  js      short loc_18006ABD1
0x18006ab62  mov     rcx, [rsp+1A0h+var_170]
0x18006ab67  lea     rdx, [rsp+1A0h+var_168]
0x18006ab6c  mov     rax, [rcx]
0x18006ab6f  mov     rax, [rax+38h]
0x18006ab73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ab78  test    eax, eax
0x18006ab7a  js      short loc_18006ABD1
0x18006ab7c  mov     edi, dword ptr [rsp+1A0h+var_168]
0x18006ab80  mov     ebx, dword ptr [rsp+1A0h+var_168+4]
0x18006ab84  add     edi, r12d
0x18006ab87  sub     ebx, r15d
0x18006ab8a  add     ebx, edi
0x18006ab8c  jz      short loc_18006ABAC
0x18006ab8e  mov     rcx, [r13+18h]; this
0x18006ab92  xor     r8d, r8d
0x18006ab95  cmp     r15d, edi
0x18006ab98  mov     edx, r15d; int
0x18006ab9b  setz    r8b; int
0x18006ab9f  call    ?SetBreak@CBreakArray@@QEAAXJH@Z; CBreakArray::SetBreak(long,int)
0x18006aba4  inc     r15d
0x18006aba7  sub     ebx, 1
0x18006abaa  jnz     short loc_18006AB8E
0x18006abac  mov     rcx, [rsp+1A0h+var_170]
0x18006abb1  xor     edi, edi
0x18006abb3  test    rcx, rcx
0x18006abb6  jz      short loc_18006ABC9
0x18006abb8  mov     [rsp+1A0h+var_170], rdi
0x18006abbd  mov     rax, [rcx]
0x18006abc0  mov     rax, [rax+10h]
0x18006abc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abc9  inc     r14d
0x18006abcc  jmp     loc_18006AB1E
0x18006abd1  mov     rcx, [rsp+1A0h+var_170]
0x18006abd6  test    rcx, rcx
0x18006abd9  jz      short loc_18006ABEC
0x18006abdb  mov     [rsp+1A0h+var_170], rbx
0x18006abe0  mov     rax, [rcx]
0x18006abe3  mov     rax, [rax+10h]
0x18006abe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006abec  mov     rcx, [rsp+1A0h+string]; string
0x18006abf1  call    cs:__imp_WindowsDeleteString
0x18006abf8  nop     dword ptr [rax+rax+00h]
0x18006abfd  mov     rcx, [rbp+0A0h+var_50]; void *
0x18006ac01  lea     rax, [rsp+1A0h+var_150]
0x18006ac06  mov     [rsp+1A0h+string], rbx
0x18006ac0b  cmp     rcx, rax
0x18006ac0e  jz      short loc_18006AC15
0x18006ac10  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ac15  mov     rcx, [rsp+1A0h+var_180]
0x18006ac1a  test    rcx, rcx
0x18006ac1d  jz      loc_18006ACD2
0x18006ac23  mov     [rsp+1A0h+var_180], rbx
0x18006ac28  jmp     loc_18006ACC6
0x18006ac2d  mov     rcx, [rsp+1A0h+string]; string
0x18006ac32  call    cs:__imp_WindowsDeleteString
0x18006ac39  nop     dword ptr [rax+rax+00h]
0x18006ac3e  mov     rcx, [rbp+0A0h+var_50]; void *
0x18006ac42  lea     rax, [rsp+1A0h+var_150]
0x18006ac47  mov     [rsp+1A0h+string], rdi
0x18006ac4c  cmp     rcx, rax
0x18006ac4f  jz      short loc_18006AC56
0x18006ac51  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006ac56  mov     rcx, [rsp+1A0h+var_180]
0x18006ac5b  test    rcx, rcx
0x18006ac5e  jz      short loc_18006AC71
0x18006ac60  mov     [rsp+1A0h+var_180], rdi
0x18006ac65  mov     rax, [rcx]
0x18006ac68  mov     rax, [rax+10h]
0x18006ac6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac71  test    rsi, rsi
0x18006ac74  jz      loc_18006AA4E
0x18006ac7a  mov     rax, [rsi]
0x18006ac7d  mov     rcx, rsi
0x18006ac80  mov     rax, [rax+10h]
0x18006ac84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ac89  jmp     loc_18006AA4E
0x18006ac8e  mov     rcx, [rsp+1A0h+string]; string
0x18006ac93  call    cs:__imp_WindowsDeleteString
0x18006ac9a  nop     dword ptr [rax+rax+00h]
0x18006ac9f  mov     rcx, [rbp+0A0h+var_50]; void *
0x18006aca3  lea     rax, [rsp+1A0h+var_150]
0x18006aca8  mov     [rsp+1A0h+string], rdi
0x18006acad  cmp     rcx, rax
0x18006acb0  jz      short loc_18006ACB7
0x18006acb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18006acb7  mov     rcx, [rsp+1A0h+var_180]
0x18006acbc  test    rcx, rcx
0x18006acbf  jz      short loc_18006ACD2
0x18006acc1  mov     [rsp+1A0h+var_180], rdi
0x18006acc6  mov     rax, [rcx]
0x18006acc9  mov     rax, [rax+10h]
0x18006accd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006acd2  test    rsi, rsi
0x18006acd5  jz      short loc_18006ACE6
0x18006acd7  mov     rax, [rsi]
0x18006acda  mov     rcx, rsi
0x18006acdd  mov     rax, [rax+10h]
0x18006ace1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ace6  xor     al, al
0x18006ace8  mov     rcx, [rbp+0A0h+var_40]
0x18006acec  xor     rcx, rsp; StackCookie
0x18006acef  call    __security_check_cookie
0x18006acf4  mov     rbx, [rsp+1A0h+arg_18]
0x18006acfc  add     rsp, 170h
0x18006ad03  pop     r15
0x18006ad05  pop     r14
0x18006ad07  pop     r13
0x18006ad09  pop     r12
0x18006ad0b  pop     rdi
0x18006ad0c  pop     rsi
0x18006ad0d  pop     rbp
0x18006ad0e  retn
```
