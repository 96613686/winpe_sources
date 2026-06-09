# GrantNfsSharePermissionByName(_MSFT_NfsServerTasks_GrantSharePermissionByName const *,_MI_Context *)

- ea: `0x18000b9d8`
- end: `0x18000bc9e`
- name: `?GrantNfsSharePermissionByName@@YAKPEBU_MSFT_NfsServerTasks_GrantSharePermissionByName@@PEAU_MI_Context@@@Z`
- size: `710`
- prototype: `unsigned int(const struct _MSFT_NfsServerTasks_GrantSharePermissionByName *, struct _MI_Context *)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008b80`

## callees

- `0x1800098c4`
- `0x18000b2ac`
- `0x18000b620`
- `0x18000b9d8`
- `0x18000be24`
- `0x18000be78`
- `0x18000ce30`
- `0x18001d024`
- `0x18001eca0`
- `0x180031648`
- `0x1800316ec`
- `0x180031804`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000bb02`
- `msvcrt!_wcsicmp` at `0x18000bb02`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GrantNfsSharePermissionByName(
        const struct _MSFT_NfsServerTasks_GrantSharePermissionByName *a1,
        struct _MI_Context *a2)
{
  unsigned int v4; // esi
  enum _MI_Result v5; // ebx
  unsigned __int16 *v6; // r8
  unsigned int v7; // eax
  unsigned __int16 *v8; // r8
  unsigned int v10; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v11; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v12; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v13[2]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v14; // [rsp+90h] [rbp-70h]
  struct _MI_Context *v15; // [rsp+98h] [rbp-68h]
  int v16; // [rsp+A0h] [rbp-60h]
  __int64 v17; // [rsp+A4h] [rbp-5Ch]
  MI_Instance instance; // [rsp+B0h] [rbp-50h] BYREF
  int ReturnValue; // [rsp+F0h] [rbp-10h]
  char v20; // [rsp+F4h] [rbp-Ch]

  v11 = 0;
  v4 = 0;
  v12 = 0;
  v10 = 0;
  v13[0] = &CWMIContext::`vftable';
  v15 = a2;
  v13[1] = 0;
  v14 = 0;
  v17 = 0;
  v16 = 0;
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0xA8u);
  if ( !*((_BYTE *)a1 + 80)
    || !*((_BYTE *)a1 + 112)
    || !*((_BYTE *)a1 + 128)
    || *((_BYTE *)a1 + 144) && !ValidatePermission(*((wchar_t **)a1 + 17), &v11) )
  {
    goto LABEL_24;
  }
  if ( *((_BYTE *)a1 + 128) )
  {
    if ( !ValidateClientType(*((wchar_t **)a1 + 15), &v12) )
    {
LABEL_24:
      v5 = MI_RESULT_INVALID_PARAMETER;
      goto LABEL_25;
    }
    v4 = v12;
  }
  if ( *((_BYTE *)a1 + 160) && !ValidateLanguageEncoding(*((wchar_t **)a1 + 19), &v10) )
    goto LABEL_24;
  v5 = MI_RESULT_OK;
  if ( CWMIContext::PromptUser((CWMIContext *)v13, 0x40001006u, *((_QWORD *)a1 + 13), *((_QWORD *)a1 + 9)) )
  {
    if ( _wcsicmp(*((const wchar_t **)a1 + 13), L"All Machines") || v4 != 4 )
    {
      if ( *((_BYTE *)a1 + 96) )
        v8 = (unsigned __int16 *)*((_QWORD *)a1 + 11);
      else
        v8 = 0;
      v7 = AddSharePermission(
             *((wchar_t **)a1 + 9),
             0,
             v8,
             *((unsigned __int16 **)a1 + 13),
             v4,
             (unsigned int *)((unsigned __int64)&v11 & -(__int64)(*((_BYTE *)a1 + 144) != 0)),
             (unsigned int *)((unsigned __int64)&v10 & -(__int64)(*((_BYTE *)a1 + 160) != 0)),
             (unsigned __int8 *)(((unsigned __int64)a1 + 168) & -(__int64)(*((_BYTE *)a1 + 169) != 0)),
             (struct CNfsTaskContext *)v13);
    }
    else
    {
      if ( *((_BYTE *)a1 + 96) )
        v6 = (unsigned __int16 *)*((_QWORD *)a1 + 11);
      else
        v6 = 0;
      v7 = ModifyShare(
             *((wchar_t **)a1 + 9),
             0,
             v6,
             0,
             0,
             0,
             0,
             0,
             (unsigned __int8 *)(((unsigned __int64)a1 + 168) & -(__int64)(*((_BYTE *)a1 + 169) != 0)),
             (unsigned int *)((unsigned __int64)&v10 & -(__int64)(*((_BYTE *)a1 + 160) != 0)),
             0,
             (unsigned int *)((unsigned __int64)&v11 & -(__int64)(*((_BYTE *)a1 + 144) != 0)),
             0,
             (struct CNfsTaskContext *)v13);
    }
    LODWORD(v17) = v7;
    v5 = MI_Context_ConstructParameters(a2, &MSFT_NfsServerTasks_GrantSharePermissionByName_rtti, &instance);
    if ( v5 == MI_RESULT_OK )
    {
      ReturnValue = CWMIContext::GetReturnValue((CWMIContext *)v13);
      v20 = 1;
      MI_Instance_Destruct((MI_Instance *)a2);
      v5 = MI_Instance_Destruct(&instance);
    }
  }
