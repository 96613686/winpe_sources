# CMSMQQueueInfo::Open(long,long,IMSMQQueue4 * *)

- ea: `0x18001da30`
- end: `0x18001dba5`
- name: `?Open@CMSMQQueueInfo@@UEAAJJJPEAPEAUIMSMQQueue4@@@Z`
- size: `373`
- prototype: `int(CMSMQQueueInfo *__hidden this, int, int, struct IMSMQQueue4 **)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180005430`
- `0x18000cb34`
- `0x18001ad80`
- `0x18001d960`
- `0x18001da30`
- `0x18001e10c`
- `0x180029010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001daad`
- `KERNEL32!LeaveCriticalSection` at `0x18001dad3`
- `KERNEL32!LeaveCriticalSection` at `0x18001db59`
- `KERNEL32!LeaveCriticalSection` at `0x18001db8b`
- `KERNEL32!LeaveCriticalSection` at `0x18001daad`
- `KERNEL32!LeaveCriticalSection` at `0x18001dad3`
- `KERNEL32!LeaveCriticalSection` at `0x18001db59`
- `KERNEL32!LeaveCriticalSection` at `0x18001db8b`
- `mqrt!MQOpenQueue` at `0x18001db06`
- `mqrt!MQOpenQueue` at `0x18001db06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMSMQQueueInfo::Open(LPCWSTR *this, DWORD a2, DWORD a3, struct IMSMQQueue4 **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rsi
  unsigned int ErrorHelper; // ebx
  HRESULT updated; // ebx
  __int64 v11; // rdx
  CMSMQQueue *v13; // [rsp+30h] [rbp-38h] BYREF
  struct IMSMQQueue4 *v14; // [rsp+70h] [rbp+8h] BYREF
  QUEUEHANDLE phQueue; // [rsp+88h] [rbp+20h] BYREF

  v8 = (struct _RTL_CRITICAL_SECTION *)(this + 9);
  CCriticalSection::Lock((CCriticalSection *)(this + 9));
  phQueue = 0;
  v14 = 0;
  v13 = 0;
  *a4 = 0;
  if ( (a2 == 129 || a2 == 32 || a2 - 1 <= 1 || a2 == 160) && a3 <= 1 )
  {
    updated = CMSMQQueueInfo::UpdateFormatName((CMSMQQueueInfo *)(this - 1));
    if ( updated >= 0 )
    {
      updated = MQOpenQueue(this[19], a2, a3, &phQueue);
      if ( updated >= 0 )
      {
        updated = CNewMsmqObj<CMSMQQueue>::NewObj(&v13, v11, &v14);
        if ( updated >= 0 )
        {
          updated = CMSMQQueue::Init(v13, this[19], phQueue, a2, a3);
          if ( updated >= 0 )
          {
            *a4 = v14;
            LeaveCriticalSection(v8);
            return 0;
          }
        }
        if ( v14 )
          ((void (__fastcall *)(struct IMSMQQueue4 *))v14->lpVtbl->Release)(v14);
      }
    }
    ErrorHelper = CreateErrorHelper((unsigned int)updated, 4);
    LeaveCriticalSection(v8);
  }
  else
  {
    ErrorHelper = CreateErrorHelper(2147942487LL, 4);
    LeaveCriticalSection(v8);
  }
  return ErrorHelper;
}

```

## disassembly

