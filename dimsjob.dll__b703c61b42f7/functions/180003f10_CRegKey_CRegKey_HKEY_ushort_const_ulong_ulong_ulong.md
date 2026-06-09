# CRegKey::CRegKey(HKEY__ *,ushort const *,ulong,ulong,ulong *)

- ea: `0x180003f10`
- end: `0x180003fc7`
- name: `??0CRegKey@@QEAA@PEAUHKEY__@@PEBGKKPEAK@Z`
- size: `183`
- prototype: `CRegKey *__fastcall(CRegKey *this, HKEY, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003c8c`

## callees

- `0x180003f10`
- `0x18000a360`
- `0x18000ab3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003f59`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180003f59`

## pseudocode

```c
CRegKey *__fastcall CRegKey::CRegKey(CRegKey *this, HKEY a2, const unsigned __int16 *a3, int a4)
{
  int Key; // ebx
  int pExceptionObject; // [rsp+78h] [rbp+20h] BYREF

  pExceptionObject = a4;
  Key = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x20006u, 0, (PHKEY)this, 0);
  if ( Key )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids,
        (unsigned int)Key);
    if ( Key > 0 )
      Key = (unsigned __int16)Key | 0x80070000;
    pExceptionObject = Key;
    throw (CExcept *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180003f10  mov     r11, rsp
0x180003f13  mov     [r11+8], rbx
0x180003f17  mov     [r11+20h], r9d
0x180003f1b  push    rdi
0x180003f1c  sub     rsp, 50h
0x180003f20  mov     qword ptr [r11-18h], 0
0x180003f28  mov     rax, r8
0x180003f2b  mov     [r11-20h], rcx
0x180003f2f  mov     r10, rdx
0x180003f32  mov     qword ptr [r11-28h], 0
0x180003f3a  mov     rdi, rcx
0x180003f3d  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180003f45  xor     r9d, r9d; lpClass
0x180003f48  xor     r8d, r8d; Reserved
0x180003f4b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180003f53  mov     rdx, rax; lpSubKey
0x180003f56  mov     rcx, r10; hKey
0x180003f59  call    cs:__imp_RegCreateKeyExW
0x180003f5f  mov     ebx, eax
0x180003f61  test    eax, eax
0x180003f63  jz      short loc_180003FB9
0x180003f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f6c  lea     rax, WPP_GLOBAL_Control
0x180003f73  cmp     rcx, rax
0x180003f76  jz      short loc_180003F96
0x180003f78  test    byte ptr [rcx+1Ch], 2
0x180003f7c  jz      short loc_180003F96
0x180003f7e  mov     rcx, [rcx+10h]
0x180003f82  lea     r8, WPP_1eba886745fe349fd97ae921e3b476bf_Traceguids
0x180003f89  mov     edx, 0Ah
0x180003f8e  mov     r9d, ebx
0x180003f91  call    WPP_SF_D
0x180003f96  test    ebx, ebx
0x180003f98  jle     short loc_180003FA3
0x180003f9a  movzx   ebx, bx
0x180003f9d  or      ebx, 80070000h
0x180003fa3  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180003faa  mov     [rsp+58h+pExceptionObject], ebx
0x180003fae  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180003fb3  call    _CxxThrowException_0
0x180003fb9  mov     rbx, [rsp+58h+arg_0]
0x180003fbe  mov     rax, rdi
0x180003fc1  add     rsp, 50h
0x180003fc5  pop     rdi
0x180003fc6  retn
```
