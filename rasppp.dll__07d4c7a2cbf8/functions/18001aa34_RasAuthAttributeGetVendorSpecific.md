# RasAuthAttributeGetVendorSpecific

- ea: `0x18001aa34`
- end: `0x18001aab8`
- name: `RasAuthAttributeGetVendorSpecific`
- size: `132`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180003770`
- `0x18000a610`
- `0x18001016c`
- `0x180013bb4`
- `0x1800198d8`
- `0x180023fe0`

## callees

- `0x18001a9e4`
- `0x18001aa08`
- `0x18001aa34`

## pseudocode

```c
__int64 __fastcall RasAuthAttributeGetVendorSpecific(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  int v4; // r11d
  unsigned __int8 *v5; // r8
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  for ( result = RasAuthAttributeGetFirst(26, a3, &v6); result; result = RasAuthAttributeGetNext(&v6, 26) )
  {
    if ( *(_DWORD *)(result + 4) >= 8u )
    {
      v5 = *(unsigned __int8 **)(result + 8);
      if ( v5[3] + (*v5 << 24) + (v5[2] << 8) + (v5[1] << 16) == 311 && v5[4] == v4 )
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001aa34  sub     rsp, 28h
0x18001aa38  mov     rax, r8
0x18001aa3b  mov     [rsp+28h+arg_18], 0
0x18001aa44  mov     r11d, edx
0x18001aa47  lea     r8, [rsp+28h+arg_18]
0x18001aa4c  mov     rdx, rax
0x18001aa4f  mov     ecx, 1Ah
0x18001aa54  call    RasAuthAttributeGetFirst
0x18001aa59  mov     r10, rax
0x18001aa5c  test    rax, rax
0x18001aa5f  jz      short loc_18001AAB3
0x18001aa61  cmp     dword ptr [rax+4], 8
0x18001aa65  jb      short loc_18001AA9F
0x18001aa67  mov     r8, [rax+8]
0x18001aa6b  movzx   edx, byte ptr [r8+1]
0x18001aa70  movzx   ecx, byte ptr [r8+2]
0x18001aa75  movzx   eax, byte ptr [r8]
0x18001aa79  shl     edx, 10h
0x18001aa7c  shl     eax, 18h
0x18001aa7f  shl     ecx, 8
0x18001aa82  add     edx, ecx
0x18001aa84  add     edx, eax
0x18001aa86  movzx   eax, byte ptr [r8+3]
0x18001aa8b  add     edx, eax
0x18001aa8d  cmp     edx, 137h
0x18001aa93  jnz     short loc_18001AA9F
0x18001aa95  movzx   eax, byte ptr [r8+4]
0x18001aa9a  cmp     eax, r11d
0x18001aa9d  jz      short loc_18001AAB0
0x18001aa9f  mov     edx, 1Ah
0x18001aaa4  lea     rcx, [rsp+28h+arg_18]
0x18001aaa9  call    RasAuthAttributeGetNext
0x18001aaae  jmp     short loc_18001AA59
0x18001aab0  mov     rax, r10
0x18001aab3  add     rsp, 28h
0x18001aab7  retn
```
