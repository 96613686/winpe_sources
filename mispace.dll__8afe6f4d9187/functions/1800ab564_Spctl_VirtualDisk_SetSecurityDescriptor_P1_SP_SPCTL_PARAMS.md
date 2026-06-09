# Spctl_VirtualDisk_SetSecurityDescriptor_P1(_SP_SPCTL_PARAMS *)

- ea: `0x1800ab564`
- end: `0x1800ab927`
- name: `?Spctl_VirtualDisk_SetSecurityDescriptor_P1@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `963`
- prototype: `unsigned int __fastcall(struct _SP_SPCTL_PARAMS *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009304c`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180006cf4`
- `0x18000714d`
- `0x180067a58`
- `0x1800ab564`
- `0x1800ac344`
- `0x1801ba928`
- `0x1801bb374`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ab6ca`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ab6ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab7dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab8b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab8cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab7dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab8b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab8cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ab733`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ab733`

## string_xrefs

- `0x1800ab584`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`
- `0x1800ab767`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`
- `0x1800ab7ec`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`
- `0x1800ab885`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`

## pseudocode

```c
__int64 __fastcall Spctl_VirtualDisk_SetSecurityDescriptor_P1(
        struct _SP_SPCTL_PARAMS *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  bool v5; // cf
  __int64 v7; // rbx
  __int64 v8; // r12
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // edi
  __int16 *v15; // rdx
  _DWORD *v16; // rbx
  __int64 v17; // rcx
  ULONG v18; // ecx
  size_t v19; // r15
  unsigned int v20; // edi
  _DWORD *v21; // rax
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  _DWORD *v25; // r14
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // r8
  __int64 v31; // r9
  PSECURITY_DESCRIPTOR v32; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  const char *v34; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v35[40]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v36; // [rsp+78h] [rbp-88h]
  ULONG SecurityDescriptorSize; // [rsp+BE0h] [rbp+AE0h] BYREF
  int v38; // [rsp+BE8h] [rbp+AE8h]
  const char *v39; // [rsp+BF0h] [rbp+AF0h] BYREF
  void *Src; // [rsp+BF8h] [rbp+AF8h] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v38 = 5558;
    v39 = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)word_18031D8F2,
      a3,
      a4,
      &v39);
  }
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset_0(v35, 0, 0xB48u);
  v5 = *((_DWORD *)a1 + 142) < 0x2Cu;
  Src = 0;
  if ( v5 )
    return 87;
  if ( *((_DWORD *)a1 + 146) < 0x220u )
  {
    **((_DWORD **)a1 + 74) = 544;
    return 87;
  }
  v7 = *((_QWORD *)a1 + 70);
  v8 = *((_QWORD *)a1 + 72);
  v36 = *(_OWORD *)(v7 + 4);
  if ( SuGetSpace((struct _SU_POOL_OBJECT *)v35, (struct _GUID *)(v7 + 20), (struct _SU_SPACE_OBJECT **)&Src) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           (LPCWSTR)(v7 + 40),
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      v16 = Src;
      v18 = SecurityDescriptorSize;
      if ( SecurityDescriptorSize > *((_DWORD *)Src + 690) )
      {
        v19 = (unsigned int)(*((_DWORD *)Src + 19) + 72);
        v20 = SecurityDescriptorSize + 4 * ((v19 + 3) >> 2);
        v21 = LocalAlloc(0, v20);
        v25 = v21;
        if ( !v21 )
        {
          v14 = 40002;
          if ( (unsigned int)dword_180397B68 > 2 )
          {
            v38 = 40002;
            LODWORD(v39) = 5602;
            Src = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v22,
              (__int64)byte_180322B79,
              v23,
              v24,
              &Src);
          }
          goto LABEL_25;
        }
        memcpy_0(v21, v16, v19);
        v25[19] = v20 - 72;
        v25[690] = SecurityDescriptorSize;
        v25[691] = v20 - SecurityDescriptorSize - 72;
        LocalFree(v16);
        v18 = SecurityDescriptorSize;
        v16 = v25;
      }
      v14 = 0;
      if ( SecurityDescriptor )
      {
        memcpy_0((char *)v16 + (unsigned int)v16[691] + 72, SecurityDescriptor, v18);
        v16[690] = SecurityDescriptorSize;
      }
      if ( !(unsigned int)SuSetSpace((struct _SU_SPACE_OBJECT *)v16) )
      {
        v14 = GleToSmpReturnCode(v26);
        if ( (unsigned int)dword_180397B68 > 2 )
        {
          v38 = v14;
          LODWORD(v39) = 5627;
          Src = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v27,
            (__int64)qword_18031B058,
            v28,
            v29,
            &Src);
        }
      }
      goto LABEL_25;
    }
    v14 = GleToSmpReturnCode(v17);
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v38 = v14;
      v15 = &word_180321706;
      LODWORD(v39) = 5587;
      goto LABEL_10;
    }
  }
  else
  {
    v10 = GleToSmpReturnCode(v9);
    v13 = (unsigned int)dword_180397B68;
    v14 = v10;
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      v38 = v10;
      v15 = word_18031EE32;
      LODWORD(v39) = 5576;
LABEL_10:
      v34 = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)v15,
        v11,
        v12,
        &v34);
    }
  }
  v16 = Src;
