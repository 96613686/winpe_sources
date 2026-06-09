# VerifyCertValidity(_CERT_CONTEXT const *)

- ea: `0x180026118`
- end: `0x1800261af`
- name: `?VerifyCertValidity@@YAHPEBU_CERT_CONTEXT@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025e00`

## callees

- `0x180026118`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002614c`
- `ADVAPI32!RegOpenKeyExW` at `0x18002614c`
- `ADVAPI32!RegCloseKey` at `0x18002619a`
- `ADVAPI32!RegCloseKey` at `0x18002619a`
- `KERNEL32!CompareFileTime` at `0x18002617f`
- `KERNEL32!CompareFileTime` at `0x18002617f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180026166`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180026166`

## pseudocode

```c
__int64 __fastcall VerifyCertValidity(const struct _CERT_CONTEXT *a1)
{
  unsigned int v2; // ebx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  SystemTimeAsFileTime = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\TermServLicensing\\IgnoreLicenseExpiration",
         0,
         0x20019u,
         &hKey) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = (unsigned int)CompareFileTime(&SystemTimeAsFileTime, &a1->pCertInfo->NotAfter) >> 31;
  }
  else
  {
    v2 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180026118  mov     r11, rsp
0x18002611b  push    rbx
0x18002611c  sub     rsp, 30h
0x180026120  and     qword ptr [r11+10h], 0
0x180026125  lea     rax, [r11+18h]
0x180026129  and     qword ptr [r11+18h], 0
0x18002612e  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\TermServLicensing"...
0x180026135  mov     rbx, rcx
0x180026138  mov     [r11-18h], rax
0x18002613c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026143  mov     r9d, 20019h; samDesired
0x180026149  xor     r8d, r8d; ulOptions
0x18002614c  call    cs:__imp_RegOpenKeyExW
0x180026153  nop     dword ptr [rax+rax+00h]
0x180026158  test    eax, eax
0x18002615a  jnz     short loc_180026161
0x18002615c  lea     ebx, [rax+1]
0x18002615f  jmp     short loc_180026190
0x180026161  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026166  call    cs:__imp_GetSystemTimeAsFileTime
0x18002616d  nop     dword ptr [rax+rax+00h]
0x180026172  mov     rdx, [rbx+18h]
0x180026176  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x18002617b  add     rdx, 48h ; 'H'; lpFileTime2
0x18002617f  call    cs:__imp_CompareFileTime
0x180026186  nop     dword ptr [rax+rax+00h]
0x18002618b  mov     ebx, eax
0x18002618d  shr     ebx, 1Fh
0x180026190  mov     rcx, [rsp+38h+hKey]; hKey
0x180026195  test    rcx, rcx
0x180026198  jz      short loc_1800261A6
0x18002619a  call    cs:__imp_RegCloseKey
0x1800261a1  nop     dword ptr [rax+rax+00h]
0x1800261a6  mov     eax, ebx
0x1800261a8  add     rsp, 30h
0x1800261ac  pop     rbx
0x1800261ad  retn
```
