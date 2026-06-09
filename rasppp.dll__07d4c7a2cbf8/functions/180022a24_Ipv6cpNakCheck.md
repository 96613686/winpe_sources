# Ipv6cpNakCheck

- ea: `0x180022a24`
- end: `0x180022cee`
- name: `Ipv6cpNakCheck`
- size: `714`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180022770`

## callees

- `0x180001460`
- `0x180020574`
- `0x180022504`
- `0x180022a24`
- `0x180023550`
- `0x180033010`

## string_xrefs

- `0x180022c5d`: `Ipv6cpNakCheck: Already allocated what user wants. Just returning!`

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
  if ( *((_QWORD *)&xmmword_18004C800 + 1) )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
      gRasIpv6cpEtwContext,
      *((_QWORD *)&xmmword_18004C800 + 1),
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
        if ( *((_QWORD *)&xmmword_18004C800 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasIpv6cpTemplateFunc)(
            gRasIpv6cpEtwContext,
            *((_QWORD *)&xmmword_18004C800 + 1),
            L"Ipv6cpNakCheck: Already allocated what user wants. Just returning!");
        goto LABEL_43;
      }
      if ( (_QWORD)xmmword_18004C520 )
      {
        v15 = *(_QWORD *)(a1 + 8);
        v16 = *(_QWORD *)(a1 + 72);
        v23 = *(_OWORD *)(a1 + 2084);
        v17 = ((__int64 (__fastcall *)(__int128 *, __int64, __int64, _BYTE *, __int64 *, __int64, __int64, __int64, _DWORD))xmmword_18004C520)(
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
  v21 = *((_QWORD *)&xmmword_18004C800 + 1);
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
0x180022a24  mov     [rsp+arg_18], rbx
0x180022a29  push    rbp
0x180022a2a  push    rsi
0x180022a2b  push    rdi
0x180022a2c  push    r12
0x180022a2e  push    r13
0x180022a30  push    r14
0x180022a32  push    r15
0x180022a34  sub     rsp, 80h
0x180022a3b  mov     rax, cs:__security_cookie
0x180022a42  xor     rax, rsp
0x180022a45  mov     [rsp+0B8h+var_40], rax
0x180022a4a  movzx   r15d, byte ptr [rdx+2]
0x180022a4f  lea     r13, [rdx+4]
0x180022a53  mov     rax, [rsp+0B8h+arg_20]
0x180022a5b  lea     rsi, [r8+4]
0x180022a5f  mov     [rsp+0B8h+var_68], rax
0x180022a64  xor     edi, edi
0x180022a66  movzx   eax, byte ptr [rdx+3]
0x180022a6a  mov     rbx, rcx
0x180022a6d  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180022a74  sub     ax, 4
0x180022a78  mov     ecx, 100h
0x180022a7d  mov     [rsp+0B8h+var_48], rdi
0x180022a82  imul    r15d, ecx
0x180022a86  xor     ebp, ebp
0x180022a88  mov     r12, r8
0x180022a8b  add     r15w, ax
0x180022a8f  test    rdx, rdx
0x180022a92  jz      short loc_180022AAE
0x180022a94  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022a9b  lea     r8, aIpv6cpnakcheck; "Ipv6cpNakCheck"
0x180022aa2  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aae  cmp     r15w, 2
0x180022ab3  jb      loc_180022C79
0x180022ab9  cmp     byte ptr [r13+0], 1
0x180022abe  jnz     loc_180022C24
0x180022ac4  cmp     r15w, 0Ah
0x180022ac9  jnz     loc_180022C72
0x180022acf  cmp     dword ptr [rbx], 0
0x180022ad2  lea     r14, [r13+2]
0x180022ad6  jz      loc_180022B76
0x180022adc  cmp     qword ptr [rbx+50h], 0
0x180022ae1  jz      short loc_180022AF0
0x180022ae3  mov     rax, [r14]
0x180022ae6  cmp     rax, [rbx+50h]
0x180022aea  jz      loc_180022C4A
0x180022af0  cmp     qword ptr cs:xmmword_18004C520, 0
0x180022af8  jnz     short loc_180022B01
0x180022afa  mov     ebp, 10DDh
0x180022aff  jmp     short loc_180022B76
0x180022b01  movups  xmm0, xmmword ptr [rbx+824h]
0x180022b08  mov     [rsp+0B8h+var_78], 0
0x180022b10  lea     rcx, [rbx+78h]
0x180022b14  mov     [rsp+0B8h+var_80], rcx
0x180022b19  lea     rdx, [rbx+6EAh]
0x180022b20  mov     [rsp+0B8h+var_88], rdx
0x180022b25  lea     r8, [rbx+4E8h]
0x180022b2c  mov     rdx, [rbx+8]
0x180022b30  lea     rax, [rsp+0B8h+var_48]
0x180022b35  mov     [rsp+0B8h+var_90], r8
0x180022b3a  lea     rcx, [rsp+0B8h+var_58]
0x180022b3f  mov     r8, [rbx+48h]
0x180022b43  mov     r9, r14
0x180022b46  mov     [rsp+0B8h+var_98], rax
0x180022b4b  mov     rax, qword ptr cs:xmmword_18004C520
0x180022b52  movdqu  [rsp+0B8h+var_58], xmm0
0x180022b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b5d  mov     ebp, eax
0x180022b5f  test    eax, eax
0x180022b61  jnz     short loc_180022B6F
0x180022b63  mov     rax, [r14]
0x180022b66  cmp     rax, [rsp+0B8h+var_48]
0x180022b6b  jz      short loc_180022B76
0x180022b6d  jmp     short loc_180022BBD
0x180022b6f  cmp     eax, 7Fh
0x180022b72  jnz     short loc_180022B76
0x180022b74  xor     ebp, ebp
0x180022b76  test    edi, edi
0x180022b78  jnz     short loc_180022BC2
0x180022b7a  test    byte ptr [rbx+0A8h], 1
0x180022b81  jz      short loc_180022B92
0x180022b83  mov     rax, [r14]
0x180022b86  cmp     rax, [rbx+50h]
0x180022b8a  jz      loc_180022C24
0x180022b90  jmp     short loc_180022BBD
0x180022b92  lea     rax, [rbx+28h]
0x180022b96  cmp     [rax], rax
0x180022b99  jz      short loc_180022BA9
0x180022b9b  mov     rax, [r14]
0x180022b9e  test    rax, rax
0x180022ba1  jz      short loc_180022BBD
0x180022ba3  cmp     rax, [rbx+48h]
0x180022ba7  jz      short loc_180022BBD
0x180022ba9  cmp     dword ptr [rbx], 0
0x180022bac  jz      short loc_180022C24
0x180022bae  mov     rdx, r14
0x180022bb1  mov     rcx, rbx
0x180022bb4  call    IsRemoteInterfaceIdUnique
0x180022bb9  test    eax, eax
0x180022bbb  jnz     short loc_180022C24
0x180022bbd  mov     edi, 1
0x180022bc2  test    byte ptr [rbx+0A8h], 1
0x180022bc9  jnz     short loc_180022C0F
0x180022bcb  cmp     dword ptr [rbx], 0
0x180022bce  jz      short loc_180022BE3
0x180022bd0  mov     rax, [rsp+0B8h+var_48]
0x180022bd5  test    rax, rax
0x180022bd8  jz      short loc_180022BE3
0x180022bda  lea     r14, [rbx+50h]
0x180022bde  mov     [r14], rax
0x180022be1  jmp     short loc_180022C03
0x180022be3  lea     r14, [rbx+50h]
0x180022be7  mov     r8, rbx
0x180022bea  mov     rcx, r14; pbBuffer
0x180022bed  lea     rdx, IsRemoteInterfaceIdUnique
0x180022bf4  call    Ipv6cpGetUniqueInterfaceId
0x180022bf9  mov     ebp, eax
0x180022bfb  test    eax, eax
0x180022bfd  jnz     loc_180022C97
0x180022c03  mov     rdx, [r14]
0x180022c06  lea     rcx, [rbx+38h]
0x180022c0a  call    InsertInterfaceIdInList
0x180022c0f  mov     word ptr [rsi], 0A01h
0x180022c14  mov     rcx, [rbx+50h]
0x180022c18  mov     [rsi+2], rcx
0x180022c1c  movzx   eax, byte ptr [r13+1]
0x180022c21  add     rsi, rax
0x180022c24  movzx   ecx, byte ptr [r13+1]
0x180022c29  test    cl, cl
0x180022c2b  jz      short loc_180022C3C
0x180022c2d  movzx   eax, cx
0x180022c30  cmp     cx, r15w
0x180022c34  jnb     short loc_180022C3C
0x180022c36  sub     r15w, ax
0x180022c3a  jmp     short loc_180022C42
0x180022c3c  xor     eax, eax
0x180022c3e  movzx   r15d, ax
0x180022c42  add     r13, rcx
0x180022c45  jmp     loc_180022AAE
0x180022c4a  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180022c51  test    rdx, rdx
0x180022c54  jz      short loc_180022C97
0x180022c56  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022c5d  lea     r8, aIpv6cpnakcheck_0; "Ipv6cpNakCheck: Already allocated what "...
0x180022c64  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c70  jmp     short loc_180022C97
0x180022c72  mov     ebp, 2D2h
0x180022c77  jmp     short loc_180022C97
0x180022c79  test    edi, edi
0x180022c7b  jz      short loc_180022C97
0x180022c7d  sub     si, r12w
0x180022c81  mov     byte ptr [r12], 3
0x180022c86  movzx   eax, si
0x180022c89  mov     [r12+3], sil
0x180022c8e  shr     ax, 8
0x180022c92  mov     [r12+2], al
0x180022c97  mov     rax, [rsp+0B8h+var_68]
0x180022c9c  mov     rdx, qword ptr cs:xmmword_18004C800+8
0x180022ca3  mov     [rax], edi
0x180022ca5  test    rdx, rdx
0x180022ca8  jz      short loc_180022CC4
0x180022caa  mov     rcx, cs:gRasIpv6cpEtwContext
0x180022cb1  lea     r8, aIp6cpnakcheckD; "Ip6CpNakCheck done."
0x180022cb8  mov     rax, cs:gRasIpv6cpTemplateFunc
0x180022cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cc4  mov     eax, ebp
0x180022cc6  mov     rcx, [rsp+0B8h+var_40]
0x180022ccb  xor     rcx, rsp; StackCookie
0x180022cce  call    __security_check_cookie
0x180022cd3  mov     rbx, [rsp+0B8h+arg_18]
0x180022cdb  add     rsp, 80h
0x180022ce2  pop     r15
0x180022ce4  pop     r14
0x180022ce6  pop     r13
0x180022ce8  pop     r12
0x180022cea  pop     rdi
0x180022ceb  pop     rsi
0x180022cec  pop     rbp
0x180022ced  retn
```
