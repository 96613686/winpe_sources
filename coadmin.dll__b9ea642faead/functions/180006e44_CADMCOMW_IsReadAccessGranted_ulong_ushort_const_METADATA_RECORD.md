# CADMCOMW::IsReadAccessGranted(ulong,ushort const *,_METADATA_RECORD *)

- ea: `0x180006e44`
- end: `0x180006f03`
- name: `?IsReadAccessGranted@CADMCOMW@@QEAAJKPEBGPEAU_METADATA_RECORD@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, struct _METADATA_RECORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800049a0`
- `0x180005290`
- `0x180005a20`

## callees

- `0x180001cec`
- `0x180005048`
- `0x180006e44`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180006ef0`
- `KERNEL32!LocalFree` at `0x180006ef0`

## pseudocode

```c
__int64 __fastcall CADMCOMW::IsReadAccessGranted(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct _METADATA_RECORD *a4)
{
  int ClosestProp; // edi
  DWORD v5; // eax
  unsigned int v8; // [rsp+38h] [rbp-20h]
  unsigned int v9; // [rsp+40h] [rbp-18h]
  HLOCAL hMem; // [rsp+78h] [rbp+20h] BYREF

  ClosestProp = 0;
  v5 = a4->dwMDAttributes & 0x24;
  hMem = 0;
  if ( (_BYTE)v5 == 36 )
  {
    ClosestProp = CADMCOMW::FindClosestProp(
                    this,
                    a2,
                    a3,
                    (unsigned __int16 **)&hMem,
                    a4->dwMDIdentifier,
                    a4->dwMDDataType,
                    a4->dwMDUserType,
                    v8,
                    v9);
    if ( ClosestProp >= 0 )
    {
      if ( !hMem )
        return (unsigned int)-2146646015;
      ClosestProp = CADMCOMW::AccessCheck(
                      (__int64)this,
                      0,
                      (const unsigned __int16 *)hMem,
                      2u,
                      0,
                      0,
                      (struct COpenHandle *)&g_ohMasterRootHandle,
                      0,
                      0);
    }
    if ( hMem )
      LocalFree(hMem);
  }
  return (unsigned int)ClosestProp;
}

```

## disassembly

```asm
0x180006e44  mov     [rsp+arg_0], rsi
0x180006e49  push    rdi
0x180006e4a  sub     rsp, 50h
0x180006e4e  mov     eax, [r9+4]
0x180006e52  xor     edi, edi
0x180006e54  and     eax, 24h
0x180006e57  mov     [rsp+58h+hMem], rdi
0x180006e5c  mov     rsi, rcx
0x180006e5f  cmp     al, 24h ; '$'
0x180006e61  jnz     loc_180006EF6
0x180006e67  mov     eax, [r9+8]
0x180006e6b  mov     [rsp+58h+var_28], eax; unsigned int
0x180006e6f  mov     eax, [r9+0Ch]
0x180006e73  mov     [rsp+58h+var_30], eax; unsigned int
0x180006e77  mov     eax, [r9]
0x180006e7a  lea     r9, [rsp+58h+hMem]; unsigned __int16 **
0x180006e7f  mov     [rsp+58h+var_38], eax; unsigned int
0x180006e83  call    ?FindClosestProp@CADMCOMW@@QEAAJKPEBGPEAPEAGKKKKH@Z; CADMCOMW::FindClosestProp(ulong,ushort const *,ushort * *,ulong,ulong,ulong,ulong,int)
0x180006e88  mov     edi, eax
0x180006e8a  test    eax, eax
0x180006e8c  js      short loc_180006EE3
0x180006e8e  cmp     [rsp+58h+hMem], 0
0x180006e94  jnz     short loc_180006E9D
0x180006e96  mov     edi, 800CC801h
0x180006e9b  jmp     short loc_180006EF6
0x180006e9d  mov     r8, [rsp+58h+hMem]
0x180006ea2  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x180006ea9  mov     qword ptr [rsp+58h+var_18], 0
0x180006eb2  mov     r9d, 2
0x180006eb8  mov     [rsp+58h+var_20], 0
0x180006ec1  xor     edx, edx
0x180006ec3  mov     qword ptr [rsp+58h+var_28], rax
0x180006ec8  mov     rcx, rsi
0x180006ecb  mov     qword ptr [rsp+58h+var_30], 0
0x180006ed4  mov     [rsp+58h+var_38], 0
0x180006edc  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180006ee1  mov     edi, eax
0x180006ee3  cmp     [rsp+58h+hMem], 0
0x180006ee9  jz      short loc_180006EF6
0x180006eeb  mov     rcx, [rsp+58h+hMem]; hMem
0x180006ef0  call    cs:__imp_LocalFree
0x180006ef6  mov     rsi, [rsp+58h+arg_0]
0x180006efb  mov     eax, edi
0x180006efd  add     rsp, 50h
0x180006f01  pop     rdi
0x180006f02  retn
```
