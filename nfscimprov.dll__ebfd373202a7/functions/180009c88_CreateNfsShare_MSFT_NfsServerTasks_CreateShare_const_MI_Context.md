# CreateNfsShare(_MSFT_NfsServerTasks_CreateShare const *,_MI_Context *)

- ea: `0x180009c88`
- end: `0x18000a13b`
- name: `?CreateNfsShare@@YAKPEBU_MSFT_NfsServerTasks_CreateShare@@PEAU_MI_Context@@@Z`
- size: `1203`
- prototype: `unsigned int __fastcall(const struct _MSFT_NfsServerTasks_CreateShare *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b00`

## callees

- `0x1800098c4`
- `0x180009c88`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000be24`
- `0x18000be78`
- `0x18000c814`
- `0x18000d3b0`
- `0x18000df80`
- `0x1800109c0`
- `0x18001d798`
- `0x18001e230`
- `0x18001e2d4`
- `0x18001e358`
- `0x18001e418`
- `0x180031548`
- `0x1800316ec`
- `0x180031804`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## string_xrefs

- `0x180009e65`: `no-access`
- `0x18000a03c`: `Failed to find the nfs share that was created %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateNfsShare(const struct _MSFT_NfsServerTasks_CreateShare *a1, struct _MI_Context *a2)
{
  bool v3; // si
  enum _MI_Result ClientPermission; // ebx
  unsigned int v5; // eax
  char v6; // al
  unsigned __int8 *v7; // r9
  unsigned __int16 *v8; // r8
  unsigned int NfsShareList; // r14d
  unsigned __int16 *v10; // r8
  MI_Context *v11; // r14
  MI_Result v12; // edi
  unsigned __int8 v14; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v15; // [rsp+71h] [rbp-8Fh] BYREF
  unsigned __int8 v16[2]; // [rsp+72h] [rbp-8Eh] BYREF
  unsigned int v17; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v18; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v19; // [rsp+7Ch] [rbp-84h] BYREF
  MI_Context *context; // [rsp+80h] [rbp-80h] BYREF
  struct _LIST_ENTRY v21; // [rsp+88h] [rbp-78h] BYREF
  struct _NFS_EXPORT *v22; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v23[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v24; // [rsp+B0h] [rbp-50h]
  struct _MI_Context *v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+C0h] [rbp-40h]
  __int64 v27; // [rsp+C4h] [rbp-3Ch]
  struct _LIST_ENTRY v28; // [rsp+D0h] [rbp-30h] BYREF
  _MI_ConstStringA v29; // [rsp+E0h] [rbp-20h] BYREF
  MI_Instance instance; // [rsp+F0h] [rbp-10h] BYREF
  int ReturnValue; // [rsp+130h] [rbp+30h]
  char v32; // [rsp+134h] [rbp+34h]
  MI_Instance self; // [rsp+1F0h] [rbp+F0h] BYREF

  context = a2;
  v3 = 0;
  v17 = 0;
  v19 = 0;
  v18 = 0;
  v15 = byte_18005667A;
  v14 = byte_180056679;
  v16[0] = 0;
  v23[0] = &CWMIContext::`vftable';
  v25 = a2;
  v23[1] = 0;
  v24 = 0;
  v27 = 0;
  v26 = 0;
  v28 = 0;
  v22 = 0;
  memset_0(&self, 0, 0xB0u);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xF0u);
  v21.Blink = &v21;
  v21.Flink = &v21;
  if ( !*((_BYTE *)a1 + 96)
    || !*((_BYTE *)a1 + 80)
    || *((_BYTE *)a1 + 200) && !ValidatePermission(*((wchar_t **)a1 + 24), &v19)
    || *((_BYTE *)a1 + 176) && !ValidateLanguageEncoding(*((wchar_t **)a1 + 21), &v18)
    || *((_BYTE *)a1 + 136) && (v29 = *(_MI_ConstStringA *)((char *)a1 + 120), !ValidateAndGetShareAuthType(&v29, &v17))
    || *((_BYTE *)a1 + 145) && *((_BYTE *)a1 + 148) && *((_BYTE *)a1 + 144) == 1 && *((_BYTE *)a1 + 147) == 1 )
  {
    ClientPermission = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_62;
  }
  if ( *((_BYTE *)a1 + 224) )
  {
    v29 = (_MI_ConstStringA)*((_OWORD *)a1 + 13);
    ClientPermission = (unsigned int)NfsGetClientPermission(&v21, &v29);
    if ( ClientPermission )
      goto LABEL_62;
  }
  else
  {
    ClientPermission = MI_RESULT_OK;
  }
  v5 = v17;
  if ( !*((_BYTE *)a1 + 136) )
    v5 = 12;
  v17 = v5;
  if ( !*((_BYTE *)a1 + 176) )
    ValidateLanguageEncoding((wchar_t *)L"ansi", &v18);
  if ( !*((_BYTE *)a1 + 200) )
    ValidatePermission((wchar_t *)L"no-access", &v19);
  v6 = *((_BYTE *)a1 + 148);
  if ( !*((_BYTE *)a1 + 145) )
  {
    if ( !v6 )
      goto LABEL_33;
    if ( *((_BYTE *)a1 + 147) == 1 )
    {
      v15 = 1;
LABEL_27:
      v14 = 0;
      goto LABEL_33;
    }
    goto LABEL_31;
  }
  if ( !v6 )
  {
    if ( *((_BYTE *)a1 + 144) != 1 )
      goto LABEL_27;
    v14 = 1;
LABEL_31:
    v15 = 0;
    goto LABEL_33;
  }
  v14 = *((_BYTE *)a1 + 144) == 1;
  v15 = *((_BYTE *)a1 + 147) == 1;
LABEL_33:
  NfsGetClusterOverrideEnabled(v16);
  v7 = (unsigned __int8 *)&unk_180056678;
  if ( *((_BYTE *)a1 + 185) )
    v7 = (unsigned __int8 *)a1 + 184;
  if ( *((_BYTE *)a1 + 112) )
    v8 = (unsigned __int16 *)*((_QWORD *)a1 + 13);
  else
    v8 = 0;
  LODWORD(v27) = CreateShare(
                   *((unsigned __int16 **)a1 + 11),
                   *((LPCWCH *)a1 + 9),
                   v8,
                   &v15,
                   &v14,
                   (int *)(((unsigned __int64)a1 + 152) & -(__int64)(*((_BYTE *)a1 + 156) != 0)),
                   (int *)(((unsigned __int64)a1 + 160) & -(__int64)(*((_BYTE *)a1 + 164) != 0)),
                   v7,
                   &v18,
                   &v17,
                   &v19,
                   (struct _LIST_ENTRY *)((unsigned __int64)&v21 & -(__int64)(*((_BYTE *)a1 + 224) != 0)),
                   (struct CNfsTaskContext *)v23,
                   v16[0]);
  if ( !(_DWORD)v27 )
  {
    NfsShareList = GetNfsShareList(&v28);
    if ( NfsShareList )
      goto LABEL_50;
    if ( *((_BYTE *)a1 + 112) )
      v10 = (unsigned __int16 *)*((_QWORD *)a1 + 13);
    else
      v10 = 0;
    NfsShareList = FindShareRecord(*((wchar_t **)a1 + 9), 0, v10, &v28, &v22);
    if ( !NfsShareList )
    {
      if ( context && context->ft )
      {
        ClientPermission = ((unsigned int (__fastcall *)(MI_Context *, void *, MI_Instance *))context->ft->ConstructInstance)(
                             context,
                             &MSFT_NfsShare_rtti,
                             &self);
        v3 = ClientPermission == MI_RESULT_OK;
        if ( ClientPermission == MI_RESULT_OK )
          ClientPermission = (unsigned int)SetCimShareProperties(v22, &self);
      }
      else
      {
        ClientPermission = MI_RESULT_INVALID_PARAMETER;
        v3 = 0;
      }
    }
    FreeNfsExportList(&v28);
    if ( NfsShareList )
LABEL_50:
      CWMIContext::WriteDebug((CWMIContext *)v23, L"Failed to find the nfs share that was created %d", NfsShareList);
    if ( ClientPermission )
      goto LABEL_59;
  }
  v11 = context;
  v12 = MI_Context_ConstructParameters(context, &MSFT_NfsServerTasks_CreateShare_rtti, &instance);
  if ( v12 )
  {
    ClientPermission = v12;
    goto LABEL_57;
  }
  if ( v3 )
  {
    context = (MI_Context *)&self;
    ClientPermission = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, MI_Context **, _QWORD, _DWORD))instance.ft->SetElementAt)(
                         &instance,
                         (unsigned int)(v12 + 13),
                         &context,
                         (unsigned int)(v12 + 15),
                         0);
    if ( ClientPermission )
    {
LABEL_57:
      if ( v12 )
        goto LABEL_59;
      goto LABEL_58;
    }
  }
  ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v23);
  v32 = 1;
  MI_Instance_Destruct((MI_Instance *)v11);
LABEL_58:
  ClientPermission = MI_Instance_Destruct(&instance);
LABEL_59:
  if ( v3 )
    ClientPermission = MI_Instance_Destruct(&self);
LABEL_62:
  FreeNfsExportFencingList(&v21);
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v23, ClientPermission);
  CWMIContext::~CWMIContext((CWMIContext *)v23);
  return (unsigned int)ClientPermission;
}

```

## disassembly

```asm
0x180009c88  mov     [rsp-8+arg_10], rbx
0x180009c8d  push    rbp
0x180009c8e  push    rsi
0x180009c8f  push    rdi
0x180009c90  push    r12
0x180009c92  push    r13
0x180009c94  push    r14
0x180009c96  push    r15
0x180009c98  lea     rbp, [rsp-1B0h]
0x180009ca0  sub     rsp, 2B0h
0x180009ca7  mov     rax, cs:__security_cookie
0x180009cae  xor     rax, rsp
0x180009cb1  mov     [rbp+1E0h+var_40], rax
0x180009cb8  mov     [rbp+1E0h+context], rdx
0x180009cbc  mov     rdi, rcx
0x180009cbf  xor     esi, esi
0x180009cc1  mov     [rsp+2E0h+var_26C], esi
0x180009cc5  mov     [rsp+2E0h+var_264], esi
0x180009cc9  mov     [rsp+2E0h+var_268], esi
0x180009ccd  mov     al, cs:byte_18005667A
0x180009cd3  mov     [rsp+2E0h+var_26F], al
0x180009cd7  mov     al, cs:byte_180056679
0x180009cdd  mov     [rsp+2E0h+var_270], al
0x180009ce1  mov     [rsp+2E0h+var_26E], sil
0x180009ce6  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180009ced  mov     [rbp+1E0h+var_240], rax
0x180009cf1  mov     [rbp+1E0h+var_228], rdx
0x180009cf5  mov     [rbp+1E0h+var_238], rsi
0x180009cf9  mov     [rbp+1E0h+var_230], si
0x180009cfd  mov     [rbp+1E0h+var_21C], rsi
0x180009d01  mov     [rbp+1E0h+var_220], esi
0x180009d04  xorps   xmm0, xmm0
0x180009d07  movups  xmmword ptr [rbp+1E0h+var_210.Flink], xmm0
0x180009d0b  mov     [rbp+1E0h+var_248], rsi
0x180009d0f  xor     edx, edx; Val
0x180009d11  mov     r8d, 0B0h; Size
0x180009d17  lea     rcx, [rbp+1E0h+self]; void *
0x180009d1e  call    memset_0
0x180009d23  mov     [rbp+1E0h+instance.ft], rsi
0x180009d27  xor     edx, edx; Val
0x180009d29  mov     r8d, 0F0h; Size
0x180009d2f  lea     rcx, [rbp+1E0h+instance.classDecl]; void *
0x180009d33  call    memset_0
0x180009d38  lea     rax, [rbp+1E0h+var_258]
0x180009d3c  mov     [rbp+1E0h+var_258.Blink], rax
0x180009d40  lea     rax, [rbp+1E0h+var_258]
0x180009d44  mov     [rbp+1E0h+var_258.Flink], rax
0x180009d48  cmp     [rdi+60h], sil
0x180009d4c  jz      loc_18000A0EC
0x180009d52  cmp     [rdi+50h], sil
0x180009d56  jz      loc_18000A0EC
0x180009d5c  lea     r14, [rdi+0C8h]
0x180009d63  cmp     [r14], sil
0x180009d66  jz      short loc_180009D81
0x180009d68  lea     rdx, [rsp+2E0h+var_264]; unsigned int *
0x180009d6d  mov     rcx, [rdi+0C0h]; String2
0x180009d74  call    ?ValidatePermission@@YAEPEBGPEAK@Z; ValidatePermission(ushort const *,ulong *)
0x180009d79  test    al, al
0x180009d7b  jz      loc_18000A0EC
0x180009d81  lea     r12, [rdi+0B0h]
0x180009d88  cmp     [r12], sil
0x180009d8c  jz      short loc_180009DA7
0x180009d8e  lea     rdx, [rsp+2E0h+var_268]; unsigned int *
0x180009d93  mov     rcx, [rdi+0A8h]; String2
0x180009d9a  call    ?ValidateLanguageEncoding@@YAEPEAGPEAK@Z; ValidateLanguageEncoding(ushort *,ulong *)
0x180009d9f  test    al, al
0x180009da1  jz      loc_18000A0EC
0x180009da7  lea     r15, [rdi+88h]
0x180009dae  cmp     [r15], sil
0x180009db1  jz      short loc_180009DD2
0x180009db3  movups  xmm0, xmmword ptr [rdi+78h]
0x180009db7  movdqu  xmmword ptr [rbp+1E0h+var_200.data], xmm0
0x180009dbc  lea     rdx, [rsp+2E0h+var_26C]; unsigned int *
0x180009dc1  lea     rcx, [rbp+1E0h+var_200]; struct _MI_ConstStringA
0x180009dc5  call    ?ValidateAndGetShareAuthType@@YAEU_MI_ConstStringA@@PEAK@Z; ValidateAndGetShareAuthType(_MI_ConstStringA,ulong *)
0x180009dca  test    al, al
0x180009dcc  jz      loc_18000A0EC
0x180009dd2  lea     r13, [rdi+91h]
0x180009dd9  cmp     [r13+0], sil
0x180009ddd  jz      short loc_180009DFE
0x180009ddf  cmp     [rdi+94h], sil
0x180009de6  jz      short loc_180009DFE
0x180009de8  cmp     byte ptr [rdi+90h], 1
0x180009def  jnz     short loc_180009DFE
0x180009df1  cmp     byte ptr [rdi+93h], 1
0x180009df8  jz      loc_18000A0EC
0x180009dfe  cmp     [rdi+0E0h], sil
0x180009e05  jz      short loc_180009E2B
0x180009e07  movups  xmm0, xmmword ptr [rdi+0D0h]
0x180009e0e  movdqu  xmmword ptr [rbp+1E0h+var_200.data], xmm0
0x180009e13  lea     rdx, [rbp+1E0h+var_200]
0x180009e17  lea     rcx, [rbp+1E0h+var_258]
0x180009e1b  call    NfsGetClientPermission
0x180009e20  mov     ebx, eax
0x180009e22  test    eax, eax
0x180009e24  jz      short loc_180009E2D
0x180009e26  jmp     loc_18000A0F1
0x180009e2b  mov     ebx, esi
0x180009e2d  mov     ecx, 0Ch
0x180009e32  cmp     byte ptr [r15], 0
0x180009e36  mov     eax, [rsp+2E0h+var_26C]
0x180009e3a  cmovz   eax, ecx
0x180009e3d  mov     [rsp+2E0h+var_26C], eax
0x180009e41  xor     r15d, r15d
0x180009e44  cmp     [r12], r15b
0x180009e48  jnz     short loc_180009E5B
0x180009e4a  lea     rdx, [rsp+2E0h+var_268]; unsigned int *
0x180009e4f  lea     rcx, aAnsi; "ansi"
0x180009e56  call    ?ValidateLanguageEncoding@@YAEPEAGPEAK@Z; ValidateLanguageEncoding(ushort *,ulong *)
0x180009e5b  cmp     [r14], r15b
0x180009e5e  jnz     short loc_180009E71
0x180009e60  lea     rdx, [rsp+2E0h+var_264]; unsigned int *
0x180009e65  lea     rcx, aNoAccess; "no-access"
0x180009e6c  call    ?ValidatePermission@@YAEPEBGPEAK@Z; ValidatePermission(ushort const *,ulong *)
0x180009e71  mov     al, [rdi+94h]
0x180009e77  cmp     [r13+0], r15b
0x180009e7b  jnz     short loc_180009E96
0x180009e7d  test    al, al
0x180009e7f  jz      short loc_180009EC7
0x180009e81  cmp     byte ptr [rdi+93h], 1
0x180009e88  jnz     short loc_180009EA8
0x180009e8a  mov     [rsp+2E0h+var_26F], 1
0x180009e8f  mov     [rsp+2E0h+var_270], r15b
0x180009e94  jmp     short loc_180009EC7
0x180009e96  test    al, al
0x180009e98  jnz     short loc_180009EAF
0x180009e9a  cmp     byte ptr [rdi+90h], 1
0x180009ea1  jnz     short loc_180009E8F
0x180009ea3  mov     [rsp+2E0h+var_270], 1
0x180009ea8  mov     [rsp+2E0h+var_26F], r15b
0x180009ead  jmp     short loc_180009EC7
0x180009eaf  cmp     byte ptr [rdi+90h], 1
0x180009eb6  setz    [rsp+2E0h+var_270]
0x180009ebb  cmp     byte ptr [rdi+93h], 1
0x180009ec2  setz    [rsp+2E0h+var_26F]
0x180009ec7  lea     rcx, [rsp+2E0h+var_26E]; unsigned __int8 *
0x180009ecc  call    ?NfsGetClusterOverrideEnabled@@YA?AW4_MI_Result@@AEAE@Z; NfsGetClusterOverrideEnabled(uchar &)
0x180009ed1  mov     al, [rdi+0E0h]
0x180009ed7  neg     al
0x180009ed9  sbb     rdx, rdx
0x180009edc  lea     rax, [rbp+1E0h+var_258]
0x180009ee0  and     rdx, rax
0x180009ee3  lea     rax, [rdi+0B8h]
0x180009eea  lea     r9, unk_180056678
0x180009ef1  cmp     [rax+1], r15b
0x180009ef5  cmovnz  r9, rax
0x180009ef9  lea     rcx, [rdi+0A0h]
0x180009f00  mov     al, [rcx+4]
0x180009f03  neg     al
0x180009f05  sbb     r10, r10
0x180009f08  and     r10, rcx
0x180009f0b  lea     rcx, [rdi+98h]
0x180009f12  mov     al, [rcx+4]
0x180009f15  neg     al
0x180009f17  sbb     r11, r11
0x180009f1a  and     r11, rcx
0x180009f1d  cmp     [rdi+70h], r15b
0x180009f21  jz      short loc_180009F29
0x180009f23  mov     r8, [rdi+68h]
0x180009f27  jmp     short loc_180009F2C
0x180009f29  mov     r8, r15; unsigned __int16 *
0x180009f2c  mov     al, [rsp+2E0h+var_26E]
0x180009f30  mov     [rsp+2E0h+var_278], al; unsigned __int8
0x180009f34  lea     rax, [rbp+1E0h+var_240]
0x180009f38  mov     [rsp+2E0h+var_280], rax; struct CNfsTaskContext *
0x180009f3d  mov     [rsp+2E0h+var_288], rdx; struct _LIST_ENTRY *
0x180009f42  lea     rax, [rsp+2E0h+var_264]
0x180009f47  mov     [rsp+2E0h+var_290], rax; unsigned int *
0x180009f4c  lea     rax, [rsp+2E0h+var_26C]
0x180009f51  mov     [rsp+2E0h+var_298], rax; unsigned int *
0x180009f56  lea     rax, [rsp+2E0h+var_268]
0x180009f5b  mov     [rsp+2E0h+var_2A0], rax; unsigned int *
0x180009f60  mov     [rsp+2E0h+var_2A8], r9; unsigned __int8 *
0x180009f65  mov     [rsp+2E0h+var_2B0], r10; int *
0x180009f6a  mov     [rsp+2E0h+var_2B8], r11; int *
0x180009f6f  lea     rax, [rsp+2E0h+var_270]
0x180009f74  mov     [rsp+2E0h+var_2C0], rax; unsigned __int8 *
0x180009f79  lea     r9, [rsp+2E0h+var_26F]; unsigned __int8 *
0x180009f7e  mov     rdx, [rdi+48h]; lpSrcStr
0x180009f82  mov     rcx, [rdi+58h]; unsigned __int16 *
0x180009f86  call    ?CreateShare@@YAKPEAG00PEAE1PEAJ21PEAK33PEAU_LIST_ENTRY@@PEAVCNfsTaskContext@@E@Z; CreateShare(ushort *,ushort *,ushort *,uchar *,uchar *,long *,long *,uchar *,ulong *,ulong *,ulong *,_LIST_ENTRY *,CNfsTaskContext *,uchar)
0x180009f8b  mov     dword ptr [rbp+1E0h+var_21C], eax
0x180009f8e  test    eax, eax
0x180009f90  jnz     loc_18000A054
0x180009f96  lea     rcx, [rbp+1E0h+var_210]; struct _LIST_ENTRY *
0x180009f9a  call    ?GetNfsShareList@@YAKPEAU_LIST_ENTRY@@@Z; GetNfsShareList(_LIST_ENTRY *)
0x180009f9f  mov     r14d, eax
0x180009fa2  test    eax, eax
0x180009fa4  jnz     loc_18000A039
0x180009faa  cmp     [rdi+70h], r15b
0x180009fae  jz      short loc_180009FB6
0x180009fb0  mov     r8, [rdi+68h]
0x180009fb4  jmp     short loc_180009FB9
0x180009fb6  mov     r8, r15; unsigned __int16 *
0x180009fb9  lea     rax, [rbp+1E0h+var_248]
0x180009fbd  mov     [rsp+2E0h+var_2C0], rax; struct _NFS_EXPORT **
0x180009fc2  lea     r9, [rbp+1E0h+var_210]; struct _LIST_ENTRY *
0x180009fc6  xor     edx, edx; unsigned __int8
0x180009fc8  mov     rcx, [rdi+48h]; String2
0x180009fcc  call    ?FindShareRecord@@YAKPEAGE0PEAU_LIST_ENTRY@@PEAPEAU_NFS_EXPORT@@@Z; FindShareRecord(ushort *,uchar,ushort *,_LIST_ENTRY *,_NFS_EXPORT * *)
0x180009fd1  mov     r14d, eax
0x180009fd4  test    eax, eax
0x180009fd6  jnz     short loc_18000A02B
0x180009fd8  mov     rax, [rbp+1E0h+context]
0x180009fdc  test    rax, rax
0x180009fdf  jz      short loc_18000A023
0x180009fe1  mov     r9, [rax]
0x180009fe4  test    r9, r9
0x180009fe7  jz      short loc_18000A023
0x180009fe9  lea     r8, [rbp+1E0h+self]
0x180009ff0  lea     rdx, MSFT_NfsShare_rtti
0x180009ff7  mov     rcx, rax
0x180009ffa  mov     rax, [r9+18h]
0x180009ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a003  mov     ebx, eax
0x18000a005  test    eax, eax
0x18000a007  setz    sil
0x18000a00b  test    eax, eax
0x18000a00d  jnz     short loc_18000A02B
0x18000a00f  lea     rdx, [rbp+1E0h+self]
0x18000a016  mov     rcx, [rbp+1E0h+var_248]
0x18000a01a  call    SetCimShareProperties
0x18000a01f  mov     ebx, eax
0x18000a021  jmp     short loc_18000A02B
0x18000a023  mov     ebx, 4
0x18000a028  mov     sil, r15b
0x18000a02b  lea     rcx, [rbp+1E0h+var_210]; struct _LIST_ENTRY *
0x18000a02f  call    ?FreeNfsExportList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportList(_LIST_ENTRY *)
0x18000a034  test    r14d, r14d
0x18000a037  jz      short loc_18000A04C
0x18000a039  mov     r8d, r14d
0x18000a03c  lea     rdx, aFailedToFindTh; "Failed to find the nfs share that was c"...
0x18000a043  lea     rcx, [rbp+1E0h+var_240]; this
0x18000a047  call    ?WriteDebug@CWMIContext@@UEAAXPEAGZZ; CWMIContext::WriteDebug(ushort *,...)
0x18000a04c  test    ebx, ebx
0x18000a04e  jnz     loc_18000A0D7
0x18000a054  lea     r8, [rbp+1E0h+instance]; instance
0x18000a058  lea     rdx, MSFT_NfsServerTasks_CreateShare_rtti; methodDecl
0x18000a05f  mov     r14, [rbp+1E0h+context]
0x18000a063  mov     rcx, r14; context
0x18000a066  call    MI_Context_ConstructParameters
0x18000a06b  mov     edi, eax
0x18000a06d  test    eax, eax
0x18000a06f  jnz     short loc_18000A0C6
0x18000a071  test    sil, sil
0x18000a074  jz      short loc_18000A0A8
0x18000a076  lea     rax, [rbp+1E0h+self]
0x18000a07d  mov     [rbp+1E0h+context], rax
0x18000a081  mov     rcx, [rbp+1E0h+instance.ft]
0x18000a085  mov     rax, [rcx+50h]
0x18000a089  mov     dword ptr [rsp+2E0h+var_2C0], r15d
0x18000a08e  lea     r9d, [rdi+0Fh]
0x18000a092  lea     r8, [rbp+1E0h+context]
0x18000a096  lea     edx, [rdi+0Dh]
0x18000a099  lea     rcx, [rbp+1E0h+instance]
0x18000a09d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a2  mov     ebx, eax
0x18000a0a4  test    eax, eax
0x18000a0a6  jnz     short loc_18000A0C8
0x18000a0a8  lea     rcx, [rbp+1E0h+var_240]; this
0x18000a0ac  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000a0b1  mov     [rbp+1E0h+var_1B0], eax
0x18000a0b4  mov     [rbp+1E0h+var_1AC], 1
0x18000a0b8  lea     rdx, [rbp+1E0h+instance]
0x18000a0bc  mov     rcx, r14; self
0x18000a0bf  call    MI_Instance_Destruct
0x18000a0c4  jmp     short loc_18000A0CC
0x18000a0c6  mov     ebx, edi
0x18000a0c8  test    edi, edi
0x18000a0ca  jnz     short loc_18000A0D7
0x18000a0cc  lea     rcx, [rbp+1E0h+instance]; self
0x18000a0d0  call    MI_Instance_Destruct
0x18000a0d5  mov     ebx, eax
0x18000a0d7  test    sil, sil
0x18000a0da  jz      short loc_18000A0F1
0x18000a0dc  lea     rcx, [rbp+1E0h+self]; self
0x18000a0e3  call    MI_Instance_Destruct
0x18000a0e8  mov     ebx, eax
0x18000a0ea  jmp     short loc_18000A0F1
0x18000a0ec  mov     ebx, 4
0x18000a0f1  lea     rcx, [rbp+1E0h+var_258]; struct _LIST_ENTRY *
0x18000a0f5  call    ?FreeNfsExportFencingList@@YAXPEAU_LIST_ENTRY@@@Z; FreeNfsExportFencingList(_LIST_ENTRY *)
0x18000a0fa  mov     edx, ebx; enum _MI_Result
0x18000a0fc  lea     rcx, [rbp+1E0h+var_240]; this
0x18000a100  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000a105  nop
0x18000a106  lea     rcx, [rbp+1E0h+var_240]; this
0x18000a10a  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000a10f  mov     eax, ebx
0x18000a111  mov     rcx, [rbp+1E0h+var_40]
0x18000a118  xor     rcx, rsp; StackCookie
0x18000a11b  call    __security_check_cookie
0x18000a120  mov     rbx, [rsp+2E0h+arg_10]
0x18000a128  add     rsp, 2B0h
0x18000a12f  pop     r15
0x18000a131  pop     r14
0x18000a133  pop     r13
0x18000a135  pop     r12
0x18000a137  pop     rdi
0x18000a138  pop     rsi
  ... truncated ...
```
