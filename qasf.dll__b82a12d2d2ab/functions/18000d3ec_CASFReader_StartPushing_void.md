# CASFReader::StartPushing(void)

- ea: `0x18000d3ec`
- end: `0x18000d4e7`
- name: `?StartPushing@CASFReader@@AEAAJXZ`
- size: `251`
- prototype: `__int64 __fastcall(CASFReader *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000c680`
- `0x18000dc60`
- `0x18000dea0`

## callees

- `0x18000d1e0`
- `0x18000d3ec`
- `0x18001f010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000d4cb`
- `KERNEL32!WaitForSingleObject` at `0x18000d4cb`
- `KERNEL32!ResetEvent` at `0x18000d489`
- `KERNEL32!ResetEvent` at `0x18000d489`

## pseudocode

```c
__int64 __fastcall CASFReader::StartPushing(CASFReader *this)
{
  __int64 i; // rsi
  __int64 *v3; // rcx
  __int64 v4; // rax
  bool v5; // zf
  __int64 result; // rax
  void *v7; // rcx

  for ( i = *((_QWORD *)this + 35); i; i = *(_QWORD *)(i + 8) )
  {
    v3 = *(__int64 **)(i + 16);
    v4 = *v3;
    *((_DWORD *)v3 + 72) = 1;
    *(__int64 *)((char *)v3 + 316) = 0;
    (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))(v4 + 176))(v3, *((_QWORD *)this + 32), *((_QWORD *)this + 33));
  }
  v5 = *((_DWORD *)this + 112) == 0;
  *((_DWORD *)this + 114) = 0;
  if ( !v5 || (result = CASFReader::SetupActiveStreams(this, 0), (int)result >= 0) )
  {
    v7 = (void *)*((_QWORD *)this + 54);
    *((_DWORD *)this + 111) = -1;
    ResetEvent(v7);
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 43) + 80LL))(
               *((_QWORD *)this + 43),
               *((_QWORD *)this + 32),
               0);
    if ( (int)result >= 0 )
    {
      WaitForSingleObject(*((HANDLE *)this + 54), 0xFFFFFFFF);
      return *((unsigned int *)this + 110);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d3ec  mov     [rsp+arg_0], rbx
0x18000d3f1  mov     [rsp+arg_8], rsi
0x18000d3f6  push    rdi
0x18000d3f7  sub     rsp, 30h
0x18000d3fb  mov     rsi, [rcx+118h]
0x18000d402  lea     rdi, [rcx+0F8h]
0x18000d409  mov     rbx, rcx
0x18000d40c  test    rsi, rsi
0x18000d40f  jz      short loc_18000D457
0x18000d411  mov     rcx, [rsi+10h]
0x18000d415  mov     rax, [rcx]
0x18000d418  mov     dword ptr [rcx+120h], 1
0x18000d422  mov     qword ptr [rcx+13Ch], 0
0x18000d42d  movsd   xmm3, qword ptr [rdi]
0x18000d431  mov     rax, [rax+0B0h]
0x18000d438  mov     r8, [rbx+108h]
0x18000d43f  mov     rdx, [rbx+100h]
0x18000d446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d44b  mov     rax, [rsi+8]
0x18000d44f  mov     rsi, rax
0x18000d452  test    rax, rax
0x18000d455  jnz     short loc_18000D411
0x18000d457  cmp     dword ptr [rbx+1C0h], 0
0x18000d45e  mov     dword ptr [rbx+1C8h], 0
0x18000d468  jnz     short loc_18000D478
0x18000d46a  xor     edx, edx; int
0x18000d46c  mov     rcx, rbx; this
0x18000d46f  call    ?SetupActiveStreams@CASFReader@@AEAAJH@Z; CASFReader::SetupActiveStreams(int)
0x18000d474  test    eax, eax
0x18000d476  js      short loc_18000D4D7
0x18000d478  mov     rcx, [rbx+1B0h]; hEvent
0x18000d47f  mov     dword ptr [rbx+1BCh], 0FFFFFFFFh
0x18000d489  call    cs:__imp_ResetEvent
0x18000d48f  mov     rcx, [rbx+158h]
0x18000d496  xor     r8d, r8d
0x18000d499  movsd   xmm3, qword ptr [rdi]
0x18000d49d  mov     rdx, [rbx+100h]
0x18000d4a4  cvtpd2ps xmm3, xmm3
0x18000d4a8  mov     rax, [rcx]
0x18000d4ab  mov     [rsp+38h+var_18], 0
0x18000d4b4  mov     rax, [rax+50h]
0x18000d4b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4bd  test    eax, eax
0x18000d4bf  js      short loc_18000D4D7
0x18000d4c1  mov     rcx, [rbx+1B0h]; hHandle
0x18000d4c8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d4cb  call    cs:__imp_WaitForSingleObject
0x18000d4d1  mov     eax, [rbx+1B8h]
0x18000d4d7  mov     rbx, [rsp+38h+arg_0]
0x18000d4dc  mov     rsi, [rsp+38h+arg_8]
0x18000d4e1  add     rsp, 30h
0x18000d4e5  pop     rdi
0x18000d4e6  retn
```
