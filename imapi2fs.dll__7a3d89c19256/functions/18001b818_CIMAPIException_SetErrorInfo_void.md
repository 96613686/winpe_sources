# CIMAPIException::SetErrorInfo(void)

- ea: `0x18001b818`
- end: `0x18001b96b`
- name: `?SetErrorInfo@CIMAPIException@@IEAAXXZ`
- size: `339`
- prototype: `void __fastcall(CIMAPIException *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180004820`
- `0x18002cb10`
- `0x1800872d0`

## callees

- `0x18001b818`
- `0x18001b974`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001b93a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001b93a`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001b881`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001b881`

## pseudocode

```c
void __fastcall CIMAPIException::SetErrorInfo(CIMAPIException *this)
{
  __int64 *v2; // rax
  __int64 v3; // r9
  __int64 *v4; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx
  ICreateErrorInfo *pperrinfo; // [rsp+38h] [rbp+18h] BYREF
  IErrorInfo *perrinfo; // [rsp+40h] [rbp+20h] BYREF

  pperrinfo = 0;
  perrinfo = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    v2 = (__int64 *)*((_QWORD *)this + 7);
    if ( v2 )
      v3 = *v2;
    else
      v3 = 0;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, &WPP_817273934a6939807c3974520195787b_Traceguids, v3);
  }
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    v4 = (__int64 *)*((_QWORD *)this + 7);
    if ( v4 )
      v5 = *v4;
    else
      v5 = 0;
    ((void (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v5);
    v6 = (_QWORD *)*((_QWORD *)this + 8);
    if ( v6 )
      v6 = (_QWORD *)*v6;
    ((void (__fastcall *)(ICreateErrorInfo *, _QWORD *))pperrinfo->lpVtbl->SetSource)(pperrinfo, v6);
    ((void (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetHelpContext)(
      pperrinfo,
      *((unsigned int *)this + 20));
    v7 = (_QWORD *)*((_QWORD *)this + 9);
    if ( v7 )
      v7 = (_QWORD *)*v7;
    ((void (__fastcall *)(ICreateErrorInfo *, _QWORD *))pperrinfo->lpVtbl->SetHelpFile)(pperrinfo, v7);
    if ( *((_QWORD *)this + 4) )
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->SetGUID)(pperrinfo);
    if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
           pperrinfo,
           &IID_IErrorInfo,
           &perrinfo) >= 0 )
    {
      SetErrorInfo(0, perrinfo);
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    }
    ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  }
}

```

## disassembly

```asm
0x18001b818  mov     [rsp-8+arg_0], rbx
0x18001b81d  push    rbp
0x18001b81e  mov     rbp, rsp
0x18001b821  sub     rsp, 20h
0x18001b825  mov     rbx, rcx
0x18001b828  mov     [rbp+pperrinfo], 0
0x18001b830  mov     [rbp+perrinfo], 0
0x18001b838  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b83f  lea     rax, WPP_GLOBAL_Control
0x18001b846  cmp     rcx, rax
0x18001b849  jz      short loc_18001B87D
0x18001b84b  test    byte ptr [rcx+44h], 4
0x18001b84f  jz      short loc_18001B87D
0x18001b851  cmp     byte ptr [rcx+41h], 2
0x18001b855  jb      short loc_18001B87D
0x18001b857  mov     rax, [rbx+38h]
0x18001b85b  test    rax, rax
0x18001b85e  jz      short loc_18001B865
0x18001b860  mov     r9, [rax]
0x18001b863  jmp     short loc_18001B868
0x18001b865  xor     r9d, r9d
0x18001b868  mov     rcx, [rcx+38h]
0x18001b86c  lea     r8, WPP_817273934a6939807c3974520195787b_Traceguids
0x18001b873  mov     edx, 0Ch
0x18001b878  call    WPP_SF_S
0x18001b87d  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x18001b881  call    cs:__imp_CreateErrorInfo
0x18001b887  test    eax, eax
0x18001b889  js      loc_18001B960
0x18001b88f  mov     rcx, [rbp+pperrinfo]
0x18001b893  mov     rax, [rcx]
0x18001b896  mov     r8, [rax+28h]
0x18001b89a  mov     rax, [rbx+38h]
0x18001b89e  test    rax, rax
0x18001b8a1  jz      short loc_18001B8A8
0x18001b8a3  mov     rdx, [rax]
0x18001b8a6  jmp     short loc_18001B8AA
0x18001b8a8  xor     edx, edx
0x18001b8aa  mov     rax, r8
0x18001b8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8b2  mov     rcx, [rbp+pperrinfo]
0x18001b8b6  mov     rdx, [rbx+40h]
0x18001b8ba  mov     rax, [rcx]
0x18001b8bd  test    rdx, rdx
0x18001b8c0  jz      short loc_18001B8C5
0x18001b8c2  mov     rdx, [rdx]
0x18001b8c5  mov     rax, [rax+20h]
0x18001b8c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8ce  mov     rcx, [rbp+pperrinfo]
0x18001b8d2  mov     edx, [rbx+50h]
0x18001b8d5  mov     rax, [rcx]
0x18001b8d8  mov     rax, [rax+38h]
0x18001b8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8e1  mov     rcx, [rbp+pperrinfo]
0x18001b8e5  mov     rdx, [rbx+48h]
0x18001b8e9  mov     rax, [rcx]
0x18001b8ec  test    rdx, rdx
0x18001b8ef  jz      short loc_18001B8F4
0x18001b8f1  mov     rdx, [rdx]
0x18001b8f4  mov     rax, [rax+30h]
0x18001b8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8fd  mov     rdx, [rbx+20h]
0x18001b901  test    rdx, rdx
0x18001b904  jz      short loc_18001B916
0x18001b906  mov     rcx, [rbp+pperrinfo]
0x18001b90a  mov     rax, [rcx]
0x18001b90d  mov     rax, [rax+18h]
0x18001b911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b916  mov     rcx, [rbp+pperrinfo]
0x18001b91a  lea     r8, [rbp+perrinfo]
0x18001b91e  lea     rdx, IID_IErrorInfo
0x18001b925  mov     rax, [rcx]
0x18001b928  mov     rax, [rax]
0x18001b92b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b930  test    eax, eax
0x18001b932  js      short loc_18001B950
0x18001b934  mov     rdx, [rbp+perrinfo]; perrinfo
0x18001b938  xor     ecx, ecx; dwReserved
0x18001b93a  call    cs:__imp_SetErrorInfo
0x18001b940  mov     rcx, [rbp+perrinfo]
0x18001b944  mov     rax, [rcx]
0x18001b947  mov     rax, [rax+10h]
0x18001b94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b950  mov     rcx, [rbp+pperrinfo]
0x18001b954  mov     rax, [rcx]
0x18001b957  mov     rax, [rax+10h]
0x18001b95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b960  mov     rbx, [rsp+20h+arg_0]
0x18001b965  add     rsp, 20h
0x18001b969  pop     rbp
0x18001b96a  retn
```
