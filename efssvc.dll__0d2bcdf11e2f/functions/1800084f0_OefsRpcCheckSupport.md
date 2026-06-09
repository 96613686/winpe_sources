# OefsRpcCheckSupport

- ea: `0x1800084f0`
- end: `0x1800085b6`
- name: `OefsRpcCheckSupport`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x1800084f0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EfsDllOefsCheckSupportByFilePath` at `0x180008565`
- `EFSCORE!EfsDllOefsCheckSupportByFilePath` at `0x180008565`

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
0x1800084f0  mov     [rsp+arg_0], rbx
0x1800084f5  mov     [rsp+arg_8], rsi
0x1800084fa  push    rdi
0x1800084fb  sub     rsp, 0A0h
0x180008502  mov     rsi, rdx
0x180008505  lea     rcx, [rsp+0A8h+var_78]; void *
0x18000850a  xor     edx, edx; Val
0x18000850c  mov     rdi, r8
0x18000850f  lea     r8d, [rdx+70h]; Size
0x180008513  call    memset_0
0x180008518  test    rsi, rsi
0x18000851b  jnz     short loc_180008524
0x18000851d  mov     ebx, 80070057h
0x180008522  jmp     short loc_18000859E
0x180008524  test    rdi, rdi
0x180008527  jnz     short loc_180008530
0x180008529  mov     ebx, 80004003h
0x18000852e  jmp     short loc_18000859E
0x180008530  lea     rcx, [rsp+0A8h+var_78]
0x180008535  call    EdpBeginLocalOnlyRpcCall
0x18000853a  mov     ebx, eax
0x18000853c  test    eax, eax
0x18000853e  jns     short loc_18000855F
0x180008540  mov     r9d, 6
0x180008546  mov     [rsp+0A8h+var_88], 11D5h
0x18000854e  mov     r8d, eax
0x180008551  lea     rdx, EFS_API_ERROR
0x180008558  call    fnEfsLogTrace1
0x18000855d  jmp     short loc_18000859E
0x18000855f  mov     rdx, rdi
0x180008562  mov     rcx, rsi
0x180008565  call    cs:__imp_EfsDllOefsCheckSupportByFilePath
0x18000856c  nop     dword ptr [rax+rax+00h]
0x180008571  mov     ebx, eax
0x180008573  test    eax, eax
0x180008575  jns     short loc_180008594
0x180008577  mov     r9d, 6
0x18000857d  mov     [rsp+0A8h+var_88], 11DDh
0x180008585  mov     r8d, eax
0x180008588  lea     rdx, EFS_API_ERROR
0x18000858f  call    fnEfsLogTrace1
0x180008594  lea     rcx, [rsp+0A8h+var_78]
0x180008599  call    EdpCleanupLocalOnlyRpcCall
0x18000859e  lea     r11, [rsp+0A8h+var_8]
0x1800085a6  mov     eax, ebx
0x1800085a8  mov     rbx, [r11+10h]
0x1800085ac  mov     rsi, [r11+18h]
0x1800085b0  mov     rsp, r11
0x1800085b3  pop     rdi
0x1800085b4  retn
```
