# EdpRpcRmsDecontainerizeFile

- ea: `0x1800053b0`
- end: `0x180005474`
- name: `EdpRpcRmsDecontainerizeFile`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800053b0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllRmsDecontainerizeFile` at `0x180005425`
- `EFSCORE!EdpDllRmsDecontainerizeFile` at `0x180005425`

## pseudocode

```c
__int64 __fastcall EdpRpcRmsDecontainerizeFile(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed int v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // ebx
  signed int v10; // eax
  __int64 v11; // rcx
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
        fnEfsLogTrace1(v11, (__int64)EFS_API_ERROR, v10, 6, 171);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v8, (__int64)EFS_API_ERROR, v7, 6, 160);
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
0x1800053b0  push    rbx
0x1800053b2  push    rbp
0x1800053b3  push    rsi
0x1800053b4  push    rdi
0x1800053b5  sub     rsp, 0A8h
0x1800053bc  mov     rbp, rdx
0x1800053bf  lea     rcx, [rsp+0C8h+var_98]; void *
0x1800053c4  xor     edx, edx; Val
0x1800053c6  mov     rsi, r8
0x1800053c9  mov     rdi, r9
0x1800053cc  lea     r8d, [rdx+70h]; Size
0x1800053d0  call    memset_0
0x1800053d5  test    rbp, rbp
0x1800053d8  jz      loc_180005460
0x1800053de  test    rsi, rsi
0x1800053e1  jz      short loc_180005460
0x1800053e3  test    rdi, rdi
0x1800053e6  jz      short loc_180005460
0x1800053e8  lea     rcx, [rsp+0C8h+var_98]
0x1800053ed  call    EdpBeginLocalOnlyRpcCall
0x1800053f2  mov     ebx, eax
0x1800053f4  test    eax, eax
0x1800053f6  jns     short loc_180005417
0x1800053f8  mov     r9d, 6
0x1800053fe  mov     [rsp+0C8h+var_A8], 10A0h
0x180005406  mov     r8d, eax
0x180005409  lea     rdx, EFS_API_ERROR
0x180005410  call    fnEfsLogTrace1
0x180005415  jmp     short loc_180005465
0x180005417  mov     r9, rdi
0x18000541a  lea     rcx, [rsp+0C8h+var_98]
0x18000541f  mov     r8, rsi
0x180005422  mov     rdx, rbp
0x180005425  call    cs:__imp_EdpDllRmsDecontainerizeFile
0x18000542c  nop     dword ptr [rax+rax+00h]
0x180005431  mov     ebx, eax
0x180005433  test    eax, eax
0x180005435  jns     short loc_180005454
0x180005437  mov     r9d, 6
0x18000543d  mov     [rsp+0C8h+var_A8], 10ABh
0x180005445  mov     r8d, eax
0x180005448  lea     rdx, EFS_API_ERROR
0x18000544f  call    fnEfsLogTrace1
0x180005454  lea     rcx, [rsp+0C8h+var_98]
0x180005459  call    EdpCleanupLocalOnlyRpcCall
0x18000545e  jmp     short loc_180005465
0x180005460  mov     ebx, 80070057h
0x180005465  mov     eax, ebx
0x180005467  add     rsp, 0A8h
0x18000546e  pop     rdi
0x18000546f  pop     rsi
0x180005470  pop     rbp
0x180005471  pop     rbx
0x180005472  retn
```
