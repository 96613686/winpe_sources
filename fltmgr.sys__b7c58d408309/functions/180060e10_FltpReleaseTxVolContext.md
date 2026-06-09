# FltpReleaseTxVolContext

- ea: `0x180060e10`
- end: `0x180060e79`
- name: `FltpReleaseTxVolContext`
- size: `105`
- prototype: `void __fastcall(char *Entry)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004e990`
- `0x18004eac0`
- `0x18004fe34`
- `0x180060a80`
- `0x180060c10`
- `0x1800612f0`
- `0x180070b30`

## callees

- `0x18005dcc0`
- `0x180060e10`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x180060e40`
- `ntoskrnl!ObfDereferenceObject` at `0x180060e40`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007a03d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18007a03d`
- `ntoskrnl!ZwClose` at `0x180060e50`
- `ntoskrnl!ZwClose` at `0x180060e50`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18007a027`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18007a027`

## pseudocode

```c
void __fastcall FltpReleaseTxVolContext(char *Entry)
{
  void *v2; // rcx

  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 36, 0xFFFFFFFF) == 1 )
  {
    v2 = (void *)*((_QWORD *)Entry + 3);
    if ( v2 != (void *)-1LL )
    {
      ObfDereferenceObject(v2);
      ZwClose(*((HANDLE *)Entry + 2));
      if ( (*((_DWORD *)Entry + 37) & 8) != 0 )
        FltpObjectPointerDereference(*((char **)Entry + 1));
    }
    ExCleanupAutoExpandPushLock(Entry + 160);
    ExFreeToNPagedLookasideList(&stru_18003F0C0, Entry);
  }
}

```

## disassembly

```asm
0x180060e10  push    rbx
0x180060e12  sub     rsp, 20h
0x180060e16  mov     rbx, rcx
0x180060e19  mov     eax, 0FFFFFFFFh
0x180060e1e  lock xadd [rcx+90h], eax
0x180060e26  cmp     eax, 1
0x180060e29  jz      short loc_180060E32
0x180060e2b  add     rsp, 20h
0x180060e2f  pop     rbx
0x180060e30  retn
0x180060e32  mov     rcx, [rcx+18h]; Object
0x180060e36  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180060e3a  jz      loc_18007A020
0x180060e40  call    cs:__imp_ObfDereferenceObject
0x180060e47  nop     dword ptr [rax+rax+00h]
0x180060e4c  mov     rcx, [rbx+10h]; Handle
0x180060e50  call    cs:__imp_ZwClose
0x180060e57  nop     dword ptr [rax+rax+00h]
0x180060e5c  mov     eax, [rbx+94h]
0x180060e62  test    al, 8
0x180060e64  jz      loc_18007A020
0x180060e6a  mov     rcx, [rbx+8]
0x180060e6e  call    FltpObjectPointerDereference
0x180060e73  nop
0x180060e74  jmp     loc_18007A020
0x18007a020  lea     rcx, [rbx+0A0h]
0x18007a027  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18007a02e  nop     dword ptr [rax+rax+00h]
0x18007a033  mov     rdx, rbx; Entry
0x18007a036  lea     rcx, stru_18003F0C0; Lookaside
0x18007a03d  call    cs:__imp_ExFreeToNPagedLookasideList
0x18007a044  nop     dword ptr [rax+rax+00h]
0x18007a049  nop
0x18007a04a  jmp     loc_180060E2B
```
