# Spctl_VirtualDisk_SetSecurityDescriptor_P1(_SP_SPCTL_PARAMS *)

- ea: `0x1800ae0f4`
- end: `0x1800ae4d6`
- name: `?Spctl_VirtualDisk_SetSecurityDescriptor_P1@@YAKPEAU_SP_SPCTL_PARAMS@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(struct _SP_SPCTL_PARAMS *, __int64, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800958b8`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180006dd4`
- `0x18000722d`
- `0x180069b88`
- `0x1800ae0f4`
- `0x1800aef0c`
- `0x1801c11c0`
- `0x1801c1cd8`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ae25a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800ae25a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae475`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ae475`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ae2c9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ae2c9`

## string_xrefs

- `0x1800ae114`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`
- `0x1800ae303`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`
- `0x1800ae38e`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`
- `0x1800ae427`: `Spctl_VirtualDisk_SetSecurityDescriptor_P1`

## pseudocode

```c
__int64 __fastcall Spctl_VirtualDisk_SetSecurityDescriptor_P1(struct _SP_SPCTL_PARAMS *a1, __int64 a2, int a3, int a4)
{
  bool v5; // cf
  __int64 v7; // rbx
  __int64 v8; // r12
  unsigned int v9; // eax
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  unsigned int v13; // edi
  __int16 *v14; // rdx
  _DWORD *v15; // rbx
  ULONG v16; // ecx
  size_t v17; // r15
  unsigned int v18; // edi
  _DWORD *v19; // rax
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  _DWORD *v23; // r14
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  const char *v31; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v32[40]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+78h] [rbp-88h]
  ULONG SecurityDescriptorSize; // [rsp+BE0h] [rbp+AE0h] BYREF
  int v35; // [rsp+BE8h] [rbp+AE8h] BYREF
  const char *v36; // [rsp+BF0h] [rbp+AF0h] BYREF
  void *Src; // [rsp+BF8h] [rbp+AF8h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v35 = 5558;
    v36 = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)&word_18032480E,
      a3,
      a4,
      (__int64)&v36,
      (__int64)&v35);
  }
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset_0(v32, 0, 0xB48u);
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
  v33 = *(_OWORD *)(v7 + 4);
  if ( SuGetSpace((struct _SU_POOL_OBJECT *)v32, (struct _GUID *)(v7 + 20), (struct _SU_SPACE_OBJECT **)&Src) )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           (LPCWSTR)(v7 + 40),
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize) )
    {
      v15 = Src;
      v16 = SecurityDescriptorSize;
      if ( SecurityDescriptorSize > *((_DWORD *)Src + 690) )
      {
        v17 = (unsigned int)(*((_DWORD *)Src + 19) + 72);
        v18 = SecurityDescriptorSize + 4 * ((v17 + 3) >> 2);
        v19 = LocalAlloc(0, v18);
        v23 = v19;
        if ( !v19 )
        {
          v13 = 40002;
          if ( (unsigned int)dword_18039EB68 > 2 )
          {
            v35 = 40002;
            LODWORD(v36) = 5602;
            Src = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v20,
              (unsigned int)byte_180329B01,
              v21,
              v22,
              (__int64)&Src,
              (__int64)&v36,
              (__int64)&v35);
          }
          goto LABEL_25;
        }
        memcpy_0(v19, v15, v17);
        v23[19] = v18 - 72;
        v23[690] = SecurityDescriptorSize;
        v23[691] = v18 - SecurityDescriptorSize - 72;
        LocalFree(v15);
        v16 = SecurityDescriptorSize;
        v15 = v23;
      }
      v13 = 0;
      if ( SecurityDescriptor )
      {
        memcpy_0((char *)v15 + (unsigned int)v15[691] + 72, SecurityDescriptor, v16);
        v15[690] = SecurityDescriptorSize;
      }
      if ( !(unsigned int)SuSetSpace((struct _SU_SPACE_OBJECT *)v15) )
      {
        v13 = GleToSmpReturnCode();
        if ( (unsigned int)dword_18039EB68 > 2 )
        {
          v35 = v13;
          LODWORD(v36) = 5627;
          Src = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v24,
            (unsigned int)word_180322072,
            v25,
            v26,
            (__int64)&Src,
            (__int64)&v36,
            (__int64)&v35);
        }
      }
      goto LABEL_25;
    }
    v13 = GleToSmpReturnCode();
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v35 = v13;
      v14 = &word_18032868E;
      LODWORD(v36) = 5587;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = GleToSmpReturnCode();
    v12 = dword_18039EB68;
    v13 = v9;
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v35 = v9;
      v14 = (__int16 *)qword_180325D18;
      LODWORD(v36) = 5576;
