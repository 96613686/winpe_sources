# Root::DeSerialize(void)

- ea: `0x18000c934`
- end: `0x18000ce82`
- name: `?DeSerialize@Root@@QEAA_NXZ`
- size: `1358`
- prototype: `char __fastcall(Node *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180008c90`

## callees

- `0x18000aaf0`
- `0x18000c26c`
- `0x18000c588`
- `0x18000c6f0`
- `0x18000c8a8`
- `0x18000c934`
- `0x180030568`
- `0x180030d84`
- `0x180031e08`
- `0x180032654`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000cd0e`
- `KERNEL32!HeapFree` at `0x18000cd45`
- `KERNEL32!HeapFree` at `0x18000cd0e`
- `KERNEL32!HeapFree` at `0x18000cd45`
- `KERNEL32!GetProcessHeap` at `0x18000ccf9`
- `KERNEL32!GetProcessHeap` at `0x18000cd30`
- `KERNEL32!GetProcessHeap` at `0x18000ccf9`
- `KERNEL32!GetProcessHeap` at `0x18000cd30`
- `ucrtbase_clr0400!wcstol` at `0x18000caf8`
- `ucrtbase_clr0400!wcstol` at `0x18000caf8`

## pseudocode

```c
char __fastcall Root::DeSerialize(Node *this)
{
  char v2; // bl
  char v3; // di
  bool v4; // al
  int v5; // edi
  int v6; // ebx
  bool v7; // si
  __int64 v8; // rbx
  __int64 v9; // r8
  unsigned int i; // esi
  __int64 v11; // rbx
  char v12; // bl
  Configuration *appended; // rax
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v16; // rbx
  HANDLE v17; // rax
  __int64 v19; // rbx
  _QWORD *v20; // rbx
  __int64 v21; // r9
  __int64 MatchingConfiguration; // rax
  int v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+38h] [rbp-C8h]
  int v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh]
  int v28; // [rsp+48h] [rbp-B8h]
  void *v29; // [rsp+50h] [rbp-B0h]
  wchar_t *EndPtr; // [rsp+58h] [rbp-A8h] BYREF
  struct IRegWrapper::Key *v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+68h] [rbp-98h]
  void (__fastcall ***v33)(_QWORD, __int64); // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+80h] [rbp-80h] BYREF
  int v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+8Ch] [rbp-74h]
  LPVOID lpMem; // [rsp+98h] [rbp-68h]
  __int16 v39; // [rsp+A0h] [rbp-60h] BYREF
  int v40; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+C4h] [rbp-3Ch]
  wchar_t *String; // [rsp+D0h] [rbp-30h]
  __int16 v43; // [rsp+D8h] [rbp-28h] BYREF

  v24 = 0;
  v25 = 0;
  v26 = 2;
  v27 = 2;
  v28 = 16;
  v29 = (void *)&SString::s_EmptyBuffer;
  Node::GetParentRegKeyAndPath(this, (struct IRegWrapper::Key **)&EndPtr, (struct SString *)&v26);
  SString::ConvertToUnicode((SString *)&v26);
  v2 = (*(__int64 (__fastcall **)(wchar_t *, void *, __int64 *))(*(_QWORD *)EndPtr + 8LL))(EndPtr, v29, &v24);
  if ( (v28 & 8) != 0 )
    operator delete(v29);
  if ( v2 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, const wchar_t *, Node *))(*(_QWORD *)v24 + 48LL))(
            v24,
            L"Status",
            this + 2) )
      LODWORD(this[2].lpVtbl) = 3;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, const wchar_t *, Node *))(*(_QWORD *)v24 + 48LL))(
            v24,
            L"Priority",
            this + 5) )
      LODWORD(this[5].lpVtbl) = 3;
    if ( (*(unsigned __int8 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v24 + 48LL))(
           v24,
           L"KeepPriority",
           &v35) )
    {
      v4 = v35 != 0;
    }
    else
    {
      v4 = 0;
    }
    BYTE4(this[5].lpVtbl) = v4;
    v33 = 0;
    v34 = 0;
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 88LL))(v24, &v33);
    v41 = 512;
    String = (wchar_t *)&v43;
    v40 = 2;
    v43 = 0;
    v5 = 0;
    while ( (*(unsigned __int8 (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, __int64), int *))(*(_QWORD *)v24 + 96LL))(
              v24,
              v33,
              &v40) )
    {
      EndPtr = 0;
      SString::ConvertToUnicode((SString *)&v40);
      v6 = wcstol(String, &EndPtr, 10);
      if ( v6 )
        goto LABEL_19;
      v26 = 4;
      v27 = 4;
      v29 = L"0";
      v28 = 276;
      v7 = (unsigned int)SString::Equals((SString *)&v40, (const struct SString *)&v26) == 0;
      if ( (v28 & 8) != 0 )
        operator delete(v29);
      if ( !v7 )
      {
LABEL_19:
        if ( v6 > v5 )
          v5 = v6;
      }
      else if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v24 + 160LL))(v24) )
      {
        v8 = v24;
        SString::ConvertToUnicode((SString *)&v40);
        LOBYTE(v9) = 1;
        (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v8 + 24LL))(v8, String, v9);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 88LL))(v24, &v33);
      }
    }
    EndPtr = (wchar_t *)&v36;
    v37 = 32;
    lpMem = &v39;
    v36 = 2;
    v39 = 0;
    v31 = 0;
    v32 = 0;
    for ( i = 0; (int)i <= v5; ++i )
    {
      v11 = v24;
      SString::Printf((SString *)&v36, L"%d", i);
      SString::ConvertToUnicode((SString *)&v36);
      v12 = (*(__int64 (__fastcall **)(__int64, LPVOID, struct IRegWrapper::Key **))(*(_QWORD *)v11 + 8LL))(
              v11,
              lpMem,
              &v31);
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v24 + 160LL))(v24) )
      {
        if ( v12 )
        {
          appended = (Configuration *)ArrayOfPointers<Configuration>::CreateAndAppendNode(
                                        (SBuffer *)&this[6],
                                        (__int64)this,
                                        0);
          Configuration::DeSerialize(appended, v31);
        }
      }
      else
      {
        if ( !v12 )
        {
          v19 = v24;
          SString::Printf((SString *)&v36, L"%d", i);
          SString::ConvertToUnicode((SString *)&v36);
          (*(void (__fastcall **)(__int64, LPVOID, struct IRegWrapper::Key **))(*(_QWORD *)v19 + 16LL))(
            v19,
            lpMem,
            &v31);
        }
        v20 = ArrayOfPointers<Configuration>::CreateAndAppendNode((SBuffer *)&this[6], (__int64)this, 0);
        Configuration::DeSerialize((Configuration *)v20, v31);
        if ( *((_DWORD *)v20 + 4) )
        {
          while ( 1 )
          {
            if ( !*((_BYTE *)v20 + 640) || v20 == (_QWORD *)-616LL )
            {
              v21 = 0;
            }
            else
            {
              SString::ConvertToUnicode((SString *)(v20 + 77));
              v21 = v20[79];
            }
            LOBYTE(v23) = 0;
            MatchingConfiguration = Root::FindMatchingConfiguration(this, *((unsigned int *)v20 + 6), v20[71], v21, v23);
            if ( v20 == (_QWORD *)MatchingConfiguration )
              break;
            Node::SetStatus(MatchingConfiguration, 0);
          }
        }
      }
    }
    v3 = 1;
    if ( v32 )
    {
      if ( v31 )
        (**(void (__fastcall ***)(struct IRegWrapper::Key *, __int64))v31)(v31, 1);
      v32 = 0;
    }
    EndPtr = (wchar_t *)&v36;
    if ( (v37 & 0x800000000LL) != 0 )
    {
      v14 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v14);
      }
    }
    if ( (v41 & 0x800000000LL) != 0 )
    {
      v16 = String;
      if ( String )
      {
        v17 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v17 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v17;
        }
        HeapFree(v17, 0, v16);
      }
    }
    if ( v34 )
    {
      if ( v33 )
        (**v33)(v33, 1);
      v34 = 0;
    }
  }
  else
  {
    v3 = 0;
  }
  if ( v25 )
  {
    if ( v24 )
      (**(void (__fastcall ***)(__int64, __int64))v24)(v24, 1);
    v25 = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18000c934  mov     [rsp-8+arg_8], rbx
0x18000c939  mov     [rsp-8+arg_10], rsi
0x18000c93e  push    rbp
0x18000c93f  push    rdi
0x18000c940  push    r12
0x18000c942  push    r14
0x18000c944  push    r15
0x18000c946  lea     rbp, [rsp-1F0h]
0x18000c94e  sub     rsp, 2F0h
0x18000c955  mov     rax, cs:__security_cookie
0x18000c95c  xor     rax, rsp
0x18000c95f  mov     [rbp+210h+var_30], rax
0x18000c966  mov     r14, rcx
0x18000c969  xor     r12d, r12d
0x18000c96c  mov     [rsp+310h+var_2E0], r12
0x18000c971  mov     [rsp+310h+var_2D8], r12d
0x18000c976  lea     esi, [r12+2]
0x18000c97b  mov     [rsp+310h+var_2D0], esi
0x18000c97f  mov     [rsp+310h+var_2CC], esi
0x18000c983  mov     [rsp+310h+var_2C8], 10h
0x18000c98b  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18000c992  mov     [rsp+310h+var_2C0], rax
0x18000c997  lea     r8, [rsp+310h+var_2D0]; struct SString *
0x18000c99c  lea     rdx, [rsp+310h+EndPtr]; struct IRegWrapper::Key **
0x18000c9a1  call    ?GetParentRegKeyAndPath@Node@@QEAAXPEAPEAVKey@IRegWrapper@@PEAVSString@@@Z; Node::GetParentRegKeyAndPath(IRegWrapper::Key * *,SString *)
0x18000c9a6  lea     rcx, [rsp+310h+var_2D0]; this
0x18000c9ab  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000c9b0  mov     rcx, [rsp+310h+EndPtr]
0x18000c9b5  mov     rax, [rcx]
0x18000c9b8  lea     r8, [rsp+310h+var_2E0]
0x18000c9bd  mov     rdx, [rsp+310h+var_2C0]
0x18000c9c2  mov     rax, [rax+8]
0x18000c9c6  call    cs:__guard_dispatch_icall_fptr
0x18000c9cc  mov     bl, al
0x18000c9ce  test    byte ptr [rsp+310h+var_2C8], 8
0x18000c9d3  jz      short loc_18000C9DF
0x18000c9d5  mov     rcx, [rsp+310h+var_2C0]; lpMem
0x18000c9da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c9df  test    bl, bl
0x18000c9e1  jnz     short loc_18000C9EB
0x18000c9e3  mov     dil, r12b
0x18000c9e6  jmp     loc_18000CD73
0x18000c9eb  mov     rcx, [rsp+310h+var_2E0]
0x18000c9f0  mov     rax, [rcx]
0x18000c9f3  lea     r8, [r14+10h]
0x18000c9f7  lea     rdx, aStatus_0; "Status"
0x18000c9fe  mov     rax, [rax+30h]
0x18000ca02  call    cs:__guard_dispatch_icall_fptr
0x18000ca08  mov     edi, 3
0x18000ca0d  test    al, al
0x18000ca0f  jnz     short loc_18000CA15
0x18000ca11  mov     [r14+10h], edi
0x18000ca15  mov     rcx, [rsp+310h+var_2E0]
0x18000ca1a  mov     rax, [rcx]
0x18000ca1d  lea     r8, [r14+28h]
0x18000ca21  lea     rdx, aPriority; "Priority"
0x18000ca28  mov     rax, [rax+30h]
0x18000ca2c  call    cs:__guard_dispatch_icall_fptr
0x18000ca32  test    al, al
0x18000ca34  jnz     short loc_18000CA3A
0x18000ca36  mov     [r14+28h], edi
0x18000ca3a  mov     rcx, [rsp+310h+var_2E0]
0x18000ca3f  mov     rax, [rcx]
0x18000ca42  lea     r8, [rbp+210h+var_290]
0x18000ca46  lea     rdx, aKeeppriority; "KeepPriority"
0x18000ca4d  mov     rax, [rax+30h]
0x18000ca51  call    cs:__guard_dispatch_icall_fptr
0x18000ca57  test    al, al
0x18000ca59  jz      short loc_18000CA64
0x18000ca5b  cmp     [rbp+210h+var_290], r12d
0x18000ca5f  setnz   al
0x18000ca62  jmp     short loc_18000CA67
0x18000ca64  mov     al, r12b
0x18000ca67  mov     [r14+2Ch], al
0x18000ca6b  mov     [rsp+310h+var_2A0], r12
0x18000ca70  mov     [rsp+310h+var_298], r12d
0x18000ca75  mov     rcx, [rsp+310h+var_2E0]
0x18000ca7a  mov     rax, [rcx]
0x18000ca7d  lea     rdx, [rsp+310h+var_2A0]
0x18000ca82  mov     rax, [rax+58h]
0x18000ca86  call    cs:__guard_dispatch_icall_fptr
0x18000ca8c  mov     [rbp+210h+var_250], r12
0x18000ca90  mov     [rbp+210h+var_250+4], 200h
0x18000ca98  mov     [rbp+210h+String], r12
0x18000ca9c  lea     rax, [rbp+210h+var_238]
0x18000caa0  mov     [rbp+210h+String], rax
0x18000caa4  mov     dword ptr [rbp+210h+var_250], esi
0x18000caa7  mov     rax, [rbp+210h+String]
0x18000caab  mov     [rax], r12w
0x18000caaf  mov     edi, r12d
0x18000cab2  mov     rcx, [rsp+310h+var_2E0]
0x18000cab7  mov     rax, [rcx]
0x18000caba  lea     r8, [rbp+210h+var_250]
0x18000cabe  mov     rdx, [rsp+310h+var_2A0]
0x18000cac3  mov     rax, [rax+60h]
0x18000cac7  call    cs:__guard_dispatch_icall_fptr
0x18000cacd  test    al, al
0x18000cacf  jz      loc_18000CBF2
0x18000cad5  mov     r15d, 4
0x18000cadb  mov     [rsp+310h+EndPtr], r12
0x18000cae0  lea     rcx, [rbp+210h+var_250]; this
0x18000cae4  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000cae9  mov     r8d, 0Ah; Radix
0x18000caef  lea     rdx, [rsp+310h+EndPtr]; EndPtr
0x18000caf4  mov     rcx, [rbp+210h+String]; String
0x18000caf8  call    cs:__imp_wcstol
0x18000cafe  mov     ebx, eax
0x18000cb00  test    eax, eax
0x18000cb02  jnz     loc_18000CBC5
0x18000cb08  mov     [rsp+310h+var_2D0], r15d
0x18000cb0d  mov     [rsp+310h+var_2CC], r15d
0x18000cb12  mov     [rsp+310h+var_2C8], 10h
0x18000cb1a  lea     rax, a0; "0"
0x18000cb21  mov     [rsp+310h+var_2C0], rax
0x18000cb26  mov     ecx, [rsp+310h+var_2C8]
0x18000cb2a  and     ecx, 0FFFFFFF8h
0x18000cb2d  mov     [rsp+310h+var_2C8], ecx
0x18000cb31  mov     eax, ecx
0x18000cb33  or      eax, r15d
0x18000cb36  mov     [rsp+310h+var_2C8], eax
0x18000cb3a  or      ecx, 104h
0x18000cb40  mov     [rsp+310h+var_2C8], ecx
0x18000cb44  lea     rdx, [rsp+310h+var_2D0]; struct SString *
0x18000cb49  lea     rcx, [rbp+210h+var_250]; this
0x18000cb4d  call    ?Equals@SString@@QEBAHAEBV1@@Z; SString::Equals(SString const &)
0x18000cb52  test    eax, eax
0x18000cb54  setz    sil
0x18000cb58  test    byte ptr [rsp+310h+var_2C8], 8
0x18000cb5d  jz      short loc_18000CB69
0x18000cb5f  mov     rcx, [rsp+310h+var_2C0]; lpMem
0x18000cb64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cb69  test    sil, sil
0x18000cb6c  jz      short loc_18000CBC5
0x18000cb6e  mov     rcx, [rsp+310h+var_2E0]
0x18000cb73  mov     rax, [rcx]
0x18000cb76  mov     rax, [rax+0A0h]
0x18000cb7d  call    cs:__guard_dispatch_icall_fptr
0x18000cb83  test    al, al
0x18000cb85  jnz     short loc_18000CBCA
0x18000cb87  mov     rbx, [rsp+310h+var_2E0]
0x18000cb8c  lea     rcx, [rbp+210h+var_250]; this
0x18000cb90  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000cb95  mov     rax, [rbx]
0x18000cb98  mov     r8b, 1
0x18000cb9b  mov     rdx, [rbp+210h+String]
0x18000cb9f  mov     rcx, rbx
0x18000cba2  mov     rax, [rax+18h]
0x18000cba6  call    cs:__guard_dispatch_icall_fptr
0x18000cbac  mov     rcx, [rsp+310h+var_2E0]
0x18000cbb1  mov     rax, [rcx]
0x18000cbb4  lea     rdx, [rsp+310h+var_2A0]
0x18000cbb9  mov     rax, [rax+58h]
0x18000cbbd  call    cs:__guard_dispatch_icall_fptr
0x18000cbc3  jmp     short loc_18000CBCA
0x18000cbc5  cmp     ebx, edi
0x18000cbc7  cmovg   edi, ebx
0x18000cbca  mov     rcx, [rsp+310h+var_2E0]
0x18000cbcf  mov     rax, [rcx]
0x18000cbd2  lea     r8, [rbp+210h+var_250]
0x18000cbd6  mov     rdx, [rsp+310h+var_2A0]
0x18000cbdb  mov     rax, [rax+60h]
0x18000cbdf  call    cs:__guard_dispatch_icall_fptr
0x18000cbe5  test    al, al
0x18000cbe7  jnz     loc_18000CADB
0x18000cbed  mov     esi, 2
0x18000cbf2  lea     rax, [rbp+210h+var_288]
0x18000cbf6  mov     [rsp+310h+EndPtr], rax
0x18000cbfb  mov     [rbp+210h+var_288], r12
0x18000cbff  mov     [rbp+210h+var_288+4], 20h ; ' '
0x18000cc07  mov     [rbp+210h+lpMem], r12
0x18000cc0b  lea     rax, [rbp+210h+var_270]
0x18000cc0f  mov     [rbp+210h+lpMem], rax
0x18000cc13  mov     dword ptr [rbp+210h+var_288], esi
0x18000cc16  mov     [rbp+210h+var_270], r12w
0x18000cc1b  mov     [rsp+310h+var_2B0], r12
0x18000cc20  mov     [rsp+310h+var_2A8], r12d
0x18000cc25  mov     esi, r12d
0x18000cc28  test    edi, edi
0x18000cc2a  js      short loc_18000CCAB
0x18000cc2c  mov     rbx, [rsp+310h+var_2E0]
0x18000cc31  mov     r8d, esi
0x18000cc34  lea     rdx, aD; "%d"
0x18000cc3b  lea     rcx, [rbp+210h+var_288]; this
0x18000cc3f  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18000cc44  lea     rcx, [rbp+210h+var_288]; this
0x18000cc48  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000cc4d  mov     rax, [rbx]
0x18000cc50  lea     r8, [rsp+310h+var_2B0]
0x18000cc55  mov     rdx, [rbp+210h+lpMem]
0x18000cc59  mov     rcx, rbx
0x18000cc5c  mov     rax, [rax+8]
0x18000cc60  call    cs:__guard_dispatch_icall_fptr
0x18000cc66  mov     bl, al
0x18000cc68  mov     rcx, [rsp+310h+var_2E0]
0x18000cc6d  mov     rdx, [rcx]
0x18000cc70  mov     rax, [rdx+0A0h]
0x18000cc77  call    cs:__guard_dispatch_icall_fptr
0x18000cc7d  test    al, al
0x18000cc7f  jz      loc_18000CDC8
0x18000cc85  test    bl, bl
0x18000cc87  jz      short loc_18000CCA5
0x18000cc89  lea     rcx, [r14+30h]; this
0x18000cc8d  xor     r8d, r8d
0x18000cc90  mov     rdx, r14
0x18000cc93  call    ?CreateAndAppendNode@?$ArrayOfPointers@VConfiguration@@@@QEAAPEAVConfiguration@@PEAVNode@@PEAI@Z; ArrayOfPointers<Configuration>::CreateAndAppendNode(Node *,uint *)
0x18000cc98  mov     rdx, [rsp+310h+var_2B0]; struct IRegWrapper::Key *
0x18000cc9d  mov     rcx, rax; this
0x18000cca0  call    ?DeSerialize@Configuration@@QEAAXPEAVKey@IRegWrapper@@@Z; Configuration::DeSerialize(IRegWrapper::Key *)
0x18000cca5  inc     esi
0x18000cca7  cmp     esi, edi
0x18000cca9  jle     short loc_18000CC2C
0x18000ccab  mov     dil, 1
0x18000ccae  cmp     [rsp+310h+var_2A8], r12d
0x18000ccb3  jz      short loc_18000CCD5
0x18000ccb5  mov     rcx, [rsp+310h+var_2B0]
0x18000ccba  test    rcx, rcx
0x18000ccbd  jz      short loc_18000CCD0
0x18000ccbf  mov     rax, [rcx]
0x18000ccc2  mov     edx, 1
0x18000ccc7  mov     rax, [rax]
0x18000ccca  call    cs:__guard_dispatch_icall_fptr
0x18000ccd0  mov     [rsp+310h+var_2A8], r12d
0x18000ccd5  lea     rax, [rbp+210h+var_288]
0x18000ccd9  mov     [rsp+310h+EndPtr], rax
0x18000ccde  test    [rbp+210h+var_280], 8
0x18000cce2  jz      short loc_18000CD15
0x18000cce4  mov     rbx, [rbp+210h+lpMem]
0x18000cce8  test    rbx, rbx
0x18000cceb  jz      short loc_18000CD15
0x18000cced  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000ccf4  test    rax, rax
0x18000ccf7  jnz     short loc_18000CD06
0x18000ccf9  call    cs:__imp_GetProcessHeap
0x18000ccff  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000cd06  mov     r8, rbx; lpMem
0x18000cd09  xor     edx, edx; dwFlags
0x18000cd0b  mov     rcx, rax; hHeap
0x18000cd0e  call    cs:__imp_HeapFree
0x18000cd14  nop
0x18000cd15  test    [rbp+210h+var_248], 8
0x18000cd19  jz      short loc_18000CD4C
0x18000cd1b  mov     rbx, [rbp+210h+String]
0x18000cd1f  test    rbx, rbx
0x18000cd22  jz      short loc_18000CD4C
0x18000cd24  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000cd2b  test    rax, rax
0x18000cd2e  jnz     short loc_18000CD3D
0x18000cd30  call    cs:__imp_GetProcessHeap
0x18000cd36  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18000cd3d  mov     r8, rbx; lpMem
0x18000cd40  xor     edx, edx; dwFlags
0x18000cd42  mov     rcx, rax; hHeap
0x18000cd45  call    cs:__imp_HeapFree
0x18000cd4b  nop
0x18000cd4c  cmp     [rsp+310h+var_298], r12d
0x18000cd51  jz      short loc_18000CD73
0x18000cd53  mov     rcx, [rsp+310h+var_2A0]
0x18000cd58  test    rcx, rcx
0x18000cd5b  jz      short loc_18000CD6E
0x18000cd5d  mov     rax, [rcx]
0x18000cd60  mov     edx, 1
0x18000cd65  mov     rax, [rax]
0x18000cd68  call    cs:__guard_dispatch_icall_fptr
0x18000cd6e  mov     [rsp+310h+var_298], r12d
0x18000cd73  cmp     [rsp+310h+var_2D8], r12d
0x18000cd78  jz      short loc_18000CD9A
0x18000cd7a  mov     rcx, [rsp+310h+var_2E0]
0x18000cd7f  test    rcx, rcx
0x18000cd82  jz      short loc_18000CD95
0x18000cd84  mov     r8, [rcx]
0x18000cd87  mov     edx, 1
0x18000cd8c  mov     rax, [r8]
0x18000cd8f  call    cs:__guard_dispatch_icall_fptr
0x18000cd95  mov     [rsp+310h+var_2D8], r12d
0x18000cd9a  mov     al, dil
0x18000cd9d  mov     rcx, [rbp+210h+var_30]
0x18000cda4  xor     rcx, rsp; StackCookie
0x18000cda7  call    __security_check_cookie
0x18000cdac  lea     r11, [rsp+310h+var_20]
0x18000cdb4  mov     rbx, [r11+38h]
0x18000cdb8  mov     rsi, [r11+40h]
0x18000cdbc  mov     rsp, r11
0x18000cdbf  pop     r15
0x18000cdc1  pop     r14
0x18000cdc3  pop     r12
0x18000cdc5  pop     rdi
0x18000cdc6  pop     rbp
0x18000cdc7  retn
0x18000cdc8  test    bl, bl
0x18000cdca  jnz     short loc_18000CE06
0x18000cdcc  mov     rbx, [rsp+310h+var_2E0]
0x18000cdd1  mov     r8d, esi
0x18000cdd4  lea     rdx, aD; "%d"
0x18000cddb  lea     rcx, [rbp+210h+var_288]; this
0x18000cddf  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x18000cde4  lea     rcx, [rbp+210h+var_288]; this
0x18000cde8  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18000cded  mov     rax, [rbx]
0x18000cdf0  lea     r8, [rsp+310h+var_2B0]
0x18000cdf5  mov     rdx, [rbp+210h+lpMem]
  ... truncated ...
```
