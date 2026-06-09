# CProfileMgr::GetWirelessInfo(std::list<tagNETCON_PROPERTIES *,std::allocator<tagNETCON_PROPERTIES *>> *,ushort *,uint,ulong *)

- ea: `0x180020928`
- end: `0x180020a9e`
- name: `?GetWirelessInfo@CProfileMgr@@QEAAJPEAV?$list@PEAUtagNETCON_PROPERTIES@@V?$allocator@PEAUtagNETCON_PROPERTIES@@@std@@@std@@PEAGIPEAK@Z`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001f3a4`

## callees

- `0x180014274`
- `0x180020928`

## import_xrefs

- `wlanapi!WlanQueryInterface` at `0x1800209d5`
- `wlanapi!WlanQueryInterface` at `0x1800209d5`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180020a0d`
- `wlanapi!WlanUtf8SsidToDisplayName` at `0x180020a0d`
- `wlanapi!WlanOpenHandle` at `0x180020978`
- `wlanapi!WlanOpenHandle` at `0x180020978`
- `wlanapi!WlanFreeMemory` at `0x180020a2f`
- `wlanapi!WlanFreeMemory` at `0x180020a2f`
- `wlanapi!WlanCloseHandle` at `0x180020a3c`
- `wlanapi!WlanCloseHandle` at `0x180020a3c`

## pseudocode

