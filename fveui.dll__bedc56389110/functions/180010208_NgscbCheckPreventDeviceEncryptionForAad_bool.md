# NgscbCheckPreventDeviceEncryptionForAad(bool *)

- ea: `0x180010208`
- end: `0x1800102aa`
- name: `?NgscbCheckPreventDeviceEncryptionForAad@@YAJPEA_N@Z`
- size: `162`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016084`

## callees

- `0x1800037a0`
- `0x18000ff88`
- `0x180010208`

## string_xrefs

- `0x18001021d`: `PreventDeviceEncryptionForAzureADJoinedDevices`

## pseudocode

```c
__int64 __fastcall NgscbCheckPreventDeviceEncryptionForAad(bool *a1)
{
  unsigned int v2; // eax
  int v3; // ebx
  PVOID *v4; // rcx

  v2 = NgscbCheckBoolRegistryHelper(L"PreventDeviceEncryptionForAzureADJoinedDevices");
  v3 = v2;
  if ( !v2 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
LABEL_8:
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_d(v4[2], 316, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, *a1);
    return (unsigned int)v3;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 315, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 >= 0 )
    goto LABEL_8;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180010208  mov     [rsp+arg_0], rbx
0x18001020d  mov     [rsp+arg_8], rsi
0x180010212  push    rdi
0x180010213  sub     rsp, 20h
0x180010217  mov     rdi, rcx
0x18001021a  mov     rdx, rcx
0x18001021d  lea     rcx, aPreventdevicee_0; "PreventDeviceEncryptionForAzureADJoined"...
0x180010224  call    NgscbCheckBoolRegistryHelper
0x180010229  lea     rsi, WPP_GLOBAL_Control
0x180010230  mov     ebx, eax
0x180010232  test    eax, eax
0x180010234  jz      short loc_18001026D
0x180010236  mov     rcx, cs:WPP_GLOBAL_Control
0x18001023d  cmp     rcx, rsi
0x180010240  jz      short loc_180010267
0x180010242  test    byte ptr [rcx+1Ch], 40h
0x180010246  jz      short loc_180010267
0x180010248  mov     rcx, [rcx+10h]
0x18001024c  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010253  mov     edx, 13Bh
0x180010258  mov     r9d, eax
0x18001025b  call    WPP_SF_d
0x180010260  mov     rcx, cs:WPP_GLOBAL_Control
0x180010267  test    ebx, ebx
0x180010269  js      short loc_180010298
0x18001026b  jmp     short loc_180010274
0x18001026d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010274  cmp     rcx, rsi
0x180010277  jz      short loc_180010298
0x180010279  test    byte ptr [rcx+1Ch], 8
0x18001027d  jz      short loc_180010298
0x18001027f  movzx   r9d, byte ptr [rdi]
0x180010283  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x18001028a  mov     rcx, [rcx+10h]
0x18001028e  mov     edx, 13Ch
0x180010293  call    WPP_SF_d
0x180010298  mov     rsi, [rsp+28h+arg_8]
0x18001029d  mov     eax, ebx
0x18001029f  mov     rbx, [rsp+28h+arg_0]
0x1800102a4  add     rsp, 20h
0x1800102a8  pop     rdi
0x1800102a9  retn
```
