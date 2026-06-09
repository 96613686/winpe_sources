# QuerySupportProvider(ushort *,_SUPPORT_RESPONSE *)

- ea: `0x140051f74`
- end: `0x140052105`
- name: `?QuerySupportProvider@@YAJPEAGPEAU_SUPPORT_RESPONSE@@@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029730`
- `0x14003dad0`

## callees

- `0x1400070b0`
- `0x140050354`
- `0x140051e48`
- `0x140051f74`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140052024`
- `ADVAPI32!RegOpenKeyExW` at `0x140052024`
- `ADVAPI32!RegCloseKey` at `0x1400520ec`
- `ADVAPI32!RegCloseKey` at `0x1400520ec`
- `KERNEL32!HeapAlloc` at `0x140051fc2`
- `KERNEL32!HeapAlloc` at `0x140051fc2`
- `KERNEL32!HeapFree` at `0x1400520d6`
- `KERNEL32!HeapFree` at `0x1400520d6`
- `KERNEL32!GetProcessHeap` at `0x140051fab`
- `KERNEL32!GetProcessHeap` at `0x1400520c2`
- `KERNEL32!GetProcessHeap` at `0x140051fab`
- `KERNEL32!GetProcessHeap` at `0x1400520c2`

## string_xrefs

- `0x140052096`: `PrivacyLink`

## pseudocode

```c
__int64 __fastcall QuerySupportProvider(unsigned __int16 *a1, unsigned __int16 **a2)
{
  const unsigned __int16 *v3; // rdx
  signed int RegistryString; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rdi
  LSTATUS v7; // eax
  HANDLE v8; // rax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  v3 = L"Microsoft";
  if ( a1 )
    v3 = a1;
  RegistryString = AssignString(a2 + 3, v3);
  if ( RegistryString >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
    if ( v6 )
    {
      *v6 = 0;
      RegistryString = StringCchPrintfW(v6, 0x400u, L"Software\\Microsoft\\MSDE\\Support\\%s\\", a2[3]);
      if ( RegistryString >= 0 )
      {
        v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey);
        RegistryString = v7;
        if ( !v7 )
          goto LABEL_11;
        if ( v7 > 0 )
          RegistryString = (unsigned __int16)v7 | 0x80070000;
        if ( RegistryString >= 0 )
        {
LABEL_11:
          RegistryString = QueryRegistryString(hKey, L"DisplayName", a2 + 5, 1);
          if ( RegistryString >= 0 )
          {
            RegistryString = QueryRegistryString(hKey, L"URL", a2 + 4, 1);
            if ( RegistryString >= 0 )
            {
              RegistryString = QueryRegistryString(hKey, L"PrivacyLink", a2 + 6, 1);
              if ( RegistryString >= 0 )
                RegistryString = QueryRegistryString(hKey, L"Icon", a2 + 7, 0);
            }
          }
        }
      }
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v6);
    }
    else
    {
      RegistryString = -2147024882;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)RegistryString;
}

