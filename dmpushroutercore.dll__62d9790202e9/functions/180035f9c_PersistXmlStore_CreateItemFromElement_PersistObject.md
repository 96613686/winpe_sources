# PersistXmlStore::CreateItemFromElement(PersistObject *)

- ea: `0x180035f9c`
- end: `0x180036330`
- name: `?CreateItemFromElement@PersistXmlStore@@AEAAJPEAVPersistObject@@@Z`
- size: `916`
- prototype: `__int64 __fastcall(PersistXmlStore *__hidden this, struct PersistObject *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800371c8`

## callees

- `0x18000c5c8`
- `0x180017258`
- `0x180017384`
- `0x18001abd4`
- `0x180035f9c`
- `0x180036a74`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036118`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036118`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800360f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800360f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036310`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800362b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036310`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003607e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003607e`
- `DMCmnUtils!CopyString` at `0x18003610d`
- `DMCmnUtils!CopyString` at `0x18003610d`
- `DMCmnUtils!InvStrCmpW` at `0x18003601f`
- `DMCmnUtils!InvStrCmpW` at `0x180036172`
- `DMCmnUtils!InvStrCmpW` at `0x1800362f8`
- `DMCmnUtils!InvStrCmpW` at `0x18003601f`
- `DMCmnUtils!InvStrCmpW` at `0x180036172`
- `DMCmnUtils!InvStrCmpW` at `0x1800362f8`
- `DMCmnUtils!SafeStringToDword` at `0x18003624c`
- `DMCmnUtils!SafeStringToDword` at `0x18003624c`
- `DMCmnUtils!DecodeBase64W` at `0x180036275`
- `DMCmnUtils!DecodeBase64W` at `0x180036275`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistXmlStore::CreateItemFromElement(PersistXmlStore *this, struct PersistObject *a2)
{
  int AttributeAsDword; // edi
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r15
  int v7; // ebx
  int v8; // eax
  __int64 *v9; // rcx
  __int64 v10; // r9
  unsigned int v11; // ecx
  unsigned __int64 v12; // rax
  unsigned __int16 *v13; // rax
  int v14; // eax
  unsigned int v16; // [rsp+20h] [rbp-40h] BYREF
  int v17; // [rsp+24h] [rbp-3Ch] BYREF
  int v18; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v19; // [rsp+2Ch] [rbp-34h] BYREF
  const unsigned __int16 *v20; // [rsp+30h] [rbp-30h] BYREF
  const unsigned __int16 *v21; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-20h] BYREF
  char v23; // [rsp+48h] [rbp-18h]
  const unsigned __int16 *v24; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int16 *v25; // [rsp+58h] [rbp-8h] BYREF
  unsigned __int64 v26; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v27; // [rsp+B0h] [rbp+50h] BYREF
  int v28; // [rsp+B8h] [rbp+58h] BYREF

  v28 = 0;
  v20 = 0;
  AttributeAsDword = 0;
  v24 = 0;
  v25 = 0;
  v5 = 0;
  LODWORD(v26) = 0;
  v6 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 64LL))(*((_QWORD *)this + 10));
  if ( v7 < 0 )
    goto LABEL_17;
  while ( 1 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, _QWORD))(**((_QWORD **)this + 10) + 112LL))(
           *((_QWORD *)this + 10),
           &v24,
           0);
    if ( v7 < 0 )
      goto LABEL_17;
    v8 = InvStrCmpW(v24, L"id");
    v9 = (__int64 *)*((_QWORD *)this + 10);
    v10 = *v9;
    if ( !v8 )
      break;
    AttributeAsDword = (*(__int64 (**)(void))(v10 + 72))();
    if ( AttributeAsDword )
      goto LABEL_13;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **, unsigned __int64 *))(v10 + 128))(v9, &v25, &v26);
  if ( v7 < 0 )
    goto LABEL_17;
  v11 = v26 + 1;
  if ( (int)v26 + 1 < (unsigned int)v26 )
  {
    LODWORD(v26) = -1;
    goto LABEL_16;
  }
  LODWORD(v26) = v26 + 1;
  v12 = 2LL * v11;
  if ( v12 > 0xFFFFFFFF )
  {
LABEL_16:
    v7 = -2147024362;
    goto LABEL_17;
  }
  v13 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v12);
  v5 = v13;
  if ( !v13 )
    goto LABEL_10;
  v7 = StringCchCopyW(v13, (unsigned int)v26, v25);
  if ( v7 >= 0 )
  {
    v6 = v5;
LABEL_13:
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 88LL))(*((_QWORD *)this + 10));
    v5 = 0;
    if ( !v6 )
LABEL_10:
      v7 = -2147024882;
  }
LABEL_17:
  LocalFree(v5);
  if ( AttributeAsDword >= 0 )
    AttributeAsDword = v7;
  if ( AttributeAsDword >= 0 )
  {
    hMem = (char *)a2 + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    v23 = 1;
    AttributeAsDword = CopyString(v6, 0xFFFFFFFF, (unsigned __int16 **)a2 + 3);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
    if ( AttributeAsDword >= 0 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( (*(unsigned int (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 10) + 48LL))(
                 *((_QWORD *)this + 10),
                 &v28) )
          {
            goto LABEL_47;
          }
          if ( v28 == 1 )
            break;
          if ( v28 == 15 )
          {
            AttributeAsDword = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, _QWORD))(**((_QWORD **)this + 10) + 112LL))(
                                 *((_QWORD *)this + 10),
                                 &v20,
                                 0);
            if ( AttributeAsDword < 0 || !InvStrCmpW(L"item", v20) )
              goto LABEL_47;
          }
        }
        if ( (*(int (__fastcall **)(_QWORD, const unsigned __int16 **, _QWORD))(**((_QWORD **)this + 10) + 112LL))(
               *((_QWORD *)this + 10),
               &v20,
               0) >= 0
          && InvStrCmpW(L"prop", v20) )
        {
          AttributeAsDword = -2147024883;
          break;
        }
        v21 = 0;
        hMem = 0;
        v19 = 0;
        v18 = 0;
        v16 = 0;
        v27 = -1;
        v17 = 0;
        AttributeAsDword = PersistXmlStore::GetAttributeAsDword(this, L"id", &v27);
        if ( AttributeAsDword >= 0 )
        {
          AttributeAsDword = PersistXmlStore::GetAttributeAsDword(this, L"regtype", &v16);
          if ( AttributeAsDword >= 0 )
          {
            AttributeAsDword = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 10) + 48LL))(
                                 *((_QWORD *)this + 10),
                                 &v17);
            if ( AttributeAsDword >= 0 && v17 == 3 )
            {
              AttributeAsDword = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **, int *))(**((_QWORD **)this + 10) + 128LL))(
                                   *((_QWORD *)this + 10),
                                   &v21,
                                   &v18);
              if ( AttributeAsDword >= 0 )
              {
                if ( v18 )
                {
                  switch ( v16 )
                  {
                    case 1u:
                      v14 = PersistObject::Set(a2, v27, v21);
                      goto LABEL_39;
                    case 3u:
                      AttributeAsDword = DecodeBase64W(v21, (unsigned __int8 **)&hMem, (int *)&v19);
                      if ( AttributeAsDword < 0 )
                        break;
                      v14 = PersistObject::Set(a2, v27, hMem, v19);
                      goto LABEL_39;
                    case 4u:
                      v16 = 0;
                      AttributeAsDword = SafeStringToDword(v21, 10, 1, &v16);
                      if ( AttributeAsDword >= 0 )
                      {
                        v14 = PersistObject::Set(a2, v27, v16);
LABEL_39:
                        AttributeAsDword = v14;
                      }
                      break;
                  }
                }
              }
            }
          }
        }
        LocalFree(hMem);
        LocalFree(0);
        if ( AttributeAsDword < 0 )
          break;
        v20 = 0;
      }
    }
  }
LABEL_47:
  LocalFree(v6);
  return (unsigned int)AttributeAsDword;
}

```

