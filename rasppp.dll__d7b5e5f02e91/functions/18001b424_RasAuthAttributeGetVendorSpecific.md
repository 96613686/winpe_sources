# RasAuthAttributeGetVendorSpecific

- ea: `0x18001b424`
- end: `0x18001b4a9`
- name: `RasAuthAttributeGetVendorSpecific`
- size: `133`
- prototype: `_DWORD *__fastcall(__int64, __int64, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x18000380c`
- `0x18000a9f0`
- `0x18001063c`
- `0x18001427c`
- `0x18001a254`
- `0x180024d70`

## callees

- `0x18001b3d0`
- `0x18001b3f8`
- `0x18001b424`

## pseudocode

```c
_DWORD *__fastcall RasAuthAttributeGetVendorSpecific(__int64 a1, __int64 a2, __int64 a3)
{
  _DWORD *result; // rax
  int v4; // r11d
  unsigned __int8 *v5; // r8
  _DWORD *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  for ( result = RasAuthAttributeGetFirst(26, a3); result; result = RasAuthAttributeGetNext(&v6, 26) )
  {
    if ( result[1] >= 8u )
    {
      v5 = (unsigned __int8 *)*((_QWORD *)result + 1);
      if ( v5[3] + (*v5 << 24) + (v5[2] << 8) + (v5[1] << 16) == 311 && v5[4] == v4 )
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b424  sub     rsp, 28h
0x18001b428  mov     rax, r8
0x18001b42b  mov     [rsp+28h+arg_18], 0
0x18001b434  mov     r11d, edx
0x18001b437  lea     r8, [rsp+28h+arg_18]
0x18001b43c  mov     rdx, rax
0x18001b43f  mov     ecx, 1Ah
0x18001b444  call    RasAuthAttributeGetFirst
0x18001b449  mov     r10, rax
0x18001b44c  test    rax, rax
0x18001b44f  jz      short loc_18001B4A3
0x18001b451  cmp     dword ptr [rax+4], 8
0x18001b455  jb      short loc_18001B48F
0x18001b457  mov     r8, [rax+8]
0x18001b45b  movzx   edx, byte ptr [r8+1]
0x18001b460  movzx   ecx, byte ptr [r8+2]
0x18001b465  movzx   eax, byte ptr [r8]
0x18001b469  shl     edx, 10h
0x18001b46c  shl     eax, 18h
0x18001b46f  shl     ecx, 8
0x18001b472  add     edx, ecx
0x18001b474  add     edx, eax
0x18001b476  movzx   eax, byte ptr [r8+3]
0x18001b47b  add     edx, eax
0x18001b47d  cmp     edx, 137h
0x18001b483  jnz     short loc_18001B48F
0x18001b485  movzx   eax, byte ptr [r8+4]
0x18001b48a  cmp     eax, r11d
0x18001b48d  jz      short loc_18001B4A0
0x18001b48f  mov     edx, 1Ah
0x18001b494  lea     rcx, [rsp+28h+arg_18]
0x18001b499  call    RasAuthAttributeGetNext
0x18001b49e  jmp     short loc_18001B449
0x18001b4a0  mov     rax, r10
0x18001b4a3  add     rsp, 28h
0x18001b4a7  retn
```
