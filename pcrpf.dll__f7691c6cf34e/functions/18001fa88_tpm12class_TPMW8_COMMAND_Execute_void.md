# tpm12class::TPMW8_COMMAND::Execute(void *)

- ea: `0x18001fa88`
- end: `0x18001fe1b`
- name: `?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z`
- size: `915`
- prototype: `__int64 __fastcall(tpm12class::TPMW8_COMMAND *__hidden this, void *)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001c964`
- `0x18001eb44`
- `0x1800206b8`

## callees

- `0x18000367c`
- `0x180003b3c`
- `0x180003cf0`
- `0x18001eb44`
- `0x18001ee88`
- `0x18001f650`
- `0x18001fa88`
- `0x180020048`
- `0x1800205f8`
- `0x1800206b8`
- `0x180020828`
- `0x1800241f0`
- `0x1800242bc`
- `0x1800243cc`
- `0x180059010`

## pseudocode

```c
__int64 __fastcall tpm12class::TPMW8_COMMAND::Execute(tpm12class::TPMW8_COMMAND *this, void *a2)
{
  unsigned int v2; // r13d
  tpm12class::TPMW8_SESSION *v4; // rcx
  void *v5; // r12
  void *v6; // r15
  tpm12class::TPMW8_SESSION **v7; // rdi
  tpm12class::TPMW8_SESSION **v8; // rsi
  signed int v9; // ebx
  unsigned int v10; // ebx
  unsigned __int8 v11; // al
  tpm12class::TPMW8_SESSION *v12; // rcx
  int v13; // eax
  bool v14; // sf
  tpm12class::TPMW8_SESSION *v15; // rcx
  tpm12class::TPMW8_SESSION *v16; // rcx
  tpm12class::TPMW8_SESSION *v17; // rcx
  tpm12class::TPMW8_SESSION *v18; // rcx
  tpm12class::TPMW8_SESSION *v19; // rcx
  __int64 v20; // rax
  _BYTE *v21; // rdx
  __int64 v22; // rdx
  _BYTE *v23; // rax
  size_t v25; // [rsp+70h] [rbp+40h] BYREF
  void *v26; // [rsp+78h] [rbp+48h]
  size_t Size; // [rsp+80h] [rbp+50h] BYREF

  v26 = a2;
  v2 = 0;
  LODWORD(v25) = 4096;
  LODWORD(Size) = 0;
  v4 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
  v5 = 0;
  v6 = 0;
  if ( v4
    || (v7 = (tpm12class::TPMW8_SESSION **)((char *)this + 176), *((_QWORD *)this + 22))
    || (v8 = (tpm12class::TPMW8_SESSION **)((char *)this + 184), *((_QWORD *)this + 23)) )
  {
    *((_WORD *)this + 28) = -32766;
    v7 = (tpm12class::TPMW8_SESSION **)((char *)this + 176);
    v8 = (tpm12class::TPMW8_SESSION **)((char *)this + 184);
    if ( v4 )
    {
      v9 = tpm12class::TPMW8_SESSION::Create(v4, a2);
      if ( v9 < 0 )
        goto LABEL_39;
      if ( *v7 )
      {
        v9 = tpm12class::TPMW8_SESSION::Create(*v7, v26);
        if ( v9 < 0 )
          goto LABEL_39;
        if ( *v8 )
        {
          v9 = tpm12class::TPMW8_SESSION::Create(*v8, v26);
          if ( v9 < 0 )
            goto LABEL_39;
        }
      }
    }
  }
  v9 = tpm12class::TPMW8_COMMAND::Get(this, 0, 0, (unsigned int *)&Size);
  if ( v9 < 0
    || (v10 = Size,
        v5 = operator new((unsigned int)Size),
        memset_0(v5, 0, v10),
        v9 = tpm12class::TPMW8_COMMAND::Get(this, (unsigned __int8 *)v5, Size, (unsigned int *)&Size),
        v9 < 0) )
  {
    v2 = Size;
LABEL_39:
    v17 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
    if ( v17 && (*((_BYTE *)v17 + 764) & 1) == 0 )
      tpm12class::TPMW8_SESSION::Release(v17);
    v18 = *v7;
    if ( *v7 && (*((_BYTE *)v18 + 764) & 1) == 0 )
      tpm12class::TPMW8_SESSION::Release(v18);
    v19 = *v8;
    if ( *v8 && (*((_BYTE *)v19 + 764) & 1) == 0 )
      tpm12class::TPMW8_SESSION::Release(v19);
    goto LABEL_48;
  }
  v11 = TraceEnabled();
  v2 = Size;
  if ( v11 )
  {
    (*(void (__fastcall **)(tpm12class::TPMW8_COMMAND *, const wchar_t *))(*(_QWORD *)this + 56LL))(this, L"RQU.");
    TraceDirect(L"\r\n");
    v12 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
    if ( v12 )
    {
      tpm12class::TPMW8_SESSION::Decode(v12, L"AUTH[1].");
      if ( *v7 )
      {
        tpm12class::TPMW8_SESSION::Decode(*v7, L"AUTH[2].");
        if ( *v8 )
          tpm12class::TPMW8_SESSION::Decode(*v8, L"AUTH[3].");
      }
    }
    TraceTpmBufferValue(1u, (unsigned __int8 *)v5, v2);
  }
  v6 = operator new((unsigned int)v25);
  memset_0(v6, 0, (unsigned int)v25);
  if ( g_fpW8TpmSubmit )
  {
    v13 = g_fpW8TpmSubmit(v26, (unsigned __int8 *const)v5, v2, (unsigned __int8 *)v6, (unsigned int *)&v25);
    v9 = v13 & 0xEFFFFFFF;
    if ( v13 < 0 )
      goto LABEL_39;
  }
  if ( TraceEnabled() )
  {
    TraceTpmBufferValue(0, (unsigned __int8 *)v6, v25);
    TraceDirect(L"\r\n");
  }
  v9 = tpm12class::TPMW8_COMMAND::Set(this, (const unsigned __int8 *)v6, v25);
  if ( (v9 & 0xFFFF0000) == 0x80280000 )
  {
    if ( TraceEnabled() )
    {
      tpm12class::TPMW8_COMMAND::DecodeRsp(this, L"RSP.");
      TraceDirect(L"\r\n");
    }
    v14 = v9 < 0;
LABEL_26:
    if ( !v14 )
      goto LABEL_48;
    goto LABEL_39;
  }
  v14 = v9 < 0;
  if ( v9 )
    goto LABEL_26;
  if ( TraceEnabled() )
  {
    (*(void (__fastcall **)(tpm12class::TPMW8_COMMAND *, const unsigned __int16 *))(*(_QWORD *)this + 72LL))(
      this,
      L"RSP.");
    TraceDirect(L"\r\n");
    v15 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
    if ( v15 )
    {
      tpm12class::TPMW8_SESSION::Decode(v15, L"AUTH[1].");
      if ( *v7 )
      {
        tpm12class::TPMW8_SESSION::Decode(*v7, L"AUTH[2].");
        if ( *v8 )
          tpm12class::TPMW8_SESSION::Decode(*v8, L"AUTH[3].");
      }
    }
  }
  v16 = (tpm12class::TPMW8_SESSION *)*((_QWORD *)this + 21);
  if ( v16 )
  {
    tpm12class::TPMW8_SESSION::Refresh(v16);
    if ( *v7 )
    {
      tpm12class::TPMW8_SESSION::Refresh(*v7);
      if ( *v8 )
        tpm12class::TPMW8_SESSION::Refresh(*v8);
    }
  }
LABEL_48:
  if ( v6 )
  {
    v20 = (unsigned int)v25;
    v21 = v6;
    if ( (_DWORD)v25 )
    {
      do
      {
        *v21++ = 0;
        --v20;
      }
      while ( v20 );
    }
    operator delete(v6);
  }
  LODWORD(v25) = 0;
  if ( v5 )
  {
    v22 = v2;
    v23 = v5;
    if ( v2 )
    {
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
    }
    operator delete(v5);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001fa88  mov     [rsp-38h+arg_18], rbx
0x18001fa8d  mov     [rsp-38h+arg_8], rdx
0x18001fa92  push    rbp
0x18001fa93  push    rsi
0x18001fa94  push    rdi
0x18001fa95  push    r12
0x18001fa97  push    r13
0x18001fa99  push    r14
0x18001fa9b  push    r15
0x18001fa9d  mov     rbp, rsp
0x18001faa0  sub     rsp, 30h
0x18001faa4  xor     r13d, r13d
0x18001faa7  mov     dword ptr [rbp+arg_0], 1000h
0x18001faae  mov     r14, rcx
0x18001fab1  mov     dword ptr [rbp+Size], r13d
0x18001fab5  mov     rcx, [rcx+0A8h]; this
0x18001fabc  xor     r12d, r12d
0x18001fabf  xor     r15d, r15d
0x18001fac2  test    rcx, rcx
0x18001fac5  jnz     short loc_18001FADF
0x18001fac7  lea     rdi, [r14+0B0h]
0x18001face  cmp     [rdi], r12
0x18001fad1  jnz     short loc_18001FADF
0x18001fad3  lea     rsi, [r14+0B8h]
0x18001fada  cmp     [rsi], r12
0x18001fadd  jz      short loc_18001FB3E
0x18001fadf  mov     word ptr [r14+38h], 8002h
0x18001fae6  lea     rdi, [r14+0B0h]
0x18001faed  lea     rsi, [r14+0B8h]
0x18001faf4  test    rcx, rcx
0x18001faf7  jz      short loc_18001FB3E
0x18001faf9  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x18001fafe  mov     ebx, eax
0x18001fb00  test    eax, eax
0x18001fb02  js      loc_18001FD6B
0x18001fb08  mov     rcx, [rdi]; this
0x18001fb0b  test    rcx, rcx
0x18001fb0e  jz      short loc_18001FB3E
0x18001fb10  mov     rdx, [rbp+arg_8]; void *
0x18001fb14  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x18001fb19  mov     ebx, eax
0x18001fb1b  test    eax, eax
0x18001fb1d  js      loc_18001FD6B
0x18001fb23  mov     rcx, [rsi]; this
0x18001fb26  test    rcx, rcx
0x18001fb29  jz      short loc_18001FB3E
0x18001fb2b  mov     rdx, [rbp+arg_8]; void *
0x18001fb2f  call    ?Create@TPMW8_SESSION@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_SESSION::Create(void *)
0x18001fb34  mov     ebx, eax
0x18001fb36  test    eax, eax
0x18001fb38  js      loc_18001FD6B
0x18001fb3e  lea     r9, [rbp+Size]; unsigned int *
0x18001fb42  xor     r8d, r8d; unsigned int
0x18001fb45  xor     edx, edx; unsigned __int8 *
0x18001fb47  mov     rcx, r14; this
0x18001fb4a  call    ?Get@TPMW8_COMMAND@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPMW8_COMMAND::Get(uchar *,uint,uint *)
0x18001fb4f  mov     ebx, eax
0x18001fb51  test    eax, eax
0x18001fb53  js      loc_18001FD67
0x18001fb59  mov     ebx, dword ptr [rbp+Size]
0x18001fb5c  mov     ecx, ebx; Size
0x18001fb5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fb63  mov     r8d, ebx; Size
0x18001fb66  xor     edx, edx; Val
0x18001fb68  mov     rcx, rax; void *
0x18001fb6b  mov     r12, rax
0x18001fb6e  call    memset_0
0x18001fb73  mov     r8d, dword ptr [rbp+Size]; unsigned int
0x18001fb77  lea     r9, [rbp+Size]; unsigned int *
0x18001fb7b  mov     rdx, r12; unsigned __int8 *
0x18001fb7e  mov     rcx, r14; this
0x18001fb81  call    ?Get@TPMW8_COMMAND@tpm12class@@QEAAJPEAEIPEAI@Z; tpm12class::TPMW8_COMMAND::Get(uchar *,uint,uint *)
0x18001fb86  mov     ebx, eax
0x18001fb88  test    eax, eax
0x18001fb8a  js      loc_18001FD67
0x18001fb90  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18001fb95  mov     r13d, dword ptr [rbp+Size]
0x18001fb99  test    al, al
0x18001fb9b  jz      short loc_18001FC0C
0x18001fb9d  mov     rax, [r14]
0x18001fba0  lea     rdx, aRqu; "RQU."
0x18001fba7  mov     rcx, r14
0x18001fbaa  mov     rax, [rax+38h]
0x18001fbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbb3  lea     rcx, asc_18005DE7C; "\r\n"
0x18001fbba  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18001fbbf  mov     rcx, [r14+0A8h]; this
0x18001fbc6  test    rcx, rcx
0x18001fbc9  jz      short loc_18001FBFF
0x18001fbcb  lea     rdx, aAuth1; "AUTH[1]."
0x18001fbd2  call    ?Decode@TPMW8_SESSION@tpm12class@@QEAAJPEAG@Z; tpm12class::TPMW8_SESSION::Decode(ushort *)
0x18001fbd7  mov     rcx, [rdi]; this
0x18001fbda  test    rcx, rcx
0x18001fbdd  jz      short loc_18001FBFF
0x18001fbdf  lea     rdx, aAuth2; "AUTH[2]."
0x18001fbe6  call    ?Decode@TPMW8_SESSION@tpm12class@@QEAAJPEAG@Z; tpm12class::TPMW8_SESSION::Decode(ushort *)
0x18001fbeb  mov     rcx, [rsi]; this
0x18001fbee  test    rcx, rcx
0x18001fbf1  jz      short loc_18001FBFF
0x18001fbf3  lea     rdx, aAuth3; "AUTH[3]."
0x18001fbfa  call    ?Decode@TPMW8_SESSION@tpm12class@@QEAAJPEAG@Z; tpm12class::TPMW8_SESSION::Decode(ushort *)
0x18001fbff  mov     r8d, r13d; unsigned int
0x18001fc02  mov     rdx, r12; unsigned __int8 *
0x18001fc05  mov     cl, 1; unsigned __int8
0x18001fc07  call    ?TraceTpmBufferValue@@YAJEPEAEI@Z; TraceTpmBufferValue(uchar,uchar *,uint)
0x18001fc0c  mov     ecx, dword ptr [rbp+arg_0]; Size
0x18001fc0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fc14  mov     r8d, dword ptr [rbp+arg_0]; Size
0x18001fc18  xor     edx, edx; Val
0x18001fc1a  mov     rcx, rax; void *
0x18001fc1d  mov     r15, rax
0x18001fc20  call    memset_0
0x18001fc25  mov     rax, cs:?g_fpW8TpmSubmit@@3P6AIPEAXQEAEIPEAEPEAI@ZEA; uint (*g_fpW8TpmSubmit)(void *,uchar * const,uint,uchar *,uint *)
0x18001fc2c  test    rax, rax
0x18001fc2f  jz      short loc_18001FC5A
0x18001fc31  lea     rcx, [rbp+arg_0]
0x18001fc35  mov     r9, r15
0x18001fc38  mov     [rsp+30h+var_10], rcx
0x18001fc3d  mov     r8d, r13d
0x18001fc40  mov     rcx, [rbp+arg_8]
0x18001fc44  mov     rdx, r12
0x18001fc47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc4c  mov     ebx, eax
0x18001fc4e  and     ebx, 0EFFFFFFFh
0x18001fc54  jl      loc_18001FD6B
0x18001fc5a  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18001fc5f  test    al, al
0x18001fc61  jz      short loc_18001FC7D
0x18001fc63  mov     r8d, dword ptr [rbp+arg_0]; unsigned int
0x18001fc67  mov     rdx, r15; unsigned __int8 *
0x18001fc6a  xor     ecx, ecx; unsigned __int8
0x18001fc6c  call    ?TraceTpmBufferValue@@YAJEPEAEI@Z; TraceTpmBufferValue(uchar,uchar *,uint)
0x18001fc71  lea     rcx, asc_18005DE7C; "\r\n"
0x18001fc78  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18001fc7d  mov     r8d, dword ptr [rbp+arg_0]; unsigned int
0x18001fc81  mov     rdx, r15; unsigned __int8 *
0x18001fc84  mov     rcx, r14; this
0x18001fc87  call    ?Set@TPMW8_COMMAND@tpm12class@@QEAAJPEBEI@Z; tpm12class::TPMW8_COMMAND::Set(uchar const *,uint)
0x18001fc8c  mov     ebx, eax
0x18001fc8e  and     eax, 0FFFF0000h
0x18001fc93  cmp     eax, 80280000h
0x18001fc98  jnz     short loc_18001FCCB
0x18001fc9a  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18001fc9f  test    al, al
0x18001fca1  jz      short loc_18001FCBE
0x18001fca3  lea     rdx, aRsp; "RSP."
0x18001fcaa  mov     rcx, r14; this
0x18001fcad  call    ?DecodeRsp@TPMW8_COMMAND@tpm12class@@UEAAJPEAG@Z; tpm12class::TPMW8_COMMAND::DecodeRsp(ushort *)
0x18001fcb2  lea     rcx, asc_18005DE7C; "\r\n"
0x18001fcb9  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18001fcbe  test    ebx, ebx
0x18001fcc0  jns     loc_18001FDB1
0x18001fcc6  jmp     loc_18001FD6B
0x18001fccb  test    ebx, ebx
0x18001fccd  jnz     short loc_18001FCC0
0x18001fccf  call    ?TraceEnabled@@YAEXZ; TraceEnabled(void)
0x18001fcd4  test    al, al
0x18001fcd6  jz      short loc_18001FD3A
0x18001fcd8  mov     rax, [r14]
0x18001fcdb  lea     rdx, aRsp; "RSP."
0x18001fce2  mov     rcx, r14
0x18001fce5  mov     rax, [rax+48h]
0x18001fce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcee  lea     rcx, asc_18005DE7C; "\r\n"
0x18001fcf5  call    ?TraceDirect@@YAJPEAG@Z; TraceDirect(ushort *)
0x18001fcfa  mov     rcx, [r14+0A8h]; this
0x18001fd01  test    rcx, rcx
0x18001fd04  jz      short loc_18001FD3A
0x18001fd06  lea     rdx, aAuth1; "AUTH[1]."
0x18001fd0d  call    ?Decode@TPMW8_SESSION@tpm12class@@QEAAJPEAG@Z; tpm12class::TPMW8_SESSION::Decode(ushort *)
0x18001fd12  mov     rcx, [rdi]; this
0x18001fd15  test    rcx, rcx
0x18001fd18  jz      short loc_18001FD3A
0x18001fd1a  lea     rdx, aAuth2; "AUTH[2]."
0x18001fd21  call    ?Decode@TPMW8_SESSION@tpm12class@@QEAAJPEAG@Z; tpm12class::TPMW8_SESSION::Decode(ushort *)
0x18001fd26  mov     rcx, [rsi]; this
0x18001fd29  test    rcx, rcx
0x18001fd2c  jz      short loc_18001FD3A
0x18001fd2e  lea     rdx, aAuth3; "AUTH[3]."
0x18001fd35  call    ?Decode@TPMW8_SESSION@tpm12class@@QEAAJPEAG@Z; tpm12class::TPMW8_SESSION::Decode(ushort *)
0x18001fd3a  mov     rcx, [r14+0A8h]; this
0x18001fd41  test    rcx, rcx
0x18001fd44  jz      short loc_18001FDB1
0x18001fd46  call    ?Refresh@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Refresh(void)
0x18001fd4b  mov     rcx, [rdi]; this
0x18001fd4e  test    rcx, rcx
0x18001fd51  jz      short loc_18001FDB1
0x18001fd53  call    ?Refresh@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Refresh(void)
0x18001fd58  mov     rcx, [rsi]; this
0x18001fd5b  test    rcx, rcx
0x18001fd5e  jz      short loc_18001FDB1
0x18001fd60  call    ?Refresh@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Refresh(void)
0x18001fd65  jmp     short loc_18001FDB1
0x18001fd67  mov     r13d, dword ptr [rbp+Size]
0x18001fd6b  mov     rcx, [r14+0A8h]; this
0x18001fd72  test    rcx, rcx
0x18001fd75  jz      short loc_18001FD85
0x18001fd77  test    byte ptr [rcx+2FCh], 1
0x18001fd7e  jnz     short loc_18001FD85
0x18001fd80  call    ?Release@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Release(void)
0x18001fd85  mov     rcx, [rdi]; this
0x18001fd88  test    rcx, rcx
0x18001fd8b  jz      short loc_18001FD9B
0x18001fd8d  test    byte ptr [rcx+2FCh], 1
0x18001fd94  jnz     short loc_18001FD9B
0x18001fd96  call    ?Release@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Release(void)
0x18001fd9b  mov     rcx, [rsi]; this
0x18001fd9e  test    rcx, rcx
0x18001fda1  jz      short loc_18001FDB1
0x18001fda3  test    byte ptr [rcx+2FCh], 1
0x18001fdaa  jnz     short loc_18001FDB1
0x18001fdac  call    ?Release@TPMW8_SESSION@tpm12class@@QEAAJXZ; tpm12class::TPMW8_SESSION::Release(void)
0x18001fdb1  test    r15, r15
0x18001fdb4  jz      short loc_18001FDD5
0x18001fdb6  mov     eax, dword ptr [rbp+arg_0]
0x18001fdb9  mov     rdx, r15
0x18001fdbc  test    rax, rax
0x18001fdbf  jz      short loc_18001FDCD
0x18001fdc1  mov     byte ptr [rdx], 0
0x18001fdc4  inc     rdx
0x18001fdc7  sub     rax, 1
0x18001fdcb  jnz     short loc_18001FDC1
0x18001fdcd  mov     rcx, r15; Block
0x18001fdd0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fdd5  mov     dword ptr [rbp+arg_0], 0
0x18001fddc  test    r12, r12
0x18001fddf  jz      short loc_18001FE00
0x18001fde1  mov     edx, r13d
0x18001fde4  mov     rax, r12
0x18001fde7  test    r13d, r13d
0x18001fdea  jz      short loc_18001FDF8
0x18001fdec  mov     byte ptr [rax], 0
0x18001fdef  inc     rax
0x18001fdf2  sub     rdx, 1
0x18001fdf6  jnz     short loc_18001FDEC
0x18001fdf8  mov     rcx, r12; Block
0x18001fdfb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001fe00  mov     eax, ebx
0x18001fe02  mov     rbx, [rsp+30h+arg_18]
0x18001fe0a  add     rsp, 30h
0x18001fe0e  pop     r15
0x18001fe10  pop     r14
0x18001fe12  pop     r13
0x18001fe14  pop     r12
0x18001fe16  pop     rdi
0x18001fe17  pop     rsi
0x18001fe18  pop     rbp
0x18001fe19  retn
```
