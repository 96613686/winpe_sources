# CSslUserContext::GetReadWriteApplicationTrafficSecrets(unsigned __int64 *,unsigned __int64 *)

- ea: `0x14000afb0`
- end: `0x14000afc9`
- name: `?GetReadWriteApplicationTrafficSecrets@CSslUserContext@@UEAAXPEA_K0@Z`
- size: `25`
- prototype: `void __fastcall(CSslUserContext *__hidden this, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000afb0`

## pseudocode

```c
void __fastcall CSslUserContext::GetReadWriteApplicationTrafficSecrets(
        CSslUserContext *this,
        unsigned __int64 *a2,
        unsigned __int64 *a3)
{
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
}

```

## disassembly

```asm
0x14000afb0  test    rdx, rdx
0x14000afb3  jz      short loc_14000AFBC
0x14000afb5  mov     qword ptr [rdx], 0
0x14000afbc  test    r8, r8
0x14000afbf  jz      short locret_14000AFC8
0x14000afc1  mov     qword ptr [r8], 0
0x14000afc8  retn
```
