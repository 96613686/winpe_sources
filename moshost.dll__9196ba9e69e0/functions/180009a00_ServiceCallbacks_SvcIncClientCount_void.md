# ServiceCallbacks::SvcIncClientCount(void)

- ea: `0x180009a00`
- end: `0x180009a7a`
- name: `?SvcIncClientCount@ServiceCallbacks@@UEAAHXZ`
- size: `122`
- prototype: `__int64 __fastcall(ServiceCallbacks *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009a00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a68`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009a68`

## pseudocode

```c
__int64 __fastcall ServiceCallbacks::SvcIncClientCount(ServiceCallbacks *this)
{
  unsigned int v1; // ebx
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  if ( pti )
  {
    v1 = 1;
    while ( 1 )
    {
      pftDueTime.dwLowDateTime = dword_1800185D8;
      if ( dword_1800185D8 == -2 || pftDueTime.dwLowDateTime == -1 )
        break;
      if ( _InterlockedCompareExchange(&dword_1800185D8, pftDueTime.dwLowDateTime + 1, pftDueTime.dwLowDateTime) == pftDueTime.dwLowDateTime )
      {
        pftDueTime = 0;
        SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
        return v1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009a00  push    rbx
0x180009a02  sub     rsp, 20h
0x180009a06  cmp     cs:pti, 0
0x180009a0e  jz      short loc_180009A70
0x180009a10  mov     ebx, 1
0x180009a15  mov     eax, cs:dword_1800185D8
0x180009a1b  mov     [rsp+28h+pftDueTime.dwLowDateTime], eax
0x180009a1f  mov     eax, [rsp+28h+pftDueTime.dwLowDateTime]
0x180009a23  cmp     eax, 0FFFFFFFEh
0x180009a26  jz      short loc_180009A70
0x180009a28  mov     eax, [rsp+28h+pftDueTime.dwLowDateTime]
0x180009a2c  cmp     eax, 0FFFFFFFFh
0x180009a2f  jz      short loc_180009A70
0x180009a31  mov     eax, [rsp+28h+pftDueTime.dwLowDateTime]
0x180009a35  mov     ecx, [rsp+28h+pftDueTime.dwLowDateTime]
0x180009a39  add     ecx, ebx
0x180009a3b  lock cmpxchg cs:dword_1800185D8, ecx
0x180009a43  mov     ecx, eax
0x180009a45  mov     eax, [rsp+28h+pftDueTime.dwLowDateTime]
0x180009a49  cmp     ecx, eax
0x180009a4b  jnz     short loc_180009A15
0x180009a4d  mov     rcx, cs:pti; pti
0x180009a54  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180009a59  xor     r9d, r9d; msWindowLength
0x180009a5c  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0
0x180009a65  xor     r8d, r8d; msPeriod
0x180009a68  call    cs:__imp_SetThreadpoolTimer
0x180009a6e  jmp     short loc_180009A72
0x180009a70  xor     ebx, ebx
0x180009a72  mov     eax, ebx
0x180009a74  add     rsp, 20h
0x180009a78  pop     rbx
0x180009a79  retn
```
