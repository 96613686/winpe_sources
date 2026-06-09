# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x180008de0`
- end: `0x180008f12`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `306`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this, bool)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800080f0`
- `0x180008470`
- `0x1800096d0`
- `0x180009cc0`
- `0x18000a180`
- `0x18000a5e0`
- `0x18000b020`
- `0x18000b310`
- `0x18000bd30`
- `0x18000e280`
- `0x1800160c0`

## callees

- `0x180008de0`
- `0x180009bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dfb`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_LockSpin(CReaderWriterLock2 *this, char a2)
{
  unsigned int v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r8d
  signed __int32 v10; // edx
  signed __int32 v11; // ecx
  char v12; // al

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v3);
      if ( v7 < 4 )
        v3 = dword_180032D40[v7];
      else
        v3 = 100;
      v8 = (int)((double)v8 * CReaderWriterLock2::sm_dblDfltSpinAdjFctr);
      if ( v8 > 10000 )
      {
        v8 = 10000;
      }
      else if ( v8 <= 100 )
      {
        v8 = 100;
      }
      v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    v10 = *(_DWORD *)this;
    if ( a2 )
    {
      if ( !(_WORD)v10 )
      {
        v11 = v10 | 0xFFFF;
LABEL_8:
        v12 = 1;
        if ( v10 == _InterlockedCompareExchange((volatile signed __int32 *)this, v11, v10) )
          goto LABEL_10;
      }
    }
    else if ( (v10 & 0xFFFF8000) == 0 )
    {
      v11 = v10 + 1;
      goto LABEL_8;
    }
    v12 = 0;
LABEL_10:
    if ( v12 )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180008de0  push    rbx
0x180008de2  push    rbp
0x180008de3  push    rsi
0x180008de4  push    rdi
0x180008de5  push    r12
0x180008de7  push    r14
0x180008de9  push    r15
0x180008deb  sub     rsp, 20h
0x180008def  xor     r15d, r15d
0x180008df2  mov     r14b, dl
0x180008df5  mov     ebp, r15d
0x180008df8  mov     rdi, rcx
0x180008dfb  call    cs:__imp_GetCurrentThreadId
0x180008e02  nop     dword ptr [rax+rax+00h]
0x180008e07  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180008e0e  lea     r12d, [r15+64h]
0x180008e12  mov     r9d, eax
0x180008e15  mov     esi, r15d
0x180008e18  mov     eax, 4EC4EC4Fh
0x180008e1d  mul     r9d
0x180008e20  movd    xmm0, ecx
0x180008e24  cvtdq2pd xmm0, xmm0
0x180008e28  shr     edx, 2
0x180008e2b  imul    r8d, edx, 0Dh
0x180008e2f  lea     rdx, __ImageBase
0x180008e36  sub     r9d, r8d
0x180008e39  mulsd   xmm0, ds:rva qword_180032E80[rdx+r9*8]
0x180008e43  cvttsd2si ebx, xmm0
0x180008e47  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180008e4e  mov     r8d, ebx
0x180008e51  jb      loc_180008F07
0x180008e57  test    cx, cx
0x180008e5a  jz      loc_180008F07
0x180008e60  sub     r8d, 1
0x180008e64  js      short loc_180008E8F
0x180008e66  mov     edx, [rdi]
0x180008e68  test    r14b, r14b
0x180008e6b  jnz     short loc_180008ECF
0x180008e6d  test    edx, 0FFFF8000h
0x180008e73  jnz     short loc_180008E84
0x180008e75  lea     ecx, [rdx+1]
0x180008e78  mov     eax, edx
0x180008e7a  lock cmpxchg [rdi], ecx
0x180008e7e  cmp     edx, eax
0x180008e80  mov     al, 1
0x180008e82  jz      short loc_180008E87
0x180008e84  mov     al, r15b
0x180008e87  test    al, al
0x180008e89  jnz     short loc_180008EDE
0x180008e8b  pause
0x180008e8d  jmp     short loc_180008E60
0x180008e8f  mov     ecx, ebp; unsigned int
0x180008e91  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180008e96  cmp     esi, 4
0x180008e99  jb      short loc_180008EEE
0x180008e9b  mov     ebp, r12d
0x180008e9e  movd    xmm0, ebx
0x180008ea2  cvtdq2pd xmm0, xmm0
0x180008ea6  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x180008eae  cvttsd2si ebx, xmm0
0x180008eb2  cmp     ebx, 2710h
0x180008eb8  jg      short loc_180008F00
0x180008eba  cmp     ebx, r12d
0x180008ebd  cmovle  ebx, r12d
0x180008ec1  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180008ec8  inc     esi
0x180008eca  jmp     loc_180008E47
0x180008ecf  test    dx, dx
0x180008ed2  jnz     short loc_180008E84
0x180008ed4  mov     ecx, edx
0x180008ed6  or      ecx, 0FFFFh
0x180008edc  jmp     short loc_180008E78
0x180008ede  add     rsp, 20h
0x180008ee2  pop     r15
0x180008ee4  pop     r14
0x180008ee6  pop     r12
0x180008ee8  pop     rdi
0x180008ee9  pop     rsi
0x180008eea  pop     rbp
0x180008eeb  pop     rbx
0x180008eec  retn
0x180008eee  mov     eax, esi
0x180008ef0  lea     rcx, __ImageBase
0x180008ef7  mov     ebp, ds:rva dword_180032D40[rcx+rax*4]
0x180008efe  jmp     short loc_180008E9E
0x180008f00  mov     ebx, 2710h
0x180008f05  jmp     short loc_180008EC1
0x180008f07  mov     r8d, 1
0x180008f0d  jmp     loc_180008E60
```
