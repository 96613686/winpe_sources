# DiscpSetTunnelAddress

- ea: `0x180010b5c`
- end: `0x180010dbd`
- name: `DiscpSetTunnelAddress`
- size: `609`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *, __int64, char)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004690`
- `0x18000f8e8`

## callees

- `0x18000ec10`
- `0x18000f4a8`
- `0x180010b5c`
- `0x180010dc4`
- `0x180010e4c`
- `0x180016d20`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180010c09`
- `ISCSIUM!DiscpAllocMemory` at `0x180010c09`
- `ISCSIUM!DiscpSetRegistryValue` at `0x180010bea`
- `ISCSIUM!DiscpSetRegistryValue` at `0x180010bea`
- `ISCSIUM!DiscpFreeMemory` at `0x180010bf6`
- `ISCSIUM!DiscpFreeMemory` at `0x180010cd0`
- `ISCSIUM!DiscpFreeMemory` at `0x180010ce6`
- `ISCSIUM!DiscpFreeMemory` at `0x180010d96`
- `ISCSIUM!DiscpFreeMemory` at `0x180010bf6`
- `ISCSIUM!DiscpFreeMemory` at `0x180010cd0`
- `ISCSIUM!DiscpFreeMemory` at `0x180010ce6`
- `ISCSIUM!DiscpFreeMemory` at `0x180010d96`
- `WMICLNT!WmiCloseBlock` at `0x180010cf0`
- `WMICLNT!WmiCloseBlock` at `0x180010cf0`
- `WMICLNT!WmiOpenBlock` at `0x180010d76`
- `WMICLNT!WmiOpenBlock` at `0x180010d76`

## pseudocode

