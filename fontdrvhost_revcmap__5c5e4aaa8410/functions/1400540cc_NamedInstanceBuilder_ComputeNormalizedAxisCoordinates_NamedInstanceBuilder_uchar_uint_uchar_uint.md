# NamedInstanceBuilder::ComputeNormalizedAxisCoordinates(NamedInstanceBuilder &,uchar *,uint,uchar *,uint)

- ea: `0x1400540cc`
- end: `0x140054343`
- name: `?ComputeNormalizedAxisCoordinates@NamedInstanceBuilder@@CA_NAEAV1@PEAEI1I@Z`
- size: `631`
- prototype: `bool __fastcall(struct NamedInstanceBuilder *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140005a00`

## callees

- `0x140044868`
- `0x1400540cc`
- `0x14005434c`
- `0x140054c2c`
- `0x14009273c`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140054288`
- `KERNEL32!GlobalFree` at `0x140054288`
- `KERNEL32!GlobalAlloc` at `0x140054169`
- `KERNEL32!GlobalAlloc` at `0x140054169`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall NamedInstanceBuilder::ComputeNormalizedAxisCoordinates(
        struct NamedInstanceBuilder *a1,
        unsigned __int8 *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  unsigned __int8 *v5; // r13
  struct NamedInstanceBuilder *v6; // r14
  unsigned __int8 *v7; // r15
  unsigned __int8 *v8; // r12
  unsigned int v9; // eax
  unsigned int v10; // esi
  unsigned int i; // ebx
  SIZE_T v12; // rax
  _DWORD *v13; // rdi
  unsigned int v14; // r10d
  __int64 v15; // r9
  struct NamedInstanceBuilder *v16; // r14
  __int64 v17; // rdx
  __int64 j; // r9
  _DWORD *v20; // [rsp+20h] [rbp-C8h] BYREF
  unsigned __int8 *v21; // [rsp+28h] [rbp-C0h]
  __int64 v22[2]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-A8h]
  struct NamedInstanceBuilder *v24; // [rsp+48h] [rbp-A0h]
  struct NamedInstanceBuilder *v25; // [rsp+58h] [rbp-90h]
  unsigned __int8 *v26; // [rsp+60h] [rbp-88h]
  unsigned __int8 *v27; // [rsp+68h] [rbp-80h]
  unsigned __int8 *v28; // [rsp+70h] [rbp-78h]
  __int64 v29[2]; // [rsp+80h] [rbp-68h] BYREF
  unsigned __int8 *v30[2]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v31[9]; // [rsp+A0h] [rbp-48h] BYREF
  struct NamedInstanceBuilder *v32; // [rsp+F0h] [rbp+8h]
  unsigned int v33; // [rsp+F8h] [rbp+10h]
  unsigned int v34; // [rsp+100h] [rbp+18h]
  unsigned __int8 *v35; // [rsp+108h] [rbp+20h]

  v35 = a4;
  v32 = a1;
  v5 = a2;
  v6 = a1;
  v25 = a1;
  v24 = a1;
  v26 = a2;
  v7 = &a2[a3];
  v21 = v7;
  v27 = a4;
  v8 = &a4[a5];
  v28 = v8;
  std::vector<Fixed16_16>::vector<Fixed16_16>(v22);
  v9 = *((_DWORD *)v6 + 11);
  v34 = v9;
  v10 = *((_DWORD *)v6 + 10);
  v33 = v10;
  for ( i = 0; i < v9; ++i )
  {
    v12 = 8LL * v10;
    if ( !is_mul_ok(v10, 8u) )
      v12 = -1;
    v13 = GlobalAlloc(0, v12);
    v20 = v13;
    if ( !v13 )
    {
      EngPtr<EngVariationAxisKeyCoordinate>::~EngPtr<EngVariationAxisKeyCoordinate>(&v20);
      if ( v22[0] )
        std::_Deallocate<16>(v22[0], (v23 - v22[0]) & 0xFFFFFFFFFFFFFFFCuLL);
      return 0;
    }
    v14 = 0;
    if ( v10 )
    {
      v15 = 0;
      v16 = v24;
      do
      {
        v13[2 * v15] = *(_DWORD *)(*((_QWORD *)v16 + 3) + 20 * v15);
        v17 = *((_DWORD *)v16 + 12) * i + 4 * v15;
        v13[2 * v15 + 1] = *(unsigned __int8 *)(v17 + *((_QWORD *)v16 + 4) + 7)
                         | ((*(unsigned __int8 *)(v17 + *((_QWORD *)v16 + 4) + 6)
                           | (((*(unsigned __int8 *)(v17 + *((_QWORD *)v16 + 4) + 4) << 8)
                             | *(unsigned __int8 *)(v17 + *((_QWORD *)v16 + 4) + 5)) << 8)) << 8);
        ++v14;
        ++v15;
      }
      while ( v14 < v10 );
      v6 = v32;
      v7 = v21;
    }
    try
    {
      v29[0] = (__int64)v13;
      v29[1] = (__int64)&v13[2 * v10];
      v30[0] = v35;
      v30[1] = v8;
      v31[0] = (__int64)v5;
      v31[1] = (__int64)v7;
      ComputeNormalizedAxisCoordinates(v31, v30, v29, v22);
      for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v6 + 26) + 16LL * i) + 4 * j) = *(_DWORD *)(v22[0] + 4 * j);
    }
    catch ( ... )
    {
      v10 = v33;
      v13 = v20;
      v6 = v25;
      v32 = v25;
      v5 = v26;
      v7 = v21;
      v35 = v27;
      v8 = v28;
    }
    if ( v13 )
      GlobalFree(v13);
    v9 = v34;
  }
  if ( v22[0] )
    std::_Deallocate<16>(v22[0], (v23 - v22[0]) & 0xFFFFFFFFFFFFFFFCuLL);
  return 1;
}

```

