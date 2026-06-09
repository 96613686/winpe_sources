# FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)

- ea: `0x1800375c0`
- end: `0x18003775f`
- name: `?FindCompatiblePinFactoryIdentifier@@YAJPEAUIKsPin@@0KPEAUKSIDENTIFIER@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(struct IKsPin *, struct IKsPin *, int, struct KSIDENTIFIER *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800374f8`
- `0x18003755c`

## callees

- `0x1800375c0`
- `0x180037768`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800376de`
- `ole32!CoTaskMemFree` at `0x180037743`
- `ole32!CoTaskMemFree` at `0x1800376de`
- `ole32!CoTaskMemFree` at `0x180037743`

## pseudocode

```c
__int64 __fastcall FindCompatiblePinFactoryIdentifier(
        struct IKsPin *a1,
        struct IKsPin *a2,
        int a3,
        struct KSIDENTIFIER *a4)
{
  IKsPin_vtbl *v4; // rax
  int v8; // eax
  int Identifier; // ebx
  LPVOID v10; // r9
  struct KSIDENTIFIER *v11; // rdi
  IKsPin_vtbl *v12; // rax
  int v13; // eax
  void *v14; // rcx
  _DWORD *v15; // r9
  struct KSIDENTIFIER *i; // r10
  int v17; // r14d
  unsigned int v18; // r8d
  struct KSIDENTIFIER *v19; // r10
  __int64 v20; // r11
  $BF1D6C6803037BEC0E57DD3D16D44AB2 *v21; // r10
  __int64 Alignment; // xmm1_8
  unsigned int v23; // r8d
  int v24; // eax
  struct KSIDENTIFIER *v25; // rdx
  LPVOID v27; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-30h] BYREF
  struct KSIDENTIFIER v29; // [rsp+30h] [rbp-28h] BYREF

  v4 = a1->__vftable;
  v27 = 0;
  if ( a3 == 6 )
    v8 = v4->KsQueryMediums(a1, (KSMULTIPLE_ITEM **)&v27);
  else
    v8 = v4->KsQueryInterfaces(a1, (KSMULTIPLE_ITEM **)&v27);
  Identifier = v8;
  if ( v8 >= 0 )
  {
    v10 = v27;
    v11 = (struct KSIDENTIFIER *)((char *)v27 + 8);
    if ( a2 )
    {
      v12 = a2->__vftable;
      pv = 0;
      if ( a3 == 6 )
        v13 = v12->KsQueryMediums(a2, (KSMULTIPLE_ITEM **)&pv);
      else
        v13 = v12->KsQueryInterfaces(a2, (KSMULTIPLE_ITEM **)&pv);
      Identifier = v13;
      if ( v13 < 0 )
      {
        v14 = v27;
LABEL_27:
        CoTaskMemFree(v14);
        return (unsigned int)Identifier;
      }
      v15 = pv;
      Identifier = -2147467259;
      for ( i = (struct KSIDENTIFIER *)((char *)pv + 8); ; i = (struct KSIDENTIFIER *)(&v21[1].Alignment + 1) )
      {
        v17 = *((_DWORD *)v27 + 1);
        if ( !v17 )
          break;
        v18 = v15[1];
        if ( !v18 )
          break;
        Identifier = FindIdentifier(v11, i, v18);
        if ( Identifier >= 0 )
        {
          a4->0 = v11->0;
          Alignment = *(_QWORD *)&v11->Id;
          goto LABEL_19;
        }
        ++v11;
        *(_DWORD *)(v20 + 4) = v17 - 1;
        Identifier = FindIdentifier(v19, v11, *((_DWORD *)v27 + 1));
        if ( Identifier >= 0 )
        {
          v15 = pv;
          a4->0 = *v21;
          Alignment = v21[1].Alignment;
LABEL_19:
          *(_QWORD *)&a4->Id = Alignment;
          break;
        }
        --*((_DWORD *)pv + 1);
        v15 = pv;
      }
      CoTaskMemFree(v15);
      v10 = v27;
    }
    else
    {
      memset(&v29, 0, sizeof(v29));
      if ( a3 == 5 )
      {
        v23 = *((_DWORD *)v27 + 1);
        *(_QWORD *)&v29.Id = 0;
        v29.Set = GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000;
        v24 = FindIdentifier(&v29, (struct KSIDENTIFIER *)((char *)v27 + 8), v23);
        v25 = &v29;
        if ( v24 < 0 )
          v25 = v11;
        v11 = v25;
      }
      a4->0 = v11->0;
      *(_QWORD *)&a4->Id = *(_QWORD *)&v11->Id;
    }
    v14 = v10;
    goto LABEL_27;
  }
  return (unsigned int)Identifier;
}

