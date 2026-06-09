# CDirectStream::SetSize(unsigned __int64)

- ea: `0x18000afb0`
- end: `0x18000b3c0`
- name: `?SetSize@CDirectStream@@QEAAJ_K@Z`
- size: `1040`
- prototype: `__int64 __fastcall(CDirectStream *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800050f8`
- `0x180009d7c`
- `0x18000ae88`
- `0x18000bb1c`

## callees

- `0x180003678`
- `0x1800093fc`
- `0x180009610`
- `0x18000ae88`
- `0x18000afb0`
- `0x18000b3d0`
- `0x18000b530`
- `0x18000bb1c`
- `0x18000c3b0`
- `0x18000e340`
- `0x180010020`
- `0x180010d20`
- `0x180011290`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b283`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b2eb`

## pseudocode

```c
__int64 __fastcall CDirectStream::SetSize(CDirectStream *this, unsigned __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdi
  unsigned __int64 v6; // r14
  bool v7; // zf
  int v8; // r13d
  unsigned int v9; // eax
  int Start; // ebx
  __int16 v12; // r8
  unsigned __int64 v13; // rcx
  unsigned int v14; // r14d
  unsigned __int64 v15; // r15
  char *v16; // r13
  int ESect; // eax
  unsigned int v18; // r8d
  unsigned int v19; // edx
  unsigned __int64 v20; // rbx
  CStreamCache *v21; // rcx
  unsigned int v22; // [rsp+30h] [rbp-40h]
  unsigned int v23; // [rsp+34h] [rbp-3Ch] BYREF
  int v24; // [rsp+38h] [rbp-38h]
  unsigned __int64 v25; // [rsp+40h] [rbp-30h]
  CFat *v26; // [rsp+48h] [rbp-28h]
  struct CFat *v27; // [rsp+50h] [rbp-20h]
  CDirectory *v28; // [rsp+58h] [rbp-18h]
  __int64 v29; // [rsp+60h] [rbp-10h]
  unsigned int v30; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+C0h] [rbp+50h] BYREF
  unsigned int v32; // [rsp+C8h] [rbp+58h]

  v4 = *((_QWORD *)this + 2);
  if ( !v4 )
    return 2147680509LL;
  v5 = v4 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  if ( !v5 )
    return 2147680509LL;
  v6 = *((_QWORD *)this + 22);
  if ( v6 != a2 )
  {
    v7 = *(_DWORD *)(v5 + 1376) == 0;
    v8 = *(unsigned __int16 *)(v5 + 1424);
    v9 = *((_DWORD *)this + 6);
    v28 = (CDirectory *)(v5 + 536);
    v24 = v8;
    LOWORD(v30) = v8;
    v26 = (CFat *)(v5 + 616);
    v27 = (struct CFat *)(v5 + 616);
    v32 = v9;
    if ( v7 && v9 )
    {
      if ( a2 < 0x1000 )
      {
        v30 = 64;
        v27 = (struct CFat *)(v5 + 928);
        v9 = v32;
      }
      if ( v6 < 0x1000 )
      {
        v24 = 64;
        v26 = (CFat *)(v5 + 928);
        LOWORD(v8) = 64;
      }
    }
    v31 = 0;
    Start = CDirectory::GetStart((CDirectory *)(v5 + 536), v9, &v31);
    if ( Start < 0 )
      goto LABEL_11;
    v12 = v30;
    v29 = (unsigned __int16)v30;
    v13 = ((unsigned __int16)v8 + v6 - 1) / (unsigned __int16)v8;
    v25 = v13;
    v14 = 0;
    v15 = (a2 + (unsigned __int16)v30 - 1LL) / (unsigned __int16)v30;
    v22 = v31;
    if ( (_WORD)v8 != (_WORD)v30 )
    {
      v20 = *((_QWORD *)this + 22);
      if ( a2 <= v20 )
        LODWORD(v20) = a2;
      v14 = v20;
      if ( (_DWORD)v20 )
      {
        while ( 1 )
        {
          v16 = (char *)CoTaskMemAlloc(v14);
          if ( v16 )
            break;
          v14 >>= 1;
          if ( v14 < (unsigned int)v20 )
          {
            Start = -2147287032;
            goto LABEL_11;
          }
        }
        v23 = 0;
        Start = CDirectStream::ReadAt(this, 0, v16, v14, &v23);
        if ( Start < 0 )
          goto LABEL_53;
        if ( v23 == v14 )
        {
          CStreamCache::Empty((CDirectStream *)((char *)this + 32));
          Start = CStreamCache::Allocate(v21, v27, v15, &v31);
          if ( Start >= 0 )
            goto LABEL_24;
        }
        else
        {
          Start = -2147286787;
        }
LABEL_53:
        CoTaskMemFree(v16);
LABEL_15:
        if ( Start >= 0 )
          return (unsigned int)Start;
        goto LABEL_11;
      }
    }
    v16 = 0;
    v23 = 0;
    if ( (unsigned int)v13 > (unsigned int)v15 )
    {
      if ( (_DWORD)v15 )
      {
        v18 = (a2 + (unsigned __int16)v30 - 1LL) / (unsigned __int16)v30;
        v19 = v31;
      }
      else
      {
        Start = CDirectory::SetStart(v28, v32, 0xFFFFFFFE);
        if ( Start < 0 )
          goto LABEL_11;
        v19 = v22;
        v18 = 0;
        v31 = -2;
      }
      Start = CFat::SetChainLength(v26, v19, v18);
      if ( Start >= 0 )
      {
        CStreamCache::Empty((CDirectStream *)((char *)this + 32));
        goto LABEL_24;
      }
    }
    else
    {
      if ( (_DWORD)v13 )
      {
        if ( (unsigned int)v15 <= (unsigned int)v13 )
        {
LABEL_25:
          if ( ((_WORD)v24 != 64 || !(_DWORD)v13) && (v12 != 64 || !(_DWORD)v15)
            || (Start = CMStream::SetMiniSize((CMStream *)v5), Start >= 0) )
          {
            Start = CMStream::SetSize((CMStream *)v5);
            if ( Start >= 0 )
            {
              if ( v31 == v22 || (Start = CDirectory::SetStart(v28, v32, v31), Start >= 0) )
              {
                Start = CDirectory::SetSize(v28, v32, a2);
                if ( Start >= 0 )
                {
                  *((_QWORD *)this + 22) = a2;
                  if ( !v14 )
                    goto LABEL_33;
                  v30 = 0;
                  Start = CDirectStream::WriteAt(this, 0, v16, v14, &v30);
                  if ( Start < 0 )
                    goto LABEL_14;
                  if ( v30 != v14 )
                  {
                    Start = -2147286787;
                    goto LABEL_14;
                  }
                  Start = CFat::SetChainLength(v26, v22, 0);
                  if ( Start >= 0 )
                  {
                    Start = CMStream::SetMiniSize((CMStream *)v5);
                    if ( Start >= 0 )
                    {
                      Start = CMStream::SetSize((CMStream *)v5);
                      if ( Start >= 0 )
                      {
LABEL_33:
                        if ( ((unsigned int)v15 > (unsigned int)v25 || v14) && ((v29 - 1) & a2) != 0 )
                        {
                          v30 = 0;
                          Start = CStreamCache::GetSect((CDirectStream *)((char *)this + 32), (int)v15 - 1, &v30);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
LABEL_14:
          if ( !v16 )
            goto LABEL_15;
          goto LABEL_53;
        }
        ESect = CStreamCache::GetESect((CDirectStream *)((char *)this + 32), (int)v15 - 1, &v23);
      }
      else
      {
        ESect = CStreamCache::Allocate((CDirectStream *)((char *)this + 32), v27, v15, &v31);
      }
      Start = ESect;
      if ( ESect >= 0 )
      {
LABEL_24:
        v12 = v30;
        LODWORD(v13) = v25;
        goto LABEL_25;
      }
    }
LABEL_11:
    CStreamCache::Empty((CDirectStream *)((char *)this + 32));
    return (unsigned int)Start;
  }
  return 0;
}

```

