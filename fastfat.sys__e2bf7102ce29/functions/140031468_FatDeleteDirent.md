# FatDeleteDirent

- ea: `0x140031468`
- end: `0x140031723`
- name: `FatDeleteDirent`
- size: `699`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140024bd4`
- `0x1400268c0`
- `0x140028cc0`
- `0x140029774`
- `0x1400333d0`
- `0x140035e50`
- `0x14003a3e0`
- `0x14003bea4`

## callees

- `0x140005288`
- `0x140024228`
- `0x140031468`
- `0x140035608`

## import_xrefs

- `ntoskrnl!RtlClearBits` at `0x14003163d`
- `ntoskrnl!RtlClearBits` at `0x14003163d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400314f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400314f7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140031703`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d1bc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140031703`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005d1bc`
- `ntoskrnl!CcUnpinData` at `0x14003153e`
- `ntoskrnl!CcUnpinData` at `0x1400316ef`
- `ntoskrnl!CcUnpinData` at `0x14005d19d`
- `ntoskrnl!CcUnpinData` at `0x14003153e`
- `ntoskrnl!CcUnpinData` at `0x1400316ef`
- `ntoskrnl!CcUnpinData` at `0x14005d19d`
- `ntoskrnl!KeBugCheckEx` at `0x1400314d4`
- `ntoskrnl!KeBugCheckEx` at `0x1400314d4`

## pseudocode

```c
void __fastcall FatDeleteDirent(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  PVOID v5; // r14
  _BYTE *v6; // rdi
  __int64 *v7; // r12
  _DWORD *v8; // rax
  unsigned int i; // r15d
  _DWORD *v10; // r13
  _BYTE *v11; // rdi
  __int64 v12; // rdx
  unsigned __int16 v13; // r8
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-98h]
  __int64 v16; // [rsp+50h] [rbp-78h] BYREF
  _BYTE *v17; // [rsp+58h] [rbp-70h] BYREF
  PVOID v18; // [rsp+60h] [rbp-68h] BYREF
  _DWORD *v19; // [rsp+68h] [rbp-60h]
  __int64 v20; // [rsp+70h] [rbp-58h]
  __int64 v21; // [rsp+78h] [rbp-50h]
  _DWORD *v22; // [rsp+80h] [rbp-48h]

  v22 = (_DWORD *)a3;
  v5 = 0;
  v18 = 0;
  v6 = 0;
  v17 = 0;
  if ( a4 && (*(_DWORD *)(a2 + 24) || *(_WORD *)a2 == 1282 && *(_DWORD *)(a2 + 32)) )
    KeBugCheckEx(0x23u, 0xA0378u, 0, 0, 0);
  v7 = (__int64 *)(a2 + 176);
  v20 = a2 + 176;
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(a2 + 176) + 8LL), 1u);
  v8 = (_DWORD *)(a2 + 248);
  v19 = (_DWORD *)(a2 + 248);
  for ( i = *(_DWORD *)(a2 + 248); ; i += 32 )
  {
    v10 = (_DWORD *)(a2 + 244);
    v16 = a2 + 244;
    if ( i > *(_DWORD *)(a2 + 244) )
      break;
    if ( i == *v8 || (i & 0xFFF) == 0 )
    {
      if ( v5 )
      {
        CcUnpinData(v5);
        v18 = 0;
      }
      FatPrepareWriteDirectoryFile(a1, *v7, i, 0x20u, &v18, (PVOID *)&v17, v15, 1, &v16);
      v5 = v18;
      v6 = v17;
      v8 = v19;
    }
    *v6 = -27;
    v6 += 32;
    v17 = v6;
  }
  v11 = v6 - 32;
  v17 = v11;
  v21 = a2 + 184;
  v12 = *(_QWORD *)(a2 + 184);
  if ( *(_BYTE *)(v12 + 376) != 32 )
  {
    if ( a4 )
    {
      v13 = *((_WORD *)v11 + 10);
      if ( v13 )
      {
        FatDeleteEa(a1, v12, v13);
        v8 = v19;
      }
    }
  }
  RtlClearBits((PRTL_BITMAP)(*v7 + 400), *v8 >> 5, ((unsigned int)(*v10 - *v8) >> 5) + 1);
  if ( a3 )
  {
    *((_DWORD *)v11 + 7) = *v22;
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 200LL) & 0x400000) != 0 && (*(_DWORD *)(a2 + 192) & 0x8000) != 0 )
    {
      *(_BYTE *)(a2 + 136) = ((v11[28] + 15) & 0xF0) - v11[28];
      v14 = (*((_DWORD *)v11 + 7) + 15) & 0xFFFFFFF0;
      *((_DWORD *)v11 + 7) = v14;
      *((_DWORD *)v11 + 7) = *(_DWORD *)(a2 + 132) + v14;
      v11[12] = v11[12] & 0x1B | (4 * (*(_BYTE *)(a2 + 136) & 1 | (4 * (*(_BYTE *)(a2 + 136) & 0xFE))));
    }
    *((_WORD *)v11 + 13) = *(_WORD *)(a3 + 4);
  }
  if ( *v10 < *(_DWORD *)(*v7 + 380) )
    *(_DWORD *)(*v7 + 380) = *v19;
  if ( v5 )
    CcUnpinData(v5);
  ExReleaseResourceLite(*(PERESOURCE *)(*v7 + 8));
}

