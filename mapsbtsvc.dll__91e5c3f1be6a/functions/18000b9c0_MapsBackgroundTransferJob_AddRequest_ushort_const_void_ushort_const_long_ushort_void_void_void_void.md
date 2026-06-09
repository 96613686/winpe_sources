# MapsBackgroundTransferJob::AddRequest(ushort const *,void (*)(ushort const *,long,ushort *,void *,void *),void *,void *)

- ea: `0x18000b9c0`
- end: `0x18000bb5e`
- name: `?AddRequest@MapsBackgroundTransferJob@@UEAAJPEBGP6AX0JPEAGPEAX2@Z22@Z`
- size: `414`
- prototype: `int __fastcall(MapsBackgroundTransferJob *this, const unsigned __int16 *, void (*)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *), void *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001e70`
- `0x18000abac`
- `0x18000b9c0`
- `0x18000bb70`
- `0x18000d508`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000ba2a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18000ba2a`
- `ZTrace_Maps!ZTraceHelper` at `0x18000ba89`
- `ZTrace_Maps!ZTraceHelper` at `0x18000ba89`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000ba46`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000ba46`

## string_xrefs

- `0x18000ba68`: `Thread running in unsupported apartment - APTTYPE: %d | APTTYPEQUALIFIER: %d. Marshalling call through another thread`

## pseudocode

```c
int __fastcall MapsBackgroundTransferJob::AddRequest(
        MapsBackgroundTransferJob *this,
        const unsigned __int16 *a2,
        void (*a3)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *),
        void *a4,
        void *a5)
{
  int ApartmentType; // eax
  int v7; // r8d
  int v8; // ecx
  int v10; // ebx
  _QWORD *v11; // rdx
  APTTYPE pAptType; // [rsp+48h] [rbp-41h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+4Ch] [rbp-3Dh] BYREF
  MapsBackgroundTransferJob *v14; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v15; // [rsp+58h] [rbp-31h]
  void (*v16)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *); // [rsp+60h] [rbp-29h]
  void *v17; // [rsp+68h] [rbp-21h]
  void *v18; // [rsp+70h] [rbp-19h]
  _QWORD v19[7]; // [rsp+78h] [rbp-11h] BYREF
  _QWORD *v20; // [rsp+B0h] [rbp+27h]
  const unsigned __int16 *v21; // [rsp+F0h] [rbp+67h] BYREF
  void (*v22)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *); // [rsp+F8h] [rbp+6Fh] BYREF
  void *v23; // [rsp+100h] [rbp+77h] BYREF

  v23 = a4;
  v22 = a3;
  v21 = a2;
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  lambda_6e58ab9661acc4b93fb68d9bbc634d5b_::_lambda_6e58ab9661acc4b93fb68d9bbc634d5b_(
    (unsigned int)&v14,
    (_DWORD)this,
    (unsigned int)&v21,
    (unsigned int)&v22,
    (__int64)&v23,
    (__int64)&a5);
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
  {
    v7 = 727;
LABEL_3:
    v8 = ApartmentType;
    return ZTraceReportPropagation(v8, "MapsBackgroundTransferJob::AddRequest", v7, this);
  }
  if ( pAptType == APTTYPE_MTA )
  {
    ApartmentType = MapsBackgroundTransferJob::AddRequestWithRanges(v14, v15, 0, 0, v16, v17, v18);
    if ( ApartmentType < 0 )
    {
      v7 = 745;
      goto LABEL_3;
    }
  }
  else
  {
    ZTraceHelper(
      2,
      "MapsBackgroundTransferJob::AddRequest",
      739,
      this,
      "Thread running in unsupported apartment - APTTYPE: %d | APTTYPEQUALIFIER: %d. Marshalling call through another thread",
      pAptType,
      pAptQualifier);
    v19[0] = off_180016308;
    v19[1] = v14;
    v19[2] = v15;
    v19[3] = v16;
    v19[4] = v17;
    v19[5] = v18;
    v20 = v19;
    v10 = MapsBackgroundTransferJob::MTA_Send(this, v19);
    if ( v20 )
    {
      v11 = v19;
      LOBYTE(v11) = v20 != v19;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v20 + 32LL))(v20, v11);
    }
    if ( v10 < 0 )
    {
      v7 = 741;
      v8 = v10;
      return ZTraceReportPropagation(v8, "MapsBackgroundTransferJob::AddRequest", v7, this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b9c0  mov     rax, rsp
0x18000b9c3  mov     [rax+20h], r9
0x18000b9c7  mov     [rax+18h], r8
0x18000b9cb  mov     [rax+10h], rdx
0x18000b9cf  push    rbp
0x18000b9d0  push    rbx
0x18000b9d1  push    rdi
0x18000b9d2  lea     rbp, [rax-57h]
0x18000b9d6  sub     rsp, 0C0h
0x18000b9dd  mov     rax, cs:__security_cookie
0x18000b9e4  xor     rax, rsp
0x18000b9e7  mov     [rbp+4Fh+var_20], rax
0x18000b9eb  mov     rdi, rcx
0x18000b9ee  mov     [rbp+4Fh+pAptType], 0
0x18000b9f5  mov     [rbp+4Fh+pAptQualifier], 0
0x18000b9fc  lea     rax, [rbp+4Fh+arg_20]
0x18000ba00  mov     [rsp+0D0h+var_A8], rax
0x18000ba05  lea     rax, [rbp+4Fh+arg_18]
0x18000ba09  mov     [rsp+0D0h+var_B0], rax
0x18000ba0e  lea     r9, [rbp+4Fh+arg_10]
0x18000ba12  lea     r8, [rbp+4Fh+arg_8]
0x18000ba16  mov     rdx, rcx
0x18000ba19  lea     rcx, [rbp+4Fh+var_88]
0x18000ba1d  call    _lambda_6e58ab9661acc4b93fb68d9bbc634d5b____lambda_6e58ab9661acc4b93fb68d9bbc634d5b_
0x18000ba22  lea     rdx, [rbp+4Fh+pAptQualifier]; pAptQualifier
0x18000ba26  lea     rcx, [rbp+4Fh+pAptType]; pAptType
0x18000ba2a  call    cs:__imp_CoGetApartmentType
0x18000ba30  test    eax, eax
0x18000ba32  jns     short loc_18000BA51
0x18000ba34  mov     r8d, 2D7h
0x18000ba3a  mov     ecx, eax
0x18000ba3c  mov     r9, rdi
0x18000ba3f  lea     rdx, aMapsbackground_23; "MapsBackgroundTransferJob::AddRequest"
0x18000ba46  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000ba4c  jmp     loc_18000BB47
0x18000ba51  mov     ecx, [rbp+4Fh+pAptType]
0x18000ba54  cmp     ecx, 1
0x18000ba57  jz      loc_18000BB08
0x18000ba5d  mov     eax, [rbp+4Fh+pAptQualifier]
0x18000ba60  mov     [rsp+30h], eax
0x18000ba64  mov     dword ptr [rsp+0D0h+var_A8], ecx
0x18000ba68  lea     rax, aThreadRunningI; "Thread running in unsupported apartment"...
0x18000ba6f  mov     [rsp+0D0h+var_B0], rax
0x18000ba74  mov     r9, rdi
0x18000ba77  mov     r8d, 2E3h
0x18000ba7d  lea     rdx, aMapsbackground_23; "MapsBackgroundTransferJob::AddRequest"
0x18000ba84  mov     ecx, 2
0x18000ba89  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000ba8f  lea     rax, off_180016308
0x18000ba96  mov     [rbp+4Fh+var_60], rax
0x18000ba9a  mov     rax, [rbp+4Fh+var_88]
0x18000ba9e  mov     [rbp+4Fh+var_58], rax
0x18000baa2  mov     rax, [rbp+4Fh+var_80]
0x18000baa6  mov     [rbp+4Fh+var_50], rax
0x18000baaa  mov     rax, [rbp+4Fh+var_78]
0x18000baae  mov     [rbp+4Fh+var_48], rax
0x18000bab2  mov     rax, [rbp+4Fh+var_70]
0x18000bab6  mov     [rbp+4Fh+var_40], rax
0x18000baba  mov     rax, [rbp+4Fh+var_68]
0x18000babe  mov     [rbp+4Fh+var_38], rax
0x18000bac2  lea     rax, [rbp+4Fh+var_60]
0x18000bac6  mov     [rbp+4Fh+var_28], rax
0x18000baca  lea     rdx, [rbp+4Fh+var_60]
0x18000bace  mov     rcx, rdi
0x18000bad1  call    ?MTA_Send@MapsBackgroundTransferJob@@AEAAJAEBV?$function@$$A6AJXZ@std@@@Z; MapsBackgroundTransferJob::MTA_Send(std::function<long (void)> const &)
0x18000bad6  mov     ebx, eax
0x18000bad8  mov     rcx, [rbp+4Fh+var_28]
0x18000badc  test    rcx, rcx
0x18000badf  jz      short loc_18000BAF7
0x18000bae1  mov     rax, [rcx]
0x18000bae4  lea     rdx, [rbp+4Fh+var_60]
0x18000bae8  cmp     rcx, rdx
0x18000baeb  setnz   dl
0x18000baee  mov     rax, [rax+20h]
0x18000baf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf7  test    ebx, ebx
0x18000baf9  jns     short loc_18000BB45
0x18000bafb  mov     r8d, 2E5h
0x18000bb01  mov     ecx, ebx
0x18000bb03  jmp     loc_18000BA3C
0x18000bb08  mov     rax, [rbp+4Fh+var_68]
0x18000bb0c  mov     [rsp+30h], rax; void *
0x18000bb11  mov     rax, [rbp+4Fh+var_70]
0x18000bb15  mov     [rsp+0D0h+var_A8], rax; void *
0x18000bb1a  mov     rax, [rbp+4Fh+var_78]
0x18000bb1e  mov     [rsp+0D0h+var_B0], rax; void (*)(const unsigned __int16 *, int, unsigned __int16 *, void *, void *)
0x18000bb23  xor     r9d, r9d; struct MAPSBTSVC_RANGE *
0x18000bb26  xor     r8d, r8d; unsigned int
0x18000bb29  mov     rdx, [rbp+4Fh+var_80]; unsigned __int16 *
0x18000bb2d  mov     rcx, [rbp+4Fh+var_88]; this
0x18000bb31  call    ?AddRequestWithRanges@MapsBackgroundTransferJob@@UEAAJPEBGKPEAUMAPSBTSVC_RANGE@@P6AX0JPEAGPEAX3@Z33@Z; MapsBackgroundTransferJob::AddRequestWithRanges(ushort const *,ulong,MAPSBTSVC_RANGE *,void (*)(ushort const *,long,ushort *,void *,void *),void *,void *)
0x18000bb36  test    eax, eax
0x18000bb38  jns     short loc_18000BB45
0x18000bb3a  mov     r8d, 2E9h
0x18000bb40  jmp     loc_18000BA3A
0x18000bb45  xor     eax, eax
0x18000bb47  mov     rcx, [rbp+4Fh+var_20]
0x18000bb4b  xor     rcx, rsp; StackCookie
0x18000bb4e  call    __security_check_cookie
0x18000bb53  add     rsp, 0C0h
0x18000bb5a  pop     rdi
0x18000bb5b  pop     rbx
0x18000bb5c  pop     rbp
0x18000bb5d  retn
```
