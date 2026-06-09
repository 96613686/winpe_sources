# EdpRpcGetLockSessionUnwrappedKey

- ea: `0x1800044f0`
- end: `0x180004621`
- name: `EdpRpcGetLockSessionUnwrappedKey`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x1800044f0`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllGetLockSessionUnwrappedKey` at `0x1800045ca`
- `EFSCORE!EdpDllGetLockSessionUnwrappedKey` at `0x1800045ca`

## pseudocode

```c
__int64 __fastcall EdpRpcGetLockSessionUnwrappedKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8)
{
  signed int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  signed int LockSessionUnwrappedKey; // eax
  __int64 v15; // rcx
  _BYTE v17[184]; // [rsp+40h] [rbp-B8h] BYREF

  memset_0(v17, 0, 0x70u);
  if ( a2 && a3 && a4 && a5 && a6 )
  {
    if ( a7 && a8 )
    {
      v11 = EdpBeginLocalOnlyRpcCall((__int64)v17);
      v13 = v11;
      if ( v11 >= 0 )
      {
        LockSessionUnwrappedKey = EdpDllGetLockSessionUnwrappedKey(v17, a2, a3, a4, a5, a6, a7, a8);
        v13 = LockSessionUnwrappedKey;
        if ( LockSessionUnwrappedKey < 0 )
          fnEfsLogTrace1(v15, (__int64)EFS_API_ERROR, LockSessionUnwrappedKey, 6, 140);
        EdpCleanupLocalOnlyRpcCall((__int64)v17);
      }
      else
      {
        fnEfsLogTrace1(v12, (__int64)EFS_API_ERROR, v11, 6, 125);
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
  return v13;
}

```

## disassembly

```asm
0x1800044f0  push    rbx
0x1800044f2  push    rbp
0x1800044f3  push    rsi
0x1800044f4  push    rdi
0x1800044f5  push    r12
0x1800044f7  push    r13
0x1800044f9  push    r14
0x1800044fb  push    r15
0x1800044fd  sub     rsp, 0B8h
0x180004504  mov     r13, rdx
0x180004507  lea     rcx, [rsp+0F8h+var_B8]; void *
0x18000450c  xor     edx, edx; Val
0x18000450e  mov     r12, r8
0x180004511  mov     r15d, r9d
0x180004514  lea     r8d, [rdx+70h]; Size
0x180004518  call    memset_0
0x18000451d  test    r13, r13
0x180004520  jz      loc_180004606
0x180004526  test    r12, r12
0x180004529  jz      loc_180004606
0x18000452f  test    r15d, r15d
0x180004532  jz      loc_180004606
0x180004538  mov     rdi, [rsp+0F8h+arg_20]
0x180004540  test    rdi, rdi
0x180004543  jz      loc_180004606
0x180004549  mov     esi, [rsp+0F8h+arg_28]
0x180004550  test    esi, esi
0x180004552  jz      loc_180004606
0x180004558  mov     rbp, [rsp+0F8h+arg_30]
0x180004560  test    rbp, rbp
0x180004563  jz      loc_1800045FF
0x180004569  mov     r14, [rsp+0F8h+arg_38]
0x180004571  test    r14, r14
0x180004574  jz      loc_1800045FF
0x18000457a  lea     rcx, [rsp+0F8h+var_B8]
0x18000457f  call    EdpBeginLocalOnlyRpcCall
0x180004584  mov     ebx, eax
0x180004586  test    eax, eax
0x180004588  jns     short loc_1800045A9
0x18000458a  mov     r9d, 6
0x180004590  mov     dword ptr [rsp+0F8h+var_D8], 0C7Dh
0x180004598  mov     r8d, eax
0x18000459b  lea     rdx, EFS_API_ERROR
0x1800045a2  call    fnEfsLogTrace1
0x1800045a7  jmp     short loc_18000460B
0x1800045a9  mov     [rsp+0F8h+var_C0], r14
0x1800045ae  lea     rcx, [rsp+0F8h+var_B8]
0x1800045b3  mov     [rsp+0F8h+var_C8], rbp
0x1800045b8  mov     r9d, r15d
0x1800045bb  mov     [rsp+0F8h+var_D0], esi
0x1800045bf  mov     r8, r12
0x1800045c2  mov     rdx, r13
0x1800045c5  mov     [rsp+0F8h+var_D8], rdi
0x1800045ca  call    cs:__imp_EdpDllGetLockSessionUnwrappedKey
0x1800045d0  mov     ebx, eax
0x1800045d2  test    eax, eax
0x1800045d4  jns     short loc_1800045F3
0x1800045d6  mov     r9d, 6
0x1800045dc  mov     dword ptr [rsp+0F8h+var_D8], 0C8Ch
0x1800045e4  mov     r8d, eax
0x1800045e7  lea     rdx, EFS_API_ERROR
0x1800045ee  call    fnEfsLogTrace1
0x1800045f3  lea     rcx, [rsp+0F8h+var_B8]
0x1800045f8  call    EdpCleanupLocalOnlyRpcCall
0x1800045fd  jmp     short loc_18000460B
0x1800045ff  mov     ebx, 80004003h
0x180004604  jmp     short loc_18000460B
0x180004606  mov     ebx, 80070057h
0x18000460b  mov     eax, ebx
0x18000460d  add     rsp, 0B8h
0x180004614  pop     r15
0x180004616  pop     r14
0x180004618  pop     r13
0x18000461a  pop     r12
0x18000461c  pop     rdi
0x18000461d  pop     rsi
0x18000461e  pop     rbp
0x18000461f  pop     rbx
0x180004620  retn
```
