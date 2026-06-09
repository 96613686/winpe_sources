# CKsNotification::IsCameraAccessAllowedForFilter(_KSFILTER *,uchar)

- ea: `0x180045030`
- end: `0x18004540e`
- name: `?IsCameraAccessAllowedForFilter@CKsNotification@@UEAAJPEAU_KSFILTER@@E@Z`
- size: `990`
- prototype: `__int64 __fastcall(CKsNotification *__hidden this, struct _KSFILTER *, unsigned __int8)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000c630`
- `0x18000cc40`
- `0x18000ed64`
- `0x180010de4`
- `0x180015960`
- `0x180018d8c`
- `0x180018f30`
- `0x180018f5c`
- `0x180018fa8`
- `0x180045030`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800453e7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800453e7`
- `ntoskrnl!KeReleaseMutex` at `0x18004517d`
- `ntoskrnl!KeReleaseMutex` at `0x18004530d`
- `ntoskrnl!KeReleaseMutex` at `0x18004517d`
- `ntoskrnl!KeReleaseMutex` at `0x18004530d`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800451b5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1800451b5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800451a6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1800451a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800450e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800452ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800450e8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800452ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800453d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800453d7`

## pseudocode

```c
__int64 __fastcall CKsNotification::IsCameraAccessAllowedForFilter(void **this, struct _KSFILTER *a2, char a3)
{
  PVOID v5; // rsi
  int v6; // r14d
  PVOID *p_Context; // rdi
  __int64 *v8; // rdx
  int CamRpcBinding; // ebx
  struct _KMUTANT *v10; // r13
  void **v11; // r12
  int v12; // edx
  int v13; // r9d
  unsigned int CurrentProcessId; // r15d
  struct _EPROCESS *CurrentProcess; // rax
  int UserSidForProcess; // eax
  int v17; // edx
  int v18; // eax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  const wchar_t *v22; // rax
  __int64 v24; // [rsp+28h] [rbp-38h]
  PVOID P; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-18h] BYREF
  int v27; // [rsp+A8h] [rbp+48h] BYREF
  unsigned __int8 v28; // [rsp+B0h] [rbp+50h]
  void *v29; // [rsp+B8h] [rbp+58h] BYREF

  v28 = a3;
  P = 0;
  v29 = 0;
  v5 = 0;
  v6 = 1;
  p_Context = 0;
  UnicodeString = 0;
  v8 = WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v8) = 5;
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v8,
      a3,
      39,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      (char)a2,
      a3);
  }
  if ( a2 )
  {
    p_Context = &a2[-6].Context;
    if ( a2 == (struct _KSFILTER *)128 )
    {
      CamRpcBinding = -1073741446;
      goto LABEL_36;
    }
  }
  v10 = (struct _KMUTANT *)(this + 2);
  v27 = 0;
  v6 = 0;
  KeWaitForSingleObject(this + 2, Executive, 0, 0, 0);
  v11 = this + 42;
  if ( !this[42] )
  {
    CamRpcBinding = CreateCamRpcBinding(this + 42);
    if ( CamRpcBinding < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_15;
      v13 = 40;
      goto LABEL_14;
    }
  }
  CamRpcBinding = DuplicateCamRpcBinding(*v11, &v29);
  if ( CamRpcBinding < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = 41;
LABEL_14:
    LODWORD(v24) = CamRpcBinding;
    LOBYTE(v12) = 2;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      1,
      v13,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      v24);
  }
LABEL_15:
  KeReleaseMutex((PRKMUTEX)(this + 2), 0);
  if ( CamRpcBinding >= 0 )
  {
    if ( p_Context )
    {
      CurrentProcessId = *((_DWORD *)p_Context + 56);
      CurrentProcess = (struct _EPROCESS *)p_Context[21];
    }
    else
    {
      CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
      CurrentProcess = IoGetCurrentProcess();
    }
    UserSidForProcess = GetUserSidForProcess(CurrentProcess, &P);
    CamRpcBinding = UserSidForProcess;
    if ( UserSidForProcess >= 0 )
    {
      v5 = P;
      v18 = ConvertSidToUnicodeString(P, &UnicodeString);
      CamRpcBinding = v18;
      if ( v18 >= 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_S(
            WPP_GLOBAL_Control->DeviceExtension,
            v19,
            a3,
            44,
            (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
            (__int64)UnicodeString.Buffer);
        v20 = DoCameraAccessCheck(CurrentProcessId, UnicodeString.Buffer, (_DWORD)v29, v28, (__int64)&v27);
        CamRpcBinding = v20;
        if ( v20 < 0 )
        {
          if ( v20 != -1073741790 )
          {
            KeWaitForSingleObject(v10, Executive, 0, 0, 0);
            DeleteCamRpcBinding(*v11);
            *v11 = 0;
            KeReleaseMutex(v10, 0);
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LODWORD(v24) = CamRpcBinding;
            LOBYTE(v21) = 2;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              v21,
              1,
              45,
              (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
              v24);
          }
        }
        v6 = v27;
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v24) = v18;
        LOBYTE(v19) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          1,
          43,
          (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
          v24);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v24) = UserSidForProcess;
        LOBYTE(v17) = 2;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v17,
          1,
          42,
          (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
          v24);
      }
      v5 = P;
    }
  }
LABEL_36:
  if ( v29 )
  {
    DeleteCamRpcBinding(v29);
    v29 = 0;
  }
  if ( !v6 )
    CamRpcBinding = -1073741790;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    v22 = L"ALLOWED";
    if ( CamRpcBinding < 0 )
      v22 = L"DENIED";
    WPP_RECORDER_SF_S(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)L"DENIED",
      a3,
      46,
      (__int64)WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids,
      (__int64)v22);
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)CamRpcBinding;
}

```

