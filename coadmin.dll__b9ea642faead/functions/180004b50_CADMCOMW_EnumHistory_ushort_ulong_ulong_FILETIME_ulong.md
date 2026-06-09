# CADMCOMW::EnumHistory(ushort *,ulong *,ulong *,_FILETIME *,ulong)

- ea: `0x180004b50`
- end: `0x180004c58`
- name: `?EnumHistory@CADMCOMW@@UEAAJPEAGPEAK1PEAU_FILETIME@@K@Z`
- size: `264`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned __int16 *, unsigned int *, unsigned int *, struct _FILETIME *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001cec`
- `0x180004b50`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180004c0c`
- `IisRTL!PuDbgPrint` at `0x180004c0c`

## string_xrefs

- `0x180004bf3`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180004bfa`: `AccessCheck failed hr = 0x%08x\n`
- `0x180004be8`: `CADMCOMW::EnumHistory`

## pseudocode

```c
__int64 __fastcall CADMCOMW::EnumHistory(
        CADMCOMW *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4,
        struct _FILETIME *a5,
        unsigned int a6)
{
  int v10; // eax
  unsigned int v11; // ebx

  if ( a2 && a3 && a4 && a5 )
  {
    v10 = CADMCOMW::AccessCheck(
            (__int64)this,
            0,
            &byte_1800127D8,
            2u,
            2u,
            0,
            (struct COpenHandle *)&g_ohMasterRootHandle,
            0,
            0);
    v11 = v10;
    if ( v10 >= 0 )
    {
      return (*(unsigned int (__fastcall **)(_QWORD, unsigned __int16 *, unsigned int *, unsigned int *, struct _FILETIME *, unsigned int))(**((_QWORD **)this + 4) + 496LL))(
               *((_QWORD *)this + 4),
               a2,
               a3,
               a4,
               a5,
               a6);
    }
    else if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        4239,
        "CADMCOMW::EnumHistory",
        "AccessCheck failed hr = 0x%08x\n",
        v10);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x180004b50  mov     r11, rsp
0x180004b53  push    rbx
0x180004b54  push    rbp
0x180004b55  push    rsi
0x180004b56  push    rdi
0x180004b57  push    r14
0x180004b59  push    r15
0x180004b5b  sub     rsp, 58h
0x180004b5f  mov     rsi, r9
0x180004b62  mov     rbp, r8
0x180004b65  mov     r14, rdx
0x180004b68  mov     r15, rcx
0x180004b6b  test    rdx, rdx
0x180004b6e  jz      loc_180004C44
0x180004b74  test    r8, r8
0x180004b77  jz      loc_180004C44
0x180004b7d  test    r9, r9
0x180004b80  jz      loc_180004C44
0x180004b86  mov     rdi, [rsp+88h+arg_20]
0x180004b8e  test    rdi, rdi
0x180004b91  jz      loc_180004C44
0x180004b97  mov     qword ptr [r11-48h], 0
0x180004b9f  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x180004ba6  mov     qword ptr [r11-50h], 0
0x180004bae  lea     r8, byte_1800127D8
0x180004bb5  mov     [r11-58h], rax
0x180004bb9  mov     r9d, 2
0x180004bbf  mov     qword ptr [r11-60h], 0
0x180004bc7  xor     edx, edx
0x180004bc9  mov     [r11-68h], r9d
0x180004bcd  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180004bd2  mov     ebx, eax
0x180004bd4  test    eax, eax
0x180004bd6  jns     short loc_180004C14
0x180004bd8  test    byte ptr cs:g_dwDebugFlags, 3
0x180004bdf  jz      short loc_180004C49
0x180004be1  mov     rcx, cs:g_pDebug
0x180004be8  lea     r9, aCadmcomwEnumhi; "CADMCOMW::EnumHistory"
0x180004bef  mov     [rsp+88h+var_60], eax
0x180004bf3  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180004bfa  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180004c01  mov     r8d, 108Fh
0x180004c07  mov     [rsp+88h+var_68], rax
0x180004c0c  call    cs:__imp_PuDbgPrint
0x180004c12  jmp     short loc_180004C49
0x180004c14  mov     rcx, [r15+20h]
0x180004c18  mov     r9, rsi
0x180004c1b  mov     edx, [rsp+88h+arg_28]
0x180004c22  mov     r8, rbp
0x180004c25  mov     [rsp+88h+var_60], edx
0x180004c29  mov     rdx, r14
0x180004c2c  mov     [rsp+88h+var_68], rdi
0x180004c31  mov     rax, [rcx]
0x180004c34  mov     rax, [rax+1F0h]
0x180004c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c40  mov     ebx, eax
0x180004c42  jmp     short loc_180004C49
0x180004c44  mov     ebx, 80070057h
0x180004c49  mov     eax, ebx
0x180004c4b  add     rsp, 58h
0x180004c4f  pop     r15
0x180004c51  pop     r14
0x180004c53  pop     rdi
0x180004c54  pop     rsi
0x180004c55  pop     rbp
0x180004c56  pop     rbx
0x180004c57  retn
```
