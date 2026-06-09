# InitializeForPLAP(void)

- ea: `0x18001c080`
- end: `0x18001c2ac`
- name: `?InitializeForPLAP@@YAKXZ`
- size: `556`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000cbc0`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001bffc`
- `0x18001c080`
- `0x18001d47c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c132`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c132`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c16a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c16a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c25b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c25b`

## pseudocode

```c
__int64 InitializeForPLAP(void)
{
  struct _LIST_ENTRY *v0; // rcx
  unsigned int Dot3ServiceRootRegistryLocation; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[512]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 0;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 52, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  Dot3ServiceRootRegistryLocation = GetDot3ServiceRootRegistryLocation((__int64)v0, SubKey);
  v2 = Dot3ServiceRootRegistryLocation;
  if ( Dot3ServiceRootRegistryLocation )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      goto LABEL_32;
    if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
LABEL_27:
      if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) && (BYTE4(v4[1].Blink) & 1) != 0 )
      {
        v5 = 56;
        v6 = v2;
        goto LABEL_31;
      }
      goto LABEL_32;
    }
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      53,
      WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids,
      Dot3ServiceRootRegistryLocation);
LABEL_26:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( v2 )
    goto LABEL_26;
  v3 = RegQueryValueExW(hKey, L"L2NA8023Mode", 0, &Type, Data, &cbData);
  if ( !v3 && Type == 4 && cbData == 4 && *(_DWORD *)Data == 1 )
  {
    v3 = StRegisterCredProviders();
    if ( !v3 )
    {
      v4 = WPP_GLOBAL_Control;
      goto LABEL_32;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v5 = 54;
LABEL_16:
      v6 = v3;
LABEL_31:
      WPP_SF_d(v4[1].Flink, v5, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, v6);
      v4 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v5 = 55;
      goto LABEL_16;
    }
  }
LABEL_32:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 57, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18001c080  push    rbp
0x18001c082  push    rbx
0x18001c083  push    r12
0x18001c085  push    r14
0x18001c087  lea     rbp, [rsp-368h]
0x18001c08f  sub     rsp, 468h
0x18001c096  mov     rax, cs:__security_cookie
0x18001c09d  xor     rax, rsp
0x18001c0a0  mov     [rbp+380h+var_30], rax
0x18001c0a7  mov     [rsp+480h+hKey], 0
0x18001c0b0  mov     dword ptr [rsp+480h+Data], 0
0x18001c0b8  mov     [rsp+480h+cbData], 4
0x18001c0c0  mov     [rsp+480h+Type], 0
0x18001c0c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0cf  lea     r14, WPP_GLOBAL_Control
0x18001c0d6  lea     r12, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c0dd  cmp     rcx, r14
0x18001c0e0  jz      short loc_18001C0FF
0x18001c0e2  cmp     byte ptr [rcx+19h], 4
0x18001c0e6  jb      short loc_18001C0FF
0x18001c0e8  test    byte ptr [rcx+1Ch], 1
0x18001c0ec  jz      short loc_18001C0FF
0x18001c0ee  mov     rcx, [rcx+10h]
0x18001c0f2  mov     edx, 34h ; '4'
0x18001c0f7  mov     r8, r12
0x18001c0fa  call    WPP_SF_
0x18001c0ff  lea     rdx, [rsp+480h+SubKey]; unsigned __int16 *
0x18001c104  call    ?GetDot3ServiceRootRegistryLocation@@YAKKPEAG@Z; GetDot3ServiceRootRegistryLocation(ulong,ushort *)
0x18001c109  mov     ebx, eax
0x18001c10b  test    eax, eax
0x18001c10d  jnz     loc_18001C1ED
0x18001c113  lea     rax, [rsp+480h+hKey]
0x18001c118  mov     r9d, 20019h; samDesired
0x18001c11e  xor     r8d, r8d; ulOptions
0x18001c121  mov     [rsp+480h+phkResult], rax; phkResult
0x18001c126  lea     rdx, [rsp+480h+SubKey]; lpSubKey
0x18001c12b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c132  call    cs:__imp_RegOpenKeyExW
0x18001c138  mov     ebx, eax
0x18001c13a  test    eax, eax
0x18001c13c  jnz     loc_18001C219
0x18001c142  mov     rcx, [rsp+480h+hKey]; hKey
0x18001c147  lea     rax, [rsp+480h+cbData]
0x18001c14c  mov     [rsp+480h+lpcbData], rax; lpcbData
0x18001c151  lea     r9, [rsp+480h+Type]; lpType
0x18001c156  lea     rax, [rsp+480h+Data]
0x18001c15b  xor     r8d, r8d; lpReserved
0x18001c15e  lea     rdx, ValueName; "L2NA8023Mode"
0x18001c165  mov     [rsp+480h+phkResult], rax; lpData
0x18001c16a  call    cs:__imp_RegQueryValueExW
0x18001c170  test    eax, eax
0x18001c172  jnz     short loc_18001C1CE
0x18001c174  cmp     [rsp+480h+Type], 4
0x18001c179  jnz     short loc_18001C1CE
0x18001c17b  cmp     [rsp+480h+cbData], 4
0x18001c180  jnz     short loc_18001C1CE
0x18001c182  cmp     dword ptr [rsp+480h+Data], 1
0x18001c187  jnz     short loc_18001C1CE
0x18001c189  call    ?StRegisterCredProviders@@YAKXZ; StRegisterCredProviders(void)
0x18001c18e  mov     ebx, eax
0x18001c190  test    eax, eax
0x18001c192  jz      short loc_18001C1C2
0x18001c194  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c19b  cmp     rcx, r14
0x18001c19e  jz      loc_18001C24C
0x18001c1a4  cmp     byte ptr [rcx+19h], 1
0x18001c1a8  jb      loc_18001C24C
0x18001c1ae  test    byte ptr [rcx+1Ch], 1
0x18001c1b2  jz      loc_18001C24C
0x18001c1b8  mov     edx, 36h ; '6'
0x18001c1bd  mov     r9d, eax
0x18001c1c0  jmp     short loc_18001C239
0x18001c1c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1c9  jmp     loc_18001C24E
0x18001c1ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1d5  cmp     rcx, r14
0x18001c1d8  jz      short loc_18001C24C
0x18001c1da  cmp     byte ptr [rcx+19h], 1
0x18001c1de  jb      short loc_18001C24C
0x18001c1e0  test    byte ptr [rcx+1Ch], 1
0x18001c1e4  jz      short loc_18001C24C
0x18001c1e6  mov     edx, 37h ; '7'
0x18001c1eb  jmp     short loc_18001C1BD
0x18001c1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1f4  cmp     rcx, r14
0x18001c1f7  jz      short loc_18001C24C
0x18001c1f9  cmp     byte ptr [rcx+19h], 1
0x18001c1fd  jb      short loc_18001C220
0x18001c1ff  test    byte ptr [rcx+1Ch], 1
0x18001c203  jz      short loc_18001C220
0x18001c205  mov     rcx, [rcx+10h]
0x18001c209  mov     edx, 35h ; '5'
0x18001c20e  mov     r9d, eax
0x18001c211  mov     r8, r12
0x18001c214  call    WPP_SF_d
0x18001c219  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c220  cmp     rcx, r14
0x18001c223  jz      short loc_18001C24C
0x18001c225  cmp     byte ptr [rcx+19h], 1
0x18001c229  jb      short loc_18001C24C
0x18001c22b  test    byte ptr [rcx+1Ch], 1
0x18001c22f  jz      short loc_18001C24C
0x18001c231  mov     edx, 38h ; '8'
0x18001c236  mov     r9d, ebx
0x18001c239  mov     rcx, [rcx+10h]
0x18001c23d  mov     r8, r12
0x18001c240  call    WPP_SF_d
0x18001c245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c24c  xor     ebx, ebx
0x18001c24e  mov     rax, [rsp+480h+hKey]
0x18001c253  test    rax, rax
0x18001c256  jz      short loc_18001C268
0x18001c258  mov     rcx, rax; hKey
0x18001c25b  call    cs:__imp_RegCloseKey
0x18001c261  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c268  cmp     rcx, r14
0x18001c26b  jz      short loc_18001C28D
0x18001c26d  cmp     byte ptr [rcx+19h], 4
0x18001c271  jb      short loc_18001C28D
0x18001c273  test    byte ptr [rcx+1Ch], 1
0x18001c277  jz      short loc_18001C28D
0x18001c279  mov     rcx, [rcx+10h]
0x18001c27d  mov     edx, 39h ; '9'
0x18001c282  mov     r9d, ebx
0x18001c285  mov     r8, r12
0x18001c288  call    WPP_SF_d
0x18001c28d  mov     eax, ebx
0x18001c28f  mov     rcx, [rbp+380h+var_30]
0x18001c296  xor     rcx, rsp; StackCookie
0x18001c299  call    __security_check_cookie
0x18001c29e  add     rsp, 468h
0x18001c2a5  pop     r14
0x18001c2a7  pop     r12
0x18001c2a9  pop     rbx
0x18001c2aa  pop     rbp
0x18001c2ab  retn
```
