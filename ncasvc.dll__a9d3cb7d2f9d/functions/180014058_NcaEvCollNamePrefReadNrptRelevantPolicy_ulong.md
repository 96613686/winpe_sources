# NcaEvCollNamePrefReadNrptRelevantPolicy(ulong *)

- ea: `0x180014058`
- end: `0x180014180`
- name: `?NcaEvCollNamePrefReadNrptRelevantPolicy@@YAKPEAK@Z`
- size: `296`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180014330`

## callees

- `0x180002d50`
- `0x1800037b0`
- `0x180004f34`
- `0x180014058`
- `0x180014248`
- `0x180019784`
- `0x18001a654`

## string_xrefs

- `0x1800140db`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters`
- `0x180014128`: `DirectAccessPreferLocal`

## pseudocode

```c
__int64 __fastcall NcaEvCollNamePrefReadNrptRelevantPolicy(unsigned int *a1)
{
  int DWord; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h]

  hKey = 0;
  LODWORD(v6) = 0;
  Data = 0;
  DWord = NcaEvCollNamePrefValidateNrptRelevantPolicyConfig();
  if ( DWord >= 0 )
  {
    DWord = NcaRegOpenKey(
              HKEY_LOCAL_MACHINE,
              L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters",
              9u,
              (__int64)&v6);
    if ( DWord >= 0 )
    {
      DWord = NcaRegQueryDWord(hKey, 0, L"DirectAccessPreferLocal", (LPBYTE)&Data, (__int64)&v6);
      if ( DWord >= 0 )
      {
        *a1 = Data;
        goto LABEL_15;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 33;
        goto LABEL_5;
      }
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 32;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 31;
LABEL_5:
      WPP_SF_d(v3[2], v4, WPP_845cef01834031fc88ca7e3c296c903d_Traceguids, (unsigned int)DWord);
    }
  }
LABEL_15:
  NcaRegCloseKey(hKey);
  return NcaHResultToWindowsError((unsigned int)DWord);
}

```

## disassembly

```asm
0x180014058  mov     rax, rsp
0x18001405b  mov     [rax+8], rbx
0x18001405f  push    rdi
0x180014060  sub     rsp, 30h
0x180014064  mov     rdi, rcx
0x180014067  mov     qword ptr [rax+20h], 0
0x18001406f  mov     dword ptr [rax+10h], 0
0x180014076  mov     dword ptr [rax+18h], 0
0x18001407d  call    ?NcaEvCollNamePrefValidateNrptRelevantPolicyConfig@@YAJXZ; NcaEvCollNamePrefValidateNrptRelevantPolicyConfig(void)
0x180014082  mov     ebx, eax
0x180014084  test    eax, eax
0x180014086  jns     short loc_1800140C6
0x180014088  mov     rcx, cs:WPP_GLOBAL_Control
0x18001408f  lea     rax, WPP_GLOBAL_Control
0x180014096  cmp     rcx, rax
0x180014099  jz      loc_180014165
0x18001409f  test    byte ptr [rcx+1Ch], 1
0x1800140a3  jz      loc_180014165
0x1800140a9  mov     edx, 1Fh
0x1800140ae  mov     rcx, [rcx+10h]
0x1800140b2  lea     r8, WPP_845cef01834031fc88ca7e3c296c903d_Traceguids
0x1800140b9  mov     r9d, ebx
0x1800140bc  call    WPP_SF_d
0x1800140c1  jmp     loc_180014165
0x1800140c6  lea     rax, [rsp+38h+arg_8]
0x1800140cb  mov     r8d, 9; samDesired
0x1800140d1  lea     r9, [rsp+38h+hKey]
0x1800140d6  mov     [rsp+38h+var_18], rax; __int64
0x1800140db  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800140e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800140e9  call    NcaRegOpenKey
0x1800140ee  mov     ebx, eax
0x1800140f0  test    eax, eax
0x1800140f2  jns     short loc_180014114
0x1800140f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140fb  lea     rax, WPP_GLOBAL_Control
0x180014102  cmp     rcx, rax
0x180014105  jz      short loc_180014165
0x180014107  test    byte ptr [rcx+1Ch], 1
0x18001410b  jz      short loc_180014165
0x18001410d  mov     edx, 20h ; ' '
0x180014112  jmp     short loc_1800140AE
0x180014114  mov     rcx, [rsp+38h+hKey]; hKey
0x180014119  lea     rax, [rsp+38h+arg_8]
0x18001411e  lea     r9, [rsp+38h+Data]; lpData
0x180014123  mov     [rsp+38h+var_18], rax; __int64
0x180014128  lea     r8, ValueName; "DirectAccessPreferLocal"
0x18001412f  xor     edx, edx; lpSubKey
0x180014131  call    NcaRegQueryDWord
0x180014136  mov     ebx, eax
0x180014138  test    eax, eax
0x18001413a  jns     short loc_18001415F
0x18001413c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014143  lea     rax, WPP_GLOBAL_Control
0x18001414a  cmp     rcx, rax
0x18001414d  jz      short loc_180014165
0x18001414f  test    byte ptr [rcx+1Ch], 1
0x180014153  jz      short loc_180014165
0x180014155  mov     edx, 21h ; '!'
0x18001415a  jmp     loc_1800140AE
0x18001415f  mov     eax, [rsp+38h+Data]
0x180014163  mov     [rdi], eax
0x180014165  mov     rcx, [rsp+38h+hKey]
0x18001416a  call    NcaRegCloseKey
0x18001416f  mov     ecx, ebx
0x180014171  mov     rbx, [rsp+38h+arg_0]
0x180014176  add     rsp, 30h
0x18001417a  pop     rdi
0x18001417b  jmp     NcaHResultToWindowsError
```
