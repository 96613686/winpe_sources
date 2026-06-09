# _bstr_t::Data_t::Compare(_bstr_t::Data_t const &)

- ea: `0x140006138`
- end: `0x1400061cc`
- name: `?Compare@Data_t@_bstr_t@@QEBAHAEBV12@@Z`
- size: `148`
- prototype: `__int64 __fastcall(OLECHAR **this, BSTR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006ac8`

## callees

- `0x140006138`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x14000616b`
- `OLEAUT32!__imp_SysStringLen` at `0x140006176`
- `OLEAUT32!__imp_SysStringLen` at `0x14000616b`
- `OLEAUT32!__imp_SysStringLen` at `0x140006176`

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
0x140006138  mov     [rsp+arg_0], rbx
0x14000613d  mov     [rsp+arg_8], rsi
0x140006142  push    rdi
0x140006143  sub     rsp, 20h
0x140006147  mov     rdi, rdx
0x14000614a  mov     rsi, rcx
0x14000614d  mov     rcx, [rcx]; pbstr
0x140006150  mov     rax, [rdx]
0x140006153  test    rcx, rcx
0x140006156  jnz     short loc_14000615F
0x140006158  neg     rax
0x14000615b  sbb     eax, eax
0x14000615d  jmp     short loc_1400061BC
0x14000615f  test    rax, rax
0x140006162  jnz     short loc_14000616B
0x140006164  mov     eax, 1
0x140006169  jmp     short loc_1400061BC
0x14000616b  call    cs:__imp_SysStringLen
0x140006171  mov     ebx, eax
0x140006173  mov     rcx, [rdi]; pbstr
0x140006176  call    cs:__imp_SysStringLen
0x14000617c  mov     edx, eax
0x14000617e  mov     ecx, ebx
0x140006180  cmp     ebx, eax
0x140006182  cmova   ecx, eax
0x140006185  mov     r9, [rsi]
0x140006188  mov     r10, [rdi]
0x14000618b  test    ecx, ecx
0x14000618d  jz      short loc_1400061AC
0x14000618f  dec     ecx
0x140006191  movzx   eax, word ptr [r9]
0x140006195  movzx   r8d, word ptr [r10]
0x140006199  add     r10, 2
0x14000619d  add     r9, 2
0x1400061a1  cmp     ax, r8w
0x1400061a5  jz      short loc_14000618B
0x1400061a7  sub     eax, r8d
0x1400061aa  jmp     short loc_1400061BC
0x1400061ac  cmp     ebx, edx
0x1400061ae  jnb     short loc_1400061B5
0x1400061b0  or      eax, 0FFFFFFFFh
0x1400061b3  jmp     short loc_1400061BC
0x1400061b5  xor     eax, eax
0x1400061b7  cmp     ebx, edx
0x1400061b9  setnz   al
0x1400061bc  mov     rbx, [rsp+28h+arg_0]
0x1400061c1  mov     rsi, [rsp+28h+arg_8]
0x1400061c6  add     rsp, 20h
0x1400061ca  pop     rdi
0x1400061cb  retn
```
