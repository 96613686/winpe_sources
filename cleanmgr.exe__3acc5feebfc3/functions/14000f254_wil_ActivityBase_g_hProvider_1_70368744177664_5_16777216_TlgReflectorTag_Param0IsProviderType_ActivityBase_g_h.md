# wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)

- ea: `0x14000f254`
- end: `0x14000f30e`
- name: `??0?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z`
- size: `186`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ee64`
- `0x14000f154`
- `0x14000f1b4`
- `0x140012a7c`
- `0x140013530`
- `0x140014fe0`

## callees

- `0x140003390`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rcx

  *(_QWORD *)a1 = &wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable';
  v3 = a1 + 8;
  *(_DWORD *)(a1 + 8) = 0;
  *(_BYTE *)(a1 + 12) = 0;
  *(_BYTE *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = a2;
  *(_QWORD *)(a1 + 64) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  v4 = (_QWORD *)(a1 + 88);
  v4[19] = 0;
  v4[20] = 0;
  memset_0(v4, 0, 0x98u);
  *(_DWORD *)(v3 + 248) = 1;
  *(_QWORD *)(v3 + 256) = 0;
  *(_QWORD *)(a1 + 272) = v3;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = a1;
  *(_QWORD *)(a1 + 304) = 0;
  *(_DWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = a1 + 48;
  *(_BYTE *)(a1 + 328) = 0;
  return a1;
}

```

## disassembly

```asm
0x14000f254  mov     [rsp+arg_0], rbx
0x14000f259  mov     [rsp+arg_8], rsi
0x14000f25e  push    rdi
0x14000f25f  sub     rsp, 20h
0x14000f263  mov     rdi, rcx
0x14000f266  lea     rax, ??_7?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@6B@; const wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::`vftable'
0x14000f26d  mov     [rcx], rax
0x14000f270  lea     rbx, [rcx+8]
0x14000f274  xor     esi, esi
0x14000f276  mov     [rbx], esi
0x14000f278  mov     [rbx+4], sil
0x14000f27c  mov     [rbx+40h], sil
0x14000f280  mov     [rbx+28h], esi
0x14000f283  mov     [rbx+30h], rdx
0x14000f287  mov     [rbx+38h], rsi
0x14000f28b  mov     [rbx+48h], esi
0x14000f28e  lea     rcx, [rbx+50h]; void *
0x14000f292  mov     [rcx+98h], rsi
0x14000f299  mov     [rcx+0A0h], rsi
0x14000f2a0  xor     edx, edx; Val
0x14000f2a2  mov     r8d, 98h; Size
0x14000f2a8  call    memset_0
0x14000f2ad  mov     dword ptr [rbx+0F8h], 1
0x14000f2b7  xor     eax, eax
0x14000f2b9  mov     [rbx+100h], rax
0x14000f2c0  mov     [rdi+110h], rbx
0x14000f2c7  mov     [rdi+118h], rsi
0x14000f2ce  mov     [rdi+120h], rsi
0x14000f2d5  mov     [rdi+128h], rdi
0x14000f2dc  mov     [rdi+130h], rsi
0x14000f2e3  mov     [rdi+138h], esi
0x14000f2e9  lea     rax, [rdi+30h]
0x14000f2ed  mov     [rdi+140h], rax
0x14000f2f4  mov     [rdi+148h], sil
0x14000f2fb  mov     rax, rdi
0x14000f2fe  mov     rbx, [rsp+28h+arg_0]
0x14000f303  mov     rsi, [rsp+28h+arg_8]
0x14000f308  add     rsp, 20h
0x14000f30c  pop     rdi
0x14000f30d  retn
```
