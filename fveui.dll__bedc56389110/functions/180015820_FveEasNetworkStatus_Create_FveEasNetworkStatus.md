# FveEasNetworkStatus::Create(FveEasNetworkStatus * *)

- ea: `0x180015820`
- end: `0x18001595a`
- name: `?Create@FveEasNetworkStatus@@SAJPEAPEAV1@@Z`
- size: `314`
- prototype: `__int64 __fastcall(struct FveEasNetworkStatus **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001472c`
- `0x180025a18`

## callees

- `0x180002bc4`
- `0x1800037a0`
- `0x180014538`
- `0x18001559c`
- `0x180015820`
- `0x180017dec`

## pseudocode

```c
__int64 __fastcall FveEasNetworkStatus::Create(struct FveEasNetworkStatus **a1)
{
  struct FveEasNetworkStatus *v2; // rax
  struct FveEasNetworkStatus *v3; // rsi
  FveEasNetworkStatusImpl *v4; // rax
  unsigned int v5; // edx
  FveEasNetworkStatusImpl *v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // edx

  v2 = (struct FveEasNetworkStatus *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = 0;
    v4 = (FveEasNetworkStatusImpl *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v4;
    if ( v4 )
    {
      *(_QWORD *)v4 = 0;
      *((_QWORD *)v4 + 1) = 0;
      v7 = FveEasNetworkStatusImpl::Initialize(v4);
      if ( !v7 )
        goto LABEL_8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v7);
      if ( (v7 & 0x80000000) == 0 )
      {
LABEL_8:
        *(_QWORD *)v3 = v6;
        *a1 = v3;
        return v7;
      }
    }
    else
    {
      v7 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          2147942414LL);
      v6 = 0;
    }
    FveEasNetworkStatus::`scalar deleting destructor'(v3, v5);
    if ( v6 )
      FveEasNetworkStatusImpl::`scalar deleting destructor'(v6, v8);
  }
  else
  {
    v7 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, 2147942414LL);
  }
  return v7;
}

```

## disassembly

```asm
0x180015820  push    rbx
0x180015822  push    rsi
0x180015823  push    rdi
0x180015824  push    r14
0x180015826  sub     rsp, 28h
0x18001582a  mov     r14, rcx
0x18001582d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015834  mov     ecx, 8; unsigned __int64
0x180015839  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001583e  mov     rsi, rax
0x180015841  test    rax, rax
0x180015844  jz      loc_180015917
0x18001584a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015851  mov     qword ptr [rax], 0
0x180015858  mov     ecx, 10h; unsigned __int64
0x18001585d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015862  mov     rdi, rax
0x180015865  test    rax, rax
0x180015868  jz      short loc_1800158C7
0x18001586a  mov     qword ptr [rax], 0
0x180015871  mov     rcx, rax; this
0x180015874  mov     qword ptr [rax+8], 0
0x18001587c  call    ?Initialize@FveEasNetworkStatusImpl@@QEAAJXZ; FveEasNetworkStatusImpl::Initialize(void)
0x180015881  mov     ebx, eax
0x180015883  test    eax, eax
0x180015885  jz      short loc_1800158BC
0x180015887  mov     rcx, cs:WPP_GLOBAL_Control
0x18001588e  lea     rax, WPP_GLOBAL_Control
0x180015895  cmp     rcx, rax
0x180015898  jz      short loc_1800158B8
0x18001589a  test    byte ptr [rcx+1Ch], 40h
0x18001589e  jz      short loc_1800158B8
0x1800158a0  mov     rcx, [rcx+10h]
0x1800158a4  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800158ab  mov     edx, 9Bh
0x1800158b0  mov     r9d, ebx
0x1800158b3  call    WPP_SF_d
0x1800158b8  test    ebx, ebx
0x1800158ba  js      short loc_180015900
0x1800158bc  mov     [rsi], rdi
0x1800158bf  mov     [r14], rsi
0x1800158c2  jmp     loc_18001594E
0x1800158c7  mov     r9d, 8007000Eh
0x1800158cd  mov     ebx, r9d
0x1800158d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158d7  lea     rax, WPP_GLOBAL_Control
0x1800158de  cmp     rcx, rax
0x1800158e1  jz      short loc_1800158FE
0x1800158e3  test    byte ptr [rcx+1Ch], 40h
0x1800158e7  jz      short loc_1800158FE
0x1800158e9  mov     rcx, [rcx+10h]
0x1800158ed  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800158f4  mov     edx, 9Ah
0x1800158f9  call    WPP_SF_d
0x1800158fe  xor     edi, edi
0x180015900  mov     rcx, rsi; this
0x180015903  call    ??_GFveEasNetworkStatus@@QEAAPEAXI@Z; FveEasNetworkStatus::`scalar deleting destructor'(uint)
0x180015908  test    rdi, rdi
0x18001590b  jz      short loc_18001594E
0x18001590d  mov     rcx, rdi; this
0x180015910  call    ??_GFveEasNetworkStatusImpl@@QEAAPEAXI@Z; FveEasNetworkStatusImpl::`scalar deleting destructor'(uint)
0x180015915  jmp     short loc_18001594E
0x180015917  mov     r9d, 8007000Eh
0x18001591d  mov     ebx, r9d
0x180015920  mov     rcx, cs:WPP_GLOBAL_Control
0x180015927  lea     rax, WPP_GLOBAL_Control
0x18001592e  cmp     rcx, rax
0x180015931  jz      short loc_18001594E
0x180015933  test    byte ptr [rcx+1Ch], 40h
0x180015937  jz      short loc_18001594E
0x180015939  mov     rcx, [rcx+10h]
0x18001593d  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015944  mov     edx, 99h
0x180015949  call    WPP_SF_d
0x18001594e  mov     eax, ebx
0x180015950  add     rsp, 28h
0x180015954  pop     r14
0x180015956  pop     rdi
0x180015957  pop     rsi
0x180015958  pop     rbx
0x180015959  retn
```
