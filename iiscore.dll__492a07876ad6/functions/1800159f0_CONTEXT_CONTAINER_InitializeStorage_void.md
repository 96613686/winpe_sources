# CONTEXT_CONTAINER::InitializeStorage(void)

- ea: `0x1800159f0`
- end: `0x180015ad4`
- name: `?InitializeStorage@CONTEXT_CONTAINER@@AEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(CONTEXT_CONTAINER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180015940`
- `0x1800317a0`

## callees

- `0x1800159f0`
- `0x18003773a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015ab1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015ab1`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015a07`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015a07`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015a7b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015ac6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015a7b`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015ac6`

## pseudocode

```c
__int64 __fastcall CONTEXT_CONTAINER::InitializeStorage(CONTEXT_CONTAINER *this)
{
  unsigned int v2; // ecx
  char *v3; // rdx
  bool v4; // zf
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( *((_BYTE *)this + 52) )
    CReaderWriterLock3::WriteLock((CONTEXT_CONTAINER *)((char *)this + 24));
  if ( *((_BYTE *)this + 54) )
    goto LABEL_10;
  v2 = 16 * *((_DWORD *)g_pW3Server + 152);
  if ( *((_DWORD *)this + 10) < v2 )
  {
    v3 = (char *)LocalAlloc(0x40u, v2);
  }
  else
  {
    memset_0(*((void **)this + 4), 0, v2);
    v3 = (char *)*((_QWORD *)this + 4);
  }
  *((_QWORD *)this + 7) = v3;
  if ( v3 )
  {
    v4 = *((_BYTE *)this + 52) == 0;
    *((_QWORD *)this + 8) = &v3[8 * *((unsigned int *)g_pW3Server + 152)];
    if ( !v4 )
      _InterlockedOr(v6, 0);
    *((_BYTE *)this + 54) = 1;
LABEL_10:
    if ( *((_BYTE *)this + 52) )
      CReaderWriterLock3::WriteUnlock((CONTEXT_CONTAINER *)((char *)this + 24));
    return 0;
  }
  if ( *((_BYTE *)this + 52) )
    CReaderWriterLock3::WriteUnlock((CONTEXT_CONTAINER *)((char *)this + 24));
  return 2147942408LL;
}

```

## disassembly

```asm
0x1800159f0  mov     [rsp+arg_0], rbx
0x1800159f5  push    rdi
0x1800159f6  sub     rsp, 20h
0x1800159fa  cmp     byte ptr [rcx+34h], 0
0x1800159fe  mov     rbx, rcx
0x180015a01  jz      short loc_180015A13
0x180015a03  add     rcx, 18h
0x180015a07  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180015a0e  nop     dword ptr [rax+rax+00h]
0x180015a13  movzx   eax, byte ptr [rbx+36h]
0x180015a17  test    al, al
0x180015a19  jnz     short loc_180015A71
0x180015a1b  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180015a22  mov     ecx, [rax+260h]
0x180015a28  shl     ecx, 4
0x180015a2b  mov     edx, ecx; uBytes
0x180015a2d  cmp     [rbx+28h], ecx
0x180015a30  jb      short loc_180015AAC
0x180015a32  mov     rcx, [rbx+20h]; void *
0x180015a36  mov     r8d, edx; Size
0x180015a39  xor     edx, edx; Val
0x180015a3b  call    memset_0
0x180015a40  mov     rdx, [rbx+20h]
0x180015a44  mov     [rbx+38h], rdx
0x180015a48  test    rdx, rdx
0x180015a4b  jz      short loc_180015A95
0x180015a4d  cmp     byte ptr [rbx+34h], 0
0x180015a51  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180015a58  mov     ecx, [rax+260h]
0x180015a5e  lea     rax, [rdx+rcx*8]
0x180015a62  mov     [rbx+40h], rax
0x180015a66  jz      short loc_180015A6D
0x180015a68  lock or [rsp+28h+var_28], 0
0x180015a6d  mov     byte ptr [rbx+36h], 1
0x180015a71  cmp     byte ptr [rbx+34h], 0
0x180015a75  jz      short loc_180015A87
0x180015a77  lea     rcx, [rbx+18h]
0x180015a7b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180015a82  nop     dword ptr [rax+rax+00h]
0x180015a87  xor     eax, eax
0x180015a89  mov     rbx, [rsp+28h+arg_0]
0x180015a8e  add     rsp, 20h
0x180015a92  pop     rdi
0x180015a93  retn
0x180015a95  cmp     byte ptr [rbx+34h], 0
0x180015a99  jnz     short loc_180015AC2
0x180015a9b  mov     rbx, [rsp+28h+arg_0]
0x180015aa0  mov     eax, 80070008h
0x180015aa5  add     rsp, 20h
0x180015aa9  pop     rdi
0x180015aaa  retn
0x180015aac  mov     ecx, 40h ; '@'; uFlags
0x180015ab1  call    cs:__imp_LocalAlloc
0x180015ab8  nop     dword ptr [rax+rax+00h]
0x180015abd  mov     rdx, rax
0x180015ac0  jmp     short loc_180015A44
0x180015ac2  lea     rcx, [rbx+18h]
0x180015ac6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180015acd  nop     dword ptr [rax+rax+00h]
0x180015ad2  jmp     short loc_180015A9B
```
