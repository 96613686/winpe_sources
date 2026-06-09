# DiskReadFailurePredictThresholds

- ea: `0x140010e14`
- end: `0x140010f33`
- name: `DiskReadFailurePredictThresholds`
- size: `287`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140014200`

## callees

- `0x140010e14`
- `0x140012810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010f06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f06`
- `ntoskrnl!ExAllocatePool2` at `0x140010e61`
- `ntoskrnl!ExAllocatePool2` at `0x140010e61`

## pseudocode

```c
__int64 __fastcall DiskReadFailurePredictThresholds(__int64 a1, _OWORD *a2)
{
  char *Buffer; // rdi
  NTSTATUS v5; // ebx
  __int64 v6; // rcx
  _OWORD *v7; // rax
  __int128 v8; // xmm1
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)(*(_QWORD *)(a1 + 96) + 16LL) == 2 )
  {
    LODWORD(v10) = 556;
    Buffer = (char *)ExAllocatePool2(64, 556, 1631871827);
    if ( Buffer )
    {
      v5 = DiskPerformSmartCommand(a1, 1770755, 176, 209, 0, 0, Buffer, (int *)&v10);
      if ( v5 >= 0 )
      {
        v6 = 4;
        v7 = Buffer + 44;
        do
        {
          *a2 = *v7;
          a2[1] = v7[1];
          a2[2] = v7[2];
          a2[3] = v7[3];
          a2[4] = v7[4];
          a2[5] = v7[5];
          a2[6] = v7[6];
          v8 = v7[7];
          v7 += 8;
          a2[7] = v8;
          a2 += 8;
          --v6;
        }
        while ( v6 );
      }
      ExFreePoolWithTag(Buffer, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741808;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140010e14  mov     [rsp+arg_8], rbx
0x140010e19  mov     [rsp+arg_10], rsi
0x140010e1e  push    rdi
0x140010e1f  sub     rsp, 40h
0x140010e23  mov     r8, [rcx+60h]
0x140010e27  mov     rsi, rdx
0x140010e2a  mov     rbx, rcx
0x140010e2d  mov     r9d, [r8+10h]
0x140010e31  test    r9d, r9d
0x140010e34  jz      loc_140010F1B
0x140010e3a  sub     r9d, 1
0x140010e3e  jz      loc_140010F1B
0x140010e44  cmp     r9d, 1
0x140010e48  jnz     loc_140010F1B
0x140010e4e  mov     edx, 22Ch
0x140010e53  lea     ecx, [r9+3Fh]
0x140010e57  mov     r8d, 61446353h
0x140010e5d  mov     dword ptr [rsp+48h+arg_0], edx
0x140010e61  call    cs:__imp_ExAllocatePool2
0x140010e68  nop     dword ptr [rax+rax+00h]
0x140010e6d  mov     rdi, rax
0x140010e70  test    rax, rax
0x140010e73  jz      loc_140010F14
0x140010e79  lea     rax, [rsp+48h+arg_0]
0x140010e7e  mov     r9b, 0D1h; int
0x140010e81  mov     [rsp+48h+var_10], rax; __int64
0x140010e86  mov     r8b, 0B0h; int
0x140010e89  mov     [rsp+48h+Buffer], rdi; Buffer
0x140010e8e  mov     edx, 1B0503h; int
0x140010e93  mov     [rsp+48h+var_20], 0; char
0x140010e98  mov     rcx, rbx; int
0x140010e9b  mov     [rsp+48h+var_28], 0; char
0x140010ea0  call    DiskPerformSmartCommand
0x140010ea5  mov     ebx, eax
0x140010ea7  test    eax, eax
0x140010ea9  js      short loc_140010F01
0x140010eab  mov     ecx, 4
0x140010eb0  lea     rax, [rdi+2Ch]
0x140010eb4  lea     edx, [rcx+7Ch]
0x140010eb7  movups  xmm0, xmmword ptr [rax]
0x140010eba  movups  xmmword ptr [rsi], xmm0
0x140010ebd  movups  xmm1, xmmword ptr [rax+10h]
0x140010ec1  movups  xmmword ptr [rsi+10h], xmm1
0x140010ec5  movups  xmm0, xmmword ptr [rax+20h]
0x140010ec9  movups  xmmword ptr [rsi+20h], xmm0
0x140010ecd  movups  xmm1, xmmword ptr [rax+30h]
0x140010ed1  movups  xmmword ptr [rsi+30h], xmm1
0x140010ed5  movups  xmm0, xmmword ptr [rax+40h]
0x140010ed9  movups  xmmword ptr [rsi+40h], xmm0
0x140010edd  movups  xmm1, xmmword ptr [rax+50h]
0x140010ee1  movups  xmmword ptr [rsi+50h], xmm1
0x140010ee5  movups  xmm0, xmmword ptr [rax+60h]
0x140010ee9  movups  xmmword ptr [rsi+60h], xmm0
0x140010eed  movups  xmm1, xmmword ptr [rax+70h]
0x140010ef1  add     rax, rdx
0x140010ef4  movups  xmmword ptr [rsi+70h], xmm1
0x140010ef8  add     rsi, rdx
0x140010efb  sub     rcx, 1
0x140010eff  jnz     short loc_140010EB7
0x140010f01  xor     edx, edx; Tag
0x140010f03  mov     rcx, rdi; P
0x140010f06  call    cs:__imp_ExFreePoolWithTag
0x140010f0d  nop     dword ptr [rax+rax+00h]
0x140010f12  jmp     short loc_140010F20
0x140010f14  mov     ebx, 0C000009Ah
0x140010f19  jmp     short loc_140010F20
0x140010f1b  mov     ebx, 0C0000010h
0x140010f20  mov     rsi, [rsp+48h+arg_10]
0x140010f25  mov     eax, ebx
0x140010f27  mov     rbx, [rsp+48h+arg_8]
0x140010f2c  add     rsp, 40h
0x140010f30  pop     rdi
0x140010f31  retn
```
