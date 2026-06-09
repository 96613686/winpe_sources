# NatQueryInformationMapping

- ea: `0x14000f134`
- end: `0x14000f29c`
- name: `NatQueryInformationMapping`
- size: `360`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140001890`
- `0x140005fb0`
- `0x140006374`
- `0x14000e988`
- `0x14000f2a4`
- `0x14000f6cc`
- `0x1400123a8`
- `0x140014f30`
- `0x140017168`
- `0x1400196d4`
- `0x14001a5e0`

## callees

- `0x14000218c`
- `0x14000f134`
- `0x14000fbb0`

## pseudocode

```c
void __fastcall NatQueryInformationMapping(
        __int64 a1,
        _BYTE *a2,
        _DWORD *a3,
        _WORD *a4,
        _DWORD *a5,
        _WORD *a6,
        _DWORD *a7,
        _WORD *a8,
        _OWORD *a9)
{
  int v13; // ecx
  _BOOL8 v14; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x41u,
      (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  v13 = *(_DWORD *)(a1 + 240) & 0x20;
  v14 = v13 != 0;
  if ( a2 )
    *a2 = *(_BYTE *)(a1 + 8 * v14 + 86);
  if ( a3 )
    *a3 = *(_DWORD *)(a1 + 8 * v14 + 80);
  if ( a4 )
    *a4 = *(_WORD *)(a1 + 8 * v14 + 84);
  if ( a7 )
    *a7 = *(_DWORD *)((-(__int64)(v13 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + a1 + 72);
  if ( a8 )
    *a8 = *(_WORD *)((-(__int64)(v13 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + a1 + 76);
  if ( a5 )
    *a5 = *(_DWORD *)((v13 != 0 ? 8 : 0) + a1 + 64);
  if ( a6 )
    *a6 = *(_WORD *)((v13 != 0 ? 8 : 0) + a1 + 68);
  if ( a9 )
  {
    NatUpdateStatisticsMapping(a1);
    *a9 = *(_OWORD *)(a1 + 288);
    a9[1] = *(_OWORD *)(a1 + 304);
    a9[2] = *(_OWORD *)(a1 + 320);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x42u,
      (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
}

```

## disassembly

```asm
0x14000f134  push    rbx
0x14000f136  push    rbp
0x14000f137  push    rsi
0x14000f138  push    rdi
0x14000f139  push    r14
0x14000f13b  sub     rsp, 20h
0x14000f13f  mov     r14, r9
0x14000f142  mov     rdi, r8
0x14000f145  mov     rsi, rdx
0x14000f148  mov     rbx, rcx
0x14000f14b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f152  lea     rbp, WPP_GLOBAL_Control
0x14000f159  cmp     rcx, rbp
0x14000f15c  jz      short loc_14000F180
0x14000f15e  mov     eax, [rcx+2Ch]
0x14000f161  test    al, 1
0x14000f163  jz      short loc_14000F180
0x14000f165  cmp     byte ptr [rcx+29h], 6
0x14000f169  jb      short loc_14000F180
0x14000f16b  mov     rcx, [rcx+18h]
0x14000f16f  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000f176  mov     edx, 41h ; 'A'
0x14000f17b  call    WPP_SF_
0x14000f180  mov     ecx, [rbx+0F0h]
0x14000f186  xor     edx, edx
0x14000f188  and     ecx, 20h
0x14000f18b  test    rsi, rsi
0x14000f18e  jz      short loc_14000F19D
0x14000f190  test    ecx, ecx
0x14000f192  setnz   dl
0x14000f195  mov     al, [rbx+rdx*8+56h]
0x14000f199  mov     [rsi], al
0x14000f19b  jmp     short loc_14000F1A2
0x14000f19d  test    ecx, ecx
0x14000f19f  setnz   dl
0x14000f1a2  test    rdi, rdi
0x14000f1a5  jz      short loc_14000F1AD
0x14000f1a7  mov     eax, [rbx+rdx*8+50h]
0x14000f1ab  mov     [rdi], eax
0x14000f1ad  test    r14, r14
0x14000f1b0  jz      short loc_14000F1BB
0x14000f1b2  movzx   eax, word ptr [rbx+rdx*8+54h]
0x14000f1b7  mov     [r14], ax
0x14000f1bb  mov     rdx, [rsp+48h+arg_30]
0x14000f1c3  test    rdx, rdx
0x14000f1c6  jz      short loc_14000F1D9
0x14000f1c8  mov     eax, ecx
0x14000f1ca  neg     eax
0x14000f1cc  sbb     rax, rax
0x14000f1cf  and     rax, 0FFFFFFFFFFFFFFF8h
0x14000f1d3  mov     eax, [rax+rbx+48h]
0x14000f1d7  mov     [rdx], eax
0x14000f1d9  mov     rdx, [rsp+48h+arg_38]
0x14000f1e1  test    rdx, rdx
0x14000f1e4  jz      short loc_14000F1F9
0x14000f1e6  mov     eax, ecx
0x14000f1e8  neg     eax
0x14000f1ea  sbb     rax, rax
0x14000f1ed  and     rax, 0FFFFFFFFFFFFFFF8h
0x14000f1f1  movzx   eax, word ptr [rax+rbx+4Ch]
0x14000f1f6  mov     [rdx], ax
0x14000f1f9  mov     rdx, [rsp+48h+arg_20]
0x14000f1fe  test    rdx, rdx
0x14000f201  jz      short loc_14000F213
0x14000f203  mov     eax, ecx
0x14000f205  neg     eax
0x14000f207  sbb     rax, rax
0x14000f20a  and     eax, 8
0x14000f20d  mov     eax, [rax+rbx+40h]
0x14000f211  mov     [rdx], eax
0x14000f213  mov     rdx, [rsp+48h+arg_28]
0x14000f218  test    rdx, rdx
0x14000f21b  jz      short loc_14000F22D
0x14000f21d  neg     ecx
0x14000f21f  sbb     rax, rax
0x14000f222  and     eax, 8
0x14000f225  movzx   eax, word ptr [rax+rbx+44h]
0x14000f22a  mov     [rdx], ax
0x14000f22d  mov     rdi, [rsp+48h+arg_40]
0x14000f235  test    rdi, rdi
0x14000f238  jz      short loc_14000F262
0x14000f23a  mov     rcx, rbx
0x14000f23d  call    NatUpdateStatisticsMapping
0x14000f242  movups  xmm0, xmmword ptr [rbx+120h]
0x14000f249  movups  xmmword ptr [rdi], xmm0
0x14000f24c  movups  xmm1, xmmword ptr [rbx+130h]
0x14000f253  movups  xmmword ptr [rdi+10h], xmm1
0x14000f257  movups  xmm0, xmmword ptr [rbx+140h]
0x14000f25e  movups  xmmword ptr [rdi+20h], xmm0
0x14000f262  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f269  cmp     rcx, rbp
0x14000f26c  jz      short loc_14000F290
0x14000f26e  mov     eax, [rcx+2Ch]
0x14000f271  test    al, 1
0x14000f273  jz      short loc_14000F290
0x14000f275  cmp     byte ptr [rcx+29h], 6
0x14000f279  jb      short loc_14000F290
0x14000f27b  mov     rcx, [rcx+18h]
0x14000f27f  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000f286  mov     edx, 42h ; 'B'
0x14000f28b  call    WPP_SF_
0x14000f290  add     rsp, 20h
0x14000f294  pop     r14
0x14000f296  pop     rdi
0x14000f297  pop     rsi
0x14000f298  pop     rbp
0x14000f299  pop     rbx
0x14000f29a  retn
```