## disassembly

```asm
0x180035f9c  mov     [rsp-38h+arg_8], rbx
0x180035fa1  push    rbp
0x180035fa2  push    rsi
0x180035fa3  push    rdi
0x180035fa4  push    r12
0x180035fa6  push    r13
0x180035fa8  push    r14
0x180035faa  push    r15
0x180035fac  mov     rbp, rsp
0x180035faf  sub     rsp, 60h
0x180035fb3  mov     r13, rdx
0x180035fb6  mov     r14, rcx
0x180035fb9  xor     r12d, r12d
0x180035fbc  mov     [rbp+arg_18], r12d
0x180035fc0  mov     [rbp+var_30], r12
0x180035fc4  mov     edi, r12d
0x180035fc7  mov     [rbp+var_10], r12
0x180035fcb  mov     [rbp+var_8], r12
0x180035fcf  mov     esi, r12d
0x180035fd2  mov     dword ptr [rbp+arg_0], r12d
0x180035fd6  mov     r15d, r12d
0x180035fd9  mov     rcx, [rcx+50h]
0x180035fdd  mov     rax, [rcx]
0x180035fe0  mov     rax, [rax+40h]
0x180035fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fe9  mov     ebx, eax
0x180035feb  test    eax, eax
0x180035fed  js      loc_1800360D4
0x180035ff3  mov     rcx, [r14+50h]
0x180035ff7  mov     rax, [rcx]
0x180035ffa  xor     r8d, r8d
0x180035ffd  lea     rdx, [rbp+var_10]
0x180036001  mov     rax, [rax+70h]
0x180036005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003600a  mov     ebx, eax
0x18003600c  test    eax, eax
0x18003600e  js      loc_1800360D4
0x180036014  lea     rdx, aId; "id"
0x18003601b  mov     rcx, [rbp+var_10]
0x18003601f  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180036025  mov     rcx, [r14+50h]
0x180036029  mov     r9, [rcx]
0x18003602c  test    eax, eax
0x18003602e  jz      short loc_180036041
0x180036030  mov     rax, [r9+48h]
0x180036034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036039  mov     edi, eax
0x18003603b  test    eax, eax
0x18003603d  jz      short loc_180035FF3
0x18003603f  jmp     short loc_1800360AB
0x180036041  lea     r8, [rbp+arg_0]
0x180036045  lea     rdx, [rbp+var_8]
0x180036049  mov     rax, [r9+80h]
0x180036050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036055  mov     ebx, eax
0x180036057  test    eax, eax
0x180036059  js      short loc_1800360D4
0x18003605b  mov     eax, dword ptr [rbp+arg_0]
0x18003605e  lea     ecx, [rax+1]
0x180036061  cmp     ecx, eax
0x180036063  jb      short loc_1800360C7
0x180036065  mov     dword ptr [rbp+arg_0], ecx
0x180036068  mov     eax, ecx
0x18003606a  add     rax, rax
0x18003606d  mov     ecx, 0FFFFFFFFh
0x180036072  cmp     rax, rcx
0x180036075  ja      short loc_1800360CF
0x180036077  mov     edx, eax; uBytes
0x180036079  mov     ecx, 40h ; '@'; uFlags
0x18003607e  call    cs:__imp_LocalAlloc
0x180036084  mov     rsi, rax
0x180036087  test    rax, rax
0x18003608a  jnz     short loc_180036093
0x18003608c  mov     ebx, 8007000Eh
0x180036091  jmp     short loc_1800360D4
0x180036093  mov     edx, dword ptr [rbp+arg_0]; unsigned __int64
0x180036096  mov     r8, [rbp+var_8]; unsigned __int16 *
0x18003609a  mov     rcx, rsi; unsigned __int16 *
0x18003609d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800360a2  mov     ebx, eax
0x1800360a4  test    eax, eax
0x1800360a6  js      short loc_1800360D4
0x1800360a8  mov     r15, rsi
0x1800360ab  mov     rcx, [r14+50h]
0x1800360af  mov     rax, [rcx]
0x1800360b2  mov     rax, [rax+58h]
0x1800360b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360bb  mov     ebx, eax
0x1800360bd  mov     rsi, r12
0x1800360c0  test    r15, r15
0x1800360c3  jnz     short loc_1800360D4
0x1800360c5  jmp     short loc_18003608C
0x1800360c7  mov     ecx, 0FFFFFFFFh
0x1800360cc  mov     dword ptr [rbp+arg_0], ecx
0x1800360cf  mov     ebx, 80070216h
0x1800360d4  mov     rcx, rsi; hMem
0x1800360d7  call    cs:__imp_LocalFree
0x1800360dd  test    edi, edi
0x1800360df  cmovns  edi, ebx
0x1800360e2  test    edi, edi
0x1800360e4  js      loc_18003630D
0x1800360ea  lea     rbx, [r13+20h]
0x1800360ee  mov     [rbp+hMem], rbx
0x1800360f2  mov     rcx, rbx; lpCriticalSection
0x1800360f5  call    cs:__imp_EnterCriticalSection
0x1800360fb  mov     [rbp+var_18], 1
0x1800360ff  lea     r8, [r13+18h]
0x180036103  mov     esi, 0FFFFFFFFh
0x180036108  mov     edx, esi
0x18003610a  mov     rcx, r15
0x18003610d  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180036113  mov     edi, eax
0x180036115  mov     rcx, rbx; lpCriticalSection
0x180036118  call    cs:__imp_LeaveCriticalSection
0x18003611e  test    edi, edi
0x180036120  js      loc_18003630D
0x180036126  mov     rcx, [r14+50h]
0x18003612a  mov     rax, [rcx]
0x18003612d  lea     rdx, [rbp+arg_18]
0x180036131  mov     rax, [rax+30h]
0x180036135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003613a  test    eax, eax
0x18003613c  jnz     loc_18003630D
0x180036142  cmp     [rbp+arg_18], 1
0x180036146  jnz     loc_1800362C6
0x18003614c  mov     rcx, [r14+50h]
0x180036150  mov     rax, [rcx]
0x180036153  xor     r8d, r8d
0x180036156  lea     rdx, [rbp+var_30]
0x18003615a  mov     rax, [rax+70h]
0x18003615e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036163  test    eax, eax
0x180036165  js      short loc_180036180
0x180036167  mov     rdx, [rbp+var_30]
0x18003616b  lea     rcx, aProp; "prop"
0x180036172  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180036178  test    eax, eax
0x18003617a  jnz     loc_180036308
0x180036180  mov     [rbp+var_28], r12
0x180036184  mov     [rbp+hMem], r12
0x180036188  mov     [rbp+var_34], r12d
0x18003618c  mov     [rbp+var_38], r12d
0x180036190  mov     [rbp+var_40], r12d
0x180036194  mov     [rbp+arg_10], esi
0x180036197  mov     [rbp+var_3C], r12d
0x18003619b  lea     r8, [rbp+arg_10]; unsigned int *
0x18003619f  lea     rdx, aId; "id"
0x1800361a6  mov     rcx, r14; this
0x1800361a9  call    ?GetAttributeAsDword@PersistXmlStore@@AEAAJPEBGPEAK@Z; PersistXmlStore::GetAttributeAsDword(ushort const *,ulong *)
0x1800361ae  mov     edi, eax
0x1800361b0  test    eax, eax
0x1800361b2  js      loc_1800362A7
0x1800361b8  lea     r8, [rbp+var_40]; unsigned int *
0x1800361bc  lea     rdx, aRegtype; "regtype"
0x1800361c3  mov     rcx, r14; this
0x1800361c6  call    ?GetAttributeAsDword@PersistXmlStore@@AEAAJPEBGPEAK@Z; PersistXmlStore::GetAttributeAsDword(ushort const *,ulong *)
0x1800361cb  mov     edi, eax
0x1800361cd  test    eax, eax
0x1800361cf  js      loc_1800362A7
0x1800361d5  mov     rcx, [r14+50h]
0x1800361d9  mov     rax, [rcx]
0x1800361dc  lea     rdx, [rbp+var_3C]
0x1800361e0  mov     rax, [rax+30h]
0x1800361e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361e9  mov     edi, eax
0x1800361eb  test    eax, eax
0x1800361ed  js      loc_1800362A7
0x1800361f3  cmp     [rbp+var_3C], 3
0x1800361f7  jnz     loc_1800362A7
0x1800361fd  mov     rcx, [r14+50h]
0x180036201  mov     rax, [rcx]
0x180036204  lea     r8, [rbp+var_38]
0x180036208  lea     rdx, [rbp+var_28]
0x18003620c  mov     rax, [rax+80h]
0x180036213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036218  mov     edi, eax
0x18003621a  test    eax, eax
0x18003621c  js      loc_1800362A7
0x180036222  cmp     [rbp+var_38], r12d
0x180036226  jz      short loc_1800362A7
0x180036228  mov     eax, [rbp+var_40]
0x18003622b  sub     eax, 1
0x18003622e  jz      short loc_180036296
0x180036230  sub     eax, 2
0x180036233  jz      short loc_180036269
0x180036235  cmp     eax, 1
0x180036238  jnz     short loc_1800362A7
0x18003623a  mov     [rbp+var_40], r12d
0x18003623e  lea     r9, [rbp+var_40]
0x180036242  lea     edx, [rax+9]
0x180036245  mov     r8d, eax
0x180036248  mov     rcx, [rbp+var_28]
0x18003624c  call    cs:__imp_?SafeStringToDword@@YAJPEBGHHPEAK@Z; SafeStringToDword(ushort const *,int,int,ulong *)
0x180036252  mov     edi, eax
0x180036254  test    eax, eax
0x180036256  js      short loc_1800362A7
0x180036258  mov     r8d, [rbp+var_40]
0x18003625c  mov     edx, [rbp+arg_10]
0x18003625f  mov     rcx, r13
0x180036262  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@K@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ulong)
0x180036267  jmp     short loc_1800362A5
0x180036269  lea     r8, [rbp+var_34]
0x18003626d  lea     rdx, [rbp+hMem]
0x180036271  mov     rcx, [rbp+var_28]
0x180036275  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x18003627b  mov     edi, eax
0x18003627d  test    eax, eax
0x18003627f  js      short loc_1800362A7
0x180036281  mov     r9d, [rbp+var_34]
0x180036285  mov     r8, [rbp+hMem]
0x180036289  mov     edx, [rbp+arg_10]
0x18003628c  mov     rcx, r13
0x18003628f  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@QEAEK@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,uchar * const,ulong)
0x180036294  jmp     short loc_1800362A5
0x180036296  mov     r8, [rbp+var_28]
0x18003629a  mov     edx, [rbp+arg_10]
0x18003629d  mov     rcx, r13
0x1800362a0  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)
0x1800362a5  mov     edi, eax
0x1800362a7  mov     rcx, [rbp+hMem]; hMem
0x1800362ab  call    cs:__imp_LocalFree
0x1800362b1  xor     ecx, ecx; hMem
0x1800362b3  call    cs:__imp_LocalFree
0x1800362b9  test    edi, edi
0x1800362bb  js      short loc_18003630D
0x1800362bd  mov     [rbp+var_30], r12
0x1800362c1  jmp     loc_180036126
0x1800362c6  cmp     [rbp+arg_18], 0Fh
0x1800362ca  jnz     loc_180036126
0x1800362d0  mov     rcx, [r14+50h]
0x1800362d4  mov     rax, [rcx]
0x1800362d7  xor     r8d, r8d
0x1800362da  lea     rdx, [rbp+var_30]
0x1800362de  mov     rax, [rax+70h]
0x1800362e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800362e7  mov     edi, eax
0x1800362e9  test    eax, eax
0x1800362eb  js      short loc_18003630D
0x1800362ed  mov     rdx, [rbp+var_30]
0x1800362f1  lea     rcx, aItem; "item"
0x1800362f8  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x1800362fe  test    eax, eax
0x180036300  jnz     loc_180036126
0x180036306  jmp     short loc_18003630D
0x180036308  mov     edi, 8007000Dh
0x18003630d  mov     rcx, r15; hMem
0x180036310  call    cs:__imp_LocalFree
0x180036316  mov     eax, edi
0x180036318  mov     rbx, [rsp+60h+arg_8]
0x180036320  add     rsp, 60h
0x180036324  pop     r15
0x180036326  pop     r14
0x180036328  pop     r13
0x18003632a  pop     r12
0x18003632c  pop     rdi
0x18003632d  pop     rsi
0x18003632e  pop     rbp
0x18003632f  retn
```
