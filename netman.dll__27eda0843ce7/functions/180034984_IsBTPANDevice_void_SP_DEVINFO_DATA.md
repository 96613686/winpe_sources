# IsBTPANDevice(void *,_SP_DEVINFO_DATA *)

- ea: `0x180034984`
- end: `0x180034a43`
- name: `?IsBTPANDevice@@YAHPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800212b4`
- `0x180034208`

## callees

- `0x180001710`
- `0x1800052b4`
- `0x180034984`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800349da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800349da`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x1800349c4`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x1800349c4`

## pseudocode

```c
__int64 __fastcall IsBTPANDevice(void *a1, struct _SP_DEVINFO_DATA *a2)
{
  unsigned int v2; // ebx
  const wchar_t *v3; // r9
  BYTE PropertyBuffer[416]; // [rsp+40h] [rbp-1B8h] BYREF

  v2 = 1;
  if ( !SetupDiGetDeviceRegistryPropertyW(a1, a2, 1u, 0, PropertyBuffer, 0x192u, 0)
    || (unsigned int)_o__wcsicmp(PropertyBuffer, L"BTH\\MS_BTHPAN") )
  {
    v2 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v3 = L"TRUE";
    if ( !v2 )
      v3 = L"FALSE";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids, v3);
  }
  return v2;
}

```

## disassembly

```asm
0x180034984  push    rbx
0x180034986  sub     rsp, 1F0h
0x18003498d  mov     rax, cs:__security_cookie
0x180034994  xor     rax, rsp
0x180034997  mov     [rsp+1F8h+var_18], rax
0x18003499f  xor     r9d, r9d; PropertyRegDataType
0x1800349a2  mov     [rsp+1F8h+RequiredSize], 0; RequiredSize
0x1800349ab  lea     rax, [rsp+1F8h+var_1B8]
0x1800349b0  mov     [rsp+1F8h+PropertyBufferSize], 192h; PropertyBufferSize
0x1800349b8  mov     [rsp+1F8h+PropertyBuffer], rax; PropertyBuffer
0x1800349bd  lea     ebx, [r9+1]
0x1800349c1  mov     r8d, ebx; Property
0x1800349c4  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x1800349ca  cmp     eax, ebx
0x1800349cc  jnz     short loc_1800349E4
0x1800349ce  lea     rdx, aBthMsBthpan; "BTH\\MS_BTHPAN"
0x1800349d5  lea     rcx, [rsp+1F8h+var_1B8]
0x1800349da  call    cs:__imp__o__wcsicmp
0x1800349e0  test    eax, eax
0x1800349e2  jz      short loc_1800349E6
0x1800349e4  xor     ebx, ebx
0x1800349e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800349ed  lea     rax, WPP_GLOBAL_Control
0x1800349f4  cmp     rcx, rax
0x1800349f7  jz      short loc_180034A28
0x1800349f9  test    byte ptr [rcx+1Ch], 8
0x1800349fd  jz      short loc_180034A28
0x1800349ff  mov     rcx, [rcx+10h]
0x180034a03  lea     rax, aFalse_0; "FALSE"
0x180034a0a  test    ebx, ebx
0x180034a0c  lea     r9, aTrue_0; "TRUE"
0x180034a13  mov     edx, 0Eh
0x180034a18  lea     r8, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids
0x180034a1f  cmovz   r9, rax
0x180034a23  call    WPP_SF_S
0x180034a28  mov     eax, ebx
0x180034a2a  mov     rcx, [rsp+1F8h+var_18]
0x180034a32  xor     rcx, rsp; StackCookie
0x180034a35  call    __security_check_cookie
0x180034a3a  add     rsp, 1F0h
0x180034a41  pop     rbx
0x180034a42  retn
```
