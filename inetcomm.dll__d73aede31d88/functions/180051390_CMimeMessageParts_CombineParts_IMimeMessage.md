# CMimeMessageParts::CombineParts(IMimeMessage * *)

- ea: `0x180051390`
- end: `0x1800517f7`
- name: `?CombineParts@CMimeMessageParts@@UEAAJPEAPEAUIMimeMessage@@@Z`
- size: `1127`
- prototype: `__int64 __fastcall(CMimeMessageParts *__hidden this, struct IMimeMessage **)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002098`
- `0x180002cf0`
- `0x180005748`
- `0x180021140`
- `0x18002e398`
- `0x180051390`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrStreamSeekSet` at `0x1800515c2`
- `MSOERT2!HrStreamSeekSet` at `0x180051623`
- `MSOERT2!HrStreamSeekSet` at `0x1800515c2`
- `MSOERT2!HrStreamSeekSet` at `0x180051623`
- `MSOERT2!HrCopyStream` at `0x1800515dc`
- `MSOERT2!HrCopyStream` at `0x1800515dc`
- `MSOERT2!HrGetStreamSize` at `0x180051605`
- `MSOERT2!HrGetStreamSize` at `0x180051605`
- `SHLWAPI!__imp_IStream_Reset` at `0x1800516ab`
- `SHLWAPI!__imp_IStream_Reset` at `0x1800516ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800517c8`
- `KERNEL32!LeaveCriticalSection` at `0x1800517c8`
- `KERNEL32!EnterCriticalSection` at `0x180051406`
- `KERNEL32!EnterCriticalSection` at `0x180051406`

## pseudocode

```c
__int64 __fastcall CMimeMessageParts::CombineParts(CMimeMessageParts *this, struct IMimeMessage **a2)
{
  struct IMimeMessage *v4; // rsi
  HRESULT StreamSize; // ebx
  int v7; // r12d
  unsigned int v8; // edx
  __int64 v9; // rcx
  IStream *v10; // r14
  unsigned int j; // r15d
  __int64 v12; // r13
  int v13; // ecx
  int v14; // edx
  int v15; // eax
  __int64 v16; // rdx
  struct CMessageTree *Instance; // rax
  struct IMimeMessage *v18; // r15
  __int64 v19; // rax
  unsigned int k; // r14d
  __int64 v21; // rcx
  _BYTE v22[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v23; // [rsp+38h] [rbp-51h] BYREF
  int v24; // [rsp+40h] [rbp-49h]
  int i; // [rsp+44h] [rbp-45h]
  __int64 v26; // [rsp+48h] [rbp-41h] BYREF
  struct CMessageTree *v27; // [rsp+50h] [rbp-39h] BYREF
  IStream *pstm; // [rsp+58h] [rbp-31h] BYREF
  struct IMimeMessage *v29; // [rsp+60h] [rbp-29h] BYREF
  struct IMimeMessage **v30; // [rsp+68h] [rbp-21h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+70h] [rbp-19h]
  __int128 v32; // [rsp+78h] [rbp-11h] BYREF
  __int64 v33; // [rsp+88h] [rbp-1h]
  __int128 v34; // [rsp+90h] [rbp+7h] BYREF

  v30 = a2;
  pstm = 0;
  v23 = 0;
  v29 = 0;
  v26 = 0;
  v33 = 0;
  v4 = 0;
  v34 = 0;
  v32 = 0;
  if ( !a2 )
    return 2147942487LL;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *a2 = 0;
  StreamSize = MimeOleCreateVirtualStream(&pstm);
  if ( StreamSize < 0 )
    goto LABEL_53;
  v7 = 0;
  v24 = 0;
  v8 = 0;
  for ( i = 0; v8 < *((_DWORD *)this + 3); *(_BYTE *)(*((_QWORD *)this + 3) + 16 * v9) = 0 )
    v9 = v8++;
  v10 = pstm;
  for ( j = 0; j < *((_DWORD *)this + 3); ++j )
  {
    v12 = *(_QWORD *)(*((_QWORD *)this + 3) + 16LL * j + 8);
    StreamSize = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v12 + 72LL))(v12, &v23, 1);
    if ( StreamSize < 0 )
      goto LABEL_53;
    StreamSize = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v12 + 128LL))(
                   v12,
                   -1,
                   &IID_IMimeBody,
                   &v26);
    if ( StreamSize < 0 )
      goto LABEL_53;
    StreamSize = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v26 + 248LL))(v26, &v34);
    if ( StreamSize < 0 )
      goto LABEL_53;
    LOWORD(v32) = 19;
    if ( (*(unsigned int (__fastcall **)(__int64, const CHAR *, const CHAR *))(*(_QWORD *)v26 + 176LL))(
           v26,
           "message",
           "partial")
      || (*(int (__fastcall **)(__int64, const char *, _QWORD, __int128 *))(*(_QWORD *)v26 + 88LL))(
           v26,
           "par:content-type:number",
           0,
           &v32) < 0 )
    {
      v14 = 0;
      v13 = 0;
      *(_BYTE *)(*((_QWORD *)this + 3) + 16LL * j) = 0;
      if ( v24 )
        *(_BYTE *)(*((_QWORD *)this + 3) + 16LL * j) = 1;
    }
    else
    {
      ++v24;
      v13 = 1;
      v14 = DWORD2(v32);
    }
    if ( *(_BYTE *)(*((_QWORD *)this + 3) + 16LL * j) )
    {
      v7 = ++i;
      continue;
    }
    if ( j )
    {
      v16 = DWORD2(v34);
    }
    else
    {
      if ( v13 && v14 == 1 )
      {
        StreamSize = MimeOleMergePartialHeaders(v23, v10);
        if ( StreamSize < 0 )
          goto LABEL_53;
        v15 = ((__int64 (__fastcall *)(IStream *, const char *, __int64, _QWORD))v10->lpVtbl->Write)(v10, "\r\n", 2, 0);
        goto LABEL_26;
      }
      v16 = 0;
    }
    v15 = HrStreamSeekSet(v23, v16);
