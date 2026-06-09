# DfscNetUseCreate

- ea: `0x140017798`
- end: `0x140017a5c`
- name: `DfscNetUseCreate`
- size: `708`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int, int *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140017458`

## callees

- `0x1400027f8`
- `0x140004944`
- `0x140006080`
- `0x140006380`
- `0x140017798`
- `0x14001ef20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017a3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a3c`
- `ntoskrnl!ExAllocatePool2` at `0x1400178ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400178ba`

## pseudocode

```c
__int64 __fastcall DfscNetUseCreate(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int *a6, _QWORD *a7)
{
  unsigned int v7; // edi
  unsigned int inited; // edi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // ecx
  char *Pool2; // rax
  char *v19; // rbx
  const void *v20; // rdx
  __int64 v21; // r13
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  _WORD *v25; // rcx
  _OWORD *v26; // rcx
  __int64 Ea; // rax
  __int64 v28; // rcx
  __int128 v30; // [rsp+20h] [rbp-58h] BYREF

  v7 = *(unsigned __int16 *)(a1 + 80) + 178;
  v30 = 0;
  if ( !a6 )
    goto LABEL_17;
  if ( v7 + 15 < v7 )
  {
    inited = -1073741675;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      v14 = 19;
LABEL_6:
      WPP_SF_D(v13->AttachedDevice, v14, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids, 3221225621LL);
      return inited;
    }
    return inited;
  }
  v15 = *a6;
  v16 = (v7 + 15) & 0xFFFFFFF0;
  if ( (unsigned int)*a6 < 0x10 )
    v15 = 16;
  v17 = v16 + v15;
  if ( v16 + v15 >= v16 )
  {
    v7 = v17 + a6[1];
    if ( v7 < v17 )
    {
      inited = -1073741675;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
      {
        v14 = 21;
        goto LABEL_6;
      }
      return inited;
    }
LABEL_17:
    Pool2 = (char *)ExAllocatePool2(258, v7, 1162044996);
    v19 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, v7);
      *(_WORD *)v19 = -32504;
      *((_WORD *)v19 + 1) = v7;
      *((_DWORD *)v19 + 1) = 1;
      v20 = *(const void **)(a1 + 88);
      LOWORD(v30) = *(_WORD *)(a1 + 80);
      *((_QWORD *)&v30 + 1) = (unsigned __int64)(v19 + 177) & 0xFFFFFFFFFFFFFFFEuLL;
      memmove(*((void **)&v30 + 1), v20, (unsigned __int16)v30);
      *(_WORD *)(*((_QWORD *)&v30 + 1) + 2 * ((unsigned __int64)(unsigned __int16)v30 >> 1)) = 0;
      v21 = (unsigned __int16)(v30 + 2);
      WORD1(v30) = v30 + 2;
      inited = DfscInitDfsPath(&v30, v19 + 8, v22, v23);
      if ( inited )
      {
        ExFreePoolWithTag(v19, 0);
      }
      else
      {
        v25 = v19 + 104;
        if ( a2 )
          memmove(v25, *(const void **)(a2 + 8), *(unsigned __int16 *)(a2 + 2));
        else
          *v25 = 0;
        if ( a4 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(a4 + 4));
          *((_QWORD *)v19 + 14) = a4;
        }
        if ( a3 )
          *((_QWORD *)v19 + 17) = a3;
        *((_DWORD *)v19 + 37) = a5;
        if ( a6 )
        {
          v26 = (_OWORD *)((((unsigned __int64)(v19 + 177) & 0xFFFFFFFFFFFFFFFEuLL) + v21 + 15) & 0xFFFFFFFFFFFFFFF0uLL);
          *((_QWORD *)v19 + 21) = v26;
          *v26 = *(_OWORD *)a6;
          memmove(
            (void *)(*((_QWORD *)v19 + 21) + **((unsigned int **)v19 + 21)),
            (char *)a6 + (unsigned int)*a6,
            (unsigned int)a6[1]);
        }
        *((_DWORD *)v19 + 38) = 0;
        v19[156] = 0;
        if ( a6 )
        {
          Ea = DfscFindEa((char *)a6 + (unsigned int)*a6, v24, "TransportInfo", 13);
          if ( Ea )
          {
            if ( *(_WORD *)(Ea + 6) == 16 )
            {
              v28 = *(unsigned __int8 *)(Ea + 5);
              if ( *(_DWORD *)(v28 + Ea + 9) )
                *(_OWORD *)(v19 + 152) = *(_OWORD *)(v28 + Ea + 9);
            }
          }
        }
        *a7 = v19;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
    return inited;
  }
  inited = -1073741675;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    v14 = 20;
    goto LABEL_6;
  }
  return inited;
}

