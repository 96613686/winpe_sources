# CCertTypeInfo::_GetTemplatesContainer(ldap *,ushort * *)

- ea: `0x1800325b8`
- end: `0x18003271d`
- name: `?_GetTemplatesContainer@CCertTypeInfo@@KAJPEAUldap@@PEAPEAG@Z`
- size: `357`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18000a630`
- `0x18000a920`

## callees

- `0x180005944`
- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x18000e52c`
- `0x18000f718`
- `0x1800325b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003268a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003268a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032707`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032707`

## string_xrefs

- `0x180032648`: `CN=Certificate Templates,CN=Public Key Services,CN=Services,`
- `0x1800326a9`: `CN=Certificate Templates,CN=Public Key Services,CN=Services,`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_GetTemplatesContainer(struct ldap *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // ecx
  int v7; // edx
  unsigned __int64 v8; // r11
  unsigned __int64 v9; // r11
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v13; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v14; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 v15; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  v13 = 0;
  if ( !a1 )
  {
    v4 = -2147467261;
    CSPrintErrorLineFile(0xAAE0328u, -2147467261);
    goto LABEL_22;
  }
  v5 = CAGetAuthoritativeDomainDn(a1, 0, &v13);
  v4 = v5;
  if ( v5 )
  {
    v6 = 179438376;
LABEL_5:
    v7 = v5;
LABEL_6:
    CSPrintErrorLineFile(v6, v7);
    goto LABEL_20;
  }
  v14 = 0;
  v5 = StringCchLengthW(v13, 0x10000u, &v14);
  v4 = v5;
  if ( v5 )
  {
    v6 = 179700520;
    goto LABEL_5;
  }
  v15 = 0;
  v5 = StringCchLengthW(L"CN=Certificate Templates,CN=Public Key Services,CN=Services,", v8, &v15);
  v4 = v5;
  if ( v5 )
  {
    v6 = 179962664;
    goto LABEL_5;
  }
  v10 = v15 + v14 + 1;
  if ( v10 > v9 )
  {
    v4 = -2147024362;
    v6 = 180355880;
    v7 = -2147024362;
    goto LABEL_6;
  }
  v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v10);
  v2 = v11;
  if ( !v11 )
  {
    v4 = -2147024882;
    v6 = 180814632;
    v7 = -2147024882;
    goto LABEL_6;
  }
  v5 = StringCchCopyW(v11, v10, L"CN=Certificate Templates,CN=Public Key Services,CN=Services,");
  v4 = v5;
  if ( v5 )
  {
    v6 = 181076776;
    goto LABEL_5;
  }
  v5 = StringCchCatW(v2, v10, v13);
  v4 = v5;
  if ( v5 )
  {
    v6 = 181273384;
    goto LABEL_5;
  }
  *a2 = v2;
  v2 = 0;
  v4 = 0;
LABEL_20:
  if ( v13 )
    CertFreeString(v13);
LABEL_22:
  LocalFree(v2);
  return v4;
}

```

## disassembly