## disassembly

```asm
0x180045030  mov     r11, rsp
0x180045033  mov     [r11+8], rbx
0x180045037  mov     [r11+18h], r8b
0x18004503b  push    rbp
0x18004503c  push    rsi
0x18004503d  push    rdi
0x18004503e  push    r12
0x180045040  push    r13
0x180045042  push    r14
0x180045044  push    r15
0x180045046  mov     rbp, rsp
0x180045049  sub     rsp, 60h
0x18004504d  xor     r12d, r12d
0x180045050  movzx   eax, r8b
0x180045054  xorps   xmm0, xmm0
0x180045057  mov     [rbp+P], r12
0x18004505b  mov     rbx, rdx
0x18004505e  mov     [rbp+arg_18], r12
0x180045062  mov     r15, rcx
0x180045065  mov     esi, r12d
0x180045068  lea     r14d, [r12+1]
0x18004506d  mov     edi, r12d
0x180045070  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180045074  lea     r13, WPP_RECORDER_INITIALIZED
0x18004507b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180045082  lea     rdx, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180045089  jz      short loc_1800450B5
0x18004508b  mov     rcx, cs:WPP_GLOBAL_Control
0x180045092  cmp     [rcx+48h], r12w
0x180045097  jz      short loc_1800450B5
0x180045099  mov     rcx, [rcx+40h]
0x18004509d  lea     r9d, [r12+27h]
0x1800450a2  mov     [rsp+60h+var_30], eax
0x1800450a6  mov     [r11-70h], rbx
0x1800450aa  mov     [r11-78h], rdx
0x1800450ae  mov     dl, 5
0x1800450b0  call    WPP_RECORDER_SF_qd
0x1800450b5  test    rbx, rbx
0x1800450b8  jz      short loc_1800450CD
0x1800450ba  lea     rdi, [rbx-80h]
0x1800450be  test    rdi, rdi
0x1800450c1  jnz     short loc_1800450CD
0x1800450c3  mov     ebx, 0C000017Ah
0x1800450c8  jmp     loc_180045364
0x1800450cd  lea     r13, [r15+10h]
0x1800450d1  mov     [rbp+arg_8], r12d
0x1800450d5  mov     rcx, r13; Object
0x1800450d8  mov     [rsp+60h+Timeout], r12; Timeout
0x1800450dd  xor     r9d, r9d; Alertable
0x1800450e0  xor     r8d, r8d; WaitMode
0x1800450e3  xor     edx, edx; WaitReason
0x1800450e5  mov     r14d, r12d
0x1800450e8  call    cs:__imp_KeWaitForSingleObject
0x1800450ef  nop     dword ptr [rax+rax+00h]
0x1800450f4  lea     r12, [r15+150h]
0x1800450fb  cmp     [r12], rsi
0x1800450ff  jnz     short loc_180045127
0x180045101  mov     rcx, r12; void **
0x180045104  call    ?CreateCamRpcBinding@@YAJPEAPEAX@Z; CreateCamRpcBinding(void * *)
0x180045109  mov     ebx, eax
0x18004510b  test    eax, eax
0x18004510d  jns     short loc_180045127
0x18004510f  lea     rax, WPP_RECORDER_INITIALIZED
0x180045116  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004511d  jz      short loc_180045178
0x18004511f  mov     r9d, 28h ; '('
0x180045125  jmp     short loc_180045150
0x180045127  mov     rcx, [r12]; void *
0x18004512b  lea     rdx, [rbp+arg_18]; void **
0x18004512f  call    ?DuplicateCamRpcBinding@@YAJPEAXPEAPEAX@Z; DuplicateCamRpcBinding(void *,void * *)
0x180045134  mov     ebx, eax
0x180045136  test    eax, eax
0x180045138  jns     short loc_180045178
0x18004513a  lea     rax, WPP_RECORDER_INITIALIZED
0x180045141  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180045148  jz      short loc_180045178
0x18004514a  mov     r9d, 29h ; ')'
0x180045150  mov     rcx, cs:WPP_GLOBAL_Control
0x180045157  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x18004515e  mov     dword ptr [rsp+60h+var_38], ebx
0x180045162  mov     r8d, 1
0x180045168  mov     dl, 2
0x18004516a  mov     [rsp+60h+Timeout], rax
0x18004516f  mov     rcx, [rcx+40h]
0x180045173  call    WPP_RECORDER_SF_D
0x180045178  xor     edx, edx; Wait
0x18004517a  mov     rcx, r13; Mutex
0x18004517d  call    cs:__imp_KeReleaseMutex
0x180045184  nop     dword ptr [rax+rax+00h]
0x180045189  test    ebx, ebx
0x18004518b  js      loc_18004535D
0x180045191  test    rdi, rdi
0x180045194  jz      short loc_1800451A6
0x180045196  mov     r15d, [rdi+0E0h]
0x18004519d  mov     rax, [rdi+0A8h]
0x1800451a4  jmp     short loc_1800451C1
0x1800451a6  call    cs:__imp_PsGetCurrentProcessId
0x1800451ad  nop     dword ptr [rax+rax+00h]
0x1800451b2  mov     r15, rax
0x1800451b5  call    cs:__imp_IoGetCurrentProcess
0x1800451bc  nop     dword ptr [rax+rax+00h]
0x1800451c1  lea     rdx, [rbp+P]; void **
0x1800451c5  mov     rcx, rax; struct _EPROCESS *
0x1800451c8  call    ?GetUserSidForProcess@@YAJPEAU_EPROCESS@@PEAPEAX@Z; GetUserSidForProcess(_EPROCESS *,void * *)
0x1800451cd  xor     edi, edi
0x1800451cf  mov     ebx, eax
0x1800451d1  test    eax, eax
0x1800451d3  jns     short loc_180045218
0x1800451d5  lea     r13, WPP_RECORDER_INITIALIZED
0x1800451dc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800451e3  jz      short loc_18004520F
0x1800451e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800451ec  lea     r9d, [rdi+2Ah]
0x1800451f0  mov     dword ptr [rsp+60h+var_38], eax
0x1800451f4  lea     r8d, [rdi+1]
0x1800451f8  lea     rax, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x1800451ff  mov     dl, 2
0x180045201  mov     [rsp+60h+Timeout], rax
0x180045206  mov     rcx, [rcx+40h]
0x18004520a  call    WPP_RECORDER_SF_D
0x18004520f  mov     rsi, [rbp+P]
0x180045213  jmp     loc_180045366
0x180045218  mov     rsi, [rbp+P]
0x18004521c  lea     rdx, [rbp+UnicodeString]; UnicodeString
0x180045220  mov     rcx, rsi; Sid
0x180045223  call    ?ConvertSidToUnicodeString@@YAJPEAXPEAU_UNICODE_STRING@@@Z; ConvertSidToUnicodeString(void *,_UNICODE_STRING *)
0x180045228  mov     ebx, eax
0x18004522a  test    eax, eax
0x18004522c  jns     short loc_180045273
0x18004522e  lea     r13, WPP_RECORDER_INITIALIZED
0x180045235  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18004523c  lea     r15, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180045243  jz      loc_18004536D
0x180045249  mov     rcx, cs:WPP_GLOBAL_Control
0x180045250  mov     r9d, 2Bh ; '+'
0x180045256  mov     dword ptr [rsp+60h+var_38], eax
0x18004525a  mov     dl, 2
0x18004525c  mov     [rsp+60h+Timeout], r15
0x180045261  mov     rcx, [rcx+40h]
0x180045265  lea     r8d, [r9-2Ah]
0x180045269  call    WPP_RECORDER_SF_D
0x18004526e  jmp     loc_18004536D
0x180045273  lea     rax, WPP_RECORDER_INITIALIZED
0x18004527a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180045281  lea     r14, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x180045288  jz      short loc_1800452B4
0x18004528a  mov     rcx, cs:WPP_GLOBAL_Control
0x180045291  cmp     [rcx+48h], di
0x180045295  jz      short loc_1800452B4
0x180045297  mov     rax, [rbp+UnicodeString.Buffer]
0x18004529b  mov     r9d, 2Ch ; ','
0x1800452a1  mov     rcx, [rcx+40h]
0x1800452a5  mov     [rsp+60h+var_38], rax
0x1800452aa  mov     [rsp+60h+Timeout], r14
0x1800452af  call    WPP_RECORDER_SF_S
0x1800452b4  movzx   r9d, [rbp+arg_10]
0x1800452b9  lea     rax, [rbp+arg_8]
0x1800452bd  mov     r8, [rbp+arg_18]
0x1800452c1  mov     ecx, r15d
0x1800452c4  mov     rdx, [rbp+UnicodeString.Buffer]
0x1800452c8  mov     [rsp+60h+Timeout], rax
0x1800452cd  call    DoCameraAccessCheck
0x1800452d2  mov     ebx, eax
0x1800452d4  test    eax, eax
0x1800452d6  jns     short loc_180045354
0x1800452d8  cmp     eax, 0C0000022h
0x1800452dd  jz      short loc_180045319
0x1800452df  xor     r9d, r9d; Alertable
0x1800452e2  mov     [rsp+60h+Timeout], rdi; Timeout
0x1800452e7  xor     r8d, r8d; WaitMode
0x1800452ea  xor     edx, edx; WaitReason
0x1800452ec  mov     rcx, r13; Object
0x1800452ef  call    cs:__imp_KeWaitForSingleObject
0x1800452f6  nop     dword ptr [rax+rax+00h]
0x1800452fb  mov     rcx, [r12]; void *
0x1800452ff  call    ?DeleteCamRpcBinding@@YAXPEAX@Z; DeleteCamRpcBinding(void *)
0x180045304  xor     edx, edx; Wait
0x180045306  mov     [r12], rdi
0x18004530a  mov     rcx, r13; Mutex
0x18004530d  call    cs:__imp_KeReleaseMutex
0x180045314  nop     dword ptr [rax+rax+00h]
0x180045319  lea     r13, WPP_RECORDER_INITIALIZED
0x180045320  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180045327  jz      short loc_18004534E
0x180045329  mov     rcx, cs:WPP_GLOBAL_Control
0x180045330  mov     r9d, 2Dh ; '-'
0x180045336  mov     dword ptr [rsp+60h+var_38], ebx
0x18004533a  mov     dl, 2
0x18004533c  mov     [rsp+60h+Timeout], r14
0x180045341  mov     rcx, [rcx+40h]
0x180045345  lea     r8d, [r9-2Ch]
0x180045349  call    WPP_RECORDER_SF_D
0x18004534e  mov     r14d, [rbp+arg_8]
0x180045352  jmp     short loc_180045366
0x180045354  lea     r13, WPP_RECORDER_INITIALIZED
0x18004535b  jmp     short loc_18004534E
0x18004535d  lea     r13, WPP_RECORDER_INITIALIZED
0x180045364  xor     edi, edi
0x180045366  lea     r15, WPP_0f409e30936e3eb7e2fb5867878996e2_Traceguids
0x18004536d  mov     rcx, [rbp+arg_18]; void *
0x180045371  test    rcx, rcx
0x180045374  jz      short loc_18004537F
0x180045376  call    ?DeleteCamRpcBinding@@YAXPEAX@Z; DeleteCamRpcBinding(void *)
0x18004537b  mov     [rbp+arg_18], rdi
0x18004537f  test    r14d, r14d
0x180045382  mov     eax, 0C0000022h
0x180045387  cmovz   ebx, eax
0x18004538a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180045391  jz      short loc_1800453CD
0x180045393  mov     rcx, cs:WPP_GLOBAL_Control
0x18004539a  cmp     [rcx+48h], di
0x18004539e  jz      short loc_1800453CD
0x1800453a0  mov     rcx, [rcx+40h]
0x1800453a4  lea     rdx, aDenied; "DENIED"
0x1800453ab  test    ebx, ebx
0x1800453ad  lea     rax, aAllowed; "ALLOWED"
0x1800453b4  mov     r9d, 2Eh ; '.'
0x1800453ba  cmovs   rax, rdx
0x1800453be  mov     [rsp+60h+var_38], rax
0x1800453c3  mov     [rsp+60h+Timeout], r15
0x1800453c8  call    WPP_RECORDER_SF_S
0x1800453cd  test    rsi, rsi
0x1800453d0  jz      short loc_1800453E3
0x1800453d2  xor     edx, edx; Tag
0x1800453d4  mov     rcx, rsi; P
0x1800453d7  call    cs:__imp_ExFreePoolWithTag
0x1800453de  nop     dword ptr [rax+rax+00h]
0x1800453e3  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x1800453e7  call    cs:__imp_RtlFreeUnicodeString
0x1800453ee  nop     dword ptr [rax+rax+00h]
0x1800453f3  mov     eax, ebx
0x1800453f5  mov     rbx, [rsp+60h+arg_0]
0x1800453fd  add     rsp, 60h
0x180045401  pop     r15
0x180045403  pop     r14
0x180045405  pop     r13
0x180045407  pop     r12
0x180045409  pop     rdi
0x18004540a  pop     rsi
0x18004540b  pop     rbp
0x18004540c  retn
```
