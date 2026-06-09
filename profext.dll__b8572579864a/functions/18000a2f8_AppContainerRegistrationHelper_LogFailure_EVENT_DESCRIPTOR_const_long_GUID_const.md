# AppContainerRegistrationHelper::LogFailure(_EVENT_DESCRIPTOR const *,long,_GUID const *)

- ea: `0x18000a2f8`
- end: `0x18000a3dc`
- name: `?LogFailure@AppContainerRegistrationHelper@@CAXPEBU_EVENT_DESCRIPTOR@@JPEBU_GUID@@@Z`
- size: `228`
- prototype: `void __fastcall(const struct _EVENT_DESCRIPTOR *, int, const struct _GUID *)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009860`
- `0x180009a34`
- `0x18000d980`
- `0x18000ea1c`
- `0x18000fcb4`
- `0x180015fe0`
- `0x1800162d0`

## callees

- `0x18000a2f8`
- `0x18000b984`
- `0x18001b948`
- `0x180022830`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x18000a342`
- `ntdll!EtwEventRegister` at `0x18000a342`
- `ntdll!EtwEventWrite` at `0x18000a376`
- `ntdll!EtwEventWrite` at `0x18000a376`
- `ntdll!EtwEventUnregister` at `0x18000a386`
- `ntdll!EtwEventUnregister` at `0x18000a386`

## pseudocode

```c
void __fastcall AppContainerRegistrationHelper::LogFailure(
        const struct _EVENT_DESCRIPTOR *a1,
        int a2,
        const struct _GUID *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // r8d
  int v7; // r9d
  unsigned int v8; // [rsp+20h] [rbp-40h]
  int v9; // [rsp+30h] [rbp-30h] BYREF
  __int64 v10; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v11[2]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v13; // [rsp+88h] [rbp+28h] BYREF

  v13 = a2;
  v10 = 0;
  v11[1] = 4;
  v11[0] = &v13;
  v5 = EtwEventRegister(AppModelRuntimeProviderId, 0, 0, &v10);
  if ( v5 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x8D, v6, (const char *)v5, v8);
  }
  else
  {
    EtwEventWrite(v10, a1, 1, v11);
    EtwEventUnregister(v10);
  }
  if ( a3 )
  {
    if ( (unsigned int)dword_180031038 > 5 )
    {
      v9 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180031038,
        (unsigned int)byte_18002AF2D,
        (_DWORD)a3,
        v7,
        (__int64)&v9);
    }
  }
}

```

## disassembly

```asm
0x18000a2f8  mov     [rsp-18h+arg_8], edx
0x18000a2fc  push    rbp
0x18000a2fd  push    rbx
0x18000a2fe  push    rdi
0x18000a2ff  mov     rbp, rsp
0x18000a302  sub     rsp, 60h
0x18000a306  mov     rax, cs:__security_cookie
0x18000a30d  xor     rax, rsp
0x18000a310  mov     [rbp+var_10], rax
0x18000a314  mov     rbx, r8
0x18000a317  mov     [rbp+var_28], 0
0x18000a31f  mov     rdi, rcx
0x18000a322  mov     [rbp+var_18], 4
0x18000a32a  lea     rax, [rbp+arg_8]
0x18000a32e  xor     r8d, r8d
0x18000a331  lea     rcx, AppModelRuntimeProviderId
0x18000a338  mov     [rbp+var_20], rax
0x18000a33c  lea     r9, [rbp+var_28]
0x18000a340  xor     edx, edx
0x18000a342  call    cs:__imp_EtwEventRegister
0x18000a349  nop     dword ptr [rax+rax+00h]
0x18000a34e  test    eax, eax
0x18000a350  jz      short loc_18000A365
0x18000a352  mov     rcx, [rbp+18h]; this
0x18000a356  mov     r9d, eax; char *
0x18000a359  mov     edx, 8Dh; void *
0x18000a35e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18000a363  jmp     short loc_18000A392
0x18000a365  mov     rcx, [rbp+var_28]
0x18000a369  lea     r9, [rbp+var_20]
0x18000a36d  mov     r8d, 1
0x18000a373  mov     rdx, rdi
0x18000a376  call    cs:__imp_EtwEventWrite
0x18000a37d  nop     dword ptr [rax+rax+00h]
0x18000a382  mov     rcx, [rbp+var_28]
0x18000a386  call    cs:__imp_EtwEventUnregister
0x18000a38d  nop     dword ptr [rax+rax+00h]
0x18000a392  test    rbx, rbx
0x18000a395  jz      short loc_18000A3C7
0x18000a397  mov     eax, cs:dword_180031038
0x18000a39d  cmp     eax, 5
0x18000a3a0  jbe     short loc_18000A3C7
0x18000a3a2  mov     eax, [rbp+arg_8]
0x18000a3a5  lea     rdx, byte_18002AF2D
0x18000a3ac  mov     [rbp+var_30], eax
0x18000a3af  lea     rcx, dword_180031038
0x18000a3b6  lea     rax, [rbp+var_30]
0x18000a3ba  mov     r8, rbx
0x18000a3bd  mov     qword ptr [rsp+60h+var_40], rax
0x18000a3c2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000a3c7  mov     rcx, [rbp+var_10]
0x18000a3cb  xor     rcx, rsp; StackCookie
0x18000a3ce  call    __security_check_cookie
0x18000a3d3  add     rsp, 60h
0x18000a3d7  pop     rdi
0x18000a3d8  pop     rbx
0x18000a3d9  pop     rbp
0x18000a3da  retn
```
