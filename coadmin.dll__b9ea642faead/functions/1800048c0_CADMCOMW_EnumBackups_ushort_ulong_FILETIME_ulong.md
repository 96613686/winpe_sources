# CADMCOMW::EnumBackups(ushort *,ulong *,_FILETIME *,ulong)

- ea: `0x1800048c0`
- end: `0x18000498c`
- name: `?EnumBackups@CADMCOMW@@UEAAJPEAGPEAKPEAU_FILETIME@@K@Z`
- size: `204`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned __int16 *, unsigned int *, struct _FILETIME *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001cec`
- `0x1800048c0`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000494e`
- `IisRTL!PuDbgPrint` at `0x18000494e`

## string_xrefs

- `0x180004935`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x18000493c`: `AccessCheck failed hr = 0x%08x\n`
- `0x18000492a`: `CADMCOMW::EnumBackups`

## pseudocode

```c
__int64 __fastcall CADMCOMW::EnumBackups(
        CADMCOMW *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        struct _FILETIME *a4,
        unsigned int a5)
{
  int v9; // eax
  unsigned int v10; // ebx

  v9 = CADMCOMW::AccessCheck(
         (__int64)this,
         0,
         &byte_1800127D8,
         2u,
         2u,
         0,
         (struct COpenHandle *)&g_ohMasterRootHandle,
         0,
         0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    return (*(unsigned int (__fastcall **)(_QWORD, unsigned __int16 *, unsigned int *, struct _FILETIME *, unsigned int))(**((_QWORD **)this + 4) + 432LL))(
             *((_QWORD *)this + 4),
             a2,
             a3,
             a4,
             a5);
  }
  else if ( (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
      3754,
      "CADMCOMW::EnumBackups",
      "AccessCheck failed hr = 0x%08x\n",
      v9);
  }
  return v10;
}

```

## disassembly

```asm
0x1800048c0  mov     r11, rsp
0x1800048c3  push    rbx
0x1800048c4  push    rbp
0x1800048c5  push    rsi
0x1800048c6  push    rdi
0x1800048c7  push    r14
0x1800048c9  sub     rsp, 50h
0x1800048cd  mov     qword ptr [r11-38h], 0
0x1800048d5  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x1800048dc  mov     qword ptr [r11-40h], 0
0x1800048e4  mov     rsi, r9
0x1800048e7  mov     [r11-48h], rax
0x1800048eb  mov     rbp, r8
0x1800048ee  mov     r14, rdx
0x1800048f1  mov     qword ptr [r11-50h], 0
0x1800048f9  mov     r9d, 2
0x1800048ff  lea     r8, byte_1800127D8
0x180004906  xor     edx, edx
0x180004908  mov     [r11-58h], r9d
0x18000490c  mov     rdi, rcx
0x18000490f  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180004914  mov     ebx, eax
0x180004916  test    eax, eax
0x180004918  jns     short loc_180004956
0x18000491a  test    byte ptr cs:g_dwDebugFlags, 3
0x180004921  jz      short loc_18000497F
0x180004923  mov     rcx, cs:g_pDebug
0x18000492a  lea     r9, aCadmcomwEnumba; "CADMCOMW::EnumBackups"
0x180004931  mov     [rsp+78h+var_50], eax
0x180004935  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000493c  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180004943  mov     r8d, 0EAAh
0x180004949  mov     [rsp+78h+var_58], rax
0x18000494e  call    cs:__imp_PuDbgPrint
0x180004954  jmp     short loc_18000497F
0x180004956  mov     rcx, [rdi+20h]
0x18000495a  mov     r9, rsi
0x18000495d  mov     edx, [rsp+78h+arg_20]
0x180004964  mov     r8, rbp
0x180004967  mov     dword ptr [rsp+78h+var_58], edx
0x18000496b  mov     rdx, r14
0x18000496e  mov     rax, [rcx]
0x180004971  mov     rax, [rax+1B0h]
0x180004978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497d  mov     ebx, eax
0x18000497f  mov     eax, ebx
0x180004981  add     rsp, 50h
0x180004985  pop     r14
0x180004987  pop     rdi
0x180004988  pop     rsi
0x180004989  pop     rbp
0x18000498a  pop     rbx
0x18000498b  retn
```