```

## disassembly

```asm
0x1800375c0  push    rbp
0x1800375c2  push    rbx
0x1800375c3  push    rsi
0x1800375c4  push    rdi
0x1800375c5  push    r14
0x1800375c7  push    r15
0x1800375c9  mov     rbp, rsp
0x1800375cc  sub     rsp, 58h
0x1800375d0  mov     rax, [rcx]
0x1800375d3  mov     r14, rdx
0x1800375d6  mov     [rbp+var_38], 0
0x1800375de  lea     rdx, [rbp+var_38]
0x1800375e2  mov     rsi, r9
0x1800375e5  mov     r15d, r8d
0x1800375e8  cmp     r8d, 6
0x1800375ec  jnz     short loc_1800375F4
0x1800375ee  mov     rax, [rax+18h]
0x1800375f2  jmp     short loc_1800375F8
0x1800375f4  mov     rax, [rax+20h]
0x1800375f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375fd  mov     ebx, eax
0x1800375ff  test    eax, eax
0x180037601  js      loc_18003774F
0x180037607  mov     r9, [rbp+var_38]
0x18003760b  lea     rdi, [r9+8]
0x18003760f  test    r14, r14
0x180037612  jz      loc_1800376F0
0x180037618  mov     rax, [r14]
0x18003761b  lea     rdx, [rbp+pv]
0x18003761f  mov     [rbp+pv], 0
0x180037627  mov     rcx, r14
0x18003762a  cmp     r15d, 6
0x18003762e  jnz     short loc_180037636
0x180037630  mov     rax, [rax+18h]
0x180037634  jmp     short loc_18003763A
0x180037636  mov     rax, [rax+20h]
0x18003763a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003763f  mov     ebx, eax
0x180037641  test    eax, eax
0x180037643  jns     short loc_18003764E
0x180037645  mov     rcx, [rbp+var_38]
0x180037649  jmp     loc_180037743
0x18003764e  mov     r9, [rbp+pv]
0x180037652  mov     ebx, 80004005h
0x180037657  lea     r10, [r9+8]
0x18003765b  mov     r11, [rbp+var_38]
0x18003765f  mov     r14d, [r11+4]
0x180037663  test    r14d, r14d
0x180037666  jz      short loc_1800376DB
0x180037668  mov     r8d, [r9+4]; unsigned int
0x18003766c  test    r8d, r8d
0x18003766f  jz      short loc_1800376DB
0x180037671  mov     rdx, r10; struct KSIDENTIFIER *
0x180037674  mov     rcx, rdi; struct KSIDENTIFIER *
0x180037677  call    ?FindIdentifier@@YAJPEAUKSIDENTIFIER@@0K@Z; FindIdentifier(KSIDENTIFIER *,KSIDENTIFIER *,ulong)
0x18003767c  mov     ebx, eax
0x18003767e  test    eax, eax
0x180037680  jns     short loc_1800376CB
0x180037682  lea     eax, [r14-1]
0x180037686  add     rdi, 18h
0x18003768a  mov     [r11+4], eax
0x18003768e  mov     rdx, rdi; struct KSIDENTIFIER *
0x180037691  mov     r8, [rbp+var_38]
0x180037695  mov     rcx, r10; struct KSIDENTIFIER *
0x180037698  mov     r8d, [r8+4]; unsigned int
0x18003769c  call    ?FindIdentifier@@YAJPEAUKSIDENTIFIER@@0K@Z; FindIdentifier(KSIDENTIFIER *,KSIDENTIFIER *,ulong)
0x1800376a1  mov     ebx, eax
0x1800376a3  test    eax, eax
0x1800376a5  jns     short loc_1800376B8
0x1800376a7  mov     rax, [rbp+pv]
0x1800376ab  dec     dword ptr [rax+4]
0x1800376ae  mov     r9, [rbp+pv]
0x1800376b2  add     r10, 18h
0x1800376b6  jmp     short loc_18003765B
0x1800376b8  movups  xmm0, xmmword ptr [r10]
0x1800376bc  mov     r9, [rbp+pv]
0x1800376c0  movups  xmmword ptr [rsi], xmm0
0x1800376c3  movsd   xmm1, qword ptr [r10+10h]
0x1800376c9  jmp     short loc_1800376D6
0x1800376cb  movups  xmm0, xmmword ptr [rdi]
0x1800376ce  movups  xmmword ptr [rsi], xmm0
0x1800376d1  movsd   xmm1, qword ptr [rdi+10h]
0x1800376d6  movsd   qword ptr [rsi+10h], xmm1
0x1800376db  mov     rcx, r9; pv
0x1800376de  call    cs:__imp_CoTaskMemFree
0x1800376e5  nop     dword ptr [rax+rax+00h]
0x1800376ea  mov     r9, [rbp+var_38]
0x1800376ee  jmp     short loc_180037740
0x1800376f0  xor     eax, eax
0x1800376f2  xorps   xmm0, xmm0
0x1800376f5  mov     qword ptr [rbp+var_28.Id], rax
0x1800376f9  movups  xmmword ptr [rbp+var_28.___u0], xmm0
0x1800376fd  cmp     r15d, 5
0x180037701  jnz     short loc_180037730
0x180037703  movups  xmm0, xmmword ptr cs:_GUID_1a8766a0_62ce_11cf_a5d6_28db04c10000.Data1
0x18003770a  mov     r8d, [r9+4]; unsigned int
0x18003770e  lea     rcx, [rbp+var_28]; struct KSIDENTIFIER *
0x180037712  mov     rdx, rdi; struct KSIDENTIFIER *
0x180037715  mov     qword ptr [rbp+var_28.Id], rax
0x180037719  movdqu  xmmword ptr [rbp+var_28.___u0], xmm0
0x18003771e  call    ?FindIdentifier@@YAJPEAUKSIDENTIFIER@@0K@Z; FindIdentifier(KSIDENTIFIER *,KSIDENTIFIER *,ulong)
0x180037723  test    eax, eax
0x180037725  lea     rdx, [rbp+var_28]
0x180037729  cmovs   rdx, rdi
0x18003772d  mov     rdi, rdx
0x180037730  movups  xmm0, xmmword ptr [rdi]
0x180037733  movups  xmmword ptr [rsi], xmm0
0x180037736  movsd   xmm1, qword ptr [rdi+10h]
0x18003773b  movsd   qword ptr [rsi+10h], xmm1
0x180037740  mov     rcx, r9; pv
0x180037743  call    cs:__imp_CoTaskMemFree
0x18003774a  nop     dword ptr [rax+rax+00h]
0x18003774f  mov     eax, ebx
0x180037751  add     rsp, 58h
0x180037755  pop     r15
0x180037757  pop     r14
0x180037759  pop     rdi
0x18003775a  pop     rsi
0x18003775b  pop     rbx
0x18003775c  pop     rbp
0x18003775d  retn
```
