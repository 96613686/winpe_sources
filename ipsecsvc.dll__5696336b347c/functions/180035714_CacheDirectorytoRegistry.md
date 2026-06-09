# CacheDirectorytoRegistry

- ea: `0x180035714`
- end: `0x1800357be`
- name: `CacheDirectorytoRegistry`
- size: `170`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002b688`
- `0x18002cf74`
- `0x18002d64c`

## callees

- `0x18000e510`
- `0x180035714`
- `0x1800366c4`
- `0x180036f00`
- `0x180038908`
- `0x180042e20`

## pseudocode

```c
__int64 __fastcall CacheDirectorytoRegistry(__int64 a1)
{
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  LPVOID lpMem; // [rsp+38h] [rbp+10h] BYREF

  lpMem = 0;
  DeleteRegistryCache();
  v2 = CloneDirectoryPolicyObject(a1, &lpMem);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_10;
    v4 = 10;
    goto LABEL_9;
  }
  v2 = PersistRegistryObject((__int64)lpMem);
  if ( !v2 )
    goto LABEL_11;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v4 = 11;
LABEL_9:
    WPP_SF_d(v3[2], v4, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v2);
  }
LABEL_10:
  DeleteRegistryCache();
LABEL_11:
  if ( lpMem )
    FreeIpsecPolicyObject(lpMem);
  return v2;
}

```

## disassembly

```asm
0x180035714  push    rbx
0x180035716  sub     rsp, 20h
0x18003571a  mov     rbx, rcx
0x18003571d  mov     [rsp+28h+lpMem], 0
0x180035726  call    DeleteRegistryCache
0x18003572b  lea     rdx, [rsp+28h+lpMem]
0x180035730  mov     rcx, rbx
0x180035733  call    CloneDirectoryPolicyObject
0x180035738  mov     ebx, eax
0x18003573a  test    eax, eax
0x18003573c  jz      short loc_18003575E
0x18003573e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035745  lea     rax, WPP_GLOBAL_Control
0x18003574c  cmp     rcx, rax
0x18003574f  jz      short loc_18003579F
0x180035751  test    byte ptr [rcx+1Ch], 10h
0x180035755  jz      short loc_18003579F
0x180035757  mov     edx, 0Ah
0x18003575c  jmp     short loc_18003578C
0x18003575e  mov     rcx, [rsp+28h+lpMem]
0x180035763  call    PersistRegistryObject
0x180035768  mov     ebx, eax
0x18003576a  test    eax, eax
0x18003576c  jz      short loc_1800357A4
0x18003576e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035775  lea     rax, WPP_GLOBAL_Control
0x18003577c  cmp     rcx, rax
0x18003577f  jz      short loc_18003579F
0x180035781  test    byte ptr [rcx+1Ch], 10h
0x180035785  jz      short loc_18003579F
0x180035787  mov     edx, 0Bh
0x18003578c  mov     rcx, [rcx+10h]
0x180035790  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180035797  mov     r9d, ebx
0x18003579a  call    WPP_SF_d
0x18003579f  call    DeleteRegistryCache
0x1800357a4  cmp     [rsp+28h+lpMem], 0
0x1800357aa  jz      short loc_1800357B6
0x1800357ac  mov     rcx, [rsp+28h+lpMem]; lpMem
0x1800357b1  call    FreeIpsecPolicyObject
0x1800357b6  mov     eax, ebx
0x1800357b8  add     rsp, 20h
0x1800357bc  pop     rbx
0x1800357bd  retn
```