```c
__int64 __fastcall CProfileMgr::GetWirelessInfo(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4, unsigned int *a5)
{
  unsigned int *v5; // r15
  _QWORD *v8; // rbx
  int v9; // r14d
  unsigned int v10; // edi
  const GUID *v11; // rdx
  unsigned int v12; // esi
  int v13; // eax
  PVOID pMemory; // [rsp+40h] [rbp-10h] BYREF
  void *phClientHandle; // [rsp+48h] [rbp-8h] BYREF
  __int64 pdwDataSize; // [rsp+90h] [rbp+40h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+A8h] [rbp+58h] BYREF

  pdwDataSize = a1;
  v5 = a5;
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  *a5 = 0;
  if ( WlanOpenHandle(1u, 0, &pdwNegotiatedVersion, &phClientHandle) )
  {
    v10 = 1;
  }
  else
  {
    v8 = (_QWORD *)*a2;
    v9 = 0;
    v10 = 0;
    pMemory = 0;
    LODWORD(pdwDataSize) = 0;
    while ( 1 )
    {
      v8 = (_QWORD *)*v8;
      if ( v8 == (_QWORD *)*a2 )
        break;
      v11 = (const GUID *)v8[2];
      pMemory = 0;
      if ( !WlanQueryInterface(
              phClientHandle,
              v11,
              wlan_intf_opcode_current_connection,
              0,
              (PDWORD)&pdwDataSize,
              &pMemory,
              0) )
      {
        v12 = *((_DWORD *)pMemory + 144);
        if ( !v9 || v12 > *v5 )
        {
          LODWORD(a5) = 33;
          v9 = 1;
          v13 = WlanUtf8SsidToDisplayName((char *)pMemory + 520, 0, a3, &a5);
          if ( v13 )
          {
            if ( v13 > 0 )
              v10 = (unsigned __int16)v13 | 0x80070000;
            else
              v10 = v13;
          }
          else
          {
            *v5 = v12;
          }
        }
        WlanFreeMemory(pMemory);
      }
    }
    WlanCloseHandle(phClientHandle, 0);
    if ( !v10 )
      v10 = v9 == 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180020928  mov     [rsp-38h+arg_8], rbx
0x18002092d  mov     [rsp-38h+pdwNegotiatedVersion], r9d
0x180020932  mov     [rsp-38h+arg_0], rcx
0x180020937  push    rbp
0x180020938  push    rsi
0x180020939  push    rdi
0x18002093a  push    r12
0x18002093c  push    r13
0x18002093e  push    r14
0x180020940  push    r15
0x180020942  mov     rbp, rsp
0x180020945  sub     rsp, 50h
0x180020949  mov     r15, [rbp+arg_20]
0x18002094d  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180020951  mov     r12, rdx
0x180020954  mov     [rbp+phClientHandle], 0
0x18002095c  xor     edx, edx; pReserved
0x18002095e  mov     [rbp+pdwNegotiatedVersion], 0
0x180020965  mov     r13, r8
0x180020968  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18002096c  mov     dword ptr [r15], 0
0x180020973  lea     esi, [rdx+1]
0x180020976  mov     ecx, esi; dwClientVersion
0x180020978  call    cs:__imp_WlanOpenHandle
0x18002097e  test    eax, eax
0x180020980  jnz     loc_180020A51
0x180020986  mov     rbx, [r12]
0x18002098a  xor     r14d, r14d
0x18002098d  xor     edi, edi
0x18002098f  mov     [rbp+pMemory], rdi
0x180020993  mov     dword ptr [rbp+arg_0], edi
0x180020996  mov     rbx, [rbx]
0x180020999  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x18002099d  cmp     rbx, [r12]
0x1800209a1  jz      loc_180020A3A
0x1800209a7  mov     rdx, [rbx+10h]; pInterfaceGuid
0x1800209ab  lea     rax, [rbp+pMemory]
0x1800209af  xor     r9d, r9d; pReserved
0x1800209b2  mov     [rsp+50h+pWlanOpcodeValueType], 0; pWlanOpcodeValueType
0x1800209bb  mov     [rsp+50h+ppData], rax; ppData
0x1800209c0  lea     rax, [rbp+arg_0]
0x1800209c4  mov     [rbp+pMemory], 0
0x1800209cc  mov     [rsp+50h+pdwDataSize], rax; pdwDataSize
0x1800209d1  lea     r8d, [r9+7]; OpCode
0x1800209d5  call    cs:__imp_WlanQueryInterface
0x1800209db  test    eax, eax
0x1800209dd  jnz     short loc_180020996
0x1800209df  mov     rcx, [rbp+pMemory]
0x1800209e3  add     rcx, 208h
0x1800209ea  mov     esi, [rcx+38h]
0x1800209ed  test    r14d, r14d
0x1800209f0  jz      short loc_1800209F7
0x1800209f2  cmp     esi, [r15]
0x1800209f5  jbe     short loc_180020A2B
0x1800209f7  lea     r9, [rbp+arg_20]
0x1800209fb  mov     dword ptr [rbp+arg_20], 21h ; '!'
0x180020a02  mov     r8, r13
0x180020a05  xor     edx, edx
0x180020a07  mov     r14d, 1
0x180020a0d  call    cs:__imp_WlanUtf8SsidToDisplayName
0x180020a13  test    eax, eax
0x180020a15  jnz     short loc_180020A1C
0x180020a17  mov     [r15], esi
0x180020a1a  jmp     short loc_180020A2B
0x180020a1c  jg      short loc_180020A22
0x180020a1e  mov     edi, eax
0x180020a20  jmp     short loc_180020A2B
0x180020a22  movzx   edi, ax
0x180020a25  or      edi, 80070000h
0x180020a2b  mov     rcx, [rbp+pMemory]; pMemory
0x180020a2f  call    cs:__imp_WlanFreeMemory
0x180020a35  jmp     loc_180020996
0x180020a3a  xor     edx, edx; pReserved
0x180020a3c  call    cs:__imp_WlanCloseHandle
0x180020a42  test    edi, edi
0x180020a44  jnz     short loc_180020A53
0x180020a46  test    r14d, r14d
0x180020a49  lea     eax, [rdi+1]
0x180020a4c  cmovz   edi, eax
0x180020a4f  jmp     short loc_180020A53
0x180020a51  mov     edi, esi
0x180020a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a5a  lea     rax, WPP_GLOBAL_Control
0x180020a61  cmp     rcx, rax
0x180020a64  jz      short loc_180020A84
0x180020a66  test    byte ptr [rcx+1Ch], 8
0x180020a6a  jz      short loc_180020A84
0x180020a6c  mov     rcx, [rcx+10h]
0x180020a70  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x180020a77  mov     edx, 38h ; '8'
0x180020a7c  mov     r9d, edi
0x180020a7f  call    WPP_SF_d
0x180020a84  mov     rbx, [rsp+50h+arg_8]
0x180020a8c  mov     eax, edi
0x180020a8e  add     rsp, 50h
0x180020a92  pop     r15
0x180020a94  pop     r14
0x180020a96  pop     r13
0x180020a98  pop     r12
0x180020a9a  pop     rdi
0x180020a9b  pop     rsi
0x180020a9c  pop     rbp
0x180020a9d  retn
```
