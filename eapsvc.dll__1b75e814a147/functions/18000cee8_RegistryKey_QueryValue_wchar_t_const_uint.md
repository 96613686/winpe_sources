# RegistryKey::QueryValue(wchar_t const *,uint &)

- ea: `0x18000cee8`
- end: `0x18000cf48`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAI@Z`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18000a5cc`
- `0x18000c2a0`
- `0x18000dfb0`

## callees

- `0x18000ab70`
- `0x18000cee8`
- `0x18000cf50`

## pseudocode

```c
__int64 __fastcall RegistryKey::QueryValue(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  LPCVOID lpMem[3]; // [rsp+30h] [rbp-18h] BYREF
  int v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  lpMem[0] = 0;
  lpMem[1] = 0;
  v4 = RegistryKey::QueryValue(a1, a2, &v8, lpMem);
  v5 = (void *)lpMem[0];
  if ( !v4 )
  {
    if ( v8 == 4 )
      *a3 = *(_DWORD *)lpMem[0];
    else
      v4 = 2;
  }
  operator delete(v5);
  return v4;
}

```

## disassembly

```asm
0x18000cee8  mov     rax, rsp
0x18000ceeb  mov     [rax+8], rbx
0x18000ceef  push    rdi
0x18000cef0  sub     rsp, 40h
0x18000cef4  mov     rdi, r8
0x18000cef7  mov     dword ptr [rax+20h], 0
0x18000cefe  mov     qword ptr [rax-18h], 0
0x18000cf06  mov     qword ptr [rax-10h], 0
0x18000cf0e  lea     r9, [rax-18h]
0x18000cf12  lea     r8, [rax+20h]
0x18000cf16  call    ?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z; RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)
0x18000cf1b  mov     ebx, eax
0x18000cf1d  mov     rcx, [rsp+48h+lpMem]; lpMem
0x18000cf22  test    eax, eax
0x18000cf24  jnz     short loc_18000CF36
0x18000cf26  cmp     [rsp+48h+arg_18], 4
0x18000cf2b  jz      short loc_18000CF32
0x18000cf2d  lea     ebx, [rax+2]
0x18000cf30  jmp     short loc_18000CF36
0x18000cf32  mov     eax, [rcx]
0x18000cf34  mov     [rdi], eax
0x18000cf36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cf3b  mov     eax, ebx
0x18000cf3d  mov     rbx, [rsp+48h+arg_0]
0x18000cf42  add     rsp, 40h
0x18000cf46  pop     rdi
0x18000cf47  retn
```
