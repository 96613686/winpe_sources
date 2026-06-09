# CVistaInterfaceSettings::InitInterface(HKEY__ *,ushort const *,_GUID,ushort const *)

- ea: `0x180037e9c`
- end: `0x180037ff0`
- name: `?InitInterface@CVistaInterfaceSettings@@QEAAJPEAUHKEY__@@PEBGU_GUID@@1@Z`
- size: `340`
- prototype: `__int64 __fastcall(struct _GUID *this, HKEY hKey, LPCWSTR lpSubKey, struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800362c8`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180036dfc`
- `0x180037e9c`
- `0x1800381b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037f38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037f38`

## pseudocode

```c
__int64 __fastcall CVistaInterfaceSettings::InitInterface(
        struct _GUID *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        struct _GUID *a4,
        unsigned __int16 *a5)
{
  unsigned int v9; // eax
  signed int Profiles; // ebx
  bool v11; // sf
  HKEY hkey; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids);
  }
  hkey = 0;
  if ( hKey && lpSubKey && a5 )
  {
    this[2] = *a4;
    v9 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hkey);
    Profiles = v9;
    if ( !v9 )
      goto LABEL_16;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 15, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids, v9);
    }
    v11 = Profiles < 0;
    if ( Profiles > 0 )
    {
      Profiles = (unsigned __int16)Profiles | 0x80070000;
      v11 = Profiles < 0;
    }
    if ( !v11 )
LABEL_16:
      Profiles = CVistaInterfaceSettings::LoadProfiles((CVistaInterfaceSettings *)this, hkey, a5);
  }
  else
  {
    Profiles = -2147024809;
  }
  SafeCloseKey(&hkey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 16, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids, (unsigned int)Profiles);
  }
  return (unsigned int)Profiles;
}

```

## disassembly

```asm
0x180037e9c  mov     [rsp+arg_0], rbx
0x180037ea1  mov     [rsp+arg_10], rbp
0x180037ea6  push    rsi
0x180037ea7  push    r12
0x180037ea9  push    r14
0x180037eab  sub     rsp, 30h
0x180037eaf  mov     r14, r9
0x180037eb2  mov     rbx, r8
0x180037eb5  mov     rsi, rdx
0x180037eb8  mov     rbp, rcx
0x180037ebb  mov     rcx, cs:WPP_GLOBAL_Control
0x180037ec2  lea     r12, WPP_GLOBAL_Control
0x180037ec9  cmp     rcx, r12
0x180037ecc  jz      short loc_180037EEF
0x180037ece  cmp     byte ptr [rcx+19h], 4
0x180037ed2  jb      short loc_180037EEF
0x180037ed4  test    byte ptr [rcx+1Ch], 1
0x180037ed8  jz      short loc_180037EEF
0x180037eda  mov     rcx, [rcx+10h]
0x180037ede  lea     r8, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids
0x180037ee5  mov     edx, 0Eh
0x180037eea  call    WPP_SF_
0x180037eef  mov     [rsp+48h+hkey], 0
0x180037ef8  test    rsi, rsi
0x180037efb  jz      loc_180037F9B
0x180037f01  test    rbx, rbx
0x180037f04  jz      loc_180037F9B
0x180037f0a  cmp     [rsp+48h+arg_20], 0
0x180037f10  jz      loc_180037F9B
0x180037f16  movaps  xmm0, xmmword ptr [r14]
0x180037f1a  lea     rax, [rsp+48h+hkey]
0x180037f1f  mov     r9d, 20019h; samDesired
0x180037f25  mov     [rsp+48h+phkResult], rax; phkResult
0x180037f2a  xor     r8d, r8d; ulOptions
0x180037f2d  mov     rdx, rbx; lpSubKey
0x180037f30  mov     rcx, rsi; hKey
0x180037f33  movdqu  xmmword ptr [rbp+20h], xmm0
0x180037f38  call    cs:__imp_RegOpenKeyExW
0x180037f3e  mov     ebx, eax
0x180037f40  test    eax, eax
0x180037f42  jz      short loc_180037F85
0x180037f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f4b  cmp     rcx, r12
0x180037f4e  jz      short loc_180037F74
0x180037f50  cmp     byte ptr [rcx+19h], 1
0x180037f54  jb      short loc_180037F74
0x180037f56  test    byte ptr [rcx+1Ch], 1
0x180037f5a  jz      short loc_180037F74
0x180037f5c  mov     rcx, [rcx+10h]
0x180037f60  lea     r8, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids
0x180037f67  mov     edx, 0Fh
0x180037f6c  mov     r9d, eax
0x180037f6f  call    WPP_SF_d
0x180037f74  test    ebx, ebx
0x180037f76  jle     short loc_180037F83
0x180037f78  movzx   ebx, bx
0x180037f7b  or      ebx, 80070000h
0x180037f81  test    ebx, ebx
0x180037f83  js      short loc_180037FA0
0x180037f85  mov     r8, [rsp+48h+arg_20]; unsigned __int16 *
0x180037f8a  mov     rcx, rbp; this
0x180037f8d  mov     rdx, [rsp+48h+hkey]; hkey
0x180037f92  call    ?LoadProfiles@CVistaInterfaceSettings@@QEAAJPEAUHKEY__@@PEBG@Z; CVistaInterfaceSettings::LoadProfiles(HKEY__ *,ushort const *)
0x180037f97  mov     ebx, eax
0x180037f99  jmp     short loc_180037FA0
0x180037f9b  mov     ebx, 80070057h
0x180037fa0  lea     rcx, [rsp+48h+hkey]; HKEY *
0x180037fa5  call    ?SafeCloseKey@@YAXAEAPEAUHKEY__@@@Z; SafeCloseKey(HKEY__ * &)
0x180037faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fb1  cmp     rcx, r12
0x180037fb4  jz      short loc_180037FDA
0x180037fb6  cmp     byte ptr [rcx+19h], 4
0x180037fba  jb      short loc_180037FDA
0x180037fbc  test    byte ptr [rcx+1Ch], 1
0x180037fc0  jz      short loc_180037FDA
0x180037fc2  mov     rcx, [rcx+10h]
0x180037fc6  lea     r8, WPP_70f92f02fefa32abcc20130b0f9a98ba_Traceguids
0x180037fcd  mov     edx, 10h
0x180037fd2  mov     r9d, ebx
0x180037fd5  call    WPP_SF_d
0x180037fda  mov     rbp, [rsp+48h+arg_10]
0x180037fdf  mov     eax, ebx
0x180037fe1  mov     rbx, [rsp+48h+arg_0]
0x180037fe6  add     rsp, 30h
0x180037fea  pop     r14
0x180037fec  pop     r12
0x180037fee  pop     rsi
0x180037fef  retn
```
