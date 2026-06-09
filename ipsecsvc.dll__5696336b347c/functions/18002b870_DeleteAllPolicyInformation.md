# DeleteAllPolicyInformation

- ea: `0x18002b870`
- end: `0x18002b8c7`
- name: `DeleteAllPolicyInformation`
- size: `87`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c564`

## callees

- `0x18000f638`
- `0x180027758`
- `0x1800280f4`
- `0x180028a8c`
- `0x18002902c`
- `0x180029cac`
- `0x18002b870`
- `0x18002ffe0`

## pseudocode

```c
__int64 DeleteAllPolicyInformation()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  PADeleteAllMMFilters();
  PADeleteAllMMAuthMethods();
  PADeleteAllMMPolicies();
  PADeleteAllTxFilters();
  PADeleteAllTnFilters();
  PADeleteAllQMPolicies();
  return 0;
}

```

## disassembly

```asm
0x18002b870  sub     rsp, 28h
0x18002b874  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b87b  lea     rax, WPP_GLOBAL_Control
0x18002b882  cmp     rcx, rax
0x18002b885  jz      short loc_18002B8A2
0x18002b887  test    byte ptr [rcx+1Ch], 4
0x18002b88b  jz      short loc_18002B8A2
0x18002b88d  mov     rcx, [rcx+10h]
0x18002b891  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002b898  mov     edx, 55h ; 'U'
0x18002b89d  call    WPP_SF_
0x18002b8a2  call    PADeleteAllMMFilters
0x18002b8a7  call    PADeleteAllMMAuthMethods
0x18002b8ac  call    PADeleteAllMMPolicies
0x18002b8b1  call    PADeleteAllTxFilters
0x18002b8b6  call    PADeleteAllTnFilters
0x18002b8bb  call    PADeleteAllQMPolicies
0x18002b8c0  xor     eax, eax
0x18002b8c2  add     rsp, 28h
0x18002b8c6  retn
```
