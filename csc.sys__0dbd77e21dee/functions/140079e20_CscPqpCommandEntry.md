# CscPqpCommandEntry

- ea: `0x140079e20`
- end: `0x14007a255`
- name: `CscPqpCommandEntry`
- size: `1077`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14001256c`
- `0x140014de0`
- `0x140026874`
- `0x14002cad0`
- `0x14002cccc`

## callees

- `0x1400063f0`
- `0x140007228`
- `0x1400190ec`
- `0x14002d1e4`
- `0x14002f440`
- `0x140079e20`
- `0x14007a25c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140079ea3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140079ea3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140079f06`
- `ntoskrnl!ExReleaseResourceLite` at `0x140079f06`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140079fff`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140079fff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140079fbb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140079fbb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007a0c6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14007a0c6`

## pseudocode

```c
__int64 __fastcall CscPqpCommandEntry(
        __int64 a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        unsigned __int8 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v12; // rdx
  unsigned __int64 v13; // r12
  int Entry; // edi
  int v15; // esi
  _QWORD *v17; // rax
  _QWORD *v18; // rbp
  int v19; // esi
  _BYTE v20[8]; // [rsp+60h] [rbp-58h] BYREF
  __int64 v21; // [rsp+68h] [rbp-50h] BYREF
  int v22; // [rsp+70h] [rbp-48h]
  __int64 v23; // [rsp+78h] [rbp-40h]

  v23 = a8;
  v21 = a6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qdDidqqq(WPP_GLOBAL_Control->AttachedDevice, a6, a8, a1, a2, a3, a4, a5, a6, a7, a8);
  if ( *(_BYTE *)(a1 + 88) )
  {
    Entry = -1073741596;
    v15 = 1764;
    goto LABEL_11;
  }
  if ( a2 )
  {
    if ( a2 != 1 && a2 != 2 )
    {
      Entry = -1073740768;
      v15 = 1801;
      goto LABEL_11;
    }
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 96), 1u);
  }
  else
  {
    ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 96), 1u);
  }
  if ( *(_BYTE *)(a1 + 88) )
  {
    Entry = -1073741596;
    v15 = 1807;
    goto LABEL_10;
  }
  if ( a3 )
  {
    if ( a3 <= *(_DWORD *)(a1 + 36) )
    {
      v12 = *(unsigned int *)(a1 + 24);
      v13 = *(unsigned int *)(a1 + 20) + (unsigned __int64)((unsigned int)v12 * (a3 - 1));
      if ( ((v13 ^ (v13 + v12)) & 0xFFFFFFFFFFFC0000uLL) == 0 )
      {
        if ( v13 )
        {
          v17 = ExAllocateFromPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(a1 + 152));
          v18 = v17;
          if ( !v17 )
          {
            Entry = -1073741670;
            v15 = 1821;
            goto LABEL_10;
          }
          Entry = CscPqpReadEntry(a1, v13, v17);
          if ( Entry < 0 )
          {
            v15 = 1825;
          }
          else
          {
            if ( a4 != *v18 )
            {
              Entry = -1073741802;
              v15 = 1834;
              goto LABEL_29;
            }
            if ( a2 )
            {
              v19 = a2 - 1;
              if ( v19 )
              {
                if ( v19 != 1 )
                {
                  Entry = -1073740768;
                  v15 = 1892;
                  goto LABEL_29;
                }
                v21 = 0x300000003LL;
                v22 = 3;
                Entry = CscPqpUpdateEntry(a1, a3, (_DWORD)v18, v13, 0, 0, 0, (__int64)&v21, (__int64)v20);
                if ( Entry < 0 )
                {
                  v15 = 1864;
                  goto LABEL_29;
                }
                memset(v18, 0, 0xD0u);
                *((_DWORD *)v18 + 3) = *(_DWORD *)(a1 + 52);
                *((_DWORD *)v18 + 2) = 1;
                Entry = CscPqpWriteEntry(a1, v13, 1, v18);
                if ( Entry < 0 )
                {
                  v15 = 1881;
                  goto LABEL_29;
                }
                ++*(_DWORD *)(a1 + 40);
                *(_DWORD *)(a1 + 52) = a3;
              }
              else
              {
                Entry = CscPqpUpdateEntry(a1, a3, (_DWORD)v18, v13, a5, v21, a7, v23, 0);
                if ( Entry < 0 )
                {
                  v15 = 1845;
                  goto LABEL_29;
                }
              }
            }
            else
            {
              *(_OWORD *)a7 = *(_OWORD *)(v18 + 5);
              *(_OWORD *)(a7 + 16) = *(_OWORD *)(v18 + 7);
              *(_OWORD *)(a7 + 32) = *(_OWORD *)(v18 + 9);
              *(_OWORD *)(a7 + 48) = *(_OWORD *)(v18 + 11);
              *(_OWORD *)(a7 + 64) = *(_OWORD *)(v18 + 13);
              *(_OWORD *)(a7 + 80) = *(_OWORD *)(v18 + 15);
              *(_OWORD *)(a7 + 96) = *(_OWORD *)(v18 + 17);
              *(_OWORD *)(a7 + 112) = *(_OWORD *)(v18 + 19);
              *(_OWORD *)(a7 + 128) = *(_OWORD *)(v18 + 21);
              *(_OWORD *)(a7 + 144) = *(_OWORD *)(v18 + 23);
              *(_QWORD *)(a7 + 160) = v18[25];
            }
            v15 = 0;
          }
LABEL_29:
          ExFreeToPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(a1 + 152), v18);
          goto LABEL_10;
        }
      }
    }
  }
  Entry = -1073741802;
  v15 = 1814;
