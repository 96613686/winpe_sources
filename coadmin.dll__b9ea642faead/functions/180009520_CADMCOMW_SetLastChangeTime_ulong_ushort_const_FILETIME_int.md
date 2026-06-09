# CADMCOMW::SetLastChangeTime(ulong,ushort const *,_FILETIME *,int)

- ea: `0x180009520`
- end: `0x180009670`
- name: `?SetLastChangeTime@CADMCOMW@@UEAAJKPEBGPEAU_FILETIME@@H@Z`
- size: `336`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, const unsigned __int16 *, FILETIME *lpLocalFileTime, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000238c`
- `0x18000716c`
- `0x180009520`
- `0x180010010`

## import_xrefs

- `KERNEL32!LocalFileTimeToFileTime` at `0x1800095b1`
- `KERNEL32!LocalFileTimeToFileTime` at `0x1800095b1`
- `KERNEL32!GetLastError` at `0x1800095bb`
- `KERNEL32!GetLastError` at `0x1800095bb`

## pseudocode

```c
__int64 __fastcall CADMCOMW::SetLastChangeTime(
        CADMCOMW *this,
        unsigned int a2,
        unsigned __int16 *a3,
        FILETIME *lpLocalFileTime,
        int a5)
{
  struct _FILETIME *p_FileTime; // rdi
  signed int v9; // ebx
  signed int LastError; // eax
  __int64 v11; // rcx
  signed int v12; // eax
  int v14; // [rsp+60h] [rbp-10h] BYREF
  int v15; // [rsp+64h] [rbp-Ch] BYREF
  struct _FILETIME FileTime; // [rsp+68h] [rbp-8h] BYREF
  unsigned int v17; // [rsp+B8h] [rbp+48h] BYREF

  p_FileTime = lpLocalFileTime;
  v17 = 0;
  FileTime = 0;
  v15 = 0;
  v14 = 0;
  if ( !lpLocalFileTime || !a2 )
  {
    v9 = -2147024809;
    goto LABEL_15;
  }
  v9 = CADMCOMW::LookupAndAccessCheck(this, a2, &v17, (__int64)a3, 0, 1, 0, 0, 0, &v14, (__int64)&v15);
  if ( v9 < 0 )
    goto LABEL_15;
  if ( !a5 )
    goto LABEL_9;
  if ( LocalFileTimeToFileTime(p_FileTime, &FileTime) )
  {
    p_FileTime = &FileTime;
LABEL_9:
    v11 = *((_QWORD *)this + 101);
    if ( v11 && v14 == 1 )
      v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, struct _FILETIME *))(*(_QWORD *)v11 + 144LL))(
              v11,
              v17,
              a3,
              p_FileTime);
    else
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, struct _FILETIME *))(**((_QWORD **)this + 4)
                                                                                              + 368LL))(
              *((_QWORD *)this + 4),
              v17,
              a3,
              p_FileTime);
    v9 = v12;
    goto LABEL_15;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
  if ( v15 )
    CADMCOMW::AuditAccess(this, 0x119Du, v9, a2, a3, 0, 0, 0, 0, 0, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009520  mov     r11, rsp
0x180009523  mov     [r11+8], rbx
0x180009527  mov     [r11+10h], rsi
0x18000952b  push    rbp
0x18000952c  push    rdi
0x18000952d  push    r12
0x18000952f  push    r14
0x180009531  push    r15
0x180009533  mov     rbp, rsp
0x180009536  sub     rsp, 70h
0x18000953a  xor     r12d, r12d
0x18000953d  mov     rdi, r9
0x180009540  mov     [rbp+arg_18], r12d
0x180009544  mov     r15, r8
0x180009547  mov     qword ptr [rbp+FileTime.dwLowDateTime], r12
0x18000954b  mov     r14d, edx
0x18000954e  mov     [rbp+var_C], r12d
0x180009552  mov     rsi, rcx
0x180009555  mov     [rbp+var_10], r12d
0x180009559  test    r9, r9
0x18000955c  jz      loc_180009614
0x180009562  test    edx, edx
0x180009564  jz      loc_180009614
0x18000956a  lea     rax, [rbp+var_C]
0x18000956e  mov     r9, r8
0x180009571  mov     [r11-48h], rax
0x180009575  lea     r8, [rbp+arg_18]
0x180009579  lea     rax, [rbp+var_10]
0x18000957d  mov     [r11-50h], rax
0x180009581  mov     [r11-58h], r12
0x180009585  mov     [r11-60h], r12
0x180009589  mov     [r11-68h], r12
0x18000958d  mov     [rsp+70h+var_48], 1
0x180009595  mov     [r11-78h], r12d
0x180009599  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x18000959e  mov     ebx, eax
0x1800095a0  test    eax, eax
0x1800095a2  js      short loc_180009619
0x1800095a4  cmp     [rbp+arg_20], r12d
0x1800095a8  jz      short loc_1800095D6
0x1800095aa  lea     rdx, [rbp+FileTime]; lpFileTime
0x1800095ae  mov     rcx, rdi; lpLocalFileTime
0x1800095b1  call    cs:__imp_LocalFileTimeToFileTime
0x1800095b7  test    eax, eax
0x1800095b9  jnz     short loc_1800095D2
0x1800095bb  call    cs:__imp_GetLastError
0x1800095c1  mov     ebx, eax
0x1800095c3  test    eax, eax
0x1800095c5  jle     short loc_180009619
0x1800095c7  movzx   ebx, ax
0x1800095ca  or      ebx, 80070000h
0x1800095d0  jmp     short loc_180009619
0x1800095d2  lea     rdi, [rbp+FileTime]
0x1800095d6  mov     rcx, [rsi+328h]
0x1800095dd  test    rcx, rcx
0x1800095e0  jz      short loc_1800095F4
0x1800095e2  cmp     [rbp+var_10], 1
0x1800095e6  jnz     short loc_1800095F4
0x1800095e8  mov     rax, [rcx]
0x1800095eb  mov     rax, [rax+90h]
0x1800095f2  jmp     short loc_180009602
0x1800095f4  mov     rcx, [rsi+20h]
0x1800095f8  mov     rax, [rcx]
0x1800095fb  mov     rax, [rax+170h]
0x180009602  mov     edx, [rbp+arg_18]
0x180009605  mov     r8, r15
0x180009608  mov     r9, rdi
0x18000960b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009610  mov     ebx, eax
0x180009612  jmp     short loc_180009619
0x180009614  mov     ebx, 80070057h
0x180009619  cmp     [rbp+var_C], r12d
0x18000961d  jz      short loc_180009655
0x18000961f  mov     [rsp+70h+var_20], r12; unsigned __int16 *
0x180009624  mov     r9d, r14d; unsigned int
0x180009627  mov     [rsp+70h+var_28], r12; struct _METADATA_RECORD *
0x18000962c  mov     r8d, ebx; int
0x18000962f  mov     [rsp+70h+var_30], r12; struct _METADATA_RECORD *
0x180009634  mov     edx, 119Dh; unsigned int
0x180009639  mov     [rsp+70h+var_38], r12d; unsigned int
0x18000963e  mov     rcx, rsi; this
0x180009641  mov     [rsp+70h+var_40], r12; unsigned __int16 *
0x180009646  mov     [rsp+70h+var_48], r12d; unsigned int
0x18000964b  mov     [rsp+70h+var_50], r15; unsigned __int16 *
0x180009650  call    ?AuditAccess@CADMCOMW@@AEAAJKJKPEBGK0KPEAU_METADATA_RECORD@@10@Z; CADMCOMW::AuditAccess(ulong,long,ulong,ushort const *,ulong,ushort const *,ulong,_METADATA_RECORD *,_METADATA_RECORD *,ushort const *)
0x180009655  lea     r11, [rsp+70h+var_s0]
0x18000965a  mov     eax, ebx
0x18000965c  mov     rbx, [r11+30h]
0x180009660  mov     rsi, [r11+38h]
0x180009664  mov     rsp, r11
0x180009667  pop     r15
0x180009669  pop     r14
0x18000966b  pop     r12
0x18000966d  pop     rdi
0x18000966e  pop     rbp
0x18000966f  retn
```
