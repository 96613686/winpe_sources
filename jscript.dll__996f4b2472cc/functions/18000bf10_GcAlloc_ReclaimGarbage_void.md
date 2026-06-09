# GcAlloc::ReclaimGarbage(void)

- ea: `0x18000bf10`
- end: `0x18000c267`
- name: `?ReclaimGarbage@GcAlloc@@QEAAXXZ`
- size: `855`
- prototype: `void __fastcall(GcAlloc *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18003bd60`
- `0x180063b10`

## callees

- `0x180008ad0`
- `0x18000bf10`
- `0x18000c860`
- `0x18000c8c0`
- `0x18003c300`
- `0x180044b00`
- `0x1800585c4`
- `0x180098010`

## import_xrefs

- `msvcrt!free` at `0x18000c14d`
- `msvcrt!free` at `0x18000c14d`
- `OLEAUT32!__imp_VariantClear` at `0x18000c101`
- `OLEAUT32!__imp_VariantClear` at `0x18000c101`
- `KERNEL32!DeleteCriticalSection` at `0x18000c226`
- `KERNEL32!DeleteCriticalSection` at `0x18000c226`

## pseudocode

```c
void __fastcall GcAlloc::ReclaimGarbage(GcAlloc *this)
{
  int v1; // edx
  int v2; // r10d
  VARIANTARG *v3; // r13
  GcAlloc *v4; // r9
  _QWORD *v5; // rcx
  int v6; // r12d
  __int64 v7; // r8
  _QWORD *v8; // rdi
  VARIANTARG *v9; // r15
  __int64 vt; // rcx
  VARIANTARG *v11; // rbx
  VARTYPE v12; // cx
  int v13; // r14d
  LONGLONG llVal; // rdi
  __int64 v15; // rsi
  bool v16; // zf
  __int64 v17; // rcx
  __int64 v18; // rdx
  IRecordInfo *pRecInfo; // rdi
  AString *v20; // rcx
  __int64 v21; // rax
  struct GcBlock *v22; // [rsp+20h] [rbp-68h]
  __int64 v23; // [rsp+28h] [rbp-60h]
  _QWORD *v24; // [rsp+30h] [rbp-58h]
  int v26; // [rsp+98h] [rbp+10h]
  int v27; // [rsp+A0h] [rbp+18h]

  v1 = 0;
  *((_QWORD *)this + 4) = 0;
  v2 = 0;
  v26 = 0;
  v3 = 0;
  v27 = 0;
  v4 = this;
  v5 = (_QWORD *)*((_QWORD *)this + 3);
  v6 = 0;
  v7 = 138;
  while ( 1 )
  {
    v22 = (struct GcBlock *)v5;
    if ( !v5 )
      break;
    v8 = (_QWORD *)*v5;
    v9 = (VARIANTARG *)(v5 + 302);
    vt = (__int64)(v5 + 2);
    v24 = v8;
    v23 = vt;
    v11 = (VARIANTARG *)vt;
    while ( v11 < v9 )
    {
      vt = v11->vt;
      if ( (vt & 0x800) != 0 )
      {
        v12 = vt & 0xF7FF;
        v11->vt = v12;
        if ( v12 != 138 )
        {
          ++v2;
          ++v6;
          v27 = v2;
          v13 = 1;
          if ( v12 == 129 )
          {
            llVal = v11->llVal;
            if ( *(__int64 **)(llVal + 32) == NameTbl::s_varNameTblConstructed )
            {
              *(_QWORD *)(llVal + 32) = 0;
            }
            else
            {
              v15 = *(_QWORD *)(llVal + 72);
              _InterlockedIncrement((volatile signed __int32 *)v15);
              if ( (unsigned int)MUTX::Enter((MUTX *)(v15 + 56)) )
              {
                v16 = *(_DWORD *)(llVal + 8) == 0;
                *(_QWORD *)(llVal + 32) = 0;
                if ( v16 )
                  (*(void (__fastcall **)(LONGLONG, __int64))(*(_QWORD *)llVal + 408LL))(llVal, 1);
                MUTX::Leave((MUTX *)(v15 + 56));
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15, 0xFFFFFFFF) == 1 && v15 )
              {
                if ( *(_BYTE *)(v15 + 97) )
                  DeleteCriticalSection((LPCRITICAL_SECTION)(v15 + 56));
                operator delete((void *)v15);
              }
LABEL_15:
              v2 = v27;
              v4 = this;
              v7 = 138;
LABEL_16:
              v1 = v26;
            }
            v11->vt = 0;
            goto LABEL_18;
          }
          if ( v12 == 130 )
          {
            pRecInfo = v11->pRecInfo;
            if ( pRecInfo && _InterlockedExchangeAdd((volatile signed __int32 *)&pRecInfo[1], 0xFFFFFFFF) <= 1 )
            {
              free(pRecInfo->lpVtbl);
              operator delete(pRecInfo);
              goto LABEL_15;
            }
            goto LABEL_16;
          }
          v18 = (unsigned int)v12 - 134;
          if ( v12 != 134 )
          {
            v18 = (unsigned int)v12 - 135;
            if ( v12 != 135 )
            {
              if ( v12 == 143 )
              {
                v20 = (AString *)v11->llVal;
                if ( v20 )
                {
                  AString::`scalar deleting destructor'(v20, 0);
                  goto LABEL_15;
                }
                goto LABEL_16;
              }
              if ( v12 != 144 )
              {
                if ( (unsigned __int16)(v12 - 8) <= 0x77u || v12 >= 0x91u )
                {
                  VariantClear(v11);
                  goto LABEL_15;
                }
                goto LABEL_16;
              }
              (*(void (__fastcall **)(LONGLONG, _QWORD, __int64, GcAlloc *, struct GcBlock *))(*v11->pllVal + 128))(
                v11->llVal,
                0,
                138,
                v4,
                v22);
            }
          }
          (*(void (__fastcall **)(LONGLONG, __int64, __int64, GcAlloc *))(*v11->pllVal + 16))(v11->llVal, v18, v7, v4);
          goto LABEL_15;
        }
        v13 = v11->lVal + 1;
