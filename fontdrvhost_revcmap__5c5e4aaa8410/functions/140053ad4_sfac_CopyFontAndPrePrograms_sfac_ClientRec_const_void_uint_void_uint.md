# sfac_CopyFontAndPrePrograms(sfac_ClientRec const *,void *,uint,void *,uint)

- ea: `0x140053ad4`
- end: `0x140053c74`
- name: `?sfac_CopyFontAndPrePrograms@@YAHPEBUsfac_ClientRec@@PEAXI1I@Z`
- size: `416`
- prototype: `int(const struct sfac_ClientRec *, void *, unsigned int, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140013530`

## callees

- `0x1400265a8`
- `0x140053ad4`
- `0x140072578`
- `0x140076eea`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall sfac_CopyFontAndPrePrograms(
        const struct sfac_ClientRec *a1,
        unsigned __int64 a2,
        int a3,
        void *a4,
        unsigned int a5)
{
  size_t v6; // rbp
  void *v7; // r14
  size_t v9; // rdi
  size_t v10; // rsi
  const void *v11; // rax
  const void *v12; // rax
  _QWORD v14[4]; // [rsp+30h] [rbp-48h] BYREF
  size_t v15; // [rsp+80h] [rbp+8h] BYREF

  LODWORD(v6) = a3;
  v7 = (void *)a2;
  v9 = *((unsigned int *)a1 + 27);
  v10 = 0;
  v15 = 0;
  if ( !(_DWORD)v9 )
    goto LABEL_24;
  if ( (unsigned int)v9 > 0x7FFFFFFF || (a2 = *((unsigned int *)a1 + 26), (unsigned int)a2 > 0x7FFFFFFF) )
  {
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
    goto LABEL_23;
  }
  v11 = (const void *)(*((__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, size_t *))a1 + 1))(
                        *(_QWORD *)a1,
                        a2,
                        (unsigned int)v9,
                        &v15);
  v10 = v15;
  while ( 1 )
  {
    v14[0] = a1;
    v14[1] = v10;
    if ( (_DWORD)v9 )
    {
      if ( !v11 || (unsigned int)v9 > (unsigned int)v6 )
      {
        AutoReleaseSfntFrag::~AutoReleaseSfntFrag((AutoReleaseSfntFrag *)v14);
        return 5120;
      }
      memcpy_0(v7, v11, v9);
    }
    v6 = *((unsigned int *)a1 + 19);
    v9 = 0;
    v15 = 0;
    if ( !(_DWORD)v6 )
      break;
    if ( (unsigned int)v6 <= 0x7FFFFFFF )
    {
      a2 = *((unsigned int *)a1 + 18);
      if ( (unsigned int)a2 <= 0x7FFFFFFF )
      {
        v12 = (const void *)(*((__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD, size_t *))a1 + 1))(
                              *(_QWORD *)a1,
                              a2,
                              (unsigned int)v6,
                              &v15);
        v9 = v15;
        goto LABEL_10;
      }
    }
LABEL_23:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
LABEL_24:
    v11 = 0;
  }
  v12 = 0;
LABEL_10:
  v14[2] = a1;
  v14[3] = v9;
  if ( (_DWORD)v6 )
  {
    if ( !v12 || (unsigned int)v6 > a5 )
    {
      if ( v9 )
        (*((void (__fastcall **)(size_t))a1 + 2))(v9);
      if ( v10 )
        (*((void (__fastcall **)(size_t))a1 + 2))(v10);
      return 5120;
    }
    memcpy_0(a4, v12, v6);
  }
  if ( v9 )
    (*((void (__fastcall **)(size_t))a1 + 2))(v9);
  if ( v10 )
    (*((void (__fastcall **)(size_t))a1 + 2))(v10);
  return 0;
}

