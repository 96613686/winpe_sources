# CFveApiBase::GetCurrentOsGuid(void *,_GUID *)

- ea: `0x18009c170`
- end: `0x18009c20d`
- name: `?GetCurrentOsGuid@CFveApiBase@@KAJPEAXPEAU_GUID@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(void *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009ba80`

## callees

- `0x180018b10`
- `0x18009c170`
- `0x18011f010`

## import_xrefs

- `bcd!BcdQueryObject` at `0x18009c1c7`
- `bcd!BcdQueryObject` at `0x18009c1c7`
- `bcd!BcdCloseObject` at `0x18009c1e6`
- `bcd!BcdCloseObject` at `0x180124854`
- `bcd!BcdCloseObject` at `0x18009c1e6`
- `bcd!BcdCloseObject` at `0x180124854`
- `bcd!BcdOpenObject` at `0x18009c1a1`
- `bcd!BcdOpenObject` at `0x18009c1a1`

## pseudocode

```c
__int64 __fastcall CFveApiBase::GetCurrentOsGuid(void *a1, struct _GUID *a2)
{
  int v3; // eax
  int v4; // ebx
  int Object; // eax
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

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
0x18009c170  mov     [rsp+arg_10], rbx
0x18009c175  push    rdi
0x18009c176  sub     rsp, 30h
0x18009c17a  mov     rax, cs:__security_cookie
0x18009c181  xor     rax, rsp
0x18009c184  mov     [rsp+38h+var_10], rax
0x18009c189  mov     rdi, rdx
0x18009c18c  mov     [rsp+38h+var_18], 0
0x18009c195  lea     r8, [rsp+38h+var_18]
0x18009c19a  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x18009c1a1  call    cs:__imp_BcdOpenObject
0x18009c1a8  nop     dword ptr [rax+rax+00h]
0x18009c1ad  mov     ecx, eax; int
0x18009c1af  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c1b4  mov     ebx, eax
0x18009c1b6  test    eax, eax
0x18009c1b8  js      short loc_18009C1DC
0x18009c1ba  mov     r9, rdi
0x18009c1bd  xor     r8d, r8d
0x18009c1c0  xor     edx, edx
0x18009c1c2  mov     rcx, [rsp+38h+var_18]
0x18009c1c7  call    cs:__imp_BcdQueryObject
0x18009c1ce  nop     dword ptr [rax+rax+00h]
0x18009c1d3  mov     ecx, eax; int
0x18009c1d5  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009c1da  mov     ebx, eax
0x18009c1dc  mov     rcx, [rsp+38h+var_18]
0x18009c1e1  test    rcx, rcx
0x18009c1e4  jz      short loc_18009C1F2
0x18009c1e6  call    cs:__imp_BcdCloseObject
0x18009c1ed  nop     dword ptr [rax+rax+00h]
0x18009c1f2  mov     eax, ebx
0x18009c1f4  mov     rcx, [rsp+38h+var_10]
0x18009c1f9  xor     rcx, rsp; StackCookie
0x18009c1fc  call    __security_check_cookie
0x18009c201  mov     rbx, [rsp+38h+arg_10]
0x18009c206  add     rsp, 30h
0x18009c20a  pop     rdi
0x18009c20b  retn
0x180124842  push    rbp
0x180124844  sub     rsp, 20h
0x180124848  mov     rbp, rdx
0x18012484b  mov     rcx, [rbp+20h]
0x18012484f  test    rcx, rcx
0x180124852  jz      short loc_180124861
0x180124854  call    cs:__imp_BcdCloseObject
0x18012485b  nop     dword ptr [rax+rax+00h]
0x180124860  nop
0x180124861  add     rsp, 20h
0x180124865  pop     rbp
0x180124866  retn
```