## disassembly

```asm
0x1400540cc  mov     [rsp+arg_18], r9
0x1400540d1  mov     [rsp+arg_0], rcx
0x1400540d6  push    rbx
0x1400540d7  push    rsi
0x1400540d8  push    rdi
0x1400540d9  push    r12
0x1400540db  push    r13
0x1400540dd  push    r14
0x1400540df  push    r15
0x1400540e1  sub     rsp, 0B0h
0x1400540e8  mov     r13, rdx
0x1400540eb  mov     r14, rcx
0x1400540ee  mov     [rsp+0E8h+var_90], rcx
0x1400540f3  mov     [rsp+0E8h+var_A0], rcx
0x1400540f8  mov     [rsp+0E8h+var_88], rdx
0x1400540fd  mov     r15d, r8d
0x140054100  add     r15, rdx
0x140054103  mov     [rsp+0E8h+var_C0], r15
0x140054108  mov     [rsp+0E8h+var_80], r9
0x14005410d  mov     r12d, [rsp+0E8h+arg_20]
0x140054115  add     r12, r9
0x140054118  mov     [rsp+0E8h+var_78], r12
0x14005411d  lea     rcx, [rsp+0E8h+var_B8]
0x140054122  call    ??0?$vector@VFixed16_16@@V?$allocator@VFixed16_16@@@std@@@std@@QEAA@XZ; std::vector<Fixed16_16>::vector<Fixed16_16>(void)
0x140054127  nop
0x140054128  mov     eax, [r14+2Ch]
0x14005412c  mov     [rsp+0E8h+arg_10], eax
0x140054133  mov     esi, [r14+28h]
0x140054137  mov     [rsp+0E8h+arg_8], esi
0x14005413e  xor     ebx, ebx
0x140054140  mov     [rsp+0E8h+arg_20], ebx
0x140054147  cmp     ebx, eax
0x140054149  jnb     loc_14005429D
0x14005414f  mov     ecx, esi
0x140054151  mov     eax, 8
0x140054156  mul     rcx
0x140054159  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140054160  cmovb   rax, rcx
0x140054164  mov     rdx, rax; dwBytes
0x140054167  xor     ecx, ecx; uFlags
0x140054169  call    cs:__imp_GlobalAlloc
0x14005416f  mov     rdi, rax
0x140054172  mov     [rsp+0E8h+var_C8], rax
0x140054177  test    rax, rax
0x14005417a  jz      loc_1400542C0
0x140054180  xor     r10d, r10d
0x140054183  test    esi, esi
0x140054185  jz      short loc_1400541F3
0x140054187  xor     r9d, r9d
0x14005418a  mov     r14, [rsp+0E8h+var_A0]
0x14005418f  lea     rcx, [r9+r9*4]
0x140054193  mov     rax, [r14+18h]
0x140054197  mov     ecx, [rax+rcx*4]
0x14005419a  mov     [rdi+r9*8], ecx
0x14005419e  mov     eax, ebx
0x1400541a0  imul    eax, [r14+30h]
0x1400541a5  lea     rdx, [rax+r9*4]
0x1400541a9  mov     rcx, [r14+20h]
0x1400541ad  movzx   r8d, byte ptr [rdx+rcx+5]
0x1400541b3  movzx   eax, byte ptr [rdx+rcx+4]
0x1400541b8  shl     eax, 8
0x1400541bb  or      r8d, eax
0x1400541be  shl     r8d, 8
0x1400541c2  movzx   eax, byte ptr [rdx+rcx+6]
0x1400541c7  or      r8d, eax
0x1400541ca  shl     r8d, 8
0x1400541ce  movzx   eax, byte ptr [rdx+rcx+7]
0x1400541d3  or      r8d, eax
0x1400541d6  mov     [rdi+r9*8+4], r8d
0x1400541db  inc     r10d
0x1400541de  inc     r9
0x1400541e1  cmp     r10d, esi
0x1400541e4  jb      short loc_14005418F
0x1400541e6  mov     r14, [rsp+0E8h+arg_0]
0x1400541ee  mov     r15, [rsp+0E8h+var_C0]
0x1400541f3  mov     eax, esi
0x1400541f5  lea     rcx, [rdi+rax*8]
0x1400541f9  mov     [rsp+0E8h+var_68], rdi
0x140054201  mov     [rsp+0E8h+var_60], rcx
0x140054209  mov     rax, [rsp+0E8h+arg_18]
0x140054211  mov     [rsp+0E8h+var_58], rax
0x140054219  mov     [rsp+0E8h+var_50], r12
0x140054221  mov     [rsp+0E8h+var_48], r13
0x140054229  mov     [rsp+0E8h+var_40], r15
0x140054231  lea     r9, [rsp+0E8h+var_B8]
0x140054236  lea     r8, [rsp+0E8h+var_68]
0x14005423e  lea     rdx, [rsp+0E8h+var_58]
0x140054246  lea     rcx, [rsp+0E8h+var_48]
0x14005424e  call    ?ComputeNormalizedAxisCoordinates@@YAXV?$array_ref@$$CBE@@0V?$array_ref@$$CBUDWRITE_FONT_AXIS_VALUE_FIXED@@@@AEAV?$vector@VFixed16_16@@V?$allocator@VFixed16_16@@@std@@@std@@@Z; ComputeNormalizedAxisCoordinates(array_ref<uchar const>,array_ref<uchar const>,array_ref<DWRITE_FONT_AXIS_VALUE_FIXED const>,std::vector<Fixed16_16> &)
0x140054253  xor     r9d, r9d
0x140054256  test    esi, esi
0x140054258  jz      short loc_140054280
0x14005425a  mov     r10d, ebx
0x14005425d  add     r10, r10
0x140054260  mov     rax, [r14+0D0h]
0x140054267  mov     rdx, [rax+r10*8]
0x14005426b  mov     rax, [rsp+0E8h+var_B8]
0x140054270  mov     ecx, [rax+r9*4]
0x140054274  mov     [rdx+r9*4], ecx
0x140054278  inc     r9d
0x14005427b  cmp     r9d, esi
0x14005427e  jb      short loc_140054260
0x140054280  test    rdi, rdi
0x140054283  jz      short loc_14005428F
0x140054285  mov     rcx, rdi; hMem
0x140054288  call    cs:__imp_GlobalFree
0x14005428e  nop
0x14005428f  inc     ebx
0x140054291  mov     eax, [rsp+0E8h+arg_10]
0x140054298  jmp     loc_140054140
0x14005429d  mov     rcx, [rsp+0E8h+var_B8]
0x1400542a2  test    rcx, rcx
0x1400542a5  jnz     loc_14005432D
0x1400542ab  mov     al, 1
0x1400542ad  add     rsp, 0B0h
0x1400542b4  pop     r15
0x1400542b6  pop     r14
0x1400542b8  pop     r13
0x1400542ba  pop     r12
0x1400542bc  pop     rdi
0x1400542bd  pop     rsi
0x1400542be  pop     rbx
0x1400542bf  retn
0x1400542c0  lea     rcx, [rsp+0E8h+var_C8]
0x1400542c5  call    ??1?$EngPtr@VEngVariationAxisKeyCoordinate@@@@QEAA@XZ; EngPtr<EngVariationAxisKeyCoordinate>::~EngPtr<EngVariationAxisKeyCoordinate>(void)
0x1400542ca  nop
0x1400542cb  mov     rcx, [rsp+0E8h+var_B8]
0x1400542d0  test    rcx, rcx
0x1400542d3  jnz     short loc_1400542D9
0x1400542d5  xor     al, al
0x1400542d7  jmp     short loc_1400542AD
0x1400542d9  mov     rdx, [rsp+0E8h+var_A8]
0x1400542de  sub     rdx, rcx
0x1400542e1  and     rdx, 0FFFFFFFFFFFFFFFCh
0x1400542e5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400542ea  jmp     short loc_1400542D5
0x1400542ec  mov     esi, [rsp+0E8h+arg_8]
0x1400542f3  mov     ebx, [rsp+0E8h+arg_20]
0x1400542fa  mov     rdi, [rsp+0E8h+var_C8]
0x1400542ff  mov     r14, [rsp+0E8h+var_90]
0x140054304  mov     [rsp+0E8h+arg_0], r14
0x14005430c  mov     r13, [rsp+0E8h+var_88]
0x140054311  mov     r15, [rsp+0E8h+var_C0]
0x140054316  mov     rax, [rsp+0E8h+var_80]
0x14005431b  mov     [rsp+0E8h+arg_18], rax
0x140054323  mov     r12, [rsp+0E8h+var_78]
0x140054328  jmp     loc_140054280
0x14005432d  mov     rdx, [rsp+0E8h+var_A8]
0x140054332  sub     rdx, rcx
0x140054335  and     rdx, 0FFFFFFFFFFFFFFFCh
0x140054339  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14005433e  jmp     loc_1400542AB
```
