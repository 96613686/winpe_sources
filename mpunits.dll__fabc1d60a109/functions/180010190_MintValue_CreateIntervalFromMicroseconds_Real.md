# MintValue_CreateIntervalFromMicroseconds_Real

- ea: `0x180010190`
- end: `0x180010254`
- name: `MintValue_CreateIntervalFromMicroseconds_Real`
- size: `196`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001514c`
- `0x180015e14`
- `0x180018480`

## callees

- `0x180006ef8`
- `0x180007c80`
- `0x180010080`
- `0x180010190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800101ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800101ae`

## string_xrefs

- `0x1800101a2`: `mpunits.dll`

## pseudocode

```c
_OWORD *__fastcall MintValue_CreateIntervalFromMicroseconds_Real(_OWORD *a1, double a2)
{
  __int64 v3; // rdx
  __int128 v5; // [rsp+30h] [rbp-18h] BYREF

  if ( a2 >= 0.0 )
  {
    v3 = 8639999999999000000LL;
    if ( a2 <= 8.639999999999e18 )
      v3 = (unsigned int)(int)a2;
  }
  else
  {
    v3 = -1;
  }
  *a1 = *(_OWORD *)MintValue_CreateIntervalFromMicroseconds((__int64)&v5, v3);
  return a1;
}

```

## disassembly

```asm
0x180010190  push    rbx
0x180010192  sub     rsp, 40h
0x180010196  ucomisd xmm1, xmm1
0x18001019a  mov     rbx, rcx
0x18001019d  xorps   xmm0, xmm0
0x1800101a0  jnp     short loc_180010215
0x1800101a2  lea     rcx, ModuleName; "mpunits.dll"
0x1800101a9  movups  [rsp+48h+var_18], xmm0
0x1800101ae  call    cs:__imp_GetModuleHandleA
0x1800101b4  mov     rcx, rax
0x1800101b7  mov     edx, 821h
0x1800101bc  call    _Intlstr_GetString_LoadString
0x1800101c1  mov     qword ptr [rsp+48h+var_18], rax
0x1800101c6  lea     r9, [rsp+48h+var_18]
0x1800101cb  xor     eax, eax
0x1800101cd  lea     rdx, aMi; "MI"
0x1800101d4  mov     byte ptr [rsp+48h+var_18+8], al
0x1800101d8  movaps  xmm0, [rsp+48h+var_18]
0x1800101dd  mov     [rsp+48h+var_20], rax; __int64
0x1800101e2  lea     r8d, [rax+5]
0x1800101e6  movdqa  [rsp+48h+var_18], xmm0
0x1800101ec  lea     ecx, [rax+4]; int
0x1800101ef  mov     [rsp+48h+var_28], rax; __int64
0x1800101f4  call    MI_ReportErrorDetails_ForCustomError
0x1800101f9  xor     edx, edx
0x1800101fb  xor     ecx, ecx
0x1800101fd  mov     eax, 0FFh
0x180010202  mov     [rbx+4], edx
0x180010205  and     eax, 0FFFFFFFEh
0x180010208  mov     [rbx+8], rcx
0x18001020c  or      eax, 0FEh
0x180010211  mov     [rbx], eax
0x180010213  jmp     short loc_18001024B
0x180010215  comisd  xmm0, xmm1
0x180010219  jbe     short loc_180010221
0x18001021b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001021f  jmp     short loc_18001023A
0x180010221  comisd  xmm1, cs:__real@43ddf9dc8e4ad42f
0x180010229  mov     rdx, 77E772392B50BDC0h
0x180010233  ja      short loc_18001023A
0x180010235  cvttsd2si rdx, xmm1
0x18001023a  lea     rcx, [rsp+48h+var_18]
0x18001023f  call    MintValue_CreateIntervalFromMicroseconds
0x180010244  movups  xmm0, xmmword ptr [rax]
0x180010247  movdqu  xmmword ptr [rbx], xmm0
0x18001024b  mov     rax, rbx
0x18001024e  add     rsp, 40h
0x180010252  pop     rbx
0x180010253  retn
```
