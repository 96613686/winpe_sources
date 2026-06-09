# SQLGetConfigMode

- ea: `0x180008d50`
- end: `0x180008db4`
- name: `SQLGetConfigMode`
- size: `100`
- prototype: `BOOL __stdcall(UWORD *pwConfigMode)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180001740`
- `0x180008d50`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180008da1`
- `KERNEL32!LeaveCriticalSection` at `0x180008da1`
- `KERNEL32!EnterCriticalSection` at `0x180008d64`
- `KERNEL32!EnterCriticalSection` at `0x180008d64`

## pseudocode

```c
BOOL __stdcall SQLGetConfigMode(UWORD *pwConfigMode)
{
  UWORD v2; // ax

  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  if ( pwConfigMode )
  {
    if ( (g_wSystemDSN & 4) != 0 )
    {
      v2 = 0;
    }
    else
    {
      v2 = 1;
      if ( (g_wSystemDSN & 2) == 0 )
        v2 = 2;
    }
    *pwConfigMode = v2;
  }
  LeaveCriticalSection(&g_csInstaller);
  return 1;
}

```

## disassembly

```asm
0x180008d50  mov     [rsp+arg_0], rbx
0x180008d55  push    rdi
0x180008d56  sub     rsp, 20h
0x180008d5a  mov     rbx, rcx
0x180008d5d  lea     rcx, g_csInstaller; lpCriticalSection
0x180008d64  call    cs:__imp_EnterCriticalSection
0x180008d6a  call    FreeErrorQueue
0x180008d6f  mov     edi, 1
0x180008d74  test    rbx, rbx
0x180008d77  jz      short loc_180008D9A
0x180008d79  movzx   eax, cs:g_wSystemDSN
0x180008d80  test    al, 4
0x180008d82  jz      short loc_180008D88
0x180008d84  xor     eax, eax
0x180008d86  jmp     short loc_180008D97
0x180008d88  mov     ecx, 2
0x180008d8d  test    cl, al
0x180008d8f  movzx   eax, di
0x180008d92  jnz     short loc_180008D97
0x180008d94  movzx   eax, cx
0x180008d97  mov     [rbx], ax
0x180008d9a  lea     rcx, g_csInstaller; lpCriticalSection
0x180008da1  call    cs:__imp_LeaveCriticalSection
0x180008da7  mov     rbx, [rsp+28h+arg_0]
0x180008dac  mov     eax, edi
0x180008dae  add     rsp, 20h
0x180008db2  pop     rdi
0x180008db3  retn
```
