# CheckResult(long)

- ea: `0x180001e7c`
- end: `0x180001eed`
- name: `?CheckResult@@YAKJ@Z`
- size: `113`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180002254`
- `0x1800023d4`
- `0x180002448`
- `0x180002b00`
- `0x180002b78`
- `0x180002d20`
- `0x180003210`
- `0x180003408`
- `0x180003604`
- `0x180003848`
- `0x180003a04`
- `0x18000443c`
- `0x18000485c`
- `0x180004e58`
- `0x180005384`
- `0x180005804`
- `0x180005934`

## callees

- `0x180001e7c`

## pseudocode

```c
__int64 __fastcall CheckResult(int a1)
{
  __int64 result; // rax

  if ( a1 >= 0 )
    return 0;
  if ( a1 == -2147024882 )
    return 264;
  if ( a1 == -2147024809 )
    return 282;
  if ( (unsigned int)(a1 + 2147024894) <= 1 || a1 == -2147220970 || (unsigned int)(a1 + 2147287038) <= 1 )
    return 275;
  if ( a1 == -2147221164 )
    return 296;
  result = 6;
  if ( a1 != -2147220907 && a1 != -2147220903 )
    return 277;
  return result;
}

```

## disassembly

```asm
0x180001e7c  test    ecx, ecx
0x180001e7e  jns     short loc_180001EEA
0x180001e80  cmp     ecx, 8007000Eh
0x180001e86  jnz     short loc_180001E8E
0x180001e88  mov     eax, 108h
0x180001e8d  retn
0x180001e8e  cmp     ecx, 80070057h
0x180001e94  jnz     short loc_180001E9C
0x180001e96  mov     eax, 11Ah
0x180001e9b  retn
0x180001e9c  lea     eax, [rcx+7FF8FFFEh]
0x180001ea2  cmp     eax, 1
0x180001ea5  jbe     short loc_180001EE4
0x180001ea7  cmp     ecx, 80040216h
0x180001ead  jz      short loc_180001EE4
0x180001eaf  lea     eax, [rcx+7FFCFFFEh]
0x180001eb5  cmp     eax, 1
0x180001eb8  jbe     short loc_180001EE4
0x180001eba  cmp     ecx, 80040154h
0x180001ec0  jnz     short loc_180001EC8
0x180001ec2  mov     eax, 128h
0x180001ec7  retn
0x180001ec8  mov     eax, 6
0x180001ecd  cmp     ecx, 80040255h
0x180001ed3  jz      short locret_180001EEC
0x180001ed5  cmp     ecx, 80040259h
0x180001edb  mov     edx, 115h
0x180001ee0  cmovnz  eax, edx
0x180001ee3  retn
0x180001ee4  mov     eax, 113h
0x180001ee9  retn
0x180001eea  xor     eax, eax
0x180001eec  retn
```
