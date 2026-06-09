# Variant::toBuffer(tagVARIANT,uchar * *,ulong *)

- ea: `0x1800e9380`
- end: `0x1800e94dc`
- name: `?toBuffer@Variant@@SAJUtagVARIANT@@PEAPEAEPEAK@Z`
- size: `348`
- prototype: `static int(struct tagVARIANT *__struct_ptr, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800e9550`

## callees

- `0x18001dde0`
- `0x1800e9070`
- `0x1800e9294`
- `0x1800e9380`
- `0x180102cc6`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800e94ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800e94ae`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800e93d9`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800e93d9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800e942d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800e942d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800e9411`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800e9411`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e93f5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800e93f5`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800e94c1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800e94c1`

## pseudocode

```c
__int64 __fastcall Variant::toBuffer(struct tagVARIANT *a1, unsigned __int8 **a2, unsigned int *a3)
{
  VARTYPE vt; // ax
  unsigned int v4; // edi
  SAFEARRAY *parray; // rsi
  HRESULT LBound; // ebx
  unsigned __int8 *v9; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned __int16 *v11; // rax
  OLECHAR *v12; // r14
  VARIANTARG pvarSrc; // [rsp+20h] [rbp-20h] BYREF
  LONG plUbound; // [rsp+80h] [rbp+40h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+48h] BYREF
  unsigned int v17; // [rsp+90h] [rbp+50h] BYREF
  void *ppvData; // [rsp+98h] [rbp+58h] BYREF

  vt = a1->vt;
  v4 = 0;
  *a2 = 0;
  ppvData = 0;
  plUbound = 0;
  plLbound = 0;
  v17 = 0;
  if ( (vt & 0x11) != 0 && (vt & 0x2000) != 0 )
  {
    parray = a1->parray;
    if ( SafeArrayGetDim(parray) != 1 )
    {
      LBound = -2147467259;
      goto LABEL_14;
    }
    LBound = SafeArrayAccessData(parray, &ppvData);
    if ( LBound >= 0 )
    {
      LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
      if ( LBound >= 0 )
      {
        LBound = SafeArrayGetUBound(parray, 1u, &plUbound);
        if ( LBound >= 0 )
        {
          v4 = plUbound - plLbound + 1;
          if ( plUbound - plLbound != -1 )
          {
            v9 = (unsigned __int8 *)new_array_ne<unsigned char>(v4);
            *a2 = v9;
            if ( !v9 )
            {
              v4 = 0;
              LBound = -2147024882;
              goto LABEL_14;
            }
            memcpy_0(v9, ppvData, v4);
          }
          LBound = 0;
        }
      }
    }
  }
  else
  {
    LBound = 1;
    pRecInfo = a1->pRecInfo;
    parray = 0;
    *(_OWORD *)&pvarSrc.vt = *(_OWORD *)&a1->vt;
    pvarSrc.pRecInfo = pRecInfo;
    v11 = Variant::toBSTR(&pvarSrc);
    v12 = v11;
    if ( v11 )
    {
      LBound = BSTRToUTF8(v11, a2, &v17);
      SysFreeString(v12);
      v4 = v17;
    }
  }
LABEL_14:
  if ( ppvData )
    SafeArrayUnaccessData(parray);
  *a3 = v4;
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x1800e9380  push    rbp
0x1800e9382  push    rbx
0x1800e9383  push    rsi
0x1800e9384  push    rdi
0x1800e9385  push    r12
0x1800e9387  push    r14
0x1800e9389  push    r15
0x1800e938b  mov     rbp, rsp
0x1800e938e  sub     rsp, 40h
0x1800e9392  movzx   eax, word ptr [rcx]
0x1800e9395  xor     edi, edi
0x1800e9397  test    al, 11h
0x1800e9399  mov     [rdx], rdi
0x1800e939c  mov     r15, rdx
0x1800e939f  mov     [rbp+ppvData], 0
0x1800e93a7  mov     r12, r8
0x1800e93aa  mov     [rbp+plUbound], 0
0x1800e93b1  setnz   r8b
0x1800e93b5  mov     [rbp+plLbound], 0
0x1800e93bc  lea     edx, [rdi+0Dh]
0x1800e93bf  mov     [rbp+arg_10], edi
0x1800e93c2  bt      ax, dx
0x1800e93c6  setb    al
0x1800e93c9  test    al, r8b
0x1800e93cc  jz      loc_1800E9471
0x1800e93d2  mov     rsi, [rcx+8]
0x1800e93d6  mov     rcx, rsi; psa
0x1800e93d9  call    cs:__imp_SafeArrayGetDim
0x1800e93df  cmp     eax, 1
0x1800e93e2  jz      short loc_1800E93EE
0x1800e93e4  mov     ebx, 80004005h
0x1800e93e9  jmp     loc_1800E94B7
0x1800e93ee  lea     rdx, [rbp+ppvData]; ppvData
0x1800e93f2  mov     rcx, rsi; psa
0x1800e93f5  call    cs:__imp_SafeArrayAccessData
0x1800e93fb  mov     ebx, eax
0x1800e93fd  test    eax, eax
0x1800e93ff  js      loc_1800E94B7
0x1800e9405  lea     r8, [rbp+plLbound]; plLbound
0x1800e9409  mov     edx, 1; nDim
0x1800e940e  mov     rcx, rsi; psa
0x1800e9411  call    cs:__imp_SafeArrayGetLBound
0x1800e9417  mov     ebx, eax
0x1800e9419  test    eax, eax
0x1800e941b  js      loc_1800E94B7
0x1800e9421  lea     r8, [rbp+plUbound]; plUbound
0x1800e9425  mov     edx, 1; nDim
0x1800e942a  mov     rcx, rsi; psa
0x1800e942d  call    cs:__imp_SafeArrayGetUBound
0x1800e9433  mov     ebx, eax
0x1800e9435  test    eax, eax
0x1800e9437  js      short loc_1800E94B7
0x1800e9439  mov     edi, [rbp+plUbound]
0x1800e943c  sub     edi, [rbp+plLbound]
0x1800e943f  add     edi, 1
0x1800e9442  jz      short loc_1800E946D
0x1800e9444  mov     ecx, edi; unsigned __int64
0x1800e9446  mov     ebx, edi
0x1800e9448  call    ??$new_array_ne@E@@YAPEAE_J@Z; new_array_ne<uchar>(__int64)
0x1800e944d  mov     [r15], rax
0x1800e9450  test    rax, rax
0x1800e9453  jnz     short loc_1800E945E
0x1800e9455  xor     edi, edi
0x1800e9457  mov     ebx, 8007000Eh
0x1800e945c  jmp     short loc_1800E94B7
0x1800e945e  mov     rdx, [rbp+ppvData]; Src
0x1800e9462  mov     r8, rbx; Size
0x1800e9465  mov     rcx, rax; void *
0x1800e9468  call    memcpy_0
0x1800e946d  xor     ebx, ebx
0x1800e946f  jmp     short loc_1800E94B7
0x1800e9471  movaps  xmm0, xmmword ptr [rcx]
0x1800e9474  mov     ebx, 1
0x1800e9479  movsd   xmm1, qword ptr [rcx+10h]
0x1800e947e  xor     esi, esi
0x1800e9480  lea     rcx, [rbp+pvarSrc]; pvarSrc
0x1800e9484  movaps  xmmword ptr [rbp+pvarSrc], xmm0
0x1800e9488  movsd   qword ptr [rbp+pvarSrc+10h], xmm1
0x1800e948d  call    ?toBSTR@Variant@@SAPEAGUtagVARIANT@@@Z; Variant::toBSTR(tagVARIANT)
0x1800e9492  mov     r14, rax
0x1800e9495  test    rax, rax
0x1800e9498  jz      short loc_1800E94B7
0x1800e949a  lea     r8, [rbp+arg_10]; unsigned int *
0x1800e949e  mov     rdx, r15; unsigned __int8 **
0x1800e94a1  mov     rcx, rax; unsigned __int16 *
0x1800e94a4  call    ?BSTRToUTF8@@YAJPEAGPEAPEAEPEAK@Z; BSTRToUTF8(ushort *,uchar * *,ulong *)
0x1800e94a9  mov     rcx, r14; bstrString
0x1800e94ac  mov     ebx, eax
0x1800e94ae  call    cs:__imp_SysFreeString
0x1800e94b4  mov     edi, [rbp+arg_10]
0x1800e94b7  cmp     [rbp+ppvData], 0
0x1800e94bc  jz      short loc_1800E94C7
0x1800e94be  mov     rcx, rsi; psa
0x1800e94c1  call    cs:__imp_SafeArrayUnaccessData
0x1800e94c7  mov     [r12], edi
0x1800e94cb  mov     eax, ebx
0x1800e94cd  add     rsp, 40h
0x1800e94d1  pop     r15
0x1800e94d3  pop     r14
0x1800e94d5  pop     r12
0x1800e94d7  pop     rdi
0x1800e94d8  pop     rsi
0x1800e94d9  pop     rbx
0x1800e94da  pop     rbp
0x1800e94db  retn
```
