# container::ObjectManager::GetDirectorySecurityDescriptor(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,windows_wrappers::SecurityDescriptor &,bool)

- ea: `0x180026b68`
- end: `0x180026c26`
- name: `?GetDirectorySecurityDescriptor@ObjectManager@container@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVSecurityDescriptor@windows_wrappers@@_N@Z`
- size: `190`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800268b8`
- `0x180026f60`

## callees

- `0x180002ad0`
- `0x1800051b0`
- `0x180026830`
- `0x180026b68`
- `0x180026de4`
- `0x18002c444`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026bea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026bea`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall container::ObjectManager::GetDirectorySecurityDescriptor(int a1, _QWORD *a2, char a3)
{
  void *v5; // rax
  struct SecurityDescriptor *v6; // r8
  void *v7; // rbx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v10[32]; // [rsp+80h] [rbp-38h] BYREF

  windows_wrappers::ObjectAttributes::ObjectAttributes((unsigned int)&ObjectAttributes, a1, 64, 0, 0);
  v5 = container::ObjectManager::OpenDir(&ObjectAttributes, (struct _OBJECT_ATTRIBUTES *)0x1020001, a3);
  v7 = v5;
  if ( v5 )
  {
    windows_wrappers::GetSecurityDescriptor(v5, a2, v6);
    if ( v7 != (void *)-1LL )
      CloseHandle(v7);
  }
  return std::wstring::~wstring(v10);
}

```

## disassembly

```asm
0x180026b68  mov     [rsp+arg_10], rbx
0x180026b6d  push    rdi
0x180026b6e  sub     rsp, 0B0h
0x180026b75  mov     rax, cs:__security_cookie
0x180026b7c  xor     rax, rsp
0x180026b7f  mov     [rsp+0B8h+var_18], rax
0x180026b87  mov     bl, r8b
0x180026b8a  mov     rdi, rdx
0x180026b8d  mov     [rsp+0B8h+var_98], 0
0x180026b96  xor     r9d, r9d
0x180026b99  lea     r8d, [r9+40h]
0x180026b9d  mov     rdx, rcx
0x180026ba0  lea     rcx, [rsp+0B8h+ObjectAttributes]
0x180026ba5  call    ??0ObjectAttributes@windows_wrappers@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KQEAX1@Z; windows_wrappers::ObjectAttributes::ObjectAttributes(std::wstring const &,ulong,void * const,void * const)
0x180026baa  nop
0x180026bab  mov     [rsp+0B8h+var_88], 0
0x180026bb4  mov     r8b, bl; unsigned int
0x180026bb7  mov     edx, 1020001h; struct _OBJECT_ATTRIBUTES *
0x180026bbc  lea     rcx, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x180026bc1  call    ?OpenDir@ObjectManager@container@@YAPEAXPEAU_OBJECT_ATTRIBUTES@@K_N@Z; container::ObjectManager::OpenDir(_OBJECT_ATTRIBUTES *,ulong,bool)
0x180026bc6  mov     rbx, rax
0x180026bc9  mov     [rsp+0B8h+var_88], rax
0x180026bce  test    rax, rax
0x180026bd1  jnz     short loc_180026BD5
0x180026bd3  jmp     short loc_180026BF7
0x180026bd5  mov     rdx, rdi; void *
0x180026bd8  mov     rcx, rbx; Handle
0x180026bdb  call    ?GetSecurityDescriptor@windows_wrappers@@YAXPEAXAEAVSecurityDescriptor@1@@Z; windows_wrappers::GetSecurityDescriptor(void *,windows_wrappers::SecurityDescriptor &)
0x180026be0  nop
0x180026be1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180026be5  jz      short loc_180026BF7
0x180026be7  mov     rcx, rbx; hObject
0x180026bea  call    cs:__imp_CloseHandle
0x180026bf1  nop     dword ptr [rax+rax+00h]
0x180026bf6  nop
0x180026bf7  lea     rcx, [rsp+0B8h+var_38]
0x180026bff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026c04  mov     rcx, [rsp+0B8h+var_18]
0x180026c0c  xor     rcx, rsp; StackCookie
0x180026c0f  call    __security_check_cookie
0x180026c14  mov     rbx, [rsp+0B8h+arg_10]
0x180026c1c  add     rsp, 0B0h
0x180026c23  pop     rdi
0x180026c24  retn
```
