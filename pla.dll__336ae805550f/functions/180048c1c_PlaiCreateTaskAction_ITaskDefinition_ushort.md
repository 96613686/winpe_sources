# PlaiCreateTaskAction(ITaskDefinition *,ushort *)

- ea: `0x180048c1c`
- end: `0x180049466`
- name: `?PlaiCreateTaskAction@@YAJPEAUITaskDefinition@@PEAG@Z`
- size: `2122`
- prototype: `__int64 __fastcall(struct ITaskDefinition *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d8af4`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180015f98`
- `0x180018420`
- `0x1800198b0`
- `0x180048c1c`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180049017`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180049017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800493dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800493dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048c7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180048c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048c6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180048c6b`
- `OLEAUT32!__imp_SysAllocString` at `0x18004909b`
- `OLEAUT32!__imp_SysAllocString` at `0x18004909b`

## string_xrefs

- `0x180048dc0`: `PlaiCreateTaskAction`
- `0x180048ea0`: `PlaiCreateTaskAction`
- `0x180049376`: `PlaiCreateTaskAction`

## pseudocode

```c
__int64 __fastcall PlaiCreateTaskAction(struct ITaskDefinition *a1, unsigned __int16 *a2)
{
  OLECHAR *v3; // r12
  OLECHAR *v4; // r15
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v7; // rax
  int v8; // edx
  unsigned __int16 *v9; // r14
  unsigned __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rax
  BSTR v21; // rax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  const char *v27; // rdx
  int v28; // r8d
  unsigned __int16 *v29; // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  int v34; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  __int64 v37; // [rsp+88h] [rbp-78h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h] BYREF
  LPOLESTR lpsz; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v40; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v41[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v42[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v43[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v44[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v45[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v46[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v47[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v48[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v49[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v50[64]; // [rsp+530h] [rbp+430h] BYREF

  lpsz = 0;
  v3 = 0;
  v4 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  ProcessHeap = GetProcessHeap();
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
  v8 = xmmword_180169738;
  v9 = v7;
  v10 = qword_180169748;
  v35 = 2048;
  v40 = v7;
  v34 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ALLOC, 4, byte_180147320, 1, &v34, 4, &v40, 8);
    v10 = qword_180169748;
    v8 = xmmword_180169738;
  }
  if ( v9 )
  {
    v13 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))a1->lpVtbl->get_Actions)(a1, &v36);
    v11 = v13;
    if ( v13 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 96LL))(v36, 5, &v37);
      v11 = v15;
      if ( v15 >= 0 )
      {
        v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(v37, &IID_IComHandlerAction, &v38);
        v11 = v17;
        if ( v17 >= 0 )
        {
          v19 = StringFromCLSID(&CLSID_PlaTaskHost, &lpsz);
          v11 = v19;
          if ( v19 >= 0 )
          {
            v21 = SysAllocString(lpsz);
            v3 = v21;
            if ( v21 )
            {
              v23 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v38 + 88LL))(v38, v21);
              v11 = v23;
              if ( v23 >= 0 )
              {
                v25 = StringCchPrintfW(v9, 0x400u, L"%s|$(Arg0)", a2);
                v11 = v25;
                if ( v25 >= 0 )
                {
                  PlaiFreeString(0);
                  v29 = PlaiAllocStringEx(v9, v27, v28);
                  v4 = v29;
                  if ( v29 )
                  {
                    v31 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v38 + 104LL))(v38, v29);
                    v11 = v31;
                    if ( v31 >= 0 )
                      goto LABEL_75;
                    LODWORD(v35) = 0;
                    v34 = v31;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_75;
                    }
                    PlaiWhoAmI(v50, 0x4000000000000800uLL);
                    v32 = -1;
                    do
                      ++v32;
                    while ( v50[v32] );
                  }
                  else
                  {
                    v11 = -2147024882;
                    v34 = -2147024882;
                    LODWORD(v35) = 0;
                    if ( !(_DWORD)xmmword_180169738
                      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                    {
                      goto LABEL_75;
                    }
                    PlaiWhoAmI(v49, 0x4000000000000800uLL);
                    v30 = -1;
                    do
                      ++v30;
                    while ( v49[v30] );
                  }
                }
                else
                {
                  LODWORD(v35) = 0;
                  v34 = v25;
                  if ( !(_DWORD)xmmword_180169738
                    || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                    || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                  {
                    goto LABEL_75;
                  }
                  PlaiWhoAmI(v48, 0x4000000000000800uLL);
                  v26 = -1;
                  do
                    ++v26;
                  while ( v48[v26] );
                }
              }
              else
              {
                LODWORD(v35) = 0;
                v34 = v23;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_75;
                }
                PlaiWhoAmI(v47, 0x4000000000000800uLL);
                v24 = -1;
                do
                  ++v24;
                while ( v47[v24] );
              }
            }
            else
            {
              v11 = -2147024882;
              v34 = -2147024882;
              LODWORD(v35) = 0;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_75;
              }
              PlaiWhoAmI(v46, 0x4000000000000800uLL);
              v22 = -1;
              do
                ++v22;
              while ( v46[v22] );
            }
          }
          else
          {
            LODWORD(v35) = 0;
            v34 = v19;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_75;
            }
            PlaiWhoAmI(v45, 0x4000000000000800uLL);
            v20 = -1;
            do
              ++v20;
            while ( v45[v20] );
          }
        }
        else
        {
          LODWORD(v35) = 0;
          v34 = v17;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_75;
          }
          PlaiWhoAmI(v44, 0x4000000000000800uLL);
          v18 = -1;
          do
            ++v18;
          while ( v44[v18] );
        }
      }
      else
      {
        LODWORD(v35) = 0;
        v34 = v15;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_75;
        }
        PlaiWhoAmI(v43, 0x4000000000000800uLL);
        v16 = -1;
        do
          ++v16;
        while ( v43[v16] );
      }
    }
    else
    {
      LODWORD(v35) = 0;
      v34 = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_75;
      }
      PlaiWhoAmI(v42, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v42[v14] );
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v34, 4, byte_180147320, 1, &v35, 4);
LABEL_75:
    PlaiFree(v9, 1);
    goto LABEL_76;
  }
  v34 = 0;
  LODWORD(v35) = -2147024882;
  v11 = -2147024882;
  if ( v8 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v10 == (v10 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v41, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v41[v12] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v35, 4, byte_180147320, 1, &v34, 4);
  }
