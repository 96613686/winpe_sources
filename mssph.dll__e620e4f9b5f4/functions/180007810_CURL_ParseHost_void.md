# CURL::ParseHost(void)

- ea: `0x180007810`
- end: `0x180007b73`
- name: `?ParseHost@CURL@@IEAAXXZ`
- size: `867`
- prototype: `void __fastcall(CURL *__hidden this)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180005880`
- `0x1800061d0`
- `0x1800075e0`
- `0x180007650`
- `0x1800076a0`
- `0x180021724`

## callees

- `0x180007810`
- `0x180007b80`
- `0x1800080b0`
- `0x18000a0a0`
- `0x18000bdec`
- `0x18000e7fc`
- `0x18000fcd0`
- `0x180011135`
- `0x180024dc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180007b1a`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180007b1a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180007a5c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180007a5c`

## string_xrefs

- `0x180007ad9`: `onecoreuap\base\appmodel\search\common\pkmutill\url.cxx`

## pseudocode

```c
void __fastcall CURL::ParseHost(CURL *this)
{
  __int16 v1; // ax
  __int64 v3; // rbx
  unsigned int v4; // r12d
  __int16 v5; // r10
  unsigned int v6; // edx
  __int64 v7; // r9
  int v8; // edx
  int v9; // r8d
  __int16 v10; // bx
  __int64 v11; // rdx
  __int64 v12; // rdi
  int v13; // edx
  __int16 v14; // dx
  signed int AnySlash; // eax
  int v16; // r11d
  __int16 v17; // bx
  unsigned int v18; // edx
  signed int v19; // eax
  __int64 v20; // r8
  __int16 v21; // cx
  __int16 v22; // ax
  __int64 v23; // r9
  unsigned int v24; // edx
  __int16 v25; // cx
  wchar_t *v26; // rax
  __int64 v27; // rsi
  __int64 v28; // r8
  unsigned int *v29; // r8
  __int64 v30; // r9
  unsigned __int64 v31; // rdx
  __int64 v32; // rax
  void *v33; // rsp
  __int64 v34; // rdi
  int v35[4]; // [rsp+20h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+58h]

  v1 = *((_WORD *)this + 231);
  if ( (v1 & 4) == 0 )
    return;
  *((_WORD *)this + 231) = v1 & 0xFFFB;
  CURL::ParseAccessType(this);
  v3 = *((unsigned __int16 *)this + 221);
  v4 = *((unsigned __int16 *)this + 227);
  if ( *((_WORD *)this + 220) )
  {
    if ( v4 >= (int)v3 + 2 )
    {
      v20 = *((_QWORD *)this + 4);
      v21 = *(_WORD *)(v20 + 2 * v3);
      if ( v21 == 47 || v21 == 92 )
      {
        v22 = *(_WORD *)(v20 + 2LL * (unsigned int)(v3 + 1));
        if ( v22 == 47 || v22 == 92 )
        {
          v23 = (unsigned __int16)(v3 + 2);
          *((_WORD *)this + 221) = v23;
          LODWORD(v3) = (unsigned __int16)(v3 + 2);
          v24 = *((_DWORD *)this + 11);
          if ( (unsigned int)v23 < v24 )
          {
            do
            {
              v25 = *(_WORD *)(v20 + 2LL * (unsigned int)v3);
              if ( v25 == 47 )
                break;
              if ( v25 == 92 )
                break;
              LODWORD(v3) = v3 + 1;
            }
            while ( (unsigned int)v3 < v24 );
          }
          if ( (unsigned int)v3 >= v24 || (_DWORD)v3 == -1 || (int)v3 > (int)v4 )
            LODWORD(v3) = v4;
          if ( (unsigned int)v23 >= v24
            || (v26 = wcschr((const wchar_t *)(v20 + 2 * v23), 0x3Au)) == 0
            || (v27 = ((__int64)v26 - *((_QWORD *)this + 4)) >> 1, (_DWORD)v27 == -1)
            || (v28 = (unsigned int)(v27 + 1), (int)v28 >= (int)v3) )
          {
            LOWORD(v27) = v3;
          }
          else
          {
            v29 = (unsigned int *)CLMString::Mid((char *)this + 24, v35, v28, (unsigned int)(v3 - v28));
            v30 = v29[1];
            v31 = 2LL * (unsigned int)(v30 + 1);
            v32 = v31 + 15;
            if ( v31 + 15 < v31 )
              v32 = 0xFFFFFFFFFFFFFF0LL;
            v33 = alloca(v32 & 0xFFFFFFFFFFFFFFF0uLL);
            if ( !v35 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x20B,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\url.cxx",
                (const char *)0x8007000ELL,
                v35[0]);
            v34 = 2 * v30;
            memcpy_0(v35, (const void *)(*(_QWORD *)(*((_QWORD *)v29 + 1) + 8LL) + 2LL * *v29), 2 * v30);
            *(_WORD *)((char *)v35 + v34) = 0;
            *((_DWORD *)this + 117) = _o__wtol(v35);
            *((_WORD *)this + 231) &= ~2u;
          }
          *((_WORD *)this + 222) = v27 - *((_WORD *)this + 221);
        }
      }
    }
    *((_WORD *)this + 225) = v3;
    *((_WORD *)this + 233) = v3;
    return;
  }
  v5 = 0;
  v6 = *((unsigned __int16 *)this + 221);
  if ( (unsigned int)v3 < v4 )
  {
    v7 = *((_QWORD *)this + 4);
    do
    {
      if ( !(unsigned int)IsSlash(*(_WORD *)(v7 + 2LL * v6)) )
        break;
      ++v9;
      v6 = v8 + 1;
    }
    while ( v6 < v4 );
    if ( v9 == 4 )
    {
      v10 = v3 + 2;
LABEL_13:
      *((_WORD *)this + 221) = v10;
      goto LABEL_14;
    }
    if ( ((v9 - 3) & 0xFFFFFFFD) == 0 )
    {
      v10 = v3 + 3;
      goto LABEL_13;
    }
    if ( v9 == 6 )
    {
      v10 = v3 + 4;
      goto LABEL_13;
    }
  }
LABEL_14:
  v11 = *((unsigned __int16 *)this + 221);
  *((_WORD *)this + 225) = v11;
  if ( v4 < (int)v11 + 2 )
    goto LABEL_22;
  v12 = *((_QWORD *)this + 4);
  if ( !(unsigned int)IsSlash(*(_WORD *)(v12 + 2 * v11))
    || !(unsigned int)IsSlash(*(_WORD *)(v12 + 2LL * (unsigned int)(v13 + 1))) )
  {
    goto LABEL_22;
  }
  *((_WORD *)this + 221) = v14 + 2;
  AnySlash = CLMString::FindAnySlash((CURL *)((char *)this + 24), (unsigned __int16)(v14 + 2));
  v17 = AnySlash;
  if ( AnySlash == -1 || AnySlash > (int)v4 )
  {
    *((_WORD *)this + 222) = v4 - v16;
  }
  else
  {
    *((_WORD *)this + 222) = AnySlash - v16;
    if ( (_WORD)AnySlash - (_WORD)v16 == 2 && *(_WORD *)(v12 + 2LL * (unsigned int)(v16 + 1)) == 58 )
    {
      *((_WORD *)this + 225) = v16;
LABEL_22:
      *((_WORD *)this + 224) = v5;
      *((_WORD *)this + 222) = v5;
      return;
    }
    v18 = (unsigned __int16)(AnySlash + 1);
    *((_WORD *)this + 223) = v18;
    v19 = CLMString::FindAnySlash((CURL *)((char *)this + 24), v18);
    if ( v19 == -1 || v19 > (int)v4 )
      LOWORD(v19) = v4;
    *((_WORD *)this + 224) = v19 - v17 - 1;
  }
}

