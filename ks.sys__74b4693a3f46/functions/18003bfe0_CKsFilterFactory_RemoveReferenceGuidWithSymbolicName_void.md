# CKsFilterFactory::RemoveReferenceGuidWithSymbolicName(void)

- ea: `0x18003bfe0`
- end: `0x18003c105`
- name: `?RemoveReferenceGuidWithSymbolicName@CKsFilterFactory@@QEAAJXZ`
- size: `293`
- prototype: `__int64 __fastcall(CKsFilterFactory *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180056d04`

## callees

- `0x18000abec`
- `0x18000c630`
- `0x18003b8d0`
- `0x18003bfe0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c084`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18003c084`
- `ntoskrnl!ZwClose` at `0x18003c073`
- `ntoskrnl!ZwClose` at `0x18003c073`
- `ntoskrnl!ZwDeleteValueKey` at `0x18003c060`
- `ntoskrnl!ZwDeleteValueKey` at `0x18003c060`

## pseudocode

```c
__int64 __fastcall CKsFilterFactory::RemoveReferenceGuidWithSymbolicName(CKsFilterFactory *this)
{
  unsigned int v1; // ebx
  int v2; // edx
  CKsFilterFactory *v3; // r9
  int v4; // eax
  int v5; // r9d
  __int64 v7; // [rsp+28h] [rbp-40h]
  unsigned int v8; // [rsp+28h] [rbp-40h]
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+70h] [rbp+8h] BYREF

  v1 = 0;
  if ( !(unsigned int)IsEqualGUIDAligned(&this->m_ReferenceGUID, &GUID_9b365890_165f_11d0_a195_0020afd156e4) )
  {
    KeyHandle = 0;
    ValueName = 0;
    v4 = CKsFilterFactory::BuildKeyAndValueName(v3, &KeyHandle, &ValueName);
    v1 = v4;
    if ( v4 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v1;
      v5 = 54;
      v8 = v4;
      goto LABEL_8;
    }
    v1 = ZwDeleteValueKey(KeyHandle, &ValueName);
    ZwClose(KeyHandle);
    RtlFreeUnicodeString(&ValueName);
    if ( (v1 & 0x80000000) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v1;
      v5 = 55;
      v8 = v1;
LABEL_8:
      LOBYTE(v2) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        1,
        v5,
        (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
        v8);
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LODWORD(v7) = v1;
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v2,
      1,
      56,
      (__int64)WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids,
      v7);
  }
  return v1;
}

```

## disassembly

```asm
0x18003bfe0  push    rbx
0x18003bfe2  push    rsi
0x18003bfe3  push    rdi
0x18003bfe4  push    r14
0x18003bfe6  sub     rsp, 48h
0x18003bfea  mov     r9, rcx
0x18003bfed  lea     rdx, _GUID_9b365890_165f_11d0_a195_0020afd156e4
0x18003bff4  xor     edi, edi
0x18003bff6  add     rcx, 1ACh
0x18003bffd  mov     ebx, edi
0x18003bfff  call    IsEqualGUIDAligned
0x18003c004  lea     rsi, WPP_RECORDER_INITIALIZED
0x18003c00b  lea     r14, WPP_ea3b0a67dfee366f9593b42725d6a222_Traceguids
0x18003c012  test    eax, eax
0x18003c014  jnz     loc_18003C0C4
0x18003c01a  xorps   xmm0, xmm0
0x18003c01d  mov     [rsp+68h+KeyHandle], rdi
0x18003c022  lea     r8, [rsp+68h+ValueName]; struct _UNICODE_STRING *
0x18003c027  mov     rcx, r9; this
0x18003c02a  lea     rdx, [rsp+68h+KeyHandle]; void **
0x18003c02f  movups  xmmword ptr [rsp+68h+ValueName.Length], xmm0
0x18003c034  call    ?BuildKeyAndValueName@CKsFilterFactory@@QEAAJPEAPEAXPEAU_UNICODE_STRING@@@Z; CKsFilterFactory::BuildKeyAndValueName(void * *,_UNICODE_STRING *)
0x18003c039  mov     ebx, eax
0x18003c03b  test    eax, eax
0x18003c03d  jns     short loc_18003C056
0x18003c03f  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003c046  jz      loc_18003C0F8
0x18003c04c  lea     r9d, [rdi+36h]
0x18003c050  mov     dword ptr [rsp+68h+var_40], eax
0x18003c054  jmp     short loc_18003C0A7
0x18003c056  mov     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x18003c05b  lea     rdx, [rsp+68h+ValueName]; ValueName
0x18003c060  call    cs:__imp_ZwDeleteValueKey
0x18003c067  nop     dword ptr [rax+rax+00h]
0x18003c06c  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x18003c071  mov     ebx, eax
0x18003c073  call    cs:__imp_ZwClose
0x18003c07a  nop     dword ptr [rax+rax+00h]
0x18003c07f  lea     rcx, [rsp+68h+ValueName]; UnicodeString
0x18003c084  call    cs:__imp_RtlFreeUnicodeString
0x18003c08b  nop     dword ptr [rax+rax+00h]
0x18003c090  test    ebx, ebx
0x18003c092  jns     short loc_18003C0C4
0x18003c094  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003c09b  jz      short loc_18003C0F8
0x18003c09d  mov     r9d, 37h ; '7'
0x18003c0a3  mov     dword ptr [rsp+68h+var_40], ebx
0x18003c0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0ae  mov     r8d, 1
0x18003c0b4  mov     dl, 2
0x18003c0b6  mov     [rsp+68h+var_48], r14
0x18003c0bb  mov     rcx, [rcx+40h]
0x18003c0bf  call    WPP_RECORDER_SF_D
0x18003c0c4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003c0cb  jz      short loc_18003C0F8
0x18003c0cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0d4  cmp     [rcx+48h], di
0x18003c0d8  jz      short loc_18003C0F8
0x18003c0da  mov     rcx, [rcx+40h]
0x18003c0de  mov     r9d, 38h ; '8'
0x18003c0e4  mov     dword ptr [rsp+68h+var_40], ebx
0x18003c0e8  mov     dl, 5
0x18003c0ea  mov     [rsp+68h+var_48], r14
0x18003c0ef  lea     r8d, [r9-37h]
0x18003c0f3  call    WPP_RECORDER_SF_D
0x18003c0f8  mov     eax, ebx
0x18003c0fa  add     rsp, 48h
0x18003c0fe  pop     r14
0x18003c100  pop     rdi
0x18003c101  pop     rsi
0x18003c102  pop     rbx
0x18003c103  retn
```
