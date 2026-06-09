# MediaTypeCreateVIHFromVIH2

- ea: `0x180013278`
- end: `0x18001334d`
- name: `MediaTypeCreateVIHFromVIH2`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180013a50`
- `0x180014f78`

## callees

- `0x180013278`
- `0x18001e5c5`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001329f`
- `ole32!CoTaskMemAlloc` at `0x1800132e4`
- `ole32!CoTaskMemAlloc` at `0x18001329f`
- `ole32!CoTaskMemAlloc` at `0x1800132e4`
- `ole32!CoTaskMemFree` at `0x1800132f2`
- `ole32!CoTaskMemFree` at `0x1800132f2`

## pseudocode

```c
__int64 __fastcall MediaTypeCreateVIHFromVIH2(_QWORD *a1, __int128 *a2)
{
  _OWORD *v2; // rbp
  unsigned int v3; // esi
  _OWORD *v6; // rax
  void *v7; // rdi
  char *v9; // rax
  __int128 v10; // xmm0

  v2 = (_OWORD *)*((_QWORD *)a2 + 10);
  v3 = *((_DWORD *)a2 + 18) - 24;
  if ( v3 < 0x30 )
    v3 = 48;
  v6 = CoTaskMemAlloc(v3);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  *v6 = *v2;
  v6[1] = v2[1];
  v6[2] = v2[2];
  memcpy_0(v6 + 3, (char *)v2 + 72, v3 - 48);
  v9 = (char *)CoTaskMemAlloc(0x58u);
  if ( !v9 )
  {
    CoTaskMemFree(v7);
    return 2147942414LL;
  }
  v10 = *a2;
  *a1 = v9;
  *(_OWORD *)v9 = v10;
  *((_OWORD *)v9 + 1) = a2[1];
  *((_OWORD *)v9 + 2) = a2[2];
  *((_OWORD *)v9 + 3) = a2[3];
  *((_OWORD *)v9 + 4) = a2[4];
  *((_QWORD *)v9 + 10) = *((_QWORD *)a2 + 10);
  *(GUID *)(v9 + 44) = FORMAT_VideoInfo;
  *((_QWORD *)v9 + 10) = v7;
  *((_DWORD *)v9 + 18) = v3;
  return 0;
}

```

## disassembly

```asm
0x180013278  push    rbx
0x18001327a  push    rbp
0x18001327b  push    rsi
0x18001327c  push    rdi
0x18001327d  push    r14
0x18001327f  sub     rsp, 20h
0x180013283  mov     esi, [rdx+48h]
0x180013286  mov     eax, 30h ; '0'
0x18001328b  mov     rbp, [rdx+50h]
0x18001328f  add     esi, 0FFFFFFE8h
0x180013292  cmp     esi, eax
0x180013294  mov     r14, rcx
0x180013297  mov     rbx, rdx
0x18001329a  cmovb   esi, eax
0x18001329d  mov     ecx, esi; cb
0x18001329f  call    cs:__imp_CoTaskMemAlloc
0x1800132a5  mov     rdi, rax
0x1800132a8  test    rax, rax
0x1800132ab  jnz     short loc_1800132B7
0x1800132ad  mov     eax, 8007000Eh
0x1800132b2  jmp     loc_180013342
0x1800132b7  movups  xmm0, xmmword ptr [rbp+0]
0x1800132bb  lea     r8d, [rsi-30h]; Size
0x1800132bf  lea     rdx, [rbp+48h]; Src
0x1800132c3  movups  xmmword ptr [rax], xmm0
0x1800132c6  lea     rcx, [rax+30h]; void *
0x1800132ca  movups  xmm1, xmmword ptr [rbp+10h]
0x1800132ce  movups  xmmword ptr [rax+10h], xmm1
0x1800132d2  movups  xmm0, xmmword ptr [rbp+20h]
0x1800132d6  movups  xmmword ptr [rax+20h], xmm0
0x1800132da  call    memcpy_0
0x1800132df  mov     ecx, 58h ; 'X'; cb
0x1800132e4  call    cs:__imp_CoTaskMemAlloc
0x1800132ea  test    rax, rax
0x1800132ed  jnz     short loc_1800132FA
0x1800132ef  mov     rcx, rdi; pv
0x1800132f2  call    cs:__imp_CoTaskMemFree
0x1800132f8  jmp     short loc_1800132AD
0x1800132fa  movups  xmm0, xmmword ptr [rbx]
0x1800132fd  mov     [r14], rax
0x180013300  movups  xmmword ptr [rax], xmm0
0x180013303  movups  xmm1, xmmword ptr [rbx+10h]
0x180013307  movups  xmmword ptr [rax+10h], xmm1
0x18001330b  movups  xmm0, xmmword ptr [rbx+20h]
0x18001330f  movups  xmmword ptr [rax+20h], xmm0
0x180013313  movups  xmm1, xmmword ptr [rbx+30h]
0x180013317  movups  xmmword ptr [rax+30h], xmm1
0x18001331b  movups  xmm0, xmmword ptr [rbx+40h]
0x18001331f  movups  xmmword ptr [rax+40h], xmm0
0x180013323  movsd   xmm1, qword ptr [rbx+50h]
0x180013328  movsd   qword ptr [rax+50h], xmm1
0x18001332d  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180013334  movdqu  xmmword ptr [rax+2Ch], xmm0
0x180013339  mov     [rax+50h], rdi
0x18001333d  mov     [rax+48h], esi
0x180013340  xor     eax, eax
0x180013342  add     rsp, 20h
0x180013346  pop     r14
0x180013348  pop     rdi
0x180013349  pop     rsi
0x18001334a  pop     rbp
0x18001334b  pop     rbx
0x18001334c  retn
```