LABEL_18:
        if ( (*(_BYTE *)(*((_QWORD *)v4 + 2) + 12LL) & 2) != 0 )
          return;
        v17 = *((_QWORD *)v4 + 4);
        if ( v3 == v11 )
        {
          *(_DWORD *)(v17 + 8) += v13;
        }
        else
        {
          v11->vt = 138;
          v11->lVal = v13 - 1;
          v11->pRecInfo = (IRecordInfo *)v17;
          *((_QWORD *)v4 + 4) = v11;
        }
        vt = 3LL * v13;
        v11 += v13;
        v3 = v11;
      }
      else
      {
        ++v1;
        ++v11;
        v26 = v1;
        ++v6;
      }
    }
    if ( v3 == v9 )
    {
      v21 = *((_QWORD *)v4 + 4);
      if ( v21 == v23 )
      {
        *((_QWORD *)v4 + 4) = *(_QWORD *)(v21 + 16);
        GcBlockFactory::FreeBlk((GcBlockFactory *)vt, v22);
        v4 = this;
        v7 = 138;
        v1 = v26;
        v2 = v27;
      }
    }
    v5 = v24;
  }
  *(_DWORD *)(*((_QWORD *)v4 + 2) + 116LL) += v1;
  GcContext::Adapt(*((GcContext **)v4 + 2), v2, v6);
}

