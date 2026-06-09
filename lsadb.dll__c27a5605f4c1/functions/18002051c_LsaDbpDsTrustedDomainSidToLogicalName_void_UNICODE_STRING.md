# LsaDbpDsTrustedDomainSidToLogicalName(void *,_UNICODE_STRING *)

- ea: `0x18002051c`
- end: `0x1800206b7`
- name: `?LsaDbpDsTrustedDomainSidToLogicalName@@YAJPEAXPEAU_UNICODE_STRING@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(PSID Sid, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180016340`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x180011f90`
- `0x180012758`
- `0x18001f5c0`
- `0x18001fbcc`
- `0x18002051c`

## import_xrefs

- `LSASRV!LsapFreeLsaHeap` at `0x180020663`
- `LSASRV!LsapFreeLsaHeap` at `0x180020663`
- `ntdll!RtlLengthSid` at `0x180020609`
- `ntdll!RtlLengthSid` at `0x180020609`
- `ntdll!RtlValidSid` at `0x18002059a`
- `ntdll!RtlValidSid` at `0x18002059a`

## pseudocode

```c
__int64 __fastcall LsaDbpDsTrustedDomainSidToLogicalName(PSID Sid, struct _UNICODE_STRING *a2)
{
  int inited; // ebx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int128 v8; // [rsp+30h] [rbp-19h] BYREF
  _DWORD v9[2]; // [rsp+40h] [rbp-9h] BYREF
  _DWORD *v10; // [rsp+48h] [rbp-1h]
  __int128 v11; // [rsp+50h] [rbp+7h] BYREF
  __int128 v12; // [rsp+60h] [rbp+17h] BYREF
  __int128 *v13; // [rsp+70h] [rbp+27h]
  _DWORD v14[4]; // [rsp+78h] [rbp+2Fh] BYREF
  __int64 v15; // [rsp+88h] [rbp+3Fh]
  struct _UNICODE_STRING *v16; // [rsp+B8h] [rbp+6Fh] BYREF
  struct _DSNAME *v17; // [rsp+C0h] [rbp+77h] BYREF

  v16 = a2;
  v14[2] = 0;
  v13 = 0;
  v17 = 0;
  LOBYTE(v16) = 0;
  v9[1] = 0;
  v14[0] = dword_180047EA8;
  v12 = 0;
  v15 = 0;
  v8 = 0;
  v11 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids);
  if ( RtlValidSid(Sid) )
  {
    inited = LsaDbpDsInitAllocAsNeededEx(50331648, 2, &v16);
    if ( inited >= 0 )
    {
      LODWORD(v12) = 589945;
      v13 = &v8;
      DWORD2(v12) = 1;
      LODWORD(v8) = RtlLengthSid(Sid);
      *((_QWORD *)&v8 + 1) = Sid;
      inited = LsaDbpDsSearchUnique(0x20002u, qword_180047010, (struct _ATTRSIMPLE *)&v12, 1u, &v17);
      if ( inited >= 0 )
      {
        v10 = v14;
        v9[0] = 1;
        inited = LsaDbpDsReadByDsName(v17, 1u, (struct _ATTRBLOCKSIMPLE *)v9, (struct _ATTRBLOCKSIMPLE *)&v11);
        LsapFreeLsaHeap(v17, v6, v7);
      }
      LOBYTE(v5) = (_BYTE)v16;
      LsaDbpDsDeleteAllocAsNeededEx(50331648, 2, v5);
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids,
        (unsigned int)inited);
    return (unsigned int)inited;
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_49c8527826843b97b1b25aea330fd00e_Traceguids, 3221225485LL);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18002051c  mov     [rsp-8+arg_0], rbx
0x180020521  mov     [rsp-8+arg_8], rdx
0x180020526  push    rbp
0x180020527  push    rdi
0x180020528  push    r14
0x18002052a  lea     rbp, [rsp-47h]
0x18002052f  sub     rsp, 90h
0x180020536  xor     eax, eax
0x180020538  mov     [rbp+57h+var_20], 0
0x18002053f  xorps   xmm0, xmm0
0x180020542  mov     [rbp+57h+var_30], rax
0x180020546  mov     [rbp+57h+arg_10], rax
0x18002054a  mov     rdi, rcx
0x18002054d  mov     byte ptr [rbp+57h+arg_8], al
0x180020550  mov     [rbp+57h+var_5C], eax
0x180020553  mov     eax, cs:dword_180047EA8
0x180020559  mov     [rbp+57h+var_28], eax
0x18002055c  movups  [rbp+57h+var_40], xmm0
0x180020560  mov     [rbp+57h+var_18], 0
0x180020568  movups  [rbp+57h+var_70], xmm0
0x18002056c  movups  [rbp+57h+var_50], xmm0
0x180020570  mov     rcx, cs:WPP_GLOBAL_Control
0x180020577  mov     r14d, 1
0x18002057d  test    [rcx+1Ch], r14b
0x180020581  jz      short loc_180020597
0x180020583  mov     rcx, [rcx+10h]
0x180020587  lea     edx, [r14+31h]
0x18002058b  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x180020592  call    WPP_SF_
0x180020597  mov     rcx, rdi; Sid
0x18002059a  call    cs:__imp_RtlValidSid
0x1800205a0  test    al, al
0x1800205a2  jnz     short loc_1800205D6
0x1800205a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205ab  test    [rcx+1Ch], r14b
0x1800205af  jz      short loc_1800205CC
0x1800205b1  mov     rcx, [rcx+10h]
0x1800205b5  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x1800205bc  mov     edx, 33h ; '3'
0x1800205c1  mov     r9d, 0C000000Dh
0x1800205c7  call    WPP_SF_d
0x1800205cc  mov     eax, 0C000000Dh
0x1800205d1  jmp     loc_1800206A3
0x1800205d6  lea     r8, [rbp+57h+arg_8]
0x1800205da  mov     edx, 2
0x1800205df  mov     ecx, 3000000h
0x1800205e4  call    ?LsaDbpDsInitAllocAsNeededEx@@YAJKW4_LSAP_DB_OBJECT_TYPE_ID@@PEAE@Z; LsaDbpDsInitAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar *)
0x1800205e9  mov     ebx, eax
0x1800205eb  test    eax, eax
0x1800205ed  js      loc_18002067C
0x1800205f3  lea     rax, [rbp+57h+var_70]
0x1800205f7  mov     dword ptr [rbp+57h+var_40], 90079h
0x1800205fe  mov     rcx, rdi; Sid
0x180020601  mov     [rbp+57h+var_30], rax
0x180020605  mov     dword ptr [rbp+57h+var_40+8], r14d
0x180020609  call    cs:__imp_RtlLengthSid
0x18002060f  mov     rdx, cs:qword_180047010; struct _DSNAME *
0x180020616  lea     r8, [rbp+57h+var_40]; struct _ATTRSIMPLE *
0x18002061a  mov     dword ptr [rbp+57h+var_70], eax
0x18002061d  mov     r9d, r14d; unsigned int
0x180020620  lea     rax, [rbp+57h+arg_10]
0x180020624  mov     qword ptr [rbp+57h+var_70+8], rdi
0x180020628  mov     ecx, 20002h; unsigned int
0x18002062d  mov     [rsp+0A0h+var_80], rax; struct _DSNAME **
0x180020632  call    ?LsaDbpDsSearchUnique@@YAJKPEAU_DSNAME@@PEAU_ATTRSIMPLE@@KPEAPEAU1@@Z; LsaDbpDsSearchUnique(ulong,_DSNAME *,_ATTRSIMPLE *,ulong,_DSNAME * *)
0x180020637  mov     ebx, eax
0x180020639  test    eax, eax
0x18002063b  js      short loc_180020669
0x18002063d  mov     rcx, [rbp+57h+arg_10]; struct _DSNAME *
0x180020641  lea     rax, [rbp+57h+var_28]
0x180020645  lea     r9, [rbp+57h+var_50]; struct _ATTRBLOCKSIMPLE *
0x180020649  mov     [rbp+57h+var_58], rax
0x18002064d  lea     r8, [rbp+57h+var_60]; struct _ATTRBLOCKSIMPLE *
0x180020651  mov     [rbp+57h+var_60], r14d
0x180020655  mov     edx, r14d; unsigned int
0x180020658  call    ?LsaDbpDsReadByDsName@@YAJPEAU_DSNAME@@KPEAU_ATTRBLOCKSIMPLE@@1@Z; LsaDbpDsReadByDsName(_DSNAME *,ulong,_ATTRBLOCKSIMPLE *,_ATTRBLOCKSIMPLE *)
0x18002065d  mov     rcx, [rbp+57h+arg_10]
0x180020661  mov     ebx, eax
0x180020663  call    cs:__imp_LsapFreeLsaHeap
0x180020669  mov     r8b, byte ptr [rbp+57h+arg_8]
0x18002066d  mov     edx, 2
0x180020672  mov     ecx, 3000000h
0x180020677  call    ?LsaDbpDsDeleteAllocAsNeededEx@@YAXKW4_LSAP_DB_OBJECT_TYPE_ID@@E@Z; LsaDbpDsDeleteAllocAsNeededEx(ulong,_LSAP_DB_OBJECT_TYPE_ID,uchar)
0x18002067c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020683  test    [rcx+1Ch], r14b
0x180020687  jz      short loc_1800206A1
0x180020689  mov     rcx, [rcx+10h]
0x18002068d  lea     r8, WPP_49c8527826843b97b1b25aea330fd00e_Traceguids
0x180020694  mov     edx, 34h ; '4'
0x180020699  mov     r9d, ebx
0x18002069c  call    WPP_SF_d
0x1800206a1  mov     eax, ebx
0x1800206a3  mov     rbx, [rsp+0A0h+arg_0]
0x1800206ab  add     rsp, 90h
0x1800206b2  pop     r14
0x1800206b4  pop     rdi
0x1800206b5  pop     rbp
0x1800206b6  retn
```