```

## disassembly

```asm
0x140051f74  push    rbx
0x140051f76  push    rsi
0x140051f77  push    rdi
0x140051f78  push    r14
0x140051f7a  sub     rsp, 38h
0x140051f7e  mov     rsi, rdx
0x140051f81  mov     [rsp+58h+hKey], 0
0x140051f8a  test    rcx, rcx
0x140051f8d  lea     rdx, aMicrosoft; "Microsoft"
0x140051f94  cmovnz  rdx, rcx; unsigned __int16 *
0x140051f98  lea     rcx, [rsi+18h]; unsigned __int16 **
0x140051f9c  call    ?AssignString@@YAJPEAPEAGPEBG@Z; AssignString(ushort * *,ushort const *)
0x140051fa1  mov     ebx, eax
0x140051fa3  test    eax, eax
0x140051fa5  js      loc_1400520E2
0x140051fab  call    cs:__imp_GetProcessHeap
0x140051fb2  nop     dword ptr [rax+rax+00h]
0x140051fb7  xor     edx, edx; dwFlags
0x140051fb9  mov     r8d, 800h; dwBytes
0x140051fbf  mov     rcx, rax; hHeap
0x140051fc2  call    cs:__imp_HeapAlloc
0x140051fc9  nop     dword ptr [rax+rax+00h]
0x140051fce  mov     rdi, rax
0x140051fd1  test    rax, rax
0x140051fd4  jnz     short loc_140051FE0
0x140051fd6  mov     ebx, 8007000Eh
0x140051fdb  jmp     loc_1400520E2
0x140051fe0  xor     eax, eax
0x140051fe2  lea     r8, aSoftwareMicros_3; "Software\\Microsoft\\MSDE\\Support\\%s"...
0x140051fe9  mov     [rdi], ax
0x140051fec  mov     edx, 400h; unsigned __int64
0x140051ff1  mov     r9, [rsi+18h]
0x140051ff5  mov     rcx, rdi; unsigned __int16 *
0x140051ff8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140051ffd  mov     ebx, eax
0x140051fff  test    eax, eax
0x140052001  js      loc_1400520C2
0x140052007  lea     rax, [rsp+58h+hKey]
0x14005200c  mov     r9d, 20019h; samDesired
0x140052012  xor     r8d, r8d; ulOptions
0x140052015  mov     [rsp+58h+phkResult], rax; phkResult
0x14005201a  mov     rdx, rdi; lpSubKey
0x14005201d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140052024  call    cs:__imp_RegOpenKeyExW
0x14005202b  nop     dword ptr [rax+rax+00h]
0x140052030  mov     ebx, eax
0x140052032  test    eax, eax
0x140052034  jz      short loc_140052045
0x140052036  jle     short loc_140052041
0x140052038  movzx   ebx, ax
0x14005203b  or      ebx, 80070000h
0x140052041  test    ebx, ebx
0x140052043  js      short loc_1400520C2
0x140052045  mov     rcx, [rsp+58h+hKey]; hKey
0x14005204a  lea     r8, [rsi+28h]; unsigned __int16 **
0x14005204e  mov     r9d, 1; int
0x140052054  lea     rdx, aDisplayname; "DisplayName"
0x14005205b  call    ?QueryRegistryString@@YAJPEAUHKEY__@@PEAGPEAPEAGH@Z; QueryRegistryString(HKEY__ *,ushort *,ushort * *,int)
0x140052060  mov     ebx, eax
0x140052062  test    eax, eax
0x140052064  js      short loc_1400520C2
0x140052066  mov     rcx, [rsp+58h+hKey]; hKey
0x14005206b  lea     r8, [rsi+20h]; unsigned __int16 **
0x14005206f  mov     r9d, 1; int
0x140052075  lea     rdx, aUrl; "URL"
0x14005207c  call    ?QueryRegistryString@@YAJPEAUHKEY__@@PEAGPEAPEAGH@Z; QueryRegistryString(HKEY__ *,ushort *,ushort * *,int)
0x140052081  mov     ebx, eax
0x140052083  test    eax, eax
0x140052085  js      short loc_1400520C2
0x140052087  mov     rcx, [rsp+58h+hKey]; hKey
0x14005208c  lea     r8, [rsi+30h]; unsigned __int16 **
0x140052090  mov     r9d, 1; int
0x140052096  lea     rdx, aPrivacylink; "PrivacyLink"
0x14005209d  call    ?QueryRegistryString@@YAJPEAUHKEY__@@PEAGPEAPEAGH@Z; QueryRegistryString(HKEY__ *,ushort *,ushort * *,int)
0x1400520a2  mov     ebx, eax
0x1400520a4  test    eax, eax
0x1400520a6  js      short loc_1400520C2
0x1400520a8  mov     rcx, [rsp+58h+hKey]; hKey
0x1400520ad  lea     r8, [rsi+38h]; unsigned __int16 **
0x1400520b1  xor     r9d, r9d; int
0x1400520b4  lea     rdx, aIcon; "Icon"
0x1400520bb  call    ?QueryRegistryString@@YAJPEAUHKEY__@@PEAGPEAPEAGH@Z; QueryRegistryString(HKEY__ *,ushort *,ushort * *,int)
0x1400520c0  mov     ebx, eax
0x1400520c2  call    cs:__imp_GetProcessHeap
0x1400520c9  nop     dword ptr [rax+rax+00h]
0x1400520ce  mov     r8, rdi; lpMem
0x1400520d1  xor     edx, edx; dwFlags
0x1400520d3  mov     rcx, rax; hHeap
0x1400520d6  call    cs:__imp_HeapFree
0x1400520dd  nop     dword ptr [rax+rax+00h]
0x1400520e2  mov     rcx, [rsp+58h+hKey]; hKey
0x1400520e7  test    rcx, rcx
0x1400520ea  jz      short loc_1400520F8
0x1400520ec  call    cs:__imp_RegCloseKey
0x1400520f3  nop     dword ptr [rax+rax+00h]
0x1400520f8  mov     eax, ebx
0x1400520fa  add     rsp, 38h
0x1400520fe  pop     r14
0x140052100  pop     rdi
0x140052101  pop     rsi
0x140052102  pop     rbx
0x140052103  retn
```
