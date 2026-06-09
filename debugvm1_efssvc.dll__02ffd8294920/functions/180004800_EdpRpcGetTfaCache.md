# EdpRpcGetTfaCache

- ea: `0x180004800`
- end: `0x1800048a4`
- name: `EdpRpcGetTfaCache`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180003604`
- `0x1800036a0`
- `0x180003828`
- `0x180004800`
- `0x18000c392`

## import_xrefs

- `EFSCORE!EdpDllGetTfaCache` at `0x18000485e`
- `EFSCORE!EdpDllGetTfaCache` at `0x18000485e`

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
0x180004800  mov     [rsp+arg_0], rbx
0x180004805  push    rdi
0x180004806  sub     rsp, 0A0h
0x18000480d  mov     rdi, rdx
0x180004810  lea     rcx, [rsp+0A8h+var_78]; void *
0x180004815  xor     edx, edx; Val
0x180004817  lea     r8d, [rdx+70h]; Size
0x18000481b  call    memset_0
0x180004820  test    rdi, rdi
0x180004823  jnz     short loc_18000482C
0x180004825  mov     ebx, 80004003h
0x18000482a  jmp     short loc_180004891
0x18000482c  lea     rcx, [rsp+0A8h+var_78]
0x180004831  call    EdpBeginLocalOnlyRpcCall
0x180004836  mov     ebx, eax
0x180004838  test    eax, eax
0x18000483a  jns     short loc_18000485B
0x18000483c  mov     r9d, 6
0x180004842  mov     [rsp+0A8h+var_88], 111Ch
0x18000484a  mov     r8d, eax
0x18000484d  lea     rdx, EFS_API_ERROR
0x180004854  call    fnEfsLogTrace1
0x180004859  jmp     short loc_180004891
0x18000485b  mov     rcx, rdi
0x18000485e  call    cs:__imp_EdpDllGetTfaCache
0x180004864  mov     ebx, eax
0x180004866  test    eax, eax
0x180004868  jns     short loc_180004887
0x18000486a  mov     r9d, 6
0x180004870  mov     [rsp+0A8h+var_88], 1124h
0x180004878  mov     r8d, eax
0x18000487b  lea     rdx, EFS_API_ERROR
0x180004882  call    fnEfsLogTrace1
0x180004887  lea     rcx, [rsp+0A8h+var_78]
0x18000488c  call    EdpCleanupLocalOnlyRpcCall
0x180004891  mov     eax, ebx
0x180004893  mov     rbx, [rsp+0A8h+arg_0]
0x18000489b  add     rsp, 0A0h
0x1800048a2  pop     rdi
0x1800048a3  retn
```
