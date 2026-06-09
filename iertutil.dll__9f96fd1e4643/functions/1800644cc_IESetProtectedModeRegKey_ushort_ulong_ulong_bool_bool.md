# IESetProtectedModeRegKey(ushort *,ulong,ulong,bool,bool)

- ea: `0x1800644cc`
- end: `0x180064642`
- name: `?IESetProtectedModeRegKey@@YAJPEAGKK_N1@Z`
- size: `374`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned int, bool, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800517b4`
- `0x180051bb0`
- `0x1800644cc`

## callees

- `0x180021d38`
- `0x1800644cc`
- `0x180064648`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006453f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006453f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800645a3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800645a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006461c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006461c`

## pseudocode

```c
__int64 __fastcall IESetProtectedModeRegKey(unsigned __int16 *a1, unsigned int a2, unsigned int a3, char a4, bool a5)
{
  int v9; // ebx
  LSTATUS v10; // eax
  DWORD v11; // edi
  LSTATUS v12; // eax
  DWORD cchName; // [rsp+40h] [rbp-648h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-640h] BYREF
  WCHAR Name[256]; // [rsp+50h] [rbp-638h] BYREF
  WCHAR SubKey[512]; // [rsp+250h] [rbp-438h] BYREF

  v9 = IESetProtectedModeRegKeyOnly(a1, a2, a3);
  if ( v9 >= 0 && (a5 || a4) )
  {
    hKey = 0;
    v10 = RegOpenKeyExW(HKEY_CURRENT_USER, a1, 0, 0x20019u, &hKey);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v9 >= 0 )
    {
      v11 = 0;
      while ( v9 >= 0 )
      {
        cchName = 255;
        v12 = RegEnumKeyExW(hKey, v11, Name, &cchName, 0, 0, 0, 0);
        v9 = v12;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( v9 < 0 )
        {
          if ( v9 == -2147024637 )
          {
            v9 = 0;
            break;
          }
        }
        else
        {
          v9 = StringCchPrintfW(SubKey, 0x1FEu, L"%s\\%s", a1, Name);
          if ( v9 >= 0 )
            v9 = IESetProtectedModeRegKey(SubKey, a2, a3, 1, 1);
        }
        ++v11;
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800644cc  push    rbx
0x1800644ce  push    rbp
0x1800644cf  push    rsi
0x1800644d0  push    rdi
0x1800644d1  push    r14
0x1800644d3  sub     rsp, 660h
0x1800644da  mov     rax, cs:__security_cookie
0x1800644e1  xor     rax, rsp
0x1800644e4  mov     [rsp+688h+var_38], rax
0x1800644ec  mov     dil, r9b
0x1800644ef  mov     r14d, r8d
0x1800644f2  mov     ebp, edx
0x1800644f4  mov     rsi, rcx
0x1800644f7  call    ?IESetProtectedModeRegKeyOnly@@YAJPEAGKK@Z; IESetProtectedModeRegKeyOnly(ushort *,ulong,ulong)
0x1800644fc  mov     ebx, eax
0x1800644fe  test    eax, eax
0x180064500  js      loc_180064622
0x180064506  cmp     [rsp+688h+arg_20], 0
0x18006450e  jnz     short loc_180064519
0x180064510  test    dil, dil
0x180064513  jz      loc_180064622
0x180064519  lea     rax, [rsp+688h+hKey]
0x18006451e  mov     [rsp+688h+hKey], 0
0x180064527  mov     r9d, 20019h; samDesired
0x18006452d  mov     [rsp+688h+phkResult], rax; phkResult
0x180064532  xor     r8d, r8d; ulOptions
0x180064535  mov     rdx, rsi; lpSubKey
0x180064538  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006453f  call    cs:__imp_RegOpenKeyExW
0x180064545  mov     ebx, eax
0x180064547  test    eax, eax
0x180064549  jle     short loc_180064554
0x18006454b  movzx   ebx, ax
0x18006454e  or      ebx, 80070000h
0x180064554  test    ebx, ebx
0x180064556  js      loc_180064622
0x18006455c  xor     edi, edi
0x18006455e  test    ebx, ebx
0x180064560  js      loc_180064617
0x180064566  mov     rcx, [rsp+688h+hKey]; hKey
0x18006456b  lea     r9, [rsp+688h+cchName]; lpcchName
0x180064570  mov     [rsp+688h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180064579  lea     r8, [rsp+688h+Name]; lpName
0x18006457e  mov     [rsp+688h+lpcchClass], 0; lpcchClass
0x180064587  mov     edx, edi; dwIndex
0x180064589  mov     [rsp+688h+lpClass], 0; lpClass
0x180064592  mov     [rsp+688h+phkResult], 0; lpReserved
0x18006459b  mov     [rsp+688h+cchName], 0FFh
0x1800645a3  call    cs:__imp_RegEnumKeyExW
0x1800645a9  mov     ebx, eax
0x1800645ab  test    eax, eax
0x1800645ad  jle     short loc_1800645B8
0x1800645af  movzx   ebx, ax
0x1800645b2  or      ebx, 80070000h
0x1800645b8  test    ebx, ebx
0x1800645ba  js      short loc_180064606
0x1800645bc  lea     rax, [rsp+688h+Name]
0x1800645c1  mov     r9, rsi
0x1800645c4  lea     r8, Format; "%s\\%s"
0x1800645cb  mov     [rsp+688h+phkResult], rax
0x1800645d0  mov     edx, 1FEh; unsigned __int64
0x1800645d5  lea     rcx, [rsp+688h+SubKey]; unsigned __int16 *
0x1800645dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800645e2  mov     ebx, eax
0x1800645e4  test    eax, eax
0x1800645e6  js      short loc_18006460E
0x1800645e8  mov     r9b, 1; bool
0x1800645eb  mov     byte ptr [rsp+688h+phkResult], 1; bool
0x1800645f0  mov     r8d, r14d; unsigned int
0x1800645f3  lea     rcx, [rsp+688h+SubKey]; unsigned __int16 *
0x1800645fb  mov     edx, ebp; unsigned int
0x1800645fd  call    ?IESetProtectedModeRegKey@@YAJPEAGKK_N1@Z; IESetProtectedModeRegKey(ushort *,ulong,ulong,bool,bool)
0x180064602  mov     ebx, eax
0x180064604  jmp     short loc_18006460E
0x180064606  cmp     ebx, 80070103h
0x18006460c  jz      short loc_180064615
0x18006460e  inc     edi
0x180064610  jmp     loc_18006455E
0x180064615  xor     ebx, ebx
0x180064617  mov     rcx, [rsp+688h+hKey]; hKey
0x18006461c  call    cs:__imp_RegCloseKey
0x180064622  mov     eax, ebx
0x180064624  mov     rcx, [rsp+688h+var_38]
0x18006462c  xor     rcx, rsp; StackCookie
0x18006462f  call    __security_check_cookie
0x180064634  add     rsp, 660h
0x18006463b  pop     r14
0x18006463d  pop     rdi
0x18006463e  pop     rsi
0x18006463f  pop     rbp
0x180064640  pop     rbx
0x180064641  retn
```
