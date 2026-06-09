# RecyclerPageAllocator::ResetWriteWatch(void)

- ea: `0x18015b6e0`
- end: `0x18015b7da`
- name: `?ResetWriteWatch@RecyclerPageAllocator@@QEAA_NXZ`
- size: `250`
- prototype: `bool __fastcall(RecyclerPageAllocator *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007b8c`
- `0x180007f6c`
- `0x180164260`

## callees

- `0x18000463c`
- `0x18000ed88`
- `0x18015b6e0`
- `0x18015b7e0`

## import_xrefs

- `KERNEL32!ResetWriteWatch` at `0x18015b749`
- `KERNEL32!ResetWriteWatch` at `0x18015b799`
- `KERNEL32!ResetWriteWatch` at `0x18015b749`
- `KERNEL32!ResetWriteWatch` at `0x18015b799`

## pseudocode

```c
char __fastcall RecyclerPageAllocator::ResetWriteWatch(RecyclerPageAllocator *this)
{
  __int64 v2; // rcx
  LPVOID *v3; // rdi
  char v4; // si
  LPVOID *v6; // rdi

  if ( *((_DWORD *)this + 23) != 0x200000 )
    return 0;
  if ( (Microsoft_JScriptEnableBits & 0x20) != 0 )
    McTemplateU0p_EventWriteTransfer(this, JSCRIPT_GC_RESETWRITEWATCH_START, this);
  PageAllocator::SuspendIdleDecommit(this);
  if ( (unsigned __int8)RecyclerPageAllocator::ResetWriteWatch((char *)this + 8)
    && (unsigned __int8)RecyclerPageAllocator::ResetWriteWatch((char *)this + 56) )
  {
    v3 = (LPVOID *)((char *)this + 24);
    while ( 1 )
    {
      v3 = (LPVOID *)*v3;
      if ( v3 == (LPVOID *)((char *)this + 24) )
        break;
      if ( ResetWriteWatch(v3[4], (_QWORD)v3[5] << 12) )
        goto LABEL_9;
    }
    v4 = 1;
    v6 = (LPVOID *)((char *)this + 72);
    while ( 1 )
    {
      v6 = (LPVOID *)*v6;
      if ( v6 == (LPVOID *)((char *)this + 72) )
        break;
      if ( ResetWriteWatch(v6[4], (_QWORD)v6[5] << 12) )
        goto LABEL_9;
    }
  }
  else
  {
LABEL_9:
    *((_DWORD *)this + 23) = 0;
    v4 = 0;
  }
  if ( !*((_DWORD *)this + 38) )
    *((_DWORD *)this + 60) = 0;
  if ( (Microsoft_JScriptEnableBits & 0x20) != 0 )
    McTemplateU0p_EventWriteTransfer(v2, JSCRIPT_GC_RESETWRITEWATCH_STOP, this);
  return v4;
}

```

## disassembly

```asm
0x18015b6e0  mov     [rsp+arg_0], rcx
0x18015b6e5  push    rbx
0x18015b6e6  push    rbp
0x18015b6e7  push    rsi
0x18015b6e8  push    rdi
0x18015b6e9  sub     rsp, 28h
0x18015b6ed  mov     rbx, [rsp+48h+arg_0]
0x18015b6f2  cmp     dword ptr [rbx+5Ch], 200000h
0x18015b6f9  jnz     loc_18015B7B1
0x18015b6ff  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x18015b706  jnz     loc_18015B7B5
0x18015b70c  mov     rcx, rbx; this
0x18015b70f  call    ?SuspendIdleDecommit@PageAllocator@@QEAAXXZ; PageAllocator::SuspendIdleDecommit(void)
0x18015b714  lea     rcx, [rbx+8]
0x18015b718  call    ?ResetWriteWatch@RecyclerPageAllocator@@CA_NPEAV?$DListBase@VPageSegment@@@@@Z; RecyclerPageAllocator::ResetWriteWatch(DListBase<PageSegment> *)
0x18015b71d  test    al, al
0x18015b71f  jz      short loc_18015B753
0x18015b721  lea     rcx, [rbx+38h]
0x18015b725  call    ?ResetWriteWatch@RecyclerPageAllocator@@CA_NPEAV?$DListBase@VPageSegment@@@@@Z; RecyclerPageAllocator::ResetWriteWatch(DListBase<PageSegment> *)
0x18015b72a  test    al, al
0x18015b72c  jz      short loc_18015B753
0x18015b72e  lea     rsi, [rbx+18h]
0x18015b732  mov     rdi, rsi
0x18015b735  mov     rdi, [rdi]
0x18015b738  cmp     rdi, rsi
0x18015b73b  jz      short loc_18015B77B
0x18015b73d  mov     rdx, [rdi+28h]
0x18015b741  mov     rcx, [rdi+20h]; lpBaseAddress
0x18015b745  shl     rdx, 0Ch; dwRegionSize
0x18015b749  call    cs:__imp_ResetWriteWatch
0x18015b74f  test    eax, eax
0x18015b751  jz      short loc_18015B735
0x18015b753  mov     dword ptr [rbx+5Ch], 0
0x18015b75a  xor     sil, sil
0x18015b75d  cmp     dword ptr [rbx+98h], 0
0x18015b764  jz      short loc_18015B7A5
0x18015b766  test    byte ptr cs:Microsoft_JScriptEnableBits, 20h
0x18015b76d  jnz     short loc_18015B7C9
0x18015b76f  mov     al, sil
0x18015b772  add     rsp, 28h
0x18015b776  pop     rdi
0x18015b777  pop     rsi
0x18015b778  pop     rbp
0x18015b779  pop     rbx
0x18015b77a  retn
0x18015b77b  lea     rbp, [rbx+48h]
0x18015b77f  mov     sil, 1
0x18015b782  mov     rdi, rbp
0x18015b785  mov     rdi, [rdi]
0x18015b788  cmp     rdi, rbp
0x18015b78b  jz      short loc_18015B75D
0x18015b78d  mov     rdx, [rdi+28h]
0x18015b791  mov     rcx, [rdi+20h]; lpBaseAddress
0x18015b795  shl     rdx, 0Ch; dwRegionSize
0x18015b799  call    cs:__imp_ResetWriteWatch
0x18015b79f  test    eax, eax
0x18015b7a1  jz      short loc_18015B785
0x18015b7a3  jmp     short loc_18015B753
0x18015b7a5  mov     dword ptr [rbx+0F0h], 0
0x18015b7af  jmp     short loc_18015B766
0x18015b7b1  xor     al, al
0x18015b7b3  jmp     short loc_18015B772
0x18015b7b5  mov     r8, rbx
0x18015b7b8  lea     rdx, JSCRIPT_GC_RESETWRITEWATCH_START
0x18015b7bf  call    McTemplateU0p_EventWriteTransfer
0x18015b7c4  jmp     loc_18015B70C
0x18015b7c9  mov     r8, rbx
0x18015b7cc  lea     rdx, JSCRIPT_GC_RESETWRITEWATCH_STOP
0x18015b7d3  call    McTemplateU0p_EventWriteTransfer
0x18015b7d8  jmp     short loc_18015B76F
```
