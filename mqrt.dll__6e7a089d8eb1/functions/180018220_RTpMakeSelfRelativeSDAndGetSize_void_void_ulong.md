# RTpMakeSelfRelativeSDAndGetSize(void * *,void * *,ulong *)

- ea: `0x180018220`
- end: `0x1800182d7`
- name: `?RTpMakeSelfRelativeSDAndGetSize@@YAJPEAPEAX0PEAK@Z`
- size: `183`
- prototype: `__int64 __fastcall(void **, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e590`
- `0x1800106c0`

## callees

- `0x180013c74`
- `0x180018220`
- `0x180021010`

## import_xrefs

- `ADVAPI32!MakeSelfRelativeSD` at `0x1800182a1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800182be`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800182a1`
- `ADVAPI32!MakeSelfRelativeSD` at `0x1800182be`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18001827d`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18001827d`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18001824b`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18001824b`

## pseudocode

```c
__int64 __fastcall RTpMakeSelfRelativeSDAndGetSize(void **a1, void **a2, unsigned int *a3)
{
  PSECURITY_DESCRIPTOR v5; // rcx
  PSECURITY_DESCRIPTOR v7; // rcx
  void *v8; // rax
  DWORD dwBufferLength; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwRevision; // [rsp+38h] [rbp+10h] BYREF
  unsigned int *pControl; // [rsp+40h] [rbp+18h] BYREF

  pControl = a3;
  *a2 = 0;
  v5 = *a1;
  LOWORD(pControl) = 0;
  dwRevision = 0;
  if ( v5 )
  {
    if ( !IsValidSecurityDescriptor(v5) )
    {
      LogMsgHR(-1072824287, (wchar_t *)L"rt/rtutil", 0xAu);
      return 3222143009LL;
    }
    GetSecurityDescriptorControl(*a1, (PSECURITY_DESCRIPTOR_CONTROL)&pControl, &dwRevision);
    if ( (__int16)pControl >= 0 )
    {
      v7 = *a1;
      dwBufferLength = 0;
      MakeSelfRelativeSD(v7, 0, &dwBufferLength);
      v8 = MmAllocate(dwBufferLength);
      *a2 = v8;
      MakeSelfRelativeSD(*a1, v8, &dwBufferLength);
      *a1 = *a2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018220  mov     [rsp+arg_18], rbx
0x180018225  mov     [rsp+pControl], r8
0x18001822a  push    rdi
0x18001822b  sub     rsp, 20h
0x18001822f  xor     eax, eax
0x180018231  mov     rbx, rcx
0x180018234  mov     [rdx], rax
0x180018237  mov     rdi, rdx
0x18001823a  mov     rcx, [rcx]; pSecurityDescriptor
0x18001823d  mov     word ptr [rsp+28h+pControl], ax
0x180018242  mov     [rsp+28h+dwRevision], eax
0x180018246  test    rcx, rcx
0x180018249  jz      short loc_1800182CA
0x18001824b  call    cs:__imp_IsValidSecurityDescriptor
0x180018251  test    eax, eax
0x180018253  jnz     short loc_180018270
0x180018255  mov     ebx, 0C00E0021h
0x18001825a  lea     r8d, [rax+0Ah]; unsigned __int16
0x18001825e  mov     ecx, ebx; int
0x180018260  lea     rdx, aRtRtutil; "rt/rtutil"
0x180018267  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001826c  mov     eax, ebx
0x18001826e  jmp     short loc_1800182CC
0x180018270  mov     rcx, [rbx]; pSecurityDescriptor
0x180018273  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x180018278  lea     rdx, [rsp+28h+pControl]; pControl
0x18001827d  call    cs:__imp_GetSecurityDescriptorControl
0x180018283  mov     eax, 8000h
0x180018288  test    word ptr [rsp+28h+pControl], ax
0x18001828d  jnz     short loc_1800182CA
0x18001828f  mov     rcx, [rbx]; pAbsoluteSecurityDescriptor
0x180018292  lea     r8, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x180018297  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180018299  mov     [rsp+28h+dwBufferLength], 0
0x1800182a1  call    cs:__imp_MakeSelfRelativeSD
0x1800182a7  mov     ecx, [rsp+28h+dwBufferLength]; unsigned __int64
0x1800182ab  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800182b0  mov     [rdi], rax
0x1800182b3  lea     r8, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x1800182b8  mov     rcx, [rbx]; pAbsoluteSecurityDescriptor
0x1800182bb  mov     rdx, rax; pSelfRelativeSecurityDescriptor
0x1800182be  call    cs:__imp_MakeSelfRelativeSD
0x1800182c4  mov     rax, [rdi]
0x1800182c7  mov     [rbx], rax
0x1800182ca  xor     eax, eax
0x1800182cc  mov     rbx, [rsp+28h+arg_18]
0x1800182d1  add     rsp, 20h
0x1800182d5  pop     rdi
0x1800182d6  retn
```
