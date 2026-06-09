# EnumerateNfsSharePermissionByName(_MSFT_NfsServerTasks_GetSharePermissionByName const *,_MI_Context *)

- ea: `0x18000ac38`
- end: `0x18000af7b`
- name: `?EnumerateNfsSharePermissionByName@@YAXPEBU_MSFT_NfsServerTasks_GetSharePermissionByName@@PEAU_MI_Context@@@Z`
- size: `835`
- prototype: `void(const struct _MSFT_NfsServerTasks_GetSharePermissionByName *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b60`

## callees

- `0x1800098c4`
- `0x18000ac38`
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

- `msvcrt!wcscpy_s` at `0x18000ad4e`
- `msvcrt!wcscpy_s` at `0x18000ad8d`
- `msvcrt!wcscpy_s` at `0x18000adce`
- `msvcrt!wcscpy_s` at `0x18000ad4e`
- `msvcrt!wcscpy_s` at `0x18000ad8d`
- `msvcrt!wcscpy_s` at `0x18000adce`
- `msvcrt!malloc` at `0x18000ad3a`
- `msvcrt!malloc` at `0x18000ad79`
- `msvcrt!malloc` at `0x18000adba`
- `msvcrt!malloc` at `0x18000ad3a`
- `msvcrt!malloc` at `0x18000ad79`
- `msvcrt!malloc` at `0x18000adba`
- `msvcrt!free` at `0x18000aed5`
- `msvcrt!free` at `0x18000aee5`
- `msvcrt!free` at `0x18000aef5`
- `msvcrt!free` at `0x18000aed5`
- `msvcrt!free` at `0x18000aee5`
- `msvcrt!free` at `0x18000aef5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EnumerateNfsSharePermissionByName(
        const struct _MSFT_NfsServerTasks_GetSharePermissionByName *a1,
        struct _MI_Context *a2)
{
  unsigned int (*v4)(void *, struct _NFS_EXPORT_FENCING *, struct _NFS_EXPORT *); // r9
  wchar_t **v5; // r15
  enum _MI_Result v6; // esi
  __int64 v7; // r14
  const wchar_t *v8; // r12
  __int64 v9; // rbx
  rsize_t v10; // rbx
  const wchar_t *v11; // r12
  __int64 v12; // rbx
  rsize_t v13; // rbx
  const wchar_t *v14; // r12
  unsigned __int16 *v15; // r8
  unsigned int v16; // ebx
  char v17; // cl
  char v18; // al
  const wchar_t *v19; // r10
  const wchar_t *v20; // r11
  char v21; // al
  const wchar_t *v22; // r8
  const wchar_t *v23; // rdx
  const wchar_t *v24; // rax
  const wchar_t *v25; // r9
  unsigned int v26; // [rsp+50h] [rbp-B0h] BYREF
  void *Block[2]; // [rsp+58h] [rbp-A8h] BYREF
  void *v28[2]; // [rsp+68h] [rbp-98h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  _QWORD v30[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v31; // [rsp+90h] [rbp-70h]
  struct _MI_Context *v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A4h] [rbp-5Ch]
  MI_Instance instance; // [rsp+B0h] [rbp-50h] BYREF
  int ReturnValue; // [rsp+F0h] [rbp-10h]
  char v37; // [rsp+F4h] [rbp-Ch]

  v30[0] = &CWMIContext::`vftable';
  v32 = a2;
  v30[1] = 0;
  v31 = 0;
  v34 = 0;
  v33 = 0;
  *(_OWORD *)Block = 0;
  *(_OWORD *)v28 = 0;
  v29 = 1;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xA8u);
  Block[0] = v30;
  if ( *((_BYTE *)a1 + 80)
    && ((v5 = (wchar_t **)((char *)a1 + 120), !*((_BYTE *)a1 + 128)) || ValidateClientType(*v5, &v26))
    && (!*((_BYTE *)a1 + 144) || ValidatePermission(*((wchar_t **)a1 + 17), &v26)) )
  {
    v6 = MI_RESULT_OK;
    v7 = -1;
    if ( *((_BYTE *)a1 + 112) )
    {
      v8 = (const wchar_t *)*((_QWORD *)a1 + 13);
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v10 = v9 + 1;
      Block[1] = malloc(2 * v10);
      wcscpy_s((wchar_t *)Block[1], v10, v8);
    }
    if ( *((_BYTE *)a1 + 128) )
    {
      v11 = *v5;
      v12 = -1;
      do
        ++v12;
      while ( v11[v12] );
      v13 = v12 + 1;
      v28[0] = malloc(2 * v13);
      wcscpy_s((wchar_t *)v28[0], v13, v11);
    }
    if ( *((_BYTE *)a1 + 144) )
    {
      v14 = (const wchar_t *)*((_QWORD *)a1 + 17);
      do
        ++v7;
      while ( v14[v7] );
      v28[1] = malloc(2 * (v7 + 1));
      wcscpy_s((wchar_t *)v28[1], v7 + 1, v14);
    }
    if ( *((_BYTE *)a1 + 96) )
      v15 = (unsigned __int16 *)*((_QWORD *)a1 + 11);
    else
      v15 = 0;
    v16 = EnumSharePermission(*((wchar_t **)a1 + 9), 0, v15, v4, Block, (struct CNfsTaskContext *)v30);
    if ( !v16 && !HIDWORD(v29) )
    {
      v17 = *((_BYTE *)a1 + 112);
      if ( v17 || *((_BYTE *)a1 + 128) || *((_BYTE *)a1 + 144) )
      {
        v16 = 1168;
        v18 = *((_BYTE *)a1 + 144);
        if ( v18 )
          v19 = (const wchar_t *)*((_QWORD *)a1 + 17);
        else
          v19 = &pServiceName;
        v20 = L" Permission=";
        if ( !v18 )
          v20 = &pServiceName;
        v21 = *((_BYTE *)a1 + 128);
        if ( v21 )
          v22 = *v5;
        else
          v22 = &pServiceName;
        v23 = L" ClientType=";
        if ( !v21 )
          v23 = &pServiceName;
        if ( v17 )
          v24 = (const wchar_t *)*((_QWORD *)a1 + 13);
        else
          v24 = &pServiceName;
        v25 = L" ClientName=";
        if ( !v17 )
          v25 = &pServiceName;
        CWMIContext::WriteError((CWMIContext *)v30, 0x490u, 0xC0001066, v25, v24, v23, v22, v20, v19);
      }
    }
    LODWORD(v34) = v16;
  }
  else
  {
    v6 = MI_RESULT_INVALID_PARAMETER;
  }
  if ( Block[1] )
    free(Block[1]);
  if ( v28[0] )
    free(v28[0]);
  if ( v28[1] )
    free(v28[1]);
  if ( v6 == MI_RESULT_OK )
  {
    v6 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_GetSharePermissionByName_rtti, &instance);
    if ( v6 == MI_RESULT_OK )
    {
      ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v30);
      v37 = 1;
      MI_Instance_Destruct((MI_Instance *)a2);
      v6 = MI_Instance_Destruct(&instance);
    }
  }
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v30, v6);
  CWMIContext::~CWMIContext((CWMIContext *)v30);
}

