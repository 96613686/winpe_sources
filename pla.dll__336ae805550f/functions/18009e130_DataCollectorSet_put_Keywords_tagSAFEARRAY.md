# DataCollectorSet::put_Keywords(tagSAFEARRAY *)

- ea: `0x18009e130`
- end: `0x18009e652`
- name: `?put_Keywords@DataCollectorSet@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `1314`
- prototype: `__int64 __fastcall(DataCollectorSet *this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180042ec4`
- `0x18006e574`
- `0x18009e130`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e611`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e611`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e20d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e20d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009e57c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009e591`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009e57c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009e591`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18009e38c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18009e38c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18009e620`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18009e620`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18009e4ef`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18009e4ef`

## pseudocode

```c
__int64 __fastcall DataCollectorSet::put_Keywords(DataCollectorSet *this, struct tagSAFEARRAY *a2)
{
  int v2; // eax
  int v4; // edx
  unsigned __int64 v6; // rcx
  HRESULT v7; // ebx
  __int64 v8; // rax
  int *v9; // r9
  int *v10; // rax
  __int64 v11; // rax
  HRESULT v12; // eax
  __int64 v13; // rax
  ULONG i; // ebx
  int v15; // eax
  __int64 v16; // rax
  HRESULT v17; // eax
  __int64 v18; // rax
  SAFEARRAY *v19; // rcx
  __int64 v20; // rax
  int v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+80h] [rbp-80h] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v26[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v27[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v28[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v29[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v30[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v31[64]; // [rsp+310h] [rbp+210h] BYREF

  v2 = *((_DWORD *)this + 14);
  ppsaOut = (SAFEARRAY *)this;
  ppvData = 0;
  v4 = xmmword_180169738;
  v6 = qword_180169748;
  v22 = v2;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "DataCollectorSet::put_Keywords", 31, &ppsaOut, 8, &v22, 4);
    v6 = qword_180169748;
    v4 = xmmword_180169738;
  }
  if ( *((_DWORD *)this + 2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v6 = qword_180169748;
    v4 = xmmword_180169738;
  }
  if ( !a2 )
  {
    v22 = 0;
    v7 = -2147467261;
    v23 = -2147467261;
    if ( v4 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v6 == (v6 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v26, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v26[v8] );
      v9 = &v23;
      v10 = &v22;
      goto LABEL_14;
    }
    goto LABEL_57;
  }
  if ( a2->rgsabound[0].cElements > 0x100 )
  {
    v23 = 0;
    v7 = -2147024809;
    v22 = -2147024809;
    if ( !v4 || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0 || v6 != (v6 & 0x4000000000000800LL) )
      goto LABEL_57;
    PlaiWhoAmI(v27, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v27[v11] );
    goto LABEL_21;
  }
  v12 = SafeArrayAccessData(a2, &ppvData);
  v7 = v12;
  if ( v12 < 0 )
  {
    v23 = 0;
    v22 = v12;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_57;
    }
    PlaiWhoAmI(v28, 0x4000000000000800uLL);
    v13 = -1;
    do
      ++v13;
    while ( v28[v13] );
    goto LABEL_21;
  }
  for ( i = 0; i < a2->rgsabound[0].cElements; ++i )
  {
    if ( PlaiValidateString(*((const unsigned __int16 **)ppvData + i), 1u, 0x400u) < 0 )
      break;
  }
  ppsaOut = 0;
  v15 = PlaiValidateSafeArray(a2);
  v7 = v15;
  if ( v15 < 0 )
  {
    v23 = 0;
    v22 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_57;
    }
    PlaiWhoAmI(v29, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v29[v16] );
    goto LABEL_21;
  }
  v17 = SafeArrayCopy(a2, &ppsaOut);
  v7 = v17;
  if ( v17 < 0 )
  {
    v23 = 0;
    v22 = v17;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_57;
    }
    PlaiWhoAmI(v30, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v30[v18] );
LABEL_21:
    v10 = &v23;
    v9 = &v22;
LABEL_14:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v9, 4, byte_180147320, 1, v10, 4);
    goto LABEL_57;
  }
  v19 = (SAFEARRAY *)*((_QWORD *)this + 13);
  if ( !v19 || (v7 = SafeArrayDestroy(v19), v7 >= 0) )
  {
    *((_QWORD *)this + 13) = ppsaOut;
    goto LABEL_57;
  }
  if ( ppsaOut )
    SafeArrayDestroy(ppsaOut);
  v23 = 0;
  v22 = v7;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v31, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v31[v20] );
    goto LABEL_21;
  }
