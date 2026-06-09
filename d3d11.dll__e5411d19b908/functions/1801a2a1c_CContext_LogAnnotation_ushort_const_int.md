# CContext::LogAnnotation(ushort const *,int)

- ea: `0x1801a2a1c`
- end: `0x1801a2ac7`
- name: `?LogAnnotation@CContext@@QEAAXPEBGH@Z`
- size: `171`
- prototype: `void(CContext *__hidden this, const unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180106e00`
- `0x18012f2a0`
- `0x18012f300`
- `0x1801a29c0`
- `0x1801ad310`

## callees

- `0x1800a9d20`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801a2a68`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1801a2a68`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1801a2aa7`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1801a2aa7`

## pseudocode

```c
void __fastcall CContext::LogAnnotation(CContext *this, const unsigned __int16 *a2, int a3)
{
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-50h] BYREF
  char *v4; // [rsp+30h] [rbp-40h]
  __int64 v5; // [rsp+38h] [rbp-38h]
  const unsigned __int16 *v6; // [rsp+40h] [rbp-30h]
  int v7; // [rsp+48h] [rbp-28h]
  int v8; // [rsp+4Ch] [rbp-24h]
  int *v9; // [rsp+50h] [rbp-20h]
  __int64 v10; // [rsp+58h] [rbp-18h]
  int v11; // [rsp+90h] [rbp+20h] BYREF

  v11 = a3;
  *(_QWORD *)&UserData.Size = 8;
  UserData.Ptr = (ULONGLONG)this + 168;
  v5 = 8;
  v4 = (char *)this + 39336;
  v6 = a2;
  v8 = 0;
  v10 = 4;
  v7 = 2 * wcslen(a2) + 2;
  v9 = &v11;
  EventWrite(Direct3D11EtwProviderGuid_Context, &EventD3D11MarkerInt, 4u, &UserData);
}

```

## disassembly

```asm
0x1801a2a1c  mov     [rsp-8+arg_0], rbx
0x1801a2a21  mov     [rsp-8+arg_10], r8d
0x1801a2a26  push    rbp
0x1801a2a27  mov     rbp, rsp
0x1801a2a2a  sub     rsp, 70h
0x1801a2a2e  mov     rax, cs:__security_cookie
0x1801a2a35  xor     rax, rsp
0x1801a2a38  mov     [rbp+var_10], rax
0x1801a2a3c  lea     rax, [rcx+0A8h]
0x1801a2a43  mov     qword ptr [rbp+UserData.Size], 8
0x1801a2a4b  mov     [rbp+UserData.Ptr], rax
0x1801a2a4f  mov     rbx, rdx
0x1801a2a52  lea     rax, [rcx+99A8h]
0x1801a2a59  mov     [rbp+var_38], 8
0x1801a2a61  mov     rcx, rdx; String
0x1801a2a64  mov     [rbp+var_40], rax
0x1801a2a68  call    cs:__imp_wcslen
0x1801a2a6e  mov     rcx, cs:Direct3D11EtwProviderGuid_Context; RegHandle
0x1801a2a75  lea     r9, [rbp+UserData]; UserData
0x1801a2a79  mov     r8d, 4; UserDataCount
0x1801a2a7f  mov     [rbp+var_30], rbx
0x1801a2a83  lea     rdx, EventD3D11MarkerInt; EventDescriptor
0x1801a2a8a  mov     [rbp+var_24], 0
0x1801a2a91  lea     eax, ds:2[rax*2]
0x1801a2a98  mov     [rbp+var_18], r8
0x1801a2a9c  mov     [rbp+var_28], eax
0x1801a2a9f  lea     rax, [rbp+arg_10]
0x1801a2aa3  mov     [rbp+var_20], rax
0x1801a2aa7  call    cs:__imp_EventWrite
0x1801a2aad  mov     rcx, [rbp+var_10]
0x1801a2ab1  xor     rcx, rsp; StackCookie
0x1801a2ab4  call    __security_check_cookie
0x1801a2ab9  mov     rbx, [rsp+70h+arg_0]
0x1801a2ac1  add     rsp, 70h
0x1801a2ac5  pop     rbp
0x1801a2ac6  retn
```