```

## disassembly

```asm
0x140053ad4  mov     rax, rsp
0x140053ad7  mov     [rax+10h], rbx
0x140053adb  mov     [rax+18h], rbp
0x140053adf  push    rsi
0x140053ae0  push    rdi
0x140053ae1  push    r12
0x140053ae3  push    r14
0x140053ae5  push    r15
0x140053ae7  sub     rsp, 50h
0x140053aeb  mov     r15, r9
0x140053aee  mov     ebp, r8d
0x140053af1  mov     r14, rdx
0x140053af4  mov     rbx, rcx
0x140053af7  mov     edi, [rcx+6Ch]
0x140053afa  xor     esi, esi
0x140053afc  mov     [rax+8], rsi
0x140053b00  mov     r12d, 7FFFFFFFh
0x140053b06  test    edi, edi
0x140053b08  jz      loc_140053C11
0x140053b0e  cmp     edi, r12d
0x140053b11  ja      loc_140053C05
0x140053b17  mov     edx, [rcx+68h]
0x140053b1a  cmp     edx, r12d
0x140053b1d  ja      loc_140053C05
0x140053b23  lea     r9, [rax+8]
0x140053b27  mov     r8d, edi
0x140053b2a  mov     rcx, [rcx]
0x140053b2d  mov     rax, [rbx+8]
0x140053b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053b36  mov     rsi, [rsp+78h+arg_0]
0x140053b3e  mov     [rsp+78h+var_48], rbx
0x140053b43  mov     [rsp+78h+var_40], rsi
0x140053b48  test    edi, edi
0x140053b4a  jnz     loc_140053BE9
0x140053b50  mov     ebp, [rbx+4Ch]
0x140053b53  xor     edi, edi
0x140053b55  mov     [rsp+78h+arg_0], rdi
0x140053b5d  test    ebp, ebp
0x140053b5f  jz      loc_140053C18
0x140053b65  cmp     ebp, r12d
0x140053b68  ja      loc_140053C0B
0x140053b6e  mov     edx, [rbx+48h]
0x140053b71  cmp     edx, r12d
0x140053b74  ja      loc_140053C0B
0x140053b7a  lea     r9, [rsp+78h+arg_0]
0x140053b82  mov     r8d, ebp
0x140053b85  mov     rcx, [rbx]
0x140053b88  mov     rax, [rbx+8]
0x140053b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053b91  mov     rdi, [rsp+78h+arg_0]
0x140053b99  mov     [rsp+78h+var_38], rbx
0x140053b9e  mov     [rsp+78h+var_30], rdi
0x140053ba3  test    ebp, ebp
0x140053ba5  jz      short loc_140053BC4
0x140053ba7  test    rax, rax
0x140053baa  jz      short loc_140053C1F
0x140053bac  cmp     ebp, [rsp+78h+arg_20]
0x140053bb3  ja      short loc_140053C1F
0x140053bb5  mov     r8, rbp; Size
0x140053bb8  mov     rdx, rax; Src
0x140053bbb  mov     rcx, r15; void *
0x140053bbe  call    memcpy_0
0x140053bc3  nop
0x140053bc4  test    rdi, rdi
0x140053bc7  jnz     short loc_140053C30
0x140053bc9  test    rsi, rsi
0x140053bcc  jnz     short loc_140053C3E
0x140053bce  xor     eax, eax
0x140053bd0  lea     r11, [rsp+78h+var_28]
0x140053bd5  mov     rbx, [r11+38h]
0x140053bd9  mov     rbp, [r11+40h]
0x140053bdd  mov     rsp, r11
0x140053be0  pop     r15
0x140053be2  pop     r14
0x140053be4  pop     r12
0x140053be6  pop     rdi
0x140053be7  pop     rsi
0x140053be8  retn
0x140053be9  test    rax, rax
0x140053bec  jz      short loc_140053C68
0x140053bee  cmp     edi, ebp
0x140053bf0  ja      short loc_140053C68
0x140053bf2  mov     r8, rdi; Size
0x140053bf5  mov     rdx, rax; Src
0x140053bf8  mov     rcx, r14; void *
0x140053bfb  call    memcpy_0
0x140053c00  jmp     loc_140053B50
0x140053c05  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140053c0a  nop
0x140053c0b  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140053c10  nop
0x140053c11  xor     eax, eax
0x140053c13  jmp     loc_140053B3E
0x140053c18  xor     eax, eax
0x140053c1a  jmp     loc_140053B99
0x140053c1f  test    rdi, rdi
0x140053c22  jnz     short loc_140053C4C
0x140053c24  test    rsi, rsi
0x140053c27  jnz     short loc_140053C5A
0x140053c29  mov     eax, 1400h
0x140053c2e  jmp     short loc_140053BD0
0x140053c30  mov     rcx, rdi
0x140053c33  mov     rax, [rbx+10h]
0x140053c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053c3c  jmp     short loc_140053BC9
0x140053c3e  mov     rcx, rsi
0x140053c41  mov     rax, [rbx+10h]
0x140053c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053c4a  jmp     short loc_140053BCE
0x140053c4c  mov     rcx, rdi
0x140053c4f  mov     rax, [rbx+10h]
0x140053c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053c58  jmp     short loc_140053C24
0x140053c5a  mov     rcx, rsi
0x140053c5d  mov     rax, [rbx+10h]
0x140053c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053c66  jmp     short loc_140053C29
0x140053c68  lea     rcx, [rsp+78h+var_48]; this
0x140053c6d  call    ??1AutoReleaseSfntFrag@@QEAA@XZ; AutoReleaseSfntFrag::~AutoReleaseSfntFrag(void)
0x140053c72  jmp     short loc_140053C29
```
