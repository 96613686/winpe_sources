# MarkTableForDeletion

- ea: `0x18000e34c`
- end: `0x18000e3c4`
- name: `MarkTableForDeletion`
- size: `120`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x180010088`
- `0x1800105d0`
- `0x18001077c`
- `0x1800108e4`
- `0x1800109fc`
- `0x180010fd4`
- `0x180013364`

## callees

- `0x18000e34c`
- `0x180019b9c`
- `0x18001a808`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall MarkTableForDeletion(__int64 a1, __int64 a2)
{
  unsigned int TTDirectory; // eax
  __int16 v5; // [rsp+30h] [rbp-28h] BYREF
  __int128 v6; // [rsp+38h] [rbp-20h] BYREF

  v6 = 0;
  v5 = 0;
  TTDirectory = GetTTDirectory(a1, a2, (__int64)&v6);
  if ( TTDirectory )
  {
    LODWORD(v6) = 16843009;
    LOWORD(TTDirectory) = WriteGeneric(a1, (__int64)&v6, 0x10u, (unsigned __int8 *)&DIRECTORY_CONTROL, TTDirectory, &v5);
  }
  return TTDirectory;
}

```

## disassembly

```asm
0x18000e34c  push    rbx
0x18000e34e  sub     rsp, 50h
0x18000e352  mov     rax, cs:__security_cookie
0x18000e359  xor     rax, rsp
0x18000e35c  mov     [rsp+58h+var_10], rax
0x18000e361  xorps   xmm0, xmm0
0x18000e364  lea     r8, [rsp+58h+var_20]
0x18000e369  xor     eax, eax
0x18000e36b  mov     rbx, rcx
0x18000e36e  movups  [rsp+58h+var_20], xmm0
0x18000e373  mov     [rsp+58h+var_28], ax
0x18000e378  call    GetTTDirectory
0x18000e37d  test    eax, eax
0x18000e37f  jz      short loc_18000E3B1
0x18000e381  lea     rcx, [rsp+58h+var_28]
0x18000e386  mov     dword ptr [rsp+58h+var_20], 1010101h
0x18000e38e  mov     [rsp+58h+var_30], rcx
0x18000e393  lea     r9, DIRECTORY_CONTROL
0x18000e39a  mov     rcx, rbx
0x18000e39d  mov     [rsp+58h+var_38], eax
0x18000e3a1  mov     r8d, 10h
0x18000e3a7  lea     rdx, [rsp+58h+var_20]
0x18000e3ac  call    WriteGeneric
0x18000e3b1  mov     rcx, [rsp+58h+var_10]
0x18000e3b6  xor     rcx, rsp; StackCookie
0x18000e3b9  call    __security_check_cookie
0x18000e3be  add     rsp, 50h
0x18000e3c2  pop     rbx
0x18000e3c3  retn
```
