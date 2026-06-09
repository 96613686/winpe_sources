# CClfsRequest::DeleteContainer(void)

- ea: `0x1400408b0`
- end: `0x140040ba0`
- name: `?DeleteContainer@CClfsRequest@@AEAAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14006c874`

## callees

- `0x14000bd70`
- `0x140012418`
- `0x140017f20`
- `0x1400408b0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140040b69`
- `ntoskrnl!KeSetEvent` at `0x14007e990`
- `ntoskrnl!KeSetEvent` at `0x140040b69`
- `ntoskrnl!KeSetEvent` at `0x14007e990`

## string_xrefs

- `0x1400409a3`: `CClfsRequest::DeleteContainer`

## pseudocode

```c
__int64 __fastcall CClfsRequest::DeleteContainer(CClfsRequest *this)
{
  int v2; // ebx
  unsigned int v3; // edi
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 v6; // rax
  __int64 v7; // r12
  _WORD *v8; // r15
  const unsigned __int16 *v9; // r14
  __int64 v10; // r13
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r14
  char v14; // r12
  __int64 v15; // rcx
  _WORD *i; // rax
  int v17; // eax
  struct _KEVENT *v18; // rcx
  __int64 v20; // [rsp+48h] [rbp-60h]
  __int128 v21; // [rsp+60h] [rbp-48h] BYREF
  char v22; // [rsp+B8h] [rbp+10h]
  __int64 v23; // [rsp+B8h] [rbp+10h]
  unsigned __int64 v24; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+20h]

  v21 = 0u;
  v2 = 0;
  v3 = 0;
  v4 = *((_QWORD *)this + 6);
  v20 = *(_QWORD *)(v4 + 184);
  v5 = *(unsigned int *)(v20 + 16);
  if ( (unsigned int)v5 >= 0x10 )
  {
    v6 = *(_QWORD *)(v4 + 24);
    v25 = v6;
    v22 = *(_BYTE *)(v6 + 10);
    v3 = 0;
    v24 = 0;
    v7 = 0;
    v8 = (_WORD *)(v6 + 16);
    v9 = (const unsigned __int16 *)(v6 + 16);
    while ( v3 < *(unsigned __int16 *)(v6 + 8) )
    {
      v2 = RtlStringCbLengthW(v9, v5 - v7 - 16, &v24);
      if ( v2 < 0 )
      {
LABEL_6:
        v2 = -1073741592;
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slS(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          24,
          (unsigned int)WPP_e99822b18e20334f40b669f21686eb29_Traceguids,
          (unsigned int)"CClfsRequest::DeleteContainer",
          219,
          (__int64)v9);
      }
      v7 += v24 + 2;
      v9 = (const unsigned __int16 *)((char *)v9 + v24 + 2);
      ++v3;
      v6 = v25;
    }
    v10 = *(_QWORD *)(v20 + 48);
    v11 = *(_QWORD *)(*(_QWORD *)(v10 + 24) + 120LL);
    *((_QWORD *)this + 18) = v11;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 64LL))(v11);
    v3 = 0;
    v13 = v25;
    v14 = v22;
    while ( v3 < *(unsigned __int16 *)(v13 + 8) )
    {
      v2 = 0;
      v21 = 0;
      if ( v8 )
      {
        v15 = 0x7FFF;
        for ( i = v8; v15 && *i; ++i )
          --v15;
        if ( !v15 )
          v2 = -1073741811;
        if ( v2 < 0 )
          v23 = 0;
        else
          v23 = 0x7FFF - v15;
        if ( v2 >= 0 )
        {
          v25 = 2 * v23;
          LOWORD(v21) = 2 * v23;
          WORD1(v21) = 2 * v23 + 2;
          *((_QWORD *)&v21 + 1) = v8;
        }
      }
      if ( v2 < 0 )
        goto LABEL_6;
      LOBYTE(v12) = v14;
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int128 *, __int64))(**((_QWORD **)this + 18) + 224LL))(
              *((_QWORD *)this + 18),
              v10,
              &v21,
              v12);
      if ( v17 < 0 )
      {
        v2 = v17;
        if ( v17 != -1072037871 )
          break;
      }
      v8 += ((unsigned __int64)(unsigned __int16)v21 >> 1) + 1;
      ++v3;
    }
  }
  else
  {
    v2 = -1073741306;
  }
LABEL_29:
  if ( (*((_BYTE *)this + 16) & 1) != 0 )
  {
    v18 = *(struct _KEVENT **)(*((_QWORD *)this + 6) + 80LL);
    if ( v18 )
      KeSetEvent(v18, 0, 0);
  }
  if ( (*((_DWORD *)this + 4) & 4) == 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 48LL) = v2;
    *(_QWORD *)(*((_QWORD *)this + 6) + 56LL) = v3;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400408b0  mov     rax, rsp
0x1400408b3  mov     [rax+8], rcx
0x1400408b7  push    rbx
0x1400408b8  push    rsi
0x1400408b9  push    rdi
0x1400408ba  push    r12
0x1400408bc  push    r13
0x1400408be  push    r14
0x1400408c0  push    r15
0x1400408c2  sub     rsp, 70h
0x1400408c6  mov     rsi, rcx
0x1400408c9  xor     r10d, r10d
0x1400408cc  mov     [rax-48h], r10
0x1400408d0  mov     [rax-40h], r10
0x1400408d4  mov     ebx, r10d
0x1400408d7  mov     [rax-78h], ebx
0x1400408da  mov     edi, r10d
0x1400408dd  mov     [rax-74h], r10d
0x1400408e1  mov     rax, [rcx+30h]
0x1400408e5  mov     rcx, [rax+0B8h]
0x1400408ec  mov     [rsp+0A8h+var_60], rcx
0x1400408f1  mov     r13d, [rcx+10h]
0x1400408f5  cmp     r13d, 10h
0x1400408f9  jnb     short loc_140040909
0x1400408fb  mov     ebx, 0C0000206h
0x140040900  mov     [rsp+0A8h+var_78], ebx
0x140040904  jmp     loc_140040B51
0x140040909  mov     rax, [rax+18h]
0x14004090d  mov     [rsp+0A8h+arg_18], rax
0x140040915  mov     cl, [rax+0Ah]
0x140040918  mov     byte ptr [rsp+0A8h+arg_8], cl
0x14004091f  mov     edi, r10d
0x140040922  mov     [rsp+0A8h+var_74], r10d
0x140040927  mov     [rsp+0A8h+arg_10], r10
0x14004092f  mov     r12, r10
0x140040932  lea     r15, [rax+10h]
0x140040936  mov     r14, r15
0x140040939  mov     [rsp+0A8h+var_68], r15
0x14004093e  movzx   eax, word ptr [rax+8]
0x140040942  cmp     edi, eax
0x140040944  jnb     loc_1400409ED
0x14004094a  mov     rdx, r13
0x14004094d  sub     rdx, r12
0x140040950  sub     rdx, 10h; unsigned __int64
0x140040954  lea     r8, [rsp+0A8h+arg_10]; unsigned __int64 *
0x14004095c  mov     rcx, r14; unsigned __int16 *
0x14004095f  call    ?RtlStringCbLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140040964  mov     ebx, eax
0x140040966  mov     [rsp+0A8h+var_78], eax
0x14004096a  test    eax, eax
0x14004096c  jns     short loc_140040975
0x14004096e  mov     ebx, 0C00000E8h
0x140040973  jmp     short loc_140040900
0x140040975  lea     rax, WPP_GLOBAL_Control
0x14004097c  mov     rcx, cs:WPP_GLOBAL_Control
0x140040983  cmp     rcx, rax
0x140040986  jz      short loc_1400409BD
0x140040988  test    dword ptr [rcx+2Ch], 4000000h
0x14004098f  jz      short loc_1400409BD
0x140040991  mov     edx, 18h
0x140040996  mov     [rsp+0A8h+var_80], r14
0x14004099b  mov     [rsp+0A8h+var_88], 1CDBh
0x1400409a3  lea     r9, aCclfsrequestDe; "CClfsRequest::DeleteContainer"
0x1400409aa  lea     r8, WPP_e99822b18e20334f40b669f21686eb29_Traceguids
0x1400409b1  mov     rcx, [rcx+18h]
0x1400409b5  call    WPP_SF_slS
0x1400409ba  xor     r10d, r10d
0x1400409bd  add     r12, 2
0x1400409c1  add     r12, [rsp+0A8h+arg_10]
0x1400409c9  add     r14, 2
0x1400409cd  add     r14, [rsp+0A8h+arg_10]
0x1400409d5  mov     [rsp+0A8h+var_68], r14
0x1400409da  inc     edi
0x1400409dc  mov     [rsp+0A8h+var_74], edi
0x1400409e0  mov     rax, [rsp+0A8h+arg_18]
0x1400409e8  jmp     loc_14004093E
0x1400409ed  mov     rax, [rsp+0A8h+var_60]
0x1400409f2  mov     r13, [rax+30h]
0x1400409f6  mov     rax, [r13+18h]
0x1400409fa  mov     rcx, [rax+78h]
0x1400409fe  mov     [rsi+90h], rcx
0x140040a05  mov     rax, [rcx]
0x140040a08  mov     rax, [rax+40h]
0x140040a0c  call    _guard_dispatch_icall
0x140040a11  xor     r10d, r10d
0x140040a14  mov     edi, r10d
0x140040a17  mov     [rsp+0A8h+var_74], r10d
0x140040a1c  mov     [rsp+0A8h+var_68], r15
0x140040a21  mov     r14, [rsp+0A8h+arg_18]
0x140040a29  mov     r12b, byte ptr [rsp+0A8h+arg_8]
0x140040a31  mov     r8d, 2
0x140040a37  movzx   eax, word ptr [r14+8]
0x140040a3c  cmp     edi, eax
0x140040a3e  jnb     loc_140040B51
0x140040a44  mov     ebx, r10d
0x140040a47  mov     [rsp+0A8h+var_70], ebx
0x140040a4b  xorps   xmm0, xmm0
0x140040a4e  movups  [rsp+0A8h+var_48], xmm0
0x140040a53  test    r15, r15
0x140040a56  jz      loc_140040AF0
0x140040a5c  mov     [rsp+0A8h+arg_8], r10
0x140040a64  lea     rdx, [rsp+0A8h+arg_8]
0x140040a6c  mov     ecx, 7FFFh
0x140040a71  mov     [rsp+0A8h+var_50], rcx
0x140040a76  mov     rax, r15
0x140040a79  mov     [rsp+0A8h+var_58], rax
0x140040a7e  test    rcx, rcx
0x140040a81  jz      short loc_140040A9B
0x140040a83  cmp     [rax], r10w
0x140040a87  jz      short loc_140040A9B
0x140040a89  add     rax, r8
0x140040a8c  mov     [rsp+0A8h+var_58], rax
0x140040a91  dec     rcx
0x140040a94  mov     [rsp+0A8h+var_50], rcx
0x140040a99  jmp     short loc_140040A7E
0x140040a9b  mov     eax, 0C000000Dh
0x140040aa0  test    rcx, rcx
0x140040aa3  cmovz   ebx, eax
0x140040aa6  test    ebx, ebx
0x140040aa8  js      short loc_140040AB7
0x140040aaa  mov     eax, 7FFFh
0x140040aaf  sub     rax, rcx
0x140040ab2  mov     [rdx], rax
0x140040ab5  jmp     short loc_140040ABA
0x140040ab7  mov     [rdx], r10
0x140040aba  mov     [rsp+0A8h+var_70], ebx
0x140040abe  test    ebx, ebx
0x140040ac0  js      short loc_140040AF0
0x140040ac2  mov     [rsp+0A8h+arg_18], r10
0x140040aca  mov     rax, [rsp+0A8h+arg_8]
0x140040ad2  add     rax, rax
0x140040ad5  mov     [rsp+0A8h+arg_18], rax
0x140040add  mov     word ptr [rsp+0A8h+var_48], ax
0x140040ae2  add     ax, r8w
0x140040ae6  mov     word ptr [rsp+0A8h+var_48+2], ax
0x140040aeb  mov     qword ptr [rsp+0A8h+var_48+8], r15
0x140040af0  mov     [rsp+0A8h+var_78], ebx
0x140040af4  test    ebx, ebx
0x140040af6  js      loc_14004096E
0x140040afc  mov     rcx, [rsi+90h]
0x140040b03  mov     rax, [rcx]
0x140040b06  mov     rax, [rax+0E0h]
0x140040b0d  mov     r9b, r12b
0x140040b10  lea     r8, [rsp+0A8h+var_48]
0x140040b15  mov     rdx, r13
0x140040b18  call    _guard_dispatch_icall
0x140040b1d  xor     r10d, r10d
0x140040b20  test    eax, eax
0x140040b22  jns     short loc_140040B31
0x140040b24  mov     ebx, eax
0x140040b26  mov     [rsp+0A8h+var_78], eax
0x140040b2a  cmp     eax, 0C01A0011h
0x140040b2f  jnz     short loc_140040B51
0x140040b31  movzx   eax, word ptr [rsp+0A8h+var_48]
0x140040b36  shr     rax, 1
0x140040b39  lea     r15, [r15+rax*2]
0x140040b3d  add     r15, 2
0x140040b41  mov     [rsp+0A8h+var_68], r15
0x140040b46  inc     edi
0x140040b48  mov     [rsp+0A8h+var_74], edi
0x140040b4c  jmp     loc_140040A31
0x140040b51  test    byte ptr [rsi+10h], 1
0x140040b55  jz      short loc_140040B75
0x140040b57  mov     rax, [rsi+30h]
0x140040b5b  mov     rcx, [rax+50h]; Event
0x140040b5f  test    rcx, rcx
0x140040b62  jz      short loc_140040B75
0x140040b64  xor     r8d, r8d; Wait
0x140040b67  xor     edx, edx; Increment
0x140040b69  call    cs:__imp_KeSetEvent
0x140040b70  nop     dword ptr [rax+rax+00h]
0x140040b75  mov     eax, [rsi+10h]
0x140040b78  test    al, 4
0x140040b7a  jnz     short loc_140040B8D
0x140040b7c  mov     rax, [rsi+30h]
0x140040b80  mov     [rax+30h], ebx
0x140040b83  mov     ecx, edi
0x140040b85  mov     rax, [rsi+30h]
0x140040b89  mov     [rax+38h], rcx
0x140040b8d  mov     eax, ebx
0x140040b8f  add     rsp, 70h
0x140040b93  pop     r15
0x140040b95  pop     r14
0x140040b97  pop     r13
0x140040b99  pop     r12
0x140040b9b  pop     rdi
0x140040b9c  pop     rsi
0x140040b9d  pop     rbx
0x140040b9e  retn
0x14007e956  push    rbx
0x14007e958  push    rbp
0x14007e959  sub     rsp, 38h
0x14007e95d  mov     rbp, rdx
0x14007e960  xor     cl, cl
0x14007e962  mov     rbx, [rbp+0B0h]
0x14007e969  test    byte ptr [rbx+10h], 1
0x14007e96d  movzx   eax, cl
0x14007e970  mov     ecx, 1
0x14007e975  cmovnz  eax, ecx
0x14007e978  test    al, al
0x14007e97a  jz      short loc_14007E99D
0x14007e97c  mov     rax, [rbx+30h]
0x14007e980  cmp     qword ptr [rax+50h], 0
0x14007e985  jz      short loc_14007E99D
0x14007e987  xor     r8d, r8d; Wait
0x14007e98a  xor     edx, edx; Increment
0x14007e98c  mov     rcx, [rax+50h]; Event
0x14007e990  call    cs:__imp_KeSetEvent
0x14007e997  nop     dword ptr [rax+rax+00h]
0x14007e99c  nop
0x14007e99d  xor     cl, cl
0x14007e99f  test    byte ptr [rbx+10h], 4
0x14007e9a3  movzx   eax, cl
0x14007e9a6  mov     ecx, 1
0x14007e9ab  cmovnz  eax, ecx
0x14007e9ae  test    al, al
0x14007e9b0  jnz     short loc_14007E9C7
0x14007e9b2  mov     rcx, [rbx+30h]
0x14007e9b6  mov     eax, [rbp+30h]
0x14007e9b9  mov     [rcx+30h], eax
0x14007e9bc  mov     ecx, [rbp+34h]
0x14007e9bf  mov     rax, [rbx+30h]
0x14007e9c3  mov     [rax+38h], rcx
0x14007e9c7  add     rsp, 38h
0x14007e9cb  pop     rbp
0x14007e9cc  pop     rbx
0x14007e9cd  retn
```
