# ProcessCommandLine

- ea: `0x180002180`
- end: `0x1800024f7`
- name: `ProcessCommandLine`
- size: `887`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002180`
- `0x180002500`
- `0x1800026e0`
- `0x180003010`

## import_xrefs

- `msvcrt!wcschr` at `0x18000230f`
- `msvcrt!wcschr` at `0x18000230f`
- `msvcrt!iswspace` at `0x1800021e3`
- `msvcrt!iswspace` at `0x180002347`
- `msvcrt!iswspace` at `0x180002438`
- `msvcrt!iswspace` at `0x1800021e3`
- `msvcrt!iswspace` at `0x180002347`
- `msvcrt!iswspace` at `0x180002438`

## pseudocode

```c
__int64 __fastcall ProcessCommandLine(
        __int64 a1,
        int a2,
        __int64 (__fastcall *a3)(_BYTE *, __int64),
        wint_t *a4,
        __int64 a5,
        int a6)
{
  wint_t *v6; // rdi
  unsigned int v10; // ebx
  wint_t v11; // ax
  wchar_t v12; // dx
  wint_t *v13; // rcx
  wint_t v14; // dx
  wint_t *v15; // r8
  wint_t *v16; // rax
  unsigned __int64 v18; // rax
  __int64 v19; // rdx
  _WORD *v20; // r8
  _WORD *v21; // rcx
  bool v22; // zf
  wint_t *v23; // rdi
  wint_t v24; // ax
  wint_t *v25; // rsi
  wint_t *v26; // rcx
  wint_t *v27; // rbx
  unsigned __int64 v28; // rbx
  __int64 v29; // rdx
  _WORD *v30; // rax
  _WORD *v31; // rcx
  wint_t v32; // ax
  wint_t *v33; // rsi
  wint_t *v34; // rbp
  wint_t *v35; // rcx
  wint_t *v36; // rbx
  unsigned __int64 v37; // rbx
  __int64 v38; // rdx
  _WORD *v39; // rax
  _WORD *v40; // rcx
  wint_t *v41; // [rsp+30h] [rbp-268h] BYREF
  _BYTE v42[528]; // [rsp+40h] [rbp-258h] BYREF

  v6 = a4;
  if ( a1 && a2 > 0 && a4 )
  {
    v11 = *a4;
    v10 = 0;
    while ( v11 )
    {
      do
      {
        if ( !iswspace(v11) )
          break;
        v11 = *++v6;
      }
      while ( *v6 );
      v12 = *v6;
      if ( *v6 )
      {
        if ( v12 == 34 )
        {
          v13 = ++v6;
          v14 = *v6;
          if ( !*v6 )
            return (unsigned int)-2147467259;
          v15 = v6;
          v16 = v6;
          while ( v14 != 34 )
          {
            v6 = v15 + 1;
            v14 = v15[1];
            v15 = v6;
            v16 = v6;
            if ( !v14 )
              return (unsigned int)-2147467259;
          }
          v18 = v16 - v13;
          if ( v18 > 0x7FFFFFFE )
            return (unsigned int)-2147024809;
          v19 = 260;
          v20 = v42;
          do
          {
            if ( !v18 )
              break;
            if ( !*v13 )
              break;
            *v20++ = *v13++;
            --v18;
            --v19;
          }
          while ( v19 );
          v21 = v20 - 1;
          if ( v19 )
            v21 = v20;
          v10 = v19 == 0 ? 0x8007007A : 0;
          *v21 = 0;
          if ( !v19 )
            return v10;
          v10 = a3(v42, a5);
          if ( (v10 & 0x80000000) != 0 )
            return v10;
          if ( *v6 )
            ++v6;
        }
        else if ( wcschr(L"/-", v12) )
        {
          v22 = v6 + 1 == 0;
          v23 = v6 + 1;
          v41 = v23;
          if ( v22 )
            return (unsigned int)-2147467259;
          v24 = *v23;
          if ( *v23 )
          {
            v25 = v23;
            v26 = v23;
            do
            {
              v27 = v26;
              if ( iswspace(v24) )
                break;
              v41 = ++v25;
              v26 = v25;
              v27 = v25;
              v24 = *v25;
            }
            while ( *v25 );
          }
          else
          {
            v27 = v23;
          }
          v28 = v27 - v23;
          if ( v28 > 0x7FFFFFFE )
            return (unsigned int)-2147024809;
          v29 = 260;
          v30 = v42;
          do
          {
            if ( !v28 )
              break;
            if ( !*v23 )
              break;
            *v30++ = *v23++;
            --v28;
            --v29;
          }
          while ( v29 );
          v31 = v30 - 1;
          if ( v29 )
            v31 = v30;
          *v31 = 0;
          v10 = v29 == 0 ? 0x8007007A : 0;
          if ( !v29 )
            return v10;
          v10 = ProcessCommandLineOption(a1, (unsigned int)a2, v42, a5, a6, &v41);
          if ( (v10 & 0x80000000) != 0 )
            return v10;
          v6 = v41;
        }
        else
        {
          if ( !a3 )
            return (unsigned int)-2147467259;
          v32 = *v6;
          v33 = v6;
          if ( *v6 )
          {
            v34 = v6;
            v35 = v6;
            do
            {
              v36 = v35;
              if ( iswspace(v32) )
                break;
              v6 = v34 + 1;
              v32 = v34[1];
              v34 = v6;
              v35 = v6;
              v36 = v6;
            }
            while ( v32 );
          }
          else
          {
            v36 = v6;
          }
          v37 = v36 - v33;
          if ( v37 > 0x7FFFFFFE )
            return (unsigned int)-2147024809;
          v38 = 260;
          v39 = v42;
          do
          {
            if ( !v37 )
              break;
            if ( !*v33 )
              break;
            *v39++ = *v33++;
            --v37;
            --v38;
          }
          while ( v38 );
          v40 = v39 - 1;
          if ( v38 )
            v40 = v39;
          *v40 = 0;
          v10 = v38 == 0 ? 0x8007007A : 0;
          if ( !v38 )
            return v10;
          v10 = a3(v42, a5);
          if ( (v10 & 0x80000000) != 0 )
            return v10;
        }
      }
      v11 = *v6;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x180002180  mov     [rsp+arg_8], rbx
0x180002185  push    rbp
0x180002186  push    rsi
0x180002187  push    rdi
0x180002188  push    r12
0x18000218a  push    r13
0x18000218c  push    r14
0x18000218e  push    r15
0x180002190  sub     rsp, 260h
0x180002197  mov     rax, cs:__security_cookie
0x18000219e  xor     rax, rsp
0x1800021a1  mov     [rsp+298h+var_48], rax
0x1800021a9  mov     r12, [rsp+298h+arg_20]
0x1800021b1  xor     ebp, ebp
0x1800021b3  mov     rdi, r9
0x1800021b6  mov     r14, r8
0x1800021b9  mov     r15d, edx
0x1800021bc  mov     r13, rcx
0x1800021bf  test    rcx, rcx
0x1800021c2  jnz     short loc_1800021CB
0x1800021c4  mov     ebx, 80070057h
0x1800021c9  jmp     short loc_180002247
0x1800021cb  test    r15d, r15d
0x1800021ce  jle     short loc_1800021C4
0x1800021d0  test    r9, r9
0x1800021d3  jz      short loc_1800021C4
0x1800021d5  movzx   eax, word ptr [r9]
0x1800021d9  mov     ebx, ebp
0x1800021db  jmp     loc_1800024E1
0x1800021e0  movzx   ecx, ax; C
0x1800021e3  call    cs:__imp_iswspace
0x1800021ea  nop     dword ptr [rax+rax+00h]
0x1800021ef  test    eax, eax
0x1800021f1  jz      short loc_1800021FF
0x1800021f3  add     rdi, 2
0x1800021f7  movzx   eax, word ptr [rdi]
0x1800021fa  test    ax, ax
0x1800021fd  jnz     short loc_1800021E0
0x1800021ff  movzx   edx, word ptr [rdi]; Ch
0x180002202  test    dx, dx
0x180002205  jz      loc_1800024DE
0x18000220b  cmp     dx, 22h ; '"'
0x18000220f  jnz     loc_180002308
0x180002215  add     rdi, 2
0x180002219  mov     rcx, rdi
0x18000221c  movzx   edx, word ptr [rdi]
0x18000221f  test    dx, dx
0x180002222  jz      short loc_180002242
0x180002224  mov     r8, rcx
0x180002227  mov     rax, rcx
0x18000222a  cmp     dx, 22h ; '"'
0x18000222e  jz      short loc_180002275
0x180002230  lea     rdi, [r8+2]
0x180002234  movzx   edx, word ptr [rdi]
0x180002237  mov     r8, rdi
0x18000223a  mov     rax, rdi
0x18000223d  test    dx, dx
0x180002240  jnz     short loc_18000222A
0x180002242  mov     ebx, 80004005h
0x180002247  mov     eax, ebx
0x180002249  mov     rcx, [rsp+298h+var_48]
0x180002251  xor     rcx, rsp; StackCookie
0x180002254  call    __security_check_cookie
0x180002259  mov     rbx, [rsp+298h+arg_8]
0x180002261  add     rsp, 260h
0x180002268  pop     r15
0x18000226a  pop     r14
0x18000226c  pop     r13
0x18000226e  pop     r12
0x180002270  pop     rdi
0x180002271  pop     rsi
0x180002272  pop     rbp
0x180002273  retn
0x180002275  sub     rax, rcx
0x180002278  sar     rax, 1
0x18000227b  cmp     rax, 7FFFFFFEh
0x180002281  ja      loc_1800021C4
0x180002287  mov     edx, 104h
0x18000228c  lea     r8, [rsp+298h+var_258]
0x180002291  test    rax, rax
0x180002294  jz      short loc_1800022B5
0x180002296  movzx   r9d, word ptr [rcx]
0x18000229a  test    r9w, r9w
0x18000229e  jz      short loc_1800022B5
0x1800022a0  mov     [r8], r9w
0x1800022a4  add     rcx, 2
0x1800022a8  add     r8, 2
0x1800022ac  dec     rax
0x1800022af  sub     rdx, 1
0x1800022b3  jnz     short loc_180002291
0x1800022b5  test    rdx, rdx
0x1800022b8  lea     rcx, [r8-2]
0x1800022bc  mov     rax, rdx
0x1800022bf  cmovnz  rcx, r8
0x1800022c3  neg     rax
0x1800022c6  sbb     ebx, ebx
0x1800022c8  not     ebx
0x1800022ca  and     ebx, 8007007Ah
0x1800022d0  mov     [rcx], bp
0x1800022d3  test    rdx, rdx
0x1800022d6  jz      loc_180002247
0x1800022dc  mov     rdx, r12
0x1800022df  lea     rcx, [rsp+298h+var_258]
0x1800022e4  mov     rax, r14
0x1800022e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ec  mov     ebx, eax
0x1800022ee  test    eax, eax
0x1800022f0  js      loc_180002247
0x1800022f6  cmp     [rdi], bp
0x1800022f9  jz      loc_1800024DE
0x1800022ff  add     rdi, 2
0x180002303  jmp     loc_1800024DE
0x180002308  lea     rcx, Str; "/-"
0x18000230f  call    cs:__imp_wcschr
0x180002316  nop     dword ptr [rax+rax+00h]
0x18000231b  test    rax, rax
0x18000231e  jz      loc_180002414
0x180002324  add     rdi, 2
0x180002328  mov     [rsp+298h+var_268], rdi
0x18000232d  jz      loc_180002242
0x180002333  movzx   eax, word ptr [rdi]
0x180002336  test    ax, ax
0x180002339  jz      short loc_180002370
0x18000233b  mov     rsi, rdi
0x18000233e  mov     rcx, rdi
0x180002341  mov     rbx, rcx
0x180002344  movzx   ecx, ax; C
0x180002347  call    cs:__imp_iswspace
0x18000234e  nop     dword ptr [rax+rax+00h]
0x180002353  test    eax, eax
0x180002355  jnz     short loc_180002373
0x180002357  add     rsi, 2
0x18000235b  mov     [rsp+298h+var_268], rsi
0x180002360  mov     rcx, rsi
0x180002363  mov     rbx, rsi
0x180002366  movzx   eax, word ptr [rsi]
0x180002369  test    ax, ax
0x18000236c  jnz     short loc_180002341
0x18000236e  jmp     short loc_180002373
0x180002370  mov     rbx, rdi
0x180002373  sub     rbx, rdi
0x180002376  sar     rbx, 1
0x180002379  cmp     rbx, 7FFFFFFEh
0x180002380  ja      loc_1800021C4
0x180002386  mov     edx, 104h
0x18000238b  lea     rax, [rsp+298h+var_258]
0x180002390  test    rbx, rbx
0x180002393  jz      short loc_1800023B1
0x180002395  movzx   ecx, word ptr [rdi]
0x180002398  test    cx, cx
0x18000239b  jz      short loc_1800023B1
0x18000239d  mov     [rax], cx
0x1800023a0  add     rdi, 2
0x1800023a4  add     rax, 2
0x1800023a8  dec     rbx
0x1800023ab  sub     rdx, 1
0x1800023af  jnz     short loc_180002390
0x1800023b1  test    rdx, rdx
0x1800023b4  lea     rcx, [rax-2]
0x1800023b8  cmovnz  rcx, rax
0x1800023bc  mov     rax, rdx
0x1800023bf  neg     rax
0x1800023c2  sbb     ebx, ebx
0x1800023c4  not     ebx
0x1800023c6  mov     [rcx], bp
0x1800023c9  and     ebx, 8007007Ah
0x1800023cf  test    rdx, rdx
0x1800023d2  jz      loc_180002247
0x1800023d8  lea     rax, [rsp+298h+var_268]
0x1800023dd  mov     r9, r12
0x1800023e0  mov     [rsp+298h+var_270], rax
0x1800023e5  lea     r8, [rsp+298h+var_258]
0x1800023ea  mov     eax, [rsp+298h+arg_28]
0x1800023f1  mov     edx, r15d
0x1800023f4  mov     rcx, r13
0x1800023f7  mov     [rsp+298h+var_278], eax
0x1800023fb  call    ProcessCommandLineOption
0x180002400  mov     ebx, eax
0x180002402  test    eax, eax
0x180002404  js      loc_180002247
0x18000240a  mov     rdi, [rsp+298h+var_268]
0x18000240f  jmp     loc_1800024DE
0x180002414  test    r14, r14
0x180002417  jz      loc_180002242
0x18000241d  movzx   eax, word ptr [rdi]
0x180002420  mov     rsi, rdi
0x180002423  test    ax, ax
0x180002426  jz      loc_1800024EF
0x18000242c  mov     rbp, rdi
0x18000242f  mov     rcx, rdi
0x180002432  mov     rbx, rcx
0x180002435  movzx   ecx, ax; C
0x180002438  call    cs:__imp_iswspace
0x18000243f  nop     dword ptr [rax+rax+00h]
0x180002444  test    eax, eax
0x180002446  jnz     short loc_18000245D
0x180002448  lea     rdi, [rbp+2]
0x18000244c  movzx   eax, word ptr [rdi]
0x18000244f  mov     rbp, rdi
0x180002452  mov     rcx, rdi
0x180002455  mov     rbx, rdi
0x180002458  test    ax, ax
0x18000245b  jnz     short loc_180002432
0x18000245d  xor     ebp, ebp
0x18000245f  sub     rbx, rsi
0x180002462  sar     rbx, 1
0x180002465  cmp     rbx, 7FFFFFFEh
0x18000246c  ja      loc_1800021C4
0x180002472  mov     edx, 104h
0x180002477  lea     rax, [rsp+298h+var_258]
0x18000247c  test    rbx, rbx
0x18000247f  jz      short loc_18000249D
0x180002481  movzx   ecx, word ptr [rsi]
0x180002484  test    cx, cx
0x180002487  jz      short loc_18000249D
0x180002489  mov     [rax], cx
0x18000248c  add     rsi, 2
0x180002490  add     rax, 2
0x180002494  dec     rbx
0x180002497  sub     rdx, 1
0x18000249b  jnz     short loc_18000247C
0x18000249d  test    rdx, rdx
0x1800024a0  lea     rcx, [rax-2]
0x1800024a4  cmovnz  rcx, rax
0x1800024a8  mov     rax, rdx
0x1800024ab  neg     rax
0x1800024ae  sbb     ebx, ebx
0x1800024b0  not     ebx
0x1800024b2  mov     [rcx], bp
0x1800024b5  and     ebx, 8007007Ah
0x1800024bb  test    rdx, rdx
0x1800024be  jz      loc_180002247
0x1800024c4  mov     rdx, r12
0x1800024c7  lea     rcx, [rsp+298h+var_258]
0x1800024cc  mov     rax, r14
0x1800024cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d4  mov     ebx, eax
0x1800024d6  test    eax, eax
0x1800024d8  js      loc_180002247
0x1800024de  movzx   eax, word ptr [rdi]
0x1800024e1  test    ax, ax
0x1800024e4  jnz     loc_1800021E0
0x1800024ea  jmp     loc_180002247
0x1800024ef  mov     rbx, rsi
0x1800024f2  jmp     loc_18000245F
```