```

## disassembly

```asm
0x18000bf10  mov     [rsp+arg_0], rcx
0x18000bf15  push    rbx
0x18000bf16  push    rbp
0x18000bf17  push    rsi
0x18000bf18  push    rdi
0x18000bf19  push    r12
0x18000bf1b  push    r13
0x18000bf1d  push    r14
0x18000bf1f  push    r15
0x18000bf21  sub     rsp, 48h
0x18000bf25  xor     edx, edx
0x18000bf27  mov     qword ptr [rcx+20h], 0
0x18000bf2f  xor     r10d, r10d
0x18000bf32  mov     [rsp+88h+arg_8], edx
0x18000bf39  xor     r13d, r13d
0x18000bf3c  mov     [rsp+88h+arg_10], r10d
0x18000bf44  mov     r9, rcx
0x18000bf47  lea     rbp, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000bf4e  mov     rcx, [rcx+18h]
0x18000bf52  xor     r12d, r12d
0x18000bf55  mov     eax, 800h
0x18000bf5a  mov     esi, 0F7FFh
0x18000bf5f  mov     r8d, 8Ah
0x18000bf65  mov     r11d, 81h
0x18000bf6b  mov     [rsp+88h+var_68], rcx
0x18000bf70  test    rcx, rcx
0x18000bf73  jz      loc_18000C23F
0x18000bf79  mov     rdi, [rcx]
0x18000bf7c  lea     r15, [rcx+970h]
0x18000bf83  add     rcx, 10h; this
0x18000bf87  mov     [rsp+88h+var_58], rdi
0x18000bf8c  mov     [rsp+88h+var_60], rcx
0x18000bf91  mov     rbx, rcx
0x18000bf94  cmp     rbx, r15
0x18000bf97  jnb     loc_18000C1BA
0x18000bf9d  movzx   ecx, word ptr [rbx]
0x18000bfa0  test    ax, cx
0x18000bfa3  jz      loc_18000C0B1
0x18000bfa9  and     cx, si
0x18000bfac  mov     [rbx], cx
0x18000bfaf  cmp     r8w, cx
0x18000bfb3  jz      loc_18000C1C9
0x18000bfb9  inc     r10d
0x18000bfbc  inc     r12d
0x18000bfbf  mov     [rsp+88h+arg_10], r10d
0x18000bfc7  mov     r14d, 1
0x18000bfcd  cmp     cx, r11w
0x18000bfd1  jnz     loc_18000C0C6
0x18000bfd7  mov     rdi, [rbx+8]
0x18000bfdb  cmp     [rdi+20h], rbp
0x18000bfdf  jz      loc_18000C0A7
0x18000bfe5  mov     rsi, [rdi+48h]
0x18000bfe9  lock inc dword ptr [rsi]
0x18000bfec  lea     rcx, [rsi+38h]; this
0x18000bff0  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000bff5  test    eax, eax
0x18000bff7  jz      short loc_18000C025
0x18000bff9  cmp     dword ptr [rdi+8], 0
0x18000bffd  mov     qword ptr [rdi+20h], 0
0x18000c005  jnz     short loc_18000C01C
0x18000c007  mov     rax, [rdi]
0x18000c00a  mov     edx, r14d
0x18000c00d  mov     rcx, rdi
0x18000c010  mov     rax, [rax+198h]
0x18000c017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c01c  lea     rcx, [rsi+38h]; this
0x18000c020  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000c025  mov     eax, 0FFFFFFFFh
0x18000c02a  lock xadd [rsi], eax
0x18000c02e  cmp     eax, r14d
0x18000c031  jnz     short loc_18000C03C
0x18000c033  test    rsi, rsi
0x18000c036  jnz     loc_18000C21C
0x18000c03c  lea     rbp, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000c043  mov     esi, 0F7FFh
0x18000c048  mov     r10d, [rsp+88h+arg_10]
0x18000c050  mov     r11d, 81h
0x18000c056  mov     r9, [rsp+88h+arg_0]
0x18000c05e  mov     r8d, 8Ah
0x18000c064  mov     edx, [rsp+88h+arg_8]
0x18000c06b  xor     eax, eax
0x18000c06d  mov     [rbx], ax
0x18000c070  mov     rax, [r9+10h]
0x18000c074  test    byte ptr [rax+0Ch], 2
0x18000c078  jnz     loc_18000C255
0x18000c07e  mov     rcx, [r9+20h]
0x18000c082  cmp     r13, rbx
0x18000c085  jnz     loc_18000C112
0x18000c08b  add     [rcx+8], r14d
0x18000c08f  movsxd  rax, r14d
0x18000c092  lea     rcx, [rax+rax*2]
0x18000c096  mov     eax, 800h
0x18000c09b  lea     rbx, [rbx+rcx*8]
0x18000c09f  mov     r13, rbx
0x18000c0a2  jmp     loc_18000BF94
0x18000c0a7  mov     qword ptr [rdi+20h], 0
0x18000c0af  jmp     short loc_18000C06B
0x18000c0b1  inc     edx
0x18000c0b3  add     rbx, 18h
0x18000c0b7  mov     [rsp+88h+arg_8], edx
0x18000c0be  inc     r12d
0x18000c0c1  jmp     loc_18000BF94
0x18000c0c6  movzx   edx, cx
0x18000c0c9  sub     edx, 82h
0x18000c0cf  jz      short loc_18000C12A
0x18000c0d1  sub     edx, 4
0x18000c0d4  jz      loc_18000C192
0x18000c0da  sub     edx, r14d
0x18000c0dd  jz      loc_18000C192
0x18000c0e3  sub     edx, 8; unsigned int
0x18000c0e6  jz      short loc_18000C166
0x18000c0e8  cmp     edx, r14d
0x18000c0eb  jz      loc_18000C17D
0x18000c0f1  lea     eax, [rcx-8]
0x18000c0f4  cmp     ax, 77h ; 'w'
0x18000c0f8  ja      loc_18000C1A7
0x18000c0fe  mov     rcx, rbx; pvarg
0x18000c101  call    cs:__imp_VariantClear
0x18000c108  nop     dword ptr [rax+rax+00h]
0x18000c10d  jmp     loc_18000C048
0x18000c112  lea     eax, [r14-1]
0x18000c116  mov     [rbx], r8w
0x18000c11a  mov     [rbx+8], eax
0x18000c11d  mov     [rbx+10h], rcx
0x18000c121  mov     [r9+20h], rbx
0x18000c125  jmp     loc_18000C08F
0x18000c12a  mov     rdi, [rbx+10h]
0x18000c12e  test    rdi, rdi
0x18000c131  jz      loc_18000C064
0x18000c137  mov     eax, 0FFFFFFFFh
0x18000c13c  lock xadd [rdi+8], eax
0x18000c141  sub     eax, r14d
0x18000c144  jg      loc_18000C064
0x18000c14a  mov     rcx, [rdi]; Block
0x18000c14d  call    cs:__imp_free
0x18000c154  nop     dword ptr [rax+rax+00h]
0x18000c159  mov     rcx, rdi; Block
0x18000c15c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c161  jmp     loc_18000C048
0x18000c166  mov     rcx, [rbx+8]; this
0x18000c16a  test    rcx, rcx
0x18000c16d  jz      loc_18000C064
0x18000c173  call    ??_GAString@@IEAAPEAXI@Z; AString::`scalar deleting destructor'(uint)
0x18000c178  jmp     loc_18000C048
0x18000c17d  mov     rcx, [rbx+8]
0x18000c181  xor     edx, edx
0x18000c183  mov     rax, [rcx]
0x18000c186  mov     rax, [rax+80h]
0x18000c18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c192  mov     rcx, [rbx+8]
0x18000c196  mov     rax, [rcx]
0x18000c199  mov     rax, [rax+10h]
0x18000c19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a2  jmp     loc_18000C048
0x18000c1a7  mov     eax, 91h
0x18000c1ac  cmp     cx, ax
0x18000c1af  jnb     loc_18000C0FE
0x18000c1b5  jmp     loc_18000C064
0x18000c1ba  cmp     r13, r15
0x18000c1bd  jz      short loc_18000C1D5
0x18000c1bf  mov     rcx, [rsp+88h+var_58]
0x18000c1c4  jmp     loc_18000BF6B
0x18000c1c9  mov     r14d, [rbx+8]
0x18000c1cd  inc     r14d
0x18000c1d0  jmp     loc_18000C070
0x18000c1d5  mov     rax, [r9+20h]
0x18000c1d9  cmp     rax, [rsp+88h+var_60]
0x18000c1de  jnz     short loc_18000C215
0x18000c1e0  mov     rax, [rax+10h]
0x18000c1e4  mov     rdx, [rsp+88h+var_68]; struct GcBlock *
0x18000c1e9  mov     [r9+20h], rax
0x18000c1ed  call    ?FreeBlk@GcBlockFactory@@QEAAXPEAVGcBlock@@@Z; GcBlockFactory::FreeBlk(GcBlock *)
0x18000c1f2  mov     r9, [rsp+88h+arg_0]
0x18000c1fa  mov     r8d, 8Ah
0x18000c200  mov     edx, [rsp+88h+arg_8]
0x18000c207  mov     r11d, 81h
0x18000c20d  mov     r10d, [rsp+88h+arg_10]
0x18000c215  mov     eax, 800h
0x18000c21a  jmp     short loc_18000C1BF
0x18000c21c  cmp     byte ptr [rsi+61h], 0
0x18000c220  jz      short loc_18000C232
0x18000c222  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000c226  call    cs:__imp_DeleteCriticalSection
0x18000c22d  nop     dword ptr [rax+rax+00h]
0x18000c232  mov     rcx, rsi; Block
0x18000c235  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c23a  jmp     loc_18000C03C
0x18000c23f  mov     rax, [r9+10h]
0x18000c243  mov     r8d, r12d; int
0x18000c246  add     [rax+74h], edx
0x18000c249  mov     edx, r10d; int
0x18000c24c  mov     rcx, [r9+10h]; this
0x18000c250  call    ?Adapt@GcContext@@QEAAXJJ@Z; GcContext::Adapt(long,long)
0x18000c255  add     rsp, 48h
0x18000c259  pop     r15
0x18000c25b  pop     r14
0x18000c25d  pop     r13
0x18000c25f  pop     r12
0x18000c261  pop     rdi
0x18000c262  pop     rsi
0x18000c263  pop     rbp
0x18000c264  pop     rbx
0x18000c265  retn
```
