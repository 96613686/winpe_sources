# EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)

- ea: `0x18000eb50`
- end: `0x18000ec02`
- name: `?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z`
- size: `178`
- prototype: `int __fastcall(struct _GUID *, __int64, const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e2d0`
- `0x18000e354`

## callees

- `0x180001a70`
- `0x18000deb0`
- `0x18000e994`
- `0x18000eb50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eb8e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000eb8e`

## pseudocode

```c
int __fastcall EEDBManager::OpenEnrollmentKey(struct _GUID *a1, __int64 a2, const unsigned __int16 *a3, HKEY *a4)
{
  int result; // eax
  OLECHAR sz[40]; // [rsp+30h] [rbp-2C8h] BYREF
  wchar_t String1[40]; // [rsp+80h] [rbp-278h] BYREF
  unsigned __int16 v8[264]; // [rsp+D0h] [rbp-228h] BYREF

  v8[0] = 0;
  String1[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2(a1, sz, 39) != 39 )
    return -2147418113;
  result = EEDBTrimGuidBracket(sz, String1);
  if ( result >= 0 )
    return EEDBManager::OpenEnrollmentHKEY(HKEY_LOCAL_MACHINE, String1, 131097, a4, v8, 0x104u);
  return result;
}

```

## disassembly

```asm
0x18000eb50  push    rbx
0x18000eb52  sub     rsp, 2F0h
0x18000eb59  mov     rax, cs:__security_cookie
0x18000eb60  xor     rax, rsp
0x18000eb63  mov     [rsp+2F8h+var_18], rax
0x18000eb6b  xor     eax, eax
0x18000eb6d  lea     rdx, [rsp+2F8h+sz]; lpsz
0x18000eb72  mov     rbx, r9
0x18000eb75  mov     [rsp+2F8h+var_228], ax
0x18000eb7d  mov     [rsp+2F8h+String1], ax
0x18000eb85  mov     [rsp+2F8h+sz], ax
0x18000eb8a  lea     r8d, [rax+27h]; cchMax
0x18000eb8e  call    cs:__imp_StringFromGUID2
0x18000eb94  cmp     eax, 27h ; '''
0x18000eb97  jz      short loc_18000EBA0
0x18000eb99  mov     eax, 8000FFFFh
0x18000eb9e  jmp     short loc_18000EBE9
0x18000eba0  lea     rdx, [rsp+2F8h+String1]; unsigned __int16 *
0x18000eba8  lea     rcx, [rsp+2F8h+sz]; unsigned __int16 *
0x18000ebad  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x18000ebb2  test    eax, eax
0x18000ebb4  js      short loc_18000EBE9
0x18000ebb6  lea     rax, [rsp+2F8h+var_228]
0x18000ebbe  mov     [rsp+2F8h+var_2D0], 104h; unsigned __int64
0x18000ebc7  mov     r9, rbx; HKEY *
0x18000ebca  mov     [rsp+2F8h+var_2D8], rax; unsigned __int16 *
0x18000ebcf  mov     r8d, 20019h; unsigned int
0x18000ebd5  lea     rdx, [rsp+2F8h+String1]; String1
0x18000ebdd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ebe4  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x18000ebe9  mov     rcx, [rsp+2F8h+var_18]
0x18000ebf1  xor     rcx, rsp; StackCookie
0x18000ebf4  call    __security_check_cookie
0x18000ebf9  add     rsp, 2F0h
0x18000ec00  pop     rbx
0x18000ec01  retn
```