LABEL_76:
  CoTaskMemFree(lpsz);
  PlaiFreeString(v3);
  PlaiFreeString(v4);
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  return v11;
}

```

## disassembly

```asm
0x180048c1c  mov     [rsp-8+arg_10], rbx
0x180048c21  push    rbp
0x180048c22  push    rsi
0x180048c23  push    rdi
0x180048c24  push    r12
0x180048c26  push    r13
0x180048c28  push    r14
0x180048c2a  push    r15
0x180048c2c  lea     rbp, [rsp-4C0h]
0x180048c34  sub     rsp, 5C0h
0x180048c3b  mov     rax, cs:__security_cookie
0x180048c42  xor     rax, rsp
0x180048c45  mov     [rbp+4F0h+var_40], rax
0x180048c4c  xor     r13d, r13d
0x180048c4f  mov     rdi, rdx
0x180048c52  mov     [rbp+4F0h+lpsz], r13
0x180048c56  mov     r12d, r13d
0x180048c59  mov     r15d, r13d
0x180048c5c  mov     [rbp+4F0h+var_570], r13
0x180048c60  mov     [rbp+4F0h+var_568], r13
0x180048c64  mov     rbx, rcx
0x180048c67  mov     [rbp+4F0h+var_560], r13
0x180048c6b  call    cs:__imp_GetProcessHeap
0x180048c71  mov     esi, 800h
0x180048c76  xor     edx, edx; dwFlags
0x180048c78  mov     rcx, rax; hHeap
0x180048c7b  mov     r8d, esi; dwBytes
0x180048c7e  call    cs:__imp_HeapAlloc
0x180048c84  mov     edx, dword ptr cs:xmmword_180169738
0x180048c8a  mov     r14, rax
0x180048c8d  mov     rcx, cs:qword_180169748
0x180048c94  mov     [rsp+5F0h+var_578], rsi
0x180048c99  lea     esi, [r13+4]
0x180048c9d  mov     [rbp+4F0h+var_550], rax
0x180048ca1  mov     [rsp+5F0h+var_580], r13d
0x180048ca6  test    edx, edx
0x180048ca8  jz      loc_180048D2E
0x180048cae  mov     r8, 4000000000000200h
0x180048cb8  test    qword ptr cs:xmmword_180169738+8, r8
0x180048cbf  jz      short loc_180048D2E
0x180048cc1  mov     rax, rcx
0x180048cc4  and     rax, r8
0x180048cc7  cmp     rcx, rax
0x180048cca  jnz     short loc_180048D2E
0x180048ccc  lea     ecx, [rsi+4]
0x180048ccf  mov     r8d, esi
0x180048cd2  mov     [rsp+5F0h+var_5A0], rcx
0x180048cd7  lea     rax, [rsp+5F0h+var_578]
0x180048cdc  mov     [rsp+5F0h+var_5A8], rax
0x180048ce1  lea     r9, byte_180147320
0x180048ce8  mov     [rsp+5F0h+var_5B0], rcx
0x180048ced  lea     rax, [rbp+4F0h+var_550]
0x180048cf1  mov     [rsp+5F0h+var_5B8], rax
0x180048cf6  lea     rdx, PLA_EVENT_ALLOC
0x180048cfd  lea     rax, [rsp+5F0h+var_580]
0x180048d02  mov     [rsp+5F0h+var_5C0], rsi
0x180048d07  mov     [rsp+5F0h+var_5C8], rax
0x180048d0c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180048d13  mov     [rsp+5F0h+var_5D0], 1
0x180048d1c  call    EventingWriteEvent
0x180048d21  mov     rcx, cs:qword_180169748
0x180048d28  mov     edx, dword ptr cs:xmmword_180169738
0x180048d2e  test    r14, r14
0x180048d31  jnz     loc_180048E06
0x180048d37  mov     [rsp+5F0h+var_580], r13d
0x180048d3c  mov     eax, 8007000Eh
0x180048d41  mov     dword ptr [rsp+5F0h+var_578], eax
0x180048d45  mov     ebx, eax
0x180048d47  test    edx, edx
0x180048d49  jz      loc_1800493D9
0x180048d4f  mov     rdx, 4000000000000800h; unsigned __int64
0x180048d59  test    qword ptr cs:xmmword_180169738+8, rdx
0x180048d60  jz      loc_1800493D9
0x180048d66  mov     rax, rcx
0x180048d69  and     rax, rdx
0x180048d6c  cmp     rcx, rax
0x180048d6f  jnz     loc_1800493D9
0x180048d75  lea     rcx, [rbp+4F0h+var_540]; unsigned __int16 *
0x180048d79  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180048d7e  lea     rcx, [rbp+4F0h+var_540]
0x180048d82  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048d86  inc     rax
0x180048d89  cmp     [rcx+rax*2], r13w
0x180048d8e  jnz     short loc_180048D86
0x180048d90  lea     ecx, [rax+rax]
0x180048d93  mov     r8d, 5
0x180048d99  add     rcx, 2
0x180048d9d  lea     rax, [rbp+4F0h+var_540]
0x180048da1  mov     [rsp+5F0h+var_590], rcx
0x180048da6  lea     r9, [rsp+5F0h+var_578]
0x180048dab  mov     [rsp+5F0h+var_598], rax
0x180048db0  lea     rdx, PLA_EVENT_ERROR
0x180048db7  mov     [rsp+5F0h+var_5A0], 15h
0x180048dc0  lea     rax, aPlaicreatetask; "PlaiCreateTaskAction"
0x180048dc7  mov     [rsp+5F0h+var_5A8], rax
0x180048dcc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180048dd3  mov     [rsp+5F0h+var_5B0], rsi
0x180048dd8  lea     rax, [rsp+5F0h+var_580]
0x180048ddd  mov     [rsp+5F0h+var_5B8], rax
0x180048de2  lea     rax, byte_180147320
0x180048de9  mov     [rsp+5F0h+var_5C0], 1
0x180048df2  mov     [rsp+5F0h+var_5C8], rax
0x180048df7  mov     [rsp+5F0h+var_5D0], rsi
0x180048dfc  call    EventingWriteEvent
0x180048e01  jmp     loc_1800493D9
0x180048e06  mov     rax, [rbx]
0x180048e09  lea     rdx, [rbp+4F0h+var_570]
0x180048e0d  mov     rcx, rbx
0x180048e10  mov     rax, [rax+88h]
0x180048e17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e1c  mov     ebx, eax
0x180048e1e  test    eax, eax
0x180048e20  jns     loc_180048EE3
0x180048e26  cmp     dword ptr cs:xmmword_180169738, r13d
0x180048e2d  mov     dword ptr [rsp+5F0h+var_578], r13d
0x180048e32  mov     [rsp+5F0h+var_580], eax
0x180048e36  jz      loc_1800493CC
0x180048e3c  mov     rdx, 4000000000000800h; unsigned __int64
0x180048e46  test    qword ptr cs:xmmword_180169738+8, rdx
0x180048e4d  jz      loc_1800493CC
0x180048e53  mov     rax, cs:qword_180169748
0x180048e5a  and     rax, rdx
0x180048e5d  cmp     cs:qword_180169748, rax
0x180048e64  jnz     loc_1800493CC
0x180048e6a  lea     rcx, [rbp+4F0h+var_4C0]; unsigned __int16 *
0x180048e6e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180048e73  lea     rcx, [rbp+4F0h+var_4C0]
0x180048e77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048e7b  inc     rax
0x180048e7e  cmp     [rcx+rax*2], r13w
0x180048e83  jnz     short loc_180048E7B
0x180048e85  lea     ecx, [rax+rax]
0x180048e88  mov     r8d, 5
0x180048e8e  lea     rax, [rbp+4F0h+var_4C0]
0x180048e92  add     rcx, 2
0x180048e96  mov     [rsp+5F0h+var_590], rcx
0x180048e9b  mov     [rsp+5F0h+var_598], rax
0x180048ea0  lea     rax, aPlaicreatetask; "PlaiCreateTaskAction"
0x180048ea7  mov     [rsp+5F0h+var_5A0], 15h
0x180048eb0  mov     [rsp+5F0h+var_5A8], rax
0x180048eb5  lea     rax, [rsp+5F0h+var_578]
0x180048eba  mov     [rsp+5F0h+var_5B0], rsi
0x180048ebf  mov     [rsp+5F0h+var_5B8], rax
0x180048ec4  lea     rax, byte_180147320
0x180048ecb  mov     [rsp+5F0h+var_5C0], 1
0x180048ed4  mov     [rsp+5F0h+var_5C8], rax
0x180048ed9  mov     [rsp+5F0h+var_5D0], rsi
0x180048ede  jmp     loc_1800493B4
0x180048ee3  mov     rcx, [rbp+4F0h+var_570]
0x180048ee7  lea     r8, [rbp+4F0h+var_568]
0x180048eeb  mov     esi, 5
0x180048ef0  mov     edx, esi
0x180048ef2  mov     rax, [rcx]
0x180048ef5  mov     rax, [rax+60h]
0x180048ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048efe  mov     ebx, eax
0x180048f00  test    eax, eax
0x180048f02  jns     short loc_180048F78
0x180048f04  cmp     dword ptr cs:xmmword_180169738, r13d
0x180048f0b  mov     dword ptr [rsp+5F0h+var_578], r13d
0x180048f10  mov     [rsp+5F0h+var_580], eax
0x180048f14  jz      loc_1800493CC
0x180048f1a  mov     rdx, 4000000000000800h; unsigned __int64
0x180048f24  test    qword ptr cs:xmmword_180169738+8, rdx
0x180048f2b  jz      loc_1800493CC
0x180048f31  mov     rax, cs:qword_180169748
0x180048f38  and     rax, rdx
0x180048f3b  cmp     cs:qword_180169748, rax
0x180048f42  jnz     loc_1800493CC
0x180048f48  lea     rcx, [rbp+4F0h+var_440]; unsigned __int16 *
0x180048f4f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180048f54  lea     rcx, [rbp+4F0h+var_440]
0x180048f5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048f5f  inc     rax
0x180048f62  cmp     [rcx+rax*2], r13w
0x180048f67  jnz     short loc_180048F5F
0x180048f69  lea     ecx, [rax+rax]
0x180048f6c  lea     rax, [rbp+4F0h+var_440]
0x180048f73  jmp     loc_180049360
0x180048f78  mov     rcx, [rbp+4F0h+var_568]
0x180048f7c  lea     r8, [rbp+4F0h+var_560]
0x180048f80  lea     rdx, IID_IComHandlerAction
0x180048f87  mov     rax, [rcx]
0x180048f8a  mov     rax, [rax]
0x180048f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f92  mov     ebx, eax
0x180048f94  test    eax, eax
0x180048f96  jns     short loc_18004900C
0x180048f98  cmp     dword ptr cs:xmmword_180169738, r13d
0x180048f9f  mov     dword ptr [rsp+5F0h+var_578], r13d
0x180048fa4  mov     [rsp+5F0h+var_580], eax
0x180048fa8  jz      loc_1800493CC
0x180048fae  mov     rdx, 4000000000000800h; unsigned __int64
0x180048fb8  test    qword ptr cs:xmmword_180169738+8, rdx
0x180048fbf  jz      loc_1800493CC
0x180048fc5  mov     rax, cs:qword_180169748
0x180048fcc  and     rax, rdx
0x180048fcf  cmp     cs:qword_180169748, rax
0x180048fd6  jnz     loc_1800493CC
0x180048fdc  lea     rcx, [rbp+4F0h+var_3C0]; unsigned __int16 *
0x180048fe3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180048fe8  lea     rcx, [rbp+4F0h+var_3C0]
0x180048fef  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048ff3  inc     rax
0x180048ff6  cmp     [rcx+rax*2], r13w
0x180048ffb  jnz     short loc_180048FF3
0x180048ffd  lea     ecx, [rax+rax]
0x180049000  lea     rax, [rbp+4F0h+var_3C0]
0x180049007  jmp     loc_180049360
0x18004900c  lea     rdx, [rbp+4F0h+lpsz]; lplpsz
0x180049010  lea     rcx, CLSID_PlaTaskHost; rclsid
0x180049017  call    cs:__imp_StringFromCLSID
0x18004901d  mov     ebx, eax
0x18004901f  test    eax, eax
0x180049021  jns     short loc_180049097
0x180049023  cmp     dword ptr cs:xmmword_180169738, r13d
0x18004902a  mov     dword ptr [rsp+5F0h+var_578], r13d
0x18004902f  mov     [rsp+5F0h+var_580], eax
0x180049033  jz      loc_1800493CC
0x180049039  mov     rdx, 4000000000000800h; unsigned __int64
0x180049043  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004904a  jz      loc_1800493CC
0x180049050  mov     rax, cs:qword_180169748
0x180049057  and     rax, rdx
0x18004905a  cmp     cs:qword_180169748, rax
0x180049061  jnz     loc_1800493CC
0x180049067  lea     rcx, [rbp+4F0h+var_340]; unsigned __int16 *
0x18004906e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180049073  lea     rcx, [rbp+4F0h+var_340]
0x18004907a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004907e  inc     rax
0x180049081  cmp     [rcx+rax*2], r13w
0x180049086  jnz     short loc_18004907E
0x180049088  lea     ecx, [rax+rax]
0x18004908b  lea     rax, [rbp+4F0h+var_340]
0x180049092  jmp     loc_180049360
0x180049097  mov     rcx, [rbp+4F0h+lpsz]; psz
0x18004909b  call    cs:__imp_SysAllocString
0x1800490a1  mov     r12, rax
0x1800490a4  test    rax, rax
0x1800490a7  jnz     short loc_180049124
0x1800490a9  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800490b0  mov     eax, 8007000Eh
0x1800490b5  mov     ebx, eax
0x1800490b7  mov     [rsp+5F0h+var_580], eax
0x1800490bb  mov     dword ptr [rsp+5F0h+var_578], r13d
0x1800490c0  jz      loc_1800493CC
0x1800490c6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800490d0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800490d7  jz      loc_1800493CC
0x1800490dd  mov     rax, cs:qword_180169748
0x1800490e4  and     rax, rdx
0x1800490e7  cmp     cs:qword_180169748, rax
0x1800490ee  jnz     loc_1800493CC
0x1800490f4  lea     rcx, [rbp+4F0h+var_2C0]; unsigned __int16 *
0x1800490fb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180049100  lea     rcx, [rbp+4F0h+var_2C0]
0x180049107  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004910b  inc     rax
0x18004910e  cmp     [rcx+rax*2], r13w
0x180049113  jnz     short loc_18004910B
0x180049115  lea     ecx, [rax+rax]
0x180049118  lea     rax, [rbp+4F0h+var_2C0]
0x18004911f  jmp     loc_180049360
0x180049124  mov     rcx, [rbp+4F0h+var_560]
0x180049128  mov     rdx, r12
0x18004912b  mov     rax, [rcx]
0x18004912e  mov     rax, [rax+58h]
0x180049132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049137  mov     ebx, eax
0x180049139  test    eax, eax
0x18004913b  jns     short loc_1800491B1
0x18004913d  cmp     dword ptr cs:xmmword_180169738, r13d
0x180049144  mov     dword ptr [rsp+5F0h+var_578], r13d
0x180049149  mov     [rsp+5F0h+var_580], eax
0x18004914d  jz      loc_1800493CC
0x180049153  mov     rdx, 4000000000000800h; unsigned __int64
0x18004915d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180049164  jz      loc_1800493CC
0x18004916a  mov     rax, cs:qword_180169748
0x180049171  and     rax, rdx
0x180049174  cmp     cs:qword_180169748, rax
0x18004917b  jnz     loc_1800493CC
0x180049181  lea     rcx, [rbp+4F0h+var_240]; unsigned __int16 *
0x180049188  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004918d  lea     rcx, [rbp+4F0h+var_240]
0x180049194  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049198  inc     rax
0x18004919b  cmp     [rcx+rax*2], r13w
0x1800491a0  jnz     short loc_180049198
0x1800491a2  lea     ecx, [rax+rax]
0x1800491a5  lea     rax, [rbp+4F0h+var_240]
0x1800491ac  jmp     loc_180049360
0x1800491b1  mov     r9, rdi
0x1800491b4  lea     r8, aSArg0; "%s|$(Arg0)"
0x1800491bb  mov     edx, 400h; unsigned __int64
0x1800491c0  mov     rcx, r14; unsigned __int16 *
0x1800491c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800491c8  mov     ebx, eax
0x1800491ca  test    eax, eax
  ... truncated ...
```
