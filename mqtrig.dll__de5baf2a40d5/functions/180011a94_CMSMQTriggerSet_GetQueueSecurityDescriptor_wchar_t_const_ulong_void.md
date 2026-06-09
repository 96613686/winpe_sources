# CMSMQTriggerSet::GetQueueSecurityDescriptor(wchar_t const *,ulong,void * *)

- ea: `0x180011a94`
- end: `0x180011b4b`
- name: `?GetQueueSecurityDescriptor@CMSMQTriggerSet@@AEAAJPEB_WKPEAPEAX@Z`
- size: `183`
- prototype: `HRESULT __fastcall(CMSMQTriggerSet *this, const wchar_t *, __int64, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012d10`

## callees

- `0x180011a94`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180011b2c`
- `KERNEL32!LocalFree` at `0x180011b2c`
- `KERNEL32!LocalAlloc` at `0x180011aee`
- `KERNEL32!LocalAlloc` at `0x180011aee`
- `mqrt!MQGetQueueSecurity` at `0x180011ad8`
- `mqrt!MQGetQueueSecurity` at `0x180011b1d`
- `mqrt!MQGetQueueSecurity` at `0x180011ad8`
- `mqrt!MQGetQueueSecurity` at `0x180011b1d`

## pseudocode

```c
HRESULT __fastcall CMSMQTriggerSet::GetQueueSecurityDescriptor(
        CMSMQTriggerSet *this,
        const wchar_t *a2,
        __int64 a3,
        void **a4)
{
  HRESULT result; // eax
  HLOCAL v7; // rbx
  HRESULT v8; // edi
  int pSecurityDescriptor; // [rsp+40h] [rbp+8h] BYREF
  int v10; // [rsp+44h] [rbp+Ch]
  SIZE_T uBytes; // [rsp+50h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  pSecurityDescriptor = 0;
  LODWORD(uBytes) = 0;
  result = MQGetQueueSecurity(a2, 4u, &pSecurityDescriptor, 0, (LPDWORD)&uBytes);
  if ( result == -1072824285 )
  {
    v7 = LocalAlloc(0x40u, (unsigned int)uBytes);
    if ( v7 )
    {
      v8 = MQGetQueueSecurity(a2, 4u, v7, uBytes, (LPDWORD)&uBytes);
      if ( v8 >= 0 )
      {
        *a4 = v7;
        return 0;
      }
      else
      {
        LocalFree(v7);
        return v8;
      }
    }
    else
    {
      return -1072824281;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011a94  mov     rax, rsp
0x180011a97  mov     [rax+10h], rbx
0x180011a9b  mov     [rax+20h], rsi
0x180011a9f  mov     [rax+18h], r8d
0x180011aa3  mov     [rax+8], rcx
0x180011aa7  push    rdi
0x180011aa8  sub     rsp, 30h
0x180011aac  mov     rdi, rdx
0x180011aaf  mov     dword ptr [rax+8], 0
0x180011ab6  mov     rsi, r9
0x180011ab9  mov     dword ptr [rax+18h], 0
0x180011ac0  xor     r9d, r9d; nLength
0x180011ac3  lea     rax, [rax+18h]
0x180011ac7  lea     r8, [rsp+38h+pSecurityDescriptor]; pSecurityDescriptor
0x180011acc  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180011ad1  mov     rcx, rdi; lpwcsFormatName
0x180011ad4  lea     edx, [r9+4]; RequestedInformation
0x180011ad8  call    cs:__imp_MQGetQueueSecurity
0x180011ade  cmp     eax, 0C00E0023h
0x180011ae3  jnz     short loc_180011B3B
0x180011ae5  mov     edx, dword ptr [rsp+38h+uBytes]; uBytes
0x180011ae9  mov     ecx, 40h ; '@'; uFlags
0x180011aee  call    cs:__imp_LocalAlloc
0x180011af4  mov     rbx, rax
0x180011af7  test    rax, rax
0x180011afa  jnz     short loc_180011B03
0x180011afc  mov     eax, 0C00E0027h
0x180011b01  jmp     short loc_180011B3B
0x180011b03  mov     r9d, dword ptr [rsp+38h+uBytes]; nLength
0x180011b08  lea     rax, [rsp+38h+uBytes]
0x180011b0d  mov     r8, rbx; pSecurityDescriptor
0x180011b10  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180011b15  mov     edx, 4; RequestedInformation
0x180011b1a  mov     rcx, rdi; lpwcsFormatName
0x180011b1d  call    cs:__imp_MQGetQueueSecurity
0x180011b23  mov     edi, eax
0x180011b25  test    eax, eax
0x180011b27  jns     short loc_180011B36
0x180011b29  mov     rcx, rbx; hMem
0x180011b2c  call    cs:__imp_LocalFree
0x180011b32  mov     eax, edi
0x180011b34  jmp     short loc_180011B3B
0x180011b36  mov     [rsi], rbx
0x180011b39  xor     eax, eax
0x180011b3b  mov     rbx, [rsp+38h+arg_8]
0x180011b40  mov     rsi, [rsp+38h+arg_18]
0x180011b45  add     rsp, 30h
0x180011b49  pop     rdi
0x180011b4a  retn
```
