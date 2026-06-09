# CONTEXT_CONTAINER::InitializeStorage(void)

- ea: `0x180014900`
- end: `0x1800149ca`
- name: `?InitializeStorage@CONTEXT_CONTAINER@@AEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(CONTEXT_CONTAINER *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180014860`
- `0x18002eb90`

## callees

- `0x180014900`
- `0x18003439a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800149b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800149b3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180014917`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180014917`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180014985`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800149c2`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180014985`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800149c2`

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
0x180014900  mov     [rsp+arg_0], rbx
0x180014905  push    rdi
0x180014906  sub     rsp, 20h
0x18001490a  cmp     byte ptr [rcx+34h], 0
0x18001490e  mov     rbx, rcx
0x180014911  jz      short loc_18001491D
0x180014913  add     rcx, 18h
0x180014917  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001491d  movzx   eax, byte ptr [rbx+36h]
0x180014921  test    al, al
0x180014923  jnz     short loc_18001497B
0x180014925  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001492c  mov     ecx, [rax+260h]
0x180014932  shl     ecx, 4
0x180014935  mov     edx, ecx; uBytes
0x180014937  cmp     [rbx+28h], ecx
0x18001493a  jb      short loc_1800149AE
0x18001493c  mov     rcx, [rbx+20h]; void *
0x180014940  mov     r8d, edx; Size
0x180014943  xor     edx, edx; Val
0x180014945  call    memset_0
0x18001494a  mov     rdx, [rbx+20h]
0x18001494e  mov     [rbx+38h], rdx
0x180014952  test    rdx, rdx
0x180014955  jz      short loc_180014998
0x180014957  cmp     byte ptr [rbx+34h], 0
0x18001495b  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180014962  mov     ecx, [rax+260h]
0x180014968  lea     rax, [rdx+rcx*8]
0x18001496c  mov     [rbx+40h], rax
0x180014970  jz      short loc_180014977
0x180014972  lock or [rsp+28h+var_28], 0
0x180014977  mov     byte ptr [rbx+36h], 1
0x18001497b  cmp     byte ptr [rbx+34h], 0
0x18001497f  jz      short loc_18001498B
0x180014981  lea     rcx, [rbx+18h]
0x180014985  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001498b  xor     eax, eax
0x18001498d  mov     rbx, [rsp+28h+arg_0]
0x180014992  add     rsp, 20h
0x180014996  pop     rdi
0x180014997  retn
0x180014998  cmp     byte ptr [rbx+34h], 0
0x18001499c  jnz     short loc_1800149BE
0x18001499e  mov     rbx, [rsp+28h+arg_0]
0x1800149a3  mov     eax, 80070008h
0x1800149a8  add     rsp, 20h
0x1800149ac  pop     rdi
0x1800149ad  retn
0x1800149ae  mov     ecx, 40h ; '@'; uFlags
0x1800149b3  call    cs:__imp_LocalAlloc
0x1800149b9  mov     rdx, rax
0x1800149bc  jmp     short loc_18001494E
0x1800149be  lea     rcx, [rbx+18h]
0x1800149c2  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800149c8  jmp     short loc_18001499E
```