```

## disassembly

```asm
0x18000ac38  mov     [rsp-8+arg_10], rbx
0x18000ac3d  push    rbp
0x18000ac3e  push    rsi
0x18000ac3f  push    rdi
0x18000ac40  push    r12
0x18000ac42  push    r13
0x18000ac44  push    r14
0x18000ac46  push    r15
0x18000ac48  lea     rbp, [rsp-70h]
0x18000ac4d  sub     rsp, 170h
0x18000ac54  mov     rax, cs:__security_cookie
0x18000ac5b  xor     rax, rsp
0x18000ac5e  mov     [rbp+0A0h+var_40], rax
0x18000ac62  mov     r13, rdx
0x18000ac65  mov     rdi, rcx
0x18000ac68  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000ac6f  mov     [rbp+0A0h+var_120], rax
0x18000ac73  mov     [rbp+0A0h+var_108], rdx
0x18000ac77  xor     r12d, r12d
0x18000ac7a  mov     [rbp+0A0h+var_118], r12
0x18000ac7e  mov     [rbp+0A0h+var_110], r12w
0x18000ac83  mov     [rbp+0A0h+var_FC], r12
0x18000ac87  mov     [rbp+0A0h+var_100], r12d
0x18000ac8b  xorps   xmm0, xmm0
0x18000ac8e  xor     eax, eax
0x18000ac90  movups  xmmword ptr [rsp+1A0h+Block], xmm0
0x18000ac95  movups  xmmword ptr [rsp+1A0h+var_138], xmm0
0x18000ac9a  mov     [rsp+1A0h+var_128], rax
0x18000ac9f  mov     [rbp+0A0h+instance.ft], r12
0x18000aca3  xor     edx, edx; Val
0x18000aca5  mov     r8d, 0A8h; Size
0x18000acab  lea     rcx, [rbp+0A0h+instance.classDecl]; void *
0x18000acaf  call    memset_0
0x18000acb4  lea     rax, [rbp+0A0h+var_120]
0x18000acb8  mov     [rsp+1A0h+Block], rax
0x18000acbd  mov     byte ptr [rsp+1A0h+var_128], 1
0x18000acc2  mov     dword ptr [rsp+1A0h+var_128+4], r12d
0x18000acc7  cmp     [rdi+50h], r12b
0x18000accb  jz      short loc_18000AD09
0x18000accd  lea     r15, [rdi+78h]
0x18000acd1  cmp     [rdi+80h], r12b
0x18000acd8  jz      short loc_18000ACEB
0x18000acda  lea     rdx, [rsp+1A0h+var_150]; unsigned int *
0x18000acdf  mov     rcx, [r15]; String2
0x18000ace2  call    ?ValidateClientType@@YAEPEBGPEAK@Z; ValidateClientType(ushort const *,ulong *)
0x18000ace7  test    al, al
0x18000ace9  jz      short loc_18000AD09
0x18000aceb  cmp     [rdi+90h], r12b
0x18000acf2  jz      short loc_18000AD13
0x18000acf4  lea     rdx, [rsp+1A0h+var_150]; unsigned int *
0x18000acf9  mov     rcx, [rdi+88h]; String2
0x18000ad00  call    ?ValidatePermission@@YAEPEBGPEAK@Z; ValidatePermission(ushort const *,ulong *)
0x18000ad05  test    al, al
0x18000ad07  jnz     short loc_18000AD13
0x18000ad09  mov     esi, 4
0x18000ad0e  jmp     loc_18000AECB
0x18000ad13  mov     esi, r12d
0x18000ad16  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000ad1a  cmp     [rdi+70h], r12b
0x18000ad1e  jz      short loc_18000AD57
0x18000ad20  mov     r12, [rdi+68h]
0x18000ad24  mov     rbx, r14
0x18000ad27  xor     eax, eax
0x18000ad29  inc     rbx
0x18000ad2c  cmp     [r12+rbx*2], ax
0x18000ad31  jnz     short loc_18000AD29
0x18000ad33  inc     rbx
0x18000ad36  lea     rcx, [rbx+rbx]; Size
0x18000ad3a  call    cs:__imp_malloc
0x18000ad40  mov     [rsp+1A0h+Block+8], rax
0x18000ad45  mov     r8, r12; Source
0x18000ad48  mov     rdx, rbx; SizeInWords
0x18000ad4b  mov     rcx, rax; Destination
0x18000ad4e  call    cs:__imp_wcscpy_s
0x18000ad54  xor     r12d, r12d
0x18000ad57  cmp     [rdi+80h], r12b
0x18000ad5e  jz      short loc_18000AD96
0x18000ad60  mov     r12, [r15]
0x18000ad63  mov     rbx, r14
0x18000ad66  xor     eax, eax
0x18000ad68  inc     rbx
0x18000ad6b  cmp     [r12+rbx*2], ax
0x18000ad70  jnz     short loc_18000AD68
0x18000ad72  inc     rbx
0x18000ad75  lea     rcx, [rbx+rbx]; Size
0x18000ad79  call    cs:__imp_malloc
0x18000ad7f  mov     [rsp+1A0h+var_138], rax
0x18000ad84  mov     r8, r12; Source
0x18000ad87  mov     rdx, rbx; SizeInWords
0x18000ad8a  mov     rcx, rax; Destination
0x18000ad8d  call    cs:__imp_wcscpy_s
0x18000ad93  xor     r12d, r12d
0x18000ad96  cmp     [rdi+90h], r12b
0x18000ad9d  jz      short loc_18000ADD7
0x18000ad9f  mov     r12, [rdi+88h]
0x18000ada6  xor     eax, eax
0x18000ada8  inc     r14
0x18000adab  cmp     [r12+r14*2], ax
0x18000adb0  jnz     short loc_18000ADA8
0x18000adb2  lea     rbx, [r14+1]
0x18000adb6  lea     rcx, [rbx+rbx]; Size
0x18000adba  call    cs:__imp_malloc
0x18000adc0  mov     [rsp+1A0h+var_138+8], rax
0x18000adc5  mov     r8, r12; Source
0x18000adc8  mov     rdx, rbx; SizeInWords
0x18000adcb  mov     rcx, rax; Destination
0x18000adce  call    cs:__imp_wcscpy_s
0x18000add4  xor     r12d, r12d
0x18000add7  cmp     [rdi+60h], r12b
0x18000addb  jz      short loc_18000ADE3
0x18000addd  mov     r8, [rdi+58h]
0x18000ade1  jmp     short loc_18000ADE6
0x18000ade3  mov     r8, r12; unsigned __int16 *
0x18000ade6  lea     rax, [rbp+0A0h+var_120]
0x18000adea  mov     [rsp+1A0h+var_178], rax; struct CNfsTaskContext *
0x18000adef  lea     rax, [rsp+1A0h+Block]
0x18000adf4  mov     [rsp+1A0h+var_180], rax; void *
0x18000adf9  xor     edx, edx; unsigned __int8
0x18000adfb  mov     rcx, [rdi+48h]; String2
0x18000adff  call    ?EnumSharePermission@@YAKPEAGE0P6AKPEAXPEAU_NFS_EXPORT_FENCING@@PEAU_NFS_EXPORT@@@Z1PEAVCNfsTaskContext@@@Z; EnumSharePermission(ushort *,uchar,ushort *,ulong (*)(void *,_NFS_EXPORT_FENCING *,_NFS_EXPORT *),void *,CNfsTaskContext *)
0x18000ae04  mov     ebx, eax
0x18000ae06  test    eax, eax
0x18000ae08  jnz     loc_18000AEC8
0x18000ae0e  cmp     dword ptr [rsp+1A0h+var_128+4], r12d
0x18000ae13  jnz     loc_18000AEC8
0x18000ae19  mov     cl, [rdi+70h]
0x18000ae1c  test    cl, cl
0x18000ae1e  jnz     short loc_18000AE36
0x18000ae20  cmp     [rdi+80h], r12b
0x18000ae27  jnz     short loc_18000AE36
0x18000ae29  cmp     [rdi+90h], r12b
0x18000ae30  jz      loc_18000AEC8
0x18000ae36  mov     ebx, 490h
0x18000ae3b  mov     al, [rdi+90h]
0x18000ae41  lea     r14, pServiceName
0x18000ae48  test    al, al
0x18000ae4a  jz      short loc_18000AE55
0x18000ae4c  mov     r10, [rdi+88h]
0x18000ae53  jmp     short loc_18000AE58
0x18000ae55  mov     r10, r14
0x18000ae58  lea     r11, aPermission; " Permission="
0x18000ae5f  test    al, al
0x18000ae61  cmovz   r11, r14
0x18000ae65  mov     al, [rdi+80h]
0x18000ae6b  test    al, al
0x18000ae6d  jz      short loc_18000AE74
0x18000ae6f  mov     r8, [r15]
0x18000ae72  jmp     short loc_18000AE77
0x18000ae74  mov     r8, r14
0x18000ae77  lea     rdx, aClienttype; " ClientType="
0x18000ae7e  test    al, al
0x18000ae80  cmovz   rdx, r14
0x18000ae84  test    cl, cl
0x18000ae86  jz      short loc_18000AE8E
0x18000ae88  mov     rax, [rdi+68h]
0x18000ae8c  jmp     short loc_18000AE91
0x18000ae8e  mov     rax, r14
0x18000ae91  lea     r9, aClientname; " ClientName="
0x18000ae98  test    cl, cl
0x18000ae9a  cmovz   r9, r14
0x18000ae9e  mov     [rsp+1A0h+var_160], r10
0x18000aea3  mov     [rsp+1A0h+var_168], r11
0x18000aea8  mov     [rsp+1A0h+var_170], r8
0x18000aead  mov     [rsp+1A0h+var_178], rdx
0x18000aeb2  mov     [rsp+1A0h+var_180], rax
0x18000aeb7  mov     r8d, 0C0001066h; unsigned int
0x18000aebd  mov     edx, ebx; unsigned int
0x18000aebf  lea     rcx, [rbp+0A0h+var_120]; this
0x18000aec3  call    ?WriteError@CWMIContext@@UEAAXKKZZ; CWMIContext::WriteError(ulong,ulong,...)
0x18000aec8  mov     dword ptr [rbp+0A0h+var_FC], ebx
0x18000aecb  mov     rcx, [rsp+1A0h+Block+8]; Block
0x18000aed0  test    rcx, rcx
0x18000aed3  jz      short loc_18000AEDB
0x18000aed5  call    cs:__imp_free
0x18000aedb  mov     rcx, [rsp+1A0h+var_138]; Block
0x18000aee0  test    rcx, rcx
0x18000aee3  jz      short loc_18000AEEB
0x18000aee5  call    cs:__imp_free
0x18000aeeb  mov     rcx, [rsp+1A0h+var_138+8]; Block
0x18000aef0  test    rcx, rcx
0x18000aef3  jz      short loc_18000AEFB
0x18000aef5  call    cs:__imp_free
0x18000aefb  test    esi, esi
0x18000aefd  jnz     short loc_18000AF3F
0x18000aeff  lea     r8, [rbp+0A0h+instance]; instance
0x18000af03  lea     rdx, MSFT_NfsServerTasks_GetSharePermissionByName_rtti; methodDecl
0x18000af0a  mov     rcx, r13; context
0x18000af0d  call    MI_Context_ConstructParameters
0x18000af12  mov     esi, eax
0x18000af14  test    eax, eax
0x18000af16  jnz     short loc_18000AF3F
0x18000af18  lea     rcx, [rbp+0A0h+var_120]; this
0x18000af1c  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000af21  mov     [rbp+0A0h+var_B0], eax
0x18000af24  mov     [rbp+0A0h+var_AC], 1
0x18000af28  lea     rdx, [rbp+0A0h+instance]
0x18000af2c  mov     rcx, r13; self
0x18000af2f  call    MI_Instance_Destruct
0x18000af34  lea     rcx, [rbp+0A0h+instance]; self
0x18000af38  call    MI_Instance_Destruct
0x18000af3d  mov     esi, eax
0x18000af3f  mov     edx, esi; enum _MI_Result
0x18000af41  lea     rcx, [rbp+0A0h+var_120]; this
0x18000af45  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000af4a  nop
0x18000af4b  lea     rcx, [rbp+0A0h+var_120]; this
0x18000af4f  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000af54  mov     rcx, [rbp+0A0h+var_40]
0x18000af58  xor     rcx, rsp; StackCookie
0x18000af5b  call    __security_check_cookie
0x18000af60  mov     rbx, [rsp+1A0h+arg_10]
0x18000af68  add     rsp, 170h
0x18000af6f  pop     r15
0x18000af71  pop     r14
0x18000af73  pop     r13
0x18000af75  pop     r12
0x18000af77  pop     rdi
0x18000af78  pop     rsi
0x18000af79  pop     rbp
0x18000af7a  retn
```
