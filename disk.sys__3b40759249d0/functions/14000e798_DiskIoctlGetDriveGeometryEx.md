# DiskIoctlGetDriveGeometryEx

- ea: `0x14000e798`
- end: `0x14000e8ae`
- name: `DiskIoctlGetDriveGeometryEx`
- size: `278`
- prototype: `NTSTATUS __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400014a0`

## callees

- `0x140003a78`
- `0x140004078`
- `0x140006000`
- `0x14000e798`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000e7ab`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e7ab`
- `CLASSPNP!ClassReadDriveCapacity` at `0x14000e838`
- `CLASSPNP!ClassReadDriveCapacity` at `0x14000e838`

## pseudocode

```c
NTSTATUS __fastcall DiskIoctlGetDriveGeometryEx(__int64 a1, __int64 a2)
{
  NTSTATUS result; // eax
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rsi
  __int64 v8; // r15
  __int64 v9; // r8
  __int64 v10; // rax

  if ( KeGetCurrentIrql() >= 2u )
    return -1073741496;
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(unsigned int *)(v5 + 8);
  if ( (int)v6 >= 32 )
  {
    v7 = *(_QWORD *)(a1 + 64);
    v8 = *(_QWORD *)(v7 + 96);
    memset(*(void **)(a2 + 24), 0, *(unsigned int *)(v5 + 8));
    if ( (*(_DWORD *)(a1 + 52) & 1) == 0
      || (result = ClassReadDriveCapacity(*(PDEVICE_OBJECT *)(*(_QWORD *)(v7 + 24) + 8LL)),
          *(_DWORD *)(v8 + 4) = result,
          result >= 0) )
    {
      v9 = *(_QWORD *)(a2 + 24);
      *(_OWORD *)v9 = *(_OWORD *)(v7 + 552);
      *(_QWORD *)(v9 + 16) = *(_QWORD *)(v7 + 568);
      if ( !*(_DWORD *)(v9 + 20) && !(unsigned __int8)DiskIsManagedZonedDevice(a1) )
        *(_DWORD *)(v9 + 20) = 512;
      *(_QWORD *)(v9 + 24) = *(_QWORD *)(v7 + 144);
      v10 = 40;
      if ( (unsigned int)v6 < 0x28 )
        v10 = v6;
      *(_QWORD *)(a2 + 56) = v10;
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
    }
    return -1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x14000e798  push    rbx
0x14000e79a  push    rbp
0x14000e79b  push    rsi
0x14000e79c  push    rdi
0x14000e79d  push    r14
0x14000e79f  push    r15
0x14000e7a1  sub     rsp, 28h
0x14000e7a5  mov     rbx, rdx
0x14000e7a8  mov     rbp, rcx
0x14000e7ab  call    cs:__imp_KeGetCurrentIrql
0x14000e7b2  nop     dword ptr [rax+rax+00h]
0x14000e7b7  cmp     al, 2
0x14000e7b9  jb      short loc_14000E7C5
0x14000e7bb  mov     eax, 0C0000148h
0x14000e7c0  jmp     loc_14000E8A0
0x14000e7c5  mov     rax, [rbx+0B8h]
0x14000e7cc  mov     edi, [rax+8]
0x14000e7cf  cmp     edi, 20h ; ' '
0x14000e7d2  jge     short loc_14000E813
0x14000e7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7db  lea     rax, WPP_GLOBAL_Control
0x14000e7e2  cmp     rcx, rax
0x14000e7e5  jz      short loc_14000E809
0x14000e7e7  mov     eax, [rcx+2Ch]
0x14000e7ea  test    al, 10h
0x14000e7ec  jz      short loc_14000E809
0x14000e7ee  cmp     byte ptr [rcx+29h], 2
0x14000e7f2  jb      short loc_14000E809
0x14000e7f4  mov     rcx, [rcx+18h]
0x14000e7f8  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x14000e7ff  mov     edx, 3Ah ; ':'
0x14000e804  call    WPP_SF_
0x14000e809  mov     eax, 0C0000023h
0x14000e80e  jmp     loc_14000E8A0
0x14000e813  mov     rsi, [rbp+40h]
0x14000e817  mov     r8, rdi; Size
0x14000e81a  mov     rcx, [rbx+18h]; void *
0x14000e81e  xor     edx, edx; Val
0x14000e820  mov     r15, [rsi+60h]
0x14000e824  call    memset
0x14000e829  mov     eax, [rbp+34h]
0x14000e82c  test    al, 1
0x14000e82e  jz      short loc_14000E84C
0x14000e830  mov     rcx, [rsi+18h]
0x14000e834  mov     rcx, [rcx+8]; DeviceObject
0x14000e838  call    cs:__imp_ClassReadDriveCapacity
0x14000e83f  nop     dword ptr [rax+rax+00h]
0x14000e844  mov     [r15+4], eax
0x14000e848  test    eax, eax
0x14000e84a  js      short loc_14000E8A0
0x14000e84c  mov     r8, [rbx+18h]
0x14000e850  movups  xmm0, xmmword ptr [rsi+228h]
0x14000e857  movups  xmmword ptr [r8], xmm0
0x14000e85b  movsd   xmm1, qword ptr [rsi+238h]
0x14000e863  movsd   qword ptr [r8+10h], xmm1
0x14000e869  cmp     dword ptr [r8+14h], 0
0x14000e86e  jnz     short loc_14000E884
0x14000e870  mov     rcx, rbp
0x14000e873  call    DiskIsManagedZonedDevice
0x14000e878  test    al, al
0x14000e87a  jnz     short loc_14000E884
0x14000e87c  mov     dword ptr [r8+14h], 200h
0x14000e884  mov     rax, [rsi+90h]
0x14000e88b  mov     [r8+18h], rax
0x14000e88f  mov     eax, 28h ; '('
0x14000e894  cmp     edi, eax
0x14000e896  cmovb   rax, rdi
0x14000e89a  mov     [rbx+38h], rax
0x14000e89e  xor     eax, eax
0x14000e8a0  add     rsp, 28h
0x14000e8a4  pop     r15
0x14000e8a6  pop     r14
0x14000e8a8  pop     rdi
0x14000e8a9  pop     rsi
0x14000e8aa  pop     rbp
0x14000e8ab  pop     rbx
0x14000e8ac  retn
```
