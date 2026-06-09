# PlaiModifyInvokeResult(tagVARIANT *)

- ea: `0x180075334`
- end: `0x1800756a7`
- name: `?PlaiModifyInvokeResult@@YAJPEAUtagVARIANT@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(VARIANTARG *pvarg)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x180052dd0`
- `0x180054d50`
- `0x18006eaa0`
- `0x180074070`
- `0x18007c700`
- `0x18007e970`
- `0x18009fe80`
- `0x1800b12f0`
- `0x1800b7e90`
- `0x1800b90c0`
- `0x1800c3f30`
- `0x1800caf00`
- `0x1800dd450`
- `0x1800e2000`
- `0x1800e4a30`
- `0x1800e8030`
- `0x180100790`
- `0x180105f50`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180075334`
- `0x18013aee0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180075635`
- `OLEAUT32!__imp_VariantClear` at `0x180075635`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180075678`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180075678`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800754a9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007553a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800754a9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007553a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180075628`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007564d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180075660`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180075628`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007564d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180075660`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800753b3`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800753b3`

## pseudocode

```c
__int64 __fastcall PlaiModifyInvokeResult(VARIANTARG *pvarg)
{
  SAFEARRAY *parray; // r15
  VARTYPE vt; // si
  __int16 v4; // si
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v6; // r14
  unsigned int v7; // ebx
  __int64 v8; // rax
  int *v9; // r9
  int *v10; // rcx
  HRESULT v11; // eax
  __int64 v12; // rax
  HRESULT v13; // eax
  __int64 v14; // rax
  ULONG i; // r9d
  __int64 v16; // rax
  HRESULT v18; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+78h] [rbp-88h] BYREF
  void *v20; // [rsp+80h] [rbp-80h] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v22[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v23[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v24[64]; // [rsp+190h] [rbp+90h] BYREF

  v20 = 0;
  ppvData = 0;
  if ( !pvarg )
    return 0;
  parray = pvarg->parray;
  if ( !parray )
    return 0;
  vt = pvarg->vt;
  if ( pvarg->vt != 8200 && vt != 8209 )
    return 0;
  v4 = vt & 0xDFFF;
  Vector = SafeArrayCreateVector(0xCu, 0, parray->rgsabound[0].cElements);
  v6 = Vector;
  if ( !Vector )
  {
    v7 = -2147024882;
    v19 = -2147024882;
    v18 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_36;
    }
    PlaiWhoAmI(v22, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v22[v8] );
    v9 = &v19;
    v10 = &v18;
    goto LABEL_12;
  }
  v11 = SafeArrayAccessData(Vector, &ppvData);
  v7 = v11;
  if ( v11 < 0 )
  {
    v19 = 0;
    v18 = v11;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_36;
    }
    PlaiWhoAmI(v23, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v23[v12] );
    goto LABEL_19;
  }
  v13 = SafeArrayAccessData(parray, &v20);
  v7 = v13;
  if ( v13 >= 0 )
  {
    for ( i = 0; i < parray->rgsabound[0].cElements; *((_WORD *)ppvData + 12 * v16) = v4 )
    {
      if ( v4 == 8 )
      {
        *((_QWORD *)ppvData + 3 * i + 1) = *((_QWORD *)v20 + i);
        *((_QWORD *)v20 + i) = 0;
      }
      else if ( v4 == 17 )
      {
        *((_BYTE *)ppvData + 24 * i + 8) = *((_BYTE *)v20 + i);
      }
      v16 = i++;
    }
    if ( v20 )
    {
      SafeArrayUnaccessData(parray);
      v20 = 0;
    }
    VariantClear(pvarg);
    pvarg->vt = 8204;
    pvarg->llVal = (LONGLONG)v6;
    goto LABEL_36;
  }
  v19 = 0;
  v18 = v13;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v24, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v24[v14] );
LABEL_19:
    v9 = &v18;
    v10 = &v19;
LABEL_12:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v9, 4, qword_180147320, 1, v10, 4, "PlaiModifyInvokeResult", 23);
  }
