# DeleteBitLockerStatusReg(BITLOCKER_CSP_STATUS)

- ea: `0x18002b894`
- end: `0x18002ba12`
- name: `?DeleteBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014564`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x180011020`
- `0x18002b894`
- `0x18002ba18`

## import_xrefs

- `ADVAPI32!RegDeleteKeyValueW` at `0x18002b950`
- `ADVAPI32!RegDeleteKeyValueW` at `0x18002b950`

## pseudocode

```c
__int64 __fastcall DeleteBitLockerStatusReg(unsigned int a1)
{
  int BitLockerCSPRegValueName; // eax
  unsigned int v3; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  LSTATUS v6; // eax
  LPCWSTR lpValueName; // [rsp+68h] [rbp+10h] BYREF

  lpValueName = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
  BitLockerCSPRegValueName = GetBitLockerCSPRegValueName(a1, &lpValueName);
  v3 = BitLockerCSPRegValueName;
  if ( BitLockerCSPRegValueName >= 0 )
  {
    v6 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\BitLockerCsp\\EncryptionFailure", lpValueName);
    v3 = v6;
    if ( v6 == -2147024894 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, a1);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      v3 = 0;
      goto LABEL_25;
    }
    if ( v6 >= 0 )
      goto LABEL_24;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, a1, v6);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v5 = 79;
          goto LABEL_23;
        }
LABEL_25:
        if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
          WPP_SF_(v4[2], 80, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      }
    }
  }
  else
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
          a1,
          BitLockerCSPRegValueName);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
        {
          v5 = 76;
LABEL_23:
          WPP_SF_d(v4[2], v5, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v3);
LABEL_24:
          v4 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_25;
        }
        goto LABEL_25;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18002b894  push    rbx
0x18002b896  push    rbp
0x18002b897  push    rsi
0x18002b898  push    rdi
0x18002b899  sub     rsp, 38h
0x18002b89d  mov     edi, ecx
0x18002b89f  mov     [rsp+58h+lpValueName], 0
0x18002b8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8af  lea     rsi, WPP_GLOBAL_Control
0x18002b8b6  lea     rbp, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18002b8bd  cmp     rcx, rsi
0x18002b8c0  jz      short loc_18002B8D9
0x18002b8c2  test    byte ptr [rcx+1Ch], 20h
0x18002b8c6  jz      short loc_18002B8D9
0x18002b8c8  mov     rcx, [rcx+10h]
0x18002b8cc  mov     edx, 4Ah ; 'J'
0x18002b8d1  mov     r8, rbp
0x18002b8d4  call    WPP_SF_
0x18002b8d9  lea     rdx, [rsp+58h+lpValueName]
0x18002b8de  mov     ecx, edi
0x18002b8e0  call    ?GetBitLockerCSPRegValueName@@YAJW4BITLOCKER_CSP_STATUS@@PEAPEBG@Z; GetBitLockerCSPRegValueName(BITLOCKER_CSP_STATUS,ushort const * *)
0x18002b8e5  mov     ebx, eax
0x18002b8e7  test    eax, eax
0x18002b8e9  jns     short loc_18002B93D
0x18002b8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b8f2  cmp     rcx, rsi
0x18002b8f5  jz      loc_18002BA07
0x18002b8fb  test    byte ptr [rcx+1Ch], 2
0x18002b8ff  jz      short loc_18002B920
0x18002b901  mov     rcx, [rcx+10h]
0x18002b905  mov     edx, 4Bh ; 'K'
0x18002b90a  mov     r9d, edi
0x18002b90d  mov     [rsp+58h+var_38], eax
0x18002b911  mov     r8, rbp
0x18002b914  call    WPP_SF_dd
0x18002b919  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b920  cmp     rcx, rsi
0x18002b923  jz      loc_18002BA07
0x18002b929  test    byte ptr [rcx+1Ch], 40h
0x18002b92d  jz      loc_18002B9EB
0x18002b933  mov     edx, 4Ch ; 'L'
0x18002b938  jmp     loc_18002B9D5
0x18002b93d  mov     r8, [rsp+58h+lpValueName]; lpValueName
0x18002b942  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\BitLockerCsp\\Encr"...
0x18002b949  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b950  call    cs:__imp_RegDeleteKeyValueW
0x18002b956  mov     ebx, eax
0x18002b958  cmp     eax, 80070002h
0x18002b95d  jnz     short loc_18002B990
0x18002b95f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b966  cmp     rcx, rsi
0x18002b969  jz      short loc_18002B98C
0x18002b96b  test    byte ptr [rcx+1Ch], 8
0x18002b96f  jz      short loc_18002B98C
0x18002b971  mov     rcx, [rcx+10h]
0x18002b975  mov     edx, 4Dh ; 'M'
0x18002b97a  mov     r9d, edi
0x18002b97d  mov     r8, rbp
0x18002b980  call    WPP_SF_d
0x18002b985  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b98c  xor     ebx, ebx
0x18002b98e  jmp     short loc_18002B9EB
0x18002b990  test    ebx, ebx
0x18002b992  jns     short loc_18002B9E4
0x18002b994  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b99b  cmp     rcx, rsi
0x18002b99e  jz      short loc_18002BA07
0x18002b9a0  test    byte ptr [rcx+1Ch], 2
0x18002b9a4  jz      short loc_18002B9C5
0x18002b9a6  mov     rcx, [rcx+10h]
0x18002b9aa  mov     edx, 4Eh ; 'N'
0x18002b9af  mov     r9d, edi
0x18002b9b2  mov     [rsp+58h+var_38], ebx
0x18002b9b6  mov     r8, rbp
0x18002b9b9  call    WPP_SF_dd
0x18002b9be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9c5  cmp     rcx, rsi
0x18002b9c8  jz      short loc_18002BA07
0x18002b9ca  test    byte ptr [rcx+1Ch], 40h
0x18002b9ce  jz      short loc_18002B9EB
0x18002b9d0  mov     edx, 4Fh ; 'O'
0x18002b9d5  mov     rcx, [rcx+10h]
0x18002b9d9  mov     r9d, ebx
0x18002b9dc  mov     r8, rbp
0x18002b9df  call    WPP_SF_d
0x18002b9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9eb  cmp     rcx, rsi
0x18002b9ee  jz      short loc_18002BA07
0x18002b9f0  test    byte ptr [rcx+1Ch], 20h
0x18002b9f4  jz      short loc_18002BA07
0x18002b9f6  mov     rcx, [rcx+10h]
0x18002b9fa  mov     edx, 50h ; 'P'
0x18002b9ff  mov     r8, rbp
0x18002ba02  call    WPP_SF_
0x18002ba07  mov     eax, ebx
0x18002ba09  add     rsp, 38h
0x18002ba0d  pop     rdi
0x18002ba0e  pop     rsi
0x18002ba0f  pop     rbp
0x18002ba10  pop     rbx
0x18002ba11  retn
```
