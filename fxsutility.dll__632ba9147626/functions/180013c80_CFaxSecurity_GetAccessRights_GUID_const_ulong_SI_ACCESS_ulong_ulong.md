# CFaxSecurity::GetAccessRights(_GUID const *,ulong,_SI_ACCESS * *,ulong *,ulong *)

- ea: `0x180013c80`
- end: `0x180013cbc`
- name: `?GetAccessRights@CFaxSecurity@@UEAAJPEBU_GUID@@KPEAPEAU_SI_ACCESS@@PEAK2@Z`
- size: `60`
- prototype: `__int64 __fastcall(CFaxSecurity *__hidden this, const struct _GUID *, unsigned int, struct _SI_ACCESS **, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::GetAccessRights(
        CFaxSecurity *this,
        const struct _GUID *a2,
        int a3,
        struct _SI_ACCESS **a4,
        unsigned int *a5,
        unsigned int *a6)
{
  struct _SI_ACCESS *v6; // rax
  unsigned int v7; // ecx

  v6 = (struct _SI_ACCESS *)&off_18001E0A0;
  if ( a3 )
    v6 = (struct _SI_ACCESS *)&off_18001E100;
  v7 = 3;
  *a4 = v6;
  if ( a3 )
    v7 = 13;
  *a5 = v7;
  *a6 = a3 != 0;
  return 0;
}

```

## disassembly

```asm
0x180013c80  test    r8d, r8d
0x180013c83  lea     rcx, off_18001E100
0x180013c8a  lea     rax, off_18001E0A0
0x180013c91  cmovnz  rax, rcx
0x180013c95  mov     ecx, 3
0x180013c9a  mov     [r9], rax
0x180013c9d  lea     eax, [rcx+0Ah]
0x180013ca0  cmovnz  ecx, eax
0x180013ca3  mov     rax, [rsp+arg_20]
0x180013ca8  mov     [rax], ecx
0x180013caa  xor     ecx, ecx
0x180013cac  mov     rax, [rsp+arg_28]
0x180013cb1  test    r8d, r8d
0x180013cb4  setnz   cl
0x180013cb7  mov     [rax], ecx
0x180013cb9  xor     eax, eax
0x180013cbb  retn
```
