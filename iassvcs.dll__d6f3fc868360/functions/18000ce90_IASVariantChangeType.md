# IASVariantChangeType

- ea: `0x18000ce90`
- end: `0x18000d1c0`
- name: `IASVariantChangeType`
- size: `816`
- prototype: `HRESULT __fastcall(VARIANTARG *pvarg, VARIANTARG *, __int64, unsigned __int16)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002280`
- `0x18000236c`
- `0x18000ce90`
- `0x1800181e0`

## import_xrefs

- `msvcrt!_wtol` at `0x18000d131`
- `msvcrt!_wtol` at `0x18000d165`
- `msvcrt!_wtol` at `0x18000d131`
- `msvcrt!_wtol` at `0x18000d165`
- `msvcrt!_ltow` at `0x18000d182`
- `msvcrt!_ltow` at `0x18000d182`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d024`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d024`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000cf72`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000cf72`
- `OLEAUT32!__imp_VariantInit` at `0x18000cf03`
- `OLEAUT32!__imp_VariantInit` at `0x18000cf03`
- `OLEAUT32!__imp_VariantClear` at `0x18000d04b`
- `OLEAUT32!__imp_VariantClear` at `0x18000d04b`
- `OLEAUT32!__imp_VariantCopy` at `0x18000cedc`
- `OLEAUT32!__imp_VariantCopy` at `0x18000cedc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000cf8a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d002`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d116`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000cf8a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d002`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d116`

## pseudocode

```c
HRESULT __fastcall IASVariantChangeType(VARIANTARG *pvarg, VARIANTARG *a2, __int64 a3, unsigned __int16 a4)
{
  int v4; // r14d
  struct IErrorInfo *v8; // r8
  bool v9; // r9
  char *v10; // rsi
  int v11; // ebx
  BSTR v12; // rax
  BSTR v13; // rdx
  char v14; // al
  wchar_t *v15; // rcx
  BSTR v16; // rbx
  __int64 v17; // rax
  int v18; // esi
  _BYTE *i; // r10
  char v20; // cl
  char v21; // r8
  OLECHAR v22; // dx
  char v23; // cl
  const wchar_t *v24; // rcx
  const wchar_t *bstrVal; // rcx
  VARIANTARG pvarga; // [rsp+28h] [rbp-60h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-38h] BYREF
  int v28; // [rsp+58h] [rbp-30h]
  _BYTE *v29; // [rsp+60h] [rbp-28h]

  v4 = a4;
  if ( !pvarg || !a2 )
    return -2147024809;
  if ( a2->vt != a4 )
  {
    memset(&pvarga, 0, sizeof(pvarga));
    VariantInit(&pvarga);
    if ( (v4 | (a2->vt << 16)) != 0x30008 )
    {
      switch ( v4 | (a2->vt << 16) )
      {
        case 524291:
          bstrVal = a2->bstrVal;
          if ( !bstrVal )
            return -2147352571;
          pvarga.lVal = _wtol(bstrVal);
          break;
        case 524299:
          v24 = a2->bstrVal;
          if ( !v24 )
            return -2147352571;
          if ( (unsigned __int16)_wtol(v24) )
            pvarga.iVal = -1;
          else
            pvarga.iVal = 0;
          break;
        case 532497:
          v16 = a2->bstrVal;
          if ( !v16 )
            return -2147352571;
          v17 = -1;
          do
            ++v17;
          while ( v16[v17] );
          if ( (v17 & 1) != 0 )
            return -2147352571;
          v18 = (int)v17 / 2;
          CVariantVector<unsigned char>::CVariantVector<unsigned char>((__int64)&psa, &pvarga, (int)v17 / 2);
          for ( i = v29; v18; --v18 )
          {
            v20 = 48;
            if ( (unsigned __int16)(*v16 - 48) > 9u )
              v20 = 55;
            v21 = 16 * (*v16 - v20);
            *i = v21;
            v22 = v16[1];
            v16 += 2;
            v23 = 48;
            if ( (unsigned __int16)(v22 - 48) > 9u )
              v23 = 55;
            *i++ = v21 | (v22 - v23);
          }
          SafeArrayUnaccessData(psa);
          break;
        case 720904:
          v15 = L"-1";
          if ( !a2->iVal )
            v15 = (wchar_t *)L"0";
          goto LABEL_20;
        case 537985032:
          CVariantVector<unsigned char>::CVariantVector<unsigned char>((__int64)&psa, (__int64)a2, v8, v9);
          v10 = v29;
          v11 = v28;
          v12 = SysAllocStringLen(0, 2 * v28);
          v13 = v12;
          if ( !v12 )
          {
            SafeArrayUnaccessData(psa);
            return -2147024882;
          }
          for ( pvarga.llVal = (LONGLONG)v12; v11; --v11 )
          {
            *v13 = ((unsigned __int8)*v10 >> 4) + ((unsigned __int8)((unsigned __int8)*v10 >> 4) < 0xAu ? 48 : 55);
            v14 = *v10++;
            v13[1] = (v14 & 0xF) + ((v14 & 0xFu) < 0xA ? 48 : 55);
            v13 += 2;
          }
          *v13 = 0;
          SafeArrayUnaccessData(psa);
          break;
        default:
          return -2147352571;
      }
LABEL_21:
      pvarga.vt = v4;
      VariantClear(pvarg);
      *pvarg = pvarga;
      return 0;
    }
    v15 = _ltow(a2->lVal, (wchar_t *)&psa, 10);
LABEL_20:
    pvarga.llVal = (LONGLONG)SysAllocString(v15);
    if ( !pvarga.llVal )
      return -2147024882;
    goto LABEL_21;
  }
  if ( pvarg == a2 )
    return 0;
  else
    return VariantCopy(pvarg, a2);
}

