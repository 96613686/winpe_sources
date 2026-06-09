# FindCommonMemoryTypesBasedOnBuses(KSALLOCATOR_FRAMING_EX *,KSALLOCATOR_FRAMING_EX *,_GUID,_GUID,ulong *,_GUID *)

- ea: `0x18003729c`
- end: `0x1800374ef`
- name: `?FindCommonMemoryTypesBasedOnBuses@@YAHPEAUKSALLOCATOR_FRAMING_EX@@0U_GUID@@1PEAKPEAU2@@Z`
- size: `595`
- prototype: `__int64 __fastcall(struct KSALLOCATOR_FRAMING_EX *, __int64, struct _GUID *, struct _GUID *, unsigned int *, struct _GUID *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033570`
- `0x180036dbc`
- `0x1800399ac`

## callees

- `0x180002b58`
- `0x18001f1c4`
- `0x18001f210`
- `0x18003729c`
- `0x18004485c`

## pseudocode

```c
__int64 __fastcall FindCommonMemoryTypesBasedOnBuses(
        struct KSALLOCATOR_FRAMING_EX *a1,
        __int64 a2,
        struct _GUID *a3,
        struct _GUID *a4,
        unsigned int *a5,
        struct _GUID *a6)
{
  int v7; // esi
  struct _GUID *v8; // r15
  struct KSALLOCATOR_FRAMING_EX *v9; // r10
  unsigned int v11; // ebx
  char *v12; // rdi
  int v13; // ebp
  unsigned int v14; // r13d
  int v15; // r11d
  __int64 v16; // rcx
  __int64 v17; // rax
  _GUID MemoryType; // xmm6
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int i; // ecx
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // r15d
  void *v27; // rsi
  char *v28; // rax
  unsigned __int64 v29; // rdx
  __int64 v30; // rax
  int v32; // [rsp+80h] [rbp+8h]
  __int64 v33; // [rsp+88h] [rbp+10h]
  struct _GUID *v34; // [rsp+90h] [rbp+18h]
  int v36; // [rsp+A0h] [rbp+28h]

  v34 = a3;
  v33 = a2;
  v7 = 1;
  v8 = a4;
  v9 = (struct KSALLOCATOR_FRAMING_EX *)a2;
  v32 = 1;
  v11 = 0;
  v12 = (char *)((unsigned __int64)a6 & -(__int64)(*a5 != 0));
  if ( a1->CountItems )
  {
    v13 = 0;
    v14 = 0;
    v15 = 0;
    v36 = 0;
    while ( !v13 )
    {
      v16 = v14;
      v17 = *(_QWORD *)&a1->FramingItem[v16].BusType.Data1 - *(_QWORD *)&a3->Data1;
      if ( !v17 )
        v17 = *(_QWORD *)a1->FramingItem[v16].BusType.Data4 - *(_QWORD *)a3->Data4;
      if ( v17 )
      {
        v7 = v32;
      }
      else
      {
        MemoryType = a1->FramingItem[v16].MemoryType;
        v19 = *(_QWORD *)a1->FramingItem[v16].MemoryType.Data4;
        a2 = 0;
        v20 = *(_QWORD *)&a1->FramingItem[v16].MemoryType.Data1;
        while ( (unsigned int)a2 < v11 )
        {
          v21 = 16LL * (unsigned int)a2;
          v22 = v20 - *(_QWORD *)&v12[v21];
          if ( v20 == *(_QWORD *)&v12[v21] )
            v22 = v19 - *(_QWORD *)&v12[v21 + 8];
          if ( !v22 )
            goto LABEL_35;
          a2 = (unsigned int)(a2 + 1);
        }
        for ( i = 0; i < v9->CountItems; ++i )
        {
          a2 = 88LL * i;
          v24 = *(_QWORD *)((char *)&v9->FramingItem[0].MemoryType.Data1 + a2) - v20;
          if ( !v24 )
            v24 = *(_QWORD *)&v9->FramingItem[0].MemoryType.Data4[a2] - v19;
          if ( !v24 )
          {
            v25 = *(_QWORD *)((char *)&v9->FramingItem[0].BusType.Data1 + a2) - *(_QWORD *)&v8->Data1;
            if ( !v25 )
              v25 = *(_QWORD *)&v9->FramingItem[0].BusType.Data4[a2] - *(_QWORD *)v8->Data4;
            if ( !v25 )
            {
              if ( !*a5 && v11 == v15 )
              {
                v26 = v15 + 25;
                v27 = v12;
                v36 = v15 + 25;
                v28 = (char *)operator new[](saturated_mul((unsigned int)(v15 + 25), 0x10u));
                v12 = v28;
                if ( !v28 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      191,
                      &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
                      v26);
                  v7 = 0;
                  v32 = 0;
                  v13 = 1;
                  goto LABEL_36;
                }
                if ( v27 && v11 )
                {
                  memmove_0(v28, v27, 16LL * v11);
                  operator delete(v27, v29);
                }
              }
              v30 = 2LL * v11++;
              if ( *a5 == v11 )
                v13 = 1;
              *(_GUID *)&v12[8 * v30] = MemoryType;
              break;
            }
          }
        }
LABEL_35:
        v7 = v32;
LABEL_36:
        a3 = v34;
      }
      v9 = (struct KSALLOCATOR_FRAMING_EX *)v33;
      ++v14;
      v15 = v36;
      v8 = a4;
      if ( v14 >= a1->CountItems )
        goto LABEL_41;
    }
    v7 = v32;
  }
LABEL_41:
  if ( !*a5 )
  {
    *a5 = v11;
    if ( v12 )
      operator delete(v12, a2);
  }
  return v7 & (unsigned int)-(v11 != 0);
}

```

