# Ipv6cpNakCheck

- ea: `0x180023704`
- end: `0x1800239cf`
- name: `Ipv6cpNakCheck`
- size: `715`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180023450`

## callees

- `0x180001460`
- `0x180021184`
- `0x1800231e4`
- `0x180023704`
- `0x180024260`
- `0x180034010`

## string_xrefs

- `0x18002393d`: `Ipv6cpNakCheck: Already allocated what user wants. Just returning!`

## pseudocode

```c
__int64 __fastcall Ipv6cpNakCheck(__int64 a1, unsigned __int8 *a2, _BYTE *a3, __int64 a4, int *a5)
{
  __int16 v5; // r15
  _BYTE *v6; // r13
  _BYTE *v7; // rsi
  int v8; // edi
  __int16 v9; // ax
  unsigned int UniqueInterfaceId; // ebp
  unsigned __int16 v13; // r15
  _QWORD *v14; // r14
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int v17; // eax
  _QWORD *v18; // r14
  __int64 v19; // rcx
  __int16 v20; // si
  __int64 v21; // rdx
  __int128 v23; // [rsp+60h] [rbp-58h] BYREF
  __int64 v24; // [rsp+70h] [rbp-48h] BYREF

  v5 = a2[2];
  v6 = a2 + 4;
  v7 = a3 + 4;
  v8 = 0;
  v9 = a2[3];
  v24 = 0;
  UniqueInterfaceId = 0;
  v13 = v9 - 4 + (v5 << 8);
  if ( *((_QWORD *)&xmmword_18004D800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004D800 + 1),
      L"Ipv6cpNakCheck");
  while ( v13 >= 2u )
  {
    if ( *v6 != 1 )
      goto LABEL_33;
    if ( v13 != 10 )
    {
      UniqueInterfaceId = 722;
      goto LABEL_43;
    }
    v14 = v6 + 2;
    if ( *(_DWORD *)a1 )
    {
      if ( *(_QWORD *)(a1 + 80) && *v14 == *(_QWORD *)(a1 + 80) )
      {
        if ( *((_QWORD *)&xmmword_18004D800 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            *((_QWORD *)&xmmword_18004D800 + 1),
            L"Ipv6cpNakCheck: Already allocated what user wants. Just returning!");
        goto LABEL_43;
      }
      if ( (_QWORD)xmmword_18004D520 )
      {
        v15 = *(_QWORD *)(a1 + 8);
        v16 = *(_QWORD *)(a1 + 72);
        v23 = *(_OWORD *)(a1 + 2084);
        v17 = ((__int64 (__fastcall *)(__int128 *, __int64, __int64, _BYTE *, __int64 *, __int64, __int64, __int64, _DWORD))xmmword_18004D520)(
                &v23,
                v15,
                v16,
                v6 + 2,
                &v24,
                a1 + 1256,
                a1 + 1770,
                a1 + 120,
                0);
        UniqueInterfaceId = v17;
        if ( v17 )
        {
          if ( v17 == 127 )
            UniqueInterfaceId = 0;
        }
        else if ( *v14 != v24 )
        {
          goto LABEL_25;
        }
      }
      else
      {
        UniqueInterfaceId = 4317;
      }
    }
    if ( !v8 )
    {
      if ( (*(_BYTE *)(a1 + 168) & 1) != 0 )
      {
        if ( *v14 == *(_QWORD *)(a1 + 80) )
          goto LABEL_33;
      }
      else if ( (*(_QWORD *)(a1 + 40) == a1 + 40 || *v14 && *v14 != *(_QWORD *)(a1 + 72))
             && (!*(_DWORD *)a1 || (unsigned int)IsRemoteInterfaceIdUnique(a1, v6 + 2)) )
      {
        goto LABEL_33;
      }
LABEL_25:
      v8 = 1;
    }
    if ( (*(_BYTE *)(a1 + 168) & 1) == 0 )
    {
      if ( *(_DWORD *)a1 && v24 )
      {
        v18 = (_QWORD *)(a1 + 80);
        *(_QWORD *)(a1 + 80) = v24;
      }
      else
      {
        v18 = (_QWORD *)(a1 + 80);
        UniqueInterfaceId = Ipv6cpGetUniqueInterfaceId((BYTE *)(a1 + 80));
        if ( UniqueInterfaceId )
          goto LABEL_43;
      }
      InsertInterfaceIdInList(a1 + 56, *v18);
    }
    *(_WORD *)v7 = 2561;
    *(_QWORD *)(v7 + 2) = *(_QWORD *)(a1 + 80);
    v7 += (unsigned __int8)v6[1];
LABEL_33:
    v19 = (unsigned __int8)v6[1];
    if ( (_BYTE)v19 && (unsigned __int16)v19 < v13 )
      v13 -= v19;
    else
      v13 = 0;
    v6 += v19;
  }
  if ( v8 )
  {
    v20 = (_WORD)v7 - (_WORD)a3;
    *a3 = 3;
    a3[3] = v20;
    a3[2] = HIBYTE(v20);
  }
LABEL_43:
  v21 = *((_QWORD *)&xmmword_18004D800 + 1);
  *a5 = v8;
  if ( v21 )
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      v21,
      L"Ip6CpNakCheck done.");
  return UniqueInterfaceId;
}