```

## disassembly

```asm
0x180007810  push    rbp
0x180007812  push    rbx
0x180007813  push    rsi
0x180007814  push    rdi
0x180007815  push    r12
0x180007817  push    r14
0x180007819  push    r15
0x18000781b  sub     rsp, 40h
0x18000781f  lea     rbp, [rsp+20h]
0x180007824  mov     rax, cs:__security_cookie
0x18000782b  xor     rax, rbp
0x18000782e  mov     [rbp+50h+var_40], rax
0x180007832  movzx   eax, word ptr [rcx+1CEh]
0x180007839  mov     r15, rcx
0x18000783c  test    al, 4
0x18000783e  jz      loc_180007B58
0x180007844  mov     ecx, 0FFFBh
0x180007849  and     ax, cx
0x18000784c  mov     rcx, r15; this
0x18000784f  mov     [r15+1CEh], ax
0x180007857  call    ?ParseAccessType@CURL@@IEAAXXZ; CURL::ParseAccessType(void)
0x18000785c  cmp     word ptr [r15+1B8h], 0
0x180007865  movzx   ebx, word ptr [r15+1BAh]
0x18000786d  movzx   r12d, word ptr [r15+1C6h]
0x180007875  jnz     loc_1800079BC
0x18000787b  xor     r10d, r10d
0x18000787e  mov     edx, ebx
0x180007880  cmp     ebx, r12d
0x180007883  jnb     short loc_1800078D5
0x180007885  mov     r9, [r15+20h]
0x180007889  mov     r8d, r10d
0x18000788c  mov     ecx, edx
0x18000788e  movzx   ecx, word ptr [r9+rcx*2]; wchar_t
0x180007893  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x180007898  test    eax, eax
0x18000789a  jz      short loc_1800078A6
0x18000789c  inc     r8d
0x18000789f  inc     edx
0x1800078a1  cmp     edx, r12d
0x1800078a4  jb      short loc_18000788C
0x1800078a6  cmp     r8d, 4
0x1800078aa  jnz     short loc_1800078B2
0x1800078ac  add     bx, 2
0x1800078b0  jmp     short loc_1800078CD
0x1800078b2  lea     eax, [r8-3]
0x1800078b6  test    eax, 0FFFFFFFDh
0x1800078bb  jz      short loc_1800078C9
0x1800078bd  cmp     r8d, 6
0x1800078c1  jnz     short loc_1800078D5
0x1800078c3  add     bx, 4
0x1800078c7  jmp     short loc_1800078CD
0x1800078c9  add     bx, 3
0x1800078cd  mov     [r15+1BAh], bx
0x1800078d5  movzx   edx, word ptr [r15+1BAh]
0x1800078dd  mov     [r15+1C2h], dx
0x1800078e5  lea     eax, [rdx+2]
0x1800078e8  cmp     r12d, eax
0x1800078eb  jb      short loc_18000795E
0x1800078ed  mov     rdi, [r15+20h]
0x1800078f1  movzx   ecx, word ptr [rdi+rdx*2]; wchar_t
0x1800078f5  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x1800078fa  test    eax, eax
0x1800078fc  jz      short loc_18000795E
0x1800078fe  lea     eax, [rdx+1]
0x180007901  movzx   ecx, word ptr [rdi+rax*2]; wchar_t
0x180007905  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x18000790a  test    eax, eax
0x18000790c  jz      short loc_18000795E
0x18000790e  add     dx, 2
0x180007912  lea     rcx, [r15+18h]; this
0x180007916  movzx   r11d, dx
0x18000791a  mov     edx, r11d; unsigned int
0x18000791d  mov     [r15+1BAh], r11w
0x180007925  call    ?FindAnySlash@CLMString@@QEBAHI@Z; CLMString::FindAnySlash(uint)
0x18000792a  mov     ebx, eax
0x18000792c  cmp     eax, 0FFFFFFFFh
0x18000792f  jz      short loc_1800079AB
0x180007931  cmp     eax, r12d
0x180007934  jg      short loc_1800079AB
0x180007936  movzx   ecx, bx
0x180007939  sub     cx, r11w
0x18000793d  mov     [r15+1BCh], cx
0x180007945  cmp     cx, 2
0x180007949  jnz     short loc_180007973
0x18000794b  lea     eax, [r11+1]
0x18000794f  cmp     word ptr [rdi+rax*2], 3Ah ; ':'
0x180007954  jnz     short loc_180007973
0x180007956  mov     [r15+1C2h], r11w
0x18000795e  mov     [r15+1C0h], r10w
0x180007966  mov     [r15+1BCh], r10w
0x18000796e  jmp     loc_180007B58
0x180007973  lea     eax, [rbx+1]
0x180007976  movzx   edx, ax; unsigned int
0x180007979  lea     rcx, [r15+18h]; this
0x18000797d  mov     [r15+1BEh], dx
0x180007985  call    ?FindAnySlash@CLMString@@QEBAHI@Z; CLMString::FindAnySlash(uint)
0x18000798a  cmp     eax, 0FFFFFFFFh
0x18000798d  jz      short loc_180007994
0x18000798f  cmp     eax, r12d
0x180007992  jle     short loc_180007998
0x180007994  movzx   eax, r12w
0x180007998  sub     ax, bx
0x18000799b  dec     ax
0x18000799e  mov     [r15+1C0h], ax
0x1800079a6  jmp     loc_180007B58
0x1800079ab  sub     r12w, r11w
0x1800079af  mov     [r15+1BCh], r12w
0x1800079b7  jmp     loc_180007B58
0x1800079bc  lea     eax, [rbx+2]
0x1800079bf  cmp     r12d, eax
0x1800079c2  jb      loc_180007B48
0x1800079c8  mov     r8, [r15+20h]
0x1800079cc  movzx   ecx, word ptr [r8+rbx*2]
0x1800079d1  cmp     cx, 2Fh ; '/'
0x1800079d5  jz      short loc_1800079E1
0x1800079d7  cmp     cx, 5Ch ; '\'
0x1800079db  jnz     loc_180007B48
0x1800079e1  lea     eax, [rbx+1]
0x1800079e4  movzx   eax, word ptr [r8+rax*2]
0x1800079e9  cmp     ax, 2Fh ; '/'
0x1800079ed  jz      short loc_1800079F9
0x1800079ef  cmp     ax, 5Ch ; '\'
0x1800079f3  jnz     loc_180007B48
0x1800079f9  add     bx, 2
0x1800079fd  movzx   r9d, bx
0x180007a01  mov     [r15+1BAh], r9w
0x180007a09  mov     ebx, r9d
0x180007a0c  mov     edx, [r15+2Ch]
0x180007a10  cmp     r9d, edx
0x180007a13  jnb     short loc_180007A39
0x180007a15  nop     word ptr [rax+rax+00000000h]
0x180007a20  mov     eax, ebx
0x180007a22  movzx   ecx, word ptr [r8+rax*2]
0x180007a27  cmp     cx, 2Fh ; '/'
0x180007a2b  jz      short loc_180007A39
0x180007a2d  cmp     cx, 5Ch ; '\'
0x180007a31  jz      short loc_180007A39
0x180007a33  inc     ebx
0x180007a35  cmp     ebx, edx
0x180007a37  jb      short loc_180007A20
0x180007a39  cmp     ebx, edx
0x180007a3b  jnb     short loc_180007A47
0x180007a3d  cmp     ebx, 0FFFFFFFFh
0x180007a40  jz      short loc_180007A47
0x180007a42  cmp     ebx, r12d
0x180007a45  jle     short loc_180007A4A
0x180007a47  mov     ebx, r12d
0x180007a4a  cmp     r9d, edx
0x180007a4d  jnb     loc_180007B36
0x180007a53  mov     edx, 3Ah ; ':'; Ch
0x180007a58  lea     rcx, [r8+r9*2]; Str
0x180007a5c  call    cs:__imp_wcschr
0x180007a62  mov     rsi, rax
0x180007a65  test    rax, rax
0x180007a68  jz      loc_180007B36
0x180007a6e  sub     rsi, [r15+20h]
0x180007a72  sar     rsi, 1
0x180007a75  cmp     esi, 0FFFFFFFFh
0x180007a78  jz      loc_180007B36
0x180007a7e  lea     r8d, [rsi+1]
0x180007a82  cmp     r8d, ebx
0x180007a85  jge     loc_180007B36
0x180007a8b  mov     r9d, ebx
0x180007a8e  lea     rcx, [r15+18h]
0x180007a92  sub     r9d, r8d
0x180007a95  lea     rdx, [rbp+50h+var_50]
0x180007a99  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x180007a9e  mov     r8, rax
0x180007aa1  mov     r9d, [rax+4]
0x180007aa5  lea     edx, [r9+1]
0x180007aa9  add     rdx, rdx
0x180007aac  lea     rax, [rdx+0Fh]
0x180007ab0  cmp     rax, rdx
0x180007ab3  ja      short loc_180007ABF
0x180007ab5  mov     rax, 0FFFFFFFFFFFFFF0h
0x180007abf  and     rax, 0FFFFFFFFFFFFFFF0h
0x180007ac3  call    _alloca_probe
0x180007ac8  sub     rsp, rax
0x180007acb  lea     r14, [rsp+70h+var_50]
0x180007ad0  test    r14, r14
0x180007ad3  jnz     short loc_180007AF1
0x180007ad5  mov     rcx, [rbp+58h]; this
0x180007ad9  lea     r8, aOnecoreuapBase_6; "onecoreuap\\base\\appmodel\\search\\com"...
0x180007ae0  mov     r9d, 8007000Eh; char *
0x180007ae6  mov     edx, 20Bh; void *
0x180007aeb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180007af1  mov     rax, [r8+8]
0x180007af5  lea     rdi, [r9+r9]
0x180007af9  mov     edx, [r8]
0x180007afc  mov     rcx, r14; void *
0x180007aff  mov     r8, rdi; Size
0x180007b02  mov     rax, [rax+8]
0x180007b06  lea     rdx, [rax+rdx*2]; Src
0x180007b0a  call    memcpy_0
0x180007b0f  xor     r10d, r10d
0x180007b12  mov     rcx, r14
0x180007b15  mov     [rdi+r14], r10w
0x180007b1a  call    cs:__imp__o__wtol
0x180007b20  mov     [r15+1D4h], eax
0x180007b27  mov     eax, 0FFFDh
0x180007b2c  and     [r15+1CEh], ax
0x180007b34  jmp     short loc_180007B38
0x180007b36  mov     esi, ebx
0x180007b38  sub     si, [r15+1BAh]
0x180007b40  mov     [r15+1BCh], si
0x180007b48  mov     [r15+1C2h], bx
0x180007b50  mov     [r15+1D2h], bx
0x180007b58  mov     rcx, [rbp+50h+var_40]
0x180007b5c  xor     rcx, rbp; StackCookie
0x180007b5f  call    __security_check_cookie
0x180007b64  lea     rsp, [rbp+20h]
0x180007b68  pop     r15
0x180007b6a  pop     r14
0x180007b6c  pop     r12
0x180007b6e  pop     rdi
0x180007b6f  pop     rsi
0x180007b70  pop     rbx
0x180007b71  pop     rbp
0x180007b72  retn
```