```

## disassembly

```asm
0x140031468  mov     rax, rsp
0x14003146b  mov     [rax+20h], r9b
0x14003146f  mov     [rax+18h], r8
0x140031473  mov     [rax+10h], rdx
0x140031477  mov     [rax+8], rcx
0x14003147b  push    rbx
0x14003147c  push    rsi
0x14003147d  push    rdi
0x14003147e  push    r12
0x140031480  push    r13
0x140031482  push    r14
0x140031484  push    r15
0x140031486  sub     rsp, 90h
0x14003148d  mov     rsi, rdx
0x140031490  mov     [rsp+0C8h+var_48], r8
0x140031498  xor     ebx, ebx
0x14003149a  mov     r14d, ebx
0x14003149d  mov     [rax-68h], rbx
0x1400314a1  mov     edi, ebx
0x1400314a3  mov     [rax-70h], rbx
0x1400314a7  test    r9b, r9b
0x1400314aa  jz      short loc_1400314E1
0x1400314ac  cmp     [rdx+18h], ebx
0x1400314af  jnz     short loc_1400314C0
0x1400314b1  mov     eax, 502h
0x1400314b6  cmp     [rdx], ax
0x1400314b9  jnz     short loc_1400314E1
0x1400314bb  cmp     [rdx+20h], ebx
0x1400314be  jz      short loc_1400314E1
0x1400314c0  mov     [rsp+0C8h+BugCheckParameter4], rbx; BugCheckParameter4
0x1400314c5  xor     r9d, r9d; BugCheckParameter3
0x1400314c8  xor     r8d, r8d; BugCheckParameter2
0x1400314cb  mov     edx, 0A0378h; BugCheckParameter1
0x1400314d0  lea     ecx, [r9+23h]; BugCheckCode
0x1400314d4  call    cs:__imp_KeBugCheckEx
0x1400314e1  lea     r12, [rdx+0B0h]
0x1400314e8  mov     [rsp+0C8h+var_58], r12
0x1400314ed  mov     rcx, [r12]
0x1400314f1  mov     dl, 1; Wait
0x1400314f3  mov     rcx, [rcx+8]; Resource
0x1400314f7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400314fe  nop     dword ptr [rax+rax+00h]
0x140031503  lea     rax, [rsi+0F8h]
0x14003150a  mov     [rsp+0C8h+var_60], rax
0x14003150f  mov     r15d, [rax]
0x140031512  lea     r13, [rsi+0F4h]
0x140031519  mov     [rsp+0C8h+var_78], r13
0x14003151e  cmp     r15d, [r13+0]
0x140031522  ja      loc_1400315B0
0x140031528  cmp     r15d, [rax]
0x14003152b  jz      short loc_140031536
0x14003152d  test    r15d, 0FFFh
0x140031534  jnz     short loc_14003159B
0x140031536  test    r14, r14
0x140031539  jz      short loc_14003154F
0x14003153b  mov     rcx, r14; Bcb
0x14003153e  call    cs:__imp_CcUnpinData
0x140031545  nop     dword ptr [rax+rax+00h]
0x14003154a  mov     [rsp+0C8h+var_68], rbx
0x14003154f  lea     rax, [rsp+0C8h+var_78]
0x140031554  mov     [rsp+0C8h+var_88], rax
0x140031559  mov     [rsp+0C8h+var_90], 1
0x14003155e  lea     rax, [rsp+0C8h+var_70]
0x140031563  mov     [rsp+0C8h+var_A0], rax
0x140031568  lea     rax, [rsp+0C8h+var_68]
0x14003156d  mov     [rsp+0C8h+BugCheckParameter4], rax
0x140031572  mov     r9d, 20h ; ' '
0x140031578  mov     r8d, r15d
0x14003157b  mov     rdx, [r12]
0x14003157f  mov     rcx, [rsp+0C8h+arg_0]
0x140031587  call    FatPrepareWriteDirectoryFile
0x14003158c  mov     r14, [rsp+0C8h+var_68]
0x140031591  mov     rdi, [rsp+0C8h+var_70]
0x140031596  mov     rax, [rsp+0C8h+var_60]
0x14003159b  mov     byte ptr [rdi], 0E5h
0x14003159e  add     r15d, 20h ; ' '
0x1400315a2  add     rdi, 20h ; ' '
0x1400315a6  mov     [rsp+0C8h+var_70], rdi
0x1400315ab  jmp     loc_140031512
0x1400315b0  sub     rdi, 20h ; ' '
0x1400315b4  mov     [rsp+0C8h+var_70], rdi
0x1400315b9  lea     r15, [rsi+0B8h]
0x1400315c0  mov     [rsp+0C8h+var_50], r15
0x1400315c5  mov     rdx, [r15]
0x1400315c8  cmp     byte ptr [rdx+178h], 20h ; ' '
0x1400315cf  jz      short loc_14003161F
0x1400315d1  cmp     [rsp+0C8h+arg_18], bl
0x1400315d8  jz      short loc_14003161F
0x1400315da  movzx   r8d, word ptr [rdi+14h]
0x1400315df  test    r8w, r8w
0x1400315e3  jz      short loc_14003161F
0x1400315e5  mov     rcx, [rsp+0C8h+arg_0]
0x1400315ed  call    FatDeleteEa
0x1400315f2  mov     rax, [rsp+0C8h+var_60]
0x1400315f7  jmp     short loc_14003161F
0x1400315f9  mov     rsi, [rsp+0C8h+arg_8]
0x140031601  mov     r14, [rsp+0C8h+var_68]
0x140031606  mov     rdi, [rsp+0C8h+var_70]
0x14003160b  mov     r12, [rsp+0C8h+var_58]
0x140031610  mov     r13, [rsp+0C8h+var_78]
0x140031615  mov     r15, [rsp+0C8h+var_50]
0x14003161a  mov     rax, [rsp+0C8h+var_60]
0x14003161f  mov     edx, [rax]
0x140031621  mov     r8d, [r13+0]
0x140031625  sub     r8d, edx
0x140031628  shr     r8d, 5
0x14003162c  inc     r8d; NumberToClear
0x14003162f  shr     edx, 5; StartingIndex
0x140031632  mov     rcx, [r12]
0x140031636  add     rcx, 190h; BitMapHeader
0x14003163d  call    cs:__imp_RtlClearBits
0x140031644  nop     dword ptr [rax+rax+00h]
0x140031649  mov     rdx, [rsp+0C8h+arg_10]
0x140031651  test    rdx, rdx
0x140031654  jz      short loc_1400316CA
0x140031656  mov     rax, [rsp+0C8h+var_48]
0x14003165e  mov     eax, [rax]
0x140031660  mov     [rdi+1Ch], eax
0x140031663  mov     rax, [r15]
0x140031666  mov     ecx, [rax+0C8h]
0x14003166c  bt      ecx, 16h
0x140031670  jnb     short loc_1400316C2
0x140031672  test    dword ptr [rsi+0C0h], 8000h
0x14003167c  jz      short loc_1400316C2
0x14003167e  mov     cl, [rdi+1Ch]
0x140031681  lea     eax, [rcx+0Fh]
0x140031684  and     al, 0F0h
0x140031686  sub     al, cl
0x140031688  mov     [rsi+88h], al
0x14003168e  mov     ecx, [rdi+1Ch]
0x140031691  add     ecx, 0Fh
0x140031694  and     ecx, 0FFFFFFF0h
0x140031697  mov     [rdi+1Ch], ecx
0x14003169a  add     ecx, [rsi+84h]
0x1400316a0  mov     [rdi+1Ch], ecx
0x1400316a3  mov     al, [rsi+88h]
0x1400316a9  mov     cl, al
0x1400316ab  and     cl, 0FEh
0x1400316ae  shl     cl, 2
0x1400316b1  and     al, 1
0x1400316b3  or      cl, al
0x1400316b5  shl     cl, 2
0x1400316b8  mov     al, [rdi+0Ch]
0x1400316bb  and     al, 1Bh
0x1400316bd  or      cl, al
0x1400316bf  mov     [rdi+0Ch], cl
0x1400316c2  movzx   eax, word ptr [rdx+4]
0x1400316c6  mov     [rdi+1Ah], ax
0x1400316ca  mov     rcx, [r12]
0x1400316ce  mov     eax, [rcx+17Ch]
0x1400316d4  cmp     [r13+0], eax
0x1400316d8  jnb     short loc_1400316E7
0x1400316da  mov     rax, [rsp+0C8h+var_60]
0x1400316df  mov     eax, [rax]
0x1400316e1  mov     [rcx+17Ch], eax
0x1400316e7  test    r14, r14
0x1400316ea  jz      short loc_1400316FB
0x1400316ec  mov     rcx, r14; Bcb
0x1400316ef  call    cs:__imp_CcUnpinData
0x1400316f6  nop     dword ptr [rax+rax+00h]
0x1400316fb  mov     rcx, [r12]
0x1400316ff  mov     rcx, [rcx+8]; Resource
0x140031703  call    cs:__imp_ExReleaseResourceLite
0x14003170a  nop     dword ptr [rax+rax+00h]
0x14003170f  add     rsp, 90h
0x140031716  pop     r15
0x140031718  pop     r14
0x14003171a  pop     r13
0x14003171c  pop     r12
0x14003171e  pop     rdi
0x14003171f  pop     rsi
0x140031720  pop     rbx
0x140031721  retn
0x14005d16b  push    rbp
0x14005d16d  sub     rsp, 50h
0x14005d171  mov     rbp, rdx
0x14005d174  mov     rdx, rcx
0x14005d177  mov     rcx, [rbp+0D0h]
0x14005d17e  call    FatExceptionFilter
0x14005d183  nop
0x14005d184  add     rsp, 50h
0x14005d188  pop     rbp
0x14005d189  retn
0x14005d18b  push    rbp
0x14005d18d  sub     rsp, 50h
0x14005d191  mov     rbp, rdx
0x14005d194  mov     rcx, [rbp+60h]; Bcb
0x14005d198  test    rcx, rcx
0x14005d19b  jz      short loc_14005D1AA
0x14005d19d  call    cs:__imp_CcUnpinData
0x14005d1a4  nop     dword ptr [rax+rax+00h]
0x14005d1a9  nop
0x14005d1aa  mov     rax, [rbp+0D8h]
0x14005d1b1  mov     rcx, [rax+0B0h]
0x14005d1b8  mov     rcx, [rcx+8]; Resource
0x14005d1bc  call    cs:__imp_ExReleaseResourceLite
0x14005d1c3  nop     dword ptr [rax+rax+00h]
0x14005d1c8  nop
0x14005d1c9  add     rsp, 50h
0x14005d1cd  pop     rbp
0x14005d1ce  retn
```
