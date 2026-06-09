# CMSMQQueue::EnableNotification(IMSMQEvent3 *,tagVARIANT *,tagVARIANT *)

- ea: `0x18001aaa0`
- end: `0x18001ad29`
- name: `?EnableNotification@CMSMQQueue@@UEAAJPEAUIMSMQEvent3@@PEAUtagVARIANT@@1@Z`
- size: `649`
- prototype: `__int64 __fastcall(CMSMQQueue *this, struct IMSMQEvent3 *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001aaa0`
- `0x18001ad30`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001aaee`
- `KERNEL32!LeaveCriticalSection` at `0x18001abc5`
- `KERNEL32!LeaveCriticalSection` at `0x18001ac68`
- `KERNEL32!LeaveCriticalSection` at `0x18001acc1`
- `KERNEL32!LeaveCriticalSection` at `0x18001acd2`
- `KERNEL32!LeaveCriticalSection` at `0x18001ad07`
- `KERNEL32!LeaveCriticalSection` at `0x18001aaee`
- `KERNEL32!LeaveCriticalSection` at `0x18001abc5`
- `KERNEL32!LeaveCriticalSection` at `0x18001ac68`
- `KERNEL32!LeaveCriticalSection` at `0x18001acc1`
- `KERNEL32!LeaveCriticalSection` at `0x18001acd2`
- `KERNEL32!LeaveCriticalSection` at `0x18001ad07`
- `KERNEL32!LoadLibraryW` at `0x18001abae`
- `KERNEL32!LoadLibraryW` at `0x18001abae`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001ab5a`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001ab5a`
- `mqrt!MQReceiveMessage` at `0x18001ac9b`
- `mqrt!MQReceiveMessage` at `0x18001ac9b`

## string_xrefs

- `0x18001aba7`: `mqoa.dll`

## pseudocode

```c
__int64 __fastcall CMSMQQueue::EnableNotification(
        CMSMQQueue *this,
        struct IMSMQEvent3 *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // r15
  unsigned int ErrorHelper; // ebx
  HRESULT OptionalReceiveTimeout; // ebx
  unsigned int Lo; // edi
  unsigned int v12; // edi
  DWORD v13; // ebx
  void *hCursor; // rdi
  void (__fastcall *fnReceiveCallback)(int, void *, __int64, __int64); // r14
  __int64 v16; // rcx
  __int64 v18; // [rsp+48h] [rbp-8h] BYREF
  int v19; // [rsp+80h] [rbp+30h] BYREF

  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  CCriticalSection::Lock((CMSMQQueue *)((char *)this + 72));
  if ( *((_DWORD *)this + 44) )
  {
    v18 = 0;
    if ( !a2 )
    {
      OptionalReceiveTimeout = -2147024809;
LABEL_32:
      ErrorHelper = CreateErrorHelper((unsigned int)OptionalReceiveTimeout, 2);
      LeaveCriticalSection(v8);
      return ErrorHelper;
    }
    if ( ((__int64 (__fastcall *)(struct IMSMQEvent3 *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IMSMQPrivateEvent,
           &v18) < 0 )
      goto LABEL_6;
    Lo = 0;
    if ( a3 && a3->vt != 10 )
    {
      OptionalReceiveTimeout = VariantChangeType(a3, a3, 0, 3u);
      if ( OptionalReceiveTimeout < 0 )
        goto LABEL_30;
      Lo = a3->cyVal.Lo;
      if ( Lo > 2 )
      {
LABEL_6:
        OptionalReceiveTimeout = -2147024809;
        goto LABEL_30;
      }
    }
    OptionalReceiveTimeout = GetOptionalReceiveTimeout(a4);
    if ( OptionalReceiveTimeout >= 0 )
    {
      if ( !dword_180038790 )
      {
        CCriticalSection::Lock((CCriticalSection *)&g_csWeirdLoadLibraryWorkaround);
        if ( !dword_180038790 )
        {
          LoadLibraryW(L"mqoa.dll");
          dword_180038790 = 1;
        }
        LeaveCriticalSection(&g_csWeirdLoadLibraryWorkaround);
      }
      if ( Lo )
      {
        v12 = Lo - 1;
        if ( v12 )
        {
          if ( v12 == 1 )
          {
            v13 = -2147483647;
            fnReceiveCallback = ReceiveCallbackNext;
            hCursor = (void *)*((_QWORD *)this + 27);
          }
          else
          {
            v13 = 0;
            hCursor = 0;
            fnReceiveCallback = 0;
          }
LABEL_24:
          v19 = 0;
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v19);
          if ( v19 )
          {
            CCriticalSection::Lock((CCriticalSection *)&g_csCallback);
            v16 = *((_QWORD *)this + 28);
            if ( !v16 || *(_QWORD *)(v16 + 8) )
            {
              OptionalReceiveTimeout = -2147024809;
              LeaveCriticalSection(&g_csCallback);
            }
            else
            {
              *(_QWORD *)(v16 + 8) = v19;
              LeaveCriticalSection(&g_csCallback);
              OptionalReceiveTimeout = MQReceiveMessage(
                                         *((QUEUEHANDLE *)this + 21),
                                         0xFFFFFFFF,
                                         v13,
                                         0,
                                         0,
                                         (PMQRECEIVECALLBACK)fnReceiveCallback,
                                         hCursor,
                                         0);
              if ( OptionalReceiveTimeout < 0 )
              {
                CCriticalSection::Lock((CCriticalSection *)&g_csCallback);
                *(_QWORD *)(*((_QWORD *)this + 28) + 8LL) = 0;
                LeaveCriticalSection(&g_csCallback);
              }
            }
            goto LABEL_30;
          }
          goto LABEL_6;
        }
        fnReceiveCallback = ReceiveCallbackCurrent;
        hCursor = (void *)*((_QWORD *)this + 27);
      }
      else
      {
        fnReceiveCallback = ReceiveCallback;
        hCursor = 0;
      }
      v13 = 0x80000000;
      goto LABEL_24;
    }
LABEL_30:
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
    }
    goto LABEL_32;
  }
  ErrorHelper = CreateErrorHelper(2147745799LL, 2);
  LeaveCriticalSection(v8);
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001aaa0  mov     [rsp-28h+arg_8], rbx
0x18001aaa5  mov     [rsp-28h+arg_10], rsi
0x18001aaaa  push    rbp
0x18001aaab  push    rdi
0x18001aaac  push    r12
0x18001aaae  push    r14
0x18001aab0  push    r15
0x18001aab2  mov     rbp, rsp
0x18001aab5  sub     rsp, 50h
0x18001aab9  mov     r12, r9
0x18001aabc  mov     r14, r8
0x18001aabf  mov     rbx, rdx
0x18001aac2  mov     rsi, rcx
0x18001aac5  lea     r15, [rcx+48h]
0x18001aac9  mov     rcx, r15; this
0x18001aacc  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001aad1  cmp     dword ptr [rsi+0B0h], 0
0x18001aad8  jnz     short loc_18001AAFA
0x18001aada  mov     edx, 2
0x18001aadf  mov     ecx, 80040007h
0x18001aae4  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001aae9  mov     ebx, eax
0x18001aaeb  mov     rcx, r15; lpCriticalSection
0x18001aaee  call    cs:__imp_LeaveCriticalSection
0x18001aaf4  nop
0x18001aaf5  jmp     loc_18001AD0E
0x18001aafa  mov     [rbp+dwTimeout], 0FFFFFFFFh
0x18001ab01  mov     [rbp+var_8], 0
0x18001ab09  test    rbx, rbx
0x18001ab0c  jnz     short loc_18001AB18
0x18001ab0e  mov     ebx, 80070057h
0x18001ab13  jmp     loc_18001ACF6
0x18001ab18  mov     rax, [rbx]
0x18001ab1b  lea     r8, [rbp+var_8]
0x18001ab1f  lea     rdx, IID_IMSMQPrivateEvent
0x18001ab26  mov     rcx, rbx
0x18001ab29  mov     rax, [rax]
0x18001ab2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab31  test    eax, eax
0x18001ab33  jns     short loc_18001AB3F
0x18001ab35  mov     ebx, 80070057h
0x18001ab3a  jmp     loc_18001ACD9
0x18001ab3f  xor     edi, edi
0x18001ab41  test    r14, r14
0x18001ab44  jz      short loc_18001AB73
0x18001ab46  cmp     word ptr [r14], 0Ah
0x18001ab4b  jz      short loc_18001AB73
0x18001ab4d  lea     r9d, [rdi+3]; vt
0x18001ab51  xor     r8d, r8d; wFlags
0x18001ab54  mov     rdx, r14; pvarSrc
0x18001ab57  mov     rcx, r14; pvargDest
0x18001ab5a  call    cs:__imp_VariantChangeType
0x18001ab60  mov     ebx, eax
0x18001ab62  test    eax, eax
0x18001ab64  js      loc_18001ACD9
0x18001ab6a  mov     edi, [r14+8]
0x18001ab6e  cmp     edi, 2
0x18001ab71  ja      short loc_18001AB35
0x18001ab73  lea     rdx, [rbp+dwTimeout]
0x18001ab77  mov     rcx, r12; pvargDest
0x18001ab7a  call    GetOptionalReceiveTimeout
0x18001ab7f  mov     ebx, eax
0x18001ab81  test    eax, eax
0x18001ab83  js      loc_18001ACD9
0x18001ab89  cmp     cs:dword_180038790, 0
0x18001ab90  jnz     short loc_18001ABCC
0x18001ab92  lea     rcx, ?g_csWeirdLoadLibraryWorkaround@@3VCCriticalSection@@A; this
0x18001ab99  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001ab9e  cmp     cs:dword_180038790, 0
0x18001aba5  jnz     short loc_18001ABBE
0x18001aba7  lea     rcx, aMqoaDll_0; "mqoa.dll"
0x18001abae  call    cs:__imp_LoadLibraryW
0x18001abb4  mov     cs:dword_180038790, 1
0x18001abbe  lea     rcx, ?g_csWeirdLoadLibraryWorkaround@@3VCCriticalSection@@A; lpCriticalSection
0x18001abc5  call    cs:__imp_LeaveCriticalSection
0x18001abcb  nop
0x18001abcc  test    edi, edi
0x18001abce  jz      short loc_18001AC08
0x18001abd0  sub     edi, 1
0x18001abd3  jz      short loc_18001ABF8
0x18001abd5  cmp     edi, 1
0x18001abd8  jz      short loc_18001ABE3
0x18001abda  xor     ebx, ebx
0x18001abdc  xor     edi, edi
0x18001abde  xor     r14d, r14d
0x18001abe1  jmp     short loc_18001AC16
0x18001abe3  mov     ebx, 80000001h
0x18001abe8  lea     r14, ?ReceiveCallbackNext@@YAXJPEAXKKPEAUtagMQMSGPROPS@@PEAU_OVERLAPPED@@0@Z; ReceiveCallbackNext(long,void *,ulong,ulong,tagMQMSGPROPS *,_OVERLAPPED *,void *)
0x18001abef  mov     rdi, [rsi+0D8h]
0x18001abf6  jmp     short loc_18001AC16
0x18001abf8  lea     r14, ?ReceiveCallbackCurrent@@YAXJPEAXKKPEAUtagMQMSGPROPS@@PEAU_OVERLAPPED@@0@Z; ReceiveCallbackCurrent(long,void *,ulong,ulong,tagMQMSGPROPS *,_OVERLAPPED *,void *)
0x18001abff  mov     rdi, [rsi+0D8h]
0x18001ac06  jmp     short loc_18001AC11
0x18001ac08  lea     r14, ?ReceiveCallback@@YAXJPEAXKKPEAUtagMQMSGPROPS@@PEAU_OVERLAPPED@@0@Z; ReceiveCallback(long,void *,ulong,ulong,tagMQMSGPROPS *,_OVERLAPPED *,void *)
0x18001ac0f  xor     edi, edi
0x18001ac11  mov     ebx, 80000000h
0x18001ac16  mov     [rbp+arg_0], 0
0x18001ac1d  mov     rcx, [rbp+var_8]
0x18001ac21  mov     rax, [rcx]
0x18001ac24  lea     rdx, [rbp+arg_0]
0x18001ac28  mov     rax, [rax+38h]
0x18001ac2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac31  cmp     [rbp+arg_0], 0
0x18001ac35  jz      loc_18001AB35
0x18001ac3b  lea     r12, ?g_csCallback@@3VCCriticalSection@@A; CCriticalSection g_csCallback
0x18001ac42  mov     rcx, r12; this
0x18001ac45  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001ac4a  mov     rcx, [rsi+0E0h]
0x18001ac51  test    rcx, rcx
0x18001ac54  jz      short loc_18001ACCA
0x18001ac56  cmp     qword ptr [rcx+8], 0
0x18001ac5b  jnz     short loc_18001ACCA
0x18001ac5d  movsxd  rax, [rbp+arg_0]
0x18001ac61  mov     [rcx+8], rax
0x18001ac65  mov     rcx, r12; lpCriticalSection
0x18001ac68  call    cs:__imp_LeaveCriticalSection
0x18001ac6e  nop
0x18001ac6f  mov     [rsp+50h+pTransaction], 0; pTransaction
0x18001ac78  mov     [rsp+50h+hCursor], rdi; hCursor
0x18001ac7d  mov     [rsp+50h+fnReceiveCallback], r14; fnReceiveCallback
0x18001ac82  mov     [rsp+50h+lpOverlapped], 0; lpOverlapped
0x18001ac8b  xor     r9d, r9d; pMessageProps
0x18001ac8e  mov     r8d, ebx; dwAction
0x18001ac91  mov     edx, [rbp+dwTimeout]; dwTimeout
0x18001ac94  mov     rcx, [rsi+0A8h]; hSource
0x18001ac9b  call    cs:__imp_MQReceiveMessage
0x18001aca1  mov     ebx, eax
0x18001aca3  test    eax, eax
0x18001aca5  jns     short loc_18001ACD9
0x18001aca7  mov     rcx, r12; this
0x18001acaa  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001acaf  mov     rax, [rsi+0E0h]
0x18001acb6  mov     qword ptr [rax+8], 0
0x18001acbe  mov     rcx, r12; lpCriticalSection
0x18001acc1  call    cs:__imp_LeaveCriticalSection
0x18001acc7  nop
0x18001acc8  jmp     short loc_18001ACD9
0x18001acca  mov     ebx, 80070057h
0x18001accf  mov     rcx, r12; lpCriticalSection
0x18001acd2  call    cs:__imp_LeaveCriticalSection
0x18001acd8  nop
0x18001acd9  mov     rcx, [rbp+var_8]
0x18001acdd  test    rcx, rcx
0x18001ace0  jz      short loc_18001ACF6
0x18001ace2  mov     rax, [rcx]
0x18001ace5  mov     rax, [rax+10h]
0x18001ace9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acee  mov     [rbp+var_8], 0
0x18001acf6  mov     edx, 2
0x18001acfb  mov     ecx, ebx
0x18001acfd  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001ad02  mov     ebx, eax
0x18001ad04  mov     rcx, r15; lpCriticalSection
0x18001ad07  call    cs:__imp_LeaveCriticalSection
0x18001ad0d  nop
0x18001ad0e  mov     eax, ebx
0x18001ad10  lea     r11, [rsp+50h+var_s0]
0x18001ad15  mov     rbx, [r11+38h]
0x18001ad19  mov     rsi, [r11+40h]
0x18001ad1d  mov     rsp, r11
0x18001ad20  pop     r15
0x18001ad22  pop     r14
0x18001ad24  pop     r12
0x18001ad26  pop     rdi
0x18001ad27  pop     rbp
0x18001ad28  retn
```