```asm
0x1800325b8  mov     [rsp+arg_8], rbx
0x1800325bd  push    rsi
0x1800325be  push    rdi
0x1800325bf  push    r14
0x1800325c1  sub     rsp, 20h
0x1800325c5  xor     edi, edi
0x1800325c7  mov     [rsp+38h+arg_0], 0
0x1800325d0  mov     r14, rdx
0x1800325d3  test    rcx, rcx
0x1800325d6  jnz     short loc_1800325EE
0x1800325d8  mov     ebx, 80004003h
0x1800325dd  mov     ecx, 0AAE0328h; unsigned int
0x1800325e2  mov     edx, ebx; int
0x1800325e4  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800325e9  jmp     loc_180032704
0x1800325ee  lea     r8, [rsp+38h+arg_0]; unsigned __int16 **
0x1800325f3  xor     edx, edx; unsigned __int16 **
0x1800325f5  call    ?CAGetAuthoritativeDomainDn@@YAJPEAUldap@@PEAPEAG1@Z; CAGetAuthoritativeDomainDn(ldap *,ushort * *,ushort * *)
0x1800325fa  mov     ebx, eax
0x1800325fc  test    eax, eax
0x1800325fe  jz      short loc_180032611
0x180032600  mov     ecx, 0AB20328h; unsigned int
0x180032605  mov     edx, eax; int
0x180032607  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003260c  jmp     loc_1800326F2
0x180032611  mov     rcx, [rsp+38h+arg_0]; unsigned __int16 *
0x180032616  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x18003261b  mov     r11d, 10000h
0x180032621  mov     [rsp+38h+arg_10], rdi
0x180032626  mov     edx, r11d; unsigned __int64
0x180032629  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003262e  mov     ebx, eax
0x180032630  test    eax, eax
0x180032632  jz      short loc_18003263B
0x180032634  mov     ecx, 0AB60328h
0x180032639  jmp     short loc_180032605
0x18003263b  lea     r8, [rsp+38h+arg_18]; unsigned __int64 *
0x180032640  mov     [rsp+38h+arg_18], rdi
0x180032645  mov     rdx, r11; unsigned __int64
0x180032648  lea     rcx, aCnCertificateT_0; "CN=Certificate Templates,CN=Public Key "...
0x18003264f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180032654  mov     ebx, eax
0x180032656  test    eax, eax
0x180032658  jz      short loc_180032661
0x18003265a  mov     ecx, 0ABA0328h
0x18003265f  jmp     short loc_180032605
0x180032661  mov     rsi, [rsp+38h+arg_10]
0x180032666  inc     rsi
0x180032669  add     rsi, [rsp+38h+arg_18]
0x18003266e  cmp     rsi, r11
0x180032671  jbe     short loc_180032681
0x180032673  mov     ebx, 80070216h
0x180032678  mov     ecx, 0AC00328h
0x18003267d  mov     edx, ebx
0x18003267f  jmp     short loc_180032607
0x180032681  lea     rdx, [rsi+rsi]; uBytes
0x180032685  mov     ecx, 40h ; '@'; uFlags
0x18003268a  call    cs:__imp_LocalAlloc
0x180032690  mov     rdi, rax
0x180032693  test    rax, rax
0x180032696  jnz     short loc_1800326A9
0x180032698  mov     ebx, 8007000Eh
0x18003269d  mov     ecx, 0AC70328h
0x1800326a2  mov     edx, ebx
0x1800326a4  jmp     loc_180032607
0x1800326a9  lea     r8, aCnCertificateT_0; "CN=Certificate Templates,CN=Public Key "...
0x1800326b0  mov     rdx, rsi; unsigned __int64
0x1800326b3  mov     rcx, rdi; unsigned __int16 *
0x1800326b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800326bb  mov     ebx, eax
0x1800326bd  test    eax, eax
0x1800326bf  jz      short loc_1800326CB
0x1800326c1  mov     ecx, 0ACB0328h
0x1800326c6  jmp     loc_180032605
0x1800326cb  mov     r8, [rsp+38h+arg_0]; unsigned __int16 *
0x1800326d0  mov     rdx, rsi; unsigned __int64
0x1800326d3  mov     rcx, rdi; unsigned __int16 *
0x1800326d6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800326db  mov     ebx, eax
0x1800326dd  test    eax, eax
0x1800326df  jz      short loc_1800326EB
0x1800326e1  mov     ecx, 0ACE0328h
0x1800326e6  jmp     loc_180032605
0x1800326eb  mov     [r14], rdi
0x1800326ee  xor     edi, edi
0x1800326f0  xor     ebx, ebx
0x1800326f2  cmp     [rsp+38h+arg_0], 0
0x1800326f8  jz      short loc_180032704
0x1800326fa  mov     rcx, [rsp+38h+arg_0]; unsigned __int16 *
0x1800326ff  call    ?CertFreeString@@YAJPEAG@Z; CertFreeString(ushort *)
0x180032704  mov     rcx, rdi; hMem
0x180032707  call    cs:__imp_LocalFree
0x18003270d  mov     eax, ebx
0x18003270f  mov     rbx, [rsp+38h+arg_8]
0x180032714  add     rsp, 20h
0x180032718  pop     r14
0x18003271a  pop     rdi
0x18003271b  pop     rsi
0x18003271c  retn
```
