# PoWdiPass1_FirmwareSleepCorruption

- ea: `0x180003f80`
- end: `0x18000400b`
- name: `PoWdiPass1_FirmwareSleepCorruption`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024e8`
- `0x180003f80`

## pseudocode

```c
__int64 __fastcall PoWdiPass1_FirmwareSleepCorruption(struct _EVENT_RECORD *a1, _DWORD *a2)
{
  __int64 result; // rax
  BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+50h] [rbp+18h] BYREF
  int v7; // [rsp+58h] [rbp+20h] BYREF

  v6 = 0;
  v7 = 0;
  *(_DWORD *)v5 = 0;
  result = PoWdiGetULongProperty(a1, (ULONGLONG)L"Count", (BYTE *)&v6);
  if ( (_DWORD)result )
  {
    result = PoWdiGetULongProperty(a1, (ULONGLONG)L"FirstPage", (BYTE *)&v7);
    if ( (_DWORD)result )
    {
      result = PoWdiGetULongProperty(a1, (ULONGLONG)L"LastPage", v5);
      if ( (_DWORD)result )
      {
        a2[14] = v6;
        a2[15] = v7;
        result = *(unsigned int *)v5;
        a2[16] = *(_DWORD *)v5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003f80  mov     rax, rsp
0x180003f83  mov     [rax+8], rbx
0x180003f87  push    rdi
0x180003f88  sub     rsp, 30h
0x180003f8c  mov     rbx, rdx
0x180003f8f  mov     dword ptr [rax+18h], 0
0x180003f96  lea     rdx, aCount; "Count"
0x180003f9d  mov     dword ptr [rax+20h], 0
0x180003fa4  lea     r8, [rax+18h]
0x180003fa8  mov     dword ptr [rax-18h], 0
0x180003faf  mov     rdi, rcx
0x180003fb2  call    PoWdiGetULongProperty
0x180003fb7  test    eax, eax
0x180003fb9  jz      short loc_180004000
0x180003fbb  lea     r8, [rsp+38h+arg_18]
0x180003fc0  mov     rcx, rdi
0x180003fc3  lea     rdx, aFirstpage; "FirstPage"
0x180003fca  call    PoWdiGetULongProperty
0x180003fcf  test    eax, eax
0x180003fd1  jz      short loc_180004000
0x180003fd3  lea     r8, [rsp+38h+var_18]
0x180003fd8  mov     rcx, rdi
0x180003fdb  lea     rdx, aLastpage; "LastPage"
0x180003fe2  call    PoWdiGetULongProperty
0x180003fe7  test    eax, eax
0x180003fe9  jz      short loc_180004000
0x180003feb  mov     eax, [rsp+38h+arg_10]
0x180003fef  mov     [rbx+38h], eax
0x180003ff2  mov     eax, [rsp+38h+arg_18]
0x180003ff6  mov     [rbx+3Ch], eax
0x180003ff9  mov     eax, dword ptr [rsp+38h+var_18]
0x180003ffd  mov     [rbx+40h], eax
0x180004000  mov     rbx, [rsp+38h+arg_0]
0x180004005  add     rsp, 30h
0x180004009  pop     rdi
0x18000400a  retn
```