## disassembly

```asm
0x18003729c  mov     rax, rsp
0x18003729f  mov     [rax+20h], r9
0x1800372a3  mov     [rax+18h], r8
0x1800372a7  mov     [rax+10h], rdx
0x1800372ab  push    rbx
0x1800372ac  push    rbp
0x1800372ad  push    rsi
0x1800372ae  push    rdi
0x1800372af  push    r12
0x1800372b1  push    r13
0x1800372b3  push    r14
0x1800372b5  push    r15
0x1800372b7  sub     rsp, 38h
0x1800372bb  mov     r14, [rsp+78h+arg_20]
0x1800372c3  mov     esi, 1
0x1800372c8  movaps  xmmword ptr [rax-58h], xmm6
0x1800372cc  mov     r15, r9
0x1800372cf  mov     r10, rdx
0x1800372d2  mov     [rsp+78h+arg_0], esi
0x1800372d9  mov     r12, rcx
0x1800372dc  mov     eax, [r14]
0x1800372df  neg     eax
0x1800372e1  sbb     rdi, rdi
0x1800372e4  xor     ebx, ebx
0x1800372e6  and     rdi, [rsp+78h+arg_28]
0x1800372ee  cmp     [rcx], ebx
0x1800372f0  jbe     loc_1800374BC
0x1800372f6  xor     ebp, ebp
0x1800372f8  xor     r13d, r13d
0x1800372fb  xor     r11d, r11d
0x1800372fe  mov     dword ptr [rsp+78h+arg_20], r11d
0x180037306  test    ebp, ebp
0x180037308  jnz     loc_1800374B5
0x18003730e  mov     eax, r13d
0x180037311  imul    rcx, rax, 58h ; 'X'
0x180037315  mov     rax, [rcx+r12+28h]
0x18003731a  sub     rax, [r8]
0x18003731d  jnz     short loc_180037328
0x18003731f  mov     rax, [rcx+r12+30h]
0x180037324  sub     rax, [r8+8]
0x180037328  test    rax, rax
0x18003732b  jnz     loc_1800374AC
0x180037331  movups  xmm6, xmmword ptr [rcx+r12+18h]
0x180037337  mov     r8, [rcx+r12+20h]
0x18003733c  lea     esi, [rax+1]
0x18003733f  xor     edx, edx
0x180037341  movq    r9, xmm6
0x180037346  cmp     edx, ebx
0x180037348  jnb     short loc_18003736E
0x18003734a  mov     ecx, edx
0x18003734c  mov     rax, r9
0x18003734f  shl     rcx, 4
0x180037353  sub     rax, [rcx+rdi]
0x180037357  jnz     short loc_180037361
0x180037359  mov     rax, r8
0x18003735c  sub     rax, [rcx+rdi+8]
0x180037361  test    rax, rax
0x180037364  jz      loc_180037476
0x18003736a  add     edx, esi
0x18003736c  jmp     short loc_180037346
0x18003736e  xor     ecx, ecx
0x180037370  cmp     ecx, [r10]
0x180037373  jnb     loc_180037476
0x180037379  mov     eax, ecx
0x18003737b  imul    rdx, rax, 58h ; 'X'
0x18003737f  mov     rax, [rdx+r10+18h]
0x180037384  sub     rax, r9
0x180037387  jnz     short loc_180037391
0x180037389  mov     rax, [rdx+r10+20h]
0x18003738e  sub     rax, r8
0x180037391  test    rax, rax
0x180037394  jnz     short loc_1800373AE
0x180037396  mov     rax, [rdx+r10+28h]
0x18003739b  sub     rax, [r15]
0x18003739e  jnz     short loc_1800373A9
0x1800373a0  mov     rax, [rdx+r10+30h]
0x1800373a5  sub     rax, [r15+8]
0x1800373a9  test    rax, rax
0x1800373ac  jz      short loc_1800373B2
0x1800373ae  add     ecx, esi
0x1800373b0  jmp     short loc_180037370
0x1800373b2  cmp     dword ptr [r14], 0
0x1800373b6  jnz     loc_18003745C
0x1800373bc  cmp     ebx, r11d
0x1800373bf  jnz     loc_18003745C
0x1800373c5  add     r11d, 19h
0x1800373c9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800373d0  mov     r15d, r11d
0x1800373d3  mov     eax, 10h
0x1800373d8  mul     r15
0x1800373db  mov     rsi, rdi
0x1800373de  mov     dword ptr [rsp+78h+arg_20], r11d
0x1800373e6  cmovb   rax, rcx
0x1800373ea  mov     rcx, rax; unsigned __int64
0x1800373ed  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800373f2  mov     rdi, rax
0x1800373f5  test    rax, rax
0x1800373f8  jnz     short loc_180037439
0x1800373fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180037401  lea     rax, WPP_GLOBAL_Control
0x180037408  cmp     rcx, rax
0x18003740b  jz      short loc_18003742B
0x18003740d  cmp     byte ptr [rcx+19h], 2
0x180037411  jb      short loc_18003742B
0x180037413  mov     rcx, [rcx+10h]
0x180037417  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x18003741e  mov     edx, 0BFh
0x180037423  mov     r9d, r15d
0x180037426  call    WPP_SF_d
0x18003742b  xor     esi, esi
0x18003742d  mov     [rsp+78h+arg_0], esi
0x180037434  lea     ebp, [rsi+1]
0x180037437  jmp     short loc_18003747D
0x180037439  test    rsi, rsi
0x18003743c  jz      short loc_18003745C
0x18003743e  test    ebx, ebx
0x180037440  jz      short loc_18003745C
0x180037442  mov     r8d, ebx
0x180037445  mov     rdx, rsi; Src
0x180037448  shl     r8, 4; Size
0x18003744c  mov     rcx, rax; void *
0x18003744f  call    memmove_0
0x180037454  mov     rcx, rsi; void *
0x180037457  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003745c  mov     eax, ebx
0x18003745e  mov     r8d, 1
0x180037464  add     rax, rax
0x180037467  add     ebx, r8d
0x18003746a  cmp     [r14], ebx
0x18003746d  cmovz   ebp, r8d
0x180037471  movdqu  xmmword ptr [rdi+rax*8], xmm6
0x180037476  mov     esi, [rsp+78h+arg_0]
0x18003747d  mov     r8, [rsp+78h+arg_10]
0x180037485  mov     r10, [rsp+78h+arg_8]
0x18003748d  inc     r13d
0x180037490  mov     r11d, dword ptr [rsp+78h+arg_20]
0x180037498  mov     r15, [rsp+78h+arg_18]
0x1800374a0  cmp     r13d, [r12]
0x1800374a4  jb      loc_180037306
0x1800374aa  jmp     short loc_1800374BC
0x1800374ac  mov     esi, [rsp+78h+arg_0]
0x1800374b3  jmp     short loc_180037485
0x1800374b5  mov     esi, [rsp+78h+arg_0]
0x1800374bc  cmp     dword ptr [r14], 0
0x1800374c0  jnz     short loc_1800374D2
0x1800374c2  mov     [r14], ebx
0x1800374c5  test    rdi, rdi
0x1800374c8  jz      short loc_1800374D2
0x1800374ca  mov     rcx, rdi; void *
0x1800374cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800374d2  movaps  xmm6, [rsp+78h+var_58]
0x1800374d7  neg     ebx
0x1800374d9  sbb     eax, eax
0x1800374db  and     eax, esi
0x1800374dd  add     rsp, 38h
0x1800374e1  pop     r15
0x1800374e3  pop     r14
0x1800374e5  pop     r13
0x1800374e7  pop     r12
0x1800374e9  pop     rdi
0x1800374ea  pop     rsi
0x1800374eb  pop     rbp
0x1800374ec  pop     rbx
0x1800374ed  retn
```
