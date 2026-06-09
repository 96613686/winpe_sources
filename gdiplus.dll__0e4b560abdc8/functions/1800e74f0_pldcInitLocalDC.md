# pldcInitLocalDC

- ea: `0x1800e74f0`
- end: `0x1800e7614`
- name: `pldcInitLocalDC`
- size: `292`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800ddd98`

## callees

- `0x1800e74f0`
- `0x18013dff4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e7513`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800e7513`
- `GDI32!SetGraphicsMode` at `0x1800e75ec`
- `GDI32!SetGraphicsMode` at `0x1800e75ec`
- `GDI32!CreateICA` at `0x1800e7560`
- `GDI32!CreateICA` at `0x1800e7560`

## pseudocode

```c
_DWORD *__fastcall pldcInitLocalDC(__int64 a1, int a2, __int16 a3)
{
  __int64 v4; // rdi
  _DWORD *result; // rax
  __int64 v7; // rbx
  __int64 v8; // rax
  HDC ICA; // rax

  v4 = 0;
  result = LocalAlloc(0x40u, 0x240u);
  v7 = (__int64)result;
  if ( result )
  {
    *result = 576;
    if ( (a3 & 1) != 0 )
      result[1] |= 2u;
    if ( (a3 & 0x1000) != 0 )
      result[1] |= 0x10u;
    v8 = pfnSetVirtualResolution;
    if ( pfnSetVirtualResolution )
    {
      ICA = CreateICA("DISPLAY", 0, 0, 0);
      *(_QWORD *)(v7 + 40) = ICA;
      if ( !ICA )
      {
        vFreeLocalDC(v7);
        return (_DWORD *)v4;
      }
      v8 = pfnSetVirtualResolution;
    }
    *(_DWORD *)(v7 + 500) = -1;
    *(_DWORD *)(v7 + 448) = -1;
    *(_DWORD *)(v7 + 64) = a2;
    *(_QWORD *)(v7 + 48) = 0;
    *(_DWORD *)(v7 + 432) = 1;
    *(_DWORD *)(v7 + 360) = 0x7FFFFFFF;
    *(_DWORD *)(v7 + 364) = 0x7FFFFFFF;
    *(_DWORD *)(v7 + 436) = -2147483641;
    *(_DWORD *)(v7 + 440) = 0x80000000;
    *(_DWORD *)(v7 + 444) = -2147483633;
    *(_DWORD *)(v7 + 428) = 0xFFFFFF;
    if ( v8 )
      SetGraphicsMode(*(HDC *)(v7 + 40), 2);
    return (_DWORD *)v7;
  }
  return result;
}

```

## disassembly

```asm
0x1800e74f0  mov     [rsp+arg_0], rbx
0x1800e74f5  mov     [rsp+arg_8], rbp
0x1800e74fa  mov     [rsp+arg_10], rsi
0x1800e74ff  push    rdi
0x1800e7500  sub     rsp, 20h
0x1800e7504  mov     ebp, edx
0x1800e7506  xor     edi, edi
0x1800e7508  mov     edx, 240h; uBytes
0x1800e750d  mov     esi, r8d
0x1800e7510  lea     ecx, [rdi+40h]; uFlags
0x1800e7513  call    cs:__imp_LocalAlloc
0x1800e751a  nop     dword ptr [rax+rax+00h]
0x1800e751f  mov     rbx, rax
0x1800e7522  test    rax, rax
0x1800e7525  jz      loc_1800E75FE
0x1800e752b  mov     dword ptr [rax], 240h
0x1800e7531  test    sil, 1
0x1800e7535  jz      short loc_1800E753B
0x1800e7537  or      dword ptr [rax+4], 2
0x1800e753b  bt      esi, 0Ch
0x1800e753f  jnb     short loc_1800E7545
0x1800e7541  or      dword ptr [rax+4], 10h
0x1800e7545  mov     rax, cs:pfnSetVirtualResolution
0x1800e754c  test    rax, rax
0x1800e754f  jz      short loc_1800E7586
0x1800e7551  xor     r9d, r9d; pdm
0x1800e7554  lea     rcx, aDisplay_0; "DISPLAY"
0x1800e755b  xor     r8d, r8d; pszPort
0x1800e755e  xor     edx, edx; pszDevice
0x1800e7560  call    cs:__imp_CreateICA
0x1800e7567  nop     dword ptr [rax+rax+00h]
0x1800e756c  mov     [rbx+28h], rax
0x1800e7570  test    rax, rax
0x1800e7573  jnz     short loc_1800E757F
0x1800e7575  mov     rcx, rbx
0x1800e7578  call    vFreeLocalDC
0x1800e757d  jmp     short loc_1800E75FB
0x1800e757f  mov     rax, cs:pfnSetVirtualResolution
0x1800e7586  or      dword ptr [rbx+1F4h], 0FFFFFFFFh
0x1800e758d  mov     ecx, 7FFFFFFFh
0x1800e7592  or      dword ptr [rbx+1C0h], 0FFFFFFFFh
0x1800e7599  mov     [rbx+40h], ebp
0x1800e759c  mov     [rbx+30h], rdi
0x1800e75a0  mov     dword ptr [rbx+1B0h], 1
0x1800e75aa  mov     [rbx+168h], ecx
0x1800e75b0  mov     [rbx+16Ch], ecx
0x1800e75b6  mov     dword ptr [rbx+1B4h], 80000007h
0x1800e75c0  mov     dword ptr [rbx+1B8h], 80000000h
0x1800e75ca  mov     dword ptr [rbx+1BCh], 8000000Fh
0x1800e75d4  mov     dword ptr [rbx+1ACh], 0FFFFFFh
0x1800e75de  test    rax, rax
0x1800e75e1  jz      short loc_1800E75F8
0x1800e75e3  mov     rcx, [rbx+28h]; hdc
0x1800e75e7  mov     edx, 2; iMode
0x1800e75ec  call    cs:__imp_SetGraphicsMode
0x1800e75f3  nop     dword ptr [rax+rax+00h]
0x1800e75f8  mov     rdi, rbx
0x1800e75fb  mov     rax, rdi
0x1800e75fe  mov     rbx, [rsp+28h+arg_0]
0x1800e7603  mov     rbp, [rsp+28h+arg_8]
0x1800e7608  mov     rsi, [rsp+28h+arg_10]
0x1800e760d  add     rsp, 20h
0x1800e7611  pop     rdi
0x1800e7612  retn
```
