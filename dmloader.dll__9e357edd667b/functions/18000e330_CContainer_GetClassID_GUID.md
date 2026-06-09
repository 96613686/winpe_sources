# CContainer::GetClassID(_GUID *)

- ea: `0x18000e330`
- end: `0x18000e358`
- name: `?GetClassID@CContainer@@UEAAJPEAU_GUID@@@Z`
- size: `40`
- prototype: `__int64 __fastcall(CContainer *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000e330`

## pseudocode

```c
__int64 __fastcall CContainer::GetClassID(CContainer *this, struct _GUID *a2)
{
  __int64 result; // rax

  if ( *((_BYTE *)this + 856) )
    return 142086678;
  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = CLSID_DirectMusicContainer;
  return result;
}

```

## disassembly

```asm
0x18000e330  cmp     byte ptr [rcx+358h], 0
0x18000e337  jz      short loc_18000E33F
0x18000e339  mov     eax, 8781216h
0x18000e33e  retn
0x18000e33f  test    rdx, rdx
0x18000e342  jz      short loc_18000E352
0x18000e344  movups  xmm0, xmmword ptr cs:CLSID_DirectMusicContainer.Data1
0x18000e34b  xor     eax, eax
0x18000e34d  movdqu  xmmword ptr [rdx], xmm0
0x18000e351  retn
0x18000e352  mov     eax, 80004003h
0x18000e357  retn
```
