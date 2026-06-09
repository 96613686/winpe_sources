# EnumerateNfsSharePermissionByPath(_MSFT_NfsServerTasks_GetSharePermission const *,_MI_Context *)

- ea: `0x18000af84`
- end: `0x18000b2a6`
- name: `?EnumerateNfsSharePermissionByPath@@YAXPEBU_MSFT_NfsServerTasks_GetSharePermission@@PEAU_MI_Context@@@Z`
- size: `802`
- prototype: `void(const struct _MSFT_NfsServerTasks_GetSharePermission *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b50`

## callees

- `0x1800098c4`
- `0x18000af84`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000be24`
- `0x18000be78`
- `0x18000e030`
- `0x18001e0a4`
- `0x180031648`
- `0x180031804`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000b094`
- `msvcrt!wcscpy_s` at `0x18000b0d0`
- `msvcrt!wcscpy_s` at `0x18000b10e`
- `msvcrt!wcscpy_s` at `0x18000b094`
- `msvcrt!wcscpy_s` at `0x18000b0d0`
- `msvcrt!wcscpy_s` at `0x18000b10e`
- `msvcrt!malloc` at `0x18000b080`
- `msvcrt!malloc` at `0x18000b0bc`
- `msvcrt!malloc` at `0x18000b0fa`
- `msvcrt!malloc` at `0x18000b080`
- `msvcrt!malloc` at `0x18000b0bc`
- `msvcrt!malloc` at `0x18000b0fa`
- `msvcrt!free` at `0x18000b200`
- `msvcrt!free` at `0x18000b210`
- `msvcrt!free` at `0x18000b220`
- `msvcrt!free` at `0x18000b200`
- `msvcrt!free` at `0x18000b210`
- `msvcrt!free` at `0x18000b220`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EnumerateNfsSharePermissionByPath(
        const struct _MSFT_NfsServerTasks_GetSharePermission *a1,
        struct _MI_Context *a2)
{
  unsigned int (*v4)(void *, struct _NFS_EXPORT_FENCING *, struct _NFS_EXPORT *); // r9
  wchar_t **v5; // r15
  enum _MI_Result v6; // esi
  __int64 v7; // r14
  const wchar_t *v8; // r12
  __int64 v9; // rbx
  rsize_t v10; // rbx
  wchar_t *v11; // r12
  __int64 v12; // rbx
  rsize_t v13; // rbx
  const wchar_t *v14; // r12
  unsigned int v15; // ebx
  char v16; // cl
  char v17; // al
  const wchar_t *v18; // r10
  const wchar_t *v19; // r11
  char v20; // al
  const wchar_t *v21; // r8
  const wchar_t *v22; // rdx
  const wchar_t *v23; // rax
  const wchar_t *v24; // r9
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *v27[2]; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+78h] [rbp-88h]
  _QWORD v29[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v30; // [rsp+90h] [rbp-70h]
  struct _MI_Context *v31; // [rsp+98h] [rbp-68h]
  int v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A4h] [rbp-5Ch]
  MI_Instance instance; // [rsp+B0h] [rbp-50h] BYREF
  int ReturnValue; // [rsp+F0h] [rbp-10h]
  char v36; // [rsp+F4h] [rbp-Ch]

  v29[0] = &CWMIContext::`vftable';
  v31 = a2;
  v29[1] = 0;
  v30 = 0;
  v33 = 0;
  v32 = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v27 = 0;
  v28 = 1;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x98u);
  Block[0] = v29;
  if ( *((_BYTE *)a1 + 80)
    && ((v5 = (wchar_t **)((char *)a1 + 104), !*((_BYTE *)a1 + 112)) || ValidateClientType(*v5, &v25))
    && (!*((_BYTE *)a1 + 128) || ValidatePermission(*((wchar_t **)a1 + 15), &v25)) )
  {
    v6 = MI_RESULT_OK;
    v7 = -1;
    if ( *((_BYTE *)a1 + 96) )
    {
      v8 = (const wchar_t *)*((_QWORD *)a1 + 11);
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v10 = v9 + 1;
      Block[1] = malloc(2 * v10);
      wcscpy_s((wchar_t *)Block[1], v10, v8);
    }
    if ( *((_BYTE *)a1 + 112) )
    {
      v11 = *v5;
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v13 = v12 + 1;
      v27[0] = malloc(2 * v13);
      wcscpy_s((wchar_t *)v27[0], v13, v11);
    }
    if ( *((_BYTE *)a1 + 128) )
    {
      v14 = (const wchar_t *)*((_QWORD *)a1 + 15);
      do
        ++v7;
      while ( v14[v7] );
      v27[1] = malloc(2 * (v7 + 1));
      wcscpy_s((wchar_t *)v27[1], v7 + 1, v14);
    }
    v15 = EnumSharePermission(*((wchar_t **)a1 + 9), 1u, 0, v4, Block, (struct CNfsTaskContext *)v29);
    if ( !v15 && !HIDWORD(v28) )
    {
      v16 = *((_BYTE *)a1 + 96);
      if ( v16 || *((_BYTE *)a1 + 112) || *((_BYTE *)a1 + 128) )
      {
        v15 = 1168;
        v17 = *((_BYTE *)a1 + 128);
        if ( v17 )
          v18 = (const wchar_t *)*((_QWORD *)a1 + 15);
        else
          v18 = &pServiceName;
        v19 = L" Permission=";
        if ( !v17 )
          v19 = &pServiceName;
        v20 = *((_BYTE *)a1 + 112);
        if ( v20 )
          v21 = *v5;
        else
          v21 = &pServiceName;
        v22 = L" ClientType=";
        if ( !v20 )
          v22 = &pServiceName;
        if ( v16 )
          v23 = (const wchar_t *)*((_QWORD *)a1 + 11);
        else
          v23 = &pServiceName;
        v24 = L" ClientName=";
        if ( !v16 )
          v24 = &pServiceName;
        CWMIContext::WriteError((CWMIContext *)v29, 0x490u, 0xC0001066, v24, v23, v22, v21, v19, v18);
      }
    }
    LODWORD(v33) = v15;
  }
  else
  {
    v6 = MI_RESULT_INVALID_PARAMETER;
  }
  if ( Block[1] )
    free(Block[1]);
  if ( v27[0] )
    free(v27[0]);
  if ( v27[1] )
    free(v27[1]);
  if ( v6 == MI_RESULT_OK )
  {
    v6 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_GetSharePermission_rtti, &instance);
    if ( v6 == MI_RESULT_OK )
    {
      ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v29);
      v36 = 1;
      MI_Instance_Destruct((MI_Instance *)a2);
      v6 = MI_Instance_Destruct(&instance);
    }
  }
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v29, v6);
  CWMIContext::~CWMIContext((CWMIContext *)v29);
}

```

