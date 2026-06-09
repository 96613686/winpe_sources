# SlowLinkp_OpenNetCacheKey(ulong,int,HKEY__ * *)

- ea: `0x180034d50`
- end: `0x180034eb1`
- name: `?SlowLinkp_OpenNetCacheKey@@YAJKHPEAPEAUHKEY__@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(REGSAM, int, HKEY *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a0c0`
- `0x18005fbb0`
- `0x18005fc7c`
- `0x1800605e8`

## callees

- `0x180034d50`
- `0x180036400`
- `0x18003c354`
- `0x18003c560`
- `0x18003e928`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180034d7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180034d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e5f`

## string_xrefs

- `0x180034daf`: `Software\Microsoft\Windows\CurrentVersion\NetCache`
- `0x180034df2`: `Software\Microsoft\Windows\CurrentVersion\NetCache`

## pseudocode

```c
__int64 __fastcall SlowLinkp_OpenNetCacheKey(REGSAM a1, int a2, HKEY *a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // r8d
  unsigned __int16 *v8; // r9
  signed int Key; // ebx
  HKEY v10; // rdi
  unsigned int v12; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+28h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES *v14; // [rsp+30h] [rbp-38h]
  unsigned int *v15; // [rsp+40h] [rbp-28h]
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  hKey = 0;
  v6 = RegOpenCurrentUser(a1, &hKey);
  Key = v6;
  if ( v6 )
  {
    v10 = HKEY_CURRENT_USER;
    if ( v6 > 0 )
      Key = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v10 = hKey;
  }
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d3155cbb37bf3e821adcb63eaba4c981_Traceguids, a1, Key);
  }
  else
  {
    if ( a2 )
    {
      Key = CscReg_CreateKeyEx(
              v10,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache",
              v7,
              v8,
              v12,
              a1,
              v14,
              a3,
              v15);
      if ( Key < 0
        && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        LODWORD(v13) = Key;
        WPP_SF_SdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_d3155cbb37bf3e821adcb63eaba4c981_Traceguids,
          (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache",
          a1,
          v13);
      }
    }
    else
    {
      Key = CscReg_OpenKeyEx(v10, L"Software\\Microsoft\\Windows\\CurrentVersion\\NetCache", v7, a1, a3);
      if ( Key < 0
        && WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d3155cbb37bf3e821adcb63eaba4c981_Traceguids, a1, Key);
      }
    }
    RegCloseKey(v10);
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180034d50  mov     rax, rsp
0x180034d53  mov     [rax+8], rbx
0x180034d57  mov     [rax+10h], rbp
0x180034d5b  push    rsi
0x180034d5c  push    rdi
0x180034d5d  push    r14
0x180034d5f  sub     rsp, 50h
0x180034d63  mov     ebp, edx
0x180034d65  mov     qword ptr [r8], 0
0x180034d6c  lea     rdx, [rax+18h]; phkResult
0x180034d70  mov     qword ptr [rax+18h], 0
0x180034d78  mov     r14, r8
0x180034d7b  mov     esi, ecx
0x180034d7d  call    cs:__imp_RegOpenCurrentUser
0x180034d83  mov     ebx, eax
0x180034d85  test    eax, eax
0x180034d87  jnz     short loc_180034D93
0x180034d89  mov     rdi, [rsp+68h+hKey]
0x180034d91  jmp     short loc_180034DA7
0x180034d93  mov     rdi, 0FFFFFFFF80000001h
0x180034d9a  test    eax, eax
0x180034d9c  jle     short loc_180034DA7
0x180034d9e  movzx   ebx, ax
0x180034da1  or      ebx, 80070000h
0x180034da7  test    ebx, ebx
0x180034da9  js      loc_180034E67
0x180034daf  lea     rdx, REGSTR_KEY_OFFLINEFILES; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034db6  mov     rcx, rdi; HKEY
0x180034db9  test    ebp, ebp
0x180034dbb  jz      short loc_180034E14
0x180034dbd  mov     [rsp+68h+var_30], r14; PHKEY
0x180034dc2  mov     dword ptr [rsp+68h+var_40], esi; REGSAM
0x180034dc6  call    ?CscReg_CreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; CscReg_CreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180034dcb  mov     ebx, eax
0x180034dcd  test    eax, eax
0x180034dcf  jns     loc_180034E5C
0x180034dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ddc  lea     rax, WPP_GLOBAL_Control
0x180034de3  cmp     rcx, rax
0x180034de6  jz      short loc_180034E5C
0x180034de8  test    byte ptr [rcx+1Ch], 2
0x180034dec  jz      short loc_180034E5C
0x180034dee  mov     rcx, [rcx+10h]
0x180034df2  lea     r9, REGSTR_KEY_OFFLINEFILES; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180034df9  mov     edx, 0Ah
0x180034dfe  mov     dword ptr [rsp+68h+var_40], ebx
0x180034e02  lea     r8, WPP_d3155cbb37bf3e821adcb63eaba4c981_Traceguids
0x180034e09  mov     dword ptr [rsp+68h+var_48], esi
0x180034e0d  call    WPP_SF_SdD
0x180034e12  jmp     short loc_180034E5C
0x180034e14  mov     r9d, esi; unsigned int
0x180034e17  mov     [rsp+68h+var_48], r14; PHKEY
0x180034e1c  call    ?CscReg_OpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; CscReg_OpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180034e21  mov     ebx, eax
0x180034e23  test    eax, eax
0x180034e25  jns     short loc_180034E5C
0x180034e27  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e2e  lea     rax, WPP_GLOBAL_Control
0x180034e35  cmp     rcx, rax
0x180034e38  jz      short loc_180034E5C
0x180034e3a  test    byte ptr [rcx+1Ch], 2
0x180034e3e  jz      short loc_180034E5C
0x180034e40  mov     rcx, [rcx+10h]
0x180034e44  lea     r8, WPP_d3155cbb37bf3e821adcb63eaba4c981_Traceguids
0x180034e4b  mov     edx, 0Bh
0x180034e50  mov     dword ptr [rsp+68h+var_48], ebx
0x180034e54  mov     r9d, esi
0x180034e57  call    WPP_SF_dd
0x180034e5c  mov     rcx, rdi; hKey
0x180034e5f  call    cs:__imp_RegCloseKey
0x180034e65  jmp     short loc_180034E9C
0x180034e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e6e  lea     rax, WPP_GLOBAL_Control
0x180034e75  cmp     rcx, rax
0x180034e78  jz      short loc_180034E9C
0x180034e7a  test    byte ptr [rcx+1Ch], 2
0x180034e7e  jz      short loc_180034E9C
0x180034e80  mov     rcx, [rcx+10h]
0x180034e84  lea     r8, WPP_d3155cbb37bf3e821adcb63eaba4c981_Traceguids
0x180034e8b  mov     edx, 0Ch
0x180034e90  mov     dword ptr [rsp+68h+var_48], ebx
0x180034e94  mov     r9d, esi
0x180034e97  call    WPP_SF_dd
0x180034e9c  mov     rbp, [rsp+68h+arg_8]
0x180034ea1  mov     eax, ebx
0x180034ea3  mov     rbx, [rsp+68h+arg_0]
0x180034ea8  add     rsp, 50h
0x180034eac  pop     r14
0x180034eae  pop     rdi
0x180034eaf  pop     rsi
0x180034eb0  retn
```
