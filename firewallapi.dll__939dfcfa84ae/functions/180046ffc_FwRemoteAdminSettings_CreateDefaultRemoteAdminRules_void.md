# FwRemoteAdminSettings::CreateDefaultRemoteAdminRules(void)

- ea: `0x180046ffc`
- end: `0x1800470c3`
- name: `?CreateDefaultRemoteAdminRules@FwRemoteAdminSettings@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(FwRemoteAdminSettings *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800474c8`

## callees

- `0x180046ffc`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x18004708c`
- `fwbase!FwReportReturnError` at `0x1800470a7`
- `fwbase!FwReportReturnError` at `0x18004708c`
- `fwbase!FwReportReturnError` at `0x1800470a7`
- `FWPolicyIOMgr!GetRemoteAdminSettings` at `0x18004700c`
- `FWPolicyIOMgr!GetRemoteAdminSettings` at `0x18004700c`
- `FWPolicyIOMgr!CreateDefaultRemoteAdminRule` at `0x180047064`
- `FWPolicyIOMgr!CreateDefaultRemoteAdminRule` at `0x180047064`

## string_xrefs

- `0x180047085`: `FwRemoteAdminSettings::CreateDefaultRemoteAdminRules`
- `0x1800470a0`: `FwRemoteAdminSettings::CreateDefaultRemoteAdminRules`

## pseudocode

```c
__int64 __fastcall FwRemoteAdminSettings::CreateDefaultRemoteAdminRules(FwRemoteAdminSettings *this)
{
  unsigned int v2; // ebx
  struct FW_REMOTE_ADMIN_SETTING_ *RemoteAdminSettings; // r14
  __int64 i; // rdi
  char *v5; // rsi
  int DefaultRemoteAdminRule; // eax

  v2 = 0;
  RemoteAdminSettings = GetRemoteAdminSettings();
  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    v5 = (char *)this + 8 * i + 80;
    if ( !*(_QWORD *)v5 )
    {
      DefaultRemoteAdminRule = CreateDefaultRemoteAdminRule(
                                 *((unsigned int *)RemoteAdminSettings + 12 * i),
                                 *((unsigned int *)RemoteAdminSettings + 12 * i + 1),
                                 *((_QWORD *)RemoteAdminSettings + 6 * i + 1),
                                 *((_QWORD *)RemoteAdminSettings + 6 * i + 2),
                                 (char *)RemoteAdminSettings + 48 * i + 24,
                                 (char *)this + 8 * i + 80,
                                 0x7FFFFFFF);
      v2 = DefaultRemoteAdminRule;
      if ( DefaultRemoteAdminRule < 0 )
      {
        FwReportReturnError(
          "FwRemoteAdminSettings::CreateDefaultRemoteAdminRules",
          (unsigned int)DefaultRemoteAdminRule);
        return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::CreateDefaultRemoteAdminRules", v2);
      }
      *(_DWORD *)(*(_QWORD *)v5 + 40LL) = *((_DWORD *)this + 16);
    }
  }
  if ( (v2 & 0x80000000) == 0 )
    return v2;
  return (unsigned int)FwReportReturnError("FwRemoteAdminSettings::CreateDefaultRemoteAdminRules", v2);
}

```

## disassembly

```asm
0x180046ffc  push    rbx
0x180046ffe  push    rbp
0x180046fff  push    rsi
0x180047000  push    rdi
0x180047001  push    r14
0x180047003  sub     rsp, 40h
0x180047007  mov     rbp, rcx
0x18004700a  xor     ebx, ebx
0x18004700c  call    cs:__imp_?GetRemoteAdminSettings@@YAPEAUFW_REMOTE_ADMIN_SETTING_@@XZ; GetRemoteAdminSettings(void)
0x180047013  nop     dword ptr [rax+rax+00h]
0x180047018  mov     r14, rax
0x18004701b  xor     edi, edi
0x18004701d  cmp     edi, 3
0x180047020  jnb     short loc_18004709A
0x180047022  lea     rsi, [rbp+50h]
0x180047026  lea     rsi, [rsi+rdi*8]
0x18004702a  cmp     qword ptr [rsi], 0
0x18004702e  jnz     short loc_18004707F
0x180047030  mov     [rsp+68h+var_38], 7FFFFFFFh
0x180047038  lea     rcx, [rdi+rdi*2]
0x18004703c  shl     rcx, 4
0x180047040  lea     rax, [r14+18h]
0x180047044  add     rax, rcx
0x180047047  mov     [rsp+68h+var_40], rsi
0x18004704c  mov     [rsp+68h+var_48], rax
0x180047051  mov     r9, [rcx+r14+10h]
0x180047056  mov     r8, [rcx+r14+8]
0x18004705b  mov     edx, [rcx+r14+4]
0x180047060  mov     ecx, [rcx+r14]
0x180047064  call    cs:__imp_?CreateDefaultRemoteAdminRule@@YAJIIPEBG0PEAU_tag_FW_PORTS@@PEAPEAU_tag_FW_RULE@@W4_tag_FW_PROFILE_TYPE@@@Z; CreateDefaultRemoteAdminRule(uint,uint,ushort const *,ushort const *,_tag_FW_PORTS *,_tag_FW_RULE * *,_tag_FW_PROFILE_TYPE)
0x18004706b  nop     dword ptr [rax+rax+00h]
0x180047070  mov     ebx, eax
0x180047072  test    eax, eax
0x180047074  js      short loc_180047083
0x180047076  mov     rdx, [rsi]
0x180047079  mov     ecx, [rbp+40h]
0x18004707c  mov     [rdx+28h], ecx
0x18004707f  inc     edi
0x180047081  jmp     short loc_18004701D
0x180047083  mov     edx, eax
0x180047085  lea     rcx, aFwremoteadmins_4; "FwRemoteAdminSettings::CreateDefaultRem"...
0x18004708c  call    cs:__imp_FwReportReturnError
0x180047093  nop     dword ptr [rax+rax+00h]
0x180047098  jmp     short loc_18004709E
0x18004709a  test    ebx, ebx
0x18004709c  jns     short loc_1800470B5
0x18004709e  mov     edx, ebx
0x1800470a0  lea     rcx, aFwremoteadmins_4; "FwRemoteAdminSettings::CreateDefaultRem"...
0x1800470a7  call    cs:__imp_FwReportReturnError
0x1800470ae  nop     dword ptr [rax+rax+00h]
0x1800470b3  mov     ebx, eax
0x1800470b5  mov     eax, ebx
0x1800470b7  add     rsp, 40h
0x1800470bb  pop     r14
0x1800470bd  pop     rdi
0x1800470be  pop     rsi
0x1800470bf  pop     rbp
0x1800470c0  pop     rbx
0x1800470c1  retn
```