LABEL_25:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v13, v5);
  CWMIContext::~CWMIContext((CWMIContext *)v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b9d8  mov     [rsp-8+arg_10], rbx
0x18000b9dd  push    rbp
0x18000b9de  push    rsi
0x18000b9df  push    rdi
0x18000b9e0  push    r14
0x18000b9e2  push    r15
0x18000b9e4  lea     rbp, [rsp-70h]
0x18000b9e9  sub     rsp, 170h
0x18000b9f0  mov     rax, cs:__security_cookie
0x18000b9f7  xor     rax, rsp
0x18000b9fa  mov     [rbp+90h+var_30], rax
0x18000b9fe  mov     r14, rdx
0x18000ba01  mov     rdi, rcx
0x18000ba04  xor     r15d, r15d
0x18000ba07  mov     [rsp+190h+var_11C], r15d
0x18000ba0c  mov     esi, r15d
0x18000ba0f  mov     [rsp+190h+var_118], r15d
0x18000ba14  mov     [rsp+190h+var_120], r15d
0x18000ba19  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x18000ba20  mov     [rbp+90h+var_110], rax
0x18000ba24  mov     [rbp+90h+var_F8], rdx
0x18000ba28  mov     [rbp+90h+var_108], r15
0x18000ba2c  mov     [rbp+90h+var_100], r15w
0x18000ba31  mov     [rbp+90h+var_EC], r15
0x18000ba35  mov     [rbp+90h+var_F0], r15d
0x18000ba39  mov     [rbp+90h+instance.ft], r15
0x18000ba3d  xor     edx, edx; Val
0x18000ba3f  mov     r8d, 0A8h; Size
0x18000ba45  lea     rcx, [rbp+90h+instance.classDecl]; void *
0x18000ba49  call    memset_0
0x18000ba4e  cmp     [rdi+50h], r15b
0x18000ba52  jz      loc_18000BC5F
0x18000ba58  cmp     [rdi+70h], r15b
0x18000ba5c  jz      loc_18000BC5F
0x18000ba62  cmp     [rdi+80h], r15b
0x18000ba69  jz      loc_18000BC5F
0x18000ba6f  cmp     [rdi+90h], r15b
0x18000ba76  jz      short loc_18000BA91
0x18000ba78  lea     rdx, [rsp+190h+var_11C]; unsigned int *
0x18000ba7d  mov     rcx, [rdi+88h]; String2
0x18000ba84  call    ?ValidatePermission@@YAEPEBGPEAK@Z; ValidatePermission(ushort const *,ulong *)
0x18000ba89  test    al, al
0x18000ba8b  jz      loc_18000BC5F
0x18000ba91  cmp     [rdi+80h], r15b
0x18000ba98  jz      short loc_18000BAB4
0x18000ba9a  lea     rdx, [rsp+190h+var_118]; unsigned int *
0x18000ba9f  mov     rcx, [rdi+78h]; String2
0x18000baa3  call    ?ValidateClientType@@YAEPEBGPEAK@Z; ValidateClientType(ushort const *,ulong *)
0x18000baa8  test    al, al
0x18000baaa  jz      loc_18000BC5F
0x18000bab0  mov     esi, [rsp+190h+var_118]
0x18000bab4  cmp     [rdi+0A0h], r15b
0x18000babb  jz      short loc_18000BAD6
0x18000babd  lea     rdx, [rsp+190h+var_120]; unsigned int *
0x18000bac2  mov     rcx, [rdi+98h]; String2
0x18000bac9  call    ?ValidateLanguageEncoding@@YAEPEAGPEAK@Z; ValidateLanguageEncoding(ushort *,ulong *)
0x18000bace  test    al, al
0x18000bad0  jz      loc_18000BC5F
0x18000bad6  mov     ebx, r15d
0x18000bad9  mov     r9, [rdi+48h]
0x18000badd  mov     r8, [rdi+68h]
0x18000bae1  mov     edx, 40001006h; unsigned int
0x18000bae6  lea     rcx, [rbp+90h+var_110]; this
0x18000baea  call    ?PromptUser@CWMIContext@@UEAAEKZZ; CWMIContext::PromptUser(ulong,...)
0x18000baef  test    al, al
0x18000baf1  jz      loc_18000BC64
0x18000baf7  lea     rdx, aAllMachines; "All Machines"
0x18000bafe  mov     rcx, [rdi+68h]; String1
0x18000bb02  call    cs:__imp__wcsicmp
0x18000bb08  test    eax, eax
0x18000bb0a  jnz     loc_18000BBA8
0x18000bb10  lea     ebx, [rax+4]
0x18000bb13  cmp     esi, ebx
0x18000bb15  jnz     loc_18000BBA8
0x18000bb1b  mov     al, [rdi+90h]
0x18000bb21  neg     al
0x18000bb23  sbb     rdx, rdx
0x18000bb26  lea     rax, [rsp+190h+var_11C]
0x18000bb2b  and     rdx, rax
0x18000bb2e  mov     al, [rdi+0A0h]
0x18000bb34  neg     al
0x18000bb36  sbb     r9, r9
0x18000bb39  lea     rax, [rsp+190h+var_120]
0x18000bb3e  and     r9, rax
0x18000bb41  lea     rcx, [rdi+0A8h]
0x18000bb48  mov     al, [rcx+1]
0x18000bb4b  neg     al
0x18000bb4d  sbb     r10, r10
0x18000bb50  and     r10, rcx
0x18000bb53  cmp     [rdi+60h], r15b
0x18000bb57  jz      short loc_18000BB5F
0x18000bb59  mov     r8, [rdi+58h]
0x18000bb5d  jmp     short loc_18000BB62
0x18000bb5f  mov     r8, r15; unsigned __int16 *
0x18000bb62  lea     rax, [rbp+90h+var_110]
0x18000bb66  mov     [rsp+190h+var_128], rax; struct CNfsTaskContext *
0x18000bb6b  mov     [rsp+190h+var_130], r15; struct _LIST_ENTRY *
0x18000bb70  mov     [rsp+190h+var_138], rdx; unsigned int *
0x18000bb75  mov     [rsp+190h+var_140], r15; unsigned int *
0x18000bb7a  mov     [rsp+190h+var_148], r9; unsigned int *
0x18000bb7f  mov     [rsp+190h+var_150], r10; unsigned __int8 *
0x18000bb84  mov     [rsp+190h+var_158], r15; int *
0x18000bb89  mov     [rsp+190h+var_160], r15; int *
0x18000bb8e  mov     [rsp+190h+var_168], r15; unsigned __int8 *
0x18000bb93  mov     [rsp+190h+var_170], r15; unsigned __int8 *
0x18000bb98  xor     r9d, r9d; unsigned __int16 *
0x18000bb9b  xor     edx, edx; unsigned __int8
0x18000bb9d  mov     rcx, [rdi+48h]; String2
0x18000bba1  call    ?ModifyShare@@YAKPEAGE00PEAE1PEAJ21PEAK33PEAU_LIST_ENTRY@@PEAVCNfsTaskContext@@@Z; ModifyShare(ushort *,uchar,ushort *,ushort *,uchar *,uchar *,long *,long *,uchar *,ulong *,ulong *,ulong *,_LIST_ENTRY *,CNfsTaskContext *)
0x18000bba6  jmp     short loc_18000BC1A
0x18000bba8  lea     rcx, [rdi+0A8h]
0x18000bbaf  mov     al, [rcx+1]
0x18000bbb2  neg     al
0x18000bbb4  sbb     rdx, rdx
0x18000bbb7  and     rdx, rcx
0x18000bbba  mov     al, [rdi+0A0h]
0x18000bbc0  neg     al
0x18000bbc2  sbb     rcx, rcx
0x18000bbc5  lea     rax, [rsp+190h+var_120]
0x18000bbca  and     rcx, rax
0x18000bbcd  mov     al, [rdi+90h]
0x18000bbd3  neg     al
0x18000bbd5  sbb     r9, r9
0x18000bbd8  lea     rax, [rsp+190h+var_11C]
0x18000bbdd  and     r9, rax
0x18000bbe0  cmp     [rdi+60h], r15b
0x18000bbe4  jz      short loc_18000BBEC
0x18000bbe6  mov     r8, [rdi+58h]
0x18000bbea  jmp     short loc_18000BBEF
0x18000bbec  mov     r8, r15; unsigned __int16 *
0x18000bbef  lea     rax, [rbp+90h+var_110]
0x18000bbf3  mov     [rsp+190h+var_150], rax; struct CNfsTaskContext *
0x18000bbf8  mov     [rsp+190h+var_158], rdx; unsigned __int8 *
0x18000bbfd  mov     [rsp+190h+var_160], rcx; unsigned int *
0x18000bc02  mov     [rsp+190h+var_168], r9; unsigned int *
0x18000bc07  mov     dword ptr [rsp+190h+var_170], esi; unsigned int
0x18000bc0b  mov     r9, [rdi+68h]; unsigned __int16 *
0x18000bc0f  xor     edx, edx; unsigned __int8
0x18000bc11  mov     rcx, [rdi+48h]; String2
0x18000bc15  call    ?AddSharePermission@@YAKPEAGE00KPEAK1PEAEPEAVCNfsTaskContext@@@Z; AddSharePermission(ushort *,uchar,ushort *,ushort *,ulong,ulong *,ulong *,uchar *,CNfsTaskContext *)
0x18000bc1a  mov     dword ptr [rbp+90h+var_EC], eax
0x18000bc1d  lea     r8, [rbp+90h+instance]; instance
0x18000bc21  lea     rdx, MSFT_NfsServerTasks_GrantSharePermissionByName_rtti; methodDecl
0x18000bc28  mov     rcx, r14; context
0x18000bc2b  call    MI_Context_ConstructParameters
0x18000bc30  mov     ebx, eax
0x18000bc32  test    eax, eax
0x18000bc34  jnz     short loc_18000BC64
0x18000bc36  lea     rcx, [rbp+90h+var_110]; this
0x18000bc3a  call    ?GetReturnValue@CWMIContext@@QEAAJXZ; CWMIContext::GetReturnValue(void)
0x18000bc3f  mov     [rbp+90h+var_A0], eax
0x18000bc42  mov     [rbp+90h+var_9C], 1
0x18000bc46  lea     rdx, [rbp+90h+instance]
0x18000bc4a  mov     rcx, r14; self
0x18000bc4d  call    MI_Instance_Destruct
0x18000bc52  lea     rcx, [rbp+90h+instance]; self
0x18000bc56  call    MI_Instance_Destruct
0x18000bc5b  mov     ebx, eax
0x18000bc5d  jmp     short loc_18000BC64
0x18000bc5f  mov     ebx, 4
0x18000bc64  mov     edx, ebx; enum _MI_Result
0x18000bc66  lea     rcx, [rbp+90h+var_110]; this
0x18000bc6a  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x18000bc6f  nop
0x18000bc70  lea     rcx, [rbp+90h+var_110]; this
0x18000bc74  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x18000bc79  mov     eax, ebx
0x18000bc7b  mov     rcx, [rbp+90h+var_30]
0x18000bc7f  xor     rcx, rsp; StackCookie
0x18000bc82  call    __security_check_cookie
0x18000bc87  mov     rbx, [rsp+190h+arg_10]
0x18000bc8f  add     rsp, 170h
0x18000bc96  pop     r15
0x18000bc98  pop     r14
0x18000bc9a  pop     rdi
0x18000bc9b  pop     rsi
0x18000bc9c  pop     rbp
0x18000bc9d  retn
```
