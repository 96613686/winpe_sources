# StSaveProfileList(_GUID *,_ST_PROFILE_LIST *)

- ea: `0x18001d91c`
- end: `0x18001dbc4`
- name: `?StSaveProfileList@@YAKPEAU_GUID@@PEAU_ST_PROFILE_LIST@@@Z`
- size: `680`
- prototype: `__int64 __fastcall(GUID *rguid, struct _ST_PROFILE_LIST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e59c`

## callees

- `0x1800025f0`
- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a96c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000c460`
- `0x18001d91c`
- `0x18001e620`
- `0x18001e974`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001da00`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001da00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001db5a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001db34`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001db34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da65`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001daa7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001daa7`

## pseudocode

```c
__int64 __fastcall StSaveProfileList(GUID *rguid, struct _ST_PROFILE_LIST *a2)
{
  unsigned int RegKeyPath; // ebx
  unsigned __int64 v5; // r14
  BYTE *v6; // rsi
  unsigned __int16 *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned int i; // r15d
  unsigned __int64 v10; // r9
  int v11; // eax
  DWORD v12; // eax
  unsigned int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  SIZE_T dwBytes; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v16; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  v16 = 0;
  dwBytes = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 27, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, 0, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    RegKeyPath = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( !RegKeyPath )
    {
      if ( (int)ULongLongMult(0x27u, *(unsigned int *)a2, &v16) < 0
        || (v5 = v16 + 1, v16 + 1 < v16)
        || (int)ULongLongMult(v16 + 1, 2u, &dwBytes) < 0 )
      {
        RegKeyPath = 534;
      }
      else
      {
        v6 = (BYTE *)Dot3Alloc(dwBytes);
        if ( v6 || (RegKeyPath = GetLastError()) == 0 )
        {
          v7 = (unsigned __int16 *)v6;
          v16 = v5;
          v8 = v5;
          for ( i = 0; ; ++i )
          {
            dwBytes = (SIZE_T)v7;
            if ( i >= *(_DWORD *)a2 )
              break;
            StringFromGUID2((const GUID *const)((char *)a2 + 16 * i + 4), sz, 39);
            v11 = StringCchCopyNExW(v7, v8, sz, v10, (unsigned __int16 **)&dwBytes, &v16, lpSecurityAttributes);
            RegKeyPath = v11;
            if ( v11 < 0 )
            {
              if ( (v11 & 0x1FFF0000) == 0x70000 )
                RegKeyPath = (unsigned __int16)v11;
              if ( RegKeyPath )
                goto LABEL_20;
            }
            v8 = v16 - 1;
            v7 = (unsigned __int16 *)(dwBytes + 2);
            --v16;
          }
          *v7 = 0;
          v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v5);
          RegKeyPath = RegSetValueExW(hKey, L"ProfileList", 0, 7u, v6, v12);
LABEL_20:
          if ( v6 )
            Dot3Free(v6);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 28, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001d91c  mov     [rsp-8+arg_10], rbx
0x18001d921  mov     [rsp-8+arg_18], rsi
0x18001d926  push    rbp
0x18001d927  push    rdi
0x18001d928  push    r12
0x18001d92a  push    r14
0x18001d92c  push    r15
0x18001d92e  lea     rbp, [rsp-1E0h]
0x18001d936  sub     rsp, 2E0h
0x18001d93d  mov     rax, cs:__security_cookie
0x18001d944  xor     rax, rsp
0x18001d947  mov     [rbp+200h+var_30], rax
0x18001d94e  mov     r12, rdx
0x18001d951  mov     [rsp+300h+hKey], 0
0x18001d95a  mov     rbx, rcx
0x18001d95d  mov     [rsp+300h+var_2A8], 0
0x18001d966  mov     [rsp+300h+dwBytes], 0
0x18001d96f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d976  lea     rdi, WPP_GLOBAL_Control
0x18001d97d  cmp     rcx, rdi
0x18001d980  jz      short loc_18001D9A3
0x18001d982  cmp     byte ptr [rcx+19h], 4
0x18001d986  jb      short loc_18001D9A3
0x18001d988  test    byte ptr [rcx+1Ch], 1
0x18001d98c  jz      short loc_18001D9A3
0x18001d98e  mov     rcx, [rcx+10h]
0x18001d992  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d999  mov     edx, 1Bh
0x18001d99e  call    WPP_SF_
0x18001d9a3  lea     r9, [rbp+200h+SubKey]; unsigned __int16 *
0x18001d9a7  mov     qword ptr [rsp+300h+dwOptions], 104h; unsigned __int64
0x18001d9b0  xor     r8d, r8d; int
0x18001d9b3  xor     edx, edx; GUID *
0x18001d9b5  mov     rcx, rbx; rguid
0x18001d9b8  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001d9bd  mov     ebx, eax
0x18001d9bf  test    eax, eax
0x18001d9c1  jnz     loc_18001DB50
0x18001d9c7  mov     [rsp+300h+lpdwDisposition], 0; lpdwDisposition
0x18001d9d0  lea     rax, [rsp+300h+hKey]
0x18001d9d5  mov     [rsp+300h+phkResult], rax; phkResult
0x18001d9da  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x18001d9de  mov     [rsp+300h+lpSecurityAttributes], 0; unsigned int
0x18001d9e7  xor     r9d, r9d; lpClass
0x18001d9ea  mov     [rsp+300h+samDesired], 20006h; samDesired
0x18001d9f2  xor     r8d, r8d; Reserved
0x18001d9f5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d9fc  mov     [rsp+300h+dwOptions], ebx; dwOptions
0x18001da00  call    cs:__imp_RegCreateKeyExW
0x18001da06  mov     ebx, eax
0x18001da08  test    eax, eax
0x18001da0a  jnz     loc_18001DB50
0x18001da10  mov     edx, [r12]; unsigned __int64
0x18001da14  lea     r8, [rsp+300h+var_2A8]; unsigned __int64 *
0x18001da19  lea     ecx, [rax+27h]; unsigned __int64
0x18001da1c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001da21  test    eax, eax
0x18001da23  js      loc_18001DBBD
0x18001da29  mov     rax, [rsp+300h+var_2A8]
0x18001da2e  lea     r14, [rax+1]
0x18001da32  cmp     r14, rax
0x18001da35  jb      loc_18001DBBD
0x18001da3b  lea     r8, [rsp+300h+dwBytes]; unsigned __int64 *
0x18001da40  mov     rcx, r14; unsigned __int64
0x18001da43  lea     edx, [rbx+2]; unsigned __int64
0x18001da46  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001da4b  test    eax, eax
0x18001da4d  js      loc_18001DBBD
0x18001da53  mov     rcx, [rsp+300h+dwBytes]; dwBytes
0x18001da58  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001da5d  mov     rsi, rax
0x18001da60  test    rax, rax
0x18001da63  jnz     short loc_18001DA75
0x18001da65  call    cs:__imp_GetLastError
0x18001da6b  mov     ebx, eax
0x18001da6d  test    eax, eax
0x18001da6f  jnz     loc_18001DB50
0x18001da75  mov     rbx, rsi
0x18001da78  mov     [rsp+300h+var_2A8], r14
0x18001da7d  mov     rdi, r14
0x18001da80  xor     r15d, r15d
0x18001da83  mov     [rsp+300h+dwBytes], rbx
0x18001da88  cmp     r15d, [r12]
0x18001da8c  jnb     short loc_18001DB08
0x18001da8e  mov     ecx, r15d
0x18001da91  lea     rdx, [rsp+300h+sz]; lpsz
0x18001da96  shl     rcx, 4
0x18001da9a  mov     r8d, 27h ; '''; cchMax
0x18001daa0  add     rcx, 4
0x18001daa4  add     rcx, r12; rguid
0x18001daa7  call    cs:__imp_StringFromGUID2
0x18001daad  lea     rax, [rsp+300h+var_2A8]
0x18001dab2  mov     rdx, rdi; unsigned __int64
0x18001dab5  mov     qword ptr [rsp+300h+samDesired], rax; unsigned __int64 *
0x18001daba  lea     r8, [rsp+300h+sz]; unsigned __int16 *
0x18001dabf  lea     rax, [rsp+300h+dwBytes]
0x18001dac4  mov     rcx, rbx; unsigned __int16 *
0x18001dac7  mov     qword ptr [rsp+300h+dwOptions], rax; unsigned __int16 **
0x18001dacc  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18001dad1  mov     ebx, eax
0x18001dad3  test    eax, eax
0x18001dad5  jns     short loc_18001DAEA
0x18001dad7  and     eax, 1FFF0000h
0x18001dadc  cmp     eax, 70000h
0x18001dae1  jnz     short loc_18001DAE6
0x18001dae3  movzx   ebx, bx
0x18001dae6  test    ebx, ebx
0x18001dae8  jnz     short loc_18001DB3C
0x18001daea  mov     rdi, [rsp+300h+var_2A8]
0x18001daef  mov     rbx, [rsp+300h+dwBytes]
0x18001daf4  dec     rdi
0x18001daf7  add     rbx, 2
0x18001dafb  mov     [rsp+300h+var_2A8], rdi
0x18001db00  inc     r15d
0x18001db03  jmp     loc_18001DA83
0x18001db08  xor     eax, eax
0x18001db0a  lea     rcx, [r14+r14]
0x18001db0e  mov     [rbx], ax
0x18001db11  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001db16  mov     rcx, [rsp+300h+hKey]; hKey
0x18001db1b  lea     rdx, aProfilelist; "ProfileList"
0x18001db22  mov     [rsp+300h+samDesired], eax; cbData
0x18001db26  mov     r9d, 7; dwType
0x18001db2c  xor     r8d, r8d; Reserved
0x18001db2f  mov     qword ptr [rsp+300h+dwOptions], rsi; lpData
0x18001db34  call    cs:__imp_RegSetValueExW
0x18001db3a  mov     ebx, eax
0x18001db3c  test    rsi, rsi
0x18001db3f  jz      short loc_18001DB49
0x18001db41  mov     rcx, rsi; lpMem
0x18001db44  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001db49  lea     rdi, WPP_GLOBAL_Control
0x18001db50  mov     rcx, [rsp+300h+hKey]; hKey
0x18001db55  test    rcx, rcx
0x18001db58  jz      short loc_18001DB60
0x18001db5a  call    cs:__imp_RegCloseKey
0x18001db60  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db67  cmp     rcx, rdi
0x18001db6a  jz      short loc_18001DB90
0x18001db6c  cmp     byte ptr [rcx+19h], 4
0x18001db70  jb      short loc_18001DB90
0x18001db72  test    byte ptr [rcx+1Ch], 1
0x18001db76  jz      short loc_18001DB90
0x18001db78  mov     rcx, [rcx+10h]
0x18001db7c  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001db83  mov     edx, 1Ch
0x18001db88  mov     r9d, ebx
0x18001db8b  call    WPP_SF_d
0x18001db90  mov     eax, ebx
0x18001db92  mov     rcx, [rbp+200h+var_30]
0x18001db99  xor     rcx, rsp; StackCookie
0x18001db9c  call    __security_check_cookie
0x18001dba1  lea     r11, [rsp+300h+var_20]
0x18001dba9  mov     rbx, [r11+40h]
0x18001dbad  mov     rsi, [r11+48h]
0x18001dbb1  mov     rsp, r11
0x18001dbb4  pop     r15
0x18001dbb6  pop     r14
0x18001dbb8  pop     r12
0x18001dbba  pop     rdi
0x18001dbbb  pop     rbp
0x18001dbbc  retn
0x18001dbbd  mov     ebx, 216h
0x18001dbc2  jmp     short loc_18001DB50
```
