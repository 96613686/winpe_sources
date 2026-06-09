# CDot3Profile::GetMigratedData(ushort const *)

- ea: `0x180037134`
- end: `0x18003730e`
- name: `?GetMigratedData@CDot3Profile@@QEAAJPEBG@Z`
- size: `474`
- prototype: `__int64 __fastcall(CDot3Profile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034a78`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x180012874`
- `0x180036dfc`
- `0x180037134`
- `0x180037314`
- `0x180038480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800371ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800371ca`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18003721d`
- `api-ms-win-shcore-registry-l1-1-0!SHEnumKeyExW` at `0x18003721d`

## pseudocode

```c
__int64 __fastcall CDot3Profile::GetMigratedData(CDot3Profile *this, const unsigned __int16 *a2)
{
  unsigned int v3; // eax
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  DWORD v6; // edi
  DWORD i; // edx
  const unsigned __int16 *v8; // rdx
  unsigned int ProfileXml; // eax
  int v10; // ebx
  DWORD pcchName; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hkey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszName[264]; // [rsp+40h] [rbp-C0h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_05335b45813f339031e56eee033bcbc8_Traceguids);
  }
  hkey = 0;
  CGlobalEapolSettings::Acquire((CDot3Profile *)((char *)this + 8));
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Wlansvc\\MigrationData\\Upgrade\\EAPOL\\Parameters\\Interfaces",
         0,
         0x20019u,
         &hkey);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control[1].Blink)
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_24;
    }
    v5 = 11;
    goto LABEL_23;
  }
  v6 = 0;
  for ( i = 0; ; i = v6 )
  {
    pcchName = 260;
    v3 = SHEnumKeyExW(hkey, i, pszName, &pcchName);
    if ( v3 )
      break;
    ProfileXml = CDot3Profile::GetProfileXml(this, v8, pszName);
    v10 = ProfileXml;
    if ( !ProfileXml )
      goto LABEL_25;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_Sd(
        WPP_GLOBAL_Control[1].Flink,
        12,
        (unsigned int)WPP_05335b45813f339031e56eee033bcbc8_Traceguids,
        (unsigned int)pszName,
        ProfileXml);
    }
    ++v6;
  }
  if ( v3 != 259 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v5 = 13;
LABEL_23:
      WPP_SF_d(v4[1].Flink, v5, WPP_05335b45813f339031e56eee033bcbc8_Traceguids, v3);
    }
  }
LABEL_24:
  v10 = 1168;
LABEL_25:
  SafeCloseKey(&hkey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 14, WPP_05335b45813f339031e56eee033bcbc8_Traceguids, (unsigned int)v10);
  }
  if ( v10 > 0 )
    return (unsigned __int16)v10 | 0x80070000;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180037134  push    rbp
0x180037136  push    rbx
0x180037137  push    rsi
0x180037138  push    rdi
0x180037139  push    r12
0x18003713b  push    r15
0x18003713d  lea     rbp, [rsp-168h]
0x180037145  sub     rsp, 268h
0x18003714c  mov     rax, cs:__security_cookie
0x180037153  xor     rax, rsp
0x180037156  mov     [rbp+190h+var_40], rax
0x18003715d  mov     rsi, rcx
0x180037160  mov     rcx, cs:WPP_GLOBAL_Control
0x180037167  lea     r15, WPP_GLOBAL_Control
0x18003716e  lea     r12, WPP_05335b45813f339031e56eee033bcbc8_Traceguids
0x180037175  cmp     rcx, r15
0x180037178  jz      short loc_180037197
0x18003717a  cmp     byte ptr [rcx+19h], 4
0x18003717e  jb      short loc_180037197
0x180037180  test    byte ptr [rcx+1Ch], 1
0x180037184  jz      short loc_180037197
0x180037186  mov     rcx, [rcx+10h]
0x18003718a  mov     edx, 0Ah
0x18003718f  mov     r8, r12
0x180037192  call    WPP_SF_
0x180037197  lea     rcx, [rsi+8]; this
0x18003719b  mov     [rsp+290h+hkey], 0
0x1800371a4  call    ?Acquire@CGlobalEapolSettings@@QEAAXXZ; CGlobalEapolSettings::Acquire(void)
0x1800371a9  lea     rax, [rsp+290h+hkey]
0x1800371ae  mov     r9d, 20019h; samDesired
0x1800371b4  xor     r8d, r8d; ulOptions
0x1800371b7  mov     [rsp+290h+phkResult], rax; phkResult
0x1800371bc  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Wlansvc\\Migration"...
0x1800371c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800371ca  call    cs:__imp_RegOpenKeyExW
0x1800371d0  test    eax, eax
0x1800371d2  jz      short loc_180037202
0x1800371d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800371db  cmp     rcx, r15
0x1800371de  jz      loc_1800372A5
0x1800371e4  cmp     byte ptr [rcx+19h], 1
0x1800371e8  jb      loc_1800372A5
0x1800371ee  test    byte ptr [rcx+1Ch], 1
0x1800371f2  jz      loc_1800372A5
0x1800371f8  mov     edx, 0Bh
0x1800371fd  jmp     loc_180037296
0x180037202  xor     edi, edi
0x180037204  xor     edx, edx; dwIndex
0x180037206  mov     rcx, [rsp+290h+hkey]; hkey
0x18003720b  lea     r9, [rsp+290h+pcchName]; pcchName
0x180037210  lea     r8, [rsp+290h+pszName]; pszName
0x180037215  mov     [rsp+290h+pcchName], 104h
0x18003721d  call    cs:__imp_SHEnumKeyExW
0x180037223  test    eax, eax
0x180037225  jnz     short loc_180037272
0x180037227  lea     r8, [rsp+290h+pszName]; unsigned __int16 *
0x18003722c  mov     rcx, rsi; this
0x18003722f  call    ?GetProfileXml@CDot3Profile@@QEAAKPEBG0@Z; CDot3Profile::GetProfileXml(ushort const *,ushort const *)
0x180037234  mov     ebx, eax
0x180037236  test    eax, eax
0x180037238  jz      short loc_1800372AA
0x18003723a  mov     rcx, cs:WPP_GLOBAL_Control
0x180037241  cmp     rcx, r15
0x180037244  jz      short loc_18003726C
0x180037246  cmp     byte ptr [rcx+19h], 1
0x18003724a  jb      short loc_18003726C
0x18003724c  test    byte ptr [rcx+1Ch], 1
0x180037250  jz      short loc_18003726C
0x180037252  mov     rcx, [rcx+10h]
0x180037256  lea     r9, [rsp+290h+pszName]
0x18003725b  mov     edx, 0Ch
0x180037260  mov     dword ptr [rsp+290h+phkResult], eax
0x180037264  mov     r8, r12
0x180037267  call    WPP_SF_Sd
0x18003726c  inc     edi
0x18003726e  mov     edx, edi
0x180037270  jmp     short loc_180037206
0x180037272  cmp     eax, 103h
0x180037277  jz      short loc_1800372A5
0x180037279  mov     rcx, cs:WPP_GLOBAL_Control
0x180037280  cmp     rcx, r15
0x180037283  jz      short loc_1800372A5
0x180037285  cmp     byte ptr [rcx+19h], 1
0x180037289  jb      short loc_1800372A5
0x18003728b  test    byte ptr [rcx+1Ch], 1
0x18003728f  jz      short loc_1800372A5
0x180037291  mov     edx, 0Dh
0x180037296  mov     rcx, [rcx+10h]
0x18003729a  mov     r9d, eax
0x18003729d  mov     r8, r12
0x1800372a0  call    WPP_SF_d
0x1800372a5  mov     ebx, 490h
0x1800372aa  lea     rcx, [rsp+290h+hkey]; HKEY *
0x1800372af  call    ?SafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * &)
0x1800372b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372bb  cmp     rcx, r15
0x1800372be  jz      short loc_1800372E0
0x1800372c0  cmp     byte ptr [rcx+19h], 4
0x1800372c4  jb      short loc_1800372E0
0x1800372c6  test    byte ptr [rcx+1Ch], 1
0x1800372ca  jz      short loc_1800372E0
0x1800372cc  mov     rcx, [rcx+10h]
0x1800372d0  mov     edx, 0Eh
0x1800372d5  mov     r9d, ebx
0x1800372d8  mov     r8, r12
0x1800372db  call    WPP_SF_d
0x1800372e0  test    ebx, ebx
0x1800372e2  jle     short loc_1800372ED
0x1800372e4  movzx   ebx, bx
0x1800372e7  or      ebx, 80070000h
0x1800372ed  mov     eax, ebx
0x1800372ef  mov     rcx, [rbp+190h+var_40]
0x1800372f6  xor     rcx, rsp; StackCookie
0x1800372f9  call    __security_check_cookie
0x1800372fe  add     rsp, 268h
0x180037305  pop     r15
0x180037307  pop     r12
0x180037309  pop     rdi
0x18003730a  pop     rsi
0x18003730b  pop     rbx
0x18003730c  pop     rbp
0x18003730d  retn
```
