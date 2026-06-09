# _bstr_t::Data_t::Compare(_bstr_t::Data_t const &)

- ea: `0x180005b74`
- end: `0x180005c08`
- name: `?Compare@Data_t@_bstr_t@@QEBAHAEBV12@@Z`
- size: `148`
- prototype: `__int64 __fastcall(OLECHAR **this, BSTR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000578c`

## callees

- `0x180005b74`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180005ba7`
- `OLEAUT32!__imp_SysStringLen` at `0x180005bb2`
- `OLEAUT32!__imp_SysStringLen` at `0x180005ba7`
- `OLEAUT32!__imp_SysStringLen` at `0x180005bb2`

## pseudocode

```c
__int64 __fastcall _bstr_t::Data_t::Compare(OLECHAR **this, BSTR *a2)
{
  OLECHAR *v4; // rcx
  BSTR v5; // rax
  UINT v7; // ebx
  UINT v8; // eax
  UINT v9; // edx
  UINT v10; // ecx
  OLECHAR *v11; // r9
  BSTR v12; // r10
  int v13; // eax
  int v14; // r8d

  v4 = *this;
  v5 = *a2;
  if ( !v4 )
    return (unsigned int)-(v5 != 0);
  if ( !v5 )
    return 1;
  v7 = SysStringLen(v4);
  v8 = SysStringLen(*a2);
  v9 = v8;
  v10 = v7;
  if ( v7 > v8 )
    v10 = v8;
  v11 = *this;
  v12 = *a2;
  while ( v10 )
  {
    --v10;
    v13 = *v11;
    v14 = *v12++;
    ++v11;
    if ( (_WORD)v13 != (_WORD)v14 )
      return (unsigned int)(v13 - v14);
  }
  if ( v7 >= v9 )
    return v7 != v9;
  else
    return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x180005b74  mov     [rsp+arg_0], rbx
0x180005b79  mov     [rsp+arg_8], rsi
0x180005b7e  push    rdi
0x180005b7f  sub     rsp, 20h
0x180005b83  mov     rdi, rdx
0x180005b86  mov     rsi, rcx
0x180005b89  mov     rcx, [rcx]; pbstr
0x180005b8c  mov     rax, [rdx]
0x180005b8f  test    rcx, rcx
0x180005b92  jnz     short loc_180005B9B
0x180005b94  neg     rax
0x180005b97  sbb     eax, eax
0x180005b99  jmp     short loc_180005BF8
0x180005b9b  test    rax, rax
0x180005b9e  jnz     short loc_180005BA7
0x180005ba0  mov     eax, 1
0x180005ba5  jmp     short loc_180005BF8
0x180005ba7  call    cs:__imp_SysStringLen
0x180005bad  mov     ebx, eax
0x180005baf  mov     rcx, [rdi]; pbstr
0x180005bb2  call    cs:__imp_SysStringLen
0x180005bb8  mov     edx, eax
0x180005bba  mov     ecx, ebx
0x180005bbc  cmp     ebx, eax
0x180005bbe  cmova   ecx, eax
0x180005bc1  mov     r9, [rsi]
0x180005bc4  mov     r10, [rdi]
0x180005bc7  test    ecx, ecx
0x180005bc9  jz      short loc_180005BE8
0x180005bcb  dec     ecx
0x180005bcd  movzx   eax, word ptr [r9]
0x180005bd1  movzx   r8d, word ptr [r10]
0x180005bd5  add     r10, 2
0x180005bd9  add     r9, 2
0x180005bdd  cmp     ax, r8w
0x180005be1  jz      short loc_180005BC7
0x180005be3  sub     eax, r8d
0x180005be6  jmp     short loc_180005BF8
0x180005be8  cmp     ebx, edx
0x180005bea  jnb     short loc_180005BF1
0x180005bec  or      eax, 0FFFFFFFFh
0x180005bef  jmp     short loc_180005BF8
0x180005bf1  xor     eax, eax
0x180005bf3  cmp     ebx, edx
0x180005bf5  setnz   al
0x180005bf8  mov     rbx, [rsp+28h+arg_0]
0x180005bfd  mov     rsi, [rsp+28h+arg_8]
0x180005c02  add     rsp, 20h
0x180005c06  pop     rdi
0x180005c07  retn
```
