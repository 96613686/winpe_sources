# CGenerateMSI::GenerateIdentifier(ushort * *,ushort const *)

- ea: `0x18002dda8`
- end: `0x18002dea5`
- name: `?GenerateIdentifier@CGenerateMSI@@AEAAJPEAPEAGPEBG@Z`
- size: `253`
- prototype: `__int64 __fastcall(CGenerateMSI *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002b600`
- `0x18002b820`
- `0x18002c050`
- `0x18002c300`
- `0x18002cae0`
- `0x18002cc60`
- `0x18002cef0`

## callees

- `0x18000a01c`
- `0x18002dda8`

## import_xrefs

- `msvcrt!iswdigit` at `0x18002ddea`
- `msvcrt!iswdigit` at `0x18002ddea`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18002ddd9`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18002de65`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18002ddd9`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18002de65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002de4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002de4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002de16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002de16`

## pseudocode

```c
__int64 __fastcall CGenerateMSI::GenerateIdentifier(CGenerateMSI *this, LPVOID *a2, WCHAR *a3)
{
  WCHAR v3; // ax
  const unsigned __int16 *v4; // rdi
  int v6; // ebx
  int v7; // ebp
  wint_t *v8; // rsi
  int v9; // eax
  __int64 v10; // rax
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  int v14; // esi
  unsigned int v15; // ebx
  __int64 v16; // rdx

  v3 = *a3;
  v4 = a3;
  v6 = 0;
  v7 = 0;
  if ( *a3 )
  {
    v8 = a3;
    do
    {
      if ( IsCharAlphaNumericW(v3) )
      {
        if ( !v6 && iswdigit(*v8) )
          v7 = 1;
        ++v6;
      }
      v3 = *++v8;
    }
    while ( *v8 );
  }
  v9 = v6 + 1;
  if ( !v7 )
    v9 = v6;
  v10 = (unsigned int)(v9 + 1);
  v11 = (unsigned int)v10;
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
  *a2 = v12;
  if ( !v12 )
    return 2147942414LL;
  if ( !v7 )
  {
    v14 = 0;
    v15 = 0;
    goto LABEL_21;
  }
  v14 = StringCchCopyW(v12, v11, L"I");
  if ( v14 >= 0 )
  {
    v15 = 1;
LABEL_21:
    while ( *v4 )
    {
      if ( IsCharAlphaNumericW(*v4) )
      {
        v16 = v15++;
        *((_WORD *)*a2 + v16) = *v4;
      }
      ++v4;
    }
    *((_WORD *)*a2 + v15) = 0;
    return (unsigned int)v14;
  }
  CoTaskMemFree(*a2);
  *a2 = 0;
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002dda8  push    rbx
0x18002ddaa  push    rbp
0x18002ddab  push    rsi
0x18002ddac  push    rdi
0x18002ddad  push    r12
0x18002ddaf  push    r14
0x18002ddb1  push    r15
0x18002ddb3  sub     rsp, 20h
0x18002ddb7  movzx   eax, word ptr [r8]
0x18002ddbb  xor     r15d, r15d
0x18002ddbe  mov     rdi, r8
0x18002ddc1  mov     r14, rdx
0x18002ddc4  mov     ebx, r15d
0x18002ddc7  mov     ebp, r15d
0x18002ddca  lea     r12d, [r15+1]
0x18002ddce  test    ax, ax
0x18002ddd1  jz      short loc_18002DE05
0x18002ddd3  mov     rsi, r8
0x18002ddd6  movzx   ecx, ax; ch
0x18002ddd9  call    cs:__imp_IsCharAlphaNumericW
0x18002dddf  test    eax, eax
0x18002dde1  jz      short loc_18002DDF9
0x18002dde3  test    ebx, ebx
0x18002dde5  jnz     short loc_18002DDF6
0x18002dde7  movzx   ecx, word ptr [rsi]; C
0x18002ddea  call    cs:__imp_iswdigit
0x18002ddf0  test    eax, eax
0x18002ddf2  cmovnz  ebp, r12d
0x18002ddf6  add     ebx, r12d
0x18002ddf9  add     rsi, 2
0x18002ddfd  movzx   eax, word ptr [rsi]
0x18002de00  test    ax, ax
0x18002de03  jnz     short loc_18002DDD6
0x18002de05  lea     eax, [rbx+1]
0x18002de08  test    ebp, ebp
0x18002de0a  cmovz   eax, ebx
0x18002de0d  add     eax, r12d
0x18002de10  mov     ebx, eax
0x18002de12  lea     rcx, [rax+rax]; cb
0x18002de16  call    cs:__imp_CoTaskMemAlloc
0x18002de1c  mov     [r14], rax
0x18002de1f  test    rax, rax
0x18002de22  jnz     short loc_18002DE2B
0x18002de24  mov     eax, 8007000Eh
0x18002de29  jmp     short loc_18002DE96
0x18002de2b  test    ebp, ebp
0x18002de2d  jz      short loc_18002DE5A
0x18002de2f  lea     r8, aI; "I"
0x18002de36  mov     rdx, rbx; unsigned __int64
0x18002de39  mov     rcx, rax; unsigned __int16 *
0x18002de3c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002de41  mov     esi, eax
0x18002de43  test    eax, eax
0x18002de45  jns     short loc_18002DE55
0x18002de47  mov     rcx, [r14]; pv
0x18002de4a  call    cs:__imp_CoTaskMemFree
0x18002de50  mov     [r14], r15
0x18002de53  jmp     short loc_18002DE94
0x18002de55  mov     ebx, r12d
0x18002de58  jmp     short loc_18002DE82
0x18002de5a  mov     esi, r15d
0x18002de5d  mov     ebx, r15d
0x18002de60  jmp     short loc_18002DE82
0x18002de62  movzx   ecx, ax; ch
0x18002de65  call    cs:__imp_IsCharAlphaNumericW
0x18002de6b  test    eax, eax
0x18002de6d  jz      short loc_18002DE7E
0x18002de6f  mov     rcx, [r14]
0x18002de72  movzx   eax, word ptr [rdi]
0x18002de75  mov     edx, ebx
0x18002de77  add     ebx, r12d
0x18002de7a  mov     [rcx+rdx*2], ax
0x18002de7e  add     rdi, 2
0x18002de82  movzx   eax, word ptr [rdi]
0x18002de85  test    ax, ax
0x18002de88  jnz     short loc_18002DE62
0x18002de8a  mov     rcx, [r14]
0x18002de8d  mov     edx, ebx
0x18002de8f  mov     [rcx+rdx*2], r15w
0x18002de94  mov     eax, esi
0x18002de96  add     rsp, 20h
0x18002de9a  pop     r15
0x18002de9c  pop     r14
0x18002de9e  pop     r12
0x18002dea0  pop     rdi
0x18002dea1  pop     rsi
0x18002dea2  pop     rbp
0x18002dea3  pop     rbx
0x18002dea4  retn
```
