# SipProvider::CreateHash(SIP_SUBJECTINFO_ const *,ulong *,SIP_INDIRECT_DATA_ *)

- ea: `0x1800037bc`
- end: `0x180003aa9`
- name: `?CreateHash@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@PEAKPEAUSIP_INDIRECT_DATA_@@@Z`
- size: `749`
- prototype: `unsigned int(SipProvider *__hidden this, const struct SIP_SUBJECTINFO_ *, unsigned int *, struct SIP_INDIRECT_DATA_ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800049c0`

## callees

- `0x180001008`
- `0x180001014`
- `0x1800037bc`
- `0x180004220`
- `0x1800042ec`
- `0x180004834`
- `0x1800054a2`
- `0x1800054f0`
- `0x180006010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003a38`
- `KERNEL32!GetLastError` at `0x180003a38`
- `CRYPT32!CryptEncodeObject` at `0x18000391d`
- `CRYPT32!CryptEncodeObject` at `0x180003952`
- `CRYPT32!CryptEncodeObject` at `0x18000391d`
- `CRYPT32!CryptEncodeObject` at `0x180003952`

## pseudocode

```c
__int64 __fastcall SipProvider::CreateHash(
        SipProvider *this,
        const struct SIP_SUBJECTINFO_ *a2,
        unsigned int *a3,
        struct SIP_INDIRECT_DATA_ *a4)
{
  void *v7; // r12
  SipFile *v8; // rax
  struct SipFile *v9; // r14
  unsigned int HashSize; // esi
  void (__fastcall ***v11)(_QWORD, __int64, __int64); // r15
  SipProvider *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  size_t v16; // rdx
  __int64 v17; // rax
  LPSTR pszObjId; // rcx
  DWORD v19; // r11d
  DWORD v20; // r9d
  unsigned int v21; // r10d
  unsigned int v22; // ecx
  CHAR *v23; // rdi
  BYTE *v24; // rbx
  unsigned int pcbEncoded; // [rsp+20h] [rbp-E0h]
  DWORD v27; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Size; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int Size_4; // [rsp+38h] [rbp-C8h]
  unsigned int *v30; // [rsp+40h] [rbp-C0h]
  void *Src; // [rsp+48h] [rbp-B8h]
  __int128 pvStructInfo; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  _BYTE v35[40]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v36[1024]; // [rsp+A0h] [rbp-60h] BYREF

  Size = 0;
  v27 = 0;
  v30 = a3;
  v34 = 0;
  pvStructInfo = 0;
  v33 = 0;
  if ( !a2 || !a3 )
    return 87;
  v7 = 0;
  if ( !a4 )
  {
    v9 = 0;
    HashSize = SipProvider::GetHashSize(0, a2, &Size);
    if ( HashSize )
      return HashSize;
    goto LABEL_10;
  }
  v8 = (SipFile *)(*(__int64 (__fastcall **)(SipProvider *))(*(_QWORD *)this + 8LL))(this);
  v9 = v8;
  if ( !v8 )
    return 8;
  v11 = 0;
  HashSize = SipFile::Open(v8, a2, 0);
  if ( !HashSize )
  {
    HashSize = SipProvider::GetHash(v12, v9, a2, v36, pcbEncoded, &Size);
    if ( !HashSize )
    {
LABEL_10:
      v13 = (*(__int64 (__fastcall **)(SipProvider *))(*(_QWORD *)this + 16LL))(this);
      v11 = (void (__fastcall ***)(_QWORD, __int64, __int64))v13;
      if ( v13 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 24LL))(v13, v35);
        pvStructInfo = *(_OWORD *)v15;
        v33 = *(_OWORD *)(v15 + 16);
        v34 = *(_QWORD *)(v15 + 32);
        if ( CryptEncodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", &pvStructInfo, 0, &v27)
          && (v7 = operator new(v27),
              CryptEncodeObject(0x10001u, "1.3.6.1.4.1.311.2.1.30", &pvStructInfo, (BYTE *)v7, &v27)) )
        {
          v16 = v27;
          v17 = -1;
          pszObjId = a2->DigestAlgorithm.pszObjId;
          Src = pszObjId;
          v19 = v27 + 87;
          do
            ++v17;
          while ( pszObjId[v17] );
          v20 = Size;
          Size_4 = v17 + 1;
          v21 = v17 + 1 + v19;
          v22 = v21 + Size;
          v14 = *v30;
          *v30 = v21 + Size;
          if ( a4 )
          {
            if ( v22 <= (unsigned int)v14 )
            {
              a4->Data.Value.cbData = v16;
              a4->Data.pszObjId = (LPSTR)&a4[1];
              a4->Data.Value.pbData = (BYTE *)&a4[1].Data.Value.pbData + 7;
              a4->DigestAlgorithm.Parameters.pbData = 0;
              a4->DigestAlgorithm.Parameters.cbData = 0;
              a4->Digest.cbData = v20;
              v23 = (char *)a4 + v19;
              a4->DigestAlgorithm.pszObjId = v23;
              v24 = (BYTE *)a4 + v21;
              a4->Digest.pbData = v24;
              strcpy((char *)&a4[1], "1.3.6.1.4.1.311.2.1.30");
              memcpy_0((char *)&a4[1].Data.Value.pbData + 7, v7, v16);
              memcpy_0(v23, Src, Size_4);
              memcpy_0(v24, v36, Size);
            }
            else
            {
              HashSize = 122;
            }
          }
        }
        else
        {
          HashSize = GetLastError();
        }
      }
      else
      {
        HashSize = 8;
      }
      if ( !v9 )
        goto LABEL_23;
    }
  }
  (**(void (__fastcall ***)(struct SipFile *, __int64))v9)(v9, 1);
LABEL_23:
  if ( v11 )
    (**v11)(v11, 1, v14);
  if ( v7 )
    operator delete(v7);
  return HashSize;
}

```

