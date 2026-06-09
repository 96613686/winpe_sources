# EdpRpcDplUserUnlockComplete

- ea: `0x180004470`
- end: `0x18000452b`
- name: `EdpRpcDplUserUnlockComplete`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004470`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllDplUserUnlockComplete` at `0x1800044dc`
- `EFSCORE!EdpDllDplUserUnlockComplete` at `0x1800044dc`

## pseudocode

```c
__int64 __fastcall EdpRpcDplUserUnlockComplete(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // ecx
  _BYTE v13[152]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v13, 0, 0x70u);
  if ( a2 && a4 )
  {
    v7 = EdpBeginLocalOnlyRpcCall((__int64)v13);
    v9 = v7;
    if ( v7 >= 0 )
    {
      v10 = EdpDllDplUserUnlockComplete(v13, a2, a3, a4);
      v9 = v10;
      if ( v10 < 0 )
        fnEfsLogTrace1(v11, (unsigned int)EFS_API_ERROR, v10, 6, 49);
      EdpCleanupLocalOnlyRpcCall((__int64)v13);
    }
    else
    {
      fnEfsLogTrace1(v8, (unsigned int)EFS_API_ERROR, v7, 6, 38);
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
0x180004470  push    rbx
0x180004472  push    rbp
0x180004473  push    rsi
0x180004474  push    rdi
0x180004475  sub     rsp, 0A8h
0x18000447c  mov     rsi, rdx
0x18000447f  lea     rcx, [rsp+0C8h+var_98]; void *
0x180004484  xor     edx, edx; Val
0x180004486  mov     ebp, r8d
0x180004489  mov     rdi, r9
0x18000448c  lea     r8d, [rdx+70h]; Size
0x180004490  call    memset_0
0x180004495  test    rsi, rsi
0x180004498  jz      short loc_180004517
0x18000449a  test    rdi, rdi
0x18000449d  jz      short loc_180004517
0x18000449f  lea     rcx, [rsp+0C8h+var_98]
0x1800044a4  call    EdpBeginLocalOnlyRpcCall
0x1800044a9  mov     ebx, eax
0x1800044ab  test    eax, eax
0x1800044ad  jns     short loc_1800044CE
0x1800044af  mov     r9d, 6
0x1800044b5  mov     [rsp+0C8h+var_A8], 0E26h
0x1800044bd  mov     r8d, eax
0x1800044c0  lea     rdx, EFS_API_ERROR
0x1800044c7  call    fnEfsLogTrace1
0x1800044cc  jmp     short loc_18000451C
0x1800044ce  mov     r9, rdi
0x1800044d1  lea     rcx, [rsp+0C8h+var_98]
0x1800044d6  mov     r8d, ebp
0x1800044d9  mov     rdx, rsi
0x1800044dc  call    cs:__imp_EdpDllDplUserUnlockComplete
0x1800044e3  nop     dword ptr [rax+rax+00h]
0x1800044e8  mov     ebx, eax
0x1800044ea  test    eax, eax
0x1800044ec  jns     short loc_18000450B
0x1800044ee  mov     r9d, 6
0x1800044f4  mov     [rsp+0C8h+var_A8], 0E31h
0x1800044fc  mov     r8d, eax
0x1800044ff  lea     rdx, EFS_API_ERROR
0x180004506  call    fnEfsLogTrace1
0x18000450b  lea     rcx, [rsp+0C8h+var_98]
0x180004510  call    EdpCleanupLocalOnlyRpcCall
0x180004515  jmp     short loc_18000451C
0x180004517  mov     ebx, 80070057h
0x18000451c  mov     eax, ebx
0x18000451e  add     rsp, 0A8h
0x180004525  pop     rdi
0x180004526  pop     rsi
0x180004527  pop     rbp
0x180004528  pop     rbx
0x180004529  retn
```
