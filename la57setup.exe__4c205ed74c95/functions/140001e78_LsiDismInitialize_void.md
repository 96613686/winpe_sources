# LsiDismInitialize(void)

- ea: `0x140001e78`
- end: `0x140001f2e`
- name: `?LsiDismInitialize@@YAHXZ`
- size: `182`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001ca4`

## callees

- `0x140001e78`

## import_xrefs

- `DismApi!DismShutdown` at `0x140001f10`
- `DismApi!DismShutdown` at `0x140001f10`
- `DismApi!DismCloseSession` at `0x140001f00`
- `DismApi!DismCloseSession` at `0x140001f00`
- `DismApi!DismOpenSession` at `0x140001ec4`
- `DismApi!DismOpenSession` at `0x140001ec4`
- `DismApi!DismInitialize` at `0x140001e9f`
- `DismApi!DismInitialize` at `0x140001e9f`

## pseudocode

```c
__int64 LsiDismInitialize(void)
{
  int v0; // ecx
  __int64 v1; // rcx
  unsigned int v3; // [rsp+30h] [rbp+8h] BYREF

  v0 = LsiDismState;
  v3 = 0;
  if ( LsiDismState != 2 )
  {
    if ( !LsiDismState )
    {
      if ( (int)DismInitialize(2, 0, 0) < 0
        || (LsiDismState = 1, (int)DismOpenSession(L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}", 0, 0, &v3) < 0) )
      {
        v0 = LsiDismState;
      }
      else
      {
        v0 = 2;
        LsiDismState = 2;
        LsiDismSession = v3;
      }
    }
    if ( v0 != 2 )
    {
      v1 = (unsigned int)(v0 - 1);
      if ( (_DWORD)v1 )
      {
        if ( (_DWORD)v1 != 1 )
          return 0;
        DismCloseSession(LsiDismSession);
        LsiDismSession = 0;
      }
      DismShutdown(v1);
      LsiDismState = 0;
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140001e78  sub     rsp, 28h
0x140001e7c  mov     ecx, cs:?LsiDismState@@3W4_LSI_DISM_STATE@@A; _LSI_DISM_STATE LsiDismState
0x140001e82  mov     [rsp+28h+arg_0], 0
0x140001e8a  cmp     ecx, 2
0x140001e8d  jz      loc_140001F24
0x140001e93  test    ecx, ecx
0x140001e95  jnz     short loc_140001EEB
0x140001e97  xor     edx, edx
0x140001e99  xor     r8d, r8d
0x140001e9c  lea     ecx, [rdx+2]
0x140001e9f  call    cs:__imp_DismInitialize
0x140001ea5  test    eax, eax
0x140001ea7  js      short loc_140001EE5
0x140001ea9  lea     r9, [rsp+28h+arg_0]
0x140001eae  mov     cs:?LsiDismState@@3W4_LSI_DISM_STATE@@A, 1; _LSI_DISM_STATE LsiDismState
0x140001eb8  xor     r8d, r8d
0x140001ebb  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x140001ec2  xor     edx, edx
0x140001ec4  call    cs:__imp_DismOpenSession
0x140001eca  test    eax, eax
0x140001ecc  js      short loc_140001EE5
0x140001ece  mov     eax, [rsp+28h+arg_0]
0x140001ed2  mov     ecx, 2
0x140001ed7  mov     cs:?LsiDismState@@3W4_LSI_DISM_STATE@@A, ecx; _LSI_DISM_STATE LsiDismState
0x140001edd  mov     cs:?LsiDismSession@@3IA, eax; uint LsiDismSession
0x140001ee3  jmp     short loc_140001EEB
0x140001ee5  mov     ecx, cs:?LsiDismState@@3W4_LSI_DISM_STATE@@A; _LSI_DISM_STATE LsiDismState
0x140001eeb  cmp     ecx, 2
0x140001eee  jz      short loc_140001F24
0x140001ef0  sub     ecx, 1
0x140001ef3  jz      short loc_140001F10
0x140001ef5  cmp     ecx, 1
0x140001ef8  jnz     short loc_140001F20
0x140001efa  mov     ecx, cs:?LsiDismSession@@3IA; uint LsiDismSession
0x140001f00  call    cs:__imp_DismCloseSession
0x140001f06  mov     cs:?LsiDismSession@@3IA, 0; uint LsiDismSession
0x140001f10  call    cs:__imp_DismShutdown
0x140001f16  mov     cs:?LsiDismState@@3W4_LSI_DISM_STATE@@A, 0; _LSI_DISM_STATE LsiDismState
0x140001f20  xor     eax, eax
0x140001f22  jmp     short loc_140001F29
0x140001f24  mov     eax, 1
0x140001f29  add     rsp, 28h
0x140001f2d  retn
```
