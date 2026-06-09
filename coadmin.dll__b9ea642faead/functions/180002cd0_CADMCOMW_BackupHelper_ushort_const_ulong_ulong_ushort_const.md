# CADMCOMW::BackupHelper(ushort const *,ulong,ulong,ushort const *)

- ea: `0x180002cd0`
- end: `0x180002e3e`
- name: `?BackupHelper@CADMCOMW@@AEAAJPEBGKK0@Z`
- size: `366`
- prototype: `__int64 __fastcall(CADMCOMW *this, const unsigned __int16 *, unsigned int, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002cb0`
- `0x180002e50`

## callees

- `0x180001cec`
- `0x180002cd0`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180002d63`
- `IisRTL!PuDbgPrint` at `0x180002d63`

## string_xrefs

- `0x180002d4a`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180002d51`: `AccessCheck failed hr = 0x%08x\n`
- `0x180002d3f`: `CADMCOMW::BackupHelper`

## pseudocode

```c
__int64 __fastcall CADMCOMW::BackupHelper(
        CADMCOMW *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        const unsigned __int16 *a5)
{
  unsigned int v5; // ebp
  const unsigned __int16 *v7; // r14
  int v10; // eax
  int v11; // edi
  __int64 **v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // r10
  int v15; // eax
  unsigned int v17; // [rsp+98h] [rbp+10h] BYREF

  v5 = 0;
  v7 = &byte_1800127D8;
  if ( a2 )
    v7 = a2;
  v17 = 0;
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
    v12 = (__int64 **)((char *)this + 32);
    if ( (a4 & 2) != 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64, int, unsigned int *))(**v12 + 280))(
              *v12,
              0,
              0,
              1,
              5000,
              &v17);
      if ( v11 < 0 )
      {
        if ( (a4 & 4) == 0 )
          goto LABEL_15;
        v5 = 837641;
        a4 &= 0xFFFFFFF9;
      }
    }
    v13 = *v12;
    v14 = **v12;
    if ( a5 )
      v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const unsigned __int16 *, _QWORD, int, const unsigned __int16 *))(v14 + 456))(
              v13,
              v17,
              v7,
              a3,
              a4,
              a5);
    else
      v15 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const unsigned __int16 *, _QWORD, int))(v14 + 400))(
              v13,
              v17,
              v7,
              a3,
              a4);
    v11 = v15;
  }
  else
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
        2994,
        "CADMCOMW::BackupHelper",
        "AccessCheck failed hr = 0x%08x\n",
        v10);
    v12 = (__int64 **)((char *)this + 32);
  }
LABEL_15:
  if ( v17 )
    v5 = (*(__int64 (__fastcall **)(__int64 *))(**v12 + 288))(*v12);
  if ( v11 )
    return (unsigned int)v11;
  return v5;
}

```

## disassembly

```asm
0x180002cd0  mov     r11, rsp
0x180002cd3  push    rbx
0x180002cd4  push    rbp
0x180002cd5  push    rsi
0x180002cd6  push    rdi
0x180002cd7  push    r14
0x180002cd9  push    r15
0x180002cdb  sub     rsp, 58h
0x180002cdf  xor     ebp, ebp
0x180002ce1  lea     rax, ?g_ohMasterRootHandle@@3VCOpenHandle@@A; COpenHandle g_ohMasterRootHandle
0x180002ce8  mov     [r11-48h], rbp
0x180002cec  test    rdx, rdx
0x180002cef  mov     [r11-50h], rbp
0x180002cf3  mov     r15d, r8d
0x180002cf6  mov     [r11-58h], rax
0x180002cfa  lea     r8, byte_1800127D8
0x180002d01  mov     r14, r8
0x180002d04  mov     [r11-60h], rbp
0x180002d08  cmovnz  r14, rdx
0x180002d0c  mov     [r11+10h], ebp
0x180002d10  mov     esi, r9d
0x180002d13  mov     dword ptr [rsp+88h+var_68], 2
0x180002d1b  xor     edx, edx
0x180002d1d  lea     r9d, [rbp+2]
0x180002d21  mov     rbx, rcx
0x180002d24  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180002d29  mov     edi, eax
0x180002d2b  test    eax, eax
0x180002d2d  jns     short loc_180002D72
0x180002d2f  test    byte ptr cs:g_dwDebugFlags, 3
0x180002d36  jz      short loc_180002D69
0x180002d38  mov     rcx, cs:g_pDebug
0x180002d3f  lea     r9, aCadmcomwBackup; "CADMCOMW::BackupHelper"
0x180002d46  mov     dword ptr [rsp+88h+var_60], eax
0x180002d4a  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180002d51  lea     rax, aAccesscheckFai; "AccessCheck failed hr = 0x%08x\n"
0x180002d58  mov     r8d, 0BB2h
0x180002d5e  mov     [rsp+88h+var_68], rax
0x180002d63  call    cs:__imp_PuDbgPrint
0x180002d69  add     rbx, 20h ; ' '
0x180002d6d  jmp     loc_180002E0B
0x180002d72  add     rbx, 20h ; ' '
0x180002d76  test    sil, 2
0x180002d7a  jz      short loc_180002DC2
0x180002d7c  mov     rcx, [rbx]
0x180002d7f  lea     rdx, [rsp+88h+arg_8]
0x180002d87  mov     [rsp+88h+var_60], rdx
0x180002d8c  mov     r9d, 1
0x180002d92  xor     r8d, r8d
0x180002d95  mov     dword ptr [rsp+88h+var_68], 1388h
0x180002d9d  xor     edx, edx
0x180002d9f  mov     rax, [rcx]
0x180002da2  mov     rax, [rax+118h]
0x180002da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dae  mov     edi, eax
0x180002db0  test    eax, eax
0x180002db2  jns     short loc_180002DC2
0x180002db4  test    sil, 4
0x180002db8  jz      short loc_180002E0B
0x180002dba  mov     ebp, 0CC809h
0x180002dbf  and     esi, 0FFFFFFF9h
0x180002dc2  mov     rcx, [rbx]
0x180002dc5  mov     r9d, r15d
0x180002dc8  mov     rax, [rsp+88h+arg_20]
0x180002dd0  mov     r8, r14
0x180002dd3  mov     edx, [rsp+88h+arg_8]
0x180002dda  mov     r10, [rcx]
0x180002ddd  test    rax, rax
0x180002de0  jnz     short loc_180002DF4
0x180002de2  mov     rax, [r10+190h]
0x180002de9  mov     dword ptr [rsp+88h+var_68], esi
0x180002ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df2  jmp     short loc_180002E09
0x180002df4  mov     [rsp+88h+var_60], rax
0x180002df9  mov     rax, [r10+1C8h]
0x180002e00  mov     dword ptr [rsp+88h+var_68], esi
0x180002e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e09  mov     edi, eax
0x180002e0b  mov     edx, [rsp+88h+arg_8]
0x180002e12  test    edx, edx
0x180002e14  jz      short loc_180002E2A
0x180002e16  mov     rcx, [rbx]
0x180002e19  mov     rax, [rcx]
0x180002e1c  mov     rax, [rax+120h]
0x180002e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e28  mov     ebp, eax
0x180002e2a  test    edi, edi
0x180002e2c  cmovnz  ebp, edi
0x180002e2f  mov     eax, ebp
0x180002e31  add     rsp, 58h
0x180002e35  pop     r15
0x180002e37  pop     r14
0x180002e39  pop     rdi
0x180002e3a  pop     rsi
0x180002e3b  pop     rbp
0x180002e3c  pop     rbx
0x180002e3d  retn
```
