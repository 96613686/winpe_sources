# AccWrap_AddIAccProp::QueryInterface(_GUID const &,void * *)

- ea: `0x180001ec0`
- end: `0x180002480`
- name: `?QueryInterface@AccWrap_AddIAccProp@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `1472`
- prototype: `__int64 __fastcall(AccWrap_AddIAccProp *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180024180`
- `0x180024190`
- `0x1800241a0`
- `0x1800241b0`

## callees

- `0x180001ec0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002432`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800023b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002432`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002475`

## pseudocode

```c
__int64 __fastcall AccWrap_AddIAccProp::QueryInterface(AccWrap_AddIAccProp *this, const struct _GUID *a2, void **a3)
{
  AccWrap_AddIAccProp *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rax
  int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, char *); // rcx
  int v10; // esi
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, GUID *, char *); // rcx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, GUID *, char *); // rcx
  int v25; // eax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, char *); // rcx
  __int64 v27; // rcx
  __int64 v28; // r15
  unsigned int (__fastcall **v29)(_QWORD, GUID *, __int64 *); // rax
  int v30; // ebx
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // r15
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  int v35; // r15d
  __int64 v36; // rbx
  int v37; // r12d
  __int64 v38; // [rsp+30h] [rbp-40h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  __int64 v40; // [rsp+40h] [rbp-30h] BYREF
  __int64 v41; // [rsp+48h] [rbp-28h] BYREF
  __int64 v42; // [rsp+50h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-18h] BYREF
  int v44; // [rsp+B0h] [rbp+40h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // [rsp+B8h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = this;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v6 )
    goto LABEL_16;
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IAccessible.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IAccessible.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IAccessible.Data4;
  if ( !v7 )
    goto LABEL_99;
  v14 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
    v14 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IDispatch.Data4;
  if ( !v14 )
  {
LABEL_99:
    if ( !*((_QWORD *)this + 8) )
    {
      v8 = *((_DWORD *)this + 26);
      if ( (v8 & 1) != 0 )
      {
        v10 = -2147467262;
        goto LABEL_11;
      }
      v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 6);
      *((_DWORD *)v5 + 26) = v8 | 1;
      v10 = (**v9)(v9, &IID_IAccessible, (char *)v5 + 64);
      if ( v10 < 0 )
      {
        *((_QWORD *)v5 + 8) = 0;
LABEL_11:
        v11 = *(_QWORD *)IID_IAccIdentity.Data4;
        v12 = *(_QWORD *)&IID_IAccIdentity.Data1;
        goto LABEL_12;
      }
      if ( !*((_QWORD *)v5 + 8) )
        goto LABEL_92;
    }
    this = v5;
    goto LABEL_16;
  }
  v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IEnumVARIANT.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IEnumVARIANT.Data1 )
    v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IEnumVARIANT.Data4;
  if ( !v15 )
  {
    if ( !*((_QWORD *)this + 9) )
    {
      v21 = *((_DWORD *)this + 26);
      if ( (v21 & 2) != 0 )
      {
        v10 = -2147467262;
        goto LABEL_11;
      }
      v22 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 6);
      *((_DWORD *)v5 + 26) = v21 | 2;
      v10 = (**v22)(v22, &IID_IEnumVARIANT, (char *)v5 + 72);
      if ( v10 < 0 )
      {
        *((_QWORD *)v5 + 9) = 0;
        goto LABEL_11;
      }
      if ( !*((_QWORD *)v5 + 9) )
        goto LABEL_92;
    }
    this = (AccWrap_AddIAccProp *)((char *)v5 + 16);
    if ( !v5 )
      this = 0;
    goto LABEL_16;
  }
  v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IOleWindow.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IOleWindow.Data1 )
    v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IOleWindow.Data4;
  if ( !v16 )
  {
    if ( !*((_QWORD *)this + 10) )
    {
      v23 = *((_DWORD *)this + 26);
      if ( (v23 & 4) != 0 )
      {
        v10 = -2147467262;
        goto LABEL_11;
      }
      v24 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 6);
      *((_DWORD *)v5 + 26) = v23 | 4;
      v10 = (**v24)(v24, &IID_IOleWindow, (char *)v5 + 80);
      if ( v10 < 0 )
      {
        *((_QWORD *)v5 + 10) = 0;
        goto LABEL_11;
      }
      if ( !*((_QWORD *)v5 + 10) )
        goto LABEL_92;
    }
    this = (AccWrap_AddIAccProp *)((char *)v5 + 8);
    if ( !v5 )
      this = 0;
    goto LABEL_16;
  }
  v17 = *(_QWORD *)&a2->Data1;
  v12 = *(_QWORD *)&IID_IAccIdentity.Data1;
  v11 = *(_QWORD *)IID_IAccIdentity.Data4;
  v18 = v17 - *(_QWORD *)&IID_IAccIdentity.Data1;
  if ( !v18 )
    v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IAccIdentity.Data4;
  if ( !v18 )
  {
    if ( *((_QWORD *)v5 + 11) )
      goto LABEL_55;
    v25 = *((_DWORD *)v5 + 26);
    if ( (v25 & 8) != 0 )
    {
      v10 = -2147467262;
LABEL_12:
      if ( v10 != -2147467262 )
        return (unsigned int)v10;
LABEL_34:
      v20 = *(_QWORD *)&a2->Data1 - v12;
      if ( *(_QWORD *)&a2->Data1 == v12 )
        v20 = *(_QWORD *)a2->Data4 - v11;
      if ( v20 )
        return (unsigned int)v10;
      if ( *((_DWORD *)v5 + 32) )
        goto LABEL_38;
      v27 = *((_QWORD *)v5 + 8);
      *((_DWORD *)v5 + 32) = 1;
      v45 = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v27 + 56LL))(
             v27,
             &v45) )
      {
        goto LABEL_38;
      }
      v28 = (__int64)v45;
      if ( !v45 )
        goto LABEL_38;
      v29 = (unsigned int (__fastcall **)(_QWORD, GUID *, __int64 *))*v45;
      v38 = 0;
      if ( (*v29)(v45, &IID_IServiceProvider, &v38)
        || !v38
        || (v42 = 0,
            v30 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v38 + 24LL))(
                    v38,
                    &IIS_AccWrapBase_GetIUnknown,
                    &IID_IUnknown,
                    &v42),
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38),
            v30)
        || !v42 )
      {
        v28 = (*(__int64 (__fastcall **)(AccWrap_AddIAccProp *, __int64, __int64))(*(_QWORD *)v5 + 232LL))(v5, v28, 1);
        if ( !v28 )
        {
          v31 = v45;
          goto LABEL_65;
        }
      }
      else
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      }
      v39 = 0;
      (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v28)(v28, &IID_IDispatch, &v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v45)[2])(v45);
      v31 = v39;
      v45 = v39;
