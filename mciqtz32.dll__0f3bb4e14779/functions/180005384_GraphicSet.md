# GraphicSet

- ea: `0x180005384`
- end: `0x18000562e`
- name: `GraphicSet`
- size: `682`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180001e7c`
- `0x1800023d4`
- `0x180005384`
- `0x180007010`

## pseudocode

```c
int __fastcall GraphicSet(struct _MCIGRAPHIC *a1, int a2, _DWORD *a3)
{
  __int16 v4; // bx
  int v6; // esi
  const GUID *v7; // r14
  int v8; // eax
  __int64 v9; // rcx
  int result; // eax
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // rax
  void (*v16)(void); // rax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // ecx
  int v21; // ecx
  int v22; // [rsp+58h] [rbp+10h] BYREF

  v4 = a2;
  if ( (a2 & 0x80000) != 0 )
    return 274;
  if ( (a2 & 0x40000) != 0 )
    return 274;
  v6 = a2 & 0x31C00;
  if ( (a2 & 0x31C00) == 0 )
    return 274;
  v7 = 0;
  if ( (a2 & 0x400) == 0 )
    goto LABEL_15;
  v8 = a3[2];
  if ( !v8 )
  {
    if ( *((_QWORD *)a1 + 18) )
    {
      v7 = &TIME_FORMAT_MEDIA_TIME;
      goto LABEL_13;
    }
    return 274;
  }
  if ( v8 == 3 )
  {
    if ( *((double *)a1 + 73) != 0.0 )
    {
      v7 = &TIME_FORMAT_FRAME;
      goto LABEL_13;
    }
    return 274;
  }
  if ( v8 != 8 )
    return 274;
  v7 = &TIME_FORMAT_BYTE;
LABEL_13:
  v9 = *((_QWORD *)a1 + 18);
  if ( !v9 || (*(unsigned int (__fastcall **)(__int64, const GUID *))(*(_QWORD *)v9 + 40LL))(v9, v7) )
    return 274;
LABEL_15:
  if ( (v6 & 0x20000) != 0 && a3[5] > 0x186A0u )
    return 282;
  v11 = v4 & 0x6020;
  if ( (v11 & 0x6000) != 0 )
  {
    if ( (v11 & 0x6000) == 0x6000 || (v6 & 0x20400) != 0 )
      return 284;
  }
  else if ( (v6 & 0x11800) != 0 )
  {
    return 273;
  }
  if ( (v11 & 0x20) != 0 )
    return 0;
  if ( (v6 & 0x400) != 0 )
  {
    v12 = a3[2];
    if ( *((_DWORD *)a1 + 15) != v12 )
    {
      v13 = *((_QWORD *)a1 + 16);
      *((_DWORD *)a1 + 15) = v12;
      v22 = 0;
      (*(void (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v13 + 56LL))(v13, 0, &v22);
      if ( v22 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 72LL))(*((_QWORD *)a1 + 19));
      v14 = (*(__int64 (__fastcall **)(_QWORD, const GUID *))(**((_QWORD **)a1 + 18) + 72LL))(*((_QWORD *)a1 + 18), v7);
      if ( v22 )
      {
        v15 = **((_QWORD **)a1 + 19);
        if ( v22 == 1 )
          v16 = *(void (**)(void))(v15 + 64);
        else
          v16 = *(void (**)(void))(v15 + 56);
        v16();
      }
      if ( v14 < 0 )
        return 274;
    }
  }
  result = 0;
  if ( (v6 & 0x20000) == 0 )
    goto LABEL_43;
  v17 = *((_DWORD *)a1 + 53);
  if ( a3[5] )
  {
    if ( v17 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 14) + 80LL))(*((_QWORD *)a1 + 14));
      *((_DWORD *)a1 + 53) = 0;
    }
  }
  else if ( !v17 )
  {
    v18 = *((_QWORD *)a1 + 16);
    *((_DWORD *)a1 + 53) = 1;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 64LL))(v18, 0);
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 18) + 136LL))(*((_QWORD *)a1 + 18));
  result = CheckResult(v19);
  if ( !result )
  {
LABEL_43:
    if ( (v6 & 0x800) != 0 )
    {
      v20 = a3[3];
      if ( !v20 )
        return DeviceMute(a1, v11);
      v21 = v20 - 1;
      if ( !v21 )
      {
        v11 |= 0x200000u;
        return DeviceMute(a1, v11);
      }
      if ( v21 == 1 )
      {
        v11 |= 0x400000u;
        return DeviceMute(a1, v11);
      }
      return 274;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005384  mov     [rsp+arg_0], rbx
0x180005389  mov     [rsp+arg_10], rbp
0x18000538e  push    rsi
0x18000538f  push    rdi
0x180005390  push    r12
0x180005392  push    r14
0x180005394  push    r15
0x180005396  sub     rsp, 20h
0x18000539a  mov     rbp, r8
0x18000539d  mov     ebx, edx
0x18000539f  mov     rdi, rcx
0x1800053a2  bt      edx, 13h
0x1800053a6  jb      loc_180005612
0x1800053ac  bt      edx, 12h
0x1800053b0  jb      loc_180005612
0x1800053b6  mov     esi, edx
0x1800053b8  and     esi, 31C00h
0x1800053be  jz      loc_180005612
0x1800053c4  xor     r14d, r14d
0x1800053c7  mov     r15d, esi
0x1800053ca  and     r15d, 400h
0x1800053d1  jz      short loc_18000544E
0x1800053d3  mov     eax, [r8+8]
0x1800053d7  test    eax, eax
0x1800053d9  jz      short loc_180005413
0x1800053db  cmp     eax, 3
0x1800053de  jz      short loc_1800053F2
0x1800053e0  cmp     eax, 8
0x1800053e3  jnz     loc_180005612
0x1800053e9  lea     r14, TIME_FORMAT_BYTE
0x1800053f0  jmp     short loc_180005427
0x1800053f2  movsd   xmm0, qword ptr [rcx+248h]
0x1800053fa  ucomisd xmm0, cs:__real@0000000000000000
0x180005402  jp      short loc_18000540A
0x180005404  jz      loc_180005612
0x18000540a  lea     r14, TIME_FORMAT_FRAME
0x180005411  jmp     short loc_180005427
0x180005413  cmp     [rcx+90h], r14
0x18000541a  jz      loc_180005612
0x180005420  lea     r14, TIME_FORMAT_MEDIA_TIME
0x180005427  mov     rcx, [rcx+90h]
0x18000542e  test    rcx, rcx
0x180005431  jz      loc_180005612
0x180005437  mov     rax, [rcx]
0x18000543a  mov     rdx, r14
0x18000543d  mov     rax, [rax+28h]
0x180005441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005446  test    eax, eax
0x180005448  jnz     loc_180005612
0x18000544e  mov     r12d, esi
0x180005451  and     r12d, 20000h
0x180005458  jz      short loc_18000546D
0x18000545a  cmp     dword ptr [rbp+14h], 186A0h
0x180005461  jbe     short loc_18000546D
0x180005463  mov     eax, 11Ah
0x180005468  jmp     loc_180005617
0x18000546d  and     ebx, 6020h
0x180005473  mov     ecx, 6000h
0x180005478  mov     eax, ebx
0x18000547a  and     eax, ecx
0x18000547c  jz      short loc_180005494
0x18000547e  cmp     eax, ecx
0x180005480  jz      short loc_18000548A
0x180005482  test    esi, 20400h
0x180005488  jz      short loc_1800054A6
0x18000548a  mov     eax, 11Ch
0x18000548f  jmp     loc_180005617
0x180005494  test    esi, 11800h
0x18000549a  jz      short loc_1800054A6
0x18000549c  mov     eax, 111h
0x1800054a1  jmp     loc_180005617
0x1800054a6  test    bl, 20h
0x1800054a9  jz      short loc_1800054B2
0x1800054ab  xor     eax, eax
0x1800054ad  jmp     loc_180005617
0x1800054b2  test    r15d, r15d
0x1800054b5  jz      loc_18000554E
0x1800054bb  mov     eax, [rbp+8]
0x1800054be  cmp     [rdi+3Ch], eax
0x1800054c1  jz      loc_18000554E
0x1800054c7  mov     rcx, [rdi+80h]
0x1800054ce  lea     r8, [rsp+48h+arg_8]
0x1800054d3  mov     [rdi+3Ch], eax
0x1800054d6  xor     edx, edx
0x1800054d8  mov     [rsp+48h+arg_8], 0
0x1800054e0  mov     rax, [rcx]
0x1800054e3  mov     rax, [rax+38h]
0x1800054e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ec  cmp     [rsp+48h+arg_8], 0
0x1800054f1  jz      short loc_180005506
0x1800054f3  mov     rcx, [rdi+98h]
0x1800054fa  mov     rax, [rcx]
0x1800054fd  mov     rax, [rax+48h]
0x180005501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005506  mov     rcx, [rdi+90h]
0x18000550d  mov     rdx, r14
0x180005510  mov     rax, [rcx]
0x180005513  mov     rax, [rax+48h]
0x180005517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551c  mov     edx, [rsp+48h+arg_8]
0x180005520  mov     r14d, eax
0x180005523  test    edx, edx
0x180005525  jz      short loc_180005545
0x180005527  mov     rcx, [rdi+98h]
0x18000552e  mov     rax, [rcx]
0x180005531  cmp     edx, 1
0x180005534  jnz     short loc_18000553C
0x180005536  mov     rax, [rax+40h]
0x18000553a  jmp     short loc_180005540
0x18000553c  mov     rax, [rax+38h]
0x180005540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005545  test    r14d, r14d
0x180005548  js      loc_180005612
0x18000554e  xor     eax, eax
0x180005550  test    r12d, r12d
0x180005553  jz      loc_1800055E5
0x180005559  mov     r14d, [rbp+14h]
0x18000555d  mov     eax, [rdi+0D4h]
0x180005563  test    r14d, r14d
0x180005566  jnz     short loc_180005593
0x180005568  mov     r14d, 3E8h
0x18000556e  test    eax, eax
0x180005570  jnz     short loc_1800055B1
0x180005572  mov     rcx, [rdi+80h]
0x180005579  xor     edx, edx
0x18000557b  mov     dword ptr [rdi+0D4h], 1
0x180005585  mov     rax, [rcx]
0x180005588  mov     rax, [rax+40h]
0x18000558c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005591  jmp     short loc_1800055B1
0x180005593  test    eax, eax
0x180005595  jz      short loc_1800055B1
0x180005597  mov     rcx, [rdi+70h]
0x18000559b  mov     rax, [rcx]
0x18000559e  mov     rax, [rax+50h]
0x1800055a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a7  mov     dword ptr [rdi+0D4h], 0
0x1800055b1  mov     rcx, [rdi+90h]
0x1800055b8  xorps   xmm1, xmm1
0x1800055bb  mov     eax, r14d
0x1800055be  mov     rdx, [rcx]
0x1800055c1  cvtsi2sd xmm1, rax
0x1800055c6  mov     rax, [rdx+88h]
0x1800055cd  divsd   xmm1, cs:__real@408f400000000000
0x1800055d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055da  mov     ecx, eax; int
0x1800055dc  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x1800055e1  test    eax, eax
0x1800055e3  jnz     short loc_180005617
0x1800055e5  bt      esi, 0Bh
0x1800055e9  jnb     short loc_180005617
0x1800055eb  mov     ecx, [rbp+0Ch]
0x1800055ee  test    ecx, ecx
0x1800055f0  jz      short loc_180005606
0x1800055f2  sub     ecx, 1
0x1800055f5  jz      short loc_180005602
0x1800055f7  cmp     ecx, 1
0x1800055fa  jnz     short loc_180005612
0x1800055fc  bts     ebx, 16h
0x180005600  jmp     short loc_180005606
0x180005602  bts     ebx, 15h
0x180005606  mov     edx, ebx; unsigned int
0x180005608  mov     rcx, rdi; struct _MCIGRAPHIC *
0x18000560b  call    ?DeviceMute@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceMute(_MCIGRAPHIC *,ulong)
0x180005610  jmp     short loc_180005617
0x180005612  mov     eax, 112h
0x180005617  mov     rbx, [rsp+48h+arg_0]
0x18000561c  mov     rbp, [rsp+48h+arg_10]
0x180005621  add     rsp, 20h
0x180005625  pop     r15
0x180005627  pop     r14
0x180005629  pop     r12
0x18000562b  pop     rdi
0x18000562c  pop     rsi
0x18000562d  retn
```