LABEL_10:
      v31 = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (_DWORD)v14,
        v10,
        v11,
        (__int64)&v31,
        (__int64)&v36,
        (__int64)&v35);
    }
  }
  v15 = Src;
LABEL_25:
  _FillMethodResponse(v8, *((unsigned int *)a1 + 146), v13, 0, *((_QWORD *)a1 + 74));
  v29 = (int)SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    LocalFree(SecurityDescriptor);
    SecurityDescriptor = 0;
  }
  if ( v15 )
    LocalFree(v15);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v35 = 5641;
    v36 = "Spctl_VirtualDisk_SetSecurityDescriptor_P1";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v29,
      (unsigned int)byte_180320353,
      v27,
      v28,
      (__int64)&v36,
      (__int64)&v35);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ae0f4  push    rbp
0x1800ae0f6  push    rbx
0x1800ae0f7  push    rsi
0x1800ae0f8  push    rdi
0x1800ae0f9  push    r12
0x1800ae0fb  push    r14
0x1800ae0fd  push    r15
0x1800ae0ff  lea     rbp, [rsp-0AA0h]
0x1800ae107  sub     rsp, 0BA0h
0x1800ae10e  mov     eax, cs:dword_18039EB68
0x1800ae114  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ae11b  mov     rsi, rcx
0x1800ae11e  cmp     eax, 5
0x1800ae121  jbe     short loc_1800AE158
0x1800ae123  lea     rax, [rbp+0AD0h+arg_8]
0x1800ae12a  mov     [rbp+0AD0h+arg_8], 15B6h
0x1800ae134  mov     [rsp+0BD0h+var_BA8], rax
0x1800ae139  lea     rdx, word_18032480E
0x1800ae140  lea     rax, [rbp+0AD0h+arg_10]
0x1800ae147  mov     [rbp+0AD0h+arg_10], r14
0x1800ae14e  mov     [rsp+0BD0h+var_BB0], rax
0x1800ae153  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ae158  xor     edx, edx; Val
0x1800ae15a  mov     [rsp+0BD0h+SecurityDescriptor], 0
0x1800ae163  mov     r8d, 0B48h; Size
0x1800ae169  mov     [rbp+0AD0h+SecurityDescriptorSize], 0
0x1800ae173  lea     rcx, [rsp+0BD0h+var_B80]; void *
0x1800ae178  call    memset_0
0x1800ae17d  cmp     dword ptr [rsi+238h], 2Ch ; ','
0x1800ae184  mov     [rbp+0AD0h+Src], 0
0x1800ae18f  jnb     short loc_1800AE19B
0x1800ae191  mov     eax, 57h ; 'W'
0x1800ae196  jmp     loc_1800AE4C3
0x1800ae19b  mov     ecx, 220h
0x1800ae1a0  cmp     [rsi+248h], ecx
0x1800ae1a6  jnb     short loc_1800AE1B3
0x1800ae1a8  mov     rax, [rsi+250h]
0x1800ae1af  mov     [rax], ecx
0x1800ae1b1  jmp     short loc_1800AE191
0x1800ae1b3  mov     rbx, [rsi+230h]
0x1800ae1ba  lea     r8, [rbp+0AD0h+Src]; struct _SU_SPACE_OBJECT **
0x1800ae1c1  mov     r12, [rsi+240h]
0x1800ae1c8  lea     rcx, [rsp+0BD0h+var_B80]; struct _SU_POOL_OBJECT *
0x1800ae1cd  movups  xmm0, xmmword ptr [rbx+4]
0x1800ae1d1  lea     rdx, [rbx+14h]; struct _GUID *
0x1800ae1d5  movdqu  [rsp+0BD0h+var_B58], xmm0
0x1800ae1db  call    ?SuGetSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@PEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpace(_SU_POOL_OBJECT *,_GUID *,_SU_SPACE_OBJECT * *)
0x1800ae1e0  test    eax, eax
0x1800ae1e2  jnz     short loc_1800AE245
0x1800ae1e4  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800ae1e9  mov     ecx, cs:dword_18039EB68
0x1800ae1ef  mov     edi, eax
0x1800ae1f1  cmp     ecx, 2
0x1800ae1f4  jbe     short loc_1800AE239
0x1800ae1f6  mov     [rbp+0AD0h+arg_8], eax
0x1800ae1fc  lea     rdx, qword_180325D18
0x1800ae203  mov     dword ptr [rbp+0AD0h+arg_10], 15C8h
0x1800ae20d  lea     rax, [rbp+0AD0h+arg_8]
0x1800ae214  mov     [rsp+0BD0h+var_B88], r14
0x1800ae219  mov     [rsp+0BD0h+var_BA0], rax
0x1800ae21e  lea     rax, [rbp+0AD0h+arg_10]
0x1800ae225  mov     [rsp+0BD0h+var_BA8], rax
0x1800ae22a  lea     rax, [rsp+0BD0h+var_B88]
0x1800ae22f  mov     [rsp+0BD0h+var_BB0], rax
0x1800ae234  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae239  mov     rbx, [rbp+0AD0h+Src]
0x1800ae240  jmp     loc_1800AE427
0x1800ae245  lea     rcx, [rbx+28h]; StringSecurityDescriptor
0x1800ae249  mov     edx, 1; StringSDRevision
0x1800ae24e  lea     r9, [rbp+0AD0h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800ae255  lea     r8, [rsp+0BD0h+SecurityDescriptor]; SecurityDescriptor
0x1800ae25a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800ae261  nop     dword ptr [rax+rax+00h]
0x1800ae266  test    eax, eax
0x1800ae268  jnz     short loc_1800AE298
0x1800ae26a  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800ae26f  mov     edi, eax
0x1800ae271  mov     eax, cs:dword_18039EB68
0x1800ae277  cmp     eax, 2
0x1800ae27a  jbe     short loc_1800AE239
0x1800ae27c  mov     [rbp+0AD0h+arg_8], edi
0x1800ae282  lea     rdx, word_18032868E
0x1800ae289  mov     dword ptr [rbp+0AD0h+arg_10], 15D3h
0x1800ae293  jmp     loc_1800AE20D
0x1800ae298  mov     rbx, [rbp+0AD0h+Src]
0x1800ae29f  mov     ecx, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ae2a5  cmp     ecx, [rbx+0AC8h]
0x1800ae2ab  jbe     loc_1800AE395
0x1800ae2b1  mov     eax, [rbx+4Ch]
0x1800ae2b4  add     eax, 48h ; 'H'
0x1800ae2b7  mov     r15d, eax
0x1800ae2ba  add     rax, 3
0x1800ae2be  shr     rax, 2
0x1800ae2c2  lea     edi, [rcx+rax*4]
0x1800ae2c5  xor     ecx, ecx; uFlags
0x1800ae2c7  mov     edx, edi; uBytes
0x1800ae2c9  call    cs:__imp_LocalAlloc
0x1800ae2d0  nop     dword ptr [rax+rax+00h]
0x1800ae2d5  mov     r14, rax
0x1800ae2d8  test    rax, rax
0x1800ae2db  jnz     short loc_1800AE344
0x1800ae2dd  mov     eax, cs:dword_18039EB68
0x1800ae2e3  mov     edi, 9C42h
0x1800ae2e8  cmp     eax, 2
0x1800ae2eb  jbe     loc_1800AE427
0x1800ae2f1  lea     rax, [rbp+0AD0h+arg_8]
0x1800ae2f8  mov     [rbp+0AD0h+arg_8], edi
0x1800ae2fe  mov     [rsp+0BD0h+var_BA0], rax
0x1800ae303  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ae30a  lea     rax, [rbp+0AD0h+arg_10]
0x1800ae311  mov     dword ptr [rbp+0AD0h+arg_10], 15E2h
0x1800ae31b  mov     [rsp+0BD0h+var_BA8], rax
0x1800ae320  lea     rdx, byte_180329B01
0x1800ae327  lea     rax, [rbp+0AD0h+Src]
0x1800ae32e  mov     [rbp+0AD0h+Src], r14
0x1800ae335  mov     [rsp+0BD0h+var_BB0], rax
0x1800ae33a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae33f  jmp     loc_1800AE42E
0x1800ae344  mov     r8, r15; Size
0x1800ae347  mov     rdx, rbx; Src
0x1800ae34a  mov     rcx, r14; void *
0x1800ae34d  call    memcpy_0
0x1800ae352  lea     eax, [rdi-48h]
0x1800ae355  mov     rcx, rbx; hMem
0x1800ae358  mov     [r14+4Ch], eax
0x1800ae35c  mov     eax, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ae362  mov     [r14+0AC8h], eax
0x1800ae369  sub     edi, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ae36f  sub     edi, 48h ; 'H'
0x1800ae372  mov     [r14+0ACCh], edi
0x1800ae379  call    cs:__imp_LocalFree
0x1800ae380  nop     dword ptr [rax+rax+00h]
0x1800ae385  mov     ecx, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ae38b  mov     rbx, r14
0x1800ae38e  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ae395  mov     rdx, [rsp+0BD0h+SecurityDescriptor]; Src
0x1800ae39a  xor     edi, edi
0x1800ae39c  test    rdx, rdx
0x1800ae39f  jz      short loc_1800AE3C2
0x1800ae3a1  mov     r8d, ecx; Size
0x1800ae3a4  mov     ecx, [rbx+0ACCh]
0x1800ae3aa  add     rcx, 48h ; 'H'
0x1800ae3ae  add     rcx, rbx; void *
0x1800ae3b1  call    memcpy_0
0x1800ae3b6  mov     eax, [rbp+0AD0h+SecurityDescriptorSize]
0x1800ae3bc  mov     [rbx+0AC8h], eax
0x1800ae3c2  mov     rcx, rbx; struct _SU_SPACE_OBJECT *
0x1800ae3c5  call    ?SuSetSpace@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuSetSpace(_SU_SPACE_OBJECT *)
0x1800ae3ca  test    eax, eax
0x1800ae3cc  jnz     short loc_1800AE427
0x1800ae3ce  call    ?GleToSmpReturnCode@@YA?AW4SM_RETURN_CODE@@XZ; GleToSmpReturnCode(void)
0x1800ae3d3  mov     edi, eax
0x1800ae3d5  mov     eax, cs:dword_18039EB68
0x1800ae3db  cmp     eax, 2
0x1800ae3de  jbe     short loc_1800AE427
0x1800ae3e0  lea     rax, [rbp+0AD0h+arg_8]
0x1800ae3e7  mov     [rbp+0AD0h+arg_8], edi
0x1800ae3ed  mov     [rsp+0BD0h+var_BA0], rax
0x1800ae3f2  lea     rdx, word_180322072
0x1800ae3f9  lea     rax, [rbp+0AD0h+arg_10]
0x1800ae400  mov     dword ptr [rbp+0AD0h+arg_10], 15FBh
0x1800ae40a  mov     [rsp+0BD0h+var_BA8], rax
0x1800ae40f  lea     rax, [rbp+0AD0h+Src]
0x1800ae416  mov     [rsp+0BD0h+var_BB0], rax
0x1800ae41b  mov     [rbp+0AD0h+Src], r14
0x1800ae422  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae427  lea     r14, aSpctlVirtualdi_30; "Spctl_VirtualDisk_SetSecurityDescriptor"...
0x1800ae42e  mov     rax, [rsi+250h]
0x1800ae435  xor     r9d, r9d
0x1800ae438  mov     edx, [rsi+248h]
0x1800ae43e  mov     r8d, edi
0x1800ae441  mov     rcx, r12
0x1800ae444  mov     [rsp+0BD0h+var_BB0], rax
0x1800ae449  call    ?_FillMethodResponse@@YAXPEAEKW4SM_RETURN_CODE@@PEAU_SUEX_EXTENDEDSTATUS_OBJECT@@PEAK@Z; _FillMethodResponse(uchar *,ulong,SM_RETURN_CODE,_SUEX_EXTENDEDSTATUS_OBJECT *,ulong *)
0x1800ae44e  mov     rcx, [rsp+0BD0h+SecurityDescriptor]; hMem
0x1800ae453  test    rcx, rcx
0x1800ae456  jz      short loc_1800AE46D
0x1800ae458  call    cs:__imp_LocalFree
0x1800ae45f  nop     dword ptr [rax+rax+00h]
0x1800ae464  mov     [rsp+0BD0h+SecurityDescriptor], 0
0x1800ae46d  test    rbx, rbx
0x1800ae470  jz      short loc_1800AE481
0x1800ae472  mov     rcx, rbx; hMem
0x1800ae475  call    cs:__imp_LocalFree
0x1800ae47c  nop     dword ptr [rax+rax+00h]
0x1800ae481  mov     eax, cs:dword_18039EB68
0x1800ae487  cmp     eax, 5
0x1800ae48a  jbe     short loc_1800AE4C1
0x1800ae48c  lea     rax, [rbp+0AD0h+arg_8]
0x1800ae493  mov     [rbp+0AD0h+arg_8], 1609h
0x1800ae49d  mov     [rsp+0BD0h+var_BA8], rax
0x1800ae4a2  lea     rdx, byte_180320353
0x1800ae4a9  lea     rax, [rbp+0AD0h+arg_10]
0x1800ae4b0  mov     [rbp+0AD0h+arg_10], r14
0x1800ae4b7  mov     [rsp+0BD0h+var_BB0], rax
0x1800ae4bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800ae4c1  xor     eax, eax
0x1800ae4c3  add     rsp, 0BA0h
0x1800ae4ca  pop     r15
0x1800ae4cc  pop     r14
0x1800ae4ce  pop     r12
0x1800ae4d0  pop     rdi
0x1800ae4d1  pop     rsi
0x1800ae4d2  pop     rbx
0x1800ae4d3  pop     rbp
0x1800ae4d4  retn
```