LABEL_25:
  _FillMethodResponse(v8, *((_DWORD *)a1 + 146), v14, 0, *((unsigned int **)a1 + 74));
  v32 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v16 )
    LocalFree(v16);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v38 = 5641;
    v39 = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)v32,
      (__int64)byte_18031935B,
      v30,
      v31,
      &v39);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ab564  push    rbp
0x1800ab566  push    rbx
0x1800ab567  push    rsi
0x1800ab568  push    rdi
0x1800ab569  push    r12
0x1800ab56b  push    r14
0x1800ab56d  push    r15
0x1800ab56f  lea     rbp, [rsp-0AA0h]
0x1800ab577  sub     rsp, 0BA0h
0x1800ab57e  mov     eax, cs:dword_180397B68
0x1800ab584  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ab58b  mov     rsi, rcx
0x1800ab58e  cmp     eax, 5
0x1800ab591  jbe     short loc_1800AB5C8
0x1800ab593  lea     rax, [rbp+0AD0h+arg_8]
0x1800ab59a  mov     [rbp+0AD0h+arg_8], 15B6h
0x1800ab5a4  mov     [rsp+0BD0h+var_BA8], rax
0x1800ab5a9  lea     rdx, word_18031D8F2
0x1800ab5b0  lea     rax, [rbp+0AD0h+arg_10]
0x1800ab5b7  mov     [rbp+0AD0h+arg_10], r14
0x1800ab5be  mov     [rsp+0BD0h+var_BB0], rax
0x1800ab5c3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ab5c8  xor     edx, edx; Val
0x1800ab5ca  mov     [rsp+0BD0h+SecurityDescriptor], 0
0x1800ab5d3  mov     r8d, 0B48h; Size
0x1800ab5d9  mov     [rbp+0AD0h+SecurityDescriptorSize], 0
0x1800ab5e3  lea     rcx, [rsp+0BD0h+var_B80]; void *
0x1800ab5e8  call    memset_0
0x1800ab5ed  cmp     dword ptr [rsi+238h], 2Ch ; ','
0x1800ab5f4  mov     [rbp+0AD0h+Src], 0
0x1800ab5ff  jnb     short loc_1800AB60B
0x1800ab601  mov     eax, 57h ; 'W'
0x1800ab606  jmp     loc_1800AB915
0x1800ab60b  mov     ecx, 220h
0x1800ab610  cmp     [rsi+248h], ecx
0x1800ab616  jnb     short loc_1800AB623
0x1800ab618  mov     rax, [rsi+250h]
0x1800ab61f  mov     [rax], ecx
0x1800ab621  jmp     short loc_1800AB601
0x1800ab623  mov     rbx, [rsi+230h]
0x1800ab62a  lea     r8, [rbp+0AD0h+Src]; struct _SU_SPACE_OBJECT **
0x1800ab631  mov     r12, [rsi+240h]
0x1800ab638  lea     rcx, [rsp+0BD0h+var_B80]; struct _SU_POOL_OBJECT *
0x1800ab63d  movups  xmm0, xmmword ptr [rbx+4]
0x1800ab641  lea     rdx, [rbx+14h]; struct _GUID *
0x1800ab645  movdqu  [rsp+0BD0h+var_B58], xmm0
0x1800ab64b  call    ?SuGetSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@PEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpace(_SU_POOL_OBJECT *,_GUID *,_SU_SPACE_OBJECT * *)
0x1800ab650  test    eax, eax
0x1800ab652  jnz     short loc_1800AB6B5
0x1800ab654  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800ab659  mov     ecx, cs:dword_180397B68
0x1800ab65f  mov     edi, eax
0x1800ab661  cmp     ecx, 2
0x1800ab664  jbe     short loc_1800AB6A9
0x1800ab666  mov     [rbp+0AD0h+arg_8], eax
0x1800ab66c  lea     rdx, word_18031EE32
0x1800ab673  mov     dword ptr [rbp+0AD0h+arg_10], 15C8h
0x1800ab67d  lea     rax, [rbp+0AD0h+arg_8]
0x1800ab684  mov     [rsp+0BD0h+var_B88], r14
0x1800ab689  mov     [rsp+0BD0h+var_BA0], rax
0x1800ab68e  lea     rax, [rbp+0AD0h+arg_10]
0x1800ab695  mov     [rsp+0BD0h+var_BA8], rax
0x1800ab69a  lea     rax, [rsp+0BD0h+var_B88]
0x1800ab69f  mov     [rsp+0BD0h+var_BB0], rax
0x1800ab6a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ab6a9  mov     rbx, [rbp+0AD0h+Src]
0x1800ab6b0  jmp     loc_1800AB885
0x1800ab6b5  lea     rcx, [rbx+28h]; StringSecurityDescriptor
0x1800ab6b9  mov     edx, 1; StringSDRevision
0x1800ab6be  lea     r9, [rbp+0AD0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800ab6c5  lea     r8, [rsp+0BD0h+SecurityDescriptor]; SecurityDescriptor
0x1800ab6ca  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ab6d0  test    eax, eax
0x1800ab6d2  jnz     short loc_1800AB702
0x1800ab6d4  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800ab6d9  mov     edi, eax
0x1800ab6db  mov     eax, cs:dword_180397B68
0x1800ab6e1  cmp     eax, 2
0x1800ab6e4  jbe     short loc_1800AB6A9
0x1800ab6e6  mov     [rbp+0AD0h+arg_8], edi
0x1800ab6ec  lea     rdx, word_180321706
0x1800ab6f3  mov     dword ptr [rbp+0AD0h+arg_10], 15D3h
0x1800ab6fd  jmp     loc_1800AB67D
0x1800ab702  mov     rbx, [rbp+0AD0h+Src]
0x1800ab709  mov     ecx, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ab70f  cmp     ecx, [rbx+0AC8h]
0x1800ab715  jbe     loc_1800AB7F3
0x1800ab71b  mov     eax, [rbx+4Ch]
0x1800ab71e  add     eax, 48h ; 'H'
0x1800ab721  mov     r15d, eax
0x1800ab724  add     rax, 3
0x1800ab728  shr     rax, 2
0x1800ab72c  lea     edi, [rcx+rax*4]
0x1800ab72f  xor     ecx, ecx; uFlags
0x1800ab731  mov     edx, edi; uBytes
0x1800ab733  call    cs:__imp_LocalAlloc
0x1800ab739  mov     r14, rax
0x1800ab73c  test    rax, rax
0x1800ab73f  jnz     short loc_1800AB7A8
0x1800ab741  mov     eax, cs:dword_180397B68
0x1800ab747  mov     edi, 9C42h
0x1800ab74c  cmp     eax, 2
0x1800ab74f  jbe     loc_1800AB885
0x1800ab755  lea     rax, [rbp+0AD0h+arg_8]
0x1800ab75c  mov     [rbp+0AD0h+arg_8], edi
0x1800ab762  mov     [rsp+0BD0h+var_BA0], rax
0x1800ab767  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ab76e  lea     rax, [rbp+0AD0h+arg_10]
0x1800ab775  mov     dword ptr [rbp+0AD0h+arg_10], 15E2h
0x1800ab77f  mov     [rsp+0BD0h+var_BA8], rax
0x1800ab784  lea     rdx, byte_180322B79
0x1800ab78b  lea     rax, [rbp+0AD0h+Src]
0x1800ab792  mov     [rbp+0AD0h+Src], r14
0x1800ab799  mov     [rsp+0BD0h+var_BB0], rax
0x1800ab79e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ab7a3  jmp     loc_1800AB88C
0x1800ab7a8  mov     r8, r15; Size
0x1800ab7ab  mov     rdx, rbx; Src
0x1800ab7ae  mov     rcx, r14; void *
0x1800ab7b1  call    memcpy_0
0x1800ab7b6  lea     eax, [rdi-48h]
0x1800ab7b9  mov     rcx, rbx; hMem
0x1800ab7bc  mov     [r14+4Ch], eax
0x1800ab7c0  mov     eax, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ab7c6  mov     [r14+0AC8h], eax
0x1800ab7cd  sub     edi, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ab7d3  sub     edi, 48h ; 'H'
0x1800ab7d6  mov     [r14+0ACCh], edi
0x1800ab7dd  call    cs:__imp_LocalFree
0x1800ab7e3  mov     ecx, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ab7e9  mov     rbx, r14
0x1800ab7ec  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ab7f3  mov     rdx, [rsp+0BD0h+SecurityDescriptor]; Src
0x1800ab7f8  xor     edi, edi
0x1800ab7fa  test    rdx, rdx
0x1800ab7fd  jz      short loc_1800AB820
0x1800ab7ff  mov     r8d, ecx; Size
0x1800ab802  mov     ecx, [rbx+0ACCh]
0x1800ab808  add     rcx, 48h ; 'H'
0x1800ab80c  add     rcx, rbx; void *
0x1800ab80f  call    memcpy_0
0x1800ab814  mov     eax, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ab81a  mov     [rbx+0AC8h], eax
0x1800ab820  mov     rcx, rbx; struct _SU_SPACE_OBJECT *
0x1800ab823  call    ?SuSetSpace@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuSetSpace(_SU_SPACE_OBJECT *)
0x1800ab828  test    eax, eax
0x1800ab82a  jnz     short loc_1800AB885
0x1800ab82c  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800ab831  mov     edi, eax
0x1800ab833  mov     eax, cs:dword_180397B68
0x1800ab839  cmp     eax, 2
0x1800ab83c  jbe     short loc_1800AB885
0x1800ab83e  lea     rax, [rbp+0AD0h+arg_8]
0x1800ab845  mov     [rbp+0AD0h+arg_8], edi
0x1800ab84b  mov     [rsp+0BD0h+var_BA0], rax
0x1800ab850  lea     rdx, qword_18031B058
0x1800ab857  lea     rax, [rbp+0AD0h+arg_10]
0x1800ab85e  mov     dword ptr [rbp+0AD0h+arg_10], 15FBh
0x1800ab868  mov     [rsp+0BD0h+var_BA8], rax
0x1800ab86d  lea     rax, [rbp+0AD0h+Src]
0x1800ab874  mov     [rsp+0BD0h+var_BB0], rax
0x1800ab879  mov     [rbp+0AD0h+Src], r14
0x1800ab880  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ab885  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ab88c  mov     rax, [rsi+250h]
0x1800ab893  xor     r9d, r9d
0x1800ab896  mov     edx, [rsi+248h]
0x1800ab89c  mov     r8d, edi
0x1800ab89f  mov     rcx, r12
0x1800ab8a2  mov     [rsp+0BD0h+var_BB0], rax
0x1800ab8a7  call    ?_FillMethodResponse@@YAXPEAEKW4SM_RETURN_CODE@@PEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAK@Z; _FillMethodResponse(uchar *,ulong,SM_RETURN_CODE,_SUEX_EXTENDEDSTATUS_OBJECT *,ulong *)
0x1800ab8ac  mov     rcx, [rsp+0BD0h+SecurityDescriptor]; hMem
0x1800ab8b1  test    rcx, rcx
0x1800ab8b4  jz      short loc_1800AB8C5
0x1800ab8b6  call    cs:__imp_LocalFree
0x1800ab8bc  mov     [rsp+0BD0h+SecurityDescriptor], 0
0x1800ab8c5  test    rbx, rbx
0x1800ab8c8  jz      short loc_1800AB8D3
0x1800ab8ca  mov     rcx, rbx; hMem
0x1800ab8cd  call    cs:__imp_LocalFree
0x1800ab8d3  mov     eax, cs:dword_180397B68
0x1800ab8d9  cmp     eax, 5
0x1800ab8dc  jbe     short loc_1800AB913
0x1800ab8de  lea     rax, [rbp+0AD0h+arg_8]
0x1800ab8e5  mov     [rbp+0AD0h+arg_8], 1609h
0x1800ab8ef  mov     [rsp+0BD0h+var_BA8], rax
0x1800ab8f4  lea     rdx, byte_18031935B
0x1800ab8fb  lea     rax, [rbp+0AD0h+arg_10]
0x1800ab902  mov     [rbp+0AD0h+arg_10], r14
0x1800ab909  mov     [rsp+0BD0h+var_BB0], rax
0x1800ab90e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ab913  xor     eax, eax
0x1800ab915  add     rsp, 0BA0h
0x1800ab91c  pop     r15
0x1800ab91e  pop     r14
0x1800ab920  pop     r12
0x1800ab922  pop     rdi
0x1800ab923  pop     rsi
0x1800ab924  pop     rbx
0x1800ab925  pop     rbp
0x1800ab926  retn
```
