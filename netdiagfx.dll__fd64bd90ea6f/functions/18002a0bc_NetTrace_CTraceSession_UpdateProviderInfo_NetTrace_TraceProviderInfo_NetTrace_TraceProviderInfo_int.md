# NetTrace::CTraceSession::UpdateProviderInfo(NetTrace::TraceProviderInfo &,NetTrace::TraceProviderInfo &,int)

- ea: `0x18002a0bc`
- end: `0x18002a158`
- name: `?UpdateProviderInfo@CTraceSession@NetTrace@@AEAAJAEAUTraceProviderInfo@2@0H@Z`
- size: `156`
- prototype: `int(NetTrace::CTraceSession *__hidden this, struct NetTrace::TraceProviderInfo *, struct NetTrace::TraceProviderInfo *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180028bd0`

## callees

- `0x1800020d6`
- `0x1800299c8`
- `0x18002a0bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a114`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a114`

## pseudocode

```c
__int64 __fastcall NetTrace::CTraceSession::UpdateProviderInfo(
        unsigned __int64 this,
        struct NetTrace::TraceProviderInfo *a2,
        struct NetTrace::TraceProviderInfo *a3)
{
  unsigned int v3; // esi
  __int64 v6; // rax
  unsigned int v7; // edx
  void *v8; // rax

  v3 = 0;
  *(_OWORD *)a3 = *(_OWORD *)a2;
  v6 = *((_QWORD *)a2 + 3);
  if ( v6 )
    *((_QWORD *)a3 + 3) |= v6;
  v7 = *((unsigned __int8 *)a2 + 16);
  if ( (_BYTE)v7 )
  {
    this = *((unsigned __int8 *)a3 + 16);
    if ( (unsigned __int8)this <= (unsigned __int8)v7 )
      this = v7;
    *((_BYTE *)a3 + 16) = this;
  }
  if ( *((_QWORD *)a2 + 4) )
  {
    if ( *((_DWORD *)a2 + 10) )
    {
      NetTrace::CTraceSession::ReleaseProviderFilterData((NetTrace::CTraceSession *)this, a3);
      v8 = CoTaskMemAlloc(*((unsigned int *)a2 + 10));
      *((_QWORD *)a3 + 4) = v8;
      v3 = -2147024882;
      if ( v8 )
      {
        v3 = 0;
        memcpy_0(v8, *((const void **)a2 + 4), *((unsigned int *)a2 + 10));
        *((_DWORD *)a3 + 10) = *((_DWORD *)a2 + 10);
        *((_DWORD *)a3 + 11) = *((_DWORD *)a2 + 11);
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18002a0bc  mov     [rsp+arg_0], rbx
0x18002a0c1  mov     [rsp+arg_8], rsi
0x18002a0c6  push    rdi
0x18002a0c7  sub     rsp, 20h
0x18002a0cb  movups  xmm0, xmmword ptr [rdx]
0x18002a0ce  xor     esi, esi
0x18002a0d0  mov     rdi, r8
0x18002a0d3  mov     rbx, rdx
0x18002a0d6  movdqu  xmmword ptr [r8], xmm0
0x18002a0db  mov     rax, [rdx+18h]
0x18002a0df  test    rax, rax
0x18002a0e2  jz      short loc_18002A0E8
0x18002a0e4  or      [r8+18h], rax
0x18002a0e8  movzx   edx, byte ptr [rdx+10h]
0x18002a0ec  test    dl, dl
0x18002a0ee  jz      short loc_18002A0FE
0x18002a0f0  movzx   ecx, byte ptr [r8+10h]
0x18002a0f5  cmp     cl, dl
0x18002a0f7  cmovbe  ecx, edx; this
0x18002a0fa  mov     [r8+10h], cl
0x18002a0fe  cmp     [rbx+20h], rsi
0x18002a102  jz      short loc_18002A146
0x18002a104  cmp     [rbx+28h], esi
0x18002a107  jz      short loc_18002A146
0x18002a109  mov     rdx, rdi; struct NetTrace::TraceProviderInfo *
0x18002a10c  call    ?ReleaseProviderFilterData@CTraceSession@NetTrace@@AEAAXAEAUTraceProviderInfo@2@@Z; NetTrace::CTraceSession::ReleaseProviderFilterData(NetTrace::TraceProviderInfo &)
0x18002a111  mov     ecx, [rbx+28h]; cb
0x18002a114  call    cs:__imp_CoTaskMemAlloc
0x18002a11a  mov     [rdi+20h], rax
0x18002a11e  mov     esi, 8007000Eh
0x18002a123  test    rax, rax
0x18002a126  jz      short loc_18002A146
0x18002a128  mov     r8d, [rbx+28h]; Size
0x18002a12c  xor     esi, esi
0x18002a12e  mov     rdx, [rbx+20h]; Src
0x18002a132  mov     rcx, rax; void *
0x18002a135  call    memcpy_0
0x18002a13a  mov     ecx, [rbx+28h]
0x18002a13d  mov     [rdi+28h], ecx
0x18002a140  mov     ecx, [rbx+2Ch]
0x18002a143  mov     [rdi+2Ch], ecx
0x18002a146  mov     rbx, [rsp+28h+arg_0]
0x18002a14b  mov     eax, esi
0x18002a14d  mov     rsi, [rsp+28h+arg_8]
0x18002a152  add     rsp, 20h
0x18002a156  pop     rdi
0x18002a157  retn
```
