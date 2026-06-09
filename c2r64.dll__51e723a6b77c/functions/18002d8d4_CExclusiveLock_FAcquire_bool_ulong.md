# CExclusiveLock::FAcquire(bool,ulong)

- ea: `0x18002d8d4`
- end: `0x18002d912`
- name: `?FAcquire@CExclusiveLock@@QEAA_N_NK@Z`
- size: `62`
- prototype: `bool __fastcall(CExclusiveLock *__hidden this, bool, unsigned int)`
- caller_count: `56`
- callee_count: `1`
- tags: ``

## callers

- `0x180026664`
- `0x18002ce98`
- `0x18002d558`
- `0x1801076f8`
- `0x180107770`
- `0x180107800`
- `0x180107920`
- `0x18010cec0`
- `0x18010d110`
- `0x18010d33c`
- `0x18010d540`
- `0x18010d760`
- `0x18010dc1c`
- `0x18010def8`
- `0x18010df84`
- `0x18010e380`
- `0x18010e6ac`
- `0x180111c0c`
- `0x180113cb8`
- `0x180115410`
- `0x180115740`
- `0x18011655c`
- `0x180116a10`
- `0x18011712c`
- `0x1801187f0`
- `0x180118c10`
- `0x180118e80`
- `0x180119240`
- `0x1801196d0`
- `0x180119700`
- `0x180119970`
- `0x180119da0`
- `0x180119fc0`
- `0x18011a0f0`
- `0x18011a190`
- `0x18011a430`
- `0x18011a5d0`
- `0x18011a6b0`
- `0x18011a800`
- `0x18011a8d0`
- `0x18011b650`
- `0x18011bbb8`
- `0x18011cf60`
- `0x18011d310`
- `0x18011e480`
- `0x18011ee20`
- `0x18011f5a0`
- `0x180120080`
- `0x1801208d0`
- `0x180120b38`

## callees

- `0x18002d8d4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002d8e1`
- `KERNEL32!GetCurrentThreadId` at `0x18002d8e1`
- `KERNEL32!EnterCriticalSection` at `0x18002d8f6`
- `KERNEL32!EnterCriticalSection` at `0x18002d8f6`

## pseudocode

```c
char __fastcall CExclusiveLock::FAcquire(CExclusiveLock *this)
{
  DWORD CurrentThreadId; // edi

  CurrentThreadId = GetCurrentThreadId();
  if ( CurrentThreadId == *(_DWORD *)this )
  {
    ++*((_DWORD *)this + 1);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
    *(_DWORD *)this = CurrentThreadId;
    *((_DWORD *)this + 1) = 1;
  }
  return 1;
}

```

## disassembly

```asm
0x18002d8d4  mov     [rsp+arg_0], rbx
0x18002d8d9  push    rdi
0x18002d8da  sub     rsp, 20h
0x18002d8de  mov     rbx, rcx
0x18002d8e1  call    cs:__imp_GetCurrentThreadId
0x18002d8e7  mov     edi, eax
0x18002d8e9  cmp     eax, [rbx]
0x18002d8eb  jnz     short loc_18002D8F2
0x18002d8ed  inc     dword ptr [rbx+4]
0x18002d8f0  jmp     short loc_18002D905
0x18002d8f2  lea     rcx, [rbx+8]; lpCriticalSection
0x18002d8f6  call    cs:__imp_EnterCriticalSection
0x18002d8fc  mov     [rbx], edi
0x18002d8fe  mov     dword ptr [rbx+4], 1
0x18002d905  mov     rbx, [rsp+28h+arg_0]
0x18002d90a  mov     al, 1
0x18002d90c  add     rsp, 20h
0x18002d910  pop     rdi
0x18002d911  retn
```
