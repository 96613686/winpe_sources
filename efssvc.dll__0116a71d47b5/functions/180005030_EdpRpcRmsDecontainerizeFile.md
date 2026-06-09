# EdpRpcRmsDecontainerizeFile

- ea: `0x180005030`
- end: `0x1800050e9`
- name: `EdpRpcRmsDecontainerizeFile`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180005030`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllRmsDecontainerizeFile` at `0x1800050a1`
- `EFSCORE!EdpDllRmsDecontainerizeFile` at `0x1800050a1`

## pseudocode

```c
__int64 __fastcall EdpRpcRmsDecontainerizeFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ecx
  _BYTE v13[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v13, 0, 0x70u);
  if ( a2 && a3 && a4 )
  {
    v7 = EdpBeginLocalOnlyRpcCall((__int64)v13);
    v9 = v7;
    if ( v7 >= 0 )
    {
      v10 = EdpDllRmsDecontainerizeFile(v13, a2, a3, a4);
      v9 = v10;
      if ( v10 < 0 )
        fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, v10, 6, 171);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 160);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x180005030  push    rbx
0x180005032  push    rbp
0x180005033  push    rsi
0x180005034  push    rdi
0x180005035  sub     rsp, 0A8h
0x18000503c  mov     rbp, rdx
0x18000503f  lea     rcx, [rsp+0C8h+var_98]; void *
0x180005044  xor     edx, edx; Val
0x180005046  mov     rsi, r8
0x180005049  mov     rdi, r9
0x18000504c  lea     r8d, [rdx+70h]; Size
0x180005050  call    memset_0
0x180005055  test    rbp, rbp
0x180005058  jz      short loc_1800050D6
0x18000505a  test    rsi, rsi
0x18000505d  jz      short loc_1800050D6
0x18000505f  test    rdi, rdi
0x180005062  jz      short loc_1800050D6
0x180005064  lea     rcx, [rsp+0C8h+var_98]
0x180005069  call    EdpBeginLocalOnlyRpcCall
0x18000506e  mov     ebx, eax
0x180005070  test    eax, eax
0x180005072  jns     short loc_180005093
0x180005074  mov     r9d, 6
0x18000507a  mov     [rsp+0C8h+var_A8], 10A0h
0x180005082  mov     r8d, eax
0x180005085  lea     rdx, EFS_API_ERROR
0x18000508c  call    fnEfsLogTrace1
0x180005091  jmp     short loc_1800050DB
0x180005093  mov     r9, rdi
0x180005096  lea     rcx, [rsp+0C8h+var_98]
0x18000509b  mov     r8, rsi
0x18000509e  mov     rdx, rbp
0x1800050a1  call    cs:__imp_EdpDllRmsDecontainerizeFile
0x1800050a7  mov     ebx, eax
0x1800050a9  test    eax, eax
0x1800050ab  jns     short loc_1800050CA
0x1800050ad  mov     r9d, 6
0x1800050b3  mov     [rsp+0C8h+var_A8], 10ABh
0x1800050bb  mov     r8d, eax
0x1800050be  lea     rdx, EFS_API_ERROR
0x1800050c5  call    fnEfsLogTrace1
0x1800050ca  lea     rcx, [rsp+0C8h+var_98]
0x1800050cf  call    EdpCleanupLocalOnlyRpcCall
0x1800050d4  jmp     short loc_1800050DB
0x1800050d6  mov     ebx, 80070057h
0x1800050db  mov     eax, ebx
0x1800050dd  add     rsp, 0A8h
0x1800050e4  pop     rdi
0x1800050e5  pop     rsi
0x1800050e6  pop     rbp
0x1800050e7  pop     rbx
0x1800050e8  retn
```
