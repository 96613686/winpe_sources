# PcwpClearCounterSetSecurityDescriptor(_UNICODE_STRING const *)

- ea: `0x14000ddf4`
- end: `0x14000df6d`
- name: `?PcwpClearCounterSetSecurityDescriptor@@YAJPEBU_UNICODE_STRING@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a9b0`

## callees

- `0x14000cf6c`
- `0x14000dd2c`
- `0x14000ddf4`
- `0x14000e4e8`
- `0x14000e648`
- `0x14000ed84`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000de6c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000de6c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000de52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000deac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000de52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000deac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000de98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000df41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000de98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000df41`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000de8c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000de8c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000debd`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000debd`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000df35`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000df35`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14000deff`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14000deff`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000dee1`
- `ntoskrnl!ZwDeleteValueKey` at `0x14000dee1`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000df24`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000df24`

## pseudocode

```c
__int64 __fastcall PcwpClearCounterSetSecurityDescriptor(const struct _UNICODE_STRING *a1)
{
  __int64 result; // rax
  __int64 v2; // rcx
  int v3; // ebx
  struct PCW_SILO_NEUTRAL_COUNTERSET *v4; // rbx
  char *v5; // rsi
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  struct PCW_SILO_NEUTRAL_COUNTERSET *v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  result = PcwpOpenSecurityKey();
  if ( (int)result >= 0 )
  {
    result = PcwpInitDefaultSecurityDescriptor();
    if ( (int)result >= 0 )
    {
      v3 = PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(&v9);
      if ( v3 >= 0 )
      {
        KeEnterCriticalRegion();
        v4 = v9;
        v5 = (char *)v9 + 88;
        ExAcquirePushLockSharedEx((char *)v9 + 88, 0);
        v6 = PcwpAccessCheck((PSECURITY_DESCRIPTOR *)v4, 0x10C0000u);
        ExReleasePushLockSharedEx(v5, 0);
        KeLeaveCriticalRegion();
        if ( v6 >= 0 )
        {
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(v5, 0);
          if ( PcwDefaultSecurityDescriptor != *((void **)v4 + 12) )
          {
            v6 = ZwDeleteValueKey(PcwSecurityKey, (PUNICODE_STRING)((char *)v4 + 24));
            if ( v6 >= 0 )
            {
              ObReferenceSecurityDescriptor(PcwDefaultSecurityDescriptor, 1);
              v8 = *((_QWORD *)v4 + 12);
              *((_QWORD *)v4 + 12) = PcwDefaultSecurityDescriptor;
              if ( v8 )
                ObDereferenceSecurityDescriptor(v8, 1);
            }
          }
          ExReleasePushLockExclusiveEx(v5, 0);
          KeLeaveCriticalRegion();
        }
        if ( v4 )
          ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v7, v4);
        return (unsigned int)v6;
      }
      else
      {
        if ( v9 )
          ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v2, v9);
        return (unsigned int)v3;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ddf4  mov     [rsp+arg_0], rbx
0x14000ddf9  mov     [rsp+arg_10], rsi
0x14000ddfe  push    rdi
0x14000ddff  sub     rsp, 20h
0x14000de03  mov     rbx, rcx
0x14000de06  mov     [rsp+28h+arg_8], 0
0x14000de0f  call    ?PcwpOpenSecurityKey@@YAJXZ; PcwpOpenSecurityKey(void)
0x14000de14  test    eax, eax
0x14000de16  js      loc_14000DF5C
0x14000de1c  call    ?PcwpInitDefaultSecurityDescriptor@@YAJXZ; PcwpInitDefaultSecurityDescriptor(void)
0x14000de21  test    eax, eax
0x14000de23  js      loc_14000DF5C
0x14000de29  mov     rdx, rbx
0x14000de2c  lea     rcx, [rsp+28h+arg_8]
0x14000de31  call    ?FindOrCreate@PCW_SILO_NEUTRAL_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000de36  mov     ebx, eax
0x14000de38  test    eax, eax
0x14000de3a  jns     short loc_14000DE52
0x14000de3c  mov     rdx, [rsp+28h+arg_8]
0x14000de41  test    rdx, rdx
0x14000de44  jz      short loc_14000DE4B
0x14000de46  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000de4b  mov     eax, ebx
0x14000de4d  jmp     loc_14000DF5C
0x14000de52  call    cs:__imp_KeEnterCriticalRegion
0x14000de59  nop     dword ptr [rax+rax+00h]
0x14000de5e  mov     rbx, [rsp+28h+arg_8]
0x14000de63  xor     edx, edx
0x14000de65  lea     rsi, [rbx+58h]
0x14000de69  mov     rcx, rsi
0x14000de6c  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000de73  nop     dword ptr [rax+rax+00h]
0x14000de78  mov     edx, 10C0000h; unsigned int
0x14000de7d  mov     rcx, rbx; struct PCW_SILO_NEUTRAL_COUNTERSET *
0x14000de80  call    ?PcwpAccessCheck@@YAJPEBVPCW_SILO_NEUTRAL_COUNTERSET@@K@Z; PcwpAccessCheck(PCW_SILO_NEUTRAL_COUNTERSET const *,ulong)
0x14000de85  xor     edx, edx
0x14000de87  mov     rcx, rsi
0x14000de8a  mov     edi, eax
0x14000de8c  call    cs:__imp_ExReleasePushLockSharedEx
0x14000de93  nop     dword ptr [rax+rax+00h]
0x14000de98  call    cs:__imp_KeLeaveCriticalRegion
0x14000de9f  nop     dword ptr [rax+rax+00h]
0x14000dea4  test    edi, edi
0x14000dea6  js      loc_14000DF4D
0x14000deac  call    cs:__imp_KeEnterCriticalRegion
0x14000deb3  nop     dword ptr [rax+rax+00h]
0x14000deb8  xor     edx, edx
0x14000deba  mov     rcx, rsi
0x14000debd  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000dec4  nop     dword ptr [rax+rax+00h]
0x14000dec9  mov     rax, [rbx+60h]
0x14000decd  cmp     cs:?PcwDefaultSecurityDescriptor@@3PEAXEA, rax; void * PcwDefaultSecurityDescriptor
0x14000ded4  jz      short loc_14000DF30
0x14000ded6  mov     rcx, cs:?PcwSecurityKey@@3PEAXEA; KeyHandle
0x14000dedd  lea     rdx, [rbx+18h]; ValueName
0x14000dee1  call    cs:__imp_ZwDeleteValueKey
0x14000dee8  nop     dword ptr [rax+rax+00h]
0x14000deed  mov     edi, eax
0x14000deef  test    eax, eax
0x14000def1  js      short loc_14000DF30
0x14000def3  mov     rcx, cs:?PcwDefaultSecurityDescriptor@@3PEAXEA; void * PcwDefaultSecurityDescriptor
0x14000defa  mov     edx, 1
0x14000deff  call    cs:__imp_ObReferenceSecurityDescriptor
0x14000df06  nop     dword ptr [rax+rax+00h]
0x14000df0b  mov     rcx, [rbx+60h]
0x14000df0f  mov     rax, cs:?PcwDefaultSecurityDescriptor@@3PEAXEA; void * PcwDefaultSecurityDescriptor
0x14000df16  mov     [rbx+60h], rax
0x14000df1a  test    rcx, rcx
0x14000df1d  jz      short loc_14000DF30
0x14000df1f  mov     edx, 1
0x14000df24  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000df2b  nop     dword ptr [rax+rax+00h]
0x14000df30  xor     edx, edx
0x14000df32  mov     rcx, rsi
0x14000df35  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000df3c  nop     dword ptr [rax+rax+00h]
0x14000df41  call    cs:__imp_KeLeaveCriticalRegion
0x14000df48  nop     dword ptr [rax+rax+00h]
0x14000df4d  test    rbx, rbx
0x14000df50  jz      short loc_14000DF5A
0x14000df52  mov     rdx, rbx
0x14000df55  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000df5a  mov     eax, edi
0x14000df5c  mov     rbx, [rsp+28h+arg_0]
0x14000df61  mov     rsi, [rsp+28h+arg_10]
0x14000df66  add     rsp, 20h
0x14000df6a  pop     rdi
0x14000df6b  retn
```
