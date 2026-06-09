# tpm12class::TPMW8_PCR_Read::DecodeRqu(ushort *)

- ea: `0x180020f20`
- end: `0x180021045`
- name: `?DecodeRqu@TPMW8_PCR_Read@tpm12class@@UEAAJPEAG@Z`
- size: `293`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_PCR_Read *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x18000a534`
- `0x18001f570`
- `0x180020f20`
- `0x1800241f0`
- `0x1800242bc`
- `0x180059010`

## string_xrefs

- `0x180020f84`: `--TPM2_PCR_Read: Parameters------------------------------------------\n`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_PCR_Read::DecodeRqu(tpm12class::TPMW8_PCR_Read *this, unsigned __int16 *a2)
{
  signed int v4; // ebx
  unsigned __int16 *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  unsigned __int16 v10; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v11[510]; // [rsp+22h] [rbp-226h] BYREF

  v10 = 0;
  v4 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( TraceEnabled() )
  {
    v4 = tpm12class::TPMW8_COMMAND::DecodeRqu(this, a2);
    if ( v4 >= 0 )
    {
      v4 = TraceDirect(L"--TPM2_PCR_Read: Parameters------------------------------------------\r\n");
      if ( v4 >= 0 )
      {
        v5 = &v10;
        v6 = 256;
        v7 = 2147483646;
        do
        {
          if ( !v7 )
            break;
          if ( !*a2 )
            break;
          *v5++ = *a2++;
          --v7;
          --v6;
        }
        while ( v6 );
        v8 = v5 - 1;
        v4 = v6 == 0 ? 0x8007007A : 0;
        if ( v6 )
          v8 = v5;
        *v8 = 0;
        if ( v6 )
        {
          v4 = StringCchCatW(&v10, 0x100u, L"pcrSelectionIn.");
          if ( v4 >= 0 )
            return (unsigned int)(*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 24) + 40LL))(
                                   (char *)this + 192,
                                   &v10);
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180020f20  mov     [rsp+arg_10], rbx
0x180020f25  push    rbp
0x180020f26  push    rsi
0x180020f27  push    rdi
0x180020f28  sub     rsp, 230h
0x180020f2f  mov     rax, cs:__security_cookie
0x180020f36  xor     rax, rsp
0x180020f39  mov     [rsp+248h+var_28], rax
0x180020f41  mov     rdi, rdx
0x180020f44  mov     rsi, rcx
0x180020f47  xor     ebp, ebp
0x180020f49  lea     rcx, [rsp+248h+var_226]; void *
0x180020f4e  xor     edx, edx; Val
0x180020f50  mov     [rsp+248h+var_228], bp
0x180020f55  mov     r8d, 1FEh; Size
0x180020f5b  mov     ebx, ebp
0x180020f5d  call    memset_0
0x180020f62  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x180020f67  test    al, al
0x180020f69  jz      loc_18002101F
0x180020f6f  mov     rdx, rdi; unsigned __int16 *
0x180020f72  mov     rcx, rsi; this
0x180020f75  call    ?DecodeRqu@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRqu(ushort *)
0x180020f7a  mov     ebx, eax
0x180020f7c  test    eax, eax
0x180020f7e  js      loc_18002101F
0x180020f84  lea     rcx, aTpm2PcrReadPar; "--TPM2_PCR_Read: Parameters------------"...
0x180020f8b  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x180020f90  mov     ebx, eax
0x180020f92  test    eax, eax
0x180020f94  js      loc_18002101F
0x180020f9a  mov     edx, 100h; unsigned __int64
0x180020f9f  lea     r9, [rsp+248h+var_228]
0x180020fa4  mov     r8d, edx
0x180020fa7  mov     eax, 7FFFFFFEh
0x180020fac  test    rax, rax
0x180020faf  jz      short loc_180020FCE
0x180020fb1  movzx   ecx, word ptr [rdi]
0x180020fb4  test    cx, cx
0x180020fb7  jz      short loc_180020FCE
0x180020fb9  mov     [r9], cx
0x180020fbd  add     rdi, 2
0x180020fc1  add     r9, 2
0x180020fc5  dec     rax
0x180020fc8  sub     r8, 1
0x180020fcc  jnz     short loc_180020FAC
0x180020fce  mov     rax, r8
0x180020fd1  lea     rcx, [r9-2]
0x180020fd5  neg     rax
0x180020fd8  sbb     ebx, ebx
0x180020fda  not     ebx
0x180020fdc  and     ebx, 8007007Ah
0x180020fe2  test    r8, r8
0x180020fe5  cmovnz  rcx, r9
0x180020fe9  mov     [rcx], bp
0x180020fec  jz      short loc_18002101F
0x180020fee  lea     r8, aPcrselectionin; "pcrSelectionIn."
0x180020ff5  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180020ffa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020fff  mov     ebx, eax
0x180021001  test    eax, eax
0x180021003  js      short loc_18002101F
0x180021005  lea     rcx, [rsi+0C0h]
0x18002100c  mov     rax, [rcx]
0x18002100f  lea     rdx, [rsp+248h+var_228]
0x180021014  mov     rax, [rax+28h]
0x180021018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002101d  mov     ebx, eax
0x18002101f  mov     eax, ebx
0x180021021  mov     rcx, [rsp+248h+var_28]
0x180021029  xor     rcx, rsp; StackCookie
0x18002102c  call    __security_check_cookie
0x180021031  mov     rbx, [rsp+248h+arg_10]
0x180021039  add     rsp, 230h
0x180021040  pop     rdi
0x180021041  pop     rsi
0x180021042  pop     rbp
0x180021043  retn
```
