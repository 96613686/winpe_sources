# FveBcdUtil::GetCurrentOsGuid(void *,_GUID *)

- ea: `0x180012b74`
- end: `0x180012be2`
- name: `?GetCurrentOsGuid@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800126b8`

## callees

- `0x18000ff64`
- `0x180012b74`

## import_xrefs

- `bcd!BcdQueryObject` at `0x180012bb6`
- `bcd!BcdQueryObject` at `0x180012bb6`
- `bcd!BcdOpenObject` at `0x180012b96`
- `bcd!BcdOpenObject` at `0x180012b96`
- `bcd!BcdCloseObject` at `0x180012bcf`
- `bcd!BcdCloseObject` at `0x18002c8c4`
- `bcd!BcdCloseObject` at `0x180012bcf`
- `bcd!BcdCloseObject` at `0x18002c8c4`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetCurrentOsGuid(void *a1, struct _GUID *a2)
{
  NTSTATUS v3; // eax
  signed int v4; // ebx
  NTSTATUS Object; // eax
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v3 = BcdOpenObject(a1, &GUID_CURRENT_BOOT_ENTRY, &v7);
  v4 = FromNtStatus(v3);
  if ( v4 >= 0 )
  {
    Object = BcdQueryObject(v7, 0, 0, a2);
    v4 = FromNtStatus(Object);
  }
  if ( v7 )
    BcdCloseObject(v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012b74  mov     [rsp+arg_0], rbx
0x180012b79  push    rdi
0x180012b7a  sub     rsp, 20h
0x180012b7e  mov     rdi, rdx
0x180012b81  mov     [rsp+28h+arg_10], 0
0x180012b8a  lea     r8, [rsp+28h+arg_10]
0x180012b8f  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x180012b96  call    cs:__imp_BcdOpenObject
0x180012b9c  mov     ecx, eax; int
0x180012b9e  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012ba3  mov     ebx, eax
0x180012ba5  test    eax, eax
0x180012ba7  js      short loc_180012BC5
0x180012ba9  mov     r9, rdi
0x180012bac  xor     r8d, r8d
0x180012baf  xor     edx, edx
0x180012bb1  mov     rcx, [rsp+28h+arg_10]
0x180012bb6  call    cs:__imp_BcdQueryObject
0x180012bbc  mov     ecx, eax; int
0x180012bbe  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180012bc3  mov     ebx, eax
0x180012bc5  mov     rcx, [rsp+28h+arg_10]
0x180012bca  test    rcx, rcx
0x180012bcd  jz      short loc_180012BD5
0x180012bcf  call    cs:__imp_BcdCloseObject
0x180012bd5  mov     eax, ebx
0x180012bd7  mov     rbx, [rsp+28h+arg_0]
0x180012bdc  add     rsp, 20h
0x180012be0  pop     rdi
0x180012be1  retn
0x18002c8b2  push    rbp
0x18002c8b4  sub     rsp, 20h
0x18002c8b8  mov     rbp, rdx
0x18002c8bb  mov     rcx, [rbp+40h]
0x18002c8bf  test    rcx, rcx
0x18002c8c2  jz      short loc_18002C8CB
0x18002c8c4  call    cs:__imp_BcdCloseObject
0x18002c8ca  nop
0x18002c8cb  add     rsp, 20h
0x18002c8cf  pop     rbp
0x18002c8d0  retn
```
