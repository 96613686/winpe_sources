# FirewallHelper::DeleteAppRoutePolicyFiltersByLayerKey(void * const &,_GUID const &,_GUID const &)

- ea: `0x18002b8a4`
- end: `0x18002b9a3`
- name: `?DeleteAppRoutePolicyFiltersByLayerKey@FirewallHelper@@YAXAEBQEAXAEBU_GUID@@1@Z`
- size: `255`
- prototype: `void __fastcall(FirewallHelper *__hidden this, void *const *, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002bb4c`

## callees

- `0x18001d8e0`
- `0x18001e368`
- `0x18002b8a4`
- `0x18002bffc`

## import_xrefs

- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x18002b911`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x18002b911`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x18002b983`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x18002b983`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b95b`
- `fwpuclnt!FwpmFilterDeleteById0` at `0x18002b95b`
- `fwpuclnt!FwpmFilterEnum0` at `0x18002b938`
- `fwpuclnt!FwpmFilterEnum0` at `0x18002b938`

## pseudocode

```c
void __fastcall FirewallHelper::DeleteAppRoutePolicyFiltersByLayerKey(
        HANDLE *this,
        GUID *a2,
        const struct _GUID *a3,
        const struct _GUID *a4)
{
  GUID v7; // xmm0
  HANDLE v8; // rcx
  HANDLE v9; // rdi
  HANDLE v10; // rsi
  __int64 i; // rbx
  DWORD v12; // eax
  unsigned int v13; // r8d
  unsigned int numEntriesReturned; // [rsp+20h] [rbp-59h]
  UINT32 v15; // [rsp+30h] [rbp-49h] BYREF
  HANDLE enumHandle; // [rsp+38h] [rbp-41h] BYREF
  FWPM_FILTER0 **entries; // [rsp+40h] [rbp-39h] BYREF
  FWPM_FILTER_ENUM_TEMPLATE0 enumTemplate; // [rsp+50h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  enumHandle = 0;
  entries = 0;
  v15 = 0;
  memset_0(&enumTemplate, 0, sizeof(enumTemplate));
  v7 = *a3;
  v8 = *this;
  enumTemplate.providerKey = a2;
  enumTemplate.layerKey = v7;
  enumTemplate.actionMask = -1;
  if ( !FwpmFilterCreateEnumHandle0(v8, &enumTemplate, &enumHandle) )
  {
    v9 = *this;
    v10 = enumHandle;
    if ( !FwpmFilterEnum0(*this, enumHandle, 0xFFFFFFFF, &entries, &v15) )
    {
      for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
      {
        v12 = FwpmFilterDeleteById0(*this, entries[i]->filterId);
        if ( v12 )
          wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x1E7, v13, (const char *)v12, numEntriesReturned);
      }
    }
    FwpmFilterDestroyEnumHandle0(v9, v10);
  }
}

```

## disassembly

```asm
0x18002b8a4  push    rbp
0x18002b8a6  push    rbx
0x18002b8a7  push    rsi
0x18002b8a8  push    rdi
0x18002b8a9  push    r14
0x18002b8ab  lea     rbp, [rsp-37h]
0x18002b8b0  sub     rsp, 0B0h
0x18002b8b7  mov     rax, cs:__security_cookie
0x18002b8be  xor     rax, rsp
0x18002b8c1  mov     [rbp+57h+var_30], rax
0x18002b8c5  mov     rbx, rdx
0x18002b8c8  mov     [rbp+57h+enumHandle], 0
0x18002b8d0  xor     edx, edx; Val
0x18002b8d2  mov     [rbp+57h+entries], 0
0x18002b8da  mov     rdi, r8
0x18002b8dd  mov     [rbp+57h+var_A0], 0
0x18002b8e4  mov     r14, rcx
0x18002b8e7  lea     rcx, [rbp+57h+enumTemplate]; void *
0x18002b8eb  lea     r8d, [rdx+48h]; Size
0x18002b8ef  call    memset_0
0x18002b8f4  movups  xmm0, xmmword ptr [rdi]
0x18002b8f7  mov     rcx, [r14]; engineHandle
0x18002b8fa  lea     r8, [rbp+57h+enumHandle]; enumHandle
0x18002b8fe  mov     [rbp+57h+enumTemplate.providerKey], rbx
0x18002b902  lea     rdx, [rbp+57h+enumTemplate]; enumTemplate
0x18002b906  or      ebx, 0FFFFFFFFh
0x18002b909  movdqu  xmmword ptr [rbp+57h+enumTemplate.layerKey.Data1], xmm0
0x18002b90e  mov     [rbp+57h+enumTemplate.actionMask], ebx
0x18002b911  call    cs:__imp_FwpmFilterCreateEnumHandle0
0x18002b917  test    eax, eax
0x18002b919  jnz     short loc_18002B989
0x18002b91b  mov     rdi, [r14]
0x18002b91e  lea     rax, [rbp+57h+var_A0]
0x18002b922  mov     rsi, [rbp+57h+enumHandle]
0x18002b926  lea     r9, [rbp+57h+entries]; entries
0x18002b92a  mov     rdx, rsi; enumHandle
0x18002b92d  mov     qword ptr [rsp+0D0h+numEntriesReturned], rax; unsigned int
0x18002b932  mov     rcx, rdi; engineHandle
0x18002b935  mov     r8d, ebx; numEntriesRequested
0x18002b938  call    cs:__imp_FwpmFilterEnum0
0x18002b93e  test    eax, eax
0x18002b940  jnz     short loc_18002B97D
0x18002b942  xor     ebx, ebx
0x18002b944  cmp     [rbp+57h+var_A0], ebx
0x18002b947  jbe     short loc_18002B97D
0x18002b949  mov     rax, [rbp+57h+entries]
0x18002b94d  mov     rcx, [r14]; engineHandle
0x18002b950  mov     rdx, [rax+rbx*8]
0x18002b954  mov     rdx, [rdx+0B0h]; id
0x18002b95b  call    cs:__imp_FwpmFilterDeleteById0
0x18002b961  test    eax, eax
0x18002b963  jz      short loc_18002B976
0x18002b965  mov     rcx, [rbp+5Fh]; this
0x18002b969  mov     r9d, eax; char *
0x18002b96c  mov     edx, 1E7h; void *
0x18002b971  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002b976  inc     ebx
0x18002b978  cmp     ebx, [rbp+57h+var_A0]
0x18002b97b  jb      short loc_18002B949
0x18002b97d  mov     rdx, rsi; enumHandle
0x18002b980  mov     rcx, rdi; engineHandle
0x18002b983  call    cs:__imp_FwpmFilterDestroyEnumHandle0
0x18002b989  mov     rcx, [rbp+57h+var_30]
0x18002b98d  xor     rcx, rsp; StackCookie
0x18002b990  call    __security_check_cookie
0x18002b995  add     rsp, 0B0h
0x18002b99c  pop     r14
0x18002b99e  pop     rdi
0x18002b99f  pop     rsi
0x18002b9a0  pop     rbx
0x18002b9a1  pop     rbp
0x18002b9a2  retn
```
