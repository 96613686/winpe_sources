# DevUtilsIsVolumeSnapshotDevice

- ea: `0x180009ca0`
- end: `0x180009dff`
- name: `DevUtilsIsVolumeSnapshotDevice`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009410`

## callees

- `0x180009ca0`
- `0x18000a1a0`
- `0x18000a230`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009cf0`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009cf0`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180009d4a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180009d4a`
- `KERNEL32!CompareStringOrdinal` at `0x180009d82`
- `KERNEL32!CompareStringOrdinal` at `0x180009d82`

## pseudocode

```c
__int64 __fastcall DevUtilsIsVolumeSnapshotDevice(WCHAR *a1)
{
  unsigned int v1; // ebx
  unsigned int i; // esi
  const DEVPROPKEY *v3; // rdx
  const WCHAR *v4; // rdi
  __int64 v5; // rdx
  const WCHAR *v6; // rax
  ULONG PropertyBufferSize; // [rsp+30h] [rbp-D0h] BYREF
  DEVNODE pdnDevInst; // [rsp+34h] [rbp-CCh] BYREF
  DEVPROPTYPE PropertyType[1026]; // [rsp+38h] [rbp-C8h] BYREF

  pdnDevInst = 0;
  v1 = 0;
  PropertyType[0] = 0;
  PropertyBufferSize = 0;
  if ( !CM_Locate_DevNodeW(&pdnDevInst, a1, 1u) )
  {
    for ( i = 0; i < 2; ++i )
    {
      v3 = &DEVPKEY_Device_HardwareIds;
      v4 = (const WCHAR *)&PropertyType[512 * (unsigned __int64)i + 2];
      PropertyBufferSize = 2048;
      if ( i )
        v3 = &DEVPKEY_Device_CompatibleIds;
      v1 = 0;
      if ( !CM_Get_DevNode_PropertyW(
              pdnDevInst,
              v3,
              PropertyType,
              (PBYTE)&PropertyType[512 * (unsigned __int64)i + 2],
              &PropertyBufferSize,
              0)
        && PropertyType[0] == 8210 )
      {
        PropertyType[512 * (unsigned __int64)i + 513] = 0;
        while ( *v4 )
        {
          if ( CompareStringOrdinal(L"STORAGE\\VolumeSnapshot", -1, v4, -1, 1) == 2 )
            return 1;
          v5 = 0x7FFFFFFF;
          v6 = v4;
          do
          {
            if ( !*v6 )
              break;
            ++v6;
            --v5;
          }
          while ( v5 );
          if ( !v5 )
            break;
          v4 += ((0x7FFFFFFF - v5) & -(__int64)(v5 != 0)) + 1;
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180009ca0  push    rbp
0x180009ca2  push    rbx
0x180009ca3  push    rsi
0x180009ca4  push    rdi
0x180009ca5  push    r14
0x180009ca7  push    r15
0x180009ca9  lea     rbp, [rsp-0F58h]
0x180009cb1  mov     eax, 1058h
0x180009cb6  call    _alloca_probe
0x180009cbb  sub     rsp, rax
0x180009cbe  mov     rax, cs:__security_cookie
0x180009cc5  xor     rax, rsp
0x180009cc8  mov     [rbp+0F80h+var_40], rax
0x180009ccf  xor     r15d, r15d
0x180009cd2  mov     rdx, rcx; pDeviceID
0x180009cd5  lea     rcx, [rsp+1080h+pdnDevInst]; pdnDevInst
0x180009cda  mov     [rsp+1080h+pdnDevInst], r15d
0x180009cdf  mov     ebx, r15d
0x180009ce2  mov     [rsp+1080h+PropertyType], r15d
0x180009ce7  mov     [rsp+1080h+var_1050], r15d
0x180009cec  lea     r8d, [r15+1]; ulFlags
0x180009cf0  call    cs:__imp_CM_Locate_DevNodeW
0x180009cf6  test    eax, eax
0x180009cf8  jnz     loc_180009DDE
0x180009cfe  mov     esi, r15d
0x180009d01  mov     ecx, [rsp+1080h+pdnDevInst]; dnDevInst
0x180009d05  lea     rax, DEVPKEY_Device_CompatibleIds
0x180009d0c  mov     r14d, esi
0x180009d0f  lea     rdi, [rsp+1080h+var_1040]
0x180009d14  shl     r14, 0Bh
0x180009d18  lea     rdx, DEVPKEY_Device_HardwareIds
0x180009d1f  add     rdi, r14
0x180009d22  mov     [rsp+1080h+ulFlags], r15d; ulFlags
0x180009d27  test    esi, esi
0x180009d29  mov     [rsp+1080h+var_1050], 800h
0x180009d31  mov     r9, rdi; PropertyBuffer
0x180009d34  lea     r8, [rsp+1080h+PropertyType]; PropertyType
0x180009d39  cmovnz  rdx, rax; PropertyKey
0x180009d3d  mov     ebx, r15d
0x180009d40  lea     rax, [rsp+1080h+var_1050]
0x180009d45  mov     [rsp+1080h+PropertyBufferSize], rax; PropertyBufferSize
0x180009d4a  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180009d50  test    eax, eax
0x180009d52  jnz     short loc_180009DCC
0x180009d54  cmp     [rsp+1080h+PropertyType], 2012h
0x180009d5c  jnz     short loc_180009DCC
0x180009d5e  mov     [rbp+r14+0F80h+var_844], r15d
0x180009d66  jmp     short loc_180009DC6
0x180009d68  or      eax, 0FFFFFFFFh
0x180009d6b  mov     dword ptr [rsp+1080h+PropertyBufferSize], 1; bIgnoreCase
0x180009d73  mov     r9d, eax; cchCount2
0x180009d76  lea     rcx, String1; "STORAGE\\VolumeSnapshot"
0x180009d7d  mov     edx, eax; cchCount1
0x180009d7f  mov     r8, rdi; lpString2
0x180009d82  call    cs:__imp_CompareStringOrdinal
0x180009d88  cmp     eax, 2
0x180009d8b  jz      short loc_180009DD9
0x180009d8d  mov     edx, 7FFFFFFFh
0x180009d92  mov     rax, rdi
0x180009d95  cmp     [rax], r15w
0x180009d99  jz      short loc_180009DA5
0x180009d9b  add     rax, 2
0x180009d9f  sub     rdx, 1
0x180009da3  jnz     short loc_180009D95
0x180009da5  mov     ecx, 7FFFFFFFh
0x180009daa  mov     rax, rdx
0x180009dad  sub     rcx, rdx
0x180009db0  neg     rax
0x180009db3  sbb     r8, r8
0x180009db6  and     r8, rcx
0x180009db9  test    rdx, rdx
0x180009dbc  jz      short loc_180009DCC
0x180009dbe  lea     rdi, [rdi+r8*2]
0x180009dc2  add     rdi, 2
0x180009dc6  cmp     [rdi], r15w
0x180009dca  jnz     short loc_180009D68
0x180009dcc  inc     esi
0x180009dce  cmp     esi, 2
0x180009dd1  jb      loc_180009D01
0x180009dd7  jmp     short loc_180009DDE
0x180009dd9  mov     ebx, 1
0x180009dde  mov     eax, ebx
0x180009de0  mov     rcx, [rbp+0F80h+var_40]
0x180009de7  xor     rcx, rsp; StackCookie
0x180009dea  call    __security_check_cookie
0x180009def  add     rsp, 1058h
0x180009df6  pop     r15
0x180009df8  pop     r14
0x180009dfa  pop     rdi
0x180009dfb  pop     rsi
0x180009dfc  pop     rbx
0x180009dfd  pop     rbp
0x180009dfe  retn
```
