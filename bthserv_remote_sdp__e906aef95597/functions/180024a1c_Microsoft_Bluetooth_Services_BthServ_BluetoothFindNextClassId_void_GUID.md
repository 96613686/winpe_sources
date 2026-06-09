# Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(void *,_GUID *)

- ea: `0x180024a1c`
- end: `0x180024a83`
- name: `?BluetoothFindNextClassId@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAU_GUID@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ **this, struct _BLUETOOTH_SDP_RECORD *, struct _GUID *, struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180025648`
- `0x180026808`
- `0x180026dec`
- `0x180027ea8`

## callees

- `0x180024a1c`
- `0x180027788`
- `0x180028490`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024a69`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextClassId(
        Microsoft::Bluetooth::Services::BthServ **this,
        struct _BLUETOOTH_SDP_RECORD *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  unsigned int v4; // edi
  Microsoft::Bluetooth::Services::BthServ *v6; // rcx
  void *v7; // r8
  DWORD v8; // ecx

  v4 = 0;
  if ( !this )
  {
    v8 = 6;
    goto LABEL_8;
  }
  v6 = *this;
  if ( !v6 || v6 >= this[1] )
  {
    v8 = 259;
LABEL_8:
    SetLastError(v8);
    return v4;
  }
  v4 = Microsoft::Bluetooth::Services::BthServ::BthpTransposeToUUID(v6, a2, a2, a4);
  if ( v4 )
    *this = Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(*this, this[1], v7);
  return v4;
}

```

## disassembly

```asm
0x180024a1c  mov     [rsp+arg_0], rbx
0x180024a21  push    rdi
0x180024a22  sub     rsp, 20h
0x180024a26  xor     edi, edi
0x180024a28  mov     rbx, rcx
0x180024a2b  test    rcx, rcx
0x180024a2e  jz      short loc_180024A64
0x180024a30  mov     rcx, [rcx]; this
0x180024a33  test    rcx, rcx
0x180024a36  jz      short loc_180024A5D
0x180024a38  cmp     rcx, [rbx+8]
0x180024a3c  jnb     short loc_180024A5D
0x180024a3e  mov     r8, rdx; void *
0x180024a41  call    ?BthpTransposeToUUID@BthServ@Services@Bluetooth@Microsoft@@YAHPEAU_BLUETOOTH_SDP_RECORD@@PEAXPEAU_GUID@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpTransposeToUUID(_BLUETOOTH_SDP_RECORD *,void *,_GUID *)
0x180024a46  mov     edi, eax
0x180024a48  test    eax, eax
0x180024a4a  jz      short loc_180024A75
0x180024a4c  mov     rdx, [rbx+8]; struct _BLUETOOTH_SDP_RECORD *
0x180024a50  mov     rcx, [rbx]; this
0x180024a53  call    ?BthpNextRecord@BthServ@Services@Bluetooth@Microsoft@@YAPEAU_BLUETOOTH_SDP_RECORD@@PEAU5@PEAX@Z; Microsoft::Bluetooth::Services::BthServ::BthpNextRecord(_BLUETOOTH_SDP_RECORD *,void *)
0x180024a58  mov     [rbx], rax
0x180024a5b  jmp     short loc_180024A75
0x180024a5d  mov     ecx, 103h
0x180024a62  jmp     short loc_180024A69
0x180024a64  mov     ecx, 6; dwErrCode
0x180024a69  call    cs:__imp_SetLastError
0x180024a70  nop     dword ptr [rax+rax+00h]
0x180024a75  mov     rbx, [rsp+28h+arg_0]
0x180024a7a  mov     eax, edi
0x180024a7c  add     rsp, 20h
0x180024a80  pop     rdi
0x180024a81  retn
```
