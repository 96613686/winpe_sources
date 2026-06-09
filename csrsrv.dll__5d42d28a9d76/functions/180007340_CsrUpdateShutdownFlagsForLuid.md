# CsrUpdateShutdownFlagsForLuid

- ea: `0x180007340`
- end: `0x180007380`
- name: `CsrUpdateShutdownFlagsForLuid`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x180006ea0`
- `0x1800072c0`
- `0x180008420`

## callees

- `0x180007340`

## pseudocode

```c
__int64 __fastcall CsrUpdateShutdownFlagsForLuid(_DWORD *a1, _DWORD *a2)
{
  __int64 result; // rax

  result = (unsigned int)ServiceSessionId;
  if ( g_SessionId == ServiceSessionId )
  {
    result = (unsigned int)a1[32];
    if ( *((_QWORD *)a1 + 16) == 999 )
    {
      a1[31] |= 4u;
    }
    else if ( (_DWORD)result != *a2 || (result = (unsigned int)a2[1], a1[33] != (_DWORD)result) )
    {
      a1[31] |= 8u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007340  mov     eax, cs:ServiceSessionId
0x180007346  cmp     cs:g_SessionId, eax
0x18000734c  jz      short loc_180007350
0x18000734e  retn
0x180007350  mov     eax, [rcx+80h]
0x180007356  cmp     eax, 3E7h
0x18000735b  jnz     short loc_18000736C
0x18000735d  cmp     dword ptr [rcx+84h], 0
0x180007364  jnz     short loc_18000736C
0x180007366  or      dword ptr [rcx+7Ch], 4
0x18000736a  retn
0x18000736c  cmp     eax, [rdx]
0x18000736e  jnz     short loc_18000737B
0x180007370  mov     eax, [rdx+4]
0x180007373  cmp     [rcx+84h], eax
0x180007379  jz      short locret_18000734E
0x18000737b  or      dword ptr [rcx+7Ch], 8
0x18000737f  retn
```