## disassembly

```asm
0x1800037bc  push    rbp
0x1800037be  push    rbx
0x1800037bf  push    rsi
0x1800037c0  push    rdi
0x1800037c1  push    r12
0x1800037c3  push    r13
0x1800037c5  push    r14
0x1800037c7  push    r15
0x1800037c9  lea     rbp, [rsp-3B8h]
0x1800037d1  sub     rsp, 4B8h
0x1800037d8  mov     rax, cs:__security_cookie
0x1800037df  xor     rax, rsp
0x1800037e2  mov     [rbp+3F0h+var_50], rax
0x1800037e9  xorps   xmm0, xmm0
0x1800037ec  mov     dword ptr [rsp+4F0h+Size], 0
0x1800037f4  mov     rdi, rcx
0x1800037f7  mov     [rsp+4F0h+var_4C0], 0
0x1800037ff  xor     ecx, ecx; this
0x180003801  mov     rax, r8
0x180003804  mov     [rsp+4F0h+var_4B0], rax
0x180003809  mov     r13, r9
0x18000380c  mov     [rsp+4F0h+var_480], rcx
0x180003811  mov     rbx, rdx
0x180003814  movups  [rsp+4F0h+pvStructInfo], xmm0
0x180003819  movups  [rsp+4F0h+var_490], xmm0
0x18000381e  test    rdx, rdx
0x180003821  jz      loc_180003A7F
0x180003827  test    rax, rax
0x18000382a  jz      loc_180003A7F
0x180003830  xor     r12d, r12d
0x180003833  test    r9, r9
0x180003836  jz      short loc_180003897
0x180003838  mov     rax, [rdi]
0x18000383b  mov     rcx, rdi
0x18000383e  mov     rax, [rax+8]
0x180003842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003847  mov     r14, rax
0x18000384a  test    rax, rax
0x18000384d  jnz     short loc_180003857
0x18000384f  lea     esi, [rax+8]
0x180003852  jmp     loc_180003A84
0x180003857  xor     r8d, r8d; bool
0x18000385a  mov     rdx, rbx; struct SIP_SUBJECTINFO_ *
0x18000385d  mov     rcx, r14; this
0x180003860  xor     r15d, r15d
0x180003863  call    ?Open@SipFile@@QEAAKPEBUSIP_SUBJECTINFO_@@_N@Z; SipFile::Open(SIP_SUBJECTINFO_ const *,bool)
0x180003868  mov     esi, eax
0x18000386a  test    eax, eax
0x18000386c  jnz     loc_180003A45
0x180003872  lea     rax, [rsp+4F0h+Size]
0x180003877  mov     r8, rbx; struct SIP_SUBJECTINFO_ *
0x18000387a  lea     r9, [rbp+3F0h+var_450]; unsigned __int8 *
0x18000387e  mov     [rsp+4F0h+var_4C8], rax; unsigned int *
0x180003883  mov     rdx, r14; struct SipFile *
0x180003886  call    ?GetHash@SipProvider@@QEAAKPEAVSipFile@@PEBUSIP_SUBJECTINFO_@@PEAEKPEAK@Z; SipProvider::GetHash(SipFile *,SIP_SUBJECTINFO_ const *,uchar *,ulong,ulong *)
0x18000388b  mov     esi, eax
0x18000388d  test    eax, eax
0x18000388f  jnz     loc_180003A45
0x180003895  jmp     short loc_1800038AE
0x180003897  lea     r8, [rsp+4F0h+Size]; unsigned int *
0x18000389c  xor     r14d, r14d
0x18000389f  call    ?GetHashSize@SipProvider@@QEAAKPEBUSIP_SUBJECTINFO_@@PEAK@Z; SipProvider::GetHashSize(SIP_SUBJECTINFO_ const *,ulong *)
0x1800038a4  mov     esi, eax
0x1800038a6  test    eax, eax
0x1800038a8  jnz     loc_180003A84
0x1800038ae  mov     rax, [rdi]
0x1800038b1  mov     rcx, rdi
0x1800038b4  mov     rax, [rax+10h]
0x1800038b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038bd  mov     r15, rax
0x1800038c0  test    rax, rax
0x1800038c3  jnz     short loc_1800038CD
0x1800038c5  lea     esi, [rax+8]
0x1800038c8  jmp     loc_180003A40
0x1800038cd  mov     rax, [rax]
0x1800038d0  lea     rdx, [rsp+4F0h+var_478]
0x1800038d5  mov     rcx, r15
0x1800038d8  mov     rax, [rax+18h]
0x1800038dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e1  mov     edi, 10001h
0x1800038e6  lea     r8, [rsp+4F0h+pvStructInfo]; pvStructInfo
0x1800038eb  xor     r9d, r9d; pbEncoded
0x1800038ee  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x1800038f5  mov     ecx, edi; dwCertEncodingType
0x1800038f7  movups  xmm0, xmmword ptr [rax]
0x1800038fa  movups  [rsp+4F0h+pvStructInfo], xmm0
0x1800038ff  movups  xmm1, xmmword ptr [rax+10h]
0x180003903  movups  [rsp+4F0h+var_490], xmm1
0x180003908  movsd   xmm0, qword ptr [rax+20h]
0x18000390d  lea     rax, [rsp+4F0h+var_4C0]
0x180003912  mov     [rsp+4F0h+pcbEncoded], rax; pcbEncoded
0x180003917  movsd   [rsp+4F0h+var_480], xmm0
0x18000391d  call    cs:__imp_CryptEncodeObject
0x180003923  test    eax, eax
0x180003925  jz      loc_180003A38
0x18000392b  mov     ecx, [rsp+4F0h+var_4C0]; Size
0x18000392f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003934  mov     r12, rax
0x180003937  lea     r8, [rsp+4F0h+pvStructInfo]; pvStructInfo
0x18000393c  lea     rax, [rsp+4F0h+var_4C0]
0x180003941  mov     r9, r12; pbEncoded
0x180003944  lea     rdx, szStructType; "1.3.6.1.4.1.311.2.1.30"
0x18000394b  mov     [rsp+4F0h+pcbEncoded], rax; pcbEncoded
0x180003950  mov     ecx, edi; dwCertEncodingType
0x180003952  call    cs:__imp_CryptEncodeObject
0x180003958  test    eax, eax
0x18000395a  jz      loc_180003A38
0x180003960  mov     edx, [rsp+4F0h+var_4C0]
0x180003964  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003968  mov     rcx, [rbx+38h]
0x18000396c  mov     [rsp+4F0h+Src], rcx
0x180003971  lea     r11d, [rdx+57h]
0x180003975  inc     rax
0x180003978  cmp     byte ptr [rcx+rax], 0
0x18000397c  jnz     short loc_180003975
0x18000397e  mov     r9d, dword ptr [rsp+4F0h+Size]
0x180003983  inc     eax
0x180003985  mov     dword ptr [rsp+4F0h+Size+4], eax
0x180003989  lea     r10d, [rax+r11]
0x18000398d  mov     rax, [rsp+4F0h+var_4B0]
0x180003992  lea     ecx, [r10+r9]
0x180003996  mov     r8d, [rax]
0x180003999  mov     [rax], ecx
0x18000399b  test    r13, r13
0x18000399e  jz      loc_180003A40
0x1800039a4  cmp     ecx, r8d
0x1800039a7  jbe     short loc_1800039B3
0x1800039a9  mov     esi, 7Ah ; 'z'
0x1800039ae  jmp     loc_180003A40
0x1800039b3  mov     [r13+8], edx
0x1800039b7  lea     r8, [r13+40h]
0x1800039bb  mov     [r13+0], r8
0x1800039bf  lea     rcx, [r13+57h]; void *
0x1800039c3  mov     [r13+10h], rcx
0x1800039c7  mov     qword ptr [r13+28h], 0
0x1800039cf  mov     dword ptr [r13+20h], 0
0x1800039d7  mov     [r13+30h], r9d
0x1800039db  mov     edi, r11d
0x1800039de  mov     ebx, r10d
0x1800039e1  add     rdi, r13
0x1800039e4  mov     [r13+18h], rdi
0x1800039e8  add     rbx, r13
0x1800039eb  mov     [r13+38h], rbx
0x1800039ef  movups  xmm0, xmmword ptr cs:szStructType; "1.3.6.1.4.1.311.2.1.30"
0x1800039f6  movups  xmmword ptr [r8], xmm0
0x1800039fa  movsd   xmm1, qword ptr cs:szStructType+0Fh; ".2.1.30"
0x180003a02  movsd   qword ptr [r8+0Fh], xmm1
0x180003a08  mov     r8, rdx; Size
0x180003a0b  mov     rdx, r12; Src
0x180003a0e  call    memcpy_0
0x180003a13  mov     r8d, dword ptr [rsp+4F0h+Size+4]; Size
0x180003a18  mov     rcx, rdi; void *
0x180003a1b  mov     rdx, [rsp+4F0h+Src]; Src
0x180003a20  call    memcpy_0
0x180003a25  mov     r8d, dword ptr [rsp+4F0h+Size]; Size
0x180003a2a  lea     rdx, [rbp+3F0h+var_450]; Src
0x180003a2e  mov     rcx, rbx; void *
0x180003a31  call    memcpy_0
0x180003a36  jmp     short loc_180003A40
0x180003a38  call    cs:__imp_GetLastError
0x180003a3e  mov     esi, eax
0x180003a40  test    r14, r14
0x180003a43  jz      short loc_180003A58
0x180003a45  mov     rax, [r14]
0x180003a48  mov     edx, 1
0x180003a4d  mov     rcx, r14
0x180003a50  mov     rax, [rax]
0x180003a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a58  test    r15, r15
0x180003a5b  jz      short loc_180003A70
0x180003a5d  mov     rax, [r15]
0x180003a60  mov     edx, 1
0x180003a65  mov     rcx, r15
0x180003a68  mov     rax, [rax]
0x180003a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a70  test    r12, r12
0x180003a73  jz      short loc_180003A84
0x180003a75  mov     rcx, r12; Block
0x180003a78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003a7d  jmp     short loc_180003A84
0x180003a7f  mov     esi, 57h ; 'W'
0x180003a84  mov     eax, esi
0x180003a86  mov     rcx, [rbp+3F0h+var_50]
0x180003a8d  xor     rcx, rsp; StackCookie
0x180003a90  call    __security_check_cookie
0x180003a95  add     rsp, 4B8h
0x180003a9c  pop     r15
0x180003a9e  pop     r14
0x180003aa0  pop     r13
0x180003aa2  pop     r12
0x180003aa4  pop     rdi
0x180003aa5  pop     rsi
0x180003aa6  pop     rbx
0x180003aa7  pop     rbp
0x180003aa8  retn
```
