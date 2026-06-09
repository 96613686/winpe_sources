# BstrRead(IStream *,ushort * *,tagSYSKIND)

- ea: `0x1800964a8`
- end: `0x18009668b`
- name: `?BstrRead@@YAJPEAUIStream@@PEAPEAGW4tagSYSKIND@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct IStream *, unsigned __int16 **, enum tagSYSKIND)`
- caller_count: `16`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18004a95c`
- `0x18004c418`
- `0x18007c640`
- `0x18007c950`
- `0x18007d2a0`
- `0x18007f090`
- `0x18007f4e0`
- `0x180080160`
- `0x1800844b8`
- `0x1800852f4`
- `0x180085524`
- `0x18008575c`
- `0x180096968`
- `0x180097064`
- `0x18009797c`
- `0x180097c08`

## callees

- `0x18000a6d0`
- `0x180021dc0`
- `0x18004d924`
- `0x18004dd00`
- `0x180076b60`
- `0x1800964a8`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800965d4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096608`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800965d4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096608`

## pseudocode

```c
__int64 __fastcall BstrRead(struct IStream *a1, unsigned __int16 **a2, enum tagSYSKIND a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IStream *, int *, __int64, int *); // rax
  int v8; // edi
  __int64 result; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  CHAR *v12; // rax
  CHAR *v13; // rsi
  __int64 v14; // rcx
  int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rcx
  unsigned __int16 *v18; // rbx
  unsigned __int16 *v19; // rbx
  __int64 v20; // rax
  int v21; // esi
  int cchWideChar; // [rsp+28h] [rbp-18h]
  LPWSTR lpWideCharStr[2]; // [rsp+30h] [rbp-10h] BYREF
  char v24; // [rsp+70h] [rbp+30h] BYREF
  int cbMultiByte; // [rsp+78h] [rbp+38h] BYREF
  int v26; // [rsp+88h] [rbp+48h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)a1;
  lpWideCharStr[0] = 0;
  v24 = 0;
  cbMultiByte = 0;
  v6 = *(__int64 (__fastcall **)(struct IStream *, int *, __int64, int *))(v3 + 24);
  v26 = 0;
  v8 = v6(a1, &cbMultiByte, 4, &v26);
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( v26 != 4 )
    return (unsigned int)-2147287010;
  if ( cbMultiByte )
  {
    if ( a3 )
    {
      v19 = SysAllocStringByteLen(0, cbMultiByte);
      if ( v19 )
      {
        v20 = *(_QWORD *)a1;
        v21 = cbMultiByte;
        v26 = 0;
        result = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, _QWORD, int *))(v20 + 24))(
                   a1,
                   v19,
                   (unsigned int)cbMultiByte,
                   &v26);
        v8 = result;
        if ( (int)result >= 0 )
        {
          if ( v21 == v26 )
          {
            *a2 = v19;
            return result;
          }
          v8 = -2147287010;
        }
        SysFreeString(v19);
        return (unsigned int)v8;
      }
    }
    else
    {
      v12 = (CHAR *)operator new[]((unsigned int)cbMultiByte);
      v13 = v12;
      if ( v12 )
      {
        v14 = *(_QWORD *)a1;
        v15 = cbMultiByte;
        v26 = 0;
        v8 = (*(__int64 (__fastcall **)(struct IStream *, CHAR *, _QWORD, int *))(v14 + 24))(
               a1,
               v12,
               (unsigned int)cbMultiByte,
               &v26);
        if ( v8 >= 0 )
        {
          if ( v15 == v26 )
          {
            v16 = (unsigned int)MultiByteToWideChar(0, 1u, v13, cbMultiByte, 0, 0);
            v8 = ErrSysAllocStringLen(v17, v16, lpWideCharStr);
            if ( v8 >= 0 )
            {
              cchWideChar = v16;
              v18 = lpWideCharStr[0];
              MultiByteToWideChar(0, 1u, v13, cbMultiByte, lpWideCharStr[0], cchWideChar);
              *a2 = v18;
            }
          }
          else
          {
            v8 = -2147287010;
          }
        }
        operator delete(v13);
        return (unsigned int)v8;
      }
    }
    return 2147942414LL;
  }
  v10 = *(_QWORD *)a1;
  v26 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64, int *))(v10 + 24))(a1, &v24, 1, &v26);
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( v26 != 1 )
    return (unsigned int)-2147287010;
  if ( v24 )
    return 0;
  else
    return ErrSysAllocStringLen(v11, 0, a2);
}

