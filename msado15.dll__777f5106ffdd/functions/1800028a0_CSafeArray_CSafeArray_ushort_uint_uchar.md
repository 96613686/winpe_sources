# CSafeArray::CSafeArray(ushort,uint,uchar,...)

- ea: `0x1800028a0`
- end: `0x180002985`
- name: `??0CSafeArray@@QEAA@GIEZZ`
- size: `229`
- prototype: `CSafeArray *(CSafeArray *__hidden this, unsigned __int16, unsigned int, unsigned __int8, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002990`
- `0x18001fb90`
- `0x180078c80`
- `0x1800aed30`

## callees

- `0x1800028a0`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180002901`
- `MSDART!MpHeapAlloc` at `0x180002901`
- `MSDART!MpHeapFree` at `0x18000296a`
- `MSDART!MpHeapFree` at `0x18000296a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002945`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180002945`

## pseudocode

```c
CSafeArray *CSafeArray::CSafeArray(CSafeArray *this, VARTYPE a2, UINT a3, unsigned __int8 a4, ...)
{
  va_list v5; // rsi
  SAFEARRAYBOUND *v8; // rdi
  signed int i; // edx
  ULONG v10; // eax
  SAFEARRAY *v11; // rax
  void *v12; // rcx
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  *(_QWORD *)this = &CBlob::`vftable';
  va_copy(v5, va);
  *((_WORD *)this + 14) = a2;
  *((_DWORD *)this + 2) = a4 & 0xFE;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  v8 = (SAFEARRAYBOUND *)MpHeapAlloc(g_hHeapHandle, 10485760, 8LL * a3);
  if ( v8 )
  {
    for ( i = 0; i < (int)a3; ++i )
    {
      v5 += 8;
      v8[i].lLbound = 0;
      v10 = *((_DWORD *)v5 - 2);
      v8[i].cElements = v10;
      if ( !v10 )
      {
        v11 = 0;
        goto LABEL_8;
      }
    }
    v11 = SafeArrayCreate(a2, a3, v8);
LABEL_8:
    *((_QWORD *)this + 2) = v11;
    v12 = g_hHeapHandle;
    *((_DWORD *)this + 2) = a4 | 4;
    MpHeapFree(v12, v8);
  }
  return this;
}

```

## disassembly

```asm
0x1800028a0  mov     r11, rsp
0x1800028a3  mov     [r11+20h], r9b
0x1800028a7  push    rbx
0x1800028a8  push    rbp
0x1800028a9  push    rsi
0x1800028aa  push    rdi
0x1800028ab  push    r14
0x1800028ad  sub     rsp, 30h
0x1800028b1  lea     rax, ??_7CBlob@@6B@; const CBlob::`vftable'
0x1800028b8  mov     ebp, r8d
0x1800028bb  mov     [rcx], rax
0x1800028be  lea     rsi, [r11+28h]
0x1800028c2  mov     [rcx+1Ch], dx
0x1800028c6  movzx   r14d, dx
0x1800028ca  movzx   eax, r9b
0x1800028ce  mov     rbx, rcx
0x1800028d1  and     eax, 0FFFFFFFEh
0x1800028d4  mov     r8d, r8d
0x1800028d7  mov     [rcx+8], eax
0x1800028da  mov     edx, 0A00000h
0x1800028df  mov     qword ptr [rcx+10h], 0
0x1800028e7  mov     dword ptr [rcx+18h], 0
0x1800028ee  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800028f5  shl     r8, 3
0x1800028f9  mov     qword ptr [r11-38h], 0
0x180002901  call    cs:__imp_MpHeapAlloc
0x180002908  nop     dword ptr [rax+rax+00h]
0x18000290d  mov     rdi, rax
0x180002910  test    rax, rax
0x180002913  jz      short loc_180002976
0x180002915  xor     edx, edx
0x180002917  cmp     edx, ebp
0x180002919  jge     short loc_18000293C
0x18000291b  movsxd  rcx, edx
0x18000291e  add     rsi, 8
0x180002922  mov     dword ptr [rdi+rcx*8+4], 0
0x18000292a  mov     eax, [rsi-8]
0x18000292d  mov     [rdi+rcx*8], eax
0x180002930  test    eax, eax
0x180002932  jz      short loc_180002938
0x180002934  inc     edx
0x180002936  jmp     short loc_180002917
0x180002938  xor     eax, eax
0x18000293a  jmp     short loc_180002951
0x18000293c  mov     r8, rdi; rgsabound
0x18000293f  mov     edx, ebp; cDims
0x180002941  movzx   ecx, r14w; vt
0x180002945  call    cs:__imp_SafeArrayCreate
0x18000294c  nop     dword ptr [rax+rax+00h]
0x180002951  mov     [rbx+10h], rax
0x180002955  mov     rdx, rdi
0x180002958  movzx   eax, [rsp+58h+arg_18]
0x18000295d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180002964  or      eax, 4
0x180002967  mov     [rbx+8], eax
0x18000296a  call    cs:__imp_MpHeapFree
0x180002971  nop     dword ptr [rax+rax+00h]
0x180002976  mov     rax, rbx
0x180002979  add     rsp, 30h
0x18000297d  pop     r14
0x18000297f  pop     rdi
0x180002980  pop     rsi
0x180002981  pop     rbp
0x180002982  pop     rbx
0x180002983  retn
```
