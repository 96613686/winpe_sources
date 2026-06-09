# StDeleteProfileMetaData(_GUID *,_GUID *)

- ea: `0x18001c438`
- end: `0x18001c529`
- name: `?StDeleteProfileMetaData@@YAKPEAU_GUID@@0@Z`
- size: `241`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000d638`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001c438`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001c4ca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18001c4ca`

## pseudocode

```c
__int64 __fastcall StDeleteProfileMetaData(GUID *rguid, GUID *a2)
{
  unsigned int RegKeyPath; // ebx
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 25, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, a2, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
    RegKeyPath = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 26, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001c438  mov     [rsp+arg_10], rbx
0x18001c43d  mov     [rsp+arg_18], rsi
0x18001c442  push    rdi
0x18001c443  sub     rsp, 250h
0x18001c44a  mov     rax, cs:__security_cookie
0x18001c451  xor     rax, rsp
0x18001c454  mov     [rsp+258h+var_18], rax
0x18001c45c  mov     rdi, rdx
0x18001c45f  mov     rbx, rcx
0x18001c462  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c469  lea     rsi, WPP_GLOBAL_Control
0x18001c470  cmp     rcx, rsi
0x18001c473  jz      short loc_18001C496
0x18001c475  cmp     byte ptr [rcx+19h], 4
0x18001c479  jb      short loc_18001C496
0x18001c47b  test    byte ptr [rcx+1Ch], 1
0x18001c47f  jz      short loc_18001C496
0x18001c481  mov     rcx, [rcx+10h]
0x18001c485  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c48c  mov     edx, 19h
0x18001c491  call    WPP_SF_
0x18001c496  lea     r9, [rsp+258h+SubKey]; unsigned __int16 *
0x18001c49b  mov     [rsp+258h+var_238], 104h; unsigned __int64
0x18001c4a4  xor     r8d, r8d; int
0x18001c4a7  mov     rdx, rdi; GUID *
0x18001c4aa  mov     rcx, rbx; rguid
0x18001c4ad  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001c4b2  mov     ebx, eax
0x18001c4b4  test    eax, eax
0x18001c4b6  jnz     short loc_18001C4D2
0x18001c4b8  xor     r9d, r9d; Reserved
0x18001c4bb  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x18001c4c0  xor     r8d, r8d; samDesired
0x18001c4c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c4ca  call    cs:__imp_RegDeleteKeyExW
0x18001c4d0  mov     ebx, eax
0x18001c4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4d9  cmp     rcx, rsi
0x18001c4dc  jz      short loc_18001C502
0x18001c4de  cmp     byte ptr [rcx+19h], 4
0x18001c4e2  jb      short loc_18001C502
0x18001c4e4  test    byte ptr [rcx+1Ch], 1
0x18001c4e8  jz      short loc_18001C502
0x18001c4ea  mov     rcx, [rcx+10h]
0x18001c4ee  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001c4f5  mov     edx, 1Ah
0x18001c4fa  mov     r9d, ebx
0x18001c4fd  call    WPP_SF_d
0x18001c502  mov     eax, ebx
0x18001c504  mov     rcx, [rsp+258h+var_18]
0x18001c50c  xor     rcx, rsp; StackCookie
0x18001c50f  call    __security_check_cookie
0x18001c514  lea     r11, [rsp+258h+var_8]
0x18001c51c  mov     rbx, [r11+20h]
0x18001c520  mov     rsi, [r11+28h]
0x18001c524  mov     rsp, r11
0x18001c527  pop     rdi
0x18001c528  retn
```
