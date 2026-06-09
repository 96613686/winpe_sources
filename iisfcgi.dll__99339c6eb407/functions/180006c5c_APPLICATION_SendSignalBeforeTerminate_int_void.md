# APPLICATION::SendSignalBeforeTerminate(int,void * *)

- ea: `0x180006c5c`
- end: `0x180006ce0`
- name: `?SendSignalBeforeTerminate@APPLICATION@@QEAAXHPEAPEAX@Z`
- size: `132`
- prototype: `void __fastcall(APPLICATION *__hidden this, int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006480`
- `0x180008164`

## callees

- `0x180006c5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006cc5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006cc5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006ca0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006ca0`

## pseudocode

```c
void __fastcall APPLICATION::SendSignalBeforeTerminate(APPLICATION *this, __int64 a2, void **a3)
{
  void *v5; // rcx
  void *v6; // rcx

  if ( a3 )
    *a3 = (void *)-1LL;
  if ( *((_DWORD *)this + 76) )
  {
    v5 = (void *)*((_QWORD *)this + 30);
    if ( v5 )
    {
      if ( *((_QWORD *)this + 29) && *((_DWORD *)this + 62) != 1 )
      {
        if ( SetEvent(v5) )
        {
          v6 = (void *)*((_QWORD *)this + 29);
          if ( a3 )
            *a3 = v6;
          else
            WaitForSingleObject(v6, 1000 * *((_DWORD *)this + 76));
        }
        *((_DWORD *)this + 62) = 1;
      }
    }
  }
}

```

## disassembly

```asm
0x180006c5c  mov     [rsp+arg_0], rbx
0x180006c61  push    rdi
0x180006c62  sub     rsp, 20h
0x180006c66  mov     rdi, r8
0x180006c69  mov     rbx, rcx
0x180006c6c  test    r8, r8
0x180006c6f  jz      short loc_180006C78
0x180006c71  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180006c78  cmp     dword ptr [rcx+130h], 0
0x180006c7f  jz      short loc_180006CD5
0x180006c81  mov     rcx, [rcx+0F0h]; hEvent
0x180006c88  test    rcx, rcx
0x180006c8b  jz      short loc_180006CD5
0x180006c8d  cmp     qword ptr [rbx+0E8h], 0
0x180006c95  jz      short loc_180006CD5
0x180006c97  cmp     dword ptr [rbx+0F8h], 1
0x180006c9e  jz      short loc_180006CD5
0x180006ca0  call    cs:__imp_SetEvent
0x180006ca6  test    eax, eax
0x180006ca8  jz      short loc_180006CCB
0x180006caa  mov     rcx, [rbx+0E8h]; hHandle
0x180006cb1  test    rdi, rdi
0x180006cb4  jz      short loc_180006CBB
0x180006cb6  mov     [rdi], rcx
0x180006cb9  jmp     short loc_180006CCB
0x180006cbb  imul    edx, [rbx+130h], 3E8h; dwMilliseconds
0x180006cc5  call    cs:__imp_WaitForSingleObject
0x180006ccb  mov     dword ptr [rbx+0F8h], 1
0x180006cd5  mov     rbx, [rsp+28h+arg_0]
0x180006cda  add     rsp, 20h
0x180006cde  pop     rdi
0x180006cdf  retn
```
