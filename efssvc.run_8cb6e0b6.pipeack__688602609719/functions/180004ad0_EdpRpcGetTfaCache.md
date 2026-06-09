# EdpRpcGetTfaCache

- ea: `0x180004ad0`
- end: `0x180004b7b`
- name: `EdpRpcGetTfaCache`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800037b8`
- `0x180003864`
- `0x180003a24`
- `0x180004ad0`
- `0x18000d192`

## import_xrefs

- `EFSCORE!EdpDllGetTfaCache` at `0x180004b2e`
- `EFSCORE!EdpDllGetTfaCache` at `0x180004b2e`

## pseudocode

```c
__int64 __fastcall EdpRpcGetTfaCache(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // ecx
  int TfaCache; // eax
  int v7; // ecx
  _BYTE v9[120]; // [rsp+30h] [rbp-78h] BYREF

  memset_0(v9, 0, 0x70u);
  if ( a2 )
  {
    v4 = EdpBeginLocalOnlyRpcCall((__int64)v9);
    v3 = v4;
    if ( v4 >= 0 )
    {
      TfaCache = EdpDllGetTfaCache(a2);
      v3 = TfaCache;
      if ( TfaCache < 0 )
        fnEfsLogTrace1(v7, (unsigned int)EFS_API_ERROR, TfaCache, 6, 36);
      EdpCleanupLocalOnlyRpcCall((__int64)v9);
    }
    else
    {
      fnEfsLogTrace1(v5, (unsigned int)EFS_API_ERROR, v4, 6, 28);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x180004ad0  mov     [rsp+arg_0], rbx
0x180004ad5  push    rdi
0x180004ad6  sub     rsp, 0A0h
0x180004add  mov     rdi, rdx
0x180004ae0  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004ae5  xor     edx, edx; Val
0x180004ae7  lea     r8d, [rdx+70h]; Size
0x180004aeb  call    memset_0
0x180004af0  test    rdi, rdi
0x180004af3  jnz     short loc_180004AFC
0x180004af5  mov     ebx, 80004003h
0x180004afa  jmp     short loc_180004B67
0x180004afc  lea     rcx, [rsp+0A8h+var_78]
0x180004b01  call    EdpBeginLocalOnlyRpcCall
0x180004b06  mov     ebx, eax
0x180004b08  test    eax, eax
0x180004b0a  jns     short loc_180004B2B
0x180004b0c  mov     r9d, 6
0x180004b12  mov     [rsp+0A8h+var_88], 111Ch
0x180004b1a  mov     r8d, eax
0x180004b1d  lea     rdx, EFS_API_ERROR
0x180004b24  call    fnEfsLogTrace1
0x180004b29  jmp     short loc_180004B67
0x180004b2b  mov     rcx, rdi
0x180004b2e  call    cs:__imp_EdpDllGetTfaCache
0x180004b35  nop     dword ptr [rax+rax+00h]
0x180004b3a  mov     ebx, eax
0x180004b3c  test    eax, eax
0x180004b3e  jns     short loc_180004B5D
0x180004b40  mov     r9d, 6
0x180004b46  mov     [rsp+0A8h+var_88], 1124h
0x180004b4e  mov     r8d, eax
0x180004b51  lea     rdx, EFS_API_ERROR
0x180004b58  call    fnEfsLogTrace1
0x180004b5d  lea     rcx, [rsp+0A8h+var_78]
0x180004b62  call    EdpCleanupLocalOnlyRpcCall
0x180004b67  mov     eax, ebx
0x180004b69  mov     rbx, [rsp+0A8h+arg_0]
0x180004b71  add     rsp, 0A0h
0x180004b78  pop     rdi
0x180004b79  retn
```
