# CDXGISwapChain::WaitForFenceOnCPU(IDXGIFenceInternal *,unsigned __int64)

- ea: `0x18009e814`
- end: `0x18009e92e`
- name: `?WaitForFenceOnCPU@CDXGISwapChain@@QEBAJPEAUIDXGIFenceInternal@@_K@Z`
- size: `282`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, struct IDXGIFenceInternal *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001ff98`

## callees

- `0x18000c6b0`
- `0x180014750`
- `0x18002e5d8`
- `0x18009e814`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009e8e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009e8e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e845`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e858`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e858`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDXGISwapChain::WaitForFenceOnCPU(CDXGISwapChain *this, struct IDXGIFenceInternal *a2, __int64 a3)
{
  HANDLE EventA; // rbx
  signed int LastError; // eax
  unsigned int v9; // ebx
  int v10; // edi
  __int64 v11; // rcx
  __int64 v12; // rax
  CModule *v13; // rcx
  __int64 v14; // [rsp+50h] [rbp+18h] BYREF
  HANDLE v15; // [rsp+58h] [rbp+20h] BYREF

  if ( !a3 )
    return 0;
  EventA = CreateEventA(0, 0, 0, 0);
  v15 = EventA;
  if ( !EventA )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  v14 = 0;
  v10 = (**(__int64 (__fastcall ***)(struct IDXGIFenceInternal *, GUID *, __int64 *))a2)(
          a2,
          &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80,
          &v14);
  if ( v10 >= 0 )
  {
    v11 = v14;
LABEL_12:
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, HANDLE))(*(_QWORD *)v11 + 72LL))(v11, a3, EventA);
    if ( v10 >= 0 && WaitForSingleObject(EventA, 0xBB8u) )
    {
      v10 = -2005270489;
      CModule::RecordJournalImpl(v13, -2005270489, "Timed out, CPU wait not signaled.");
    }
    goto LABEL_15;
  }
  if ( *((char *)this + 288) < 0 )
  {
    v12 = (__int64)a2 + 48;
    if ( !a2 )
      v12 = 56;
    v11 = *(_QWORD *)v12;
    goto LABEL_12;
  }
LABEL_15:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  v9 = v10;
LABEL_16:
  SafeHANDLE::Close((SafeHANDLE *)&v15);
  return v9;
}

```

## disassembly

```asm
0x18009e814  mov     [rsp+arg_0], rbx
0x18009e819  mov     [rsp+arg_8], rbp
0x18009e81e  push    rsi
0x18009e81f  push    rdi
0x18009e820  push    r14
0x18009e822  sub     rsp, 20h
0x18009e826  mov     rsi, r8
0x18009e829  mov     r14, rdx
0x18009e82c  mov     rbp, rcx
0x18009e82f  test    r8, r8
0x18009e832  jnz     short loc_18009E83B
0x18009e834  xor     eax, eax
0x18009e836  jmp     loc_18009E91B
0x18009e83b  xor     r9d, r9d; lpName
0x18009e83e  xor     r8d, r8d; bInitialState
0x18009e841  xor     edx, edx; bManualReset
0x18009e843  xor     ecx, ecx; lpEventAttributes
0x18009e845  call    cs:__imp_CreateEventA
0x18009e84b  mov     rbx, rax
0x18009e84e  mov     [rsp+38h+arg_18], rax
0x18009e853  test    rax, rax
0x18009e856  jnz     short loc_18009E876
0x18009e858  call    cs:__imp_GetLastError
0x18009e85e  mov     ebx, eax
0x18009e860  test    eax, eax
0x18009e862  jle     loc_18009E90F
0x18009e868  movzx   ebx, ax
0x18009e86b  or      ebx, 80070000h
0x18009e871  jmp     loc_18009E90F
0x18009e876  mov     [rsp+38h+arg_10], 0
0x18009e87f  mov     rax, [r14]
0x18009e882  lea     r8, [rsp+38h+arg_10]
0x18009e887  lea     rdx, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x18009e88e  mov     rcx, r14
0x18009e891  mov     rax, [rax]
0x18009e894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e899  mov     edi, eax
0x18009e89b  test    eax, eax
0x18009e89d  js      short loc_18009E8A6
0x18009e89f  mov     rcx, [rsp+38h+arg_10]
0x18009e8a4  jmp     short loc_18009E8C2
0x18009e8a6  test    byte ptr [rbp+120h], 80h
0x18009e8ad  jz      short loc_18009E903
0x18009e8af  lea     rax, [r14+30h]
0x18009e8b3  mov     ecx, 38h ; '8'
0x18009e8b8  test    r14, r14
0x18009e8bb  cmovz   rax, rcx
0x18009e8bf  mov     rcx, [rax]
0x18009e8c2  mov     rax, [rcx]
0x18009e8c5  mov     r8, rbx
0x18009e8c8  mov     rdx, rsi
0x18009e8cb  mov     rax, [rax+48h]
0x18009e8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e8d4  mov     edi, eax
0x18009e8d6  test    eax, eax
0x18009e8d8  js      short loc_18009E903
0x18009e8da  mov     edx, 0BB8h; dwMilliseconds
0x18009e8df  mov     rcx, rbx; hHandle
0x18009e8e2  call    cs:__imp_WaitForSingleObject
0x18009e8e8  test    eax, eax
0x18009e8ea  jz      short loc_18009E903
0x18009e8ec  mov     edi, 887A0027h
0x18009e8f1  lea     r8, aTimedOutCpuWai; "Timed out, CPU wait not signaled."
0x18009e8f8  mov     edx, 887A0027h; unsigned int
0x18009e8fd  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18009e902  nop
0x18009e903  lea     rcx, [rsp+38h+arg_10]
0x18009e908  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18009e90d  mov     ebx, edi
0x18009e90f  lea     rcx, [rsp+38h+arg_18]; this
0x18009e914  call    ?Close@SafeHANDLE@@QEAAXXZ; SafeHANDLE::Close(void)
0x18009e919  mov     eax, ebx
0x18009e91b  mov     rbx, [rsp+38h+arg_0]
0x18009e920  mov     rbp, [rsp+38h+arg_8]
0x18009e925  add     rsp, 20h
0x18009e929  pop     r14
0x18009e92b  pop     rdi
0x18009e92c  pop     rsi
0x18009e92d  retn
```
