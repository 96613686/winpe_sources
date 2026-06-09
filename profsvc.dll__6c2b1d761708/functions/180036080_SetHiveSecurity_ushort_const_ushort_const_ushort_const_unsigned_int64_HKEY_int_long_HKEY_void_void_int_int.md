# SetHiveSecurity_(ushort const *,ushort const *,ushort const *,unsigned __int64,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x180036080`
- end: `0x1800361be`
- name: `?SetHiveSecurity_@@YAJPEBG00_KPEAUHKEY__@@HP6AJ2PEAX3HH@Z@Z`
- size: `318`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, HKEY, int, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029804`
- `0x180039ce0`
- `0x180041618`
- `0x180041678`
- `0x18004a8b8`

## callees

- `0x180005370`
- `0x180011c00`
- `0x1800172e0`
- `0x180027220`
- `0x180036080`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003618b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003619c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003618b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003619c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800360ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003613b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800360ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003613b`

## pseudocode

```c
__int64 __fastcall SetHiveSecurity_(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        HKEY a5,
        int a6,
        int (*a7)(HKEY, void *, void *, int, int))
{
  int v11; // ebx
  const unsigned __int16 *v12; // r8
  WCHAR *v13; // rdi
  BOOL v14; // eax
  BOOL v15; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR StringSecurityDescriptor[6]; // [rsp+38h] [rbp-30h] BYREF

  StringSecurityDescriptor[0] = 0;
  v11 = ResultFromHeapAllocArray<unsigned short>(a4, StringSecurityDescriptor);
  if ( v11 >= 0 )
  {
    v12 = a2;
    v13 = (WCHAR *)StringSecurityDescriptor[0];
    v11 = StringCchPrintfW((unsigned __int16 *)StringSecurityDescriptor[0], a4, v12, a1);
    if ( v11 >= 0 )
    {
      StringSecurityDescriptor[0] = 0;
      v14 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              v13,
              1u,
              (PSECURITY_DESCRIPTOR *)StringSecurityDescriptor,
              0);
      v11 = ResultFromWin32Bool(v14);
      if ( v11 >= 0 )
      {
        SecurityDescriptor = 0;
        v11 = StringCchPrintfW(v13, a4, a3, a1);
        if ( v11 >= 0 )
        {
          v15 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v13, 1u, &SecurityDescriptor, 0);
          v11 = ResultFromWin32Bool(v15);
          if ( v11 >= 0 )
          {
            v11 = ((__int64 (__fastcall *)(HKEY, LPCWSTR, PSECURITY_DESCRIPTOR, __int64, int))a7)(
                    a5,
                    StringSecurityDescriptor[0],
                    SecurityDescriptor,
                    1,
                    a6);
            LocalFree(SecurityDescriptor);
          }
        }
        LocalFree((HLOCAL)StringSecurityDescriptor[0]);
      }
    }
    ResultFromHeapFree(v13);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180036080  push    rbx
0x180036082  push    rbp
0x180036083  push    rsi
0x180036084  push    rdi
0x180036085  push    r14
0x180036087  sub     rsp, 40h
0x18003608b  mov     rdi, rdx
0x18003608e  mov     [rsp+68h+StringSecurityDescriptor], 0
0x180036097  mov     rbp, rcx
0x18003609a  lea     rdx, [rsp+68h+StringSecurityDescriptor]
0x18003609f  mov     rcx, r9
0x1800360a2  mov     rsi, r9
0x1800360a5  mov     r14, r8
0x1800360a8  call    ??$ResultFromHeapAllocArray@G@@YAJ_KPEAPEAG@Z; ResultFromHeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x1800360ad  mov     ebx, eax
0x1800360af  test    eax, eax
0x1800360b1  js      loc_1800361B0
0x1800360b7  mov     r8, rdi; unsigned __int16 *
0x1800360ba  mov     r9, rbp
0x1800360bd  mov     rdi, [rsp+68h+StringSecurityDescriptor]
0x1800360c2  mov     rdx, rsi; unsigned __int64
0x1800360c5  mov     rcx, rdi; unsigned __int16 *
0x1800360c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800360cd  mov     ebx, eax
0x1800360cf  test    eax, eax
0x1800360d1  js      loc_1800361A8
0x1800360d7  xor     r9d, r9d; SecurityDescriptorSize
0x1800360da  mov     [rsp+68h+StringSecurityDescriptor], 0
0x1800360e3  lea     r8, [rsp+68h+StringSecurityDescriptor]; SecurityDescriptor
0x1800360e8  mov     rcx, rdi; StringSecurityDescriptor
0x1800360eb  lea     edx, [r9+1]; StringSDRevision
0x1800360ef  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800360f6  nop     dword ptr [rax+rax+00h]
0x1800360fb  mov     ecx, eax; int
0x1800360fd  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x180036102  mov     ebx, eax
0x180036104  test    eax, eax
0x180036106  js      loc_1800361A8
0x18003610c  mov     r9, rbp
0x18003610f  mov     [rsp+68h+SecurityDescriptor], 0
0x180036118  mov     r8, r14; unsigned __int16 *
0x18003611b  mov     rdx, rsi; unsigned __int64
0x18003611e  mov     rcx, rdi; unsigned __int16 *
0x180036121  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036126  mov     ebx, eax
0x180036128  test    eax, eax
0x18003612a  js      short loc_180036197
0x18003612c  xor     r9d, r9d; SecurityDescriptorSize
0x18003612f  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x180036134  mov     rcx, rdi; StringSecurityDescriptor
0x180036137  lea     edx, [r9+1]; StringSDRevision
0x18003613b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180036142  nop     dword ptr [rax+rax+00h]
0x180036147  mov     ecx, eax; int
0x180036149  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18003614e  mov     ebx, eax
0x180036150  test    eax, eax
0x180036152  js      short loc_180036197
0x180036154  mov     ecx, [rsp+68h+arg_28]
0x18003615b  mov     r9d, 1
0x180036161  mov     r8, [rsp+68h+SecurityDescriptor]
0x180036166  mov     rdx, [rsp+68h+StringSecurityDescriptor]
0x18003616b  mov     rax, [rsp+68h+arg_30]
0x180036173  mov     [rsp+68h+var_48], ecx
0x180036177  mov     rcx, [rsp+68h+arg_20]
0x18003617f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036184  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x180036189  mov     ebx, eax
0x18003618b  call    cs:__imp_LocalFree
0x180036192  nop     dword ptr [rax+rax+00h]
0x180036197  mov     rcx, [rsp+68h+StringSecurityDescriptor]; hMem
0x18003619c  call    cs:__imp_LocalFree
0x1800361a3  nop     dword ptr [rax+rax+00h]
0x1800361a8  mov     rcx, rdi; lpMem
0x1800361ab  call    ?ResultFromHeapFree@@YAJPEAX@Z; ResultFromHeapFree(void *)
0x1800361b0  mov     eax, ebx
0x1800361b2  add     rsp, 40h
0x1800361b6  pop     r14
0x1800361b8  pop     rdi
0x1800361b9  pop     rsi
0x1800361ba  pop     rbp
0x1800361bb  pop     rbx
0x1800361bc  retn
```