```c
__int64 __fastcall DiscpSetTunnelAddress(__int64 a1, int a2, const wchar_t *a3, __int64 a4, char a5)
{
  __int64 v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rax
  int *v12; // rax
  int *v13; // rdi
  int v14; // esi
  __int64 v15; // rcx
  unsigned int v16; // r15d
  __int64 v17; // r13
  __int64 v18; // rbx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  unsigned int v22; // eax
  wchar_t *v24; // [rsp+40h] [rbp-10h] BYREF
  __int64 v25; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v26; // [rsp+90h] [rbp+40h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+50h] BYREF

  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  if ( a1 )
    v9 = *(_QWORD *)(a1 + 40);
  else
    v9 = 0;
  if ( !a5 )
    goto LABEL_9;
  v10 = DiscpBuildCacheName(v9, a2, a3, &v24);
  if ( !v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(a4 + 2 * v11) );
    v10 = DiscpSetRegistryValue(
            0,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\iSCSI\\Discovery\\Tunnel Address",
            v24,
            1,
            a4,
            2 * (int)v11,
            0);
    DiscpFreeMemory(v24);
    if ( !v10 )
    {
LABEL_9:
      v12 = (int *)DiscpAllocMemory(1100);
      v13 = v12;
      if ( !v12 )
        return 8;
      *v12 = a2;
      if ( !a1 )
      {
        v14 = 0;
        if ( !(unsigned int)DiscpGetInitiatorsSupportingSecurity(&v27, &v26, &v25) )
        {
          v16 = 0;
          v17 = v25;
          while ( v16 < v26 )
          {
            v18 = *(_QWORD *)(v17 + 8LL * v16);
            if ( (*(_BYTE *)(v18 + 36) & 4) != 0 )
            {
              v19 = DiscpBuildIScsiIpAddress(*(_DWORD *)(v18 + 20) & 1, a4, 1, v13 + 138);
              if ( v19 )
                goto LABEL_20;
              if ( a3 )
              {
                v19 = DiscpBuildIScsiIpAddress(*(_DWORD *)(v18 + 20) & 1, (__int64)a3, 1, v13 + 1);
                if ( v19 )
                  goto LABEL_20;
              }
              else
              {
                v13[1] = 3;
                *((_WORD *)v13 + 18) = 0;
              }
              v19 = DiscpSetTunnelAddressForAdapter(v27, v18, v13);
              if ( v19 )
LABEL_20:
                v14 = v19;
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v18 + 16), 0xFFFFFFFF) == 1 )
              DiscpFreeMemory(v18);
            ++v16;
          }
          DiscpFreeMemory(v17);
          WmiCloseBlock(v27);
        }
        v20 = DiscpSetTunnelAddressForSPD(v15, a4);
        if ( v20 )
          v14 = v20;
        v10 = v14 != 0 ? 0xAFFF002E : 0;
        goto LABEL_37;
      }
      v21 = *(unsigned int *)(a1 + 20);
      if ( (v21 & 2) != 0 )
      {
        v22 = DiscpSetTunnelAddressForSPD(v21, a4);
      }
      else
      {
        v10 = DiscpBuildIScsiIpAddress(v21 & 1, a4, 1, v12 + 138);
        if ( a3 )
        {
          v10 = DiscpBuildIScsiIpAddress(*(_DWORD *)(a1 + 20) & 1, (__int64)a3, 1, v13 + 1);
        }
        else
        {
          v13[1] = 3;
          *((_WORD *)v13 + 18) = 0;
        }
        if ( v10 )
          goto LABEL_37;
        v10 = WmiOpenBlock(MSiSCSI_SecurityConfigOperations_GUID, 2684354560LL, &v27);
        if ( v10 )
          goto LABEL_37;
        v22 = DiscpSetTunnelAddressForAdapter(v27, a1, v13);
      }
      v10 = v22;
LABEL_37:
      DiscpFreeMemory(v13);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180010b5c  mov     [rsp-38h+arg_8], rbx
0x180010b61  push    rbp
0x180010b62  push    rsi
0x180010b63  push    rdi
0x180010b64  push    r12
0x180010b66  push    r13
0x180010b68  push    r14
0x180010b6a  push    r15
0x180010b6c  mov     rbp, rsp
0x180010b6f  sub     rsp, 50h
0x180010b73  xor     r13d, r13d
0x180010b76  mov     r14, r9
0x180010b79  mov     [rbp+arg_10], r13
0x180010b7d  mov     r12, r8
0x180010b80  mov     [rbp+arg_0], r13d
0x180010b84  mov     r15d, edx
0x180010b87  mov     [rbp+var_8], r13
0x180010b8b  mov     rsi, rcx
0x180010b8e  mov     [rbp+var_10], r13
0x180010b92  test    rcx, rcx
0x180010b95  jz      short loc_180010B9D
0x180010b97  mov     rcx, [rcx+28h]
0x180010b9b  jmp     short loc_180010BA0
0x180010b9d  mov     rcx, r13
0x180010ba0  cmp     [rbp+arg_20], r13b
0x180010ba4  jz      short loc_180010C04
0x180010ba6  lea     r9, [rbp+var_10]
0x180010baa  call    DiscpBuildCacheName
0x180010baf  mov     ebx, eax
0x180010bb1  test    eax, eax
0x180010bb3  jnz     loc_180010DA3
0x180010bb9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010bbd  inc     rax
0x180010bc0  cmp     [r14+rax*2], r13w
0x180010bc5  jnz     short loc_180010BBD
0x180010bc7  mov     r8, [rbp+var_10]
0x180010bcb  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x180010bd2  add     eax, eax
0x180010bd4  mov     [rsp+50h+var_20], r13b
0x180010bd9  mov     [rsp+50h+var_28], eax
0x180010bdd  mov     r9d, 1
0x180010be3  xor     ecx, ecx
0x180010be5  mov     [rsp+50h+var_30], r14
0x180010bea  call    cs:__imp_DiscpSetRegistryValue
0x180010bf0  mov     rcx, [rbp+var_10]
0x180010bf4  mov     ebx, eax
0x180010bf6  call    cs:__imp_DiscpFreeMemory
0x180010bfc  test    ebx, ebx
0x180010bfe  jnz     loc_180010DA3
0x180010c04  mov     ecx, 44Ch
0x180010c09  call    cs:__imp_DiscpAllocMemory
0x180010c0f  mov     rdi, rax
0x180010c12  test    rax, rax
0x180010c15  jz      loc_180010D9E
0x180010c1b  mov     [rax], r15d
0x180010c1e  test    rsi, rsi
0x180010c21  jnz     loc_180010D12
0x180010c27  lea     r8, [rbp+var_8]
0x180010c2b  mov     esi, r13d
0x180010c2e  lea     rdx, [rbp+arg_0]
0x180010c32  lea     rcx, [rbp+arg_10]
0x180010c36  call    DiscpGetInitiatorsSupportingSecurity
0x180010c3b  test    eax, eax
0x180010c3d  jnz     loc_180010CF6
0x180010c43  mov     r15d, r13d
0x180010c46  mov     r13, [rbp+var_8]
0x180010c4a  cmp     [rbp+arg_0], r15d
0x180010c4e  jbe     loc_180010CE3
0x180010c54  mov     eax, r15d
0x180010c57  mov     rbx, [r13+rax*8+0]
0x180010c5c  test    byte ptr [rbx+24h], 4
0x180010c60  jz      short loc_180010CC0
0x180010c62  mov     ecx, [rbx+14h]
0x180010c65  lea     r9, [rdi+228h]
0x180010c6c  and     cl, 1
0x180010c6f  mov     r8b, 1
0x180010c72  mov     rdx, r14
0x180010c75  call    DiscpBuildIScsiIpAddress
0x180010c7a  test    eax, eax
0x180010c7c  jnz     short loc_180010CBE
0x180010c7e  test    r12, r12
0x180010c81  jz      short loc_180010C9E
0x180010c83  mov     ecx, [rbx+14h]
0x180010c86  lea     r9, [rdi+4]
0x180010c8a  and     cl, 1
0x180010c8d  mov     r8b, 1
0x180010c90  mov     rdx, r12
0x180010c93  call    DiscpBuildIScsiIpAddress
0x180010c98  test    eax, eax
0x180010c9a  jz      short loc_180010CAB
0x180010c9c  jmp     short loc_180010CBE
0x180010c9e  xor     eax, eax
0x180010ca0  mov     dword ptr [rdi+4], 3
0x180010ca7  mov     [rdi+24h], ax
0x180010cab  mov     rcx, [rbp+arg_10]
0x180010caf  mov     r8, rdi
0x180010cb2  mov     rdx, rbx
0x180010cb5  call    DiscpSetTunnelAddressForAdapter
0x180010cba  test    eax, eax
0x180010cbc  jz      short loc_180010CC0
0x180010cbe  mov     esi, eax
0x180010cc0  or      eax, 0FFFFFFFFh
0x180010cc3  lock xadd [rbx+10h], eax
0x180010cc8  cmp     eax, 1
0x180010ccb  jnz     short loc_180010CD6
0x180010ccd  mov     rcx, rbx
0x180010cd0  call    cs:__imp_DiscpFreeMemory
0x180010cd6  inc     r15d
0x180010cd9  cmp     r15d, [rbp+arg_0]
0x180010cdd  jb      loc_180010C54
0x180010ce3  mov     rcx, r13
0x180010ce6  call    cs:__imp_DiscpFreeMemory
0x180010cec  mov     rcx, [rbp+arg_10]
0x180010cf0  call    cs:__imp_WmiCloseBlock
0x180010cf6  mov     rdx, r14
0x180010cf9  call    DiscpSetTunnelAddressForSPD
0x180010cfe  test    eax, eax
0x180010d00  cmovnz  esi, eax
0x180010d03  neg     esi
0x180010d05  sbb     ebx, ebx
0x180010d07  and     ebx, 0AFFF002Eh
0x180010d0d  jmp     loc_180010D93
0x180010d12  mov     ecx, [rsi+14h]
0x180010d15  mov     rdx, r14
0x180010d18  test    cl, 2
0x180010d1b  jz      short loc_180010D24
0x180010d1d  call    DiscpSetTunnelAddressForSPD
0x180010d22  jmp     short loc_180010D91
0x180010d24  lea     r9, [rax+228h]
0x180010d2b  and     cl, 1
0x180010d2e  mov     r8b, 1
0x180010d31  call    DiscpBuildIScsiIpAddress
0x180010d36  mov     ebx, eax
0x180010d38  test    r12, r12
0x180010d3b  jz      short loc_180010D56
0x180010d3d  mov     ecx, [rsi+14h]
0x180010d40  lea     r9, [rdi+4]
0x180010d44  and     cl, 1
0x180010d47  mov     r8b, 1
0x180010d4a  mov     rdx, r12
0x180010d4d  call    DiscpBuildIScsiIpAddress
0x180010d52  mov     ebx, eax
0x180010d54  jmp     short loc_180010D62
0x180010d56  mov     dword ptr [rdi+4], 3
0x180010d5d  mov     [rdi+24h], r13w
0x180010d62  test    ebx, ebx
0x180010d64  jnz     short loc_180010D93
0x180010d66  lea     r8, [rbp+arg_10]
0x180010d6a  mov     edx, 0A0000000h
0x180010d6f  lea     rcx, MSiSCSI_SecurityConfigOperations_GUID
0x180010d76  call    cs:__imp_WmiOpenBlock
0x180010d7c  mov     ebx, eax
0x180010d7e  test    eax, eax
0x180010d80  jnz     short loc_180010D93
0x180010d82  mov     rcx, [rbp+arg_10]
0x180010d86  mov     r8, rdi
0x180010d89  mov     rdx, rsi
0x180010d8c  call    DiscpSetTunnelAddressForAdapter
0x180010d91  mov     ebx, eax
0x180010d93  mov     rcx, rdi
0x180010d96  call    cs:__imp_DiscpFreeMemory
0x180010d9c  jmp     short loc_180010DA3
0x180010d9e  mov     ebx, 8
0x180010da3  mov     eax, ebx
0x180010da5  mov     rbx, [rsp+50h+arg_8]
0x180010dad  add     rsp, 50h
0x180010db1  pop     r15
0x180010db3  pop     r14
0x180010db5  pop     r13
0x180010db7  pop     r12
0x180010db9  pop     rdi
0x180010dba  pop     rsi
0x180010dbb  pop     rbp
0x180010dbc  retn
```
