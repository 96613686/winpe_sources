# LOCATOR::FOpenEmbeddedPortablePDB(void)

- ea: `0x180086cd0`
- end: `0x180087072`
- name: `?FOpenEmbeddedPortablePDB@LOCATOR@@AEAA_NXZ`
- size: `930`
- prototype: `bool __fastcall(LOCATOR *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180086180`

## callees

- `0x180026980`
- `0x1800269d4`
- `0x1800269f8`
- `0x180033210`
- `0x180086cd0`
- `0x180087d40`
- `0x18008a930`
- `0x18008ab80`
- `0x18008abd0`
- `0x18008ac50`
- `0x1800a5970`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180086d37`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180086e43`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180086d37`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180086e43`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180086d17`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180086e27`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180086d17`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180086e27`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall LOCATOR::FOpenEmbeddedPortablePDB(LOCATOR *this)
{
  unsigned __int64 v2; // r15
  unsigned int v3; // ecx
  FILE *v4; // rbx
  bool v5; // al
  char *v6; // r14
  __int64 (__fastcall *v7)(_QWORD, _QWORD, __int64, unsigned int *); // rax
  int v8; // eax
  __int64 (__fastcall *v9)(_QWORD, _QWORD, __int64, unsigned int *); // rax
  PSGSI1::EnumPubsByAddr *v10; // rdi
  bool v11; // si
  void *v12; // rax
  void *v13; // rbx
  unsigned int v14; // ecx
  FILE *v15; // r12
  bool v16; // al
  int v17; // eax
  __int64 (__fastcall *v18)(_QWORD, _QWORD, _QWORD, void *); // rax
  int v19; // eax
  PSGSI1::EnumPubsByAddr *v20; // rcx
  _WORD *v21; // r14
  PdbMemStream *v22; // rax
  struct IStream *v23; // r15
  PSGSI1::EnumPubsByAddr *v24; // rcx
  _WORD *v25; // r12
  int v26; // r15d
  __int64 v27; // r8
  unsigned int Buffer; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int v30; // [rsp+A8h] [rbp+50h] BYREF
  int v31; // [rsp+B0h] [rbp+58h] BYREF
  unsigned int v32; // [rsp+B8h] [rbp+60h] BYREF

  v2 = (unsigned int)(*((_DWORD *)this + 853) - 8);
  v3 = *((_DWORD *)this + 855) + 4;
  v4 = (FILE *)*((_QWORD *)this + 283);
  if ( v4 )
  {
    if ( fseek(*((FILE **)this + 283), v3, 0) )
      return 0;
    v5 = fread(&Buffer, 1u, 4u, v4) == 4;
    v6 = (char *)this + 2136;
  }
  else
  {
    v6 = (char *)this + 2136;
    v7 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, unsigned int *))*((_QWORD *)this + 267);
    if ( v7 )
    {
      v8 = v7(*((_QWORD *)this + 257), v3, 4, &Buffer);
    }
    else
    {
      v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, unsigned int *))*((_QWORD *)this + 268);
      if ( !v9 || *((_DWORD *)this + 854) == -4 )
        return 0;
      v8 = v9(*((_QWORD *)this + 257), (unsigned int)(*((_DWORD *)this + 854) + 4), 4, &Buffer);
    }
    v5 = v8 >= 0;
  }
  if ( !v5 )
    return 0;
  v10 = (PSGSI1::EnumPubsByAddr *)operator new[](Buffer, (const struct std::nothrow_t *)&std::nothrow);
  if ( v10 )
  {
    v12 = operator new[](v2, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( v12 )
    {
      v14 = *((_DWORD *)this + 855) + 8;
      v15 = (FILE *)*((_QWORD *)this + 283);
      if ( v15 )
      {
        if ( fseek(*((FILE **)this + 283), v14, 0) )
          goto LABEL_50;
        v16 = fread(v13, 1u, v2, v15) == v2;
      }
      else
      {
        if ( *(_QWORD *)v6 )
        {
          v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *))v6)(
                  *((_QWORD *)this + 257),
                  v14,
                  (unsigned int)v2,
                  v12);
        }
        else
        {
          v18 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, void *))*((_QWORD *)this + 268);
          if ( !v18 || *((_DWORD *)this + 854) == -8 )
            goto LABEL_50;
          v17 = v18(*((_QWORD *)this + 257), (unsigned int)(*((_DWORD *)this + 854) + 8), (unsigned int)v2, v13);
        }
        v16 = v17 >= 0;
      }
      if ( !v16 )
        goto LABEL_50;
      v30 = Buffer;
      v31 = v2;
      v19 = uncompress2(v10, &v30, v13, &v31);
      if ( v19 != -4 )
      {
        if ( v19 == -3 || v30 != Buffer || v31 != (_DWORD)v2 )
        {
          *(_DWORD *)this = 13;
LABEL_49:
          *((_WORD *)this + 2) = 0;
          goto LABEL_50;
        }
        if ( v19 )
          goto LABEL_50;
        v20 = (PSGSI1::EnumPubsByAddr *)v13;
        v21 = 0;
        v13 = 0;
        if ( v20 )
          PSGSI1::EnumPubsByAddr::release(v20);
        v22 = (PdbMemStream *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v22 )
          v23 = PdbMemStream::PdbMemStream(v22, 0x10000u);
        else
          v23 = 0;
        if ( v23 )
        {
          if ( !(unsigned int)PdbMemStream::Seek(v23, 0, 0, 0)
            && !PdbMemStream::Write(v23, v10, Buffer, &v32)
            && v32 == Buffer )
          {
            v24 = v10;
            v10 = 0;
            PSGSI1::EnumPubsByAddr::release(v24);
            if ( !PdbMemStream::SetSize(v23, (union _ULARGE_INTEGER)Buffer) )
            {
              v25 = (_WORD *)((char *)this + 4);
              v26 = PDB::OpenInStream(v23, "r", (int *)this, (wchar_t *)this + 2, 0x400u, (struct PDB **)this + 428);
              if ( v26 )
              {
                v27 = 0;
              }
              else
              {
                v27 = *(unsigned int *)this;
                if ( !*v25 )
                  v25 = 0;
                v21 = v25;
              }
              LOCATOR::NotifyOpenPDB(this, L"Embedded Portable PDB", v27, v21);
              v11 = v26 != 0;
              goto LABEL_51;
            }
          }
LABEL_50:
          v11 = 0;
LABEL_51:
          if ( v13 )
            PSGSI1::EnumPubsByAddr::release((PSGSI1::EnumPubsByAddr *)v13);
          goto LABEL_53;
        }
      }
    }
    *(_DWORD *)this = 2;
    goto LABEL_49;
  }
  *(_DWORD *)this = 2;
  *((_WORD *)this + 2) = 0;
  v11 = 0;
