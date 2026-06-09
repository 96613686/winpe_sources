# CReaderWriterLock2::ReadLock(void)

- ea: `0x180008820`
- end: `0x180008970`
- name: `?ReadLock@CReaderWriterLock2@@QEAAXXZ`
- size: `336`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800049c0`
- `0x180008f40`
- `0x1800098c0`
- `0x180009960`
- `0x180009cd0`
- `0x18000a400`
- `0x180013d30`
- `0x180014880`

## callees

- `0x180008820`
- `0x180008e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000885f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000885f`

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
    v7 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
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
        v3 = dword_180030D30[v5];
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
0x180008820  push    rbx
0x180008822  sub     rsp, 30h
0x180008826  mov     rbx, rcx
0x180008829  mov     ecx, [rcx]
0x18000882b  test    ecx, 0FFFF8000h
0x180008831  jnz     short loc_180008844
0x180008833  lea     edx, [rcx+1]
0x180008836  mov     eax, ecx
0x180008838  lock cmpxchg [rbx], edx
0x18000883c  cmp     ecx, eax
0x18000883e  jz      loc_180008901
0x180008844  mov     [rsp+38h+arg_0], rbp
0x180008849  xor     ebp, ebp
0x18000884b  mov     [rsp+38h+arg_8], rsi
0x180008850  mov     [rsp+38h+arg_10], rdi
0x180008855  mov     [rsp+38h+var_10], r14
0x18000885a  mov     [rsp+38h+var_18], r15
0x18000885f  call    cs:__imp_GetCurrentThreadId
0x180008865  lea     r15, __ImageBase
0x18000886c  mov     r14d, 64h ; 'd'
0x180008872  mov     r8d, eax
0x180008875  mov     eax, 4EC4EC4Fh
0x18000887a  mul     r8d
0x18000887d  shr     edx, 2
0x180008880  imul    ecx, edx, 0Dh
0x180008883  sub     r8d, ecx
0x180008886  mov     ecx, r8d
0x180008889  xor     esi, esi
0x18000888b  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180008893  movd    xmm0, r8d
0x180008898  cvtdq2pd xmm0, xmm0
0x18000889c  mulsd   xmm0, ds:rva qword_180030E80[r15+rcx*8]
0x1800088a6  cvttsd2si edi, xmm0
0x1800088aa  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x1800088b1  mov     edx, edi
0x1800088b3  jb      loc_180008966
0x1800088b9  test    r8w, r8w
0x1800088bd  jz      loc_180008966
0x1800088c3  sub     edx, 1
0x1800088c6  js      short loc_180008907
0x1800088c8  mov     r8d, [rbx]
0x1800088cb  test    r8d, 0FFFF8000h
0x1800088d2  jnz     short loc_1800088E4
0x1800088d4  lea     ecx, [r8+1]
0x1800088d8  mov     eax, r8d
0x1800088db  lock cmpxchg [rbx], ecx
0x1800088df  cmp     r8d, eax
0x1800088e2  jz      short loc_1800088E8
0x1800088e4  pause
0x1800088e6  jmp     short loc_1800088C3
0x1800088e8  mov     r14, [rsp+38h+var_10]
0x1800088ed  mov     rdi, [rsp+38h+arg_10]
0x1800088f2  mov     rsi, [rsp+38h+arg_8]
0x1800088f7  mov     rbp, [rsp+38h+arg_0]
0x1800088fc  mov     r15, [rsp+38h+var_18]
0x180008901  add     rsp, 30h
0x180008905  pop     rbx
0x180008906  retn
0x180008907  mov     ecx, ebp; unsigned int
0x180008909  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18000890e  cmp     esi, 4
0x180008911  jb      short loc_180008948
0x180008913  mov     ebp, r14d
0x180008916  movd    xmm0, edi
0x18000891a  cvtdq2pd xmm0, xmm0
0x18000891e  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x180008926  cvttsd2si edi, xmm0
0x18000892a  cmp     edi, 2710h
0x180008930  jg      short loc_180008952
0x180008932  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x18000893a  cmp     edi, r14d
0x18000893d  cmovle  edi, r14d
0x180008941  inc     esi
0x180008943  jmp     loc_1800088AA
0x180008948  mov     ebp, ds:rva dword_180030D30[r15+rsi*4]
0x180008950  jmp     short loc_180008916
0x180008952  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x18000895a  mov     edi, 2710h
0x18000895f  inc     esi
0x180008961  jmp     loc_1800088AA
0x180008966  mov     edx, 1
0x18000896b  jmp     loc_1800088C3
```
