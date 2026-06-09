# CElsServiceInstance::Initialize(_GUID)

- ea: `0x1800a5eac`
- end: `0x1800a5f77`
- name: `?Initialize@CElsServiceInstance@@IEAAJU_GUID@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *__struct_ptr)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800a5cf4`
- `0x1800a5dbc`

## callees

- `0x18006ed20`
- `0x18006fb98`
- `0x1800a5eac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a5f4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a5f4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5eeb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a5eeb`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x1800a5f26`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x1800a5f26`

## pseudocode

```c
__int64 __fastcall CElsServiceInstance::Initialize(PMAPPING_SERVICE_INFO *prgServices, struct _GUID *a2)
{
  HRESULT Services; // edi
  _MAPPING_ENUM_OPTIONS pOptions; // [rsp+20h] [rbp-78h] BYREF
  __int128 v6; // [rsp+70h] [rbp-28h] BYREF

  Services = 0;
  v6 = (__int128)*a2;
  if ( !*((_BYTE *)prgServices + 12) )
  {
    AcquireSRWLockExclusive(&s_srwElsServiceLock);
    if ( !*((_BYTE *)prgServices + 12) )
    {
      memset_0(&pOptions, 0, sizeof(pOptions));
      pOptions.Size = 80;
      pOptions.pGuid = (GUID *)&v6;
      Services = MappingGetServices(&pOptions, prgServices, (DWORD *)prgServices + 2);
      if ( Services >= 0 )
      {
        if ( *((_DWORD *)prgServices + 2) )
          *((_BYTE *)prgServices + 12) = 1;
        else
          Services = -2147467259;
      }
    }
    ReleaseSRWLockExclusive(&s_srwElsServiceLock);
  }
  return (unsigned int)Services;
}

```

## disassembly

```asm
0x1800a5eac  mov     [rsp+arg_10], rbx
0x1800a5eb1  mov     [rsp+arg_18], rsi
0x1800a5eb6  push    rdi
0x1800a5eb7  sub     rsp, 90h
0x1800a5ebe  mov     rax, cs:__security_cookie
0x1800a5ec5  xor     rax, rsp
0x1800a5ec8  mov     [rsp+98h+var_18], rax
0x1800a5ed0  movups  xmm0, xmmword ptr [rdx]
0x1800a5ed3  xor     edi, edi
0x1800a5ed5  mov     rbx, rcx
0x1800a5ed8  movdqu  [rsp+98h+var_28], xmm0
0x1800a5ede  cmp     [rcx+0Ch], dil
0x1800a5ee2  jnz     short loc_1800A5F50
0x1800a5ee4  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800a5eeb  call    cs:__imp_AcquireSRWLockExclusive
0x1800a5ef1  cmp     [rbx+0Ch], dil
0x1800a5ef5  jnz     short loc_1800A5F43
0x1800a5ef7  mov     edi, 50h ; 'P'
0x1800a5efc  lea     rcx, [rsp+98h+pOptions]; void *
0x1800a5f01  mov     r8d, edi; Size
0x1800a5f04  xor     edx, edx; Val
0x1800a5f06  call    memset_0
0x1800a5f0b  lea     rax, [rsp+98h+var_28]
0x1800a5f10  mov     [rsp+98h+pOptions.Size], rdi
0x1800a5f15  lea     r8, [rbx+8]; pdwServicesCount
0x1800a5f19  mov     [rsp+98h+pOptions.pGuid], rax
0x1800a5f1e  mov     rdx, rbx; prgServices
0x1800a5f21  lea     rcx, [rsp+98h+pOptions]; pOptions
0x1800a5f26  call    cs:__imp_MappingGetServices
0x1800a5f2c  mov     edi, eax
0x1800a5f2e  test    eax, eax
0x1800a5f30  js      short loc_1800A5F43
0x1800a5f32  cmp     dword ptr [rbx+8], 0
0x1800a5f36  jbe     short loc_1800A5F3E
0x1800a5f38  mov     byte ptr [rbx+0Ch], 1
0x1800a5f3c  jmp     short loc_1800A5F43
0x1800a5f3e  mov     edi, 80004005h
0x1800a5f43  lea     rcx, ?s_srwElsServiceLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800a5f4a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a5f50  mov     eax, edi
0x1800a5f52  mov     rcx, [rsp+98h+var_18]
0x1800a5f5a  xor     rcx, rsp; StackCookie
0x1800a5f5d  call    __security_check_cookie
0x1800a5f62  lea     r11, [rsp+98h+var_8]
0x1800a5f6a  mov     rbx, [r11+20h]
0x1800a5f6e  mov     rsi, [r11+28h]
0x1800a5f72  mov     rsp, r11
0x1800a5f75  pop     rdi
0x1800a5f76  retn
```