LABEL_10:
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 96));
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      WPP_eb62243048b93ac38d7f5193621ee294_Traceguids,
      (unsigned int)Entry,
      v15);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x140079e20  mov     rax, rsp
0x140079e23  push    rsi
0x140079e24  sub     rsp, 0B0h
0x140079e2b  mov     [rax+10h], rbx
0x140079e2f  mov     esi, edx
0x140079e31  mov     rdx, [rsp+0B8h+arg_28]
0x140079e39  mov     rbx, rcx
0x140079e3c  mov     [rax-10h], rbp
0x140079e40  mov     [rax-28h], r13
0x140079e44  mov     r13, r9
0x140079e47  mov     [rax-30h], r14
0x140079e4b  mov     r14, [rsp+0B8h+arg_30]
0x140079e53  mov     [rax-38h], r15
0x140079e57  mov     r15d, r8d
0x140079e5a  mov     r8, [rsp+0B8h+arg_38]
0x140079e62  mov     [rsp+0B8h+var_40], r8
0x140079e67  mov     [rsp+0B8h+var_50], rdx
0x140079e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140079e73  lea     rbp, WPP_GLOBAL_Control
0x140079e7a  cmp     rcx, rbp
0x140079e7d  jnz     loc_140079F67
0x140079e83  cmp     byte ptr [rbx+58h], 0
0x140079e87  mov     [rsp+0B8h+var_18], rdi
0x140079e8f  jnz     loc_140079FE0
0x140079e95  test    esi, esi
0x140079e97  jnz     loc_140079FAE
0x140079e9d  mov     rcx, [rbx+60h]; Resource
0x140079ea1  mov     dl, 1; Wait
0x140079ea3  call    cs:__imp_ExAcquireResourceSharedLite
0x140079eaa  nop     dword ptr [rax+rax+00h]
0x140079eaf  cmp     byte ptr [rbx+58h], 0
0x140079eb3  jnz     loc_14007A1F1
0x140079eb9  mov     [rsp+0B8h+var_20], r12
0x140079ec1  test    r15d, r15d
0x140079ec4  jz      short loc_140079EF0
0x140079ec6  cmp     r15d, [rbx+24h]
0x140079eca  ja      short loc_140079EF0
0x140079ecc  mov     edx, [rbx+18h]
0x140079ecf  lea     r12d, [r15-1]
0x140079ed3  mov     eax, [rbx+14h]
0x140079ed6  imul    r12d, edx
0x140079eda  add     r12, rax
0x140079edd  add     rdx, r12
0x140079ee0  xor     rdx, r12
0x140079ee3  test    rdx, 0FFFFFFFFFFFC0000h
0x140079eea  jz      loc_140079FEF
0x140079ef0  mov     edi, 0C0000016h
0x140079ef5  mov     esi, 716h
0x140079efa  mov     r12, [rsp+0B8h+var_20]
0x140079f02  mov     rcx, [rbx+60h]; Resource
0x140079f06  call    cs:__imp_ExReleaseResourceLite
0x140079f0d  nop     dword ptr [rax+rax+00h]
0x140079f12  mov     rcx, cs:WPP_GLOBAL_Control
0x140079f19  mov     r15, [rsp+0B8h+var_38]
0x140079f21  cmp     rcx, rbp
0x140079f24  mov     rbp, [rsp+0B8h+var_10]
0x140079f2c  mov     r14, [rsp+0B8h+var_30]
0x140079f34  mov     r13, [rsp+0B8h+var_28]
0x140079f3c  mov     rbx, [rsp+0B8h+arg_8]
0x140079f44  jz      short loc_140079F53
0x140079f46  test    dword ptr [rcx+2Ch], 40000h
0x140079f4d  jnz     loc_14007A234
0x140079f53  mov     eax, edi
0x140079f55  mov     rdi, [rsp+0B8h+var_18]
0x140079f5d  add     rsp, 0B0h
0x140079f64  pop     rsi
0x140079f65  retn
0x140079f67  test    dword ptr [rcx+2Ch], 40000h
0x140079f6e  jz      loc_140079E83
0x140079f74  movzx   eax, [rsp+0B8h+arg_20]
0x140079f7c  mov     r9, rbx
0x140079f7f  mov     rcx, [rcx+18h]
0x140079f83  mov     [rsp+0B8h+var_68], r8
0x140079f88  mov     [rsp+0B8h+var_70], r14
0x140079f8d  mov     [rsp+0B8h+var_78], rdx
0x140079f92  mov     dword ptr [rsp+0B8h+var_80], eax
0x140079f96  mov     [rsp+0B8h+var_88], r13
0x140079f9b  mov     dword ptr [rsp+0B8h+var_90], r15d
0x140079fa0  mov     [rsp+0B8h+var_98], esi
0x140079fa4  call    WPP_SF_qdDidqqq
0x140079fa9  jmp     loc_140079E83
0x140079fae  mov     ecx, esi
0x140079fb0  sub     ecx, 1
0x140079fb3  jnz     short loc_140079FCC
0x140079fb5  mov     rcx, [rbx+60h]; Resource
0x140079fb9  mov     dl, 1; Wait
0x140079fbb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140079fc2  nop     dword ptr [rax+rax+00h]
0x140079fc7  jmp     loc_140079EAF
0x140079fcc  cmp     ecx, 1
0x140079fcf  jz      short loc_140079FB5
0x140079fd1  mov     edi, 0C0000420h
0x140079fd6  mov     esi, 709h
0x140079fdb  jmp     loc_140079F12
0x140079fe0  mov     edi, 0C00000E4h
0x140079fe5  mov     esi, 6E4h
0x140079fea  jmp     loc_140079F12
0x140079fef  test    r12, r12
0x140079ff2  jz      loc_140079EF0
0x140079ff8  mov     rcx, [rbx+98h]; Lookaside
0x140079fff  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14007a006  nop     dword ptr [rax+rax+00h]
0x14007a00b  mov     rbp, rax
0x14007a00e  test    rax, rax
0x14007a011  jz      loc_14007A0E5
0x14007a017  mov     r8, rax
0x14007a01a  mov     rdx, r12
0x14007a01d  mov     rcx, rbx
0x14007a020  call    CscPqpReadEntry
0x14007a025  mov     edi, eax
0x14007a027  test    eax, eax
0x14007a029  js      loc_14007A0DE
0x14007a02f  cmp     r13, [rbp+0]
0x14007a033  jnz     loc_14007A200
0x14007a039  test    esi, esi
0x14007a03b  jnz     loc_14007A0FB
0x14007a041  movups  xmm0, xmmword ptr [rbp+28h]
0x14007a045  movups  xmmword ptr [r14], xmm0
0x14007a049  movups  xmm1, xmmword ptr [rbp+38h]
0x14007a04d  movups  xmmword ptr [r14+10h], xmm1
0x14007a052  movups  xmm0, xmmword ptr [rbp+48h]
0x14007a056  movups  xmmword ptr [r14+20h], xmm0
0x14007a05b  movups  xmm1, xmmword ptr [rbp+58h]
0x14007a05f  movups  xmmword ptr [r14+30h], xmm1
0x14007a064  movups  xmm0, xmmword ptr [rbp+68h]
0x14007a068  movups  xmmword ptr [r14+40h], xmm0
0x14007a06d  movups  xmm1, xmmword ptr [rbp+78h]
0x14007a071  movups  xmmword ptr [r14+50h], xmm1
0x14007a076  movups  xmm0, xmmword ptr [rbp+88h]
0x14007a07d  movups  xmmword ptr [r14+60h], xmm0
0x14007a082  movups  xmm1, xmmword ptr [rbp+98h]
0x14007a089  movups  xmmword ptr [r14+70h], xmm1
0x14007a08e  movups  xmm0, xmmword ptr [rbp+0A8h]
0x14007a095  movups  xmmword ptr [r14+80h], xmm0
0x14007a09d  movups  xmm1, xmmword ptr [rbp+0B8h]
0x14007a0a4  movups  xmmword ptr [r14+90h], xmm1
0x14007a0ac  mov     rax, [rbp+0C8h]
0x14007a0b3  mov     [r14+0A0h], rax
0x14007a0ba  xor     esi, esi
0x14007a0bc  mov     rcx, [rbx+98h]; Lookaside
0x14007a0c3  mov     rdx, rbp; Entry
0x14007a0c6  call    cs:__imp_ExFreeToPagedLookasideList
0x14007a0cd  nop     dword ptr [rax+rax+00h]
0x14007a0d2  lea     rbp, WPP_GLOBAL_Control
0x14007a0d9  jmp     loc_140079EFA
0x14007a0de  mov     esi, 721h
0x14007a0e3  jmp     short loc_14007A0BC
0x14007a0e5  mov     edi, 0C000009Ah
0x14007a0ea  lea     rbp, WPP_GLOBAL_Control
0x14007a0f1  mov     esi, 71Dh
0x14007a0f6  jmp     loc_140079EFA
0x14007a0fb  sub     esi, 1
0x14007a0fe  jnz     short loc_14007A153
0x14007a100  mov     rax, [rsp+0B8h+var_40]
0x14007a105  mov     r9, r12
0x14007a108  mov     [rsp+0B8h+var_78], 0
0x14007a111  mov     r8, rbp
0x14007a114  mov     [rsp+0B8h+var_80], rax
0x14007a119  mov     edx, r15d
0x14007a11c  mov     rax, [rsp+0B8h+var_50]
0x14007a121  mov     rcx, rbx
0x14007a124  mov     [rsp+0B8h+var_88], r14
0x14007a129  mov     [rsp+0B8h+var_90], rax
0x14007a12e  movzx   eax, [rsp+0B8h+arg_20]
0x14007a136  mov     byte ptr [rsp+0B8h+var_98], al
0x14007a13a  call    CscPqpUpdateEntry
0x14007a13f  mov     edi, eax
0x14007a141  test    eax, eax
0x14007a143  jns     loc_14007A0BA
0x14007a149  mov     esi, 735h
0x14007a14e  jmp     loc_14007A0BC
0x14007a153  cmp     esi, 1
0x14007a156  jnz     loc_14007A20F
0x14007a15c  lea     rax, [rsp+0B8h+var_58]
0x14007a161  mov     dword ptr [rsp+0B8h+var_50], 3
0x14007a169  mov     [rsp+0B8h+var_78], rax
0x14007a16e  mov     r9, r12
0x14007a171  lea     rax, [rsp+0B8h+var_50]
0x14007a176  mov     dword ptr [rsp+0B8h+var_50+4], 3
0x14007a17e  mov     [rsp+0B8h+var_80], rax
0x14007a183  mov     r8, rbp
0x14007a186  mov     [rsp+0B8h+var_88], 0
0x14007a18f  mov     edx, r15d
0x14007a192  mov     [rsp+0B8h+var_90], 0
0x14007a19b  mov     rcx, rbx
0x14007a19e  mov     byte ptr [rsp+0B8h+var_98], 0
0x14007a1a3  mov     [rsp+0B8h+var_48], 3
0x14007a1ab  call    CscPqpUpdateEntry
0x14007a1b0  mov     edi, eax
0x14007a1b2  test    eax, eax
0x14007a1b4  js      short loc_14007A21E
0x14007a1b6  xor     edx, edx; Val
0x14007a1b8  mov     r8d, 0D0h; Size
0x14007a1be  mov     rcx, rbp; void *
0x14007a1c1  call    memset
0x14007a1c6  mov     eax, [rbx+34h]
0x14007a1c9  mov     r9, rbp
0x14007a1cc  movzx   r8d, sil
0x14007a1d0  mov     [rbp+0Ch], eax
0x14007a1d3  mov     rdx, r12
0x14007a1d6  mov     [rbp+8], esi
0x14007a1d9  mov     rcx, rbx
0x14007a1dc  call    CscPqpWriteEntry
0x14007a1e1  mov     edi, eax
0x14007a1e3  test    eax, eax
0x14007a1e5  jns     short loc_14007A228
0x14007a1e7  mov     esi, 759h
0x14007a1ec  jmp     loc_14007A0BC
0x14007a1f1  mov     edi, 0C00000E4h
0x14007a1f6  mov     esi, 70Fh
0x14007a1fb  jmp     loc_140079F02
0x14007a200  mov     edi, 0C0000016h
0x14007a205  mov     esi, 72Ah
0x14007a20a  jmp     loc_14007A0BC
0x14007a20f  mov     edi, 0C0000420h
0x14007a214  mov     esi, 764h
0x14007a219  jmp     loc_14007A0BC
0x14007a21e  mov     esi, 748h
0x14007a223  jmp     loc_14007A0BC
0x14007a228  inc     dword ptr [rbx+28h]
0x14007a22b  mov     [rbx+34h], r15d
0x14007a22f  jmp     loc_14007A0BA
0x14007a234  mov     rcx, [rcx+18h]
0x14007a238  lea     r8, WPP_eb62243048b93ac38d7f5193621ee294_Traceguids
0x14007a23f  mov     edx, 29h ; ')'
0x14007a244  mov     [rsp+0B8h+var_98], esi
0x14007a248  mov     r9d, edi
0x14007a24b  call    WPP_SF_Dd
0x14007a250  jmp     loc_140079F53
```
