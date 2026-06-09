# GcAlloc::ReclaimGarbage(void)

- ea: `0x18000ecc0`
- end: `0x18000f004`
- name: `?ReclaimGarbage@GcAlloc@@QEAAXXZ`
- size: `836`
- prototype: `void __fastcall(GcAlloc *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180034200`
- `0x1800628b0`

## callees

- `0x18000b970`
- `0x18000ecc0`
- `0x18000f5e0`
- `0x18000f630`
- `0x180034830`
- `0x180043860`
- `0x180057694`
- `0x180096010`

## import_xrefs

- `msvcrt!free` at `0x18000eef7`
- `msvcrt!free` at `0x18000eef7`
- `OLEAUT32!__imp_VariantClear` at `0x18000eeb1`
- `OLEAUT32!__imp_VariantClear` at `0x18000eeb1`
- `KERNEL32!DeleteCriticalSection` at `0x18000efca`
- `KERNEL32!DeleteCriticalSection` at `0x18000efca`

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
                  AString::`scalar deleting destructor'(v20);
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
0x18000ecc0  mov     [rsp+arg_0], rcx
0x18000ecc5  push    rbx
0x18000ecc6  push    rbp
0x18000ecc7  push    rsi
0x18000ecc8  push    rdi
0x18000ecc9  push    r12
0x18000eccb  push    r13
0x18000eccd  push    r14
0x18000eccf  push    r15
0x18000ecd1  sub     rsp, 48h
0x18000ecd5  xor     edx, edx
0x18000ecd7  mov     qword ptr [rcx+20h], 0
0x18000ecdf  xor     r10d, r10d
0x18000ece2  mov     [rsp+88h+arg_8], edx
0x18000ece9  xor     r13d, r13d
0x18000ecec  mov     [rsp+88h+arg_10], r10d
0x18000ecf4  mov     r9, rcx
0x18000ecf7  lea     rbp, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000ecfe  mov     rcx, [rcx+18h]
0x18000ed02  xor     r12d, r12d
0x18000ed05  mov     eax, 800h
0x18000ed0a  mov     esi, 0F7FFh
0x18000ed0f  mov     r8d, 8Ah
0x18000ed15  mov     r11d, 81h
0x18000ed1b  mov     [rsp+88h+var_68], rcx
0x18000ed20  test    rcx, rcx
0x18000ed23  jz      loc_18000EFDD
0x18000ed29  mov     rdi, [rcx]
0x18000ed2c  lea     r15, [rcx+970h]
0x18000ed33  add     rcx, 10h; this
0x18000ed37  mov     [rsp+88h+var_58], rdi
0x18000ed3c  mov     [rsp+88h+var_60], rcx
0x18000ed41  mov     rbx, rcx
0x18000ed44  cmp     rbx, r15
0x18000ed47  jnb     loc_18000EF5E
0x18000ed4d  movzx   ecx, word ptr [rbx]
0x18000ed50  test    ax, cx
0x18000ed53  jz      loc_18000EE61
0x18000ed59  and     cx, si
0x18000ed5c  mov     [rbx], cx
0x18000ed5f  cmp     r8w, cx
0x18000ed63  jz      loc_18000EF6D
0x18000ed69  inc     r10d
0x18000ed6c  inc     r12d
0x18000ed6f  mov     [rsp+88h+arg_10], r10d
0x18000ed77  mov     r14d, 1
0x18000ed7d  cmp     cx, r11w
0x18000ed81  jnz     loc_18000EE76
0x18000ed87  mov     rdi, [rbx+8]
0x18000ed8b  cmp     [rdi+20h], rbp
0x18000ed8f  jz      loc_18000EE57
0x18000ed95  mov     rsi, [rdi+48h]
0x18000ed99  lock inc dword ptr [rsi]
0x18000ed9c  lea     rcx, [rsi+38h]; this
0x18000eda0  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18000eda5  test    eax, eax
0x18000eda7  jz      short loc_18000EDD5
0x18000eda9  cmp     dword ptr [rdi+8], 0
0x18000edad  mov     qword ptr [rdi+20h], 0
0x18000edb5  jnz     short loc_18000EDCC
0x18000edb7  mov     rax, [rdi]
0x18000edba  mov     edx, r14d
0x18000edbd  mov     rcx, rdi
0x18000edc0  mov     rax, [rax+198h]
0x18000edc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edcc  lea     rcx, [rsi+38h]; this
0x18000edd0  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18000edd5  mov     eax, 0FFFFFFFFh
0x18000edda  lock xadd [rsi], eax
0x18000edde  cmp     eax, r14d
0x18000ede1  jnz     short loc_18000EDEC
0x18000ede3  test    rsi, rsi
0x18000ede6  jnz     loc_18000EFC0
0x18000edec  lea     rbp, ?s_varNameTblConstructed@NameTbl@@1VVAR@@A; VAR NameTbl::s_varNameTblConstructed
0x18000edf3  mov     esi, 0F7FFh
0x18000edf8  mov     r10d, [rsp+88h+arg_10]
0x18000ee00  mov     r11d, 81h
0x18000ee06  mov     r9, [rsp+88h+arg_0]
0x18000ee0e  mov     r8d, 8Ah
0x18000ee14  mov     edx, [rsp+88h+arg_8]
0x18000ee1b  xor     eax, eax
0x18000ee1d  mov     [rbx], ax
0x18000ee20  mov     rax, [r9+10h]
0x18000ee24  test    byte ptr [rax+0Ch], 2
0x18000ee28  jnz     loc_18000EFF3
0x18000ee2e  mov     rcx, [r9+20h]
0x18000ee32  cmp     r13, rbx
0x18000ee35  jnz     loc_18000EEBC
0x18000ee3b  add     [rcx+8], r14d
0x18000ee3f  movsxd  rax, r14d
0x18000ee42  lea     rcx, [rax+rax*2]
0x18000ee46  mov     eax, 800h
0x18000ee4b  lea     rbx, [rbx+rcx*8]
0x18000ee4f  mov     r13, rbx
0x18000ee52  jmp     loc_18000ED44
0x18000ee57  mov     qword ptr [rdi+20h], 0
0x18000ee5f  jmp     short loc_18000EE1B
0x18000ee61  inc     edx
0x18000ee63  add     rbx, 18h
0x18000ee67  mov     [rsp+88h+arg_8], edx
0x18000ee6e  inc     r12d
0x18000ee71  jmp     loc_18000ED44
0x18000ee76  movzx   edx, cx
0x18000ee79  sub     edx, 82h
0x18000ee7f  jz      short loc_18000EED4
0x18000ee81  sub     edx, 4
0x18000ee84  jz      loc_18000EF36
0x18000ee8a  sub     edx, r14d
0x18000ee8d  jz      loc_18000EF36
0x18000ee93  sub     edx, 8; unsigned int
0x18000ee96  jz      short loc_18000EF0A
0x18000ee98  cmp     edx, r14d
0x18000ee9b  jz      loc_18000EF21
0x18000eea1  lea     eax, [rcx-8]
0x18000eea4  cmp     ax, 77h ; 'w'
0x18000eea8  ja      loc_18000EF4B
0x18000eeae  mov     rcx, rbx; pvarg
0x18000eeb1  call    cs:__imp_VariantClear
0x18000eeb7  jmp     loc_18000EDF8
0x18000eebc  lea     eax, [r14-1]
0x18000eec0  mov     [rbx], r8w
0x18000eec4  mov     [rbx+8], eax
0x18000eec7  mov     [rbx+10h], rcx
0x18000eecb  mov     [r9+20h], rbx
0x18000eecf  jmp     loc_18000EE3F
0x18000eed4  mov     rdi, [rbx+10h]
0x18000eed8  test    rdi, rdi
0x18000eedb  jz      loc_18000EE14
0x18000eee1  mov     eax, 0FFFFFFFFh
0x18000eee6  lock xadd [rdi+8], eax
0x18000eeeb  sub     eax, r14d
0x18000eeee  jg      loc_18000EE14
0x18000eef4  mov     rcx, [rdi]; Block
0x18000eef7  call    cs:__imp_free
0x18000eefd  mov     rcx, rdi; Block
0x18000ef00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ef05  jmp     loc_18000EDF8
0x18000ef0a  mov     rcx, [rbx+8]; this
0x18000ef0e  test    rcx, rcx
0x18000ef11  jz      loc_18000EE14
0x18000ef17  call    ??_GAString@@IEAAPEAXI@Z; AString::`scalar deleting destructor'(uint)
0x18000ef1c  jmp     loc_18000EDF8
0x18000ef21  mov     rcx, [rbx+8]
0x18000ef25  xor     edx, edx
0x18000ef27  mov     rax, [rcx]
0x18000ef2a  mov     rax, [rax+80h]
0x18000ef31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef36  mov     rcx, [rbx+8]
0x18000ef3a  mov     rax, [rcx]
0x18000ef3d  mov     rax, [rax+10h]
0x18000ef41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef46  jmp     loc_18000EDF8
0x18000ef4b  mov     eax, 91h
0x18000ef50  cmp     cx, ax
0x18000ef53  jnb     loc_18000EEAE
0x18000ef59  jmp     loc_18000EE14
0x18000ef5e  cmp     r13, r15
0x18000ef61  jz      short loc_18000EF79
0x18000ef63  mov     rcx, [rsp+88h+var_58]
0x18000ef68  jmp     loc_18000ED1B
0x18000ef6d  mov     r14d, [rbx+8]
0x18000ef71  inc     r14d
0x18000ef74  jmp     loc_18000EE20
0x18000ef79  mov     rax, [r9+20h]
0x18000ef7d  cmp     rax, [rsp+88h+var_60]
0x18000ef82  jnz     short loc_18000EFB9
0x18000ef84  mov     rax, [rax+10h]
0x18000ef88  mov     rdx, [rsp+88h+var_68]; struct GcBlock *
0x18000ef8d  mov     [r9+20h], rax
0x18000ef91  call    ?FreeBlk@GcBlockFactory@@QEAAXPEAVGcBlock@@@Z; GcBlockFactory::FreeBlk(GcBlock *)
0x18000ef96  mov     r9, [rsp+88h+arg_0]
0x18000ef9e  mov     r8d, 8Ah
0x18000efa4  mov     edx, [rsp+88h+arg_8]
0x18000efab  mov     r11d, 81h
0x18000efb1  mov     r10d, [rsp+88h+arg_10]
0x18000efb9  mov     eax, 800h
0x18000efbe  jmp     short loc_18000EF63
0x18000efc0  cmp     byte ptr [rsi+61h], 0
0x18000efc4  jz      short loc_18000EFD0
0x18000efc6  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000efca  call    cs:__imp_DeleteCriticalSection
0x18000efd0  mov     rcx, rsi; Block
0x18000efd3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000efd8  jmp     loc_18000EDEC
0x18000efdd  mov     rax, [r9+10h]
0x18000efe1  mov     r8d, r12d; int
0x18000efe4  add     [rax+74h], edx
0x18000efe7  mov     edx, r10d; int
0x18000efea  mov     rcx, [r9+10h]; this
0x18000efee  call    ?Adapt@GcContext@@QEAAXJJ@Z; GcContext::Adapt(long,long)
0x18000eff3  add     rsp, 48h
0x18000eff7  pop     r15
0x18000eff9  pop     r14
0x18000effb  pop     r13
0x18000effd  pop     r12
0x18000efff  pop     rdi
0x18000f000  pop     rsi
0x18000f001  pop     rbp
0x18000f002  pop     rbx
0x18000f003  retn
```
