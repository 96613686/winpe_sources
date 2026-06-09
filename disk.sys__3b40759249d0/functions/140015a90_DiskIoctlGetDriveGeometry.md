# DiskIoctlGetDriveGeometry

- ea: `0x140015a90`
- end: `0x140015ba8`
- name: `DiskIoctlGetDriveGeometry`
- size: `280`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140003a78`
- `0x140004078`
- `0x140015a90`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140015ab6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140015ab6`
- `CLASSPNP!ClassReadDriveCapacity` at `0x140015b37`
- `CLASSPNP!ClassReadDriveCapacity` at `0x140015b37`

## pseudocode

```c
NTSTATUS __fastcall DiskIoctlGetDriveGeometry(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rdi
  __int64 v4; // r14
  __int64 v6; // rbx
  __int64 v7; // r15
  NTSTATUS result; // eax
  int v9; // eax

  v2 = *(_QWORD *)(a1 + 64);
  v4 = a2[23];
  v6 = a2[3];
  v7 = *(_QWORD *)(v2 + 96);
  if ( KeGetCurrentIrql() >= 2u )
    return -1073741496;
  if ( *(_DWORD *)(v4 + 8) >= 0x18u )
  {
    if ( (*(_DWORD *)(a1 + 52) & 1) == 0
      || (result = ClassReadDriveCapacity(*(PDEVICE_OBJECT *)(*(_QWORD *)(v2 + 24) + 8LL)),
          *(_DWORD *)(v7 + 4) = result,
          result >= 0) )
    {
      *(_QWORD *)v6 = *(_QWORD *)(v2 + 552);
      *(_DWORD *)(v6 + 8) = *(_DWORD *)(v2 + 560);
      *(_DWORD *)(v6 + 12) = *(_DWORD *)(v2 + 564);
      *(_DWORD *)(v6 + 16) = *(_DWORD *)(v2 + 568);
      v9 = *(_DWORD *)(v2 + 572);
      *(_DWORD *)(v6 + 20) = v9;
      if ( !v9 && !(unsigned __int8)DiskIsManagedZonedDevice(a1) )
        *(_DWORD *)(v6 + 20) = 512;
      a2[7] = 24;
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return -1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x140015a90  push    rbx
0x140015a92  push    rbp
0x140015a93  push    rsi
0x140015a94  push    rdi
0x140015a95  push    r14
0x140015a97  push    r15
0x140015a99  sub     rsp, 28h
0x140015a9d  mov     rdi, [rcx+40h]
0x140015aa1  mov     rbp, rdx
0x140015aa4  mov     r14, [rdx+0B8h]
0x140015aab  mov     rsi, rcx
0x140015aae  mov     rbx, [rdx+18h]
0x140015ab2  mov     r15, [rdi+60h]
0x140015ab6  call    cs:__imp_KeGetCurrentIrql
0x140015abd  nop     dword ptr [rax+rax+00h]
0x140015ac2  cmp     al, 2
0x140015ac4  jb      short loc_140015AD9
0x140015ac6  mov     eax, 0C0000148h
0x140015acb  add     rsp, 28h
0x140015acf  pop     r15
0x140015ad1  pop     r14
0x140015ad3  pop     rdi
0x140015ad4  pop     rsi
0x140015ad5  pop     rbp
0x140015ad6  pop     rbx
0x140015ad7  retn
0x140015ad9  cmp     dword ptr [r14+8], 18h
0x140015ade  jnb     short loc_140015B28
0x140015ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ae7  lea     rax, WPP_GLOBAL_Control
0x140015aee  cmp     rcx, rax
0x140015af1  jz      short loc_140015B15
0x140015af3  mov     eax, [rcx+2Ch]
0x140015af6  test    al, 10h
0x140015af8  jz      short loc_140015B15
0x140015afa  cmp     byte ptr [rcx+29h], 2
0x140015afe  jb      short loc_140015B15
0x140015b00  mov     rcx, [rcx+18h]
0x140015b04  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140015b0b  mov     edx, 39h ; '9'
0x140015b10  call    WPP_SF_
0x140015b15  mov     eax, 0C0000023h
0x140015b1a  add     rsp, 28h
0x140015b1e  pop     r15
0x140015b20  pop     r14
0x140015b22  pop     rdi
0x140015b23  pop     rsi
0x140015b24  pop     rbp
0x140015b25  pop     rbx
0x140015b26  retn
0x140015b28  mov     eax, [rsi+34h]
0x140015b2b  test    al, 1
0x140015b2d  jz      short loc_140015B4B
0x140015b2f  mov     rcx, [rdi+18h]
0x140015b33  mov     rcx, [rcx+8]; DeviceObject
0x140015b37  call    cs:__imp_ClassReadDriveCapacity
0x140015b3e  nop     dword ptr [rax+rax+00h]
0x140015b43  mov     [r15+4], eax
0x140015b47  test    eax, eax
0x140015b49  js      short loc_140015B9A
0x140015b4b  mov     rax, [rdi+228h]
0x140015b52  mov     [rbx], rax
0x140015b55  mov     eax, [rdi+230h]
0x140015b5b  mov     [rbx+8], eax
0x140015b5e  mov     eax, [rdi+234h]
0x140015b64  mov     [rbx+0Ch], eax
0x140015b67  mov     eax, [rdi+238h]
0x140015b6d  mov     [rbx+10h], eax
0x140015b70  mov     eax, [rdi+23Ch]
0x140015b76  mov     [rbx+14h], eax
0x140015b79  test    eax, eax
0x140015b7b  jnz     short loc_140015B90
0x140015b7d  mov     rcx, rsi
0x140015b80  call    DiskIsManagedZonedDevice
0x140015b85  test    al, al
0x140015b87  jnz     short loc_140015B90
0x140015b89  mov     dword ptr [rbx+14h], 200h
0x140015b90  mov     qword ptr [rbp+38h], 18h
0x140015b98  xor     eax, eax
0x140015b9a  add     rsp, 28h
0x140015b9e  pop     r15
0x140015ba0  pop     r14
0x140015ba2  pop     rdi
0x140015ba3  pop     rsi
0x140015ba4  pop     rbp
0x140015ba5  pop     rbx
0x140015ba6  retn
```
