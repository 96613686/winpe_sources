# DeleteRegSubtree(HKEY__ *,wchar_t const *)

- ea: `0x18000c690`
- end: `0x18000c789`
- name: `?DeleteRegSubtree@@YAXPEAUHKEY__@@PEB_W@Z`
- size: `249`
- prototype: `void __fastcall(HKEY, const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c690`
- `0x180011470`

## callees

- `0x1800024a0`
- `0x18000c690`
- `0x180014394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c74d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c74d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000c73e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000c73e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c75f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000c75f`

## pseudocode

```c
void __fastcall DeleteRegSubtree(HKEY a1, const wchar_t *a2, unsigned int a3)
{
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchName = 0;
  ftLastWriteTime = 0;
  hKey = 0;
  if ( !(unsigned int)WSearchRegOpenKey(a1, a2, a3, 0xF003Fu, &hKey) )
  {
    while ( 1 )
    {
      cchName = 260;
      if ( RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      DeleteRegSubtree(hKey, Name);
    }
    RegCloseKey(hKey);
    RegDeleteKeyExW(a1, a2, 0, 0);
  }
}

```

## disassembly

```asm
0x18000c690  mov     [rsp-8+arg_10], rbx
0x18000c695  mov     [rsp-8+arg_18], rdi
0x18000c69a  push    rbp
0x18000c69b  lea     rbp, [rsp-180h]
0x18000c6a3  sub     rsp, 280h
0x18000c6aa  mov     rax, cs:__security_cookie
0x18000c6b1  xor     rax, rsp
0x18000c6b4  mov     [rbp+180h+var_10], rax
0x18000c6bb  lea     rax, [rsp+280h+hKey]
0x18000c6c0  mov     [rsp+280h+cchName], 0
0x18000c6c8  mov     r9d, 0F003Fh; unsigned int
0x18000c6ce  mov     [rsp+280h+lpReserved], rax; HKEY *
0x18000c6d3  mov     rdi, rdx
0x18000c6d6  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x18000c6df  mov     rbx, rcx
0x18000c6e2  mov     [rsp+280h+hKey], 0
0x18000c6eb  call    ?WSearchRegOpenKey@@YAJPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; WSearchRegOpenKey(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x18000c6f0  test    eax, eax
0x18000c6f2  jnz     short loc_18000C765
0x18000c6f4  jmp     short loc_18000C700
0x18000c6f6  lea     rdx, [rsp+280h+Name]; wchar_t *
0x18000c6fb  call    ?DeleteRegSubtree@@YAXPEAUHKEY__@@PEB_W@Z; DeleteRegSubtree(HKEY__ *,wchar_t const *)
0x18000c700  mov     rcx, [rsp+280h+hKey]; hKey
0x18000c705  lea     rax, [rsp+280h+ftLastWriteTime]
0x18000c70a  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000c70f  lea     r9, [rsp+280h+cchName]; lpcchName
0x18000c714  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x18000c71d  lea     r8, [rsp+280h+Name]; lpName
0x18000c722  mov     [rsp+280h+lpClass], 0; lpClass
0x18000c72b  xor     edx, edx; dwIndex
0x18000c72d  mov     [rsp+280h+lpReserved], 0; lpReserved
0x18000c736  mov     [rsp+280h+cchName], 104h
0x18000c73e  call    cs:__imp_RegEnumKeyExW
0x18000c744  mov     rcx, [rsp+280h+hKey]; HKEY
0x18000c749  test    eax, eax
0x18000c74b  jz      short loc_18000C6F6
0x18000c74d  call    cs:__imp_RegCloseKey
0x18000c753  xor     r9d, r9d; Reserved
0x18000c756  xor     r8d, r8d; samDesired
0x18000c759  mov     rdx, rdi; lpSubKey
0x18000c75c  mov     rcx, rbx; hKey
0x18000c75f  call    cs:__imp_RegDeleteKeyExW
0x18000c765  mov     rcx, [rbp+180h+var_10]
0x18000c76c  xor     rcx, rsp; StackCookie
0x18000c76f  call    __security_check_cookie
0x18000c774  lea     r11, [rsp+280h+var_s0]
0x18000c77c  mov     rbx, [r11+20h]
0x18000c780  mov     rdi, [r11+28h]
0x18000c784  mov     rsp, r11
0x18000c787  pop     rbp
0x18000c788  retn
```