LABEL_26:
    StreamSize = v15;
    if ( v15 < 0 )
      goto LABEL_53;
    StreamSize = HrCopyStream(v23, v10, 0);
    if ( StreamSize < 0 )
      goto LABEL_53;
    if ( j < *((_DWORD *)this + 3) - 1 )
    {
      LODWORD(v27) = 0;
      StreamSize = HrGetStreamSize(v10, &v27);
      if ( StreamSize < 0 )
        goto LABEL_53;
      if ( (unsigned int)v27 > 2 )
      {
        StreamSize = HrStreamSeekSet(v10, (unsigned int)((_DWORD)v27 - 2));
        if ( StreamSize < 0 )
          goto LABEL_53;
        StreamSize = ((__int64 (__fastcall *)(IStream *, _BYTE *, __int64))v10->lpVtbl->Read)(v10, v22, 2);
        if ( StreamSize < 0 )
          goto LABEL_53;
        if ( v22[0] != 13 && v22[1] != 10 )
        {
          StreamSize = ((__int64 (__fastcall *)(IStream *, const char *, __int64))v10->lpVtbl->Write)(v10, "\r\n", 2);
          if ( StreamSize < 0 )
            goto LABEL_53;
        }
      }
    }
    OE_SafeReleaseAndNullPtr<IStream>(&v23);
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v26);
    v7 = i;
  }
  StreamSize = IStream_Reset(v10);
  if ( StreamSize >= 0 )
  {
    Instance = CMessageTree::CreateInstance(0);
    v27 = Instance;
    if ( Instance )
    {
      v18 = (struct CMessageTree *)((char *)Instance + 32);
      StreamSize = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Instance + 4) + 64LL))((__int64)Instance + 32);
      if ( StreamSize >= 0 )
      {
        v19 = *(_QWORD *)v18;
        v4 = v18;
        v29 = v18;
        (*(void (__fastcall **)(struct IMimeMessage *))(v19 + 8))(v18);
      }
    }
    else
    {
      StreamSize = -2147024882;
    }
    OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v27);
    if ( StreamSize >= 0 )
    {
      StreamSize = (*(__int64 (__fastcall **)(struct IMimeMessage *))(*(_QWORD *)v4 + 64LL))(v4);
      if ( StreamSize >= 0 )
      {
        StreamSize = (*(__int64 (__fastcall **)(struct IMimeMessage *, IStream *))(*(_QWORD *)v4 + 40LL))(v4, v10);
        if ( StreamSize >= 0 )
        {
          if ( v7 )
          {
            for ( k = 0; k < *((_DWORD *)this + 3); ++k )
            {
              v21 = *((_QWORD *)this + 3);
              if ( *(_BYTE *)(v21 + 16LL * k) )
              {
                StreamSize = (*(__int64 (__fastcall **)(struct IMimeMessage *, GUID *, _QWORD, _QWORD))(*(_QWORD *)v4 + 360LL))(
                               v4,
                               &IID_IMimeMessage,
                               *(_QWORD *)(v21 + 16LL * k + 8),
                               0);
                if ( StreamSize < 0 )
                  goto LABEL_53;
              }
            }
          }
          *v30 = v4;
          (*(void (__fastcall **)(struct IMimeMessage *))(*(_QWORD *)v4 + 8LL))(v4);
        }
      }
    }
  }