## disassembly

```asm
0x18000af84  mov     [rsp-8+arg_10], rbx
0x18000af89  push    rbp
0x18000af8a  push    rsi
0x18000af8b  push    rdi
0x18000af8c  push    r12
0x18000af8e  push    r13
0x18000af90  push    r14
0x18000af92  push    r15
0x18000af94  lea     rbp, [rsp-60h]
0x18000af99  sub     rsp, 160h
0x18000afa0  mov     rax, cs:__security_cookie
0x18000afa7  xor     rax, rsp
0x18000afaa  mov     [rbp+90h+var_40], rax
0x18000afae  mov     r13, rdx
0x18000afb1  mov     rdi, rcx
0x18000afb4  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000afbb  mov     [rbp+90h+var_110], rax
0x18000afbf  mov     [rbp+90h+var_F8], rdx
0x18000afc3  xor     r12d, r12d
0x18000afc6  mov     [rbp+90h+var_108], r12
0x18000afca  mov     [rbp+90h+var_100], r12w
0x18000afcf  mov     [rbp+90h+var_EC], r12
0x18000afd3  mov     [rbp+90h+var_F0], r12d
0x18000afd7  xorps   xmm0, xmm0
0x18000afda  xor     eax, eax
0x18000afdc  movups  xmmword ptr [rsp+190h+Block], xmm0
0x18000afe1  movups  xmmword ptr [rsp+190h+var_128], xmm0
0x18000afe6  mov     [rsp+190h+var_118], rax
0x18000afeb  mov     [rbp+90h+instance.ft], r12
0x18000afef  xor     edx, edx; Val
0x18000aff1  mov     r8d, 98h; Size
0x18000aff7  lea     rcx, [rbp+90h+instance.classDecl]; void *
0x18000affb  call    memset_0
0x18000b000  lea     rax, [rbp+90h+var_110]
0x18000b004  mov     [rsp+190h+Block], rax
0x18000b009  mov     byte ptr [rsp+190h+var_118], 1
0x18000b00e  mov     dword ptr [rsp+190h+var_118+4], r12d
0x18000b013  cmp     [rdi+50h], r12b
0x18000b017  jz      short loc_18000B04F
0x18000b019  lea     r15, [rdi+68h]
0x18000b01d  cmp     [rdi+70h], r12b
0x18000b021  jz      short loc_18000B034
0x18000b023  lea     rdx, [rsp+190h+var_140]; unsigned int *
0x18000b028  mov     rcx, [r15]; String2
0x18000b02b  call    ?ValidateClientType@@YAEPEBGPEAK@Z; ValidateClientType(ushort const *,ulong *)
0x18000b030  test    al, al
0x18000b032  jz      short loc_18000B04F
0x18000b034  cmp     [rdi+80h], r12b
0x18000b03b  jz      short loc_18000B059
0x18000b03d  lea     rdx, [rsp+190h+var_140]; unsigned int *
0x18000b042  mov     rcx, [rdi+78h]; String2
0x18000b046  call    ?ValidatePermission@@YAEPEBGPEAK@Z; ValidatePermission(ushort const *,ulong *)
0x18000b04b  test    al, al
0x18000b04d  jnz     short loc_18000B059
0x18000b04f  mov     esi, 4
0x18000b054  jmp     loc_18000B1F6
0x18000b059  mov     esi, r12d
0x18000b05c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000b060  cmp     [rdi+60h], r12b
0x18000b064  jz      short loc_18000B09D
0x18000b066  mov     r12, [rdi+58h]
0x18000b06a  mov     rbx, r14
0x18000b06d  xor     eax, eax
0x18000b06f  inc     rbx
0x18000b072  cmp     [r12+rbx*2], ax
0x18000b077  jnz     short loc_18000B06F
0x18000b079  inc     rbx
0x18000b07c  lea     rcx, [rbx+rbx]; Size
0x18000b080  call    cs:__imp_malloc
0x18000b086  mov     [rsp+190h+Block+8], rax
0x18000b08b  mov     r8, r12; Source
0x18000b08e  mov     rdx, rbx; SizeInWords
0x18000b091  mov     rcx, rax; Destination
0x18000b094  call    cs:__imp_wcscpy_s
0x18000b09a  xor     r12d, r12d
0x18000b09d  cmp     [rdi+70h], r12b
0x18000b0a1  jz      short loc_18000B0D9
0x18000b0a3  mov     r12, [r15]
0x18000b0a6  mov     rbx, r14
0x18000b0a9  xor     eax, eax
0x18000b0ab  inc     rbx
0x18000b0ae  cmp     [r12+rbx*2], ax
0x18000b0b3  jnz     short loc_18000B0AB
0x18000b0b5  inc     rbx
0x18000b0b8  lea     rcx, [rbx+rbx]; Size
0x18000b0bc  call    cs:__imp_malloc
0x18000b0c2  mov     [rsp+190h+var_128], rax
0x18000b0c7  mov     r8, r12; Source
0x18000b0ca  mov     rdx, rbx; SizeInWords
0x18000b0cd  mov     rcx, rax; Destination
0x18000b0d0  call    cs:__imp_wcscpy_s
0x18000b0d6  xor     r12d, r12d
0x18000b0d9  cmp     [rdi+80h], r12b
0x18000b0e0  jz      short loc_18000B117
0x18000b0e2  mov     r12, [rdi+78h]
0x18000b0e6  xor     eax, eax
0x18000b0e8  inc     r14
0x18000b0eb  cmp     [r12+r14*2], ax
0x18000b0f0  jnz     short loc_18000B0E8
0x18000b0f2  lea     rbx, [r14+1]
0x18000b0f6  lea     rcx, [rbx+rbx]; Size
0x18000b0fa  call    cs:__imp_malloc
0x18000b100  mov     [rsp+190h+var_128+8], rax
0x18000b105  mov     r8, r12; Source
0x18000b108  mov     rdx, rbx; SizeInWords
0x18000b10b  mov     rcx, rax; Destination
0x18000b10e  call    cs:__imp_wcscpy_s
0x18000b114  xor     r12d, r12d
0x18000b117  lea     rax, [rbp+90h+var_110]
0x18000b11b  mov     [rsp+190h+var_168], rax; struct CNfsTaskContext *
0x18000b120  lea     rax, [rsp+190h+Block]
0x18000b125  mov     [rsp+190h+var_170], rax; void *
0x18000b12a  xor     r8d, r8d; unsigned __int16 *
0x18000b12d  mov     dl, 1; unsigned __int8
0x18000b12f  mov     rcx, [rdi+48h]; String2
0x18000b133  call    ?EnumSharePermission@@YAKPEAGE0P6AKPEAXPEAU_NFS_EXPORT_FENCING@@PEAU_NFS_EXPORT@@@Z1PEAVCNfsTaskContext@@@Z; EnumSharePermission(ushort *,uchar,ushort *,ulong (*)(void *,_NFS_EXPORT_FENCING *,_NFS_EXPORT *),void *,CNfsTaskContext *)
0x18000b138  mov     ebx, eax
0x18000b13a  test    eax, eax
0x18000b13c  jnz     loc_18000B1F3
0x18000b142  cmp     dword ptr [rsp+190h+var_118+4], r12d
0x18000b147  jnz     loc_18000B1F3
0x18000b14d  mov     cl, [rdi+60h]
0x18000b150  test    cl, cl
0x18000b152  jnz     short loc_18000B167
0x18000b154  cmp     [rdi+70h], r12b
0x18000b158  jnz     short loc_18000B167
0x18000b15a  cmp     [rdi+80h], r12b
0x18000b161  jz      loc_18000B1F3
0x18000b167  mov     ebx, 490h
0x18000b16c  mov     al, [rdi+80h]
0x18000b172  lea     r14, pServiceName
0x18000b179  test    al, al
0x18000b17b  jz      short loc_18000B183
0x18000b17d  mov     r10, [rdi+78h]
0x18000b181  jmp     short loc_18000B186
0x18000b183  mov     r10, r14
0x18000b186  lea     r11, aPermission; " Permission="
0x18000b18d  test    al, al
0x18000b18f  cmovz   r11, r14
0x18000b193  mov     al, [rdi+70h]
0x18000b196  test    al, al
0x18000b198  jz      short loc_18000B19F
0x18000b19a  mov     r8, [r15]
0x18000b19d  jmp     short loc_18000B1A2
0x18000b19f  mov     r8, r14
0x18000b1a2  lea     rdx, aClienttype; " ClientType="
0x18000b1a9  test    al, al
0x18000b1ab  cmovz   rdx, r14
0x18000b1af  test    cl, cl
0x18000b1b1  jz      short loc_18000B1B9
0x18000b1b3  mov     rax, [rdi+58h]
0x18000b1b7  jmp     short loc_18000B1BC
0x18000b1b9  mov     rax, r14
0x18000b1bc  lea     r9, aClientname; " ClientName="
0x18000b1c3  test    cl, cl
0x18000b1c5  cmovz   r9, r14
0x18000b1c9  mov     [rsp+190h+var_150], r10
0x18000b1ce  mov     [rsp+190h+var_158], r11
0x18000b1d3  mov     [rsp+190h+var_160], r8
0x18000b1d8  mov     [rsp+190h+var_168], rdx
0x18000b1dd  mov     [rsp+190h+var_170], rax
0x18000b1e2  mov     r8d, 0C0001066h; unsigned int
0x18000b1e8  mov     edx, ebx; unsigned int
0x18000b1ea  lea     rcx, [rbp+90h+var_110]; this
0x18000b1ee  call    ?WriteError@CWMIContext@@UEAAXKKZZ; CWMIContext::WriteError(ulong,ulong,...)
0x18000b1f3  mov     dword ptr [rbp+90h+var_EC], ebx
0x18000b1f6  mov     rcx, [rsp+190h+Block+8]; Block
0x18000b1fb  test    rcx, rcx
0x18000b1fe  jz      short loc_18000B206
0x18000b200  call    cs:__imp_free
0x18000b206  mov     rcx, [rsp+190h+var_128]; Block
0x18000b20b  test    rcx, rcx
0x18000b20e  jz      short loc_18000B216
0x18000b210  call    cs:__imp_free
0x18000b216  mov     rcx, [rsp+190h+var_128+8]; Block
0x18000b21b  test    rcx, rcx
0x18000b21e  jz      short loc_18000B226
0x18000b220  call    cs:__imp_free
0x18000b226  test    esi, esi
0x18000b228  jnz     short loc_18000B26A
0x18000b22a  lea     r8, [rbp+90h+instance]; instance
0x18000b22e  lea     rdx, MSFT_NfsServerTasks_GetSharePermission_rtti; methodDecl
0x18000b235  mov     rcx, r13; context
0x18000b238  call    MI_Context_ConstructParameters
0x18000b23d  mov     esi, eax
0x18000b23f  test    eax, eax
0x18000b241  jnz     short loc_18000B26A
0x18000b243  lea     rcx, [rbp+90h+var_110]; this
0x18000b247  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000b24c  mov     [rbp+90h+var_A0], eax
0x18000b24f  mov     [rbp+90h+var_9C], 1
0x18000b253  lea     rdx, [rbp+90h+instance]
0x18000b257  mov     rcx, r13; self
0x18000b25a  call    MI_Instance_Destruct
0x18000b25f  lea     rcx, [rbp+90h+instance]; self
0x18000b263  call    MI_Instance_Destruct
0x18000b268  mov     esi, eax
0x18000b26a  mov     edx, esi; enum _MI_Result
0x18000b26c  lea     rcx, [rbp+90h+var_110]; this
0x18000b270  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000b275  nop
0x18000b276  lea     rcx, [rbp+90h+var_110]; this
0x18000b27a  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000b27f  mov     rcx, [rbp+90h+var_40]
0x18000b283  xor     rcx, rsp; StackCookie
0x18000b286  call    __security_check_cookie
0x18000b28b  mov     rbx, [rsp+190h+arg_10]
0x18000b293  add     rsp, 160h
0x18000b29a  pop     r15
0x18000b29c  pop     r14
0x18000b29e  pop     r13
0x18000b2a0  pop     r12
0x18000b2a2  pop     rdi
0x18000b2a3  pop     rsi
0x18000b2a4  pop     rbp
0x18000b2a5  retn
```
