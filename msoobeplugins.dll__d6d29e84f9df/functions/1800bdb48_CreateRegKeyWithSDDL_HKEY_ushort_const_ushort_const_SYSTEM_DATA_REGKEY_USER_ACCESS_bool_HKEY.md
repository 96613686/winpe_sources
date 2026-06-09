# _CreateRegKeyWithSDDL(HKEY__ *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,bool,HKEY__ * *)

- ea: `0x1800bdb48`
- end: `0x1800bdc62`
- name: `?_CreateRegKeyWithSDDL@@YAJPEAUHKEY__@@PEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@_NPEAPEAU1@@Z`
- size: `282`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, enum SYSTEM_DATA_REGKEY_USER_ACCESS, bool, HKEY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800bdc68`

## callees

- `0x180003470`
- `0x180008b54`
- `0x18000ac48`
- `0x1800bdb48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bdc3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bdc25`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bdc25`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bdbb8`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bdbb8`

## pseudocode

```c
__int64 __fastcall _CreateRegKeyWithSDDL(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        PHKEY phkResult)
{
  signed int Error; // ebx
  LSTATUS v8; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+70h] [rbp-90h] BYREF

  *phkResult = 0;
  Error = StringCchCopyW(StringSecurityDescriptor, 0x104u, L"D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CIOI;KR;;;WD)");
  if ( Error >= 0 )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
      *(_QWORD *)&SecurityAttributes.nLength = 24;
      *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
      v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, (LPWSTR)&Class, 0, 0x2001Fu, &SecurityAttributes, phkResult, 0);
      Error = v8;
      if ( v8 > 0 )
        Error = (unsigned __int16)v8 | 0x80070000;
      LocalFree(SecurityDescriptor);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800bdb48  push    rbp
0x1800bdb4a  push    rbx
0x1800bdb4b  push    rsi
0x1800bdb4c  push    rdi
0x1800bdb4d  lea     rbp, [rsp-198h]
0x1800bdb55  sub     rsp, 298h
0x1800bdb5c  mov     rax, cs:__security_cookie
0x1800bdb63  xor     rax, rsp
0x1800bdb66  mov     [rbp+1B0h+var_30], rax
0x1800bdb6d  mov     rdi, [rbp+1B0h+arg_28]
0x1800bdb74  lea     rcx, [rsp+2B0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800bdb79  mov     rsi, r8
0x1800bdb7c  mov     edx, 104h; unsigned __int64
0x1800bdb81  mov     qword ptr [rdi], 0
0x1800bdb88  mov     r8, cs:off_1800D5D20; unsigned __int16 *
0x1800bdb8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800bdb94  mov     ebx, eax
0x1800bdb96  test    eax, eax
0x1800bdb98  js      loc_1800BDC45
0x1800bdb9e  xor     r9d, r9d; SecurityDescriptorSize
0x1800bdba1  mov     [rsp+2B0h+SecurityDescriptor], 0
0x1800bdbaa  lea     r8, [rsp+2B0h+SecurityDescriptor]; SecurityDescriptor
0x1800bdbaf  lea     rcx, [rsp+2B0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800bdbb4  lea     edx, [r9+1]; StringSDRevision
0x1800bdbb8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bdbbe  test    eax, eax
0x1800bdbc0  jnz     short loc_1800BDBCD
0x1800bdbc2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bdbc7  mov     ebx, eax
0x1800bdbc9  test    eax, eax
0x1800bdbcb  js      short loc_1800BDC45
0x1800bdbcd  mov     rax, [rsp+2B0h+SecurityDescriptor]
0x1800bdbd2  lea     r9, Class; lpClass
0x1800bdbd9  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1800bdbe2  xor     r8d, r8d; Reserved
0x1800bdbe5  mov     [rsp+2B0h+phkResult], rdi; phkResult
0x1800bdbea  mov     rdx, rsi; lpSubKey
0x1800bdbed  mov     [rsp+2B0h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800bdbf2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bdbf9  lea     rax, [rsp+2B0h+SecurityAttributes]
0x1800bdbfe  mov     qword ptr [rsp+2B0h+SecurityAttributes.nLength], 18h
0x1800bdc07  mov     [rsp+2B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800bdc0c  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x1800bdc14  mov     [rsp+2B0h+dwOptions], 0; dwOptions
0x1800bdc1c  mov     qword ptr [rsp+2B0h+SecurityAttributes.bInheritHandle], 0
0x1800bdc25  call    cs:__imp_RegCreateKeyExW
0x1800bdc2b  mov     ebx, eax
0x1800bdc2d  test    eax, eax
0x1800bdc2f  jle     short loc_1800BDC3A
0x1800bdc31  movzx   ebx, ax
0x1800bdc34  or      ebx, 80070000h
0x1800bdc3a  mov     rcx, [rsp+2B0h+SecurityDescriptor]; hMem
0x1800bdc3f  call    cs:__imp_LocalFree
0x1800bdc45  mov     eax, ebx
0x1800bdc47  mov     rcx, [rbp+1B0h+var_30]
0x1800bdc4e  xor     rcx, rsp; StackCookie
0x1800bdc51  call    __security_check_cookie
0x1800bdc56  add     rsp, 298h
0x1800bdc5d  pop     rdi
0x1800bdc5e  pop     rsi
0x1800bdc5f  pop     rbx
0x1800bdc60  pop     rbp
0x1800bdc61  retn
```
