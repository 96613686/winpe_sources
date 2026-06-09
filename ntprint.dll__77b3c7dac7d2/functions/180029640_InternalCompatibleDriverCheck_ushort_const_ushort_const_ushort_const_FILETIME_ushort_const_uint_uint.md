# InternalCompatibleDriverCheck(ushort const *,ushort const *,ushort const *,_FILETIME *,ushort const *,uint,uint *)

- ea: `0x180029640`
- end: `0x180029703`
- name: `?InternalCompatibleDriverCheck@@YAJPEBG00PEAU_FILETIME@@0IPEAI@Z`
- size: `195`
- prototype: `__int64 __fastcall(PCWSTR Key, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME *, const unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002a060`

## callees

- `0x180018d18`
- `0x180029640`
- `0x18002970c`

## import_xrefs

- `SETUPAPI!SetupOpenInfFileW` at `0x18002969a`
- `SETUPAPI!SetupOpenInfFileW` at `0x18002969a`
- `SETUPAPI!SetupCloseInfFile` at `0x1800296e5`
- `SETUPAPI!SetupCloseInfFile` at `0x1800296e5`

## pseudocode

```c
__int64 __fastcall InternalCompatibleDriverCheck(
        PCWSTR Key,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FILETIME *a4,
        const unsigned __int16 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  HINF v11; // rsi
  int LastErrorAsHResult; // ebx

  if ( Key && a2 && a3 && a4 && a7 )
  {
    *a7 = 0;
    v11 = SetupOpenInfFileW(cszUpgradeInf, 0, 0x42u, 0);
    if ( v11 != (HINF)-1LL || (LastErrorAsHResult = GetLastErrorAsHResult(), LastErrorAsHResult >= 0) )
    {
      LastErrorAsHResult = InternalCompatibleInfDriverCheck(Key, a2, a3, a4, v11, a6, a7);
      if ( v11 != (HINF)-1LL )
        SetupCloseInfFile(v11);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x180029640  push    rbx
0x180029642  push    rbp
0x180029643  push    rsi
0x180029644  push    rdi
0x180029645  push    r12
0x180029647  push    r14
0x180029649  push    r15
0x18002964b  sub     rsp, 40h
0x18002964f  mov     rbp, r9
0x180029652  mov     r14, r8
0x180029655  mov     r15, rdx
0x180029658  mov     r12, rcx
0x18002965b  test    rcx, rcx
0x18002965e  jz      loc_1800296ED
0x180029664  test    rdx, rdx
0x180029667  jz      loc_1800296ED
0x18002966d  test    r8, r8
0x180029670  jz      short loc_1800296ED
0x180029672  test    r9, r9
0x180029675  jz      short loc_1800296ED
0x180029677  mov     rdi, [rsp+78h+arg_30]
0x18002967f  test    rdi, rdi
0x180029682  jz      short loc_1800296ED
0x180029684  xor     r9d, r9d; ErrorLine
0x180029687  mov     dword ptr [rdi], 0
0x18002968d  xor     edx, edx; InfClass
0x18002968f  lea     rcx, ?cszUpgradeInf@@3PAGA; "printupg.inf"
0x180029696  lea     r8d, [r9+42h]; InfStyle
0x18002969a  call    cs:__imp_SetupOpenInfFileW
0x1800296a0  mov     rsi, rax
0x1800296a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800296a7  jnz     short loc_1800296B4
0x1800296a9  call    GetLastErrorAsHResult
0x1800296ae  mov     ebx, eax
0x1800296b0  test    eax, eax
0x1800296b2  js      short loc_1800296F2
0x1800296b4  mov     ecx, [rsp+78h+arg_28]
0x1800296bb  mov     r9, rbp; struct _FILETIME *
0x1800296be  mov     [rsp+78h+var_48], rdi; unsigned int *
0x1800296c3  mov     r8, r14; unsigned __int16 *
0x1800296c6  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800296ca  mov     rdx, r15; unsigned __int16 *
0x1800296cd  mov     rcx, r12; Key
0x1800296d0  mov     [rsp+78h+var_58], rsi; void *
0x1800296d5  call    ?InternalCompatibleInfDriverCheck@@YAJPEBG00PEAU_FILETIME@@PEAXIPEAI@Z; InternalCompatibleInfDriverCheck(ushort const *,ushort const *,ushort const *,_FILETIME *,void *,uint,uint *)
0x1800296da  mov     ebx, eax
0x1800296dc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800296e0  jz      short loc_1800296F2
0x1800296e2  mov     rcx, rsi; InfHandle
0x1800296e5  call    cs:__imp_SetupCloseInfFile
0x1800296eb  jmp     short loc_1800296F2
0x1800296ed  mov     ebx, 80070057h
0x1800296f2  mov     eax, ebx
0x1800296f4  add     rsp, 40h
0x1800296f8  pop     r15
0x1800296fa  pop     r14
0x1800296fc  pop     r12
0x1800296fe  pop     rdi
0x1800296ff  pop     rsi
0x180029700  pop     rbp
0x180029701  pop     rbx
0x180029702  retn
```