LABEL_53:
  if ( v10 )
    PSGSI1::EnumPubsByAddr::release(v10);
  return v11;
}

```

## disassembly

```asm
0x180086cd0  push    rbp
0x180086cd2  push    rbx
0x180086cd3  push    rsi
0x180086cd4  push    rdi
0x180086cd5  push    r12
0x180086cd7  push    r13
0x180086cd9  push    r14
0x180086cdb  push    r15
0x180086cdd  mov     rbp, rsp
0x180086ce0  sub     rsp, 58h
0x180086ce4  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x180086cec  mov     rsi, rcx
0x180086cef  mov     r15d, [rcx+0D54h]
0x180086cf6  sub     r15d, 8
0x180086cfa  mov     ecx, [rcx+0D5Ch]
0x180086d00  add     ecx, 4
0x180086d03  mov     rbx, [rsi+8D8h]
0x180086d0a  test    rbx, rbx
0x180086d0d  jz      short loc_180086D4D
0x180086d0f  xor     r8d, r8d; Origin
0x180086d12  mov     edx, ecx; Offset
0x180086d14  mov     rcx, rbx; Stream
0x180086d17  call    cs:__imp_fseek
0x180086d1d  test    eax, eax
0x180086d1f  jnz     loc_18008705F
0x180086d25  mov     r9, rbx; Stream
0x180086d28  mov     edx, 1; ElementSize
0x180086d2d  mov     r8d, 4; ElementCount
0x180086d33  lea     rcx, [rbp+Buffer]; Buffer
0x180086d37  call    cs:__imp_fread
0x180086d3d  cmp     rax, 4
0x180086d41  setz    al
0x180086d44  lea     r14, [rsi+858h]
0x180086d4b  jmp     short loc_180086DB2
0x180086d4d  lea     r14, [rsi+858h]
0x180086d54  mov     rax, [r14]
0x180086d57  test    rax, rax
0x180086d5a  jz      short loc_180086D77
0x180086d5c  mov     edx, ecx
0x180086d5e  lea     r9, [rbp+Buffer]
0x180086d62  mov     r8d, 4
0x180086d68  mov     rcx, [rsi+808h]
0x180086d6f  call    cs:__guard_dispatch_icall_fptr
0x180086d75  jmp     short loc_180086DAD
0x180086d77  mov     rax, [rsi+860h]
0x180086d7e  test    rax, rax
0x180086d81  jz      loc_18008705F
0x180086d87  mov     edx, [rsi+0D58h]
0x180086d8d  add     edx, 4
0x180086d90  jz      loc_18008705F
0x180086d96  lea     r9, [rbp+Buffer]
0x180086d9a  mov     r8d, 4
0x180086da0  mov     rcx, [rsi+808h]
0x180086da7  call    cs:__guard_dispatch_icall_fptr
0x180086dad  shr     eax, 1Fh
0x180086db0  xor     al, 1
0x180086db2  test    al, al
0x180086db4  jz      loc_18008705F
0x180086dba  mov     ecx, [rbp+Buffer]; unsigned __int64
0x180086dbd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086dc4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180086dc9  mov     rdi, rax
0x180086dcc  mov     [rbp+var_18], rax
0x180086dd0  test    rax, rax
0x180086dd3  jnz     short loc_180086DEB
0x180086dd5  mov     dword ptr [rsi], 2
0x180086ddb  xor     r14d, r14d
0x180086dde  mov     [rsi+4], r14w
0x180086de3  xor     sil, sil
0x180086de6  jmp     loc_18008704C
0x180086deb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086df2  mov     rcx, r15; unsigned __int64
0x180086df5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180086dfa  mov     rbx, rax
0x180086dfd  mov     [rbp+var_20], rax
0x180086e01  test    rax, rax
0x180086e04  jz      loc_18008702D
0x180086e0a  mov     ecx, [rsi+0D5Ch]
0x180086e10  add     ecx, 8
0x180086e13  mov     r12, [rsi+8D8h]
0x180086e1a  test    r12, r12
0x180086e1d  jz      short loc_180086E51
0x180086e1f  xor     r8d, r8d; Origin
0x180086e22  mov     edx, ecx; Offset
0x180086e24  mov     rcx, r12; Stream
0x180086e27  call    cs:__imp_fseek
0x180086e2d  test    eax, eax
0x180086e2f  jnz     loc_18008703B
0x180086e35  mov     r9, r12; Stream
0x180086e38  mov     r8, r15; ElementCount
0x180086e3b  mov     edx, 1; ElementSize
0x180086e40  mov     rcx, rbx; Buffer
0x180086e43  call    cs:__imp_fread
0x180086e49  cmp     rax, r15
0x180086e4c  setz    al
0x180086e4f  jmp     short loc_180086EA7
0x180086e51  mov     rax, [r14]
0x180086e54  test    rax, rax
0x180086e57  jz      short loc_180086E70
0x180086e59  mov     edx, ecx
0x180086e5b  mov     r9, rbx
0x180086e5e  mov     r8d, r15d
0x180086e61  mov     rcx, [rsi+808h]
0x180086e68  call    cs:__guard_dispatch_icall_fptr
0x180086e6e  jmp     short loc_180086EA2
0x180086e70  mov     rax, [rsi+860h]
0x180086e77  test    rax, rax
0x180086e7a  jz      loc_18008703B
0x180086e80  mov     edx, [rsi+0D58h]
0x180086e86  add     edx, 8
0x180086e89  jz      loc_18008703B
0x180086e8f  mov     r9, rbx
0x180086e92  mov     r8d, r15d
0x180086e95  mov     rcx, [rsi+808h]
0x180086e9c  call    cs:__guard_dispatch_icall_fptr
0x180086ea2  shr     eax, 1Fh
0x180086ea5  xor     al, 1
0x180086ea7  test    al, al
0x180086ea9  jz      loc_18008703B
0x180086eaf  mov     eax, [rbp+Buffer]
0x180086eb2  mov     [rbp+arg_8], eax
0x180086eb5  mov     [rbp+arg_10], r15d
0x180086eb9  lea     r9, [rbp+arg_10]
0x180086ebd  mov     r8, rbx
0x180086ec0  lea     rdx, [rbp+arg_8]
0x180086ec4  mov     rcx, rdi
0x180086ec7  call    uncompress2
0x180086ecc  cmp     eax, 0FFFFFFFCh
0x180086ecf  jz      loc_18008702D
0x180086ed5  cmp     eax, 0FFFFFFFDh
0x180086ed8  jz      loc_180087022
0x180086ede  mov     ecx, [rbp+Buffer]
0x180086ee1  cmp     [rbp+arg_8], ecx
0x180086ee4  jnz     loc_180087022
0x180086eea  cmp     [rbp+arg_10], r15d
0x180086eee  jnz     loc_180087022
0x180086ef4  test    eax, eax
0x180086ef6  jnz     loc_18008703B
0x180086efc  mov     rcx, rbx; this
0x180086eff  xor     r14d, r14d
0x180086f02  mov     ebx, r14d
0x180086f05  mov     [rbp+var_20], rbx
0x180086f09  test    rcx, rcx
0x180086f0c  jz      short loc_180086F13
0x180086f0e  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180086f13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086f1a  mov     ecx, 40h ; '@'; unsigned __int64
0x180086f1f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180086f24  mov     qword ptr [rbp+var_28], rax
0x180086f28  test    rax, rax
0x180086f2b  jz      short loc_180086F3F
0x180086f2d  mov     edx, 10000h; unsigned int
0x180086f32  mov     rcx, rax; this
0x180086f35  call    ??0PdbMemStream@@QEAA@I@Z; PdbMemStream::PdbMemStream(uint)
0x180086f3a  mov     r15, rax
0x180086f3d  jmp     short loc_180086F42
0x180086f3f  mov     r15, r14
0x180086f42  test    r15, r15
0x180086f45  jz      loc_180087030
0x180086f4b  mov     qword ptr [rbp+var_28], r14
0x180086f4f  xor     r9d, r9d; union _ULARGE_INTEGER *
0x180086f52  xor     r8d, r8d; unsigned int
0x180086f55  mov     rdx, r14; union _LARGE_INTEGER
0x180086f58  mov     rcx, r15; this
0x180086f5b  call    ?Seek@PdbMemStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z; PdbMemStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)
0x180086f60  test    eax, eax
0x180086f62  jnz     loc_18008703B
0x180086f68  lea     r9, [rbp+arg_18]; unsigned int *
0x180086f6c  mov     r8d, [rbp+Buffer]; unsigned int
0x180086f70  mov     rdx, rdi; void *
0x180086f73  mov     rcx, r15; this
0x180086f76  call    ?Write@PdbMemStream@@UEAAJPEBXKPEAK@Z; PdbMemStream::Write(void const *,ulong,ulong *)
0x180086f7b  test    eax, eax
0x180086f7d  jnz     loc_18008703B
0x180086f83  mov     eax, [rbp+Buffer]
0x180086f86  cmp     [rbp+arg_18], eax
0x180086f89  jnz     loc_18008703B
0x180086f8f  mov     rcx, rdi; this
0x180086f92  mov     rdi, r14
0x180086f95  mov     [rbp+var_18], r14
0x180086f99  test    rcx, rcx
0x180086f9c  jz      short loc_180086FA6
0x180086f9e  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180086fa3  mov     eax, [rbp+Buffer]
0x180086fa6  xor     ecx, ecx
0x180086fa8  mov     dword ptr [rbp+var_28+4], ecx
0x180086fab  mov     dword ptr [rbp+var_28], eax
0x180086fae  mov     rdx, qword ptr [rbp+var_28]; union _ULARGE_INTEGER
0x180086fb2  mov     rcx, r15; this
0x180086fb5  call    ?SetSize@PdbMemStream@@UEAAJT_ULARGE_INTEGER@@@Z; PdbMemStream::SetSize(_ULARGE_INTEGER)
0x180086fba  test    eax, eax
0x180086fbc  jnz     short loc_18008703B
0x180086fbe  lea     r12, [rsi+4]
0x180086fc2  lea     rax, [rsi+0D60h]
0x180086fc9  mov     [rsp+58h+var_30], rax; struct PDB **
0x180086fce  mov     [rsp+58h+var_38], 400h; unsigned __int64
0x180086fd7  mov     r9, r12; wchar_t *
0x180086fda  mov     r8, rsi; int *
0x180086fdd  lea     rdx, aR; "r"
0x180086fe4  mov     rcx, r15; struct IStream *
0x180086fe7  call    ?OpenInStream@PDB@@SAHPEAUIStream@@PEBDPEAJPEA_W_KPEAPEAU1@@Z; PDB::OpenInStream(IStream *,char const *,long *,wchar_t *,unsigned __int64,PDB * *)
0x180086fec  mov     r15d, eax
0x180086fef  test    eax, eax
0x180086ff1  jz      short loc_180086FF8
0x180086ff3  mov     r8d, r14d
0x180086ff6  jmp     short loc_180087007
0x180086ff8  mov     r8d, [rsi]
0x180086ffb  cmp     [r12], r14w
0x180087000  cmovz   r12, r14
0x180087004  mov     r14, r12
0x180087007  mov     r9, r14
0x18008700a  lea     rdx, aEmbeddedPortab; "Embedded Portable PDB"
0x180087011  mov     rcx, rsi
0x180087014  call    ?NotifyOpenPDB@LOCATOR@@AEAAXPEB_WW4PDBErrors@@0@Z; LOCATOR::NotifyOpenPDB(wchar_t const *,PDBErrors,wchar_t const *)
0x180087019  test    r15d, r15d
0x18008701c  setnz   sil
0x180087020  jmp     short loc_18008703E
0x180087022  mov     dword ptr [rsi], 0Dh
0x180087028  xor     r14d, r14d
0x18008702b  jmp     short loc_180087036
0x18008702d  xor     r14d, r14d
0x180087030  mov     dword ptr [rsi], 2
0x180087036  mov     [rsi+4], r14w
0x18008703b  xor     sil, sil
0x18008703e  test    rbx, rbx
0x180087041  jz      short loc_18008704C
0x180087043  mov     rcx, rbx; this
0x180087046  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18008704b  nop
0x18008704c  test    rdi, rdi
0x18008704f  jz      short loc_180087059
0x180087051  mov     rcx, rdi; this
0x180087054  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x180087059  movzx   eax, sil
0x18008705d  jmp     short loc_180087061
0x18008705f  xor     al, al
0x180087061  add     rsp, 58h
0x180087065  pop     r15
0x180087067  pop     r14
0x180087069  pop     r13
0x18008706b  pop     r12
0x18008706d  pop     rdi
0x18008706e  pop     rsi
0x18008706f  pop     rbx
0x180087070  pop     rbp
0x180087071  retn
```