## disassembly

```asm
0x18000afb0  mov     [rsp-38h+arg_8], rbx
0x18000afb5  push    rbp
0x18000afb6  push    rsi
0x18000afb7  push    rdi
0x18000afb8  push    r12
0x18000afba  push    r13
0x18000afbc  push    r14
0x18000afbe  push    r15
0x18000afc0  mov     rbp, rsp
0x18000afc3  sub     rsp, 70h
0x18000afc7  mov     rsi, rcx
0x18000afca  mov     r12, rdx
0x18000afcd  mov     rcx, [rcx+10h]
0x18000afd1  test    rcx, rcx
0x18000afd4  jz      loc_18000B216
0x18000afda  mov     rax, gs:30h
0x18000afe3  mov     r8, [rax+1758h]
0x18000afea  mov     rdi, [r8]
0x18000afed  add     rdi, rcx
0x18000aff0  jz      loc_18000B216
0x18000aff6  mov     r14, [rsi+0B0h]
0x18000affd  cmp     r14, rdx
0x18000b000  jz      loc_18000B20F
0x18000b006  cmp     dword ptr [rdi+560h], 0
0x18000b00d  lea     r15, [rdi+268h]
0x18000b014  movzx   r13d, word ptr [rdi+590h]
0x18000b01c  lea     r9, [rdi+218h]
0x18000b023  mov     eax, [rsi+18h]
0x18000b026  mov     edx, 40h ; '@'
0x18000b02b  mov     [rbp+var_18], r9
0x18000b02f  mov     [rbp+var_38], r13d
0x18000b033  mov     word ptr [rbp+arg_0], r13w
0x18000b038  mov     [rbp+var_28], r15
0x18000b03c  mov     [rbp+var_20], r15
0x18000b040  mov     [rbp+arg_18], eax
0x18000b043  jnz     short loc_18000B07A
0x18000b045  test    eax, eax
0x18000b047  jz      short loc_18000B07A
0x18000b049  mov     ecx, 1000h
0x18000b04e  cmp     r12, rcx
0x18000b051  jnb     short loc_18000B064
0x18000b053  lea     rax, [rdi+3A0h]
0x18000b05a  mov     [rbp+arg_0], edx
0x18000b05d  mov     [rbp+var_20], rax
0x18000b061  mov     eax, [rbp+arg_18]
0x18000b064  cmp     r14, rcx
0x18000b067  jnb     short loc_18000B07A
0x18000b069  lea     rcx, [rdi+3A0h]
0x18000b070  mov     [rbp+var_38], edx
0x18000b073  mov     [rbp+var_28], rcx
0x18000b077  mov     r13d, edx
0x18000b07a  lea     r8, [rbp+arg_10]; unsigned int *
0x18000b07e  mov     [rbp+arg_10], 0
0x18000b085  mov     edx, eax; unsigned int
0x18000b087  mov     rcx, r9; this
0x18000b08a  call    ?GetStart@CDirectory@@QEAAJKPEAK@Z; CDirectory::GetStart(ulong,ulong *)
0x18000b08f  mov     ebx, eax
0x18000b091  test    eax, eax
0x18000b093  jns     short loc_18000B0ED
0x18000b095  lea     rcx, [rsi+20h]; this
0x18000b099  call    ?Empty@CStreamCache@@QEAAXXZ; CStreamCache::Empty(void)
0x18000b09e  jmp     short loc_18000B0D3
0x18000b0a0  mov     rax, [rbp+var_10]
0x18000b0a4  dec     rax
0x18000b0a7  test    r12, rax
0x18000b0aa  jz      short loc_18000B0C6
0x18000b0ac  lea     edx, [r15-1]; unsigned int
0x18000b0b0  mov     [rbp+arg_0], 0
0x18000b0b7  lea     rcx, [rsi+20h]; this
0x18000b0bb  lea     r8, [rbp+arg_0]; unsigned int *
0x18000b0bf  call    ?GetSect@CStreamCache@@QEAAJKPEAK@Z; CStreamCache::GetSect(ulong,ulong *)
0x18000b0c4  mov     ebx, eax
0x18000b0c6  test    r13, r13
0x18000b0c9  jnz     loc_18000B2E8
0x18000b0cf  test    ebx, ebx
0x18000b0d1  js      short loc_18000B095
0x18000b0d3  mov     eax, ebx
0x18000b0d5  mov     rbx, [rsp+70h+arg_8]
0x18000b0dd  add     rsp, 70h
0x18000b0e1  pop     r15
0x18000b0e3  pop     r14
0x18000b0e5  pop     r13
0x18000b0e7  pop     r12
0x18000b0e9  pop     rdi
0x18000b0ea  pop     rsi
0x18000b0eb  pop     rbp
0x18000b0ec  retn
0x18000b0ed  mov     r8d, [rbp+arg_0]
0x18000b0f1  lea     rax, [r14-1]
0x18000b0f5  xor     edx, edx
0x18000b0f7  movzx   ecx, r13w
0x18000b0fb  add     rax, rcx
0x18000b0fe  movzx   r9d, r8w
0x18000b102  div     rcx
0x18000b105  xor     edx, edx
0x18000b107  mov     [rbp+var_10], r9
0x18000b10b  mov     rcx, rax
0x18000b10e  mov     [rbp+var_30], rax
0x18000b112  lea     rax, [r9-1]
0x18000b116  xor     r14d, r14d
0x18000b119  add     rax, r12
0x18000b11c  div     r9
0x18000b11f  mov     r15, rax
0x18000b122  mov     eax, [rbp+arg_10]
0x18000b125  mov     [rbp+var_40], eax
0x18000b128  cmp     r13w, r8w
0x18000b12c  jnz     loc_18000B267
0x18000b132  xor     r13d, r13d
0x18000b135  mov     [rbp+var_3C], r13d
0x18000b139  cmp     ecx, r15d
0x18000b13c  ja      loc_18000B238
0x18000b142  test    ecx, ecx
0x18000b144  jz      short loc_18000B15E
0x18000b146  cmp     r15d, ecx
0x18000b149  jbe     short loc_18000B184
0x18000b14b  lea     edx, [r15-1]; unsigned int
0x18000b14f  lea     rcx, [rsi+20h]; this
0x18000b153  lea     r8, [rbp+var_3C]; unsigned int *
0x18000b157  call    ?GetESect@CStreamCache@@QEAAJKPEAK@Z; CStreamCache::GetESect(ulong,ulong *)
0x18000b15c  jmp     short loc_18000B172
0x18000b15e  mov     rdx, [rbp+var_20]; struct CFat *
0x18000b162  lea     rcx, [rsi+20h]; this
0x18000b166  lea     r9, [rbp+arg_10]; unsigned int *
0x18000b16a  mov     r8d, r15d; unsigned int
0x18000b16d  call    ?Allocate@CStreamCache@@QEAAJPEAVCFat@@KPEAK@Z; CStreamCache::Allocate(CFat *,ulong,ulong *)
0x18000b172  mov     ebx, eax
0x18000b174  test    eax, eax
0x18000b176  js      loc_18000B095
0x18000b17c  mov     r8d, [rbp+arg_0]
0x18000b180  mov     rcx, [rbp+var_30]
0x18000b184  mov     eax, 40h ; '@'
0x18000b189  cmp     ax, word ptr [rbp+var_38]
0x18000b18d  jnz     short loc_18000B202
0x18000b18f  test    ecx, ecx
0x18000b191  jz      short loc_18000B202
0x18000b193  mov     rcx, rdi; this
0x18000b196  call    ?SetMiniSize@CMStream@@QEAAJXZ; CMStream::SetMiniSize(void)
0x18000b19b  mov     ebx, eax
0x18000b19d  test    eax, eax
0x18000b19f  js      loc_18000B0C6
0x18000b1a5  mov     rcx, rdi; this
0x18000b1a8  call    ?SetSize@CMStream@@QEAAJXZ; CMStream::SetSize(void)
0x18000b1ad  mov     ebx, eax
0x18000b1af  test    eax, eax
0x18000b1b1  js      loc_18000B0C6
0x18000b1b7  mov     r8d, [rbp+arg_10]; unsigned int
0x18000b1bb  cmp     r8d, [rbp+var_40]
0x18000b1bf  jnz     short loc_18000B220
0x18000b1c1  mov     edx, [rbp+arg_18]; unsigned int
0x18000b1c4  mov     r8, r12; unsigned __int64
0x18000b1c7  mov     rcx, [rbp+var_18]; this
0x18000b1cb  call    ?SetSize@CDirectory@@QEAAJK_K@Z; CDirectory::SetSize(ulong,unsigned __int64)
0x18000b1d0  mov     ebx, eax
0x18000b1d2  test    eax, eax
0x18000b1d4  js      loc_18000B0C6
0x18000b1da  mov     [rsi+0B0h], r12
0x18000b1e1  test    r14d, r14d
0x18000b1e4  jnz     loc_18000B324
0x18000b1ea  cmp     r15d, dword ptr [rbp+var_30]
0x18000b1ee  ja      loc_18000B0A0
0x18000b1f4  test    r14d, r14d
0x18000b1f7  jz      loc_18000B0C6
0x18000b1fd  jmp     loc_18000B0A0
0x18000b202  cmp     ax, r8w
0x18000b206  jnz     short loc_18000B1A5
0x18000b208  test    r15d, r15d
0x18000b20b  jz      short loc_18000B1A5
0x18000b20d  jmp     short loc_18000B193
0x18000b20f  xor     eax, eax
0x18000b211  jmp     loc_18000B0D5
0x18000b216  mov     eax, 800300FDh
0x18000b21b  jmp     loc_18000B0D5
0x18000b220  mov     edx, [rbp+arg_18]; unsigned int
0x18000b223  mov     rcx, [rbp+var_18]; this
0x18000b227  call    ?SetStart@CDirectory@@QEAAJKK@Z; CDirectory::SetStart(ulong,ulong)
0x18000b22c  mov     ebx, eax
0x18000b22e  test    eax, eax
0x18000b230  js      loc_18000B0C6
0x18000b236  jmp     short loc_18000B1C1
0x18000b238  test    r15d, r15d
0x18000b23b  jz      loc_18000B2F6
0x18000b241  mov     r8d, r15d; unsigned int
0x18000b244  mov     edx, eax; unsigned int
0x18000b246  mov     rcx, [rbp+var_28]; this
0x18000b24a  call    ?SetChainLength@CFat@@QEAAJKK@Z; CFat::SetChainLength(ulong,ulong)
0x18000b24f  mov     ebx, eax
0x18000b251  test    eax, eax
0x18000b253  js      loc_18000B095
0x18000b259  lea     rcx, [rsi+20h]; this
0x18000b25d  call    ?Empty@CStreamCache@@QEAAXXZ; CStreamCache::Empty(void)
0x18000b262  jmp     loc_18000B17C
0x18000b267  mov     rbx, [rsi+0B0h]
0x18000b26e  cmp     r12, rbx
0x18000b271  cmovbe  ebx, r12d
0x18000b275  mov     r14d, ebx
0x18000b278  test    ebx, ebx
0x18000b27a  jz      loc_18000B132
0x18000b280  mov     ecx, r14d; cb
0x18000b283  call    cs:__imp_CoTaskMemAlloc
0x18000b289  mov     r13, rax
0x18000b28c  test    rax, rax
0x18000b28f  jz      loc_18000B35E
0x18000b295  lea     rax, [rbp+var_3C]
0x18000b299  mov     [rbp+var_3C], 0
0x18000b2a0  mov     r9d, r14d; unsigned int
0x18000b2a3  mov     [rsp+70h+var_50], rax; unsigned int *
0x18000b2a8  mov     r8, r13; void *
0x18000b2ab  xor     edx, edx; unsigned __int64
0x18000b2ad  mov     rcx, rsi; this
0x18000b2b0  call    ?ReadAt@CDirectStream@@QEAAJ_KPEAXKPEAK@Z; CDirectStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x18000b2b5  mov     ebx, eax
0x18000b2b7  test    eax, eax
0x18000b2b9  js      short loc_18000B2E8
0x18000b2bb  cmp     [rbp+var_3C], r14d
0x18000b2bf  jnz     loc_18000B374
0x18000b2c5  lea     rcx, [rsi+20h]; this
0x18000b2c9  call    ?Empty@CStreamCache@@QEAAXXZ; CStreamCache::Empty(void)
0x18000b2ce  mov     rdx, [rbp+var_20]; struct CFat *
0x18000b2d2  lea     r9, [rbp+arg_10]; unsigned int *
0x18000b2d6  mov     r8d, r15d; unsigned int
0x18000b2d9  call    ?Allocate@CStreamCache@@QEAAJPEAVCFat@@KPEAK@Z; CStreamCache::Allocate(CFat *,ulong,ulong *)
0x18000b2de  mov     ebx, eax
0x18000b2e0  test    eax, eax
0x18000b2e2  jns     loc_18000B17C
0x18000b2e8  mov     rcx, r13; pv
0x18000b2eb  call    cs:__imp_CoTaskMemFree
0x18000b2f1  jmp     loc_18000B0CF
0x18000b2f6  mov     edx, [rbp+arg_18]; unsigned int
0x18000b2f9  mov     r8d, 0FFFFFFFEh; unsigned int
0x18000b2ff  mov     rcx, [rbp+var_18]; this
0x18000b303  call    ?SetStart@CDirectory@@QEAAJKK@Z; CDirectory::SetStart(ulong,ulong)
0x18000b308  mov     ebx, eax
0x18000b30a  test    eax, eax
0x18000b30c  js      loc_18000B095
0x18000b312  mov     edx, [rbp+var_40]
0x18000b315  xor     r8d, r8d
0x18000b318  mov     [rbp+arg_10], 0FFFFFFFEh
0x18000b31f  jmp     loc_18000B246
0x18000b324  lea     rax, [rbp+arg_0]
0x18000b328  mov     [rbp+arg_0], 0
0x18000b32f  mov     r9d, r14d; unsigned int
0x18000b332  mov     [rsp+70h+var_50], rax; unsigned int *
0x18000b337  mov     r8, r13; void *
0x18000b33a  xor     edx, edx; unsigned __int64
0x18000b33c  mov     rcx, rsi; this
0x18000b33f  call    ?WriteAt@CDirectStream@@QEAAJ_KPEBXKPEAK@Z; CDirectStream::WriteAt(unsigned __int64,void const *,ulong,ulong *)
0x18000b344  mov     ebx, eax
0x18000b346  test    eax, eax
0x18000b348  js      loc_18000B0C6
0x18000b34e  cmp     [rbp+arg_0], r14d
0x18000b352  jz      short loc_18000B37E
0x18000b354  mov     ebx, 800300FDh
0x18000b359  jmp     loc_18000B0C6
0x18000b35e  shr     r14d, 1
0x18000b361  cmp     r14d, ebx
0x18000b364  jnb     loc_18000B280
0x18000b36a  mov     ebx, 80030008h
0x18000b36f  jmp     loc_18000B095
0x18000b374  mov     ebx, 800300FDh
0x18000b379  jmp     loc_18000B2E8
0x18000b37e  mov     edx, [rbp+var_40]; unsigned int
0x18000b381  xor     r8d, r8d; unsigned int
0x18000b384  mov     rcx, [rbp+var_28]; this
0x18000b388  call    ?SetChainLength@CFat@@QEAAJKK@Z; CFat::SetChainLength(ulong,ulong)
0x18000b38d  mov     ebx, eax
0x18000b38f  test    eax, eax
0x18000b391  js      loc_18000B0C6
0x18000b397  mov     rcx, rdi; this
0x18000b39a  call    ?SetMiniSize@CMStream@@QEAAJXZ; CMStream::SetMiniSize(void)
0x18000b39f  mov     ebx, eax
0x18000b3a1  test    eax, eax
0x18000b3a3  js      loc_18000B0C6
0x18000b3a9  mov     rcx, rdi; this
0x18000b3ac  call    ?SetSize@CMStream@@QEAAJXZ; CMStream::SetSize(void)
0x18000b3b1  mov     ebx, eax
0x18000b3b3  test    eax, eax
0x18000b3b5  js      loc_18000B0C6
0x18000b3bb  jmp     loc_18000B1EA
```
