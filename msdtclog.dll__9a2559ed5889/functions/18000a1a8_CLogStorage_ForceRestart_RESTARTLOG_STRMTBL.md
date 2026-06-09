# CLogStorage::ForceRestart(_RESTARTLOG *,_STRMTBL *)

- ea: `0x18000a1a8`
- end: `0x18000a282`
- name: `?ForceRestart@CLogStorage@@QEAAXPEAU_RESTARTLOG@@PEAU_STRMTBL@@@Z`
- size: `218`
- prototype: `void __fastcall(CLogStorage *__hidden this, struct _RESTARTLOG *, struct _STRMTBL *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042b4`
- `0x180006f8c`
- `0x180008090`
- `0x180013b24`

## callees

- `0x18000b974`
- `0x18000c6b8`
- `0x1800127f2`
- `0x180015010`

## pseudocode

```c
void __fastcall CLogStorage::ForceRestart(CLogStorage *this, struct _RESTARTLOG *a2, struct _STRMTBL *a3)
{
  unsigned int v4; // edx
  struct CBuffer *v7; // rbp
  __int64 v8; // rdi

  v4 = 0;
  if ( !*((_DWORD *)this + 26) )
    v4 = *((_DWORD *)this + 10);
  v7 = CLogStorage::_MapBuffer(this, v4, *((_DWORD *)this + 10), 0, 0);
  v8 = *((_QWORD *)v7 + 3);
  *(_DWORD *)(v8 + 8) = *(_DWORD *)this;
  *(_DWORD *)v8 = 1381258066;
  *(_DWORD *)(v8 + 20) = *((_DWORD *)this + 10);
  *(_OWORD *)(v8 + 24) = *(_OWORD *)a2;
  *(_OWORD *)(v8 + 40) = *((_OWORD *)a2 + 1);
  *(_OWORD *)(v8 + 56) = *((_OWORD *)a2 + 2);
  *(_OWORD *)(v8 + 72) = *((_OWORD *)a2 + 3);
  *(_OWORD *)(v8 + 88) = *((_OWORD *)a2 + 4);
  *(_DWORD *)(v8 + 104) = *((_DWORD *)a2 + 20);
  memcpy_0((void *)(v8 + 108), a3, 44LL * *((unsigned __int16 *)a2 + 32));
  *(_DWORD *)(v8 + 4) = ((__int64 (__fastcall *)(_QWORD, __int64, void *))lpCalcCRC)(
                          (unsigned int)(*((_DWORD *)this + 10) - 8),
                          v8 + 8,
                          pulCRCTable);
  CLogStorage::_UnmapBuffer(this, (LPCVOID *)v7, 1);
  *((_DWORD *)this + 26) = *((_DWORD *)this + 26) == 0;
}

```

## disassembly

```asm
0x18000a1a8  push    rbx
0x18000a1aa  push    rbp
0x18000a1ab  push    rsi
0x18000a1ac  push    rdi
0x18000a1ad  push    r14
0x18000a1af  push    r15
0x18000a1b1  sub     rsp, 38h
0x18000a1b5  mov     rsi, rdx
0x18000a1b8  mov     [rsp+68h+var_48], 0; unsigned int
0x18000a1c0  xor     edx, edx
0x18000a1c2  mov     r14, r8
0x18000a1c5  cmp     [rcx+68h], edx
0x18000a1c8  mov     r15, rcx
0x18000a1cb  mov     r8d, [rcx+28h]; unsigned int
0x18000a1cf  cmovz   edx, r8d; unsigned int
0x18000a1d3  xor     r9d, r9d; int
0x18000a1d6  call    ?_MapBuffer@CLogStorage@@AEAAPEAVCBuffer@@KKHK@Z; CLogStorage::_MapBuffer(ulong,ulong,int,ulong)
0x18000a1db  mov     ecx, [r15]
0x18000a1de  mov     rbp, rax
0x18000a1e1  mov     rdx, r14; Src
0x18000a1e4  mov     rdi, [rax+18h]
0x18000a1e8  mov     [rdi+8], ecx
0x18000a1eb  mov     dword ptr [rdi], 52545352h
0x18000a1f1  mov     ecx, [r15+28h]
0x18000a1f5  mov     [rdi+14h], ecx
0x18000a1f8  lea     rcx, [rdi+6Ch]; void *
0x18000a1fc  movaps  xmm0, xmmword ptr [rsi]
0x18000a1ff  movups  xmmword ptr [rdi+18h], xmm0
0x18000a203  movaps  xmm1, xmmword ptr [rsi+10h]
0x18000a207  movups  xmmword ptr [rdi+28h], xmm1
0x18000a20b  movaps  xmm0, xmmword ptr [rsi+20h]
0x18000a20f  movups  xmmword ptr [rdi+38h], xmm0
0x18000a213  movaps  xmm1, xmmword ptr [rsi+30h]
0x18000a217  movups  xmmword ptr [rdi+48h], xmm1
0x18000a21b  movaps  xmm0, xmmword ptr [rsi+40h]
0x18000a21f  movups  xmmword ptr [rdi+58h], xmm0
0x18000a223  mov     eax, [rsi+50h]
0x18000a226  mov     [rdi+68h], eax
0x18000a229  movzx   eax, word ptr [rsi+40h]
0x18000a22d  imul    r8, rax, 2Ch ; ','; Size
0x18000a231  call    memcpy_0
0x18000a236  mov     ecx, [r15+28h]
0x18000a23a  lea     rdx, [rdi+8]
0x18000a23e  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x18000a245  sub     ecx, 8
0x18000a248  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x18000a24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a254  mov     r8d, 1; int
0x18000a25a  mov     [rdi+4], eax
0x18000a25d  mov     rdx, rbp; struct CBuffer *
0x18000a260  mov     rcx, r15; this
0x18000a263  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a268  xor     eax, eax
0x18000a26a  cmp     [r15+68h], eax
0x18000a26e  setz    al
0x18000a271  mov     [r15+68h], eax
0x18000a275  add     rsp, 38h
0x18000a279  pop     r15
0x18000a27b  pop     r14
0x18000a27d  pop     rdi
0x18000a27e  pop     rsi
0x18000a27f  pop     rbp
0x18000a280  pop     rbx
0x18000a281  retn
```
