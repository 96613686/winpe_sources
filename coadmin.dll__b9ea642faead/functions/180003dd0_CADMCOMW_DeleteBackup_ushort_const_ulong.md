# CADMCOMW::DeleteBackup(ushort const *,ulong)

- ea: `0x180003dd0`
- end: `0x180003ee5`
- name: `?DeleteBackup@CADMCOMW@@UEAAJPEBGK@Z`
- size: `277`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001cec`
- `0x18000238c`
- `0x180003dd0`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180003e61`
- `IisRTL!PuDbgPrint` at `0x180003e61`

## string_xrefs

- `0x180003e48`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180003e4f`: `AccessCheck failed hr = 0x%08x\n`
- `0x180003e3d`: `CADMCOMW::DeleteBackup`

## pseudocode

```c
__int64 __fastcall CADMCOMW::DeleteBackup(CADMCOMW *this, const unsigned __int16 *a2, unsigned int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+A8h] [rbp+20h] BYREF

  v9 = 0;
  v6 = CADMCOMW::AccessCheck(
         (__int64)this,
         0,
         &byte_1800127D8,
         2u,
         2u,
         0,
         (struct COpenHandle *)&g_ohMasterRootHandle,
         0,
         &v9);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD))(**((_QWORD **)this + 4) + 448LL))(
           *((_QWORD *)this + 4),
           a2,
           a3);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      3788,
      "CADMCOMW::DeleteBackup",
      "AccessCheck failed hr = 0x%08x\n",
      v6);
  }
  if ( v9 )
    CADMCOMW::AuditAccess(this, 0x119Fu, v7, 0, 0, 0, 0, 0, 0, 0, a2);
  return v7;
}

```

## disassembly

```asm
0x180003dd0  mov     r11, rsp
0x180003dd3  push    rbx
0x180003dd4  push    rbp
0x180003dd5  push    rsi
0x180003dd6  push    rdi
0x180003dd7  sub     rsp, 68h
0x180003ddb  lea     rax, [r11+20h]
0x180003ddf  mov     dword ptr [r11+20h], 0
0x180003de7  mov     [r11-48h], rax
0x180003deb  mov     ebp, r8d
0x180003dee  mov     qword ptr [r11-50h], 0
0x180003df6  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x180003dfd  mov     [r11-58h], rax
0x180003e01  lea     r8, byte_1800127D8
0x180003e08  mov     rsi, rdx
0x180003e0b  mov     qword ptr [r11-60h], 0
0x180003e13  mov     r9d, 2
0x180003e19  xor     edx, edx
0x180003e1b  mov     [r11-68h], r9d
0x180003e1f  mov     rdi, rcx
0x180003e22  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180003e27  mov     ebx, eax
0x180003e29  test    eax, eax
0x180003e2b  jns     short loc_180003E69
0x180003e2d  test    byte ptr cs:g_dwDebugFlags, 3
0x180003e34  jz      short loc_180003E84
0x180003e36  mov     rcx, cs:g_pDebug
0x180003e3d  lea     r9, aCadmcomwDelete; "CADMCOMW::DeleteBackup"
0x180003e44  mov     [rsp+88h+var_60], eax
0x180003e48  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180003e4f  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180003e56  mov     r8d, 0ECCh
0x180003e5c  mov     [rsp+88h+var_68], rax
0x180003e61  call    cs:__imp_PuDbgPrint
0x180003e67  jmp     short loc_180003E84
0x180003e69  mov     rcx, [rdi+20h]
0x180003e6d  mov     r8d, ebp
0x180003e70  mov     rdx, rsi
0x180003e73  mov     rax, [rcx]
0x180003e76  mov     rax, [rax+1C0h]
0x180003e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e82  mov     ebx, eax
0x180003e84  cmp     [rsp+88h+arg_18], 0
0x180003e8c  jz      short loc_180003EDA
0x180003e8e  mov     [rsp+88h+var_38], rsi; unsigned __int16 *
0x180003e93  xor     r9d, r9d; unsigned int
0x180003e96  mov     [rsp+88h+var_40], 0; struct _METADATA_RECORD *
0x180003e9f  mov     r8d, ebx; int
0x180003ea2  mov     [rsp+88h+var_48], 0; struct _METADATA_RECORD *
0x180003eab  mov     edx, 119Fh; unsigned int
0x180003eb0  mov     [rsp+88h+var_50], 0; unsigned int
0x180003eb8  mov     rcx, rdi; this
0x180003ebb  mov     [rsp+88h+var_58], 0; unsigned __int16 *
0x180003ec4  mov     [rsp+88h+var_60], 0; unsigned int
0x180003ecc  mov     [rsp+88h+var_68], 0; unsigned __int16 *
0x180003ed5  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180003eda  mov     eax, ebx
0x180003edc  add     rsp, 68h
0x180003ee0  pop     rdi
0x180003ee1  pop     rsi
0x180003ee2  pop     rbp
0x180003ee3  pop     rbx
0x180003ee4  retn
```
