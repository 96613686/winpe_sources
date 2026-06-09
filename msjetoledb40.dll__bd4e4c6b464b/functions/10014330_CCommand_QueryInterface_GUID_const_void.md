# CCommand::QueryInterface(_GUID const &,void * *)

- ea: `0x10014330`
- end: `0x10014631`
- name: `?QueryInterface@CCommand@@UAGJABU_GUID@@PAPAX@Z`
- size: `769`
- prototype: `int __stdcall(CCommand *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000ba90`
- `0x10014330`
- `0x1001c6d0`
- `0x1004ce5d`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10014615`
- `KERNEL32!LeaveCriticalSection` at `0x10014615`
- `KERNEL32!EnterCriticalSection` at `0x10014367`
- `KERNEL32!EnterCriticalSection` at `0x10014367`

## pseudocode

```c
int __stdcall CCommand::QueryInterface(CCommand *this, const struct _GUID *a2, void **a3)
{
  GUID *v3; // edx
  const struct _GUID *v4; // edi
  unsigned int v5; // ebx
  const struct _GUID *v6; // ecx
  bool v7; // cf
  void **v8; // ecx
  const struct _GUID *v9; // ecx
  GUID *v10; // edx
  unsigned int v11; // ebx
  const struct _GUID *v12; // ecx
  GUID *v13; // edx
  unsigned int v14; // ebx
  const struct _GUID *v15; // ecx
  GUID *v16; // edx
  unsigned int v17; // ebx
  const struct _GUID *v18; // ecx
  GUID *v19; // edx
  unsigned int v20; // ebx
  const struct _GUID *v21; // ecx
  GUID *v22; // edx
  unsigned int v23; // ebx
  const struct _GUID *v24; // ecx
  GUID *v25; // edx
  unsigned int v26; // ebx
  const struct _GUID *v27; // ecx
  GUID *v28; // edx
  unsigned int v29; // ebx
  const struct _GUID *v30; // ecx
  GUID *v31; // edx
  unsigned int v32; // ebx
  const struct _GUID *v33; // ecx
  GUID *v34; // edx
  unsigned int v35; // ebx
  GUID *v36; // ecx
  const struct _GUID *v37; // edx
  unsigned int v38; // ebx
  _DWORD *v39; // eax
  GUID *v40; // ecx
  unsigned int v41; // edx
  void *v42; // ecx
  int v43; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v3 = &IID_IUnknown;
  v4 = a2;
  v5 = 12;
  v6 = a2;
  *a3 = 0;
  while ( v6->Data1 == v3->Data1 )
  {
    v6 = (const struct _GUID *)((char *)v6 + 4);
    v3 = (GUID *)((char *)v3 + 4);
    v7 = v5 < 4;
    v5 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = this;
      goto LABEL_52;
    }
  }
  v9 = a2;
  v10 = &IID_IAccessor;
  v11 = 12;
  while ( v9->Data1 == v10->Data1 )
  {
    v9 = (const struct _GUID *)((char *)v9 + 4);
    v10 = (GUID *)((char *)v10 + 4);
    v7 = v11 < 4;
    v11 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 3);
      goto LABEL_52;
    }
  }
  v12 = a2;
  v13 = &IID_IColumnsInfo;
  v14 = 12;
  while ( v12->Data1 == v13->Data1 )
  {
    v12 = (const struct _GUID *)((char *)v12 + 4);
    v13 = (GUID *)((char *)v13 + 4);
    v7 = v14 < 4;
    v14 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 8);
      goto LABEL_52;
    }
  }
  v15 = a2;
  v16 = &IID_IColumnsRowset;
  v17 = 12;
  while ( v15->Data1 == v16->Data1 )
  {
    v15 = (const struct _GUID *)((char *)v15 + 4);
    v16 = (GUID *)((char *)v16 + 4);
    v7 = v17 < 4;
    v17 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 9);
      goto LABEL_52;
    }
  }
  v18 = a2;
  v19 = &IID_ICommand;
  v20 = 12;
  while ( v18->Data1 == v19->Data1 )
  {
    v18 = (const struct _GUID *)((char *)v18 + 4);
    v19 = (GUID *)((char *)v19 + 4);
    v7 = v20 < 4;
    v20 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 4);
      goto LABEL_52;
    }
  }
  v21 = a2;
  v22 = &IID_ICommandText;
  v23 = 12;
  while ( v21->Data1 == v22->Data1 )
  {
    v21 = (const struct _GUID *)((char *)v21 + 4);
    v22 = (GUID *)((char *)v22 + 4);
    v7 = v23 < 4;
    v23 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 4);
      goto LABEL_52;
    }
  }
  v24 = a2;
  v25 = &IID_ICommandPrepare;
  v26 = 12;
  while ( v24->Data1 == v25->Data1 )
  {
    v24 = (const struct _GUID *)((char *)v24 + 4);
    v25 = (GUID *)((char *)v25 + 4);
    v7 = v26 < 4;
    v26 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 6);
      goto LABEL_52;
    }
  }
  v27 = a2;
  v28 = &IID_ICommandProperties;
  v29 = 12;
  while ( v27->Data1 == v28->Data1 )
  {
    v27 = (const struct _GUID *)((char *)v27 + 4);
    v28 = (GUID *)((char *)v28 + 4);
    v7 = v29 < 4;
    v29 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 5);
      goto LABEL_52;
    }
  }
  v30 = a2;
  v31 = &IID_ICommandWithParameters;
  v32 = 12;
  while ( v30->Data1 == v31->Data1 )
  {
    v30 = (const struct _GUID *)((char *)v30 + 4);
    v31 = (GUID *)((char *)v31 + 4);
    v7 = v32 < 4;
    v32 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 7);
      goto LABEL_52;
    }
  }
  v33 = a2;
  v34 = &IID_IConvertType;
  v35 = 12;
  while ( v33->Data1 == v34->Data1 )
  {
    v33 = (const struct _GUID *)((char *)v33 + 4);
    v34 = (GUID *)((char *)v34 + 4);
    v7 = v35 < 4;
    v35 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 10);
      goto LABEL_52;
    }
  }
  v36 = &IID_ISupportErrorInfo;
  v37 = a2;
  v38 = 12;
  while ( v36->Data1 == v37->Data1 )
  {
    v36 = (GUID *)((char *)v36 + 4);
    v37 = (const struct _GUID *)((char *)v37 + 4);
    v7 = v38 < 4;
    v38 -= 4;
    if ( v7 )
    {
      v39 = operator new(0x14u);
      if ( v39 )
      {
        v39[2] = *((_DWORD *)this + 2);
        v8 = a3;
        *v39 = &CImpISupportErrorInfo::`vftable';
        v39[1] = 0;
        v39[3] = 9;
        v39[4] = &rgCommandExtendedErrorCLSIDs;
        *a3 = v39;
      }
      else
      {
        v8 = a3;
        *a3 = 0;
      }
      goto LABEL_52;
    }
  }
  v40 = &IID_ICommandPersist;
  v41 = 12;
  while ( v40->Data1 == v4->Data1 )
  {
    v40 = (GUID *)((char *)v40 + 4);
    v4 = (const struct _GUID *)((char *)v4 + 4);
    v7 = v41 < 4;
    v41 -= 4;
    if ( v7 )
    {
      v8 = a3;
      *a3 = (void *)*((_DWORD *)this + 11);
      goto LABEL_52;
    }
  }
  v8 = a3;
LABEL_52:
  v42 = *v8;
  if ( v42 )
  {
    (*(void (__thiscall **)(_DWORD, void *))(*(_DWORD *)v42 + 4))(*(_DWORD *)(*(_DWORD *)v42 + 4), v42);
    v43 = 0;
  }
  else
  {
    v43 = -2147467262;
  }
  if ( this != (CCommand *)-248 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  return v43;
}

```

## disassembly

```asm
0x10014330  mov     edi, edi
0x10014332  push    ebp
0x10014333  mov     ebp, esp
0x10014335  push    0FFFFFFFFh
0x10014337  push    offset ?StartTransaction@CImpITransactionLocal@@UAGJJKPAUITransactionOptions@@PAK@Z_SEH
0x1001433c  mov     eax, large fs:0
0x10014342  push    eax
0x10014343  sub     esp, 8
0x10014346  push    ebx
0x10014347  push    esi
0x10014348  push    edi
0x10014349  mov     eax, ___security_cookie
0x1001434e  xor     eax, ebp
0x10014350  push    eax
0x10014351  lea     eax, [ebp+var_C]
0x10014354  mov     large fs:0, eax
0x1001435a  mov     esi, [ebp+this]
0x1001435d  add     esi, 0F8h
0x10014363  push    esi; lpCriticalSection
0x10014364  mov     [ebp+var_10], esi
0x10014367  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1001436d  mov     eax, [ebp+arg_8]
0x10014370  mov     edx, offset _IID_IUnknown
0x10014375  mov     edi, [ebp+arg_4]
0x10014378  mov     ebx, 0Ch
0x1001437d  mov     [ebp+var_4], 0
0x10014384  mov     ecx, edi
0x10014386  mov     dword ptr [eax], 0
0x1001438c  nop     dword ptr [eax+00h]
0x10014390  mov     eax, [ecx]
0x10014392  cmp     eax, [edx]
0x10014394  jnz     short loc_100143AE
0x10014396  add     ecx, 4
0x10014399  add     edx, 4
0x1001439c  sub     ebx, 4
0x1001439f  jnb     short loc_10014390
0x100143a1  mov     ecx, [ebp+arg_8]
0x100143a4  mov     eax, [ebp+this]
0x100143a7  mov     [ecx], eax
0x100143a9  jmp     loc_100145F1
0x100143ae  mov     ecx, edi
0x100143b0  mov     edx, offset _IID_IAccessor
0x100143b5  mov     ebx, 0Ch
0x100143ba  nop     word ptr [eax+eax+00h]
0x100143c0  mov     eax, [ecx]
0x100143c2  cmp     eax, [edx]
0x100143c4  jnz     short loc_100143E1
0x100143c6  add     ecx, 4
0x100143c9  add     edx, 4
0x100143cc  sub     ebx, 4
0x100143cf  jnb     short loc_100143C0
0x100143d1  mov     eax, [ebp+this]
0x100143d4  mov     ecx, [ebp+arg_8]
0x100143d7  mov     eax, [eax+0Ch]
0x100143da  mov     [ecx], eax
0x100143dc  jmp     loc_100145F1
0x100143e1  mov     ecx, edi
0x100143e3  mov     edx, offset _IID_IColumnsInfo
0x100143e8  mov     ebx, 0Ch
0x100143ed  nop     dword ptr [eax]
0x100143f0  mov     eax, [ecx]
0x100143f2  cmp     eax, [edx]
0x100143f4  jnz     short loc_10014411
0x100143f6  add     ecx, 4
0x100143f9  add     edx, 4
0x100143fc  sub     ebx, 4
0x100143ff  jnb     short loc_100143F0
0x10014401  mov     eax, [ebp+this]
0x10014404  mov     ecx, [ebp+arg_8]
0x10014407  mov     eax, [eax+20h]
0x1001440a  mov     [ecx], eax
0x1001440c  jmp     loc_100145F1
0x10014411  mov     ecx, edi
0x10014413  mov     edx, offset _IID_IColumnsRowset
0x10014418  mov     ebx, 0Ch
0x1001441d  nop     dword ptr [eax]
0x10014420  mov     eax, [ecx]
0x10014422  cmp     eax, [edx]
0x10014424  jnz     short loc_10014441
0x10014426  add     ecx, 4
0x10014429  add     edx, 4
0x1001442c  sub     ebx, 4
0x1001442f  jnb     short loc_10014420
0x10014431  mov     eax, [ebp+this]
0x10014434  mov     ecx, [ebp+arg_8]
0x10014437  mov     eax, [eax+24h]
0x1001443a  mov     [ecx], eax
0x1001443c  jmp     loc_100145F1
0x10014441  mov     ecx, edi
0x10014443  mov     edx, offset _IID_ICommand
0x10014448  mov     ebx, 0Ch
0x1001444d  nop     dword ptr [eax]
0x10014450  mov     eax, [ecx]
0x10014452  cmp     eax, [edx]
0x10014454  jnz     short loc_10014471
0x10014456  add     ecx, 4
0x10014459  add     edx, 4
0x1001445c  sub     ebx, 4
0x1001445f  jnb     short loc_10014450
0x10014461  mov     eax, [ebp+this]
0x10014464  mov     ecx, [ebp+arg_8]
0x10014467  mov     eax, [eax+10h]
0x1001446a  mov     [ecx], eax
0x1001446c  jmp     loc_100145F1
0x10014471  mov     ecx, edi
0x10014473  mov     edx, offset _IID_ICommandText
0x10014478  mov     ebx, 0Ch
0x1001447d  nop     dword ptr [eax]
0x10014480  mov     eax, [ecx]
0x10014482  cmp     eax, [edx]
0x10014484  jnz     short loc_100144A1
0x10014486  add     ecx, 4
0x10014489  add     edx, 4
0x1001448c  sub     ebx, 4
0x1001448f  jnb     short loc_10014480
0x10014491  mov     eax, [ebp+this]
0x10014494  mov     ecx, [ebp+arg_8]
0x10014497  mov     eax, [eax+10h]
0x1001449a  mov     [ecx], eax
0x1001449c  jmp     loc_100145F1
0x100144a1  mov     ecx, edi
0x100144a3  mov     edx, offset _IID_ICommandPrepare
0x100144a8  mov     ebx, 0Ch
0x100144ad  nop     dword ptr [eax]
0x100144b0  mov     eax, [ecx]
0x100144b2  cmp     eax, [edx]
0x100144b4  jnz     short loc_100144D1
0x100144b6  add     ecx, 4
0x100144b9  add     edx, 4
0x100144bc  sub     ebx, 4
0x100144bf  jnb     short loc_100144B0
0x100144c1  mov     eax, [ebp+this]
0x100144c4  mov     ecx, [ebp+arg_8]
0x100144c7  mov     eax, [eax+18h]
0x100144ca  mov     [ecx], eax
0x100144cc  jmp     loc_100145F1
0x100144d1  mov     ecx, edi
0x100144d3  mov     edx, offset _IID_ICommandProperties
0x100144d8  mov     ebx, 0Ch
0x100144dd  nop     dword ptr [eax]
0x100144e0  mov     eax, [ecx]
0x100144e2  cmp     eax, [edx]
0x100144e4  jnz     short loc_10014501
0x100144e6  add     ecx, 4
0x100144e9  add     edx, 4
0x100144ec  sub     ebx, 4
0x100144ef  jnb     short loc_100144E0
0x100144f1  mov     eax, [ebp+this]
0x100144f4  mov     ecx, [ebp+arg_8]
0x100144f7  mov     eax, [eax+14h]
0x100144fa  mov     [ecx], eax
0x100144fc  jmp     loc_100145F1
0x10014501  mov     ecx, edi
0x10014503  mov     edx, offset _IID_ICommandWithParameters
0x10014508  mov     ebx, 0Ch
0x1001450d  nop     dword ptr [eax]
0x10014510  mov     eax, [ecx]
0x10014512  cmp     eax, [edx]
0x10014514  jnz     short loc_10014531
0x10014516  add     ecx, 4
0x10014519  add     edx, 4
0x1001451c  sub     ebx, 4
0x1001451f  jnb     short loc_10014510
0x10014521  mov     eax, [ebp+this]
0x10014524  mov     ecx, [ebp+arg_8]
0x10014527  mov     eax, [eax+1Ch]
0x1001452a  mov     [ecx], eax
0x1001452c  jmp     loc_100145F1
0x10014531  mov     ecx, edi
0x10014533  mov     edx, offset _IID_IConvertType
0x10014538  mov     ebx, 0Ch
0x1001453d  nop     dword ptr [eax]
0x10014540  mov     eax, [ecx]
0x10014542  cmp     eax, [edx]
0x10014544  jnz     short loc_10014561
0x10014546  add     ecx, 4
0x10014549  add     edx, 4
0x1001454c  sub     ebx, 4
0x1001454f  jnb     short loc_10014540
0x10014551  mov     eax, [ebp+this]
0x10014554  mov     ecx, [ebp+arg_8]
0x10014557  mov     eax, [eax+28h]
0x1001455a  mov     [ecx], eax
0x1001455c  jmp     loc_100145F1
0x10014561  mov     ecx, offset _IID_ISupportErrorInfo
0x10014566  mov     edx, edi
0x10014568  mov     ebx, 0Ch
0x1001456d  nop     dword ptr [eax]
0x10014570  mov     eax, [ecx]
0x10014572  cmp     eax, [edx]
0x10014574  jnz     short loc_100145C6
0x10014576  add     ecx, 4
0x10014579  add     edx, 4
0x1001457c  sub     ebx, 4
0x1001457f  jnb     short loc_10014570
0x10014581  push    14h; Size
0x10014583  call    ??2@YAPAXI@Z; operator new(uint)
0x10014588  add     esp, 4
0x1001458b  mov     [ebp+var_14], eax
0x1001458e  test    eax, eax
0x10014590  jz      short loc_100145BD
0x10014592  mov     ecx, [ebp+this]
0x10014595  mov     ecx, [ecx+8]
0x10014598  mov     [eax+8], ecx
0x1001459b  mov     ecx, [ebp+arg_8]
0x1001459e  mov     dword ptr [eax], offset ??_7CImpISupportErrorInfo@@6B@; const CImpISupportErrorInfo::`vftable'
0x100145a4  mov     dword ptr [eax+4], 0
0x100145ab  mov     dword ptr [eax+0Ch], 9
0x100145b2  mov     dword ptr [eax+10h], offset ?rgCommandExtendedErrorCLSIDs@@3PAPBU_GUID@@A; _GUID const * * rgCommandExtendedErrorCLSIDs
0x100145b9  mov     [ecx], eax
0x100145bb  jmp     short loc_100145F1
0x100145bd  mov     ecx, [ebp+arg_8]
0x100145c0  xor     eax, eax
0x100145c2  mov     [ecx], eax
0x100145c4  jmp     short loc_100145F1
0x100145c6  mov     ecx, offset _IID_ICommandPersist
0x100145cb  mov     edx, 0Ch
0x100145d0  mov     eax, [ecx]
0x100145d2  cmp     eax, [edi]
0x100145d4  jnz     short loc_100145EE
0x100145d6  add     ecx, 4
0x100145d9  add     edi, 4
0x100145dc  sub     edx, 4
0x100145df  jnb     short loc_100145D0
0x100145e1  mov     eax, [ebp+this]
0x100145e4  mov     ecx, [ebp+arg_8]
0x100145e7  mov     eax, [eax+2Ch]
0x100145ea  mov     [ecx], eax
0x100145ec  jmp     short loc_100145F1
0x100145ee  mov     ecx, [ebp+arg_8]
0x100145f1  mov     ecx, [ecx]
0x100145f3  test    ecx, ecx
0x100145f5  jz      short loc_1001460B
0x100145f7  mov     eax, [ecx]
0x100145f9  push    ecx
0x100145fa  mov     edi, [eax+4]
0x100145fd  mov     ecx, edi
0x100145ff  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10014605  call    edi
0x10014607  xor     edi, edi
0x10014609  jmp     short loc_10014610
0x1001460b  mov     edi, 80004002h
0x10014610  test    esi, esi
0x10014612  jz      short loc_1001461B
0x10014614  push    esi; lpCriticalSection
0x10014615  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1001461b  mov     eax, edi
0x1001461d  mov     ecx, [ebp+var_C]
0x10014620  mov     large fs:0, ecx
0x10014627  pop     ecx
0x10014628  pop     edi
0x10014629  pop     esi
0x1001462a  pop     ebx
0x1001462b  mov     esp, ebp
0x1001462d  pop     ebp
0x1001462e  retn    0Ch
0x1004ddb0  lea     ecx, [ebp+var_10]; this
0x1004ddb3  jmp     ??1CMutex@@QAE@XZ
0x1004ddbd  nop
0x1004ddbe  nop
0x1004ddbf  mov     edx, [esp-4+arg_4]
0x1004ddc3  lea     eax, [edx+0Ch]
0x1004ddc6  mov     ecx, [edx-18h]
0x1004ddc9  xor     ecx, eax; StackCookie
0x1004ddcb  call    @__security_check_cookie@4
0x1004ddd0  mov     eax, offset stru_1004F3AC
0x1004ddd5  jmp     ___CxxFrameHandler3
```