```

## disassembly

```asm
0x180023704  mov     [rsp+arg_18], rbx
0x180023709  push    rbp
0x18002370a  push    rsi
0x18002370b  push    rdi
0x18002370c  push    r12
0x18002370e  push    r13
0x180023710  push    r14
0x180023712  push    r15
0x180023714  sub     rsp, 80h
0x18002371b  mov     rax, cs:__security_cookie
0x180023722  xor     rax, rsp
0x180023725  mov     [rsp+0B8h+var_40], rax
0x18002372a  movzx   r15d, byte ptr [rdx+2]
0x18002372f  lea     r13, [rdx+4]
0x180023733  mov     rax, [rsp+0B8h+arg_20]
0x18002373b  lea     rsi, [r8+4]
0x18002373f  mov     [rsp+0B8h+var_68], rax
0x180023744  xor     edi, edi
0x180023746  movzx   eax, byte ptr [rdx+3]
0x18002374a  mov     rbx, rcx
0x18002374d  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180023754  sub     ax, 4
0x180023758  mov     ecx, 100h
0x18002375d  mov     [rsp+0B8h+var_48], rdi
0x180023762  imul    r15d, ecx
0x180023766  xor     ebp, ebp
0x180023768  mov     r12, r8
0x18002376b  add     r15w, ax
0x18002376f  test    rdx, rdx
0x180023772  jz      short loc_18002378E
0x180023774  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002377b  lea     r8, aIpv6cpnakcheck; "Ipv6cpNakCheck"
0x180023782  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180023789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002378e  cmp     r15w, 2
0x180023793  jb      loc_180023959
0x180023799  cmp     byte ptr [r13+0], 1
0x18002379e  jnz     loc_180023904
0x1800237a4  cmp     r15w, 0Ah
0x1800237a9  jnz     loc_180023952
0x1800237af  cmp     dword ptr [rbx], 0
0x1800237b2  lea     r14, [r13+2]
0x1800237b6  jz      loc_180023856
0x1800237bc  cmp     qword ptr [rbx+50h], 0
0x1800237c1  jz      short loc_1800237D0
0x1800237c3  mov     rax, [r14]
0x1800237c6  cmp     rax, [rbx+50h]
0x1800237ca  jz      loc_18002392A
0x1800237d0  cmp     qword ptr cs:xmmword_18004D520, 0
0x1800237d8  jnz     short loc_1800237E1
0x1800237da  mov     ebp, 10DDh
0x1800237df  jmp     short loc_180023856
0x1800237e1  movups  xmm0, xmmword ptr [rbx+824h]
0x1800237e8  mov     [rsp+0B8h+var_78], 0
0x1800237f0  lea     rcx, [rbx+78h]
0x1800237f4  mov     [rsp+0B8h+var_80], rcx
0x1800237f9  lea     rdx, [rbx+6EAh]
0x180023800  mov     [rsp+0B8h+var_88], rdx
0x180023805  lea     r8, [rbx+4E8h]
0x18002380c  mov     rdx, [rbx+8]
0x180023810  lea     rax, [rsp+0B8h+var_48]
0x180023815  mov     [rsp+0B8h+var_90], r8
0x18002381a  lea     rcx, [rsp+0B8h+var_58]
0x18002381f  mov     r8, [rbx+48h]
0x180023823  mov     r9, r14
0x180023826  mov     [rsp+0B8h+var_98], rax
0x18002382b  mov     rax, qword ptr cs:xmmword_18004D520
0x180023832  movdqu  [rsp+0B8h+var_58], xmm0
0x180023838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002383d  mov     ebp, eax
0x18002383f  test    eax, eax
0x180023841  jnz     short loc_18002384F
0x180023843  mov     rax, [r14]
0x180023846  cmp     rax, [rsp+0B8h+var_48]
0x18002384b  jz      short loc_180023856
0x18002384d  jmp     short loc_18002389D
0x18002384f  cmp     eax, 7Fh
0x180023852  jnz     short loc_180023856
0x180023854  xor     ebp, ebp
0x180023856  test    edi, edi
0x180023858  jnz     short loc_1800238A2
0x18002385a  test    byte ptr [rbx+0A8h], 1
0x180023861  jz      short loc_180023872
0x180023863  mov     rax, [r14]
0x180023866  cmp     rax, [rbx+50h]
0x18002386a  jz      loc_180023904
0x180023870  jmp     short loc_18002389D
0x180023872  lea     rax, [rbx+28h]
0x180023876  cmp     [rax], rax
0x180023879  jz      short loc_180023889
0x18002387b  mov     rax, [r14]
0x18002387e  test    rax, rax
0x180023881  jz      short loc_18002389D
0x180023883  cmp     rax, [rbx+48h]
0x180023887  jz      short loc_18002389D
0x180023889  cmp     dword ptr [rbx], 0
0x18002388c  jz      short loc_180023904
0x18002388e  mov     rdx, r14
0x180023891  mov     rcx, rbx
0x180023894  call    IsRemoteInterfaceIdUnique
0x180023899  test    eax, eax
0x18002389b  jnz     short loc_180023904
0x18002389d  mov     edi, 1
0x1800238a2  test    byte ptr [rbx+0A8h], 1
0x1800238a9  jnz     short loc_1800238EF
0x1800238ab  cmp     dword ptr [rbx], 0
0x1800238ae  jz      short loc_1800238C3
0x1800238b0  mov     rax, [rsp+0B8h+var_48]
0x1800238b5  test    rax, rax
0x1800238b8  jz      short loc_1800238C3
0x1800238ba  lea     r14, [rbx+50h]
0x1800238be  mov     [r14], rax
0x1800238c1  jmp     short loc_1800238E3
0x1800238c3  lea     r14, [rbx+50h]
0x1800238c7  mov     r8, rbx
0x1800238ca  mov     rcx, r14; pbBuffer
0x1800238cd  lea     rdx, IsRemoteInterfaceIdUnique
0x1800238d4  call    Ipv6cpGetUniqueInterfaceId
0x1800238d9  mov     ebp, eax
0x1800238db  test    eax, eax
0x1800238dd  jnz     loc_180023977
0x1800238e3  mov     rdx, [r14]
0x1800238e6  lea     rcx, [rbx+38h]
0x1800238ea  call    InsertInterfaceIdInList
0x1800238ef  mov     word ptr [rsi], 0A01h
0x1800238f4  mov     rcx, [rbx+50h]
0x1800238f8  mov     [rsi+2], rcx
0x1800238fc  movzx   eax, byte ptr [r13+1]
0x180023901  add     rsi, rax
0x180023904  movzx   ecx, byte ptr [r13+1]
0x180023909  test    cl, cl
0x18002390b  jz      short loc_18002391C
0x18002390d  movzx   eax, cx
0x180023910  cmp     cx, r15w
0x180023914  jnb     short loc_18002391C
0x180023916  sub     r15w, ax
0x18002391a  jmp     short loc_180023922
0x18002391c  xor     eax, eax
0x18002391e  movzx   r15d, ax
0x180023922  add     r13, rcx
0x180023925  jmp     loc_18002378E
0x18002392a  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180023931  test    rdx, rdx
0x180023934  jz      short loc_180023977
0x180023936  mov     rcx, cs:gRasIpv6cpEtwContext
0x18002393d  lea     r8, aIpv6cpnakcheck_0; "Ipv6cpNakCheck: Already allocated what "...
0x180023944  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002394b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023950  jmp     short loc_180023977
0x180023952  mov     ebp, 2D2h
0x180023957  jmp     short loc_180023977
0x180023959  test    edi, edi
0x18002395b  jz      short loc_180023977
0x18002395d  sub     si, r12w
0x180023961  mov     byte ptr [r12], 3
0x180023966  movzx   eax, si
0x180023969  mov     [r12+3], sil
0x18002396e  shr     ax, 8
0x180023972  mov     [r12+2], al
0x180023977  mov     rax, [rsp+0B8h+var_68]
0x18002397c  mov     rdx, qword ptr cs:xmmword_18004D800+8
0x180023983  mov     [rax], edi
0x180023985  test    rdx, rdx
0x180023988  jz      short loc_1800239A4
0x18002398a  mov     rcx, cs:gRasIpv6cpEtwContext
0x180023991  lea     r8, aIp6cpnakcheckD; "Ip6CpNakCheck done."
0x180023998  mov     rax, cs:gRasIpv6cpTemplateFunc
0x18002399f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239a4  mov     eax, ebp
0x1800239a6  mov     rcx, [rsp+0B8h+var_40]
0x1800239ab  xor     rcx, rsp; StackCookie
0x1800239ae  call    __security_check_cookie
0x1800239b3  mov     rbx, [rsp+0B8h+arg_18]
0x1800239bb  add     rsp, 80h
0x1800239c2  pop     r15
0x1800239c4  pop     r14
0x1800239c6  pop     r13
0x1800239c8  pop     r12
0x1800239ca  pop     rdi
0x1800239cb  pop     rsi
0x1800239cc  pop     rbp
0x1800239cd  retn
```