LABEL_53:
  OE_SafeReleaseAndNullPtr<IStream>(&pstm);
  OE_SafeReleaseAndNullPtr<IStream>(&v23);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v26);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v29);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)StreamSize;
}

```

## disassembly

```asm
0x180051390  mov     [rsp-8+arg_10], rbx
0x180051395  push    rbp
0x180051396  push    rsi
0x180051397  push    rdi
0x180051398  push    r12
0x18005139a  push    r13
0x18005139c  push    r14
0x18005139e  push    r15
0x1800513a0  lea     rbp, [rsp-27h]
0x1800513a5  sub     rsp, 0B0h
0x1800513ac  mov     rax, cs:__security_cookie
0x1800513b3  xor     rax, rsp
0x1800513b6  mov     [rbp+57h+var_40], rax
0x1800513ba  xor     ebx, ebx
0x1800513bc  mov     [rbp+57h+var_78], rdx
0x1800513c0  xor     eax, eax
0x1800513c2  mov     [rbp+57h+pstm], rbx
0x1800513c6  mov     [rbp+57h+var_A8], rbx
0x1800513ca  xorps   xmm0, xmm0
0x1800513cd  mov     [rbp+57h+var_80], rbx
0x1800513d1  xorps   xmm1, xmm1
0x1800513d4  mov     [rbp+57h+var_98], rbx
0x1800513d8  mov     r13, rdx
0x1800513db  mov     [rbp+57h+var_58], rax
0x1800513df  mov     rdi, rcx
0x1800513e2  mov     esi, ebx
0x1800513e4  movups  [rbp+57h+var_50], xmm0
0x1800513e8  movups  [rbp+57h+var_68], xmm1
0x1800513ec  test    rdx, rdx
0x1800513ef  jnz     short loc_1800513FB
0x1800513f1  mov     eax, 80070057h
0x1800513f6  jmp     loc_1800517D0
0x1800513fb  lea     rax, [rcx+20h]
0x1800513ff  mov     rcx, rax; lpCriticalSection
0x180051402  mov     [rbp+57h+lpCriticalSection], rax
0x180051406  call    cs:__imp_EnterCriticalSection
0x18005140c  lea     rcx, [rbp+57h+pstm]
0x180051410  mov     [r13+0], rbx
0x180051414  call    MimeOleCreateVirtualStream
0x180051419  xor     r13d, r13d
0x18005141c  mov     ebx, eax
0x18005141e  test    eax, eax
0x180051420  js      loc_1800517A0
0x180051426  mov     r12d, r13d
0x180051429  mov     [rbp+57h+var_A0], r13d
0x18005142d  mov     edx, r13d
0x180051430  mov     [rbp+57h+var_9C], r13d
0x180051434  cmp     [rdi+0Ch], r13d
0x180051438  jbe     short loc_18005144E
0x18005143a  mov     rax, [rdi+18h]
0x18005143e  mov     ecx, edx
0x180051440  inc     edx
0x180051442  add     rcx, rcx
0x180051445  mov     [rax+rcx*8], r13b
0x180051449  cmp     edx, [rdi+0Ch]
0x18005144c  jb      short loc_18005143A
0x18005144e  mov     r14, [rbp+57h+pstm]
0x180051452  mov     r15d, r13d
0x180051455  cmp     r15d, [rdi+0Ch]
0x180051459  jnb     loc_1800516A8
0x18005145f  mov     rax, [rdi+18h]
0x180051463  lea     rdx, [rbp+57h+var_A8]
0x180051467  mov     r12d, r15d
0x18005146a  mov     r8d, 1
0x180051470  add     r12, r12
0x180051473  mov     r13, [rax+r12*8+8]
0x180051478  mov     rcx, r13
0x18005147b  mov     rax, [r13+0]
0x18005147f  mov     rax, [rax+48h]
0x180051483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051488  mov     ebx, eax
0x18005148a  test    eax, eax
0x18005148c  js      loc_1800517A0
0x180051492  mov     rax, [r13+0]
0x180051496  lea     r9, [rbp+57h+var_98]
0x18005149a  lea     r8, IID_IMimeBody
0x1800514a1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800514a5  mov     rcx, r13
0x1800514a8  mov     rax, [rax+80h]
0x1800514af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514b4  xor     r13d, r13d
0x1800514b7  mov     ebx, eax
0x1800514b9  test    eax, eax
0x1800514bb  js      loc_1800517A0
0x1800514c1  mov     rcx, [rbp+57h+var_98]
0x1800514c5  lea     rdx, [rbp+57h+var_50]
0x1800514c9  mov     rax, [rcx]
0x1800514cc  mov     rax, [rax+0F8h]
0x1800514d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514d8  mov     ebx, eax
0x1800514da  test    eax, eax
0x1800514dc  js      loc_1800517A0
0x1800514e2  mov     rcx, [rbp+57h+var_98]
0x1800514e6  lea     eax, [r13+13h]
0x1800514ea  mov     word ptr [rbp+57h+var_68], ax
0x1800514ee  lea     r8, STR_SUB_PARTIAL; "partial"
0x1800514f5  lea     rdx, STR_CNT_MESSAGE; "message"
0x1800514fc  mov     rax, [rcx]
0x1800514ff  mov     rax, [rax+0B0h]
0x180051506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005150b  test    eax, eax
0x18005150d  jnz     short loc_18005153D
0x18005150f  mov     rcx, [rbp+57h+var_98]
0x180051513  lea     r9, [rbp+57h+var_68]
0x180051517  xor     r8d, r8d
0x18005151a  lea     rdx, STR_PAR_NUMBER; "par:content-type:number"
0x180051521  mov     rax, [rcx]
0x180051524  mov     rax, [rax+58h]
0x180051528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005152d  test    eax, eax
0x18005152f  js      short loc_18005153D
0x180051531  inc     [rbp+57h+var_A0]
0x180051534  lea     ecx, [r13+1]
0x180051538  mov     edx, dword ptr [rbp+57h+var_68+8]
0x18005153b  jmp     short loc_18005155A
0x18005153d  mov     edx, r13d
0x180051540  mov     rax, [rdi+18h]
0x180051544  mov     ecx, r13d
0x180051547  mov     [rax+r12*8], r13b
0x18005154b  cmp     [rbp+57h+var_A0], r13d
0x18005154f  jbe     short loc_18005155A
0x180051551  mov     rax, [rdi+18h]
0x180051555  mov     byte ptr [rax+r12*8], 1
0x18005155a  mov     rax, [rdi+18h]
0x18005155e  cmp     [rax+r12*8], r13b
0x180051562  jz      short loc_180051574
0x180051564  mov     r12d, [rbp+57h+var_9C]
0x180051568  inc     r12d
0x18005156b  mov     [rbp+57h+var_9C], r12d
0x18005156f  jmp     loc_1800516A0
0x180051574  test    r15d, r15d
0x180051577  jnz     short loc_1800515BB
0x180051579  test    ecx, ecx
0x18005157b  jz      short loc_1800515B7
0x18005157d  cmp     edx, 1
0x180051580  jnz     short loc_1800515B7
0x180051582  mov     rcx, [rbp+57h+var_A8]
0x180051586  mov     rdx, r14
0x180051589  call    MimeOleMergePartialHeaders
0x18005158e  mov     ebx, eax
0x180051590  test    eax, eax
0x180051592  js      loc_1800517A0
0x180051598  mov     rax, [r14]
0x18005159b  lea     r8d, [r15+2]
0x18005159f  xor     r9d, r9d
0x1800515a2  lea     rdx, c_szCRLF; "\r\n"
0x1800515a9  mov     rcx, r14
0x1800515ac  mov     rax, [rax+20h]
0x1800515b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800515b5  jmp     short loc_1800515C8
0x1800515b7  xor     edx, edx
0x1800515b9  jmp     short loc_1800515BE
0x1800515bb  mov     edx, dword ptr [rbp+57h+var_50+8]
0x1800515be  mov     rcx, [rbp+57h+var_A8]
0x1800515c2  call    cs:__imp_HrStreamSeekSet
0x1800515c8  mov     ebx, eax
0x1800515ca  test    eax, eax
0x1800515cc  js      loc_1800517A0
0x1800515d2  mov     rcx, [rbp+57h+var_A8]
0x1800515d6  xor     r8d, r8d
0x1800515d9  mov     rdx, r14
0x1800515dc  call    cs:__imp_HrCopyStream
0x1800515e2  mov     ebx, eax
0x1800515e4  test    eax, eax
0x1800515e6  js      loc_1800517A0
0x1800515ec  mov     eax, [rdi+0Ch]
0x1800515ef  dec     eax
0x1800515f1  cmp     r15d, eax
0x1800515f4  jnb     loc_18005168A
0x1800515fa  lea     rdx, [rbp+57h+var_90]
0x1800515fe  mov     dword ptr [rbp+57h+var_90], r13d
0x180051602  mov     rcx, r14
0x180051605  call    cs:__imp_HrGetStreamSize
0x18005160b  mov     ebx, eax
0x18005160d  test    eax, eax
0x18005160f  js      loc_1800517A0
0x180051615  mov     edx, dword ptr [rbp+57h+var_90]
0x180051618  cmp     edx, 2
0x18005161b  jbe     short loc_18005168A
0x18005161d  add     edx, 0FFFFFFFEh
0x180051620  mov     rcx, r14
0x180051623  call    cs:__imp_HrStreamSeekSet
0x180051629  mov     ebx, eax
0x18005162b  test    eax, eax
0x18005162d  js      loc_1800517A0
0x180051633  mov     rax, [r14]
0x180051636  lea     rdx, [rbp+57h+var_B0]
0x18005163a  xor     r9d, r9d
0x18005163d  mov     rcx, r14
0x180051640  mov     rax, [rax+18h]
0x180051644  lea     r8d, [r9+2]
0x180051648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005164d  mov     ebx, eax
0x18005164f  test    eax, eax
0x180051651  js      loc_1800517A0
0x180051657  cmp     [rbp+57h+var_B0], 0Dh
0x18005165b  jz      short loc_18005168A
0x18005165d  cmp     [rbp+57h+var_AF], 0Ah
0x180051661  jz      short loc_18005168A
0x180051663  mov     rax, [r14]
0x180051666  lea     rdx, c_szCRLF; "\r\n"
0x18005166d  xor     r9d, r9d
0x180051670  mov     rcx, r14
0x180051673  mov     rax, [rax+20h]
0x180051677  lea     r8d, [r9+2]
0x18005167b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051680  mov     ebx, eax
0x180051682  test    eax, eax
0x180051684  js      loc_1800517A0
0x18005168a  lea     rcx, [rbp+57h+var_A8]
0x18005168e  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x180051693  lea     rcx, [rbp+57h+var_98]
0x180051697  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18005169c  mov     r12d, [rbp+57h+var_9C]
0x1800516a0  inc     r15d
0x1800516a3  jmp     loc_180051455
0x1800516a8  mov     rcx, r14; pstm
0x1800516ab  call    cs:__imp_IStream_Reset
0x1800516b1  mov     ebx, eax
0x1800516b3  test    eax, eax
0x1800516b5  js      loc_1800517A0
0x1800516bb  xor     ecx, ecx; struct IUnknown *
0x1800516bd  call    ?CreateInstance@CMessageTree@@SAPEAV1@PEAUIUnknown@@@Z; CMessageTree::CreateInstance(IUnknown *)
0x1800516c2  mov     [rbp+57h+var_90], rax
0x1800516c6  test    rax, rax
0x1800516c9  jnz     short loc_1800516D2
0x1800516cb  mov     ebx, 8007000Eh
0x1800516d0  jmp     short loc_180051702
0x1800516d2  lea     r15, [rax+20h]
0x1800516d6  mov     rax, [rax+20h]
0x1800516da  mov     rcx, r15
0x1800516dd  mov     rax, [rax+40h]
0x1800516e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516e6  mov     ebx, eax
0x1800516e8  test    eax, eax
0x1800516ea  js      short loc_180051702
0x1800516ec  mov     rax, [r15]
0x1800516ef  mov     rcx, r15
0x1800516f2  mov     rsi, r15
0x1800516f5  mov     [rbp+57h+var_80], r15
0x1800516f9  mov     rax, [rax+8]
0x1800516fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051702  lea     rcx, [rbp+57h+var_90]
0x180051706  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18005170b  test    ebx, ebx
0x18005170d  js      loc_1800517A0
0x180051713  mov     rax, [rsi]
0x180051716  mov     rcx, rsi
0x180051719  mov     rax, [rax+40h]
0x18005171d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051722  mov     ebx, eax
0x180051724  test    eax, eax
0x180051726  js      short loc_1800517A0
0x180051728  mov     rax, [rsi]
0x18005172b  mov     rdx, r14
0x18005172e  mov     rcx, rsi
0x180051731  mov     rax, [rax+28h]
0x180051735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005173a  mov     ebx, eax
0x18005173c  test    eax, eax
0x18005173e  js      short loc_1800517A0
0x180051740  test    r12d, r12d
0x180051743  jz      short loc_18005178A
0x180051745  mov     r14d, r13d
0x180051748  cmp     r14d, [rdi+0Ch]
0x18005174c  jnb     short loc_18005178A
0x18005174e  mov     rcx, [rdi+18h]
0x180051752  mov     r8d, r14d
0x180051755  add     r8, r8
0x180051758  cmp     [rcx+r8*8], r13b
0x18005175c  jz      short loc_180051785
0x18005175e  mov     rax, [rsi]
0x180051761  lea     rdx, IID_IMimeMessage
0x180051768  mov     r8, [rcx+r8*8+8]
0x18005176d  xor     r9d, r9d
0x180051770  mov     rcx, rsi
0x180051773  mov     rax, [rax+168h]
0x18005177a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005177f  mov     ebx, eax
0x180051781  test    eax, eax
0x180051783  js      short loc_1800517A0
0x180051785  inc     r14d
0x180051788  jmp     short loc_180051748
0x18005178a  mov     rax, [rbp+57h+var_78]
0x18005178e  mov     rcx, rsi
0x180051791  mov     [rax], rsi
0x180051794  mov     rax, [rsi]
0x180051797  mov     rax, [rax+8]
0x18005179b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517a0  lea     rcx, [rbp+57h+pstm]
0x1800517a4  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x1800517a9  lea     rcx, [rbp+57h+var_A8]
0x1800517ad  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x1800517b2  lea     rcx, [rbp+57h+var_98]
0x1800517b6  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800517bb  lea     rcx, [rbp+57h+var_80]
0x1800517bf  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800517c4  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800517c8  call    cs:__imp_LeaveCriticalSection
0x1800517ce  mov     eax, ebx
  ... truncated ...
```
