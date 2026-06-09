# Enumerator::Clone(IEnumVARIANT * *)

- ea: `0x180024360`
- end: `0x180024ccc`
- name: `?Clone@Enumerator@@UEAAJPEAPEAUIEnumVARIANT@@@Z`
- size: `2412`
- prototype: `__int64 __fastcall(Enumerator *__hidden this, struct IEnumVARIANT **)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180024360`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180024455`
- `msvcrt!?name@type_info@@QEBAPEBDXZ` at `0x180024455`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800245c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024614`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024544`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800245c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024614`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800243d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024595`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800243d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800244e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024595`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800243eb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800243eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800243da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800243da`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024ca0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024cb3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024cc1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024ca0`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024cb3`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180024cc1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800244fc`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800244fc`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18002451e`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18002451e`

## pseudocode

```c
__int64 __fastcall Enumerator::Clone(Enumerator *this, struct IEnumVARIANT **a2)
{
  SAFEARRAY *v2; // r14
  HANDLE ProcessHeap; // rax
  SAFEARRAY *v6; // rax
  int v7; // ecx
  SAFEARRAYBOUND v8; // rbx
  unsigned __int64 v9; // rdx
  const char *v10; // rax
  unsigned __int64 v11; // rdx
  __int64 v12; // r12
  SAFEARRAY *v13; // rcx
  HRESULT v14; // eax
  int v15; // esi
  HRESULT v16; // eax
  SAFEARRAY *v17; // rcx
  ULONG cElements; // eax
  int v19; // eax
  unsigned __int64 v20; // rdx
  bool v22; // zf
  __int64 v23; // r12
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  SAFEARRAYBOUND v28; // [rsp+78h] [rbp-90h] BYREF
  Enumerator *v29; // [rsp+80h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+88h] [rbp-80h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 v32[64]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 v33[64]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 v34[64]; // [rsp+198h] [rbp+90h] BYREF
  unsigned __int16 v35[64]; // [rsp+218h] [rbp+110h] BYREF
  unsigned __int16 v36[64]; // [rsp+298h] [rbp+190h] BYREF
  unsigned __int16 v37[64]; // [rsp+318h] [rbp+210h] BYREF

  v2 = 0;
  v28.cElements = *((_DWORD *)this + 14);
  psaboundNew = (SAFEARRAYBOUND)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_METHOD, 3, (__int64)"Enumerator::Clone");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ProcessHeap = GetProcessHeap();
  v6 = (SAFEARRAY *)HeapAlloc(ProcessHeap, 0, 0x58u);
  v7 = xmmword_180169738;
  v8 = (SAFEARRAYBOUND)v6;
  v9 = qword_180169748;
  psaboundNew = (SAFEARRAYBOUND)88LL;
  ppsaOut = v6;
  v28.cElements = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
  {
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_NEW, 4, (__int64)byte_180147320);
    v9 = qword_180169748;
    v7 = xmmword_180169738;
  }
  if ( !*(_QWORD *)&v8 )
  {
    v8 = 0;
    v15 = -2147024882;
    v28.cElements = -2147024882;
    LODWORD(v29) = 0;
    if ( v7 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v9 == (v9 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v37, v9);
      v23 = -1;
      do
        v22 = v37[++v23] == 0;
      while ( !v22 );
      goto LABEL_46;
    }
    goto LABEL_34;
  }
  *(_DWORD *)(*(_QWORD *)&v8 + 8LL) = 0;
  **(_QWORD **)&v8 = &Unknown<IEnumVARIANT>::`vftable';
  psaboundNew = v8;
  v10 = type_info::name((type_info *)&IEnumVARIANT `RTTI Type Descriptor');
  v12 = -1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    if ( v10 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v10[v24] );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_CONSTRUCTOR, 2, (__int64)v10);
  }
  _InterlockedIncrement(&g_Count);
  *(_DWORD *)(*(_QWORD *)&v8 + 56LL) = 1;
  **(_QWORD **)&v8 = &Enumerator::`vftable';
  *(_QWORD *)(*(_QWORD *)&v8 + 64LL) = 0;
  *(_QWORD *)(*(_QWORD *)&v8 + 72LL) = 0;
  *(_DWORD *)(*(_QWORD *)&v8 + 80LL) = 0;
  if ( !*((_DWORD *)this + 19) )
    goto LABEL_33;
  v28.cElements = *((_DWORD *)this + 14);
  ppsaOut = 0;
  v29 = this;
  if ( (_DWORD)xmmword_180169738 )
  {
    v11 = 0x4000000000000400LL;
    if ( (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_METHOD, 3, (__int64)"Enumerator::get_Array");
    }
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v13 = (SAFEARRAY *)*((_QWORD *)this + 8);
  if ( v13 )
  {
    v14 = SafeArrayCopy(v13, &ppsaOut);
    v15 = v14;
    if ( v14 < 0 )
    {
      LODWORD(v29) = 0;
      v28.cElements = v14;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v33, v11);
        v26 = -1;
        do
          v22 = v33[++v26] == 0;
        while ( !v22 );
        goto LABEL_75;
      }
    }
    else
    {
      psaboundNew.cElements = *((_DWORD *)this + 19);
      psaboundNew.lLbound = 0;
      v16 = SafeArrayRedim(ppsaOut, &psaboundNew);
      v15 = v16;
      if ( v16 >= 0 )
      {
        v2 = ppsaOut;
        ppsaOut = 0;
        goto LABEL_19;
      }
      LODWORD(v29) = 0;
      v28.cElements = v16;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v34, v11);
        v27 = -1;
        do
          v22 = v34[++v27] == 0;
        while ( !v22 );
LABEL_75:
        EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v28);
      }
    }
  }
  else
  {
    v15 = -2147020590;
    LODWORD(v29) = -2147020590;
    v28.cElements = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v32, v11);
      v25 = -1;
      do
        v22 = v32[++v25] == 0;
      while ( !v22 );
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v29);
    }
  }
LABEL_19:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( ppsaOut )
  {
    SafeArrayDestroy(ppsaOut);
    ppsaOut = 0;
  }
  if ( v15 >= 0 )
  {
    LODWORD(v29) = *(_DWORD *)(*(_QWORD *)&v8 + 56LL);
    v28 = v8;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_METHOD, 3, (__int64)"Enumerator::put_Array");
    }
    if ( *(_DWORD *)(*(_QWORD *)&v8 + 8LL) )
      EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&v8 + 16LL));
    v17 = *(SAFEARRAY **)(*(_QWORD *)&v8 + 64LL);
    if ( v17 )
      SafeArrayDestroy(v17);
    *(_QWORD *)(*(_QWORD *)&v8 + 64LL) = v2;
    *(_DWORD *)(*(_QWORD *)&v8 + 72LL) = 0;
    cElements = v2->rgsabound[0].cElements;
    *(_DWORD *)(*(_QWORD *)&v8 + 76LL) = cElements;
    *(_DWORD *)(*(_QWORD *)&v8 + 80LL) = cElements;
    if ( *(_DWORD *)(*(_QWORD *)&v8 + 8LL) )
      LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)&v8 + 16LL));
    v2 = 0;
LABEL_33:
    v19 = (***(__int64 (__fastcall ****)(SAFEARRAYBOUND, GUID *, struct IEnumVARIANT **))&v8)(v8, &IID_IEnumVARIANT, a2);
    v15 = v19;
    if ( v19 < 0 )
    {
      LODWORD(v29) = 0;
      v28.cElements = v19;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v36, v20);
          do
            v22 = v36[++v12] == 0;
          while ( !v22 );
LABEL_46:
          EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v28);
          goto LABEL_34;
        }
      }
    }
    goto LABEL_34;
  }
  LODWORD(v29) = 0;
  v28.cElements = v15;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v35, v11);
    do
      v22 = v35[++v12] == 0;
    while ( !v22 );
    goto LABEL_46;
  }
LABEL_34:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v8 )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v8 + 16LL))(v8);
  if ( v2 )
    SafeArrayDestroy(v2);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180024360  mov     r11, rsp
0x180024363  push    rbp
0x180024364  push    rsi
0x180024365  push    r14
0x180024367  lea     rbp, [r11-2D8h]
0x18002436e  sub     rsp, 3C0h
0x180024375  mov     rax, cs:__security_cookie
0x18002437c  xor     rax, rsp
0x18002437f  mov     [rbp+2D0h+var_40], rax
0x180024386  mov     eax, [rcx+38h]
0x180024389  xor     esi, esi
0x18002438b  cmp     dword ptr cs:xmmword_180169738, esi
0x180024391  mov     r14d, esi
0x180024394  mov     [r11+18h], rbx
0x180024398  mov     [r11-20h], rdi
0x18002439c  mov     rdi, rcx
0x18002439f  mov     [r11-30h], r13
0x1800243a3  mov     r13, rdx
0x1800243a6  mov     [r11-38h], r15
0x1800243aa  mov     r15, 4000000000000400h
0x1800243b4  mov     dword ptr [rsp+3D0h+var_360], eax
0x1800243b8  mov     qword ptr [rbp+2D0h+psaboundNew.cElements], rcx
0x1800243bc  jz      short loc_1800243CB
0x1800243be  test    qword ptr cs:xmmword_180169738+8, r15
0x1800243c5  jnz     loc_1800247C9
0x1800243cb  cmp     [rdi+8], esi
0x1800243ce  jz      short loc_1800243DA
0x1800243d0  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800243d4  call    cs:__imp_EnterCriticalSection
0x1800243da  call    cs:__imp_GetProcessHeap
0x1800243e0  xor     edx, edx; dwFlags
0x1800243e2  mov     r8d, 58h ; 'X'; dwBytes
0x1800243e8  mov     rcx, rax; hHeap
0x1800243eb  call    cs:__imp_HeapAlloc
0x1800243f1  mov     ecx, dword ptr cs:xmmword_180169738
0x1800243f7  mov     rbx, rax
0x1800243fa  mov     rdx, cs:qword_180169748; unsigned __int64
0x180024401  mov     qword ptr [rbp+2D0h+psaboundNew.cElements], 58h ; 'X'
0x180024409  mov     [rbp+2D0h+ppsaOut], rax
0x18002440d  mov     dword ptr [rsp+3D0h+var_360], esi
0x180024411  test    ecx, ecx
0x180024413  jz      short loc_18002442C
0x180024415  mov     r8, 4000000000000200h
0x18002441f  test    qword ptr cs:xmmword_180169738+8, r8
0x180024426  jnz     loc_180024833
0x18002442c  mov     [rsp+3D0h+var_20], r12
0x180024434  test    rbx, rbx
0x180024437  jz      loc_180024750
0x18002443d  lea     rax, ??_7?$Unknown@UIEnumVARIANT@@@@6B@; const Unknown<IEnumVARIANT>::`vftable'
0x180024444  mov     [rbx+8], esi
0x180024447  lea     rcx, ??_R0?AUIEnumVARIANT@@@8; IEnumVARIANT `RTTI Type Descriptor'
0x18002444e  mov     [rbx], rax
0x180024451  mov     qword ptr [rbp+2D0h+psaboundNew.cElements], rbx
0x180024455  call    cs:__imp_?name@type_info@@QEBAPEBDXZ; type_info::name(void)
0x18002445b  cmp     dword ptr cs:xmmword_180169738, esi
0x180024461  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180024468  jz      short loc_180024477
0x18002446a  test    qword ptr cs:xmmword_180169738+8, r15
0x180024471  jnz     loc_1800248B4
0x180024477  lock inc cs:?g_Count@@3JA; long g_Count
0x18002447e  lea     rax, ??_7Enumerator@@6B@; const Enumerator::`vftable'
0x180024485  mov     dword ptr [rbx+38h], 1
0x18002448c  mov     [rbx], rax
0x18002448f  mov     r15, 4000000000000800h
0x180024499  mov     [rbx+40h], rsi
0x18002449d  mov     [rbx+48h], rsi
0x1800244a1  mov     [rbx+50h], esi
0x1800244a4  cmp     [rdi+4Ch], esi
0x1800244a7  jbe     loc_1800245D0
0x1800244ad  cmp     dword ptr cs:xmmword_180169738, esi
0x1800244b3  mov     eax, [rdi+38h]
0x1800244b6  mov     dword ptr [rsp+3D0h+var_360], eax
0x1800244ba  mov     [rbp+2D0h+ppsaOut], rsi
0x1800244be  mov     [rsp+3D0h+var_358], rdi
0x1800244c3  jz      short loc_1800244DC
0x1800244c5  mov     rdx, 4000000000000400h
0x1800244cf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800244d6  jnz     loc_1800248EA
0x1800244dc  cmp     [rdi+8], esi
0x1800244df  jz      short loc_1800244EB
0x1800244e1  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800244e5  call    cs:__imp_EnterCriticalSection
0x1800244eb  mov     rcx, [rdi+40h]; psa
0x1800244ef  test    rcx, rcx
0x1800244f2  jz      loc_1800249C0
0x1800244f8  lea     rdx, [rbp+2D0h+ppsaOut]; ppsaOut
0x1800244fc  call    cs:__imp_SafeArrayCopy
0x180024502  mov     esi, eax
0x180024504  test    eax, eax
0x180024506  js      loc_180024BEA
0x18002450c  mov     eax, [rdi+4Ch]
0x18002450f  lea     rdx, [rbp+2D0h+psaboundNew]; psaboundNew
0x180024513  mov     rcx, [rbp+2D0h+ppsaOut]; psa
0x180024517  mov     [rbp+2D0h+psaboundNew.cElements], eax
0x18002451a  mov     [rbp+2D0h+psaboundNew.lLbound], r14d
0x18002451e  call    cs:__imp_SafeArrayRedim
0x180024524  mov     esi, eax
0x180024526  test    eax, eax
0x180024528  js      loc_180024C12
0x18002452e  mov     r14, [rbp+2D0h+ppsaOut]
0x180024532  mov     [rbp+2D0h+ppsaOut], 0
0x18002453a  cmp     dword ptr [rdi+8], 0
0x18002453e  jz      short loc_18002454A
0x180024540  lea     rcx, [rdi+10h]; lpCriticalSection
0x180024544  call    cs:__imp_LeaveCriticalSection
0x18002454a  mov     rcx, [rbp+2D0h+ppsaOut]; psa
0x18002454e  test    rcx, rcx
0x180024551  jnz     loc_180024CA0
0x180024557  test    esi, esi
0x180024559  js      loc_180024664
0x18002455f  cmp     dword ptr cs:xmmword_180169738, 0
0x180024566  mov     eax, [rbx+38h]
0x180024569  mov     dword ptr [rsp+3D0h+var_358], eax
0x18002456d  mov     [rsp+3D0h+var_360], rbx
0x180024572  jz      short loc_18002458B
0x180024574  mov     rdx, 4000000000000400h
0x18002457e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180024585  jnz     loc_180024955
0x18002458b  cmp     dword ptr [rbx+8], 0
0x18002458f  jz      short loc_18002459B
0x180024591  lea     rcx, [rbx+10h]; lpCriticalSection
0x180024595  call    cs:__imp_EnterCriticalSection
0x18002459b  mov     rcx, [rbx+40h]; psa
0x18002459f  test    rcx, rcx
0x1800245a2  jnz     loc_180024CB3
0x1800245a8  mov     [rbx+40h], r14
0x1800245ac  mov     dword ptr [rbx+48h], 0
0x1800245b3  mov     eax, [r14+18h]
0x1800245b7  mov     [rbx+4Ch], eax
0x1800245ba  mov     [rbx+50h], eax
0x1800245bd  cmp     dword ptr [rbx+8], 0
0x1800245c1  jz      short loc_1800245CD
0x1800245c3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800245c7  call    cs:__imp_LeaveCriticalSection
0x1800245cd  xor     r14d, r14d
0x1800245d0  mov     rax, [rbx]
0x1800245d3  lea     rdx, IID_IEnumVARIANT
0x1800245da  mov     r8, r13
0x1800245dd  mov     rcx, rbx
0x1800245e0  mov     rax, [rax]
0x1800245e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245e8  mov     esi, eax
0x1800245ea  test    eax, eax
0x1800245ec  js      loc_180024C3A
0x1800245f2  cmp     dword ptr [rdi+8], 0
0x1800245f6  mov     r15, [rsp+3D0h+var_30]
0x1800245fe  mov     r13, [rsp+3D0h+var_28]
0x180024606  mov     r12, [rsp+3D0h+var_20]
0x18002460e  jz      short loc_18002461A
0x180024610  lea     rcx, [rdi+10h]; lpCriticalSection
0x180024614  call    cs:__imp_LeaveCriticalSection
0x18002461a  mov     rdi, [rsp+3B8h]
0x180024622  test    rbx, rbx
0x180024625  jz      short loc_180024636
0x180024627  mov     rax, [rbx]
0x18002462a  mov     rcx, rbx
0x18002462d  mov     rax, [rax+10h]
0x180024631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024636  mov     rbx, [rsp+3D0h+arg_10]
0x18002463e  test    r14, r14
0x180024641  jnz     loc_180024CBE
0x180024647  mov     eax, esi
0x180024649  mov     rcx, [rbp+2D0h+var_40]
0x180024650  xor     rcx, rsp; StackCookie
0x180024653  call    __security_check_cookie
0x180024658  add     rsp, 3C0h
0x18002465f  pop     r14
0x180024661  pop     rsi
0x180024662  pop     rbp
0x180024663  retn
0x180024664  cmp     dword ptr cs:xmmword_180169738, 0
0x18002466b  mov     dword ptr [rsp+3D0h+var_358], 0
0x180024673  mov     dword ptr [rsp+3D0h+var_360], esi
0x180024677  jz      loc_1800245F2
0x18002467d  test    qword ptr cs:xmmword_180169738+8, r15
0x180024684  jz      loc_1800245F2
0x18002468a  mov     rax, cs:qword_180169748
0x180024691  and     rax, r15
0x180024694  cmp     cs:qword_180169748, rax
0x18002469b  jnz     loc_1800245F2
0x1800246a1  lea     rcx, [rbp+2D0h+var_1C0]; unsigned __int16 *
0x1800246a8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800246ad  lea     rax, [rbp+2D0h+var_1C0]
0x1800246b4  nop     dword ptr [rax+00h]
0x1800246b8  nop     dword ptr [rax+rax+00000000h]
0x1800246c0  cmp     word ptr [rax+r12*2+2], 0
0x1800246c7  lea     r12, [r12+1]
0x1800246cc  jnz     short loc_1800246C0
0x1800246ce  lea     rax, [rbp+2D0h+var_1C0]
0x1800246d5  lea     ecx, [r12+r12]
0x1800246d9  mov     r8d, 5
0x1800246df  add     rcx, 2
0x1800246e3  lea     r9, [rsp+3D0h+var_360]
0x1800246e8  mov     [rsp+60h], rcx
0x1800246ed  lea     rdx, PLA_EVENT_ERROR
0x1800246f4  mov     [rsp+3D0h+var_378], rax
0x1800246f9  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180024700  mov     [rsp+3D0h+var_380], 12h
0x180024709  lea     rax, aEnumeratorClon; "Enumerator::Clone"
0x180024710  mov     [rsp+3D0h+var_388], rax
0x180024715  lea     rax, [rsp+3D0h+var_358]
0x18002471a  mov     [rsp+3D0h+var_390], 4
0x180024723  mov     [rsp+3D0h+var_398], rax
0x180024728  lea     rax, byte_180147320
0x18002472f  mov     [rsp+3D0h+var_3A0], 1
0x180024738  mov     [rsp+3D0h+var_3A8], rax
0x18002473d  mov     [rsp+3D0h+var_3B0], 4
0x180024746  call    EventingWriteEvent
0x18002474b  jmp     loc_1800245F2
0x180024750  mov     rbx, rsi
0x180024753  mov     esi, 8007000Eh
0x180024758  mov     dword ptr [rsp+3D0h+var_360], esi
0x18002475c  mov     dword ptr [rsp+3D0h+var_358], ebx
0x180024760  test    ecx, ecx
0x180024762  jz      loc_1800245F2
0x180024768  mov     r15, 4000000000000800h
0x180024772  test    qword ptr cs:xmmword_180169738+8, r15
0x180024779  jz      loc_1800245F2
0x18002477f  mov     rax, rdx
0x180024782  and     rax, r15
0x180024785  cmp     rdx, rax
0x180024788  jnz     loc_1800245F2
0x18002478e  lea     rcx, [rbp+2D0h+var_C0]; unsigned __int16 *
0x180024795  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18002479a  lea     rax, [rbp+2D0h+var_C0]
0x1800247a1  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800247a8  nop     dword ptr [rax+rax+00000000h]
0x1800247b0  cmp     [rax+r12*2+2], bx
0x1800247b6  lea     r12, [r12+1]
0x1800247bb  jnz     short loc_1800247B0
0x1800247bd  lea     rax, [rbp+2D0h+var_C0]
0x1800247c4  jmp     loc_1800246D5
0x1800247c9  mov     rax, cs:qword_180169748
0x1800247d0  and     rax, r15
0x1800247d3  cmp     cs:qword_180169748, rax
0x1800247da  jnz     loc_1800243CB
0x1800247e0  mov     [rsp+3D0h+var_390], 4
0x1800247e9  lea     rax, [rsp+3D0h+var_360]
0x1800247ee  mov     [rsp+3D0h+var_398], rax
0x1800247f3  lea     r9, aEnumeratorClon; "Enumerator::Clone"
0x1800247fa  lea     rax, [rbp+2D0h+psaboundNew]
0x1800247fe  mov     [rsp+3D0h+var_3A0], 8
0x180024807  mov     [rsp+3D0h+var_3A8], rax
0x18002480c  lea     rdx, PLA_EVENT_METHOD
0x180024813  mov     r8d, 3
0x180024819  mov     [rsp+3D0h+var_3B0], 12h
0x180024822  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180024829  call    EventingWriteEvent
0x18002482e  jmp     loc_1800243CB
0x180024833  mov     rax, rdx
0x180024836  and     rax, r8
0x180024839  cmp     rdx, rax
0x18002483c  jnz     loc_18002442C
0x180024842  mov     [rsp+3D0h+var_380], 8
0x18002484b  lea     rax, [rbp+2D0h+psaboundNew]
0x18002484f  mov     [rsp+3D0h+var_388], rax
0x180024854  lea     r9, byte_180147320
0x18002485b  mov     [rsp+3D0h+var_390], 8
0x180024864  lea     rax, [rbp+2D0h+ppsaOut]
0x180024868  mov     [rsp+3D0h+var_398], rax
0x18002486d  lea     rdx, PLA_EVENT_NEW
0x180024874  lea     rax, [rsp+3D0h+var_360]
0x180024879  mov     [rsp+3D0h+var_3A0], 4
0x180024882  mov     [rsp+3D0h+var_3A8], rax
0x180024887  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002488e  mov     r8d, 4
0x180024894  mov     [rsp+3D0h+var_3B0], 1
0x18002489d  call    EventingWriteEvent
0x1800248a2  mov     rdx, cs:qword_180169748
0x1800248a9  mov     ecx, dword ptr cs:xmmword_180169738
0x1800248af  jmp     loc_18002442C
0x1800248b4  mov     rcx, cs:qword_180169748
0x1800248bb  and     rcx, r15
0x1800248be  cmp     cs:qword_180169748, rcx
0x1800248c5  jnz     loc_180024477
0x1800248cb  test    rax, rax
0x1800248ce  jz      loc_180024C65
0x1800248d4  mov     rcx, r12
0x1800248d7  inc     rcx
0x1800248da  cmp     [rax+rcx], sil
0x1800248de  jnz     short loc_1800248D7
0x1800248e0  mov     ecx, ecx
0x1800248e2  inc     rcx
0x1800248e5  jmp     loc_180024C68
0x1800248ea  mov     rax, cs:qword_180169748
0x1800248f1  and     rax, rdx
0x1800248f4  cmp     cs:qword_180169748, rax
0x1800248fb  jnz     loc_1800244DC
0x180024901  mov     [rsp+3D0h+var_390], 4
0x18002490a  lea     rax, [rsp+3D0h+var_360]
0x18002490f  mov     [rsp+3D0h+var_398], rax
0x180024914  lea     r9, aEnumeratorGetA; "Enumerator::get_Array"
0x18002491b  lea     rax, [rsp+3D0h+var_358]
0x180024920  mov     [rsp+3D0h+var_3A0], 8
0x180024929  mov     [rsp+3D0h+var_3A8], rax
0x18002492e  lea     rdx, PLA_EVENT_METHOD
0x180024935  mov     r8d, 3
0x18002493b  mov     [rsp+3D0h+var_3B0], 16h
0x180024944  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18002494b  call    EventingWriteEvent
  ... truncated ...
```
