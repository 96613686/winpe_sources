# SetStatusAndHeaders(IHttpResponse *,char *,char *,ulong)

- ea: `0x180005b20`
- end: `0x180005d3e`
- name: `?SetStatusAndHeaders@@YAJPEAVIHttpResponse@@PEAD1K@Z`
- size: `542`
- prototype: `__int64 __fastcall(struct IHttpResponse *, char *String, char *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d20`
- `0x180007d40`

## callees

- `0x180005b20`
- `0x1800074f0`
- `0x18000d010`

## import_xrefs

- `msvcrt!atoi` at `0x180005b61`
- `msvcrt!atoi` at `0x180005b61`
- `msvcrt!isdigit` at `0x180005c91`
- `msvcrt!isdigit` at `0x180005ca2`
- `msvcrt!isdigit` at `0x180005c91`
- `msvcrt!isdigit` at `0x180005ca2`
- `msvcrt!isspace` at `0x180005caf`
- `msvcrt!isspace` at `0x180005cc0`
- `msvcrt!isspace` at `0x180005caf`
- `msvcrt!isspace` at `0x180005cc0`

## pseudocode

```c
__int64 __fastcall SetStatusAndHeaders(struct IHttpResponse *a1, char *String, char *a3, unsigned int a4)
{
  char *v6; // rdi
  unsigned __int16 v8; // r14
  void (__fastcall *v9)(struct IHttpResponse *, __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  unsigned int v10; // edi
  __int64 result; // rax
  __int64 v12; // rax
  unsigned __int16 v13; // r15
  int v14; // ecx
  int v15; // ecx
  unsigned int i; // edi
  int v17; // [rsp+60h] [rbp-58h] BYREF
  __int128 v18; // [rsp+68h] [rbp-50h] BYREF
  __int128 v19; // [rsp+78h] [rbp-40h]
  __int16 v20; // [rsp+C8h] [rbp+10h] BYREF

  v17 = 0;
  v6 = String;
  v18 = 0;
  v19 = 0;
  if ( String )
  {
    if ( *String )
    {
      v8 = atoi(String);
      v9 = *(void (__fastcall **)(struct IHttpResponse *, __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 184LL);
      v20 = 0;
      v9(a1, &v20, 0, 0, 0, 0, 0, 0, 0, 0);
      if ( v8 != v20 )
      {
        v13 = 4;
        if ( v8 != 401 )
          v13 = 0;
        if ( isdigit((unsigned __int8)*v6) )
        {
          do
            v14 = (unsigned __int8)*++v6;
          while ( isdigit(v14) );
        }
        if ( isspace((unsigned __int8)*v6) )
        {
          do
            v15 = (unsigned __int8)*++v6;
          while ( isspace(v15) );
        }
        result = (*(__int64 (__fastcall **)(struct IHttpResponse *, _QWORD, char *, _QWORD, _DWORD, _QWORD, _DWORD))(*(_QWORD *)a1 + 24LL))(
                   a1,
                   v8,
                   v6,
                   v13,
                   0,
                   0,
                   0);
        if ( (int)result < 0 )
          return result;
      }
    }
  }
  if ( !a4 )
    return 0;
  if ( a4 < 2 )
    return 2147942487LL;
  if ( *a3 != 13 || a3[1] != 10 )
  {
    for ( i = 0; i < a4 - 2; ++i )
    {
      if ( a3[i] == 10 && a3[i + 1] == 13 && a3[i + 2] == 10 )
      {
        v10 = i + 3;
        if ( v10 > 2 )
        {
          result = SetHeaders(a1, a3, v10 - 2);
          if ( (int)result < 0 )
            return result;
        }
        goto LABEL_12;
      }
    }
    return 2147942487LL;
  }
  v10 = 2;
LABEL_12:
  if ( v10 >= a4 )
    return 0;
  LODWORD(v18) = 0;
  *((_QWORD *)&v18 + 1) = &a3[v10];
  v12 = *(_QWORD *)a1;
  LODWORD(v19) = a4 - v10;
  result = (*(__int64 (__fastcall **)(struct IHttpResponse *, __int128 *, __int64, _QWORD, int, int *, _QWORD))(v12 + 168))(
             a1,
             &v18,
             1,
             0,
             1,
             &v17,
             0);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180005b20  mov     [rsp+arg_10], rbx
0x180005b25  push    rbp
0x180005b26  push    rsi
0x180005b27  push    rdi
0x180005b28  push    r12
0x180005b2a  push    r14
0x180005b2c  sub     rsp, 90h
0x180005b33  xor     r12d, r12d
0x180005b36  xorps   xmm0, xmm0
0x180005b39  mov     [rsp+0B8h+var_58], r12d
0x180005b3e  mov     ebx, r9d
0x180005b41  mov     rbp, r8
0x180005b44  mov     rdi, rdx
0x180005b47  mov     rsi, rcx
0x180005b4a  movups  [rsp+0B8h+var_50], xmm0
0x180005b4f  movups  [rsp+0B8h+var_40], xmm0
0x180005b54  test    rdx, rdx
0x180005b57  jz      short loc_180005BC0
0x180005b59  cmp     [rdx], r12b
0x180005b5c  jz      short loc_180005BC0
0x180005b5e  mov     rcx, rdx; String
0x180005b61  call    cs:__imp_atoi
0x180005b67  mov     rcx, [rsi]
0x180005b6a  lea     rdx, [rsp+0B8h+arg_8]
0x180005b72  mov     [rsp+0B8h+var_70], r12
0x180005b77  mov     r14d, eax
0x180005b7a  mov     [rsp+0B8h+var_78], r12
0x180005b7f  xor     r9d, r9d
0x180005b82  mov     [rsp+0B8h+var_80], r12
0x180005b87  xor     r8d, r8d
0x180005b8a  mov     rax, [rcx+0B8h]
0x180005b91  mov     rcx, rsi
0x180005b94  mov     [rsp+0B8h+var_88], r12
0x180005b99  mov     [rsp+0B8h+var_90], r12
0x180005b9e  mov     [rsp+0B8h+arg_8], r12w
0x180005ba7  mov     [rsp+0B8h+var_98], r12
0x180005bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb1  cmp     r14w, [rsp+0B8h+arg_8]
0x180005bba  jnz     loc_180005C72
0x180005bc0  test    ebx, ebx
0x180005bc2  jz      short loc_180005BE8
0x180005bc4  cmp     ebx, 2
0x180005bc7  jb      loc_180005D34
0x180005bcd  cmp     byte ptr [rbp+0], 0Dh
0x180005bd1  jnz     loc_180005D08
0x180005bd7  cmp     byte ptr [rbp+1], 0Ah
0x180005bdb  jnz     loc_180005D08
0x180005be1  mov     edi, 2
0x180005be6  jmp     short loc_180005C07
0x180005be8  xor     eax, eax
0x180005bea  jmp     short loc_180005C5B
0x180005bec  add     edi, 3
0x180005bef  cmp     edi, 2
0x180005bf2  jbe     short loc_180005C07
0x180005bf4  lea     r8d, [rdi-2]; unsigned int
0x180005bf8  mov     rdx, rbp; char *
0x180005bfb  mov     rcx, rsi; struct IHttpResponse *
0x180005bfe  call    ?SetHeaders@@YAJPEAVIHttpResponse@@PEADK@Z; SetHeaders(IHttpResponse *,char *,ulong)
0x180005c03  test    eax, eax
0x180005c05  js      short loc_180005C5B
0x180005c07  cmp     edi, ebx
0x180005c09  jnb     short loc_180005BE8
0x180005c0b  lea     rcx, [rsp+0B8h+var_58]
0x180005c10  mov     [rsp+0B8h+var_88], r12
0x180005c15  mov     [rsp+0B8h+var_90], rcx
0x180005c1a  lea     rdx, [rsp+0B8h+var_50]
0x180005c1f  mov     eax, edi
0x180005c21  sub     ebx, edi
0x180005c23  add     rax, rbp
0x180005c26  mov     dword ptr [rsp+0B8h+var_50], r12d
0x180005c2b  mov     qword ptr [rsp+0B8h+var_50+8], rax
0x180005c30  xor     r9d, r9d
0x180005c33  mov     rax, [rsi]
0x180005c36  mov     r8d, 1
0x180005c3c  mov     rcx, rsi
0x180005c3f  mov     dword ptr [rsp+0B8h+var_40], ebx
0x180005c43  mov     dword ptr [rsp+0B8h+var_98], 1
0x180005c4b  mov     rax, [rax+0A8h]
0x180005c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c57  test    eax, eax
0x180005c59  jns     short loc_180005BE8
0x180005c5b  mov     rbx, [rsp+0B8h+arg_10]
0x180005c63  add     rsp, 90h
0x180005c6a  pop     r14
0x180005c6c  pop     r12
0x180005c6e  pop     rdi
0x180005c6f  pop     rsi
0x180005c70  pop     rbp
0x180005c71  retn
0x180005c72  mov     ecx, 191h
0x180005c77  mov     [rsp+0B8h+arg_0], r15
0x180005c7f  cmp     r14w, cx
0x180005c83  mov     r15d, 4
0x180005c89  movzx   ecx, byte ptr [rdi]; C
0x180005c8c  cmovnz  r15w, r12w
0x180005c91  call    cs:__imp_isdigit
0x180005c97  test    eax, eax
0x180005c99  jz      short loc_180005CAC
0x180005c9b  movzx   ecx, byte ptr [rdi+1]; C
0x180005c9f  inc     rdi
0x180005ca2  call    cs:__imp_isdigit
0x180005ca8  test    eax, eax
0x180005caa  jnz     short loc_180005C9B
0x180005cac  movzx   ecx, byte ptr [rdi]; C
0x180005caf  call    cs:__imp_isspace
0x180005cb5  test    eax, eax
0x180005cb7  jz      short loc_180005CCA
0x180005cb9  movzx   ecx, byte ptr [rdi+1]; C
0x180005cbd  inc     rdi
0x180005cc0  call    cs:__imp_isspace
0x180005cc6  test    eax, eax
0x180005cc8  jnz     short loc_180005CB9
0x180005cca  mov     rax, [rsi]
0x180005ccd  movzx   r9d, r15w
0x180005cd1  mov     dword ptr [rsp+0B8h+var_88], r12d
0x180005cd6  mov     r8, rdi
0x180005cd9  mov     [rsp+0B8h+var_90], r12
0x180005cde  movzx   edx, r14w
0x180005ce2  mov     rcx, rsi
0x180005ce5  mov     dword ptr [rsp+0B8h+var_98], r12d
0x180005cea  mov     rax, [rax+18h]
0x180005cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cf3  mov     r15, [rsp+0B8h+arg_0]
0x180005cfb  test    eax, eax
0x180005cfd  js      loc_180005C5B
0x180005d03  jmp     loc_180005BC0
0x180005d08  mov     edi, r12d
0x180005d0b  lea     edx, [rbx-2]
0x180005d0e  cmp     edi, edx
0x180005d10  jnb     short loc_180005D34
0x180005d12  mov     eax, edi
0x180005d14  cmp     byte ptr [rax+rbp], 0Ah
0x180005d18  jnz     short loc_180005D30
0x180005d1a  lea     eax, [rdi+1]
0x180005d1d  cmp     byte ptr [rax+rbp], 0Dh
0x180005d21  jnz     short loc_180005D30
0x180005d23  lea     eax, [rdi+2]
0x180005d26  cmp     byte ptr [rax+rbp], 0Ah
0x180005d2a  jz      loc_180005BEC
0x180005d30  inc     edi
0x180005d32  jmp     short loc_180005D0E
0x180005d34  mov     eax, 80070057h
0x180005d39  jmp     loc_180005C5B
```
