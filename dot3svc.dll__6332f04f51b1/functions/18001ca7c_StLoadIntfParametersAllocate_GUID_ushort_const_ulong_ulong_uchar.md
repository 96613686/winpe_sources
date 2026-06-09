# StLoadIntfParametersAllocate(_GUID *,ushort const *,ulong,ulong *,uchar * *)

- ea: `0x18001ca7c`
- end: `0x18001cbdd`
- name: `?StLoadIntfParametersAllocate@@YAKPEAU_GUID@@PEBGKPEAKPEAPEAE@Z`
- size: `353`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180011638`
- `0x180011d28`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001ca7c`
- `0x18001e620`
- `0x18001e808`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001cb3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001cb7e`

## pseudocode

```c
__int64 __fastcall StLoadIntfParametersAllocate(
        struct _GUID *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  struct _LIST_ENTRY *v8; // rcx
  unsigned int RegKeyPath; // ebx
  HKEY hKey; // [rsp+30h] [rbp-258h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-248h] BYREF

  hKey = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 41, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( a4 && a5 )
  {
    RegKeyPath = StpGetRegKeyPath(0, 0, 0, SubKey, 0x104u);
    if ( !RegKeyPath )
    {
      RegKeyPath = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
      if ( !RegKeyPath )
        RegKeyPath = StpQueryRegValue(hKey, a2, a3, a4, a5);
    }
    v8 = WPP_GLOBAL_Control;
  }
  else
  {
    RegKeyPath = 87;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_d(v8[1].Flink, 42, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001ca7c  mov     [rsp+arg_0], rbx
0x18001ca81  push    rbp
0x18001ca82  push    rsi
0x18001ca83  push    rdi
0x18001ca84  push    r14
0x18001ca86  push    r15
0x18001ca88  sub     rsp, 260h
0x18001ca8f  mov     rax, cs:__security_cookie
0x18001ca96  xor     rax, rsp
0x18001ca99  mov     [rsp+288h+var_38], rax
0x18001caa1  mov     rsi, [rsp+288h+arg_20]
0x18001caa9  mov     rdi, r9
0x18001caac  mov     r14d, r8d
0x18001caaf  mov     [rsp+288h+hKey], 0
0x18001cab8  mov     rbp, rdx
0x18001cabb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cac2  lea     r15, WPP_GLOBAL_Control
0x18001cac9  cmp     rcx, r15
0x18001cacc  jz      short loc_18001CAF6
0x18001cace  cmp     byte ptr [rcx+19h], 4
0x18001cad2  jb      short loc_18001CAF6
0x18001cad4  test    byte ptr [rcx+1Ch], 1
0x18001cad8  jz      short loc_18001CAF6
0x18001cada  mov     rcx, [rcx+10h]
0x18001cade  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001cae5  mov     edx, 29h ; ')'
0x18001caea  call    WPP_SF_
0x18001caef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caf6  test    rdi, rdi
0x18001caf9  jz      short loc_18001CB6C
0x18001cafb  test    rsi, rsi
0x18001cafe  jz      short loc_18001CB6C
0x18001cb00  lea     r9, [rsp+288h+SubKey]; unsigned __int16 *
0x18001cb05  mov     [rsp+288h+phkResult], 104h; unsigned __int64
0x18001cb0e  xor     r8d, r8d; int
0x18001cb11  xor     edx, edx; GUID *
0x18001cb13  xor     ecx, ecx; rguid
0x18001cb15  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001cb1a  mov     ebx, eax
0x18001cb1c  test    eax, eax
0x18001cb1e  jnz     short loc_18001CB63
0x18001cb20  lea     rax, [rsp+288h+hKey]
0x18001cb25  xor     r8d, r8d; ulOptions
0x18001cb28  lea     r9d, [rbx+1]; samDesired
0x18001cb2c  mov     [rsp+288h+phkResult], rax; phkResult
0x18001cb31  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18001cb36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001cb3d  call    cs:__imp_RegOpenKeyExW
0x18001cb43  mov     ebx, eax
0x18001cb45  test    eax, eax
0x18001cb47  jnz     short loc_18001CB63
0x18001cb49  mov     rcx, [rsp+288h+hKey]; hKey
0x18001cb4e  mov     r9, rdi; unsigned int *
0x18001cb51  mov     r8d, r14d; unsigned int
0x18001cb54  mov     [rsp+288h+phkResult], rsi; unsigned __int8 **
0x18001cb59  mov     rdx, rbp; lpValueName
0x18001cb5c  call    ?StpQueryRegValue@@YAKPEAUHKEY__@@PEBGKPEAKPEAPEAE@Z; StpQueryRegValue(HKEY__ *,ushort const *,ulong,ulong *,uchar * *)
0x18001cb61  mov     ebx, eax
0x18001cb63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb6a  jmp     short loc_18001CB71
0x18001cb6c  mov     ebx, 57h ; 'W'
0x18001cb71  mov     rax, [rsp+288h+hKey]
0x18001cb76  test    rax, rax
0x18001cb79  jz      short loc_18001CB8B
0x18001cb7b  mov     rcx, rax; hKey
0x18001cb7e  call    cs:__imp_RegCloseKey
0x18001cb84  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cb8b  cmp     rcx, r15
0x18001cb8e  jz      short loc_18001CBB4
0x18001cb90  cmp     byte ptr [rcx+19h], 4
0x18001cb94  jb      short loc_18001CBB4
0x18001cb96  test    byte ptr [rcx+1Ch], 1
0x18001cb9a  jz      short loc_18001CBB4
0x18001cb9c  mov     rcx, [rcx+10h]
0x18001cba0  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001cba7  mov     edx, 2Ah ; '*'
0x18001cbac  mov     r9d, ebx
0x18001cbaf  call    WPP_SF_d
0x18001cbb4  mov     eax, ebx
0x18001cbb6  mov     rcx, [rsp+288h+var_38]
0x18001cbbe  xor     rcx, rsp; StackCookie
0x18001cbc1  call    __security_check_cookie
0x18001cbc6  mov     rbx, [rsp+288h+arg_0]
0x18001cbce  add     rsp, 260h
0x18001cbd5  pop     r15
0x18001cbd7  pop     r14
0x18001cbd9  pop     rdi
0x18001cbda  pop     rsi
0x18001cbdb  pop     rbp
0x18001cbdc  retn
```
