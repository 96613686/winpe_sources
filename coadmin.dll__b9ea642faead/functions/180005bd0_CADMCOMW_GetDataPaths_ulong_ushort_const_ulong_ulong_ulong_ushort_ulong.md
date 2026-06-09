# CADMCOMW::GetDataPaths(ulong,ushort const *,ulong,ulong,ulong,ushort *,ulong *)

- ea: `0x180005bd0`
- end: `0x180005e85`
- name: `?GetDataPaths@CADMCOMW@@UEAAJKPEBGKKKPEAGPEAK@Z`
- size: `693`
- prototype: `__int64 __usercall@<rax>(CADMCOMW *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005bd0`
- `0x180007068`
- `0x18000716c`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180005d0b`
- `IisRTL!PuDbgPrint` at `0x180005d0b`

## string_xrefs

- `0x180005cf2`: `inetsrv\iis\mb\coadmin\comobj.cxx`

## pseudocode

```c
__int64 __fastcall CADMCOMW::GetDataPaths(
        CADMCOMW *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int16 *a7,
        unsigned int *a8)
{
  unsigned __int16 *v8; // rdi
  int v11; // ebx
  __int64 v12; // rcx
  unsigned int (__fastcall *v13)(__int64, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, unsigned int, unsigned __int16 *, unsigned int *); // rax
  int v14; // eax
  unsigned int v17; // [rsp+60h] [rbp-20h] BYREF
  int v18; // [rsp+64h] [rbp-1Ch] BYREF
  unsigned int v19; // [rsp+68h] [rbp-18h] BYREF
  int v20; // [rsp+6Ch] [rbp-14h] BYREF
  int v21; // [rsp+70h] [rbp-10h] BYREF
  struct COpenHandle *v22; // [rsp+78h] [rbp-8h] BYREF

  v8 = a7;
  v18 = 0;
  v22 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  if ( !a7 && a6 || a5 >= 6 || !a8 )
    return (unsigned int)-2147024809;
  v11 = CADMCOMW::LookupAndAccessCheck(this, a2, &v17, (__int64)a3, 1u, 0, 0, 0, 0, &v18, 0);
  if ( v11 >= 0 )
  {
    v12 = *((_QWORD *)this + 101);
    if ( !v12 )
      goto LABEL_21;
    if ( v18 == 1 )
    {
      v13 = *(unsigned int (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, unsigned int, unsigned __int16 *, unsigned int *))(*(_QWORD *)v12 + 88LL);
      return v13(v12, v17, a3, a4, a5, a6, a7, a8);
    }
    if ( v18 != 2 )
    {
LABEL_21:
      v12 = *((_QWORD *)this + 4);
      v13 = *(unsigned int (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, unsigned int, unsigned __int16 *, unsigned int *))(*(_QWORD *)v12 + 264LL);
      return v13(v12, v17, a3, a4, a5, a6, a7, a8);
    }
    v14 = CADMCOMW::Lookup(this, a2, &v17, &v19, &v22);
    v11 = v14;
    if ( v14 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, _DWORD, unsigned __int16 *, int *))(**((_QWORD **)this + 101) + 88LL))(
              *((_QWORD *)this + 101),
              v19,
              a3,
              a4,
              a5,
              0,
              a7,
              &v20);
      if ( v11 == -2147024774 )
      {
        v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, _DWORD, unsigned __int16 *, int *))(**((_QWORD **)this + 4) + 264LL))(
                *((_QWORD *)this + 4),
                v17,
                a3,
                a4,
                a5,
                0,
                a7,
                &v21);
        if ( v11 == -2147024774 )
        {
          if ( v20 + v21 <= a6 )
          {
            v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, int, unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 101) + 88LL))(
                    *((_QWORD *)this + 101),
                    v19,
                    a3,
                    a4,
                    a5,
                    v20,
                    a7,
                    a8);
            if ( v11 >= 0 )
            {
              if ( v20 )
                v8 = &a7[v20 - 1];
              return (unsigned int)(*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, unsigned int, int, unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 4) + 264LL))(
                                     *((_QWORD *)this + 4),
                                     v17,
                                     a3,
                                     a4,
                                     a5,
                                     v21,
                                     v8,
                                     a8);
            }
          }
          else
          {
            *a8 = v20 + v21;
            return (unsigned int)-2147024774;
          }
        }
      }
    }
    else if ( (g_dwDebugFlags & 4) != 0 )
    {
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 2220, &word_1800127E6, "*%08x\n", v14);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005bd0  mov     [rsp-38h+arg_0], rbx
0x180005bd5  mov     [rsp-38h+arg_18], r9d
0x180005bda  mov     [rsp-38h+arg_8], edx
0x180005bde  push    rbp
0x180005bdf  push    rsi
0x180005be0  push    rdi
0x180005be1  push    r12
0x180005be3  push    r13
0x180005be5  push    r14
0x180005be7  push    r15
0x180005be9  mov     rbp, rsp
0x180005bec  sub     rsp, 80h
0x180005bf3  mov     rdi, [rbp+arg_30]
0x180005bf7  mov     eax, edx
0x180005bf9  mov     r13d, [rbp+arg_28]
0x180005bfd  xor     edx, edx
0x180005bff  mov     [rbp+var_1C], edx
0x180005c02  mov     r12, r8
0x180005c05  mov     [rbp+var_8], rdx
0x180005c09  mov     rsi, rcx
0x180005c0c  mov     [rbp+var_20], edx
0x180005c0f  mov     [rbp+var_18], edx
0x180005c12  mov     [rbp+var_14], edx
0x180005c15  mov     [rbp+var_10], edx
0x180005c18  test    rdi, rdi
0x180005c1b  jnz     short loc_180005C26
0x180005c1d  test    r13d, r13d
0x180005c20  jnz     loc_180005E63
0x180005c26  mov     r15d, [rbp+arg_20]
0x180005c2a  cmp     r15d, 6
0x180005c2e  jnb     loc_180005E63
0x180005c34  mov     r14, [rbp+arg_38]
0x180005c38  test    r14, r14
0x180005c3b  jz      loc_180005E63
0x180005c41  mov     [rsp+80h+var_30], rdx
0x180005c46  lea     rcx, [rbp+var_1C]
0x180005c4a  mov     [rsp+80h+var_38], rcx
0x180005c4f  lea     r8, [rbp+var_20]
0x180005c53  mov     [rsp+80h+var_40], rdx
0x180005c58  mov     r9, r12
0x180005c5b  mov     [rsp+80h+var_48], rdx
0x180005c60  mov     rcx, rsi
0x180005c63  mov     [rsp+80h+var_50], rdx
0x180005c68  mov     [rsp+80h+var_58], edx
0x180005c6c  mov     edx, eax
0x180005c6e  mov     dword ptr [rsp+80h+var_60], 1
0x180005c76  call    ?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z; CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)
0x180005c7b  mov     ebx, eax
0x180005c7d  test    eax, eax
0x180005c7f  js      loc_180005E68
0x180005c85  mov     rcx, [rsi+328h]
0x180005c8c  test    rcx, rcx
0x180005c8f  jz      loc_180005E2E
0x180005c95  cmp     [rbp+var_1C], 1
0x180005c99  jnz     short loc_180005CA7
0x180005c9b  mov     rax, [rcx]
0x180005c9e  mov     rax, [rax+58h]
0x180005ca2  jmp     loc_180005E3C
0x180005ca7  cmp     [rbp+var_1C], 2
0x180005cab  jnz     loc_180005E2E
0x180005cb1  mov     edx, [rbp+arg_8]; unsigned int
0x180005cb4  lea     rax, [rbp+var_8]
0x180005cb8  lea     r9, [rbp+var_18]; unsigned int *
0x180005cbc  mov     [rsp+80h+var_60], rax; struct COpenHandle **
0x180005cc1  lea     r8, [rbp+var_20]; unsigned int *
0x180005cc5  mov     rcx, rsi; this
0x180005cc8  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x180005ccd  mov     ebx, eax
0x180005ccf  test    eax, eax
0x180005cd1  jns     short loc_180005D16
0x180005cd3  test    byte ptr cs:g_dwDebugFlags, 4
0x180005cda  jz      loc_180005E68
0x180005ce0  mov     rcx, cs:g_pDebug
0x180005ce7  lea     r9, word_1800127E6
0x180005cee  mov     [rsp+80h+var_58], eax
0x180005cf2  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180005cf9  lea     rax, a08x; "*%08x\n"
0x180005d00  mov     r8d, 8ACh
0x180005d06  mov     [rsp+80h+var_60], rax
0x180005d0b  call    cs:__imp_PuDbgPrint
0x180005d11  jmp     loc_180005E68
0x180005d16  mov     rcx, [rsi+328h]
0x180005d1d  lea     rdx, [rbp+var_14]
0x180005d21  mov     r9d, [rbp+arg_18]
0x180005d25  mov     r8, r12
0x180005d28  mov     [rsp+80h+var_48], rdx
0x180005d2d  mov     edx, [rbp+var_18]
0x180005d30  mov     rax, [rcx]
0x180005d33  mov     [rsp+80h+var_50], rdi
0x180005d38  mov     [rsp+80h+var_58], 0
0x180005d40  mov     dword ptr [rsp+80h+var_60], r15d
0x180005d45  mov     rax, [rax+58h]
0x180005d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d4e  mov     ebx, eax
0x180005d50  cmp     eax, 8007007Ah
0x180005d55  jnz     loc_180005E68
0x180005d5b  mov     rcx, [rsi+20h]
0x180005d5f  lea     rdx, [rbp+var_10]
0x180005d63  mov     r9d, [rbp+arg_18]
0x180005d67  mov     r8, r12
0x180005d6a  mov     [rsp+80h+var_48], rdx
0x180005d6f  mov     edx, [rbp+var_20]
0x180005d72  mov     rax, [rcx]
0x180005d75  mov     [rsp+80h+var_50], rdi
0x180005d7a  mov     [rsp+80h+var_58], 0
0x180005d82  mov     dword ptr [rsp+80h+var_60], r15d
0x180005d87  mov     rax, [rax+108h]
0x180005d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d93  mov     r8d, 8007007Ah
0x180005d99  mov     ebx, eax
0x180005d9b  cmp     eax, r8d
0x180005d9e  jnz     loc_180005E68
0x180005da4  mov     ecx, [rbp+var_10]
0x180005da7  mov     edx, [rbp+var_14]
0x180005daa  add     ecx, edx
0x180005dac  cmp     ecx, r13d
0x180005daf  jbe     short loc_180005DBC
0x180005db1  mov     [r14], ecx
0x180005db4  mov     ebx, r8d
0x180005db7  jmp     loc_180005E68
0x180005dbc  mov     rcx, [rsi+328h]
0x180005dc3  mov     r8, r12
0x180005dc6  mov     r13d, [rbp+arg_18]
0x180005dca  mov     r9d, r13d
0x180005dcd  mov     [rsp+80h+var_48], r14
0x180005dd2  mov     [rsp+80h+var_50], rdi
0x180005dd7  mov     rax, [rcx]
0x180005dda  mov     [rsp+80h+var_58], edx
0x180005dde  mov     edx, [rbp+var_18]
0x180005de1  mov     dword ptr [rsp+80h+var_60], r15d
0x180005de6  mov     rax, [rax+58h]
0x180005dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005def  mov     ebx, eax
0x180005df1  test    eax, eax
0x180005df3  js      short loc_180005E68
0x180005df5  mov     r10, [rsi+20h]
0x180005df9  mov     rax, [r10]
0x180005dfc  mov     r11, [rax+108h]
0x180005e03  mov     eax, [rbp+var_14]
0x180005e06  test    eax, eax
0x180005e08  jz      short loc_180005E10
0x180005e0a  dec     eax
0x180005e0c  lea     rdi, [rdi+rax*2]
0x180005e10  mov     r8d, [rbp+var_10]
0x180005e14  mov     r9d, r13d
0x180005e17  mov     [rsp+80h+var_48], r14
0x180005e1c  mov     rcx, r10
0x180005e1f  mov     [rsp+80h+var_50], rdi
0x180005e24  mov     rax, r11
0x180005e27  mov     [rsp+80h+var_58], r8d
0x180005e2c  jmp     short loc_180005E4F
0x180005e2e  mov     rcx, [rsi+20h]
0x180005e32  mov     rax, [rcx]
0x180005e35  mov     rax, [rax+108h]
0x180005e3c  mov     r9d, [rbp+arg_18]
0x180005e40  mov     [rsp+80h+var_48], r14
0x180005e45  mov     [rsp+80h+var_50], rdi
0x180005e4a  mov     [rsp+80h+var_58], r13d
0x180005e4f  mov     edx, [rbp+var_20]
0x180005e52  mov     r8, r12
0x180005e55  mov     dword ptr [rsp+80h+var_60], r15d
0x180005e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e5f  mov     ebx, eax
0x180005e61  jmp     short loc_180005E68
0x180005e63  mov     ebx, 80070057h
0x180005e68  mov     eax, ebx
0x180005e6a  mov     rbx, [rsp+80h+arg_0]
0x180005e72  add     rsp, 80h
0x180005e79  pop     r15
0x180005e7b  pop     r14
0x180005e7d  pop     r13
0x180005e7f  pop     r12
0x180005e81  pop     rdi
0x180005e82  pop     rsi
0x180005e83  pop     rbp
0x180005e84  retn
```
