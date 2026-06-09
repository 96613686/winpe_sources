# StartList::ClearSessionSecureConfiguration(ATL::CRegKey &)

- ea: `0x14001ddc4`
- end: `0x14001de19`
- name: `?ClearSessionSecureConfiguration@StartList@@AEBAXAEAVCRegKey@ATL@@@Z`
- size: `85`
- prototype: `void(StartList *__hidden this, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001f728`

## callees

- `0x14000df20`
- `0x14001cb58`
- `0x14001ddc4`

## string_xrefs

- `0x14001ddd2`: `SecureConfiguration`

## pseudocode

```c
void __fastcall StartList::ClearSessionSecureConfiguration(StartList *this, HKEY *a2)
{
  unsigned int v2; // eax

  v2 = ATL::CRegKey::SetStringValue(a2, L"SecureConfiguration", (const BYTE *)&qword_14002AAD0);
  if ( v2 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v2);
}

```

## disassembly

```asm
0x14001ddc4  sub     rsp, 28h
0x14001ddc8  mov     rcx, rdx; this
0x14001ddcb  lea     r8, qword_14002AAD0; unsigned __int16 *
0x14001ddd2  lea     rdx, ?c_secureConfiguration@StartList@@0QBGB; "SecureConfiguration"
0x14001ddd9  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x14001ddde  test    eax, eax
0x14001dde0  jz      short loc_14001DE14
0x14001dde2  lea     rdx, WPP_GLOBAL_Control
0x14001dde9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddf0  cmp     rcx, rdx
0x14001ddf3  jz      short loc_14001DE14
0x14001ddf5  test    byte ptr [rcx+1Ch], 8
0x14001ddf9  jz      short loc_14001DE14
0x14001ddfb  mov     edx, 1Dh
0x14001de00  mov     r9d, eax
0x14001de03  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001de0a  mov     rcx, [rcx+10h]
0x14001de0e  call    WPP_SF_d
0x14001de13  nop
0x14001de14  add     rsp, 28h
0x14001de18  retn
```