LABEL_65:
      if ( v31 )
      {
        v40 = 0;
        v32 = (**v31)(v31, &IID_IServiceProvider, &v40);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v45)[2])(v45);
        if ( !v32 )
        {
          if ( v40 )
          {
            v41 = 0;
            v33 = (*(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v40 + 24LL))(
                    v40,
                    &IIS_AccWrapBase_GetIUnknown,
                    &IID_IAccIdentity,
                    &v41);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
            if ( !v33 )
            {
              if ( v41 )
              {
                pv = 0;
                v44 = 0;
                v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, int *))(*(_QWORD *)v41 + 24LL))(
                        v41,
                        0,
                        &pv,
                        &v44);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                if ( !v34 )
                {
                  if ( pv )
                  {
                    if ( v44 == 16 && *(_DWORD *)pv == -2147483647 )
                    {
                      v35 = *((_DWORD *)pv + 3);
                      v36 = *((int *)pv + 1);
                      v37 = *((_DWORD *)pv + 2);
                      CoTaskMemFree(pv);
                      if ( v36 && !v37 && !v35 )
                        *((_QWORD *)v5 + 15) = v36;
                    }
                    else
                    {
                      CoTaskMemFree(pv);
                    }
                  }
                }
              }
            }
          }
        }
      }
LABEL_38:
      if ( *((_QWORD *)v5 + 15) )
      {
        *a3 = (char *)v5 + 24;
        goto LABEL_17;
      }
      return (unsigned int)v10;
    }
    v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)v5 + 6);
    *((_DWORD *)v5 + 26) = v25 | 8;
    v10 = (**v26)(v26, &IID_IAccIdentity, (char *)v5 + 88);
    if ( v10 < 0 )
    {
      *((_QWORD *)v5 + 11) = 0;
      goto LABEL_11;
    }
    if ( *((_QWORD *)v5 + 11) )
    {
LABEL_55:
      this = (AccWrap_AddIAccProp *)((char *)v5 + 24);
      if ( !v5 )
        this = 0;
      goto LABEL_16;
    }
