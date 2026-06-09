# Dhcpv6FreeCachedParamsDataEx

- ea: `0x180004c40`
- end: `0x180004caf`
- name: `Dhcpv6FreeCachedParamsDataEx`
- size: `111`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005b30`
- `0x180005ec0`

## callees

- `0x180002650`
- `0x180004c40`

## pseudocode

```c
HLOCAL __fastcall Dhcpv6FreeCachedParamsDataEx(void **a1)
{
  void **v2; // rsi
  unsigned int i; // ebp
  __int64 v4; // rbx
  HLOCAL result; // rax
  void **v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = a1;
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport && a1 )
  {
    v2 = a1 + 1;
    if ( a1[1] )
    {
      for ( i = 0; i < *(_DWORD *)a1; *(_DWORD *)((char *)*v2 + v4 + 24) = 0 )
      {
        v4 = 32LL * i;
        DhcpMidlUserFree((void **)((char *)*v2 + v4 + 16));
        ++i;
      }
    }
    DhcpMidlUserFree(v2);
    return DhcpMidlUserFree((void **)&v6);
  }
  return result;
}

```

## disassembly

```asm
0x180004c40  mov     [rsp+arg_0], rcx
0x180004c45  push    rbx
0x180004c46  push    rbp
0x180004c47  push    rsi
0x180004c48  push    rdi
0x180004c49  sub     rsp, 28h
0x180004c4d  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, 0
0x180004c54  mov     rdi, rcx
0x180004c57  jz      short loc_180004CA6
0x180004c59  test    rcx, rcx
0x180004c5c  jz      short loc_180004CA6
0x180004c5e  lea     rsi, [rcx+8]
0x180004c62  cmp     qword ptr [rsi], 0
0x180004c66  jz      short loc_180004C94
0x180004c68  xor     ebp, ebp
0x180004c6a  cmp     [rcx], ebp
0x180004c6c  jbe     short loc_180004C94
0x180004c6e  mov     rcx, [rsi]
0x180004c71  add     rcx, 10h
0x180004c75  mov     ebx, ebp
0x180004c77  shl     rbx, 5
0x180004c7b  add     rcx, rbx
0x180004c7e  call    DhcpMidlUserFree
0x180004c83  mov     rax, [rsi]
0x180004c86  inc     ebp
0x180004c88  mov     dword ptr [rax+rbx+18h], 0
0x180004c90  cmp     ebp, [rdi]
0x180004c92  jb      short loc_180004C6E
0x180004c94  mov     rcx, rsi
0x180004c97  call    DhcpMidlUserFree
0x180004c9c  lea     rcx, [rsp+48h+arg_0]
0x180004ca1  call    DhcpMidlUserFree
0x180004ca6  add     rsp, 28h
0x180004caa  pop     rdi
0x180004cab  pop     rsi
0x180004cac  pop     rbp
0x180004cad  pop     rbx
0x180004cae  retn
```
