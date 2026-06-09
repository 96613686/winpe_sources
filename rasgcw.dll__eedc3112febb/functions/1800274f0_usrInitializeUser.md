# usrInitializeUser

- ea: `0x1800274f0`
- end: `0x180027691`
- name: `usrInitializeUser`
- size: `417`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180026e6c`

## callees

- `0x180021438`
- `0x180021470`
- `0x180021c04`
- `0x1800274f0`
- `0x180027874`
- `0x18002c318`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `MPRAPI!MprAdminUserRead` at `0x1800275f2`
- `MPRAPI!MprAdminUserRead` at `0x1800275f2`
- `MPRAPI!MprAdminUserOpen` at `0x1800275dc`
- `MPRAPI!MprAdminUserOpen` at `0x1800275dc`

## pseudocode

```c
_BOOL8 __fastcall usrInitializeUser(STRSAFE_LPCWSTR *a1, __int64 a2)
{
  unsigned int v4; // edx
  char *v5; // rdi
  __int64 v6; // rax
  unsigned int v7; // ebp
  wchar_t *v8; // rax
  STRSAFE_LPWSTR *v9; // r9
  int v10; // ebx
  HRESULT v11; // eax
  unsigned int v12; // eax
  void *v13; // rcx
  size_t *v15; // [rsp+20h] [rbp-148h]
  _BYTE v16[2]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE v17[270]; // [rsp+32h] [rbp-136h] BYREF

  v16[1] = 0;
  memset_0(v16, 0, 0x103u);
  if ( a2 )
  {
    v4 = *(_DWORD *)(a2 + 12);
    if ( *(_DWORD *)(a2 + 8) < v4 || !(unsigned int)usrResizeCache(a2, v4 + 50) )
    {
      v5 = (char *)RassrvAlloc(800, 1);
      if ( v5 )
      {
        v6 = -1;
        do
          ++v6;
        while ( (*a1)[v6] );
        v7 = 2 * v6 + 2;
        v8 = (wchar_t *)RassrvAlloc(v7, 0);
        *((_QWORD *)v5 + 1) = v8;
        if ( !v8 )
        {
          v10 = 8;
          goto LABEL_18;
        }
        v11 = StringCchCopyExW(v8, (unsigned __int64)v7 >> 1, *a1, v9, v15, 0x100u);
        if ( v11 >= 0 )
        {
          v10 = MprAdminUserOpen(*(_QWORD *)a2, *((_QWORD *)v5 + 1), v5);
          if ( v10
            || (v10 = MprAdminUserRead(*(_QWORD *)v5, 0, v16)) != 0
            || (v5[797] = 0, (v10 = StringCchCopyWrapW(v5 + 538, 129, v17)) != 0) )
          {
LABEL_18:
            v13 = (void *)*((_QWORD *)v5 + 1);
            if ( v13 )
              RassrvFree(v13);
            RassrvFree(v5);
            return v10 == 0;
          }
          v5[796] = v16[0];
          v12 = *(_DWORD *)(a2 + 8);
          if ( v12 >= *(_DWORD *)(a2 + 12) )
          {
            v10 = 111;
            goto LABEL_18;
          }
          *(_QWORD *)(*(_QWORD *)(a2 + 40) + 8LL * v12) = v5;
          ++*(_DWORD *)(a2 + 8);
        }
        else
        {
          v10 = (unsigned __int16)v11;
          if ( (_WORD)v11 )
            goto LABEL_18;
        }
        return v10 == 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800274f0  mov     [rsp+arg_10], rbx
0x1800274f5  mov     [rsp+arg_18], rbp
0x1800274fa  push    rsi
0x1800274fb  push    rdi
0x1800274fc  push    r14
0x1800274fe  sub     rsp, 150h
0x180027505  mov     rax, cs:__security_cookie
0x18002750c  xor     rax, rsp
0x18002750f  mov     [rsp+168h+var_28], rax
0x180027517  mov     rsi, rdx
0x18002751a  mov     rbx, rcx
0x18002751d  xor     eax, eax
0x18002751f  lea     rcx, [rsp+168h+var_138]; void *
0x180027524  xor     edx, edx; Val
0x180027526  mov     [rsp+168h+var_137], al
0x18002752a  mov     r8d, 103h; Size
0x180027530  call    memset_0
0x180027535  xor     r14d, r14d
0x180027538  test    rsi, rsi
0x18002753b  jz      loc_180027667
0x180027541  mov     edx, [rsi+0Ch]
0x180027544  cmp     [rsi+8], edx
0x180027547  jb      short loc_18002755C
0x180027549  add     edx, 32h ; '2'
0x18002754c  mov     rcx, rsi
0x18002754f  call    usrResizeCache
0x180027554  test    eax, eax
0x180027556  jnz     loc_180027667
0x18002755c  mov     edx, 1
0x180027561  mov     ecx, 320h
0x180027566  call    RassrvAlloc
0x18002756b  mov     rdi, rax
0x18002756e  test    rax, rax
0x180027571  jz      loc_180027667
0x180027577  mov     rcx, [rbx]
0x18002757a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002757e  inc     rax
0x180027581  cmp     [rcx+rax*2], r14w
0x180027586  jnz     short loc_18002757E
0x180027588  lea     ebp, ds:2[rax*2]
0x18002758f  xor     edx, edx
0x180027591  mov     ecx, ebp
0x180027593  call    RassrvAlloc
0x180027598  mov     [rdi+8], rax
0x18002759c  test    rax, rax
0x18002759f  jnz     short loc_1800275A9
0x1800275a1  lea     ebx, [rax+8]
0x1800275a4  jmp     loc_180027647
0x1800275a9  mov     r8, [rbx]; pszSrc
0x1800275ac  mov     rcx, rax; pszDest
0x1800275af  mov     edx, ebp
0x1800275b1  shr     rdx, 1; cchDest
0x1800275b4  mov     [rsp+168h+dwFlags], 100h; dwFlags
0x1800275bc  call    StringCchCopyExW
0x1800275c1  test    eax, eax
0x1800275c3  jns     short loc_1800275D2
0x1800275c5  movzx   ebx, ax
0x1800275c8  test    ebx, ebx
0x1800275ca  jz      loc_18002765D
0x1800275d0  jmp     short loc_180027647
0x1800275d2  mov     rdx, [rdi+8]
0x1800275d6  mov     r8, rdi
0x1800275d9  mov     rcx, [rsi]
0x1800275dc  call    cs:__imp_MprAdminUserOpen
0x1800275e2  mov     ebx, eax
0x1800275e4  test    eax, eax
0x1800275e6  jnz     short loc_180027647
0x1800275e8  mov     rcx, [rdi]
0x1800275eb  lea     r8, [rsp+168h+var_138]
0x1800275f0  xor     edx, edx
0x1800275f2  call    cs:__imp_MprAdminUserRead
0x1800275f8  mov     ebx, eax
0x1800275fa  test    eax, eax
0x1800275fc  jnz     short loc_180027647
0x1800275fe  lea     rcx, [rdi+21Ah]
0x180027605  mov     [rdi+31Dh], r14b
0x18002760c  lea     r8, [rsp+168h+var_136]
0x180027611  mov     edx, 81h
0x180027616  call    StringCchCopyWrapW
0x18002761b  mov     ebx, eax
0x18002761d  test    eax, eax
0x18002761f  jnz     short loc_180027647
0x180027621  mov     al, [rsp+168h+var_138]
0x180027625  mov     [rdi+31Ch], al
0x18002762b  mov     eax, [rsi+8]
0x18002762e  cmp     eax, [rsi+0Ch]
0x180027631  jnb     short loc_180027642
0x180027633  mov     ecx, eax
0x180027635  mov     rax, [rsi+28h]
0x180027639  mov     [rax+rcx*8], rdi
0x18002763d  inc     dword ptr [rsi+8]
0x180027640  jmp     short loc_18002765D
0x180027642  mov     ebx, 6Fh ; 'o'
0x180027647  mov     rcx, [rdi+8]; lpMem
0x18002764b  test    rcx, rcx
0x18002764e  jz      short loc_180027655
0x180027650  call    RassrvFree
0x180027655  mov     rcx, rdi; lpMem
0x180027658  call    RassrvFree
0x18002765d  test    ebx, ebx
0x18002765f  mov     eax, r14d
0x180027662  setz    al
0x180027665  jmp     short loc_180027669
0x180027667  xor     eax, eax
0x180027669  mov     rcx, [rsp+168h+var_28]
0x180027671  xor     rcx, rsp; StackCookie
0x180027674  call    __security_check_cookie
0x180027679  lea     r11, [rsp+168h+var_18]
0x180027681  mov     rbx, [r11+30h]
0x180027685  mov     rbp, [r11+38h]
0x180027689  mov     rsp, r11
0x18002768c  pop     r14
0x18002768e  pop     rdi
0x18002768f  pop     rsi
0x180027690  retn
```
