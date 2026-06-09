# CDDSURFLOCK::vDone(void)

- ea: `0x140033db0`
- end: `0x140033e58`
- name: `?vDone@CDDSURFLOCK@@QEAAXXZ`
- size: `168`
- prototype: `void __fastcall(CDDSURFLOCK *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`

## callees

- `0x140008fa4`
- `0x1400224a0`
- `0x140033db0`

## import_xrefs

- `WIN32K!EngReleaseSemaphore` at `0x140033de3`
- `WIN32K!EngReleaseSemaphore` at `0x140033e24`
- `WIN32K!EngReleaseSemaphore` at `0x140033de3`
- `WIN32K!EngReleaseSemaphore` at `0x140033e24`

## string_xrefs

- `0x140033dcb`: `vUnLockBmpAndRemovePunt: cddBmp == NULL\n`

## pseudocode

```c
void __fastcall CDDSURFLOCK::vDone(CDDSURFLOCK *this)
{
  int i; // esi
  __int64 v3; // rdi
  __int64 v4; // r14
  __int64 v5; // rbp

  if ( *(_QWORD *)this )
  {
    if ( !*((_QWORD *)this + 1) )
    {
      DbgLog("vUnLockBmpAndRemovePunt: cddBmp == NULL\n");
      __debugbreak();
    }
    EngReleaseSemaphore(*(HSEMAPHORE *)(*((_QWORD *)this + 1) + 192LL));
    *(_QWORD *)this = 0;
  }
  if ( *((_QWORD *)this + 2) )
  {
    for ( i = 8; i >= 0; --i )
    {
      v3 = 8;
      v4 = 9LL * (unsigned int)i;
      do
      {
        v5 = v4 + v3;
        if ( *((_BYTE *)this + v4 + v3 + 24) == 1 )
        {
          EngReleaseSemaphore(*(HSEMAPHORE *)(*((_QWORD *)this + 2) + 8 * v5 + 2928));
          *((_BYTE *)this + v5 + 24) = 0;
        }
        --v3;
      }
      while ( v3 != -1 );
    }
    ShadowUnLock(*((struct CDDPDEV **)this + 2));
  }
}

```

## disassembly

```asm
0x140033db0  push    rbx
0x140033db2  push    rbp
0x140033db3  push    rsi
0x140033db4  push    rdi
0x140033db5  push    r14
0x140033db7  sub     rsp, 20h
0x140033dbb  cmp     qword ptr [rcx], 0
0x140033dbf  mov     rbx, rcx
0x140033dc2  jz      short loc_140033DF6
0x140033dc4  cmp     qword ptr [rcx+8], 0
0x140033dc9  jnz     short loc_140033DD8
0x140033dcb  lea     rcx, aVunlockbmpandr; "vUnLockBmpAndRemovePunt: cddBmp == NULL"...
0x140033dd2  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140033dd7  int     3; Trap to Debugger
0x140033dd8  mov     rcx, [rbx+8]
0x140033ddc  mov     rcx, [rcx+0C0h]; hsem
0x140033de3  call    cs:__imp_EngReleaseSemaphore
0x140033dea  nop     dword ptr [rax+rax+00h]
0x140033def  mov     qword ptr [rbx], 0
0x140033df6  cmp     qword ptr [rbx+10h], 0
0x140033dfb  jz      short loc_140033E4C
0x140033dfd  mov     esi, 8
0x140033e02  mov     eax, esi
0x140033e04  mov     edi, 8
0x140033e09  lea     r14, [rax+rax*8]
0x140033e0d  lea     rbp, [r14+rdi]
0x140033e11  cmp     byte ptr [rbx+rbp+18h], 1
0x140033e16  jnz     short loc_140033E35
0x140033e18  mov     rcx, [rbx+10h]
0x140033e1c  mov     rcx, [rcx+rbp*8+0B70h]; hsem
0x140033e24  call    cs:__imp_EngReleaseSemaphore
0x140033e2b  nop     dword ptr [rax+rax+00h]
0x140033e30  mov     byte ptr [rbx+rbp+18h], 0
0x140033e35  dec     rdi
0x140033e38  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140033e3c  jnz     short loc_140033E0D
0x140033e3e  sub     esi, 1
0x140033e41  jns     short loc_140033E02
0x140033e43  mov     rcx, [rbx+10h]; struct CDDPDEV *
0x140033e47  call    ?ShadowUnLock@@YAXPEAUCDDPDEV@@@Z; ShadowUnLock(CDDPDEV *)
0x140033e4c  add     rsp, 20h
0x140033e50  pop     r14
0x140033e52  pop     rdi
0x140033e53  pop     rsi
0x140033e54  pop     rbp
0x140033e55  pop     rbx
0x140033e56  retn
```
