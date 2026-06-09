# FveBcdUtil::GetCurrentOsGuid(void *,_GUID *)

- ea: `0x1800dad64`
- end: `0x1800dade5`
- name: `?GetCurrentOsGuid@FveBcdUtil@@SAJPEAXPEAU_GUID@@@Z`
- size: `129`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800da860`

## callees

- `0x180018b10`
- `0x1800dad64`

## import_xrefs

- `bcd!BcdQueryObject` at `0x1800dadac`
- `bcd!BcdQueryObject` at `0x1800dadac`
- `bcd!BcdCloseObject` at `0x1800dadcb`
- `bcd!BcdCloseObject` at `0x180128b55`
- `bcd!BcdCloseObject` at `0x1800dadcb`
- `bcd!BcdCloseObject` at `0x180128b55`
- `bcd!BcdOpenObject` at `0x1800dad86`
- `bcd!BcdOpenObject` at `0x1800dad86`

## pseudocode

```c
__int64 __fastcall FveBcdUtil::GetCurrentOsGuid(void *a1, struct _GUID *a2)
{
  int v3; // eax
  int v4; // ebx
  int Object; // eax
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
0x1800dad64  mov     [rsp+arg_0], rbx
0x1800dad69  push    rdi
0x1800dad6a  sub     rsp, 20h
0x1800dad6e  mov     rdi, rdx
0x1800dad71  mov     [rsp+28h+arg_10], 0
0x1800dad7a  lea     r8, [rsp+28h+arg_10]
0x1800dad7f  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x1800dad86  call    cs:__imp_BcdOpenObject
0x1800dad8d  nop     dword ptr [rax+rax+00h]
0x1800dad92  mov     ecx, eax; int
0x1800dad94  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800dad99  mov     ebx, eax
0x1800dad9b  test    eax, eax
0x1800dad9d  js      short loc_1800DADC1
0x1800dad9f  mov     r9, rdi
0x1800dada2  xor     r8d, r8d
0x1800dada5  xor     edx, edx
0x1800dada7  mov     rcx, [rsp+28h+arg_10]
0x1800dadac  call    cs:__imp_BcdQueryObject
0x1800dadb3  nop     dword ptr [rax+rax+00h]
0x1800dadb8  mov     ecx, eax; int
0x1800dadba  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800dadbf  mov     ebx, eax
0x1800dadc1  mov     rcx, [rsp+28h+arg_10]
0x1800dadc6  test    rcx, rcx
0x1800dadc9  jz      short loc_1800DADD7
0x1800dadcb  call    cs:__imp_BcdCloseObject
0x1800dadd2  nop     dword ptr [rax+rax+00h]
0x1800dadd7  mov     eax, ebx
0x1800dadd9  mov     rbx, [rsp+28h+arg_0]
0x1800dadde  add     rsp, 20h
0x1800dade2  pop     rdi
0x1800dade3  retn
0x180128b43  push    rbp
0x180128b45  sub     rsp, 20h
0x180128b49  mov     rbp, rdx
0x180128b4c  mov     rcx, [rbp+40h]
0x180128b50  test    rcx, rcx
0x180128b53  jz      short loc_180128B62
0x180128b55  call    cs:__imp_BcdCloseObject
0x180128b5c  nop     dword ptr [rax+rax+00h]
0x180128b61  nop
0x180128b62  add     rsp, 20h
0x180128b66  pop     rbp
0x180128b67  retn
```
