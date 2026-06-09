# HidpIdleNotificationRequestComplete

- ea: `0x18000fd60`
- end: `0x18000fd98`
- name: `HidpIdleNotificationRequestComplete`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000fd60`
- `0x180010814`

## pseudocode

```c
__int64 __fastcall HidpIdleNotificationRequestComplete(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = *(_DWORD *)(a2 + 48);
  if ( v3 == -1073741536 )
  {
    v4 = 2034;
  }
  else
  {
    v4 = 2042;
    if ( v3 != -1073741101 )
      v4 = 2014;
  }
  HIDSM_AddHidsmEvent(a3, v4);
  return 3221225494LL;
}

```

## disassembly

```asm
0x18000fd60  sub     rsp, 28h
0x18000fd64  mov     eax, [rdx+30h]
0x18000fd67  cmp     eax, 0C0000120h
0x18000fd6c  jnz     short loc_18000FD86
0x18000fd6e  mov     edx, 7F2h
0x18000fd73  mov     rcx, r8
0x18000fd76  call    HIDSM_AddHidsmEvent
0x18000fd7b  mov     eax, 0C0000016h
0x18000fd80  add     rsp, 28h
0x18000fd84  retn
0x18000fd86  mov     edx, 7FAh
0x18000fd8b  cmp     eax, 0C00002D3h
0x18000fd90  lea     ecx, [rdx-1Ch]
0x18000fd93  cmovnz  edx, ecx
0x18000fd96  jmp     short loc_18000FD73
```
