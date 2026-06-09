# CallSetupComplete

- ea: `0x14001070c`
- end: `0x14001077d`
- name: `CallSetupComplete`
- size: `113`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000f2ec`
- `0x1400109d0`
- `0x140011518`

## callees

- `0x14001070c`
- `0x140012078`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001073e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001073e`

## pseudocode

```c
__int64 __fastcall CallSetupComplete(__int64 a1)
{
  _QWORD *v2; // rdi

  if ( _InterlockedExchange64((volatile __int64 *)(a1 + 168), 0) )
  {
    v2 = (_QWORD *)(a1 + 192);
    if ( (*(_DWORD *)(a1 + 60) & 8) != 0 )
      ExFreePoolWithTag((PVOID)(*v2 - 16LL), 0);
    *(_QWORD *)(a1 + 176) = 0;
    *(_QWORD *)(a1 + 184) = 0;
    *v2 = 0;
  }
  return UnlockIcs(a1, 0);
}

```

## disassembly

```asm
0x14001070c  mov     [rsp+arg_0], rbx
0x140010711  push    rdi
0x140010712  sub     rsp, 20h
0x140010716  xor     eax, eax
0x140010718  mov     rbx, rcx
0x14001071b  xchg    rax, [rcx+0A8h]
0x140010722  test    rax, rax
0x140010725  jz      short loc_140010767
0x140010727  mov     eax, [rcx+3Ch]
0x14001072a  lea     rdi, [rcx+0C0h]
0x140010731  test    al, 8
0x140010733  jz      short loc_14001074A
0x140010735  mov     rcx, [rdi]
0x140010738  xor     edx, edx; Tag
0x14001073a  sub     rcx, 10h; P
0x14001073e  call    cs:__imp_ExFreePoolWithTag
0x140010745  nop     dword ptr [rax+rax+00h]
0x14001074a  mov     qword ptr [rbx+0B0h], 0
0x140010755  mov     qword ptr [rbx+0B8h], 0
0x140010760  mov     qword ptr [rdi], 0
0x140010767  xor     edx, edx
0x140010769  mov     rcx, rbx
0x14001076c  call    UnlockIcs
0x140010771  mov     rbx, [rsp+28h+arg_0]
0x140010776  add     rsp, 20h
0x14001077a  pop     rdi
0x14001077b  retn
```
