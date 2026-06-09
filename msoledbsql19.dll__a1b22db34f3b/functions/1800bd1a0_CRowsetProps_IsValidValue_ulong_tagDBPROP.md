# CRowsetProps::IsValidValue(ulong,tagDBPROP *)

- ea: `0x1800bd1a0`
- end: `0x1800bd539`
- name: `?IsValidValue@CRowsetProps@@EEAAJKPEAUtagDBPROP@@@Z`
- size: `921`
- prototype: `__int64 __fastcall(CRowsetProps *__hidden this, unsigned int, struct tagDBPROP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003d80`
- `0x1800bd1a0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800bd29f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800bd29f`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800bd2e5`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800bd2e5`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800bd2f6`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x1800bd2f6`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800bd32a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800bd32a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800bd30f`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800bd30f`

## pseudocode

```c
__int64 __fastcall CRowsetProps::IsValidValue(CRowsetProps *this, int a2, struct tagDBPROP *a3)
{
  VARTYPE vt; // r9
  unsigned int v4; // r10d
  int v5; // edx
  int v6; // edx
  bool v8; // cc
  SAFEARRAY *parray; // rbx
  LONG plUbound; // [rsp+20h] [rbp-18h] BYREF
  LONG plLbound; // [rsp+24h] [rbp-14h] BYREF

  vt = a3->vValue.vt;
  v4 = 0;
  plLbound = 0;
  plUbound = 0;
  if ( vt == 11 && (unsigned __int16)(a3->vValue.iVal + 1) > 1u )
    return 1;
  if ( !a2 )
  {
    switch ( a3->dwPropertyID )
    {
      case 0x22u:
        if ( vt != 3 )
          return 1;
        v8 = a3->vValue.lVal <= 0xFFFEu;
        goto LABEL_22;
      case 0x49u:
      case 0x4Eu:
        return vt != 3 || a3->vValue.lVal < 0;
      case 0x75u:
        if ( vt != 3 )
          return 1;
        LOBYTE(v4) = (a3->vValue.lVal & 7) != a3->vValue.lVal;
        return v4;
      case 0xC6u:
      case 0xECu:
        if ( vt != 3 )
          return 1;
        v8 = (unsigned int)(a3->vValue.lVal - 1) <= 1;
        goto LABEL_22;
      case 0xC9u:
        return vt != 3 || (a3->vValue.lVal & 0xFFFFFFFE) != 0;
      case 0xE7u:
        if ( vt != 3 )
          return 1;
        v8 = a3->vValue.lVal <= 2u;
        goto LABEL_22;
      case 0xEEu:
        return vt != 11;
      default:
        return 0;
    }
  }
  v5 = a2 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 == 1 )
      {
        if ( a3->dwPropertyID != 19 )
          return 1;
LABEL_8:
        if ( vt != 8 )
          return 1;
      }
    }
    else if ( a3->dwPropertyID == 286 )
    {
      if ( vt != 13 )
        return 1;
    }
    else
    {
      if ( a3->dwPropertyID != 287 || vt != 8 )
        return 1;
      *((_WORD *)this + 343) = 1;
    }
  }
  else
  {
    switch ( a3->dwPropertyID )
    {
      case 8u:
        return vt != 3 || a3->vValue.lVal < 0;
      case 9u:
        goto LABEL_8;
      case 0xCu:
      case 0xDu:
      case 0xEu:
      case 0x14u:
      case 0x17u:
      case 0x19u:
        return vt != 11;
      case 0x11u:
        if ( vt != 19 )
          return 1;
        v8 = (unsigned int)(a3->vValue.lVal - 1) <= 0x7FFFFFFE;
        break;
      case 0x12u:
      case 0x13u:
        if ( vt != 8 )
          return 1;
        v8 = SysStringLen(a3->vValue.bstrVal) <= 0x7D0;
        break;
      case 0x15u:
        return vt != 18;
      case 0x16u:
        if ( vt == 8210 )
        {
          parray = a3->vValue.parray;
          if ( parray )
          {
            if ( SafeArrayGetDim(a3->vValue.parray) == 1
              && SafeArrayGetElemsize(parray) == 2
              && SafeArrayGetLBound(parray, 1u, &plLbound) >= 0 )
            {
              _mm_lfence();
              if ( SafeArrayGetUBound(parray, 1u, &plUbound) >= 0 && plUbound - plLbound < 0xFFFF )
                return 0;
            }
          }
        }
        return 1;
      default:
        return 0;
    }
LABEL_22:
    if ( !v8 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bd1a0  mov     [rsp+arg_8], rbx
0x1800bd1a5  push    rdi
0x1800bd1a6  sub     rsp, 30h
0x1800bd1aa  mov     rax, cs:__security_cookie
0x1800bd1b1  xor     rax, rsp
0x1800bd1b4  mov     [rsp+38h+var_10], rax
0x1800bd1b9  movzx   r9d, word ptr [r8+30h]
0x1800bd1be  xor     r10d, r10d
0x1800bd1c1  mov     [rsp+38h+plLbound], r10d
0x1800bd1c6  mov     r11, rcx
0x1800bd1c9  mov     [rsp+38h+plUbound], r10d
0x1800bd1ce  mov     edi, 1
0x1800bd1d3  cmp     r9w, 0Bh
0x1800bd1d8  jnz     short loc_1800BD1E7
0x1800bd1da  movzx   eax, word ptr [r8+38h]
0x1800bd1df  inc     ax
0x1800bd1e2  cmp     ax, di
0x1800bd1e5  ja      short loc_1800BD208
0x1800bd1e7  test    edx, edx
0x1800bd1e9  jz      loc_1800BD350
0x1800bd1ef  sub     edx, edi
0x1800bd1f1  jz      short loc_1800BD235
0x1800bd1f3  sub     edx, edi
0x1800bd1f5  jz      short loc_1800BD20C
0x1800bd1f7  cmp     edx, edi
0x1800bd1f9  jnz     short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd1fb  cmp     dword ptr [r8], 13h
0x1800bd1ff  jnz     short loc_1800BD208
0x1800bd201  cmp     r9w, 8; jumptable 00000001800BD251 case 9
0x1800bd206  jz      short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd208  mov     eax, edi
0x1800bd20a  jmp     short loc_1800BD278
0x1800bd20c  mov     ecx, [r8]
0x1800bd20f  sub     ecx, 11Eh
0x1800bd215  jz      short loc_1800BD22C
0x1800bd217  cmp     ecx, edi
0x1800bd219  jnz     short loc_1800BD208
0x1800bd21b  cmp     r9w, 8
0x1800bd220  jnz     short loc_1800BD208
0x1800bd222  mov     [r11+2AEh], di
0x1800bd22a  jmp     short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd22c  cmp     r9w, 0Dh
0x1800bd231  jnz     short loc_1800BD208
0x1800bd233  jmp     short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd235  mov     eax, [r8]
0x1800bd238  add     eax, 0FFFFFFF8h; switch 18 cases
0x1800bd23b  cmp     eax, 11h
0x1800bd23e  ja      short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd240  lea     rdx, cs:180000000h
0x1800bd247  mov     eax, ds:(jpt_1800BD251 - 180000000h)[rdx+rax*4]
0x1800bd24e  add     rax, rdx
0x1800bd251  jmp     rax; switch jump
0x1800bd253  cmp     r9w, 3; jumptable 00000001800BD251 case 8
0x1800bd258  jnz     short loc_1800BD208
0x1800bd25a  cmp     [r8+38h], r10d
0x1800bd25e  jl      short loc_1800BD208
0x1800bd260  jmp     short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd262  cmp     r9w, 13h; jumptable 00000001800BD251 case 17
0x1800bd267  jnz     short loc_1800BD208
0x1800bd269  mov     eax, [r8+38h]
0x1800bd26d  dec     eax
0x1800bd26f  cmp     eax, 7FFFFFFEh
0x1800bd274  ja      short loc_1800BD208
0x1800bd276  xor     eax, eax; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd278  mov     rcx, [rsp+38h+var_10]
0x1800bd27d  xor     rcx, rsp; StackCookie
0x1800bd280  call    __security_check_cookie
0x1800bd285  mov     rbx, [rsp+38h+arg_8]
0x1800bd28a  add     rsp, 30h
0x1800bd28e  pop     rdi
0x1800bd28f  retn
0x1800bd290  cmp     r9w, 8; jumptable 00000001800BD251 cases 18,19
0x1800bd295  jnz     loc_1800BD208
0x1800bd29b  mov     rcx, [r8+38h]; pbstr
0x1800bd29f  call    cs:__imp_SysStringLen
0x1800bd2a5  cmp     eax, 7D0h
0x1800bd2aa  jmp     short loc_1800BD274
0x1800bd2ac  cmp     r9w, 0Bh; jumptable 00000001800BD251 cases 12-14,20,23,25
0x1800bd2b1  jnz     loc_1800BD208
0x1800bd2b7  jmp     short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd2b9  cmp     r9w, 12h; jumptable 00000001800BD251 case 21
0x1800bd2be  jnz     loc_1800BD208
0x1800bd2c4  jmp     short def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd2c6  mov     eax, 2012h; jumptable 00000001800BD251 case 22
0x1800bd2cb  cmp     r9w, ax
0x1800bd2cf  jnz     loc_1800BD208
0x1800bd2d5  mov     rbx, [r8+38h]
0x1800bd2d9  test    rbx, rbx
0x1800bd2dc  jz      loc_1800BD208
0x1800bd2e2  mov     rcx, rbx; psa
0x1800bd2e5  call    cs:__imp_SafeArrayGetDim
0x1800bd2eb  cmp     eax, edi
0x1800bd2ed  jnz     loc_1800BD208
0x1800bd2f3  mov     rcx, rbx; psa
0x1800bd2f6  call    cs:__imp_SafeArrayGetElemsize
0x1800bd2fc  cmp     eax, 2
0x1800bd2ff  jnz     loc_1800BD208
0x1800bd305  lea     r8, [rsp+38h+plLbound]; plLbound
0x1800bd30a  mov     edx, edi; nDim
0x1800bd30c  mov     rcx, rbx; psa
0x1800bd30f  call    cs:__imp_SafeArrayGetLBound
0x1800bd315  test    eax, eax
0x1800bd317  js      loc_1800BD208
0x1800bd31d  lfence
0x1800bd320  lea     r8, [rsp+38h+plUbound]; plUbound
0x1800bd325  mov     edx, edi; nDim
0x1800bd327  mov     rcx, rbx; psa
0x1800bd32a  call    cs:__imp_SafeArrayGetUBound
0x1800bd330  test    eax, eax
0x1800bd332  js      loc_1800BD208
0x1800bd338  mov     eax, [rsp+38h+plUbound]
0x1800bd33c  sub     eax, [rsp+38h+plLbound]
0x1800bd340  cmp     eax, 0FFFFh
0x1800bd345  jge     loc_1800BD208
0x1800bd34b  jmp     def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd350  mov     eax, [r8]
0x1800bd353  add     eax, 0FFFFFFDEh; switch 205 cases
0x1800bd356  cmp     eax, 0CCh
0x1800bd35b  ja      def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd361  lea     rdx, cs:180000000h
0x1800bd368  movzx   eax, ds:(byte_1800BD46C - 180000000h)[rdx+rax]
0x1800bd370  mov     ecx, ds:(jpt_1800BD37A - 180000000h)[rdx+rax*4]
0x1800bd377  add     rcx, rdx
0x1800bd37a  jmp     rcx; switch jump
0x1800bd37c  cmp     r9w, 3; jumptable 00000001800BD37A case 231
0x1800bd381  jnz     loc_1800BD208
0x1800bd387  cmp     dword ptr [r8+38h], 2
0x1800bd38c  jmp     loc_1800BD274
0x1800bd391  cmp     r9w, 3; jumptable 00000001800BD37A case 34
0x1800bd396  jnz     loc_1800BD208
0x1800bd39c  cmp     dword ptr [r8+38h], 0FFFEh
0x1800bd3a4  jmp     loc_1800BD274
0x1800bd3a9  cmp     r9w, 3; jumptable 00000001800BD37A cases 198,236
0x1800bd3ae  jnz     loc_1800BD208
0x1800bd3b4  mov     eax, [r8+38h]
0x1800bd3b8  dec     eax
0x1800bd3ba  cmp     eax, edi
0x1800bd3bc  jmp     loc_1800BD274
0x1800bd3c1  cmp     r9w, 3; jumptable 00000001800BD37A case 201
0x1800bd3c6  jnz     loc_1800BD208
0x1800bd3cc  test    dword ptr [r8+38h], 0FFFFFFFEh
0x1800bd3d4  jnz     loc_1800BD208
0x1800bd3da  jmp     def_1800BD251; jumptable 00000001800BD251 default case, cases 10,11,15,16,24
0x1800bd3df  cmp     r9w, 3; jumptable 00000001800BD37A case 117
0x1800bd3e4  jnz     loc_1800BD208
0x1800bd3ea  mov     ecx, [r8+38h]
0x1800bd3ee  and     ecx, 7
0x1800bd3f1  cmp     ecx, [r8+38h]
0x1800bd3f5  setnz   r10b
0x1800bd3f9  mov     eax, r10d
0x1800bd3fc  jmp     loc_1800BD278
```
