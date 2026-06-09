# CSecConLib::StatusWServEx(bool,ushort const *,ushort const *)

- ea: `0x1800103ac`
- end: `0x18001056a`
- name: `?StatusWServEx@CSecConLib@@AEAAJ_NPEBG1@Z`
- size: `446`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800092e0`
- `0x180009440`
- `0x18000ee40`

## callees

- `0x180001048`
- `0x180001054`
- `0x180001988`
- `0x18000f02c`
- `0x18001011c`
- `0x1800103ac`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180010475`
- `msvcrt!wcscpy_s` at `0x180010475`

## pseudocode

```c
__int64 __fastcall CSecConLib::StatusWServEx(CSecConLib *this, char a2, char *a3, const unsigned __int16 *a4)
{
  int MultiSZPropVal; // ebx
  wchar_t *v6; // rbx
  unsigned __int16 *v7; // rdi
  unsigned int v8; // r12d
  char v9; // si
  wchar_t *v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // r15
  wchar_t *v13; // rax
  wchar_t *v14; // r14
  wchar_t **v15; // r8
  wchar_t *v16; // rax
  wchar_t **v17; // r8
  int v18; // ebp
  char *v19; // r8
  int v20; // ecx
  int v21; // edx
  unsigned int v23; // [rsp+30h] [rbp-48h] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-40h] BYREF

  Source = 0;
  v23 = 0;
  MultiSZPropVal = CSecConLib::GetMultiSZPropVal(this, a4, 0x878u, &Source, &v23);
  if ( MultiSZPropVal >= 0 )
  {
    v6 = Source;
    if ( Source )
    {
      v7 = Source;
      if ( *Source )
      {
        v8 = v23;
        v9 = 0;
        v10 = Source;
        Source += v23 - 1;
        do
        {
          v11 = -1;
          do
            ++v11;
          while ( v10[v11] );
          v12 = (unsigned int)(v11 + 1);
          v13 = (wchar_t *)operator new[](saturated_mul(v12, 2u));
          v14 = v13;
          if ( !v13 )
          {
            MultiSZPropVal = -2147024882;
            goto LABEL_26;
          }
          wcscpy_s(v13, (unsigned int)v12, v6);
          v16 = wcstok_mvcrt_legacy_two_parameter_form(v14, L",", v15);
          v18 = 3;
          do
          {
            if ( v16 )
              v16 = wcstok_mvcrt_legacy_two_parameter_form(0, L",", v17);
            --v18;
          }
          while ( v18 );
          if ( v16 )
          {
            v19 = (char *)(a3 - (char *)v16);
            do
            {
              v20 = *(unsigned __int16 *)&v19[(_QWORD)v16];
              v21 = *v16 - v20;
              if ( v21 )
                break;
              ++v16;
            }
            while ( v20 );
            if ( !v21 )
            {
              v9 = 1;
              if ( a2 )
                *v6 = 49;
              else
                *v6 = 48;
            }
          }
          operator delete(v14);
          v6 += v12;
          v10 = v6;
        }
        while ( v6 <= Source && *v6 );
        if ( !v9 )
          goto LABEL_25;
        MultiSZPropVal = CSecConLib::SetMultiSZPropVal(this, a4, 0x878u, v7, v8);
      }
      else
      {
LABEL_25:
        MultiSZPropVal = -2146646015;
      }
LABEL_26:
      operator delete(v7);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)MultiSZPropVal;
}

```

## disassembly

