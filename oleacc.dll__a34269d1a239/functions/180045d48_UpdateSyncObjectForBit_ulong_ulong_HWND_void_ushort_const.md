# UpdateSyncObjectForBit(ulong,ulong,HWND__ *,void * *,ushort const *)

- ea: `0x180045d48`
- end: `0x180045db5`
- name: `?UpdateSyncObjectForBit@@YAXKKPEAUHWND__@@PEAPEAXPEBG@Z`
- size: `109`
- prototype: `void(unsigned int, unsigned int, HWND, void **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180045f04`

## callees

- `0x180045d48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180045d6d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180045d6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045d86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045d86`
- `USER32!NotifyWinEvent` at `0x180045da6`
- `USER32!NotifyWinEvent` at `0x180045da6`

## pseudocode

```c
void __fastcall UpdateSyncObjectForBit(int a1, int a2, HWND a3, void **a4, const unsigned __int16 *lpName)
{
  HANDLE MutexW; // rbx
  unsigned __int16 v8; // si
  int v9; // r8d

  MutexW = 0;
  v8 = a2;
  if ( (a1 & a2) != 0 )
  {
    if ( *a4 )
      return;
    MutexW = CreateMutexW(0, 0, lpName);
    v9 = 1;
  }
  else
  {
    if ( !*a4 )
      return;
    CloseHandle(*a4);
    v9 = 0;
  }
  *a4 = MutexW;
  NotifyWinEvent(0x23u, a3, v8 | (v9 << 16), 0);
}

```

## disassembly

```asm
0x180045d48  push    rbx
0x180045d4a  push    rbp
0x180045d4b  push    rsi
0x180045d4c  push    rdi
0x180045d4d  sub     rsp, 28h
0x180045d51  xor     ebx, ebx
0x180045d53  mov     rdi, r9
0x180045d56  mov     rbp, r8
0x180045d59  mov     esi, edx
0x180045d5b  test    edx, ecx
0x180045d5d  jz      short loc_180045D7E
0x180045d5f  cmp     [r9], rbx
0x180045d62  jnz     short loc_180045DAC
0x180045d64  mov     r8, [rsp+48h+lpName]; lpName
0x180045d69  xor     edx, edx; bInitialOwner
0x180045d6b  xor     ecx, ecx; lpMutexAttributes
0x180045d6d  call    cs:__imp_CreateMutexW
0x180045d73  mov     rbx, rax
0x180045d76  mov     r8d, 1
0x180045d7c  jmp     short loc_180045D8F
0x180045d7e  cmp     [r9], rbx
0x180045d81  jz      short loc_180045DAC
0x180045d83  mov     rcx, [r9]; hObject
0x180045d86  call    cs:__imp_CloseHandle
0x180045d8c  mov     r8d, ebx
0x180045d8f  xor     r9d, r9d; idChild
0x180045d92  shl     r8d, 10h
0x180045d96  movzx   eax, si
0x180045d99  mov     rdx, rbp; hwnd
0x180045d9c  or      r8d, eax; idObject
0x180045d9f  mov     [rdi], rbx
0x180045da2  lea     ecx, [r9+23h]; event
0x180045da6  call    cs:__imp_NotifyWinEvent
0x180045dac  add     rsp, 28h
0x180045db0  pop     rdi
0x180045db1  pop     rsi
0x180045db2  pop     rbp
0x180045db3  pop     rbx
0x180045db4  retn
```