```

## disassembly

```asm
0x1800964a8  mov     [rsp-28h+arg_10], rbx
0x1800964ad  push    rbp
0x1800964ae  push    rsi
0x1800964af  push    rdi
0x1800964b0  push    r14
0x1800964b2  push    r15
0x1800964b4  mov     rbp, rsp
0x1800964b7  sub     rsp, 40h
0x1800964bb  mov     qword ptr [rdx], 0
0x1800964c2  lea     r9, [rbp+arg_18]
0x1800964c6  mov     rax, [rcx]
0x1800964c9  mov     ebx, r8d
0x1800964cc  mov     r15, rdx
0x1800964cf  mov     [rbp+var_10], 0
0x1800964d7  mov     r8d, 4
0x1800964dd  mov     [rbp+arg_0], 0
0x1800964e1  lea     rdx, [rbp+cbMultiByte]
0x1800964e5  mov     [rbp+cbMultiByte], 0
0x1800964ec  mov     rax, [rax+18h]
0x1800964f0  mov     r14, rcx
0x1800964f3  mov     [rbp+arg_18], 0
0x1800964fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800964ff  mov     edi, eax
0x180096501  test    eax, eax
0x180096503  js      short loc_180096510
0x180096505  cmp     [rbp+arg_18], 4
0x180096509  jz      short loc_180096517
0x18009650b  mov     edi, 8003001Eh
0x180096510  mov     eax, edi
0x180096512  jmp     loc_180096677
0x180096517  mov     edx, [rbp+cbMultiByte]; len
0x18009651a  test    edx, edx
0x18009651c  jnz     short loc_180096564
0x18009651e  mov     rax, [r14]
0x180096521  lea     r8d, [rdx+1]
0x180096525  mov     [rbp+arg_18], edx
0x180096528  lea     r9, [rbp+arg_18]
0x18009652c  lea     rdx, [rbp+arg_0]
0x180096530  mov     rcx, r14
0x180096533  mov     rax, [rax+18h]
0x180096537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009653c  mov     edi, eax
0x18009653e  test    eax, eax
0x180096540  js      short loc_180096510
0x180096542  cmp     [rbp+arg_18], 1
0x180096546  jnz     short loc_18009650B
0x180096548  cmp     [rbp+arg_0], 0
0x18009654c  jz      short loc_180096555
0x18009654e  xor     eax, eax
0x180096550  jmp     loc_180096677
0x180096555  mov     r8, r15
0x180096558  xor     edx, edx
0x18009655a  call    ErrSysAllocStringLen
0x18009655f  jmp     loc_180096677
0x180096564  test    ebx, ebx
0x180096566  jnz     loc_18009661E
0x18009656c  mov     rcx, rdx; unsigned __int64
0x18009656f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180096574  mov     rsi, rax
0x180096577  test    rax, rax
0x18009657a  jz      loc_18009662D
0x180096580  mov     rcx, [r14]
0x180096583  lea     r9, [rbp+arg_18]
0x180096587  mov     ebx, [rbp+cbMultiByte]
0x18009658a  mov     rdx, rsi
0x18009658d  mov     r8d, ebx
0x180096590  mov     [rbp+arg_18], 0
0x180096597  mov     rax, [rcx+18h]
0x18009659b  mov     rcx, r14
0x18009659e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800965a3  mov     edi, eax
0x1800965a5  test    eax, eax
0x1800965a7  js      short loc_180096611
0x1800965a9  cmp     ebx, [rbp+arg_18]
0x1800965ac  jz      short loc_1800965B5
0x1800965ae  mov     edi, 8003001Eh
0x1800965b3  jmp     short loc_180096611
0x1800965b5  mov     r9d, [rbp+cbMultiByte]; cbMultiByte
0x1800965b9  mov     r8, rsi; lpMultiByteStr
0x1800965bc  mov     [rsp+40h+cchWideChar], 0; cchWideChar
0x1800965c4  mov     edx, 1; dwFlags
0x1800965c9  xor     ecx, ecx; CodePage
0x1800965cb  mov     [rsp+40h+lpWideCharStr], 0; lpWideCharStr
0x1800965d4  call    cs:__imp_MultiByteToWideChar
0x1800965da  mov     edx, eax
0x1800965dc  lea     r8, [rbp+var_10]
0x1800965e0  mov     ebx, eax
0x1800965e2  call    ErrSysAllocStringLen
0x1800965e7  mov     edi, eax
0x1800965e9  test    eax, eax
0x1800965eb  js      short loc_180096611
0x1800965ed  mov     r9d, [rbp+cbMultiByte]; cbMultiByte
0x1800965f1  mov     r8, rsi; lpMultiByteStr
0x1800965f4  mov     [rsp+40h+cchWideChar], ebx; cchWideChar
0x1800965f8  mov     edx, 1; dwFlags
0x1800965fd  mov     rbx, [rbp+var_10]
0x180096601  xor     ecx, ecx; CodePage
0x180096603  mov     [rsp+40h+lpWideCharStr], rbx; lpWideCharStr
0x180096608  call    cs:__imp_MultiByteToWideChar
0x18009660e  mov     [r15], rbx
0x180096611  mov     rcx, rsi; void *
0x180096614  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180096619  jmp     loc_180096510
0x18009661e  xor     ecx, ecx; psz
0x180096620  call    SysAllocStringByteLen
0x180096625  mov     rbx, rax
0x180096628  test    rax, rax
0x18009662b  jnz     short loc_180096634
0x18009662d  mov     eax, 8007000Eh
0x180096632  jmp     short loc_180096677
0x180096634  mov     rax, [r14]
0x180096637  lea     r9, [rbp+arg_18]
0x18009663b  mov     esi, [rbp+cbMultiByte]
0x18009663e  mov     rdx, rbx
0x180096641  mov     r8d, esi
0x180096644  mov     [rbp+arg_18], 0
0x18009664b  mov     rcx, r14
0x18009664e  mov     rax, [rax+18h]
0x180096652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096657  mov     edi, eax
0x180096659  test    eax, eax
0x18009665b  js      short loc_180096667
0x18009665d  cmp     esi, [rbp+arg_18]
0x180096660  jz      short loc_180096674
0x180096662  mov     edi, 8003001Eh
0x180096667  mov     rcx, rbx; bstrString
0x18009666a  call    SysFreeString
0x18009666f  jmp     loc_180096510
0x180096674  mov     [r15], rbx
0x180096677  mov     rbx, [rsp+40h+arg_10]
0x18009667f  add     rsp, 40h
0x180096683  pop     r15
0x180096685  pop     r14
0x180096687  pop     rdi
0x180096688  pop     rsi
0x180096689  pop     rbp
0x18009668a  retn
```
