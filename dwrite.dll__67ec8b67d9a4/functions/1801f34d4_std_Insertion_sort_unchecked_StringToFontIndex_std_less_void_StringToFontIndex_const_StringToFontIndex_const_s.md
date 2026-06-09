# std::_Insertion_sort_unchecked<StringToFontIndex *,std::less<void>>(StringToFontIndex * const,StringToFontIndex * const,std::less<void>)

- ea: `0x1801f34d4`
- end: `0x1801f36c7`
- name: `??$_Insertion_sort_unchecked@PEAUStringToFontIndex@@U?$less@X@std@@@std@@YAPEAUStringToFontIndex@@QEAU1@0U?$less@X@0@@Z`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801f33e8`

## callees

- `0x1801644d0`
- `0x1801f34d4`
- `0x1801f37b0`
- `0x180212a70`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f356b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f3632`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f356b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1801f3632`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall std::_Insertion_sort_unchecked<StringToFontIndex *,std::less<void>>(_DWORD *a1, _DWORD *a2)
{
  _DWORD *v4; // rbx
  volatile signed __int32 *v5; // rdi
  unsigned int v6; // r12d
  int v7; // eax
  unsigned int cchCount2; // edx
  unsigned int v9; // r9d
  struct DWrite::RefString::Data **v10; // r14
  struct DWrite::RefString::Data **v11; // r15
  int v12; // eax
  _DWORD *v13; // r15
  struct DWrite::RefString::Data **v14; // r14
  unsigned int v15; // edx
  unsigned int v16; // r9d
  struct DWrite::RefString::Data *v18; // rcx

  if ( a1 != a2 )
  {
    v4 = a1 + 4;
    while ( 1 )
    {
      if ( v4 == a2 )
        return a2;
      v5 = *(volatile signed __int32 **)v4;
      _InterlockedIncrement(*(volatile signed __int32 **)v4);
      v6 = v4[2];
      if ( v5 == (volatile signed __int32 *)-8LL )
      {
        if ( *(_QWORD *)a1 == -8 )
          goto LABEL_16;
        v7 = -1;
      }
      else if ( *(_QWORD *)a1 == -8 )
      {
        v7 = 1;
      }
      else
      {
        cchCount2 = *(_DWORD *)(*(_QWORD *)a1 + 4LL);
        if ( cchCount2 > 0x7FFFFFFF || (v9 = *((_DWORD *)v5 + 1), v9 > 0x7FFFFFFF) )
LABEL_36:
          SafeIntExceptionHandler<Exception>::SafeIntOnOverflow();
        v7 = CompareStringW(0x7Fu, 1u, (PCNZWCH)v5 + 4, v9, (PCNZWCH)(*(_QWORD *)a1 + 8LL), cchCount2) - 2;
        if ( !v7 )
        {
LABEL_16:
          if ( v6 < a1[2] )
            goto LABEL_17;
LABEL_12:
          v10 = (struct DWrite::RefString::Data **)v4;
          v11 = (struct DWrite::RefString::Data **)v4;
          while ( 2 )
          {
            v10 -= 2;
            if ( v5 == (volatile signed __int32 *)-8LL )
            {
              if ( *v10 != (struct DWrite::RefString::Data *)-8LL )
              {
                v12 = -1;
                goto LABEL_26;
              }
LABEL_31:
              if ( v6 >= *((_DWORD *)v10 + 2) )
              {
LABEL_27:
                _InterlockedIncrement(v5);
                DWrite::RefString::DecrementRef(*v11);
                *v11 = (struct DWrite::RefString::Data *)v5;
                *((_DWORD *)v11 + 2) = v6;
                v4 += 4;
                goto LABEL_28;
              }
            }
            else
            {
              if ( *v10 == (struct DWrite::RefString::Data *)-8LL )
              {
                v12 = 1;
                goto LABEL_26;
              }
              v15 = *((_DWORD *)*v10 + 1);
              if ( v15 > 0x7FFFFFFF )
                goto LABEL_36;
              v16 = *((_DWORD *)v5 + 1);
              if ( v16 > 0x7FFFFFFF )
                goto LABEL_36;
              v12 = CompareStringW(0x7Fu, 1u, (PCNZWCH)v5 + 4, v16, (PCNZWCH)*v10 + 4, v15) - 2;
              if ( !v12 )
                goto LABEL_31;
LABEL_26:
              if ( v12 >= 0 )
                goto LABEL_27;
            }
            _InterlockedIncrement((volatile signed __int32 *)*v10);
            v18 = *v11;
            if ( *v11 != (struct DWrite::RefString::Data *)&DWrite::RefString::empty_
              && _InterlockedExchangeAdd((volatile signed __int32 *)v18, 0xFFFFFFFF) == 1 )
            {
              operator delete(v18);
            }
            *v11 = *v10;
            *((_DWORD *)v11 + 2) = *((_DWORD *)v10 + 2);
            v11 = v10;
            continue;
          }
        }
      }
      if ( v7 >= 0 )
        goto LABEL_12;
LABEL_17:
      v13 = v4 + 4;
      v14 = (struct DWrite::RefString::Data **)(v4 + 4);
      while ( v4 != a1 )
      {
        v4 -= 4;
        v14 -= 2;
        _InterlockedIncrement(*(volatile signed __int32 **)v4);
        DWrite::RefString::DecrementRef(*v14);
        *v14 = *(struct DWrite::RefString::Data **)v4;
        *((_DWORD *)v14 + 2) = v4[2];
      }
      _InterlockedIncrement(v5);
      DWrite::RefString::DecrementRef(*(struct DWrite::RefString::Data **)a1);
      *(_QWORD *)a1 = v5;
      a1[2] = v6;
      v4 = v13;
LABEL_28:
      DWrite::RefString::DecrementRef((struct DWrite::RefString::Data *)v5);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1801f34d4  push    rbx
0x1801f34d6  push    rbp
0x1801f34d7  push    rsi
0x1801f34d8  push    rdi
0x1801f34d9  push    r12
0x1801f34db  push    r13
0x1801f34dd  push    r14
0x1801f34df  push    r15
0x1801f34e1  sub     rsp, 48h
0x1801f34e5  mov     rbp, rdx
0x1801f34e8  mov     rsi, rcx
0x1801f34eb  cmp     rcx, rdx
0x1801f34ee  jz      loc_1801F366B
0x1801f34f4  lea     rbx, [rcx+10h]
0x1801f34f8  jmp     loc_1801F3662
0x1801f34fd  mov     rdi, [rbx]
0x1801f3500  mov     [rsp+88h+var_58], rdi
0x1801f3505  lock inc dword ptr [rdi]
0x1801f3508  mov     r12d, [rbx+8]
0x1801f350c  mov     [rsp+88h+var_50], r12d
0x1801f3511  mov     rcx, [rsi]
0x1801f3514  lea     rax, [rcx+8]
0x1801f3518  lea     r13, [rdi+8]
0x1801f351c  test    r13, r13
0x1801f351f  jnz     short loc_1801F352B
0x1801f3521  test    rax, rax
0x1801f3524  jz      short loc_1801F35A4
0x1801f3526  or      eax, 0FFFFFFFFh
0x1801f3529  jmp     short loc_1801F3576
0x1801f352b  test    rax, rax
0x1801f352e  jnz     short loc_1801F3537
0x1801f3530  mov     eax, 1
0x1801f3535  jmp     short loc_1801F3576
0x1801f3537  mov     edx, [rcx+4]
0x1801f353a  cmp     edx, 7FFFFFFFh
0x1801f3540  ja      loc_1801F36C1
0x1801f3546  mov     r9d, [rdi+4]; cchCount1
0x1801f354a  cmp     r9d, 7FFFFFFFh
0x1801f3551  ja      loc_1801F36C1
0x1801f3557  mov     [rsp+88h+cchCount2], edx; cchCount2
0x1801f355b  mov     [rsp+88h+lpString2], rax; lpString2
0x1801f3560  mov     r8, r13; lpString1
0x1801f3563  mov     edx, 1; dwCmpFlags
0x1801f3568  lea     ecx, [rdx+7Eh]; Locale
0x1801f356b  call    cs:__imp_CompareStringW
0x1801f3571  add     eax, 0FFFFFFFEh
0x1801f3574  jz      short loc_1801F35A4
0x1801f3576  shr     eax, 1Fh
0x1801f3579  test    al, al
0x1801f357b  jnz     short loc_1801F35AA
0x1801f357d  mov     r14, rbx
0x1801f3580  mov     r15, rbx
0x1801f3583  sub     r14, 10h
0x1801f3587  mov     rcx, [r14]
0x1801f358a  lea     rax, [rcx+8]
0x1801f358e  test    r13, r13
0x1801f3591  jnz     short loc_1801F35F2
0x1801f3593  test    rax, rax
0x1801f3596  jz      loc_1801F367F
0x1801f359c  or      eax, 0FFFFFFFFh
0x1801f359f  jmp     loc_1801F363D
0x1801f35a4  cmp     r12d, [rsi+8]
0x1801f35a8  jnb     short loc_1801F357D
0x1801f35aa  lea     r15, [rbx+10h]
0x1801f35ae  mov     r14, r15
0x1801f35b1  jmp     short loc_1801F35D6
0x1801f35b3  sub     rbx, 10h
0x1801f35b7  lea     r14, [r14-10h]
0x1801f35bb  mov     rax, [rbx]
0x1801f35be  lock inc dword ptr [rax]
0x1801f35c1  mov     rcx, [r14]; struct DWrite::RefString::Data *
0x1801f35c4  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801f35c9  mov     rax, [rbx]
0x1801f35cc  mov     [r14], rax
0x1801f35cf  mov     eax, [rbx+8]
0x1801f35d2  mov     [r14+8], eax
0x1801f35d6  cmp     rbx, rsi
0x1801f35d9  jnz     short loc_1801F35B3
0x1801f35db  lock inc dword ptr [rdi]
0x1801f35de  mov     rcx, [rsi]; struct DWrite::RefString::Data *
0x1801f35e1  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801f35e6  mov     [rsi], rdi
0x1801f35e9  mov     [rsi+8], r12d
0x1801f35ed  mov     rbx, r15
0x1801f35f0  jmp     short loc_1801F365A
0x1801f35f2  test    rax, rax
0x1801f35f5  jnz     short loc_1801F35FE
0x1801f35f7  mov     eax, 1
0x1801f35fc  jmp     short loc_1801F363D
0x1801f35fe  mov     edx, [rcx+4]
0x1801f3601  cmp     edx, 7FFFFFFFh
0x1801f3607  ja      loc_1801F36C1
0x1801f360d  mov     r9d, [rdi+4]; cchCount1
0x1801f3611  cmp     r9d, 7FFFFFFFh
0x1801f3618  ja      loc_1801F36C1
0x1801f361e  mov     [rsp+88h+cchCount2], edx; cchCount2
0x1801f3622  mov     [rsp+88h+lpString2], rax; lpString2
0x1801f3627  mov     r8, r13; lpString1
0x1801f362a  mov     edx, 1; dwCmpFlags
0x1801f362f  lea     ecx, [rdx+7Eh]; Locale
0x1801f3632  call    cs:__imp_CompareStringW
0x1801f3638  add     eax, 0FFFFFFFEh
0x1801f363b  jz      short loc_1801F367F
0x1801f363d  shr     eax, 1Fh
0x1801f3640  test    al, al
0x1801f3642  jnz     short loc_1801F3685
0x1801f3644  lock inc dword ptr [rdi]
0x1801f3647  mov     rcx, [r15]; struct DWrite::RefString::Data *
0x1801f364a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801f364f  mov     [r15], rdi
0x1801f3652  mov     [r15+8], r12d
0x1801f3656  add     rbx, 10h
0x1801f365a  mov     rcx, rdi; struct DWrite::RefString::Data *
0x1801f365d  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1801f3662  cmp     rbx, rbp
0x1801f3665  jnz     loc_1801F34FD
0x1801f366b  mov     rax, rbp
0x1801f366e  add     rsp, 48h
0x1801f3672  pop     r15
0x1801f3674  pop     r14
0x1801f3676  pop     r13
0x1801f3678  pop     r12
0x1801f367a  pop     rdi
0x1801f367b  pop     rsi
0x1801f367c  pop     rbp
0x1801f367d  pop     rbx
0x1801f367e  retn
0x1801f367f  cmp     r12d, [r14+8]
0x1801f3683  jnb     short loc_1801F3644
0x1801f3685  mov     rax, [r14]
0x1801f3688  lock inc dword ptr [rax]
0x1801f368b  mov     rcx, [r15]; Block
0x1801f368e  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x1801f3695  cmp     rcx, rax
0x1801f3698  jz      short loc_1801F36AB
0x1801f369a  or      eax, 0FFFFFFFFh
0x1801f369d  lock xadd [rcx], eax
0x1801f36a1  cmp     eax, 1
0x1801f36a4  jnz     short loc_1801F36AB
0x1801f36a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801f36ab  mov     rax, [r14]
0x1801f36ae  mov     [r15], rax
0x1801f36b1  mov     eax, [r14+8]
0x1801f36b5  mov     [r15+8], eax
0x1801f36b9  mov     r15, r14
0x1801f36bc  jmp     loc_1801F3583
0x1801f36c1  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
```
