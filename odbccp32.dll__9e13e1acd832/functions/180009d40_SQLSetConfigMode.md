# SQLSetConfigMode

- ea: `0x180009d40`
- end: `0x180009db7`
- name: `SQLSetConfigMode`
- size: `119`
- prototype: `BOOL __stdcall(UWORD wConfigMode)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x180001740`
- `0x180004bac`
- `0x180009d40`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009da4`
- `KERNEL32!LeaveCriticalSection` at `0x180009da4`
- `KERNEL32!EnterCriticalSection` at `0x180009d59`
- `KERNEL32!EnterCriticalSection` at `0x180009d59`

## pseudocode

```c
BOOL __stdcall SQLSetConfigMode(UWORD wConfigMode)
{
  BOOL v2; // ebx
  __int16 v3; // ax

  v2 = 1;
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  if ( !wConfigMode )
  {
    v3 = 4;
LABEL_4:
    g_wSystemDSN = v3;
    goto LABEL_8;
  }
  v3 = 2;
  if ( wConfigMode == 1 )
    goto LABEL_4;
  if ( wConfigMode == 2 )
  {
    g_wSystemDSN = 1;
  }
  else
  {
    v2 = 0;
    PostInstError(14);
  }
LABEL_8:
  LeaveCriticalSection(&g_csInstaller);
  return v2;
}

```

## disassembly

```asm
0x180009d40  mov     [rsp+arg_0], rbx
0x180009d45  push    rdi
0x180009d46  sub     rsp, 20h
0x180009d4a  movzx   edi, cx
0x180009d4d  mov     ebx, 1
0x180009d52  lea     rcx, g_csInstaller; lpCriticalSection
0x180009d59  call    cs:__imp_EnterCriticalSection
0x180009d5f  call    FreeErrorQueue
0x180009d64  xor     ecx, ecx
0x180009d66  test    di, di
0x180009d69  jnz     short loc_180009D70
0x180009d6b  lea     eax, [rbx+3]
0x180009d6e  jmp     short loc_180009D7A
0x180009d70  mov     eax, 2
0x180009d75  cmp     di, bx
0x180009d78  jnz     short loc_180009D83
0x180009d7a  mov     cs:g_wSystemDSN, ax
0x180009d81  jmp     short loc_180009D9D
0x180009d83  cmp     di, ax
0x180009d86  jnz     short loc_180009D91
0x180009d88  mov     cs:g_wSystemDSN, bx
0x180009d8f  jmp     short loc_180009D9D
0x180009d91  mov     ebx, ecx
0x180009d93  mov     ecx, 0Eh
0x180009d98  call    PostInstError
0x180009d9d  lea     rcx, g_csInstaller; lpCriticalSection
0x180009da4  call    cs:__imp_LeaveCriticalSection
0x180009daa  mov     eax, ebx
0x180009dac  mov     rbx, [rsp+28h+arg_0]
0x180009db1  add     rsp, 20h
0x180009db5  pop     rdi
0x180009db6  retn
```
