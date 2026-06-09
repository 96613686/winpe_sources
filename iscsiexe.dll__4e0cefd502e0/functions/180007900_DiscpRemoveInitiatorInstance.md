# DiscpRemoveInitiatorInstance

- ea: `0x180007900`
- end: `0x1800079a5`
- name: `DiscpRemoveInitiatorInstance`
- size: `165`
- prototype: `NTSTATUS __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x180012510`
- `0x180012ee4`

## callees

- `0x1800067e8`
- `0x180007900`
- `0x180007bb4`

## import_xrefs

- `ISCSIUM!DiscpDisestablishIrpPump` at `0x180007966`
- `ISCSIUM!DiscpDisestablishIrpPump` at `0x180007966`
- `ntdll!RtlLeaveCriticalSection` at `0x180007997`
- `ntdll!RtlEnterCriticalSection` at `0x180007910`
- `ntdll!RtlEnterCriticalSection` at `0x180007910`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x18000797d`
- `api-ms-win-service-private-l1-1-0!I_ScUnregisterDeviceNotification` at `0x18000797d`

## pseudocode

```c
NTSTATUS __fastcall DiscpRemoveInitiatorInstance(__int64 *a1)
{
  __int64 *v2; // rcx
  __int64 **v3; // rax
  bool v4; // zf

  RtlEnterCriticalSection(&DiscpCritSection);
  *((_DWORD *)a1 + 5) |= 0x80000000;
  v2 = (__int64 *)*a1;
  if ( *(__int64 **)(*a1 + 8) != a1 || (v3 = (__int64 **)a1[1], *v3 != a1) )
    __fastfail(3u);
  --DiscpInitiatorInstanceCount;
  *v3 = v2;
  v2[1] = (__int64)v3;
  DiscpRemoveTargetsByTag(*((unsigned int *)a1 + 8));
  DiscpFreeDiscoveryTag((wchar_t *)a1[5], 5);
  v4 = (*((_BYTE *)a1 + 20) & 2) == 0;
  *((_DWORD *)a1 + 8) = 0;
  if ( !v4 )
  {
    if ( a1[7] )
    {
      DiscpDisestablishIrpPump();
      a1[7] = 0;
    }
    if ( a1[8] )
    {
      I_ScUnregisterDeviceNotification();
      a1[8] = 0;
    }
  }
  return RtlLeaveCriticalSection(&DiscpCritSection);
}

```

## disassembly

```asm
0x180007900  push    rbx
0x180007902  sub     rsp, 20h
0x180007906  mov     rbx, rcx
0x180007909  lea     rcx, DiscpCritSection; CriticalSection
0x180007910  call    cs:__imp_RtlEnterCriticalSection
0x180007916  bts     dword ptr [rbx+14h], 1Fh
0x18000791b  mov     rcx, [rbx]
0x18000791e  cmp     [rcx+8], rbx
0x180007922  jnz     short loc_18000799E
0x180007924  mov     rax, [rbx+8]
0x180007928  cmp     [rax], rbx
0x18000792b  jnz     short loc_18000799E
0x18000792d  dec     cs:DiscpInitiatorInstanceCount
0x180007933  mov     [rax], rcx
0x180007936  mov     [rcx+8], rax
0x18000793a  mov     ecx, [rbx+20h]
0x18000793d  call    DiscpRemoveTargetsByTag
0x180007942  mov     rcx, [rbx+28h]; pszSrc
0x180007946  mov     edx, 5
0x18000794b  call    DiscpFreeDiscoveryTag
0x180007950  test    byte ptr [rbx+14h], 2
0x180007954  mov     dword ptr [rbx+20h], 0
0x18000795b  jz      short loc_18000798B
0x18000795d  mov     rcx, [rbx+38h]
0x180007961  test    rcx, rcx
0x180007964  jz      short loc_180007974
0x180007966  call    cs:__imp_DiscpDisestablishIrpPump
0x18000796c  mov     qword ptr [rbx+38h], 0
0x180007974  mov     rcx, [rbx+40h]
0x180007978  test    rcx, rcx
0x18000797b  jz      short loc_18000798B
0x18000797d  call    cs:__imp_I_ScUnregisterDeviceNotification
0x180007983  mov     qword ptr [rbx+40h], 0
0x18000798b  lea     rcx, DiscpCritSection
0x180007992  add     rsp, 20h
0x180007996  pop     rbx
0x180007997  jmp     cs:__imp_RtlLeaveCriticalSection
0x18000799e  mov     ecx, 3
0x1800079a3  int     29h; Win8: RtlFailFast(ecx)
```
