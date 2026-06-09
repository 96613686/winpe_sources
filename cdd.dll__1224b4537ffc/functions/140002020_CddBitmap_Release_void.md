# CddBitmap::Release(void)

- ea: `0x140002020`
- end: `0x140002079`
- name: `?Release@CddBitmap@@UEAAXXZ`
- size: `89`
- prototype: `void __fastcall(CddBitmap *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015e0`
- `0x140032000`

## callees

- `0x140002020`
- `0x1400224a0`

## import_xrefs

- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x140002035`
- `WIN32K!EngIsSemaphoreOwnedByCurrentThread` at `0x140002035`
- `WIN32K!EngDeleteSemaphore` at `0x14000204c`
- `WIN32K!EngDeleteSemaphore` at `0x14000204c`

## pseudocode

```c
void __fastcall CddBitmap::Release(CddBitmap *this)
{
  HSEMAPHORE v2; // rcx

  v2 = (HSEMAPHORE)*((_QWORD *)this + 24);
  if ( v2 )
  {
    if ( EngIsSemaphoreOwnedByCurrentThread(v2) )
    {
      DbgLog("CddBitmap::Release m_hsemBmp is still owned!\n");
      __debugbreak();
    }
    EngDeleteSemaphore(*((HSEMAPHORE *)this + 24));
    *((_QWORD *)this + 24) = 0;
  }
}

```

## disassembly

```asm
0x140002020  push    rbx
0x140002022  sub     rsp, 20h
0x140002026  mov     rbx, rcx
0x140002029  mov     rcx, [rcx+0C0h]; hsem
0x140002030  test    rcx, rcx
0x140002033  jz      short loc_140002063
0x140002035  call    cs:__imp_EngIsSemaphoreOwnedByCurrentThread
0x14000203c  nop     dword ptr [rax+rax+00h]
0x140002041  test    eax, eax
0x140002043  jnz     short loc_14000206A
0x140002045  mov     rcx, [rbx+0C0h]; hsem
0x14000204c  call    cs:__imp_EngDeleteSemaphore
0x140002053  nop     dword ptr [rax+rax+00h]
0x140002058  mov     qword ptr [rbx+0C0h], 0
0x140002063  add     rsp, 20h
0x140002067  pop     rbx
0x140002068  retn
0x14000206a  lea     rcx, aCddbitmapRelea; "CddBitmap::Release m_hsemBmp is still o"...
0x140002071  call    ?DbgLog@@YAXPEBDZZ; DbgLog(char const *,...)
0x140002076  int     3; Trap to Debugger
```