```asm
0x1800103ac  mov     r11, rsp
0x1800103af  mov     [r11+20h], rbx
0x1800103b3  mov     [r11+18h], r8
0x1800103b7  mov     [rsp+arg_8], dl
0x1800103bb  mov     [r11+8], rcx
0x1800103bf  push    rbp
0x1800103c0  push    rsi
0x1800103c1  push    rdi
0x1800103c2  push    r12
0x1800103c4  push    r13
0x1800103c6  push    r14
0x1800103c8  push    r15
0x1800103ca  sub     rsp, 40h
0x1800103ce  mov     rax, rcx
0x1800103d1  mov     r13, r9
0x1800103d4  lea     rcx, [r11-48h]
0x1800103d8  xor     ebp, ebp
0x1800103da  mov     [r11-58h], rcx
0x1800103de  lea     r9, [r11-40h]; unsigned __int16 **
0x1800103e2  mov     rcx, rax; this
0x1800103e5  mov     [r11-40h], rbp
0x1800103e9  mov     r8d, 878h; unsigned int
0x1800103ef  mov     [rsp+78h+var_48], ebp
0x1800103f3  mov     rdx, r13; unsigned __int16 *
0x1800103f6  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x1800103fb  mov     ebx, eax
0x1800103fd  test    eax, eax
0x1800103ff  js      loc_180010550
0x180010405  mov     rbx, [rsp+78h+Source]
0x18001040a  test    rbx, rbx
0x18001040d  jz      loc_18001054B
0x180010413  mov     rdi, rbx
0x180010416  cmp     [rbx], bp
0x180010419  jz      loc_180010537
0x18001041f  mov     r12d, [rsp+78h+var_48]
0x180010424  mov     sil, bpl
0x180010427  mov     rcx, rbx
0x18001042a  lea     rax, [r12-1]
0x18001042f  lea     rax, [rbx+rax*2]
0x180010433  mov     [rsp+78h+Source], rax
0x180010438  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001043c  mov     rax, r8
0x18001043f  inc     rax
0x180010442  cmp     [rcx+rax*2], bp
0x180010446  jnz     short loc_18001043F
0x180010448  lea     r15d, [rax+1]
0x18001044c  mov     eax, 2
0x180010451  mul     r15
0x180010454  cmovb   rax, r8
0x180010458  mov     rcx, rax; unsigned __int64
0x18001045b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010460  mov     r14, rax
0x180010463  test    rax, rax
0x180010466  jz      loc_180010530
0x18001046c  mov     r8, rbx; Source
0x18001046f  mov     edx, r15d; SizeInWords
0x180010472  mov     rcx, rax; Destination
0x180010475  call    cs:__imp_wcscpy_s
0x18001047b  lea     rdx, Delimiter; ","
0x180010482  mov     rcx, r14; String
0x180010485  call    wcstok_mvcrt_legacy_two_parameter_form
0x18001048a  mov     ebp, 3
0x18001048f  test    rax, rax
0x180010492  jz      short loc_1800104A2
0x180010494  lea     rdx, Delimiter; ","
0x18001049b  xor     ecx, ecx; String
0x18001049d  call    wcstok_mvcrt_legacy_two_parameter_form
0x1800104a2  sub     ebp, 1
0x1800104a5  jnz     short loc_18001048F
0x1800104a7  xor     ebp, ebp
0x1800104a9  test    rax, rax
0x1800104ac  jz      short loc_1800104EA
0x1800104ae  mov     r8, [rsp+78h+arg_10]
0x1800104b6  sub     r8, rax
0x1800104b9  movzx   edx, word ptr [rax]
0x1800104bc  movzx   ecx, word ptr [rax+r8]
0x1800104c1  sub     edx, ecx
0x1800104c3  jnz     short loc_1800104CD
0x1800104c5  add     rax, 2
0x1800104c9  test    ecx, ecx
0x1800104cb  jnz     short loc_1800104B9
0x1800104cd  test    edx, edx
0x1800104cf  jnz     short loc_1800104EA
0x1800104d1  mov     sil, 1
0x1800104d4  cmp     [rsp+78h+arg_8], bpl
0x1800104dc  jz      short loc_1800104E5
0x1800104de  mov     word ptr [rbx], 31h ; '1'
0x1800104e3  jmp     short loc_1800104EA
0x1800104e5  mov     word ptr [rbx], 30h ; '0'
0x1800104ea  mov     rcx, r14; Block
0x1800104ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800104f2  lea     rbx, [rbx+r15*2]
0x1800104f6  mov     rcx, rbx
0x1800104f9  cmp     rbx, [rsp+78h+Source]
0x1800104fe  ja      short loc_180010509
0x180010500  cmp     [rbx], bp
0x180010503  jnz     loc_180010438
0x180010509  test    sil, sil
0x18001050c  jz      short loc_180010537
0x18001050e  mov     rcx, [rsp+78h+arg_0]; this
0x180010516  mov     r9, rdi; unsigned __int16 *
0x180010519  mov     r8d, 878h; unsigned int
0x18001051f  mov     [rsp+78h+var_58], r12d; unsigned int
0x180010524  mov     rdx, r13; unsigned __int16 *
0x180010527  call    ?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z; CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)
0x18001052c  mov     ebx, eax
0x18001052e  jmp     short loc_18001053C
0x180010530  mov     ebx, 8007000Eh
0x180010535  jmp     short loc_18001053C
0x180010537  mov     ebx, 800CC801h
0x18001053c  test    rdi, rdi
0x18001053f  jz      short loc_180010550
0x180010541  mov     rcx, rdi; Block
0x180010544  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010549  jmp     short loc_180010550
0x18001054b  mov     ebx, 8007000Eh
0x180010550  mov     eax, ebx
0x180010552  mov     rbx, [rsp+78h+arg_18]
0x18001055a  add     rsp, 40h
0x18001055e  pop     r15
0x180010560  pop     r14
0x180010562  pop     r13
0x180010564  pop     r12
0x180010566  pop     rdi
0x180010567  pop     rsi
0x180010568  pop     rbp
0x180010569  retn
```