LABEL_92:
    v10 = -2147467259;
    goto LABEL_11;
  }
  v19 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IServiceProvider.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IServiceProvider.Data1 )
    v19 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IServiceProvider.Data4;
  if ( v19 )
  {
    v10 = -2147467262;
    goto LABEL_34;
  }
  this = (AccWrap_AddIAccProp *)((char *)v5 + 32);
  if ( !v5 )
    this = 0;
LABEL_16:
  *a3 = this;
LABEL_17:
  (*(void (__fastcall **)(AccWrap_AddIAccProp *))(*(_QWORD *)v5 + 8LL))(v5);
  return 0;
}

```

## disassembly

```asm
0x180001ec0  push    rbp
0x180001ec2  push    rbx
0x180001ec3  push    rdi
0x180001ec4  push    r13
0x180001ec6  push    r14
0x180001ec8  mov     rbp, rsp
0x180001ecb  sub     rsp, 70h
0x180001ecf  xor     r13d, r13d
0x180001ed2  mov     r14, r8
0x180001ed5  mov     [r8], r13
0x180001ed8  mov     rbx, rdx
0x180001edb  mov     rax, [rdx]
0x180001ede  mov     rdi, rcx
0x180001ee1  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x180001ee8  jnz     short loc_180001EF5
0x180001eea  mov     rax, [rdx+8]
0x180001eee  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180001ef5  mov     [rsp+70h+arg_0], rsi
0x180001efd  mov     [rsp+70h+var_10], r15
0x180001f02  test    rax, rax
0x180001f05  jz      loc_180001F97
0x180001f0b  mov     rax, [rdx]
0x180001f0e  sub     rax, qword ptr cs:IID_IAccessible.Data1
0x180001f15  jnz     short loc_180001F22
0x180001f17  mov     rax, [rdx+8]
0x180001f1b  sub     rax, qword ptr cs:IID_IAccessible.Data4
0x180001f22  test    rax, rax
0x180001f25  jnz     loc_180001FC5
0x180001f2b  cmp     [rcx+40h], r13
0x180001f2f  jnz     loc_180002185
0x180001f35  mov     eax, [rcx+68h]
0x180001f38  test    al, 1
0x180001f3a  jnz     loc_18000246B
0x180001f40  mov     rcx, [rcx+30h]
0x180001f44  lea     r8, [rdi+40h]
0x180001f48  or      eax, 1
0x180001f4b  lea     rdx, IID_IAccessible
0x180001f52  mov     [rdi+68h], eax
0x180001f55  mov     rax, [rcx]
0x180001f58  mov     rax, [rax]
0x180001f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f60  mov     esi, eax
0x180001f62  test    eax, eax
0x180001f64  jns     loc_18000217B
0x180001f6a  mov     [rdi+40h], r13
0x180001f6e  mov     rcx, qword ptr cs:IID_IAccIdentity.Data4
0x180001f75  mov     rdx, qword ptr cs:IID_IAccIdentity.Data1
0x180001f7c  cmp     esi, 80004002h
0x180001f82  jz      loc_180002070
0x180001f88  mov     eax, esi
0x180001f8a  jmp     short loc_180001FAC
0x180001f8c  test    rdi, rdi
0x180001f8f  lea     rcx, [rdi+20h]
0x180001f93  cmovz   rcx, r13
0x180001f97  mov     [r14], rcx
0x180001f9a  mov     rax, [rdi]
0x180001f9d  mov     rcx, rdi
0x180001fa0  mov     rax, [rax+8]
0x180001fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fa9  mov     eax, r13d
0x180001fac  mov     r15, [rsp+70h+var_10]
0x180001fb1  mov     rsi, [rsp+70h+arg_0]
0x180001fb9  add     rsp, 70h
0x180001fbd  pop     r14
0x180001fbf  pop     r13
0x180001fc1  pop     rdi
0x180001fc2  pop     rbx
0x180001fc3  pop     rbp
0x180001fc4  retn
0x180001fc5  mov     rax, [rdx]
0x180001fc8  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180001fcf  jnz     short loc_180001FDC
0x180001fd1  mov     rax, [rdx+8]
0x180001fd5  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180001fdc  test    rax, rax
0x180001fdf  jz      loc_180001F2B
0x180001fe5  mov     rax, [rdx]
0x180001fe8  sub     rax, qword ptr cs:IID_IEnumVARIANT.Data1
0x180001fef  jnz     short loc_180001FFC
0x180001ff1  mov     rax, [rdx+8]
0x180001ff5  sub     rax, qword ptr cs:IID_IEnumVARIANT.Data4
0x180001ffc  test    rax, rax
0x180001fff  jz      loc_1800020AB
0x180002005  mov     rax, [rdx]
0x180002008  sub     rax, qword ptr cs:IID_IOleWindow.Data1
0x18000200f  jnz     short loc_18000201C
0x180002011  mov     rax, [rdx+8]
0x180002015  sub     rax, qword ptr cs:IID_IOleWindow.Data4
0x18000201c  test    rax, rax
0x18000201f  jz      loc_1800020F3
0x180002025  mov     rax, [rdx]
0x180002028  mov     rdx, qword ptr cs:IID_IAccIdentity.Data1
0x18000202f  mov     rcx, qword ptr cs:IID_IAccIdentity.Data4
0x180002036  sub     rax, rdx
0x180002039  jnz     short loc_180002042
0x18000203b  mov     rax, [rbx+8]
0x18000203f  sub     rax, rcx
0x180002042  test    rax, rax
0x180002045  jz      loc_18000213B
0x18000204b  mov     rax, [rbx]
0x18000204e  sub     rax, qword ptr cs:IID_IServiceProvider.Data1
0x180002055  jnz     short loc_180002062
0x180002057  mov     rax, [rbx+8]
0x18000205b  sub     rax, qword ptr cs:IID_IServiceProvider.Data4
0x180002062  test    rax, rax
0x180002065  jz      loc_180001F8C
0x18000206b  mov     esi, 80004002h
0x180002070  mov     rax, [rbx]
0x180002073  sub     rax, rdx
0x180002076  jnz     short loc_18000207F
0x180002078  mov     rax, [rbx+8]
0x18000207c  sub     rax, rcx
0x18000207f  test    rax, rax
0x180002082  jnz     loc_180001F88
0x180002088  cmp     [rdi+80h], r13d
0x18000208f  jz      loc_1800021A7
0x180002095  cmp     [rdi+78h], r13
0x180002099  jz      loc_180001F88
0x18000209f  lea     rax, [rdi+18h]
0x1800020a3  mov     [r14], rax
0x1800020a6  jmp     loc_180001F9A
0x1800020ab  cmp     [rcx+48h], r13
0x1800020af  jnz     loc_1800023DC
0x1800020b5  mov     eax, [rcx+68h]
0x1800020b8  test    al, 2
0x1800020ba  jnz     loc_180002457
0x1800020c0  mov     rcx, [rcx+30h]
0x1800020c4  lea     r8, [rdi+48h]
0x1800020c8  or      eax, 2
0x1800020cb  lea     rdx, IID_IEnumVARIANT
0x1800020d2  mov     [rdi+68h], eax
0x1800020d5  mov     rax, [rcx]
0x1800020d8  mov     rax, [rax]
0x1800020db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e0  mov     esi, eax
0x1800020e2  test    eax, eax
0x1800020e4  jns     loc_1800023D6
0x1800020ea  mov     [rdi+48h], r13
0x1800020ee  jmp     loc_180001F6E
0x1800020f3  cmp     [rcx+50h], r13
0x1800020f7  jnz     loc_180002419
0x1800020fd  mov     eax, [rcx+68h]
0x180002100  test    al, 4
0x180002102  jnz     loc_180002461
0x180002108  mov     rcx, [rcx+30h]
0x18000210c  lea     r8, [rdi+50h]
0x180002110  or      eax, 4
0x180002113  lea     rdx, IID_IOleWindow
0x18000211a  mov     [rdi+68h], eax
0x18000211d  mov     rax, [rcx]
0x180002120  mov     rax, [rax]
0x180002123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002128  mov     esi, eax
0x18000212a  test    eax, eax
0x18000212c  jns     loc_180002447
0x180002132  mov     [rdi+50h], r13
0x180002136  jmp     loc_180001F6E
0x18000213b  cmp     [rdi+58h], r13
0x18000213f  jnz     short loc_180002197
0x180002141  mov     eax, [rdi+68h]
0x180002144  test    al, 8
0x180002146  jnz     loc_18000243D
0x18000214c  mov     rcx, [rdi+30h]
0x180002150  lea     r8, [rdi+58h]
0x180002154  or      eax, 8
0x180002157  lea     rdx, IID_IAccIdentity
0x18000215e  mov     [rdi+68h], eax
0x180002161  mov     rax, [rcx]
0x180002164  mov     rax, [rax]
0x180002167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000216c  mov     esi, eax
0x18000216e  test    eax, eax
0x180002170  jns     short loc_18000218D
0x180002172  mov     [rdi+58h], r13
0x180002176  jmp     loc_180001F6E
0x18000217b  cmp     [rdi+40h], r13
0x18000217f  jz      loc_18000244D
0x180002185  mov     rcx, rdi
0x180002188  jmp     loc_180001F97
0x18000218d  cmp     [rdi+58h], r13
0x180002191  jz      loc_18000244D
0x180002197  test    rdi, rdi
0x18000219a  lea     rcx, [rdi+18h]
0x18000219e  cmovz   rcx, r13
0x1800021a2  jmp     loc_180001F97
0x1800021a7  mov     rcx, [rdi+40h]
0x1800021ab  lea     rdx, [rbp+arg_18]
0x1800021af  mov     dword ptr [rdi+80h], 1
0x1800021b9  mov     [rbp+arg_18], r13
0x1800021bd  mov     rax, [rcx]
0x1800021c0  mov     rax, [rax+38h]
0x1800021c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c9  test    eax, eax
0x1800021cb  jnz     loc_180002095
0x1800021d1  mov     r15, [rbp+arg_18]
0x1800021d5  test    r15, r15
0x1800021d8  jz      loc_180002095
0x1800021de  mov     rax, [r15]
0x1800021e1  lea     r8, [rbp+var_40]
0x1800021e5  lea     rdx, IID_IServiceProvider
0x1800021ec  mov     [rbp+var_40], r13
0x1800021f0  mov     rcx, r15
0x1800021f3  mov     rax, [rax]
0x1800021f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021fb  test    eax, eax
0x1800021fd  jnz     short loc_180002244
0x1800021ff  mov     rcx, [rbp+var_40]
0x180002203  test    rcx, rcx
0x180002206  jz      short loc_180002244
0x180002208  mov     [rbp+var_20], r13
0x18000220c  lea     r9, [rbp+var_20]
0x180002210  mov     rax, [rcx]
0x180002213  lea     r8, IID_IUnknown
0x18000221a  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x180002221  mov     rax, [rax+18h]
0x180002225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222a  mov     rcx, [rbp+var_40]
0x18000222e  mov     ebx, eax
0x180002230  mov     rdx, [rcx]
0x180002233  mov     rax, [rdx+10h]
0x180002237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000223c  test    ebx, ebx
0x18000223e  jz      loc_1800023EC
0x180002244  mov     rax, [rdi]
0x180002247  mov     r8d, 1
0x18000224d  mov     rdx, r15
0x180002250  mov     rcx, rdi
0x180002253  mov     rax, [rax+0E8h]
0x18000225a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000225f  mov     r15, rax
0x180002262  test    rax, rax
0x180002265  jz      loc_180002429
0x18000226b  mov     [rbp+var_38], r13
0x18000226f  lea     r8, [rbp+var_38]
0x180002273  mov     rax, [r15]
0x180002276  lea     rdx, IID_IDispatch
0x18000227d  mov     rcx, r15
0x180002280  mov     rax, [rax]
0x180002283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002288  mov     rdx, [r15]
0x18000228b  mov     ebx, eax
0x18000228d  mov     rcx, r15
0x180002290  mov     rax, [rdx+10h]
0x180002294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002299  mov     rcx, [rbp+arg_18]
0x18000229d  mov     rax, [rcx]
0x1800022a0  mov     rax, [rax+10h]
0x1800022a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a9  mov     r15, [rbp+var_38]
0x1800022ad  mov     [rbp+arg_18], r15
0x1800022b1  test    r15, r15
0x1800022b4  jz      loc_180002095
0x1800022ba  mov     [rbp+var_30], r13
0x1800022be  lea     r8, [rbp+var_30]
0x1800022c2  mov     rax, [r15]
0x1800022c5  lea     rdx, IID_IServiceProvider
0x1800022cc  mov     rcx, r15
0x1800022cf  mov     rax, [rax]
0x1800022d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022d7  mov     rcx, [rbp+arg_18]
0x1800022db  mov     ebx, eax
0x1800022dd  mov     rdx, [rcx]
0x1800022e0  mov     rax, [rdx+10h]
0x1800022e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e9  test    ebx, ebx
0x1800022eb  jnz     loc_180002095
0x1800022f1  mov     rcx, [rbp+var_30]
0x1800022f5  test    rcx, rcx
0x1800022f8  jz      loc_180002095
0x1800022fe  mov     [rbp+var_28], r13
0x180002302  lea     r9, [rbp+var_28]
0x180002306  mov     rax, [rcx]
0x180002309  lea     r8, IID_IAccIdentity
0x180002310  lea     rdx, ?IIS_AccWrapBase_GetIUnknown@@3U_GUID@@A; _GUID IIS_AccWrapBase_GetIUnknown
0x180002317  mov     rax, [rax+18h]
0x18000231b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002320  mov     rcx, [rbp+var_30]
0x180002324  mov     ebx, eax
0x180002326  mov     rdx, [rcx]
0x180002329  mov     rax, [rdx+10h]
0x18000232d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002332  test    ebx, ebx
0x180002334  jnz     loc_180002095
0x18000233a  mov     rcx, [rbp+var_28]
0x18000233e  test    rcx, rcx
0x180002341  jz      loc_180002095
0x180002347  mov     [rbp+pv], r13
0x18000234b  lea     r9, [rbp+arg_10]
0x18000234f  mov     [rbp+arg_10], r13d
0x180002353  lea     r8, [rbp+pv]
0x180002357  mov     rax, [rcx]
0x18000235a  xor     edx, edx
0x18000235c  mov     rax, [rax+18h]
0x180002360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002365  mov     rcx, [rbp+var_28]
0x180002369  mov     ebx, eax
0x18000236b  mov     rdx, [rcx]
0x18000236e  mov     rax, [rdx+10h]
0x180002372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002377  test    ebx, ebx
  ... truncated ...
```
