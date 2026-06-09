# CDefragEngine::Register(IDefragClient *,_GUID *)

- ea: `0x18001d560`
- end: `0x18001d75d`
- name: `?Register@CDefragEngine@@UEAAJPEAUIDefragClient@@PEAU_GUID@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(CDefragEngine *__hidden this, struct IDefragClient *, struct _GUID *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001d560`
- `0x18001d82c`
- `0x18002530c`
- `0x180025384`
- `0x180038b88`
- `0x18004631c`
- `0x180046494`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d719`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d719`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d627`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d627`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d646`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d659`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d646`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d659`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d66b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001d66b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001d698`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001d698`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDefragEngine::Register(CDefragEngine *this, struct IDefragClient *a2, struct _GUID *a3)
{
  GUID *v6; // rdi
  __int16 v7; // ax
  int v8; // ebx
  __int64 v9; // rcx
  __int16 v10; // ax
  HRESULT started; // [rsp+20h] [rbp-40h] BYREF
  __int16 v13; // [rsp+24h] [rbp-3Ch]
  __int16 v14; // [rsp+26h] [rbp-3Ah]
  unsigned int v15; // [rsp+98h] [rbp+38h] BYREF
  struct CDfClientListItem *v16; // [rsp+A8h] [rbp+48h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&started, "CDefragEngine::Register", 1394, 1);
  v6 = 0;
  v16 = 0;
  v15 = 0;
  v7 = 1402;
  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_21;
  }
  started = 0;
  v13 = 1402;
  if ( *((_DWORD *)this + 38) )
  {
    v8 = -1996488700;
    v7 = 1410;
LABEL_21:
    started = v8;
    goto LABEL_22;
  }
  v8 = CDfClientListItem::CreateInstance(&v16);
  started = v8;
  v6 = (GUID *)v16;
  v7 = 1415;
  if ( v8 < 0 )
  {
LABEL_22:
    v14 = v7;
    goto LABEL_23;
  }
  v13 = 1415;
  (*(void (__fastcall **)(struct IDefragClient *))(*(_QWORD *)a2 + 8LL))(a2);
  v9 = *(_QWORD *)v6->Data4;
  if ( v9 )
  {
    *(_QWORD *)v6->Data4 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  *(_QWORD *)v6->Data4 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( (unsigned __int64)(*((_QWORD *)this + 18) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    while ( WaitForSingleObject(*((HANDLE *)this + 18), 0) )
    {
      if ( WaitForSingleObject(*((HANDLE *)this + 17), 0) == 258 )
        goto LABEL_14;
      Sleep(0xC8u);
    }
  }
  started = CDefragEngine::_StartNotificationThread(this);
  v10 = 1458;
  if ( started < 0 )
    goto LABEL_12;
  v13 = 1458;
LABEL_14:
  started = CoCreateGuid(v6 + 1);
  v10 = 1461;
  if ( started < 0
    || (v13 = 1461,
        *a3 = v6[1],
        started = CSxList<CDfClientList,CDfClientListItem>::InsertTail(*((_QWORD *)this + 14), v6),
        v10 = 1465,
        started < 0) )
  {
LABEL_12:
    v14 = v10;
  }
  else
  {
    v13 = 1465;
    CSxList<CDfClientList,CDfClientListItem>::CalculateCount(*((_QWORD *)this + 14), &v15);
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_bf5248634d2b3b92b4f78ef82fe4291c_Traceguids, v15);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v8 = started;
LABEL_23:
  if ( v6 )
    CDfClientListItem::Release((CDfClientListItem *)v6);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&started);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d560  mov     [rsp-28h+arg_0], rbx
0x18001d565  push    rbp
0x18001d566  push    rsi
0x18001d567  push    rdi
0x18001d568  push    r14
0x18001d56a  push    r15
0x18001d56c  mov     rbp, rsp
0x18001d56f  sub     rsp, 60h
0x18001d573  mov     r15, r8
0x18001d576  mov     r14, rdx
0x18001d579  mov     rsi, rcx
0x18001d57c  mov     r9d, 1; unsigned __int16
0x18001d582  mov     r8d, 572h; unsigned __int16
0x18001d588  lea     rdx, aCdefragengineR_1; "CDefragEngine::Register"
0x18001d58f  lea     rcx, [rbp+var_40]; this
0x18001d593  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001d598  nop
0x18001d599  xor     edi, edi
0x18001d59b  mov     [rbp+arg_18], rdi
0x18001d59f  mov     [rbp+arg_8], edi
0x18001d5a2  mov     eax, 57Ah
0x18001d5a7  test    r14, r14
0x18001d5aa  jz      loc_18001D724
0x18001d5b0  mov     [rbp+var_40], edi
0x18001d5b3  mov     [rbp+var_3C], ax
0x18001d5b7  cmp     [rsi+98h], edi
0x18001d5bd  jz      short loc_18001D5CE
0x18001d5bf  mov     ebx, 89000004h
0x18001d5c4  mov     eax, 582h
0x18001d5c9  jmp     loc_18001D729
0x18001d5ce  lea     rcx, [rbp+arg_18]; struct CDfClientListItem **
0x18001d5d2  call    ?CreateInstance@CDfClientListItem@@SAJPEAPEAV1@@Z; CDfClientListItem::CreateInstance(CDfClientListItem * *)
0x18001d5d7  mov     ebx, eax
0x18001d5d9  mov     [rbp+var_40], eax
0x18001d5dc  mov     rdi, [rbp+arg_18]
0x18001d5e0  test    eax, eax
0x18001d5e2  mov     eax, 587h
0x18001d5e7  js      loc_18001D72C
0x18001d5ed  mov     [rbp+var_3C], ax
0x18001d5f1  mov     rax, [r14]
0x18001d5f4  mov     rcx, r14
0x18001d5f7  mov     rax, [rax+8]
0x18001d5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d600  nop
0x18001d601  mov     rcx, [rdi+8]
0x18001d605  test    rcx, rcx
0x18001d608  jz      short loc_18001D61F
0x18001d60a  mov     qword ptr [rdi+8], 0
0x18001d612  mov     rax, [rcx]
0x18001d615  mov     rax, [rax+10h]
0x18001d619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d61e  nop
0x18001d61f  mov     [rdi+8], r14
0x18001d623  lea     rcx, [rsi+40h]; lpCriticalSection
0x18001d627  call    cs:__imp_EnterCriticalSection
0x18001d62d  mov     rax, [rsi+90h]
0x18001d634  dec     rax
0x18001d637  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001d63b  ja      short loc_18001D673
0x18001d63d  xor     edx, edx; dwMilliseconds
0x18001d63f  mov     rcx, [rsi+90h]; hHandle
0x18001d646  call    cs:__imp_WaitForSingleObject
0x18001d64c  test    eax, eax
0x18001d64e  jz      short loc_18001D673
0x18001d650  xor     edx, edx; dwMilliseconds
0x18001d652  mov     rcx, [rsi+88h]; hHandle
0x18001d659  call    cs:__imp_WaitForSingleObject
0x18001d65f  cmp     eax, 102h
0x18001d664  jz      short loc_18001D694
0x18001d666  mov     ecx, 0C8h; dwMilliseconds
0x18001d66b  call    cs:__imp_Sleep
0x18001d671  jmp     short loc_18001D63D
0x18001d673  mov     rcx, rsi; this
0x18001d676  call    ?_StartNotificationThread@CDefragEngine@@AEAAJXZ; CDefragEngine::_StartNotificationThread(void)
0x18001d67b  mov     [rbp+var_40], eax
0x18001d67e  test    eax, eax
0x18001d680  mov     eax, 5B2h
0x18001d685  jns     short loc_18001D690
0x18001d687  mov     [rbp+var_3A], ax
0x18001d68b  jmp     loc_18001D715
0x18001d690  mov     [rbp+var_3C], ax
0x18001d694  lea     rcx, [rdi+10h]; pguid
0x18001d698  call    cs:__imp_CoCreateGuid
0x18001d69e  mov     [rbp+var_40], eax
0x18001d6a1  test    eax, eax
0x18001d6a3  mov     eax, 5B5h
0x18001d6a8  js      short loc_18001D687
0x18001d6aa  mov     [rbp+var_3C], ax
0x18001d6ae  movups  xmm0, xmmword ptr [rdi+10h]
0x18001d6b2  movdqu  xmmword ptr [r15], xmm0
0x18001d6b7  mov     rdx, rdi
0x18001d6ba  mov     rcx, [rsi+70h]
0x18001d6be  call    ?InsertTail@?$CSxList@VCDfClientList@@VCDfClientListItem@@@@QEAAJPEAVCDfClientListItem@@@Z; CSxList<CDfClientList,CDfClientListItem>::InsertTail(CDfClientListItem *)
0x18001d6c3  mov     [rbp+var_40], eax
0x18001d6c6  test    eax, eax
0x18001d6c8  mov     eax, 5B9h
0x18001d6cd  js      short loc_18001D687
0x18001d6cf  mov     [rbp+var_3C], ax
0x18001d6d3  lea     rdx, [rbp+arg_8]
0x18001d6d7  mov     rcx, [rsi+70h]
0x18001d6db  call    ?CalculateCount@?$CSxList@VCDfClientList@@VCDfClientListItem@@@@QEAAJPEAK@Z; CSxList<CDfClientList,CDfClientListItem>::CalculateCount(ulong *)
0x18001d6e0  lea     rax, WPP_GLOBAL_Control
0x18001d6e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6ee  cmp     rcx, rax
0x18001d6f1  jz      short loc_18001D715
0x18001d6f3  test    dword ptr [rcx+1Ch], 8000000h
0x18001d6fa  jz      short loc_18001D715
0x18001d6fc  mov     edx, 0Dh
0x18001d701  mov     r9d, [rbp+arg_8]
0x18001d705  lea     r8, WPP_bf5248634d2b3b92b4f78ef82fe4291c_Traceguids
0x18001d70c  mov     rcx, [rcx+10h]
0x18001d710  call    WPP_SF_d
0x18001d715  lea     rcx, [rsi+40h]; lpCriticalSection
0x18001d719  call    cs:__imp_LeaveCriticalSection
0x18001d71f  mov     ebx, [rbp+var_40]
0x18001d722  jmp     short loc_18001D730
0x18001d724  mov     ebx, 80070057h
0x18001d729  mov     [rbp+var_40], ebx
0x18001d72c  mov     [rbp+var_3A], ax
0x18001d730  test    rdi, rdi
0x18001d733  jz      short loc_18001D73E
0x18001d735  mov     rcx, rdi; this
0x18001d738  call    ?Release@CDfClientListItem@@QEAAKXZ; CDfClientListItem::Release(void)
0x18001d73d  nop
0x18001d73e  lea     rcx, [rbp+var_40]; this
0x18001d742  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001d747  mov     eax, ebx
0x18001d749  mov     rbx, [rsp+60h+arg_0]
0x18001d751  add     rsp, 60h
0x18001d755  pop     r15
0x18001d757  pop     r14
0x18001d759  pop     rdi
0x18001d75a  pop     rsi
0x18001d75b  pop     rbp
0x18001d75c  retn
```
