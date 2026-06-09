# PlaiStringsToSafeArray(ushort const *,tagSAFEARRAY * *)

- ea: `0x180056474`
- end: `0x180056778`
- name: `?PlaiStringsToSafeArray@@YAJPEBGPEAPEAUtagSAFEARRAY@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagSAFEARRAY **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180065b80`
- `0x1800c5a04`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x180056474`
- `0x18013aee0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005673e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18005673e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800565ea`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800565ea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180056727`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180056727`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800564f5`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800564f5`

## pseudocode

```c
__int64 __fastcall PlaiStringsToSafeArray(const unsigned __int16 *a1, struct tagSAFEARRAY **a2)
{
  ULONG v2; // r15d
  const unsigned __int16 *v4; // rdi
  __int64 v6; // rbx
  ULONG v7; // r12d
  const unsigned __int16 *i; // rax
  __int64 v9; // rcx
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v11; // rsi
  int v12; // r14d
  int *v13; // r9
  int *v14; // rcx
  HRESULT v15; // eax
  const char *v16; // rdx
  int v17; // r8d
  unsigned __int16 *v18; // rax
  __int64 v19; // rax
  int v20; // [rsp+70h] [rbp-90h] BYREF
  int v21; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v25[64]; // [rsp+190h] [rbp+90h] BYREF

  v2 = 0;
  ppvData = 0;
  v4 = a1;
  if ( !a1 )
    return 0;
  v6 = -1;
  v7 = 0;
  for ( i = a1; *i; i += v9 + 1 )
  {
    v9 = -1;
    do
      ++v9;
    while ( i[v9] );
    ++v7;
  }
  Vector = SafeArrayCreateVector(8u, 0, v7);
  v11 = Vector;
  if ( !Vector )
  {
    v12 = -2147024882;
    v21 = -2147024882;
    v20 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_33;
    }
    PlaiWhoAmI(v23, 0x4000000000000800uLL);
    do
      ++v6;
    while ( v23[v6] );
    v13 = &v21;
    v14 = &v20;
    goto LABEL_14;
  }
  v15 = SafeArrayAccessData(Vector, &ppvData);
  v12 = v15;
  if ( v15 >= 0 )
  {
    while ( v2 < v7 )
    {
      v18 = PlaiAllocStringEx(v4, v16, v17);
      v17 = 0;
      if ( !v18 )
      {
        v12 = -2147024882;
        v21 = 0;
        v20 = -2147024882;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v25, 0x4000000000000800uLL);
          do
            ++v6;
          while ( v25[v6] );
          goto LABEL_21;
        }
        goto LABEL_33;
      }
      v16 = (const char *)v2;
      *((_QWORD *)ppvData + v2) = v18;
      v19 = -1;
      do
        ++v19;
      while ( v4[v19] );
      v4 += v19 + 1;
      ++v2;
    }
    goto LABEL_33;
  }
  v21 = 0;
  v20 = v15;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v24, 0x4000000000000800uLL);
    do
      ++v6;
    while ( v24[v6] );
LABEL_21:
    v13 = &v20;
    v14 = &v21;
LABEL_14:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v13, 4, byte_180147320, 1, v14, 4);
  }
LABEL_33:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v11);
    ppvData = 0;
  }
  if ( v12 < 0 )
  {
    if ( v11 )
      SafeArrayDestroy(v11);
    v11 = 0;
  }
  *a2 = v11;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180056474  mov     [rsp-8+arg_10], rbx
