# OmaDmIsInformativeServerSessionActive

- ea: `0x18001a3f0`
- end: `0x18001a4ff`
- name: `OmaDmIsInformativeServerSessionActive`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800031b0`
- `0x180014514`
- `0x180014698`
- `0x18001a3f0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001a469`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001a469`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001a49c`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001a49c`

## pseudocode

```c
__int64 __fastcall OmaDmIsInformativeServerSessionActive(_DWORD *a1, __int64 a2, __int64 a3)
{
  int v4; // ebx
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v6; // rdx
  int DWORD; // eax
  unsigned int v9; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+38h] [rbp-30h] BYREF
  const wchar_t *v11; // [rsp+48h] [rbp-20h]
  __int64 v12; // [rsp+50h] [rbp-18h]

  v9 = 0;
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
  {
    v11 = L"OmaDmIsInformativeServerSessionActive";
    v12 = 76;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADMAPI_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)FunctionEntryPointEvent,
      a3,
      2u,
      &v10);
  }
  if ( a1 )
  {
    *a1 = 0;
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
    v6 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM";
    if ( !IsStateSeparationEnabled )
      v6 = L"Software\\Microsoft\\Provisioning\\OMADM";
    DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, v6, L"SessionModelessUIActive", &v9);
    v4 = 0;
    if ( DWORD != -2147024894 )
      v4 = DWORD;
    if ( v4 >= 0 )
      *a1 = v9 == 1;
  }
  else
  {
    v4 = -2147024882;
  }
  if ( (Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      a1,
      FunctionReturnValueEvent,
      L"OmaDmIsInformativeServerSessionActive",
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001a3f0  mov     r11, rsp
0x18001a3f3  mov     [r11+10h], rbx
0x18001a3f7  mov     [r11+18h], rbp
0x18001a3fb  push    rdi
0x18001a3fc  sub     rsp, 60h
0x18001a400  mov     rax, cs:__security_cookie
0x18001a407  xor     rax, rsp
0x18001a40a  mov     [rsp+68h+var_10], rax
0x18001a40f  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x18001a416  lea     rbp, aOmadmisinforma_0; "OmaDmIsInformativeServerSessionActive"
0x18001a41d  mov     rdi, rcx
0x18001a420  mov     [rsp+68h+var_38], 0
0x18001a428  jz      short loc_18001A457
0x18001a42a  lea     rax, [r11-30h]
0x18001a42e  mov     [r11-20h], rbp
0x18001a432  mov     r9d, 2
0x18001a438  mov     [r11-48h], rax
0x18001a43c  lea     rdx, FunctionEntryPointEvent
0x18001a443  mov     qword ptr [r11-18h], 4Ch ; 'L'
0x18001a44b  lea     rcx, WP_OMADMAPI_PROVIDER_Context
0x18001a452  call    McGenEventWrite_EventWriteTransfer
0x18001a457  test    rdi, rdi
0x18001a45a  jnz     short loc_18001A463
0x18001a45c  mov     ebx, 8007000Eh
0x18001a461  jmp     short loc_18001A4C2
0x18001a463  mov     dword ptr [rdi], 0
0x18001a469  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001a470  nop     dword ptr [rax+rax+00h]
0x18001a475  test    al, al
0x18001a477  lea     rcx, aSoftwareMicros_6; "Software\\Microsoft\\Provisioning\\OMAD"...
0x18001a47e  lea     rdx, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001a485  cmovz   rdx, rcx
0x18001a489  lea     r9, [rsp+68h+var_38]
0x18001a48e  mov     rcx, 0FFFFFFFF80000002h
0x18001a495  lea     r8, aSessionmodeles; "SessionModelessUIActive"
0x18001a49c  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001a4a3  nop     dword ptr [rax+rax+00h]
0x18001a4a8  xor     ebx, ebx
0x18001a4aa  cmp     eax, 80070002h
0x18001a4af  cmovnz  ebx, eax
0x18001a4b2  test    ebx, ebx
0x18001a4b4  js      short loc_18001A4C2
0x18001a4b6  xor     eax, eax
0x18001a4b8  cmp     [rsp+68h+var_38], 1
0x18001a4bd  setz    al
0x18001a4c0  mov     [rdi], eax
0x18001a4c2  test    byte ptr cs:Microsoft_WindowsPhone_OMADMAPI_ProviderEnableBits, 1
0x18001a4c9  jz      short loc_18001A4DD
0x18001a4cb  mov     r9d, ebx
0x18001a4ce  lea     rdx, FunctionReturnValueEvent
0x18001a4d5  mov     r8, rbp
0x18001a4d8  call    McTemplateU0zq_EventWriteTransfer
0x18001a4dd  mov     eax, ebx
0x18001a4df  mov     rcx, [rsp+68h+var_10]
0x18001a4e4  xor     rcx, rsp; StackCookie
0x18001a4e7  call    __security_check_cookie
0x18001a4ec  lea     r11, [rsp+68h+var_8]
0x18001a4f1  mov     rbx, [r11+18h]
0x18001a4f5  mov     rbp, [r11+20h]
0x18001a4f9  mov     rsp, r11
0x18001a4fc  pop     rdi
0x18001a4fd  retn
```
