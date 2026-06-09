# IsCamCxhOnlyUser(ushort const *)

- ea: `0x14001f4f0`
- end: `0x14001f582`
- name: `?IsCamCxhOnlyUser@@YA_NPEBG@Z`
- size: `146`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f5bc`

## callees

- `0x14001f4f0`
- `0x1400202b4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001f530`
- `ADVAPI32!RegOpenKeyExW` at `0x14001f530`
- `ADVAPI32!RegCloseKey` at `0x14001f569`
- `ADVAPI32!RegCloseKey` at `0x14001f569`

## pseudocode

```c
char __fastcall IsCamCxhOnlyUser(const unsigned __int16 *a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // r9d
  bool v4; // sf
  int v6; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  if ( !a1 )
    return 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\CandidateAccountManager",
         0,
         0x20019u,
         &hKey);
  v4 = v2 < 0;
  if ( v2 > 0 )
    v4 = 1;
  if ( !v4 && (SHRegGetBOOLWithREGSAM(hKey, a1, L"CxhOnlyUse", v3, &v6), RegCloseKey(hKey), v6) )
    return 1;
  else
    return 0;
}

```

## disassembly

```asm
0x14001f4f0  push    rbx
0x14001f4f2  sub     rsp, 30h
0x14001f4f6  mov     [rsp+38h+arg_0], 0
0x14001f4fe  mov     rbx, rcx
0x14001f501  test    rcx, rcx
0x14001f504  jz      short loc_14001F57A
0x14001f506  lea     rax, [rsp+38h+hKey]
0x14001f50b  mov     [rsp+38h+hKey], 0
0x14001f514  mov     r9d, 20019h; samDesired
0x14001f51a  mov     [rsp+38h+phkResult], rax; phkResult
0x14001f51f  xor     r8d, r8d; ulOptions
0x14001f522  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001f529  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001f530  call    cs:__imp_RegOpenKeyExW
0x14001f536  test    eax, eax
0x14001f538  jle     short loc_14001F544
0x14001f53a  movzx   eax, ax
0x14001f53d  or      eax, 80070000h
0x14001f542  test    eax, eax
0x14001f544  js      short loc_14001F57A
0x14001f546  mov     rcx, [rsp+38h+hKey]; HKEY
0x14001f54b  lea     rax, [rsp+38h+arg_0]
0x14001f550  lea     r8, aCxhonlyuse; "CxhOnlyUse"
0x14001f557  mov     [rsp+38h+phkResult], rax; int *
0x14001f55c  mov     rdx, rbx; unsigned __int16 *
0x14001f55f  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x14001f564  mov     rcx, [rsp+38h+hKey]; hKey
0x14001f569  call    cs:__imp_RegCloseKey
0x14001f56f  cmp     [rsp+38h+arg_0], 0
0x14001f574  jz      short loc_14001F57A
0x14001f576  mov     al, 1
0x14001f578  jmp     short loc_14001F57C
0x14001f57a  xor     al, al
0x14001f57c  add     rsp, 30h
0x14001f580  pop     rbx
0x14001f581  retn
```
