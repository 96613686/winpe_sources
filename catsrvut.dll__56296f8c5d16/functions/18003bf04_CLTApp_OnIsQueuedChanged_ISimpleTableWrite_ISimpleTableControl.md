# CLTApp::OnIsQueuedChanged(ISimpleTableWrite *,ISimpleTableControl *)

- ea: `0x18003bf04`
- end: `0x18003c261`
- name: `?OnIsQueuedChanged@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(CLTApp *__hidden this, struct ISimpleTableWrite *, struct ISimpleTableControl *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x18003bf04`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c158`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003c158`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c216`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003c168`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18003c168`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003c1c2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003c242`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003c1c2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003c242`

## pseudocode

```c
__int64 __fastcall CLTApp::OnIsQueuedChanged(
        CLTApp *this,
        struct ISimpleTableWrite *a2,
        struct ISimpleTableControl *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct ISimpleTableWrite *, __int64, int *, _QWORD, _QWORD, _DWORD **); // rax
  char v7; // r14
  HRESULT v8; // ebx
  bool v9; // si
  LPVOID v10; // r9
  __int64 v11; // r8
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // eax
  int v16; // [rsp+40h] [rbp-29h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-21h] BYREF
  __int64 v18; // [rsp+50h] [rbp-19h] BYREF
  __int64 v19; // [rsp+58h] [rbp-11h] BYREF
  __int64 v20; // [rsp+60h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1h]
  _DWORD *v22; // [rsp+70h] [rbp+7h] BYREF
  __int64 v23; // [rsp+78h] [rbp+Fh]
  _DWORD *v24; // [rsp+80h] [rbp+17h]
  __int64 v25; // [rsp+88h] [rbp+1Fh]
  CLTApp *v26; // [rsp+D0h] [rbp+67h] BYREF
  int v27; // [rsp+D8h] [rbp+6Fh] BYREF
  int v28; // [rsp+E8h] [rbp+7Fh] BYREF

  v26 = this;
  v3 = *(_QWORD *)a2;
  v19 = 0;
  v23 = 0;
  v6 = *(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, _QWORD, _QWORD, _DWORD **))(v3 + 152);
  v18 = 0;
  v22 = 0;
  v24 = 0;
  v28 = 0;
  v7 = 0;
  v27 = 0;
  v16 = 0;
  LODWORD(v26) = 0;
  v25 = 0;
  v20 = 0;
  pv = 0;
  ppv = 0;
  v8 = v6(a2, 28, &v28, 0, 0, &v22);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a2 + 152LL))(
           a2,
           1,
           &v27,
           0,
           0,
           &v19);
    if ( v8 >= 0 )
    {
      if ( !v19 )
      {
LABEL_4:
        v8 = -2147418113;
        goto LABEL_33;
      }
      v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, _QWORD, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)a2 + 152LL))(
             a2,
             0,
             0,
             0,
             0,
             &v18);
      if ( v8 >= 0 )
      {
        if ( !v18 )
          goto LABEL_4;
        v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD))(*(_QWORD *)a2 + 152LL))(a2, 33, 0);
        if ( v8 >= 0 )
        {
          if ( !v24 )
            goto LABEL_4;
          v9 = 0;
          if ( *v24 && *v22 )
          {
            v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, CLTApp **))(*(_QWORD *)a2 + 152LL))(
                   a2,
                   3,
                   &v26);
            if ( v8 < 0 )
              goto LABEL_33;
            if ( !v23 )
              goto LABEL_4;
            v9 = ((unsigned __int8)v26 & 2) != 0;
          }
          if ( (((unsigned __int8)v28 | (unsigned __int8)v27) & 2) != 0 || v9 )
          {
            v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *))(*(_QWORD *)a2 + 152LL))(
                   a2,
                   20,
                   &v16);
            if ( v8 >= 0 && ((v16 & 2) == 0 || v9) )
            {
              v8 = (*(__int64 (__fastcall **)(struct ISimpleTableControl *))(*(_QWORD *)a3 + 80LL))(a3);
              if ( v8 >= 0 )
              {
                if ( *v22 || v9 )
                {
                  v8 = CoCreateInstance(&CLSID_QCQueueAdmin, 0, 1u, &IID_IQCQueueAdministration, &ppv);
                  if ( v8 < 0 )
                    goto LABEL_33;
                  v8 = CoImpersonateClient();
                  if ( v8 < 0 )
                    goto LABEL_33;
                  v7 = 1;
                  v12 = *(_QWORD *)ppv;
                  v13 = v9
                      ? (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, __int64 *))(v12 + 72))(
                          ppv,
                          v23,
                          v19,
                          v18,
                          &v20)
                      : (*(unsigned __int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64, _QWORD, __int64 *))(v12 + 32))(
                          ppv,
                          0,
                          v19,
                          v18,
                          0,
                          &v20);
                  v8 = v13;
                  if ( v13 < 0 )
                    goto LABEL_33;
                  v8 = CoRevertToSelf();
                  if ( v8 < 0 )
                    goto LABEL_33;
                  v10 = pv;
                  v7 = 0;
                  v11 = (unsigned int)v20;
                }
                else
                {
                  v10 = 0;
                  v11 = 0;
                }
                v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, __int64, LPVOID))(*(_QWORD *)a2 + 160LL))(
                       a2,
                       20,
                       v11,
                       v10);
                if ( v8 >= 0 )
                {
                  v8 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2);
                  v7 = 0;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_33:
  if ( pv )
  {
    CoTaskMemFree(pv);
    LODWORD(v20) = 0;
    pv = 0;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v7 )
  {
    v14 = CoRevertToSelf();
    if ( !v8 )
      return v14;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003bf04  mov     [rsp-8+arg_0], rcx
0x18003bf09  push    rbp
0x18003bf0a  push    rbx
0x18003bf0b  push    rsi
0x18003bf0c  push    rdi
0x18003bf0d  push    r12
0x18003bf0f  push    r14
0x18003bf11  push    r15
0x18003bf13  lea     rbp, [rsp-27h]
0x18003bf18  sub     rsp, 90h
0x18003bf1f  mov     rax, [rdx]
0x18003bf22  lea     rcx, [rbp+57h+var_50]
0x18003bf26  xor     r12d, r12d
0x18003bf29  mov     [rsp+0C0h+var_98], rcx
0x18003bf2e  mov     rdi, rdx
0x18003bf31  mov     [rbp+57h+var_68], r12
0x18003bf35  mov     r15, r8
0x18003bf38  mov     [rbp+57h+var_48], r12
0x18003bf3c  mov     rax, [rax+98h]
0x18003bf43  lea     r8, [rbp+57h+arg_18]
0x18003bf47  lea     edx, [r12+1Ch]
0x18003bf4c  mov     [rbp+57h+var_70], r12
0x18003bf50  xor     r9d, r9d
0x18003bf53  mov     [rbp+57h+var_50], r12
0x18003bf57  mov     rcx, rdi
0x18003bf5a  mov     [rbp+57h+var_40], r12
0x18003bf5e  mov     [rbp+57h+arg_18], r12d
0x18003bf62  mov     r14b, r12b
0x18003bf65  mov     [rbp+57h+arg_8], r12d
0x18003bf69  mov     [rbp+57h+var_80], r12d
0x18003bf6d  mov     dword ptr [rbp+57h+arg_0], r12d
0x18003bf71  mov     [rbp+57h+var_38], r12
0x18003bf75  mov     [rbp+57h+var_60], r12
0x18003bf79  mov     [rbp+57h+pv], r12
0x18003bf7d  mov     [rbp+57h+var_78], r12
0x18003bf81  mov     [rsp+0C0h+ppv], r12
0x18003bf86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf8b  mov     ebx, eax
0x18003bf8d  test    eax, eax
0x18003bf8f  js      loc_18003C20D
0x18003bf95  mov     rax, [rdi]
0x18003bf98  lea     rcx, [rbp+57h+var_68]
0x18003bf9c  mov     [rsp+0C0h+var_98], rcx
0x18003bfa1  lea     r8, [rbp+57h+arg_8]
0x18003bfa5  xor     r9d, r9d
0x18003bfa8  mov     [rsp+0C0h+ppv], r12
0x18003bfad  lea     edx, [r12+1]
0x18003bfb2  mov     rcx, rdi
0x18003bfb5  mov     rax, [rax+98h]
0x18003bfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfc1  mov     ebx, eax
0x18003bfc3  test    eax, eax
0x18003bfc5  js      loc_18003C20D
0x18003bfcb  cmp     [rbp+57h+var_68], r12
0x18003bfcf  jnz     short loc_18003BFDB
0x18003bfd1  mov     ebx, 8000FFFFh
0x18003bfd6  jmp     loc_18003C20D
0x18003bfdb  mov     rax, [rdi]
0x18003bfde  lea     rcx, [rbp+57h+var_70]
0x18003bfe2  mov     [rsp+0C0h+var_98], rcx
0x18003bfe7  xor     r9d, r9d
0x18003bfea  xor     r8d, r8d
0x18003bfed  mov     [rsp+0C0h+ppv], r12
0x18003bff2  xor     edx, edx
0x18003bff4  mov     rcx, rdi
0x18003bff7  mov     rax, [rax+98h]
0x18003bffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c003  mov     ebx, eax
0x18003c005  test    eax, eax
0x18003c007  js      loc_18003C20D
0x18003c00d  cmp     [rbp+57h+var_70], r12
0x18003c011  jz      short loc_18003BFD1
0x18003c013  mov     rax, [rdi]
0x18003c016  lea     rcx, [rbp+57h+var_40]
0x18003c01a  mov     [rsp+0C0h+var_98], rcx
0x18003c01f  xor     r9d, r9d
0x18003c022  xor     r8d, r8d
0x18003c025  mov     [rsp+0C0h+ppv], r12
0x18003c02a  mov     rcx, rdi
0x18003c02d  mov     rax, [rax+98h]
0x18003c034  lea     edx, [r9+21h]
0x18003c038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c03d  mov     ebx, eax
0x18003c03f  test    eax, eax
0x18003c041  js      loc_18003C20D
0x18003c047  mov     rax, [rbp+57h+var_40]
0x18003c04b  test    rax, rax
0x18003c04e  jz      short loc_18003BFD1
0x18003c050  movzx   esi, r12b
0x18003c054  cmp     [rax], r12d
0x18003c057  jz      short loc_18003C0AD
0x18003c059  mov     rax, [rbp+57h+var_50]
0x18003c05d  cmp     [rax], r12d
0x18003c060  jz      short loc_18003C0AD
0x18003c062  mov     rax, [rdi]
0x18003c065  lea     rcx, [rbp+57h+var_48]
0x18003c069  mov     [rsp+0C0h+var_98], rcx
0x18003c06e  lea     r8, [rbp+57h+arg_0]
0x18003c072  xor     r9d, r9d
0x18003c075  mov     [rsp+0C0h+ppv], r12
0x18003c07a  mov     rcx, rdi
0x18003c07d  mov     rax, [rax+98h]
0x18003c084  lea     edx, [r9+3]
0x18003c088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c08d  mov     ebx, eax
0x18003c08f  test    eax, eax
0x18003c091  js      loc_18003C20D
0x18003c097  cmp     [rbp+57h+var_48], r12
0x18003c09b  jz      loc_18003BFD1
0x18003c0a1  test    byte ptr [rbp+57h+arg_0], 2
0x18003c0a5  mov     eax, 1
0x18003c0aa  cmovnz  esi, eax
0x18003c0ad  mov     eax, [rbp+57h+arg_8]
0x18003c0b0  or      eax, [rbp+57h+arg_18]
0x18003c0b3  test    al, 2
0x18003c0b5  jnz     short loc_18003C0C0
0x18003c0b7  test    sil, sil
0x18003c0ba  jz      loc_18003C20D
0x18003c0c0  mov     rax, [rdi]
0x18003c0c3  lea     rcx, [rbp+57h+var_38]
0x18003c0c7  mov     [rsp+0C0h+var_98], rcx
0x18003c0cc  lea     r8, [rbp+57h+var_80]
0x18003c0d0  xor     r9d, r9d
0x18003c0d3  mov     [rsp+0C0h+ppv], r12
0x18003c0d8  mov     rcx, rdi
0x18003c0db  mov     rax, [rax+98h]
0x18003c0e2  lea     edx, [r9+14h]
0x18003c0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0eb  mov     ebx, eax
0x18003c0ed  test    eax, eax
0x18003c0ef  js      loc_18003C20D
0x18003c0f5  test    byte ptr [rbp+57h+var_80], 2
0x18003c0f9  jz      short loc_18003C104
0x18003c0fb  test    sil, sil
0x18003c0fe  jz      loc_18003C20D
0x18003c104  mov     rax, [r15]
0x18003c107  mov     rcx, r15
0x18003c10a  mov     rax, [rax+50h]
0x18003c10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c113  mov     ebx, eax
0x18003c115  test    eax, eax
0x18003c117  js      loc_18003C20D
0x18003c11d  mov     rax, [rbp+57h+var_50]
0x18003c121  cmp     [rax], r12d
0x18003c124  jnz     short loc_18003C136
0x18003c126  test    sil, sil
0x18003c129  jnz     short loc_18003C136
0x18003c12b  xor     r9d, r9d
0x18003c12e  xor     r8d, r8d
0x18003c131  jmp     loc_18003C1D9
0x18003c136  lea     rax, [rbp+57h+var_78]
0x18003c13a  mov     r15d, 1
0x18003c140  mov     r8d, r15d; dwClsContext
0x18003c143  mov     [rsp+0C0h+ppv], rax; ppv
0x18003c148  lea     r9, IID_IQCQueueAdministration; riid
0x18003c14f  xor     edx, edx; pUnkOuter
0x18003c151  lea     rcx, CLSID_QCQueueAdmin; rclsid
0x18003c158  call    cs:__imp_CoCreateInstance
0x18003c15e  mov     ebx, eax
0x18003c160  test    eax, eax
0x18003c162  js      loc_18003C20D
0x18003c168  call    cs:__imp_CoImpersonateClient
0x18003c16e  mov     ebx, eax
0x18003c170  test    eax, eax
0x18003c172  js      loc_18003C20D
0x18003c178  mov     rcx, [rbp+57h+var_78]
0x18003c17c  mov     r14b, r15b
0x18003c17f  mov     r9, [rbp+57h+var_70]
0x18003c183  lea     rdx, [rbp+57h+var_60]
0x18003c187  mov     r8, [rbp+57h+var_68]
0x18003c18b  mov     rax, [rcx]
0x18003c18e  test    sil, sil
0x18003c191  jz      short loc_18003C1A7
0x18003c193  mov     rax, [rax+48h]
0x18003c197  mov     [rsp+0C0h+ppv], rdx
0x18003c19c  mov     rdx, [rbp+57h+var_48]
0x18003c1a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1a5  jmp     short loc_18003C1BC
0x18003c1a7  mov     rax, [rax+20h]
0x18003c1ab  mov     [rsp+0C0h+var_98], rdx
0x18003c1b0  xor     edx, edx
0x18003c1b2  mov     [rsp+0C0h+ppv], r12
0x18003c1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1bc  mov     ebx, eax
0x18003c1be  test    eax, eax
0x18003c1c0  js      short loc_18003C20D
0x18003c1c2  call    cs:__imp_CoRevertToSelf
0x18003c1c8  mov     ebx, eax
0x18003c1ca  test    eax, eax
0x18003c1cc  js      short loc_18003C20D
0x18003c1ce  mov     r9, [rbp+57h+pv]
0x18003c1d2  mov     r14b, r12b
0x18003c1d5  mov     r8d, dword ptr [rbp+57h+var_60]
0x18003c1d9  mov     rax, [rdi]
0x18003c1dc  mov     edx, 14h
0x18003c1e1  mov     rcx, rdi
0x18003c1e4  mov     rax, [rax+0A0h]
0x18003c1eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1f0  mov     ebx, eax
0x18003c1f2  test    eax, eax
0x18003c1f4  js      short loc_18003C20D
0x18003c1f6  mov     rax, [rdi]
0x18003c1f9  mov     rcx, rdi
0x18003c1fc  mov     rax, [rax+90h]
0x18003c203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c208  mov     ebx, eax
0x18003c20a  mov     r14b, r12b
0x18003c20d  mov     rcx, [rbp+57h+pv]; pv
0x18003c211  test    rcx, rcx
0x18003c214  jz      short loc_18003C224
0x18003c216  call    cs:__imp_CoTaskMemFree
0x18003c21c  mov     dword ptr [rbp+57h+var_60], r12d
0x18003c220  mov     [rbp+57h+pv], r12
0x18003c224  mov     rcx, [rbp+57h+var_78]
0x18003c228  test    rcx, rcx
0x18003c22b  jz      short loc_18003C23D
0x18003c22d  mov     rax, [rcx]
0x18003c230  mov     rax, [rax+10h]
0x18003c234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c239  mov     [rbp+57h+var_78], r12
0x18003c23d  test    r14b, r14b
0x18003c240  jz      short loc_18003C24D
0x18003c242  call    cs:__imp_CoRevertToSelf
0x18003c248  test    ebx, ebx
0x18003c24a  cmovz   ebx, eax
0x18003c24d  mov     eax, ebx
0x18003c24f  add     rsp, 90h
0x18003c256  pop     r15
0x18003c258  pop     r14
0x18003c25a  pop     r12
0x18003c25c  pop     rdi
0x18003c25d  pop     rsi
0x18003c25e  pop     rbx
0x18003c25f  pop     rbp
0x18003c260  retn
```
