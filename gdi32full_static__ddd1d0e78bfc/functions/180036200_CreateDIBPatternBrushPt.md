# CreateDIBPatternBrushPt

- ea: `0x180036200`
- end: `0x1800362a7`
- name: `CreateDIBPatternBrushPt`
- size: `167`
- prototype: `HBRUSH __stdcall(const void *lpPackedDIB, UINT iUsage)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800360e0`

## callees

- `0x18002fda0`
- `0x180036200`
- `0x180036734`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180036299`
- `ntdll!RtlFreeHeap` at `0x180036299`
- `win32u!NtGdiCreateDIBBrush` at `0x180036252`
- `win32u!NtGdiCreateDIBBrush` at `0x180036252`

## pseudocode

```c
HBRUSH __stdcall CreateDIBPatternBrushPt(const void *lpPackedDIB, UINT iUsage)
{
  __int64 v4; // rax
  const BITMAPINFOHEADER *v5; // rdx
  DWORD v6; // r8d
  const void *v7; // r9
  void *v8; // rdi
  HDC DIBBrush; // rsi
  unsigned int v11; // [rsp+40h] [rbp+8h] BYREF

  if ( !lpPackedDIB )
    return 0;
  v11 = 0;
  v4 = pbmiConvertInfo(lpPackedDIB, iUsage, &v11, 1);
  v8 = (void *)v4;
  if ( v4 )
  {
    DIBBrush = (HDC)NtGdiCreateDIBBrush(v4, iUsage, v11, 0, 0, lpPackedDIB);
    if ( v8 != lpPackedDIB )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  else
  {
    DIBBrush = 0;
  }
  return (HBRUSH)GdiTrackHCreate(DIBBrush, v5, v6, v7);
}

```

## disassembly

```asm
0x180036200  mov     rax, rsp
0x180036203  mov     [rax+10h], rbx
0x180036207  mov     [rax+18h], rsi
0x18003620b  push    rdi
0x18003620c  sub     rsp, 30h
0x180036210  mov     esi, edx
0x180036212  mov     rbx, rcx
0x180036215  test    rcx, rcx
0x180036218  jz      short loc_180036283
0x18003621a  mov     r9d, 1
0x180036220  mov     dword ptr [rax+8], 0
0x180036227  lea     r8, [rax+8]
0x18003622b  call    pbmiConvertInfo
0x180036230  mov     rdi, rax
0x180036233  test    rax, rax
0x180036236  jz      short loc_18003627F
0x180036238  mov     r8d, [rsp+38h+arg_0]
0x18003623d  xor     r9d, r9d
0x180036240  mov     [rsp+38h+var_10], rbx
0x180036245  mov     edx, esi
0x180036247  mov     rcx, rax
0x18003624a  mov     [rsp+38h+var_18], 0
0x180036252  call    cs:__imp_NtGdiCreateDIBBrush
0x180036259  nop     dword ptr [rax+rax+00h]
0x18003625e  mov     rsi, rax
0x180036261  cmp     rdi, rbx
0x180036264  jnz     short loc_180036287
0x180036266  mov     rcx, rsi
0x180036269  call    GdiTrackHCreate
0x18003626e  mov     rbx, [rsp+38h+arg_8]
0x180036273  mov     rsi, [rsp+38h+arg_10]
0x180036278  add     rsp, 30h
0x18003627c  pop     rdi
0x18003627d  retn
0x18003627f  xor     esi, esi
0x180036281  jmp     short loc_180036266
0x180036283  xor     eax, eax
0x180036285  jmp     short loc_18003626E
0x180036287  mov     rcx, gs:60h
0x180036290  mov     r8, rdi; P
0x180036293  xor     edx, edx; Flags
0x180036295  mov     rcx, [rcx+30h]; HeapHandle
0x180036299  call    cs:__imp_RtlFreeHeap
0x1800362a0  nop     dword ptr [rax+rax+00h]
0x1800362a5  jmp     short loc_180036266
```
