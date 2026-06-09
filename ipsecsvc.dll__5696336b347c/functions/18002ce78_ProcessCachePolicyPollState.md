# ProcessCachePolicyPollState

- ea: `0x18002ce78`
- end: `0x18002cf6b`
- name: `ProcessCachePolicyPollState`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x18000adac`

## callees

- `0x180006f60`
- `0x18000acb4`
- `0x18000afe8`
- `0x18000f638`
- `0x18002bb44`
- `0x18002c380`
- `0x18002ce78`
- `0x18002d64c`
- `0x180036c54`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002cf10`
- `msvcrt!_wcsicmp` at `0x18002cf10`

## pseudocode

```c
__int64 __fastcall ProcessCachePolicyPollState(__int64 a1)
{
  wchar_t *v1; // rdi
  unsigned int DirectoryPolicyDN; // ebx
  unsigned int v4; // eax
  int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // eax
  int v9; // [rsp+48h] [rbp+10h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp+18h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp+20h] BYREF

  v1 = 0;
  lpMem = 0;
  String2 = 0;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  DirectoryPolicyDN = GetDirectoryPolicyDN((__int64 *)&lpMem);
  if ( !DirectoryPolicyDN )
  {
    DirectoryPolicyDN = GetDirectoryIncarnationNumber((int)lpMem, &v9);
    if ( !DirectoryPolicyDN )
    {
      v4 = CopyDSToFQRegString((const wchar_t *)lpMem, 1, &String2);
      v1 = String2;
      DirectoryPolicyDN = v4;
      if ( !v4 )
      {
        v5 = _wcsicmp(*(const wchar_t **)(a1 + 8), String2);
        v6 = a1;
        if ( v5 )
        {
LABEL_13:
          DirectoryPolicyDN = OnPolicyChanged(v6);
          goto LABEL_14;
        }
        if ( *(_DWORD *)(a1 + 28) == v9 )
          v7 = MigrateFromCacheToDS(a1);
        else
          v7 = UpdateFromCacheToDS(a1);
        DirectoryPolicyDN = v7;
        if ( v7 )
        {
          v6 = a1;
          goto LABEL_13;
        }
      }
    }
  }
LABEL_14:
  if ( lpMem )
    IpsecFreeMem(lpMem);
  if ( v1 )
    IpsecFreeMem(v1);
  return DirectoryPolicyDN;
}

```

## disassembly

```asm
0x18002ce78  push    rbx
0x18002ce7a  push    rsi
0x18002ce7b  push    rdi
0x18002ce7c  sub     rsp, 20h
0x18002ce80  xor     edi, edi
0x18002ce82  mov     [rsp+38h+lpMem], 0
0x18002ce8b  mov     [rsp+38h+String2], rdi
0x18002ce90  mov     rsi, rcx
0x18002ce93  mov     [rsp+38h+arg_8], 0
0x18002ce9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cea2  lea     rax, WPP_GLOBAL_Control
0x18002cea9  cmp     rcx, rax
0x18002ceac  jz      short loc_18002CEC7
0x18002ceae  test    byte ptr [rcx+1Ch], 4
0x18002ceb2  jz      short loc_18002CEC7
0x18002ceb4  mov     rcx, [rcx+10h]
0x18002ceb8  lea     edx, [rdi+70h]
0x18002cebb  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cec2  call    WPP_SF_
0x18002cec7  lea     rcx, [rsp+38h+lpMem]
0x18002cecc  call    GetDirectoryPolicyDN
0x18002ced1  mov     ebx, eax
0x18002ced3  test    eax, eax
0x18002ced5  jnz     short loc_18002CF42
0x18002ced7  mov     rcx, [rsp+38h+lpMem]; int
0x18002cedc  lea     rdx, [rsp+38h+arg_8]
0x18002cee1  call    GetDirectoryIncarnationNumber
0x18002cee6  mov     ebx, eax
0x18002cee8  test    eax, eax
0x18002ceea  jnz     short loc_18002CF42
0x18002ceec  mov     rcx, [rsp+38h+lpMem]
0x18002cef1  lea     r8, [rsp+38h+String2]
0x18002cef6  lea     edx, [rax+1]
0x18002cef9  call    CopyDSToFQRegString
0x18002cefe  mov     rdi, [rsp+38h+String2]
0x18002cf03  mov     ebx, eax
0x18002cf05  test    eax, eax
0x18002cf07  jnz     short loc_18002CF42
0x18002cf09  mov     rcx, [rsi+8]; String1
0x18002cf0d  mov     rdx, rdi; String2
0x18002cf10  call    cs:__imp__wcsicmp
0x18002cf16  mov     rcx, rsi
0x18002cf19  test    eax, eax
0x18002cf1b  jnz     short loc_18002CF3B
0x18002cf1d  mov     eax, [rsp+38h+arg_8]
0x18002cf21  cmp     [rsi+1Ch], eax
0x18002cf24  jnz     short loc_18002CF2D
0x18002cf26  call    MigrateFromCacheToDS
0x18002cf2b  jmp     short loc_18002CF32
0x18002cf2d  call    UpdateFromCacheToDS
0x18002cf32  mov     ebx, eax
0x18002cf34  test    eax, eax
0x18002cf36  jz      short loc_18002CF42
0x18002cf38  mov     rcx, rsi
0x18002cf3b  call    OnPolicyChanged
0x18002cf40  mov     ebx, eax
0x18002cf42  cmp     [rsp+38h+lpMem], 0
0x18002cf48  jz      short loc_18002CF54
0x18002cf4a  mov     rcx, [rsp+38h+lpMem]; lpMem
0x18002cf4f  call    IpsecFreeMem
0x18002cf54  test    rdi, rdi
0x18002cf57  jz      short loc_18002CF61
0x18002cf59  mov     rcx, rdi; lpMem
0x18002cf5c  call    IpsecFreeMem
0x18002cf61  mov     eax, ebx
0x18002cf63  add     rsp, 20h
0x18002cf67  pop     rdi
0x18002cf68  pop     rsi
0x18002cf69  pop     rbx
0x18002cf6a  retn
```
