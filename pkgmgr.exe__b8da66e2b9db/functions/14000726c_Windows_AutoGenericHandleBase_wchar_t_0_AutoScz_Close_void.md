# Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)

- ea: `0x14000726c`
- end: `0x14000728f`
- name: `?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x140007040`
- `0x140007524`
- `0x1400089c0`
- `0x140008de8`
- `0x14000903c`
- `0x14000a1dc`
- `0x14000aca8`
- `0x14000b454`
- `0x14000bf34`
- `0x14000c384`
- `0x14000ccac`
- `0x14000d410`
- `0x14000d9d0`
- `0x140010d34`
- `0x140011100`
- `0x14001154c`
- `0x140011a4c`
- `0x140012b88`
- `0x140013200`
- `0x140013288`
- `0x140015a08`
- `0x140016328`
- `0x1400170c0`
- `0x140017568`

## callees

- `0x14000726c`
- `0x140007298`

## pseudocode

```c
__int64 __fastcall Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
  {
    result = anonymous_namespace_::CloseWithSczFree();
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000726c  push    rbx
0x14000726e  sub     rsp, 20h
0x140007272  mov     rbx, rcx
0x140007275  mov     rcx, [rcx]
0x140007278  test    rcx, rcx
0x14000727b  jz      short loc_140007289
0x14000727d  call    _anonymous_namespace___CloseWithSczFree
0x140007282  mov     qword ptr [rbx], 0
0x140007289  add     rsp, 20h
0x14000728d  pop     rbx
0x14000728e  retn
```