```

## disassembly

```asm
0x140017798  push    rbx
0x14001779a  push    rbp
0x14001779b  push    rsi
0x14001779c  push    rdi
0x14001779d  push    r12
0x14001779f  push    r13
0x1400177a1  push    r14
0x1400177a3  push    r15
0x1400177a5  sub     rsp, 38h
0x1400177a9  movzx   edi, word ptr [rcx+50h]
0x1400177ad  xorps   xmm0, xmm0
0x1400177b0  mov     rsi, [rsp+78h+arg_28]
0x1400177b8  add     edi, 0B2h
0x1400177be  mov     r13, rcx
0x1400177c1  mov     rbp, r9
0x1400177c4  mov     r15, r8
0x1400177c7  mov     r14, rdx
0x1400177ca  mov     ecx, 10h
0x1400177cf  movups  [rsp+78h+var_58], xmm0
0x1400177d4  test    rsi, rsi
0x1400177d7  jz      loc_1400178AA
0x1400177dd  lea     edx, [rdi+0Fh]
0x1400177e0  cmp     edx, edi
0x1400177e2  jnb     short loc_14001782D
0x1400177e4  mov     edi, 0C0000095h
0x1400177e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177f0  lea     rax, WPP_GLOBAL_Control
0x1400177f7  cmp     rcx, rax
0x1400177fa  jz      loc_140017A48
0x140017800  test    dword ptr [rcx+2Ch], 400000h
0x140017807  jz      loc_140017A48
0x14001780d  mov     edx, 13h
0x140017812  mov     rcx, [rcx+18h]
0x140017816  lea     r8, WPP_87cf2b6004dc3e7f3eb3e63342a64277_Traceguids
0x14001781d  mov     r9d, 0C0000095h
0x140017823  call    WPP_SF_D
0x140017828  jmp     loc_140017A48
0x14001782d  mov     eax, [rsi]
0x14001782f  and     edx, 0FFFFFFF0h
0x140017832  cmp     eax, ecx
0x140017834  cmovb   eax, ecx
0x140017837  lea     ecx, [rdx+rax]
0x14001783a  cmp     ecx, edx
0x14001783c  jnb     short loc_14001786E
0x14001783e  mov     edi, 0C0000095h
0x140017843  mov     rcx, cs:WPP_GLOBAL_Control
0x14001784a  lea     rax, WPP_GLOBAL_Control
0x140017851  cmp     rcx, rax
0x140017854  jz      loc_140017A48
0x14001785a  test    dword ptr [rcx+2Ch], 400000h
0x140017861  jz      loc_140017A48
0x140017867  mov     edx, 14h
0x14001786c  jmp     short loc_140017812
0x14001786e  mov     edi, [rsi+4]
0x140017871  add     edi, ecx
0x140017873  cmp     edi, ecx
0x140017875  jnb     short loc_1400178AA
0x140017877  mov     edi, 0C0000095h
0x14001787c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017883  lea     rax, WPP_GLOBAL_Control
0x14001788a  cmp     rcx, rax
0x14001788d  jz      loc_140017A48
0x140017893  test    dword ptr [rcx+2Ch], 400000h
0x14001789a  jz      loc_140017A48
0x1400178a0  mov     edx, 15h
0x1400178a5  jmp     loc_140017812
0x1400178aa  mov     r8d, 45436644h
0x1400178b0  mov     edx, edi
0x1400178b2  mov     ecx, 102h
0x1400178b7  mov     r12d, edi
0x1400178ba  call    cs:__imp_ExAllocatePool2
0x1400178c1  nop     dword ptr [rax+rax+00h]
0x1400178c6  mov     rbx, rax
0x1400178c9  test    rax, rax
0x1400178cc  jnz     short loc_1400178D8
0x1400178ce  mov     edi, 0C000009Ah
0x1400178d3  jmp     loc_140017A48
0x1400178d8  mov     r8, r12; Size
0x1400178db  xor     edx, edx; Val
0x1400178dd  mov     rcx, rbx; void *
0x1400178e0  call    memset
0x1400178e5  mov     word ptr [rbx], 8108h
0x1400178ea  lea     r12, [rbx+0B1h]
0x1400178f1  mov     [rbx+2], di
0x1400178f5  and     r12, 0FFFFFFFFFFFFFFFEh
0x1400178f9  mov     dword ptr [rbx+4], 1
0x140017900  mov     rcx, r12; void *
0x140017903  movzx   r8d, word ptr [r13+50h]; Size
0x140017908  mov     rdx, [r13+58h]; Src
0x14001790c  mov     word ptr [rsp+78h+var_58], r8w
0x140017912  mov     qword ptr [rsp+78h+var_58+8], r12
0x140017917  call    memmove
0x14001791c  movzx   edx, word ptr [rsp+78h+var_58]
0x140017921  xor     ecx, ecx
0x140017923  mov     rax, qword ptr [rsp+78h+var_58+8]
0x140017928  shr     rdx, 1
0x14001792b  mov     [rax+rdx*2], cx
0x14001792f  lea     rdx, [rbx+8]
0x140017933  movzx   eax, word ptr [rsp+78h+var_58]
0x140017938  lea     rcx, [rsp+78h+var_58]
0x14001793d  add     ax, 2
0x140017941  movzx   r13d, ax
0x140017945  mov     word ptr [rsp+78h+var_58+2], ax
0x14001794a  call    DfscInitDfsPath
0x14001794f  mov     edi, eax
0x140017951  test    eax, eax
0x140017953  jnz     loc_140017A37
0x140017959  lea     rcx, [rbx+68h]; void *
0x14001795d  test    r14, r14
0x140017960  jz      short loc_140017972
0x140017962  movzx   r8d, word ptr [r14+2]; Size
0x140017967  mov     rdx, [r14+8]; Src
0x14001796b  call    memmove
0x140017970  jmp     short loc_140017977
0x140017972  xor     eax, eax
0x140017974  mov     [rcx], ax
0x140017977  test    rbp, rbp
0x14001797a  jz      short loc_140017984
0x14001797c  lock inc dword ptr [rbp+4]
0x140017980  mov     [rbx+70h], rbp
0x140017984  test    r15, r15
0x140017987  jz      short loc_140017990
0x140017989  mov     [rbx+88h], r15
0x140017990  mov     eax, [rsp+78h+arg_20]
0x140017997  mov     [rbx+94h], eax
0x14001799d  test    rsi, rsi
0x1400179a0  jz      short loc_1400179D5
0x1400179a2  lea     rcx, [r13+0Fh]
0x1400179a6  add     rcx, r12
0x1400179a9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400179ad  mov     [rbx+0A8h], rcx
0x1400179b4  movups  xmm0, xmmword ptr [rsi]
0x1400179b7  movdqu  xmmword ptr [rcx], xmm0
0x1400179bb  mov     rax, [rbx+0A8h]
0x1400179c2  mov     edx, [rsi]
0x1400179c4  mov     r8d, [rsi+4]; Size
0x1400179c8  add     rdx, rsi; Src
0x1400179cb  mov     ecx, [rax]
0x1400179cd  add     rcx, rax; void *
0x1400179d0  call    memmove
0x1400179d5  mov     dword ptr [rbx+98h], 0
0x1400179df  mov     byte ptr [rbx+9Ch], 0
0x1400179e6  test    rsi, rsi
0x1400179e9  jz      short loc_140017A2A
0x1400179eb  mov     ecx, [rsi]
0x1400179ed  lea     r8, aTransportinfo; "TransportInfo"
0x1400179f4  add     rcx, rsi
0x1400179f7  mov     r9d, 0Dh
0x1400179fd  call    DfscFindEa
0x140017a02  test    rax, rax
0x140017a05  jz      short loc_140017A2A
0x140017a07  mov     ecx, 10h
0x140017a0c  cmp     [rax+6], cx
0x140017a10  jnz     short loc_140017A2A
0x140017a12  movzx   ecx, byte ptr [rax+5]
0x140017a16  cmp     dword ptr [rcx+rax+9], 0
0x140017a1b  jz      short loc_140017A2A
0x140017a1d  movups  xmm0, xmmword ptr [rcx+rax+9]
0x140017a22  movdqu  xmmword ptr [rbx+98h], xmm0
0x140017a2a  mov     rax, [rsp+78h+arg_30]
0x140017a32  mov     [rax], rbx
0x140017a35  jmp     short loc_140017A48
0x140017a37  xor     edx, edx; Tag
0x140017a39  mov     rcx, rbx; P
0x140017a3c  call    cs:__imp_ExFreePoolWithTag
0x140017a43  nop     dword ptr [rax+rax+00h]
0x140017a48  mov     eax, edi
0x140017a4a  add     rsp, 38h
0x140017a4e  pop     r15
0x140017a50  pop     r14
0x140017a52  pop     r13
0x140017a54  pop     r12
0x140017a56  pop     rdi
0x140017a57  pop     rsi
0x140017a58  pop     rbp
0x140017a59  pop     rbx
0x140017a5a  retn
```
