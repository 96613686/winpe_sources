# OefsRpcCheckSupport

- ea: `0x180007bb0`
- end: `0x180007c6f`
- name: `OefsRpcCheckSupport`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180007bb0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EfsDllOefsCheckSupportByFilePath` at `0x180007c25`
- `EFSCORE!EfsDllOefsCheckSupportByFilePath` at `0x180007c25`

## pseudocode

```c
__int64 __fastcall OefsRpcCheckSupport(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  signed int v6; // eax
  __int64 v7; // rcx
  signed int v8; // eax
  __int64 v9; // rcx
  _BYTE v11[112]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v11, 0, sizeof(v11));
  if ( a2 )
  {
    if ( a3 )
    {
      v6 = EdpBeginLocalOnlyRpcCall((__int64)v11);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v8 = EfsDllOefsCheckSupportByFilePath(a2, a3);
        v5 = v8;
        if ( v8 < 0 )
          fnEfsLogTrace1(v9, (__int64)EFS_API_ERROR, v8, 6, 221);
        EdpCleanupLocalOnlyRpcCall((__int64)v11);
      }
      else
      {
        fnEfsLogTrace1(v7, (__int64)EFS_API_ERROR, v6, 6, 213);
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180007bb0  mov     [rsp+arg_0], rbx
0x180007bb5  mov     [rsp+arg_8], rsi
0x180007bba  push    rdi
0x180007bbb  sub     rsp, 0A0h
0x180007bc2  mov     rsi, rdx
0x180007bc5  lea     rcx, [rsp+0A8h+var_78]; void *
0x180007bca  xor     edx, edx; Val
0x180007bcc  mov     rdi, r8
0x180007bcf  lea     r8d, [rdx+70h]; Size
0x180007bd3  call    memset_0
0x180007bd8  test    rsi, rsi
0x180007bdb  jnz     short loc_180007BE4
0x180007bdd  mov     ebx, 80070057h
0x180007be2  jmp     short loc_180007C58
0x180007be4  test    rdi, rdi
0x180007be7  jnz     short loc_180007BF0
0x180007be9  mov     ebx, 80004003h
0x180007bee  jmp     short loc_180007C58
0x180007bf0  lea     rcx, [rsp+0A8h+var_78]
0x180007bf5  call    EdpBeginLocalOnlyRpcCall
0x180007bfa  mov     ebx, eax
0x180007bfc  test    eax, eax
0x180007bfe  jns     short loc_180007C1F
0x180007c00  mov     r9d, 6
0x180007c06  mov     [rsp+0A8h+var_88], 11D5h
0x180007c0e  mov     r8d, eax
0x180007c11  lea     rdx, EFS_API_ERROR
0x180007c18  call    fnEfsLogTrace1
0x180007c1d  jmp     short loc_180007C58
0x180007c1f  mov     rdx, rdi
0x180007c22  mov     rcx, rsi
0x180007c25  call    cs:__imp_EfsDllOefsCheckSupportByFilePath
0x180007c2b  mov     ebx, eax
0x180007c2d  test    eax, eax
0x180007c2f  jns     short loc_180007C4E
0x180007c31  mov     r9d, 6
0x180007c37  mov     [rsp+0A8h+var_88], 11DDh
0x180007c3f  mov     r8d, eax
0x180007c42  lea     rdx, EFS_API_ERROR
0x180007c49  call    fnEfsLogTrace1
0x180007c4e  lea     rcx, [rsp+0A8h+var_78]
0x180007c53  call    EdpCleanupLocalOnlyRpcCall
0x180007c58  lea     r11, [rsp+0A8h+var_8]
0x180007c60  mov     eax, ebx
0x180007c62  mov     rbx, [r11+10h]
0x180007c66  mov     rsi, [r11+18h]
0x180007c6a  mov     rsp, r11
0x180007c6d  pop     rdi
0x180007c6e  retn
```
