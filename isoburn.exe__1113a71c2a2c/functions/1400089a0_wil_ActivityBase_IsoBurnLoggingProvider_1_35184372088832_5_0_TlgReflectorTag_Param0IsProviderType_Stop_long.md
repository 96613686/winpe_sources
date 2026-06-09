# wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1400089a0`
- end: `0x140008b6d`
- name: `?Stop@?$ActivityBase@VIsoBurnLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140009e64`

## callees

- `0x1400018dc`
- `0x140001fa0`
- `0x140002bc6`
- `0x140006c34`
- `0x140007610`
- `0x1400089a0`
- `0x1400096d0`
- `0x140010010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400089ff`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400089ff`
- `KERNEL32!GetCurrentThreadId` at `0x140008a56`
- `KERNEL32!GetCurrentThreadId` at `0x140008ae1`
- `KERNEL32!GetCurrentThreadId` at `0x140008a56`
- `KERNEL32!GetCurrentThreadId` at `0x140008ae1`

## string_xrefs

- `0x140008afc`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        int a2)
{
  __int64 v4; // rax
  int v5; // edi
  RTL_SRWLOCK *v6; // rcx
  int v7; // edi
  __int64 result; // rax
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 *v13; // rcx
  const struct wil::FailureInfo *v14; // rdx
  DWORD v15; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[32]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h]
  PSRWLOCK *p_SRWLock; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  DWORD *v23; // [rsp+90h] [rbp-70h]
  __int64 v24; // [rsp+98h] [rbp-68h]
  void *retaddr; // [rsp+128h] [rbp+28h]

  wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v4 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v4 + 248);
  if ( v5 < 1 )
  {
    memset_0(v18, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v18, v14);
  }
  if ( *(int *)(v4 + 72) >= 0 )
    *(_DWORD *)(v4 + 72) = a2;
  v6 = SRWLock;
  v7 = v5 - 1;
  *(_DWORD *)(v4 + 248) = v7;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  if ( v7 )
  {
    result = (__int64)IsoBurnLoggingProvider::Provider();
    v9 = result;
    if ( *(_DWORD *)result > 5u )
    {
      result = *(_QWORD *)(result + 24);
      if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (result & 0x200000000000LL) == result )
      {
        CurrentThreadId = GetCurrentThreadId();
        v11 = *(_QWORD *)(a1 + 272);
        v15 = CurrentThreadId;
        LODWORD(SRWLock) = a2;
        v23 = &v15;
        v17 = 0x1000000;
        p_SRWLock = &SRWLock;
        v24 = 4;
        v19 = &v17;
        v22 = 4;
        v20 = 8;
        result = tlgWriteTransfer_EventWriteTransfer(v9, byte_14001317D, v11 + 8, 0, 5, v18);
      }
    }
  }
  else
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  if ( *(_DWORD *)(a1 + 312) )
  {
    v12 = a1 + 288;
    if ( *(_DWORD *)(v12 + 24) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    v13 = *(__int64 **)v12;
    *(_DWORD *)(v12 + 24) = 0;
    while ( 1 )
    {
      result = *v13;
      if ( !*v13 )
        break;
      if ( result == v12 )
      {
        result = *(_QWORD *)(v12 + 16);
        *v13 = result;
        break;
      }
      v13 = (__int64 *)(result + 16);
      *(_QWORD *)v12 = result + 16;
    }
    *(_QWORD *)v12 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400089a0  push    rbp
0x1400089a2  push    rbx
0x1400089a3  push    rsi
0x1400089a4  push    rdi
0x1400089a5  lea     rbp, [rsp-8]
0x1400089aa  sub     rsp, 108h
0x1400089b1  mov     rax, cs:__security_cookie
0x1400089b8  xor     rax, rsp
0x1400089bb  mov     [rbp+20h+var_30], rax
0x1400089bf  mov     esi, edx
0x1400089c1  mov     rbx, rcx
0x1400089c4  lea     rdx, [rsp+120h+SRWLock]
0x1400089c9  call    ?LockExclusive@?$ActivityBase@VIsoBurnLoggingProvider@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoBurnLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400089ce  mov     rax, [rbx+110h]
0x1400089d5  mov     edi, [rax+0F8h]
0x1400089db  cmp     edi, 1
0x1400089de  jl      loc_140008B50
0x1400089e4  cmp     dword ptr [rax+48h], 0
0x1400089e8  jl      short loc_1400089ED
0x1400089ea  mov     [rax+48h], esi
0x1400089ed  mov     rcx, [rsp+120h+SRWLock]; SRWLock
0x1400089f2  dec     edi
0x1400089f4  mov     [rax+0F8h], edi
0x1400089fa  test    rcx, rcx
0x1400089fd  jz      short loc_140008A05
0x1400089ff  call    cs:__imp_ReleaseSRWLockExclusive
0x140008a05  test    edi, edi
0x140008a07  jnz     short loc_140008A1D
0x140008a09  mov     rax, [rbx]
0x140008a0c  mov     rcx, rbx
0x140008a0f  mov     rax, [rax+8]
0x140008a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a18  jmp     loc_140008AD1
0x140008a1d  call    ?Provider@IsoBurnLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; IsoBurnLoggingProvider::Provider(void)
0x140008a22  mov     rdi, rax
0x140008a25  mov     ecx, [rax]
0x140008a27  cmp     ecx, 5
0x140008a2a  jbe     loc_140008AD1
0x140008a30  mov     rax, [rax+18h]
0x140008a34  mov     rdx, 200000000000h
0x140008a3e  mov     rcx, [rdi+10h]
0x140008a42  test    rdx, rcx
0x140008a45  jz      loc_140008AD1
0x140008a4b  mov     rcx, rax
0x140008a4e  and     rcx, rdx
0x140008a51  cmp     rcx, rax
0x140008a54  jnz     short loc_140008AD1
0x140008a56  call    cs:__imp_GetCurrentThreadId
0x140008a5c  mov     r8, [rbx+110h]
0x140008a63  lea     rdx, byte_14001317D
0x140008a6a  mov     [rsp+120h+var_F0], eax
0x140008a6e  add     r8, 8
0x140008a72  lea     rax, [rsp+120h+var_F0]
0x140008a77  mov     dword ptr [rsp+120h+SRWLock], esi
0x140008a7b  mov     [rbp+20h+var_90], rax
0x140008a7f  xor     r9d, r9d
0x140008a82  lea     rax, [rsp+120h+SRWLock]
0x140008a87  mov     [rsp+120h+var_E0], 1000000h
0x140008a90  mov     [rbp+20h+var_A0], rax
0x140008a94  mov     rcx, rdi
0x140008a97  lea     rax, [rsp+120h+var_E0]
0x140008a9c  mov     [rbp+20h+var_88], 4
0x140008aa4  mov     [rsp+120h+var_B0], rax
0x140008aa9  lea     rax, [rsp+120h+var_D0]
0x140008aae  mov     [rsp+120h+var_F8], rax
0x140008ab3  mov     [rsp+120h+var_100], 5
0x140008abb  mov     [rbp+20h+var_98], 4
0x140008ac3  mov     [rsp+120h+var_A8], 8
0x140008acc  call    _tlgWriteTransfer_EventWriteTransfer
0x140008ad1  cmp     dword ptr [rbx+138h], 0
0x140008ad8  jz      short loc_140008B38
0x140008ada  add     rbx, 120h
0x140008ae1  call    cs:__imp_GetCurrentThreadId
0x140008ae7  cmp     [rbx+18h], eax
0x140008aea  jz      short loc_140008B08
0x140008aec  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140008af3  test    rax, rax
0x140008af6  jz      short loc_140008B08
0x140008af8  mov     rdx, [rbp+28h]
0x140008afc  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140008b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b08  mov     rcx, [rbx]
0x140008b0b  mov     dword ptr [rbx+18h], 0
0x140008b12  jmp     short loc_140008B20
0x140008b14  cmp     rax, rbx
0x140008b17  jz      short loc_140008B2A
0x140008b19  lea     rcx, [rax+10h]
0x140008b1d  mov     [rbx], rcx
0x140008b20  mov     rax, [rcx]
0x140008b23  test    rax, rax
0x140008b26  jnz     short loc_140008B14
0x140008b28  jmp     short loc_140008B31
0x140008b2a  mov     rax, [rbx+10h]
0x140008b2e  mov     [rcx], rax
0x140008b31  mov     qword ptr [rbx], 0
0x140008b38  mov     rcx, [rbp+20h+var_30]
0x140008b3c  xor     rcx, rsp; StackCookie
0x140008b3f  call    __security_check_cookie
0x140008b44  add     rsp, 108h
0x140008b4b  pop     rdi
0x140008b4c  pop     rsi
0x140008b4d  pop     rbx
0x140008b4e  pop     rbp
0x140008b4f  retn
0x140008b50  xor     edx, edx; Val
0x140008b52  lea     rcx, [rsp+120h+var_D0]; void *
0x140008b57  mov     r8d, 98h; Size
0x140008b5d  call    memset_0
0x140008b62  lea     rcx, [rsp+120h+var_D0]; this
0x140008b67  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
