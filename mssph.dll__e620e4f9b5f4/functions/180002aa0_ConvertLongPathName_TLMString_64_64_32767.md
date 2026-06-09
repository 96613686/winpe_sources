# ConvertLongPathName(TLMString<64,64,32767> &)

- ea: `0x180002aa0`
- end: `0x180002bf7`
- name: `?ConvertLongPathName@@YAXAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z`
- size: `343`
- prototype: `void __fastcall(const wchar_t **this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003970`

## callees

- `0x180002aa0`
- `0x1800055b0`
- `0x180006430`
- `0x18000a0a0`
- `0x18000a210`
- `0x18000bf0c`
- `0x18000d84c`
- `0x18000fcd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002ad1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002b0e`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002ad1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180002b0e`

## pseudocode

```c
void __fastcall ConvertLongPathName(const wchar_t **this)
{
  wchar_t *v2; // rax
  __int64 i; // rdx
  wchar_t *v4; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-C8h] BYREF
  __int64 v6; // [rsp+28h] [rbp-C0h]
  wchar_t v7; // [rsp+30h] [rbp-B8h] BYREF
  _WORD *v8; // [rsp+38h] [rbp-B0h]
  int v9; // [rsp+44h] [rbp-A4h]

  if ( *((_DWORD *)this + 5) )
  {
    v2 = wcschr(this[1], 0x2Fu);
    if ( v2 )
    {
      for ( i = v2 - this[1]; (_DWORD)i != -1; LODWORD(i) = v4 - this[1] )
      {
        this[1][(unsigned int)i] = 92;
        if ( (unsigned int)(i + 1) >= *((_DWORD *)this + 5) )
          break;
        v4 = wcschr(&this[1][(unsigned int)(i + 1)], 0x2Fu);
        if ( !v4 )
          break;
      }
    }
  }
  if ( *((_DWORD *)this + 5) >= 0x104u )
  {
    TLMString<64,64,32767>::TLMString<64,64,32767>((TLMString<64,64,32767> *)&v7, (__int64)this);
    if ( *v8 == 92 && v8[1] == 92 )
    {
      if ( v8[2] != 63 && v8[3] != 92 )
      {
        CLMString::operator=((__int64)this, (__int64)L"\\\\?\\");
        CLMString::Mid(&v7, v5, 1, (unsigned int)(v9 - 1));
        CLMString::Append((CLMString *)this, (const wchar_t *)(*(_QWORD *)(v6 + 8) + 2LL * v5[0]), v5[1]);
      }
    }
    else
    {
      CLMString::operator=((__int64)this, (__int64)L"\\\\?\\");
      CLMString::operator+=(this, &v7);
    }
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v7);
  }
}

```

## disassembly

```asm
0x180002aa0  mov     [rsp+arg_8], rbx
0x180002aa5  push    rdi
0x180002aa6  sub     rsp, 0E0h
0x180002aad  mov     rax, cs:__security_cookie
0x180002ab4  xor     rax, rsp
0x180002ab7  mov     [rsp+0E8h+var_18], rax
0x180002abf  mov     rbx, rcx
0x180002ac2  cmp     dword ptr [rcx+14h], 0
0x180002ac6  jbe     short loc_180002B27
0x180002ac8  mov     edx, 2Fh ; '/'; Ch
0x180002acd  mov     rcx, [rcx+8]; Str
0x180002ad1  call    cs:__imp_wcschr
0x180002ad7  mov     rdx, rax
0x180002ada  test    rax, rax
0x180002add  jz      short loc_180002B27
0x180002adf  sub     rdx, [rbx+8]
0x180002ae3  sar     rdx, 1
0x180002ae6  cmp     edx, 0FFFFFFFFh
0x180002ae9  jz      short loc_180002B27
0x180002aeb  mov     ecx, edx
0x180002aed  mov     rax, [rbx+8]
0x180002af1  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180002af7  lea     eax, [rdx+1]
0x180002afa  cmp     eax, [rbx+14h]
0x180002afd  jnb     short loc_180002B27
0x180002aff  mov     edx, 2Fh ; '/'; Ch
0x180002b04  mov     ecx, eax
0x180002b06  mov     rax, [rbx+8]
0x180002b0a  lea     rcx, [rax+rcx*2]; Str
0x180002b0e  call    cs:__imp_wcschr
0x180002b14  test    rax, rax
0x180002b17  jz      short loc_180002B27
0x180002b19  sub     rax, [rbx+8]
0x180002b1d  sar     rax, 1
0x180002b20  mov     edx, eax
0x180002b22  cmp     eax, 0FFFFFFFFh
0x180002b25  jnz     short loc_180002AEB
0x180002b27  cmp     dword ptr [rbx+14h], 104h
0x180002b2e  jb      loc_180002BD6
0x180002b34  mov     rdx, rbx
0x180002b37  lea     rcx, [rsp+0E8h+var_B8]
0x180002b3c  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@AEBV0@@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(TLMString<64,64,32767> const &)
0x180002b41  nop
0x180002b42  mov     rax, [rsp+0E8h+var_B0]
0x180002b47  cmp     word ptr [rax], 5Ch ; '\'
0x180002b4b  jnz     short loc_180002BAF
0x180002b4d  cmp     word ptr [rax+2], 5Ch ; '\'
0x180002b52  jnz     short loc_180002BAF
0x180002b54  cmp     word ptr [rax+4], 3Fh ; '?'
0x180002b59  jz      short loc_180002BCC
0x180002b5b  cmp     word ptr [rax+6], 5Ch ; '\'
0x180002b60  jz      short loc_180002BCC
0x180002b62  lea     rdx, String2; "\\\\?\\"
0x180002b69  mov     rcx, rbx
0x180002b6c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180002b71  mov     r9d, [rsp+0E8h+var_A4]
0x180002b76  dec     r9d
0x180002b79  mov     r8d, 1
0x180002b7f  lea     rdx, [rsp+0E8h+var_C8]
0x180002b84  lea     rcx, [rsp+0E8h+var_B8]
0x180002b89  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180002b8e  mov     r8d, [rsp+0E8h+var_C8]
0x180002b93  mov     rax, [rsp+0E8h+var_C0]
0x180002b98  mov     rdx, [rax+8]
0x180002b9c  lea     rdx, [rdx+r8*2]; wchar_t *
0x180002ba0  mov     r8d, [rsp+0E8h+var_C4]; unsigned int
0x180002ba5  mov     rcx, rbx; this
0x180002ba8  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180002bad  jmp     short loc_180002BCC
0x180002baf  lea     rdx, String2; "\\\\?\\"
0x180002bb6  mov     rcx, rbx
0x180002bb9  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180002bbe  lea     rdx, [rsp+0E8h+var_B8]
0x180002bc3  mov     rcx, rbx
0x180002bc6  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x180002bcb  nop
0x180002bcc  lea     rcx, [rsp+0E8h+var_B8]
0x180002bd1  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180002bd6  mov     rcx, [rsp+0E8h+var_18]
0x180002bde  xor     rcx, rsp; StackCookie
0x180002be1  call    __security_check_cookie
0x180002be6  mov     rbx, [rsp+0E8h+arg_8]
0x180002bee  add     rsp, 0E0h
0x180002bf5  pop     rdi
0x180002bf6  retn
```
