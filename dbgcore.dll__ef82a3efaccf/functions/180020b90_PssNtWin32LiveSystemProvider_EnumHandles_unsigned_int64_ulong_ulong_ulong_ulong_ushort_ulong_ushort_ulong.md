# PssNtWin32LiveSystemProvider::EnumHandles(unsigned __int64 *,ulong *,ulong *,ulong *,ulong *,ushort *,ulong,ushort *,ulong)

- ea: `0x180020b90`
- end: `0x180020d17`
- name: `?EnumHandles@PssNtWin32LiveSystemProvider@@UEAAJPEA_KPEAK111PEAGK2K@Z`
- size: `391`
- prototype: `__int64 __fastcall(PssNtWin32LiveSystemProvider *__hidden this, unsigned __int64 *, unsigned int *, unsigned int *, unsigned int *, unsigned int *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180003424`
- `0x180020b90`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall PssNtWin32LiveSystemProvider::EnumHandles(
        PssNtWin32LiveSystemProvider *this,
        unsigned __int64 *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned int a10)
{
  __int64 result; // rax
  void *v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // eax
  unsigned __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned __int64 v21; // rbx
  _QWORD v22[3]; // [rsp+40h] [rbp-A1h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-89h]
  unsigned int v24; // [rsp+5Ch] [rbp-85h]
  unsigned int v25; // [rsp+60h] [rbp-81h]
  unsigned int v26; // [rsp+64h] [rbp-7Dh]
  unsigned __int16 v27; // [rsp+78h] [rbp-69h]
  void *Src; // [rsp+80h] [rbp-61h]
  unsigned __int16 v29; // [rsp+88h] [rbp-59h]
  void *v30; // [rsp+90h] [rbp-51h]

  memset_0(v22, 0, 0x88u);
  result = (*((__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD *, int))this + 143))(
             *((_QWORD *)this + 153),
             2,
             *((_QWORD *)this + 156),
             v22,
             136);
  if ( (_DWORD)result == 259 )
  {
    *a2 = 0;
    return 1;
  }
  else if ( (_DWORD)result )
  {
    *a2 = 0;
    if ( (int)result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v15 = Src;
    *a2 = v22[0];
    *a3 = v23;
    *a4 = v24;
    *a5 = v25;
    *a6 = v26;
    if ( v15 && v27 )
    {
      v16 = a8 - 1;
      v17 = 2 * v16;
      if ( v27 <= (unsigned __int64)(2 * v16) )
        v17 = v27;
      v18 = v17;
      memcpy_0(a7, v15, v17);
      a7[v18 >> 1] = 0;
    }
    if ( v30 && v29 )
    {
      v19 = a10 - 1;
      v20 = 2 * v19;
      if ( v29 <= (unsigned __int64)(2 * v19) )
        v20 = v29;
      v21 = v20;
      memcpy_0(a9, v30, v20);
      a9[v21 >> 1] = 0;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180020b90  push    rbp
0x180020b92  push    rbx
0x180020b93  push    rsi
0x180020b94  push    rdi
0x180020b95  push    r12
0x180020b97  push    r13
0x180020b99  push    r14
0x180020b9b  push    r15
0x180020b9d  lea     rbp, [rsp-7]
0x180020ba2  sub     rsp, 0E8h
0x180020ba9  mov     rax, cs:__security_cookie
0x180020bb0  xor     rax, rsp
0x180020bb3  mov     [rbp+3Fh+var_50], rax
0x180020bb7  mov     rax, [rbp+3Fh+arg_20]
0x180020bbb  mov     r12, r8
0x180020bbe  mov     r14, [rbp+3Fh+arg_30]
0x180020bc2  mov     rsi, rdx
0x180020bc5  mov     r15, [rbp+3Fh+arg_40]
0x180020bcc  mov     rbx, rcx
0x180020bcf  mov     [rsp+120h+var_F0], rax
0x180020bd4  lea     rcx, [rsp+120h+var_E0]; void *
0x180020bd9  mov     rax, [rbp+3Fh+arg_28]
0x180020bdd  mov     edi, 88h
0x180020be2  mov     r8d, edi; Size
0x180020be5  mov     [rsp+120h+var_E8], rax
0x180020bea  xor     edx, edx; Val
0x180020bec  mov     r13, r9
0x180020bef  call    memset_0
0x180020bf4  mov     r8, [rbx+4E0h]
0x180020bfb  lea     r9, [rsp+120h+var_E0]
0x180020c00  mov     rcx, [rbx+4C8h]
0x180020c07  mov     edx, 2
0x180020c0c  mov     rax, [rbx+478h]
0x180020c13  mov     [rsp+120h+var_100], edi
0x180020c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c1c  xor     edi, edi
0x180020c1e  cmp     eax, 103h
0x180020c23  jnz     short loc_180020C30
0x180020c25  mov     [rsi], rdi
0x180020c28  lea     eax, [rdi+1]
0x180020c2b  jmp     loc_180020CF7
0x180020c30  test    eax, eax
0x180020c32  jz      short loc_180020C4A
0x180020c34  mov     [rsi], rdi
0x180020c37  jle     loc_180020CF7
0x180020c3d  movzx   eax, ax
0x180020c40  or      eax, 80070000h
0x180020c45  jmp     loc_180020CF7
0x180020c4a  mov     rax, [rsp+120h+var_E0]
0x180020c4f  mov     rcx, [rsp+120h+var_F0]
0x180020c54  mov     rdx, [rbp+3Fh+Src]; Src
0x180020c58  mov     [rsi], rax
0x180020c5b  mov     eax, [rsp+120h+var_C8]
0x180020c5f  mov     [r12], eax
0x180020c63  mov     eax, [rsp+120h+var_C4]
0x180020c67  mov     [r13+0], eax
0x180020c6b  mov     eax, [rsp+120h+var_C0]
0x180020c6f  mov     [rcx], eax
0x180020c71  mov     rcx, [rsp+120h+var_E8]
0x180020c76  mov     eax, [rbp+3Fh+var_BC]
0x180020c79  mov     [rcx], eax
0x180020c7b  test    rdx, rdx
0x180020c7e  jz      short loc_180020CB6
0x180020c80  cmp     [rbp+3Fh+var_A8], di
0x180020c84  jz      short loc_180020CB6
0x180020c86  movzx   r8d, [rbp+3Fh+var_A8]
0x180020c8b  mov     eax, [rbp+3Fh+arg_38]
0x180020c91  dec     eax
0x180020c93  mov     ecx, eax
0x180020c95  add     eax, eax
0x180020c97  add     rcx, rcx
0x180020c9a  cmp     r8, rcx
0x180020c9d  mov     rcx, r14; void *
0x180020ca0  cmovbe  eax, r8d
0x180020ca4  mov     r8d, eax; Size
0x180020ca7  mov     ebx, eax
0x180020ca9  call    memcpy_0
0x180020cae  shr     rbx, 1
0x180020cb1  mov     [r14+rbx*2], di
0x180020cb6  mov     rdx, [rbp+3Fh+var_90]; Src
0x180020cba  test    rdx, rdx
0x180020cbd  jz      short loc_180020CF5
0x180020cbf  cmp     [rbp+3Fh+var_98], di
0x180020cc3  jz      short loc_180020CF5
0x180020cc5  movzx   r8d, [rbp+3Fh+var_98]
0x180020cca  mov     eax, [rbp+3Fh+arg_48]
0x180020cd0  dec     eax
0x180020cd2  mov     ecx, eax
0x180020cd4  add     eax, eax
0x180020cd6  add     rcx, rcx
0x180020cd9  cmp     r8, rcx
0x180020cdc  mov     rcx, r15; void *
0x180020cdf  cmovbe  eax, r8d
0x180020ce3  mov     r8d, eax; Size
0x180020ce6  mov     ebx, eax
0x180020ce8  call    memcpy_0
0x180020ced  shr     rbx, 1
0x180020cf0  mov     [r15+rbx*2], di
0x180020cf5  xor     eax, eax
0x180020cf7  mov     rcx, [rbp+3Fh+var_50]
0x180020cfb  xor     rcx, rsp; StackCookie
0x180020cfe  call    __security_check_cookie
0x180020d03  add     rsp, 0E8h
0x180020d0a  pop     r15
0x180020d0c  pop     r14
0x180020d0e  pop     r13
0x180020d10  pop     r12
0x180020d12  pop     rdi
0x180020d13  pop     rsi
0x180020d14  pop     rbx
0x180020d15  pop     rbp
0x180020d16  retn
```
