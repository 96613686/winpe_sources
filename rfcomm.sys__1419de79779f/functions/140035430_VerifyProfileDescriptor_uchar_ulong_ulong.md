# VerifyProfileDescriptor(uchar *,ulong,ulong)

- ea: `0x140035430`
- end: `0x14003547c`
- name: `?VerifyProfileDescriptor@@YAJPEAEKK@Z`
- size: `76`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140035430`
- `0x14003573c`

## pseudocode

```c
__int64 __fastcall VerifyProfileDescriptor(unsigned __int8 *a1, int a2)
{
  __int64 result; // rax
  int v3; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  result = SdpVerifySequenceOf((_DWORD)a1, a2, 6, 0, (__int64)&v3, (__int64)WalkProfileDescriptor, 0);
  if ( (int)result >= 0 && !v3 )
    return 3221225485LL;
  return result;
}

```

## disassembly

```asm
0x140035430  mov     r11, rsp
0x140035433  sub     rsp, 48h
0x140035437  mov     qword ptr [r11-18h], 0
0x14003543f  lea     rax, ?WalkProfileDescriptor@@YAJPEAXEKPEAE@Z; WalkProfileDescriptor(void *,uchar,ulong,uchar *)
0x140035446  mov     [r11-20h], rax
0x14003544a  xor     r9d, r9d
0x14003544d  lea     rax, [r11+20h]
0x140035451  mov     [rsp+48h+arg_18], 0
0x140035459  mov     r8b, 6
0x14003545c  mov     [r11-28h], rax
0x140035460  call    SdpVerifySequenceOf
0x140035465  test    eax, eax
0x140035467  js      short loc_140035476
0x140035469  cmp     [rsp+48h+arg_18], 0
0x14003546e  mov     ecx, 0C000000Dh
0x140035473  cmovz   eax, ecx
0x140035476  add     rsp, 48h
0x14003547a  retn
```
