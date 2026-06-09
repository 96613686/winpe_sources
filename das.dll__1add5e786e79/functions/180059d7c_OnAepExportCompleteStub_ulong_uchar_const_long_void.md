# OnAepExportCompleteStub(ulong,uchar const *,long,void *)

- ea: `0x180059d7c`
- end: `0x180059f8b`
- name: `?OnAepExportCompleteStub@@YAJKPEBEJPEAX@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned int, const unsigned __int8 *, int, void *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005a570`
- `0x18005aac8`
- `0x1800641f0`

## callees

- `0x180009220`
- `0x180009590`
- `0x180059d7c`
- `0x18005b674`
- `0x18005f5b8`
- `0x18007e9d8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059dba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059dba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059ddb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059e06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059f4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059ddb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059e06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059f4f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180059f2f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180059f2f`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180059ef3`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180059ef3`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059daa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180059daa`

## pseudocode

```c
__int64 __fastcall OnAepExportCompleteStub(int a1, const unsigned __int8 *a2, int a3, char *a4)
{
  unsigned int v7; // edi
  wil::details *v8; // rsi
  void *v9; // rdx
  void ***v10; // rsi
  wil::details *v11; // rcx
  size_t v12; // r14
  void *v13; // rcx
  char IsEnabled; // al
  struct _RPC_ASYNC_STATE *v15; // rcx
  RPC_STATUS v16; // eax
  void *v17; // rdx
  void *Src; // [rsp+20h] [rbp-30h] BYREF
  _DWORD v20[2]; // [rsp+28h] [rbp-28h] BYREF
  const unsigned __int8 *v21; // [rsp+30h] [rbp-20h]
  _QWORD v22[3]; // [rsp+38h] [rbp-18h] BYREF
  int Reply; // [rsp+A0h] [rbp+50h] BYREF
  size_t Size; // [rsp+A8h] [rbp+58h] BYREF

  Reply = a3;
  EventActivityIdControl(2u, (LPGUID)(a4 + 8));
  EnterCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
  if ( *((_DWORD *)a4 + 56) )
  {
    v7 = -2147416294;
    *((_DWORD *)a4 + 56) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
    (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
    return v7;
  }
  if ( *((_DWORD *)a4 + 57) )
  {
    v7 = -2147418113;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
    return v7;
  }
  v7 = 0;
  LODWORD(Size) = 0;
  v8 = 0;
  Src = 0;
  if ( !Reply )
  {
    v22[1] = 2;
    v20[1] = 0;
    v22[0] = *((_QWORD *)a4 + 6);
    v20[0] = a1;
    v21 = a2;
    v22[2] = v20;
    v7 = EncodeBlob((struct _ENCODE_OBJECT *)v22, (unsigned int *)&Size, &Src);
    if ( v7 )
    {
      v10 = (void ***)(a4 + 64);
      goto LABEL_14;
    }
    if ( Reply )
    {
LABEL_15:
      v8 = (wil::details *)Src;
      goto LABEL_16;
    }
    v10 = (void ***)(a4 + 64);
    v11 = (wil::details *)**((_QWORD **)a4 + 8);
    if ( v11 )
    {
      wil::details::FreeProcessHeap(v11, v9);
      **v10 = 0;
    }
    v12 = (unsigned int)Size;
    **v10 = (void *)DAF_user_alloc((unsigned int)Size);
    v13 = **v10;
    if ( !v13 )
    {
      v7 = -2147024882;
LABEL_14:
      **v10 = 0;
      **((_DWORD **)a4 + 7) = 0;
      goto LABEL_15;
    }
    v8 = (wil::details *)Src;
    memcpy_0(v13, Src, v12);
    **((_DWORD **)a4 + 7) = v12;
  }
LABEL_16:
  if ( *((_DWORD *)a4 + 72) )
  {
    LODWORD(Size) = 0;
    RpcServerUnsubscribeForNotification(
      *(RPC_BINDING_HANDLE *)(*((_QWORD *)a4 + 4) + 32LL),
      RpcNotificationCallCancel,
      (unsigned int *)&Size);
    (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl'::`2'::impl);
  v15 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a4 + 4);
  if ( !IsEnabled || v15 )
  {
    *((_DWORD *)a4 + 57) = 1;
    v16 = RpcAsyncCompleteCall(v15, &Reply);
    if ( v16 )
    {
      if ( v16 < 0 )
        v7 = v16;
      else
        v7 = (unsigned __int16)v16 | 0x80010000;
    }
    *((_QWORD *)a4 + 4) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a4 + 232));
  (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
  if ( v8 )
    wil::details::FreeProcessHeap(v8, v17);
  return v7;
}

```

## disassembly

```asm
0x180059d7c  mov     [rsp-38h+arg_0], rbx
0x180059d81  mov     [rsp-38h+Reply], r8d
0x180059d86  push    rbp
0x180059d87  push    rsi
0x180059d88  push    rdi
0x180059d89  push    r12
0x180059d8b  push    r13
0x180059d8d  push    r14
0x180059d8f  push    r15
0x180059d91  mov     rbp, rsp
0x180059d94  sub     rsp, 50h
0x180059d98  mov     rbx, r9
0x180059d9b  mov     r14, rdx
0x180059d9e  mov     r15d, ecx
0x180059da1  lea     rdx, [r9+8]; ActivityId
0x180059da5  mov     ecx, 2; ControlCode
0x180059daa  call    cs:__imp_EventActivityIdControl
0x180059db0  lea     r12, [rbx+0E8h]
0x180059db7  mov     rcx, r12; lpCriticalSection
0x180059dba  call    cs:__imp_EnterCriticalSection
0x180059dc0  xor     r13d, r13d
0x180059dc3  cmp     [rbx+0E0h], r13d
0x180059dca  jz      short loc_180059DF5
0x180059dcc  mov     edi, 8001071Ah
0x180059dd1  mov     [rbx+0E0h], r13d
0x180059dd8  mov     rcx, r12; lpCriticalSection
0x180059ddb  call    cs:__imp_LeaveCriticalSection
0x180059de1  mov     rax, [rbx]
0x180059de4  mov     rcx, rbx
0x180059de7  mov     rax, [rax+10h]
0x180059deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059df0  jmp     loc_180059F71
0x180059df5  cmp     [rbx+0E4h], r13d
0x180059dfc  jz      short loc_180059E11
0x180059dfe  mov     edi, 8000FFFFh
0x180059e03  mov     rcx, r12; lpCriticalSection
0x180059e06  call    cs:__imp_LeaveCriticalSection
0x180059e0c  jmp     loc_180059F71
0x180059e11  mov     edi, r13d
0x180059e14  mov     dword ptr [rbp+Size], r13d
0x180059e18  mov     rsi, r13
0x180059e1b  mov     [rbp+Src], r13
0x180059e1f  cmp     [rbp+Reply], r13d
0x180059e23  jnz     loc_180059ED5
0x180059e29  mov     [rbp+var_10], 2
0x180059e31  mov     [rbp+var_24], r13d
0x180059e35  mov     rax, [rbx+30h]
0x180059e39  mov     [rbp+var_18], rax
0x180059e3d  mov     [rbp+var_28], r15d
0x180059e41  mov     [rbp+var_20], r14
0x180059e45  lea     rax, [rbp+var_28]
0x180059e49  mov     [rbp+var_8], rax
0x180059e4d  lea     r8, [rbp+Src]; void **
0x180059e51  lea     rdx, [rbp+Size]; unsigned int *
0x180059e55  lea     rcx, [rbp+var_18]; struct _ENCODE_OBJECT *
0x180059e59  call    ?EncodeBlob@@YAJPEAU_ENCODE_OBJECT@@PEAKPEAPEAX@Z; EncodeBlob(_ENCODE_OBJECT *,ulong *,void * *)
0x180059e5e  mov     edi, eax
0x180059e60  test    eax, eax
0x180059e62  jnz     short loc_180059EC0
0x180059e64  cmp     [rbp+Reply], r13d
0x180059e68  jnz     short loc_180059ED1
0x180059e6a  lea     rsi, [rbx+40h]
0x180059e6e  mov     rcx, [rsi]
0x180059e71  mov     rcx, [rcx]; this
0x180059e74  test    rcx, rcx
0x180059e77  jz      short loc_180059E84
0x180059e79  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180059e7e  mov     rax, [rsi]
0x180059e81  mov     [rax], r13
0x180059e84  mov     r14d, dword ptr [rbp+Size]
0x180059e88  mov     ecx, r14d
0x180059e8b  call    DAF_user_alloc
0x180059e90  mov     rcx, [rsi]
0x180059e93  mov     [rcx], rax
0x180059e96  mov     rax, [rsi]
0x180059e99  mov     rcx, [rax]; void *
0x180059e9c  test    rcx, rcx
0x180059e9f  jnz     short loc_180059EA8
0x180059ea1  mov     edi, 8007000Eh
0x180059ea6  jmp     short loc_180059EC4
0x180059ea8  mov     r8, r14; Size
0x180059eab  mov     rsi, [rbp+Src]
0x180059eaf  mov     rdx, rsi; Src
0x180059eb2  call    memcpy_0
0x180059eb7  mov     rax, [rbx+38h]
0x180059ebb  mov     [rax], r14d
0x180059ebe  jmp     short loc_180059ED5
0x180059ec0  lea     rsi, [rbx+40h]
0x180059ec4  mov     rax, [rsi]
0x180059ec7  mov     [rax], r13
0x180059eca  mov     rax, [rbx+38h]
0x180059ece  mov     [rax], r13d
0x180059ed1  mov     rsi, [rbp+Src]
0x180059ed5  cmp     [rbx+120h], r13d
0x180059edc  jz      short loc_180059F08
0x180059ede  mov     dword ptr [rbp+Size], r13d
0x180059ee2  mov     rcx, [rbx+20h]
0x180059ee6  lea     r8, [rbp+Size]; NotificationsQueued
0x180059eea  mov     edx, 2; Notification
0x180059eef  mov     rcx, [rcx+20h]; Binding
0x180059ef3  call    cs:__imp_RpcServerUnsubscribeForNotification
0x180059ef9  mov     rax, [rbx]
0x180059efc  mov     rcx, rbx
0x180059eff  mov     rax, [rax+10h]
0x180059f03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f08  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_bugfix_59720933@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933> `wil::Feature<__WilFeatureTraits_Feature_bugfix_59720933>::GetImpl(void)'::`2'::impl
0x180059f0f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_bugfix_59720933@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_bugfix_59720933>::__private_IsEnabled(void)
0x180059f14  mov     rcx, [rbx+20h]; pAsync
0x180059f18  test    al, al
0x180059f1a  jz      short loc_180059F21
0x180059f1c  test    rcx, rcx
0x180059f1f  jz      short loc_180059F4C
0x180059f21  mov     dword ptr [rbx+0E4h], 1
0x180059f2b  lea     rdx, [rbp+Reply]; Reply
0x180059f2f  call    cs:__imp_RpcAsyncCompleteCall
0x180059f35  test    eax, eax
0x180059f37  jz      short loc_180059F48
0x180059f39  js      short loc_180059F46
0x180059f3b  movzx   edi, ax
0x180059f3e  or      edi, 80010000h
0x180059f44  jmp     short loc_180059F48
0x180059f46  mov     edi, eax
0x180059f48  mov     [rbx+20h], r13
0x180059f4c  mov     rcx, r12; lpCriticalSection
0x180059f4f  call    cs:__imp_LeaveCriticalSection
0x180059f55  mov     rax, [rbx]
0x180059f58  mov     rcx, rbx
0x180059f5b  mov     rax, [rax+10h]
0x180059f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f64  test    rsi, rsi
0x180059f67  jz      short loc_180059F71
0x180059f69  mov     rcx, rsi; this
0x180059f6c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180059f71  mov     eax, edi
0x180059f73  mov     rbx, [rsp+50h+arg_0]
0x180059f7b  add     rsp, 50h
0x180059f7f  pop     r15
0x180059f81  pop     r14
0x180059f83  pop     r13
0x180059f85  pop     r12
0x180059f87  pop     rdi
0x180059f88  pop     rsi
0x180059f89  pop     rbp
0x180059f8a  retn
```
