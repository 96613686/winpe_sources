# TextLogSetLogStatus

- ea: `0x180005970`
- end: `0x1800059ed`
- name: `TextLogSetLogStatus`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800052c4`
- `0x1800063bc`
- `0x180006590`

## callees

- `0x18000355c`
- `0x180003ad4`
- `0x180005970`
- `0x180006fb0`

## import_xrefs

- `ntdll!NtClose` at `0x1800059da`
- `ntdll!NtClose` at `0x1800059da`

## pseudocode

```c
__int64 __fastcall TextLogSetLogStatus(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v6; // [rsp+28h] [rbp-20h]
  HANDLE Handle; // [rsp+60h] [rbp+18h] BYREF

  v3 = 0;
  Handle = 0;
  if ( !(unsigned int)pSetupCreateKeyEx(a1, L"SYSTEM\\Setup\\SetupapiLogStatus", a3, 1u, 2u, v6, (__int64 *)&Handle) )
  {
    pSetupGetFileTitle(*(_QWORD *)(a1 + 16));
    LOBYTE(v3) = (unsigned int)pSetupSetValue(Handle, 4u) == 0;
    NtClose((HANDLE)(unsigned int)Handle);
  }
  return v3;
}

```

## disassembly

```asm
0x180005970  mov     rax, rsp
0x180005973  mov     [rax+8], rbx
0x180005977  mov     [rax+10h], edx
0x18000597a  push    rdi
0x18000597b  sub     rsp, 40h
0x18000597f  xor     ebx, ebx
0x180005981  lea     rdx, aSystemSetupSet_0; "SYSTEM\\Setup\\SetupapiLogStatus"
0x180005988  mov     [rax+18h], rbx
0x18000598c  lea     rax, [rax+18h]
0x180005990  mov     [rsp+48h+var_18], rax
0x180005995  mov     rdi, rcx
0x180005998  mov     [rsp+48h+var_28], 2
0x1800059a0  lea     r9d, [rbx+1]
0x1800059a4  call    pSetupCreateKeyEx
0x1800059a9  test    eax, eax
0x1800059ab  jnz     short loc_1800059E0
0x1800059ad  mov     rcx, [rdi+10h]
0x1800059b1  call    pSetupGetFileTitle
0x1800059b6  mov     rcx, [rsp+48h+Handle]; KeyHandle
0x1800059bb  lea     r8d, [rbx+4]
0x1800059bf  mov     rdx, rax
0x1800059c2  mov     [rsp+48h+var_28], r8d; ULONG
0x1800059c7  lea     r9, [rsp+48h+arg_8]
0x1800059cc  call    pSetupSetValue
0x1800059d1  mov     ecx, dword ptr [rsp+48h+Handle]; Handle
0x1800059d5  test    eax, eax
0x1800059d7  setz    bl
0x1800059da  call    cs:__imp_NtClose
0x1800059e0  mov     eax, ebx
0x1800059e2  mov     rbx, [rsp+48h+arg_0]
0x1800059e7  add     rsp, 40h
0x1800059eb  pop     rdi
0x1800059ec  retn
```
