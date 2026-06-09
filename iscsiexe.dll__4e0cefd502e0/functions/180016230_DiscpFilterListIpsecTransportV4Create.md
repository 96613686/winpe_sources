# DiscpFilterListIpsecTransportV4Create

- ea: `0x180016230`
- end: `0x1800163f8`
- name: `DiscpFilterListIpsecTransportV4Create`
- size: `456`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, int, int, __int16, __int64, _OWORD *, _OWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015384`

## callees

- `0x1800161c8`
- `0x180016230`
- `0x1800165c4`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800163b3`
- `ISCSIUM!DiscpAllocMemory` at `0x1800163b3`

## pseudocode

```c
__int64 __fastcall DiscpFilterListIpsecTransportV4Create(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        __int16 a7,
        __int64 a8,
        _OWORD *a9,
        _OWORD *a10,
        _QWORD *a11,
        _DWORD *a12)
{
  unsigned int v13; // ebx
  __int64 v14; // rax
  __int64 v15; // rax
  _OWORD *v16; // rax
  __int128 v17; // xmm1
  int v19; // [rsp+50h] [rbp-31h] BYREF
  __int128 v20; // [rsp+58h] [rbp-29h]
  __int128 v21; // [rsp+68h] [rbp-19h]
  _QWORD v22[7]; // [rsp+78h] [rbp-9h] BYREF

  *a11 = 0;
  v19 = 0;
  v22[0] = 0;
  v20 = 0;
  *a12 = 0;
  v21 = 0;
  v13 = DiscpFilterV4Create(68, a4, -1, 0, 0, 0, 0, 0);
  if ( v13 )
    goto LABEL_11;
  if ( a9 )
  {
    v14 = v20;
    *(_OWORD *)(v20 + 152) = *a9;
    *(_DWORD *)(v14 + 32) |= 4u;
  }
  v19 = 1;
  v13 = DiscpFilterV4Create(72, a4, -1, 0, 0, a7, 0, 6);
  if ( v13 )
    goto LABEL_11;
  if ( a10 )
  {
    v15 = *((_QWORD *)&v20 + 1);
    *(_OWORD *)(*((_QWORD *)&v20 + 1) + 152LL) = *a10;
    *(_DWORD *)(v15 + 32) |= 4u;
  }
  v19 = 2;
  v13 = DiscpFilterV4Create(34, 0, 0, a4, -1, 0, a7, 6);
  if ( v13 || (v19 = 3, (v13 = DiscpFilterV4Create(33, a4, -1, 0, 0, a7, 0, 6)) != 0) )
  {
LABEL_11:
    DiscpFilterListDestroy(v22, &v19);
  }
  else
  {
    v16 = (_OWORD *)DiscpAllocMemory(32);
    if ( v16 )
    {
      v17 = v21;
      *v16 = v20;
      v16[1] = v17;
      *a11 = v16;
      *a12 = 4;
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180016230  push    rbp
0x180016232  push    rbx
0x180016233  push    rsi
0x180016234  push    rdi
0x180016235  push    r14
0x180016237  push    r15
0x180016239  lea     rbp, [rsp-7]
0x18001623e  sub     rsp, 88h
0x180016245  mov     r14, [rbp+2Fh+arg_50]
0x18001624c  lea     rdx, [rbp+2Fh+var_58]
0x180016250  mov     r15, [rbp+2Fh+arg_58]
0x180016257  xor     eax, eax
0x180016259  mov     [rsp+0B0h+var_68], rdx
0x18001625e  xor     ecx, ecx
0x180016260  mov     [rsp+0B0h+var_78], al
0x180016264  mov     esi, r9d
0x180016267  mov     [rsp+0B0h+var_80], ax
0x18001626c  xorps   xmm0, xmm0
0x18001626f  mov     [rsp+0B0h+var_88], cx
0x180016274  xor     r9d, r9d
0x180016277  mov     qword ptr [r14], 0
0x18001627e  lea     ecx, [rax+44h]
0x180016281  or      r8d, 0FFFFFFFFh
0x180016285  mov     [rbp+2Fh+var_60], 0
0x18001628c  mov     edx, esi
0x18001628e  mov     [rbp+2Fh+var_38], 0
0x180016296  movups  [rbp+2Fh+var_58], xmm0
0x18001629a  mov     dword ptr [r15], 0
0x1800162a1  movups  [rbp+2Fh+var_48], xmm0
0x1800162a5  mov     [rsp+0B0h+var_90], eax
0x1800162a9  call    DiscpFilterV4Create
0x1800162ae  mov     ebx, eax
0x1800162b0  test    eax, eax
0x1800162b2  jnz     loc_1800163D9
0x1800162b8  mov     rcx, [rbp+2Fh+arg_40]
0x1800162bc  test    rcx, rcx
0x1800162bf  jz      short loc_1800162D4
0x1800162c1  mov     rax, qword ptr [rbp+2Fh+var_58]
0x1800162c5  movups  xmm0, xmmword ptr [rcx]
0x1800162c8  movdqu  xmmword ptr [rax+98h], xmm0
0x1800162d0  or      dword ptr [rax+20h], 4
0x1800162d4  movzx   edi, [rbp+2Fh+arg_30]
0x1800162d8  lea     rcx, [rbp+2Fh+var_58+8]
0x1800162dc  mov     [rsp+0B0h+var_68], rcx
0x1800162e1  xor     eax, eax
0x1800162e3  mov     [rsp+0B0h+var_78], 6
0x1800162e8  xor     r9d, r9d
0x1800162eb  mov     [rsp+0B0h+var_80], ax
0x1800162f0  or      r8d, 0FFFFFFFFh
0x1800162f4  mov     [rsp+0B0h+var_88], di
0x1800162f9  mov     edx, esi
0x1800162fb  lea     ecx, [rax+48h]
0x1800162fe  mov     [rsp+0B0h+var_90], eax
0x180016302  mov     [rbp+2Fh+var_60], 1
0x180016309  call    DiscpFilterV4Create
0x18001630e  mov     ebx, eax
0x180016310  test    eax, eax
0x180016312  jnz     loc_1800163D9
0x180016318  mov     rcx, [rbp+2Fh+arg_48]
0x18001631f  test    rcx, rcx
0x180016322  jz      short loc_180016337
0x180016324  mov     rax, qword ptr [rbp+2Fh+var_58+8]
0x180016328  movups  xmm0, xmmword ptr [rcx]
0x18001632b  movdqu  xmmword ptr [rax+98h], xmm0
0x180016333  or      dword ptr [rax+20h], 4
0x180016337  xor     eax, eax
0x180016339  mov     [rbp+2Fh+var_60], 2
0x180016340  lea     rcx, [rbp+2Fh+var_48]
0x180016344  mov     r9d, esi
0x180016347  mov     [rsp+0B0h+var_68], rcx
0x18001634c  xor     r8d, r8d
0x18001634f  mov     [rsp+0B0h+var_78], 6
0x180016354  xor     edx, edx
0x180016356  mov     [rsp+0B0h+var_80], di
0x18001635b  lea     ecx, [rax+22h]
0x18001635e  mov     [rsp+0B0h+var_88], ax
0x180016363  mov     [rsp+0B0h+var_90], 0FFFFFFFFh
0x18001636b  call    DiscpFilterV4Create
0x180016370  mov     ebx, eax
0x180016372  test    eax, eax
0x180016374  jnz     short loc_1800163D9
0x180016376  lea     rcx, [rbp+2Fh+var_48+8]
0x18001637a  mov     [rbp+2Fh+var_60], 3
0x180016381  mov     [rsp+0B0h+var_68], rcx
0x180016386  xor     r9d, r9d
0x180016389  mov     [rsp+0B0h+var_78], 6
0x18001638e  lea     ecx, [rax+21h]
0x180016391  mov     [rsp+0B0h+var_80], ax
0x180016396  or      r8d, 0FFFFFFFFh
0x18001639a  mov     [rsp+0B0h+var_88], di
0x18001639f  mov     edx, esi
0x1800163a1  mov     [rsp+0B0h+var_90], eax
0x1800163a5  call    DiscpFilterV4Create
0x1800163aa  mov     ebx, eax
0x1800163ac  test    eax, eax
0x1800163ae  jnz     short loc_1800163D9
0x1800163b0  lea     ecx, [rax+20h]
0x1800163b3  call    cs:__imp_DiscpAllocMemory
0x1800163b9  test    rax, rax
0x1800163bc  jz      short loc_1800163E6
0x1800163be  movups  xmm0, [rbp+2Fh+var_58]
0x1800163c2  movups  xmm1, [rbp+2Fh+var_48]
0x1800163c6  movups  xmmword ptr [rax], xmm0
0x1800163c9  movups  xmmword ptr [rax+10h], xmm1
0x1800163cd  mov     [r14], rax
0x1800163d0  mov     dword ptr [r15], 4
0x1800163d7  jmp     short loc_1800163E6
0x1800163d9  lea     rdx, [rbp+2Fh+var_60]
0x1800163dd  lea     rcx, [rbp+2Fh+var_38]
0x1800163e1  call    DiscpFilterListDestroy
0x1800163e6  mov     eax, ebx
0x1800163e8  add     rsp, 88h
0x1800163ef  pop     r15
0x1800163f1  pop     r14
0x1800163f3  pop     rdi
0x1800163f4  pop     rsi
0x1800163f5  pop     rbx
0x1800163f6  pop     rbp
0x1800163f7  retn
```
