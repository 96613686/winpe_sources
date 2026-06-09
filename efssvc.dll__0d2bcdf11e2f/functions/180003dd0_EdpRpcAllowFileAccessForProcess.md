# EdpRpcAllowFileAccessForProcess

- ea: `0x180003dd0`
- end: `0x180003e80`
- name: `EdpRpcAllowFileAccessForProcess`
- size: `176`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180003dd0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllAllowFileAccessForProcess` at `0x180003e38`
- `EFSCORE!EdpDllAllowFileAccessForProcess` at `0x180003e38`

## pseudocode

```c
__int64 __fastcall EdpRpcAllowFileAccessForProcess(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  unsigned int v7; // ebx
  signed int v8; // eax
  __int64 v9; // rcx
  signed int v10; // eax
  __int64 v11; // rcx
  _BYTE v13[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v13, 0, 0x70u);
  if ( a2 )
  {
    v8 = EdpBeginLocalOnlyRpcCall((__int64)v13);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v10 = EdpDllAllowFileAccessForProcess(a2, a3, a4);
      v7 = v10;
      if ( v10 < 0 )
        fnEfsLogTrace1(v11, (__int64)EFS_API_ERROR, v10, 6, 237);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v8, 6, 227);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x180003dd0  push    rbx
0x180003dd2  push    rbp
0x180003dd3  push    rsi
0x180003dd4  push    rdi
0x180003dd5  sub     rsp, 0A8h
0x180003ddc  mov     rdi, rdx
0x180003ddf  lea     rcx, [rsp+0C8h+var_98]; void *
0x180003de4  xor     edx, edx; Val
0x180003de6  mov     ebp, r8d
0x180003de9  mov     rsi, r9
0x180003dec  lea     r8d, [rdx+70h]; Size
0x180003df0  call    memset_0
0x180003df5  test    rdi, rdi
0x180003df8  jnz     short loc_180003E01
0x180003dfa  mov     ebx, 80070057h
0x180003dff  jmp     short loc_180003E71
0x180003e01  lea     rcx, [rsp+0C8h+var_98]
0x180003e06  call    EdpBeginLocalOnlyRpcCall
0x180003e0b  mov     ebx, eax
0x180003e0d  test    eax, eax
0x180003e0f  jns     short loc_180003E30
0x180003e11  mov     r9d, 6
0x180003e17  mov     [rsp+0C8h+var_A8], 10E3h
0x180003e1f  mov     r8d, eax
0x180003e22  lea     rdx, EFS_API_ERROR
0x180003e29  call    fnEfsLogTrace1
0x180003e2e  jmp     short loc_180003E71
0x180003e30  mov     r8, rsi
0x180003e33  mov     edx, ebp
0x180003e35  mov     rcx, rdi
0x180003e38  call    cs:__imp_EdpDllAllowFileAccessForProcess
0x180003e3f  nop     dword ptr [rax+rax+00h]
0x180003e44  mov     ebx, eax
0x180003e46  test    eax, eax
0x180003e48  jns     short loc_180003E67
0x180003e4a  mov     r9d, 6
0x180003e50  mov     [rsp+0C8h+var_A8], 10EDh
0x180003e58  mov     r8d, eax
0x180003e5b  lea     rdx, EFS_API_ERROR
0x180003e62  call    fnEfsLogTrace1
0x180003e67  lea     rcx, [rsp+0C8h+var_98]
0x180003e6c  call    EdpCleanupLocalOnlyRpcCall
0x180003e71  mov     eax, ebx
0x180003e73  add     rsp, 0A8h
0x180003e7a  pop     rdi
0x180003e7b  pop     rsi
0x180003e7c  pop     rbp
0x180003e7d  pop     rbx
0x180003e7e  retn
```
