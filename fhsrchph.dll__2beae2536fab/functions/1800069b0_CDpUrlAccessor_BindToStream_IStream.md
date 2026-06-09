# CDpUrlAccessor::BindToStream(IStream * *)

- ea: `0x1800069b0`
- end: `0x180006b59`
- name: `?BindToStream@CDpUrlAccessor@@UEAAJPEAPEAUIStream@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(CDpUrlAccessor *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800069b0`
- `0x180006b60`
- `0x180007530`
- `0x1800075fc`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::BindToStream(CDpUrlAccessor *this, struct IStream **a2)
{
  __int64 result; // rax
  CFileStream *v5; // rbx
  char *v6; // rsi
  const unsigned __int16 *v7; // rdx
  int v8; // eax
  char v9; // r12
  int v10; // edi
  CFileStream *v11; // rdi
  const unsigned __int16 *v12; // r14
  const unsigned __int16 *v13; // rdx
  int v14; // edx
  int v15; // ebp
  int v16; // r8d
  CFileStream *v17; // [rsp+78h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v17 = 0;
  result = ATL::CComObject<CFileStream>::CreateInstance(&v17);
  if ( (int)result >= 0 )
  {
    v5 = v17;
    if ( v17 )
      (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v17 + 8LL))(v17);
    v6 = (char *)this + 144;
    if ( *((_QWORD *)this + 21) < 8u )
      v7 = (const unsigned __int16 *)((char *)this + 144);
    else
      v7 = *(const unsigned __int16 **)v6;
    v8 = CFileStream::Init(v5, v7);
    v9 = v8;
    if ( v8 >= 0 )
    {
      *a2 = (struct IStream *)v5;
      return 0;
    }
    v17 = 0;
    v10 = ATL::CComObject<CFileStream>::CreateInstance(&v17);
    if ( v10 >= 0 )
    {
      v11 = v17;
      if ( v17 )
        (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v17 + 8LL))(v17);
      v12 = (const unsigned __int16 *)((char *)this + 184);
      if ( *((_QWORD *)v12 + 3) < 8u )
        v13 = v12;
      else
        v13 = *(const unsigned __int16 **)v12;
      v15 = CFileStream::Init(v11, v13);
      if ( v15 >= 0 )
      {
        *a2 = (struct IStream *)v11;
        if ( v5 )
          (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v5 + 16LL))(v5);
        return 0;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( *((_QWORD *)v12 + 3) >= 8u )
          v12 = *(const unsigned __int16 **)v12;
        if ( *((_QWORD *)v6 + 3) >= 8u )
          v6 = *(char **)v6;
        WPP_SF_SdSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v16, (_DWORD)v6, v9, (__int64)v12, v15);
      }
      if ( v11 )
        (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v5 )
        (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v5 + 16LL))(v5);
      return (unsigned int)v15;
    }
    else
    {
      if ( v5 )
        (*(void (__fastcall **)(CFileStream *))(*(_QWORD *)v5 + 16LL))(v5);
      return (unsigned int)v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800069b0  mov     [rsp+arg_0], rbx
0x1800069b5  mov     [rsp+arg_10], rbp
0x1800069ba  push    rsi
0x1800069bb  push    rdi
0x1800069bc  push    r12
0x1800069be  push    r14
0x1800069c0  push    r15
0x1800069c2  sub     rsp, 40h
0x1800069c6  mov     r15, rdx
0x1800069c9  mov     r14, rcx
0x1800069cc  test    rdx, rdx
0x1800069cf  jnz     short loc_1800069DB
0x1800069d1  mov     eax, 80004003h
0x1800069d6  jmp     loc_180006B40
0x1800069db  mov     [rsp+68h+arg_8], 0
0x1800069e4  lea     rcx, [rsp+68h+arg_8]
0x1800069e9  call    ?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)
0x1800069ee  test    eax, eax
0x1800069f0  js      loc_180006B40
0x1800069f6  mov     rbx, [rsp+68h+arg_8]
0x1800069fb  test    rbx, rbx
0x1800069fe  jz      short loc_180006A10
0x180006a00  mov     rax, [rbx]
0x180006a03  mov     rcx, rbx
0x180006a06  mov     rax, [rax+8]
0x180006a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a0f  nop
0x180006a10  lea     rsi, [r14+90h]
0x180006a17  cmp     qword ptr [rsi+18h], 8
0x180006a1c  jb      short loc_180006A23
0x180006a1e  mov     rdx, [rsi]
0x180006a21  jmp     short loc_180006A26
0x180006a23  mov     rdx, rsi; unsigned __int16 *
0x180006a26  mov     rcx, rbx; this
0x180006a29  call    ?Init@CFileStream@@QEAAJPEBG@Z; CFileStream::Init(ushort const *)
0x180006a2e  mov     r12d, eax
0x180006a31  test    eax, eax
0x180006a33  js      short loc_180006A3D
0x180006a35  mov     [r15], rbx
0x180006a38  jmp     loc_180006B3E
0x180006a3d  mov     [rsp+68h+arg_8], 0
0x180006a46  lea     rcx, [rsp+68h+arg_8]
0x180006a4b  call    ?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)
0x180006a50  mov     edi, eax
0x180006a52  test    eax, eax
0x180006a54  jns     short loc_180006A72
0x180006a56  test    rbx, rbx
0x180006a59  jz      short loc_180006A6B
0x180006a5b  mov     rdx, [rbx]
0x180006a5e  mov     rcx, rbx
0x180006a61  mov     rax, [rdx+10h]
0x180006a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6a  nop
0x180006a6b  mov     eax, edi
0x180006a6d  jmp     loc_180006B40
0x180006a72  mov     rdi, [rsp+68h+arg_8]
0x180006a77  test    rdi, rdi
0x180006a7a  jz      short loc_180006A8C
0x180006a7c  mov     rax, [rdi]
0x180006a7f  mov     rcx, rdi
0x180006a82  mov     rax, [rax+8]
0x180006a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a8b  nop
0x180006a8c  add     r14, 0B8h
0x180006a93  cmp     qword ptr [r14+18h], 8
0x180006a98  jb      short loc_180006A9F
0x180006a9a  mov     rdx, [r14]
0x180006a9d  jmp     short loc_180006AA2
0x180006a9f  mov     rdx, r14; unsigned __int16 *
0x180006aa2  mov     rcx, rdi; this
0x180006aa5  call    ?Init@CFileStream@@QEAAJPEBG@Z; CFileStream::Init(ushort const *)
0x180006aaa  mov     ebp, eax
0x180006aac  test    eax, eax
0x180006aae  jns     short loc_180006B26
0x180006ab0  lea     rax, WPP_GLOBAL_Control
0x180006ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006abe  cmp     rcx, rax
0x180006ac1  jz      short loc_180006AF8
0x180006ac3  test    byte ptr [rcx+1Ch], 1
0x180006ac7  jz      short loc_180006AF8
0x180006ac9  cmp     qword ptr [r14+18h], 8
0x180006ace  jb      short loc_180006AD3
0x180006ad0  mov     r14, [r14]
0x180006ad3  cmp     qword ptr [rsi+18h], 8
0x180006ad8  jb      short loc_180006ADD
0x180006ada  mov     rsi, [rsi]
0x180006add  mov     [rsp+68h+var_38], ebp
0x180006ae1  mov     [rsp+68h+var_40], r14
0x180006ae6  mov     [rsp+68h+var_48], r12d
0x180006aeb  mov     r9, rsi
0x180006aee  mov     rcx, [rcx+10h]
0x180006af2  call    WPP_SF_SdSd
0x180006af7  nop
0x180006af8  test    rdi, rdi
0x180006afb  jz      short loc_180006B0D
0x180006afd  mov     rax, [rdi]
0x180006b00  mov     rcx, rdi
0x180006b03  mov     rax, [rax+10h]
0x180006b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0c  nop
0x180006b0d  test    rbx, rbx
0x180006b10  jz      short loc_180006B22
0x180006b12  mov     rax, [rbx]
0x180006b15  mov     rcx, rbx
0x180006b18  mov     rax, [rax+10h]
0x180006b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b21  nop
0x180006b22  mov     eax, ebp
0x180006b24  jmp     short loc_180006B40
0x180006b26  mov     [r15], rdi
0x180006b29  test    rbx, rbx
0x180006b2c  jz      short loc_180006B3E
0x180006b2e  mov     rax, [rbx]
0x180006b31  mov     rcx, rbx
0x180006b34  mov     rax, [rax+10h]
0x180006b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b3d  nop
0x180006b3e  xor     eax, eax
0x180006b40  lea     r11, [rsp+68h+var_28]
0x180006b45  mov     rbx, [r11+30h]
0x180006b49  mov     rbp, [r11+40h]
0x180006b4d  mov     rsp, r11
0x180006b50  pop     r15
0x180006b52  pop     r14
0x180006b54  pop     r12
0x180006b56  pop     rdi
0x180006b57  pop     rsi
0x180006b58  retn
```