LABEL_57:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ppvData )
    SafeArrayUnaccessData(a2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009e130  mov     [rsp-8+arg_10], rbx
0x18009e135  push    rbp
0x18009e136  push    rsi
0x18009e137  push    rdi
0x18009e138  push    r12
0x18009e13a  push    r13
0x18009e13c  push    r14
0x18009e13e  push    r15
0x18009e140  lea     rbp, [rsp-2A0h]
0x18009e148  sub     rsp, 3A0h
0x18009e14f  mov     rax, cs:__security_cookie
0x18009e156  xor     rax, rsp
0x18009e159  mov     [rbp+2D0h+var_40], rax
0x18009e160  mov     eax, [rcx+38h]
0x18009e163  lea     r14, aDatacollectors_7; "DataCollectorSet::put_Keywords"
0x18009e16a  xor     r15d, r15d
0x18009e16d  mov     [rbp+2D0h+ppsaOut], rcx
0x18009e171  mov     rsi, rdx
0x18009e174  mov     [rbp+2D0h+ppvData], r15
0x18009e178  mov     edx, dword ptr cs:xmmword_180169738
0x18009e17e  mov     rdi, rcx
0x18009e181  mov     rcx, cs:qword_180169748
0x18009e188  mov     [rsp+3D0h+var_360], eax
0x18009e18c  lea     r12d, [r15+4]
0x18009e190  lea     r13d, [r15+1Fh]
0x18009e194  test    edx, edx
0x18009e196  jz      short loc_18009E203
0x18009e198  mov     r8, 4000000000000400h
0x18009e1a2  test    qword ptr cs:xmmword_180169738+8, r8
0x18009e1a9  jz      short loc_18009E203
0x18009e1ab  mov     rax, rcx
0x18009e1ae  and     rax, r8
0x18009e1b1  cmp     rcx, rax
0x18009e1b4  jnz     short loc_18009E203
0x18009e1b6  mov     [rsp+3D0h+var_390], r12
0x18009e1bb  lea     rax, [rsp+3D0h+var_360]
0x18009e1c0  mov     [rsp+3D0h+var_398], rax
0x18009e1c5  lea     r8d, [r15+3]
0x18009e1c9  lea     rax, [rbp+2D0h+ppsaOut]
0x18009e1cd  mov     [rsp+3D0h+var_3A0], 8
0x18009e1d6  mov     [rsp+3D0h+var_3A8], rax
0x18009e1db  lea     rdx, PLA_EVENT_METHOD
0x18009e1e2  mov     r9, r14
0x18009e1e5  mov     [rsp+3D0h+var_3B0], r13
0x18009e1ea  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18009e1f1  call    EventingWriteEvent
0x18009e1f6  mov     rcx, cs:qword_180169748
0x18009e1fd  mov     edx, dword ptr cs:xmmword_180169738
0x18009e203  cmp     [rdi+8], r15d
0x18009e207  jz      short loc_18009E220
0x18009e209  lea     rcx, [rdi+10h]; lpCriticalSection
0x18009e20d  call    cs:__imp_EnterCriticalSection
0x18009e213  mov     rcx, cs:qword_180169748
0x18009e21a  mov     edx, dword ptr cs:xmmword_180169738
0x18009e220  test    rsi, rsi
0x18009e223  jnz     loc_18009E2ED
0x18009e229  mov     [rsp+3D0h+var_360], r15d
0x18009e22e  mov     ebx, 80004003h
0x18009e233  mov     [rsp+3D0h+var_358], ebx
0x18009e237  test    edx, edx
0x18009e239  jz      loc_18009E607
0x18009e23f  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e249  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e250  jz      loc_18009E607
0x18009e256  mov     rax, rcx
0x18009e259  and     rax, rdx
0x18009e25c  cmp     rcx, rax
0x18009e25f  jnz     loc_18009E607
0x18009e265  lea     rcx, [rbp+2D0h+var_340]; unsigned __int16 *
0x18009e269  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e26e  lea     rcx, [rbp+2D0h+var_340]
0x18009e272  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e276  inc     rax
0x18009e279  cmp     [rcx+rax*2], r15w
0x18009e27e  jnz     short loc_18009E276
0x18009e280  lea     ecx, [rax+rax]
0x18009e283  lea     rax, [rbp+2D0h+var_340]
0x18009e287  add     rcx, 2
0x18009e28b  mov     [rsp+3D0h+var_370], rcx
0x18009e290  lea     r9, [rsp+3D0h+var_358]
0x18009e295  mov     [rsp+3D0h+var_378], rax
0x18009e29a  lea     rax, [rsp+3D0h+var_360]
0x18009e29f  mov     [rsp+3D0h+var_380], r13
0x18009e2a4  mov     [rsp+3D0h+var_388], r14
0x18009e2a9  mov     r14d, 1
0x18009e2af  mov     [rsp+3D0h+var_390], r12
0x18009e2b4  lea     rdx, PLA_EVENT_ERROR
0x18009e2bb  mov     [rsp+3D0h+var_398], rax
0x18009e2c0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18009e2c7  lea     rax, byte_180147320
0x18009e2ce  mov     [rsp+3D0h+var_3A0], r14
0x18009e2d3  mov     [rsp+3D0h+var_3A8], rax
0x18009e2d8  mov     r8d, 5
0x18009e2de  mov     [rsp+3D0h+var_3B0], r12
0x18009e2e3  call    EventingWriteEvent
0x18009e2e8  jmp     loc_18009E607
0x18009e2ed  cmp     dword ptr [rsi+18h], 100h
0x18009e2f4  jbe     loc_18009E385
0x18009e2fa  mov     [rsp+3D0h+var_358], r15d
0x18009e2ff  mov     ebx, 80070057h
0x18009e304  mov     [rsp+3D0h+var_360], ebx
0x18009e308  test    edx, edx
0x18009e30a  jz      loc_18009E607
0x18009e310  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e31a  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e321  jz      loc_18009E607
0x18009e327  mov     rax, rcx
0x18009e32a  and     rax, rdx
0x18009e32d  cmp     rcx, rax
0x18009e330  jnz     loc_18009E607
0x18009e336  lea     rcx, [rbp+2D0h+var_2C0]; unsigned __int16 *
0x18009e33a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e33f  lea     rcx, [rbp+2D0h+var_2C0]
0x18009e343  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e347  inc     rax
0x18009e34a  cmp     [rcx+rax*2], r15w
0x18009e34f  jnz     short loc_18009E347
0x18009e351  lea     ecx, [rax+rax]
0x18009e354  lea     rax, [rbp+2D0h+var_2C0]
0x18009e358  add     rcx, 2
0x18009e35c  mov     [rsp+3D0h+var_370], rcx
0x18009e361  mov     [rsp+3D0h+var_378], rax
0x18009e366  mov     [rsp+3D0h+var_380], r13
0x18009e36b  mov     [rsp+3D0h+var_388], r14
0x18009e370  mov     r14d, 1
0x18009e376  lea     rax, [rsp+3D0h+var_358]
0x18009e37b  lea     r9, [rsp+3D0h+var_360]
0x18009e380  jmp     loc_18009E2AF
0x18009e385  lea     rdx, [rbp+2D0h+ppvData]; ppvData
0x18009e389  mov     rcx, rsi; psa
0x18009e38c  call    cs:__imp_SafeArrayAccessData
0x18009e392  mov     ebx, eax
0x18009e394  test    eax, eax
0x18009e396  jns     short loc_18009E40C
0x18009e398  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009e39f  mov     [rsp+3D0h+var_358], r15d
0x18009e3a4  mov     [rsp+3D0h+var_360], eax
0x18009e3a8  jz      loc_18009E607
0x18009e3ae  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e3b8  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e3bf  jz      loc_18009E607
0x18009e3c5  mov     rax, cs:qword_180169748
0x18009e3cc  and     rax, rdx
0x18009e3cf  cmp     cs:qword_180169748, rax
0x18009e3d6  jnz     loc_18009E607
0x18009e3dc  lea     rcx, [rbp+2D0h+var_240]; unsigned __int16 *
0x18009e3e3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e3e8  lea     rcx, [rbp+2D0h+var_240]
0x18009e3ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e3f3  inc     rax
0x18009e3f6  cmp     [rcx+rax*2], r15w
0x18009e3fb  jnz     short loc_18009E3F3
0x18009e3fd  lea     ecx, [rax+rax]
0x18009e400  lea     rax, [rbp+2D0h+var_240]
0x18009e407  jmp     loc_18009E358
0x18009e40c  mov     ebx, r15d
0x18009e40f  mov     r14d, 1
0x18009e415  cmp     [rsi+18h], r15d
0x18009e419  jbe     short loc_18009E43F
0x18009e41b  mov     rcx, [rbp+2D0h+ppvData]
0x18009e41f  mov     r8d, 400h; unsigned __int64
0x18009e425  mov     eax, ebx
0x18009e427  mov     rdx, r14; unsigned __int64
0x18009e42a  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x18009e42e  call    ?PlaiValidateString@@YAJPEBG_K1@Z; PlaiValidateString(ushort const *,unsigned __int64,unsigned __int64)
0x18009e433  test    eax, eax
0x18009e435  js      short loc_18009E43F
0x18009e437  add     ebx, r14d
0x18009e43a  cmp     ebx, [rsi+18h]
0x18009e43d  jb      short loc_18009E41B
0x18009e43f  mov     rcx, rsi; psa
0x18009e442  mov     [rbp+2D0h+ppsaOut], r15
0x18009e446  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x18009e44b  mov     ebx, eax
0x18009e44d  test    eax, eax
0x18009e44f  jns     loc_18009E4E8
0x18009e455  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009e45c  mov     [rsp+3D0h+var_358], r15d
0x18009e461  mov     [rsp+3D0h+var_360], eax
0x18009e465  jz      loc_18009E607
0x18009e46b  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e475  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e47c  jz      loc_18009E607
0x18009e482  mov     rax, cs:qword_180169748
0x18009e489  and     rax, rdx
0x18009e48c  cmp     cs:qword_180169748, rax
0x18009e493  jnz     loc_18009E607
0x18009e499  lea     rcx, [rbp+2D0h+var_1C0]; unsigned __int16 *
0x18009e4a0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e4a5  lea     rcx, [rbp+2D0h+var_1C0]
0x18009e4ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e4b0  inc     rax
0x18009e4b3  cmp     [rcx+rax*2], r15w
0x18009e4b8  jnz     short loc_18009E4B0
0x18009e4ba  lea     ecx, [rax+rax]
0x18009e4bd  lea     rax, [rbp+2D0h+var_1C0]
0x18009e4c4  add     rcx, 2
0x18009e4c8  mov     [rsp+3D0h+var_370], rcx
0x18009e4cd  mov     [rsp+3D0h+var_378], rax
0x18009e4d2  lea     rax, aDatacollectors_7; "DataCollectorSet::put_Keywords"
0x18009e4d9  mov     [rsp+3D0h+var_380], r13
0x18009e4de  mov     [rsp+3D0h+var_388], rax
0x18009e4e3  jmp     loc_18009E376
0x18009e4e8  lea     rdx, [rbp+2D0h+ppsaOut]; ppsaOut
0x18009e4ec  mov     rcx, rsi; psa
0x18009e4ef  call    cs:__imp_SafeArrayCopy
0x18009e4f5  mov     ebx, eax
0x18009e4f7  test    eax, eax
0x18009e4f9  jns     short loc_18009E56F
0x18009e4fb  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009e502  mov     [rsp+3D0h+var_358], r15d
0x18009e507  mov     [rsp+3D0h+var_360], eax
0x18009e50b  jz      loc_18009E607
0x18009e511  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e51b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e522  jz      loc_18009E607
0x18009e528  mov     rax, cs:qword_180169748
0x18009e52f  and     rax, rdx
0x18009e532  cmp     cs:qword_180169748, rax
0x18009e539  jnz     loc_18009E607
0x18009e53f  lea     rcx, [rbp+2D0h+var_140]; unsigned __int16 *
0x18009e546  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e54b  lea     rcx, [rbp+2D0h+var_140]
0x18009e552  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e556  inc     rax
0x18009e559  cmp     [rcx+rax*2], r15w
0x18009e55e  jnz     short loc_18009E556
0x18009e560  lea     ecx, [rax+rax]
0x18009e563  lea     rax, [rbp+2D0h+var_140]
0x18009e56a  jmp     loc_18009E4C4
0x18009e56f  mov     rcx, [rdi+68h]; psa
0x18009e573  test    rcx, rcx
0x18009e576  jz      loc_18009E5FF
0x18009e57c  call    cs:__imp_SafeArrayDestroy
0x18009e582  mov     ebx, eax
0x18009e584  test    eax, eax
0x18009e586  jns     short loc_18009E5FF
0x18009e588  mov     rcx, [rbp+2D0h+ppsaOut]; psa
0x18009e58c  test    rcx, rcx
0x18009e58f  jz      short loc_18009E597
0x18009e591  call    cs:__imp_SafeArrayDestroy
0x18009e597  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009e59e  mov     [rsp+3D0h+var_358], r15d
0x18009e5a3  mov     [rsp+3D0h+var_360], ebx
0x18009e5a7  jz      short loc_18009E607
0x18009e5a9  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e5b3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e5ba  jz      short loc_18009E607
0x18009e5bc  mov     rax, cs:qword_180169748
0x18009e5c3  and     rax, rdx
0x18009e5c6  cmp     cs:qword_180169748, rax
0x18009e5cd  jnz     short loc_18009E607
0x18009e5cf  lea     rcx, [rbp+2D0h+var_C0]; unsigned __int16 *
0x18009e5d6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e5db  lea     rcx, [rbp+2D0h+var_C0]
0x18009e5e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009e5e6  inc     rax
0x18009e5e9  cmp     [rcx+rax*2], r15w
0x18009e5ee  jnz     short loc_18009E5E6
0x18009e5f0  lea     ecx, [rax+rax]
0x18009e5f3  lea     rax, [rbp+2D0h+var_C0]
0x18009e5fa  jmp     loc_18009E4C4
0x18009e5ff  mov     rax, [rbp+2D0h+ppsaOut]
0x18009e603  mov     [rdi+68h], rax
0x18009e607  cmp     [rdi+8], r15d
0x18009e60b  jz      short loc_18009E617
0x18009e60d  lea     rcx, [rdi+10h]; lpCriticalSection
0x18009e611  call    cs:__imp_LeaveCriticalSection
0x18009e617  cmp     [rbp+2D0h+ppvData], r15
0x18009e61b  jz      short loc_18009E626
0x18009e61d  mov     rcx, rsi; psa
0x18009e620  call    cs:__imp_SafeArrayUnaccessData
0x18009e626  mov     eax, ebx
0x18009e628  mov     rcx, [rbp+2D0h+var_40]
0x18009e62f  xor     rcx, rsp; StackCookie
0x18009e632  call    __security_check_cookie
0x18009e637  mov     rbx, [rsp+3D0h+arg_10]
0x18009e63f  add     rsp, 3A0h
0x18009e646  pop     r15
0x18009e648  pop     r14
0x18009e64a  pop     r13
0x18009e64c  pop     r12
0x18009e64e  pop     rdi
0x18009e64f  pop     rsi
0x18009e650  pop     rbp
0x18009e651  retn
```
