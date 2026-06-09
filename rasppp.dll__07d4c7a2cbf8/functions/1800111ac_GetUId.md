# GetUId

- ea: `0x1800111ac`
- end: `0x1800111d1`
- name: `GetUId`
- size: `37`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001e00`
- `0x180003190`
- `0x18000d1b4`
- `0x18000d284`
- `0x18000da74`
- `0x18000db70`
- `0x18000dda4`
- `0x18000df18`

## callees

- `0x1800111ac`

## pseudocode

```c
char __fastcall GetUId(__int64 a1, unsigned int a2)
{
  __int64 v2; // rcx
  char result; // al

  if ( a2 && a2 >= (unsigned int)PppConfigInfo )
  {
    v2 = *(_QWORD *)(a1 + 8);
    result = *(_BYTE *)(v2 + 32);
    ++*(_DWORD *)(v2 + 32);
  }
  else
  {
    result = *(_BYTE *)(a1 + 32);
    *(_BYTE *)(a1 + 32) = result + 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800111ac  mov     r8, rcx
0x1800111af  test    edx, edx
0x1800111b1  jz      short loc_1800111C6
0x1800111b3  cmp     edx, dword ptr cs:PppConfigInfo
0x1800111b9  jb      short loc_1800111C6
0x1800111bb  mov     rcx, [rcx+8]
0x1800111bf  mov     al, [rcx+20h]
0x1800111c2  inc     dword ptr [rcx+20h]
0x1800111c5  retn
0x1800111c6  mov     al, [rcx+20h]
0x1800111c9  lea     ecx, [rax+1]
0x1800111cc  mov     [r8+20h], cl
0x1800111d0  retn
```