LABEL_36:
  if ( v20 )
  {
    SafeArrayUnaccessData(parray);
    v20 = 0;
  }
  if ( ppvData )
  {
    SafeArrayUnaccessData(v6);
    ppvData = 0;
  }
  if ( pvarg->parray != v6 )
  {
    if ( v6 )
      SafeArrayDestroy(v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180075334  push    rbp
0x180075336  push    rbx
0x180075337  push    rsi
0x180075338  push    rdi
0x180075339  push    r12
0x18007533b  push    r13
0x18007533d  push    r14
0x18007533f  push    r15
0x180075341  lea     rbp, [rsp-128h]
0x180075349  sub     rsp, 228h
0x180075350  mov     rax, cs:__security_cookie
0x180075357  xor     rax, rsp
0x18007535a  mov     [rbp+160h+var_50], rax
0x180075361  xor     r13d, r13d
0x180075364  mov     rdi, rcx
0x180075367  mov     [rbp+160h+var_1E0], r13
0x18007536b  mov     [rbp+160h+ppvData], r13
0x18007536f  test    rcx, rcx
0x180075372  jz      loc_180075682
0x180075378  mov     r15, [rcx+8]
0x18007537c  test    r15, r15
0x18007537f  jz      loc_180075682
0x180075385  movzx   esi, word ptr [rcx]
0x180075388  mov     eax, 2008h
0x18007538d  cmp     ax, si
0x180075390  jz      short loc_1800753A0
0x180075392  mov     eax, 2011h
0x180075397  cmp     ax, si
0x18007539a  jnz     loc_180075682
0x1800753a0  mov     r8d, [r15+18h]; cElements
0x1800753a4  mov     eax, 0DFFFh
0x1800753a9  mov     ecx, 0Ch; vt
0x1800753ae  xor     edx, edx; lLbound
0x1800753b0  and     si, ax
0x1800753b3  call    cs:__imp_SafeArrayCreateVector
0x1800753b9  mov     r14, rax
0x1800753bc  test    rax, rax
0x1800753bf  jnz     loc_1800754A2
0x1800753c5  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800753cc  mov     ebx, 8007000Eh
0x1800753d1  mov     [rsp+260h+var_1E8], ebx
0x1800753d5  mov     [rsp+260h+var_1F0], r13d
0x1800753da  jz      loc_180075644
0x1800753e0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800753ea  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800753f1  jz      loc_180075644
0x1800753f7  mov     rax, cs:qword_180169748
0x1800753fe  and     rax, rdx
0x180075401  cmp     cs:qword_180169748, rax
0x180075408  jnz     loc_180075644
0x18007540e  lea     rcx, [rbp+160h+var_1D0]; unsigned __int16 *
0x180075412  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180075417  lea     rcx, [rbp+160h+var_1D0]
0x18007541b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007541f  inc     rax
0x180075422  cmp     [rcx+rax*2], r13w
0x180075427  jnz     short loc_18007541F
0x180075429  lea     ecx, [rax+rax]
0x18007542c  add     rcx, 2
0x180075430  lea     rax, [rbp+160h+var_1D0]
0x180075434  mov     [rsp+260h+var_200], rcx
0x180075439  lea     r9, [rsp+260h+var_1E8]
0x18007543e  lea     rcx, [rsp+260h+var_1F0]
0x180075443  mov     [rsp+260h+var_208], rax
0x180075448  lea     rdx, PLA_EVENT_ERROR
0x18007544f  mov     [rsp+260h+var_210], 17h
0x180075458  lea     rax, aPlaimodifyinvo; "PlaiModifyInvokeResult"
0x18007545f  mov     [rsp+260h+var_218], rax
0x180075464  mov     eax, 4
0x180075469  mov     [rsp+260h+var_220], rax
0x18007546e  mov     [rsp+260h+var_228], rcx
0x180075473  lea     rcx, qword_180147320
0x18007547a  mov     [rsp+260h+var_230], 1
0x180075483  mov     [rsp+260h+var_238], rcx
0x180075488  lea     r8d, [rax+1]
0x18007548c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180075493  mov     [rsp+260h+var_240], rax
0x180075498  call    EventingWriteEvent
0x18007549d  jmp     loc_180075644
0x1800754a2  lea     rdx, [rbp+160h+ppvData]; ppvData
0x1800754a6  mov     rcx, r14; psa
0x1800754a9  call    cs:__imp_SafeArrayAccessData
0x1800754af  mov     ebx, eax
0x1800754b1  test    eax, eax
0x1800754b3  jns     short loc_180075533
0x1800754b5  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800754bc  mov     [rsp+260h+var_1E8], r13d
0x1800754c1  mov     [rsp+260h+var_1F0], eax
0x1800754c5  jz      loc_180075644
0x1800754cb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800754d5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800754dc  jz      loc_180075644
0x1800754e2  mov     rax, cs:qword_180169748
0x1800754e9  and     rax, rdx
0x1800754ec  cmp     cs:qword_180169748, rax
0x1800754f3  jnz     loc_180075644
0x1800754f9  lea     rcx, [rbp+160h+var_150]; unsigned __int16 *
0x1800754fd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180075502  lea     rcx, [rbp+160h+var_150]
0x180075506  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007550a  inc     rax
0x18007550d  cmp     [rcx+rax*2], r13w
0x180075512  jnz     short loc_18007550A
0x180075514  lea     ecx, [rax+rax]
0x180075517  lea     rax, [rbp+160h+var_150]
0x18007551b  add     rcx, 2
0x18007551f  lea     r9, [rsp+260h+var_1F0]
0x180075524  mov     [rsp+260h+var_200], rcx
0x180075529  lea     rcx, [rsp+260h+var_1E8]
0x18007552e  jmp     loc_180075443
0x180075533  lea     rdx, [rbp+160h+var_1E0]; ppvData
0x180075537  mov     rcx, r15; psa
0x18007553a  call    cs:__imp_SafeArrayAccessData
0x180075540  mov     ebx, eax
0x180075542  test    eax, eax
0x180075544  jns     short loc_1800755BA
0x180075546  cmp     dword ptr cs:xmmword_180169738, r13d
0x18007554d  mov     [rsp+260h+var_1E8], r13d
0x180075552  mov     [rsp+260h+var_1F0], eax
0x180075556  jz      loc_180075644
0x18007555c  mov     rdx, 4000000000000800h; unsigned __int64
0x180075566  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007556d  jz      loc_180075644
0x180075573  mov     rax, cs:qword_180169748
0x18007557a  and     rax, rdx
0x18007557d  cmp     cs:qword_180169748, rax
0x180075584  jnz     loc_180075644
0x18007558a  lea     rcx, [rbp+160h+var_D0]; unsigned __int16 *
0x180075591  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180075596  lea     rcx, [rbp+160h+var_D0]
0x18007559d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800755a1  inc     rax
0x1800755a4  cmp     [rcx+rax*2], r13w
0x1800755a9  jnz     short loc_1800755A1
0x1800755ab  lea     ecx, [rax+rax]
0x1800755ae  lea     rax, [rbp+160h+var_D0]
0x1800755b5  jmp     loc_18007551B
0x1800755ba  mov     r9d, r13d
0x1800755bd  cmp     [r15+18h], r13d
0x1800755c1  jbe     short loc_18007561F
0x1800755c3  cmp     si, 8
0x1800755c7  jz      short loc_1800755E7
0x1800755c9  cmp     si, 11h
0x1800755cd  jnz     short loc_180075607
0x1800755cf  mov     rax, [rbp+160h+var_1E0]
0x1800755d3  mov     ecx, r9d
0x1800755d6  lea     rdx, [rcx+rcx*2]
0x1800755da  mov     cl, [rcx+rax]
0x1800755dd  mov     rax, [rbp+160h+ppvData]
0x1800755e1  mov     [rax+rdx*8+8], cl
0x1800755e5  jmp     short loc_180075607
0x1800755e7  mov     rax, [rbp+160h+var_1E0]
0x1800755eb  mov     r8d, r9d
0x1800755ee  mov     rcx, [rax+r8*8]
0x1800755f2  lea     rdx, [r8+r8*2]
0x1800755f6  mov     rax, [rbp+160h+ppvData]
0x1800755fa  mov     [rax+rdx*8+8], rcx
0x1800755ff  mov     rax, [rbp+160h+var_1E0]
0x180075603  mov     [rax+r8*8], r13
0x180075607  mov     eax, r9d
0x18007560a  inc     r9d
0x18007560d  lea     rcx, [rax+rax*2]
0x180075611  mov     rax, [rbp+160h+ppvData]
0x180075615  mov     [rax+rcx*8], si
0x180075619  cmp     r9d, [r15+18h]
0x18007561d  jb      short loc_1800755C3
0x18007561f  cmp     [rbp+160h+var_1E0], r13
0x180075623  jz      short loc_180075632
0x180075625  mov     rcx, r15; psa
0x180075628  call    cs:__imp_SafeArrayUnaccessData
0x18007562e  mov     [rbp+160h+var_1E0], r13
0x180075632  mov     rcx, rdi; pvarg
0x180075635  call    cs:__imp_VariantClear
0x18007563b  mov     word ptr [rdi], 200Ch
0x180075640  mov     [rdi+8], r14
0x180075644  cmp     [rbp+160h+var_1E0], r13
0x180075648  jz      short loc_180075657
0x18007564a  mov     rcx, r15; psa
0x18007564d  call    cs:__imp_SafeArrayUnaccessData
0x180075653  mov     [rbp+160h+var_1E0], r13
0x180075657  cmp     [rbp+160h+ppvData], r13
0x18007565b  jz      short loc_18007566A
0x18007565d  mov     rcx, r14; psa
0x180075660  call    cs:__imp_SafeArrayUnaccessData
0x180075666  mov     [rbp+160h+ppvData], r13
0x18007566a  cmp     [rdi+8], r14
0x18007566e  jz      short loc_18007567E
0x180075670  test    r14, r14
0x180075673  jz      short loc_18007567E
0x180075675  mov     rcx, r14; psa
0x180075678  call    cs:__imp_SafeArrayDestroy
0x18007567e  mov     eax, ebx
0x180075680  jmp     short loc_180075684
0x180075682  xor     eax, eax
0x180075684  mov     rcx, [rbp+160h+var_50]
0x18007568b  xor     rcx, rsp; StackCookie
0x18007568e  call    __security_check_cookie
0x180075693  add     rsp, 228h
0x18007569a  pop     r15
0x18007569c  pop     r14
0x18007569e  pop     r13
0x1800756a0  pop     r12
0x1800756a2  pop     rdi
0x1800756a3  pop     rsi
0x1800756a4  pop     rbx
0x1800756a5  pop     rbp
0x1800756a6  retn
```
