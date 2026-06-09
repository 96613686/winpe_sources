# CReaderWriterLock2::ReadLock(void)

- ea: `0x180009570`
- end: `0x1800096c7`
- name: `?ReadLock@CReaderWriterLock2@@QEAAXXZ`
- size: `343`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005520`
- `0x180009cc0`
- `0x18000a5e0`
- `0x18000a690`
- `0x18000aa20`
- `0x18000b840`
- `0x180014780`
- `0x180015470`

## callees

- `0x180009570`
- `0x180009bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800095af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800095af`

## pseudocode

```c
void __fastcall CReaderWriterLock2::ReadLock(CReaderWriterLock2 *this)
{
  signed __int32 v2; // ecx
  unsigned int v3; // ebp
  DWORD CurrentThreadId; // eax
  __int64 v5; // rsi
  unsigned __int16 v6; // r8
  int v7; // edi
  int v8; // edx
  signed __int32 v9; // r8d

  v2 = *(_DWORD *)this;
  if ( (v2 & 0xFFFF8000) != 0 || v2 != _InterlockedCompareExchange((volatile signed __int32 *)this, v2 + 1, v2) )
  {
    v3 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v5 = 0;
    v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
    v7 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
    while ( 1 )
    {
      v8 = v7;
      if ( g_cProcessors < 2 || !v6 )
        v8 = 1;
      while ( --v8 >= 0 )
      {
        if ( (*(_DWORD *)this & 0xFFFF8000) == 0 )
        {
          v9 = *(_DWORD *)this;
          if ( v9 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9 + 1, v9) )
            return;
        }
        _mm_pause();
      }
      SwitchOrSleep(v3);
      if ( (unsigned int)v5 < 4 )
        v3 = dword_180032D40[v5];
      else
        v3 = 100;
      v7 = (int)((double)v7 * CReaderWriterLock2::sm_dblDfltSpinAdjFctr);
      if ( v7 > 10000 )
      {
        v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
        v7 = 10000;
        v5 = (unsigned int)(v5 + 1);
      }
      else
      {
        v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
        if ( v7 <= 100 )
          v7 = 100;
        v5 = (unsigned int)(v5 + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x180009570  push    rbx
0x180009572  sub     rsp, 30h
0x180009576  mov     rbx, rcx
0x180009579  mov     ecx, [rcx]
0x18000957b  test    ecx, 0FFFF8000h
0x180009581  jnz     short loc_180009594
0x180009583  lea     edx, [rcx+1]
0x180009586  mov     eax, ecx
0x180009588  lock cmpxchg [rbx], edx
0x18000958c  cmp     ecx, eax
0x18000958e  jz      loc_180009657
0x180009594  mov     [rsp+38h+arg_0], rbp
0x180009599  xor     ebp, ebp
0x18000959b  mov     [rsp+38h+arg_8], rsi
0x1800095a0  mov     [rsp+38h+arg_10], rdi
0x1800095a5  mov     [rsp+38h+var_10], r14
0x1800095aa  mov     [rsp+38h+var_18], r15
0x1800095af  call    cs:__imp_GetCurrentThreadId
0x1800095b6  nop     dword ptr [rax+rax+00h]
0x1800095bb  lea     r15, __ImageBase
0x1800095c2  mov     r14d, 64h ; 'd'
0x1800095c8  mov     r8d, eax
0x1800095cb  mov     eax, 4EC4EC4Fh
0x1800095d0  mul     r8d
0x1800095d3  shr     edx, 2
0x1800095d6  imul    ecx, edx, 0Dh
0x1800095d9  sub     r8d, ecx
0x1800095dc  mov     ecx, r8d
0x1800095df  xor     esi, esi
0x1800095e1  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x1800095e9  movd    xmm0, r8d
0x1800095ee  cvtdq2pd xmm0, xmm0
0x1800095f2  mulsd   xmm0, ds:rva qword_180032E80[r15+rcx*8]
0x1800095fc  cvttsd2si edi, xmm0
0x180009600  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180009607  mov     edx, edi
0x180009609  jb      loc_1800096BD
0x18000960f  test    r8w, r8w
0x180009613  jz      loc_1800096BD
0x180009619  sub     edx, 1
0x18000961c  js      short loc_18000965E
0x18000961e  mov     r8d, [rbx]
0x180009621  test    r8d, 0FFFF8000h
0x180009628  jnz     short loc_18000963A
0x18000962a  lea     ecx, [r8+1]
0x18000962e  mov     eax, r8d
0x180009631  lock cmpxchg [rbx], ecx
0x180009635  cmp     r8d, eax
0x180009638  jz      short loc_18000963E
0x18000963a  pause
0x18000963c  jmp     short loc_180009619
0x18000963e  mov     r14, [rsp+38h+var_10]
0x180009643  mov     rdi, [rsp+38h+arg_10]
0x180009648  mov     rsi, [rsp+38h+arg_8]
0x18000964d  mov     rbp, [rsp+38h+arg_0]
0x180009652  mov     r15, [rsp+38h+var_18]
0x180009657  add     rsp, 30h
0x18000965b  pop     rbx
0x18000965c  retn
0x18000965e  mov     ecx, ebp; unsigned int
0x180009660  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180009665  cmp     esi, 4
0x180009668  jb      short loc_18000969F
0x18000966a  mov     ebp, r14d
0x18000966d  movd    xmm0, edi
0x180009671  cvtdq2pd xmm0, xmm0
0x180009675  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x18000967d  cvttsd2si edi, xmm0
0x180009681  cmp     edi, 2710h
0x180009687  jg      short loc_1800096A9
0x180009689  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180009691  cmp     edi, r14d
0x180009694  cmovle  edi, r14d
0x180009698  inc     esi
0x18000969a  jmp     loc_180009600
0x18000969f  mov     ebp, ds:rva dword_180032D40[r15+rsi*4]
0x1800096a7  jmp     short loc_18000966D
0x1800096a9  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x1800096b1  mov     edi, 2710h
0x1800096b6  inc     esi
0x1800096b8  jmp     loc_180009600
0x1800096bd  mov     edx, 1
0x1800096c2  jmp     loc_180009619
```
