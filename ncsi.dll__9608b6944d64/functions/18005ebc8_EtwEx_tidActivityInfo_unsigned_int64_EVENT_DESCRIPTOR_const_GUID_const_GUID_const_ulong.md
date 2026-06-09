# EtwEx_tidActivityInfo(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong)

- ea: `0x18005ebc8`
- end: `0x18005ecab`
- name: `?EtwEx_tidActivityInfo@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2K@Z`
- size: `227`
- prototype: `unsigned int __fastcall(unsigned __int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *, char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005f6b8`
- `0x18005f798`

## callees

- `0x180047240`
- `0x18005ebc8`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18005ec1a`
- `ntdll!EtwEventActivityIdControl` at `0x18005ec87`
- `ntdll!EtwEventActivityIdControl` at `0x18005ec1a`
- `ntdll!EtwEventActivityIdControl` at `0x18005ec87`
- `ntdll!EtwEventWrite` at `0x18005ec65`
- `ntdll!EtwEventWrite` at `0x18005ec65`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(
        __int64 a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        char a5)
{
  __int64 v5; // rdi
  __int128 *v7; // r9
  __int64 v8; // r8
  unsigned int v9; // edi
  __int64 v10; // r8
  __int64 v11; // r9
  __int128 v13; // [rsp+20h] [rbp-30h] BYREF
  char *v14; // [rsp+30h] [rbp-20h]
  __int64 v15; // [rsp+38h] [rbp-18h]

  v5 = Microsoft_Windows_Networking_CorrelationHandle;
  if ( a2->Id == 0xEA61 )
  {
    v13 = 0;
    if ( a3 )
      v13 = (__int128)*a3;
    ((void (__fastcall *)(__int64, __int128 *, const struct _GUID *, const struct _GUID *))EtwEventActivityIdControl)(
      2,
      &v13,
      a3,
      a4);
  }
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *((_QWORD *)&v13 + 1) = 16;
    *(_QWORD *)&v13 = &Microsoft_Windows_Networking_ProviderId;
    v7 = &v13;
    v15 = 4;
    v14 = &a5;
    v8 = 2;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  v9 = EtwEventWrite(v5, a2, v8, v7, v13, *((_QWORD *)&v13 + 1), v14, v15);
  if ( a2->Id == 0xEA62 )
  {
    v13 = 0;
    ((void (__fastcall *)(__int64, __int128 *, __int64, __int64))EtwEventActivityIdControl)(2, &v13, v10, v11);
  }
  return v9;
}

```

## disassembly

```asm
0x18005ebc8  mov     [rsp-8+arg_0], rbx
0x18005ebcd  mov     [rsp-8+arg_18], rdi
0x18005ebd2  push    rbp
0x18005ebd3  mov     rbp, rsp
0x18005ebd6  sub     rsp, 50h
0x18005ebda  mov     rax, cs:__security_cookie
0x18005ebe1  xor     rax, rsp
0x18005ebe4  mov     [rbp+var_10], rax
0x18005ebe8  mov     rdi, cs:Microsoft_Windows_Networking_CorrelationHandle
0x18005ebef  mov     eax, 0EA61h
0x18005ebf4  mov     rbx, rdx
0x18005ebf7  cmp     [rdx], ax
0x18005ebfa  jnz     short loc_18005EC20
0x18005ebfc  xorps   xmm0, xmm0
0x18005ebff  movups  [rbp+var_30], xmm0
0x18005ec03  test    r8, r8
0x18005ec06  jz      short loc_18005EC11
0x18005ec08  movups  xmm0, xmmword ptr [r8]
0x18005ec0c  movdqu  [rbp+var_30], xmm0
0x18005ec11  lea     rdx, [rbp+var_30]
0x18005ec15  mov     ecx, 2
0x18005ec1a  call    cs:__imp_EtwEventActivityIdControl
0x18005ec20  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x18005ec26  mov     rdx, rbx
0x18005ec29  mov     rcx, rdi
0x18005ec2c  test    eax, eax
0x18005ec2e  jz      short loc_18005EC5F
0x18005ec30  lea     rax, Microsoft_Windows_Networking_ProviderId
0x18005ec37  mov     qword ptr [rbp+var_30+8], 10h
0x18005ec3f  mov     qword ptr [rbp+var_30], rax
0x18005ec43  lea     r9, [rbp+var_30]
0x18005ec47  lea     rax, [rbp+arg_20]
0x18005ec4b  mov     [rbp+var_18], 4
0x18005ec53  mov     [rbp+var_20], rax
0x18005ec57  mov     r8d, 2
0x18005ec5d  jmp     short loc_18005EC65
0x18005ec5f  xor     r9d, r9d
0x18005ec62  xor     r8d, r8d
0x18005ec65  call    cs:__imp_EtwEventWrite
0x18005ec6b  mov     edi, eax
0x18005ec6d  mov     eax, 0EA62h
0x18005ec72  cmp     [rbx], ax
0x18005ec75  jnz     short loc_18005EC8D
0x18005ec77  xorps   xmm0, xmm0
0x18005ec7a  lea     rdx, [rbp+var_30]
0x18005ec7e  mov     ecx, 2
0x18005ec83  movups  [rbp+var_30], xmm0
0x18005ec87  call    cs:__imp_EtwEventActivityIdControl
0x18005ec8d  mov     eax, edi
0x18005ec8f  mov     rcx, [rbp+var_10]
0x18005ec93  xor     rcx, rsp; StackCookie
0x18005ec96  call    __security_check_cookie
0x18005ec9b  mov     rbx, [rsp+50h+arg_0]
0x18005eca0  mov     rdi, [rsp+50h+arg_18]
0x18005eca5  add     rsp, 50h
0x18005eca9  pop     rbp
0x18005ecaa  retn
```
