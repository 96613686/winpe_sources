# CIVIAudioFilter::GetClassID(_GUID *)

- ea: `0x18000e600`
- end: `0x18000e616`
- name: `?GetClassID@CIVIAudioFilter@@UEAAJPEAU_GUID@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, struct _GUID *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000e620`

## callees

- `0x18000e600`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetClassID(CIVIAudioFilter *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = *(struct _GUID *)((char *)this + 40);
  return result;
}

```

## disassembly

```asm
0x18000e600  test    rdx, rdx
0x18000e603  jnz     short loc_18000E60C
0x18000e605  mov     eax, 80004003h
0x18000e60a  retn
0x18000e60c  movups  xmm0, xmmword ptr [rcx+28h]
0x18000e610  xor     eax, eax
0x18000e612  movups  xmmword ptr [rdx], xmm0
0x18000e615  retn
```
