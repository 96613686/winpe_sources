# DeleteOutboundRuleKey

- ea: `0x14007c2a8`
- end: `0x14007c447`
- name: `DeleteOutboundRuleKey`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140061f80`

## callees

- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x1400708c4`
- `0x14007c2a8`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14007c41a`
- `ADVAPI32!RegCloseKey` at `0x14007c41a`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007c3db`
- `ADVAPI32!RegDeleteKeyExW` at `0x14007c3db`
- `KERNEL32!GetLastError` at `0x14007c395`
- `KERNEL32!GetLastError` at `0x14007c395`

## pseudocode

```c
__int64 __fastcall DeleteOutboundRuleKey(unsigned int a1, int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HKEY v6; // rax
  HKEY v7; // rdi
  DWORD LastError; // eax
  unsigned int v9; // eax
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids);
  }
  v4 = StringCchPrintfW(SubKey, 0x104u, L"%ld:%ld", a1, a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Outbound Routing\\Rules", 0, 0x10000u);
    v7 = v6;
    if ( v6 )
    {
      v9 = RegDeleteKeyExW(v6, SubKey, 0, 0);
      v5 = v9;
      if ( v9
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, v9);
      }
      RegCloseKey(v7);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids, LastError);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        102,
        &WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids,
        (unsigned int)v4);
    }
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v5;
  }
  return v5;
}

```

## disassembly

```asm
0x14007c2a8  mov     [rsp+arg_10], rbx
0x14007c2ad  mov     [rsp+arg_18], rbp
0x14007c2b2  push    rdi
0x14007c2b3  sub     rsp, 250h
0x14007c2ba  mov     rax, cs:__security_cookie
0x14007c2c1  xor     rax, rsp
0x14007c2c4  mov     [rsp+258h+var_18], rax
0x14007c2cc  mov     edi, edx
0x14007c2ce  mov     ebx, ecx
0x14007c2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c2d7  lea     rbp, WPP_GLOBAL_Control
0x14007c2de  cmp     rcx, rbp
0x14007c2e1  jz      short loc_14007C304
0x14007c2e3  test    byte ptr [rcx+1Ch], 2
0x14007c2e7  jz      short loc_14007C304
0x14007c2e9  cmp     byte ptr [rcx+19h], 5
0x14007c2ed  jb      short loc_14007C304
0x14007c2ef  mov     rcx, [rcx+10h]
0x14007c2f3  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c2fa  mov     edx, 65h ; 'e'
0x14007c2ff  call    WPP_SF_
0x14007c304  mov     r9d, ebx
0x14007c307  mov     [rsp+258h+var_238], edi
0x14007c30b  lea     r8, aLdLd; "%ld:%ld"
0x14007c312  mov     edx, 104h; unsigned __int64
0x14007c317  lea     rcx, [rsp+258h+SubKey]; unsigned __int16 *
0x14007c31c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007c321  mov     ebx, eax
0x14007c323  test    eax, eax
0x14007c325  jns     short loc_14007C371
0x14007c327  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c32e  cmp     rcx, rbp
0x14007c331  jz      short loc_14007C357
0x14007c333  test    byte ptr [rcx+1Ch], 2
0x14007c337  jz      short loc_14007C357
0x14007c339  cmp     byte ptr [rcx+19h], 2
0x14007c33d  jb      short loc_14007C357
0x14007c33f  mov     rcx, [rcx+10h]
0x14007c343  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c34a  mov     edx, 66h ; 'f'
0x14007c34f  mov     r9d, eax
0x14007c352  call    WPP_SF_d
0x14007c357  mov     eax, ebx
0x14007c359  and     eax, 1FFF0000h
0x14007c35e  cmp     eax, 70000h
0x14007c363  jnz     loc_14007C420
0x14007c369  movzx   ebx, bx
0x14007c36c  jmp     loc_14007C420
0x14007c371  mov     r9d, 10000h
0x14007c377  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Fax\\Outbound Rout"...
0x14007c37e  xor     r8d, r8d
0x14007c381  mov     rcx, 0FFFFFFFF80000002h
0x14007c388  call    OpenRegistryKey
0x14007c38d  mov     rdi, rax
0x14007c390  test    rax, rax
0x14007c393  jnz     short loc_14007C3CD
0x14007c395  call    cs:__imp_GetLastError
0x14007c39b  mov     ebx, eax
0x14007c39d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c3a4  cmp     rcx, rbp
0x14007c3a7  jz      short loc_14007C420
0x14007c3a9  test    byte ptr [rcx+1Ch], 2
0x14007c3ad  jz      short loc_14007C420
0x14007c3af  cmp     byte ptr [rcx+19h], 2
0x14007c3b3  jb      short loc_14007C420
0x14007c3b5  mov     rcx, [rcx+10h]
0x14007c3b9  lea     edx, [rdi+67h]
0x14007c3bc  mov     r9d, eax
0x14007c3bf  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c3c6  call    WPP_SF_d
0x14007c3cb  jmp     short loc_14007C420
0x14007c3cd  xor     r9d, r9d; Reserved
0x14007c3d0  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x14007c3d5  xor     r8d, r8d; samDesired
0x14007c3d8  mov     rcx, rdi; hKey
0x14007c3db  call    cs:__imp_RegDeleteKeyExW
0x14007c3e1  mov     ebx, eax
0x14007c3e3  test    eax, eax
0x14007c3e5  jz      short loc_14007C417
0x14007c3e7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c3ee  cmp     rcx, rbp
0x14007c3f1  jz      short loc_14007C417
0x14007c3f3  test    byte ptr [rcx+1Ch], 2
0x14007c3f7  jz      short loc_14007C417
0x14007c3f9  cmp     byte ptr [rcx+19h], 2
0x14007c3fd  jb      short loc_14007C417
0x14007c3ff  mov     rcx, [rcx+10h]
0x14007c403  lea     r8, WPP_80e7b883d93739e1c57436ba7b9c58f5_Traceguids
0x14007c40a  mov     edx, 68h ; 'h'
0x14007c40f  mov     r9d, eax
0x14007c412  call    WPP_SF_d
0x14007c417  mov     rcx, rdi; hKey
0x14007c41a  call    cs:__imp_RegCloseKey
0x14007c420  mov     eax, ebx
0x14007c422  mov     rcx, [rsp+258h+var_18]
0x14007c42a  xor     rcx, rsp; StackCookie
0x14007c42d  call    __security_check_cookie
0x14007c432  lea     r11, [rsp+258h+var_8]
0x14007c43a  mov     rbx, [r11+20h]
0x14007c43e  mov     rbp, [r11+28h]
0x14007c442  mov     rsp, r11
0x14007c445  pop     rdi
0x14007c446  retn
```
