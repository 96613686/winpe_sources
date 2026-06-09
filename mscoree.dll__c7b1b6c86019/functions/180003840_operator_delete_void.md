# operator delete(void *)

- ea: `0x180003840`
- end: `0x180003887`
- name: `??3@YAXPEAX@Z`
- size: `71`
- prototype: `void __fastcall(void *)`
- caller_count: `90`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001e88`
- `0x180001ff0`
- `0x180002710`
- `0x180002a90`
- `0x180002da0`
- `0x180002f30`
- `0x180003070`
- `0x180003160`
- `0x180003890`
- `0x180003ed0`
- `0x180004230`
- `0x180004660`
- `0x180004fe0`
- `0x180005190`
- `0x180005250`
- `0x1800062c0`
- `0x180006df4`
- `0x180007300`
- `0x180007388`
- `0x180008710`
- `0x180008798`
- `0x1800087f8`
- `0x18000883c`
- `0x180008bcc`
- `0x180009350`
- `0x180009af4`
- `0x18000b348`
- `0x18000db60`
- `0x180010d30`
- `0x180019560`
- `0x180028d14`
- `0x180028d70`
- `0x180029528`
- `0x1800297ac`
- `0x18002a120`
- `0x18002a43c`
- `0x18002b5b8`
- `0x18002b888`
- `0x18002bc3c`
- `0x18002be40`
- `0x18002c358`
- `0x18002dfb4`
- `0x18002e23c`
- `0x18002e810`
- `0x180030140`
- `0x180030170`
- `0x1800309d8`
- `0x180030a1c`
- `0x180031950`
- `0x1800319e0`

## callees

- `0x180003840`
- `0x180003e00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000384d`
- `KERNEL32!GetLastError` at `0x180003873`
- `KERNEL32!GetLastError` at `0x18000384d`
- `KERNEL32!GetLastError` at `0x180003873`
- `KERNEL32!SetLastError` at `0x18000387f`
- `KERNEL32!SetLastError` at `0x18000387f`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  DWORD LastError; // edi

  LastError = GetLastError();
  if ( a1 )
    ClrFreeInProcessHeapBootstrap(0, a1);
  if ( LastError )
  {
    if ( !GetLastError() )
      SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x180003840  mov     [rsp+arg_0], rbx
0x180003845  push    rdi
0x180003846  sub     rsp, 20h
0x18000384a  mov     rbx, rcx
0x18000384d  call    cs:__imp_GetLastError
0x180003853  mov     edi, eax
0x180003855  test    rbx, rbx
0x180003858  jz      short loc_180003864
0x18000385a  mov     rdx, rbx; void *
0x18000385d  xor     ecx, ecx; unsigned int
0x18000385f  call    ?ClrFreeInProcessHeapBootstrap@@YAHKPEAX@Z; ClrFreeInProcessHeapBootstrap(ulong,void *)
0x180003864  test    edi, edi
0x180003866  jnz     short loc_180003873
0x180003868  mov     rbx, [rsp+28h+arg_0]
0x18000386d  add     rsp, 20h
0x180003871  pop     rdi
0x180003872  retn
0x180003873  call    cs:__imp_GetLastError
0x180003879  test    eax, eax
0x18000387b  jnz     short loc_180003868
0x18000387d  mov     ecx, edi; dwErrCode
0x18000387f  call    cs:__imp_SetLastError
0x180003885  jmp     short loc_180003868
```
