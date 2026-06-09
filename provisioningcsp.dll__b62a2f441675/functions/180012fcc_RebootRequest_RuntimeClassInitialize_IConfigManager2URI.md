# RebootRequest::RuntimeClassInitialize(IConfigManager2URI *)

- ea: `0x180012fcc`
- end: `0x18001308e`
- name: `?RuntimeClassInitialize@RebootRequest@@QEAAJPEAUIConfigManager2URI@@@Z`
- size: `194`
- prototype: `int(RebootRequest *__hidden this, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9a8`

## callees

- `0x180006974`
- `0x180009fac`
- `0x180012fcc`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall RebootRequest::RuntimeClassInitialize(RebootRequest *this, struct IConfigManager2URI *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // r8
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v11; // [rsp+48h] [rbp+10h] BYREF
  void *Src; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v11);
  if ( v4 < 0 )
  {
    v5 = 59;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
      (const char *)(unsigned int)v4,
      v9);
    return (unsigned int)v4;
  }
  if ( v11 != 1 )
  {
    v4 = -2147024809;
    v5 = 60;
    goto LABEL_3;
  }
  Src = 0;
  (*(void (__fastcall **)(struct IConfigManager2URI *, _QWORD, void **))(*(_QWORD *)a2 + 88LL))(a2, 0, &Src);
  try
  {
    if ( *(_WORD *)Src )
    {
      v7 = -1;
      do
        ++v7;
      while ( *((_WORD *)Src + v7) );
    }
    std::wstring::assign((char *)this + 24, Src);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x44,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\rebootrequest.cpp",
                           v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180012fcc  mov     [rsp+arg_0], rbx
0x180012fd1  push    rsi
0x180012fd2  push    rdi
0x180012fd3  push    r14; int
0x180012fd5  sub     rsp, 20h
0x180012fd9  mov     rdi, rdx
0x180012fdc  mov     rsi, rcx
0x180012fdf  xor     r14d, r14d
0x180012fe2  mov     [rsp+38h+arg_8], r14d
0x180012fe7  mov     rax, [rdx]
0x180012fea  lea     rdx, [rsp+38h+arg_8]
0x180012fef  mov     rcx, rdi
0x180012ff2  mov     rax, [rax+88h]
0x180012ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ffe  mov     ebx, eax
0x180013000  test    eax, eax
0x180013002  jns     short loc_180013020
0x180013004  lea     edx, [r14+3Bh]; void *
0x180013008  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\provcsp\\reboo"...
0x18001300f  mov     r9d, ebx; char *
0x180013012  mov     rcx, [rsp+38h]; this
0x180013017  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001301c  mov     eax, ebx
0x18001301e  jmp     short loc_18001307F
0x180013020  cmp     [rsp+38h+arg_8], 1
0x180013025  jz      short loc_180013033
0x180013027  mov     ebx, 80070057h
0x18001302c  mov     edx, 3Ch ; '<'
0x180013031  jmp     short loc_180013008
0x180013033  mov     [rsp+38h+Src], r14
0x180013038  mov     rax, [rdi]
0x18001303b  lea     r8, [rsp+38h+Src]
0x180013040  xor     edx, edx
0x180013042  mov     rcx, rdi
0x180013045  mov     rax, [rax+58h]
0x180013049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001304e  nop
0x18001304f  mov     rdx, [rsp+38h+Src]; Src
0x180013054  cmp     [rdx], r14w
0x180013058  jnz     short loc_18001305F
0x18001305a  mov     r8, r14
0x18001305d  jmp     short loc_18001306D
0x18001305f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013063  inc     r8
0x180013066  cmp     [rdx+r8*2], r14w
0x18001306b  jnz     short loc_180013063
0x18001306d  lea     rcx, [rsi+18h]; void *
0x180013071  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180013076  nop
0x180013077  xor     eax, eax
0x180013079  jmp     short loc_18001307F
0x18001307b  mov     eax, [rsp+38h+arg_8]
0x18001307f  mov     rbx, [rsp+38h+arg_0]
0x180013084  add     rsp, 20h
0x180013088  pop     r14
0x18001308a  pop     rdi
0x18001308b  pop     rsi
0x18001308c  retn
```
