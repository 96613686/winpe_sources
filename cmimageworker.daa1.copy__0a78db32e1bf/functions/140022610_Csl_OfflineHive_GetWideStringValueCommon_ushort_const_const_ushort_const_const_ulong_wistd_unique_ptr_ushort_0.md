# Csl::OfflineHive::GetWideStringValueCommon(ushort const * const,ushort const * const,ulong,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong &)

- ea: `0x140022610`
- end: `0x14002279b`
- name: `?GetWideStringValueCommon@OfflineHive@Csl@@QEBAJQEBG0KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@AEAK@Z`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400223dc`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002bb0`
- `0x140006fe4`
- `0x14000d7bc`
- `0x140022610`
- `0x140025aa0`

## string_xrefs

- `0x140022677`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022722`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022776`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
int __fastcall Csl::OfflineHive::GetWideStringValueCommon(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        void **a5,
        unsigned int *a6)
{
  unsigned int v9; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int v13; // esi
  unsigned __int64 v14; // rbx
  void *v15; // rax
  void *v16; // rdi
  unsigned int v17; // eax
  const struct std::nothrow_t *v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  void *v20; // rcx
  unsigned int v21; // [rsp+20h] [rbp-38h]
  unsigned int v22; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int v24; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v25; // [rsp+78h] [rbp+20h] BYREF

  v25 = 0;
  v24 = 0;
  v9 = ORGetValue(*(_QWORD *)(a1 + 8), a2, a3, (unsigned int)&v24, 0, (__int64)&v25);
  if ( v9 == 2 )
    return -2147024894;
  if ( v9 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x23D,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
             (const char *)v9,
             v21);
  if ( v24 != 7 )
  {
    v11 = -2147023267;
    v12 = 575;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)v11,
      v21);
    return v11;
  }
  v13 = (v25 >> 1) + 2;
  v14 = 2LL * v13;
  if ( !is_mul_ok(v13, 2u) )
    v14 = -1;
  v15 = operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( !v15 )
  {
    v11 = -2147024882;
    v12 = 587;
    goto LABEL_16;
  }
  memset_0(v15, 0, v14);
  v25 = 2 * v13;
  v17 = ORGetValue(*(_QWORD *)(a1 + 8), a2, a3, (unsigned int)&v24, (__int64)v16, (__int64)&v25);
  if ( v17 )
  {
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x254,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
            (const char *)v17,
            v22);
    operator delete(v16, v19);
    return v11;
  }
  v20 = *a5;
  *a5 = v16;
  if ( v20 )
    operator delete(v20, v18);
  *a6 = v25;
  return 0;
}

```

## disassembly

```asm
0x140022610  mov     r11, rsp
0x140022613  mov     [r11+10h], rbx
0x140022617  mov     [r11+20h], r9d
0x14002261b  push    rbp
0x14002261c  push    rsi
0x14002261d  push    rdi
0x14002261e  push    r14
0x140022620  push    r15
0x140022622  sub     rsp, 30h
0x140022626  mov     rbp, r8
0x140022629  mov     r14, rdx
0x14002262c  mov     r15, rcx
0x14002262f  mov     [rsp+58h+arg_18], 0
0x140022637  mov     [rsp+58h+arg_0], 0
0x14002263f  lea     rax, [r11+20h]
0x140022643  mov     [r11-30h], rax
0x140022647  mov     qword ptr [r11-38h], 0
0x14002264f  lea     r9, [r11+8]
0x140022653  mov     rcx, [rcx+8]
0x140022657  call    ORGetValue
0x14002265c  cmp     eax, 2
0x14002265f  jnz     short loc_14002266B
0x140022661  mov     eax, 80070002h
0x140022666  jmp     loc_140022789
0x14002266b  test    eax, eax
0x14002266d  jz      short loc_14002268D
0x14002266f  mov     rcx, [rsp+58h]; this
0x140022674  mov     r9d, eax; char *
0x140022677  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14002267e  mov     edx, 23Dh; void *
0x140022683  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022688  jmp     loc_140022789
0x14002268d  cmp     [rsp+58h+arg_0], 7
0x140022692  jz      short loc_1400226A3
0x140022694  mov     ebx, 8007065Dh
0x140022699  mov     edx, 23Fh
0x14002269e  jmp     loc_140022773
0x1400226a3  mov     esi, [rsp+58h+arg_18]
0x1400226a7  shr     esi, 1
0x1400226a9  add     esi, 2
0x1400226ac  mov     ecx, esi
0x1400226ae  mov     eax, 2
0x1400226b3  mul     rcx
0x1400226b6  mov     rbx, rax
0x1400226b9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400226c0  cmovb   rbx, rax
0x1400226c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400226cb  mov     rcx, rbx; unsigned __int64
0x1400226ce  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400226d3  mov     rdi, rax
0x1400226d6  test    rax, rax
0x1400226d9  jz      loc_140022769
0x1400226df  mov     r8, rbx; Size
0x1400226e2  xor     edx, edx; Val
0x1400226e4  mov     rcx, rax; void *
0x1400226e7  call    memset_0
0x1400226ec  lea     ecx, [rsi+rsi]
0x1400226ef  mov     [rsp+58h+arg_18], ecx
0x1400226f3  lea     rax, [rsp+58h+arg_18]
0x1400226f8  mov     [rsp+58h+var_30], rax
0x1400226fd  mov     qword ptr [rsp+58h+var_38], rdi; unsigned int
0x140022702  lea     r9, [rsp+58h+arg_0]
0x140022707  mov     r8, rbp
0x14002270a  mov     rdx, r14
0x14002270d  mov     rcx, [r15+8]
0x140022711  call    ORGetValue
0x140022716  test    eax, eax
0x140022718  jz      short loc_14002273F
0x14002271a  mov     rcx, [rsp+58h]; this
0x14002271f  mov     r9d, eax; char *
0x140022722  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022729  mov     edx, 254h; void *
0x14002272e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140022733  mov     ebx, eax
0x140022735  mov     rcx, rdi; void *
0x140022738  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002273d  jmp     short loc_140022787
0x14002273f  mov     rax, [rsp+58h+arg_20]
0x140022747  mov     rcx, [rax]; void *
0x14002274a  mov     [rax], rdi
0x14002274d  test    rcx, rcx
0x140022750  jz      short loc_140022757
0x140022752  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022757  mov     ecx, [rsp+58h+arg_18]
0x14002275b  mov     rax, [rsp+58h+arg_28]
0x140022763  mov     [rax], ecx
0x140022765  xor     eax, eax
0x140022767  jmp     short loc_140022789
0x140022769  mov     ebx, 8007000Eh
0x14002276e  mov     edx, 24Bh; void *
0x140022773  mov     r9d, ebx; char *
0x140022776  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14002277d  mov     rcx, [rsp+58h]; this
0x140022782  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022787  mov     eax, ebx
0x140022789  mov     rbx, [rsp+58h+arg_8]
0x14002278e  add     rsp, 30h
0x140022792  pop     r15
0x140022794  pop     r14
0x140022796  pop     rdi
0x140022797  pop     rsi
0x140022798  pop     rbp
0x140022799  retn
```