```

## disassembly

```asm
0x18000ce90  mov     [rsp+arg_10], rbx
0x18000ce95  mov     [rsp+arg_18], rsi
0x18000ce9a  push    rdi
0x18000ce9b  push    r14
0x18000ce9d  push    r15
0x18000ce9f  sub     rsp, 70h
0x18000cea3  mov     rax, cs:__security_cookie
0x18000ceaa  xor     rax, rsp
0x18000cead  mov     [rsp+88h+var_20], rax
0x18000ceb2  movzx   r14d, r9w
0x18000ceb6  mov     rbx, rdx
0x18000ceb9  mov     rdi, rcx
0x18000cebc  xor     r15d, r15d
0x18000cebf  test    rcx, rcx
0x18000cec2  jz      loc_18000D197
0x18000cec8  test    rdx, rdx
0x18000cecb  jz      loc_18000D197
0x18000ced1  cmp     [rdx], r14w
0x18000ced5  jnz     short loc_18000CEEF
0x18000ced7  cmp     rcx, rdx
0x18000ceda  jz      short loc_18000CEE7
0x18000cedc  call    cs:__imp_VariantCopy
0x18000cee2  jmp     loc_18000D19C
0x18000cee7  mov     eax, r15d
0x18000ceea  jmp     loc_18000D19C
0x18000ceef  xorps   xmm0, xmm0
0x18000cef2  xor     eax, eax
0x18000cef4  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x18000cef9  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x18000cefe  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18000cf03  call    cs:__imp_VariantInit
0x18000cf09  movzx   ecx, word ptr [rbx]
0x18000cf0c  shl     ecx, 10h
0x18000cf0f  or      ecx, r14d
0x18000cf12  sub     ecx, 30008h
0x18000cf18  jz      loc_18000D174
0x18000cf1e  sub     ecx, 4FFFBh
0x18000cf24  jz      loc_18000D155
0x18000cf2a  sub     ecx, 8
0x18000cf2d  jz      loc_18000D128
0x18000cf33  sub     ecx, 2006h
0x18000cf39  jz      loc_18000D06B
0x18000cf3f  sub     ecx, 2DFF7h
0x18000cf45  jz      loc_18000D00D
0x18000cf4b  cmp     ecx, 20060000h
0x18000cf51  jnz     loc_18000D15E
0x18000cf57  mov     rdx, rbx
0x18000cf5a  lea     rcx, [rsp+88h+psa]
0x18000cf5f  call    ??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z; CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)
0x18000cf64  mov     rsi, [rsp+88h+var_28]
0x18000cf69  mov     ebx, [rsp+88h+var_30]
0x18000cf6d  lea     edx, [rbx+rbx]; ui
0x18000cf70  xor     ecx, ecx; strIn
0x18000cf72  call    cs:__imp_SysAllocStringLen
0x18000cf78  mov     rdx, rax
0x18000cf7b  mov     [rsp+88h+var_68], rax
0x18000cf80  test    rax, rax
0x18000cf83  jnz     short loc_18000CF9A
0x18000cf85  mov     rcx, [rsp+88h+psa]; psa
0x18000cf8a  call    cs:__imp_SafeArrayUnaccessData
0x18000cf90  mov     eax, 8007000Eh
0x18000cf95  jmp     loc_18000D19C
0x18000cf9a  mov     dword ptr [rsp+88h+pvarg+8], eax
0x18000cf9e  mov     eax, dword ptr [rsp+88h+var_68+4]
0x18000cfa2  mov     dword ptr [rsp+88h+pvarg+0Ch], eax
0x18000cfa6  test    ebx, ebx
0x18000cfa8  jz      short loc_18000CFF9
0x18000cfaa  mov     r8w, 0FFF9h
0x18000cfaf  mov     r9d, 37h ; '7'
0x18000cfb5  mov     al, [rsi]
0x18000cfb7  shr     al, 4
0x18000cfba  movzx   ecx, al
0x18000cfbd  cmp     cl, 0Ah
0x18000cfc0  sbb     ax, ax
0x18000cfc3  and     ax, r8w
0x18000cfc7  add     ax, r9w
0x18000cfcb  add     ax, cx
0x18000cfce  mov     [rdx], ax
0x18000cfd1  mov     al, [rsi]
0x18000cfd3  inc     rsi
0x18000cfd6  and     al, 0Fh
0x18000cfd8  movzx   ecx, al
0x18000cfdb  cmp     cl, 0Ah
0x18000cfde  sbb     ax, ax
0x18000cfe1  and     ax, r8w
0x18000cfe5  add     ax, r9w
0x18000cfe9  add     ax, cx
0x18000cfec  mov     [rdx+2], ax
0x18000cff0  add     rdx, 4
0x18000cff4  sub     ebx, 1
0x18000cff7  jnz     short loc_18000CFB5
0x18000cff9  mov     [rdx], r15w
0x18000cffd  mov     rcx, [rsp+88h+psa]; psa
0x18000d002  call    cs:__imp_SafeArrayUnaccessData
0x18000d008  jmp     loc_18000D11D
0x18000d00d  lea     rax, psz; "0"
0x18000d014  lea     rcx, a1; "-1"
0x18000d01b  cmp     [rbx+8], r15w
0x18000d020  cmovz   rcx, rax; psz
0x18000d024  call    cs:__imp_SysAllocString
0x18000d02a  mov     rcx, rax
0x18000d02d  sar     rcx, 20h
0x18000d031  test    rax, rax
0x18000d034  mov     dword ptr [rsp+88h+pvarg+0Ch], ecx
0x18000d038  mov     dword ptr [rsp+88h+pvarg+8], eax
0x18000d03c  jz      loc_18000D190
0x18000d042  mov     word ptr [rsp+88h+pvarg], r14w
0x18000d048  mov     rcx, rdi; pvarg
0x18000d04b  call    cs:__imp_VariantClear
0x18000d051  movups  xmm0, xmmword ptr [rsp+88h+pvarg]
0x18000d056  movups  xmmword ptr [rdi], xmm0
0x18000d059  movsd   xmm1, qword ptr [rsp+88h+pvarg+10h]
0x18000d05f  movsd   qword ptr [rdi+10h], xmm1
0x18000d064  xor     eax, eax
0x18000d066  jmp     loc_18000D19C
0x18000d06b  mov     rbx, [rbx+8]
0x18000d06f  test    rbx, rbx
0x18000d072  jnz     short loc_18000D07E
0x18000d074  mov     eax, 80020005h
0x18000d079  jmp     loc_18000D19C
0x18000d07e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d082  inc     rax
0x18000d085  cmp     [rbx+rax*2], r15w
0x18000d08a  jnz     short loc_18000D082
0x18000d08c  test    al, 1
0x18000d08e  jz      short loc_18000D09A
0x18000d090  mov     eax, 80020005h
0x18000d095  jmp     loc_18000D19C
0x18000d09a  cdq
0x18000d09b  sub     eax, edx
0x18000d09d  sar     eax, 1
0x18000d09f  mov     esi, eax
0x18000d0a1  mov     r8d, eax
0x18000d0a4  lea     rdx, [rsp+88h+pvarg]
0x18000d0a9  lea     rcx, [rsp+88h+psa]
0x18000d0ae  call    ??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@I@Z; CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *,uint)
0x18000d0b3  mov     r10, [rsp+88h+var_28]
0x18000d0b8  test    esi, esi
0x18000d0ba  jz      short loc_18000D111
0x18000d0bc  mov     r9d, 37h ; '7'
0x18000d0c2  lea     r11d, [r9-7]
0x18000d0c6  movzx   r8d, word ptr [rbx]
0x18000d0ca  movzx   eax, r8w
0x18000d0ce  sub     ax, r11w
0x18000d0d2  mov     ecx, r11d
0x18000d0d5  cmp     ax, 9
0x18000d0d9  cmova   ecx, r9d
0x18000d0dd  sub     r8b, cl
0x18000d0e0  shl     r8b, 4
0x18000d0e4  mov     [r10], r8b
0x18000d0e7  movzx   edx, word ptr [rbx+2]
0x18000d0eb  lea     rbx, [rbx+4]
0x18000d0ef  movzx   eax, dx
0x18000d0f2  sub     ax, r11w
0x18000d0f6  mov     ecx, r11d
0x18000d0f9  cmp     ax, 9
0x18000d0fd  cmova   ecx, r9d
0x18000d101  sub     dl, cl
0x18000d103  or      dl, r8b
0x18000d106  mov     [r10], dl
0x18000d109  inc     r10
0x18000d10c  sub     esi, 1
0x18000d10f  jnz     short loc_18000D0C6
0x18000d111  mov     rcx, [rsp+88h+psa]; psa
0x18000d116  call    cs:__imp_SafeArrayUnaccessData
0x18000d11c  nop
0x18000d11d  jmp     loc_18000D042
0x18000d122  mov     eax, dword ptr [rsp+88h+var_68]
0x18000d126  jmp     short loc_18000D19C
0x18000d128  mov     rcx, [rbx+8]; String
0x18000d12c  test    rcx, rcx
0x18000d12f  jz      short loc_18000D15E
0x18000d131  call    cs:__imp__wtol
0x18000d137  test    ax, ax
0x18000d13a  jz      short loc_18000D14A
0x18000d13c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d140  mov     word ptr [rsp+88h+pvarg+8], ax
0x18000d145  jmp     loc_18000D042
0x18000d14a  mov     word ptr [rsp+88h+pvarg+8], r15w
0x18000d150  jmp     loc_18000D042
0x18000d155  mov     rcx, [rbx+8]; String
0x18000d159  test    rcx, rcx
0x18000d15c  jnz     short loc_18000D165
0x18000d15e  mov     eax, 80020005h
0x18000d163  jmp     short loc_18000D19C
0x18000d165  call    cs:__imp__wtol
0x18000d16b  mov     dword ptr [rsp+88h+pvarg+8], eax
0x18000d16f  jmp     loc_18000D042
0x18000d174  mov     r8d, 0Ah; Radix
0x18000d17a  lea     rdx, [rsp+88h+psa]; Buffer
0x18000d17f  mov     ecx, [rbx+8]; Value
0x18000d182  call    cs:__imp__ltow
0x18000d188  mov     rcx, rax
0x18000d18b  jmp     loc_18000D024
0x18000d190  mov     eax, 8007000Eh
0x18000d195  jmp     short loc_18000D19C
0x18000d197  mov     eax, 80070057h
0x18000d19c  mov     rcx, [rsp+88h+var_20]
0x18000d1a1  xor     rcx, rsp; StackCookie
0x18000d1a4  call    __security_check_cookie
0x18000d1a9  lea     r11, [rsp+88h+var_18]
0x18000d1ae  mov     rbx, [r11+30h]
0x18000d1b2  mov     rsi, [r11+38h]
0x18000d1b6  mov     rsp, r11
0x18000d1b9  pop     r15
0x18000d1bb  pop     r14
0x18000d1bd  pop     rdi
0x18000d1be  retn
```
