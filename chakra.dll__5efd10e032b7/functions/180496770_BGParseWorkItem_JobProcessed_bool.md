# BGParseWorkItem::JobProcessed(bool)

- ea: `0x180496770`
- end: `0x180496829`
- name: `?JobProcessed@BGParseWorkItem@@QEAAX_N@Z`
- size: `185`
- prototype: `void __fastcall(BGParseWorkItem *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1804966c0`

## callees

- `0x18016a52c`
- `0x1802f0c84`
- `0x1803ccd78`
- `0x180495e20`
- `0x180496770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180496811`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180496811`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804967d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1804967d2`

## string_xrefs

- `0x1804967e1`: `[BgParse: Discard Before GetResults -- cookie: %04d on thread 0x%X at %.2f ms]\n`

## pseudocode

```c
void __fastcall BGParseWorkItem::JobProcessed(HANDLE **this)
{
  __int64 v2; // rax
  float v3; // xmm0_4
  DWORD CurrentThreadId; // eax
  __int64 v5; // rcx
  HANDLE *v6; // rcx
  _BYTE v7[16]; // [rsp+20h] [rbp-28h] BYREF

  if ( *((_BYTE *)this + 184) )
  {
    Js::Tick::Now(v7);
    v2 = Js::Tick::ToMicroseconds((Js::Tick *)v7);
    if ( v2 < 0 )
      v3 = (float)(v2 & 1 | (unsigned int)((unsigned __int64)v2 >> 1))
         + (float)(v2 & 1 | (unsigned int)((unsigned __int64)v2 >> 1));
    else
      v3 = (float)(int)v2;
    CurrentThreadId = GetCurrentThreadId();
    Output::Print(
      L"[BgParse: Discard Before GetResults -- cookie: %04d on thread 0x%X at %.2f ms]\n",
      *((unsigned int *)this + 8),
      CurrentThreadId,
      (float)(v3 / 1000.0));
    Memory::DeleteObject<Memory::HeapAllocator,0,BGParseWorkItem>(v5, this);
  }
  else
  {
    v6 = this[22];
    if ( v6 )
      SetEvent(*v6);
  }
}

```

## disassembly

```asm
0x180496770  mov     rax, rsp
0x180496773  mov     [rax+10h], dl
0x180496776  mov     [rax+8], rcx
0x18049677a  push    rbx
0x18049677b  sub     rsp, 40h
0x18049677f  cmp     byte ptr [rcx+0B8h], 0
0x180496786  mov     rbx, rcx
0x180496789  movaps  xmmword ptr [rax-18h], xmm6
0x18049678d  jz      short loc_180496802
0x18049678f  lea     rcx, [rax-28h]
0x180496793  call    ?Now@Tick@Js@@SA?AU12@XZ; Js::Tick::Now(void)
0x180496798  lea     rcx, [rsp+48h+var_28]; this
0x18049679d  call    ?ToMicroseconds@Tick@Js@@QEBA_KXZ; Js::Tick::ToMicroseconds(void)
0x1804967a2  mov     r11, rax
0x1804967a5  xorps   xmm0, xmm0
0x1804967a8  test    rax, rax
0x1804967ab  js      short loc_1804967B4
0x1804967ad  cvtsi2ss xmm0, rax
0x1804967b2  jmp     short loc_1804967C7
0x1804967b4  shr     rax, 1
0x1804967b7  and     r11d, 1
0x1804967bb  or      rax, r11
0x1804967be  cvtsi2ss xmm0, rax
0x1804967c3  addss   xmm0, xmm0
0x1804967c7  divss   xmm0, cs:__real@447a0000
0x1804967cf  cvtps2pd xmm6, xmm0
0x1804967d2  call    cs:__imp_GetCurrentThreadId
0x1804967d9  nop     dword ptr [rax+rax+00h]
0x1804967de  mov     edx, [rbx+20h]
0x1804967e1  lea     rcx, aBgparseDiscard; "[BgParse: Discard Before GetResults -- "...
0x1804967e8  mov     r8d, eax
0x1804967eb  movaps  xmm3, xmm6
0x1804967ee  movq    r9, xmm6
0x1804967f3  call    ?Print@Output@@SA_KPEBGZZ; Output::Print(ushort const *,...)
0x1804967f8  mov     rdx, rbx
0x1804967fb  call    ??$DeleteObject@UHeapAllocator@Memory@@$0A@VBGParseWorkItem@@@Memory@@YAXPEAUHeapAllocator@0@PEAVBGParseWorkItem@@@Z; Memory::DeleteObject<Memory::HeapAllocator,0,BGParseWorkItem>(Memory::HeapAllocator *,BGParseWorkItem *)
0x180496800  jmp     short loc_18049681D
0x180496802  mov     rcx, [rbx+0B0h]
0x180496809  test    rcx, rcx
0x18049680c  jz      short loc_18049681D
0x18049680e  mov     rcx, [rcx]; hEvent
0x180496811  call    cs:__imp_SetEvent
0x180496818  nop     dword ptr [rax+rax+00h]
0x18049681d  movaps  xmm6, [rsp+48h+var_18]
0x180496822  add     rsp, 40h
0x180496826  pop     rbx
0x180496827  retn
```
