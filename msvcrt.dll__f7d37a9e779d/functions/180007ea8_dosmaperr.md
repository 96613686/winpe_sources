# _dosmaperr

- ea: `0x180007ea8`
- end: `0x180007ef6`
- name: `_dosmaperr`
- size: `78`
- prototype: ``
- caller_count: `41`
- callee_count: `3`
- tags: ``

## callers

- `0x1800080a0`
- `0x180008140`
- `0x180008290`
- `0x180008410`
- `0x1800084a0`
- `0x1800087f0`
- `0x180008830`
- `0x180008960`
- `0x180008e30`
- `0x180008e90`
- `0x180008f30`
- `0x180009080`
- `0x180009110`
- `0x180009450`
- `0x180009490`
- `0x1800094e0`
- `0x180009650`
- `0x180009b10`
- `0x180009f60`
- `0x18000a0d8`
- `0x18000a768`
- `0x180018730`
- `0x18001bba4`
- `0x18001c4a0`
- `0x18001dd50`
- `0x18001e308`
- `0x18001e7fc`
- `0x18001eb5c`
- `0x18001f5c0`
- `0x1800200c0`
- `0x180020684`
- `0x180020854`
- `0x1800209f8`
- `0x180020ee8`
- `0x1800216f0`
- `0x180021c08`
- `0x1800227c0`
- `0x180023314`
- `0x180023b50`
- `0x18003e2a0`
- `0x18003e4b0`

## callees

- `0x180007ea8`
- `0x180007fd0`
- `0x18003e074`

## pseudocode

```c
__int64 __fastcall dosmaperr(unsigned int a1)
{
  _QWORD *v2; // rax
  int *v3; // rax
  _QWORD *v4; // rax
  char *v5; // rbx
  __int64 result; // rax

  v2 = getptd_noexit();
  if ( v2 )
    v3 = (int *)v2 + 5;
  else
    v3 = &dword_18009D284;
  *v3 = a1;
  v4 = getptd_noexit();
  v5 = byte_18009D280;
  if ( v4 )
    v5 = (char *)(v4 + 2);
  result = get_errno_from_oserr(a1);
  *(_DWORD *)v5 = result;
  return result;
}

```

## disassembly

```asm
0x180007ea8  mov     [rsp+arg_0], rbx
0x180007ead  push    rdi
0x180007eae  sub     rsp, 20h
0x180007eb2  mov     edi, ecx
0x180007eb4  call    _getptd_noexit
0x180007eb9  test    rax, rax
0x180007ebc  jnz     short loc_180007EC7
0x180007ebe  lea     rax, dword_18009D284
0x180007ec5  jmp     short loc_180007ECB
0x180007ec7  add     rax, 14h
0x180007ecb  mov     [rax], edi
0x180007ecd  call    _getptd_noexit
0x180007ed2  lea     rbx, byte_18009D280
0x180007ed9  test    rax, rax
0x180007edc  jz      short loc_180007EE2
0x180007ede  lea     rbx, [rax+10h]
0x180007ee2  mov     ecx, edi
0x180007ee4  call    _get_errno_from_oserr
0x180007ee9  mov     [rbx], eax
0x180007eeb  mov     rbx, [rsp+28h+arg_0]
0x180007ef0  add     rsp, 20h
0x180007ef4  pop     rdi
0x180007ef5  retn
```
