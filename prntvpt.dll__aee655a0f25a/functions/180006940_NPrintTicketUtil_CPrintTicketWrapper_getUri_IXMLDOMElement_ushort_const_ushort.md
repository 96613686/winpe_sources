# NPrintTicketUtil::CPrintTicketWrapper::getUri(IXMLDOMElement *,ushort const *,ushort * *)

- ea: `0x180006940`
- end: `0x180006afc`
- name: `?getUri@CPrintTicketWrapper@NPrintTicketUtil@@QEAAJPEAUIXMLDOMElement@@PEBGPEAPEAG@Z`
- size: `444`
- prototype: `int(NPrintTicketUtil::CPrintTicketWrapper *__hidden this, struct IXMLDOMElement *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800064a0`
- `0x180006884`
- `0x18000cd50`
- `0x18001d878`
- `0x18001ddc4`
- `0x18001f850`

## callees

- `0x1800056e0`
- `0x180006940`
- `0x180023010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800069b5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800069b5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800069fb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006aae`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800069fb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180006aae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069db`
- `OLEAUT32!__imp_SysFreeString` at `0x180006a70`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069db`
- `OLEAUT32!__imp_SysFreeString` at `0x180006a70`

## pseudocode

```c
__int64 __fastcall NPrintTicketUtil::CPrintTicketWrapper::getUri(
        NPrintTicketUtil::CPrintTicketWrapper *this,
        struct IXMLDOMElement *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  UINT v7; // edx
  int v8; // ebp
  __int64 v9; // rax
  OLECHAR *v10; // rdi
  _QWORD *v11; // rsi
  int v12; // ebx
  __int64 v13; // rcx
  bool v14; // sf
  int v16; // eax
  unsigned __int16 *v17; // rax
  _QWORD v18[5]; // [rsp+30h] [rbp-28h] BYREF
  UINT v19; // [rsp+68h] [rbp+10h] BYREF

  v18[0] = 0;
  if ( !a2 || !a4 || !a3 )
  {
    NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(v18);
    return 2147942487LL;
  }
  v7 = 0;
  v8 = 0;
  *a4 = 0;
  v9 = -1;
  v19 = 0;
  do
    ++v9;
  while ( a3[v9] );
  if ( (int)v9 > 0 )
  {
    while ( a3[v7] != 58 )
    {
      if ( (int)++v7 >= (int)v9 )
        goto LABEL_7;
    }
    v10 = SysAllocStringLen(a3, v7);
    if ( !v10 )
      goto LABEL_9;
  }
  else
  {
LABEL_7:
    v10 = SysAllocString(&psz);
    if ( !v10 )
    {
      v10 = 0;
LABEL_9:
      v11 = (_QWORD *)((char *)this + 16);
LABEL_10:
      v12 = -2147024882;
      goto LABEL_11;
    }
  }
  v13 = *((_QWORD *)this + 2);
  v11 = (_QWORD *)((char *)this + 16);
  v12 = (*(__int64 (__fastcall **)(__int64, struct IXMLDOMElement *, __int64))(*(_QWORD *)v13 + 56LL))(v13, a2, 1);
  if ( v12 >= 0 )
  {
    v8 = 1;
    v12 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, _QWORD, UINT *))(*(_QWORD *)*v11 + 96LL))(
            *v11,
            v10,
            0,
            0,
            &v19);
  }
  v14 = v12 < 0;
  if ( !v12 )
  {
    v17 = SysAllocStringLen(0, ++v19);
    *a4 = v17;
    if ( !v17 )
      goto LABEL_10;
    v12 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD, unsigned __int16 *, UINT *))(*(_QWORD *)*v11 + 96LL))(
            *v11,
            v10,
            0,
            v17,
            &v19);
    v14 = v12 < 0;
  }
  if ( v14 )
  {
LABEL_11:
    if ( *a4 )
    {
      SysFreeString(*a4);
      *a4 = 0;
    }
  }
  if ( v8 )
  {
    v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 64LL))(*v11);
    if ( v16 < 0 )
      v12 = v16;
  }
  if ( v10 )
    SysFreeString(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180006940  mov     [rsp+arg_18], rbx
0x180006945  push    rsi
0x180006946  push    r14
0x180006948  push    r15
0x18000694a  sub     rsp, 40h
0x18000694e  xor     r15d, r15d
0x180006951  mov     r14, r9
0x180006954  mov     [rsp+58h+var_28], r15
0x180006959  mov     rbx, rdx
0x18000695c  mov     rsi, rcx
0x18000695f  test    rdx, rdx
0x180006962  jz      loc_180006AEB
0x180006968  test    r9, r9
0x18000696b  jz      loc_180006AEB
0x180006971  test    r8, r8
0x180006974  jz      loc_180006AEB
0x18000697a  mov     [rsp+58h+arg_0], rbp
0x18000697f  mov     edx, r15d; ui
0x180006982  mov     [rsp+58h+arg_10], rdi
0x180006987  mov     ebp, r15d
0x18000698a  mov     [r9], r15
0x18000698d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006994  mov     [rsp+58h+arg_8], r15d
0x180006999  nop     dword ptr [rax+00000000h]
0x1800069a0  inc     rax
0x1800069a3  cmp     [r8+rax*2], dx
0x1800069a8  jnz     short loc_1800069A0
0x1800069aa  test    eax, eax
0x1800069ac  jg      short loc_1800069E6
0x1800069ae  lea     rcx, psz; psz
0x1800069b5  call    cs:__imp_SysAllocString
0x1800069bb  mov     rdi, rax
0x1800069be  test    rax, rax
0x1800069c1  jnz     short loc_180006A09
0x1800069c3  mov     rdi, r15
0x1800069c6  add     rsi, 10h
0x1800069ca  mov     ebx, 8007000Eh
0x1800069cf  mov     rcx, [r14]; bstrString
0x1800069d2  test    rcx, rcx
0x1800069d5  jz      loc_180006A5F
0x1800069db  call    cs:__imp_SysFreeString
0x1800069e1  mov     [r14], r15
0x1800069e4  jmp     short loc_180006A5F
0x1800069e6  mov     ecx, edx
0x1800069e8  cmp     word ptr [r8+rcx*2], 3Ah ; ':'
0x1800069ee  jz      short loc_1800069F8
0x1800069f0  inc     edx
0x1800069f2  cmp     edx, eax
0x1800069f4  jl      short loc_1800069E6
0x1800069f6  jmp     short loc_1800069AE
0x1800069f8  mov     rcx, r8; strIn
0x1800069fb  call    cs:__imp_SysAllocStringLen
0x180006a01  mov     rdi, rax
0x180006a04  test    rax, rax
0x180006a07  jz      short loc_1800069C6
0x180006a09  mov     rcx, [rsi+10h]
0x180006a0d  add     rsi, 10h
0x180006a11  mov     r8d, 1
0x180006a17  mov     rdx, rbx
0x180006a1a  mov     rax, [rcx]
0x180006a1d  mov     rax, [rax+38h]
0x180006a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a26  mov     ebx, eax
0x180006a28  test    eax, eax
0x180006a2a  js      short loc_180006A55
0x180006a2c  mov     rcx, [rsi]
0x180006a2f  lea     rdx, [rsp+58h+arg_8]
0x180006a34  mov     [rsp+58h+var_38], rdx
0x180006a39  xor     r9d, r9d
0x180006a3c  xor     r8d, r8d
0x180006a3f  mov     rdx, rdi
0x180006a42  mov     ebp, 1
0x180006a47  mov     rax, [rcx]
0x180006a4a  mov     rax, [rax+60h]
0x180006a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a53  mov     ebx, eax
0x180006a55  test    ebx, ebx
0x180006a57  jz      short loc_180006AA2
0x180006a59  js      loc_1800069CF
0x180006a5f  test    ebp, ebp
0x180006a61  mov     rbp, [rsp+58h+arg_0]
0x180006a66  jnz     short loc_180006A8C
0x180006a68  test    rdi, rdi
0x180006a6b  jz      short loc_180006A76
0x180006a6d  mov     rcx, rdi; bstrString
0x180006a70  call    cs:__imp_SysFreeString
0x180006a76  mov     rdi, [rsp+58h+arg_10]
0x180006a7b  mov     eax, ebx
0x180006a7d  mov     rbx, [rsp+58h+arg_18]
0x180006a82  add     rsp, 40h
0x180006a86  pop     r15
0x180006a88  pop     r14
0x180006a8a  pop     rsi
0x180006a8b  retn
0x180006a8c  mov     rcx, [rsi]
0x180006a8f  mov     rax, [rcx]
0x180006a92  mov     rax, [rax+40h]
0x180006a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9b  test    eax, eax
0x180006a9d  cmovs   ebx, eax
0x180006aa0  jmp     short loc_180006A68
0x180006aa2  mov     edx, [rsp+58h+arg_8]
0x180006aa6  xor     ecx, ecx; strIn
0x180006aa8  inc     edx; ui
0x180006aaa  mov     [rsp+58h+arg_8], edx
0x180006aae  call    cs:__imp_SysAllocStringLen
0x180006ab4  mov     [r14], rax
0x180006ab7  mov     r9, rax
0x180006aba  test    rax, rax
0x180006abd  jz      loc_1800069CA
0x180006ac3  mov     rcx, [rsi]
0x180006ac6  lea     rdx, [rsp+58h+arg_8]
0x180006acb  mov     [rsp+58h+var_38], rdx
0x180006ad0  xor     r8d, r8d
0x180006ad3  mov     rdx, rdi
0x180006ad6  mov     rax, [rcx]
0x180006ad9  mov     rax, [rax+60h]
0x180006add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae2  mov     ebx, eax
0x180006ae4  test    eax, eax
0x180006ae6  jmp     loc_180006A59
0x180006aeb  lea     rcx, [rsp+58h+var_28]
0x180006af0  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x180006af5  mov     eax, 80070057h
0x180006afa  jmp     short loc_180006A7D
```