0x180056479  push    rbp
0x18005647a  push    rsi
0x18005647b  push    rdi
0x18005647c  push    r12
0x18005647e  push    r13
0x180056480  push    r14
0x180056482  push    r15
0x180056484  lea     rbp, [rsp-120h]
0x18005648c  sub     rsp, 220h
0x180056493  mov     rax, cs:__security_cookie
0x18005649a  xor     rax, rsp
0x18005649d  mov     [rbp+150h+var_40], rax
0x1800564a4  xor     r15d, r15d
0x1800564a7  mov     r13, rdx
0x1800564aa  mov     [rbp+150h+ppvData], r15
0x1800564ae  mov     rdi, rcx
0x1800564b1  test    rcx, rcx
0x1800564b4  jnz     short loc_1800564BD
0x1800564b6  xor     eax, eax
0x1800564b8  jmp     loc_18005674E
0x1800564bd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800564c1  mov     r12d, r15d
0x1800564c4  mov     rax, rcx
0x1800564c7  cmp     [rcx], r15w
0x1800564cb  jz      short loc_1800564EB
0x1800564cd  mov     rcx, rbx
0x1800564d0  inc     rcx
0x1800564d3  cmp     [rax+rcx*2], r15w
0x1800564d8  jnz     short loc_1800564D0
0x1800564da  lea     rax, [rax+rcx*2]
0x1800564de  inc     r12d
0x1800564e1  add     rax, 2
0x1800564e5  cmp     [rax], r15w
0x1800564e9  jnz     short loc_1800564CD
0x1800564eb  mov     ecx, 8; vt
0x1800564f0  mov     r8d, r12d; cElements
0x1800564f3  xor     edx, edx; lLbound
0x1800564f5  call    cs:__imp_SafeArrayCreateVector
0x1800564fb  mov     rsi, rax
0x1800564fe  test    rax, rax
0x180056501  jnz     loc_1800565E3
0x180056507  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005650e  mov     eax, 8007000Eh
0x180056513  mov     r14d, eax
0x180056516  mov     [rsp+250h+var_1D8], eax
0x18005651a  mov     [rsp+250h+var_1E0], r15d
0x18005651f  jz      loc_18005671E
0x180056525  mov     rdx, 4000000000000800h; unsigned __int64
0x18005652f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180056536  jz      loc_18005671E
0x18005653c  mov     rax, cs:qword_180169748
0x180056543  and     rax, rdx
0x180056546  cmp     cs:qword_180169748, rax
0x18005654d  jnz     loc_18005671E
0x180056553  lea     rcx, [rbp+150h+var_1C0]; unsigned __int16 *
0x180056557  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005655c  lea     rax, [rbp+150h+var_1C0]
0x180056560  inc     rbx
0x180056563  cmp     [rax+rbx*2], r15w
0x180056568  jnz     short loc_180056560
0x18005656a  lea     ecx, [rbx+rbx]
0x18005656d  add     rcx, 2
0x180056571  lea     rax, [rbp+150h+var_1C0]
0x180056575  mov     [rsp+250h+var_1F0], rcx
0x18005657a  lea     r9, [rsp+250h+var_1D8]
0x18005657f  lea     rcx, [rsp+250h+var_1E0]
0x180056584  mov     [rsp+250h+var_1F8], rax
0x180056589  lea     rdx, PLA_EVENT_ERROR
0x180056590  mov     [rsp+250h+var_200], 17h
0x180056599  lea     rax, aPlaistringstos; "PlaiStringsToSafeArray"
0x1800565a0  mov     [rsp+250h+var_208], rax
0x1800565a5  mov     eax, 4
0x1800565aa  mov     [rsp+250h+var_210], rax
0x1800565af  mov     [rsp+250h+var_218], rcx
0x1800565b4  lea     rcx, byte_180147320
0x1800565bb  mov     [rsp+250h+var_220], 1
0x1800565c4  mov     [rsp+250h+var_228], rcx
0x1800565c9  lea     r8d, [rax+1]
0x1800565cd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800565d4  mov     [rsp+250h+var_230], rax
0x1800565d9  call    EventingWriteEvent
0x1800565de  jmp     loc_18005671E
0x1800565e3  lea     rdx, [rbp+150h+ppvData]; ppvData
0x1800565e7  mov     rcx, rsi; psa
0x1800565ea  call    cs:__imp_SafeArrayAccessData
0x1800565f0  mov     r14d, eax
0x1800565f3  test    eax, eax
0x1800565f5  jns     short loc_180056671
0x1800565f7  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800565fe  mov     [rsp+250h+var_1D8], r15d
0x180056603  mov     [rsp+250h+var_1E0], eax
0x180056607  jz      loc_18005671E
0x18005660d  mov     rdx, 4000000000000800h; unsigned __int64
0x180056617  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005661e  jz      loc_18005671E
0x180056624  mov     rax, cs:qword_180169748
0x18005662b  and     rax, rdx
0x18005662e  cmp     cs:qword_180169748, rax
0x180056635  jnz     loc_18005671E
0x18005663b  lea     rcx, [rbp+150h+var_140]; unsigned __int16 *
0x18005663f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180056644  lea     rax, [rbp+150h+var_140]
0x180056648  inc     rbx
0x18005664b  cmp     [rax+rbx*2], r15w
0x180056650  jnz     short loc_180056648
0x180056652  lea     rax, [rbp+150h+var_140]
0x180056656  lea     ecx, [rbx+rbx]
0x180056659  add     rcx, 2
0x18005665d  lea     r9, [rsp+250h+var_1E0]
0x180056662  mov     [rsp+250h+var_1F0], rcx
0x180056667  lea     rcx, [rsp+250h+var_1D8]
0x18005666c  jmp     loc_180056584
0x180056671  cmp     r15d, r12d
0x180056674  jnb     loc_18005671B
0x18005667a  mov     rcx, rdi; unsigned __int16 *
0x18005667d  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x180056682  xor     r8d, r8d
0x180056685  test    rax, rax
0x180056688  jz      short loc_1800566AF
0x18005668a  mov     rcx, [rbp+150h+ppvData]
0x18005668e  mov     edx, r15d
0x180056691  mov     [rcx+rdx*8], rax
0x180056695  mov     rax, rbx
0x180056698  inc     rax
0x18005669b  cmp     [rdi+rax*2], r8w
0x1800566a0  jnz     short loc_180056698
0x1800566a2  lea     rdi, [rdi+rax*2]
0x1800566a6  add     rdi, 2
0x1800566aa  inc     r15d
0x1800566ad  jmp     short loc_180056671
0x1800566af  xor     r15d, r15d
0x1800566b2  mov     eax, 8007000Eh
0x1800566b7  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800566be  mov     r14d, eax
0x1800566c1  mov     [rsp+250h+var_1D8], r15d
0x1800566c6  mov     [rsp+250h+var_1E0], eax
0x1800566ca  jz      short loc_18005671E
0x1800566cc  mov     rdx, 4000000000000800h; unsigned __int64
0x1800566d6  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800566dd  jz      short loc_18005671E
0x1800566df  mov     rax, cs:qword_180169748
0x1800566e6  and     rax, rdx
0x1800566e9  cmp     cs:qword_180169748, rax
0x1800566f0  jnz     short loc_18005671E
0x1800566f2  lea     rcx, [rbp+150h+var_C0]; unsigned __int16 *
0x1800566f9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800566fe  lea     rax, [rbp+150h+var_C0]
0x180056705  inc     rbx
0x180056708  cmp     [rax+rbx*2], r15w
0x18005670d  jnz     short loc_180056705
0x18005670f  lea     rax, [rbp+150h+var_C0]
0x180056716  jmp     loc_180056656
0x18005671b  xor     r15d, r15d
0x18005671e  cmp     [rbp+150h+ppvData], r15
0x180056722  jz      short loc_180056731
0x180056724  mov     rcx, rsi; psa
0x180056727  call    cs:__imp_SafeArrayUnaccessData
0x18005672d  mov     [rbp+150h+ppvData], r15
0x180056731  test    r14d, r14d
0x180056734  jns     short loc_180056747
0x180056736  test    rsi, rsi
0x180056739  jz      short loc_180056744
0x18005673b  mov     rcx, rsi; psa
0x18005673e  call    cs:__imp_SafeArrayDestroy
0x180056744  mov     rsi, r15
0x180056747  mov     [r13+0], rsi
0x18005674b  mov     eax, r14d
0x18005674e  mov     rcx, [rbp+150h+var_40]
0x180056755  xor     rcx, rsp; StackCookie
0x180056758  call    __security_check_cookie
0x18005675d  mov     rbx, [rsp+250h+arg_10]
0x180056765  add     rsp, 220h
0x18005676c  pop     r15
0x18005676e  pop     r14
0x180056770  pop     r13
0x180056772  pop     r12
0x180056774  pop     rdi
0x180056775  pop     rsi
0x180056776  pop     rbp
0x180056777  retn
```
