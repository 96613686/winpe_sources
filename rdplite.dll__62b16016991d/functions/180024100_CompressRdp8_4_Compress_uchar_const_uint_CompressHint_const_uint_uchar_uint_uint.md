# CompressRdp8<4>::Compress(uchar const *,uint,_CompressHint const *,uint,uchar *,uint,uint *)

- ea: `0x180024100`
- end: `0x1800242fc`
- name: `?Compress@?$CompressRdp8@$03@@UEAAJPEBEIPEBU_CompressHint@@IPEAEIPEAI@Z`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180024100`
- `0x180024304`
- `0x180026ec0`
- `0x180026f68`
- `0x1800271c0`
- `0x180028340`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CompressRdp8<4>::Compress(
        __int64 a1,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int a5,
        _BYTE *a6,
        unsigned int a7,
        _DWORD *a8)
{
  unsigned int v8; // r14d
  size_t v9; // rbx
  unsigned int v10; // r13d
  int v13; // r15d
  int v14; // eax
  int v15; // edi
  __int64 v16; // rcx
  int v17; // edx
  __int64 i; // rcx
  unsigned int v19; // r10d
  _BYTE *v20; // r12
  _DWORD *v21; // rcx
  _DWORD *v22; // rax
  int v24[4]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int *v27; // [rsp+B8h] [rbp+58h] BYREF

  v27 = a4;
  v8 = 0;
  v9 = a3;
  v10 = -1;
  v26 = 0;
  v24[0] = -1;
  if ( a3 > 0xFFFF || a3 + 1 > a7 )
  {
    v15 = -2147467259;
  }
  else
  {
    v13 = 1;
    if ( !*(_BYTE *)(a1 + 156) )
    {
      CompressRdp8<4>::InitializeSelf(a1, 0);
      a4 = v27;
    }
    if ( a5 == 1 && !a4[2] && a4[1] == (_DWORD)v9 )
      v13 = 0;
    v14 = RingBuffer::Insert((RingBuffer *)(a1 + 64), a2, v9, &v26);
    v8 = v26;
    v15 = v14;
    if ( v14 >= 0 )
    {
      v16 = *(_QWORD *)(a1 + 56);
      if ( !v16
        || !v13
        || (v15 = (*(__int64 (__fastcall **)(__int64, const unsigned __int8 *, _QWORD, _QWORD, unsigned int *, unsigned int, unsigned int **, unsigned int *))(*(_QWORD *)v16 + 32LL))(
                    v16,
                    a2,
                    (unsigned int)v9,
                    v26,
                    v27,
                    a5,
                    &v27,
                    &a5),
            v15 >= 0) )
      {
        if ( v27 )
        {
          v17 = a5;
          for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(i + 1) )
          {
            if ( (unsigned int)v9 > v27[3 * i] )
            {
              v19 = v27[3 * i + 1];
              if ( v19 )
              {
                if ( (unsigned int)v9 - v27[3 * i] >= v19 && v27[3 * i + 2] <= *(_DWORD *)(a1 + 152) )
                  continue;
              }
            }
            v17 = i;
            a5 = i;
            break;
          }
        }
        else
        {
          v17 = 0;
          a5 = 0;
        }
        v20 = a6;
        if ( v13 )
        {
          if ( (unsigned int)v9 < 0xA )
          {
            if ( !v15 )
            {
LABEL_28:
              if ( v10 <= (unsigned int)v9 )
                goto LABEL_31;
            }
          }
          else
          {
            v15 = CompressRdp8<4>::CompressInternal(a1, (__int64)a2, v9, v8, v27, v17, a6 + 1, a7 - 1, v24);
            if ( !v15 )
            {
              v10 = v24[0];
              v21 = a8;
              *v20 = 36;
              *v21 = v10 + 1;
              goto LABEL_28;
            }
          }
        }
        memcpy_0(v20 + 1, a2, v9);
        v22 = a8;
        *v20 = 4;
        v15 = 0;
        *v22 = v9 + 1;
      }
    }
  }
LABEL_31:
  if ( v8 > 0xFFF00000 )
    CompressRdp8<4>::Reset(a1);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180024100  mov     [rsp-38h+arg_0], rbx
0x180024105  mov     [rsp-38h+arg_18], r9
0x18002410a  mov     [rsp-38h+Src], rdx
0x18002410f  push    rbp
0x180024110  push    rsi
0x180024111  push    rdi
0x180024112  push    r12
0x180024114  push    r13
0x180024116  push    r14
0x180024118  push    r15
0x18002411a  mov     rbp, rsp
0x18002411d  sub     rsp, 60h
0x180024121  xor     r14d, r14d
0x180024124  mov     ebx, r8d
0x180024127  or      r13d, 0FFFFFFFFh
0x18002412b  mov     [rbp+arg_10], r14d
0x18002412f  mov     [rbp+var_10], r13d
0x180024133  mov     r12, rdx
0x180024136  mov     rsi, rcx
0x180024139  cmp     r8d, 0FFFFh
0x180024140  ja      loc_1800242CC
0x180024146  lea     eax, [rbx+1]
0x180024149  cmp     eax, [rbp+arg_30]
0x18002414c  ja      loc_1800242CC
0x180024152  lea     r15d, [r14+1]
0x180024156  cmp     [rcx+9Ch], r14b
0x18002415d  jnz     short loc_18002416A
0x18002415f  xor     edx, edx
0x180024161  call    ?InitializeSelf@?$CompressRdp8@$03@@UEAAJPEAUIUnknown@@@Z; CompressRdp8<4>::InitializeSelf(IUnknown *)
0x180024166  mov     r9, [rbp+arg_18]
0x18002416a  cmp     [rbp+arg_20], r15d
0x18002416e  jnz     short loc_180024180
0x180024170  cmp     [r9+8], r14d
0x180024174  jnz     short loc_180024180
0x180024176  xor     eax, eax
0x180024178  cmp     [r9+4], ebx
0x18002417c  cmovz   r15d, eax
0x180024180  lea     rcx, [rsi+40h]; this
0x180024184  mov     r8d, ebx; unsigned int
0x180024187  lea     r9, [rbp+arg_10]; unsigned int *
0x18002418b  mov     rdx, r12; unsigned __int8 *
0x18002418e  call    ?Insert@RingBuffer@@QEAAJPEBEIPEAI@Z; RingBuffer::Insert(uchar const *,uint,uint *)
0x180024193  mov     r14d, [rbp+arg_10]
0x180024197  mov     edi, eax
0x180024199  test    eax, eax
0x18002419b  js      loc_1800242D1
0x1800241a1  mov     rcx, [rsi+38h]
0x1800241a5  test    rcx, rcx
0x1800241a8  jz      short loc_1800241F0
0x1800241aa  test    r15d, r15d
0x1800241ad  jz      short loc_1800241F0
0x1800241af  mov     edx, [rbp+arg_20]
0x1800241b2  lea     r9, [rbp+arg_20]
0x1800241b6  mov     r8, [rbp+arg_18]
0x1800241ba  mov     rax, [rcx]
0x1800241bd  mov     [rsp+60h+var_28], r9
0x1800241c2  lea     r9, [rbp+arg_18]
0x1800241c6  mov     [rsp+60h+var_30], r9
0x1800241cb  mov     r9d, r14d
0x1800241ce  mov     [rsp+60h+var_38], edx
0x1800241d2  mov     rdx, r12
0x1800241d5  mov     rax, [rax+20h]
0x1800241d9  mov     [rsp+60h+var_40], r8
0x1800241de  mov     r8d, ebx
0x1800241e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241e6  mov     edi, eax
0x1800241e8  test    eax, eax
0x1800241ea  js      loc_1800242D1
0x1800241f0  mov     r8, [rbp+arg_18]
0x1800241f4  test    r8, r8
0x1800241f7  jnz     short loc_180024200
0x1800241f9  xor     edx, edx
0x1800241fb  mov     [rbp+arg_20], edx
0x1800241fe  jmp     short loc_18002423E
0x180024200  mov     edx, [rbp+arg_20]
0x180024203  xor     ecx, ecx
0x180024205  cmp     ecx, edx
0x180024207  jnb     short loc_18002423E
0x180024209  lea     r9, [rcx+rcx*2]
0x18002420d  cmp     ebx, [r8+r9*4]
0x180024211  jbe     short loc_180024239
0x180024213  mov     r10d, [r8+r9*4+4]
0x180024218  test    r10d, r10d
0x18002421b  jz      short loc_180024239
0x18002421d  mov     eax, ebx
0x18002421f  sub     eax, [r8+r9*4]
0x180024223  cmp     eax, r10d
0x180024226  jb      short loc_180024239
0x180024228  mov     eax, [rsi+98h]
0x18002422e  cmp     [r8+r9*4+8], eax
0x180024233  ja      short loc_180024239
0x180024235  inc     ecx
0x180024237  jmp     short loc_180024205
0x180024239  mov     edx, ecx
0x18002423b  mov     [rbp+arg_20], ecx
0x18002423e  mov     r12, [rbp+arg_28]
0x180024242  test    r15d, r15d
0x180024245  mov     r15, [rbp+Src]
0x180024249  jz      short loc_1800242AA
0x18002424b  cmp     ebx, 0Ah
0x18002424e  jb      short loc_1800242A1
0x180024250  mov     eax, [rbp+arg_30]
0x180024253  lea     r9, [rbp+var_10]
0x180024257  mov     [rsp+60h+var_20], r9
0x18002425c  lea     rcx, [r12+1]
0x180024261  dec     eax
0x180024263  mov     r9d, r14d
0x180024266  mov     dword ptr [rsp+60h+var_28], eax
0x18002426a  mov     [rsp+60h+var_30], rcx
0x18002426f  mov     rcx, rsi
0x180024272  mov     [rsp+60h+var_38], edx
0x180024276  mov     rdx, r15
0x180024279  mov     [rsp+60h+var_40], r8
0x18002427e  mov     r8d, ebx
0x180024281  call    ?CompressInternal@?$CompressRdp8@$03@@AEAAJPEBEIIPEBU_CompressHint@@IPEAEIPEAI@Z; CompressRdp8<4>::CompressInternal(uchar const *,uint,uint,_CompressHint const *,uint,uchar *,uint,uint *)
0x180024286  mov     edi, eax
0x180024288  test    eax, eax
0x18002428a  jnz     short loc_1800242AA
0x18002428c  mov     r13d, [rbp+var_10]
0x180024290  mov     rcx, [rbp+arg_38]
0x180024294  mov     byte ptr [r12], 24h ; '$'
0x180024299  lea     eax, [r13+1]
0x18002429d  mov     [rcx], eax
0x18002429f  jmp     short loc_1800242A5
0x1800242a1  test    edi, edi
0x1800242a3  jnz     short loc_1800242AA
0x1800242a5  cmp     r13d, ebx
0x1800242a8  jbe     short loc_1800242D1
0x1800242aa  mov     r8, rbx; Size
0x1800242ad  lea     rcx, [r12+1]; void *
0x1800242b2  mov     rdx, r15; Src
0x1800242b5  call    memcpy_0
0x1800242ba  mov     rax, [rbp+arg_38]
0x1800242be  lea     ecx, [rbx+1]
0x1800242c1  mov     byte ptr [r12], 4
0x1800242c6  xor     edi, edi
0x1800242c8  mov     [rax], ecx
0x1800242ca  jmp     short loc_1800242D1
0x1800242cc  mov     edi, 80004005h
0x1800242d1  cmp     r14d, 0FFF00000h
0x1800242d8  jbe     short loc_1800242E2
0x1800242da  mov     rcx, rsi
0x1800242dd  call    ?Reset@?$CompressRdp8@$03@@UEAAXXZ; CompressRdp8<4>::Reset(void)
0x1800242e2  mov     rbx, [rsp+60h+arg_0]
0x1800242ea  mov     eax, edi
0x1800242ec  add     rsp, 60h
0x1800242f0  pop     r15
0x1800242f2  pop     r14
0x1800242f4  pop     r13
0x1800242f6  pop     r12
0x1800242f8  pop     rdi
0x1800242f9  pop     rsi
0x1800242fa  pop     rbp
0x1800242fb  retn
```