```asm
0x18001da30  mov     [rsp+arg_8], rbx
0x18001da35  push    rbp
0x18001da36  push    rsi
0x18001da37  push    rdi
0x18001da38  push    r14
0x18001da3a  push    r15
0x18001da3c  sub     rsp, 40h
0x18001da40  mov     r15, r9
0x18001da43  mov     r14d, r8d
0x18001da46  mov     edi, edx
0x18001da48  mov     rbp, rcx
0x18001da4b  lea     rsi, [rcx+48h]
0x18001da4f  mov     rcx, rsi; this
0x18001da52  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18001da57  mov     [rsp+68h+phQueue], 0
0x18001da63  mov     [rsp+68h+arg_0], 0
0x18001da6c  mov     [rsp+68h+var_38], 0
0x18001da75  mov     qword ptr [r15], 0
0x18001da7c  cmp     edi, 81h
0x18001da82  jz      short loc_18001DAB9
0x18001da84  cmp     edi, 20h ; ' '
0x18001da87  jz      short loc_18001DAB9
0x18001da89  lea     eax, [rdi-1]
0x18001da8c  cmp     eax, 1
0x18001da8f  jbe     short loc_18001DAB9
0x18001da91  cmp     edi, 0A0h
0x18001da97  jz      short loc_18001DAB9
0x18001da99  mov     edx, 4
0x18001da9e  mov     ecx, 80070057h
0x18001daa3  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001daa8  mov     ebx, eax
0x18001daaa  mov     rcx, rsi; lpCriticalSection
0x18001daad  call    cs:__imp_LeaveCriticalSection
0x18001dab3  nop
0x18001dab4  jmp     loc_18001DB92
0x18001dab9  cmp     r14d, 1
0x18001dabd  jbe     short loc_18001DADF
0x18001dabf  mov     edx, 4
0x18001dac4  mov     ecx, 80070057h
0x18001dac9  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001dace  mov     ebx, eax
0x18001dad0  mov     rcx, rsi; lpCriticalSection
0x18001dad3  call    cs:__imp_LeaveCriticalSection
0x18001dad9  nop
0x18001dada  jmp     loc_18001DB92
0x18001dadf  lea     rcx, [rbp-8]; this
0x18001dae3  call    ?UpdateFormatName@CMSMQQueueInfo@@IEAAJXZ; CMSMQQueueInfo::UpdateFormatName(void)
0x18001dae8  mov     ebx, eax
0x18001daea  test    eax, eax
0x18001daec  js      loc_18001DB7A
0x18001daf2  lea     r9, [rsp+68h+phQueue]; phQueue
0x18001dafa  mov     r8d, r14d; dwShareMode
0x18001dafd  mov     edx, edi; dwAccess
0x18001daff  mov     rcx, [rbp+98h]; lpwcsFormatName
0x18001db06  call    cs:__imp_MQOpenQueue
0x18001db0c  mov     ebx, eax
0x18001db0e  test    eax, eax
0x18001db10  js      short loc_18001DB7A
0x18001db12  lea     r8, [rsp+68h+arg_0]
0x18001db17  lea     rcx, [rsp+68h+var_38]
0x18001db1c  call    ?NewObj@?$CNewMsmqObj@VCMSMQQueue@@@@SAJPEAPEAV?$CComObject@VCMSMQQueue@@@ATL@@PEBU_GUID@@PEAPEAUIUnknown@@@Z; CNewMsmqObj<CMSMQQueue>::NewObj(ATL::CComObject<CMSMQQueue> * *,_GUID const *,IUnknown * *)
0x18001db21  mov     ebx, eax
0x18001db23  test    eax, eax
0x18001db25  js      short loc_18001DB64
0x18001db27  mov     [rsp+68h+var_48], r14d; int
0x18001db2c  mov     r9d, edi; int
0x18001db2f  mov     r8, [rsp+68h+phQueue]; void *
0x18001db37  mov     rdx, [rbp+98h]; wchar_t *
0x18001db3e  mov     rcx, [rsp+68h+var_38]; this
0x18001db43  call    ?Init@CMSMQQueue@@QEAAJPEB_WPEAXJJ@Z; CMSMQQueue::Init(wchar_t const *,void *,long,long)
0x18001db48  mov     ebx, eax
0x18001db4a  test    eax, eax
0x18001db4c  js      short loc_18001DB64
0x18001db4e  mov     rax, [rsp+68h+arg_0]
0x18001db53  mov     [r15], rax
0x18001db56  mov     rcx, rsi; lpCriticalSection
0x18001db59  call    cs:__imp_LeaveCriticalSection
0x18001db5f  nop
0x18001db60  xor     eax, eax
0x18001db62  jmp     short loc_18001DB94
0x18001db64  mov     rcx, [rsp+68h+arg_0]
0x18001db69  test    rcx, rcx
0x18001db6c  jz      short loc_18001DB7A
0x18001db6e  mov     rax, [rcx]
0x18001db71  mov     rax, [rax+10h]
0x18001db75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db7a  mov     edx, 4
0x18001db7f  mov     ecx, ebx
0x18001db81  call    ?CreateErrorHelper@@YAJJW4MsmqObjType@@@Z; CreateErrorHelper(long,MsmqObjType)
0x18001db86  mov     ebx, eax
0x18001db88  mov     rcx, rsi; lpCriticalSection
0x18001db8b  call    cs:__imp_LeaveCriticalSection
0x18001db91  nop
0x18001db92  mov     eax, ebx
0x18001db94  mov     rbx, [rsp+68h+arg_8]
0x18001db99  add     rsp, 40h
0x18001db9d  pop     r15
0x18001db9f  pop     r14
0x18001dba1  pop     rdi
0x18001dba2  pop     rsi
0x18001dba3  pop     rbp
0x18001dba4  retn
```
